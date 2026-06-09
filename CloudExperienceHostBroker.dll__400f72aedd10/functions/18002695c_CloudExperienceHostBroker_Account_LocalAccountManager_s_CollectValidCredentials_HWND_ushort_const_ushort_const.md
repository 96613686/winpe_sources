# CloudExperienceHostBroker::Account::LocalAccountManager::s_CollectValidCredentials(HWND__ *,ushort const *,ushort const *)

- ea: `0x18002695c`
- end: `0x180026f2d`
- name: `?s_CollectValidCredentials@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEAUHWND__@@PEBG1@Z`
- size: `1489`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022ec4`

## callees

- `0x180008320`
- `0x180008344`
- `0x180009f30`
- `0x18000a8fc`
- `0x18000e6f4`
- `0x180012408`
- `0x1800224b8`
- `0x18002255c`
- `0x1800251d0`
- `0x18002695c`
- `0x180027510`
- `0x180035a5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026c71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026dd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026e57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026c71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026dd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026e57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026b12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026b12`
- `SspiCli!LsaConnectUntrusted` at `0x1800269d9`
- `SspiCli!LsaConnectUntrusted` at `0x1800269d9`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180026cbc`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180026ee7`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180026cbc`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180026ee7`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180026a5f`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180026a5f`
- `credui!CredPackAuthenticationBufferW` at `0x180026b04`
- `credui!CredPackAuthenticationBufferW` at `0x180026b41`
- `credui!CredPackAuthenticationBufferW` at `0x180026b04`
- `credui!CredPackAuthenticationBufferW` at `0x180026b41`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x180026bd0`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x180026bd0`
- `credui!CredUnPackAuthenticationBufferW` at `0x180026c29`
- `credui!CredUnPackAuthenticationBufferW` at `0x180026c29`

## string_xrefs

- `0x1800269ed`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180026a73`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180026ce4`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180026d45`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180026d9d`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180026e98`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CloudExperienceHostBroker::Account::LocalAccountManager::s_CollectValidCredentials(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  NTSTATUS v6; // eax
  int LastError; // edi
  void *v8; // rbx
  __int64 v9; // rax
  NTSTATUS v10; // eax
  _BYTE *v11; // rcx
  int v12; // esi
  void *v13; // rax
  const char *v14; // r9
  DWORD v15; // edx
  DWORD v16; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  const char *v19; // r9
  _BYTE *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rax
  _BYTE *v24; // rcx
  __int64 v25; // rdx
  _BYTE *v26; // rcx
  __int64 v27; // rax
  _BYTE *v28; // rcx
  __int64 v29; // rdx
  _BYTE *v30; // rcx
  __int64 v31; // rax
  _BYTE *v32; // rcx
  __int64 v33; // rdx
  _BYTE *v34; // rcx
  __int64 v35; // rax
  _BYTE *v36; // rcx
  __int64 v37; // rax
  int pcbPackedCredentials; // [rsp+20h] [rbp-E0h]
  int pcbPackedCredentialsa; // [rsp+20h] [rbp-E0h]
  unsigned int pcbPackedCredentialsb; // [rsp+20h] [rbp-E0h]
  DWORD ulInAuthBufferSize; // [rsp+50h] [rbp-B0h] BYREF
  LPCVOID pvInAuthBuffer; // [rsp+58h] [rbp-A8h] BYREF
  ULONG cbAuthBuffer; // [rsp+60h] [rbp-A0h] BYREF
  PVOID pAuthBuffer; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR pszUserName; // [rsp+70h] [rbp-90h] BYREF
  ULONG AuthenticationPackage; // [rsp+78h] [rbp-88h] BYREF
  DWORD pcchMaxPassword; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD pcchMaxUserName; // [rsp+80h] [rbp-80h] BYREF
  void *LsaHandle; // [rsp+88h] [rbp-78h] BYREF
  struct _LSA_STRING PackageName; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v51[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v52[2]; // [rsp+B0h] [rbp-50h] BYREF
  LPWSTR *p_pszUserName; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-38h] BYREF
  char v55; // [rsp+D0h] [rbp-30h]
  _CREDUI_INFOW pUiInfo; // [rsp+D8h] [rbp-28h] BYREF
  void *v57; // [rsp+100h] [rbp+0h]
  char v58; // [rsp+108h] [rbp+8h]
  LPCVOID *p_pvInAuthBuffer; // [rsp+110h] [rbp+10h]
  DWORD *p_ulInAuthBufferSize; // [rsp+118h] [rbp+18h]
  char v61; // [rsp+120h] [rbp+20h]
  PVOID *p_pAuthBuffer; // [rsp+128h] [rbp+28h]
  ULONG *p_cbAuthBuffer; // [rsp+130h] [rbp+30h]
  char v64; // [rsp+138h] [rbp+38h]
  char v65[16]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR pszPassword[264]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR v67[264]; // [rsp+360h] [rbp+260h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5B8h] [rbp+4B8h]

  v67[0] = 0;
  v52[0] = v67;
  v52[1] = 514;
  v51[0] = pszPassword;
  v51[1] = 514;
  memset_0(pszPassword, 0, 0x101u);
  LsaHandle = 0;
  v6 = LsaConnectUntrusted(&LsaHandle);
  if ( v6 >= 0 )
  {
    v8 = LsaHandle;
    v57 = LsaHandle;
    v58 = 1;
    strcpy(v65, "Negotiate");
    *(_QWORD *)&PackageName.Length = 0;
    PackageName.Buffer = v65;
    v9 = -1;
    do
      ++v9;
    while ( v65[v9] );
    PackageName.MaximumLength = v9;
    PackageName.Length = v9;
    AuthenticationPackage = 0;
    v10 = LsaLookupAuthenticationPackage(LsaHandle, &PackageName, &AuthenticationPackage);
    if ( v10 >= 0 )
    {
      pcchMaxUserName = 0;
      pcchMaxPassword = 0;
      v12 = 0;
      while ( 1 )
      {
        pvInAuthBuffer = 0;
        ulInAuthBufferSize = 0;
        p_pvInAuthBuffer = &pvInAuthBuffer;
        p_ulInAuthBufferSize = &ulInAuthBufferSize;
        v61 = 1;
        pszUserName = 0;
        p_pszUserName = &pszUserName;
        v54 = 0;
        v55 = 1;
        LastError = SHGetUserName(v11, &v54);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pszUserName);
        if ( LastError < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x155,
            (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
            (const char *)(unsigned int)LastError,
            pcbPackedCredentials);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszUserName);
          v36 = pvInAuthBuffer;
          if ( pvInAuthBuffer )
          {
            v37 = ulInAuthBufferSize;
            if ( ulInAuthBufferSize )
            {
              do
              {
                *v36++ = 0;
                --v37;
              }
              while ( v37 );
              goto LABEL_53;
            }
          }
          goto LABEL_54;
        }
        if ( !CredPackAuthenticationBufferW(0, pszUserName, (LPWSTR)&::pszPassword, 0, &ulInAuthBufferSize) )
        {
          v13 = CoTaskMemAlloc(ulInAuthBufferSize);
          pvInAuthBuffer = v13;
          if ( !v13 )
          {
            LastError = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x15A,
              (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
              (const char *)0x8007000ELL,
              pcbPackedCredentialsa);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszUserName);
            v26 = pvInAuthBuffer;
            if ( pvInAuthBuffer )
            {
              v27 = ulInAuthBufferSize;
              if ( ulInAuthBufferSize )
              {
                do
                {
                  *v26++ = 0;
                  --v27;
                }
                while ( v27 );
                goto LABEL_53;
              }
            }
            goto LABEL_54;
          }
          if ( !CredPackAuthenticationBufferW(0, pszUserName, (LPWSTR)&::pszPassword, (PBYTE)v13, &ulInAuthBufferSize) )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x15B,
                          (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
                          v14);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszUserName);
            v24 = pvInAuthBuffer;
            if ( pvInAuthBuffer )
            {
              v25 = ulInAuthBufferSize;
              if ( ulInAuthBufferSize )
              {
                do
                {
                  *v24++ = 0;
                  --v25;
                }
                while ( v25 );
                goto LABEL_53;
              }
            }
            goto LABEL_54;
          }
        }
        *(_QWORD *)&pUiInfo.cbSize = 40;
        pUiInfo.hbmBanner = 0;
        pUiInfo.hwndParent = a1;
        pUiInfo.pszCaptionText = a2;
        pUiInfo.pszMessageText = a3;
        pAuthBuffer = 0;
        cbAuthBuffer = 0;
        p_pAuthBuffer = &pAuthBuffer;
        p_cbAuthBuffer = &cbAuthBuffer;
        v64 = 1;
        v15 = (unsigned __int16)v12;
        if ( (v12 & 0x1FFF0000) != 0x70000 )
          v15 = v12;
        v16 = CredUIPromptForWindowsCredentialsW(
                &pUiInfo,
                v15,
                &AuthenticationPackage,
                pvInAuthBuffer,
                ulInAuthBufferSize,
                &pAuthBuffer,
                &cbAuthBuffer,
                0,
                0x8000021u);
        if ( v16 )
          break;
        pcchMaxUserName = 257;
        pcchMaxPassword = 257;
        if ( !CredUnPackAuthenticationBufferW(
                1u,
                pAuthBuffer,
                cbAuthBuffer,
                v67,
                &pcchMaxUserName,
                0,
                0,
                pszPassword,
                &pcchMaxPassword) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x185,
                        (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
                        v19);
          v28 = pAuthBuffer;
          if ( pAuthBuffer )
          {
            v29 = cbAuthBuffer;
            if ( cbAuthBuffer )
            {
              do
              {
                *v28++ = 0;
                --v29;
              }
              while ( v29 );
              CoTaskMemFree(pAuthBuffer);
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszUserName);
          v30 = pvInAuthBuffer;
          if ( pvInAuthBuffer )
          {
            v31 = ulInAuthBufferSize;
            if ( ulInAuthBufferSize )
            {
              do
              {
                *v30++ = 0;
                --v31;
              }
              while ( v31 );
LABEL_53:
              CoTaskMemFree((LPVOID)pvInAuthBuffer);
              goto LABEL_54;
            }
          }
          goto LABEL_54;
        }
        v12 = CloudExperienceHostBroker::Account::LocalAccountManager::s_ValidatePassword(v67, pszPassword);
        v20 = pAuthBuffer;
        if ( pAuthBuffer )
        {
          v21 = cbAuthBuffer;
          if ( cbAuthBuffer )
          {
            do
            {
              *v20++ = 0;
              --v21;
            }
            while ( v21 );
            CoTaskMemFree(pAuthBuffer);
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszUserName);
        v11 = pvInAuthBuffer;
        if ( pvInAuthBuffer )
        {
          v22 = ulInAuthBufferSize;
          if ( ulInAuthBufferSize )
          {
            do
            {
              *v11++ = 0;
              --v22;
            }
            while ( v22 );
            CoTaskMemFree((LPVOID)pvInAuthBuffer);
          }
        }
        if ( v12 >= 0 )
        {
          LsaDeregisterLogonProcess(v8);
          __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(v51);
          __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(v52);
          return 0;
        }
      }
      LastError = wil::details::in1diag3::Return_Win32(retaddr, v17, v18, (const char *)v16, pcbPackedCredentialsb);
      v32 = pAuthBuffer;
      if ( pAuthBuffer )
      {
        v33 = cbAuthBuffer;
        if ( cbAuthBuffer )
        {
          do
          {
            *v32++ = 0;
            --v33;
          }
          while ( v33 );
          CoTaskMemFree(pAuthBuffer);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszUserName);
      v34 = pvInAuthBuffer;
      if ( pvInAuthBuffer )
      {
        v35 = ulInAuthBufferSize;
        if ( ulInAuthBufferSize )
        {
          do
          {
            *v34++ = 0;
            --v35;
          }
          while ( v35 );
          goto LABEL_53;
        }
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x141,
                    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
                    (const char *)(unsigned int)v10,
                    pcbPackedCredentials);
    }
LABEL_54:
    LsaDeregisterLogonProcess(v8);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x136,
                  (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
                  (const char *)(unsigned int)v6,
                  pcbPackedCredentials);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(v51);
  __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(v52);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002695c  mov     [rsp-8+arg_18], rbx
0x180026961  push    rbp
0x180026962  push    rsi
0x180026963  push    rdi
0x180026964  push    r12
0x180026966  push    r13
0x180026968  push    r14
0x18002696a  push    r15
0x18002696c  lea     rbp, [rsp-480h]
0x180026974  sub     rsp, 580h
0x18002697b  mov     rax, cs:__security_cookie
0x180026982  xor     rax, rsp
0x180026985  mov     [rbp+4B0h+var_40], rax
0x18002698c  mov     r12, r8
0x18002698f  mov     r15, rdx
0x180026992  mov     r14, rcx
0x180026995  xor     r13d, r13d
0x180026998  mov     [rbp+4B0h+var_250], r13w
0x1800269a0  lea     rax, [rbp+4B0h+var_250]
0x1800269a7  mov     [rbp+4B0h+var_500], rax
0x1800269ab  mov     ecx, 202h
0x1800269b0  mov     [rbp+4B0h+var_4F8], rcx
0x1800269b4  lea     rax, [rbp+4B0h+pszPassword]
0x1800269b8  mov     [rbp+4B0h+var_510], rax
0x1800269bc  mov     [rbp+4B0h+var_508], rcx
0x1800269c0  xor     edx, edx; Val
0x1800269c2  mov     r8d, 101h; Size
0x1800269c8  lea     rcx, [rbp+4B0h+pszPassword]; void *
0x1800269cc  call    memset_0
0x1800269d1  mov     [rbp+4B0h+LsaHandle], r13
0x1800269d5  lea     rcx, [rbp+4B0h+LsaHandle]; LsaHandle
0x1800269d9  call    cs:__imp_LsaConnectUntrusted
0x1800269df  test    eax, eax
0x1800269e1  jns     short loc_180026A05
0x1800269e3  mov     rcx, [rbp+4B8h]; this
0x1800269ea  mov     r9d, eax; char *
0x1800269ed  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800269f4  mov     edx, 136h; void *
0x1800269f9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800269fe  mov     edi, eax
0x180026a00  jmp     loc_180026EEE
0x180026a05  mov     rbx, [rbp+4B0h+LsaHandle]
0x180026a09  mov     [rbp+4B0h+var_4B0], rbx
0x180026a0d  mov     [rbp+4B0h+var_4A8], 1
0x180026a11  movsd   xmm0, qword ptr cs:aNegotiate; "Negotiate"
0x180026a19  movsd   qword ptr [rbp+4B0h+var_470], xmm0
0x180026a1e  movzx   eax, word ptr cs:aNegotiate+8; "e"
0x180026a25  mov     word ptr [rbp+4B0h+var_470+8], ax
0x180026a29  mov     qword ptr [rbp+4B0h+PackageName.Length], r13
0x180026a2d  lea     rax, [rbp+4B0h+var_470]
0x180026a31  mov     [rbp+4B0h+PackageName.Buffer], rax
0x180026a35  lea     rcx, [rbp+4B0h+var_470]
0x180026a39  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026a3d  inc     rax
0x180026a40  cmp     [rcx+rax], r13b
0x180026a44  jnz     short loc_180026A3D
0x180026a46  mov     [rbp+4B0h+PackageName.MaximumLength], ax
0x180026a4a  mov     [rbp+4B0h+PackageName.Length], ax
0x180026a4e  mov     [rsp+5B0h+AuthenticationPackage], r13d
0x180026a53  lea     r8, [rsp+5B0h+AuthenticationPackage]; AuthenticationPackage
0x180026a58  lea     rdx, [rbp+4B0h+PackageName]; PackageName
0x180026a5c  mov     rcx, rbx; LsaHandle
0x180026a5f  call    cs:__imp_LsaLookupAuthenticationPackage
0x180026a65  test    eax, eax
0x180026a67  jns     short loc_180026A8B
0x180026a69  mov     rcx, [rbp+4B8h]; this
0x180026a70  mov     r9d, eax; char *
0x180026a73  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180026a7a  mov     edx, 141h; void *
0x180026a7f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180026a84  mov     edi, eax
0x180026a86  jmp     loc_180026EE4
0x180026a8b  mov     [rbp+4B0h+pcchMaxUserName], r13d
0x180026a8f  mov     [rsp+5B0h+pcchMaxPassword], r13d
0x180026a94  mov     esi, r13d
0x180026a97  mov     [rsp+5B0h+pvInAuthBuffer], r13
0x180026a9c  mov     [rsp+5B0h+ulInAuthBufferSize], r13d
0x180026aa1  lea     rax, [rsp+5B0h+pvInAuthBuffer]
0x180026aa6  mov     [rbp+4B0h+var_4A0], rax
0x180026aaa  lea     rax, [rsp+5B0h+ulInAuthBufferSize]
0x180026aaf  mov     [rbp+4B0h+var_498], rax
0x180026ab3  mov     [rbp+4B0h+var_490], 1
0x180026ab7  mov     [rsp+5B0h+pszUserName], r13
0x180026abc  lea     rax, [rsp+5B0h+pszUserName]
0x180026ac1  mov     [rbp+4B0h+var_4F0], rax
0x180026ac5  mov     [rbp+4B0h+var_4E8], r13
0x180026ac9  mov     [rbp+4B0h+var_4E0], 1
0x180026acd  lea     rdx, [rbp+4B0h+var_4E8]
0x180026ad1  call    SHGetUserName
0x180026ad6  mov     edi, eax
0x180026ad8  lea     rcx, [rbp+4B0h+var_4F0]
0x180026adc  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180026ae1  test    edi, edi
0x180026ae3  js      loc_180026E8E
0x180026ae9  lea     rax, [rsp+5B0h+ulInAuthBufferSize]
0x180026aee  mov     [rsp+5B0h+pcbPackedCredentials], rax; int
0x180026af3  xor     r9d, r9d; pPackedCredentials
0x180026af6  lea     r8, pszPassword; pszPassword
0x180026afd  mov     rdx, [rsp+5B0h+pszUserName]; pszUserName
0x180026b02  xor     ecx, ecx; dwFlags
0x180026b04  call    cs:__imp_CredPackAuthenticationBufferW
0x180026b0a  test    eax, eax
0x180026b0c  jnz     short loc_180026B4F
0x180026b0e  mov     ecx, [rsp+5B0h+ulInAuthBufferSize]; cb
0x180026b12  call    cs:__imp_CoTaskMemAlloc
0x180026b18  mov     [rsp+5B0h+pvInAuthBuffer], rax
0x180026b1d  test    rax, rax
0x180026b20  jz      loc_180026D36
0x180026b26  lea     rcx, [rsp+5B0h+ulInAuthBufferSize]
0x180026b2b  mov     [rsp+5B0h+pcbPackedCredentials], rcx; pcbPackedCredentials
0x180026b30  mov     r9, rax; pPackedCredentials
0x180026b33  lea     r8, pszPassword; pszPassword
0x180026b3a  mov     rdx, [rsp+5B0h+pszUserName]; pszUserName
0x180026b3f  xor     ecx, ecx; dwFlags
0x180026b41  call    cs:__imp_CredPackAuthenticationBufferW
0x180026b47  test    eax, eax
0x180026b49  jz      loc_180026CDD
0x180026b4f  mov     qword ptr [rbp+4B0h+pUiInfo.cbSize], 28h ; '('
0x180026b57  mov     [rbp+4B0h+pUiInfo.hbmBanner], r13
0x180026b5b  mov     [rbp+4B0h+pUiInfo.hwndParent], r14
0x180026b5f  mov     [rbp+4B0h+pUiInfo.pszCaptionText], r15
0x180026b63  mov     [rbp+4B0h+pUiInfo.pszMessageText], r12
0x180026b67  mov     [rsp+5B0h+pAuthBuffer], r13
0x180026b6c  mov     [rsp+5B0h+cbAuthBuffer], r13d
0x180026b71  lea     rax, [rsp+5B0h+pAuthBuffer]
0x180026b76  mov     [rbp+4B0h+var_488], rax
0x180026b7a  lea     rax, [rsp+5B0h+cbAuthBuffer]
0x180026b7f  mov     [rbp+4B0h+var_480], rax
0x180026b83  mov     [rbp+4B0h+var_478], 1
0x180026b87  mov     ecx, [rsp+5B0h+ulInAuthBufferSize]
0x180026b8b  mov     eax, esi
0x180026b8d  and     eax, 1FFF0000h
0x180026b92  movzx   edx, si
0x180026b95  cmp     eax, 70000h
0x180026b9a  cmovnz  edx, esi; dwAuthError
0x180026b9d  mov     [rsp+5B0h+dwFlags], 8000021h; dwFlags
0x180026ba5  mov     [rsp+5B0h+pfSave], r13; pfSave
0x180026baa  lea     rax, [rsp+5B0h+cbAuthBuffer]
0x180026baf  mov     [rsp+5B0h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x180026bb4  lea     rax, [rsp+5B0h+pAuthBuffer]
0x180026bb9  mov     [rsp+5B0h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x180026bbe  mov     dword ptr [rsp+5B0h+pcbPackedCredentials], ecx; unsigned int
0x180026bc2  mov     r9, [rsp+5B0h+pvInAuthBuffer]; pvInAuthBuffer
0x180026bc7  lea     r8, [rsp+5B0h+AuthenticationPackage]; pulAuthPackage
0x180026bcc  lea     rcx, [rbp+4B0h+pUiInfo]; pUiInfo
0x180026bd0  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x180026bd6  test    eax, eax
0x180026bd8  jnz     loc_180026E1E
0x180026bde  mov     [rbp+4B0h+pcchMaxUserName], 101h
0x180026be5  mov     [rsp+5B0h+pcchMaxPassword], 101h
0x180026bed  lea     rax, [rsp+5B0h+pcchMaxPassword]
0x180026bf2  mov     qword ptr [rsp+5B0h+dwFlags], rax; pcchMaxPassword
0x180026bf7  lea     rax, [rbp+4B0h+pszPassword]
0x180026bfb  mov     [rsp+5B0h+pfSave], rax; pszPassword
0x180026c00  mov     [rsp+5B0h+pulOutAuthBufferSize], r13; pcchMaxDomainName
0x180026c05  mov     [rsp+5B0h+ppvOutAuthBuffer], r13; pszDomainName
0x180026c0a  lea     rax, [rbp+4B0h+pcchMaxUserName]
0x180026c0e  mov     [rsp+5B0h+pcbPackedCredentials], rax; pcchMaxUserName
0x180026c13  lea     r9, [rbp+4B0h+var_250]; pszUserName
0x180026c1a  mov     r8d, [rsp+5B0h+cbAuthBuffer]; cbAuthBuffer
0x180026c1f  mov     rdx, [rsp+5B0h+pAuthBuffer]; pAuthBuffer
0x180026c24  mov     ecx, 1; dwFlags
0x180026c29  call    cs:__imp_CredUnPackAuthenticationBufferW
0x180026c2f  test    eax, eax
0x180026c31  jz      loc_180026D96
0x180026c37  lea     rdx, [rbp+4B0h+pszPassword]; unsigned __int16 *
0x180026c3b  lea     rcx, [rbp+4B0h+var_250]; unsigned __int16 *
0x180026c42  call    ?s_ValidatePassword@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEBG0@Z; CloudExperienceHostBroker::Account::LocalAccountManager::s_ValidatePassword(ushort const *,ushort const *)
0x180026c47  mov     esi, eax
0x180026c49  mov     rcx, [rsp+5B0h+pAuthBuffer]
0x180026c4e  test    rcx, rcx
0x180026c51  jz      short loc_180026C78
0x180026c53  mov     edx, [rsp+5B0h+cbAuthBuffer]
0x180026c57  test    edx, edx
0x180026c59  jz      short loc_180026C78
0x180026c5b  test    rdx, rdx
0x180026c5e  jz      short loc_180026C71
0x180026c60  mov     [rcx], r13b
0x180026c63  inc     rcx
0x180026c66  sub     rdx, 1
0x180026c6a  jnz     short loc_180026C60
0x180026c6c  mov     rcx, [rsp+5B0h+pAuthBuffer]; pv
0x180026c71  call    cs:__imp_CoTaskMemFree
0x180026c77  nop
0x180026c78  lea     rcx, [rsp+5B0h+pszUserName]
0x180026c7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026c82  nop
0x180026c83  mov     rcx, [rsp+5B0h+pvInAuthBuffer]
0x180026c88  test    rcx, rcx
0x180026c8b  jz      short loc_180026CB1
0x180026c8d  mov     eax, [rsp+5B0h+ulInAuthBufferSize]
0x180026c91  test    eax, eax
0x180026c93  jz      short loc_180026CB1
0x180026c95  test    rax, rax
0x180026c98  jz      short loc_180026CAB
0x180026c9a  mov     [rcx], r13b
0x180026c9d  inc     rcx
0x180026ca0  sub     rax, 1
0x180026ca4  jnz     short loc_180026C9A
0x180026ca6  mov     rcx, [rsp+5B0h+pvInAuthBuffer]; pv
0x180026cab  call    cs:__imp_CoTaskMemFree
0x180026cb1  test    esi, esi
0x180026cb3  js      loc_180026A97
0x180026cb9  mov     rcx, rbx; LsaHandle
0x180026cbc  call    cs:__imp_LsaDeregisterLogonProcess
0x180026cc2  nop
0x180026cc3  lea     rcx, [rbp+4B0h+var_510]
0x180026cc7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXUSecureZeroData@details@wil@@@_E$1?Close@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U123@PEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026ccc  nop
0x180026ccd  lea     rcx, [rbp+4B0h+var_500]
0x180026cd1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXUSecureZeroData@details@wil@@@_E$1?Close@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U123@PEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026cd6  xor     eax, eax
0x180026cd8  jmp     loc_180026F03
0x180026cdd  mov     rcx, [rbp+4B8h]; this
0x180026ce4  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180026ceb  mov     edx, 15Bh; void *
0x180026cf0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026cf5  mov     edi, eax
0x180026cf7  lea     rcx, [rsp+5B0h+pszUserName]
0x180026cfc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026d01  nop
0x180026d02  mov     rcx, [rsp+5B0h+pvInAuthBuffer]
0x180026d07  test    rcx, rcx
0x180026d0a  jz      loc_180026EE4
0x180026d10  mov     edx, [rsp+5B0h+ulInAuthBufferSize]
0x180026d14  test    edx, edx
0x180026d16  jz      loc_180026EE4
0x180026d1c  test    rdx, rdx
0x180026d1f  jz      loc_180026EDD
0x180026d25  mov     [rcx], r13b
0x180026d28  inc     rcx
0x180026d2b  sub     rdx, 1
0x180026d2f  jnz     short loc_180026D25
0x180026d31  jmp     loc_180026ED8
0x180026d36  mov     rcx, [rbp+4B8h]; this
0x180026d3d  mov     edi, 8007000Eh
0x180026d42  mov     r9d, edi; char *
0x180026d45  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180026d4c  mov     edx, 15Ah; void *
0x180026d51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d56  nop
0x180026d57  lea     rcx, [rsp+5B0h+pszUserName]
0x180026d5c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026d61  nop
0x180026d62  mov     rcx, [rsp+5B0h+pvInAuthBuffer]
0x180026d67  test    rcx, rcx
0x180026d6a  jz      loc_180026EE4
0x180026d70  mov     eax, [rsp+5B0h+ulInAuthBufferSize]
0x180026d74  test    eax, eax
0x180026d76  jz      loc_180026EE4
0x180026d7c  test    rax, rax
0x180026d7f  jz      loc_180026EDD
0x180026d85  mov     [rcx], r13b
0x180026d88  inc     rcx
0x180026d8b  sub     rax, 1
0x180026d8f  jnz     short loc_180026D85
0x180026d91  jmp     loc_180026ED8
0x180026d96  mov     rcx, [rbp+4B8h]; this
0x180026d9d  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180026da4  mov     edx, 185h; void *
0x180026da9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026dae  mov     edi, eax
0x180026db0  mov     rcx, [rsp+5B0h+pAuthBuffer]
0x180026db5  test    rcx, rcx
0x180026db8  jz      short loc_180026DDF
0x180026dba  mov     edx, [rsp+5B0h+cbAuthBuffer]
0x180026dbe  test    edx, edx
0x180026dc0  jz      short loc_180026DDF
0x180026dc2  test    rdx, rdx
0x180026dc5  jz      short loc_180026DD8
0x180026dc7  mov     [rcx], r13b
0x180026dca  inc     rcx
0x180026dcd  sub     rdx, 1
0x180026dd1  jnz     short loc_180026DC7
0x180026dd3  mov     rcx, [rsp+5B0h+pAuthBuffer]; pv
0x180026dd8  call    cs:__imp_CoTaskMemFree
0x180026dde  nop
0x180026ddf  lea     rcx, [rsp+5B0h+pszUserName]
0x180026de4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026de9  nop
0x180026dea  mov     rcx, [rsp+5B0h+pvInAuthBuffer]
0x180026def  test    rcx, rcx
0x180026df2  jz      loc_180026EE4
0x180026df8  mov     eax, [rsp+5B0h+ulInAuthBufferSize]
0x180026dfc  test    eax, eax
0x180026dfe  jz      loc_180026EE4
0x180026e04  test    rax, rax
0x180026e07  jz      loc_180026EDD
0x180026e0d  mov     [rcx], r13b
0x180026e10  inc     rcx
0x180026e13  sub     rax, 1
0x180026e17  jnz     short loc_180026E0D
0x180026e19  jmp     loc_180026ED8
0x180026e1e  mov     rcx, [rbp+4B8h]; this
0x180026e25  mov     r9d, eax; char *
0x180026e28  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026e2d  mov     edi, eax
0x180026e2f  mov     rcx, [rsp+5B0h+pAuthBuffer]
0x180026e34  test    rcx, rcx
0x180026e37  jz      short loc_180026E5E
  ... truncated ...
```
