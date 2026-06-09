# SetDisplayLanguage(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &,void *)

- ea: `0x180037aac`
- end: `0x180038099`
- name: `?SetDisplayLanguage@@YAJAEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@PEAX@Z`
- size: `1517`
- prototype: `__int64 __fastcall(const wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180030f64`

## callees

- `0x180003a00`
- `0x180009084`
- `0x18000a024`
- `0x1800137bc`
- `0x180014ed0`
- `0x18001a570`
- `0x18001fba4`
- `0x1800263ac`
- `0x180027818`
- `0x18002bcc8`
- `0x180034b30`
- `0x180034e50`
- `0x180037aac`
- `0x180039480`
- `0x180060df4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037bb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037c2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037cdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037d20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003803c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037bb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037c2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037cdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037d20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003803c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037bdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037d5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037bdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037d5a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180037d38`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180037e7a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180037fe0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180038054`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180037d38`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180037e7a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180037fe0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180038054`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180037b09`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180037b09`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x180037bed`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x180037bed`
- `WinLangdb!SetUserLanguages` at `0x180037e25`
- `WinLangdb!SetUserLanguages` at `0x180037f82`
- `WinLangdb!SetUserLanguages` at `0x180037e25`
- `WinLangdb!SetUserLanguages` at `0x180037f82`
- `Bcp47Langs!ClearUserDisplayLanguageOverride` at `0x180037cb0`
- `Bcp47Langs!ClearUserDisplayLanguageOverride` at `0x180037cb0`
- `Bcp47Langs!GetUserLanguages` at `0x180037cf2`
- `Bcp47Langs!GetUserLanguages` at `0x180037cf2`
- `Bcp47Langs!GetUserLocaleFromLanguageProfileOptOut` at `0x180037b7a`
- `Bcp47Langs!GetUserLocaleFromLanguageProfileOptOut` at `0x180037b7a`
- `Bcp47Langs!GetAppropriateUserLocaleForUserLanguages` at `0x180037bc2`
- `Bcp47Langs!GetAppropriateUserLocaleForUserLanguages` at `0x180037bc2`
- `CoreGlobConfig!SetDisplayLanguageCore` at `0x180037b33`
- `CoreGlobConfig!SetDisplayLanguageCore` at `0x180037b33`
- `CoreGlobConfig!SyncLanguageDataToCloudDirect` at `0x180037c73`
- `CoreGlobConfig!SyncLanguageDataToCloudDirect` at `0x180038005`
- `CoreGlobConfig!SyncLanguageDataToCloudDirect` at `0x180037c73`
- `CoreGlobConfig!SyncLanguageDataToCloudDirect` at `0x180038005`

## string_xrefs

- `0x180037b4a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180037b8f`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180037c0e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180037c3d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180037c8c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180037cc5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180037d09`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180037e40`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180037f99`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x18003801a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall SetDisplayLanguage(const wchar_t *a1, __int64 a2)
{
  const wchar_t *v3; // rbx
  const wchar_t *v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  int UserLocaleFromLanguageProfileOptOut; // eax
  HSTRING v11; // rcx
  int AppropriateUserLocaleForUserLanguages; // eax
  unsigned int v13; // ebx
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  PCWSTR StringRawBuffer; // rax
  int updated; // eax
  int v18; // eax
  int v19; // eax
  int UserLanguages; // eax
  unsigned int v21; // edi
  char v22; // cl
  PCWSTR v23; // rax
  __int64 v24; // r15
  __int64 v25; // r8
  const wchar_t *v26; // rsi
  wchar_t *v27; // r14
  wchar_t *i; // rdi
  __int64 v29; // rax
  size_t v30; // r8
  const wchar_t *v31; // rcx
  int v32; // eax
  unsigned int v33; // ebx
  char v34; // al
  wchar_t *v35; // r14
  wchar_t *j; // rsi
  int v37; // r9d
  __int128 *p_Src; // rax
  __int64 v39; // rax
  int v40; // eax
  char v41; // al
  int v42; // eax
  char v43; // al
  int v44; // [rsp+20h] [rbp-D8h]
  int v45; // [rsp+20h] [rbp-D8h]
  _QWORD v46[2]; // [rsp+30h] [rbp-C8h] BYREF
  int v47[4]; // [rsp+40h] [rbp-B8h] BYREF
  __int128 v48; // [rsp+50h] [rbp-A8h]
  char v49[8]; // [rsp+60h] [rbp-98h] BYREF
  HSTRING string; // [rsp+68h] [rbp-90h] BYREF
  wchar_t *S1; // [rsp+70h] [rbp-88h] BYREF
  wchar_t *v52; // [rsp+78h] [rbp-80h]
  __int128 Src; // [rsp+88h] [rbp-70h] BYREF
  __int128 v54; // [rsp+98h] [rbp-60h]
  _QWORD v55[4]; // [rsp+A8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v3 = a1;
  v4 = a1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    v4 = *(const wchar_t **)a1;
  v46[0] = v4;
  v46[1] = *((_QWORD *)a1 + 2);
  bcp47::ConvertToMuiForm(v55, v46);
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku(v5) )
  {
    v6 = v55;
    if ( v55[3] > 7u )
      v6 = (_QWORD *)v55[0];
    v7 = SetDisplayLanguageCore(v6, 0);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E4,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        (const char *)(unsigned int)v7,
        v44);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v55);
      return v8;
    }
    v49[0] = 0;
    UserLocaleFromLanguageProfileOptOut = GetUserLocaleFromLanguageProfileOptOut(v49);
    v11 = (HSTRING)retaddr;
    if ( UserLocaleFromLanguageProfileOptOut < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        (const char *)(unsigned int)UserLocaleFromLanguageProfileOptOut,
        v44);
    if ( !v49[0] )
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      AppropriateUserLocaleForUserLanguages = GetAppropriateUserLocaleForUserLanguages(&string);
      v13 = AppropriateUserLocaleForUserLanguages;
      if ( AppropriateUserLocaleForUserLanguages < 0 )
      {
        v14 = (unsigned int)AppropriateUserLocaleForUserLanguages;
        v15 = 455;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
          (const char *)v14,
          v44);
        if ( string )
          WindowsDeleteString(string);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E5,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
          (const char *)v13,
          v45);
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v55);
        return v13;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      updated = NlsUpdateLocale(StringRawBuffer, 3);
      v13 = updated;
      if ( updated > 0 )
        v13 = (unsigned __int16)updated | 0x80070000;
      if ( (v13 & 0x80000000) != 0 )
      {
        v14 = v13;
        v15 = 456;
        goto LABEL_17;
      }
      v11 = string;
      if ( string )
        WindowsDeleteString(string);
    }
    v18 = SyncLanguageDataToCloudDirect(v11);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1E6,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        (const char *)(unsigned int)v18,
        v44);
LABEL_70:
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v55);
    return 0;
  }
  raii::ImpersonateLoggedOnUser(v49, a2);
  v19 = ClearUserDisplayLanguageOverride();
  if ( v19 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      (const char *)(unsigned int)v19,
      v44);
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  UserLanguages = GetUserLanguages(59, &string);
  v21 = UserLanguages;
  if ( UserLanguages >= 0 )
  {
    v23 = WindowsGetStringRawBuffer(string, 0);
    Src = 0;
    v54 = 0;
    v24 = -1;
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    std::wstring::_Construct<1,unsigned short const *>(&Src, v23, v25);
    WstringContainerFromDelimitedString<std::vector<std::wstring>>(&S1, &Src);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(&Src);
    if ( *((_QWORD *)v3 + 3) <= 7u )
      v26 = v3;
    else
      v26 = *(const wchar_t **)v3;
    v27 = v52;
    for ( i = S1; i != v27; i += 16 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v26[v29] );
      v30 = *((_QWORD *)i + 2);
      v31 = *((_QWORD *)i + 3) <= 7u ? i : *(const wchar_t **)i;
      if ( v30 == v29 && (!v30 || !wmemcmp(v31, v26, v30)) )
        break;
    }
    if ( i == S1 )
    {
      v32 = SetUserLanguages(59, string);
      v33 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F4,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
          (const char *)(unsigned int)v32,
          v44);
        std::vector<std::wstring>::_Tidy(&S1);
        WindowsDeleteString(string);
        string = 0;
        v34 = v49[0];
        v49[0] = 0;
        if ( v34 )
          RevertToSelf();
LABEL_50:
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v55);
        return v33;
      }
    }
    else
    {
      v35 = v52;
      if ( i != v52 )
      {
        for ( j = i + 16; j != v35; j += 16 )
        {
          std::wstring::operator=(i, j);
          i += 16;
        }
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v52 - 16);
        v52 -= 16;
        if ( *((_QWORD *)v3 + 3) > 7u )
          v3 = *(const wchar_t **)v3;
        *(_OWORD *)v47 = 0;
        v48 = 0;
        do
          ++v24;
        while ( v3[v24] );
        std::wstring::_Construct<1,unsigned short const *>(v47, v3, v24);
        std::vector<std::wstring>::insert((unsigned int)&S1, (unsigned int)v46, (_DWORD)S1, v37, (__int64)v47);
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v47);
        DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(&Src);
        p_Src = &Src;
        if ( *((_QWORD *)&v54 + 1) > 7u )
          p_Src = (__int128 *)Src;
        v46[0] = p_Src;
        v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v47, v46);
        v40 = SetUserLanguages(59, *(_QWORD *)(v39 + 24));
        v33 = v40;
        if ( v40 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1FB,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
            (const char *)(unsigned int)v40,
            v44);
          std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(&Src);
          std::vector<std::wstring>::_Tidy(&S1);
          WindowsDeleteString(string);
          string = 0;
          v41 = v49[0];
          v49[0] = 0;
          if ( v41 )
            RevertToSelf();
          goto LABEL_50;
        }
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(&Src);
      }
    }
    v42 = ((__int64 (*)(void))SyncLanguageDataToCloudDirect)();
    if ( v42 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1FF,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        (const char *)(unsigned int)v42,
        v44);
    std::vector<std::wstring>::_Tidy(&S1);
    WindowsDeleteString(string);
    string = 0;
    v43 = v49[0];
    v49[0] = 0;
    if ( v43 )
      RevertToSelf();
    goto LABEL_70;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1EE,
    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
    (const char *)(unsigned int)UserLanguages,
    v44);
  WindowsDeleteString(string);
  string = 0;
  v22 = v49[0];
  v49[0] = 0;
  if ( v22 )
    RevertToSelf();
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v55);
  return v21;
}

```

## disassembly

```asm
0x180037aac  mov     [rsp+arg_10], rbx
0x180037ab1  push    rsi
0x180037ab2  push    rdi
0x180037ab3  push    r12
0x180037ab5  push    r14
0x180037ab7  push    r15
0x180037ab9  sub     rsp, 0D0h
0x180037ac0  mov     rax, cs:__security_cookie
0x180037ac7  xor     rax, rsp
0x180037aca  mov     [rsp+0F8h+var_30], rax
0x180037ad2  mov     rdi, rdx
0x180037ad5  mov     rbx, rcx
0x180037ad8  xor     r12d, r12d
0x180037adb  mov     rax, rcx
0x180037ade  cmp     qword ptr [rcx+18h], 7
0x180037ae3  jbe     short loc_180037AE8
0x180037ae5  mov     rax, [rcx]
0x180037ae8  mov     [rsp+0F8h+var_C8], rax
0x180037aed  mov     rax, [rcx+10h]
0x180037af1  mov     [rsp+0F8h+var_C0], rax
0x180037af6  lea     rdx, [rsp+0F8h+var_C8]
0x180037afb  lea     rcx, [rsp+0F8h+var_50]
0x180037b03  call    ?ConvertToMuiForm@bcp47@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@3@@Z; bcp47::ConvertToMuiForm(std::basic_string_view<ushort,details::case_insensitive_wchar_traits> const &)
0x180037b08  nop
0x180037b09  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180037b0f  test    al, al
0x180037b11  jz      loc_180037CA2
0x180037b17  lea     rcx, [rsp+0F8h+var_50]
0x180037b1f  cmp     [rsp+0F8h+var_38], 7
0x180037b28  cmova   rcx, [rsp+0F8h+var_50]
0x180037b31  xor     edx, edx
0x180037b33  call    cs:__imp_SetDisplayLanguageCore
0x180037b39  mov     ebx, eax
0x180037b3b  test    eax, eax
0x180037b3d  jns     short loc_180037B70
0x180037b3f  mov     rcx, [rsp+0F8h]; this
0x180037b47  mov     r9d, eax; char *
0x180037b4a  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180037b51  mov     edx, 1E4h; void *
0x180037b56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037b5b  nop
0x180037b5c  lea     rcx, [rsp+0F8h+var_50]; void *
0x180037b64  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180037b69  mov     eax, ebx
0x180037b6b  jmp     loc_180038070
0x180037b70  mov     [rsp+0F8h+var_98], r12b
0x180037b75  lea     rcx, [rsp+0F8h+var_98]
0x180037b7a  call    cs:__imp_GetUserLocaleFromLanguageProfileOptOut
0x180037b80  mov     rcx, [rsp+0F8h]; this
0x180037b88  test    eax, eax
0x180037b8a  jns     short loc_180037BA0
0x180037b8c  mov     r9d, eax; char *
0x180037b8f  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180037b96  mov     edx, 1C2h; void *
0x180037b9b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037ba0  cmp     [rsp+0F8h+var_98], r12b
0x180037ba5  jnz     loc_180037C73
0x180037bab  mov     [rsp+0F8h+string], r12
0x180037bb0  xor     ecx, ecx; string
0x180037bb2  call    cs:__imp_WindowsDeleteString
0x180037bb8  mov     [rsp+0F8h+string], r12
0x180037bbd  lea     rcx, [rsp+0F8h+string]
0x180037bc2  call    cs:__imp_GetAppropriateUserLocaleForUserLanguages
0x180037bc8  mov     ebx, eax
0x180037bca  test    eax, eax
0x180037bcc  jns     short loc_180037BD8
0x180037bce  mov     r9d, eax
0x180037bd1  mov     edx, 1C7h
0x180037bd6  jmp     short loc_180037C0E
0x180037bd8  xor     edx, edx; length
0x180037bda  mov     rcx, [rsp+0F8h+string]; string
0x180037bdf  call    cs:__imp_WindowsGetStringRawBuffer
0x180037be5  mov     edx, 3
0x180037bea  mov     rcx, rax
0x180037bed  call    cs:__imp_NlsUpdateLocale
0x180037bf3  mov     ebx, eax
0x180037bf5  test    eax, eax
0x180037bf7  jle     short loc_180037C02
0x180037bf9  movzx   ebx, ax
0x180037bfc  or      ebx, 80070000h
0x180037c02  test    ebx, ebx
0x180037c04  jns     short loc_180037C63
0x180037c06  mov     r9d, ebx; char *
0x180037c09  mov     edx, 1C8h; void *
0x180037c0e  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180037c15  mov     rcx, [rsp+0F8h]; this
0x180037c1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037c22  mov     rcx, [rsp+0F8h+string]; string
0x180037c27  test    rcx, rcx
0x180037c2a  jz      short loc_180037C32
0x180037c2c  call    cs:__imp_WindowsDeleteString
0x180037c32  mov     rcx, [rsp+0F8h]; this
0x180037c3a  mov     r9d, ebx; char *
0x180037c3d  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180037c44  mov     edx, 1E5h; void *
0x180037c49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037c4e  nop
0x180037c4f  lea     rcx, [rsp+0F8h+var_50]; void *
0x180037c57  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180037c5c  mov     eax, ebx
0x180037c5e  jmp     loc_180038070
0x180037c63  mov     rcx, [rsp+0F8h+string]; string
0x180037c68  test    rcx, rcx
0x180037c6b  jz      short loc_180037C73
0x180037c6d  call    cs:__imp_WindowsDeleteString
0x180037c73  call    cs:__imp_SyncLanguageDataToCloudDirect
0x180037c79  mov     rcx, [rsp+0F8h]; this
0x180037c81  test    eax, eax
0x180037c83  jns     loc_18003805B
0x180037c89  mov     r9d, eax; char *
0x180037c8c  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180037c93  mov     edx, 1E6h; void *
0x180037c98  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037c9d  jmp     loc_18003805B
0x180037ca2  mov     rdx, rdi
0x180037ca5  lea     rcx, [rsp+0F8h+var_98]
0x180037caa  call    ?ImpersonateLoggedOnUser@raii@@YA?AV?$unique_call@P6AHXZ$1?RevertToSelf@@YAHXZ$00@wil@@PEAX@Z; raii::ImpersonateLoggedOnUser(void *)
0x180037caf  nop
0x180037cb0  call    cs:__imp_ClearUserDisplayLanguageOverride
0x180037cb6  mov     rcx, [rsp+0F8h]; this
0x180037cbe  test    eax, eax
0x180037cc0  jns     short loc_180037CD6
0x180037cc2  mov     r9d, eax; char *
0x180037cc5  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180037ccc  mov     edx, 1EBh; void *
0x180037cd1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037cd6  mov     [rsp+0F8h+string], r12
0x180037cdb  xor     ecx, ecx; string
0x180037cdd  call    cs:__imp_WindowsDeleteString
0x180037ce3  mov     [rsp+0F8h+string], r12
0x180037ce8  mov     ecx, 3Bh ; ';'
0x180037ced  lea     rdx, [rsp+0F8h+string]
0x180037cf2  call    cs:__imp_GetUserLanguages
0x180037cf8  mov     edi, eax
0x180037cfa  test    eax, eax
0x180037cfc  jns     short loc_180037D53
0x180037cfe  mov     rcx, [rsp+0F8h]; this
0x180037d06  mov     r9d, eax; char *
0x180037d09  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180037d10  mov     edx, 1EEh; void *
0x180037d15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037d1a  nop
0x180037d1b  mov     rcx, [rsp+0F8h+string]; string
0x180037d20  call    cs:__imp_WindowsDeleteString
0x180037d26  mov     [rsp+0F8h+string], r12
0x180037d2b  mov     cl, [rsp+0F8h+var_98]
0x180037d2f  mov     [rsp+0F8h+var_98], r12b
0x180037d34  test    cl, cl
0x180037d36  jz      short loc_180037D3F
0x180037d38  call    cs:__imp_RevertToSelf
0x180037d3e  nop
0x180037d3f  lea     rcx, [rsp+0F8h+var_50]; void *
0x180037d47  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180037d4c  mov     eax, edi
0x180037d4e  jmp     loc_180038070
0x180037d53  xor     edx, edx; length
0x180037d55  mov     rcx, [rsp+0F8h+string]; string
0x180037d5a  call    cs:__imp_WindowsGetStringRawBuffer
0x180037d60  xorps   xmm0, xmm0
0x180037d63  movups  [rsp+0F8h+Src], xmm0
0x180037d6b  xorps   xmm1, xmm1
0x180037d6e  movdqu  [rsp+0F8h+var_60], xmm1
0x180037d77  or      r15, 0FFFFFFFFFFFFFFFFh
0x180037d7b  mov     r8, r15
0x180037d7e  inc     r8
0x180037d81  cmp     [rax+r8*2], r12w
0x180037d86  jnz     short loc_180037D7E
0x180037d88  mov     rdx, rax
0x180037d8b  lea     rcx, [rsp+0F8h+Src]
0x180037d93  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180037d98  nop
0x180037d99  lea     rdx, [rsp+0F8h+Src]
0x180037da1  lea     rcx, [rsp+0F8h+S1]
0x180037da6  call    ??$WstringContainerFromDelimitedString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@G@Z; WstringContainerFromDelimitedString<std::vector<std::wstring>>(std::wstring const &,ushort)
0x180037dab  nop
0x180037dac  lea     rcx, [rsp+0F8h+Src]; void *
0x180037db4  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180037db9  nop
0x180037dba  cmp     qword ptr [rbx+18h], 7
0x180037dbf  jbe     short loc_180037DC6
0x180037dc1  mov     rsi, [rbx]
0x180037dc4  jmp     short loc_180037DC9
0x180037dc6  mov     rsi, rbx
0x180037dc9  mov     r14, [rsp+0F8h+var_80]
0x180037dce  mov     rdi, [rsp+0F8h+S1]
0x180037dd3  jmp     short loc_180037E0F
0x180037dd5  mov     rax, r15
0x180037dd8  inc     rax
0x180037ddb  cmp     [rsi+rax*2], r12w
0x180037de0  jnz     short loc_180037DD8
0x180037de2  mov     r8, [rdi+10h]; N
0x180037de6  cmp     qword ptr [rdi+18h], 7
0x180037deb  jbe     short loc_180037DF2
0x180037ded  mov     rcx, [rdi]
0x180037df0  jmp     short loc_180037DF5
0x180037df2  mov     rcx, rdi; S1
0x180037df5  cmp     r8, rax
0x180037df8  jnz     short loc_180037E0B
0x180037dfa  test    r8, r8
0x180037dfd  jz      short loc_180037E14
0x180037dff  mov     rdx, rsi; S2
0x180037e02  call    wmemcmp
0x180037e07  test    eax, eax
0x180037e09  jz      short loc_180037E14
0x180037e0b  add     rdi, 20h ; ' '
0x180037e0f  cmp     rdi, r14
0x180037e12  jnz     short loc_180037DD5
0x180037e14  cmp     rdi, [rsp+0F8h+S1]
0x180037e19  jnz     short loc_180037E95
0x180037e1b  mov     ecx, 3Bh ; ';'
0x180037e20  mov     rdx, [rsp+0F8h+string]
0x180037e25  call    cs:__imp_SetUserLanguages
0x180037e2b  mov     ebx, eax
0x180037e2d  test    eax, eax
0x180037e2f  jns     loc_180038005
0x180037e35  mov     rcx, [rsp+0F8h]; this
0x180037e3d  mov     r9d, eax; char *
0x180037e40  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180037e47  mov     edx, 1F4h; void *
0x180037e4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e51  nop
0x180037e52  lea     rcx, [rsp+0F8h+S1]
0x180037e57  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180037e5c  nop
0x180037e5d  mov     rcx, [rsp+0F8h+string]; string
0x180037e62  call    cs:__imp_WindowsDeleteString
0x180037e68  mov     [rsp+0F8h+string], r12
0x180037e6d  mov     al, [rsp+0F8h+var_98]
0x180037e71  mov     [rsp+0F8h+var_98], r12b
0x180037e76  test    al, al
0x180037e78  jz      short loc_180037E81
0x180037e7a  call    cs:__imp_RevertToSelf
0x180037e80  nop
0x180037e81  lea     rcx, [rsp+0F8h+var_50]; void *
0x180037e89  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180037e8e  mov     eax, ebx
0x180037e90  jmp     loc_180038070
0x180037e95  mov     r14, [rsp+0F8h+var_80]
0x180037e9a  cmp     rdi, r14
0x180037e9d  jz      loc_180038005
0x180037ea3  lea     rsi, [rdi+20h]
0x180037ea7  jmp     short loc_180037EBC
0x180037ea9  mov     rdx, rsi
0x180037eac  mov     rcx, rdi
0x180037eaf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180037eb4  add     rdi, 20h ; ' '
0x180037eb8  add     rsi, 20h ; ' '
0x180037ebc  cmp     rsi, r14
0x180037ebf  jnz     short loc_180037EA9
0x180037ec1  mov     rcx, [rsp+0F8h+var_80]
0x180037ec6  add     rcx, 0FFFFFFFFFFFFFFE0h; void *
0x180037eca  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180037ecf  sub     [rsp+0F8h+var_80], 20h ; ' '
0x180037ed5  cmp     qword ptr [rbx+18h], 7
0x180037eda  jbe     short loc_180037EDF
0x180037edc  mov     rbx, [rbx]
0x180037edf  xorps   xmm0, xmm0
0x180037ee2  movups  xmmword ptr [rsp+0F8h+var_B8], xmm0
0x180037ee7  xorps   xmm1, xmm1
0x180037eea  movdqu  [rsp+0F8h+var_A8], xmm1
0x180037ef0  inc     r15
0x180037ef3  cmp     [rbx+r15*2], r12w
0x180037ef8  jnz     short loc_180037EF0
0x180037efa  mov     r8, r15
0x180037efd  mov     rdx, rbx
0x180037f00  lea     rcx, [rsp+0F8h+var_B8]
0x180037f05  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180037f0a  nop
0x180037f0b  lea     rax, [rsp+0F8h+var_B8]
0x180037f10  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x180037f15  mov     r8, [rsp+0F8h+S1]
0x180037f1a  lea     rdx, [rsp+0F8h+var_C8]
0x180037f1f  lea     rcx, [rsp+0F8h+S1]
0x180037f24  call    ?insert@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,unsigned __int64,std::wstring const &)
0x180037f29  nop
0x180037f2a  lea     rcx, [rsp+0F8h+var_B8]; void *
0x180037f2f  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180037f34  mov     r8, [rsp+0F8h+var_80]
0x180037f39  mov     rdx, [rsp+0F8h+S1]
0x180037f3e  lea     rcx, [rsp+0F8h+Src]; Src
0x180037f46  call    ??$DelimitedStringFromItems@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x180037f4b  lea     rax, [rsp+0F8h+Src]
0x180037f53  cmp     qword ptr [rsp+0F8h+var_60+8], 7
0x180037f5c  cmova   rax, qword ptr [rsp+0F8h+Src]
0x180037f65  mov     [rsp+0F8h+var_C8], rax
0x180037f6a  lea     rdx, [rsp+0F8h+var_C8]
0x180037f6f  lea     rcx, [rsp+0F8h+var_B8]
0x180037f74  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037f79  mov     ecx, 3Bh ; ';'
0x180037f7e  mov     rdx, [rax+18h]
0x180037f82  call    cs:__imp_SetUserLanguages
0x180037f88  mov     ebx, eax
0x180037f8a  test    eax, eax
0x180037f8c  jns     short loc_180037FF8
0x180037f8e  mov     rcx, [rsp+0F8h]; this
0x180037f96  mov     r9d, eax; char *
0x180037f99  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180037fa0  mov     edx, 1FBh; void *
0x180037fa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037faa  lea     rcx, [rsp+0F8h+Src]; void *
  ... truncated ...
```
