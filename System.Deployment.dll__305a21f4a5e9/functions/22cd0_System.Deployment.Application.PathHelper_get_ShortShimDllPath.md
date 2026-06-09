# System.Deployment.Application.PathHelper::get_ShortShimDllPath

- ea: `0x22cd0`
- end: `0x22d04`
- name: `System.Deployment.Application.PathHelper::get_ShortShimDllPath`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1dc60`

## callees

- `0x22c70`
- `0x22cd0`

## string_xrefs

- `0x22cdc`: `dfshim.dll`

## pseudocode

```c

```

## disassembly

```asm
0x22cd0  ldsfld   object System.Deployment.Application.PathHelper::_shortShimDllPath
0x22cd5  brtrue.s loc_22CF9
0x22cd7  call     string [mscorlib]System.Environment::get_SystemDirectory()
0x22cdc  ldstr    aDfshimDll// "dfshim.dll"
0x22ce1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x22ce6  stloc.0
0x22ce7  ldsflda  object System.Deployment.Application.PathHelper::_shortShimDllPath
0x22cec  ldloc.0
0x22ced  call     string System.Deployment.Application.PathHelper::GetShortPath(string longPath)
0x22cf2  ldnull
0x22cf3  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x22cf8  pop
0x22cf9  ldsfld   object System.Deployment.Application.PathHelper::_shortShimDllPath
0x22cfe  castclass [mscorlib]System.String
0x22d03  ret
```
