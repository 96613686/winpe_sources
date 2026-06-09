# ShieldProvider::_dynamic_atexit_destructor_for__g_aszNormalizedSystemPath__

- ea: `0x140012640`
- end: `0x14001265a`
- name: `ShieldProvider::_dynamic_atexit_destructor_for__g_aszNormalizedSystemPath__`
- size: `26`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x1400015f4`
- `0x140012640`

## pseudocode

```c
void ShieldProvider::_dynamic_atexit_destructor_for__g_aszNormalizedSystemPath__()
{
  if ( String1 )
    operator delete(String1);
}

```

## disassembly

```asm
0x140012640  sub     rsp, 28h
0x140012644  mov     rcx, cs:String1; void *
0x14001264b  test    rcx, rcx
0x14001264e  jz      short loc_140012655
0x140012650  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012655  add     rsp, 28h
0x140012659  retn
```
