# Microsoft.VisualStudio.Setup.Cache.Instance::set_TemporaryCache

- ea: `0x1a740`
- end: `0x1a754`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_TemporaryCache`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a748`: `TemporaryCache`

## pseudocode

```c

```

## disassembly

```asm
0x1a740  ldarg.0
0x1a741  ldarg.0
0x1a742  ldflda   string Microsoft.VisualStudio.Setup.Cache.Instance::temporaryCache
0x1a747  ldarg.1
0x1a748  ldstr    aTemporarycache// "TemporaryCache"
0x1a74d  ldnull
0x1a74e  call     T0x2B0000C9
0x1a753  ret
```
