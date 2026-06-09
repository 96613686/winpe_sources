# Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::Initialize(void)

- ea: `0x18002e788`
- end: `0x18002e94b`
- name: `?Initialize@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@CAXXZ`
- size: `451`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002ecf8`

## callees

- `0x180003c80`
- `0x180004814`
- `0x18000e938`
- `0x18001b444`
- `0x180020814`
- `0x180021204`
- `0x180023690`
- `0x18002dec0`
- `0x18002e788`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18002e89b`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18002e8ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002e7de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002e7f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002e7de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002e7f7`

## pseudocode

```c
void Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::Initialize(void)
{
  const char *v0; // r9
  const char *v1; // r9
  __int64 v2; // r9
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  _BYTE v16[16]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v18[264]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+398h]

  memset_0(Buffer, 0, 0x208u);
  memset_0(v18, 0, 0x208u);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x293,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      v0);
  if ( !GetSystemDirectoryW(v18, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x297,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      v1);
  StringCchCatW(Buffer, 0x104u, L"\\svchost.exe");
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( Buffer[v4] );
  std::wstring::_Assign<unsigned short>(
    (__int64)Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath,
    (__int64)Buffer,
    v4,
    v2);
  StringCchCatW(v18, 0x104u, L"\\shellhost.exe");
  do
    ++v3;
  while ( v18[v3] );
  std::wstring::_Assign<unsigned short>(
    (__int64)Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_shellHostPath,
    (__int64)v18,
    v3,
    v5);
  v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
         Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath,
         v6,
         v7,
         v8);
  std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
    (unsigned int)v16,
    v9,
    v9 + 2 * qword_180062320,
    v9,
    _o_towlower);
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
          Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_shellHostPath,
          v10,
          v11,
          v12);
  std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
    (unsigned int)v16,
    v13,
    v13 + 2 * qword_1800612F0,
    v13,
    _o_towlower);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
    v14,
    v16,
    Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
    v15,
    v16,
    Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_shellHostPath);
}

```

## disassembly

```asm
0x18002e788  push    rbp
0x18002e78a  push    rbx
0x18002e78b  push    rsi
0x18002e78c  push    rdi
0x18002e78d  lea     rbp, [rsp-378h]
0x18002e795  sub     rsp, 478h
0x18002e79c  mov     rax, cs:__security_cookie
0x18002e7a3  xor     rax, rsp
0x18002e7a6  mov     [rbp+390h+var_30], rax
0x18002e7ad  mov     ebx, 208h
0x18002e7b2  lea     rcx, [rsp+490h+Buffer]; void *
0x18002e7b7  mov     r8d, ebx; Size
0x18002e7ba  xor     edx, edx; Val
0x18002e7bc  call    memset_0
0x18002e7c1  mov     r8d, ebx; Size
0x18002e7c4  lea     rcx, [rbp+390h+var_240]; void *
0x18002e7cb  xor     edx, edx; Val
0x18002e7cd  call    memset_0
0x18002e7d2  mov     esi, 104h
0x18002e7d7  lea     rcx, [rsp+490h+Buffer]; lpBuffer
0x18002e7dc  mov     edx, esi; uSize
0x18002e7de  call    cs:__imp_GetSystemDirectoryW
0x18002e7e4  xor     edi, edi
0x18002e7e6  test    eax, eax
0x18002e7e8  jz      loc_18002E932
0x18002e7ee  mov     edx, esi; uSize
0x18002e7f0  lea     rcx, [rbp+390h+var_240]; lpBuffer
0x18002e7f7  call    cs:__imp_GetSystemDirectoryW
0x18002e7fd  test    eax, eax
0x18002e7ff  jz      loc_18002E919
0x18002e805  lea     r8, aSvchostExe; "\\svchost.exe"
0x18002e80c  mov     edx, esi; unsigned __int64
0x18002e80e  lea     rcx, [rsp+490h+Buffer]; unsigned __int16 *
0x18002e813  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e818  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e81c  lea     rax, [rsp+490h+Buffer]
0x18002e821  mov     r8, rbx
0x18002e824  inc     r8
0x18002e827  cmp     [rax+r8*2], di
0x18002e82c  jnz     short loc_18002E824
0x18002e82e  lea     rdx, [rsp+490h+Buffer]
0x18002e833  lea     rcx, ?m_svcHostPath@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath
0x18002e83a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002e83f  lea     r8, aShellhostExe; "\\shellhost.exe"
0x18002e846  mov     rdx, rsi; unsigned __int64
0x18002e849  lea     rcx, [rbp+390h+var_240]; unsigned __int16 *
0x18002e850  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e855  lea     rax, [rbp+390h+var_240]
0x18002e85c  inc     rbx
0x18002e85f  cmp     [rax+rbx*2], di
0x18002e863  jnz     short loc_18002E85C
0x18002e865  mov     r8, rbx
0x18002e868  lea     rdx, [rbp+390h+var_240]
0x18002e86f  lea     rbx, ?m_shellHostPath@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_shellHostPath
0x18002e876  mov     rcx, rbx
0x18002e879  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002e87e  lea     rcx, ?m_svcHostPath@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath
0x18002e885  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002e88a  mov     rcx, cs:qword_180062320
0x18002e891  mov     r9, rax
0x18002e894  mov     rdx, rax
0x18002e897  lea     r8, [rax+rcx*2]
0x18002e89b  mov     rcx, cs:__imp__o_towlower
0x18002e8a2  mov     [rsp+490h+var_470], rcx
0x18002e8a7  lea     rcx, [rsp+490h+var_460]
0x18002e8ac  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18002e8b1  mov     rcx, rbx
0x18002e8b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002e8b9  mov     rcx, cs:qword_1800612F0
0x18002e8c0  mov     r9, rax
0x18002e8c3  mov     rdx, rax
0x18002e8c6  lea     r8, [rax+rcx*2]
0x18002e8ca  mov     rcx, cs:__imp__o_towlower
0x18002e8d1  mov     [rsp+490h+var_470], rcx
0x18002e8d6  lea     rcx, [rsp+490h+var_460]
0x18002e8db  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18002e8e0  lea     r8, ?m_svcHostPath@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::m_svcHostPath
0x18002e8e7  lea     rdx, [rsp+490h+var_460]
0x18002e8ec  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(std::wstring &)
0x18002e8f1  mov     r8, rbx
0x18002e8f4  lea     rdx, [rsp+490h+var_460]
0x18002e8f9  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(std::wstring &)
0x18002e8fe  mov     rcx, [rbp+390h+var_30]
0x18002e905  xor     rcx, rsp; StackCookie
0x18002e908  call    __security_check_cookie
0x18002e90d  add     rsp, 478h
0x18002e914  pop     rdi
0x18002e915  pop     rsi
0x18002e916  pop     rbx
0x18002e917  pop     rbp
0x18002e918  retn
0x18002e919  mov     rcx, [rbp+398h]; this
0x18002e920  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\core\\sync"...
0x18002e927  mov     edx, 297h; void *
0x18002e92c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002e932  mov     rcx, [rbp+398h]; this
0x18002e939  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\core\\sync"...
0x18002e940  mov     edx, 293h; void *
0x18002e945  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
