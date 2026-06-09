# Base::StringCom::GetBaseStringComManager(void)

- ea: `0x1800028a0`
- end: `0x1800028a8`
- name: `?GetBaseStringComManager@StringCom@Base@@SAAEAVCAtlStringMgr@ATL@@XZ`
- size: `8`
- prototype: `struct ATL::CAtlStringMgr *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void ***Base::StringCom::GetBaseStringComManager(void)
{
  return &g_stringComMgr;
}

```

## disassembly

```asm
0x1800028a0  lea     rax, ?g_stringComMgr@@3VCAtlStringMgr@ATL@@A; ATL::CAtlStringMgr g_stringComMgr
0x1800028a7  retn
```
