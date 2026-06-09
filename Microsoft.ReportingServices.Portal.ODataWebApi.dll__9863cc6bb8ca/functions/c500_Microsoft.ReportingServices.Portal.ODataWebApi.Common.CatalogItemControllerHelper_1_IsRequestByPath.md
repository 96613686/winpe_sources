# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::IsRequestByPath

- ea: `0xc500`
- end: `0xc5ab`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::IsRequestByPath`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc500`

## string_xrefs

- `0xc501`: `Path='`

## pseudocode

```c

```

## disassembly

```asm
0xc500  ldarg.2
0xc501  ldstr    aPath_1// "Path='"
0xc506  stind.ref
0xc507  ldc.i4.0
0xc508  stloc.0
0xc509  ldarg.1
0xc50a  ldarg.2
0xc50b  ldind.ref
0xc50c  ldc.i4.5
0xc50d  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xc512  brfalse.s loc_C548
0xc514  ldc.i4.1
0xc515  stloc.0
0xc516  ldarg.2
0xc517  ldarg.1
0xc518  ldarg.2
0xc519  ldind.ref
0xc51a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc51f  ldarg.1
0xc520  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc525  ldarg.2
0xc526  ldind.ref
0xc527  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc52c  sub
0xc52d  ldc.i4.1
0xc52e  sub
0xc52f  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xc534  stind.ref
0xc535  ldarg.2
0xc536  ldarg.2
0xc537  ldind.ref
0xc538  ldstr    asc_10442// "''"
0xc53d  ldstr    asc_1043E// "'"
0xc542  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xc547  stind.ref
0xc548  ldloc.0
0xc549  brtrue.s loc_C5A9
0xc54b  ldloca.s 1
0xc54d  initobj  [mscorlib]System.Guid
0xc553  ldarg.1
0xc554  ldloca.s 1
0xc556  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xc55b  stloc.2
0xc55c  ldloc.2
0xc55d  brtrue.s loc_C594
0xc55f  ldarg.1
0xc560  ldstr    asc_12644// "'/"
0xc565  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0xc56a  brfalse.s loc_C594
0xc56c  ldarg.2
0xc56d  ldarg.1
0xc56e  ldc.i4.1
0xc56f  ldarg.1
0xc570  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc575  ldc.i4.2
0xc576  sub
0xc577  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xc57c  stind.ref
0xc57d  ldc.i4.1
0xc57e  stloc.0
0xc57f  ldarg.2
0xc580  ldarg.2
0xc581  ldind.ref
0xc582  ldstr    asc_10442// "''"
0xc587  ldstr    asc_1043E// "'"
0xc58c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xc591  stind.ref
0xc592  br.s     loc_C5A9
0xc594  ldloc.2
0xc595  brtrue.s loc_C5A9
0xc597  ldarg.1
0xc598  ldstr    asc_10432// "/"
0xc59d  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0xc5a2  brfalse.s loc_C5A9
0xc5a4  ldarg.2
0xc5a5  ldarg.1
0xc5a6  stind.ref
0xc5a7  ldc.i4.1
0xc5a8  stloc.0
0xc5a9  ldloc.0
0xc5aa  ret
```
