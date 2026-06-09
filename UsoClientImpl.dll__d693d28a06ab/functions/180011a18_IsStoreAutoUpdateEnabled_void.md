# IsStoreAutoUpdateEnabled(void)

- ea: `0x180011a18`
- end: `0x180011fc7`
- name: `?IsStoreAutoUpdateEnabled@@YA_NXZ`
- size: `1455`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800120a0`

## callees

- `0x180009380`
- `0x180011a18`
- `0x180033bf0`
- `0x180033e48`
- `0x180033f14`
- `0x180036b10`
- `0x180056500`

## string_xrefs

- `0x180011cbb`: `AllowAppStoreAutoUpdate`
- `0x180011cb1`: `\WindowsUpdate`
- `0x180011de9`: `\WindowsUpdate`
- `0x180011f1b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180011f31`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180011f47`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180011f5d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180011f73`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180011f89`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180011f9f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180011fb5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char IsStoreAutoUpdateEnabled(void)
{
  __int64 traits_2_unsigned_short; // rax
  __int64 v1; // r8
  const char *v2; // r9
  __int64 v3; // r11
  __int64 v4; // rax
  __int64 v5; // rbx
  __int16 *v6; // rax
  const char *v7; // r9
  __int64 v8; // rax
  __int64 v9; // rax
  int SystemValueOrDefault; // edi
  __int64 v11; // rax
  const char *v12; // r9
  __int64 v13; // r11
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  __int16 *v17; // rax
  const char *v18; // r9
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v22; // rax
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r11
  __int64 v26; // rax
  __int16 *v27; // rax
  const char *v28; // r9
  __int64 v29; // rax
  __int64 v30; // rax
  bool v31; // bl
  __int16 *v32; // rax
  __int64 v33; // r8
  const char *v34; // r9
  __int64 v35; // rax
  __int64 v36; // rax
  const char *v37; // r9
  __int64 v38; // r11
  __int64 v39; // rax
  const wchar_t *v40; // [rsp+38h] [rbp-79h] BYREF
  __int64 v41; // [rsp+40h] [rbp-71h]
  __int128 v42; // [rsp+48h] [rbp-69h] BYREF
  const wchar_t *v43; // [rsp+58h] [rbp-59h] BYREF
  __int64 v44; // [rsp+60h] [rbp-51h]
  int v45; // [rsp+68h] [rbp-49h] BYREF
  void **v46; // [rsp+70h] [rbp-41h] BYREF
  _DWORD v47[8]; // [rsp+78h] [rbp-39h] BYREF
  char v48; // [rsp+98h] [rbp-19h]
  char v49; // [rsp+A0h] [rbp-11h]
  _DWORD v50[8]; // [rsp+A8h] [rbp-9h] BYREF
  char v51; // [rsp+C8h] [rbp+17h]
  char v52; // [rsp+D0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]

  v46 = &Windows::Registry::`vftable';
  v45 = 0;
  traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              L"DisableStoreOriginatedApps",
                              &word_18006877E,
                              0);
  if ( traits_2_unsigned_short == v3
    || (v4 = (traits_2_unsigned_short - (__int64)L"DisableStoreOriginatedApps") >> 1, v5 = -1, v4 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v2);
  }
  v40 = L"DisableStoreOriginatedApps";
  v41 = v4;
  v6 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                    L"\\ApplicationManagement",
                    &word_1800687AE,
                    v1);
  if ( v6 == &word_1800687AE || (v8 = ((char *)v6 - (char *)L"\\ApplicationManagement") >> 1, v8 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v7);
  *(_QWORD *)&v42 = L"\\ApplicationManagement";
  *((_QWORD *)&v42 + 1) = v8;
  v43 = SystemInterface::Registry::POLICYMANAGER_CURRENT_ROOT_ID;
  v9 = -1;
  do
    ++v9;
  while ( SystemInterface::Registry::POLICYMANAGER_CURRENT_ROOT_ID[v9] );
  v44 = v9;
  SystemValueOrDefault = SystemInterface::Registry::GetSystemValueOrDefault(
                           (unsigned int)&v46,
                           (unsigned int)&v43,
                           (unsigned int)&v42,
                           (unsigned int)&v40,
                           (__int64)&v45);
  v45 = 0;
  v11 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
          L"DisableStoreApps",
          word_1800687D2,
          0);
  if ( v11 == v13 || (v14 = (v11 - (__int64)L"DisableStoreApps") >> 1, v14 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v12);
  v43 = L"DisableStoreApps";
  v44 = v14;
  v42 = 0u;
  v40 = SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID;
  v15 = -1;
  do
    ++v15;
  while ( SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID[v15] );
  v41 = v15;
  v16 = SystemInterface::Registry::GetSystemValueOrDefault(
          (unsigned int)&v46,
          (unsigned int)&v40,
          (unsigned int)&v42,
          (unsigned int)&v43,
          (__int64)&v45);
  if ( SystemValueOrDefault == 1 || v16 == 1 )
    return 0;
  v17 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"AutoDownload",
                     word_1800687F2,
                     0);
  if ( v17 == word_1800687F2 || (v19 = ((char *)v17 - (char *)L"AutoDownload") >> 1, v19 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v18);
  v43 = L"AutoDownload";
  v44 = v19;
  v42 = 0u;
  v40 = SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID;
  v20 = -1;
  do
    ++v20;
  while ( SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID[v20] );
  v41 = v20;
  Windows::Registry::TryGetSystemValue(
    (unsigned int)&v46,
    (unsigned int)v47,
    (unsigned int)&v40,
    (unsigned int)&v42,
    (__int64)&v43);
  if ( v49 && !v48 )
    return v47[0] == 4;
  v22 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
          L"AllowAppStoreAutoUpdate",
          L"\\WindowsUpdate",
          0);
  if ( v22 == v25 || (v26 = (v22 - (__int64)L"AllowAppStoreAutoUpdate") >> 1, v26 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v24);
  v43 = L"AllowAppStoreAutoUpdate";
  v44 = v26;
  v27 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"\\ApplicationManagement",
                     &word_1800687AE,
                     v23);
  if ( v27 == &word_1800687AE || (v29 = ((char *)v27 - (char *)L"\\ApplicationManagement") >> 1, v29 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v28);
  *(_QWORD *)&v42 = L"\\ApplicationManagement";
  *((_QWORD *)&v42 + 1) = v29;
  v40 = SystemInterface::Registry::POLICYMANAGER_CURRENT_ROOT_ID;
  v30 = -1;
  do
    ++v30;
  while ( SystemInterface::Registry::POLICYMANAGER_CURRENT_ROOT_ID[v30] );
  v41 = v30;
  Windows::Registry::TryGetSystemValue(
    (unsigned int)&v46,
    (unsigned int)v50,
    (unsigned int)&v40,
    (unsigned int)&v42,
    (__int64)&v43);
  if ( v52 && !v51 )
  {
    v31 = v50[0] == 1;
    if ( v49 && v48 != -1 && v48 && v48 != 1 )
      std::wstring::~wstring(v47);
    return v31;
  }
  v45 = 4;
  v32 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"AutoDownload",
                     word_1800687F2,
                     0);
  if ( v32 == word_1800687F2 || (v35 = ((char *)v32 - (char *)L"AutoDownload") >> 1, v35 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v34);
  v43 = L"AutoDownload";
  v44 = v35;
  v36 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
          L"\\WindowsUpdate",
          &word_180068846,
          v33);
  if ( v36 == v38 || (v39 = (v36 - (__int64)L"\\WindowsUpdate") >> 1, v39 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v37);
  *(_QWORD *)&v42 = L"\\WindowsUpdate";
  *((_QWORD *)&v42 + 1) = v39;
  v40 = SystemInterface::Registry::CURRENTVERSION_WINDOWSSTORE_REDIRECTION_ID;
  do
    ++v5;
  while ( SystemInterface::Registry::CURRENTVERSION_WINDOWSSTORE_REDIRECTION_ID[v5] );
  v41 = v5;
  if ( (unsigned int)SystemInterface::Registry::GetSystemValueOrDefault(
                       (unsigned int)&v46,
                       (unsigned int)&v40,
                       (unsigned int)&v42,
                       (unsigned int)&v43,
                       (__int64)&v45) != 4 )
  {
    if ( v52 && v51 != -1 && v51 && v51 != 1 )
      std::wstring::~wstring(v50);
    if ( v49 && v48 != -1 && v48 && v48 != 1 )
      std::wstring::~wstring(v47);
    return 0;
  }
  if ( v52 && v51 != -1 && v51 && v51 != 1 )
    std::wstring::~wstring(v50);
  if ( v49 && v48 != -1 && v48 && v48 != 1 )
    std::wstring::~wstring(v47);
  return 1;
}

```

## disassembly

```asm
0x180011a18  mov     rax, rsp
0x180011a1b  mov     [rax+8], rbx
0x180011a1f  mov     [rax+10h], rsi
0x180011a23  mov     [rax+18h], rdi
0x180011a27  push    rbp
0x180011a28  push    r12
0x180011a2a  push    r13
0x180011a2c  push    r14
0x180011a2e  push    r15
0x180011a30  lea     rbp, [rax-5Fh]
0x180011a34  sub     rsp, 0E0h
0x180011a3b  mov     rax, cs:__security_cookie
0x180011a42  xor     rax, rsp
0x180011a45  mov     [rbp+57h+var_30], rax
0x180011a49  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x180011a50  mov     [rbp+57h+var_98], rax
0x180011a54  xor     esi, esi
0x180011a56  mov     [rbp+57h+var_A0], esi
0x180011a59  xor     r8d, r8d
0x180011a5c  lea     r11, word_18006877E
0x180011a63  mov     rdx, r11
0x180011a66  lea     rdi, aDisablestoreor; "DisableStoreOriginatedApps"
0x180011a6d  mov     rcx, rdi
0x180011a70  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180011a75  cmp     rax, r11
0x180011a78  jz      loc_180011F2D
0x180011a7e  sub     rax, rdi
0x180011a81  sar     rax, 1
0x180011a84  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011a88  cmp     rax, rbx
0x180011a8b  jz      loc_180011F2D
0x180011a91  mov     qword ptr [rbp+57h+var_D0], rdi
0x180011a95  mov     qword ptr [rbp+57h+var_D0+8], rax
0x180011a99  lea     r13, word_1800687AE
0x180011aa0  mov     rdx, r13
0x180011aa3  lea     r14, aApplicationman; "\\ApplicationManagement"
0x180011aaa  mov     rcx, r14
0x180011aad  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180011ab2  cmp     rax, r13
0x180011ab5  jz      loc_180011F17
0x180011abb  sub     rax, r14
0x180011abe  sar     rax, 1
0x180011ac1  cmp     rax, rbx
0x180011ac4  jz      loc_180011F17
0x180011aca  mov     qword ptr [rbp+57h+var_C0], r14
0x180011ace  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180011ad2  mov     rcx, cs:?POLICYMANAGER_CURRENT_ROOT_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::POLICYMANAGER_CURRENT_ROOT_ID
0x180011ad9  mov     qword ptr [rbp+57h+var_B0], rcx
0x180011add  mov     rax, rbx
0x180011ae0  inc     rax
0x180011ae3  cmp     [rcx+rax*2], si
0x180011ae7  jnz     short loc_180011AE0
0x180011ae9  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180011aed  movups  xmm0, [rbp+57h+var_D0]
0x180011af1  movdqu  [rbp+57h+var_D0], xmm0
0x180011af6  movups  xmm1, [rbp+57h+var_C0]
0x180011afa  movdqu  [rbp+57h+var_C0], xmm1
0x180011aff  movaps  xmm0, [rbp+57h+var_B0]
0x180011b03  movdqa  [rbp+57h+var_B0], xmm0
0x180011b08  lea     rax, [rbp+57h+var_A0]
0x180011b0c  mov     [rsp+100h+var_E0], rax
0x180011b11  lea     r9, [rbp+57h+var_D0]
0x180011b15  lea     r8, [rbp+57h+var_C0]
0x180011b19  lea     rdx, [rbp+57h+var_B0]
0x180011b1d  lea     rcx, [rbp+57h+var_98]
0x180011b21  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAAIV?$basic_zstring_view@_W@wil@@00AEBI@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,uint const &)
0x180011b26  mov     edi, eax
0x180011b28  mov     [rbp+57h+var_A0], esi
0x180011b2b  xor     r8d, r8d
0x180011b2e  lea     r11, word_1800687D2
0x180011b35  mov     rdx, r11
0x180011b38  lea     r15, aDisablestoreap; "DisableStoreApps"
0x180011b3f  mov     rcx, r15
0x180011b42  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180011b47  cmp     rax, r11
0x180011b4a  jz      loc_180011FB1
0x180011b50  sub     rax, r15
0x180011b53  sar     rax, 1
0x180011b56  cmp     rax, rbx
0x180011b59  jz      loc_180011FB1
0x180011b5f  mov     qword ptr [rbp+57h+var_B0], r15
0x180011b63  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180011b67  mov     qword ptr [rbp+57h+var_C0], rsi
0x180011b6b  mov     qword ptr [rbp+57h+var_C0+8], rsi
0x180011b6f  mov     rcx, cs:?POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID
0x180011b76  mov     qword ptr [rbp+57h+var_D0], rcx
0x180011b7a  mov     rax, rbx
0x180011b7d  inc     rax
0x180011b80  cmp     [rcx+rax*2], si
0x180011b84  jnz     short loc_180011B7D
0x180011b86  mov     qword ptr [rbp+57h+var_D0+8], rax
0x180011b8a  movups  xmm0, [rbp+57h+var_B0]
0x180011b8e  movdqu  [rbp+57h+var_B0], xmm0
0x180011b93  movaps  xmm1, [rbp+57h+var_C0]
0x180011b97  movdqa  [rbp+57h+var_C0], xmm1
0x180011b9c  movaps  xmm0, [rbp+57h+var_D0]
0x180011ba0  movdqa  [rbp+57h+var_D0], xmm0
0x180011ba5  lea     rax, [rbp+57h+var_A0]
0x180011ba9  mov     [rsp+100h+var_E0], rax
0x180011bae  lea     r9, [rbp+57h+var_B0]
0x180011bb2  lea     r8, [rbp+57h+var_C0]
0x180011bb6  lea     rdx, [rbp+57h+var_D0]
0x180011bba  lea     rcx, [rbp+57h+var_98]
0x180011bbe  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAAIV?$basic_zstring_view@_W@wil@@00AEBI@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,uint const &)
0x180011bc3  cmp     edi, 1
0x180011bc6  jz      loc_180011EBC
0x180011bcc  cmp     eax, 1
0x180011bcf  jz      loc_180011EBC
0x180011bd5  xor     r8d, r8d
0x180011bd8  lea     r15, word_1800687F2
0x180011bdf  mov     rdx, r15
0x180011be2  lea     rdi, aAutodownload; "AutoDownload"
0x180011be9  mov     rcx, rdi
0x180011bec  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180011bf1  cmp     rax, r15
0x180011bf4  jz      loc_180011F9B
0x180011bfa  sub     rax, rdi
0x180011bfd  sar     rax, 1
0x180011c00  cmp     rax, rbx
0x180011c03  jz      loc_180011F9B
0x180011c09  mov     qword ptr [rbp+57h+var_B0], rdi
0x180011c0d  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180011c11  mov     qword ptr [rbp+57h+var_C0], rsi
0x180011c15  mov     qword ptr [rbp+57h+var_C0+8], rsi
0x180011c19  mov     rcx, cs:?POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWSSTORE_REDIRECTION_ID
0x180011c20  mov     qword ptr [rbp+57h+var_D0], rcx
0x180011c24  mov     rax, rbx
0x180011c27  inc     rax
0x180011c2a  cmp     [rcx+rax*2], si
0x180011c2e  jnz     short loc_180011C27
0x180011c30  mov     qword ptr [rbp+57h+var_D0+8], rax
0x180011c34  movups  xmm0, [rbp+57h+var_B0]
0x180011c38  movdqu  [rbp+57h+var_B0], xmm0
0x180011c3d  movaps  xmm1, [rbp+57h+var_C0]
0x180011c41  movdqa  [rbp+57h+var_C0], xmm1
0x180011c46  movaps  xmm0, [rbp+57h+var_D0]
0x180011c4a  movdqa  [rbp+57h+var_D0], xmm0
0x180011c4f  lea     rax, [rbp+57h+var_B0]
0x180011c53  mov     [rsp+100h+var_E0], rax
0x180011c58  lea     r9, [rbp+57h+var_C0]
0x180011c5c  lea     r8, [rbp+57h+var_D0]
0x180011c60  lea     rdx, [rbp+57h+var_90]
0x180011c64  lea     rcx, [rbp+57h+var_98]
0x180011c68  call    ?TryGetSystemValue@Registry@Windows@@UEAA?AV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@V?$basic_zstring_view@_W@wil@@00@Z; Windows::Registry::TryGetSystemValue(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180011c6d  nop
0x180011c6e  cmp     [rbp+57h+var_68], sil
0x180011c72  jz      short loc_180011CAE
0x180011c74  cmp     [rbp+57h+var_70], sil
0x180011c78  jnz     short loc_180011CAE
0x180011c7a  cmp     [rbp+57h+var_90], 4
0x180011c7e  setz    al
0x180011c81  mov     rcx, [rbp+57h+var_30]
0x180011c85  xor     rcx, rsp; StackCookie
0x180011c88  call    __security_check_cookie
0x180011c8d  lea     r11, [rsp+100h+var_20]
0x180011c95  mov     rbx, [r11+30h]
0x180011c99  mov     rsi, [r11+38h]
0x180011c9d  mov     rdi, [r11+40h]
0x180011ca1  mov     rsp, r11
0x180011ca4  pop     r15
0x180011ca6  pop     r14
0x180011ca8  pop     r13
0x180011caa  pop     r12
0x180011cac  pop     rbp
0x180011cad  retn
0x180011cae  xor     r8d, r8d
0x180011cb1  lea     r11, aWindowsupdate; "\\WindowsUpdate"
0x180011cb8  mov     rdx, r11
0x180011cbb  lea     r12, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x180011cc2  mov     rcx, r12
0x180011cc5  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180011cca  cmp     rax, r11
0x180011ccd  jz      loc_180011F85
0x180011cd3  sub     rax, r12
0x180011cd6  sar     rax, 1
0x180011cd9  cmp     rax, rbx
0x180011cdc  jz      loc_180011F85
0x180011ce2  mov     qword ptr [rbp+57h+var_B0], r12
0x180011ce6  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180011cea  mov     rdx, r13
0x180011ced  mov     rcx, r14
0x180011cf0  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180011cf5  cmp     rax, r13
0x180011cf8  jz      loc_180011F6F
0x180011cfe  sub     rax, r14
0x180011d01  sar     rax, 1
0x180011d04  cmp     rax, rbx
0x180011d07  jz      loc_180011F6F
0x180011d0d  mov     qword ptr [rbp+57h+var_C0], r14
0x180011d11  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180011d15  mov     rcx, cs:?POLICYMANAGER_CURRENT_ROOT_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::POLICYMANAGER_CURRENT_ROOT_ID
0x180011d1c  mov     qword ptr [rbp+57h+var_D0], rcx
0x180011d20  mov     rax, rbx
0x180011d23  inc     rax
0x180011d26  cmp     [rcx+rax*2], si
0x180011d2a  jnz     short loc_180011D23
0x180011d2c  mov     qword ptr [rbp+57h+var_D0+8], rax
0x180011d30  movups  xmm0, [rbp+57h+var_B0]
0x180011d34  movdqu  [rbp+57h+var_B0], xmm0
0x180011d39  movups  xmm1, [rbp+57h+var_C0]
0x180011d3d  movdqu  [rbp+57h+var_C0], xmm1
0x180011d42  movaps  xmm0, [rbp+57h+var_D0]
0x180011d46  movdqa  [rbp+57h+var_D0], xmm0
0x180011d4b  lea     rax, [rbp+57h+var_B0]
0x180011d4f  mov     [rsp+100h+var_E0], rax
0x180011d54  lea     r9, [rbp+57h+var_C0]
0x180011d58  lea     r8, [rbp+57h+var_D0]
0x180011d5c  lea     rdx, [rbp+57h+var_60]
0x180011d60  lea     rcx, [rbp+57h+var_98]
0x180011d64  call    ?TryGetSystemValue@Registry@Windows@@UEAA?AV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@V?$basic_zstring_view@_W@wil@@00@Z; Windows::Registry::TryGetSystemValue(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180011d69  nop
0x180011d6a  cmp     [rbp+57h+var_38], sil
0x180011d6e  jz      short loc_180011DAA
0x180011d70  cmp     [rbp+57h+var_40], sil
0x180011d74  jnz     short loc_180011DAA
0x180011d76  cmp     [rbp+57h+var_60], 1
0x180011d7a  setz    bl
0x180011d7d  cmp     [rbp+57h+var_68], sil
0x180011d81  jz      short loc_180011DA3
0x180011d83  movsx   rcx, [rbp+57h+var_70]
0x180011d88  add     rcx, 1
0x180011d8c  jz      short loc_180011DA3
0x180011d8e  sub     rcx, 1
0x180011d92  jz      short loc_180011DA3
0x180011d94  cmp     rcx, 1
0x180011d98  jz      short loc_180011DA3
0x180011d9a  lea     rcx, [rbp+57h+var_90]; void *
0x180011d9e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011da3  mov     al, bl
0x180011da5  jmp     loc_180011C81
0x180011daa  mov     [rbp+57h+var_A0], 4
0x180011db1  xor     r8d, r8d
0x180011db4  mov     rdx, r15
0x180011db7  mov     rcx, rdi
0x180011dba  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180011dbf  cmp     rax, r15
0x180011dc2  jz      loc_180011F59
0x180011dc8  sub     rax, rdi
0x180011dcb  sar     rax, 1
0x180011dce  cmp     rax, rbx
0x180011dd1  jz      loc_180011F59
0x180011dd7  mov     qword ptr [rbp+57h+var_B0], rdi
0x180011ddb  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180011ddf  lea     r11, word_180068846
0x180011de6  mov     rdx, r11
0x180011de9  lea     rdi, aWindowsupdate; "\\WindowsUpdate"
0x180011df0  mov     rcx, rdi
0x180011df3  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180011df8  cmp     rax, r11
0x180011dfb  jz      loc_180011F43
0x180011e01  sub     rax, rdi
0x180011e04  sar     rax, 1
0x180011e07  cmp     rax, rbx
0x180011e0a  jz      loc_180011F43
0x180011e10  mov     qword ptr [rbp+57h+var_C0], rdi
0x180011e14  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180011e18  mov     rax, cs:?CURRENTVERSION_WINDOWSSTORE_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CURRENTVERSION_WINDOWSSTORE_REDIRECTION_ID
0x180011e1f  mov     qword ptr [rbp+57h+var_D0], rax
0x180011e23  inc     rbx
0x180011e26  cmp     [rax+rbx*2], si
0x180011e2a  jnz     short loc_180011E23
0x180011e2c  mov     qword ptr [rbp+57h+var_D0+8], rbx
0x180011e30  movups  xmm0, [rbp+57h+var_B0]
0x180011e34  movdqu  [rbp+57h+var_B0], xmm0
0x180011e39  movups  xmm1, [rbp+57h+var_C0]
0x180011e3d  movdqu  [rbp+57h+var_C0], xmm1
0x180011e42  movaps  xmm0, [rbp+57h+var_D0]
0x180011e46  movdqa  [rbp+57h+var_D0], xmm0
0x180011e4b  lea     rax, [rbp+57h+var_A0]
0x180011e4f  mov     [rsp+100h+var_E0], rax
0x180011e54  lea     r9, [rbp+57h+var_B0]
0x180011e58  lea     r8, [rbp+57h+var_C0]
0x180011e5c  lea     rdx, [rbp+57h+var_D0]
0x180011e60  lea     rcx, [rbp+57h+var_98]
0x180011e64  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAAIV?$basic_zstring_view@_W@wil@@00AEBI@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,uint const &)
0x180011e69  nop
0x180011e6a  cmp     eax, 4
0x180011e6d  jz      short loc_180011EC3
0x180011e6f  cmp     [rbp+57h+var_38], sil
0x180011e73  jz      short loc_180011E96
0x180011e75  movsx   rax, [rbp+57h+var_40]
0x180011e7a  add     rax, 1
0x180011e7e  jz      short loc_180011E96
0x180011e80  sub     rax, 1
0x180011e84  jz      short loc_180011E96
0x180011e86  cmp     rax, 1
0x180011e8a  jz      short loc_180011E96
0x180011e8c  lea     rcx, [rbp+57h+var_60]; void *
0x180011e90  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011e95  nop
0x180011e96  cmp     [rbp+57h+var_68], sil
0x180011e9a  jz      short loc_180011EBC
0x180011e9c  movsx   rax, [rbp+57h+var_70]
0x180011ea1  add     rax, 1
0x180011ea5  jz      short loc_180011EBC
0x180011ea7  sub     rax, 1
0x180011eab  jz      short loc_180011EBC
0x180011ead  cmp     rax, 1
0x180011eb1  jz      short loc_180011EBC
0x180011eb3  lea     rcx, [rbp+57h+var_90]; void *
  ... truncated ...
```
