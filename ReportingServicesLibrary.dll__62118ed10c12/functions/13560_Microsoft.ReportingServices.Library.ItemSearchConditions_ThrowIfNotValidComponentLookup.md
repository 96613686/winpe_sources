# Microsoft.ReportingServices.Library.ItemSearchConditions::ThrowIfNotValidComponentLookup

- ea: `0x13560`
- end: `0x135ba`
- name: `Microsoft.ReportingServices.Library.ItemSearchConditions::ThrowIfNotValidComponentLookup`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a580`

## callees

- `0x13560`

## string_xrefs

- `0x1356d`: `ComponentLookup`
- `0x13580`: `ComponentLookup`

## pseudocode

```c

```

## disassembly

```asm
0x13560  ldarg.1
0x13561  ldstr    asc_96832// "/"
0x13566  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x1356b  brfalse.s loc_1357D
0x1356d  ldstr    aComponentlooku// "ComponentLookup"
0x13572  ldstr    aFolder// "Folder"
0x13577  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x1357c  throw
0x1357d  ldarg.2
0x1357e  brfalse.s loc_13590
0x13580  ldstr    aComponentlooku// "ComponentLookup"
0x13585  ldstr    aBooleanoperato// "BooleanOperator"
0x1358a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x1358f  throw
0x13590  ldarg.0
0x13591  ldfld    string[] Microsoft.ReportingServices.Library.ItemSearchConditions::m_requiredComponentLookupProperties
0x13596  stloc.0
0x13597  ldc.i4.0
0x13598  stloc.1
0x13599  br.s     loc_135B3
0x1359b  ldloc.0
0x1359c  ldloc.1
0x1359d  ldelem.ref
0x1359e  stloc.2
0x1359f  ldarg.0
0x135a0  ldloc.2
0x135a1  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Library.ItemSearchCondition>::ContainsKey(var<u1>)
0x135a6  brtrue.s loc_135AF
0x135a8  ldloc.2
0x135a9  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x135ae  throw
0x135af  ldloc.1
0x135b0  ldc.i4.1
0x135b1  add
0x135b2  stloc.1
0x135b3  ldloc.1
0x135b4  ldloc.0
0x135b5  ldlen
0x135b6  conv.i4
0x135b7  blt.s    loc_1359B
0x135b9  ret
```
