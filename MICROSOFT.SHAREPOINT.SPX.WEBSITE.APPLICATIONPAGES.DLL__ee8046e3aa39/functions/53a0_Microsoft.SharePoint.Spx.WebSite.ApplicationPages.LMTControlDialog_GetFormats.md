# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::GetFormats

- ea: `0x53a0`
- end: `0x53e5`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::GetFormats`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x53a0`
- `0x53f0`
- `0x56d0`

## string_xrefs

- `0x53a3`: `cultureName`

## pseudocode

```c

```

## disassembly

```asm
0x53a0  ldarg.0
0x53a1  brtrue.s loc_53AE
0x53a3  ldstr    aCulturename_0// "cultureName"
0x53a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x53ad  throw
0x53ae  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x53b3  stloc.0
0x53b4  ldarg.0
0x53b5  ldstr    aEsEs// "es-ES"
0x53ba  ldc.i4.5
0x53bb  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x53c0  brfalse.s loc_53C9
0x53c2  ldstr    aEsMx// "es-MX"
0x53c7  starg.s  0
0x53c9  ldloc.0
0x53ca  ldarg.0
0x53cb  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendTimeFormats(class [mscorlib]System.Text.StringBuilder buf, string cultureName)
0x53d0  ldloc.0
0x53d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x53d6  pop
0x53d7  ldloc.0
0x53d8  ldarg.0
0x53d9  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendDateFormats(class [mscorlib]System.Text.StringBuilder buf, string cultureName)
0x53de  ldloc.0
0x53df  callvirt instance string [mscorlib]System.Object::ToString()
0x53e4  ret
```
