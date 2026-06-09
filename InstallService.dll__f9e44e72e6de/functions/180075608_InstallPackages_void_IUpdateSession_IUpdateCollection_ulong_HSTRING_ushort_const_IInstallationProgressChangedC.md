# InstallPackages(void *,IUpdateSession *,IUpdateCollection *,ulong,HSTRING__ *,ushort const *,IInstallationProgressChangedCallback *,IInstallationCompletedCallback *,char const *,IUpdateInstaller * *,IInstallationJob * *)

- ea: `0x180075608`
- end: `0x180075eb5`
- name: `?InstallPackages@@YAJPEAXPEAUIUpdateSession@@PEAUIUpdateCollection@@KPEAUHSTRING__@@PEBGPEAUIInstallationProgressChangedCallback@@PEAUIInstallationCompletedCallback@@PEBDPEAPEAUIUpdateInstaller@@PEAPEAUIInstallationJob@@@Z`
- size: `2221`
- prototype: `__int64 __fastcall(void *, struct IUpdateSession *, struct IUpdateCollection *, unsigned int, HSTRING, const unsigned __int16 *, struct IInstallationProgressChangedCallback *, struct IInstallationCompletedCallback *, const char *, struct IUpdateInstaller **, struct IInstallationJob **)`
- caller_count: `5`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f1ff0`
- `0x1800f29b4`
- `0x1800f416c`
- `0x1800f4734`
- `0x1800f981c`

## callees

- `0x1800101f4`
- `0x1800127c8`
- `0x18001c414`
- `0x18001c844`
- `0x18002ec2c`
- `0x1800649d4`
- `0x180064c7c`
- `0x18006f864`
- `0x180070300`
- `0x180071dcc`
- `0x18007230c`
- `0x180072420`
- `0x180074694`
- `0x180075608`
- `0x180079878`
- `0x180079a68`
- `0x18007a7cc`
- `0x180215010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180075e75`
- `OLEAUT32!__imp_SysFreeString` at `0x180075e75`
- `OLEAUT32!__imp_VariantInit` at `0x180075bcd`
- `OLEAUT32!__imp_VariantInit` at `0x180075c91`
- `OLEAUT32!__imp_VariantInit` at `0x180075bcd`
- `OLEAUT32!__imp_VariantInit` at `0x180075c91`
- `OLEAUT32!__imp_VariantClear` at `0x180075c41`
- `OLEAUT32!__imp_VariantClear` at `0x180075d0d`
- `OLEAUT32!__imp_VariantClear` at `0x180075c41`
- `OLEAUT32!__imp_VariantClear` at `0x180075d0d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180075c6d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180075c6d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180075921`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007599a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180075921`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007599a`

## string_xrefs

- `0x180075640`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180075d3c`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x18007565f`: `hUserToken != 0 || (flags & 0x00008000)`
- `0x1800756ef`: `pSession->CreateUpdateInstaller(&spInstaller)`
- `0x180075639`: `InstallPackages`
- `0x180075d35`: `InstallPackages`
- `0x180075803`: `spInstaller->put_ClientApplicationID(sbstrClientApplicationId)`
- `0x180075728`: `Installing with IsForced = TRUE`
- `0x1800759b7`: `Using elevated (linked) token.`
- `0x18007594e`: `Found restricted token. Auto elevating since consent already given`
- `0x180075a0e`: `Found restricted token. Getting elevated token with admin consent.`
- `0x1800759e4`: `Failed to get elevated (linked) token. Ignoring...`
- `0x180075a99`: `Using elevated token.`
- `0x180075a5f`: `GetElevatedTokenForCurrentUserWithAdminConsent(hUserToken, wil::out_param(elevatedTokenWithAdminConsent))`
- `0x180075aea`: `Failed to retrieve token elevation type`
- `0x180075ac3`: `Failed to get elevated token. Ignoring...`
- `0x180075c23`: `spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_INSTALL_USERTOKEN, var)`
- `0x180075b5c`: `spInstaller->QueryInterface(IID_PPV_ARGS(&spInternalConfiguration))`
- `0x180075d7a`: `spInstaller->put_Updates(pPackages)`
- `0x180075cef`: `spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_INSTALL_APPINSTALLUSERCONTEXT, var)`
- `0x180075e09`: `spInstaller->BeginInstall(pProgress, pCompleted, varNull, &spJob)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall InstallPackages(
        void *a1,
        struct IUpdateSession *a2,
        struct IUpdateCollection *a3,
        int a4,
        HSTRING a5,
        unsigned __int16 *a6,
        struct IInstallationProgressChangedCallback *a7,
        struct IInstallationCompletedCallback *a8,
        const char *a9,
        struct IUpdateInstaller **a10,
        struct IInstallationJob **a11)
{
  char v11; // r13
  HRESULT (__stdcall *CreateUpdateInstaller)(IUpdateSession *, IUpdateInstaller **); // rbx
  int v14; // eax
  int v15; // edi
  OLECHAR *v16; // rbx
  int v17; // eax
  int v18; // eax
  int v19; // ecx
  int ElevatedTokenForCurrentUserWithAdminConsent; // eax
  int v21; // edi
  const unsigned __int16 *v22; // rax
  unsigned int v23; // r8d
  struct IUpdateInstaller *v24; // rsi
  HRESULT (__stdcall *QueryInterface)(IUpdateInstaller *, const IID *const, void **); // rdi
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  struct IUpdateInstaller *v31; // rsi
  HRESULT (__stdcall *BeginInstall)(IUpdateInstaller *, IUnknown *, IUnknown *, VARIANT, IInstallationJob **); // rdi
  int v33; // eax
  struct IUpdateInstaller *v34; // rax
  struct IInstallationJob *v35; // rax
  int ReturnLength; // [rsp+20h] [rbp-108h]
  int v38; // [rsp+28h] [rbp-100h]
  int v39; // [rsp+28h] [rbp-100h]
  int v40; // [rsp+28h] [rbp-100h]
  int v41; // [rsp+28h] [rbp-100h]
  struct IUpdateInstaller *v42; // [rsp+50h] [rbp-D8h] BYREF
  int TokenInformation; // [rsp+58h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-C8h] BYREF
  void *v45; // [rsp+78h] [rbp-B0h] BYREF
  struct IUpdateInternalConfiguration *v46; // [rsp+80h] [rbp-A8h] BYREF
  DWORD v47; // [rsp+88h] [rbp-A0h] BYREF
  void *v48; // [rsp+90h] [rbp-98h] BYREF
  void *v49; // [rsp+98h] [rbp-90h] BYREF
  BSTR bstrString[2]; // [rsp+A0h] [rbp-88h] BYREF
  VARIANTARG v51; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v52[16]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]
  HANDLE TokenHandle; // [rsp+130h] [rbp+8h] BYREF
  LONGLONG v55; // [rsp+138h] [rbp+10h] BYREF
  struct IUpdateCollection *v56; // [rsp+140h] [rbp+18h]
  int v57; // [rsp+148h] [rbp+20h]

  v57 = a4;
  v56 = a3;
  TokenHandle = a1;
  v11 = a4;
  if ( a1 || (a4 & 0x8000) != 0 )
  {
    LODWORD(v55) = 1;
  }
  else
  {
    LODWORD(v55) = 1;
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
      0x311u,
      "InstallPackages",
      -1,
      L"Assert (%s): %s",
      0,
      0);
  }
  *a10 = 0;
  *a11 = 0;
  v42 = 0;
  CreateUpdateInstaller = a2->lpVtbl->CreateUpdateInstaller;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v42);
  v14 = ((__int64 (__fastcall *)(struct IUpdateSession *, struct IUpdateInstaller **))CreateUpdateInstaller)(a2, &v42);
  v15 = TraceHR(
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
          0x316u,
          "InstallPackages",
          "pSession->CreateUpdateInstaller(&spInstaller)",
          v14,
          v38);
  if ( v15 >= 0 )
  {
    if ( (v11 & 8) != 0 )
    {
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
        0x31Bu,
        "InstallPackages",
        -1,
        L"Installing with IsForced = TRUE",
        0,
        0);
      ((void (__fastcall *)(struct IUpdateInstaller *, __int64))v42->lpVtbl->put_IsForced)(v42, 0xFFFFFFFFLL);
    }
    ((void (__fastcall *)(struct IUpdateInstaller *, _QWORD))v42->lpVtbl->put_AllowSourcePrompts)(v42, 0);
    if ( (v11 & 8) != 0 || (v57 & 0x1000) != 0 )
    {
      v45 = 0;
      if ( (int)Microsoft::WRL::ComPtr<IUpdateInstaller>::As<IUpdateInstaller3>(&v42, &v45) >= 0 )
        (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v45 + 248LL))(v45, 0xFFFFFFFFLL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v45);
    }
    v15 = -2147024882;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a6);
    v16 = bstrString[0];
    if ( bstrString[0]
      && (v17 = ((__int64 (__fastcall *)(struct IUpdateInstaller *, BSTR))v42->lpVtbl->put_ClientApplicationID)(
                  v42,
                  bstrString[0]),
          v15 = TraceHR(
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                  0x32Fu,
                  "InstallPackages",
                  "spInstaller->put_ClientApplicationID(sbstrClientApplicationId)",
                  v17,
                  v39),
          v15 >= 0) )
    {
      *(_DWORD *)&pvarg.vt = 327681;
      LOBYTE(pvarg.decVal.Hi32) = (v57 & 0x10) != 0;
      pvarg.lVal = 327683;
      BYTE4(pvarg.decVal.Lo64) = (v57 & 0x20) != 0;
      *((_DWORD *)&pvarg.decVal + 4) = 327685;
      TokenInformation = v57 & 0x8000;
      *((_BYTE *)&pvarg.decVal + 20) = TokenInformation != 0;
      v15 = SetInternalConfigurationFlags(v42, &pvarg, 3, a9);
      if ( v15 >= 0 )
        v15 = SetIntentPFNConfigurationProperty<IUpdateInstaller>(&v42, a5);
      v18 = TokenInformation;
      v19 = v57;
    }
    else
    {
      v19 = v57;
      v18 = v57 & 0x8000;
    }
    v48 = 0;
    if ( v15 < 0 )
      goto LABEL_47;
    if ( v18 )
    {
LABEL_43:
      v30 = ((__int64 (__fastcall *)(struct IUpdateInstaller *, struct IUpdateCollection *))v42->lpVtbl->put_Updates)(
              v42,
              v56);
      v15 = TraceHR(
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
              0x3AEu,
              "InstallPackages",
              "spInstaller->put_Updates(pPackages)",
              v30,
              v39);
      if ( v15 >= 0 )
      {
        TokenHandle = 0;
        v31 = v42;
        BeginInstall = v42->lpVtbl->BeginInstall;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&TokenHandle);
        memset(&v51, 0, sizeof(v51));
        v33 = ((__int64 (__fastcall *)(struct IUpdateInstaller *, struct IInstallationProgressChangedCallback *, struct IInstallationCompletedCallback *, VARIANTARG *, HANDLE *))BeginInstall)(
                v31,
                a7,
                a8,
                &v51,
                &TokenHandle);
        v15 = TraceHR(
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                0x3B5u,
                "InstallPackages",
                "spInstaller->BeginInstall(pProgress, pCompleted, varNull, &spJob)",
                v33,
                v41);
        if ( v15 >= 0 )
        {
          v34 = v42;
          v42 = 0;
          *a10 = v34;
          v35 = (struct IInstallationJob *)TokenHandle;
          TokenHandle = 0;
          *a11 = v35;
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&TokenHandle);
      }
LABEL_47:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v48);
      SysFreeString(v16);
      goto LABEL_48;
    }
    v45 = TokenHandle;
    v49 = 0;
    if ( (v19 & 0x10000) != 0 )
    {
      TokenInformation = 1;
      v47 = 0;
      if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &v47) )
      {
        if ( TokenInformation != 1 )
        {
          if ( TokenInformation == 3 )
          {
            LogSimpleMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
              0x357u,
              "InstallPackages",
              -1,
              L"Found restricted token. Auto elevating since consent already given",
              0,
              0);
            if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &v49, 8u, &v47) )
            {
              LogSimpleMessage(
                3u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                0x35Cu,
                "InstallPackages",
                -1,
                L"Using elevated (linked) token.",
                0,
                0);
              v45 = v49;
            }
            else
            {
              LogSimpleMessage(
                3u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                0x361u,
                "InstallPackages",
                -1,
                L"Failed to get elevated (linked) token. Ignoring...",
                0,
                0);
            }
          }
LABEL_34:
          SuspendImpersonationScope::SuspendImpersonationScope((SuspendImpersonationScope *)v52);
          v46 = 0;
          v24 = v42;
          QueryInterface = v42->lpVtbl->QueryInterface;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v46);
          v26 = ((__int64 (__fastcall *)(struct IUpdateInstaller *, GUID *, struct IUpdateInternalConfiguration **))QueryInterface)(
                  v24,
                  &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
                  &v46);
          v15 = TraceHR(
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                  0x38Au,
                  "InstallPackages",
                  "spInstaller->QueryInterface(IID_PPV_ARGS(&spInternalConfiguration))",
                  v26,
                  v39);
          if ( v15 >= 0 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::GetImpl'::`2'::impl) )
            {
              v27 = _SetWuUserTokenProperty(v46, 0x50002u, v45);
              if ( v27 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x38F,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                  (const char *)(unsigned int)v27,
                  ReturnLength);
            }
            else
            {
              memset(&pvarg, 0, sizeof(pvarg));
              VariantInit(&pvarg);
              pvarg.vt = 19;
              pvarg.lVal = (int)v45;
              v51 = pvarg;
              v28 = (*(__int64 (__fastcall **)(struct IUpdateInternalConfiguration *, __int64, VARIANTARG *))(*(_QWORD *)v46 + 32LL))(
                      v46,
                      327682,
                      &v51);
              v15 = TraceHR(
                      "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                      0x397u,
                      "InstallPackages",
                      "spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_INSTALL_USERTOKEN, var)",
                      v28,
                      v39);
              VariantClear(&pvarg);
            }
            if ( (_BYTE)v55 )
            {
              v55 = 0;
              v15 = UMgrQueryUserContext(TokenHandle, &v55);
              if ( v15 >= 0 )
              {
                memset(&pvarg, 0, sizeof(pvarg));
                VariantInit(&pvarg);
                pvarg.vt = 21;
                pvarg.llVal = v55;
                v51 = pvarg;
                v29 = (*(__int64 (__fastcall **)(struct IUpdateInternalConfiguration *, __int64, VARIANTARG *))(*(_QWORD *)v46 + 32LL))(
                        v46,
                        327688,
                        &v51);
                v15 = TraceHR(
                        "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                        0x3A4u,
                        "InstallPackages",
                        "spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_INSTALL_APPI"
                        "NSTALLUSERCONTEXT, var)",
                        v29,
                        v39);
                VariantClear(&pvarg);
              }
            }
          }
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v46);
          SuspendImpersonationScope::~SuspendImpersonationScope((SuspendImpersonationScope *)v52);
          if ( v15 < 0 )
            goto LABEL_47;
          goto LABEL_43;
        }
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
          0x36Bu,
          "InstallPackages",
          -1,
          L"Found restricted token. Getting elevated token with admin consent.",
          0,
          0);
        *(_QWORD *)&pvarg.vt = &v48;
        pvarg.llVal = 0;
        *((_BYTE *)&pvarg.decVal + 16) = 1;
        ElevatedTokenForCurrentUserWithAdminConsent = GetElevatedTokenForCurrentUserWithAdminConsent(
                                                        TokenHandle,
                                                        &pvarg.byref);
        v21 = TraceHR(
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                0x36Du,
                "InstallPackages",
                "GetElevatedTokenForCurrentUserWithAdminConsent(hUserToken, wil::out_param(elevatedTokenWithAdminConsent))",
                ElevatedTokenForCurrentUserWithAdminConsent,
                v40);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&pvarg);
        if ( v21 >= 0 )
        {
          LogSimpleMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
            0x371u,
            "InstallPackages",
            -1,
            L"Using elevated token.",
            0,
            0);
          v45 = v48;
          goto LABEL_34;
        }
        v22 = L"Failed to get elevated token. Ignoring...";
        v23 = 886;
      }
      else
      {
        v22 = L"Failed to retrieve token elevation type";
        v23 = 899;
      }
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
        v23,
        "InstallPackages",
        -1,
        v22,
        0,
        0);
      goto LABEL_34;
    }
    LOBYTE(v55) = 0;
    goto LABEL_34;
  }
LABEL_48:
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v42);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180075608  mov     rax, rsp
0x18007560b  mov     [rax+20h], r9d
0x18007560f  mov     [rax+18h], r8
0x180075613  mov     [rax+8], rcx
0x180075617  push    rbx
0x180075618  push    rsi
0x180075619  push    rdi
0x18007561a  push    r12
0x18007561c  push    r13
0x18007561e  push    r14
0x180075620  push    r15
0x180075622  sub     rsp, 0F0h
0x180075629  movaps  xmmword ptr [rax-48h], xmm6
0x18007562d  mov     r13d, r9d
0x180075630  mov     rdi, rdx
0x180075633  xor     r14d, r14d
0x180075636  or      esi, 0FFFFFFFFh
0x180075639  lea     r12, aInstallpackage; "InstallPackages"
0x180075640  lea     r15, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180075647  test    rcx, rcx
0x18007564a  jnz     short loc_1800756A4
0x18007564c  bt      r9d, 0Fh
0x180075651  jb      short loc_1800756A4
0x180075653  lea     rax, aFailed_1; "Failed"
0x18007565a  mov     [rsp+128h+var_E0], rax
0x18007565f  lea     rax, aHusertoken0Fla; "hUserToken != 0 || (flags & 0x00008000)"
0x180075666  mov     [rsp+128h+var_E8], rax
0x18007566b  mov     [rsp+128h+var_F0], r14; unsigned __int16 *
0x180075670  mov     [rsp+128h+var_F8], r14; char *
0x180075675  lea     rax, aAssertSS; "Assert (%s): %s"
0x18007567c  mov     [rsp+128h+var_100], rax; unsigned __int16 *
0x180075681  mov     dword ptr [rsp+128h+ReturnLength], esi; int
0x180075685  mov     r9, r12; char *
0x180075688  mov     r8d, 311h; unsigned int
0x18007568e  mov     rdx, r15; char *
0x180075691  lea     eax, [rcx+1]
0x180075694  mov     dword ptr [rsp+128h+arg_8], eax
0x18007569b  mov     ecx, eax; unsigned int
0x18007569d  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800756a2  jmp     short loc_1800756AF
0x1800756a4  mov     dword ptr [rsp+128h+arg_8], 1
0x1800756af  mov     rax, [rsp+128h+arg_48]
0x1800756b7  mov     [rax], r14
0x1800756ba  mov     rax, [rsp+128h+arg_50]
0x1800756c2  mov     [rax], r14
0x1800756c5  mov     [rsp+128h+var_D8], r14
0x1800756ca  mov     rax, [rdi]
0x1800756cd  mov     rbx, [rax+70h]
0x1800756d1  lea     rcx, [rsp+128h+var_D8]
0x1800756d6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800756db  lea     rdx, [rsp+128h+var_D8]
0x1800756e0  mov     rcx, rdi
0x1800756e3  mov     rax, rbx
0x1800756e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800756eb  mov     dword ptr [rsp+128h+ReturnLength], eax; int
0x1800756ef  lea     r9, aPsessionCreate_0; "pSession->CreateUpdateInstaller(&spInst"...
0x1800756f6  mov     r8, r12; char *
0x1800756f9  mov     edx, 316h; unsigned int
0x1800756fe  mov     rcx, r15; char *
0x180075701  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180075706  mov     edi, eax
0x180075708  test    eax, eax
0x18007570a  js      loc_180075E7C
0x180075710  mov     ebx, r13d
0x180075713  and     ebx, 8
0x180075716  mov     r13d, 3
0x18007571c  jz      short loc_18007575F
0x18007571e  mov     [rsp+128h+var_F0], r14; unsigned __int16 *
0x180075723  mov     [rsp+128h+var_F8], r14; char *
0x180075728  lea     rax, aInstallingWith; "Installing with IsForced = TRUE"
0x18007572f  mov     [rsp+128h+var_100], rax; int
0x180075734  mov     dword ptr [rsp+128h+ReturnLength], esi; int
0x180075738  mov     r9, r12; char *
0x18007573b  mov     r8d, 31Bh; unsigned int
0x180075741  mov     rdx, r15; char *
0x180075744  mov     ecx, r13d; unsigned int
0x180075747  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18007574c  mov     rcx, [rsp+128h+var_D8]
0x180075751  mov     rax, [rcx]
0x180075754  mov     edx, esi
0x180075756  mov     rax, [rax+50h]
0x18007575a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007575f  mov     rcx, [rsp+128h+var_D8]
0x180075764  mov     rax, [rcx]
0x180075767  xor     edx, edx
0x180075769  mov     rax, [rax+0D0h]
0x180075770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075775  test    ebx, ebx
0x180075777  jnz     short loc_180075786
0x180075779  test    [rsp+128h+arg_18], 1000h
0x180075784  jz      short loc_1800757BF
0x180075786  mov     [rsp+128h+var_B0], r14
0x18007578b  lea     rdx, [rsp+128h+var_B0]
0x180075790  lea     rcx, [rsp+128h+var_D8]
0x180075795  call    ??$As@UIUpdateInstaller3@@@?$ComPtr@UIUpdateInstaller@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUpdateInstaller3@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUpdateInstaller>::As<IUpdateInstaller3>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUpdateInstaller3>>)
0x18007579a  test    eax, eax
0x18007579c  js      short loc_1800757B5
0x18007579e  mov     rcx, [rsp+128h+var_B0]
0x1800757a3  mov     rax, [rcx]
0x1800757a6  mov     edx, esi
0x1800757a8  mov     rax, [rax+0F8h]
0x1800757af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800757b4  nop
0x1800757b5  lea     rcx, [rsp+128h+var_B0]
0x1800757ba  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800757bf  mov     edi, 8007000Eh
0x1800757c4  mov     rdx, [rsp+128h+arg_28]; unsigned __int16 *
0x1800757cc  lea     rcx, [rsp+128h+bstrString]; this
0x1800757d4  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800757d9  nop
0x1800757da  mov     rbx, [rsp+128h+bstrString]
0x1800757e2  test    rbx, rbx
0x1800757e5  jz      loc_1800758AF
0x1800757eb  mov     rcx, [rsp+128h+var_D8]
0x1800757f0  mov     rax, [rcx]
0x1800757f3  mov     rdx, rbx
0x1800757f6  mov     rax, [rax+40h]
0x1800757fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800757ff  mov     dword ptr [rsp+128h+ReturnLength], eax; int
0x180075803  lea     r9, aSpinstallerPut_0; "spInstaller->put_ClientApplicationID(sb"...
0x18007580a  mov     r8, r12; char *
0x18007580d  mov     edx, 32Fh; unsigned int
0x180075812  mov     rcx, r15; char *
0x180075815  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007581a  mov     edi, eax
0x18007581c  test    eax, eax
0x18007581e  js      loc_1800758AF
0x180075824  mov     dword ptr [rsp+128h+pvarg], 50001h
0x18007582c  mov     ecx, [rsp+128h+arg_18]
0x180075833  mov     al, cl
0x180075835  shr     al, 4
0x180075838  mov     edx, 1
0x18007583d  and     al, dl
0x18007583f  mov     byte ptr [rsp+128h+pvarg+4], al
0x180075843  mov     dword ptr [rsp+128h+pvarg+8], 50003h
0x18007584b  mov     al, cl
0x18007584d  shr     al, 5
0x180075850  and     al, dl
0x180075852  mov     byte ptr [rsp+128h+pvarg+0Ch], al
0x180075856  mov     dword ptr [rsp+128h+pvarg+10h], 50005h
0x18007585e  mov     eax, ecx
0x180075860  and     eax, 8000h
0x180075865  mov     [rsp+128h+TokenInformation], eax
0x180075869  setnz   byte ptr [rsp+128h+pvarg+14h]
0x18007586e  mov     r9, [rsp+128h+arg_40]
0x180075876  mov     r8, r13
0x180075879  lea     rdx, [rsp+128h+pvarg]
0x18007587e  mov     rcx, [rsp+128h+var_D8]
0x180075883  call    _SetInternalConfigurationFlags
0x180075888  mov     edi, eax
0x18007588a  test    eax, eax
0x18007588c  js      short loc_1800758A2
0x18007588e  mov     rdx, [rsp+128h+arg_20]
0x180075896  lea     rcx, [rsp+128h+var_D8]
0x18007589b  call    ??$SetIntentPFNConfigurationProperty@UIUpdateInstaller@@@@YAJAEAV?$ComPtr@UIUpdateInstaller@@@WRL@Microsoft@@PEAUHSTRING__@@@Z; SetIntentPFNConfigurationProperty<IUpdateInstaller>(Microsoft::WRL::ComPtr<IUpdateInstaller> &,HSTRING__ *)
0x1800758a0  mov     edi, eax
0x1800758a2  mov     eax, [rsp+128h+TokenInformation]
0x1800758a6  mov     ecx, [rsp+128h+arg_18]
0x1800758ad  jmp     short loc_1800758BD
0x1800758af  mov     ecx, [rsp+128h+arg_18]
0x1800758b6  mov     eax, ecx
0x1800758b8  and     eax, 8000h
0x1800758bd  mov     [rsp+128h+var_98], r14
0x1800758c5  test    edi, edi
0x1800758c7  js      loc_180075E64
0x1800758cd  test    eax, eax
0x1800758cf  jnz     loc_180075D5A
0x1800758d5  mov     rax, [rsp+128h+TokenHandle]
0x1800758dd  mov     [rsp+128h+var_B0], rax
0x1800758e2  mov     [rsp+128h+var_90], r14
0x1800758ea  bt      ecx, 10h
0x1800758ee  jnb     loc_180075B02
0x1800758f4  mov     edi, 1
0x1800758f9  mov     [rsp+128h+TokenInformation], edi
0x1800758fd  mov     [rsp+128h+var_A0], r14d
0x180075905  lea     rcx, [rsp+128h+var_A0]
0x18007590d  mov     [rsp+128h+ReturnLength], rcx; ReturnLength
0x180075912  lea     r9d, [rdi+3]; TokenInformationLength
0x180075916  lea     r8, [rsp+128h+TokenInformation]; TokenInformation
0x18007591b  lea     edx, [rdi+11h]; TokenInformationClass
0x18007591e  mov     rcx, rax; TokenHandle
0x180075921  call    cs:__imp_GetTokenInformation
0x180075927  test    eax, eax
0x180075929  jz      loc_180075AE0
0x18007592f  mov     ecx, [rsp+128h+TokenInformation]
0x180075933  sub     ecx, edi
0x180075935  jz      loc_180075A04
0x18007593b  cmp     ecx, 2
0x18007593e  jnz     loc_180075B0A
0x180075944  mov     [rsp+128h+var_F0], r14; unsigned __int16 *
0x180075949  mov     [rsp+128h+var_F8], r14; char *
0x18007594e  lea     rax, aFoundRestricte; "Found restricted token. Auto elevating "...
0x180075955  mov     [rsp+128h+var_100], rax; unsigned __int16 *
0x18007595a  mov     dword ptr [rsp+128h+ReturnLength], esi; int
0x18007595e  mov     r9, r12; char *
0x180075961  mov     r8d, 357h; unsigned int
0x180075967  mov     rdx, r15; char *
0x18007596a  mov     ecx, r13d; unsigned int
0x18007596d  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180075972  lea     rax, [rsp+128h+var_A0]
0x18007597a  mov     [rsp+128h+ReturnLength], rax; ReturnLength
0x18007597f  lea     r9d, [rdi+7]; TokenInformationLength
0x180075983  lea     r8, [rsp+128h+var_90]; TokenInformation
0x18007598b  lea     r13d, [rdi+12h]
0x18007598f  mov     edx, r13d; TokenInformationClass
0x180075992  mov     rcx, [rsp+128h+TokenHandle]; TokenHandle
0x18007599a  call    cs:__imp_GetTokenInformation
0x1800759a0  mov     [rsp+128h+var_F0], r14; unsigned __int16 *
0x1800759a5  mov     r9, r12; char *
0x1800759a8  mov     rdx, r15; char *
0x1800759ab  lea     ecx, [rdi+2]; unsigned int
0x1800759ae  mov     [rsp+128h+var_F8], r14; char *
0x1800759b3  test    eax, eax
0x1800759b5  jz      short loc_1800759E4
0x1800759b7  lea     rax, aUsingElevatedL; "Using elevated (linked) token."
0x1800759be  mov     [rsp+128h+var_100], rax; unsigned __int16 *
0x1800759c3  mov     dword ptr [rsp+128h+ReturnLength], esi; int
0x1800759c7  mov     r8d, 35Ch; unsigned int
0x1800759cd  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800759d2  mov     rdi, [rsp+128h+var_90]
0x1800759da  mov     [rsp+128h+var_B0], rdi
0x1800759df  jmp     loc_180075B10
0x1800759e4  lea     rax, aFailedToGetEle_0; "Failed to get elevated (linked) token. "...
0x1800759eb  mov     [rsp+128h+var_100], rax; unsigned __int16 *
0x1800759f0  mov     dword ptr [rsp+128h+ReturnLength], esi; int
0x1800759f4  mov     r8d, 361h; unsigned int
0x1800759fa  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800759ff  jmp     loc_180075B10
0x180075a04  mov     [rsp+128h+var_F0], r14; unsigned __int16 *
0x180075a09  mov     [rsp+128h+var_F8], r14; char *
0x180075a0e  lea     rax, aFoundRestricte_0; "Found restricted token. Getting elevate"...
0x180075a15  mov     [rsp+128h+var_100], rax; int
0x180075a1a  mov     dword ptr [rsp+128h+ReturnLength], esi; int
0x180075a1e  mov     r9, r12; char *
0x180075a21  mov     r8d, 36Bh; unsigned int
0x180075a27  mov     rdx, r15; char *
0x180075a2a  mov     ecx, r13d; unsigned int
0x180075a2d  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180075a32  lea     rax, [rsp+128h+var_98]
0x180075a3a  mov     qword ptr [rsp+128h+pvarg], rax
0x180075a3f  mov     qword ptr [rsp+128h+pvarg+8], r14
0x180075a44  mov     byte ptr [rsp+128h+pvarg+10h], dil
0x180075a49  lea     rdx, [rsp+128h+pvarg+8]; void **
0x180075a4e  mov     rcx, [rsp+128h+TokenHandle]; void *
0x180075a56  call    ?GetElevatedTokenForCurrentUserWithAdminConsent@@YAJPEAXPEAPEAX@Z; GetElevatedTokenForCurrentUserWithAdminConsent(void *,void * *)
0x180075a5b  mov     dword ptr [rsp+128h+ReturnLength], eax; int
0x180075a5f  lea     r9, aGetelevatedtok; "GetElevatedTokenForCurrentUserWithAdmin"...
0x180075a66  mov     r8, r12; char *
0x180075a69  mov     edx, 36Dh; unsigned int
0x180075a6e  mov     rcx, r15; char *
0x180075a71  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180075a76  mov     edi, eax
0x180075a78  lea     rcx, [rsp+128h+pvarg]
0x180075a7d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180075a82  mov     [rsp+128h+var_F0], r14; unsigned __int16 *
0x180075a87  mov     r9, r12; char *
0x180075a8a  mov     rdx, r15; char *
0x180075a8d  mov     ecx, r13d; unsigned int
0x180075a90  mov     [rsp+128h+var_F8], r14; char *
0x180075a95  test    edi, edi
0x180075a97  js      short loc_180075AC3
0x180075a99  lea     rax, aUsingElevatedT; "Using elevated token."
0x180075aa0  mov     [rsp+128h+var_100], rax; unsigned __int16 *
0x180075aa5  mov     dword ptr [rsp+128h+ReturnLength], esi; int
0x180075aa9  mov     r8d, 371h; unsigned int
0x180075aaf  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180075ab4  mov     rax, [rsp+128h+var_98]
0x180075abc  mov     [rsp+128h+var_B0], rax
0x180075ac1  jmp     short loc_180075B0A
0x180075ac3  lea     rax, aFailedToGetEle; "Failed to get elevated token. Ignoring."...
0x180075aca  mov     r8d, 376h; unsigned int
0x180075ad0  mov     [rsp+128h+var_100], rax; unsigned __int16 *
0x180075ad5  mov     dword ptr [rsp+128h+ReturnLength], esi; int
0x180075ad9  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180075ade  jmp     short loc_180075B0A
0x180075ae0  mov     [rsp+128h+var_F0], r14
0x180075ae5  mov     [rsp+128h+var_F8], r14
0x180075aea  lea     rax, aFailedToRetrie_0; "Failed to retrieve token elevation type"
0x180075af1  mov     r9, r12
0x180075af4  mov     r8d, 383h
0x180075afa  mov     rdx, r15
0x180075afd  mov     ecx, r13d
0x180075b00  jmp     short loc_180075AD0
0x180075b02  mov     byte ptr [rsp+128h+arg_8], r14b
0x180075b0a  mov     r13d, 13h
0x180075b10  lea     rcx, [rsp+128h+var_58]; this
0x180075b18  call    ??0SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::SuspendImpersonationScope(void)
0x180075b1d  nop
0x180075b1e  mov     [rsp+128h+var_A8], r14
0x180075b26  mov     rsi, [rsp+128h+var_D8]
0x180075b2b  mov     rax, [rsi]
0x180075b2e  mov     rdi, [rax]
0x180075b31  lea     rcx, [rsp+128h+var_A8]
0x180075b39  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180075b3e  lea     r8, [rsp+128h+var_A8]
0x180075b46  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x180075b4d  mov     rcx, rsi
0x180075b50  mov     rax, rdi
0x180075b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b58  mov     dword ptr [rsp+128h+ReturnLength], eax; int
  ... truncated ...
```
