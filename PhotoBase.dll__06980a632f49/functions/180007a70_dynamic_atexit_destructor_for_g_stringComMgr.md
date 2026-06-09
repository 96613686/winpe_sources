# _dynamic_atexit_destructor_for__g_stringComMgr__

- ea: `0x180007a70`
- end: `0x180007a7f`
- name: `_dynamic_atexit_destructor_for__g_stringComMgr__`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void **dynamic_atexit_destructor_for__g_stringComMgr__()
{
  void **result; // rax

  result = &ATL::CAtlStringMgr::`vftable';
  g_stringComMgr = &ATL::CAtlStringMgr::`vftable';
  return result;
}

```

## disassembly

```asm
0x180007a70  lea     rax, ??_7CAtlStringMgr@ATL@@6B@; const ATL::CAtlStringMgr::`vftable'
0x180007a77  mov     cs:?g_stringComMgr@@3VCAtlStringMgr@ATL@@A, rax; ATL::CAtlStringMgr g_stringComMgr
0x180007a7e  retn
```
