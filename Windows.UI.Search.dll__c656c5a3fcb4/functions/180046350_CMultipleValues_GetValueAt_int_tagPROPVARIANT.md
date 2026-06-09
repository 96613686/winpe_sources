# CMultipleValues::GetValueAt(int,tagPROPVARIANT *)

- ea: `0x180046350`
- end: `0x18004639b`
- name: `?GetValueAt@CMultipleValues@@UEAAJHPEAUtagPROPVARIANT@@@Z`
- size: `75`
- prototype: `int(CMultipleValues *__hidden this, int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180046350`
- `0x180049184`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180046388`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180046388`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x180046377`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x180046377`

## pseudocode

```c
__int64 __fastcall CMultipleValues::GetValueAt(HDSA *this, int a2, PROPVARIANT *a3)
{
  int v6; // ebx
  const PROPVARIANT *ItemPtr; // rax

  v6 = CMultipleValues::_EnsureIndividualValuesArray((CMultipleValues *)this);
  if ( v6 >= 0 )
  {
    v6 = -2147467259;
    ItemPtr = (const PROPVARIANT *)DSA_GetItemPtr(this[7], a2);
    if ( ItemPtr )
      return (unsigned int)PropVariantCopy(a3, ItemPtr);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180046350  push    rbx
0x180046352  push    rbp
0x180046353  push    rsi
0x180046354  push    rdi
0x180046355  sub     rsp, 28h
0x180046359  mov     rsi, r8
0x18004635c  mov     ebp, edx
0x18004635e  mov     rdi, rcx
0x180046361  call    ?_EnsureIndividualValuesArray@CMultipleValues@@AEAAJXZ; CMultipleValues::_EnsureIndividualValuesArray(void)
0x180046366  mov     ebx, eax
0x180046368  test    eax, eax
0x18004636a  js      short loc_180046390
0x18004636c  mov     rcx, [rdi+38h]; hdsa
0x180046370  mov     edx, ebp; i
0x180046372  mov     ebx, 80004005h
0x180046377  call    cs:__imp_DSA_GetItemPtr
0x18004637d  test    rax, rax
0x180046380  jz      short loc_180046390
0x180046382  mov     rdx, rax; pvarSrc
0x180046385  mov     rcx, rsi; pvarDest
0x180046388  call    cs:__imp_PropVariantCopy
0x18004638e  mov     ebx, eax
0x180046390  mov     eax, ebx
0x180046392  add     rsp, 28h
0x180046396  pop     rdi
0x180046397  pop     rsi
0x180046398  pop     rbp
0x180046399  pop     rbx
0x18004639a  retn
```
