# CMultipleValues::DeleteValue(tagPROPVARIANT const &)

- ea: `0x180044c50`
- end: `0x180044cc1`
- name: `?DeleteValue@CMultipleValues@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(CMultipleValues *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180044c50`
- `0x180046910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044c90`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044c90`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x180044c82`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x180044c82`
- `COMCTL32!__imp_DSA_DeleteItem` at `0x180044c9e`
- `COMCTL32!__imp_DSA_DeleteItem` at `0x180044c9e`

## pseudocode

```c
__int64 __fastcall CMultipleValues::DeleteValue(HDSA *this, const struct tagPROPVARIANT *a2)
{
  unsigned int HasValue; // ebx
  PROPVARIANT *ItemPtr; // rax
  __int64 result; // rax
  int i; // [rsp+40h] [rbp+18h] BYREF

  i = 0;
  HasValue = CMultipleValues::HasValue((CMultipleValues *)this, a2, &i);
  if ( !HasValue )
  {
    HasValue = -2147467259;
    ItemPtr = (PROPVARIANT *)DSA_GetItemPtr(this[7], i);
    if ( ItemPtr )
    {
      PropVariantClear(ItemPtr);
      if ( DSA_DeleteItem(this[7], i) )
      {
        *((_BYTE *)this + 64) = 1;
        HasValue = 0;
      }
    }
  }
  result = 0;
  if ( HasValue != 1 )
    return HasValue;
  return result;
}

```

## disassembly

```asm
0x180044c50  mov     [rsp+arg_0], rbx
0x180044c55  push    rdi
0x180044c56  sub     rsp, 20h
0x180044c5a  lea     r8, [rsp+28h+i]; int *
0x180044c5f  mov     [rsp+28h+i], 0
0x180044c67  mov     rdi, rcx
0x180044c6a  call    ?HasValue@CMultipleValues@@UEAAJAEBUtagPROPVARIANT@@PEAH@Z; CMultipleValues::HasValue(tagPROPVARIANT const &,int *)
0x180044c6f  mov     ebx, eax
0x180044c71  test    eax, eax
0x180044c73  jnz     short loc_180044CAE
0x180044c75  mov     edx, [rsp+28h+i]; i
0x180044c79  mov     ebx, 80004005h
0x180044c7e  mov     rcx, [rdi+38h]; hdsa
0x180044c82  call    cs:__imp_DSA_GetItemPtr
0x180044c88  test    rax, rax
0x180044c8b  jz      short loc_180044CAE
0x180044c8d  mov     rcx, rax; pvar
0x180044c90  call    cs:__imp_PropVariantClear
0x180044c96  mov     edx, [rsp+28h+i]; i
0x180044c9a  mov     rcx, [rdi+38h]; hdsa
0x180044c9e  call    cs:__imp_DSA_DeleteItem
0x180044ca4  test    eax, eax
0x180044ca6  jz      short loc_180044CAE
0x180044ca8  mov     byte ptr [rdi+40h], 1
0x180044cac  xor     ebx, ebx
0x180044cae  xor     eax, eax
0x180044cb0  cmp     ebx, 1
0x180044cb3  cmovnz  eax, ebx
0x180044cb6  mov     rbx, [rsp+28h+arg_0]
0x180044cbb  add     rsp, 20h
0x180044cbf  pop     rdi
0x180044cc0  retn
```
