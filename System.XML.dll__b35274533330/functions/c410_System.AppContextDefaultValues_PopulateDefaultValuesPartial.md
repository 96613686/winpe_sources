# System.AppContextDefaultValues::PopulateDefaultValuesPartial

- ea: `0xc410`
- end: `0xc4a1`
- name: `System.AppContextDefaultValues::PopulateDefaultValuesPartial`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0xc260`

## callees

- `0xc410`
- `0xc950`

## string_xrefs

- `0xc44d`: `Switch.System.Xml.DontThrowOnInvalidSurrogatePairs`
- `0xc47f`: `Switch.System.Xml.DontThrowOnInvalidSurrogatePairs`
- `0xc458`: `Switch.System.Xml.IgnoreEmptyKeySequences`
- `0xc48a`: `Switch.System.Xml.IgnoreEmptyKeySequences`
- `0xc46b`: `Switch.System.Xml.IgnoreKindInUtcTimeSerialization`
- `0xc495`: `Switch.System.Xml.IgnoreKindInUtcTimeSerialization`

## pseudocode

```c

```

## disassembly

```asm
0xc410  ldarg.0
0xc411  ldstr    aNetcore// ".NETCore"
0xc416  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc41b  brtrue.s loc_C445
0xc41d  ldarg.0
0xc41e  ldstr    aNetframework// ".NETFramework"
0xc423  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc428  brtrue.s loc_C445
0xc42a  ldarg.0
0xc42b  ldstr    aWindowsphone// "WindowsPhone"
0xc430  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc435  brtrue.s loc_C477
0xc437  ldarg.0
0xc438  ldstr    aWindowsphoneap// "WindowsPhoneApp"
0xc43d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc442  brtrue.s loc_C477
0xc444  ret
0xc445  ldarg.2
0xc446  ldc.i4   0x9E36
0xc44b  bgt.s    loc_C463
0xc44d  ldstr    aSwitchSystemXm// "Switch.System.Xml.DontThrowOnInvalidSur"...
0xc452  ldc.i4.1
0xc453  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xc458  ldstr    aSwitchSystemXm_0// "Switch.System.Xml.IgnoreEmptyKeySequenc"...
0xc45d  ldc.i4.1
0xc45e  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xc463  ldarg.2
0xc464  ldc.i4   0x9E99
0xc469  bgt.s    loc_C4A0
0xc46b  ldstr    aSwitchSystemXm_1// "Switch.System.Xml.IgnoreKindInUtcTimeSe"...
0xc470  ldc.i4.1
0xc471  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xc476  ret
0xc477  ldarg.2
0xc478  ldc.i4   0x138E4
0xc47d  bgt.s    loc_C4A0
0xc47f  ldstr    aSwitchSystemXm// "Switch.System.Xml.DontThrowOnInvalidSur"...
0xc484  ldc.i4.1
0xc485  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xc48a  ldstr    aSwitchSystemXm_0// "Switch.System.Xml.IgnoreEmptyKeySequenc"...
0xc48f  ldc.i4.1
0xc490  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xc495  ldstr    aSwitchSystemXm_1// "Switch.System.Xml.IgnoreKindInUtcTimeSe"...
0xc49a  ldc.i4.1
0xc49b  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xc4a0  ret
```
