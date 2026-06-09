# Microsoft.VisualStudio.Setup.Cache.LayoutChannelReader::GetReaderForChannel

- ea: `0x56660`
- end: `0x5669c`
- name: `Microsoft.VisualStudio.Setup.Cache.LayoutChannelReader::GetReaderForChannel`
- size: `60`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x565f0`
- `0x56610`
- `0x56630`
- `0x56640`

## callees

- `0xee70`
- `0xeee0`
- `0x56660`

## string_xrefs

- `0x56663`: `channelUri`
- `0x56691`: `channelUri`
- `0x5668c`: `Invalid channel uri`

## pseudocode

```c

```

## disassembly

```asm
0x56660  ldarg.1
0x56661  brtrue.s loc_5666E
0x56663  ldstr    aChanneluri// "channelUri"
0x56668  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5666d  throw
0x5666e  ldarg.1
0x5666f  call     bool Microsoft.VisualStudio.Setup.Extensions::IsLayoutPath(class [System]System.Uri uri)
0x56674  brfalse.s loc_5667D
0x56676  ldarg.0
0x56677  ldfld    class Microsoft.VisualStudio.Setup.Cache.ILayoutChannelReader Microsoft.VisualStudio.Setup.Cache.LayoutChannelReader::layoutReader
0x5667c  ret
0x5667d  ldarg.1
0x5667e  call     bool Microsoft.VisualStudio.Setup.Extensions::IsWebHostedLayout(class [System]System.Uri uri)
0x56683  brfalse.s loc_5668C
0x56685  ldarg.0
0x56686  ldfld    class Microsoft.VisualStudio.Setup.Cache.ILayoutChannelReader Microsoft.VisualStudio.Setup.Cache.LayoutChannelReader::webLayoutReader
0x5668b  ret
0x5668c  ldstr    aInvalidChannel_1// "Invalid channel uri"
0x56691  ldstr    aChanneluri// "channelUri"
0x56696  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x5669b  throw
```
