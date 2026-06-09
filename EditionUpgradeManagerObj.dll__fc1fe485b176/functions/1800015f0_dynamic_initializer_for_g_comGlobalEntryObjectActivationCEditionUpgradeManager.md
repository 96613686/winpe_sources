# _dynamic_initializer_for__g_comGlobalEntryObjectActivationCEditionUpgradeManager__

- ea: `0x1800015f0`
- end: `0x18000160d`
- name: `_dynamic_initializer_for__g_comGlobalEntryObjectActivationCEditionUpgradeManager__`
- size: `29`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryObjectActivationCEditionUpgradeManager__()
{
  __int64 *result; // rax

  qword_18002F3F8 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_18002F3F8;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_18002F3F8;
  return result;
}

```

## disassembly

```asm
0x1800015f0  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x1800015f7  mov     cs:qword_18002F3F8, rax
0x1800015fe  lea     rax, qword_18002F3F8
0x180001605  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x18000160c  retn
```
