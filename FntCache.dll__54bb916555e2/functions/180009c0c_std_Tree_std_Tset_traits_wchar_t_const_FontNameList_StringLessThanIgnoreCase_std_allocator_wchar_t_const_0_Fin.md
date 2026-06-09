# std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(wchar_t const * const &)

- ea: `0x180009c0c`
- end: `0x180009cc5`
- name: `??$_Find_lower_bound@PEB_W@?$_Tree@V?$_Tset_traits@PEB_WUStringLessThanIgnoreCase@FontNameList@@V?$allocator@PEB_W@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@PEB_WPEAX@std@@@1@AEBQEB_W@Z`
- size: `185`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, const WCHAR **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a0a8`

## callees

- `0x180009c0c`
- `0x18009e420`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009c84`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009c84`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(
        __int64 a1,
        _QWORD *a2,
        const WCHAR **a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  unsigned __int64 v7; // r9
  const WCHAR *v8; // r8
  const WCHAR *v9; // rcx
  unsigned __int64 v10; // rdx
  int v11; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = -1;
    v8 = *a3;
    v9 = (const WCHAR *)v6[4];
    do
      ++v7;
    while ( v8[v7] );
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    if ( v9 )
    {
      if ( !v8 )
        goto LABEL_14;
      if ( v7 > 0x7FFFFFFF || v10 > 0x7FFFFFFF )
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow();
      if ( CompareStringOrdinal(v9, v10, v8, v7, 1) - 2 >= 0 )
      {
LABEL_14:
        a2[2] = v6;
        v11 = 1;
        goto LABEL_12;
      }
    }
    else if ( !v8 )
    {
      goto LABEL_14;
    }
    v6 += 2;
    v11 = 0;
LABEL_12:
    *((_DWORD *)a2 + 2) = v11;
  }
  return a2;
}

```

## disassembly

```asm
0x180009c0c  push    rbx
0x180009c0e  push    rbp
0x180009c0f  push    rsi
0x180009c10  push    rdi
0x180009c11  sub     rsp, 38h
0x180009c15  mov     rax, [rcx]
0x180009c18  xor     ebp, ebp
0x180009c1a  mov     rsi, r8
0x180009c1d  mov     rdi, rdx
0x180009c20  mov     r9, [rax+8]
0x180009c24  mov     [rdx], r9
0x180009c27  mov     rbx, r9
0x180009c2a  mov     [rdx+8], rbp
0x180009c2e  mov     rax, [rcx]
0x180009c31  mov     [rdx+10h], rax
0x180009c35  cmp     [r9+19h], bpl
0x180009c39  jnz     short loc_180009CA1
0x180009c3b  mov     [rdi], rbx
0x180009c3e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180009c42  mov     r8, [rsi]; lpString2
0x180009c45  mov     rcx, [rbx+20h]; lpString1
0x180009c49  inc     r9; cchCount2
0x180009c4c  cmp     [r8+r9*2], bp
0x180009c51  jnz     short loc_180009C49
0x180009c53  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009c57  inc     rdx; cchCount1
0x180009c5a  cmp     [rcx+rdx*2], bp
0x180009c5e  jnz     short loc_180009C57
0x180009c60  test    rcx, rcx
0x180009c63  jz      short loc_180009CB8
0x180009c65  test    r8, r8
0x180009c68  jz      short loc_180009CAD
0x180009c6a  cmp     r9, 7FFFFFFFh
0x180009c71  ja      short loc_180009CBF
0x180009c73  cmp     rdx, 7FFFFFFFh
0x180009c7a  ja      short loc_180009CBF
0x180009c7c  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180009c84  call    cs:__imp_CompareStringOrdinal
0x180009c8a  add     eax, 0FFFFFFFEh
0x180009c8d  jns     short loc_180009CAD
0x180009c8f  add     rbx, 10h
0x180009c93  mov     eax, ebp
0x180009c95  mov     [rdi+8], eax
0x180009c98  mov     rbx, [rbx]
0x180009c9b  cmp     [rbx+19h], bpl
0x180009c9f  jz      short loc_180009C3B
0x180009ca1  mov     rax, rdi
0x180009ca4  add     rsp, 38h
0x180009ca8  pop     rdi
0x180009ca9  pop     rsi
0x180009caa  pop     rbp
0x180009cab  pop     rbx
0x180009cac  retn
0x180009cad  mov     [rdi+10h], rbx
0x180009cb1  mov     eax, 1
0x180009cb6  jmp     short loc_180009C95
0x180009cb8  test    r8, r8
0x180009cbb  jnz     short loc_180009C8F
0x180009cbd  jmp     short loc_180009CAD
0x180009cbf  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
