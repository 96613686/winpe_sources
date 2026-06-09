# DownloadQueueItem::ToString

- ea: `0x28f00`
- end: `0x28f47`
- name: `DownloadQueueItem::ToString`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x28f00`

## string_xrefs

- `0x28f07`: ` _sourceUri = `
- `0x28f2a`: `,  _targetPath = `

## pseudocode

```c

```

## disassembly

```asm
0x28f00  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x28f05  stloc.0
0x28f06  ldloc.0
0x28f07  ldstr    aSourceuri_1// " _sourceUri = "
0x28f0c  ldarg.0
0x28f0d  ldfld    class [System]System.Uri DownloadQueueItem::_sourceUri
0x28f12  dup
0x28f13  brtrue.s loc_28F19
0x28f15  pop
0x28f16  ldnull
0x28f17  br.s     loc_28F1E
0x28f19  callvirt instance string [mscorlib]System.Object::ToString()
0x28f1e  call     string [mscorlib]System.String::Concat(string, string)
0x28f23  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x28f28  pop
0x28f29  ldloc.0
0x28f2a  ldstr    aTargetpath// ",  _targetPath = "
0x28f2f  ldarg.0
0x28f30  ldfld    string DownloadQueueItem::_targetPath
0x28f35  call     string [mscorlib]System.String::Concat(string, string)
0x28f3a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x28f3f  pop
0x28f40  ldloc.0
0x28f41  callvirt instance string [mscorlib]System.Object::ToString()
0x28f46  ret
```
