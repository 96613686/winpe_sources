# CSearchDelegateFolder::_CompareSecondary(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x1800422b8`
- end: `0x1800423c5`
- name: `?_CompareSecondary@CSearchDelegateFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@0@Z`
- size: `269`
- prototype: `__int64 __fastcall(CSearchDelegateFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180042090`

## callees

- `0x1800422b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004234e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180042359`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004234e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180042359`
- `PROPSYS!PSGetNamedPropertyFromPropertyStorage` at `0x180042390`
- `PROPSYS!PSGetNamedPropertyFromPropertyStorage` at `0x1800423ba`
- `PROPSYS!PSGetNamedPropertyFromPropertyStorage` at `0x180042390`
- `PROPSYS!PSGetNamedPropertyFromPropertyStorage` at `0x1800423ba`
- `PROPSYS!PropVariantCompareEx` at `0x180042341`
- `PROPSYS!PropVariantCompareEx` at `0x180042341`

## string_xrefs

- `0x180042389`: `SecondaryCompare`
- `0x1800423b3`: `SecondaryCompare`

## pseudocode

```c
__int64 __fastcall CSearchDelegateFolder::_CompareSecondary(
        CSearchDelegateFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _ITEMIDLIST_RELATIVE *a3)
{
  unsigned int v4; // ebx
  PROPVARIANT propvar1[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h]
  PROPVARIANT propvar2[2]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v9; // [rsp+48h] [rbp-10h]

  v7 = 0;
  *(_OWORD *)propvar1 = 0;
  if ( a2
    && *(_WORD *)a2 >= 0x12u
    && *(_DWORD *)((char *)a2 + 6) == 597942229
    && *(unsigned __int16 *)a2 >= (unsigned __int64)*((unsigned __int16 *)a2 + 5) + 18
    && *((_WORD *)a2 + 5)
    && a2 != (const struct _ITEMIDLIST_RELATIVE *)-18LL )
  {
    PSGetNamedPropertyFromPropertyStorage(
      (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + 18),
      *((unsigned __int16 *)a2 + 5),
      L"SecondaryCompare",
      propvar1);
  }
  v9 = 0;
  *(_OWORD *)propvar2 = 0;
  if ( a3
    && *(_WORD *)a3 >= 0x12u
    && *(_DWORD *)((char *)a3 + 6) == 597942229
    && *(unsigned __int16 *)a3 >= (unsigned __int64)*((unsigned __int16 *)a3 + 5) + 18
    && *((_WORD *)a3 + 5)
    && a3 != (const struct _ITEMIDLIST_RELATIVE *)-18LL )
  {
    PSGetNamedPropertyFromPropertyStorage(
      (const struct _ITEMIDLIST_RELATIVE *)((char *)a3 + 18),
      *((unsigned __int16 *)a3 + 5),
      L"SecondaryCompare",
      propvar2);
  }
  v4 = PropVariantCompareEx(propvar1, propvar2, PVCU_DEFAULT, 0);
  PropVariantClear(propvar1);
  PropVariantClear(propvar2);
  return v4;
}

```

## disassembly

```asm
0x1800422b8  mov     [rsp+arg_0], rbx
0x1800422bd  mov     [rsp+arg_8], rsi
0x1800422c2  push    rdi
0x1800422c3  sub     rsp, 50h
0x1800422c7  xor     eax, eax
0x1800422c9  xor     edi, edi
0x1800422cb  mov     [rsp+58h+var_28], rax
0x1800422d0  xorps   xmm0, xmm0
0x1800422d3  mov     rbx, r8
0x1800422d6  movups  xmmword ptr [rsp+58h+propvar1], xmm0
0x1800422db  lea     esi, [rax+12h]
0x1800422de  test    rdx, rdx
0x1800422e1  jz      short loc_180042300
0x1800422e3  cmp     [rdx], si
0x1800422e6  jb      short loc_180042300
0x1800422e8  cmp     dword ptr [rdx+6], 23A3DFD5h
0x1800422ef  jnz     short loc_180042300
0x1800422f1  movzx   ecx, word ptr [rdx+0Ah]
0x1800422f5  movzx   eax, word ptr [rdx]
0x1800422f8  add     rcx, rsi
0x1800422fb  cmp     rax, rcx
0x1800422fe  jnb     short loc_180042371
0x180042300  xor     eax, eax
0x180042302  xorps   xmm0, xmm0
0x180042305  mov     [rsp+58h+var_10], rax
0x18004230a  movups  xmmword ptr [rsp+58h+propvar2], xmm0
0x18004230f  test    rbx, rbx
0x180042312  jz      short loc_180042331
0x180042314  cmp     [rbx], si
0x180042317  jb      short loc_180042331
0x180042319  cmp     dword ptr [rbx+6], 23A3DFD5h
0x180042320  jnz     short loc_180042331
0x180042322  movzx   ecx, word ptr [rbx+0Ah]
0x180042326  movzx   eax, word ptr [rbx]
0x180042329  add     rcx, rsi
0x18004232c  cmp     rax, rcx
0x18004232f  jnb     short loc_18004239B
0x180042331  xor     r9d, r9d; flags
0x180042334  lea     rdx, [rsp+58h+propvar2]; propvar2
0x180042339  xor     r8d, r8d; unit
0x18004233c  lea     rcx, [rsp+58h+propvar1]; propvar1
0x180042341  call    cs:__imp_PropVariantCompareEx
0x180042347  lea     rcx, [rsp+58h+propvar1]; pvar
0x18004234c  mov     ebx, eax
0x18004234e  call    cs:__imp_PropVariantClear
0x180042354  lea     rcx, [rsp+58h+propvar2]; pvar
0x180042359  call    cs:__imp_PropVariantClear
0x18004235f  mov     rsi, [rsp+58h+arg_8]
0x180042364  mov     eax, ebx
0x180042366  mov     rbx, [rsp+58h+arg_0]
0x18004236b  add     rsp, 50h
0x18004236f  pop     rdi
0x180042370  retn
0x180042371  cmp     [rdx+0Ah], di
0x180042375  jz      short loc_180042300
0x180042377  lea     rcx, [rdx+12h]; psps
0x18004237b  test    rcx, rcx
0x18004237e  jz      short loc_180042300
0x180042380  movzx   edx, word ptr [rdx+0Ah]; cb
0x180042384  lea     r9, [rsp+58h+propvar1]; ppropvar
0x180042389  lea     r8, aSecondarycompa; "SecondaryCompare"
0x180042390  call    cs:__imp_PSGetNamedPropertyFromPropertyStorage
0x180042396  jmp     loc_180042300
0x18004239b  cmp     [rbx+0Ah], di
0x18004239f  jz      short loc_180042331
0x1800423a1  lea     rcx, [rbx+12h]; psps
0x1800423a5  test    rcx, rcx
0x1800423a8  jz      short loc_180042331
0x1800423aa  movzx   edx, word ptr [rbx+0Ah]; cb
0x1800423ae  lea     r9, [rsp+58h+propvar2]; ppropvar
0x1800423b3  lea     r8, aSecondarycompa; "SecondaryCompare"
0x1800423ba  call    cs:__imp_PSGetNamedPropertyFromPropertyStorage
0x1800423c0  jmp     loc_180042331
```
