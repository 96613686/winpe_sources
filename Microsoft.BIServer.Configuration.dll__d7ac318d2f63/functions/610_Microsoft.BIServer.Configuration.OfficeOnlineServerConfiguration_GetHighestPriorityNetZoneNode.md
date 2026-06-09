# Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetHighestPriorityNetZoneNode

- ea: `0x610`
- end: `0x64a`
- name: `Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetHighestPriorityNetZoneNode`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6b50`

## callees

- `0x610`

## pseudocode

```c

```

## disassembly

```asm
0x610  ldarg.0
0x611  ldstr    aNetZone// "//net-zone"
0x616  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x61b  call     T0x2B000004
0x620  ldsfld   class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, int32> <>c::<>9__6_0
0x625  dup
0x626  brtrue.s loc_63F
0x628  pop
0x629  ldsfld   class <>c <>c::<>9
0x62e  ldftn    instance int32 <>c::<GetHighestPriorityNetZoneNode>b__6_0(class [System.Xml]System.Xml.XmlNode node)
0x634  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, int32>::.ctor(object, native int)
0x639  dup
0x63a  stsfld   class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, int32> <>c::<>9__6_0
0x63f  call     T0x2B000005
0x644  call     T0x2B000006
0x649  ret
```
