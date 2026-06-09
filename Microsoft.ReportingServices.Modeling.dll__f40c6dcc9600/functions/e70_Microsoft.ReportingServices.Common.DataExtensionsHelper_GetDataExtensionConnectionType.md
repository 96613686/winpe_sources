# Microsoft.ReportingServices.Common.DataExtensionsHelper::GetDataExtensionConnectionType

- ea: `0xe70`
- end: `0xe9a`
- name: `Microsoft.ReportingServices.Common.DataExtensionsHelper::GetDataExtensionConnectionType`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xe70`

## string_xrefs

- `0xe70`: `Microsoft.ReportingServices.DataExtensions.dll`

## pseudocode

```c

```

## disassembly

```asm
0xe70  ldstr    aMicrosoftRepor// "Microsoft.ReportingServices.DataExtensi"...
0xe75  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0xe7a  ldarg.0
0xe7b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0xe80  ldarg.1
0xe81  ldc.i4.s 0x18
0xe83  ldnull
0xe84  ldnull
0xe85  ldnull
0xe86  callvirt instance object [mscorlib]System.Type::InvokeMember(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, object, object[])
0xe8b  castclass [mscorlib]System.Type
0xe90  stloc.0
0xe91  leave.s  loc_E98
0xe93  pop
0xe94  ldnull
0xe95  stloc.0
0xe96  leave.s  loc_E98
0xe98  ldloc.0
0xe99  ret
```
