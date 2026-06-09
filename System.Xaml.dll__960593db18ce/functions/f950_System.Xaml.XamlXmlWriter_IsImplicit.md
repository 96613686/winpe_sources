# System.Xaml.XamlXmlWriter::IsImplicit

- ea: `0xf950`
- end: `0xf98f`
- name: `System.Xaml.XamlXmlWriter::IsImplicit`
- size: `63`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x28630`
- `0x29400`
- `0x2d240`
- `0x2d4c0`
- `0x2d910`
- `0x2dae0`

## callees

- `0x8b20`
- `0x8b30`
- `0x8b80`
- `0x8be0`
- `0xa6e0`
- `0xb280`
- `0xf950`

## pseudocode

```c

```

## disassembly

```asm
0xf950  ldarg.0
0xf951  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0xf956  brfalse.s loc_F98D
0xf958  ldarg.0
0xf959  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0xf95e  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0xf963  brtrue.s loc_F98B
0xf965  ldarg.0
0xf966  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Initialization()
0xf96b  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0xf970  brtrue.s loc_F98B
0xf972  ldarg.0
0xf973  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0xf978  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0xf97d  brtrue.s loc_F98B
0xf97f  ldarg.0
0xf980  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_UnknownContent()
0xf985  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0xf98a  ret
0xf98b  ldc.i4.1
0xf98c  ret
0xf98d  ldc.i4.0
0xf98e  ret
```
