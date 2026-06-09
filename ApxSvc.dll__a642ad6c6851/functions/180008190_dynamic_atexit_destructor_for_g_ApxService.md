# _dynamic_atexit_destructor_for__g_ApxService__

- ea: `0x180008190`
- end: `0x1800081af`
- name: `_dynamic_atexit_destructor_for__g_ApxService__`
- size: `31`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001930`
- `0x180008190`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_ApxService__()
{
  if ( g_ApxService )
    operator delete(g_ApxService);
}

```

## disassembly

```asm
0x180008190  sub     rsp, 28h
0x180008194  mov     rcx, cs:?g_ApxService@@3V?$unique_ptr@VCApxSvc@@U?$default_delete@VCApxSvc@@@std@@@std@@A; Block
0x18000819b  test    rcx, rcx
0x18000819e  jz      short loc_1800081AA
0x1800081a0  mov     edx, 0Ch
0x1800081a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800081aa  add     rsp, 28h
0x1800081ae  retn
```
