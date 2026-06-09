# UpdateHttpsBinding(IRequestContext *,ushort const *,ushort const *,int *,int,int)

- ea: `0x1801a0010`
- end: `0x1801a070a`
- name: `?UpdateHttpsBinding@@YAHPEAVIRequestContext@@PEBG1PEAHHH@Z`
- size: `1786`
- prototype: `_BOOL8 __fastcall(struct IRequestContext *, const unsigned __int16 *, const unsigned __int16 *, int *, int, int)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180199308`
- `0x180199718`
- `0x18019b008`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180013760`
- `0x1800621e0`
- `0x180077490`
- `0x1800bac30`
- `0x1800e8a50`
- `0x1801123e8`
- `0x1801133b0`
- `0x18012a93c`
- `0x18013da24`
- `0x1801a0010`
- `0x1801a0f64`
- `0x1801a1070`
- `0x1801c2010`

## import_xrefs

- `msvcrt!wcsstr` at `0x1801a0469`
- `msvcrt!wcsstr` at `0x1801a0469`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0429`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a064b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a064b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0689`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1801a030e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1801a030e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1801a051f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1801a06b9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1801a06c8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1801a051f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1801a06b9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1801a06c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801a0612`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801a0612`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a02ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a03d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a02ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a03d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a027b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a027b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801a05e5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801a05e5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1801a044f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1801a044f`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x1801a012e`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x1801a012e`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x1801a01a3`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x1801a01a3`

## string_xrefs

- `0x1801a0058`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1801a0341`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1801a0372`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1801a00d4`: `update`
- `0x1801a01ec`: `HttpSetServiceConfiguration`
- `0x1801a0222`: `SYSTEM\ControlSet001\Services\HTTP\Parameters\UrlAclInfo`
- `0x1801a0237`: `SYSTEM\ControlSet001\Services\HTTP\Parameters\UrlAclInfo`

## pseudocode

```c
_BOOL8 __fastcall UpdateHttpsBinding(
        struct IRequestContext *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int *a4,
        int a5,
        int a6)
{
  int v11; // ebx
  const wchar_t *v12; // r8
  const wchar_t *v13; // rax
  _BOOL8 v14; // r13
  ULONG v15; // eax
  ULONG v16; // ebx
  ULONG v17; // eax
  ULONG v18; // ebx
  const WCHAR *v19; // r14
  unsigned __int16 *v20; // rbx
  int v21; // r8d
  LSTATUS v22; // r12d
  LSTATUS v23; // r8d
  HLOCAL v24; // r15
  DWORD v25; // eax
  HKEY v26; // r12
  LSTATUS v27; // esi
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned __int64 v32; // kr00_8
  __int64 v33; // rax
  LSTATUS v34; // ecx
  char LastError; // al
  char v36; // al
  int v37; // r8d
  DWORD Type; // [rsp+40h] [rbp-40h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v40; // [rsp+50h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-28h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+60h] [rbp-20h] BYREF
  DWORD v43; // [rsp+68h] [rbp-18h]
  DWORD lpcbData; // [rsp+6Ch] [rbp-14h] BYREF
  _QWORD pConfigInformation[2]; // [rsp+70h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+40h] BYREF
  int *v47; // [rsp+D8h] [rbp+58h]

  v47 = a4;
  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 0x46u, L"70", 0x54Fu, 0);
    return 0;
  }
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 0x47u, L"71", 0x54Fu, a1);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 0x48u, L"72", 0x54Fu, a1);
    return 0;
  }
  v11 = a5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    v12 = L"TRUE";
    if ( !a6 )
      v12 = L"FALSE";
    v13 = L"update";
    if ( !a5 )
      v13 = (const wchar_t *)L"reset";
    WPP_SF_SSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3, (__int64)v13, (__int64)v12);
  }
  if ( !v11 )
  {
    LODWORD(v14) = 1;
    pConfigInformation[0] = a2;
    pConfigInformation[1] = a3;
    v15 = HttpDeleteServiceConfiguration(0, HttpServiceConfigUrlAclInfo, pConfigInformation, 0x10u, 0);
    v16 = v15;
    if ( (v15 & 0xFFFFFFFD) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_56614427bb63350db5b96d546a520a16_Traceguids,
        pConfigInformation[0],
        v15);
    }
    if ( a4 )
      *a4 = v16 == 0;
    v17 = HttpSetServiceConfiguration(0, HttpServiceConfigUrlAclInfo, pConfigInformation, 0x10u, 0);
    v18 = v17;
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)&WPP_56614427bb63350db5b96d546a520a16_Traceguids,
          pConfigInformation[0],
          v17);
      (*(void (__fastcall **)(struct IRequestContext *, _QWORD, __int64, const wchar_t *, ULONG))(*(_QWORD *)a1 + 64LL))(
        a1,
        v18,
        1077134176,
        L"HttpSetServiceConfiguration",
        v18);
      LODWORD(v14) = 0;
    }
    return v14;
  }
  phkResult = 0;
  if ( ConfigRegistry::m_migContext )
    v19 = (const WCHAR *)(*(__int64 (__fastcall **)(struct WSManMigrationContext *, const wchar_t *))(*(_QWORD *)ConfigRegistry::m_migContext + 16LL))(
                           ConfigRegistry::m_migContext,
                           L"SYSTEM\\ControlSet001\\Services\\HTTP\\Parameters\\UrlAclInfo");
  else
    v19 = L"SYSTEM\\ControlSet001\\Services\\HTTP\\Parameters\\UrlAclInfo";
  pConfigInformation[0] = v19;
  v20 = 0;
  v40 = 0;
  Type = 3;
  cbData = 0;
  SecurityDescriptor = 0;
  StringSecurityDescriptor = 0;
  LODWORD(v14) = 0;
  v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x103u, &phkResult);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v21, (_DWORD)v19, (__int64)a2, v22);
  if ( !v22 )
  {
    if ( a6 )
    {
      v23 = RegQueryValueExW(phkResult, a2, 0, &Type, 0, &cbData);
      if ( v23 || !cbData )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
        {
LABEL_80:
          if ( SecurityDescriptor )
            LocalFree(SecurityDescriptor);
          if ( StringSecurityDescriptor )
            LocalFree(StringSecurityDescriptor);
          goto LABEL_84;
        }
        WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v23, (_DWORD)v19, (__int64)a2, v23);
      }
      else
      {
        v24 = LocalAlloc(0, 2 * cbData);
        SecurityDescriptor = v24;
        v25 = cbData;
        v43 = cbData;
        if ( !cbData || v24 )
        {
          v26 = phkResult;
          if ( phkResult )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, a2);
              v25 = v43;
            }
            lpcbData = v25;
            v27 = RegQueryValueExW(v26, a2, 0, &Type, (LPBYTE)v24, &lpcbData);
            if ( v27 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                WPP_SF_dS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  31,
                  (unsigned int)&WPP_56614427bb63350db5b96d546a520a16_Traceguids,
                  v27,
                  (__int64)a2);
            }
            else
            {
              if ( !v24 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    (unsigned int)(v27 + 30),
                    &WPP_56614427bb63350db5b96d546a520a16_Traceguids,
                    a2);
                v27 = 122;
                SetLastError(0x7Au);
              }
              if ( !v27 )
              {
                ConvertSecurityDescriptorToStringSecurityDescriptorW(
                  SecurityDescriptor,
                  1u,
                  0xFu,
                  &StringSecurityDescriptor,
                  &cbData);
                if ( StringSecurityDescriptor )
                {
                  if ( !wcsstr(StringSecurityDescriptor, L"S-1-5-80-4059739203-877974739-1245631912-527174227") )
                  {
                    cbData += 72;
                    v28 = 2LL * cbData;
                    if ( !is_mul_ok(cbData, 2u) )
                      v28 = -1;
                    v29 = WSManMemory::Alloc(v28, 0, 0);
                    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&v40, v29);
                    v20 = v40;
                    StringCchPrintfW(
                      v40,
                      cbData,
                      L"%ls%ls",
                      StringSecurityDescriptor,
                      L"(A;;GX;;;S-1-5-80-4059739203-877974739-1245631912-527174227-2996563517)");
                    cbData = 0;
                  }
                }
              }
            }
          }
          else
          {
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 0x1FCu, L"508", 0x54Fu, a1);
          }
        }
        else
        {
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 0x1F9u, L"505", 0x54Fu, a1);
        }
        if ( SecurityDescriptor )
        {
          LocalFree(SecurityDescriptor);
          SecurityDescriptor = 0;
        }
      }
    }
    else
    {
      v30 = -1;
      do
        ++v30;
      while ( a3[v30] );
      cbData = v30 + 1;
      v32 = (unsigned int)(v30 + 1);
      v31 = 2 * v32;
      if ( !is_mul_ok(v32, 2u) )
        v31 = -1;
      v33 = WSManMemory::Alloc(v31, 0, 0);
      AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&v40, v33);
      v20 = v40;
      StringCchPrintfW(v40, cbData, L"%ls", a3);
    }
    if ( v20 )
    {
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v20, 1u, &SecurityDescriptor, &cbData) )
      {
        v34 = RegSetValueExW(phkResult, a2, 0, Type, (const BYTE *)SecurityDescriptor, cbData);
        if ( v47 )
          *v47 = v34 == 0;
        v14 = v34 == 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_SSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v19, (__int64)a2, LastError);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      {
        v36 = GetLastError();
        WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v37, (_DWORD)v20, (__int64)a2, v36);
      }
    }
    goto LABEL_80;
  }
LABEL_84:
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v40);
  AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(pConfigInformation);
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
  return v14;
}

```

## disassembly

```asm
0x1801a0010  mov     [rsp-38h+arg_8], rbx
0x1801a0015  mov     [rsp-38h+arg_18], r9
0x1801a001a  push    rbp
0x1801a001b  push    rsi
0x1801a001c  push    rdi
0x1801a001d  push    r12
0x1801a001f  push    r13
0x1801a0021  push    r14
0x1801a0023  push    r15
0x1801a0025  mov     rbp, rsp
0x1801a0028  sub     rsp, 80h
0x1801a002f  mov     r14, r9
0x1801a0032  mov     r15, r8
0x1801a0035  mov     rdi, rdx
0x1801a0038  mov     rsi, rcx
0x1801a003b  xor     r12d, r12d
0x1801a003e  test    rcx, rcx
0x1801a0041  jnz     short loc_1801A006B
0x1801a0043  mov     [rsp+80h+pOverlapped], r12; struct IRequestContext *
0x1801a0048  lea     r8, a70; "70"
0x1801a004f  lea     edx, [rcx+46h]; unsigned int
0x1801a0052  mov     r9d, 54Fh; unsigned int
0x1801a0058  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1801a005f  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801a0064  xor     eax, eax
0x1801a0066  jmp     loc_1801A06EF
0x1801a006b  test    rdi, rdi
0x1801a006e  jnz     short loc_1801A0081
0x1801a0070  mov     [rsp+80h+pOverlapped], rsi
0x1801a0075  lea     r8, a71; "71"
0x1801a007c  lea     edx, [rdi+47h]
0x1801a007f  jmp     short loc_1801A0052
0x1801a0081  test    r15, r15
0x1801a0084  jnz     short loc_1801A0098
0x1801a0086  mov     [rsp+80h+pOverlapped], rsi
0x1801a008b  lea     r8, a72; "72"
0x1801a0092  lea     edx, [r15+48h]
0x1801a0096  jmp     short loc_1801A0052
0x1801a0098  lea     rax, WPP_GLOBAL_Control
0x1801a009f  mov     ebx, [rbp+arg_20]
0x1801a00a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a00a9  cmp     rcx, rax
0x1801a00ac  jz      short loc_1801A0108
0x1801a00ae  test    dword ptr [rcx+1Ch], 200000h
0x1801a00b5  jz      short loc_1801A0108
0x1801a00b7  lea     rax, aFalse_0; "FALSE"
0x1801a00be  lea     r8, aTrue_0; "TRUE"
0x1801a00c5  cmp     [rbp+arg_28], r12d
0x1801a00c9  cmovz   r8, rax
0x1801a00cd  lea     rdx, aReset_0; "reset"
0x1801a00d4  lea     rax, aUpdate; "update"
0x1801a00db  test    ebx, ebx
0x1801a00dd  cmovz   rax, rdx
0x1801a00e1  mov     edx, 0Ch
0x1801a00e6  mov     qword ptr [rsp+80h+var_50], r8; __int64
0x1801a00eb  mov     [rsp+80h+lpcbData], rax; __int64
0x1801a00f0  mov     [rsp+80h+pOverlapped], r15; __int64
0x1801a00f5  mov     r9, rdi
0x1801a00f8  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1801a00ff  mov     rcx, [rcx+10h]; LoggerHandle
0x1801a0103  call    WPP_SF_SSSS
0x1801a0108  test    ebx, ebx
0x1801a010a  jnz     loc_1801A020F
0x1801a0110  lea     r13d, [rbx+1]
0x1801a0114  mov     [rbp+pConfigInformation], rdi
0x1801a0118  mov     [rbp+var_8], r15
0x1801a011c  mov     [rsp+80h+pOverlapped], r12; pOverlapped
0x1801a0121  lea     r9d, [rbx+10h]; ConfigInformationLength
0x1801a0125  lea     r8, [rbp+pConfigInformation]; pConfigInformation
0x1801a0129  lea     edx, [rbx+2]; ConfigId
0x1801a012c  xor     ecx, ecx; ServiceHandle
0x1801a012e  call    cs:__imp_HttpDeleteServiceConfiguration
0x1801a0134  mov     ebx, eax
0x1801a0136  test    eax, 0FFFFFFFDh
0x1801a013b  jz      short loc_1801A0177
0x1801a013d  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a0144  lea     rdi, WPP_GLOBAL_Control
0x1801a014b  cmp     rcx, rdi
0x1801a014e  jz      short loc_1801A017E
0x1801a0150  test    dword ptr [rcx+1Ch], 200000h
0x1801a0157  jz      short loc_1801A017E
0x1801a0159  lea     edx, [r13+0Ch]
0x1801a015d  mov     dword ptr [rsp+80h+pOverlapped], eax
0x1801a0161  mov     r9, [rbp+pConfigInformation]
0x1801a0165  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1801a016c  mov     rcx, [rcx+10h]
0x1801a0170  call    WPP_SF_Sd
0x1801a0175  jmp     short loc_1801A017E
0x1801a0177  lea     rdi, WPP_GLOBAL_Control
0x1801a017e  test    r14, r14
0x1801a0181  jz      short loc_1801A018E
0x1801a0183  mov     eax, r12d
0x1801a0186  test    ebx, ebx
0x1801a0188  setz    al
0x1801a018b  mov     [r14], eax
0x1801a018e  mov     [rsp+80h+pOverlapped], r12; pOverlapped
0x1801a0193  mov     r9d, 10h; ConfigInformationLength
0x1801a0199  lea     r8, [rbp+pConfigInformation]; pConfigInformation
0x1801a019d  lea     edx, [r9-0Eh]; ConfigId
0x1801a01a1  xor     ecx, ecx; ServiceHandle
0x1801a01a3  call    cs:__imp_HttpSetServiceConfiguration
0x1801a01a9  mov     ebx, eax
0x1801a01ab  test    eax, eax
0x1801a01ad  jz      loc_1801A06EC
0x1801a01b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a01ba  cmp     rcx, rdi
0x1801a01bd  jz      short loc_1801A01E5
0x1801a01bf  test    dword ptr [rcx+1Ch], 200000h
0x1801a01c6  jz      short loc_1801A01E5
0x1801a01c8  mov     edx, 0Eh
0x1801a01cd  mov     dword ptr [rsp+80h+pOverlapped], eax
0x1801a01d1  mov     r9, [rbp+pConfigInformation]
0x1801a01d5  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1801a01dc  mov     rcx, [rcx+10h]
0x1801a01e0  call    WPP_SF_Sd
0x1801a01e5  mov     rax, [rsi]
0x1801a01e8  mov     dword ptr [rsp+80h+pOverlapped], ebx
0x1801a01ec  lea     r9, aHttpsetservice_0; "HttpSetServiceConfiguration"
0x1801a01f3  mov     r8d, 4033C360h
0x1801a01f9  mov     edx, ebx
0x1801a01fb  mov     rcx, rsi
0x1801a01fe  mov     rax, [rax+40h]
0x1801a0202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0207  mov     r13d, r12d
0x1801a020a  jmp     loc_1801A06EC
0x1801a020f  mov     [rbp+phkResult], r12
0x1801a0213  mov     rcx, cs:?m_migContext@ConfigRegistry@@2PEAVWSManMigrationContext@@EA; WSManMigrationContext * ConfigRegistry::m_migContext
0x1801a021a  test    rcx, rcx
0x1801a021d  jz      short loc_1801A0237
0x1801a021f  mov     rax, [rcx]
0x1801a0222  lea     rdx, aSystemControls; "SYSTEM\\ControlSet001\\Services\\HTTP\\"...
0x1801a0229  mov     rax, [rax+10h]
0x1801a022d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0232  mov     r14, rax
0x1801a0235  jmp     short loc_1801A023E
0x1801a0237  lea     r14, aSystemControls; "SYSTEM\\ControlSet001\\Services\\HTTP\\"...
0x1801a023e  mov     [rbp+pConfigInformation], r14
0x1801a0242  mov     rbx, r12
0x1801a0245  mov     [rbp+var_30], rbx
0x1801a0249  mov     [rbp+Type], 3
0x1801a0250  mov     [rbp+cbData], r12d
0x1801a0254  mov     [rbp+SecurityDescriptor], r12
0x1801a0258  mov     [rbp+StringSecurityDescriptor], r12
0x1801a025c  mov     r13d, r12d
0x1801a025f  lea     rax, [rbp+phkResult]
0x1801a0263  mov     [rsp+80h+pOverlapped], rax; phkResult
0x1801a0268  mov     r9d, 103h; samDesired
0x1801a026e  xor     r8d, r8d; ulOptions
0x1801a0271  mov     rdx, r14; lpSubKey
0x1801a0274  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a027b  call    cs:__imp_RegOpenKeyExW
0x1801a0281  mov     r12d, eax
0x1801a0284  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a028b  lea     rax, WPP_GLOBAL_Control
0x1801a0292  cmp     rcx, rax
0x1801a0295  jz      short loc_1801A02BB
0x1801a0297  test    dword ptr [rcx+1Ch], 200000h
0x1801a029e  jz      short loc_1801A02BB
0x1801a02a0  mov     edx, 0Fh
0x1801a02a5  mov     dword ptr [rsp+80h+lpcbData], r12d
0x1801a02aa  mov     [rsp+80h+pOverlapped], rdi
0x1801a02af  mov     r9, r14
0x1801a02b2  mov     rcx, [rcx+10h]
0x1801a02b6  call    WPP_SF_SSd
0x1801a02bb  test    r12d, r12d
0x1801a02be  jnz     loc_1801A06CF
0x1801a02c4  xor     r12d, r12d
0x1801a02c7  cmp     [rbp+arg_28], r12d
0x1801a02cb  jz      loc_1801A056F
0x1801a02d1  lea     rax, [rbp+cbData]
0x1801a02d5  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1801a02da  mov     [rsp+80h+pOverlapped], r12; lpData
0x1801a02df  lea     r9, [rbp+Type]; lpType
0x1801a02e3  xor     r8d, r8d; lpReserved
0x1801a02e6  mov     rdx, rdi; lpValueName
0x1801a02e9  mov     rcx, [rbp+phkResult]; hKey
0x1801a02ed  call    cs:__imp_RegQueryValueExW
0x1801a02f3  mov     r8d, eax
0x1801a02f6  test    eax, eax
0x1801a02f8  jnz     loc_1801A052E
0x1801a02fe  mov     eax, [rbp+cbData]
0x1801a0301  test    eax, eax
0x1801a0303  jz      loc_1801A052E
0x1801a0309  lea     edx, [rax+rax]; uBytes
0x1801a030c  xor     ecx, ecx; uFlags
0x1801a030e  call    cs:__imp_LocalAlloc
0x1801a0314  mov     r15, rax
0x1801a0317  mov     [rbp+SecurityDescriptor], rax
0x1801a031b  mov     eax, [rbp+cbData]
0x1801a031e  mov     [rbp+var_18], eax
0x1801a0321  test    eax, eax
0x1801a0323  jz      short loc_1801A0352
0x1801a0325  test    r15, r15
0x1801a0328  jnz     short loc_1801A0352
0x1801a032a  mov     [rsp+80h+pOverlapped], rsi; struct IRequestContext *
0x1801a032f  mov     r9d, 54Fh; unsigned int
0x1801a0335  lea     r8, a505; "505"
0x1801a033c  mov     edx, 1F9h; unsigned int
0x1801a0341  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1801a0348  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801a034d  jmp     loc_1801A0512
0x1801a0352  mov     r12, [rbp+phkResult]
0x1801a0356  test    r12, r12
0x1801a0359  jnz     short loc_1801A0383
0x1801a035b  mov     [rsp+80h+pOverlapped], rsi; struct IRequestContext *
0x1801a0360  mov     r9d, 54Fh; unsigned int
0x1801a0366  lea     r8, a508; "508"
0x1801a036d  mov     edx, 1FCh; unsigned int
0x1801a0372  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1801a0379  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801a037e  jmp     loc_1801A0512
0x1801a0383  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a038a  lea     rdx, WPP_GLOBAL_Control
0x1801a0391  cmp     rcx, rdx
0x1801a0394  jz      short loc_1801A03BA
0x1801a0396  test    dword ptr [rcx+1Ch], 200000h
0x1801a039d  jz      short loc_1801A03BA
0x1801a039f  mov     edx, 1Dh
0x1801a03a4  mov     r9, rdi
0x1801a03a7  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1801a03ae  mov     rcx, [rcx+10h]
0x1801a03b2  call    WPP_SF_S
0x1801a03b7  mov     eax, [rbp+var_18]
0x1801a03ba  mov     [rbp+var_14], eax
0x1801a03bd  lea     rax, [rbp+var_14]
0x1801a03c1  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1801a03c6  mov     [rsp+80h+pOverlapped], r15; lpData
0x1801a03cb  lea     r9, [rbp+Type]; lpType
0x1801a03cf  xor     r8d, r8d; lpReserved
0x1801a03d2  mov     rdx, rdi; lpValueName
0x1801a03d5  mov     rcx, r12; hKey
0x1801a03d8  call    cs:__imp_RegQueryValueExW
0x1801a03de  mov     esi, eax
0x1801a03e0  xor     r12d, r12d
0x1801a03e3  test    eax, eax
0x1801a03e5  jnz     loc_1801A04D9
0x1801a03eb  test    r15, r15
0x1801a03ee  jnz     short loc_1801A042F
0x1801a03f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a03f7  lea     rax, WPP_GLOBAL_Control
0x1801a03fe  cmp     rcx, rax
0x1801a0401  jz      short loc_1801A0422
0x1801a0403  test    dword ptr [rcx+1Ch], 400000h
0x1801a040a  jz      short loc_1801A0422
0x1801a040c  lea     edx, [rsi+1Eh]
0x1801a040f  mov     r9, rdi
0x1801a0412  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1801a0419  mov     rcx, [rcx+10h]
0x1801a041d  call    WPP_SF_S
0x1801a0422  mov     esi, 7Ah ; 'z'
0x1801a0427  mov     ecx, esi; dwErrCode
0x1801a0429  call    cs:__imp_SetLastError
0x1801a042f  test    esi, esi
0x1801a0431  jnz     loc_1801A0512
0x1801a0437  lea     rax, [rbp+cbData]
0x1801a043b  mov     [rsp+80h+pOverlapped], rax; StringSecurityDescriptorLen
0x1801a0440  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x1801a0444  lea     edx, [rsi+1]; RequestedStringSDRevision
0x1801a0447  lea     r8d, [rsi+0Fh]; SecurityInformation
0x1801a044b  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801a044f  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1801a0455  mov     rcx, [rbp+StringSecurityDescriptor]; Str
0x1801a0459  test    rcx, rcx
0x1801a045c  jz      loc_1801A0512
0x1801a0462  lea     rdx, aS1580405973920; "S-1-5-80-4059739203-877974739-124563191"...
0x1801a0469  call    cs:__imp_wcsstr
0x1801a046f  test    rax, rax
0x1801a0472  jnz     loc_1801A0512
0x1801a0478  mov     eax, [rbp+cbData]
0x1801a047b  add     eax, 48h ; 'H'
0x1801a047e  mov     [rbp+cbData], eax
0x1801a0481  mov     ecx, eax
0x1801a0483  lea     eax, [rsi+2]
0x1801a0486  mul     rcx
0x1801a0489  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1801a0490  cmovb   rax, r8
0x1801a0494  xor     r8d, r8d
0x1801a0497  xor     edx, edx
0x1801a0499  mov     rcx, rax
0x1801a049c  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1801a04a1  mov     rdx, rax
0x1801a04a4  lea     rcx, [rbp+var_30]
0x1801a04a8  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x1801a04ad  mov     edx, [rbp+cbData]; unsigned __int64
0x1801a04b0  lea     rax, aAGxS1580405973; "(A;;GX;;;S-1-5-80-4059739203-877974739-"...
0x1801a04b7  mov     [rsp+80h+pOverlapped], rax
0x1801a04bc  mov     r9, [rbp+StringSecurityDescriptor]
0x1801a04c0  lea     r8, aLsLs_0; "%ls%ls"
0x1801a04c7  mov     rbx, [rbp+var_30]
0x1801a04cb  mov     rcx, rbx; unsigned __int16 *
0x1801a04ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a04d3  mov     [rbp+cbData], r12d
0x1801a04d7  jmp     short loc_1801A0512
0x1801a04d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a04e0  lea     rax, WPP_GLOBAL_Control
0x1801a04e7  cmp     rcx, rax
0x1801a04ea  jz      short loc_1801A0512
0x1801a04ec  test    dword ptr [rcx+1Ch], 400000h
0x1801a04f3  jz      short loc_1801A0512
0x1801a04f5  mov     edx, 1Fh
  ... truncated ...
```
