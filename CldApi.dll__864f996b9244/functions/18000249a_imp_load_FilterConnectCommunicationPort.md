# __imp_load_FilterConnectCommunicationPort

- ea: `0x18000249a`
- end: `0x1800024a6`
- name: `__imp_load_FilterConnectCommunicationPort`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800023f7`

## import_xrefs

- `FLTLIB!FilterConnectCommunicationPort` at `0x18000249a`

## pseudocode

```c
__int64 load_FilterConnectCommunicationPort()
{
  return _tailMerge_fltlib_dll();
}

```

## disassembly

```asm
0x18000249a  lea     rax, __imp_FilterConnectCommunicationPort
0x1800024a1  jmp     __tailMerge_fltlib_dll
```
