# std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::find(wchar_t const * const &)

- ea: `0x18000a704`
- end: `0x18000a7cd`
- name: `?find@?$_Tree@V?$_Tset_traits@PEB_WUStringLessThanIgnoreCase@FontNameList@@V?$allocator@PEB_W@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEB_W@std@@@std@@@2@AEBQEB_W@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a0a8`

## callees

- `0x18000a704`
- `0x18000a7d4`
- `0x18009e420`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a79a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a79a`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::find(
        const WCHAR *a1,
        _QWORD *a2,
        const WCHAR **a3)
{
  __int64 *v3; // rdi
  const WCHAR *v6; // r14
  __int64 *i; // rbx
  const WCHAR *v9; // r8
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // rdx

  v3 = *(__int64 **)a1;
  v6 = a1;
  for ( i = *(__int64 **)(*(_QWORD *)a1 + 8LL); !*((_BYTE *)i + 25); i = (__int64 *)*i )
  {
    v9 = *a3;
    v10 = -1;
    a1 = (const WCHAR *)i[4];
    do
      ++v10;
    while ( v9[v10] );
    v11 = -1;
    do
      ++v11;
    while ( a1[v11] );
    if ( a1 )
    {
      if ( v9 )
      {
        if ( v10 > 0x7FFFFFFF || v11 > 0x7FFFFFFF )
          SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(a1, v11, v9, v10);
        if ( CompareStringOrdinal(a1, v11, v9, v10, 1) - 2 < 0 )
        {
LABEL_2:
          i += 2;
          continue;
        }
      }
    }
    else if ( v9 )
    {
      goto LABEL_2;
    }
    v3 = i;
  }
  if ( *((_BYTE *)v3 + 25) || (unsigned __int8)FontNameList::StringLessThanIgnoreCase::operator()(a1, *a3, v3[4]) )
    v3 = *(__int64 **)v6;
  *a2 = v3;
  return a2;
}

```

## disassembly

```asm
0x18000a704  push    rbx
0x18000a706  push    rbp
0x18000a707  push    rsi
0x18000a708  push    rdi
0x18000a709  push    r14
0x18000a70b  push    r15
0x18000a70d  sub     rsp, 58h
0x18000a711  mov     rdi, [rcx]
0x18000a714  xor     eax, eax
0x18000a716  mov     r15, r8
0x18000a719  mov     [rsp+88h+var_4C], eax
0x18000a71d  mov     rsi, rdx
0x18000a720  mov     r14, rcx
0x18000a723  xor     ebp, ebp
0x18000a725  mov     rbx, [rdi+8]
0x18000a729  jmp     short loc_18000A732
0x18000a72b  add     rbx, 10h
0x18000a72f  mov     rbx, [rbx]
0x18000a732  cmp     [rbx+19h], bpl
0x18000a736  jz      short loc_18000A754
0x18000a738  cmp     [rdi+19h], bpl
0x18000a73c  jz      short loc_18000A7AA
0x18000a73e  mov     rdi, [r14]
0x18000a741  mov     [rsi], rdi
0x18000a744  mov     rax, rsi
0x18000a747  add     rsp, 58h
0x18000a74b  pop     r15
0x18000a74d  pop     r14
0x18000a74f  pop     rdi
0x18000a750  pop     rsi
0x18000a751  pop     rbp
0x18000a752  pop     rbx
0x18000a753  retn
0x18000a754  mov     r8, [r15]; lpString2
0x18000a757  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000a75b  mov     rcx, [rbx+20h]; lpString1
0x18000a75f  inc     r9; cchCount2
0x18000a762  cmp     [r8+r9*2], bp
0x18000a767  jnz     short loc_18000A75F
0x18000a769  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a76d  inc     rdx; cchCount1
0x18000a770  cmp     [rcx+rdx*2], bp
0x18000a774  jnz     short loc_18000A76D
0x18000a776  test    rcx, rcx
0x18000a779  jz      short loc_18000A7BC
0x18000a77b  test    r8, r8
0x18000a77e  jz      short loc_18000A7A5
0x18000a780  cmp     r9, 7FFFFFFFh
0x18000a787  ja      short loc_18000A7C7
0x18000a789  cmp     rdx, 7FFFFFFFh
0x18000a790  ja      short loc_18000A7C7
0x18000a792  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x18000a79a  call    cs:__imp_CompareStringOrdinal
0x18000a7a0  add     eax, 0FFFFFFFEh
0x18000a7a3  js      short loc_18000A72B
0x18000a7a5  mov     rdi, rbx
0x18000a7a8  jmp     short loc_18000A72F
0x18000a7aa  mov     r8, [rdi+20h]
0x18000a7ae  mov     rdx, [r15]
0x18000a7b1  call    ??RStringLessThanIgnoreCase@FontNameList@@QEBA_NPEB_W0@Z; FontNameList::StringLessThanIgnoreCase::operator()(wchar_t const *,wchar_t const *)
0x18000a7b6  test    al, al
0x18000a7b8  jnz     short loc_18000A73E
0x18000a7ba  jmp     short loc_18000A741
0x18000a7bc  test    r8, r8
0x18000a7bf  jnz     loc_18000A72B
0x18000a7c5  jmp     short loc_18000A7A5
0x18000a7c7  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
