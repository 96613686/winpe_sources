# System.Web.Util.UrlPath::MakeVirtualPathAppAbsoluteReduceAndCheck

- ea: `0x59e70`
- end: `0x59eae`
- name: `System.Web.Util.UrlPath::MakeVirtualPathAppAbsoluteReduceAndCheck`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x162410`
- `0x162480`

## callees

- `0x34f20`
- `0x59880`
- `0x59d40`
- `0x59de0`
- `0x59e70`

## string_xrefs

- `0x59e73`: `virtualPath`
- `0x59e92`: `Invalid_app_VirtualPath`

## pseudocode

```c

```

## disassembly

```asm
0x59e70  ldarg.0
0x59e71  brtrue.s loc_59E7E
0x59e73  ldstr    aVirtualpath_0// "virtualPath"
0x59e78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x59e7d  throw
0x59e7e  ldarg.0
0x59e7f  call     string System.Web.Util.UrlPath::MakeVirtualPathAppAbsolute(string virtualPath)
0x59e84  call     string System.Web.Util.UrlPath::Reduce(string path)
0x59e89  stloc.0
0x59e8a  ldloc.0
0x59e8b  call     bool System.Web.Util.UrlPath::VirtualPathStartsWithAppPath(string virtualPath)
0x59e90  brtrue.s loc_59EAC
0x59e92  ldstr    aInvalidAppVirt// "Invalid_app_VirtualPath"
0x59e97  ldc.i4.1
0x59e98  newarr   [mscorlib]System.Object
0x59e9d  dup
0x59e9e  ldc.i4.0
0x59e9f  ldarg.0
0x59ea0  stelem.ref
0x59ea1  call     string System.Web.SR::GetString(string name, object[] args)
0x59ea6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x59eab  throw
0x59eac  ldloc.0
0x59ead  ret
```
