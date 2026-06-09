# Microsoft.VisualStudio.Setup.Extensions::GetDisplayName

- ea: `0x56d0`
- end: `0x5706`
- name: `Microsoft.VisualStudio.Setup.Extensions::GetDisplayName`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x55e0`
- `0x56d0`
- `0x6ca0`
- `0x81e0`
- `0x8760`
- `0xc1a0`

## pseudocode

```c

```

## disassembly

```asm
0x56d0  ldarg.0
0x56d1  ldstr    aPackage// "package"
0x56d6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x56db  ldarg.0
0x56dc  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.ILocalizedResources::get_LocalizedResources()
0x56e1  dup
0x56e2  brtrue.s loc_56E8
0x56e4  pop
0x56e5  ldnull
0x56e6  br.s     loc_56FB
0x56e8  ldarg.1
0x56e9  ldarg.2
0x56ea  call     class Microsoft.VisualStudio.Setup.LocalizedResource Microsoft.VisualStudio.Setup.Extensions::FindResource(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.LocalizedResource> source, class [mscorlib]System.Globalization.CultureInfo culture, [opt] valuetype Microsoft.VisualStudio.Setup.LocalizedResourceFallback fallback)
0x56ef  dup
0x56f0  brtrue.s loc_56F6
0x56f2  pop
0x56f3  ldnull
0x56f4  br.s     loc_56FB
0x56f6  call     instance string Microsoft.VisualStudio.Setup.LocalizedResource::get_Title()
0x56fb  dup
0x56fc  brtrue.s loc_5705
0x56fe  pop
0x56ff  ldarg.0
0x5700  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x5705  ret
```
