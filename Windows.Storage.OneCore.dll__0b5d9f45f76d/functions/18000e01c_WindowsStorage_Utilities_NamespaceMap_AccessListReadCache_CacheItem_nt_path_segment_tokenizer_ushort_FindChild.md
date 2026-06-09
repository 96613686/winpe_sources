# WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>::FindChildNode(std::basic_string_view<ushort,std::char_traits<ushort>>,bool)

- ea: `0x18000e01c`
- end: `0x18000e203`
- name: `?FindChildNode@?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@AEBA?AV?$tuple@_NV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@5@_N@Z`
- size: `487`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000de20`
- `0x1800102cc`

## callees

- `0x18000ba78`
- `0x18000c4a8`
- `0x18000c980`
- `0x18000d1c8`
- `0x18000d2f4`
- `0x18000d974`
- `0x18000e01c`
- `0x1800105b0`
- `0x180010cb8`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e0f6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e0f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e0d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e0d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>::FindChildNode(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        char a4)
{
  __int64 v5; // r15
  __int64 v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // r12
  __int128 *v10; // rax
  __int128 v11; // xmm6
  const WCHAR *StringRawBuffer; // rax
  __int64 v13; // rbx
  HSTRING *Hstring; // rax
  bool v15; // al
  __int64 v17; // [rsp+38h] [rbp-49h] BYREF
  HSTRING string; // [rsp+40h] [rbp-41h] BYREF
  int cchCount1[4]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v20; // [rsp+58h] [rbp-29h] BYREF
  __int128 v21; // [rsp+68h] [rbp-19h] BYREF
  __int128 v22; // [rsp+78h] [rbp-9h] BYREF
  __int64 v23; // [rsp+88h] [rbp+7h]
  UINT32 length; // [rsp+E8h] [rbp+67h] BYREF
  __int64 v25; // [rsp+F8h] [rbp+77h] BYREF
  char v26; // [rsp+100h] [rbp+7Fh]

  v26 = a4;
  v5 = a1;
  v6 = *(_QWORD *)(a1 + 16);
  v7 = v6;
  *(_OWORD *)cchCount1 = *a3;
  split_string<unsigned short,std::basic_string_view<unsigned short> (*)(std::basic_string_view<unsigned short>)>(
    &v25,
    cchCount1);
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))v25)(v25);
    v8 = v25;
    if ( *(_WORD *)(v25 + 8) )
      goto LABEL_5;
    std::experimental::generator<std::basic_string_view<unsigned short>,std::allocator<char>>::promise_type::_Rethrow_if_exception(v25 - 32);
  }
  v8 = 0;
LABEL_5:
  while ( v8 )
  {
    v9 = v8 - 32;
    v10 = *(__int128 **)(v8 - 32);
    v11 = *v10;
    if ( *(_BYTE *)(v7 + 48) )
      v6 = v7;
    *(_QWORD *)cchCount1 = *((_QWORD *)v10 + 1);
    v7 = **(_QWORD **)(v5 + 16);
    v17 = v7;
    while ( v7 != *(_QWORD *)(v5 + 16) )
    {
      length = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v7 + 32), &length);
      if ( CompareStringOrdinal((LPCWCH)v11, cchCount1[0], StringRawBuffer, length, 1) == 2 )
        goto LABEL_13;
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>>>,std::_Iterator_base0>::operator++(&v17);
      v7 = v17;
    }
    v7 = *(_QWORD *)(v5 + 16);
LABEL_13:
    if ( v7 == *(_QWORD *)(v5 + 16) )
    {
      if ( !v26 )
      {
        *(_QWORD *)a2 = v6;
        *(_QWORD *)(a2 + 8) = v7;
        *(_BYTE *)(a2 + 16) = 0;
        std::experimental::generator<std::basic_string_view<unsigned short>,std::allocator<char>>::~generator<std::basic_string_view<unsigned short>,std::allocator<char>>(&v25);
        return a2;
      }
      v21 = 0;
      v22 = 0;
      v23 = 0;
      v13 = WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>((__int64)&v21);
      *(_OWORD *)cchCount1 = v11;
      Hstring = (HSTRING *)WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>::make_Hstring((Microsoft::WRL::Wrappers::HString *)&string);
      std::map<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>>>::_Try_emplace<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>(
        (_QWORD *)(v5 + 16),
        (__int64)&v20,
        Hstring,
        v13);
      v7 = v20;
      WindowsDeleteString(string);
      string = 0;
      std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>>,0>>((_QWORD **)&v22);
    }
    v5 = v7 + 40;
    (*(void (__fastcall **)(__int64))v8)(v8);
    if ( !*(_WORD *)(v8 + 8) )
    {
      v8 = 0;
      std::experimental::generator<std::basic_string_view<unsigned short>,std::allocator<char>>::promise_type::_Rethrow_if_exception(v9);
    }
  }
  std::experimental::generator<std::basic_string_view<unsigned short>,std::allocator<char>>::~generator<std::basic_string_view<unsigned short>,std::allocator<char>>(&v25);
  v15 = *(_QWORD *)(v5 + 16) != v7;
  *(_QWORD *)a2 = v6;
  *(_QWORD *)(a2 + 8) = v7;
  *(_BYTE *)(a2 + 16) = v15;
  return a2;
}

```

## disassembly

```asm
0x18000e01c  mov     rax, rsp
0x18000e01f  mov     [rax+10h], rbx
0x18000e023  mov     [rax+20h], r9b
0x18000e027  push    rbp
0x18000e028  push    rsi
0x18000e029  push    rdi
0x18000e02a  push    r12
0x18000e02c  push    r13
0x18000e02e  push    r14
0x18000e030  push    r15
0x18000e032  lea     rbp, [rax-5Fh]
0x18000e036  sub     rsp, 0A0h
0x18000e03d  movaps  xmmword ptr [rax-48h], xmm6
0x18000e041  mov     r14, rdx
0x18000e044  mov     r15, rcx
0x18000e047  xor     r13d, r13d
0x18000e04a  mov     rsi, [rcx+10h]
0x18000e04e  mov     rbx, rsi
0x18000e051  movaps  xmm0, xmmword ptr [r8]
0x18000e055  movdqa  xmmword ptr [rbp+57h+cchCount1], xmm0
0x18000e05a  lea     rdx, [rbp+57h+cchCount1]
0x18000e05e  lea     rcx, [rbp+57h+arg_10]
0x18000e062  call    ??$split_string@GP6A?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@Z@@YA?AU?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@P6A?AV32@0@Z_N@Z; split_string<ushort,std::basic_string_view<ushort> (*)(std::basic_string_view<ushort>)>(std::basic_string_view<ushort>,std::basic_string_view<ushort> (*)(std::basic_string_view<ushort>),bool)
0x18000e067  nop
0x18000e068  mov     rax, [rbp+57h+arg_10]
0x18000e06c  test    rax, rax
0x18000e06f  jz      short loc_18000E090
0x18000e071  mov     rcx, rax
0x18000e074  mov     rax, [rax]
0x18000e077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e07c  mov     rdi, [rbp+57h+arg_10]
0x18000e080  cmp     [rdi+8], r13w
0x18000e085  jnz     short loc_18000E093
0x18000e087  lea     rcx, [rdi-20h]
0x18000e08b  call    ?_Rethrow_if_exception@promise_type@?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@QEAAXXZ; std::experimental::generator<std::basic_string_view<ushort>,std::allocator<char>>::promise_type::_Rethrow_if_exception(void)
0x18000e090  mov     rdi, r13
0x18000e093  test    rdi, rdi
0x18000e096  jz      loc_18000E1C5
0x18000e09c  lea     r12, [rdi-20h]
0x18000e0a0  mov     rax, [r12]
0x18000e0a4  movups  xmm6, xmmword ptr [rax]
0x18000e0a7  cmp     [rbx+30h], r13b
0x18000e0ab  cmovnz  rsi, rbx
0x18000e0af  movq    xmm0, qword ptr [rax+8]
0x18000e0b4  movq    qword ptr [rbp+57h+cchCount1], xmm0
0x18000e0b9  mov     rbx, [r15+10h]
0x18000e0bd  mov     rbx, [rbx]
0x18000e0c0  mov     [rbp+57h+var_A0], rbx
0x18000e0c4  cmp     rbx, [r15+10h]
0x18000e0c8  jz      short loc_18000E110
0x18000e0ca  mov     [rbp+57h+length], 0
0x18000e0d1  lea     rdx, [rbp+57h+length]; length
0x18000e0d5  mov     rcx, [rbx+20h]; string
0x18000e0d9  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e0df  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18000e0e7  mov     r9d, [rbp+57h+length]; cchCount2
0x18000e0eb  mov     r8, rax; lpString2
0x18000e0ee  mov     edx, [rbp+57h+cchCount1]; cchCount1
0x18000e0f1  movq    rcx, xmm6; lpString1
0x18000e0f6  call    cs:__imp_CompareStringOrdinal
0x18000e0fc  cmp     eax, 2
0x18000e0ff  jz      short loc_18000E114
0x18000e101  lea     rcx, [rbp+57h+var_A0]
0x18000e105  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>>>,std::_Iterator_base0>::operator++(void)
0x18000e10a  mov     rbx, [rbp+57h+var_A0]
0x18000e10e  jmp     short loc_18000E0C4
0x18000e110  mov     rbx, [r15+10h]
0x18000e114  xor     r13d, r13d
0x18000e117  cmp     rbx, [r15+10h]
0x18000e11b  jnz     short loc_18000E185
0x18000e11d  cmp     [rbp+57h+arg_18], r13b
0x18000e121  jz      loc_18000E1AF
0x18000e127  xorps   xmm0, xmm0
0x18000e12a  xor     eax, eax
0x18000e12c  movups  [rbp+57h+var_70], xmm0
0x18000e130  movups  [rbp+57h+var_60], xmm0
0x18000e134  mov     [rbp+57h+var_50], rax
0x18000e138  lea     rcx, [rbp+57h+var_70]
0x18000e13c  call    ??0?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>(void)
0x18000e141  mov     rbx, rax
0x18000e144  movdqa  xmmword ptr [rbp+57h+cchCount1], xmm6
0x18000e149  lea     rdx, [rbp+57h+cchCount1]
0x18000e14d  lea     rcx, [rbp+57h+string]; this
0x18000e151  call    ?make_Hstring@?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@CA?AVHString@Wrappers@WRL@Microsoft@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>::make_Hstring(std::basic_string_view<ushort>)
0x18000e156  nop
0x18000e157  mov     r9, rbx
0x18000e15a  mov     r8, rax
0x18000e15d  lea     rdx, [rbp+57h+var_80]
0x18000e161  lea     rcx, [r15+10h]
0x18000e165  call    ??$_Try_emplace@VHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@?$map@VHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@_N@1@$$QEAVHString@Wrappers@WRL@Microsoft@@$$QEAV?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@Z; std::map<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>>>::_Try_emplace<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>(Microsoft::WRL::Wrappers::HString &&,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>> &&)
0x18000e16a  mov     rbx, [rbp+57h+var_80]
0x18000e16e  mov     rcx, [rbp+57h+string]; string
0x18000e172  call    cs:__imp_WindowsDeleteString
0x18000e178  mov     [rbp+57h+string], r13
0x18000e17c  lea     rcx, [rbp+57h+var_60]
0x18000e180  call    ??1?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>>,0>>(void)
0x18000e185  lea     r15, [rbx+28h]
0x18000e189  mov     rcx, rdi
0x18000e18c  mov     rax, [rdi]
0x18000e18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e194  cmp     [rdi+8], r13w
0x18000e199  jnz     loc_18000E093
0x18000e19f  mov     rdi, r13
0x18000e1a2  mov     rcx, r12
0x18000e1a5  call    ?_Rethrow_if_exception@promise_type@?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@QEAAXXZ; std::experimental::generator<std::basic_string_view<ushort>,std::allocator<char>>::promise_type::_Rethrow_if_exception(void)
0x18000e1aa  jmp     loc_18000E093
0x18000e1af  mov     [r14], rsi
0x18000e1b2  mov     [r14+8], rbx
0x18000e1b6  mov     [r14+10h], r13b
0x18000e1ba  lea     rcx, [rbp+57h+arg_10]
0x18000e1be  call    ??1?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@QEAA@XZ; std::experimental::generator<std::basic_string_view<ushort>,std::allocator<char>>::~generator<std::basic_string_view<ushort>,std::allocator<char>>(void)
0x18000e1c3  jmp     short loc_18000E1E0
0x18000e1c5  lea     rcx, [rbp+57h+arg_10]
0x18000e1c9  call    ??1?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@QEAA@XZ; std::experimental::generator<std::basic_string_view<ushort>,std::allocator<char>>::~generator<std::basic_string_view<ushort>,std::allocator<char>>(void)
0x18000e1ce  cmp     [r15+10h], rbx
0x18000e1d2  setnz   al
0x18000e1d5  mov     [r14], rsi
0x18000e1d8  mov     [r14+8], rbx
0x18000e1dc  mov     [r14+10h], al
0x18000e1e0  mov     rax, r14
0x18000e1e3  lea     r11, [rsp+0D0h+var_30]
0x18000e1eb  mov     rbx, [r11+48h]
0x18000e1ef  movaps  xmm6, xmmword ptr [r11-10h]
0x18000e1f4  mov     rsp, r11
0x18000e1f7  pop     r15
0x18000e1f9  pop     r14
0x18000e1fb  pop     r13
0x18000e1fd  pop     r12
0x18000e1ff  pop     rdi
0x18000e200  pop     rsi
0x18000e201  pop     rbp
0x18000e202  retn
```
