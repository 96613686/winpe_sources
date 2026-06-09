# _dynamic_initializer_for__g_comGlobalEntryAppIdRegistration__

- ea: `0x1800015c0`
- end: `0x1800015dd`
- name: `_dynamic_initializer_for__g_comGlobalEntryAppIdRegistration__`
- size: `29`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryAppIdRegistration__()
{
  __int64 *result; // rax

  qword_18002F370 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_18002F370;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_18002F370;
  return result;
}

```

## disassembly

```asm
0x1800015c0  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x1800015c7  mov     cs:qword_18002F370, rax
0x1800015ce  lea     rax, qword_18002F370
0x1800015d5  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x1800015dc  retn
```
