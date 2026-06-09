# System.Xml.Xsl.Qil.QilBinary::.ctor

- ea: `0x358b0`
- end: `0x358c6`
- name: `System.Xml.Xsl.Qil.QilBinary::.ctor`
- size: `22`
- prototype: ``
- caller_count: `37`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x35970`
- `0x35b10`
- `0x363f0`
- `0x36410`
- `0x364d0`
- `0x364f0`
- `0x36510`
- `0x365d0`
- `0x365f0`
- `0x36610`
- `0x36630`
- `0x36650`
- `0x366b0`
- `0x366d0`
- `0x366f0`
- `0x36710`
- `0x36730`
- `0x36750`
- `0x36770`
- `0x36790`
- `0x367b0`
- `0x367d0`
- `0x36900`
- `0x36a60`
- `0x36a80`
- `0x36aa0`
- `0x36ac0`
- `0x36b00`
- `0x36b80`
- `0x36ba0`
- `0x36d90`
- `0x36f40`
- `0x37050`
- `0x37420`
- `0x39060`
- `0x390c0`
- `0x39120`

## callees

- `0x37670`

## pseudocode

```c

```

## disassembly

```asm
0x358b0  ldarg.0
0x358b1  ldarg.1
0x358b2  call     instance void System.Xml.Xsl.Qil.QilNode::.ctor(valuetype System.Xml.Xsl.Qil.QilNodeType nodeType)
0x358b7  ldarg.0
0x358b8  ldarg.2
0x358b9  stfld    class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::left
0x358be  ldarg.0
0x358bf  ldarg.3
0x358c0  stfld    class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::right
0x358c5  ret
```
