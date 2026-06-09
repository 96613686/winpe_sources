# System.Xml.Xsl.Qil.QilNode::Add

- ea: `0x377c0`
- end: `0x377ce`
- name: `System.Xml.Xsl.Qil.QilNode::Add`
- size: `14`
- prototype: ``
- caller_count: `37`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x148d0`
- `0x165f0`
- `0x16820`
- `0x16a10`
- `0x16b70`
- `0x17280`
- `0x17580`
- `0x17ae0`
- `0x17b90`
- `0x181b0`
- `0x18600`
- `0x18c10`
- `0x18dd0`
- `0x198c0`
- `0x19b80`
- `0x1a0a0`
- `0x1a290`
- `0x1a360`
- `0x1b580`
- `0x1b630`
- `0x1b6a0`
- `0x1b9e0`
- `0x1bf40`
- `0x1bfc0`
- `0x1cdb0`
- `0x27600`
- `0x37b00`
- `0x37b20`
- `0x37b60`
- `0x37b80`
- `0x37bc0`
- `0x37ed0`
- `0x37ef0`
- `0x37f10`
- `0x3b7d0`
- `0x3bbb0`
- `0x43790`

## callees

- `0x37740`
- `0x37770`

## pseudocode

```c

```

## disassembly

```asm
0x377c0  ldarg.0
0x377c1  ldarg.0
0x377c2  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x377c7  ldarg.1
0x377c8  callvirt instance void System.Xml.Xsl.Qil.QilNode::Insert(int32 index, class System.Xml.Xsl.Qil.QilNode node)
0x377cd  ret
```
