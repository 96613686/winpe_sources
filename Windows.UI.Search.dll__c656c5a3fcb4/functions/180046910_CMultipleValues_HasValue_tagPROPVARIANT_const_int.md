# CMultipleValues::HasValue(tagPROPVARIANT const &,int *)

- ea: `0x180046910`
- end: `0x180046989`
- name: `?HasValue@CMultipleValues@@UEAAJAEBUtagPROPVARIANT@@PEAH@Z`
- size: `121`
- prototype: `int(CMultipleValues *__hidden this, const struct tagPROPVARIANT *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180044c50`
- `0x1800474a0`

## callees

- `0x180046910`
- `0x180049184`

## import_xrefs

- `PROPSYS!PropVariantCompareEx` at `0x180046960`
- `PROPSYS!PropVariantCompareEx` at `0x180046960`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x18004694b`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x18004694b`

## pseudocode

```c
__int64 __fastcall CMultipleValues::HasValue(struct _DSA **this, const PROPVARIANT *a2, int *a3)
{
  int v6; // ebx
  int v7; // edi
  struct _DSA *v8; // rcx
  int v9; // eax
  const PROPVARIANT *ItemPtr; // rax

  v6 = CMultipleValues::_EnsureIndividualValuesArray((CMultipleValues *)this);
  if ( v6 >= 0 )
  {
    v6 = 1;
    v7 = 0;
    do
    {
      v8 = this[7];
      v9 = v8 ? *(_DWORD *)v8 : 0;
      if ( v7 >= v9 )
        break;
      ItemPtr = (const PROPVARIANT *)DSA_GetItemPtr(v8, v7);
      if ( !PropVariantCompareEx(a2, ItemPtr, PVCU_DEFAULT, 4) )
      {
        v6 = 0;
        if ( a3 )
        {
          *a3 = v7;
          return (unsigned int)v6;
        }
      }
      ++v7;
    }
    while ( v6 == 1 );
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180046910  push    rbx
0x180046912  push    rbp
0x180046913  push    rsi
0x180046914  push    rdi
0x180046915  push    r14
0x180046917  sub     rsp, 20h
0x18004691b  mov     rsi, r8
0x18004691e  mov     r14, rdx
0x180046921  mov     rbp, rcx
0x180046924  call    ?_EnsureIndividualValuesArray@CMultipleValues@@AEAAJXZ; CMultipleValues::_EnsureIndividualValuesArray(void)
0x180046929  mov     ebx, eax
0x18004692b  test    eax, eax
0x18004692d  js      short loc_18004697C
0x18004692f  mov     ebx, 1
0x180046934  xor     edi, edi
0x180046936  mov     rcx, [rbp+38h]; hdsa
0x18004693a  test    rcx, rcx
0x18004693d  jz      short loc_180046943
0x18004693f  mov     eax, [rcx]
0x180046941  jmp     short loc_180046945
0x180046943  xor     eax, eax
0x180046945  cmp     edi, eax
0x180046947  jge     short loc_18004697C
0x180046949  mov     edx, edi; i
0x18004694b  call    cs:__imp_DSA_GetItemPtr
0x180046951  mov     r9d, 4; flags
0x180046957  xor     r8d, r8d; unit
0x18004695a  mov     rdx, rax; propvar2
0x18004695d  mov     rcx, r14; propvar1
0x180046960  call    cs:__imp_PropVariantCompareEx
0x180046966  test    eax, eax
0x180046968  jnz     short loc_180046971
0x18004696a  xor     ebx, ebx
0x18004696c  test    rsi, rsi
0x18004696f  jnz     short loc_18004697A
0x180046971  inc     edi
0x180046973  cmp     ebx, 1
0x180046976  jz      short loc_180046936
0x180046978  jmp     short loc_18004697C
0x18004697a  mov     [rsi], edi
0x18004697c  mov     eax, ebx
0x18004697e  add     rsp, 20h
0x180046982  pop     r14
0x180046984  pop     rdi
0x180046985  pop     rsi
0x180046986  pop     rbp
0x180046987  pop     rbx
0x180046988  retn
```
