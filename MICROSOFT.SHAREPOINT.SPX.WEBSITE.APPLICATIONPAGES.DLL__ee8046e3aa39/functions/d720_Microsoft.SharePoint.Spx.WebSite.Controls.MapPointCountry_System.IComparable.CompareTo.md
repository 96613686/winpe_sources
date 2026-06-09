# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry::System.IComparable.CompareTo

- ea: `0xd720`
- end: `0xd743`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry::System.IComparable.CompareTo`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xd650`
- `0xd700`
- `0xd720`

## string_xrefs

- `0xd730`: `Object is not comparable.`

## pseudocode

```c

```

## disassembly

```asm
0xd720  ldarg.1
0xd721  isinst   Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry
0xd726  stloc.0
0xd727  ldloc.0
0xd728  ldnull
0xd729  call     bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry::op_Equality(class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry a, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry b)
0xd72e  brfalse.s loc_D73B
0xd730  ldstr    aObjectIsNotCom// "Object is not comparable."
0xd735  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xd73a  throw
0xd73b  ldarg.0
0xd73c  ldloc.0
0xd73d  call     instance int32 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry::CompareTo(class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointCountry country)
0xd742  ret
```
