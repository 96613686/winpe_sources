# Execution::UpdateBAMStoreSDForUser

- ea: `0x180036bfc`
- end: `0x18003700a`
- name: `Execution::UpdateBAMStoreSDForUser`
- size: `1038`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180067f40`

## callees

- `0x18001a1f0`
- `0x180036bfc`
- `0x1800371a8`
- `0x18006b690`
- `0x18006b728`
- `0x18006bf84`
- `0x18006bfa4`
- `0x18006d68c`
- `0x18006db64`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180036ca2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180036ca2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036cd1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036cd1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180036c6c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180036c6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036df2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036eb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036ed4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036ee3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036df2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036eb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036ed4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036ee3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036fe0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036ff4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036fff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036fe0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036ff4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036fff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036d63`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036d63`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180036ddc`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180036ddc`

## string_xrefs

- `0x180036c1e`: `onecoreuap\base\background\bi\backgroundmanager\lib\BAMRegistryInit.h`
- `0x180036e51`: `onecoreuap\base\background\bi\backgroundmanager\lib\BAMRegistryInit.h`
- `0x180036e7f`: `onecoreuap\base\background\bi\backgroundmanager\lib\BAMRegistryInit.h`
- `0x180036e9b`: `onecoreuap\base\background\bi\backgroundmanager\lib\BAMRegistryInit.h`
- `0x180036f3f`: `onecoreuap\base\background\bi\backgroundmanager\lib\BAMRegistryInit.h`
- `0x180036f61`: `onecoreuap\base\background\bi\backgroundmanager\lib\BAMRegistryInit.h`
- `0x180036f90`: `onecoreuap\base\background\bi\backgroundmanager\lib\BAMRegistryInit.h`
- `0x180036fac`: `onecoreuap\base\background\bi\backgroundmanager\lib\BAMRegistryInit.h`
- `0x180036ce3`: `Software\Microsoft\Windows\CurrentVersion\BackgroundAccessApplications`

## pseudocode

```c
__int64 __fastcall Execution::UpdateBAMStoreSDForUser(PSID Sid)
{
  unsigned int LastError; // ebx
  BOOL v4; // edi
  const char *v5; // r9
  const char *v6; // r9
  int v7; // eax
  WCHAR *v8; // rdi
  unsigned int v9; // eax
  HKEY v10; // rbx
  int v11; // eax
  LPWSTR v12; // rbx
  DWORD v13; // eax
  PSECURITY_DESCRIPTOR v14; // rcx
  __int64 v15; // rdx
  PSECURITY_DESCRIPTOR v16; // rcx
  unsigned int v17; // esi
  PSECURITY_DESCRIPTOR v18; // rcx
  void *v19; // rcx
  int dwOptions; // [rsp+20h] [rbp-69h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-69h]
  int dwOptionsb; // [rsp+20h] [rbp-69h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-69h]
  LPWSTR StringSid; // [rsp+50h] [rbp-39h] BYREF
  __int64 v25; // [rsp+58h] [rbp-31h]
  __int64 v26; // [rsp+60h] [rbp-29h]
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-19h] BYREF
  __int64 v29; // [rsp+78h] [rbp-11h]
  PACL pDacl; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v31[8]; // [rsp+88h] [rbp-1h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+90h] [rbp+7h] BYREF
  LPWSTR pObjectName[7]; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  WINBOOL bDaclDefaulted; // [rsp+F0h] [rbp+67h] BYREF
  WINBOOL bDaclPresent; // [rsp+F8h] [rbp+6Fh] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+100h] [rbp+77h] BYREF
  HKEY hKey; // [rsp+108h] [rbp+7Fh] BYREF

  if ( !Sid )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\BAMRegistryInit.h",
      (const char *)0x80070057LL,
      dwOptions);
    return LastError;
  }
  pSecurityDescriptor = 0;
  SecurityDescriptor = 0;
  lpSubKey = (LPCWSTR)&pSecurityDescriptor;
  LOBYTE(v29) = 1;
  v4 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;CIOI;GR;;;S-1-5-80-410965207-2550896871-1717734767-2321332215-3755966139)(A;CIOI;GR;;;S-1-5-80-2586557155-"
          "168560303-1373426920-983201488-1499765686)(A;CIOI;GA;;;BA)(A;CIOI;GA;;;S-1-5-32-581)",
         1u,
         &SecurityDescriptor,
         0);
  if ( (_BYTE)v29 )
  {
    v19 = *(void **)lpSubKey;
    *(_QWORD *)lpSubKey = SecurityDescriptor;
    if ( v19 )
      LocalFree(v19);
  }
  if ( !v4 )
  {
    v15 = 45;
    goto LABEL_27;
  }
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v15 = 54;
LABEL_27:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v15,
                  (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\BAMRegistryInit.h",
                  v5);
    goto LABEL_28;
  }
  if ( !pDacl )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\BAMRegistryInit.h",
      (const char *)0x8000FFFFLL,
      dwOptions);
    goto LABEL_28;
  }
  StringSid = 0;
  v25 = -1;
  v26 = -1;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3B,
                  (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\BAMRegistryInit.h",
                  v6);
LABEL_48:
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid);
LABEL_28:
    v16 = pSecurityDescriptor;
    pSecurityDescriptor = 0;
    if ( v16 )
      LocalFree(v16);
    return LastError;
  }
  lpSubKey = 0;
  SecurityDescriptor = 0;
  v29 = 0;
  v7 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
         &lpSubKey,
         L"%s\\%s",
         StringSid,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\BackgroundAccessApplications");
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\BAMRegistryInit.h",
      (const char *)(unsigned int)v7,
      dwOptions);
LABEL_47:
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&lpSubKey);
    goto LABEL_48;
  }
  v8 = (WCHAR *)lpSubKey;
  SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  hKey = 0;
  v9 = RegCreateKeyExW(HKEY_USERS, lpSubKey, 0, 0, 0, 0x2001Fu, &SecurityAttributes, &hKey, 0);
  if ( v9 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x4D,
                  (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\BAMRegistryInit.h",
                  (const char *)v9,
                  dwOptionsa);
LABEL_51:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_47;
  }
  v10 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v31);
    RegCloseKey(v10);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v31);
  }
  hKey = 0;
  memset(pObjectName, 0, 24);
  v11 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
          pObjectName,
          L"%s\\%s\\%s",
          L"USERS",
          StringSid,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\BackgroundAccessApplications");
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\BAMRegistryInit.h",
      (const char *)(unsigned int)v11,
      dwOptionsb);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(pObjectName);
    goto LABEL_51;
  }
  v12 = pObjectName[0];
  v13 = SetNamedSecurityInfoW(pObjectName[0], SE_REGISTRY_KEY, 4u, 0, 0, pDacl, 0);
  if ( v13 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x5B,
            (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\BAMRegistryInit.h",
            (const char *)v13,
            dwOptionsc);
    if ( v12 )
      LocalFree(v12);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v8 )
      LocalFree(v8);
    if ( StringSid )
    {
      LocalFree(StringSid);
      StringSid = 0;
    }
    v18 = pSecurityDescriptor;
    v25 = 0;
    v26 = 0;
    pSecurityDescriptor = 0;
    if ( v18 )
      LocalFree(v18);
    return v17;
  }
  else
  {
    if ( v12 )
      LocalFree(v12);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v8 )
      LocalFree(v8);
    if ( StringSid )
    {
      LocalFree(StringSid);
      StringSid = 0;
    }
    v14 = pSecurityDescriptor;
    v25 = 0;
    v26 = 0;
    pSecurityDescriptor = 0;
    if ( v14 )
      LocalFree(v14);
    return 0;
  }
}

```

## disassembly

```asm
0x180036bfc  push    rbp
0x180036bfe  push    rbx
0x180036bff  push    rsi
0x180036c00  push    rdi
0x180036c01  push    r14
0x180036c03  lea     rbp, [rsp-37h]
0x180036c08  sub     rsp, 0C0h
0x180036c0f  xor     r14d, r14d
0x180036c12  mov     rbx, rcx
0x180036c15  test    rcx, rcx
0x180036c18  jnz     short loc_180036C46
0x180036c1a  mov     rcx, [rbp+5Fh]; this
0x180036c1e  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\background\\bi\\backg"...
0x180036c25  mov     ebx, 80070057h
0x180036c2a  lea     edx, [r14+26h]; void *
0x180036c2e  mov     r9d, ebx; char *
0x180036c31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036c36  mov     eax, ebx
0x180036c38  add     rsp, 0C0h
0x180036c3f  pop     r14
0x180036c41  pop     rdi
0x180036c42  pop     rsi
0x180036c43  pop     rbx
0x180036c44  pop     rbp
0x180036c45  retn
0x180036c46  xor     r9d, r9d; SecurityDescriptorSize
0x180036c49  mov     [rbp+57h+pSecurityDescriptor], r14
0x180036c4d  lea     rax, [rbp+57h+pSecurityDescriptor]
0x180036c51  mov     [rbp+57h+SecurityDescriptor], r14
0x180036c55  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180036c59  mov     [rbp+57h+lpSubKey], rax
0x180036c5d  lea     rcx, StringSecurityDescriptor; "D:(A;CIOI;GR;;;S-1-5-80-410965207-25508"...
0x180036c64  mov     byte ptr [rbp+57h+var_68], 1
0x180036c68  lea     edx, [r9+1]; StringSDRevision
0x180036c6c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180036c72  mov     edi, eax
0x180036c74  cmp     byte ptr [rbp+57h+var_68], r14b
0x180036c78  jnz     loc_180036F0F
0x180036c7e  test    edi, edi
0x180036c80  jz      loc_180036F31
0x180036c86  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180036c8a  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180036c8e  lea     r8, [rbp+57h+pDacl]; pDacl
0x180036c92  mov     [rbp+57h+pDacl], r14
0x180036c96  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180036c9a  mov     [rbp+57h+bDaclPresent], r14d
0x180036c9e  mov     [rbp+57h+bDaclDefaulted], r14d
0x180036ca2  call    cs:__imp_GetSecurityDescriptorDacl
0x180036ca8  test    eax, eax
0x180036caa  jz      loc_180036E48
0x180036cb0  cmp     [rbp+57h+pDacl], r14
0x180036cb4  jz      loc_180036F3B
0x180036cba  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036cbe  mov     [rbp+57h+StringSid], r14
0x180036cc2  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180036cc6  mov     [rbp+57h+var_88], rax
0x180036cca  mov     rcx, rbx; Sid
0x180036ccd  mov     [rbp+57h+var_80], rax
0x180036cd1  call    cs:__imp_ConvertSidToStringSidW
0x180036cd7  test    eax, eax
0x180036cd9  jz      loc_180036E7B
0x180036cdf  mov     r8, [rbp+57h+StringSid]
0x180036ce3  lea     rsi, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180036cea  mov     r9, rsi
0x180036ced  mov     [rbp+57h+lpSubKey], r14
0x180036cf1  lea     rdx, aSS; "%s\\%s"
0x180036cf8  mov     [rbp+57h+SecurityDescriptor], r14
0x180036cfc  lea     rcx, [rbp+57h+lpSubKey]
0x180036d00  mov     [rbp+57h+var_68], r14
0x180036d04  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180036d09  mov     ebx, eax
0x180036d0b  test    eax, eax
0x180036d0d  js      loc_180036F5D
0x180036d13  mov     rax, [rbp+57h+pSecurityDescriptor]
0x180036d17  xor     r9d, r9d; lpClass
0x180036d1a  mov     rdi, [rbp+57h+lpSubKey]
0x180036d1e  xor     r8d, r8d; Reserved
0x180036d21  mov     [rsp+0E0h+lpdwDisposition], r14; lpdwDisposition
0x180036d26  mov     rdx, rdi; lpSubKey
0x180036d29  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x180036d2d  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180036d34  lea     rax, [rbp+57h+hKey]
0x180036d38  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x180036d40  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180036d45  lea     rax, [rbp+57h+SecurityAttributes]
0x180036d49  mov     [rsp+0E0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180036d4e  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x180036d56  mov     [rsp+0E0h+dwOptions], r14d; unsigned int
0x180036d5b  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], r14
0x180036d5f  mov     [rbp+57h+hKey], r14
0x180036d63  call    cs:__imp_RegCreateKeyExW
0x180036d69  test    eax, eax
0x180036d6b  jnz     loc_180036F8C
0x180036d71  mov     rbx, [rbp+57h+hKey]
0x180036d75  test    rbx, rbx
0x180036d78  jnz     loc_180036FD4
0x180036d7e  mov     r9, [rbp+57h+StringSid]
0x180036d82  lea     r8, aUsers; "USERS"
0x180036d89  lea     rdx, aSSS; "%s\\%s\\%s"
0x180036d90  mov     [rbp+57h+hKey], r14
0x180036d94  lea     rcx, [rbp+57h+pObjectName]
0x180036d98  mov     [rbp+57h+pObjectName], r14
0x180036d9c  mov     [rbp+57h+var_30], r14
0x180036da0  mov     [rbp+57h+var_28], r14
0x180036da4  mov     qword ptr [rsp+0E0h+dwOptions], rsi; int
0x180036da9  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180036dae  mov     ebx, eax
0x180036db0  test    eax, eax
0x180036db2  js      loc_180036FA8
0x180036db8  mov     rax, [rbp+57h+pDacl]
0x180036dbc  xor     r9d, r9d; psidOwner
0x180036dbf  mov     rbx, [rbp+57h+pObjectName]
0x180036dc3  mov     [rsp+0E0h+lpSecurityAttributes], r14; pSacl
0x180036dc8  mov     rcx, rbx; pObjectName
0x180036dcb  mov     qword ptr [rsp+0E0h+samDesired], rax; pDacl
0x180036dd0  lea     edx, [r9+4]; ObjectType
0x180036dd4  mov     qword ptr [rsp+0E0h+dwOptions], r14; unsigned int
0x180036dd9  mov     r8d, edx; SecurityInfo
0x180036ddc  call    cs:__imp_SetNamedSecurityInfoW
0x180036de2  test    eax, eax
0x180036de4  jnz     loc_180036E97
0x180036dea  test    rbx, rbx
0x180036ded  jz      short loc_180036DF8
0x180036def  mov     rcx, rbx; hMem
0x180036df2  call    cs:__imp_LocalFree
0x180036df8  mov     rcx, [rbp+57h+hKey]; hKey
0x180036dfc  test    rcx, rcx
0x180036dff  jnz     loc_180036FFF
0x180036e05  test    rdi, rdi
0x180036e08  jz      short loc_180036E13
0x180036e0a  mov     rcx, rdi; hMem
0x180036e0d  call    cs:__imp_LocalFree
0x180036e13  mov     rcx, [rbp+57h+StringSid]; hMem
0x180036e17  test    rcx, rcx
0x180036e1a  jz      short loc_180036E26
0x180036e1c  call    cs:__imp_LocalFree
0x180036e22  mov     [rbp+57h+StringSid], r14
0x180036e26  mov     rcx, [rbp+57h+pSecurityDescriptor]; hMem
0x180036e2a  mov     [rbp+57h+var_88], r14
0x180036e2e  mov     [rbp+57h+var_80], r14
0x180036e32  mov     [rbp+57h+pSecurityDescriptor], r14
0x180036e36  test    rcx, rcx
0x180036e39  jz      short loc_180036E41
0x180036e3b  call    cs:__imp_LocalFree
0x180036e41  xor     eax, eax
0x180036e43  jmp     loc_180036C38
0x180036e48  mov     edx, 36h ; '6'; void *
0x180036e4d  mov     rcx, [rbp+5Fh]; this
0x180036e51  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\background\\bi\\backg"...
0x180036e58  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036e5d  mov     ebx, eax
0x180036e5f  mov     rcx, [rbp+57h+pSecurityDescriptor]; hMem
0x180036e63  mov     [rbp+57h+pSecurityDescriptor], r14
0x180036e67  test    rcx, rcx
0x180036e6a  jz      loc_180036C36
0x180036e70  call    cs:__imp_LocalFree
0x180036e76  jmp     loc_180036C36
0x180036e7b  mov     rcx, [rbp+5Fh]; this
0x180036e7f  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\background\\bi\\backg"...
0x180036e86  mov     edx, 3Bh ; ';'; void *
0x180036e8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036e90  mov     ebx, eax
0x180036e92  jmp     loc_180036F7E
0x180036e97  mov     rcx, [rbp+5Fh]; this
0x180036e9b  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\background\\bi\\backg"...
0x180036ea2  mov     r9d, eax; char *
0x180036ea5  mov     edx, 5Bh ; '['; void *
0x180036eaa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036eaf  mov     esi, eax
0x180036eb1  test    rbx, rbx
0x180036eb4  jz      short loc_180036EBF
0x180036eb6  mov     rcx, rbx; hMem
0x180036eb9  call    cs:__imp_LocalFree
0x180036ebf  mov     rcx, [rbp+57h+hKey]; hKey
0x180036ec3  test    rcx, rcx
0x180036ec6  jnz     loc_180036FF4
0x180036ecc  test    rdi, rdi
0x180036ecf  jz      short loc_180036EDA
0x180036ed1  mov     rcx, rdi; hMem
0x180036ed4  call    cs:__imp_LocalFree
0x180036eda  mov     rcx, [rbp+57h+StringSid]; hMem
0x180036ede  test    rcx, rcx
0x180036ee1  jz      short loc_180036EED
0x180036ee3  call    cs:__imp_LocalFree
0x180036ee9  mov     [rbp+57h+StringSid], r14
0x180036eed  mov     rcx, [rbp+57h+pSecurityDescriptor]; hMem
0x180036ef1  mov     [rbp+57h+var_88], r14
0x180036ef5  mov     [rbp+57h+var_80], r14
0x180036ef9  mov     [rbp+57h+pSecurityDescriptor], r14
0x180036efd  test    rcx, rcx
0x180036f00  jz      short loc_180036F08
0x180036f02  call    cs:__imp_LocalFree
0x180036f08  mov     eax, esi
0x180036f0a  jmp     loc_180036C38
0x180036f0f  mov     r8, [rbp+57h+lpSubKey]
0x180036f13  mov     rdx, [rbp+57h+SecurityDescriptor]
0x180036f17  mov     rcx, [r8]; hMem
0x180036f1a  mov     [r8], rdx
0x180036f1d  test    rcx, rcx
0x180036f20  jz      loc_180036C7E
0x180036f26  call    cs:__imp_LocalFree
0x180036f2c  jmp     loc_180036C7E
0x180036f31  mov     edx, 2Dh ; '-'
0x180036f36  jmp     loc_180036E4D
0x180036f3b  mov     rcx, [rbp+5Fh]; this
0x180036f3f  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\background\\bi\\backg"...
0x180036f46  mov     ebx, 8000FFFFh
0x180036f4b  mov     edx, 38h ; '8'; void *
0x180036f50  mov     r9d, ebx; char *
0x180036f53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036f58  jmp     loc_180036E5F
0x180036f5d  mov     rcx, [rbp+5Fh]; this
0x180036f61  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\background\\bi\\backg"...
0x180036f68  mov     r9d, ebx; char *
0x180036f6b  mov     edx, 3Fh ; '?'; void *
0x180036f70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036f75  lea     rcx, [rbp+57h+lpSubKey]
0x180036f79  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180036f7e  lea     rcx, [rbp+57h+StringSid]
0x180036f82  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180036f87  jmp     loc_180036E5F
0x180036f8c  mov     rcx, [rbp+5Fh]; this
0x180036f90  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\background\\bi\\backg"...
0x180036f97  mov     r9d, eax; char *
0x180036f9a  mov     edx, 4Dh ; 'M'; void *
0x180036f9f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036fa4  mov     ebx, eax
0x180036fa6  jmp     short loc_180036FC9
0x180036fa8  mov     rcx, [rbp+5Fh]; this
0x180036fac  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\background\\bi\\backg"...
0x180036fb3  mov     r9d, ebx; char *
0x180036fb6  mov     edx, 52h ; 'R'; void *
0x180036fbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036fc0  lea     rcx, [rbp+57h+pObjectName]
0x180036fc4  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180036fc9  lea     rcx, [rbp+57h+hKey]
0x180036fcd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180036fd2  jmp     short loc_180036F75
0x180036fd4  lea     rcx, [rbp+57h+var_58]; this
0x180036fd8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180036fdd  mov     rcx, rbx; hKey
0x180036fe0  call    cs:__imp_RegCloseKey
0x180036fe6  lea     rcx, [rbp+57h+var_58]; this
0x180036fea  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036fef  jmp     loc_180036D7E
0x180036ff4  call    cs:__imp_RegCloseKey
0x180036ffa  jmp     loc_180036ECC
0x180036fff  call    cs:__imp_RegCloseKey
0x180037005  jmp     loc_180036E05
```
