# Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadExtendedActionsPaneItem

- ea: `0x3e00`
- end: `0x3e7a`
- name: `Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadExtendedActionsPaneItem`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x3d50`

## callees

- `0x3830`
- `0x3850`
- `0x38a0`
- `0x38c0`
- `0x38e0`
- `0x3e00`

## pseudocode

```c

```

## disassembly

```asm
0x3e00  ldarg.0
0x3e01  ldfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_displayName
0x3e06  ldarg.2
0x3e07  ldind.i4
0x3e08  ldelem.ref
0x3e09  stloc.0
0x3e0a  ldloc.0
0x3e0b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3e10  brtrue.s loc_3E19
0x3e12  ldarg.1
0x3e13  ldloc.0
0x3e14  callvirt instance void Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData::set_DisplayName(string value)
0x3e19  ldarg.0
0x3e1a  ldfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_mnemonicDisplayName
0x3e1f  ldarg.2
0x3e20  ldind.i4
0x3e21  ldelem.ref
0x3e22  stloc.1
0x3e23  ldloc.1
0x3e24  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3e29  brtrue.s loc_3E32
0x3e2b  ldarg.1
0x3e2c  ldloc.1
0x3e2d  callvirt instance void Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData::set_MnemonicDisplayName(string value)
0x3e32  ldarg.0
0x3e33  ldfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_description
0x3e38  ldarg.2
0x3e39  ldind.i4
0x3e3a  ldelem.ref
0x3e3b  stloc.2
0x3e3c  ldloc.2
0x3e3d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3e42  brtrue.s loc_3E4B
0x3e44  ldarg.1
0x3e45  ldloc.2
0x3e46  callvirt instance void Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData::set_Description(string value)
0x3e4b  ldarg.0
0x3e4c  ldfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_languageIndependentName
0x3e51  ldarg.2
0x3e52  ldind.i4
0x3e53  ldelem.ref
0x3e54  stloc.3
0x3e55  ldloc.3
0x3e56  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3e5b  brtrue.s loc_3E64
0x3e5d  ldarg.1
0x3e5e  ldloc.3
0x3e5f  callvirt instance void Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData::set_LanguageIndependentName(string value)
0x3e64  ldarg.1
0x3e65  ldarg.0
0x3e66  ldfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_imageIndex
0x3e6b  ldarg.2
0x3e6c  ldind.i4
0x3e6d  ldelem.i4
0x3e6e  callvirt instance void Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData::set_ImageIndex(int32 value)
0x3e73  ldarg.2
0x3e74  dup
0x3e75  ldind.i4
0x3e76  ldc.i4.1
0x3e77  add
0x3e78  stind.i4
0x3e79  ret
```
