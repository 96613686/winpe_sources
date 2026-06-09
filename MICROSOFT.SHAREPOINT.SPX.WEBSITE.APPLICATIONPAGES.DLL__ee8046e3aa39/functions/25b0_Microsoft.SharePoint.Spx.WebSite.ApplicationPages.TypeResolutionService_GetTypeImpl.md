# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.TypeResolutionService::GetTypeImpl

- ea: `0x25b0`
- end: `0x2616`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.TypeResolutionService::GetTypeImpl`
- size: `102`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2570`
- `0x2580`
- `0x2590`

## callees

- `0x25b0`
- `0x2620`
- `0x2640`

## pseudocode

```c

```

## disassembly

```asm
0x25b0  ldnull
0x25b1  stloc.0
0x25b2  ldnull
0x25b3  stloc.1
0x25b4  ldnull
0x25b5  stloc.2
0x25b6  ldarg.0
0x25b7  brfalse.s loc_25EC
0x25b9  ldarg.0
0x25ba  ldc.i4.s 0x2C
0x25bc  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x25c1  stloc.3
0x25c2  ldloc.3
0x25c3  ldc.i4.0
0x25c4  blt.s    loc_25E5
0x25c6  ldarg.0
0x25c7  ldc.i4.0
0x25c8  ldloc.3
0x25c9  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x25ce  callvirt instance string [mscorlib]System.String::Trim()
0x25d3  stloc.1
0x25d4  ldarg.0
0x25d5  ldloc.3
0x25d6  ldc.i4.1
0x25d7  add
0x25d8  callvirt instance string [mscorlib]System.String::Substring(int32)
0x25dd  callvirt instance string [mscorlib]System.String::Trim()
0x25e2  stloc.2
0x25e3  br.s     loc_25EC
0x25e5  ldarg.0
0x25e6  callvirt instance string [mscorlib]System.String::Trim()
0x25eb  stloc.1
0x25ec  ldloc.2
0x25ed  brfalse.s loc_25F8
0x25ef  ldloc.1
0x25f0  ldloc.2
0x25f1  ldarg.1
0x25f2  call     class [mscorlib]System.Type Microsoft.SharePoint.Spx.WebSite.ApplicationPages.TypeResolutionService::GetTypeFromSpecifiedAssembly(string name, string assemblyName, bool ignoreCase)
0x25f7  ret
0x25f8  ldloc.1
0x25f9  ldarg.1
0x25fa  call     class [mscorlib]System.Type Microsoft.SharePoint.Spx.WebSite.ApplicationPages.TypeResolutionService::GetTypeFromStandardAssemblies(string name, bool ignoreCase)
0x25ff  stloc.0
0x2600  ldloc.0
0x2601  ldnull
0x2602  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2607  brfalse.s loc_260B
0x2609  ldloc.0
0x260a  ret
0x260b  ldarg.0
0x260c  ldc.i4.0
0x260d  ldarg.1
0x260e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool, bool)
0x2613  stloc.0
0x2614  ldloc.0
0x2615  ret
```
