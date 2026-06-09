# _dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCEditionUpgradeManager__

- ea: `0x180001620`
- end: `0x18000163d`
- name: `_dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCEditionUpgradeManager__`
- size: `29`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCEditionUpgradeManager__()
{
  __int64 *result; // rax

  qword_18002F3E0 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_18002F3E0;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_18002F3E0;
  return result;
}

```

## disassembly

```asm
0x180001620  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x180001627  mov     cs:qword_18002F3E0, rax
0x18000162e  lea     rax, qword_18002F3E0
0x180001635  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x18000163c  retn
```
