# Debian Packages

Created using [Reprepro](http://mirrorer.alioth.debian.org/). Add
Debian packages using:

	$ reprepro includedeb precise ../path/to/some/package_version_architecture.deb

Add the packages to your Ubuntu or Debian box by checking out this Git
repository. Then add APT sources to your configuration as follows.

	deb file:/path/to/your/debian precise main
	deb-src file:/path/to/your/debian precise main

You can add both of these simultaneously on Ubuntu using Ubuntu's
Software Centre. Select the Edit menu, Software Sources. Then under
Other Sources, add `deb file:/path/to/your/debian precise main` as
your new APT line. This automatically adds the `deb-src` line as well.

Finally, don't forget to update the APT cache using:

	$ sudo apt-get update

You can now install packages from this source using:

	sudo apt-get install --allow-unauthenticated ta-lib-dev

You need to allow unauthenticated packages. This package source does
not currently include GPG signing.
