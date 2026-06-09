# Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::Initialize(void)

- ea: `0x18005b724`
- end: `0x18005b8e7`
- name: `?Initialize@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@CAXXZ`
- size: `451`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18005bc94`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x18001b30c`
- `0x180029408`
- `0x18002a5d4`
- `0x18002e304`
- `0x180039e9c`
- `0x180059f98`
- `0x18005b724`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18005b837`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18005b866`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b77a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b793`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b77a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b793`

## pseudocode

```c
void Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::Initialize(void)
{
  const char *v0; // r9
  const char *v1; // r9
  __int64 v2; // rbx
  __int64 v3; // r8
  int v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  _BYTE v8[16]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v10[264]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+398h]

  memset_0(Buffer, 0, 0x208u);
  memset_0(v10, 0, 0x208u);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x293,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      v0);
  if ( !GetSystemDirectoryW(v10, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x297,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      v1);
  StringCchCatW(Buffer, 0x104u, L"\\svchost.exe");
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( Buffer[v3] );
  std::wstring::_Assign<unsigned short>(
    Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath,
    Buffer);
  StringCchCatW(v10, 0x104u, L"\\shellhost.exe");
  do
    ++v2;
  while ( v10[v2] );
  std::wstring::_Assign<unsigned short>(
    Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_shellHostPath,
    v10);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath);
  std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
    (unsigned int)v8,
    v4,
    v4 + 2 * qword_180167910,
    v4,
    *(__int64 *)&_o_towlower);
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_shellHostPath);
  std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
    (unsigned int)v8,
    v5,
    v5 + 2 * qword_1801665A0,
    v5,
    *(__int64 *)&_o_towlower);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
    v6,
    v8,
    Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
    v7,
    v8,
    Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_shellHostPath);
}

```

## disassembly

```asm
0x18005b724  push    rbp
0x18005b726  push    rbx
0x18005b727  push    rsi
0x18005b728  push    rdi
0x18005b729  lea     rbp, [rsp-378h]
0x18005b731  sub     rsp, 478h
0x18005b738  mov     rax, cs:__security_cookie
0x18005b73f  xor     rax, rsp
0x18005b742  mov     [rbp+390h+var_30], rax
0x18005b749  mov     ebx, 208h
0x18005b74e  lea     rcx, [rsp+490h+Buffer]; void *
0x18005b753  mov     r8d, ebx; Size
0x18005b756  xor     edx, edx; Val
0x18005b758  call    memset_0
0x18005b75d  mov     r8d, ebx; Size
0x18005b760  lea     rcx, [rbp+390h+var_240]; void *
0x18005b767  xor     edx, edx; Val
0x18005b769  call    memset_0
0x18005b76e  mov     esi, 104h
0x18005b773  lea     rcx, [rsp+490h+Buffer]; lpBuffer
0x18005b778  mov     edx, esi; uSize
0x18005b77a  call    cs:__imp_GetSystemDirectoryW
0x18005b780  xor     edi, edi
0x18005b782  test    eax, eax
0x18005b784  jz      loc_18005B8CE
0x18005b78a  mov     edx, esi; uSize
0x18005b78c  lea     rcx, [rbp+390h+var_240]; lpBuffer
0x18005b793  call    cs:__imp_GetSystemDirectoryW
0x18005b799  test    eax, eax
0x18005b79b  jz      loc_18005B8B5
0x18005b7a1  lea     r8, aSvchostExe; "\\svchost.exe"
0x18005b7a8  mov     edx, esi; unsigned __int64
0x18005b7aa  lea     rcx, [rsp+490h+Buffer]; unsigned __int16 *
0x18005b7af  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005b7b4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005b7b8  lea     rax, [rsp+490h+Buffer]
0x18005b7bd  mov     r8, rbx
0x18005b7c0  inc     r8
0x18005b7c3  cmp     [rax+r8*2], di
0x18005b7c8  jnz     short loc_18005B7C0
0x18005b7ca  lea     rdx, [rsp+490h+Buffer]
0x18005b7cf  lea     rcx, ?m_svcHostPath@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath
0x18005b7d6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005b7db  lea     r8, aShellhostExe; "\\shellhost.exe"
0x18005b7e2  mov     rdx, rsi; unsigned __int64
0x18005b7e5  lea     rcx, [rbp+390h+var_240]; unsigned __int16 *
0x18005b7ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005b7f1  lea     rax, [rbp+390h+var_240]
0x18005b7f8  inc     rbx
0x18005b7fb  cmp     [rax+rbx*2], di
0x18005b7ff  jnz     short loc_18005B7F8
0x18005b801  mov     r8, rbx
0x18005b804  lea     rdx, [rbp+390h+var_240]
0x18005b80b  lea     rbx, ?m_shellHostPath@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_shellHostPath
0x18005b812  mov     rcx, rbx
0x18005b815  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005b81a  lea     rcx, ?m_svcHostPath@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath
0x18005b821  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005b826  mov     rcx, cs:qword_180167910
0x18005b82d  mov     r9, rax
0x18005b830  mov     rdx, rax
0x18005b833  lea     r8, [rax+rcx*2]
0x18005b837  mov     rcx, cs:__imp__o_towlower
0x18005b83e  mov     [rsp+490h+var_470], rcx
0x18005b843  lea     rcx, [rsp+490h+var_460]
0x18005b848  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18005b84d  mov     rcx, rbx
0x18005b850  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005b855  mov     rcx, cs:qword_1801665A0
0x18005b85c  mov     r9, rax
0x18005b85f  mov     rdx, rax
0x18005b862  lea     r8, [rax+rcx*2]
0x18005b866  mov     rcx, cs:__imp__o_towlower
0x18005b86d  mov     [rsp+490h+var_470], rcx
0x18005b872  lea     rcx, [rsp+490h+var_460]
0x18005b877  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18005b87c  lea     r8, ?m_svcHostPath@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath
0x18005b883  lea     rdx, [rsp+490h+var_460]
0x18005b888  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(std::wstring &)
0x18005b88d  mov     r8, rbx
0x18005b890  lea     rdx, [rsp+490h+var_460]
0x18005b895  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(std::wstring &)
0x18005b89a  mov     rcx, [rbp+390h+var_30]
0x18005b8a1  xor     rcx, rsp; StackCookie
0x18005b8a4  call    __security_check_cookie
0x18005b8a9  add     rsp, 478h
0x18005b8b0  pop     rdi
0x18005b8b1  pop     rsi
0x18005b8b2  pop     rbx
0x18005b8b3  pop     rbp
0x18005b8b4  retn
0x18005b8b5  mov     rcx, [rbp+398h]; this
0x18005b8bc  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005b8c3  mov     edx, 297h; void *
0x18005b8c8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005b8ce  mov     rcx, [rbp+398h]; this
0x18005b8d5  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005b8dc  mov     edx, 293h; void *
0x18005b8e1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
