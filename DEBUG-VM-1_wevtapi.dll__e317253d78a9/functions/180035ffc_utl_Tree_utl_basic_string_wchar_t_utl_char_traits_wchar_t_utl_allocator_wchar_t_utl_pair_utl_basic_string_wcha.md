# utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_LowerBoundNonEmpty<wchar_t const *>(wchar_t const * const &)

- ea: `0x180035ffc`
- end: `0x180036096`
- name: `??$_LowerBoundNonEmpty@PEB_W@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@1@AEBQEB_W@Z`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180035f58`

## callees

- `0x180035ffc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036060`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036060`

## pseudocode

```c
_QWORD *__fastcall utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_LowerBoundNonEmpty<wchar_t const *>(
        _QWORD *a1,
        __int64 *a2)
{
  _QWORD *v2; // rbx
  _QWORD *v4; // rdi
  __int64 v5; // r10
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rax

  v2 = (_QWORD *)*a1;
  v4 = a1;
  do
  {
    v5 = v2[3];
    v6 = *a2;
    v7 = (v2[4] - v5) >> 1;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v6 + 2 * v8) );
    if ( (v8 | (unsigned __int64)v7) > 0x7FFFFFFF )
      __int2c();
    v9 = 2;
    if ( v6 )
      v9 = *a2;
    v10 = 2;
    if ( v5 )
      v10 = v2[3];
    if ( CompareStringOrdinal((LPCWCH)v10, v7, (LPCWCH)v9, v8, 1) == 1 )
    {
      v11 = 2;
    }
    else
    {
      v4 = v2;
      v11 = 1;
    }
    v2 = (_QWORD *)v2[v11];
  }
  while ( v2 != (_QWORD *)&utl::_TreeSentinel );
  return v4;
}

```

## disassembly

```asm
0x180035ffc  push    rbx
0x180035ffe  push    rbp
0x180035fff  push    rsi
0x180036000  push    rdi
0x180036001  sub     rsp, 38h
0x180036005  mov     rbx, [rcx]
0x180036008  mov     rsi, rdx
0x18003600b  mov     rdi, rcx
0x18003600e  xor     ebp, ebp
0x180036010  mov     r10, [rbx+18h]
0x180036014  mov     rdx, [rbx+20h]
0x180036018  mov     rcx, [rsi]
0x18003601b  sub     rdx, r10
0x18003601e  sar     rdx, 1; cchCount1
0x180036021  or      r9, 0FFFFFFFFFFFFFFFFh
0x180036025  inc     r9; cchCount2
0x180036028  cmp     [rcx+r9*2], bp
0x18003602d  jnz     short loc_180036025
0x18003602f  mov     rax, rdx
0x180036032  or      rax, r9
0x180036035  cmp     rax, 7FFFFFFFh
0x18003603b  jbe     short loc_18003603F
0x18003603d  int     2Ch; Windows NT - assertion failure
0x18003603f  test    rcx, rcx
0x180036042  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18003604a  mov     r8d, 2
0x180036050  cmovnz  r8, rcx; lpString2
0x180036054  test    r10, r10
0x180036057  mov     ecx, 2
0x18003605c  cmovnz  rcx, r10; lpString1
0x180036060  call    cs:__imp_CompareStringOrdinal
0x180036066  cmp     eax, 1
0x180036069  jnz     short loc_180036072
0x18003606b  mov     eax, 10h
0x180036070  jmp     short loc_18003607A
0x180036072  mov     rdi, rbx
0x180036075  mov     eax, 8
0x18003607a  mov     rbx, [rax+rbx]
0x18003607e  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180036085  cmp     rbx, rax
0x180036088  jnz     short loc_180036010
0x18003608a  mov     rax, rdi
0x18003608d  add     rsp, 38h
0x180036091  pop     rdi
0x180036092  pop     rsi
0x180036093  pop     rbp
0x180036094  pop     rbx
0x180036095  retn
```
