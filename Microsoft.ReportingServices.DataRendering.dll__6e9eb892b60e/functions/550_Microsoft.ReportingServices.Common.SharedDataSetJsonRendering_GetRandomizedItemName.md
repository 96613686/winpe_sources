# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRandomizedItemName

- ea: `0x550`
- end: `0x584`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRandomizedItemName`
- size: `52`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3f0`
- `0x860`
- `0x940`
- `0xdb0`

## pseudocode

```c

```

## disassembly

```asm
0x550  call     class [mscorlib]System.Security.Cryptography.RandomNumberGenerator [mscorlib]System.Security.Cryptography.RandomNumberGenerator::Create()
0x555  ldc.i4.4
0x556  newarr   [mscorlib]System.Byte
0x55b  stloc.0
0x55c  ldloc.0
0x55d  callvirt instance void [mscorlib]System.Security.Cryptography.RandomNumberGenerator::GetBytes(unsigned int8[])
0x562  ldstr    a01// "{0}_{1}"
0x567  ldarg.0
0x568  ldloc.0
0x569  ldc.i4.0
0x56a  call     string [mscorlib]System.BitConverter::ToString(unsigned int8[], int32)
0x56f  ldstr    asc_E5C2// "-"
0x574  ldsfld   string [mscorlib]System.String::Empty
0x579  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x57e  call     string [mscorlib]System.String::Format(string, object, object)
0x583  ret
```
