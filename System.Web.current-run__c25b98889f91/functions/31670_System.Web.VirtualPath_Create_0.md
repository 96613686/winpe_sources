# System.Web.VirtualPath::Create_0

- ea: `0x31670`
- end: `0x31844`
- name: `System.Web.VirtualPath::Create_0`
- size: `468`
- prototype: ``
- caller_count: `14`
- callee_count: `8`
- tags: ``

## callers

- `0x1ba90`
- `0x1bb20`
- `0x2c6f0`
- `0x315d0`
- `0x315e0`
- `0x315f0`
- `0x31600`
- `0x31610`
- `0x31620`
- `0x31630`
- `0x31640`
- `0x31650`
- `0x31660`
- `0x32080`

## callees

- `0x18990`
- `0x30f00`
- `0x31670`
- `0x34f20`
- `0x595c0`
- `0x598d0`
- `0x59a50`
- `0x59c80`

## string_xrefs

- `0x317ee`: `VirtualPath_AllowRelativePath`
- `0x3168a`: `virtualPath`
- `0x31706`: `Invalid_vpath`
- `0x31737`: `Invalid_vpath`
- `0x3178f`: `VirtualPath_AllowAppRelativePath`
- `0x317ba`: `VirtualPath_AllowAbsolutePath`
- `0x31816`: `VirtualPath_AllowAbsolutePath`

## pseudocode

```c

```

## disassembly

```asm
0x31670  ldarg.0
0x31671  brfalse.s loc_3167B
0x31673  ldarg.0
0x31674  callvirt instance string [mscorlib]System.String::Trim()
0x31679  starg.s  0
0x3167b  ldarg.0
0x3167c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31681  brfalse.s loc_31695
0x31683  ldarg.1
0x31684  ldc.i4.1
0x31685  and
0x31686  brfalse.s loc_3168A
0x31688  ldnull
0x31689  ret
0x3168a  ldstr    aVirtualpath_0// "virtualPath"
0x3168f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x31694  throw
0x31695  ldc.i4.0
0x31696  stloc.0
0x31697  ldc.i4.0
0x31698  stloc.1
0x31699  ldarg.0
0x3169a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3169f  stloc.2
0x316a0  ldarg.0
0x316a1  stloc.s  5
0x316a3  ldloc.s  5
0x316a5  conv.u
0x316a6  stloc.s  4
0x316a8  ldloc.s  4
0x316aa  brfalse.s loc_316B6
0x316ac  ldloc.s  4
0x316ae  call     int32 [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::get_OffsetToStringData()
0x316b3  add
0x316b4  stloc.s  4
0x316b6  ldc.i4.0
0x316b7  stloc.s  6
0x316b9  br.s     loc_31726
0x316bb  ldloc.s  4
0x316bd  ldloc.s  6
0x316bf  conv.i
0x316c0  ldc.i4.2
0x316c1  mul
0x316c2  add
0x316c3  ldind.u2
0x316c4  stloc.s  7
0x316c6  ldloc.s  7
0x316c8  ldc.i4.s 0x2E
0x316ca  bgt.un.s loc_316D8
0x316cc  ldloc.s  7
0x316ce  brfalse.s loc_31706
0x316d0  ldloc.s  7
0x316d2  ldc.i4.s 0x2E
0x316d4  beq.s    loc_31702
0x316d6  br.s     loc_31720
0x316d8  ldloc.s  7
0x316da  ldc.i4.s 0x2F
0x316dc  beq.s    loc_316E6
0x316de  ldloc.s  7
0x316e0  ldc.i4.s 0x5C
0x316e2  beq.s    loc_316FE
0x316e4  br.s     loc_31720
0x316e6  ldloc.s  6
0x316e8  ldc.i4.0
0x316e9  ble.s    loc_31720
0x316eb  ldloc.s  4
0x316ed  ldloc.s  6
0x316ef  ldc.i4.1
0x316f0  sub
0x316f1  conv.i
0x316f2  ldc.i4.2
0x316f3  mul
0x316f4  add
0x316f5  ldind.u2
0x316f6  ldc.i4.s 0x2F
0x316f8  bne.un.s loc_31720
0x316fa  ldc.i4.1
0x316fb  stloc.0
0x316fc  br.s     loc_31720
0x316fe  ldc.i4.1
0x316ff  stloc.0
0x31700  br.s     loc_31720
0x31702  ldc.i4.1
0x31703  stloc.1
0x31704  br.s     loc_31720
0x31706  ldstr    aInvalidVpath// "Invalid_vpath"
0x3170b  ldc.i4.1
0x3170c  newarr   [mscorlib]System.Object
0x31711  dup
0x31712  ldc.i4.0
0x31713  ldarg.0
0x31714  stelem.ref
0x31715  call     string System.Web.SR::GetString(string name, object[] args)
0x3171a  newobj   instance void System.Web.HttpException::.ctor(string message)
0x3171f  throw
0x31720  ldloc.s  6
0x31722  ldc.i4.1
0x31723  add
0x31724  stloc.s  6
0x31726  ldloc.s  6
0x31728  ldloc.2
0x31729  blt.s    loc_316BB
0x3172b  ldnull
0x3172c  stloc.s  5
0x3172e  ldloc.0
0x3172f  brfalse.s loc_31759
0x31731  ldarg.1
0x31732  ldc.i4.s 0x20
0x31734  and
0x31735  brfalse.s loc_31751
0x31737  ldstr    aInvalidVpath// "Invalid_vpath"
0x3173c  ldc.i4.1
0x3173d  newarr   [mscorlib]System.Object
0x31742  dup
0x31743  ldc.i4.0
0x31744  ldarg.0
0x31745  stelem.ref
0x31746  call     string System.Web.SR::GetString(string name, object[] args)
0x3174b  newobj   instance void System.Web.HttpException::.ctor(string message)
0x31750  throw
0x31751  ldarg.0
0x31752  call     string System.Web.Util.UrlPath::FixVirtualPathSlashes(string virtualPath)
0x31757  starg.s  0
0x31759  ldarg.1
0x3175a  ldc.i4.2
0x3175b  and
0x3175c  brfalse.s loc_31766
0x3175e  ldarg.0
0x3175f  call     string System.Web.Util.UrlPath::AppendSlashToPathIfNeeded(string path)
0x31764  starg.s  0
0x31766  newobj   instance void System.Web.VirtualPath::.ctor()
0x3176b  stloc.3
0x3176c  ldarg.0
0x3176d  call     bool System.Web.Util.UrlPath::IsAppRelativePath(string path)
0x31772  brfalse.s loc_317DD
0x31774  ldloc.1
0x31775  brfalse.s loc_3177F
0x31777  ldarg.0
0x31778  call     string System.Web.Util.UrlPath::ReduceVirtualPath(string path)
0x3177d  starg.s  0
0x3177f  ldarg.0
0x31780  ldc.i4.0
0x31781  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x31786  ldc.i4.s 0x7E
0x31788  bne.un.s loc_317B5
0x3178a  ldarg.1
0x3178b  ldc.i4.8
0x3178c  and
0x3178d  brtrue.s loc_317A9
0x3178f  ldstr    aVirtualpathAll_0// "VirtualPath_AllowAppRelativePath"
0x31794  ldc.i4.1
0x31795  newarr   [mscorlib]System.Object
0x3179a  dup
0x3179b  ldc.i4.0
0x3179c  ldarg.0
0x3179d  stelem.ref
0x3179e  call     string System.Web.SR::GetString(string name, object[] args)
0x317a3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x317a8  throw
0x317a9  ldloc.3
0x317aa  ldarg.0
0x317ab  stfld    string System.Web.VirtualPath::_appRelativeVirtualPath
0x317b0  br       loc_31842
0x317b5  ldarg.1
0x317b6  ldc.i4.4
0x317b7  and
0x317b8  brtrue.s loc_317D4
0x317ba  ldstr    aVirtualpathAll_1// "VirtualPath_AllowAbsolutePath"
0x317bf  ldc.i4.1
0x317c0  newarr   [mscorlib]System.Object
0x317c5  dup
0x317c6  ldc.i4.0
0x317c7  ldarg.0
0x317c8  stelem.ref
0x317c9  call     string System.Web.SR::GetString(string name, object[] args)
0x317ce  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x317d3  throw
0x317d4  ldloc.3
0x317d5  ldarg.0
0x317d6  stfld    string System.Web.VirtualPath::_virtualPath
0x317db  br.s     loc_31842
0x317dd  ldarg.0
0x317de  ldc.i4.0
0x317df  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x317e4  ldc.i4.s 0x2F
0x317e6  beq.s    loc_31811
0x317e8  ldarg.1
0x317e9  ldc.i4.s 0x10
0x317eb  and
0x317ec  brtrue.s loc_31808
0x317ee  ldstr    aVirtualpathAll// "VirtualPath_AllowRelativePath"
0x317f3  ldc.i4.1
0x317f4  newarr   [mscorlib]System.Object
0x317f9  dup
0x317fa  ldc.i4.0
0x317fb  ldarg.0
0x317fc  stelem.ref
0x317fd  call     string System.Web.SR::GetString(string name, object[] args)
0x31802  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x31807  throw
0x31808  ldloc.3
0x31809  ldarg.0
0x3180a  stfld    string System.Web.VirtualPath::_virtualPath
0x3180f  br.s     loc_31842
0x31811  ldarg.1
0x31812  ldc.i4.4
0x31813  and
0x31814  brtrue.s loc_31830
0x31816  ldstr    aVirtualpathAll_1// "VirtualPath_AllowAbsolutePath"
0x3181b  ldc.i4.1
0x3181c  newarr   [mscorlib]System.Object
0x31821  dup
0x31822  ldc.i4.0
0x31823  ldarg.0
0x31824  stelem.ref
0x31825  call     string System.Web.SR::GetString(string name, object[] args)
0x3182a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3182f  throw
0x31830  ldloc.1
0x31831  brfalse.s loc_3183B
0x31833  ldarg.0
0x31834  call     string System.Web.Util.UrlPath::ReduceVirtualPath(string path)
0x31839  starg.s  0
0x3183b  ldloc.3
0x3183c  ldarg.0
0x3183d  stfld    string System.Web.VirtualPath::_virtualPath
0x31842  ldloc.3
0x31843  ret
```
