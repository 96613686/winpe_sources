# CProcessStateManager::_InitializeUserSid(void)

- ea: `0x180004c2c`
- end: `0x1800054f2`
- name: `?_InitializeUserSid@CProcessStateManager@@AEAAXXZ`
- size: `2246`
- prototype: `void __fastcall(CProcessStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000d2c8`

## callees

- `0x180004b70`
- `0x180004c2c`
- `0x18000be10`
- `0x18000bf8c`
- `0x180011c10`
- `0x18002bc20`
- `0x18004a6b0`
- `0x18006c000`
- `0x18007e6c0`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x180005361`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180005428`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180005361`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180005428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800051ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800051f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800051ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800051f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800051dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000520b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800051dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000520b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004fa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004fa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800052f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800052f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000503d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000540c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005440`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000503d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000540c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005440`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004cbd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800050a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800050f3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000514f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004cbd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800050a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800050f3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000514f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004da7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005009`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004da7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005009`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004e02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005329`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004e02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005329`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004f71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000502e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004f71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000502e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004f5d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004f5d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004f2c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004f2c`

## string_xrefs

- `0x180004fc6`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`
- `0x180004fa9`: `Accessibility`
- `0x180004f51`: `SelectedUserSID`
- `0x18000526f`: `SelectedUserSID`
- `0x180004df8`: `LoggedOnUserSID`
- `0x18000531f`: `LoggedOnUserSID`
- `0x180005216`: `LastLoggedOnUserSID`
- `0x1800053b1`: `UserSID`

## pseudocode

```c
void __fastcall CProcessStateManager::_InitializeUserSid(CProcessStateManager *this)
{
  CProcessStateManager *v1; // r13
  BOOL v2; // ebx
  WCHAR *v3; // r14
  LSTATUS ValueW; // eax
  signed int v5; // ecx
  signed int v6; // r15d
  CredProvPolicy *v7; // rcx
  CredProvPolicy *v8; // rcx
  ULONG SessionId; // ebx
  LSTATUS v10; // eax
  __int64 v11; // rdx
  bool v12; // sf
  signed int v13; // ebx
  LSTATUS v14; // eax
  HKEY v15; // rsi
  BYTE *v16; // rdi
  LSTATUS v17; // eax
  signed int v18; // ebx
  HKEY v19; // rcx
  HSTRING *v20; // r12
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // rsi
  PCWSTR StringRawBuffer; // rax
  const BYTE *v25; // rbx
  HSTRING v26; // rcx
  PCWSTR v27; // rax
  LSTATUS v28; // eax
  bool v29; // sf
  HKEY v30; // rcx
  LSTATUS v31; // eax
  bool v32; // sf
  LSTATUS v33; // eax
  bool v34; // sf
  bool v35; // bl
  LSTATUS v36; // eax
  LSTATUS v37; // eax
  __int64 v38; // rsi
  DWORD v39; // eax
  DWORD v40; // r12d
  WCHAR *v41; // rax
  WCHAR *v42; // rsi
  DWORD v43; // eax
  DWORD v44; // r13d
  __int64 v45; // rax
  signed int v46; // eax
  signed int v47; // eax
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  DWORD pdwType[2]; // [rsp+70h] [rbp-90h] BYREF
  BYTE *v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  WCHAR SubKey[8]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v58[256]; // [rsp+A0h] [rbp-60h] BYREF

  v1 = this;
  *(_QWORD *)pdwType = this;
  v2 = 0;
  v3 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  Type = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\UserSwitch",
             L"Enabled",
             0x10000012u,
             &Type,
             &cbData,
             &pcbData);
  v5 = ValueW;
  LOWORD(v6) = 13;
  if ( !ValueW )
  {
    LOWORD(v5) = 13;
    if ( Type == 4 )
    {
      if ( cbData <= 1 )
      {
        v5 = 0;
        v2 = cbData == 1;
        goto LABEL_5;
      }
    }
    else if ( pcbData == 4 && (unsigned __int16)(cbData - 48) <= 1u )
    {
      v2 = (_WORD)cbData == 49;
      v5 = 0;
      goto LABEL_5;
    }
    goto LABEL_4;
  }
  if ( ValueW == 234 )
  {
    LOWORD(v5) = 13;
    goto LABEL_4;
  }
  if ( ValueW > 0 )
LABEL_4:
    v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_5:
  if ( v5 >= 0 && v2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
      &v54,
      49,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\UserSwitch",
      L"UserSID");
    *((_BYTE *)v1 + 121) = 0;
    *((_DWORD *)v1 + 128) |= 0x20u;
    v3 = (WCHAR *)v54;
    goto LABEL_24;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_FederatedAADWebSignInSV2>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_FederatedAADWebSignInSV2>::GetImpl'::`2'::impl);
  if ( !CredProvPolicy::IsPrimaryUserSet(v7) && CredProvPolicy::IsPrimaryUserForEduEnvironment(v8) )
    goto LABEL_47;
  hKey = 0;
  SessionId = NtCurrentPeb()->SessionId;
  phkResult = 0;
  v10 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
          0,
          8u,
          &phkResult);
  v12 = v10 < 0;
  if ( v10 > 0 )
    v12 = 1;
  if ( !v12 )
  {
    v13 = StringCchPrintfW(SubKey, 8u, L"%d", SessionId);
    if ( v13 >= 0 )
    {
      v14 = RegOpenKeyExW(phkResult, SubKey, 0, 1u, &hKey);
      v13 = v14;
      if ( v14 > 0 )
        v13 = (unsigned __int16)v14 | 0x80070000;
    }
    RegCloseKey(phkResult);
    if ( v13 >= 0 )
    {
      v15 = hKey;
      v16 = 0;
      Type = 0;
      cbData = 0;
      v17 = RegQueryValueExW(hKey, L"LoggedOnUserSID", 0, &Type, 0, &cbData);
      v18 = v17;
      if ( v17 > 0 )
        v18 = (unsigned __int16)v17 | 0x80070000;
      if ( v18 < 0 )
        goto LABEL_18;
      if ( Type - 1 <= 1 && cbData && (cbData & 1) == 0 )
      {
        v16 = (BYTE *)CoTaskMemAlloc(cbData);
        if ( !v16 )
        {
          v18 = -2147024882;
          goto LABEL_18;
        }
        v37 = RegQueryValueExW(v15, L"LoggedOnUserSID", 0, &Type, v16, &cbData);
        v18 = v37;
        if ( v37 > 0 )
          v18 = (unsigned __int16)v37 | 0x80070000;
        if ( v18 < 0 )
        {
LABEL_18:
          CoTaskMemFree(v16);
          *((_BYTE *)v1 + 440) = v18 >= 0;
          if ( v3 && *v3 )
            goto LABEL_20;
          goto LABEL_68;
        }
        v38 = (cbData >> 1) - 1;
        if ( Type == 2 )
        {
          v39 = ExpandEnvironmentStringsW((LPCWSTR)v16, 0, 0);
          v40 = v39;
          if ( v39 )
          {
            v41 = (WCHAR *)CoTaskMemAlloc(2LL * v39);
            v42 = v41;
            v18 = 0;
            if ( !v41 )
            {
              v18 = -2147024882;
              goto LABEL_18;
            }
            v43 = ExpandEnvironmentStringsW((LPCWSTR)v16, v41, v40);
            v44 = v43;
            if ( !v43 || v43 > v40 )
            {
              v18 = -2147024774;
              CoTaskMemFree(v42);
              v1 = *(CProcessStateManager **)pdwType;
              goto LABEL_18;
            }
            CoTaskMemFree(v16);
            v16 = (BYTE *)v42;
            v38 = v44 - 1;
            v1 = *(CProcessStateManager **)pdwType;
          }
        }
        if ( !*(_WORD *)&v16[2 * v38] )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
          if ( !v16 || (v45 = (unsigned int)(v38 + 1), (_DWORD)v38 == -1) )
          {
            v3 = (WCHAR *)v54;
          }
          else
          {
            v3 = (WCHAR *)v16;
            v54 = v16;
            v56 = (unsigned int)v45;
            v55 = v45 - 1;
            *(_WORD *)&v16[2 * (unsigned int)v45 - 2] = 0;
          }
          v16 = 0;
          goto LABEL_18;
        }
      }
      v18 = -2147024883;
      goto LABEL_18;
    }
  }
LABEL_68:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
    &v54,
    v11,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
    L"LastLoggedOnUserSID");
  v3 = (WCHAR *)v54;
LABEL_20:
  if ( !v3 || !*v3 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
      &v54,
      v11,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
      L"SelectedUserSID");
    v3 = (WCHAR *)v54;
  }
  v19 = hKey;
  hKey = 0;
  if ( v19 )
    RegCloseKey(v19);
LABEL_24:
  if ( v3 && *v3 )
  {
    v20 = (HSTRING *)((char *)v1 + 424);
    v21 = -1;
    v22 = -1;
    do
      ++v22;
    while ( v3[v22] );
    if ( v22 <= 0xFFFFFFFF )
    {
      WindowsDeleteString(*v20);
      *v20 = 0;
      WindowsCreateString(v3, v22, (HSTRING *)v1 + 53);
    }
    v23 = -1;
    do
      ++v23;
    while ( v3[v23] );
    if ( v23 <= 0xFFFFFFFF )
    {
      WindowsDeleteString(*((HSTRING *)v1 + 54));
      *((_QWORD *)v1 + 54) = 0;
      WindowsCreateString(v3, v23, (HSTRING *)v1 + 54);
    }
    StringRawBuffer = WindowsGetStringRawBuffer(*v20, 0);
    v25 = (const BYTE *)StringRawBuffer;
    do
      ++v21;
    while ( StringRawBuffer[v21] );
    if ( v21 < 0x7FFFFFFF )
    {
      hKey = 0;
      if ( !RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
              0,
              0,
              0,
              2u,
              0,
              &hKey,
              0) )
      {
        RegSetValueExW(hKey, L"SelectedUserSID", 0, 1u, v25, 2 * v21 + 2);
        if ( hKey != HKEY_LOCAL_MACHINE )
          RegCloseKey(hKey);
      }
    }
    v26 = *v20;
    if ( *v20 )
    {
      *((_DWORD *)v1 + 111) = 1;
      *((_DWORD *)v1 + 112) = 100;
      *((_BYTE *)v1 + 452) = 1;
      v27 = WindowsGetStringRawBuffer(v26, 0);
      if ( (int)StringCchPrintfW(
                  v58,
                  0xFFu,
                  L"%s\\%s\\%s\\%s",
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                  v27,
                  L"AnyoneRead",
                  L"Accessibility") >= 0 )
      {
        hKey = 0;
        v28 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v58, 0, 0x20019u, &hKey);
        v29 = v28 < 0;
        if ( v28 > 0 )
          v29 = 1;
        if ( v29 )
          goto LABEL_45;
        pcbData = 0;
        LODWORD(phkResult) = 4;
        v31 = RegGetValueW(hKey, 0, L"CaretWidth", 0x10u, 0, &pcbData, (LPDWORD)&phkResult);
        v32 = v31 < 0;
        if ( v31 > 0 )
          v32 = 1;
        if ( !v32 )
        {
          v46 = pcbData;
          *((_DWORD *)v1 + 111) = pcbData;
          if ( v46 < 1 )
            *((_DWORD *)v1 + 111) = 1;
        }
        cbData = 0;
        LODWORD(phkResult) = 4;
        v33 = RegGetValueW(hKey, 0, L"TextScaleFactor", 0x10u, 0, &cbData, (LPDWORD)&phkResult);
        v34 = v33 < 0;
        if ( v33 > 0 )
          v34 = 1;
        if ( !v34 )
        {
          v47 = cbData;
          *((_DWORD *)v1 + 112) = cbData;
          if ( v47 >= 100 )
          {
            if ( v47 > 225 )
              *((_DWORD *)v1 + 112) = 225;
          }
          else
          {
            *((_DWORD *)v1 + 112) = 100;
          }
        }
        v35 = 0;
        pdwType[0] = 0;
        LODWORD(phkResult) = 4;
        v36 = RegGetValueW(hKey, 0, L"Transparency", 0x10000012u, pdwType, &Type, (LPDWORD)&phkResult);
        if ( v36 )
        {
          if ( v36 == 234 )
            goto LABEL_59;
          v6 = v36;
          if ( v36 > 0 )
            goto LABEL_59;
        }
        else if ( pdwType[0] == 4 )
        {
          if ( Type > 1 )
          {
LABEL_59:
            v6 = (unsigned __int16)v6 | 0x80070000;
            goto LABEL_60;
          }
          v6 = 0;
          v35 = Type == 1;
        }
        else
        {
          if ( (_DWORD)phkResult != 4 || (unsigned __int16)(Type - 48) > 1u )
            goto LABEL_59;
          v35 = (_WORD)Type == 49;
          v6 = 0;
        }
LABEL_60:
        if ( v6 >= 0 )
          *((_BYTE *)v1 + 452) = v35;
LABEL_45:
        v30 = hKey;
        hKey = 0;
        if ( v30 )
          RegCloseKey(v30);
      }
    }
  }
LABEL_47:
  if ( v3 )
    CoTaskMemFree(v3);
}

```

## disassembly

```asm
0x180004c2c  push    rbp
0x180004c2e  push    rbx
0x180004c2f  push    rsi
0x180004c30  push    rdi
0x180004c31  push    r12
0x180004c33  push    r13
0x180004c35  push    r14
0x180004c37  push    r15
0x180004c39  lea     rbp, [rsp-1B8h]
0x180004c41  sub     rsp, 2B8h
0x180004c48  mov     rax, cs:__security_cookie
0x180004c4f  xor     rax, rsp
0x180004c52  mov     [rbp+1F0h+var_50], rax
0x180004c59  mov     r13, rcx
0x180004c5c  mov     qword ptr [rsp+2F0h+var_280], rcx
0x180004c61  xor     r12d, r12d
0x180004c64  mov     ebx, r12d
0x180004c67  mov     r14d, r12d
0x180004c6a  mov     [rsp+2F0h+var_278], r12
0x180004c6f  mov     [rbp+1F0h+var_270], r12
0x180004c73  mov     [rbp+1F0h+var_268], r12
0x180004c77  mov     [rsp+2F0h+Type], r12d
0x180004c7c  mov     [rsp+2F0h+var_290], 4
0x180004c84  lea     rax, [rsp+2F0h+var_290]
0x180004c89  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180004c8e  lea     rax, [rsp+2F0h+cbData]
0x180004c93  mov     [rsp+2F0h+pvData], rax; pvData
0x180004c98  lea     rax, [rsp+2F0h+Type]
0x180004c9d  mov     [rsp+2F0h+pdwType], rax; pdwType
0x180004ca2  mov     r9d, 10000012h; dwFlags
0x180004ca8  lea     r8, aEnabled; "Enabled"
0x180004caf  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004cb6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180004cbd  call    cs:__imp_RegGetValueW
0x180004cc3  mov     ecx, eax
0x180004cc5  lea     edx, [r12+31h]
0x180004cca  lea     esi, [rdx-30h]
0x180004ccd  lea     r15d, [r12+0Dh]
0x180004cd2  test    eax, eax
0x180004cd4  jz      loc_180005187
0x180004cda  cmp     eax, 0EAh
0x180004cdf  jz      loc_1800053A1
0x180004ce5  test    eax, eax
0x180004ce7  jle     short loc_180004CF2
0x180004ce9  movzx   ecx, cx
0x180004cec  or      ecx, 80070000h
0x180004cf2  test    ecx, ecx
0x180004cf4  jns     loc_1800053A9
0x180004cfa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FederatedAADWebSignInSV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FederatedAADWebSignInSV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FederatedAADWebSignInSV2> `wil::Feature<__WilFeatureTraits_Feature_FederatedAADWebSignInSV2>::GetImpl(void)'::`2'::impl
0x180004d01  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_FederatedAADWebSignInSV2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FederatedAADWebSignInSV2>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180004d06  call    ?IsPrimaryUserSet@CredProvPolicy@@YA_NXZ; CredProvPolicy::IsPrimaryUserSet(void)
0x180004d0b  test    al, al
0x180004d0d  jnz     short loc_180004D1C
0x180004d0f  call    ?IsPrimaryUserForEduEnvironment@CredProvPolicy@@YA_NXZ; CredProvPolicy::IsPrimaryUserForEduEnvironment(void)
0x180004d14  test    al, al
0x180004d16  jnz     loc_180005035
0x180004d1c  mov     [rsp+2F0h+hKey], r12
0x180004d21  mov     rax, gs:60h
0x180004d2a  mov     ebx, [rax+2C0h]
0x180004d30  mov     [rsp+2F0h+phkResult], r12
0x180004d35  lea     rax, [rsp+2F0h+phkResult]
0x180004d3a  mov     [rsp+2F0h+pdwType], rax; phkResult
0x180004d3f  mov     edi, 8
0x180004d44  mov     r9d, edi; samDesired
0x180004d47  xor     r8d, r8d; ulOptions
0x180004d4a  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004d51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004d58  call    cs:__imp_RegOpenKeyExW
0x180004d5e  test    eax, eax
0x180004d60  jle     short loc_180004D6C
0x180004d62  movzx   eax, ax
0x180004d65  or      eax, 80070000h
0x180004d6a  test    eax, eax
0x180004d6c  js      loc_180005216
0x180004d72  mov     r9d, ebx
0x180004d75  lea     r8, aD; "%d"
0x180004d7c  mov     rdx, rdi; unsigned __int64
0x180004d7f  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180004d83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004d88  mov     ebx, eax
0x180004d8a  test    eax, eax
0x180004d8c  js      short loc_180004DBC
0x180004d8e  lea     rax, [rsp+2F0h+hKey]
0x180004d93  mov     [rsp+2F0h+pdwType], rax; phkResult
0x180004d98  mov     r9d, esi; samDesired
0x180004d9b  xor     r8d, r8d; ulOptions
0x180004d9e  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180004da2  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x180004da7  call    cs:__imp_RegOpenKeyExW
0x180004dad  mov     ebx, eax
0x180004daf  test    eax, eax
0x180004db1  jle     short loc_180004DBC
0x180004db3  movzx   ebx, ax
0x180004db6  or      ebx, 80070000h
0x180004dbc  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x180004dc1  call    cs:__imp_RegCloseKey
0x180004dc7  test    ebx, ebx
0x180004dc9  js      loc_180005216
0x180004dcf  mov     rsi, [rsp+2F0h+hKey]
0x180004dd4  mov     rdi, r12
0x180004dd7  mov     [rsp+2F0h+Type], r12d
0x180004ddc  mov     [rsp+2F0h+cbData], r12d
0x180004de1  lea     rax, [rsp+2F0h+cbData]
0x180004de6  mov     [rsp+2F0h+pvData], rax; lpcbData
0x180004deb  mov     [rsp+2F0h+pdwType], r12; lpData
0x180004df0  lea     r9, [rsp+2F0h+Type]; lpType
0x180004df5  xor     r8d, r8d; lpReserved
0x180004df8  lea     rdx, ValueName; "LoggedOnUserSID"
0x180004dff  mov     rcx, rsi; hKey
0x180004e02  call    cs:__imp_RegQueryValueExW
0x180004e08  mov     ebx, eax
0x180004e0a  test    eax, eax
0x180004e0c  jle     short loc_180004E17
0x180004e0e  movzx   ebx, ax
0x180004e11  or      ebx, 80070000h
0x180004e17  test    ebx, ebx
0x180004e19  jns     loc_1800053DF
0x180004e1f  mov     rcx, rdi; pv
0x180004e22  call    cs:__imp_CoTaskMemFree
0x180004e28  shr     ebx, 1Fh
0x180004e2b  xor     bl, 1
0x180004e2e  mov     [r13+1B8h], bl
0x180004e35  test    r14, r14
0x180004e38  jz      loc_180005216
0x180004e3e  cmp     [r14], r12w
0x180004e42  jz      loc_180005216
0x180004e48  test    r14, r14
0x180004e4b  jz      loc_18000526F
0x180004e51  cmp     [r14], r12w
0x180004e55  jz      loc_18000526F
0x180004e5b  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180004e60  mov     [rsp+2F0h+hKey], r12
0x180004e65  test    rcx, rcx
0x180004e68  jz      short loc_180004E70
0x180004e6a  call    cs:__imp_RegCloseKey
0x180004e70  test    r14, r14
0x180004e73  jz      loc_180005035
0x180004e79  cmp     [r14], r12w
0x180004e7d  jz      loc_180005035
0x180004e83  lea     r12, [r13+1A8h]
0x180004e8a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004e8e  xor     esi, esi
0x180004e90  test    r14, r14
0x180004e93  jz      loc_180005242
0x180004e99  mov     rbx, rdi
0x180004e9c  inc     rbx
0x180004e9f  cmp     [r14+rbx*2], si
0x180004ea4  jnz     short loc_180004E9C
0x180004ea6  mov     ecx, 0FFFFFFFFh
0x180004eab  cmp     rbx, rcx
0x180004eae  jbe     loc_1800051C6
0x180004eb4  mov     rsi, rdi
0x180004eb7  xor     eax, eax
0x180004eb9  inc     rsi
0x180004ebc  cmp     [r14+rsi*2], ax
0x180004ec1  jnz     short loc_180004EB9
0x180004ec3  cmp     rsi, rcx
0x180004ec6  jbe     loc_1800051EC
0x180004ecc  xor     esi, esi
0x180004ece  xor     edx, edx; length
0x180004ed0  mov     rcx, [r12]; string
0x180004ed4  call    cs:__imp_WindowsGetStringRawBuffer
0x180004eda  mov     rbx, rax
0x180004edd  inc     rdi
0x180004ee0  cmp     [rax+rdi*2], si
0x180004ee4  jnz     short loc_180004EDD
0x180004ee6  cmp     rdi, 7FFFFFFFh
0x180004eed  jnb     loc_180005238
0x180004ef3  mov     [rsp+2F0h+hKey], rsi
0x180004ef8  mov     [rsp+2F0h+lpdwDisposition], rsi; lpdwDisposition
0x180004efd  lea     rax, [rsp+2F0h+hKey]
0x180004f02  mov     [rsp+2F0h+var_2B8], rax; phkResult
0x180004f07  mov     [rsp+2F0h+pcbData], rsi; lpSecurityAttributes
0x180004f0c  mov     dword ptr [rsp+2F0h+pvData], 2; samDesired
0x180004f14  mov     dword ptr [rsp+2F0h+pdwType], esi; dwOptions
0x180004f18  xor     r9d, r9d; lpClass
0x180004f1b  xor     r8d, r8d; Reserved
0x180004f1e  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004f25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004f2c  call    cs:__imp_RegCreateKeyExW
0x180004f32  mov     esi, 1
0x180004f37  test    eax, eax
0x180004f39  jnz     short loc_180004F77
0x180004f3b  lea     eax, ds:2[rdi*2]
0x180004f42  mov     dword ptr [rsp+2F0h+pvData], eax; cbData
0x180004f46  mov     [rsp+2F0h+pdwType], rbx; lpData
0x180004f4b  mov     r9d, esi; dwType
0x180004f4e  xor     r8d, r8d; Reserved
0x180004f51  lea     rdx, aSelectedusersi; "SelectedUserSID"
0x180004f58  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180004f5d  call    cs:__imp_RegSetValueExW
0x180004f63  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180004f68  cmp     rcx, 0FFFFFFFF80000002h
0x180004f6f  jz      short loc_180004F77
0x180004f71  call    cs:__imp_RegCloseKey
0x180004f77  mov     rcx, [r12]; string
0x180004f7b  xor     r12d, r12d
0x180004f7e  test    rcx, rcx
0x180004f81  jz      loc_180005035
0x180004f87  mov     [r13+1BCh], esi
0x180004f8e  lea     edi, [r12+64h]
0x180004f93  mov     [r13+1C0h], edi
0x180004f9a  mov     [r13+1C4h], sil
0x180004fa1  xor     edx, edx; length
0x180004fa3  call    cs:__imp_WindowsGetStringRawBuffer
0x180004fa9  lea     rcx, aAccessibility; "Accessibility"
0x180004fb0  mov     [rsp+2F0h+pcbData], rcx
0x180004fb5  mov     rcx, cs:off_18009E008; "AnyoneRead"
0x180004fbc  mov     [rsp+2F0h+pvData], rcx
0x180004fc1  mov     [rsp+2F0h+pdwType], rax
0x180004fc6  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180004fcd  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180004fd4  mov     edx, 0FFh; unsigned __int64
0x180004fd9  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x180004fdd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004fe2  test    eax, eax
0x180004fe4  js      short loc_180005035
0x180004fe6  mov     [rsp+2F0h+hKey], r12
0x180004feb  lea     rax, [rsp+2F0h+hKey]
0x180004ff0  mov     [rsp+2F0h+pdwType], rax; phkResult
0x180004ff5  mov     r9d, 20019h; samDesired
0x180004ffb  xor     r8d, r8d; ulOptions
0x180004ffe  lea     rdx, [rbp+1F0h+var_250]; lpSubKey
0x180005002  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005009  call    cs:__imp_RegOpenKeyExW
0x18000500f  test    eax, eax
0x180005011  jle     short loc_18000501D
0x180005013  movzx   eax, ax
0x180005016  or      eax, 80070000h
0x18000501b  test    eax, eax
0x18000501d  jns     short loc_180005066
0x18000501f  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180005024  mov     [rsp+2F0h+hKey], r12
0x180005029  test    rcx, rcx
0x18000502c  jz      short loc_180005035
0x18000502e  call    cs:__imp_RegCloseKey
0x180005034  nop
0x180005035  test    r14, r14
0x180005038  jz      short loc_180005043
0x18000503a  mov     rcx, r14; pv
0x18000503d  call    cs:__imp_CoTaskMemFree
0x180005043  mov     rcx, [rbp+1F0h+var_50]
0x18000504a  xor     rcx, rsp; StackCookie
0x18000504d  call    __security_check_cookie
0x180005052  add     rsp, 2B8h
0x180005059  pop     r15
0x18000505b  pop     r14
0x18000505d  pop     r13
0x18000505f  pop     r12
0x180005061  pop     rdi
0x180005062  pop     rsi
0x180005063  pop     rbx
0x180005064  pop     rbp
0x180005065  retn
0x180005066  mov     [rsp+2F0h+var_290], r12d
0x18000506b  mov     dword ptr [rsp+2F0h+phkResult], 4
0x180005073  lea     rax, [rsp+2F0h+phkResult]
0x180005078  mov     [rsp+2F0h+pcbData], rax; pcbData
0x18000507d  lea     rax, [rsp+2F0h+var_290]
0x180005082  mov     [rsp+2F0h+pvData], rax; pvData
0x180005087  mov     [rsp+2F0h+pdwType], r12; pdwType
0x18000508c  mov     ebx, 10h
0x180005091  mov     r9d, ebx; dwFlags
0x180005094  lea     r8, aCaretwidth; "CaretWidth"
0x18000509b  xor     edx, edx; lpSubKey
0x18000509d  mov     rcx, [rsp+2F0h+hKey]; hkey
0x1800050a2  call    cs:__imp_RegGetValueW
0x1800050a8  test    eax, eax
0x1800050aa  jle     short loc_1800050B6
0x1800050ac  movzx   eax, ax
0x1800050af  or      eax, 80070000h
0x1800050b4  test    eax, eax
0x1800050b6  jns     loc_18000549E
0x1800050bc  mov     [rsp+2F0h+cbData], r12d
0x1800050c1  mov     dword ptr [rsp+2F0h+phkResult], 4
0x1800050c9  lea     rax, [rsp+2F0h+phkResult]
0x1800050ce  mov     [rsp+2F0h+pcbData], rax; pcbData
0x1800050d3  lea     rax, [rsp+2F0h+cbData]
0x1800050d8  mov     [rsp+2F0h+pvData], rax; pvData
0x1800050dd  mov     [rsp+2F0h+pdwType], r12; pdwType
0x1800050e2  mov     r9d, ebx; dwFlags
0x1800050e5  lea     r8, aTextscalefacto; "TextScaleFactor"
0x1800050ec  xor     edx, edx; lpSubKey
0x1800050ee  mov     rcx, [rsp+2F0h+hKey]; hkey
0x1800050f3  call    cs:__imp_RegGetValueW
0x1800050f9  test    eax, eax
0x1800050fb  jle     short loc_180005107
0x1800050fd  movzx   eax, ax
0x180005100  or      eax, 80070000h
0x180005105  test    eax, eax
0x180005107  jns     loc_1800054BD
0x18000510d  mov     ebx, r12d
0x180005110  mov     [rsp+2F0h+var_280], r12d
0x180005115  mov     dword ptr [rsp+2F0h+phkResult], 4
0x18000511d  lea     rax, [rsp+2F0h+phkResult]
0x180005122  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180005127  lea     rax, [rsp+2F0h+Type]
0x18000512c  mov     [rsp+2F0h+pvData], rax; pvData
0x180005131  lea     rax, [rsp+2F0h+var_280]
0x180005136  mov     [rsp+2F0h+pdwType], rax; pdwType
  ... truncated ...
```
