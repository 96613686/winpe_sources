# ApplyToDeviceInternationalSettings(ushort const *)

- ea: `0x180042460`
- end: `0x180042a68`
- name: `?ApplyToDeviceInternationalSettings@@YAJPEBG@Z`
- size: `1544`
- prototype: `__int64 __fastcall(wchar_t *S2)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180019b40`
- `0x1800261ac`

## callees

- `0x180003a00`
- `0x1800044b8`
- `0x180009064`
- `0x180009084`
- `0x18000a024`
- `0x180011318`
- `0x180014ed0`
- `0x1800166e0`
- `0x180036e08`
- `0x180036fd4`
- `0x180042460`
- `0x180042a70`
- `0x180042cfc`
- `0x180042d20`
- `0x180042e0c`
- `0x180042fd4`
- `0x18005aac4`
- `0x180060df4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800427cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800427cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800427f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042849`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800427f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042849`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800425b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800425f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042665`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800425b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800425f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042665`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042618`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042618`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800424cf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042559`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004259c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042604`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042677`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004279a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042898`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800428db`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004291e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004295e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004299e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800429f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042a2c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800424cf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042559`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004259c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042604`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042677`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004279a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042898`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800428db`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004291e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004295e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004299e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800429f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042a2c`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180042489`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180042489`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800427ae`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800427ae`
- `ntdll!RtlpSetPreferredUILanguages` at `0x180042746`
- `ntdll!RtlpSetPreferredUILanguages` at `0x180042746`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180042504`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180042504`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x180042626`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x180042835`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x180042626`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x180042835`
- `Bcp47Langs!GetAppropriateUserLocaleForUserLanguages` at `0x1800425c0`
- `Bcp47Langs!GetAppropriateUserLocaleForUserLanguages` at `0x1800425c0`
- `CoreGlobConfig!SetDisplayLanguageCore` at `0x180042525`
- `CoreGlobConfig!SetDisplayLanguageCore` at `0x180042525`

## string_xrefs

- `0x180042a57`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.cpp`
- `0x1800427c5`: `IntlUpdateSystemLocale`
- `0x1800424bd`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x18004253c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x18004257f`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x1800425d7`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x18004264a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042724`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x18004275b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x18004277d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x1800427e2`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042814`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042859`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x18004287b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x1800428be`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042901`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042941`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042981`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x1800429d4`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042a0f`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall ApplyToDeviceInternationalSettings(wchar_t *S2)
{
  BOOL v2; // eax
  const char *v3; // r9
  const char *v4; // r9
  __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  int updated; // eax
  unsigned int v12; // ebx
  int AppropriateUserLocaleForUserLanguages; // eax
  unsigned int v14; // ebx
  PCWSTR StringRawBuffer; // rax
  int v16; // eax
  __int16 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  _WORD *v20; // r8
  __int16 v21; // r9
  unsigned int v22; // ebx
  _WORD *v23; // rcx
  int v24; // eax
  HMODULE LibraryW; // rax
  const char *v26; // r9
  HMODULE v27; // rbx
  FARPROC ProcAddress; // rax
  const char *v29; // r9
  int LastError; // eax
  int v31; // esi
  unsigned int v32; // eax
  __int64 v33; // rdx
  int v34; // eax
  unsigned int v35; // ebx
  int v36; // eax
  unsigned int v37; // ebx
  int NewUserRegHive; // eax
  unsigned int v39; // ebx
  int v40; // eax
  unsigned int v41; // ebx
  unsigned int v42; // ebx
  int v43; // eax
  unsigned int v44; // [rsp+20h] [rbp-128h]
  HSTRING string[2]; // [rsp+28h] [rbp-120h] BYREF
  _QWORD v46[3]; // [rsp+38h] [rbp-110h] BYREF
  unsigned __int64 v47; // [rsp+50h] [rbp-F8h]
  _BYTE v48[176]; // [rsp+60h] [rbp-E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v2 = ImpersonateSelf(SecurityImpersonation);
  try
  {
    if ( !v2 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.cpp",
        v3);
    LOBYTE(v44) = 1;
    if ( !IsCallerLocalSystem() )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
        (const char *)0x80070005LL,
        v44);
      RevertToSelf();
      return 2147942405LL;
    }
    string[0] = (HSTRING)S2;
    v6 = -1;
    do
      ++v6;
    while ( S2[v6] );
    string[1] = (HSTRING)v6;
    bcp47::ConvertToMuiForm(v46, string);
    if ( (unsigned __int8)RtlIsMultiUsersInSessionSku(v7) )
    {
      v8 = v46;
      if ( v47 > 7 )
        v8 = (_QWORD *)v46[0];
      v9 = SetDisplayLanguageCore(v8, 0);
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD9,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
          (const char *)(unsigned int)v9,
          v44);
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
        RevertToSelf();
        return v10;
      }
      updated = UpdatePreferredLanguagesList(S2);
      v12 = updated;
      if ( updated < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
          (const char *)(unsigned int)updated,
          v44);
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
        RevertToSelf();
        return v12;
      }
      string[0] = 0;
      WindowsDeleteString(0);
      string[0] = 0;
      AppropriateUserLocaleForUserLanguages = GetAppropriateUserLocaleForUserLanguages(string);
      v14 = AppropriateUserLocaleForUserLanguages;
      if ( AppropriateUserLocaleForUserLanguages < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE0,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
          (const char *)(unsigned int)AppropriateUserLocaleForUserLanguages,
          v44);
        if ( string[0] )
          WindowsDeleteString(string[0]);
LABEL_17:
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
        RevertToSelf();
        return v14;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
      v16 = NlsUpdateLocale(StringRawBuffer, 3);
      v14 = v16;
      if ( v16 > 0 )
        v14 = (unsigned __int16)v16 | 0x80070000;
      if ( (v14 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE1,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
          (const char *)v14,
          v44);
        if ( string[0] )
          WindowsDeleteString(string[0]);
        goto LABEL_17;
      }
      if ( string[0] )
        WindowsDeleteString(string[0]);
LABEL_63:
      v43 = InvokeStoreAppUpdate();
      if ( v43 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
          (const char *)(unsigned int)v43,
          v44);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
      RevertToSelf();
      return 0;
    }
    LODWORD(string[0]) = 0;
    memset_0(v48, 0, 0xACu);
    v17 = (__int16 *)v46;
    if ( v47 > 7 )
      v17 = (__int16 *)v46[0];
    v18 = 2147483646;
    v19 = 86;
    v20 = v48;
    do
    {
      if ( !v18 )
        break;
      v21 = *v17;
      if ( !*v17 )
        break;
      ++v17;
      *v20++ = v21;
      --v18;
      --v19;
    }
    while ( v19 );
    v22 = v19 == 0 ? 0x8007007A : 0;
    v23 = v20 - 1;
    if ( v19 )
      v23 = v20;
    *v23 = 0;
    if ( !v19 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
        (const char *)v22,
        v44);
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
        (const char *)v22,
        v44);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
      RevertToSelf();
      return v22;
    }
    v24 = RtlpSetPreferredUILanguages(32776, v48, string);
    if ( v24 < 0 )
    {
      v22 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x31,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
              (const char *)(unsigned int)v24,
              v44);
      if ( (v22 & 0x80000000) != 0 )
        goto LABEL_38;
    }
    LibraryW = LoadLibraryW(L"intl.cpl");
    v27 = LibraryW;
    string[0] = (HSTRING)LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "IntlUpdateSystemLocale");
      if ( ProcAddress )
      {
        v32 = ((__int64 (__fastcall *)(wchar_t *, __int64))ProcAddress)(S2, 3);
        if ( v32 )
        {
          v33 = 72;
        }
        else
        {
          v32 = NlsUpdateLocale(S2, 3);
          if ( !v32 )
          {
            FreeLibrary(v27);
            goto LABEL_52;
          }
          v33 = 75;
        }
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)v33,
                      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinterna"
                                    "tionalsettings.cpp",
                      (const char *)v32,
                      v44);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x47,
                      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinterna"
                                    "tionalsettings.cpp",
                      v29);
      }
      v31 = LastError;
      FreeLibrary(v27);
    }
    else
    {
      v31 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x43,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
              v26);
    }
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
        (const char *)(unsigned int)v31,
        v44);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
      RevertToSelf();
      return (unsigned int)v31;
    }
LABEL_52:
    v34 = SetDefaultInputMethod(S2);
    v35 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
        (const char *)(unsigned int)v34,
        v44);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
      RevertToSelf();
      return v35;
    }
    v36 = UpdatePreferredLanguagesList(S2);
    v37 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEB,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
        (const char *)(unsigned int)v36,
        v44);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
      RevertToSelf();
      return v37;
    }
    NewUserRegHive = AdjustPrivilegesToLoadNewUserRegHive();
    v39 = NewUserRegHive;
    if ( NewUserRegHive < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEE,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
        (const char *)(unsigned int)NewUserRegHive,
        v44);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
      RevertToSelf();
      return v39;
    }
    v40 = CopyInternationalSettingsToDefaultUser();
    v41 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
        (const char *)(unsigned int)v40,
        v44);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
      RevertToSelf();
      return v41;
    }
    v42 = SetDefaultSpeechRecognizer(S2);
    if ( (int)(v42 + 0x80000000) >= 0 && v42 != -2147023728 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
        (const char *)v42,
        v44);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v46);
      RevertToSelf();
      return v42;
    }
    goto LABEL_63;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF8,
                           (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicein"
                                         "ternationalsettings.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180042460  push    rbx
0x180042462  push    rsi
0x180042463  push    rdi
0x180042464  push    r14
0x180042466  sub     rsp, 128h
0x18004246d  mov     rax, cs:__security_cookie
0x180042474  xor     rax, rsp
0x180042477  mov     [rsp+148h+var_38], rax
0x18004247f  mov     rdi, rcx
0x180042482  xor     r14d, r14d
0x180042485  lea     ecx, [r14+2]; ImpersonationLevel
0x180042489  call    cs:__imp_ImpersonateSelf
0x18004248f  mov     rcx, [rsp+148h]; this
0x180042497  test    eax, eax
0x180042499  jz      loc_180042A57
0x18004249f  mov     byte ptr [rsp+148h+var_128], 1; int
0x1800424a4  call    ?IsCallerLocalSystem@@YA_NXZ; IsCallerLocalSystem(void)
0x1800424a9  test    al, al
0x1800424ab  jnz     short loc_1800424DC
0x1800424ad  mov     rcx, [rsp+148h]; this
0x1800424b5  mov     ebx, 80070005h
0x1800424ba  mov     r9d, ebx; char *
0x1800424bd  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x1800424c4  mov     edx, 0D2h; void *
0x1800424c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800424ce  nop
0x1800424cf  call    cs:__imp_RevertToSelf
0x1800424d5  mov     eax, ebx
0x1800424d7  jmp     loc_180042A3A
0x1800424dc  mov     [rsp+148h+string], rdi
0x1800424e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800424e5  inc     rax
0x1800424e8  cmp     [rdi+rax*2], r14w
0x1800424ed  jnz     short loc_1800424E5
0x1800424ef  mov     [rsp+148h+var_118], rax
0x1800424f4  lea     rdx, [rsp+148h+string]
0x1800424f9  lea     rcx, [rsp+148h+var_110]
0x1800424fe  call    ?ConvertToMuiForm@bcp47@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@3@@Z; bcp47::ConvertToMuiForm(std::basic_string_view<ushort,details::case_insensitive_wchar_traits> const &)
0x180042503  nop
0x180042504  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18004250a  test    al, al
0x18004250c  jz      loc_18004269D
0x180042512  lea     rcx, [rsp+148h+var_110]
0x180042517  cmp     [rsp+148h+var_F8], 7
0x18004251d  cmova   rcx, [rsp+148h+var_110]
0x180042523  xor     edx, edx
0x180042525  call    cs:__imp_SetDisplayLanguageCore
0x18004252b  mov     ebx, eax
0x18004252d  test    eax, eax
0x18004252f  jns     short loc_180042566
0x180042531  mov     rcx, [rsp+148h]; this
0x180042539  mov     r9d, eax; char *
0x18004253c  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042543  mov     edx, 0D9h; void *
0x180042548  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004254d  nop
0x18004254e  lea     rcx, [rsp+148h+var_110]; void *
0x180042553  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180042558  nop
0x180042559  call    cs:__imp_RevertToSelf
0x18004255f  mov     eax, ebx
0x180042561  jmp     loc_180042A3A
0x180042566  mov     rcx, rdi; S2
0x180042569  call    ?UpdatePreferredLanguagesList@@YAJPEBG@Z; UpdatePreferredLanguagesList(ushort const *)
0x18004256e  mov     ebx, eax
0x180042570  test    eax, eax
0x180042572  jns     short loc_1800425A9
0x180042574  mov     rcx, [rsp+148h]; this
0x18004257c  mov     r9d, eax; char *
0x18004257f  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042586  mov     edx, 0DCh; void *
0x18004258b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042590  nop
0x180042591  lea     rcx, [rsp+148h+var_110]; void *
0x180042596  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004259b  nop
0x18004259c  call    cs:__imp_RevertToSelf
0x1800425a2  mov     eax, ebx
0x1800425a4  jmp     loc_180042A3A
0x1800425a9  mov     [rsp+148h+string], r14
0x1800425ae  xor     ecx, ecx; string
0x1800425b0  call    cs:__imp_WindowsDeleteString
0x1800425b6  mov     [rsp+148h+string], r14
0x1800425bb  lea     rcx, [rsp+148h+string]
0x1800425c0  call    cs:__imp_GetAppropriateUserLocaleForUserLanguages
0x1800425c6  mov     ebx, eax
0x1800425c8  test    eax, eax
0x1800425ca  jns     short loc_180042611
0x1800425cc  mov     rcx, [rsp+148h]; this
0x1800425d4  mov     r9d, eax; char *
0x1800425d7  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x1800425de  mov     edx, 0E0h; void *
0x1800425e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800425e8  mov     rcx, [rsp+148h+string]; string
0x1800425ed  test    rcx, rcx
0x1800425f0  jz      short loc_1800425F9
0x1800425f2  call    cs:__imp_WindowsDeleteString
0x1800425f8  nop
0x1800425f9  lea     rcx, [rsp+148h+var_110]; void *
0x1800425fe  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180042603  nop
0x180042604  call    cs:__imp_RevertToSelf
0x18004260a  mov     eax, ebx
0x18004260c  jmp     loc_180042A3A
0x180042611  xor     edx, edx; length
0x180042613  mov     rcx, [rsp+148h+string]; string
0x180042618  call    cs:__imp_WindowsGetStringRawBuffer
0x18004261e  mov     edx, 3
0x180042623  mov     rcx, rax
0x180042626  call    cs:__imp_NlsUpdateLocale
0x18004262c  mov     ebx, eax
0x18004262e  test    eax, eax
0x180042630  jle     short loc_18004263B
0x180042632  movzx   ebx, ax
0x180042635  or      ebx, 80070000h
0x18004263b  test    ebx, ebx
0x18004263d  jns     short loc_180042684
0x18004263f  mov     rcx, [rsp+148h]; this
0x180042647  mov     r9d, ebx; char *
0x18004264a  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042651  mov     edx, 0E1h; void *
0x180042656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004265b  mov     rcx, [rsp+148h+string]; string
0x180042660  test    rcx, rcx
0x180042663  jz      short loc_18004266C
0x180042665  call    cs:__imp_WindowsDeleteString
0x18004266b  nop
0x18004266c  lea     rcx, [rsp+148h+var_110]; void *
0x180042671  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180042676  nop
0x180042677  call    cs:__imp_RevertToSelf
0x18004267d  mov     eax, ebx
0x18004267f  jmp     loc_180042A3A
0x180042684  mov     rcx, [rsp+148h+string]; string
0x180042689  test    rcx, rcx
0x18004268c  jz      loc_1800429FB
0x180042692  call    cs:__imp_WindowsDeleteString
0x180042698  jmp     loc_1800429FB
0x18004269d  mov     dword ptr [rsp+148h+string], r14d
0x1800426a2  xor     edx, edx; Val
0x1800426a4  mov     r8d, 0ACh; Size
0x1800426aa  lea     rcx, [rsp+148h+var_E8]; void *
0x1800426af  call    memset_0
0x1800426b4  lea     rax, [rsp+148h+var_110]
0x1800426b9  cmp     [rsp+148h+var_F8], 7
0x1800426bf  cmova   rax, [rsp+148h+var_110]
0x1800426c5  mov     ecx, 7FFFFFFEh
0x1800426ca  mov     edx, 56h ; 'V'
0x1800426cf  lea     r8, [rsp+148h+var_E8]
0x1800426d4  test    rcx, rcx
0x1800426d7  jz      short loc_1800426F8
0x1800426d9  movzx   r9d, word ptr [rax]
0x1800426dd  test    r9w, r9w
0x1800426e1  jz      short loc_1800426F8
0x1800426e3  add     rax, 2
0x1800426e7  mov     [r8], r9w
0x1800426eb  add     r8, 2
0x1800426ef  dec     rcx
0x1800426f2  sub     rdx, 1
0x1800426f6  jnz     short loc_1800426D4
0x1800426f8  mov     rax, rdx
0x1800426fb  neg     rax
0x1800426fe  sbb     ebx, ebx
0x180042700  not     ebx
0x180042702  and     ebx, 8007007Ah
0x180042708  lea     rcx, [r8-2]
0x18004270c  test    rdx, rdx
0x18004270f  cmovnz  rcx, r8
0x180042713  mov     [rcx], r14w
0x180042717  jnz     short loc_180042737
0x180042719  mov     rcx, [rsp+148h]; this
0x180042721  mov     r9d, ebx; char *
0x180042724  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x18004272b  mov     edx, 2Dh ; '-'; void *
0x180042730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042735  jmp     short loc_180042772
0x180042737  lea     r8, [rsp+148h+string]
0x18004273c  lea     rdx, [rsp+148h+var_E8]
0x180042741  mov     ecx, 8008h
0x180042746  call    cs:__imp_RtlpSetPreferredUILanguages
0x18004274c  test    eax, eax
0x18004274e  jns     short loc_1800427A7
0x180042750  mov     rcx, [rsp+148h]; this
0x180042758  mov     r9d, eax; char *
0x18004275b  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042762  mov     edx, 31h ; '1'; void *
0x180042767  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004276c  mov     ebx, eax
0x18004276e  test    eax, eax
0x180042770  jns     short loc_1800427A7
0x180042772  mov     rcx, [rsp+148h]; this
0x18004277a  mov     r9d, ebx; char *
0x18004277d  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042784  mov     edx, 0E5h; void *
0x180042789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004278e  nop
0x18004278f  lea     rcx, [rsp+148h+var_110]; void *
0x180042794  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180042799  nop
0x18004279a  call    cs:__imp_RevertToSelf
0x1800427a0  mov     eax, ebx
0x1800427a2  jmp     loc_180042A3A
0x1800427a7  lea     rcx, LibFileName; "intl.cpl"
0x1800427ae  call    cs:__imp_LoadLibraryW
0x1800427b4  mov     rbx, rax
0x1800427b7  mov     [rsp+148h+string], rax
0x1800427bc  test    rax, rax
0x1800427bf  jz      loc_180042851
0x1800427c5  lea     rdx, aIntlupdatesyst; "IntlUpdateSystemLocale"
0x1800427cc  mov     rcx, rax; hModule
0x1800427cf  call    cs:__imp_GetProcAddress
0x1800427d5  test    rax, rax
0x1800427d8  jnz     short loc_1800427FE
0x1800427da  mov     rcx, [rsp+148h]; this
0x1800427e2  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x1800427e9  lea     edx, [rax+47h]; void *
0x1800427ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800427f1  mov     esi, eax
0x1800427f3  mov     rcx, rbx; hLibModule
0x1800427f6  call    cs:__imp_FreeLibrary
0x1800427fc  jmp     short loc_18004286C
0x1800427fe  mov     edx, 3
0x180042803  mov     rcx, rdi
0x180042806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004280b  test    eax, eax
0x18004280d  jz      short loc_18004282D
0x18004280f  mov     edx, 48h ; 'H'; void *
0x180042814  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x18004281b  mov     r9d, eax; char *
0x18004281e  mov     rcx, [rsp+148h]; this
0x180042826  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004282b  jmp     short loc_1800427F1
0x18004282d  mov     edx, 3
0x180042832  mov     rcx, rdi
0x180042835  call    cs:__imp_NlsUpdateLocale
0x18004283b  test    eax, eax
0x18004283d  jz      short loc_180042846
0x18004283f  mov     edx, 4Bh ; 'K'
0x180042844  jmp     short loc_180042814
0x180042846  mov     rcx, rbx; hLibModule
0x180042849  call    cs:__imp_FreeLibrary
0x18004284f  jmp     short loc_1800428A5
0x180042851  mov     rcx, [rsp+148h]; this
0x180042859  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042860  mov     edx, 43h ; 'C'; void *
0x180042865  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004286a  mov     esi, eax
0x18004286c  test    esi, esi
0x18004286e  jns     short loc_1800428A5
0x180042870  mov     rcx, [rsp+148h]; this
0x180042878  mov     r9d, esi; char *
0x18004287b  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042882  mov     edx, 0E8h; void *
0x180042887  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004288c  nop
0x18004288d  lea     rcx, [rsp+148h+var_110]; void *
0x180042892  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180042897  nop
0x180042898  call    cs:__imp_RevertToSelf
0x18004289e  mov     eax, esi
0x1800428a0  jmp     loc_180042A3A
0x1800428a5  mov     rcx, rdi; unsigned __int16 *
0x1800428a8  call    ?SetDefaultInputMethod@@YAJPEBG@Z; SetDefaultInputMethod(ushort const *)
0x1800428ad  mov     ebx, eax
0x1800428af  test    eax, eax
0x1800428b1  jns     short loc_1800428E8
0x1800428b3  mov     rcx, [rsp+148h]; this
0x1800428bb  mov     r9d, eax; char *
0x1800428be  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x1800428c5  mov     edx, 0EAh; void *
0x1800428ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800428cf  nop
0x1800428d0  lea     rcx, [rsp+148h+var_110]; void *
0x1800428d5  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x1800428da  nop
0x1800428db  call    cs:__imp_RevertToSelf
0x1800428e1  mov     eax, ebx
0x1800428e3  jmp     loc_180042A3A
0x1800428e8  mov     rcx, rdi; S2
0x1800428eb  call    ?UpdatePreferredLanguagesList@@YAJPEBG@Z; UpdatePreferredLanguagesList(ushort const *)
0x1800428f0  mov     ebx, eax
0x1800428f2  test    eax, eax
0x1800428f4  jns     short loc_18004292B
0x1800428f6  mov     rcx, [rsp+148h]; this
0x1800428fe  mov     r9d, eax; char *
0x180042901  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042908  mov     edx, 0EBh; void *
0x18004290d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042912  nop
0x180042913  lea     rcx, [rsp+148h+var_110]; void *
0x180042918  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004291d  nop
0x18004291e  call    cs:__imp_RevertToSelf
0x180042924  mov     eax, ebx
0x180042926  jmp     loc_180042A3A
0x18004292b  call    ?AdjustPrivilegesToLoadNewUserRegHive@@YAJXZ; AdjustPrivilegesToLoadNewUserRegHive(void)
0x180042930  mov     ebx, eax
0x180042932  test    eax, eax
0x180042934  jns     short loc_18004296B
0x180042936  mov     rcx, [rsp+148h]; this
  ... truncated ...
```
