mod_diary - simple blog system for Apache HTTPD Server
======================================================

# Demo Blog

http://www.cuspy.org/diary/

## Dependencies

 * discount
     - http://www.pell.portland.or.us/~orc/Code/discount/

 * ClearSilver
     - http://www.clearsilver.net/

In debian:
    # apt-get install libmarkdown2-dev clearsilver-dev

# Build

    % autoreconf -i
    % ./configure --with-apxs=<APXS_PATH> \
        --with-discount=<DISCOUNT_DIR> \
        --with-clearsilver=<CLEARSILVER_DIR>
    % make
    # make install

# Configration

httpd.conf

    LoadModule diary_module modules/mod_diary.so
    <Location />
      SetHandler diary
      DiaryTitle "Example Diary"
      DiaryURI http://www.example.com/diary/
      DiaryData /path/to/diary
    </Location>

You can specify `DiaryTheme` if you want to use custom theme.

# Author

HAMANO Tsukasa <http://twitter.com/hamano>
