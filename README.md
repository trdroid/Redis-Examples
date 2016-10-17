# Redis

### Links

http://redis.io/

Source code

https://github.com/antirez/redis

Download 

http://redis.io/download

### Setup

**Ubuntu**

*Version 14.04.1*

Instructions are available at http://redis.io/download

Downloaded the stable release version 3.2.4 from http://redis.io/download

```sh
~/software/Redis/redis-3.2.4$ make
cd src && make all
make[1]: Entering directory `/home/droid/software/Redis/redis-3.2.4/src'
rm -rf redis-server redis-sentinel redis-cli redis-benchmark redis-check-rdb redis-check-aof *.o *.gcda *.gcno *.gcov redis.info lcov-html
(cd ../deps && make distclean)
make[2]: Entering directory `/home/droid/software/Redis/redis-3.2.4/deps'
(cd hiredis && make clean) > /dev/null || true
(cd linenoise && make clean) > /dev/null || true
(cd lua && make clean) > /dev/null || true
(cd geohash-int && make clean) > /dev/null || true
(cd jemalloc && [ -f Makefile ] && make distclean) > /dev/null || true
(rm -f .make-*)
make[2]: Leaving directory `/home/droid/software/Redis/redis-3.2.4/deps'
(rm -f .make-*)
echo STD=-std=c99 -pedantic -DREDIS_STATIC='' >> .make-settings
echo WARN=-Wall -W >> .make-settings
echo OPT=-O2 >> .make-settings
echo MALLOC=jemalloc >> .make-settings
echo CFLAGS= >> .make-settings
echo LDFLAGS= >> .make-settings
echo REDIS_CFLAGS= >> .make-settings
echo REDIS_LDFLAGS= >> .make-settings
echo PREV_FINAL_CFLAGS=-std=c99 -pedantic -DREDIS_STATIC='' -Wall -W -O2 -g -ggdb   -I../deps/geohash-int -I../deps/hiredis -I../deps/linenoise -I../deps/lua/src -DUSE_JEMALLOC -I../deps/jemalloc/include >> .make-settings
echo PREV_FINAL_LDFLAGS=  -g -ggdb -rdynamic >> .make-settings
(cd ../deps && make hiredis linenoise lua geohash-int jemalloc)
make[2]: Entering directory `/home/droid/software/Redis/redis-3.2.4/deps'
(cd hiredis && make clean) > /dev/null || true
(cd linenoise && make clean) > /dev/null || true
(cd lua && make clean) > /dev/null || true
(cd geohash-int && make clean) > /dev/null || true
(cd jemalloc && [ -f Makefile ] && make distclean) > /dev/null || true
(rm -f .make-*)
(echo "" > .make-ldflags)
(echo "" > .make-cflags)
MAKE hiredis
cd hiredis && make static
make[3]: Entering directory `/home/droid/software/Redis/redis-3.2.4/deps/hiredis'
cc -std=c99 -pedantic -c -O3 -fPIC  -Wall -W -Wstrict-prototypes -Wwrite-strings -g -ggdb  net.c
cc -std=c99 -pedantic -c -O3 -fPIC  -Wall -W -Wstrict-prototypes -Wwrite-strings -g -ggdb  hiredis.c
cc -std=c99 -pedantic -c -O3 -fPIC  -Wall -W -Wstrict-prototypes -Wwrite-strings -g -ggdb  sds.c
cc -std=c99 -pedantic -c -O3 -fPIC  -Wall -W -Wstrict-prototypes -Wwrite-strings -g -ggdb  async.c
ar rcs libhiredis.a net.o hiredis.o sds.o async.o
make[3]: Leaving directory `/home/droid/software/Redis/redis-3.2.4/deps/hiredis'
MAKE linenoise
cd linenoise && make
make[3]: Entering directory `/home/droid/software/Redis/redis-3.2.4/deps/linenoise'
cc  -Wall -Os -g  -c linenoise.c
make[3]: Leaving directory `/home/droid/software/Redis/redis-3.2.4/deps/linenoise'
MAKE lua
cd lua/src && make all CFLAGS="-O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC='' " MYLDFLAGS="" AR="ar rcu"
make[3]: Entering directory `/home/droid/software/Redis/redis-3.2.4/deps/lua/src'
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lapi.o lapi.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lcode.o lcode.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o ldebug.o ldebug.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o ldo.o ldo.c
ldo.c: In function ‘f_parser’:
ldo.c:496:7: warning: unused variable ‘c’ [-Wunused-variable]
   int c = luaZ_lookahead(p->z);
       ^
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o ldump.o ldump.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lfunc.o lfunc.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lgc.o lgc.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o llex.o llex.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lmem.o lmem.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lobject.o lobject.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lopcodes.o lopcodes.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lparser.o lparser.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lstate.o lstate.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lstring.o lstring.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o ltable.o ltable.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o ltm.o ltm.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lundump.o lundump.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lvm.o lvm.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lzio.o lzio.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o strbuf.o strbuf.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o fpconv.o fpconv.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lauxlib.o lauxlib.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lbaselib.o lbaselib.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o ldblib.o ldblib.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o liolib.o liolib.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lmathlib.o lmathlib.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o loslib.o loslib.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o ltablib.o ltablib.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lstrlib.o lstrlib.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o loadlib.o loadlib.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o linit.o linit.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lua_cjson.o lua_cjson.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lua_struct.o lua_struct.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lua_cmsgpack.o lua_cmsgpack.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lua_bit.o lua_bit.c
ar rcu liblua.a lapi.o lcode.o ldebug.o ldo.o ldump.o lfunc.o lgc.o llex.o lmem.o lobject.o lopcodes.o lparser.o lstate.o lstring.o ltable.o ltm.o lundump.o lvm.o lzio.o strbuf.o fpconv.o lauxlib.o lbaselib.o ldblib.o liolib.o lmathlib.o loslib.o ltablib.o lstrlib.o loadlib.o linit.o lua_cjson.o lua_struct.o lua_cmsgpack.o lua_bit.o	# DLL needs all object files
ranlib liblua.a
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o lua.o lua.c
cc -o lua  lua.o liblua.a -lm 
liblua.a(loslib.o): In function `os_tmpname':
loslib.c:(.text+0x29c): warning: the use of `tmpnam' is dangerous, better use `mkstemp'
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o luac.o luac.c
cc -O2 -Wall -DLUA_ANSI -DENABLE_CJSON_GLOBAL -DREDIS_STATIC=''    -c -o print.o print.c
cc -o luac  luac.o print.o liblua.a -lm 
make[3]: Leaving directory `/home/droid/software/Redis/redis-3.2.4/deps/lua/src'
MAKE geohash-int
cd geohash-int && make
make[3]: Entering directory `/home/droid/software/Redis/redis-3.2.4/deps/geohash-int'
cc  -Wall -O2 -g  -c geohash.c
cc  -Wall -O2 -g  -c geohash_helper.c
make[3]: Leaving directory `/home/droid/software/Redis/redis-3.2.4/deps/geohash-int'
MAKE jemalloc
cd jemalloc && ./configure --with-lg-quantum=3 --with-jemalloc-prefix=je_ --enable-cc-silence CFLAGS="-std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops " LDFLAGS=""
checking for xsltproc... /usr/bin/xsltproc
checking for gcc... gcc
checking whether the C compiler works... yes
checking for C compiler default output file name... a.out
checking for suffix of executables... 
checking whether we are cross compiling... no
checking for suffix of object files... o
checking whether we are using the GNU C compiler... yes
checking whether gcc accepts -g... yes
checking for gcc option to accept ISO C89... none needed
checking how to run the C preprocessor... gcc -E
checking for grep that handles long lines and -e... /bin/grep
checking for egrep... /bin/grep -E
checking for ANSI C header files... yes
checking for sys/types.h... yes
checking for sys/stat.h... yes
checking for stdlib.h... yes
checking for string.h... yes
checking for memory.h... yes
checking for strings.h... yes
checking for inttypes.h... yes
checking for stdint.h... yes
checking for unistd.h... yes
checking whether byte ordering is bigendian... no
checking size of void *... 8
checking size of int... 4
checking size of long... 8
checking size of intmax_t... 8
checking build system type... x86_64-unknown-linux-gnu
checking host system type... x86_64-unknown-linux-gnu
checking whether pause instruction is compilable... yes
checking for ar... ar
checking malloc.h usability... yes
checking malloc.h presence... yes
checking for malloc.h... yes
checking whether malloc_usable_size definition can use const argument... no
checking whether __attribute__ syntax is compilable... yes
checking whether compiler supports -fvisibility=hidden... yes
checking whether compiler supports -Werror... yes
checking whether tls_model attribute is compilable... yes
checking whether compiler supports -Werror... yes
checking whether alloc_size attribute is compilable... yes
checking whether compiler supports -Werror... yes
checking whether format(gnu_printf, ...) attribute is compilable... yes
checking whether compiler supports -Werror... yes
checking whether format(printf, ...) attribute is compilable... yes
checking for a BSD-compatible install... /usr/bin/install -c
checking for ranlib... ranlib
checking for ld... /usr/bin/ld
checking for autoconf... /usr/bin/autoconf
checking for memalign... yes
checking for valloc... yes
checking configured backtracing method... N/A
checking for sbrk... yes
checking whether utrace(2) is compilable... no
checking whether valgrind is compilable... no
checking whether a program using __builtin_ffsl is compilable... yes
checking LG_PAGE... 12
checking pthread.h usability... yes
checking pthread.h presence... yes
checking for pthread.h... yes
checking for pthread_create in -lpthread... yes
checking for library containing clock_gettime... none required
checking for secure_getenv... yes
checking for issetugid... no
checking for _malloc_thread_cleanup... no
checking for _pthread_mutex_init_calloc_cb... no
checking for TLS... yes
checking whether C11 atomics is compilable... no
checking whether atomic(9) is compilable... no
checking whether Darwin OSAtomic*() is compilable... no
checking whether madvise(2) is compilable... yes
checking whether to force 32-bit __sync_{add,sub}_and_fetch()... no
checking whether to force 64-bit __sync_{add,sub}_and_fetch()... no
checking for __builtin_clz... yes
checking whether Darwin OSSpin*() is compilable... no
checking whether glibc malloc hook is compilable... yes
checking whether glibc memalign hook is compilable... yes
checking whether pthreads adaptive mutexes is compilable... yes
checking for stdbool.h that conforms to C99... yes
checking for _Bool... yes
configure: creating ./config.status
config.status: creating Makefile
config.status: creating jemalloc.pc
config.status: creating doc/html.xsl
config.status: creating doc/manpages.xsl
config.status: creating doc/jemalloc.xml
config.status: creating include/jemalloc/jemalloc_macros.h
config.status: creating include/jemalloc/jemalloc_protos.h
config.status: creating include/jemalloc/jemalloc_typedefs.h
config.status: creating include/jemalloc/internal/jemalloc_internal.h
config.status: creating test/test.sh
config.status: creating test/include/test/jemalloc_test.h
config.status: creating config.stamp
config.status: creating bin/jemalloc-config
config.status: creating bin/jemalloc.sh
config.status: creating bin/jeprof
config.status: creating include/jemalloc/jemalloc_defs.h
config.status: creating include/jemalloc/internal/jemalloc_internal_defs.h
config.status: creating test/include/test/jemalloc_test_defs.h
config.status: executing include/jemalloc/internal/private_namespace.h commands
config.status: executing include/jemalloc/internal/private_unnamespace.h commands
config.status: executing include/jemalloc/internal/public_symbols.txt commands
config.status: executing include/jemalloc/internal/public_namespace.h commands
config.status: executing include/jemalloc/internal/public_unnamespace.h commands
config.status: executing include/jemalloc/internal/size_classes.h commands
config.status: executing include/jemalloc/jemalloc_protos_jet.h commands
config.status: executing include/jemalloc/jemalloc_rename.h commands
config.status: executing include/jemalloc/jemalloc_mangle.h commands
config.status: executing include/jemalloc/jemalloc_mangle_jet.h commands
config.status: executing include/jemalloc/jemalloc.h commands
===============================================================================
jemalloc version   : 4.0.3-0-ge9192eacf8935e29fc62fddc2701f7942b1cc02c
library revision   : 2

CONFIG             : --with-lg-quantum=3 --with-jemalloc-prefix=je_ --enable-cc-silence 'CFLAGS=-std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops ' LDFLAGS=
CC                 : gcc
CFLAGS             : -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -fvisibility=hidden
CPPFLAGS           :  -D_GNU_SOURCE -D_REENTRANT
LDFLAGS            : 
EXTRA_LDFLAGS      : 
LIBS               :  -lpthread
TESTLIBS           : 
RPATH_EXTRA        : 

XSLTPROC           : /usr/bin/xsltproc
XSLROOT            : /usr/share/xml/docbook/stylesheet/docbook-xsl

PREFIX             : /usr/local
BINDIR             : /usr/local/bin
DATADIR            : /usr/local/share
INCLUDEDIR         : /usr/local/include
LIBDIR             : /usr/local/lib
MANDIR             : /usr/local/share/man

srcroot            : 
abs_srcroot        : /home/droid/software/Redis/redis-3.2.4/deps/jemalloc/
objroot            : 
abs_objroot        : /home/droid/software/Redis/redis-3.2.4/deps/jemalloc/

JEMALLOC_PREFIX    : je_
JEMALLOC_PRIVATE_NAMESPACE
                   : je_
install_suffix     : 
autogen            : 0
cc-silence         : 1
debug              : 0
code-coverage      : 0
stats              : 1
prof               : 0
prof-libunwind     : 0
prof-libgcc        : 0
prof-gcc           : 0
tcache             : 1
fill               : 1
utrace             : 0
valgrind           : 0
xmalloc            : 0
munmap             : 0
lazy_lock          : 0
tls                : 1
cache-oblivious    : 1
===============================================================================
cd jemalloc && make CFLAGS="-std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops " LDFLAGS="" lib/libjemalloc.a
make[3]: Entering directory `/home/droid/software/Redis/redis-3.2.4/deps/jemalloc'
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/jemalloc.o src/jemalloc.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/arena.o src/arena.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/atomic.o src/atomic.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/base.o src/base.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/bitmap.o src/bitmap.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/chunk.o src/chunk.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/chunk_dss.o src/chunk_dss.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/chunk_mmap.o src/chunk_mmap.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/ckh.o src/ckh.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/ctl.o src/ctl.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/extent.o src/extent.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/hash.o src/hash.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/huge.o src/huge.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/mb.o src/mb.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/mutex.o src/mutex.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/pages.o src/pages.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/prof.o src/prof.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/quarantine.o src/quarantine.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/rtree.o src/rtree.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/stats.o src/stats.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/tcache.o src/tcache.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/util.o src/util.c
gcc -std=gnu99 -Wall -pipe -g3 -O3 -funroll-loops  -c -D_GNU_SOURCE -D_REENTRANT -Iinclude -Iinclude -o src/tsd.o src/tsd.c
ar crus lib/libjemalloc.a src/jemalloc.o src/arena.o src/atomic.o src/base.o src/bitmap.o src/chunk.o src/chunk_dss.o src/chunk_mmap.o src/ckh.o src/ctl.o src/extent.o src/hash.o src/huge.o src/mb.o src/mutex.o src/pages.o src/prof.o src/quarantine.o src/rtree.o src/stats.o src/tcache.o src/util.o src/tsd.o
make[3]: Leaving directory `/home/droid/software/Redis/redis-3.2.4/deps/jemalloc'
make[2]: Leaving directory `/home/droid/software/Redis/redis-3.2.4/deps'
    CC adlist.o
    CC quicklist.o
    CC ae.o
    CC anet.o
    CC dict.o
    CC server.o
    CC sds.o
    CC zmalloc.o
    CC lzf_c.o
    CC lzf_d.o
    CC pqsort.o
    CC zipmap.o
    CC sha1.o
    CC ziplist.o
    CC release.o
    CC networking.o
    CC util.o
    CC object.o
    CC db.o
    CC replication.o
    CC rdb.o
    CC t_string.o
    CC t_list.o
    CC t_set.o
    CC t_zset.o
    CC t_hash.o
    CC config.o
    CC aof.o
    CC pubsub.o
    CC multi.o
    CC debug.o
    CC sort.o
    CC intset.o
    CC syncio.o
    CC cluster.o
    CC crc16.o
    CC endianconv.o
    CC slowlog.o
    CC scripting.o
    CC bio.o
    CC rio.o
    CC rand.o
    CC memtest.o
    CC crc64.o
    CC bitops.o
    CC sentinel.o
    CC notify.o
    CC setproctitle.o
    CC blocked.o
    CC hyperloglog.o
    CC latency.o
    CC sparkline.o
    CC redis-check-rdb.o
    CC geo.o
    LINK redis-server
    INSTALL redis-sentinel
    CC redis-cli.o
    LINK redis-cli
    CC redis-benchmark.o
    LINK redis-benchmark
    INSTALL redis-check-rdb
    CC redis-check-aof.o
    LINK redis-check-aof

Hint: It's a good idea to run 'make test' ;)

make[1]: Leaving directory `/home/droid/software/Redis/redis-3.2.4/src'
```

Running tests

```sh
~/software/Redis/redis-3.2.4$ make test
cd src && make test
make[1]: Entering directory `/home/droid/software/Redis/redis-3.2.4/src'
Cleanup: may take some time... OK
Starting test server at port 11111
[ready]: 32154
Testing unit/printver
[ready]: 32156
Testing unit/dump
[ready]: 32159
Testing unit/auth
[ready]: 32162
Testing unit/protocol
[ready]: 32166
Testing unit/keyspace
[ready]: 32172
Testing unit/scan
[ready]: 32168
Testing unit/type/string
[ready]: 32174
Testing unit/type/incr
[ready]: 32181
Testing unit/type/list
[ready]: 32177
Testing unit/type/list-2
[ready]: 32183
Testing unit/type/list-3
[ready]: 32187
Testing unit/type/set
[ready]: 32189
Testing unit/type/zset
[ready]: 32195
Testing unit/type/hash
[ready]: 32192
Testing unit/sort
[ready]: 32198
Testing unit/expire
Testing Redis version 3.2.4 (00000000)
[ok]: SADD, SCARD, SISMEMBER, SMEMBERS basics - regular set
[ok]: SADD, SCARD, SISMEMBER, SMEMBERS basics - intset
[ok]: SADD against non set
[ok]: SADD a non-integer against an intset
[ok]: SADD an integer larger than 64 bits
[ok]: Explicit regression for a list bug
[ok]: DUMP / RESTORE are able to serialize / unserialize a simple key
[ok]: RESTORE can set an arbitrary expire to the materialized key
[ok]: RESTORE can set an expire that overflows a 32 bit integer
[ok]: RESTORE returns an error of the key already exists
[ok]: RESTORE can overwrite an existing key with REPLACE
[ok]: RESTORE can detect a syntax error for unrecongized options
[ok]: DUMP of non existing key returns nil
[ok]: AUTH fails if there is no password configured server side
[ok]: Check encoding - ziplist
[ok]: ZSET basic ZADD and score update - ziplist
[ok]: ZSET element can't be set to NaN with ZADD - ziplist
[ok]: ZSET element can't be set to NaN with ZINCRBY
[ok]: ZADD with options syntax error with incomplete pair
[ok]: ZADD XX option without key - ziplist
[ok]: ZADD XX existing key - ziplist
[ok]: ZADD XX returns the number of elements actually added
[ok]: ZADD XX updates existing elements score
[ok]: ZADD XX and NX are not compatible
[ok]: ZADD NX with non exisitng key
[ok]: ZADD NX only add new elements without updating old ones
[ok]: ZADD INCR works like ZINCRBY
[ok]: EXPIRE - set timeouts multiple times
[ok]: ZADD INCR works with a single score-elemenet pair
[ok]: ZADD CH option changes return value to all changed elements
[ok]: ZINCRBY calls leading to NaN result in error
[ok]: EXPIRE - It should be still possible to read 'x'
[ok]: ZADD - Variadic version base case
[ok]: ZADD - Return value is the number of actually added items
[ok]: ZADD - Variadic version does not add nothing on single parsing err
[ok]: ZADD - Variadic version will raise error on missing arg
[ok]: ZINCRBY does not work variadic even if shares ZADD implementation
[ok]: ZCARD basics - ziplist
[ok]: ZREM removes key after last element is removed
[ok]: ZREM variadic version
[ok]: HSET/HLEN - Small hash creation
[ok]: ZREM variadic version -- remove elements after key deletion
[ok]: Is the small hash encoded with a ziplist?
[ok]: ZRANGE basics - ziplist
[ok]: ZREVRANGE basics - ziplist
[ok]: ZRANK/ZREVRANK basics - ziplist
[ok]: ZRANK - after deletion - ziplist
[ok]: ZINCRBY - can create a new sorted set - ziplist
[ok]: ZINCRBY - increment and decrement - ziplist
[ok]: ZINCRBY return value
[ok]: INCR against non existing key
[ok]: Regression for quicklist #3343 bug
[ok]: SADD overflows the maximum allowed integers in an intset
[ok]: INCR against key created by incr itself
[ok]: Variadic SADD
[ok]: INCR against key originally set with SET
[ok]: INCR over 32bit value
[ok]: INCRBY over 32bit value with over 32bit increment
[ok]: INCR fails against key with spaces (left)
[ok]: INCR fails against key with spaces (right)
[ok]: INCR fails against key with spaces (both)
[ok]: INCR fails against a key holding a list
[ok]: DECRBY over 32bit value with over 32bit increment, negative res
[ok]: INCR uses shared objects in the 0-9999 range
[ok]: INCR can modify objects in-place
[ok]: INCRBYFLOAT against non existing key
[ok]: INCRBYFLOAT against key originally set with SET
[ok]: INCRBYFLOAT over 32bit value
[ok]: INCRBYFLOAT over 32bit value with over 32bit increment
[ok]: INCRBYFLOAT fails against key with spaces (left)
[ok]: INCRBYFLOAT fails against key with spaces (right)
[ok]: INCRBYFLOAT fails against key with spaces (both)
[ok]: INCRBYFLOAT fails against a key holding a list
[ok]: INCRBYFLOAT does not allow NaN or Infinity
[ok]: INCRBYFLOAT decrement
[ok]: Handle an empty query
[ok]: ZRANGEBYSCORE/ZREVRANGEBYSCORE/ZCOUNT basics
[ok]: SET and GET an item
[ok]: SET and GET an empty item
[ok]: ZRANGEBYSCORE with WITHSCORES
[ok]: DEL against a single item
[ok]: ZRANGEBYSCORE with LIMIT
[ok]: Vararg DEL
[ok]: ZRANGEBYSCORE with LIMIT and WITHSCORES
[ok]: ZRANGEBYSCORE with non-value min or max
[ok]: KEYS with pattern
[ok]: KEYS to get all keys
[ok]: DBSIZE
[ok]: DEL all keys
[ok]: ZRANGEBYLEX/ZREVRANGEBYLEX/ZCOUNT basics
[ok]: Old Ziplist: SORT BY key
[ok]: Old Ziplist: SORT BY key with limit
[ok]: Old Ziplist: SORT BY hash field
[ok]: Negative multibulk length
[ok]: Out of range multibulk length
[ok]: Wrong multibulk payload header
[ok]: Negative multibulk payload length
[ok]: Out of range multibulk payload length
[ok]: Non-number multibulk payload length
[ok]: Multi bulk request not followed by bulk arguments
[ok]: Generic wrong number of args
[ok]: Unbalanced number of quotes
[ok]: ZRANGEBYSLEX with LIMIT
[ok]: ZRANGEBYLEX with invalid lex range specifiers
[ok]: LPUSH, RPUSH, LLENGTH, LINDEX, LPOP - ziplist
[ok]: LPUSH, RPUSH, LLENGTH, LINDEX, LPOP - regular list
[ok]: R/LPOP against empty list
[ok]: Variadic RPUSH/LPUSH
[ok]: DEL a list
[ok]: BLPOP, BRPOP: single existing list - linkedlist
[ok]: BLPOP, BRPOP: multiple existing lists - linkedlist
[ok]: ZREMRANGEBYSCORE basics
[ok]: ZREMRANGEBYSCORE with non-value min or max
[ok]: BLPOP, BRPOP: second list has an entry - linkedlist
[ok]: BRPOPLPUSH - linkedlist
[ok]: SCAN basic
[ok]: BLPOP, BRPOP: single existing list - ziplist
[ok]: BLPOP, BRPOP: multiple existing lists - ziplist
[ok]: BLPOP, BRPOP: second list has an entry - ziplist
[ok]: ZREMRANGEBYRANK basics
[ok]: ZUNIONSTORE against non-existing key doesn't set destination - ziplist
[ok]: ZUNIONSTORE with empty set - ziplist
[ok]: BRPOPLPUSH - ziplist
[ok]: ZUNIONSTORE basics - ziplist
[ok]: BLPOP, LPUSH + DEL should not awake blocked client
[ok]: ZUNIONSTORE with weights - ziplist
[1/42 done]: unit/printver (0 seconds)
Testing unit/other
[ok]: ZUNIONSTORE with a regular set and weights - ziplist
[ok]: ZUNIONSTORE with AGGREGATE MIN - ziplist
[ok]: ZUNIONSTORE with AGGREGATE MAX - ziplist
[ok]: ZINTERSTORE basics - ziplist
[ok]: ZINTERSTORE with weights - ziplist
[ok]: BLPOP, LPUSH + DEL + SET should not awake blocked client
[ok]: ZINTERSTORE with a regular set and weights - ziplist
[ok]: ZINTERSTORE with AGGREGATE MIN - ziplist
[ok]: ZINTERSTORE with AGGREGATE MAX - ziplist
[ok]: BLPOP with same key multiple times should work (issue #801)
[ok]: MULTI/EXEC is isolated from the point of view of BLPOP
[ok]: BLPOP with variadic LPUSH
[ok]: ZUNIONSTORE with +inf/-inf scores - ziplist
[ok]: ZUNIONSTORE with NaN weights ziplist
[ok]: ZINTERSTORE with +inf/-inf scores - ziplist
[ok]: ZINTERSTORE with NaN weights ziplist
[ok]: Check encoding - skiplist
[ok]: ZSET basic ZADD and score update - skiplist
[ok]: ZSET element can't be set to NaN with ZADD - skiplist
[ok]: ZSET element can't be set to NaN with ZINCRBY
[ok]: ZADD with options syntax error with incomplete pair
[ok]: ZADD XX option without key - skiplist
[ok]: ZADD XX existing key - skiplist
[ok]: ZADD XX returns the number of elements actually added
[ok]: ZADD XX updates existing elements score
[ok]: HSET/HLEN - Big hash creation
[ok]: ZADD XX and NX are not compatible
[ok]: ZADD NX with non exisitng key
[ok]: Is the big hash encoded with an hash table?
[ok]: HGET against the small hash
[ok]: ZADD NX only add new elements without updating old ones
[ok]: ZADD INCR works like ZINCRBY
[ok]: ZADD INCR works with a single score-elemenet pair
[ok]: ZADD CH option changes return value to all changed elements
[ok]: ZINCRBY calls leading to NaN result in error
[ok]: ZADD - Variadic version base case
[ok]: ZADD - Return value is the number of actually added items
[ok]: ZADD - Variadic version does not add nothing on single parsing err
[ok]: ZADD - Variadic version will raise error on missing arg
[ok]: ZINCRBY does not work variadic even if shares ZADD implementation
[ok]: ZCARD basics - skiplist
[ok]: ZREM removes key after last element is removed
[ok]: ZREM variadic version
[ok]: ZREM variadic version -- remove elements after key deletion
[ok]: ZRANGE basics - skiplist
[ok]: ZREVRANGE basics - skiplist
[ok]: ZRANK/ZREVRANK basics - skiplist
[ok]: ZRANK - after deletion - skiplist
[ok]: ZINCRBY - can create a new sorted set - skiplist
[ok]: ZINCRBY - increment and decrement - skiplist
[ok]: ZINCRBY return value
[ok]: ZRANGEBYSCORE/ZREVRANGEBYSCORE/ZCOUNT basics
[ok]: SCAN COUNT
[ok]: ZRANGEBYSCORE with WITHSCORES
[ok]: ZRANGEBYSCORE with LIMIT
[ok]: ZRANGEBYSCORE with LIMIT and WITHSCORES
[ok]: ZRANGEBYSCORE with non-value min or max
[ok]: ZRANGEBYLEX/ZREVRANGEBYLEX/ZCOUNT basics
[ok]: ZRANGEBYSLEX with LIMIT
[ok]: ZRANGEBYLEX with invalid lex range specifiers
[ok]: SCAN MATCH
[ok]: HGET against the big hash
[ok]: HGET against non existing key
[ok]: HSET in update and insert mode
[ok]: HSETNX target key missing - small hash
[ok]: HSETNX target key exists - small hash
[ok]: HSETNX target key missing - big hash
[ok]: HSETNX target key exists - big hash
[ok]: HMSET wrong number of args
[ok]: HMSET - small hash
[ok]: Very big payload in GET/SET
[ok]: SSCAN with encoding intset
[ok]: SSCAN with encoding hashtable
[ok]: ZREMRANGEBYSCORE basics
[ok]: HSCAN with encoding ziplist
[ok]: ZREMRANGEBYSCORE with non-value min or max
[ok]: ZREMRANGEBYRANK basics
[ok]: ZUNIONSTORE against non-existing key doesn't set destination - skiplist
[ok]: HMSET - big hash
[ok]: HMGET against non existing key and fields
[ok]: HMGET against wrong type
[ok]: HMGET - small hash
[ok]: ZUNIONSTORE with empty set - skiplist
[ok]: ZUNIONSTORE basics - skiplist
[ok]: ZUNIONSTORE with weights - skiplist
[ok]: ZUNIONSTORE with a regular set and weights - skiplist
[ok]: ZUNIONSTORE with AGGREGATE MIN - skiplist
[ok]: ZUNIONSTORE with AGGREGATE MAX - skiplist
[ok]: ZINTERSTORE basics - skiplist
[2/42 done]: unit/type/incr (1 seconds)
Testing unit/multi
[ok]: ZINTERSTORE with weights - skiplist
[ok]: ZINTERSTORE with a regular set and weights - skiplist
[ok]: ZINTERSTORE with AGGREGATE MIN - skiplist
[ok]: ZINTERSTORE with AGGREGATE MAX - skiplist
[ok]: ZUNIONSTORE with +inf/-inf scores - skiplist
[ok]: ZUNIONSTORE with NaN weights skiplist
[ok]: Set encoding after DEBUG RELOAD
[ok]: ZINTERSTORE with +inf/-inf scores - skiplist
[ok]: ZINTERSTORE with NaN weights skiplist
[ok]: ZINTERSTORE regression with two sets, intset+hashtable
[ok]: ZUNIONSTORE regression, should not create NaN in scores
[ok]: ZINTERSTORE #516 regression, mixed sets and ziplist zsets
[ok]: SREM basics - regular set
[ok]: SREM basics - intset
[ok]: SREM with multiple arguments
[ok]: SREM variadic version with more args needed to destroy the key
[ok]: HMGET - big hash
[ok]: HKEYS - small hash
[ok]: HKEYS - big hash
[ok]: HVALS - small hash
[ok]: AUTH fails when a wrong password is given
[ok]: Arbitrary command gives an error when AUTH is required
[ok]: AUTH succeeds when the right password is given
[ok]: Once AUTH succeeded we can actually send commands to the server
[ok]: HSCAN with encoding hashtable
[ok]: ZSCAN with encoding ziplist
[ok]: SAVE - make sure there are all the types as values
[ok]: Generated sets must be encoded as hashtable
[ok]: SINTER with two sets - hashtable
[ok]: HVALS - big hash
[ok]: SINTERSTORE with two sets - hashtable
[ok]: HGETALL - small hash
[ok]: MIGRATE is caching connections
[ok]: SINTERSTORE with two sets, after a DEBUG RELOAD - hashtable
[ok]: SUNION with two sets - hashtable
[ok]: ZUNIONSTORE result is sorted
[ok]: SUNIONSTORE with two sets - hashtable
[ok]: SINTER against three sets - hashtable
[ok]: SINTERSTORE with three sets - hashtable
[ok]: ZSCAN with encoding skiplist
[ok]: MUTLI / EXEC basics
[ok]: DISCARD
[ok]: Nested MULTI are not allowed
[ok]: SUNION with non existing keys - hashtable
[ok]: MULTI where commands alter argc/argv
[ok]: SDIFF with two sets - hashtable
[ok]: WATCH inside MULTI is not allowed
[ok]: SDIFF with three sets - hashtable
[ok]: SDIFFSTORE with three sets - hashtable
[ok]: EXEC fails if there are errors while queueing commands #1
[ok]: EXEC fails if there are errors while queueing commands #2
[ok]: If EXEC aborts, the client MULTI state is cleared
[ok]: EXEC works on WATCHed key not modified
[ok]: EXEC fail on WATCHed key modified (1 key of 1 watched)
[ok]: EXEC fail on WATCHed key modified (1 key of 5 watched)
[ok]: EXEC fail on WATCHed key modified by SORT with STORE even if the result is empty
[ok]: After successful EXEC key is no longer watched
[ok]: After failed EXEC key is no longer watched
[ok]: It is possible to UNWATCH
[ok]: UNWATCH when there is nothing watched works as expected
[ok]: HGETALL - big hash
[ok]: HDEL and return value
[ok]: HDEL - more than a single value
[ok]: HDEL - hash becomes empty before deleting all specified fields
[ok]: HEXISTS
[ok]: Is a ziplist encoded Hash promoted on big payload?
[ok]: HINCRBY against non existing database key
[ok]: HINCRBY against non existing hash key
[ok]: HINCRBY against hash key created by hincrby itself
[ok]: HINCRBY against hash key originally set with HSET
[ok]: HINCRBY over 32bit value
[ok]: HINCRBY over 32bit value with over 32bit increment
[ok]: HINCRBY fails against hash value with spaces (left)
[ok]: HINCRBY fails against hash value with spaces (right)
[ok]: HINCRBY can detect overflows
[ok]: HINCRBYFLOAT against non existing database key
[ok]: FLUSHALL is able to touch the watched keys
[ok]: HINCRBYFLOAT against non existing hash key
[ok]: SCAN guarantees check under write load
[ok]: SSCAN with integer encoded object (issue #1345)
[ok]: SSCAN with PATTERN
[ok]: HSCAN with PATTERN
[ok]: ZSCAN with PATTERN
[ok]: HINCRBYFLOAT against hash key created by hincrby itself
[ok]: HINCRBYFLOAT against hash key originally set with HSET
[ok]: HINCRBYFLOAT over 32bit value
[ok]: HINCRBYFLOAT over 32bit value with over 32bit increment
[ok]: HINCRBYFLOAT fails against hash value with spaces (left)
[ok]: HINCRBYFLOAT fails against hash value with spaces (right)
[ok]: HSTRLEN against the small hash
[ok]: ZSCORE - ziplist
[ok]: FLUSHALL does not touch non affected keys
[ok]: FLUSHDB is able to touch the watched keys
[ok]: FLUSHDB does not touch non affected keys
[ok]: WATCH is able to remember the DB a key belongs to
[ok]: WATCH will consider touched keys target of EXPIRE
[ok]: Old Linked list: SORT BY key
[ok]: Old Linked list: SORT BY key with limit
[ok]: Generated sets must be encoded as intset
[ok]: SINTER with two sets - intset
[ok]: SINTERSTORE with two sets - intset
[ok]: Old Linked list: SORT BY hash field
[ok]: ZSCORE after a DEBUG RELOAD - ziplist
[3/42 done]: unit/auth (1 seconds)
Testing unit/quit
[ok]: ZSCAN scores: regression test for issue #2175
[ok]: SINTERSTORE with two sets, after a DEBUG RELOAD - intset
[ok]: SUNION with two sets - intset
[ok]: SUNIONSTORE with two sets - intset
[ok]: Protocol desync regression test #1
[ok]: HSTRLEN against the big hash
[ok]: SINTER against three sets - intset
[ok]: HSTRLEN against non existing field
[ok]: SINTERSTORE with three sets - intset
[ok]: HSTRLEN corner cases
[ok]: Hash ziplist regression test for large keys
[ok]: SUNION with non existing keys - intset
[ok]: SDIFF with two sets - intset
[ok]: SDIFF with three sets - intset
[ok]: SDIFFSTORE with three sets - intset
[ok]: SDIFF with first set empty
[ok]: SDIFF with same set two times
[ok]: DEL against expired key
[ok]: EXISTS
[ok]: Zero length value in key. SET/GET/EXISTS
[ok]: Commands pipelining
[ok]: Non existing command
[ok]: RENAME basic usage
[ok]: RENAME source key should no longer exist
[ok]: RENAME against already existing key
[ok]: RENAMENX basic usage
[ok]: RENAMENX against already existing key
[ok]: RENAMENX against already existing key (2)
[ok]: RENAME against non existing source key
[ok]: RENAME where source and dest key are the same (existing)
[ok]: RENAMENX where source and dest key are the same (existing)
[ok]: RENAME where source and dest key are the same (non existing)
[ok]: RENAME with volatile key, should move the TTL as well
[ok]: RENAME with volatile key, should not inherit TTL of target key
[ok]: DEL all keys again (DB 0)
[ok]: DEL all keys again (DB 1)
[ok]: MOVE basic usage
[ok]: MOVE against key existing in the target DB
[ok]: MOVE against non-integer DB (#1428)
[ok]: MOVE can move key expire metadata as well
[ok]: MOVE does not create an expire if it does not exist
[ok]: SET/GET keys in different DBs
[ok]: ZSET sorting stresser - ziplist
[ok]: BRPOPLPUSH with zero timeout should block indefinitely
[ok]: QUIT returns OK
[ok]: Pipelined commands after QUIT must not be executed
[ok]: Pipelined commands after QUIT that exceed read buffer size
[ok]: RANDOMKEY
[ok]: RANDOMKEY against empty DB
[ok]: RANDOMKEY regression 1
[ok]: KEYS * two times with long key, Github issue #1208
[ok]: Hash fuzzing #1 - 10 fields
[4/42 done]: unit/scan (2 seconds)
Testing unit/aofrw
[ok]: Hash fuzzing #2 - 10 fields
[5/42 done]: unit/quit (1 seconds)
Testing integration/replication
[6/42 done]: unit/keyspace (2 seconds)
Testing integration/replication-2
[ok]: WATCH will not consider touched expired keys
[ok]: DISCARD should clear the WATCH dirty flag on the client
[ok]: DISCARD should UNWATCH all the keys
[ok]: Protocol desync regression test #2
[ok]: MULTI / EXEC is propagated correctly (single write command)
[ok]: EXPIRE - After 2.1 seconds the key should no longer be here
[ok]: EXPIRE - write on expire should work
[ok]: EXPIREAT - Check for EXPIRE alike behavior
[ok]: SETEX - Set + Expire combo operation. Check for TTL
[ok]: SETEX - Check value
[ok]: SETEX - Overwrite old key
[ok]: MULTI / EXEC is propagated correctly (empty transaction)
[ok]: MULTI / EXEC is propagated correctly (read-only commands)
[ok]: BRPOPLPUSH with a client BLPOPing the target list
[ok]: BRPOPLPUSH with wrong source type
[ok]: MULTI / EXEC is propagated correctly (write command, no effect)
[7/42 done]: unit/multi (2 seconds)
Testing integration/replication-3
[ok]: Protocol desync regression test #3
[ok]: FUZZ stresser with data model binary
[ok]: Slave enters handshake
[ok]: SETEX - Wait for the key to expire
[ok]: SETEX - Wrong time parameter
[ok]: PERSIST can undo an EXPIRE
[ok]: PERSIST returns 0 against non existing or non volatile keys
[ok]: First server should have role slave after SLAVEOF
[ok]: If min-slaves-to-write is honored, write is accepted
[ok]: No write if min-slaves-to-write is < attached slaves
[ok]: If min-slaves-to-write is honored, write is accepted (again)
[ok]: BRPOPLPUSH with wrong destination type
[ok]: BRPOPLPUSH maintains order of elements after failure
[ok]: BRPOPLPUSH with multiple blocked clients
[ok]: Linked BRPOPLPUSH
[ok]: Circular BRPOPLPUSH
[ok]: Self-referential BRPOPLPUSH
[ok]: BRPOPLPUSH inside a transaction
[ok]: PUSH resulting from BRPOPLPUSH affect WATCH
[ok]: BRPOPLPUSH does not affect WATCH while still blocked
[ok]: Regression for a crash with blocking ops and pipelining
[8/42 done]: unit/protocol (4 seconds)
Testing integration/replication-4
[ok]: First server should have role slave after SLAVEOF
[ok]: EXPIRE pricision is now the millisecond
[ok]: Very big payload random access
[ok]: BRPOPLPUSH timeout
[ok]: BLPOP when new key is moved into place
[ok]: BLPOP when result key is created by SORT..STORE
[ok]: BLPOP: with single empty list argument
[ok]: BLPOP: with negative timeout
[ok]: BLPOP: with non-integer timeout
[ok]: First server should have role slave after SLAVEOF
[ok]: FUZZ stresser with data model alpha
[ok]: BLPOP: with zero timeout should block indefinitely
[ok]: BLPOP: second argument is not a list
[ok]: PEXPIRE/PSETEX/PEXPIREAT can set sub-second expires
[ok]: TTL returns tiem to live in seconds
[ok]: PTTL returns time to live in milliseconds
[ok]: TTL / PTTL return -1 if key has no expire
[ok]: TTL / PTTL return -2 if key does not exit
[ok]: Hash fuzzing #1 - 512 fields
[ok]: BLPOP: timeout
[ok]: BLPOP: arguments are empty
[ok]: BRPOP: with single empty list argument
[ok]: BRPOP: with negative timeout
[ok]: BRPOP: with non-integer timeout
[ok]: Redis should actively expire keys incrementally
[ok]: FUZZ stresser with data model compr
[ok]: BRPOP: with zero timeout should block indefinitely
[ok]: BRPOP: second argument is not a list
[ok]: Redis should lazy expire keys
[ok]: No write if min-slaves-max-lag is > of the slave lag
[ok]: min-slaves-to-write is ignored by slaves
[ok]: BGSAVE
[ok]: SELECT an out of range DB
[ok]: EXPIRE should not resurrect keys (issue #1026)
[ok]: 5 keys in, 5 keys out
[ok]: EXPIRE with empty string as TTL should report an error
[9/42 done]: unit/expire (11 seconds)
Testing integration/replication-psync
[ok]: EXPIRES after a reload (snapshot + append only file rewrite)
[ok]: BRPOP: timeout
[ok]: BRPOP: arguments are empty
[ok]: BLPOP inside a transaction
[ok]: LPUSHX, RPUSHX - generic
[ok]: LPUSHX, RPUSHX - linkedlist
[ok]: LINSERT - linkedlist
[ok]: LPUSHX, RPUSHX - ziplist
[ok]: LINSERT - ziplist
[ok]: LINSERT raise error on bad syntax
[ok]: SET 10000 numeric keys and access all them in reverse order
[ok]: DBSIZE should be 10000 now
[ok]: SETNX target key missing
[ok]: SETNX target key exists
[ok]: SETNX against not-expired volatile key
[ok]: LINDEX consistency test - quicklist
[ok]: LINDEX random access - quicklist
[ok]: ZRANGEBYSCORE fuzzy test, 100 ranges in 128 element sorted set - ziplist
[ok]: Hash fuzzing #2 - 512 fields
[ok]: Test replication with parallel clients writing in differnet DBs
[ok]: Check if list is still ok after a DEBUG RELOAD - quicklist
[ok]: Slave should be able to synchronize with the master
[ok]: Detect write load to master
[ok]: Test replication partial resync: no reconnection, just sync (diskless: no, reconnect: 0)
[ok]: ZRANGEBYLEX fuzzy test, 100 ranges in 128 element sorted set - ziplist
[ok]: LINDEX consistency test - quicklist
[ok]: Old Big Linked list: SORT BY key
[ok]: Old Big Linked list: SORT BY key with limit
[ok]: LINDEX random access - quicklist
[ok]: Slave is able to detect timeout during handshake
[ok]: ZREMRANGEBYLEX fuzzy test, 100 ranges in 128 element sorted set - ziplist
[ok]: ZSETs skiplist implementation backlink consistency test - ziplist
[ok]: Check if list is still ok after a DEBUG RELOAD - quicklist
[ok]: LLEN against non-list value error
[ok]: LLEN against non existing key
[ok]: LINDEX against non-list value error
[ok]: LINDEX against non existing key
[ok]: LPUSH against non-list value error
[ok]: RPUSH against non-list value error
[ok]: RPOPLPUSH base case - linkedlist
[ok]: RPOPLPUSH with the same list as src and dst - linkedlist
[ok]: RPOPLPUSH with linkedlist source and existing target linkedlist
[ok]: RPOPLPUSH with linkedlist source and existing target ziplist
[ok]: RPOPLPUSH base case - ziplist
[ok]: RPOPLPUSH with the same list as src and dst - ziplist
[ok]: RPOPLPUSH with ziplist source and existing target linkedlist
[ok]: RPOPLPUSH with ziplist source and existing target ziplist
[ok]: RPOPLPUSH against non existing key
[ok]: RPOPLPUSH against non list src key
[ok]: RPOPLPUSH against non list dst key
[ok]: RPOPLPUSH against non existing src key
[ok]: Basic LPOP/RPOP - linkedlist
[ok]: Basic LPOP/RPOP - ziplist
[ok]: LPOP/RPOP against non list value
[ok]: Mass RPOP/LPOP - quicklist
[ok]: EXPIRES after AOF reload (without rewrite)
[ok]: First server should have role slave after SLAVEOF
[ok]: With min-slaves-to-write (1,3): master should be writable
[ok]: With min-slaves-to-write (2,3): master should not be writable
[ok]: Mass RPOP/LPOP - quicklist
[ok]: LRANGE basics - linkedlist
[ok]: LRANGE inverted indexes - linkedlist
[ok]: LRANGE out of range indexes including the full list - linkedlist
[ok]: LRANGE out of range negative end index - linkedlist
[ok]: LRANGE basics - ziplist
[ok]: LRANGE inverted indexes - ziplist
[ok]: LRANGE out of range indexes including the full list - ziplist
[ok]: LRANGE out of range negative end index - ziplist
[ok]: LRANGE against non existing key
[ok]: LTRIM basics - linkedlist
[ok]: LTRIM out of range negative end index - linkedlist
[ok]: LTRIM basics - ziplist
[ok]: LTRIM out of range negative end index - ziplist
[ok]: LSET - linkedlist
[ok]: LSET out of range index - linkedlist
[ok]: LSET - ziplist
[ok]: LSET out of range index - ziplist
[ok]: LSET against non existing key
[ok]: LSET against non list value
[ok]: LREM remove all the occurrences - linkedlist
[ok]: LREM remove the first occurrence - linkedlist
[ok]: LREM remove non existing element - linkedlist
[ok]: LREM starting from tail with negative count - linkedlist
[ok]: LREM starting from tail with negative count (2) - linkedlist
[ok]: LREM deleting objects that may be int encoded - linkedlist
[ok]: LREM remove all the occurrences - ziplist
[ok]: LREM remove the first occurrence - ziplist
[ok]: LREM remove non existing element - ziplist
[ok]: LREM starting from tail with negative count - ziplist
[ok]: LREM starting from tail with negative count (2) - ziplist
[ok]: LREM deleting objects that may be int encoded - ziplist
[ok]: Slave should be able to synchronize with the master
[ok]: Detect write load to master
[ok]: Regression for bug 593 - chaining BRPOPLPUSH with other blocking cmds
[ok]: Set instance A as slave of B
[ok]: BRPOPLPUSH replication, when blocking against empty list
[ok]: MIGRATE cached connections are released after some time
[10/42 done]: unit/type/list (16 seconds)
Testing integration/aof
[ok]: Old Big Linked list: SORT BY hash field
[ok]: Intset: SORT BY key
[ok]: Intset: SORT BY key with limit
[ok]: Intset: SORT BY hash field
[ok]: Unfinished MULTI: Server should start if load-truncated is yes
[ok]: SETNX against expired volatile key
[ok]: MGET
[ok]: MGET against non existing key
[ok]: MGET against non-string key
[ok]: GETSET (set new value)
[ok]: GETSET (replace old value)
[ok]: MSET base case
[ok]: MSET wrong number of args
[ok]: MSETNX with already existent key
[ok]: MSETNX with not existing keys
[ok]: STRLEN against non-existing key
[ok]: STRLEN against integer-encoded value
[ok]: STRLEN against plain string
[ok]: SETBIT against non-existing key
[ok]: SETBIT against string-encoded key
[ok]: SETBIT against integer-encoded key
[ok]: SETBIT against key with wrong type
[ok]: SETBIT with out of range bit offset
[ok]: SETBIT with non-bit argument
[ok]: ZSETs ZRANK augmented skip list stress testing - ziplist
[ok]: BRPOPLPUSH replication, list exists
[ok]: ZSCORE - skiplist
[ok]: MIGRATE is able to migrate a key between two instances
[ok]: ZSCORE after a DEBUG RELOAD - skiplist
[ok]: ZSET sorting stresser - skiplist
[ok]: Short read: Server should start if load-truncated is yes
[ok]: Truncated AOF loaded: we expect foo to be equal to 5
[ok]: Append a new command after loading an incomplete AOF
[ok]: BLPOP followed by role change, issue #2473
[ok]: MIGRATE is able to copy a key between two instances
[ok]: Hash table: SORT BY key
[ok]: Hash table: SORT BY key with limit
[ok]: Hash table: SORT BY hash field
[ok]: Short read + command: Server should start
[ok]: Truncated AOF loaded: we expect foo to be equal to 6 now
[ok]: Stress test the hash ziplist -> hashtable encoding conversion
[ok]: MIGRATE will not overwrite existing keys, unless REPLACE is used
[ok]: With min-slaves-to-write: master not writable with lagged slave
[11/42 done]: unit/type/hash (18 seconds)
Testing integration/rdb
[ok]: Bad format: Server should have logged an error
[ok]: Second server should have role master at first
[ok]: SLAVEOF should start with link status "down"
[ok]: The role should immediately be changed to "slave"
[ok]: RDB encoding loading test
[ok]: Unfinished MULTI: Server should have logged an error
[ok]: SETBIT fuzzing
[ok]: GETBIT against non-existing key
[ok]: GETBIT against string-encoded key
[ok]: GETBIT against integer-encoded key
[ok]: SETRANGE against non-existing key
[ok]: SETRANGE against string-encoded key
[ok]: SETRANGE against integer-encoded key
[ok]: SETRANGE against key with wrong type
[ok]: SETRANGE with out of range offset
[ok]: GETRANGE against non-existing key
[ok]: MIGRATE propagates TTL correctly
[ok]: GETRANGE against string value
[ok]: GETRANGE against integer-encoded value
[ok]: Short read: Server should have logged an error
[ok]: Sync should have transferred keys from master
[ok]: The link status should be up
[ok]: SET on the master should immediately propagate
[ok]: FLUSHALL should replicate
[ok]: ROLE in master reports master with a slave
[ok]: ROLE in slave reports slave in connected state
[ok]: Short read: Utility should confirm the AOF is not valid
[ok]: Server started empty with non-existing RDB file
[ok]: Short read: Utility should be able to fix the AOF
[ok]: SDIFF fuzzing
[ok]: SINTER against non-set should throw error
[ok]: SUNION against non-set should throw error
[ok]: SINTER should handle non existing key as empty
[ok]: SINTER with same integer elements but different encoding
[ok]: SINTERSTORE against non existing keys should delete dstkey
[ok]: SUNIONSTORE against non existing keys should delete dstkey
[ok]: SPOP basics - hashtable
[ok]: SPOP with <count>=1 - hashtable
[ok]: SRANDMEMBER - hashtable
[ok]: SPOP basics - intset
[ok]: SPOP with <count>=1 - intset
[ok]: SRANDMEMBER - intset
[ok]: SPOP with <count>
[ok]: SPOP with <count>
[ok]: SPOP using integers, testing Knuth's and Floyd's algorithm
[ok]: SPOP using integers with Knuth's algorithm
[ok]: SPOP new implementation: code path #1
[ok]: SPOP new implementation: code path #2
[ok]: SPOP new implementation: code path #3
[ok]: SRANDMEMBER with <count> against non existing key
[ok]: SRANDMEMBER with <count> - hashtable
[ok]: SRANDMEMBER with <count> - intset
[ok]: SMOVE basics - from regular set to intset
[ok]: SMOVE basics - from intset to regular set
[ok]: SMOVE non existing key
[ok]: SMOVE non existing src set
[ok]: SMOVE from regular set to non existing destination set
[ok]: SMOVE from intset to non existing destination set
[ok]: SMOVE wrong src key type
[ok]: SMOVE wrong dst key type
[ok]: SMOVE with identical source and destination
[ok]: First server should have role slave after SLAVEOF
[ok]: Fixed AOF: Server should have been started
[ok]: Fixed AOF: Keyspace should contain values that were parseable
[ok]: PIPELINING stresser (also a regression for the old epoll bug)
[ok]: APPEND basics
[ok]: APPEND basics, integer encoded values
[ok]: Server started empty with empty RDB file
[ok]: AOF+SPOP: Server should have been started
[ok]: AOF+SPOP: Set should have 1 member
[ok]: Server should not start if RDB file can't be open
[ok]: AOF+SPOP: Server should have been started
[ok]: AOF+SPOP: Set should have 1 member
[ok]: Server should not start if RDB is corrupted
[12/42 done]: integration/rdb (4 seconds)
Testing integration/convert-zipmap-hash-on-load
[ok]: APPEND fuzzing
[ok]: RDB load zipmap hash: converts to ziplist
[ok]: FLUSHDB
[ok]: Test replication partial resync: ok psync (diskless: no, reconnect: 1)
[ok]: Perform a final SAVE to leave a clean DB on disk
[ok]: AOF+EXPIRE: Server should have been started
[ok]: AOF+EXPIRE: List should be empty
[13/42 done]: unit/other (23 seconds)
Testing integration/logging
[ok]: RDB load zipmap hash: converts to hash table when hash-max-ziplist-entries is exceeded
[ok]: Redis should not try to convert DEL into EXPIREAT for EXPIRE -1
[ok]: Server is able to generate a stack trace on selected systems
[14/42 done]: integration/aof (8 seconds)
Testing unit/pubsub
[ok]: RDB load zipmap hash: converts to hash table when hash-max-ziplist-value is exceeded
[15/42 done]: integration/logging (1 seconds)
Testing unit/slowlog
[ok]: Pub/Sub PING
[ok]: PUBLISH/SUBSCRIBE basics
[ok]: PUBLISH/SUBSCRIBE with two clients
[ok]: PUBLISH/SUBSCRIBE after UNSUBSCRIBE without arguments
[ok]: SUBSCRIBE to one channel more than once
[ok]: UNSUBSCRIBE from non-subscribed channels
[ok]: PUBLISH/PSUBSCRIBE basics
[ok]: PUBLISH/PSUBSCRIBE with two clients
[ok]: PUBLISH/PSUBSCRIBE after PUNSUBSCRIBE without arguments
[ok]: PUNSUBSCRIBE from non-subscribed channels
[ok]: NUMSUB returns numbers, not strings (#1561)
[ok]: Mix SUBSCRIBE and PSUBSCRIBE
[ok]: PUNSUBSCRIBE and UNSUBSCRIBE should always reply
[ok]: Keyspace notifications: we receive keyspace notifications
[ok]: Keyspace notifications: we receive keyevent notifications
[ok]: Keyspace notifications: we can receive both kind of events
[ok]: Keyspace notifications: we are able to mask events
[ok]: Keyspace notifications: general events test
[ok]: Keyspace notifications: list events test
[ok]: Keyspace notifications: set events test
[ok]: Keyspace notifications: zset events test
[ok]: Keyspace notifications: hash events test
[ok]: SLOWLOG - check that it starts with an empty log
[16/42 done]: integration/convert-zipmap-hash-on-load (2 seconds)
Testing unit/scripting
[ok]: Keyspace notifications: expired events (triggered expire)
[ok]: SLOWLOG - only logs commands taking more time than specified
[ok]: SLOWLOG - max entries is correctly handled
[ok]: SLOWLOG - GET optional argument to limit output len works
[ok]: SLOWLOG - RESET subcommand works
[ok]: Keyspace notifications: expired events (background expire)
[ok]: Keyspace notifications: evicted events
[ok]: Keyspace notifications: test CONFIG GET/SET of event flags
[ok]: SLOWLOG - logged entry sanity check
[ok]: SLOWLOG - commands with too many arguments are trimmed
[ok]: SLOWLOG - too long arguments are trimmed
[ok]: EVAL - Does Lua interpreter replies to our requests?
[ok]: EVAL - Lua integer -> Redis protocol type conversion
[ok]: EVAL - Lua string -> Redis protocol type conversion
[ok]: EVAL - Lua true boolean -> Redis protocol type conversion
[ok]: EVAL - Lua false boolean -> Redis protocol type conversion
[ok]: EVAL - Lua status code reply -> Redis protocol type conversion
[ok]: EVAL - Lua error reply -> Redis protocol type conversion
[ok]: EVAL - Lua table -> Redis protocol type conversion
[ok]: EVAL - Are the KEYS and ARGV arrays populated correctly?
[ok]: EVAL - is Lua able to call Redis API?
[ok]: EVALSHA - Can we call a SHA1 if already defined?
[ok]: EVALSHA - Can we call a SHA1 in uppercase?
[ok]: EVALSHA - Do we get an error on invalid SHA1?
[ok]: EVALSHA - Do we get an error on non defined SHA1?
[ok]: EVAL - Redis integer -> Lua type conversion
[ok]: EVAL - Redis bulk -> Lua type conversion
[ok]: EVAL - Redis multi bulk -> Lua type conversion
[ok]: EVAL - Redis status reply -> Lua type conversion
[ok]: EVAL - Redis error reply -> Lua type conversion
[ok]: EVAL - Redis nil bulk reply -> Lua type conversion
[ok]: EVAL - Is the Lua client using the currently selected DB?
[ok]: EVAL - SELECT inside Lua should not affect the caller
[ok]: EVAL - Scripts can't run certain commands
[ok]: EVAL - Scripts can't run certain commands
[ok]: EVAL - No arguments to redis.call/pcall is considered an error
[ok]: EVAL - redis.call variant raises a Lua error on Redis cmd error (1)
[ok]: EVAL - redis.call variant raises a Lua error on Redis cmd error (1)
[ok]: EVAL - redis.call variant raises a Lua error on Redis cmd error (1)
[ok]: EVAL - JSON numeric decoding
[ok]: EVAL - JSON string decoding
[ok]: EVAL - cmsgpack can pack double?
[ok]: EVAL - cmsgpack can pack negative int64?
[ok]: EVAL - cmsgpack can pack and unpack circular references?
[ok]: EVAL - Numerical sanity check from bitop
[ok]: EVAL - Verify minimal bitop functionality
[ok]: EVAL - Able to parse trailing comments
[ok]: SCRIPTING FLUSH - is able to clear the scripts cache?
[ok]: SCRIPT EXISTS - can detect already defined scripts?
[ok]: SCRIPT LOAD - is able to register scripts in the scripting cache
[ok]: In the context of Lua the output of random commands gets ordered
[ok]: SORT is normally not alpha re-ordered for the scripting engine
[ok]: SORT BY <constant> output gets ordered for scripting
[ok]: SORT BY <constant> with GET gets ordered for scripting
[ok]: redis.sha1hex() implementation
[ok]: Globals protection reading an undeclared global variable
[ok]: Globals protection setting an undeclared global*
[ok]: Test an example script DECR_IF_GT
[ok]: Scripting engine resets PRNG at every script execution
[ok]: Scripting engine PRNG can be seeded correctly
[ok]: SLOWLOG - EXEC is not logged, just executed commands
[17/42 done]: unit/pubsub (1 seconds)
Testing unit/maxmemory
[ok]: Slave should be able to synchronize with the master
[ok]: Without maxmemory small integers are shared
[ok]: With maxmemory and non-LRU policy integers are still shared
[ok]: With maxmemory and LRU policy integers are not shared
[18/42 done]: unit/slowlog (1 seconds)
Testing unit/introspection
[ok]: Detect write load to master
[ok]: MASTER and SLAVE consistency with expire
[ok]: CLIENT LIST
[ok]: MONITOR can log executed commands
[ok]: MONITOR can log commands issued by the scripting engine
[ok]: CLIENT GETNAME should return NIL if name is not assigned
[ok]: CLIENT LIST shows empty fields for unassigned names
[ok]: CLIENT SETNAME does not accept spaces
[ok]: CLIENT SETNAME can assign a name to this connection
[ok]: CLIENT SETNAME can change the name of an existing connection
[ok]: After CLIENT SETNAME, connection can still be closed
[19/42 done]: unit/introspection (1 seconds)
Testing unit/introspection-2
[ok]: GETRANGE fuzzing
[ok]: Extended SET can detect syntax errors
[ok]: Extended SET NX option
[ok]: Extended SET XX option
[ok]: Extended SET EX option
[ok]: Extended SET PX option
[ok]: Extended SET using multiple options at once
[ok]: GETRANGE with huge ranges, Github issue #1844
[20/42 done]: unit/type/string (27 seconds)
Testing unit/limits
[ok]: maxmemory - is the memory limit honoured? (policy allkeys-random)
[ok]: ZRANGEBYSCORE fuzzy test, 100 ranges in 100 element sorted set - skiplist
[ok]: First server should have role slave after SLAVEOF
[ok]: EVAL does not leak in the Lua stack
[ok]: Check if maxclients works refusing connections
[ok]: EVAL processes writes from AOF in read-only slaves
[ok]: We can call scripts rewriting client->argv from Lua
[ok]: Call Redis command with many args from Lua (issue #1764)
[ok]: Number conversion precision test (issue #1118)
[ok]: String containing number precision test (regression of issue #1118)
[ok]: Verify negative arg count is error instead of crash (issue #1842)
[ok]: Correct handling of reused argv (issue #1939)
[ok]: Functions in the Redis namespace are able to report errors
[ok]: AOF rewrite during write load
[ok]: ZRANGEBYLEX fuzzy test, 100 ranges in 100 element sorted set - skiplist
[ok]: intsets implementation stress testing
[ok]: maxmemory - is the memory limit honoured? (policy allkeys-lru)
[21/42 done]: unit/limits (2 seconds)
Testing unit/obuf-limits
[ok]: TTL and TYPYE do not alter the last access time of a key
[22/42 done]: unit/type/set (30 seconds)
Testing unit/bitops
[ok]: BITCOUNT returns 0 against non existing key
[ok]: BITCOUNT returns 0 with out of range indexes
[ok]: BITCOUNT returns 0 with negative indexes where start > end
[ok]: BITCOUNT against test vector #1
[ok]: BITCOUNT against test vector #2
[ok]: BITCOUNT against test vector #3
[ok]: BITCOUNT against test vector #4
[ok]: BITCOUNT against test vector #5
[ok]: Timedout read-only scripts can be killed by SCRIPT KILL
[ok]: Timedout script link is still usable after Lua returns
[ok]: maxmemory - is the memory limit honoured? (policy volatile-lru)
[ok]: Timedout scripts that modified data can't be killed by SCRIPT KILL
[ok]: SHUTDOWN NOSAVE can kill a timedout script anyway
[ok]: ZREMRANGEBYLEX fuzzy test, 100 ranges in 100 element sorted set - skiplist
[ok]: ZSETs skiplist implementation backlink consistency test - skiplist
[ok]: Before the slave connects we issue two EVAL commands (scripts replication)
[ok]: Turning off AOF kills the background writing child if any
[ok]: maxmemory - is the memory limit honoured? (policy volatile-random)
[ok]: BITCOUNT fuzzing without start/end
[ok]: Connect a slave to the master instance (scripts replication)
[ok]: Now use EVALSHA against the master, with both SHAs (scripts replication)
[ok]: If EVALSHA was replicated as EVAL, 'x' should be '4' (scripts replication)
[ok]: Replication of script multiple pushes to list with BLPOP (scripts replication)
[ok]: EVALSHA replication when first call is readonly (scripts replication)
[ok]: Lua scripts using SELECT are replicated correctly (scripts replication)
[ok]: TOUCH alters the last access time of a key
[ok]: TOUCH returns the number of existing keys specified
[23/42 done]: unit/introspection-2 (7 seconds)
Testing unit/bitfield
[ok]: BITFIELD signed SET and GET basics
[ok]: BITFIELD unsigned SET and GET basics
[ok]: BITFIELD #<idx> form
[ok]: BITFIELD basic INCRBY form
[ok]: BITFIELD chaining of multiple commands
[ok]: BITFIELD unsigned overflow wrap
[ok]: BITFIELD unsigned overflow sat
[ok]: BITFIELD signed overflow wrap
[ok]: BITFIELD signed overflow sat
[ok]: Big Hash table: SORT BY key
[ok]: Big Hash table: SORT BY key with limit
[ok]: AOF rewrite of list with quicklist encoding, string data
[ok]: Test replication partial resync: no backlog (diskless: no, reconnect: 1)
[ok]: BITCOUNT fuzzing with start/end
[ok]: BITCOUNT with start, end
[ok]: BITCOUNT syntax error #1
[ok]: BITCOUNT regression test for github issue #582
[ok]: BITCOUNT misaligned prefix
[ok]: BITCOUNT misaligned prefix + full words + remainder
[ok]: BITOP NOT (empty string)
[ok]: BITOP NOT (known string)
[ok]: BITOP where dest and target are the same key
[ok]: BITOP AND|OR|XOR don't change the string with single input key
[ok]: BITOP missing key is considered a stream of zero
[ok]: BITOP shorter keys are zero-padded to the key with max length
[ok]: maxmemory - is the memory limit honoured? (policy volatile-ttl)
[ok]: Before the slave connects we issue two EVAL commands (commmands replication)
[ok]: BITFIELD overflow detection fuzzing
[ok]: LTRIM stress testing - linkedlist
[ok]: Connect a slave to the master instance (commmands replication)
[ok]: Now use EVALSHA against the master, with both SHAs (commmands replication)
[ok]: If EVALSHA was replicated as EVAL, 'x' should be '4' (commmands replication)
[ok]: Replication of script multiple pushes to list with BLPOP (commmands replication)
[ok]: EVALSHA replication when first call is readonly (commmands replication)
[ok]: Lua scripts using SELECT are replicated correctly (commmands replication)
[ok]: AOF rewrite of list with quicklist encoding, int data
[ok]: AOF rewrite of set with intset encoding, string data
[ok]: BITFIELD overflow wrap fuzzing
[ok]: BITFIELD regression for #3221
[ok]: Big Hash table: SORT BY hash field
[ok]: SORT GET #
[ok]: SORT GET <const>
[ok]: SORT GET (key and hash) with sanity check
[ok]: SORT BY key STORE
[ok]: SORT BY hash field STORE
[ok]: SORT extracts STORE correctly
[ok]: SORT extracts multiple STORE correctly
[ok]: SORT DESC
[ok]: SORT ALPHA against integer encoded strings
[ok]: SORT sorted set
[ok]: SORT sorted set BY nosort should retain ordering
[ok]: SORT sorted set BY nosort + LIMIT
[ok]: SORT sorted set BY nosort works as expected from scripts
[ok]: SORT sorted set: +inf and -inf handling
[ok]: ZSETs ZRANK augmented skip list stress testing - skiplist
[ok]: SORT regression for issue #19, sorting floats
[ok]: SORT with STORE returns zero if result is empty (github issue 224)
[ok]: SORT with STORE does not create empty lists (github issue 224)
[ok]: SORT with STORE removes key if result is empty (github issue 227)
[ok]: SORT with BY <constant> and STORE should still order output
[ok]: SORT will complain with numerical sorting and bad doubles (1)
[ok]: SORT will complain with numerical sorting and bad doubles (2)
[ok]: SORT BY sub-sorts lexicographically if score is the same
[ok]: SORT GET with pattern ending with just -> does not get hash field
[ok]: SORT by nosort retains native order for lists
[ok]: SORT by nosort plus store retains native order for lists
[ok]: SORT by nosort with limit returns based on original list order
[ok]: Slave should be able to synchronize with the master
[ok]: Detect write load to master
[24/42 done]: unit/bitfield (4 seconds)
Testing unit/geo
[ok]: SORT speed, 100 element list BY key, 100 times
[ok]: maxmemory - only allkeys-* should remove non-volatile keys (allkeys-random)
[ok]: SORT speed, 100 element list BY hash field, 100 times
[25/42 done]: unit/type/zset (37 seconds)
Testing unit/memefficiency
[ok]: SORT speed, 100 element list directly, 100 times
[ok]: GEOADD create
[ok]: GEOADD update
[ok]: GEOADD invalid coordinates
[ok]: GEOADD multi add
[ok]: Check geoset values
[ok]: GEORADIUS simple (sorted)
[ok]: GEORADIUS withdist (sorted)
[ok]: GEORADIUS with COUNT
[ok]: GEORADIUS with COUNT but missing integer argument
[ok]: GEORADIUS with COUNT DESC
[ok]: GEORADIUS HUGE, issue #2767
[ok]: GEORADIUSBYMEMBER simple (sorted)
[ok]: GEORADIUSBYMEMBER withdist (sorted)
[ok]: GEOHASH is able to return geohash strings
[ok]: GEOPOS simple
[ok]: GEOPOS missing element
[ok]: GEODIST simple & unit
[ok]: GEODIST missing elements
[ok]: GEORADIUS STORE option: syntax error
[ok]: GEORANGE STORE option: incompatible options
[ok]: GEORANGE STORE option: plain usage
[ok]: GEORANGE STOREDIST option: plain usage
[ok]: GEORANGE STOREDIST option: COUNT ASC and DESC
[ok]: Connect a slave to the master instance
[ok]: Redis.replicate_commands() must be issued before any write
[ok]: Redis.replicate_commands() must be issued before any write (2)
[ok]: Redis.set_repl() must be issued after replicate_commands()
[ok]: Redis.set_repl() don't accept invalid values
[ok]: Test selective replication of certain Redis commands from Lua
[ok]: PRNG is seeded randomly for command replication
[ok]: Using side effects is not a problem with command replication
[ok]: SORT speed, 100 element list BY <const>, 100 times
[ok]: BITOP and fuzzing
[ok]: AOF rewrite of set with hashtable encoding, string data
[26/42 done]: unit/sort (38 seconds)
Testing unit/hyperloglog
[27/42 done]: unit/scripting (14 seconds)
[ok]: maxmemory - only allkeys-* should remove non-volatile keys (allkeys-lru)
[ok]: AOF rewrite of set with intset encoding, int data
[ok]: BITOP or fuzzing
[ok]: AOF rewrite of set with hashtable encoding, int data
[ok]: maxmemory - only allkeys-* should remove non-volatile keys (volatile-lru)
[ok]: Memory efficiency with values in range 32
[ok]: AOF rewrite of hash with ziplist encoding, string data
[ok]: BITOP xor fuzzing
[ok]: BITOP NOT fuzzing
[ok]: BITOP with integer encoded source objects
[ok]: BITOP with non string source key
[ok]: BITOP with empty string after non empty string (issue #529)
[ok]: BITPOS bit=0 with empty key returns 0
[ok]: BITPOS bit=1 with empty key returns -1
[ok]: BITPOS bit=0 with string less than 1 word works
[ok]: BITPOS bit=1 with string less than 1 word works
[ok]: BITPOS bit=0 starting at unaligned address
[ok]: BITPOS bit=1 starting at unaligned address
[ok]: BITPOS bit=0 unaligned+full word+reminder
[ok]: BITPOS bit=1 unaligned+full word+reminder
[ok]: BITPOS bit=1 returns -1 if string is all 0 bits
[ok]: BITPOS bit=0 works with intervals
[ok]: BITPOS bit=1 works with intervals
[ok]: BITPOS bit=0 changes behavior if end is given
[ok]: AOF rewrite of hash with hashtable encoding, string data
[ok]: maxmemory - only allkeys-* should remove non-volatile keys (volatile-random)
[ok]: BITPOS bit=1 fuzzy testing using SETBIT
[ok]: MASTER and SLAVE dataset should be identical after complex ops
[ok]: AOF rewrite of hash with ziplist encoding, int data
[ok]: BITPOS bit=0 fuzzy testing using SETBIT
[ok]: Memory efficiency with values in range 64
[ok]: HyperLogLog self test passes
[ok]: PFADD without arguments creates an HLL value
[ok]: Approximated cardinality after creation is zero
[ok]: PFADD returns 1 when at least 1 reg was modified
[ok]: PFADD returns 0 when no reg was modified
[ok]: PFADD works with empty string (regression)
[ok]: PFCOUNT returns approximated cardinality of set
[28/42 done]: unit/bitops (15 seconds)
[29/42 done]: integration/replication-2 (43 seconds)
[ok]: AOF rewrite of hash with hashtable encoding, int data
[ok]: maxmemory - only allkeys-* should remove non-volatile keys (volatile-ttl)
[ok]: AOF rewrite of zset with ziplist encoding, string data
[ok]: HyperLogLogs are promote from sparse to dense
[ok]: Memory efficiency with values in range 128
[ok]: maxmemory - policy volatile-lru should only remove volatile keys.
[ok]: Test replication partial resync: ok after delay (diskless: no, reconnect: 1)
[ok]: AOF rewrite of zset with skiplist encoding, string data
[ok]: maxmemory - policy volatile-random should only remove volatile keys.
[ok]: MIGRATE can correctly transfer large values
[ok]: AOF rewrite of zset with ziplist encoding, int data
[ok]: MIGRATE can correctly transfer hashes
[ok]: HyperLogLog sparse encoding stress test
[ok]: Corrupted sparse HyperLogLogs are detected: Additionl at tail
[ok]: Corrupted sparse HyperLogLogs are detected: Broken magic
[ok]: Corrupted sparse HyperLogLogs are detected: Invalid encoding
[ok]: Corrupted dense HyperLogLogs are detected: Wrong length
[ok]: PFADD, PFCOUNT, PFMERGE type checking works
[ok]: PFMERGE results on the cardinality of union of sets
[ok]: Slave should be able to synchronize with the master
[ok]: Detect write load to master
[ok]: Memory efficiency with values in range 1024
[ok]: maxmemory - policy volatile-ttl should only remove volatile keys.
[ok]: MIGRATE timeout actually works
[ok]: AOF rewrite of zset with skiplist encoding, int data
[30/42 done]: unit/maxmemory (26 seconds)
[ok]: BGREWRITEAOF is delayed if BGSAVE is in progress
[ok]: BGREWRITEAOF is refused if already in progress
[31/42 done]: unit/aofrw (49 seconds)
[ok]: MIGRATE can migrate multiple keys at once
[ok]: MIGRATE with multiple keys must have empty key arg
[ok]: MIGRATE with mutliple keys migrate just existing ones
[ok]: MIGRATE with multiple keys: stress command rewriting
[ok]: MIGRATE with multiple keys: delete just ack keys
[32/42 done]: unit/dump (54 seconds)
[ok]: Memory efficiency with values in range 16384
[ok]: Connect multiple slaves at the same time (issue #141), diskless=no
[33/42 done]: unit/memefficiency (22 seconds)
[ok]: Test replication partial resync: backlog expired (diskless: no, reconnect: 1)
[ok]: LTRIM stress testing - ziplist
[34/42 done]: unit/type/list-2 (63 seconds)
[ok]: Slave should be able to synchronize with the master
[ok]: Detect write load to master
[ok]: Test replication partial resync: no reconnection, just sync (diskless: yes, reconnect: 0)
[ok]: PFCOUNT multiple-keys merge returns cardinality of union #1
[ok]: MASTER and SLAVE consistency with EVALSHA replication
[35/42 done]: integration/replication-3 (66 seconds)
[ok]: Slave should be able to synchronize with the master
[ok]: Detect write load to master
[ok]: PFCOUNT multiple-keys merge returns cardinality of union #2
[ok]: GEOADD + GEORANGE randomized test
[36/42 done]: unit/geo (39 seconds)
[ok]: Test replication partial resync: ok psync (diskless: yes, reconnect: 1)
[ok]: PFDEBUG GETREG returns the HyperLogLog raw registers
[ok]: PFADD / PFCOUNT cache invalidation works
[37/42 done]: unit/hyperloglog (39 seconds)
[ok]: Replication: commands with many arguments (issue #1221)
[ok]: Slave should be able to synchronize with the master
[ok]: Detect write load to master
[ok]: Replication of SPOP command -- alsoPropagate() API
[ok]: Stress tester for #3343-alike bugs
[ok]: Client output buffer hard limit is enforced
[38/42 done]: integration/replication-4 (78 seconds)
[ok]: Test replication partial resync: no backlog (diskless: yes, reconnect: 1)
[ok]: ziplist implementation: value encoding and backlink
[ok]: Connect multiple slaves at the same time (issue #141), diskless=yes
[ok]: Slave should be able to synchronize with the master
[ok]: Detect write load to master
[39/42 done]: integration/replication (95 seconds)
[ok]: Test replication partial resync: ok after delay (diskless: yes, reconnect: 1)
[ok]: ziplist implementation: encoding stress testing
[40/42 done]: unit/type/list-3 (105 seconds)
[ok]: Slave should be able to synchronize with the master
[ok]: Detect write load to master
[ok]: Client output buffer soft limit is not enforced if time is not overreached
[ok]: Test replication partial resync: backlog expired (diskless: yes, reconnect: 1)
[41/42 done]: integration/replication-psync (106 seconds)
[ok]: Client output buffer soft limit is enforced if time is overreached
[42/42 done]: unit/obuf-limits (101 seconds)

                   The End

Execution time of different units:
  0 seconds - unit/printver
  1 seconds - unit/type/incr
  1 seconds - unit/auth
  2 seconds - unit/scan
  1 seconds - unit/quit
  2 seconds - unit/keyspace
  2 seconds - unit/multi
  4 seconds - unit/protocol
  11 seconds - unit/expire
  16 seconds - unit/type/list
  18 seconds - unit/type/hash
  4 seconds - integration/rdb
  23 seconds - unit/other
  8 seconds - integration/aof
  1 seconds - integration/logging
  2 seconds - integration/convert-zipmap-hash-on-load
  1 seconds - unit/pubsub
  1 seconds - unit/slowlog
  1 seconds - unit/introspection
  27 seconds - unit/type/string
  2 seconds - unit/limits
  30 seconds - unit/type/set
  7 seconds - unit/introspection-2
  4 seconds - unit/bitfield
  37 seconds - unit/type/zset
  38 seconds - unit/sort
  14 seconds - unit/scripting
  15 seconds - unit/bitops
  43 seconds - integration/replication-2
  26 seconds - unit/maxmemory
  49 seconds - unit/aofrw
  54 seconds - unit/dump
  22 seconds - unit/memefficiency
  63 seconds - unit/type/list-2
  66 seconds - integration/replication-3
  39 seconds - unit/geo
  39 seconds - unit/hyperloglog
  78 seconds - integration/replication-4
  95 seconds - integration/replication
  105 seconds - unit/type/list-3
  106 seconds - integration/replication-psync
  101 seconds - unit/obuf-limits

\o/ All tests passed without errors!

Cleanup: may take some time... OK
make[1]: Leaving directory `/home/droid/software/Redis/redis-3.2.4/src'
```
