# UserOOBEController::s_SetupAutologonIfNecessary(ushort const *,UserOOBEExitReason,bool *)

- ea: `0x18002a480`
- end: `0x18002abb6`
- name: `?s_SetupAutologonIfNecessary@UserOOBEController@@CAJPEBGW4UserOOBEExitReason@@PEA_N@Z`
- size: `1846`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180029260`

## callees

- `0x1800032b0`
- `0x180004200`
- `0x180007114`
- `0x180007134`
- `0x18000a5c8`
- `0x18000d5a0`
- `0x18000d738`
- `0x18000e270`
- `0x18000e580`
- `0x180013688`
- `0x1800169b0`
- `0x1800287a0`
- `0x180028a38`
- `0x180028de8`
- `0x180029a78`
- `0x18002a480`
- `0x18002c4f8`
- `0x18002ca58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002a9b9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002a9f8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002a9b9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002a9f8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002a908`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002a908`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a66e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a6ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a745`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a66e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a6ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a745`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x18002a5d8`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x18002ab4e`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x18002a5d8`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x18002ab4e`
- `credui!CredUnPackAuthenticationBufferW` at `0x18002a995`
- `credui!CredUnPackAuthenticationBufferW` at `0x18002a995`

## string_xrefs

- `0x18002a6a3`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18002a560`: `UnattendXmlAutoLogon`
- `0x18002a664`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18002a540`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a5f9`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a7c4`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a835`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a89e`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a91e`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a9a6`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002aa2f`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002aaa2`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002ab22`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002ab6c`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UserOOBEController::s_SetupAutologonIfNecessary(const unsigned __int16 *a1, int a2, bool *a3)
{
  unsigned int v6; // r9d
  int v7; // eax
  int v8; // eax
  HKEY v9; // r8
  signed int LastError; // ebx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  unsigned int v15; // r9d
  bool v16; // r14
  LSTATUS ValueW; // eax
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdi
  int v21; // eax
  __int64 v22; // rdx
  _BYTE *v23; // rcx
  int v24; // eax
  HRESULT v25; // eax
  __int64 v26; // rdx
  _BYTE *v27; // rcx
  const char *v28; // r9
  __int64 v29; // rdx
  _BYTE *v30; // rcx
  __int64 v31; // rbx
  int v32; // eax
  signed int v33; // r14d
  WCHAR *v34; // rax
  __int64 v35; // rcx
  _BYTE *v36; // rax
  WCHAR *v37; // rax
  int v38; // eax
  signed int v39; // esi
  __int64 v40; // rbx
  _BYTE *v41; // rcx
  _BYTE *v42; // rax
  int v43; // eax
  int v44; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  int pdwTypec; // [rsp+20h] [rbp-E0h]
  DWORD pvData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbAuthBuffer; // [rsp+54h] [rbp-ACh] BYREF
  PVOID pAuthBuffer; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+60h] [rbp-A0h]
  __int64 v54; // [rsp+68h] [rbp-98h]
  DWORD pcchMaxDomainName; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcchMaxUserName; // [rsp+74h] [rbp-8Ch] BYREF
  PVOID *p_pAuthBuffer; // [rsp+78h] [rbp-88h]
  DWORD v58; // [rsp+80h] [rbp-80h]
  int v59; // [rsp+84h] [rbp-7Ch]
  char v60; // [rsp+88h] [rbp-78h]
  WCHAR *v61; // [rsp+90h] [rbp-70h]
  DWORD v62; // [rsp+98h] [rbp-68h]
  int v63; // [rsp+9Ch] [rbp-64h]
  char v64; // [rsp+A0h] [rbp-60h]
  WCHAR pszPassword[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v66[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR pszDomainName[256]; // [rsp+4D0h] [rbp+3D0h] BYREF
  WCHAR pszUserName[264]; // [rsp+6D0h] [rbp+5D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+918h] [rbp+818h]

  *a3 = 0;
  pvData = 0;
  if ( UserOOBEController::s_HasAutoLogonOobeProvisioned() || UserOOBEController::s_HasProvisioningCredentialCached() )
  {
    if ( UserOOBEController::s_HasProvisioningCredentialCached() )
    {
      v43 = UserOOBEController::s_RestoreProvisioningCredential();
      if ( v43 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x28E,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)(unsigned int)v43,
          pdwType);
    }
    v44 = SetPersistedRegistryBOOL(
            L"Winlogon",
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            L"SystemAutoLogon",
            1);
    LastError = v44;
    if ( v44 > 0 )
      LastError = (unsigned __int16)v44 | 0x80070000;
    if ( LastError < 0 )
    {
      v18 = 659;
      goto LABEL_72;
    }
    goto LABEL_74;
  }
  if ( (int)SHRegGetBOOLWithREGSAM(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
              L"UnattendSetAutologon",
              v6,
              (int *)&pvData) < 0
    || !pvData )
  {
    pvData = 0;
    cbAuthBuffer = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
           L"Enabled",
           0x10010u,
           0,
           &pvData,
           &cbAuthBuffer) )
    {
      cbAuthBuffer = 4;
      RegGetValueW(
        HKEY_LOCAL_MACHINE,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
        L"Enabled",
        0x20010010u,
        0,
        &pvData,
        &cbAuthBuffer);
    }
    v16 = pvData != 0;
    if ( a2 != 1 )
    {
      *a3 = v16;
      return 0;
    }
    pvData = 0;
    SHRegGetBOOLWithREGSAM(HKEY_USERS, a1, L"AutologonIsConnected", v15, (int *)&pvData);
    if ( !v16 || pvData )
    {
      memset_0(v66, 0, 0x208u);
      cbAuthBuffer = 520;
      ValueW = RegGetValueW(HKEY_USERS, a1, L"AutologonSigninName", 2u, 0, v66, &cbAuthBuffer);
      LastError = ValueW;
      if ( ValueW )
      {
        v66[0] = 0;
        if ( ValueW > 0 )
          LastError = (unsigned __int16)ValueW | 0x80070000;
      }
      if ( LastError < 0 )
      {
        v18 = 699;
LABEL_72:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)(unsigned int)LastError,
          pdwType);
        return (unsigned int)LastError;
      }
      pAuthBuffer = 0;
      cbAuthBuffer = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pAuthBuffer,
        0);
      v19 = SHRegAllocData(HKEY_USERS, a1, L"AutologonAuthenticationBuffer", 8, &pAuthBuffer, &cbAuthBuffer);
      LastError = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2BF,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)(unsigned int)v19,
          pdwTypeb);
        goto LABEL_60;
      }
      v20 = cbAuthBuffer;
      p_pAuthBuffer = &pAuthBuffer;
      v58 = cbAuthBuffer;
      v59 = HIDWORD(v53);
      v60 = 1;
      if ( pvData )
      {
        v21 = SetAutologonDetails(v66, 0, (unsigned __int8 *)pAuthBuffer, cbAuthBuffer, 1, !v16);
        LastError = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C9,
            (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
            (const char *)(unsigned int)v21,
            pdwTypec);
          v22 = (unsigned int)v20;
          v23 = pAuthBuffer;
          if ( (_DWORD)v20 )
          {
            do
            {
              *v23++ = 0;
              --v22;
            }
            while ( v22 );
          }
          goto LABEL_60;
        }
      }
      else
      {
        if ( cbAuthBuffer )
        {
          memset_0(pszUserName, 0, 0x202u);
          memset_0(pszDomainName, 0, sizeof(pszDomainName));
          memset_0(pszPassword, 0, 0x202u);
          pcchMaxUserName = 257;
          pcchMaxDomainName = 256;
          pvData = 257;
          v25 = CoImpersonateClient();
          LastError = v25;
          if ( v25 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E2,
              (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
              (const char *)(unsigned int)v25,
              pdwTypeb);
            v26 = v20;
            v27 = pAuthBuffer;
            do
            {
              *v27++ = 0;
              --v26;
            }
            while ( v26 );
            goto LABEL_60;
          }
          BYTE1(cbAuthBuffer) = 1;
          if ( !CredUnPackAuthenticationBufferW(
                  1u,
                  pAuthBuffer,
                  v20,
                  pszUserName,
                  &pcchMaxUserName,
                  pszDomainName,
                  &pcchMaxDomainName,
                  pszPassword,
                  &pvData) )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x2E8,
                          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
                          v28);
            CoRevertToSelf();
            v29 = v20;
            v30 = pAuthBuffer;
            do
            {
              *v30++ = 0;
              --v29;
            }
            while ( v29 );
            goto LABEL_60;
          }
          v31 = pvData;
          v61 = pszPassword;
          v62 = pvData;
          v63 = HIDWORD(v53);
          v64 = 1;
          BYTE1(cbAuthBuffer) = 0;
          CoRevertToSelf();
          v32 = SetAutologonDetails(v66, pszPassword, 0, 0, 0, 1);
          v33 = v32;
          if ( v32 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2EE,
              (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
              (const char *)(unsigned int)v32,
              pdwTypec);
            if ( v31 )
            {
              v34 = pszPassword;
              do
              {
                *(_BYTE *)v34 = 0;
                v34 = (WCHAR *)((char *)v34 + 1);
                --v31;
              }
              while ( v31 );
            }
            v35 = v20;
            v36 = pAuthBuffer;
            do
            {
              *v36++ = 0;
              --v35;
            }
            while ( v35 );
            LastError = v33;
            goto LABEL_60;
          }
          *a3 = 1;
          if ( v31 )
          {
            v37 = pszPassword;
            do
            {
              *(_BYTE *)v37 = 0;
              v37 = (WCHAR *)((char *)v37 + 1);
              --v31;
            }
            while ( v31 );
          }
          goto LABEL_56;
        }
        v24 = SetAutologonDetails(v66, &qword_180054928, 0, 0, 0, 1);
        LastError = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2D5,
            (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
            (const char *)(unsigned int)v24,
            pdwTypec);
          goto LABEL_60;
        }
      }
      *a3 = 1;
LABEL_56:
      v38 = UserOOBEController::s_PopulatePreserveOobeAutologonCredentialsIfNecessary(a1);
      v39 = v38;
      v40 = v20;
      if ( v38 >= 0 )
      {
        v42 = pAuthBuffer;
        if ( (_DWORD)v20 )
        {
          do
          {
            *v42++ = 0;
            --v40;
          }
          while ( v40 );
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pAuthBuffer);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F3,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)v38,
        pdwTypec);
      v41 = pAuthBuffer;
      if ( (_DWORD)v20 )
      {
        do
        {
          *v41++ = 0;
          --v40;
        }
        while ( v40 );
      }
      LastError = v39;
LABEL_60:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pAuthBuffer);
      return (unsigned int)LastError;
    }
LABEL_74:
    *a3 = 1;
    return 0;
  }
  v7 = SetAutologonDetails(0, 0, 0, 0, 0, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x29E,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v7,
      pdwTypea);
  pAuthBuffer = 0;
  v53 = 0;
  v54 = 0;
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         &pAuthBuffer,
         L"%s\\%s",
         a1,
         L"UnattendXmlAutoLogon");
  LastError = v8;
  if ( v8 < 0 )
  {
    v11 = (unsigned int)v8;
    v12 = 673;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)v11,
      pdwTypea);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pAuthBuffer);
    return (unsigned int)LastError;
  }
  v13 = TransferUnattendXmlAutologonValues(
          HKEY_USERS,
          (const unsigned __int16 *)pAuthBuffer,
          v9,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          0,
          0);
  LastError = v13;
  if ( v13 < 0 )
  {
    v11 = (unsigned int)v13;
    v12 = 675;
    goto LABEL_15;
  }
  v14 = SetPersistedRegistryBOOL(
          L"Winlogon",
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          L"SystemAutoLogon",
          1);
  LastError = v14;
  if ( v14 > 0 )
    LastError = (unsigned __int16)v14 | 0x80070000;
  if ( LastError < 0 )
  {
    v11 = (unsigned int)LastError;
    v12 = 679;
    goto LABEL_15;
  }
  *a3 = 1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pAuthBuffer);
  return 0;
}

```

## disassembly

```asm
0x18002a480  mov     [rsp-8+arg_8], rbx
0x18002a485  mov     [rsp-8+arg_18], rsi
0x18002a48a  push    rbp
0x18002a48b  push    rdi
0x18002a48c  push    r13
0x18002a48e  push    r14
0x18002a490  push    r15
0x18002a492  lea     rbp, [rsp-7F0h]
0x18002a49a  sub     rsp, 8F0h
0x18002a4a1  mov     rax, cs:__security_cookie
0x18002a4a8  xor     rax, rsp
0x18002a4ab  mov     [rbp+810h+var_30], rax
0x18002a4b2  mov     rsi, r8
0x18002a4b5  mov     ebx, edx
0x18002a4b7  mov     r15, rcx
0x18002a4ba  xor     r13d, r13d
0x18002a4bd  mov     [r8], r13b
0x18002a4c0  mov     [rsp+910h+var_8C0], r13d
0x18002a4c5  call    ?s_HasAutoLogonOobeProvisioned@UserOOBEController@@CA_NXZ; UserOOBEController::s_HasAutoLogonOobeProvisioned(void)
0x18002a4ca  test    al, al
0x18002a4cc  jnz     loc_18002AB06
0x18002a4d2  call    ?s_HasProvisioningCredentialCached@UserOOBEController@@CA_NXZ; UserOOBEController::s_HasProvisioningCredentialCached(void)
0x18002a4d7  test    al, al
0x18002a4d9  jnz     loc_18002AB06
0x18002a4df  lea     rax, [rsp+910h+var_8C0]
0x18002a4e4  mov     [rsp+910h+pdwType], rax; int *
0x18002a4e9  lea     r8, aUnattendsetaut; "UnattendSetAutologon"
0x18002a4f0  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002a4f7  mov     rdi, 0FFFFFFFF80000002h
0x18002a4fe  mov     rcx, rdi; HKEY
0x18002a501  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18002a506  test    eax, eax
0x18002a508  js      loc_18002A62E
0x18002a50e  cmp     [rsp+910h+var_8C0], r13d
0x18002a513  jz      loc_18002A62E
0x18002a519  mov     byte ptr [rsp+910h+pvData], r13b; bool
0x18002a51e  mov     byte ptr [rsp+910h+pdwType], r13b; int
0x18002a523  xor     r9d, r9d; unsigned int
0x18002a526  xor     r8d, r8d; unsigned __int8 *
0x18002a529  xor     edx, edx; unsigned __int16 *
0x18002a52b  xor     ecx, ecx; unsigned __int16 *
0x18002a52d  call    ?SetAutologonDetails@@YAJPEBG0PEBEK_N2@Z; SetAutologonDetails(ushort const *,ushort const *,uchar const *,ulong,bool,bool)
0x18002a532  mov     rcx, [rbp+818h]; this
0x18002a539  test    eax, eax
0x18002a53b  jns     short loc_18002A551
0x18002a53d  mov     r9d, eax; char *
0x18002a540  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002a547  mov     edx, 29Eh; void *
0x18002a54c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a551  mov     [rsp+910h+pAuthBuffer], r13
0x18002a556  mov     [rsp+910h+var_8B0], r13
0x18002a55b  mov     [rsp+910h+var_8A8], r13
0x18002a560  lea     r9, aUnattendxmlaut; "UnattendXmlAutoLogon"
0x18002a567  mov     r8, r15
0x18002a56a  lea     rdx, aSS_0; "%s\\%s"
0x18002a571  lea     rcx, [rsp+910h+pAuthBuffer]
0x18002a576  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002a57b  mov     ebx, eax
0x18002a57d  test    eax, eax
0x18002a57f  jns     short loc_18002A58B
0x18002a581  mov     r9d, eax
0x18002a584  mov     edx, 2A1h
0x18002a589  jmp     short loc_18002A5F9
0x18002a58b  mov     byte ptr [rsp+910h+pvData], r13b; bool
0x18002a590  mov     byte ptr [rsp+910h+pdwType], r13b; int
0x18002a595  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002a59c  mov     rdx, [rsp+910h+pAuthBuffer]; unsigned __int16 *
0x18002a5a1  mov     rcx, 0FFFFFFFF80000003h; HKEY
0x18002a5a8  call    ?TransferUnattendXmlAutologonValues@@YAJPEAUHKEY__@@PEBG01_N2@Z; TransferUnattendXmlAutologonValues(HKEY__ *,ushort const *,HKEY__ *,ushort const *,bool,bool)
0x18002a5ad  mov     ebx, eax
0x18002a5af  test    eax, eax
0x18002a5b1  jns     short loc_18002A5BD
0x18002a5b3  mov     r9d, eax
0x18002a5b6  mov     edx, 2A3h
0x18002a5bb  jmp     short loc_18002A5F9
0x18002a5bd  mov     r9d, 1
0x18002a5c3  lea     r8, aSystemautologo; "SystemAutoLogon"
0x18002a5ca  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002a5d1  lea     rcx, aWinlogon; "Winlogon"
0x18002a5d8  call    cs:__imp_SetPersistedRegistryBOOL
0x18002a5de  mov     ebx, eax
0x18002a5e0  test    eax, eax
0x18002a5e2  jle     short loc_18002A5ED
0x18002a5e4  movzx   ebx, ax
0x18002a5e7  or      ebx, 80070000h
0x18002a5ed  test    ebx, ebx
0x18002a5ef  jns     short loc_18002A61C
0x18002a5f1  mov     r9d, ebx; char *
0x18002a5f4  mov     edx, 2A7h; void *
0x18002a5f9  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002a600  mov     rcx, [rbp+818h]; this
0x18002a607  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a60c  nop
0x18002a60d  lea     rcx, [rsp+910h+pAuthBuffer]
0x18002a612  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002a617  jmp     loc_18002AB82
0x18002a61c  mov     byte ptr [rsi], 1
0x18002a61f  lea     rcx, [rsp+910h+pAuthBuffer]
0x18002a624  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002a629  jmp     loc_18002AB89
0x18002a62e  mov     [rsp+910h+var_8C0], r13d
0x18002a633  mov     r14d, 4
0x18002a639  mov     [rsp+910h+cbAuthBuffer], r14d
0x18002a63e  lea     rax, [rsp+910h+cbAuthBuffer]
0x18002a643  mov     [rsp+910h+pcbData], rax; pcbData
0x18002a648  lea     rax, [rsp+910h+var_8C0]
0x18002a64d  mov     [rsp+910h+pvData], rax; pvData
0x18002a652  mov     [rsp+910h+pdwType], r13; pdwType
0x18002a657  mov     r9d, 10010h; dwFlags
0x18002a65d  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18002a664  lea     rdx, aOsdataSoftware_0; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x18002a66b  mov     rcx, rdi; hkey
0x18002a66e  call    cs:__imp_RegGetValueW
0x18002a674  test    eax, eax
0x18002a676  jz      short loc_18002A6B3
0x18002a678  mov     [rsp+910h+cbAuthBuffer], r14d
0x18002a67d  lea     rax, [rsp+910h+cbAuthBuffer]
0x18002a682  mov     [rsp+910h+pcbData], rax; pcbData
0x18002a687  lea     rax, [rsp+910h+var_8C0]
0x18002a68c  mov     [rsp+910h+pvData], rax; pvData
0x18002a691  mov     [rsp+910h+pdwType], r13; pdwType
0x18002a696  mov     r9d, 20010010h; dwFlags
0x18002a69c  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18002a6a3  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002a6aa  mov     rcx, rdi; hkey
0x18002a6ad  call    cs:__imp_RegGetValueW
0x18002a6b3  cmp     [rsp+910h+var_8C0], r13d
0x18002a6b8  setnz   r14b
0x18002a6bc  cmp     ebx, 1
0x18002a6bf  jnz     loc_18002AAFE
0x18002a6c5  mov     [rsp+910h+var_8C0], r13d
0x18002a6ca  lea     rax, [rsp+910h+var_8C0]
0x18002a6cf  mov     [rsp+910h+pdwType], rax; int *
0x18002a6d4  lea     r8, aAutologoniscon; "AutologonIsConnected"
0x18002a6db  mov     rdx, r15; unsigned __int16 *
0x18002a6de  mov     rdi, 0FFFFFFFF80000003h
0x18002a6e5  mov     rcx, rdi; HKEY
0x18002a6e8  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18002a6ed  test    r14b, r14b
0x18002a6f0  jz      short loc_18002A6FD
0x18002a6f2  cmp     [rsp+910h+var_8C0], r13d
0x18002a6f7  jz      loc_18002AB86
0x18002a6fd  mov     ebx, 208h
0x18002a702  mov     r8d, ebx; Size
0x18002a705  xor     edx, edx; Val
0x18002a707  lea     rcx, [rbp+810h+var_650]; void *
0x18002a70e  call    memset_0
0x18002a713  mov     [rsp+910h+cbAuthBuffer], ebx
0x18002a717  lea     rax, [rsp+910h+cbAuthBuffer]
0x18002a71c  mov     [rsp+910h+pcbData], rax; pcbData
0x18002a721  lea     rax, [rbp+810h+var_650]
0x18002a728  mov     [rsp+910h+pvData], rax; pvData
0x18002a72d  mov     [rsp+910h+pdwType], r13; pdwType
0x18002a732  mov     r9d, 2; dwFlags
0x18002a738  lea     r8, aAutologonsigni; "AutologonSigninName"
0x18002a73f  mov     rdx, r15; lpSubKey
0x18002a742  mov     rcx, rdi; hkey
0x18002a745  call    cs:__imp_RegGetValueW
0x18002a74b  mov     ebx, eax
0x18002a74d  test    eax, eax
0x18002a74f  jz      short loc_18002A764
0x18002a751  mov     [rbp+810h+var_650], r13w
0x18002a759  jle     short loc_18002A764
0x18002a75b  movzx   ebx, ax
0x18002a75e  or      ebx, 80070000h
0x18002a764  test    ebx, ebx
0x18002a766  jns     short loc_18002A772
0x18002a768  mov     edx, 2BBh
0x18002a76d  jmp     loc_18002AB6C
0x18002a772  mov     [rsp+910h+pAuthBuffer], r13
0x18002a777  mov     [rsp+910h+cbAuthBuffer], r13d
0x18002a77c  xor     edx, edx
0x18002a77e  lea     rcx, [rsp+910h+pAuthBuffer]
0x18002a783  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002a788  lea     rax, [rsp+910h+cbAuthBuffer]
0x18002a78d  mov     [rsp+910h+pvData], rax; unsigned int *
0x18002a792  lea     rax, [rsp+910h+pAuthBuffer]
0x18002a797  mov     [rsp+910h+pdwType], rax; int
0x18002a79c  mov     r9d, 8; int
0x18002a7a2  lea     r8, aAutologonauthe; "AutologonAuthenticationBuffer"
0x18002a7a9  mov     rdx, r15; unsigned __int16 *
0x18002a7ac  mov     rcx, rdi; HKEY
0x18002a7af  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18002a7b4  mov     ebx, eax
0x18002a7b6  test    eax, eax
0x18002a7b8  jns     short loc_18002A7DA
0x18002a7ba  mov     rcx, [rbp+818h]; this
0x18002a7c1  mov     r9d, eax; char *
0x18002a7c4  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002a7cb  mov     edx, 2BFh; void *
0x18002a7d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a7d5  jmp     loc_18002AACB
0x18002a7da  mov     edi, [rsp+910h+cbAuthBuffer]
0x18002a7de  lea     rax, [rsp+910h+pAuthBuffer]
0x18002a7e3  mov     [rsp+910h+var_898], rax
0x18002a7e8  mov     [rbp+810h+var_890], edi
0x18002a7eb  mov     eax, dword ptr [rsp+910h+var_8B0+4]
0x18002a7ef  mov     [rbp+810h+var_88C], eax
0x18002a7f2  mov     [rbp+810h+var_888], 1
0x18002a7f6  cmp     [rsp+910h+var_8C0], r13d
0x18002a7fb  jz      short loc_18002A867
0x18002a7fd  xor     r14b, 1
0x18002a801  mov     byte ptr [rsp+910h+pvData], r14b; bool
0x18002a806  mov     byte ptr [rsp+910h+pdwType], 1; int
0x18002a80b  mov     r9d, edi; unsigned int
0x18002a80e  mov     r8, [rsp+910h+pAuthBuffer]; unsigned __int8 *
0x18002a813  xor     edx, edx; unsigned __int16 *
0x18002a815  lea     rcx, [rbp+810h+var_650]; unsigned __int16 *
0x18002a81c  call    ?SetAutologonDetails@@YAJPEBG0PEBEK_N2@Z; SetAutologonDetails(ushort const *,ushort const *,uchar const *,ulong,bool,bool)
0x18002a821  mov     ebx, eax
0x18002a823  test    eax, eax
0x18002a825  jns     loc_18002A8B5
0x18002a82b  mov     rcx, [rbp+818h]; this
0x18002a832  mov     r9d, eax; char *
0x18002a835  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002a83c  mov     edx, 2C9h; void *
0x18002a841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a846  nop
0x18002a847  mov     edx, edi
0x18002a849  mov     rcx, [rsp+910h+pAuthBuffer]
0x18002a84e  test    edi, edi
0x18002a850  jz      loc_18002AACB
0x18002a856  mov     [rcx], r13b
0x18002a859  inc     rcx
0x18002a85c  sub     rdx, 1
0x18002a860  jnz     short loc_18002A856
0x18002a862  jmp     loc_18002AACB
0x18002a867  test    edi, edi
0x18002a869  jnz     short loc_18002A8BD
0x18002a86b  mov     byte ptr [rsp+910h+pvData], 1; bool
0x18002a870  mov     byte ptr [rsp+910h+pdwType], r13b; int
0x18002a875  xor     r9d, r9d; unsigned int
0x18002a878  xor     r8d, r8d; unsigned __int8 *
0x18002a87b  lea     rdx, qword_180054928; unsigned __int16 *
0x18002a882  lea     rcx, [rbp+810h+var_650]; unsigned __int16 *
0x18002a889  call    ?SetAutologonDetails@@YAJPEBG0PEBEK_N2@Z; SetAutologonDetails(ushort const *,ushort const *,uchar const *,ulong,bool,bool)
0x18002a88e  mov     ebx, eax
0x18002a890  test    eax, eax
0x18002a892  jns     short loc_18002A8B5
0x18002a894  mov     rcx, [rbp+818h]; this
0x18002a89b  mov     r9d, eax; char *
0x18002a89e  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002a8a5  mov     edx, 2D5h; void *
0x18002a8aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a8af  nop
0x18002a8b0  jmp     loc_18002AACB
0x18002a8b5  mov     byte ptr [rsi], 1
0x18002a8b8  jmp     loc_18002AA87
0x18002a8bd  mov     ebx, 202h
0x18002a8c2  mov     r8d, ebx; Size
0x18002a8c5  xor     edx, edx; Val
0x18002a8c7  lea     rcx, [rbp+810h+pszUserName]; void *
0x18002a8ce  call    memset_0
0x18002a8d3  xor     edx, edx; Val
0x18002a8d5  lea     r8d, [rbx-2]; Size
0x18002a8d9  lea     rcx, [rbp+810h+pszDomainName]; void *
0x18002a8e0  call    memset_0
0x18002a8e5  mov     r8d, ebx; Size
0x18002a8e8  xor     edx, edx; Val
0x18002a8ea  lea     rcx, [rbp+810h+var_860]; void *
0x18002a8ee  call    memset_0
0x18002a8f3  mov     eax, 101h
0x18002a8f8  mov     [rsp+910h+pcchMaxUserName], eax
0x18002a8fc  mov     [rsp+910h+pcchMaxDomainName], 100h
0x18002a904  mov     [rsp+910h+var_8C0], eax
0x18002a908  call    cs:__imp_CoImpersonateClient
0x18002a90e  mov     ebx, eax
0x18002a910  test    eax, eax
0x18002a912  jns     short loc_18002A949
0x18002a914  mov     rcx, [rbp+818h]; this
0x18002a91b  mov     r9d, eax; char *
0x18002a91e  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002a925  mov     edx, 2E2h; void *
0x18002a92a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a92f  nop
0x18002a930  mov     rdx, rdi
0x18002a933  mov     rcx, [rsp+910h+pAuthBuffer]
0x18002a938  mov     [rcx], r13b
0x18002a93b  inc     rcx
0x18002a93e  sub     rdx, 1
0x18002a942  jnz     short loc_18002A938
0x18002a944  jmp     loc_18002AACB
0x18002a949  mov     byte ptr [rsp+910h+cbAuthBuffer+1], 1
0x18002a94e  lea     rax, [rsp+910h+var_8C0]
0x18002a953  mov     [rsp+910h+pcchMaxPassword], rax; pcchMaxPassword
0x18002a958  lea     rax, [rbp+810h+var_860]
0x18002a95c  mov     [rsp+910h+pszPassword], rax; pszPassword
0x18002a961  lea     rax, [rsp+910h+pcchMaxDomainName]
0x18002a966  mov     [rsp+910h+pcbData], rax; pcchMaxDomainName
0x18002a96b  lea     rax, [rbp+810h+pszDomainName]
0x18002a972  mov     [rsp+910h+pvData], rax; pszDomainName
0x18002a977  lea     rax, [rsp+910h+pcchMaxUserName]
0x18002a97c  mov     [rsp+910h+pdwType], rax; pcchMaxUserName
0x18002a981  lea     r9, [rbp+810h+pszUserName]; pszUserName
0x18002a988  mov     r8d, edi; cbAuthBuffer
0x18002a98b  mov     rdx, [rsp+910h+pAuthBuffer]; pAuthBuffer
0x18002a990  mov     ecx, 1; dwFlags
0x18002a995  call    cs:__imp_CredUnPackAuthenticationBufferW
0x18002a99b  test    eax, eax
0x18002a99d  jnz     short loc_18002A9D9
  ... truncated ...
```
