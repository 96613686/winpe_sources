# MS.Internal.Printing.Configuration.PageMediaSizeSetting::get_MediaSizeHeight

- ea: `0xf6c0`
- end: `0xf715`
- name: `MS.Internal.Printing.Configuration.PageMediaSizeSetting::get_MediaSizeHeight`
- size: `85`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0xf7e0`
- `0x14440`
- `0x14ac0`
- `0x1d6d0`

## callees

- `0xf650`
- `0xf6c0`
- `0x13e30`
- `0x16bc0`
- `0x16c10`
- `0x16ed0`

## pseudocode

```c

```

## disassembly

```asm
0xf6c0  ldarg.0
0xf6c1  ldstr    aMediasizeheigh// "MediaSizeHeight"
0xf6c6  call     instance int32 MS.Internal.Printing.Configuration.PrintTicketFeature::get_Item(string propertyName)
0xf6cb  stloc.0
0xf6cc  ldloc.0
0xf6cd  ldc.i4   0x80000000
0xf6d2  bne.un.s loc_F70E
0xf6d4  ldarg.0
0xf6d5  call     instance valuetype System.Printing.PageMediaSizeName MS.Internal.Printing.Configuration.PageMediaSizeSetting::get_Value()
0xf6da  brtrue.s loc_F70E
0xf6dc  ldarg.0
0xf6dd  call     instance class MS.Internal.Printing.Configuration.PTFeatureNode MS.Internal.Printing.Configuration.PrintTicketFeature::get_FeatureNode()
0xf6e2  brfalse.s loc_F70E
0xf6e4  ldarg.0
0xf6e5  call     instance class MS.Internal.Printing.Configuration.PTFeatureNode MS.Internal.Printing.Configuration.PrintTicketFeature::get_FeatureNode()
0xf6ea  ldloca.s 2
0xf6ec  callvirt instance string MS.Internal.Printing.Configuration.PTFeatureNode::GetOptionName([out] bool& bInPrivateNamespace)
0xf6f1  dup
0xf6f2  stloc.1
0xf6f3  brfalse.s loc_F70E
0xf6f5  ldloc.1
0xf6f6  ldstr    aCustommediasiz_1// "CustomMediaSize"
0xf6fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf700  brfalse.s loc_F70E
0xf702  ldarg.0
0xf703  ldstr    aCustommediasiz_0// "CustomMediaSizeHeight"
0xf708  call     instance int32 MS.Internal.Printing.Configuration.PrintTicketFeature::get_Item(string propertyName)
0xf70d  stloc.0
0xf70e  ldloc.0
0xf70f  call     float64 MS.Internal.Printing.Configuration.UnitConverter::LengthValueFromMicronToDIP(int32 micronValue)
0xf714  ret
```
