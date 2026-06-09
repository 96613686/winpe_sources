# Microsoft.ReportingServices.Common.DataExtensionsHelper::GetDataExtensionConnectionType

- ea: `0x39f10`
- end: `0x39f3a`
- name: `Microsoft.ReportingServices.Common.DataExtensionsHelper::GetDataExtensionConnectionType`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x39f10`

## string_xrefs

- `0x39f10`: `Microsoft.ReportingServices.DataExtensions.dll`

## pseudocode

```c

```

## disassembly

```asm
0x39f10  ldstr    aMicrosoftRepor_146// "Microsoft.ReportingServices.DataExtensi"...
0x39f15  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x39f1a  ldarg.0
0x39f1b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x39f20  ldarg.1
0x39f21  ldc.i4.s 0x18
0x39f23  ldnull
0x39f24  ldnull
0x39f25  ldnull
0x39f26  callvirt instance object [mscorlib]System.Type::InvokeMember(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, object, object[])
0x39f2b  castclass [mscorlib]System.Type
0x39f30  stloc.0
0x39f31  leave.s  loc_39F38
0x39f33  pop
0x39f34  ldnull
0x39f35  stloc.0
0x39f36  leave.s  loc_39F38
0x39f38  ldloc.0
0x39f39  ret
```
