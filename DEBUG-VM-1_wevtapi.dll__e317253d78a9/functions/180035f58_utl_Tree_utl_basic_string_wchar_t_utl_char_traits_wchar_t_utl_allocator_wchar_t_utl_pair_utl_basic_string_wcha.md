# utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_FindImpl<wchar_t const *>(wchar_t const * const &)

- ea: `0x180035f58`
- end: `0x180035ff4`
- name: `??$_FindImpl@PEB_W@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@1@AEBQEB_W@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180037a14`

## callees

- `0x180035f58`
- `0x180035ffc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035fd4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035fd4`

## pseudocode

```c
__int64 __fastcall utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_FindImpl<wchar_t const *>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 v6; // r10
  __int64 v7; // rdx
  __int64 v8; // r11
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r8

  if ( *(_QWORD *)(a1 + 16) == a1 )
    return a1;
  v5 = utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_LowerBoundNonEmpty<wchar_t const *>();
  v4 = v5;
  if ( v5 != a1 )
  {
    v6 = *a2;
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(v6 + 2 * v7) );
    v8 = *(_QWORD *)(v5 + 24);
    v9 = (*(_QWORD *)(v5 + 32) - v8) >> 1;
    if ( (v7 | (unsigned __int64)v9) > 0x7FFFFFFF )
      __int2c();
    v10 = 2;
    v11 = 2;
    if ( v8 )
      v11 = *(_QWORD *)(v5 + 24);
    if ( v6 )
      v10 = *a2;
    if ( CompareStringOrdinal((LPCWCH)v10, v7, (LPCWCH)v11, v9, 1) == 1 )
      return a1;
  }
  return v4;
}

```

## disassembly

```asm
0x180035f58  mov     [rsp+arg_0], rbx
0x180035f5d  mov     [rsp+arg_8], rsi
0x180035f62  push    rdi
0x180035f63  sub     rsp, 30h
0x180035f67  mov     rsi, rdx
0x180035f6a  mov     rbx, rcx
0x180035f6d  cmp     [rcx+10h], rcx
0x180035f71  jnz     short loc_180035F78
0x180035f73  mov     rdi, rcx
0x180035f76  jmp     short loc_180035FE1
0x180035f78  call    ??$_LowerBoundNonEmpty@PEB_W@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@1@AEBQEB_W@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_LowerBoundNonEmpty<wchar_t const *>(wchar_t const * const &)
0x180035f7d  mov     rdi, rax
0x180035f80  cmp     rax, rbx
0x180035f83  jz      short loc_180035FE1
0x180035f85  mov     r10, [rsi]
0x180035f88  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180035f8c  xor     esi, esi
0x180035f8e  inc     rdx; cchCount1
0x180035f91  cmp     [r10+rdx*2], si
0x180035f96  jnz     short loc_180035F8E
0x180035f98  mov     r11, [rax+18h]
0x180035f9c  mov     r9, [rax+20h]
0x180035fa0  sub     r9, r11
0x180035fa3  sar     r9, 1; cchCount2
0x180035fa6  mov     rax, r9
0x180035fa9  or      rax, rdx
0x180035fac  cmp     rax, 7FFFFFFFh
0x180035fb2  jbe     short loc_180035FB6
0x180035fb4  int     2Ch; Windows NT - assertion failure
0x180035fb6  test    r11, r11
0x180035fb9  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180035fc1  mov     ecx, 2
0x180035fc6  mov     r8d, ecx
0x180035fc9  cmovnz  r8, r11; lpString2
0x180035fcd  test    r10, r10
0x180035fd0  cmovnz  rcx, r10; lpString1
0x180035fd4  call    cs:__imp_CompareStringOrdinal
0x180035fda  cmp     eax, 1
0x180035fdd  cmovz   rdi, rbx
0x180035fe1  mov     rbx, [rsp+38h+arg_0]
0x180035fe6  mov     rax, rdi
0x180035fe9  mov     rsi, [rsp+38h+arg_8]
0x180035fee  add     rsp, 30h
0x180035ff2  pop     rdi
0x180035ff3  retn
```
