# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry::CompareTo

- ea: `0xd700`
- end: `0xd71d`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry::CompareTo`
- size: `29`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd650`
- `0xd670`
- `0xd690`
- `0xd6e0`
- `0xd720`

## callees

- `0xd700`

## pseudocode

```c

```

## disassembly

```asm
0xd700  ldnull
0xd701  ldarg.1
0xd702  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0xd707  brfalse.s loc_D70B
0xd709  ldc.i4.1
0xd70a  ret
0xd70b  ldarg.0
0xd70c  ldfld    string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry::name
0xd711  ldarg.1
0xd712  ldfld    string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry::name
0xd717  callvirt instance int32 [mscorlib]System.String::CompareTo(string)
0xd71c  ret
```
