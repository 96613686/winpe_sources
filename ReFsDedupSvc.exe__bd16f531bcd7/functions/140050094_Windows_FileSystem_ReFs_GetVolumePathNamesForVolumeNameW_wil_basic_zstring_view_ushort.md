# Windows::FileSystem::ReFs::GetVolumePathNamesForVolumeNameW(wil::basic_zstring_view<ushort>)

- ea: `0x140050094`
- end: `0x140050281`
- name: `?GetVolumePathNamesForVolumeNameW@ReFs@FileSystem@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@G@wil@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14005f6b8`

## callees

- `0x140004870`
- `0x140019504`
- `0x140019600`
- `0x14001983c`
- `0x1400198e4`
- `0x1400281ac`
- `0x14004bd00`
- `0x14004c9e8`
- `0x14004d568`
- `0x140050094`
- `0x140050288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400501a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400501a3`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14005018f`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x140050207`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x14005018f`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x140050207`

## string_xrefs

- `0x140050105`: `Path is not a volume Path: '%ws'`

## pseudocode

```c
__int64 __fastcall Windows::FileSystem::ReFs::GetVolumePathNamesForVolumeNameW(__int64 a1, const WCHAR **a2)
{
  __int64 v4; // rax
  const WCHAR *v5; // rsi
  __m128i si128; // xmm6
  WCHAR *v7; // rax
  WCHAR *v8; // rax
  const char *v9; // r9
  DWORD cchReturnLength; // [rsp+38h] [rbp-29h] BYREF
  _BYTE v12[40]; // [rsp+40h] [rbp-21h] BYREF
  __int128 v13; // [rsp+68h] [rbp+7h] BYREF
  __m128i v14; // [rsp+78h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  v4 = std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
         v12,
         L"\\\\\\\\\\?\\\\Volume(\\{[[:xdigit:]]{8}-[[:xdigit:]]{4}-[[:xdigit:]]{4}-[[:xdigit:]]{4}-[[:xdigit:]]{12}\\})\\\\?",
         1);
  v5 = *a2;
  LOBYTE(a2) = std::regex_match<std::_String_view_iterator<std::char_traits<unsigned short>>,unsigned short,std::regex_traits<unsigned short>>(
                 *a2,
                 &(*a2)[(_QWORD)a2[1]],
                 v4);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v12);
  if ( (_BYTE)a2 )
  {
    v13 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v14 = si128;
    LOWORD(v13) = 0;
    std::wstring::append(&v13, 260);
    cchReturnLength = 0;
    v7 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v13);
    if ( !GetVolumePathNamesForVolumeNameW(v5, v7, 0x104u, &cchReturnLength) )
    {
      if ( GetLastError() != 234 )
      {
LABEL_5:
        *(_OWORD *)a1 = 0;
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 7;
        *(_WORD *)a1 = 0;
LABEL_13:
        std::wstring::_Tidy_deallocate(&v13);
        return a1;
      }
      if ( (unsigned __int64)cchReturnLength > v14.m128i_i64[0] )
        std::wstring::append(&v13, cchReturnLength - v14.m128i_i64[0]);
      else
        std::wstring::_Eos(&v13);
      v8 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v13);
      if ( !GetVolumePathNamesForVolumeNameW(v5, v8, cchReturnLength, &cchReturnLength) )
      {
        wil::details::in1diag3::Log_GetLastError(
          retaddr,
          (void *)0xCE,
          (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\svclib\\lib\\volumehelpers.cpp",
          v9);
        goto LABEL_5;
      }
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    *(_OWORD *)a1 = v13;
    *(__m128i *)(a1 + 16) = v14;
    v14 = si128;
    LOWORD(v13) = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0xBC,
    (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\svclib\\lib\\volumehelpers.cpp",
    (const char *)0x80070057LL,
    (int)"Path is not a volume Path: '%ws'",
    (const char *)v5);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x140050094  mov     rax, rsp
0x140050097  mov     [rax+18h], rbx
0x14005009b  push    rbp
0x14005009c  push    rsi
0x14005009d  push    rdi
0x14005009e  lea     rbp, [rax-5Fh]
0x1400500a2  sub     rsp, 0A0h
0x1400500a9  movaps  xmmword ptr [rax-28h], xmm6
0x1400500ad  mov     rax, cs:__security_cookie
0x1400500b4  xor     rax, rsp
0x1400500b7  mov     [rbp+57h+var_30], rax
0x1400500bb  mov     rbx, rdx
0x1400500be  mov     rdi, rcx
0x1400500c1  mov     r8d, 1
0x1400500c7  lea     rdx, aVolumeXdigit8X; "\\\\\\\\\\?\\\\Volume(\\{[[:xdigit:]]{8"...
0x1400500ce  lea     rcx, [rbp+57h+var_78]
0x1400500d2  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x1400500d7  mov     r8, rax
0x1400500da  mov     rsi, [rbx]
0x1400500dd  mov     rax, [rbx+8]
0x1400500e1  lea     rdx, [rsi+rax*2]
0x1400500e5  mov     rcx, rsi
0x1400500e8  call    ??$regex_match@V?$_String_view_iterator@U?$char_traits@G@std@@@std@@GV?$regex_traits@G@2@@std@@YA_NV?$_String_view_iterator@U?$char_traits@G@std@@@0@0AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_match<std::_String_view_iterator<std::char_traits<ushort>>,ushort,std::regex_traits<ushort>>(std::_String_view_iterator<std::char_traits<ushort>>,std::_String_view_iterator<std::char_traits<ushort>>,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x1400500ed  mov     bl, al
0x1400500ef  lea     rcx, [rbp+57h+var_78]
0x1400500f3  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x1400500f8  test    bl, bl
0x1400500fa  jnz     short loc_140050148
0x1400500fc  mov     rcx, [rbp+5Fh]; this
0x140050100  mov     [rsp+0B0h+var_88], rsi; char *
0x140050105  lea     rax, aPathIsNotAVolu; "Path is not a volume Path: '%ws'"
0x14005010c  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x140050111  mov     r9d, 80070057h; char *
0x140050117  lea     r8, aOnecoreBaseFsR_2; "onecore\\base\\fs\\refsdedupsvc\\svclib"...
0x14005011e  mov     edx, 0BCh; void *
0x140050123  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x140050128  xorps   xmm0, xmm0
0x14005012b  movups  xmmword ptr [rdi], xmm0
0x14005012e  mov     qword ptr [rdi+10h], 0
0x140050136  mov     qword ptr [rdi+18h], 7
0x14005013e  xor     ecx, ecx
0x140050140  mov     [rdi], cx
0x140050143  jmp     loc_140050259
0x140050148  xorps   xmm0, xmm0
0x14005014b  movups  [rbp+57h+var_50], xmm0
0x14005014f  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x140050157  movdqu  [rbp+57h+var_40], xmm6
0x14005015c  xor     eax, eax
0x14005015e  mov     word ptr [rbp+57h+var_50], ax
0x140050162  mov     ebx, 104h
0x140050167  mov     edx, ebx
0x140050169  lea     rcx, [rbp+57h+var_50]
0x14005016d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x140050172  mov     [rbp+57h+cchReturnLength], 0
0x140050179  lea     rcx, [rbp+57h+var_50]
0x14005017d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140050182  mov     rdx, rax; lpszVolumePathNames
0x140050185  lea     r9, [rbp+57h+cchReturnLength]; lpcchReturnLength
0x140050189  mov     r8d, ebx; cchBufferLength
0x14005018c  mov     rcx, rsi; lpszVolumeName
0x14005018f  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x140050196  nop     dword ptr [rax+rax+00h]
0x14005019b  test    eax, eax
0x14005019d  jnz     loc_140050236
0x1400501a3  call    cs:__imp_GetLastError
0x1400501aa  nop     dword ptr [rax+rax+00h]
0x1400501af  cmp     eax, 0EAh
0x1400501b4  jz      short loc_1400501D3
0x1400501b6  xorps   xmm0, xmm0
0x1400501b9  movups  xmmword ptr [rdi], xmm0
0x1400501bc  mov     qword ptr [rdi+10h], 0
0x1400501c4  mov     qword ptr [rdi+18h], 7
0x1400501cc  xor     eax, eax
0x1400501ce  mov     [rdi], ax
0x1400501d1  jmp     short loc_140050250
0x1400501d3  mov     edx, [rbp+57h+cchReturnLength]
0x1400501d6  lea     rcx, [rbp+57h+var_50]
0x1400501da  cmp     rdx, qword ptr [rbp+57h+var_40]
0x1400501de  ja      short loc_1400501E7
0x1400501e0  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1400501e5  jmp     short loc_1400501F0
0x1400501e7  sub     rdx, qword ptr [rbp+57h+var_40]
0x1400501eb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1400501f0  lea     rcx, [rbp+57h+var_50]
0x1400501f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400501f9  mov     rdx, rax; lpszVolumePathNames
0x1400501fc  lea     r9, [rbp+57h+cchReturnLength]; lpcchReturnLength
0x140050200  mov     r8d, [rbp+57h+cchReturnLength]; cchBufferLength
0x140050204  mov     rcx, rsi; lpszVolumeName
0x140050207  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14005020e  nop     dword ptr [rax+rax+00h]
0x140050213  test    eax, eax
0x140050215  jnz     short loc_14005022E
0x140050217  mov     rcx, [rbp+5Fh]; this
0x14005021b  lea     r8, aOnecoreBaseFsR_2; "onecore\\base\\fs\\refsdedupsvc\\svclib"...
0x140050222  mov     edx, 0CEh; void *
0x140050227  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x14005022c  jmp     short loc_1400501B6
0x14005022e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x140050236  movups  xmm0, [rbp+57h+var_50]
0x14005023a  movups  xmmword ptr [rdi], xmm0
0x14005023d  movups  xmm1, [rbp+57h+var_40]
0x140050241  movups  xmmword ptr [rdi+10h], xmm1
0x140050245  movdqu  [rbp+57h+var_40], xmm6
0x14005024a  xor     eax, eax
0x14005024c  mov     word ptr [rbp+57h+var_50], ax
0x140050250  lea     rcx, [rbp+57h+var_50]
0x140050254  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140050259  mov     rax, rdi
0x14005025c  mov     rcx, [rbp+57h+var_30]
0x140050260  xor     rcx, rsp; StackCookie
0x140050263  call    __security_check_cookie
0x140050268  lea     r11, [rsp+0B0h+var_10]
0x140050270  mov     rbx, [r11+30h]
0x140050274  movaps  xmm6, xmmword ptr [r11-10h]
0x140050279  mov     rsp, r11
0x14005027c  pop     rdi
0x14005027d  pop     rsi
0x14005027e  pop     rbp
0x14005027f  retn
```
