# ConnectedStorage::UserManager::GetUserSidAndXuidFromToken(void *,HSTRING__ * *,HSTRING__ * *,bool)

- ea: `0x18002c408`
- end: `0x18002c9e6`
- name: `?GetUserSidAndXuidFromToken@UserManager@ConnectedStorage@@SAXPEAXPEAPEAUHSTRING__@@1_N@Z`
- size: `1502`
- prototype: `void __fastcall(void *, HSTRING *, HSTRING *, char)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a220`
- `0x18002c358`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000aae4`
- `0x180010f88`
- `0x180012278`
- `0x180028310`
- `0x180028434`
- `0x180028484`
- `0x180028524`
- `0x180028878`
- `0x1800295a4`
- `0x180029c44`
- `0x18002a1dc`
- `0x18002a6a8`
- `0x18002c408`
- `0x18002d880`
- `0x180084f58`
- `0x180085038`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c82c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c82c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002c858`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002c858`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002c862`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002c862`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002c8bd`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002c8bd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002c56c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002c56c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002c4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002c971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002c4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002c971`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c491`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c491`
- `ntdll!NtQueryInformationToken` at `0x18002c469`
- `ntdll!NtQueryInformationToken` at `0x18002c469`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002c513`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002c513`

## string_xrefs

- `0x18002c836`: `CoCreateInstance( __uuidof(XblAuthManager), nullptr, CLSCTX_LOCAL_SERVER, IID_PPV_ARGS(&authManager))`
- `0x18002c476`: `HRESULT_FROM_NT(NtQueryInformationToken(token, TokenUser, buffer, sizeof(buffer), &length))`
- `0x18002c4bd`: `WindowsCreateString(sidString, static_cast<uint32_t>(wcslen(sidString)), userSid)`
- `0x18002c4e2`: `UserManager::ConvertSidToStringSid`
- `0x18002c51d`: `UMgrQueryUserContext(token, &userContext)`
- `0x18002c97b`: `WindowsCreateString(xuidData.Get(), static_cast<uint32_t>(wcslen(xuidData.Get())), xuid)`
- `0x18002c907`: `hrThreadPoolCall`

## pseudocode

```c
void __fastcall ConnectedStorage::UserManager::GetUserSidAndXuidFromToken(void *a1, HSTRING *a2, HSTRING *a3, char a4)
{
  void *v7; // rbx
  char v8; // di
  int v9; // eax
  const unsigned __int16 *v10; // r8
  __int64 v11; // rsi
  __int64 v12; // rdx
  HRESULT String; // eax
  ConnectedStorage *v14; // rcx
  const unsigned __int16 *v15; // r8
  signed int LastError; // eax
  const unsigned __int16 *v17; // r8
  bool v18; // sf
  int v19; // eax
  const unsigned __int16 *v20; // r8
  __int64 v21; // rbx
  int ActivationFactory; // eax
  const unsigned __int16 *v23; // r8
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, void *, __int64 *); // rbx
  int v26; // eax
  const unsigned __int16 *v27; // r8
  __int64 v28; // rcx
  int v29; // eax
  const unsigned __int16 *v30; // r8
  int v31; // eax
  const unsigned __int16 *v32; // r8
  ConnectedStorage *v33; // rdi
  __int64 (__fastcall *v34)(ConnectedStorage *, __int64 *); // rbx
  int v35; // eax
  const unsigned __int16 *v36; // r8
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64, __int64 *); // rbx
  int v39; // eax
  const unsigned __int16 *v40; // r8
  int v41; // eax
  const unsigned __int16 *v42; // r8
  int v43; // eax
  const unsigned __int16 *v44; // r8
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, __int64, LPVOID *); // rbx
  int v47; // eax
  const unsigned __int16 *v48; // r8
  int v49; // eax
  const unsigned __int16 *v50; // r8
  int v51; // eax
  const unsigned __int16 *v52; // r8
  HRESULT v53; // eax
  const unsigned __int16 *v54; // r8
  __int64 v55; // rax
  __int64 v56; // rax
  const unsigned __int16 *v57; // r8
  LPVOID v58; // rdi
  int (__fastcall *v59)(LPVOID, __int64 *, PCNZWCH *); // rbx
  const unsigned __int16 *v60; // r8
  HRESULT v61; // eax
  const unsigned __int16 *v62; // r8
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  ConnectedStorage *v64; // [rsp+48h] [rbp-B8h] BYREF
  void *v65; // [rsp+50h] [rbp-B0h] BYREF
  ULONG ReturnLength; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v67; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v68; // [rsp+68h] [rbp-98h] BYREF
  __int64 v69; // [rsp+70h] [rbp-90h] BYREF
  __int64 v70; // [rsp+78h] [rbp-88h] BYREF
  PCNZWCH sourceString; // [rsp+80h] [rbp-80h] BYREF
  __int64 v72; // [rsp+88h] [rbp-78h] BYREF
  __int64 v73; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR StringSid; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v75[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v76[2]; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v78; // [rsp+D8h] [rbp-28h]
  ConnectedStorage **v79; // [rsp+E0h] [rbp-20h]
  HSTRING_HEADER v80; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v81; // [rsp+100h] [rbp+0h]
  PSID TokenInformation[12]; // [rsp+130h] [rbp+30h] BYREF

  v7 = a1;
  v65 = a1;
  ReturnLength = 0;
  v8 = 1;
  v9 = NtQueryInformationToken(a1, TokenUser, TokenInformation, 0x54u, &ReturnLength) | 0x10000000;
  if ( v9 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v9,
      (int)L"HRESULT_FROM_NT(NtQueryInformationToken(token, TokenUser, buffer, sizeof(buffer), &length))",
      v10);
  StringSid = 0;
  v11 = -1;
  if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
  {
    v12 = -1;
    do
      ++v12;
    while ( StringSid[v12] );
    String = WindowsCreateString(StringSid, v12, a2);
    if ( String < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)String,
        (int)L"WindowsCreateString(sidString, static_cast<uint32_t>(wcslen(sidString)), userSid)",
        v15);
  }
  else
  {
    LastError = GetLastError();
    v18 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v18 = LastError < 0;
    }
    if ( v18 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)LastError,
        (int)L"UserManager::ConvertSidToStringSid",
        v17);
  }
  v73 = 0;
  sourceString = 0;
  if ( ConnectedStorage::IsRunningOnConsole(v14) )
  {
    v65 = 0;
    v19 = UMgrQueryUserContext(v7, &v65);
    if ( v19 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v19,
        (int)L"UMgrQueryUserContext(token, &userContext)",
        v20);
    v70 = 0;
    v78 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    v21 = v78;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    ActivationFactory = RoGetActivationFactory(v21, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v70);
    if ( ActivationFactory < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)ActivationFactory,
        (int)L"Windows::Foundation::GetActivationFactory( HStringReference(RuntimeClass_Windows_System_Internal_UserManage"
              "r).Get(), &signInMgr)",
        v23);
    v69 = 0;
    v24 = v70;
    v25 = *(__int64 (__fastcall **)(__int64, void *, __int64 *))(*(_QWORD *)v70 + 160LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    v26 = v25(v24, v65, &v69);
    if ( v26 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v26,
        (int)L"signInMgr->GetUserForContext(userContext, &user)",
        v27);
    v68 = 0;
    v64 = 0;
    v67 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    v29 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
            v28,
            &v64);
    if ( v29 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v29,
        (int)L"Windows::Foundation::Collections::Internal::AgileVector<HSTRING>::Make(&propertyLookup)",
        v30);
    v81 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v80, L"XboxUserId", 0xBu, 0xAu);
    v31 = (*(__int64 (__fastcall **)(ConnectedStorage *, __int64))(*(_QWORD *)v64 + 104LL))(v64, v81);
    if ( v31 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v31,
        (int)L"propertyLookup->Append(xboxUserId.Get())",
        v32);
    v33 = v64;
    v34 = *(__int64 (__fastcall **)(ConnectedStorage *, __int64 *))(*(_QWORD *)v64 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    v35 = v34(v33, &v67);
    if ( v35 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v35,
        (int)L"propertyLookup->GetView(&propertyLookupView)",
        v36);
    v37 = v69;
    v38 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v69 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    v39 = v38(v37, v67, &v68);
    if ( v39 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v39,
        (int)L"user->GetPropertiesAsync(propertyLookupView.Get(), &asyncOp)",
        v40);
    v75[0] = 0;
    ppv = 0;
    v41 = ConnectedStorage::WaitForAsync<Windows::Foundation::Collections::IPropertySet,Windows::Foundation::Collections::IPropertySet>(
            v68,
            v75);
    if ( v41 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v41,
        (int)L"WaitForAsync(asyncOp.Get(), properties.GetAddressOf())",
        v42);
    v76[0] = 0;
    v43 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            v75,
            v76);
    if ( v43 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v43,
        (int)L"properties.As(&propertyMap)",
        v44);
    v45 = v76[0];
    v46 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v76[0] + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v47 = v46(v45, v81, &ppv);
    if ( v47 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v47,
        (int)L"propertyMap->Lookup(xboxUserId.Get(), &insp)",
        v48);
    v72 = 0;
    v49 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&ppv, &v72);
    if ( v49 < 0 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v49, (int)L"insp.As(&val)", v50);
    v51 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v72 + 152LL))(v72, a3);
    if ( v51 < 0 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v51, (int)L"val->GetString(xuid)", v52);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v76);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v75);
    v81 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v53 = CoCreateInstance(
            &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
            0,
            4u,
            &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
            &ppv);
    if ( v53 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v53,
        (int)L"CoCreateInstance( __uuidof(XblAuthManager), nullptr, CLSCTX_LOCAL_SERVER, IID_PPV_ARGS(&authManager))",
        v54);
    std::weak_ptr<ConnectedStorage::AtomManager>::weak_ptr<ConnectedStorage::AtomManager>(v75);
    if ( !a4 )
      goto LABEL_47;
    if ( CoImpersonateClient() < 0 )
    {
      v8 = 0;
      v55 = std::make_shared<ConnectedStorage::ContextImpersonator,void * &>(v76, &v65);
      std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(v75, v55);
      std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(v76);
      v7 = v65;
    }
    else
    {
      CoRevertToSelf();
    }
    CoSetProxyBlanket((IUnknown *)ppv, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
    if ( v8 )
    {
      LODWORD(v64) = 0;
      hstringHeader.Reserved.Reserved1 = v7;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = a2;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = a3;
      LOBYTE(v78) = a4;
      v79 = &v64;
      v56 = std::function_void___cdecl_void__::function_void___cdecl_void____lambda_0a9a41e030560d3fbeed20cc103d43db__0_(
              &v80,
              &hstringHeader);
      ConnectedStorage::ExecuteOnThreadPoolAndWait(v56);
      if ( (int)v64 < 0 )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v64, (int)L"hrThreadPoolCall", v57);
    }
    else
    {
LABEL_47:
      v58 = ppv;
      v59 = *(int (__fastcall **)(LPVOID, __int64 *, PCNZWCH *))(*(_QWORD *)ppv + 448LL);
      ConnectedStorage::TaskMem<unsigned short>::Release(&sourceString);
      ConnectedStorage::TaskMem<unsigned short>::Release(&v73);
      if ( v59(v58, &v73, &sourceString) < 0 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)0x8083000CLL,
          (int)L"CS_E_USER_MUST_BE_XBOX_USER",
          v60);
      do
        ++v11;
      while ( sourceString[v11] );
      v61 = WindowsCreateString(sourceString, v11, a3);
      if ( v61 < 0 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)v61,
          (int)L"WindowsCreateString(xuidData.Get(), static_cast<uint32_t>(wcslen(xuidData.Get())), xuid)",
          v62);
    }
    std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(v75);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  }
  ConnectedStorage::TaskMem<unsigned short>::Release(&sourceString);
  ConnectedStorage::TaskMem<unsigned short>::Release(&v73);
  CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&StringSid);
}

```

## disassembly

```asm
0x18002c408  mov     [rsp-8+arg_18], rbx
0x18002c40d  push    rbp
0x18002c40e  push    rsi
0x18002c40f  push    rdi
0x18002c410  push    r12
0x18002c412  push    r13
0x18002c414  push    r14
0x18002c416  push    r15
0x18002c418  lea     rbp, [rsp-0A0h]
0x18002c420  sub     rsp, 1A0h
0x18002c427  mov     rax, cs:__security_cookie
0x18002c42e  xor     rax, rsp
0x18002c431  mov     [rbp+0D0h+var_40], rax
0x18002c438  mov     r14b, r9b
0x18002c43b  mov     r12, r8
0x18002c43e  mov     r15, rdx
0x18002c441  mov     rbx, rcx
0x18002c444  mov     [rsp+1D0h+var_180], rcx
0x18002c449  xor     r13d, r13d
0x18002c44c  mov     [rsp+1D0h+var_178], r13d
0x18002c451  lea     rax, [rsp+1D0h+var_178]
0x18002c456  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x18002c45b  lea     r9d, [r13+54h]; TokenInformationLength
0x18002c45f  lea     r8, [rbp+0D0h+TokenInformation]; TokenInformation
0x18002c463  lea     edi, [r13+1]
0x18002c467  mov     edx, edi; TokenInformationClass
0x18002c469  call    cs:__imp_NtQueryInformationToken
0x18002c46f  or      eax, 10000000h
0x18002c474  jge     short loc_18002C485
0x18002c476  lea     rdx, aHresultFromNtN_0; "HRESULT_FROM_NT(NtQueryInformationToken"...
0x18002c47d  mov     ecx, eax; this
0x18002c47f  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c485  mov     [rbp+0D0h+StringSid], r13
0x18002c489  lea     rdx, [rbp+0D0h+StringSid]; StringSid
0x18002c48d  mov     rcx, [rbp+0D0h+TokenInformation]; Sid
0x18002c491  call    cs:__imp_ConvertSidToStringSidW
0x18002c497  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002c49b  test    eax, eax
0x18002c49d  jz      short loc_18002C4CC
0x18002c49f  mov     rcx, [rbp+0D0h+StringSid]; sourceString
0x18002c4a3  mov     rdx, rsi
0x18002c4a6  inc     rdx; length
0x18002c4a9  cmp     [rcx+rdx*2], r13w
0x18002c4ae  jnz     short loc_18002C4A6
0x18002c4b0  mov     r8, r15; string
0x18002c4b3  call    cs:__imp_WindowsCreateString
0x18002c4b9  test    eax, eax
0x18002c4bb  jns     short loc_18002C4F1
0x18002c4bd  lea     rdx, aWindowscreates_2; "WindowsCreateString(sidString, static_c"...
0x18002c4c4  mov     ecx, eax; this
0x18002c4c6  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c4cc  call    cs:__imp_GetLastError
0x18002c4d2  test    eax, eax
0x18002c4d4  jle     short loc_18002C4E0
0x18002c4d6  movzx   eax, ax
0x18002c4d9  or      eax, 80070000h
0x18002c4de  test    eax, eax
0x18002c4e0  jns     short loc_18002C4F1
0x18002c4e2  lea     rdx, aUsermanagerCon; "UserManager::ConvertSidToStringSid"
0x18002c4e9  mov     ecx, eax; this
0x18002c4eb  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c4f1  mov     [rbp+0D0h+var_140], r13
0x18002c4f5  mov     [rbp+0D0h+sourceString], r13
0x18002c4f9  call    ?IsRunningOnConsole@ConnectedStorage@@YA_NXZ; ConnectedStorage::IsRunningOnConsole(void)
0x18002c4fe  test    al, al
0x18002c500  jz      loc_18002C7FF
0x18002c506  mov     [rsp+1D0h+var_180], r13
0x18002c50b  lea     rdx, [rsp+1D0h+var_180]
0x18002c510  mov     rcx, rbx
0x18002c513  call    cs:__imp_UMgrQueryUserContext
0x18002c519  test    eax, eax
0x18002c51b  jns     short loc_18002C52C
0x18002c51d  lea     rdx, aUmgrqueryuserc_0; "UMgrQueryUserContext(token, &userContex"...
0x18002c524  mov     ecx, eax; this
0x18002c526  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c52c  mov     [rsp+1D0h+var_158], r13
0x18002c531  mov     [rbp+0D0h+var_F8], r13
0x18002c535  mov     r9d, 23h ; '#'; unsigned int
0x18002c53b  lea     r8d, [r9+1]; unsigned int
0x18002c53f  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18002c546  lea     rcx, [rbp+0D0h+hstringHeader]; hstringHeader
0x18002c54a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002c54f  mov     rbx, [rbp+0D0h+var_F8]
0x18002c553  lea     rcx, [rsp+1D0h+var_158]
0x18002c558  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c55d  lea     r8, [rsp+1D0h+var_158]
0x18002c562  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18002c569  mov     rcx, rbx
0x18002c56c  call    cs:__imp_RoGetActivationFactory
0x18002c572  test    eax, eax
0x18002c574  jns     short loc_18002C585
0x18002c576  lea     rdx, aWindowsFoundat; "Windows::Foundation::GetActivationFacto"...
0x18002c57d  mov     ecx, eax; this
0x18002c57f  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c585  mov     [rsp+1D0h+var_160], r13
0x18002c58a  mov     rdi, [rsp+1D0h+var_158]
0x18002c58f  mov     rax, [rdi]
0x18002c592  mov     rbx, [rax+0A0h]
0x18002c599  lea     rcx, [rsp+1D0h+var_160]
0x18002c59e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c5a3  lea     r8, [rsp+1D0h+var_160]
0x18002c5a8  mov     rdx, [rsp+1D0h+var_180]
0x18002c5ad  mov     rcx, rdi
0x18002c5b0  mov     rax, rbx
0x18002c5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5b8  test    eax, eax
0x18002c5ba  jns     short loc_18002C5CB
0x18002c5bc  lea     rdx, aSigninmgrGetus; "signInMgr->GetUserForContext(userContex"...
0x18002c5c3  mov     ecx, eax; this
0x18002c5c5  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c5cb  mov     [rsp+1D0h+var_168], r13
0x18002c5d0  mov     [rsp+1D0h+var_188], r13
0x18002c5d5  mov     [rsp+1D0h+var_170], r13
0x18002c5da  lea     rcx, [rsp+1D0h+var_188]
0x18002c5df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c5e4  lea     rdx, [rsp+1D0h+var_188]
0x18002c5e9  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x18002c5ee  test    eax, eax
0x18002c5f0  jns     short loc_18002C601
0x18002c5f2  lea     rdx, aWindowsFoundat_2; "Windows::Foundation::Collections::Inter"...
0x18002c5f9  mov     ecx, eax; this
0x18002c5fb  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c601  mov     [rbp+0D0h+var_D0], r13
0x18002c605  mov     r9d, 0Ah; unsigned int
0x18002c60b  lea     r8d, [r9+1]; unsigned int
0x18002c60f  lea     rdx, sourceString; "XboxUserId"
0x18002c616  lea     rcx, [rbp+0D0h+var_E8]; hstringHeader
0x18002c61a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002c61f  nop
0x18002c620  mov     rcx, [rsp+1D0h+var_188]
0x18002c625  mov     rax, [rcx]
0x18002c628  mov     rdx, [rbp+0D0h+var_D0]
0x18002c62c  mov     rax, [rax+68h]
0x18002c630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c635  test    eax, eax
0x18002c637  jns     short loc_18002C648
0x18002c639  lea     rdx, aPropertylookup; "propertyLookup->Append(xboxUserId.Get()"...
0x18002c640  mov     ecx, eax; this
0x18002c642  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c648  mov     rdi, [rsp+1D0h+var_188]
0x18002c64d  mov     rax, [rdi]
0x18002c650  mov     rbx, [rax+40h]
0x18002c654  lea     rcx, [rsp+1D0h+var_170]
0x18002c659  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c65e  lea     rdx, [rsp+1D0h+var_170]
0x18002c663  mov     rcx, rdi
0x18002c666  mov     rax, rbx
0x18002c669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c66e  test    eax, eax
0x18002c670  jns     short loc_18002C681
0x18002c672  lea     rdx, aPropertylookup_0; "propertyLookup->GetView(&propertyLookup"...
0x18002c679  mov     ecx, eax; this
0x18002c67b  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c681  mov     rdi, [rsp+1D0h+var_160]
0x18002c686  mov     rax, [rdi]
0x18002c689  mov     rbx, [rax+50h]
0x18002c68d  lea     rcx, [rsp+1D0h+var_168]
0x18002c692  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c697  lea     r8, [rsp+1D0h+var_168]
0x18002c69c  mov     rdx, [rsp+1D0h+var_170]
0x18002c6a1  mov     rcx, rdi
0x18002c6a4  mov     rax, rbx
0x18002c6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6ac  test    eax, eax
0x18002c6ae  jns     short loc_18002C6BF
0x18002c6b0  lea     rdx, aUserGetpropert; "user->GetPropertiesAsync(propertyLookup"...
0x18002c6b7  mov     ecx, eax; this
0x18002c6b9  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c6bf  mov     [rbp+0D0h+var_130], r13
0x18002c6c3  mov     [rsp+1D0h+ppv], r13
0x18002c6c8  lea     rdx, [rbp+0D0h+var_130]
0x18002c6cc  mov     rcx, [rsp+1D0h+var_168]
0x18002c6d1  call    ??$WaitForAsync@UIPropertySet@Collections@Foundation@Windows@@U1234@@ConnectedStorage@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@PEAPEAUIPropertySet@Collections@23@@Z; ConnectedStorage::WaitForAsync<Windows::Foundation::Collections::IPropertySet,Windows::Foundation::Collections::IPropertySet>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *,Windows::Foundation::Collections::IPropertySet * *)
0x18002c6d6  test    eax, eax
0x18002c6d8  jns     short loc_18002C6E9
0x18002c6da  lea     rdx, aWaitforasyncAs; "WaitForAsync(asyncOp.Get(), properties."...
0x18002c6e1  mov     ecx, eax; this
0x18002c6e3  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c6e9  mov     [rbp+0D0h+var_120], r13
0x18002c6ed  lea     rdx, [rbp+0D0h+var_120]
0x18002c6f1  lea     rcx, [rbp+0D0h+var_130]
0x18002c6f5  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18002c6fa  test    eax, eax
0x18002c6fc  jns     short loc_18002C70D
0x18002c6fe  lea     rdx, aPropertiesAsPr; "properties.As(&propertyMap)"
0x18002c705  mov     ecx, eax; this
0x18002c707  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c70d  mov     rdi, [rbp+0D0h+var_120]
0x18002c711  mov     rax, [rdi]
0x18002c714  mov     rbx, [rax+30h]
0x18002c718  lea     rcx, [rsp+1D0h+ppv]
0x18002c71d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c722  lea     r8, [rsp+1D0h+ppv]
0x18002c727  mov     rdx, [rbp+0D0h+var_D0]
0x18002c72b  mov     rcx, rdi
0x18002c72e  mov     rax, rbx
0x18002c731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c736  test    eax, eax
0x18002c738  jns     short loc_18002C749
0x18002c73a  lea     rdx, aPropertymapLoo; "propertyMap->Lookup(xboxUserId.Get(), &"...
0x18002c741  mov     ecx, eax; this
0x18002c743  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c749  mov     [rbp+0D0h+var_148], r13
0x18002c74d  lea     rdx, [rbp+0D0h+var_148]
0x18002c751  lea     rcx, [rsp+1D0h+ppv]
0x18002c756  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18002c75b  test    eax, eax
0x18002c75d  jns     short loc_18002C76E
0x18002c75f  lea     rdx, aInspAsVal; "insp.As(&val)"
0x18002c766  mov     ecx, eax; this
0x18002c768  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c76e  mov     rcx, [rbp+0D0h+var_148]
0x18002c772  mov     rax, [rcx]
0x18002c775  mov     rdx, r12
0x18002c778  mov     rax, [rax+98h]
0x18002c77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c784  test    eax, eax
0x18002c786  jns     short loc_18002C797
0x18002c788  lea     rdx, aValGetstringXu; "val->GetString(xuid)"
0x18002c78f  mov     ecx, eax; this
0x18002c791  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c797  lea     rcx, [rbp+0D0h+var_148]
0x18002c79b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7a0  nop
0x18002c7a1  lea     rcx, [rbp+0D0h+var_120]
0x18002c7a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7aa  nop
0x18002c7ab  lea     rcx, [rsp+1D0h+ppv]
0x18002c7b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7b5  nop
0x18002c7b6  lea     rcx, [rbp+0D0h+var_130]
0x18002c7ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7bf  nop
0x18002c7c0  mov     [rbp+0D0h+var_D0], r13
0x18002c7c4  lea     rcx, [rsp+1D0h+var_170]
0x18002c7c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7ce  nop
0x18002c7cf  lea     rcx, [rsp+1D0h+var_188]
0x18002c7d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7d9  nop
0x18002c7da  lea     rcx, [rsp+1D0h+var_168]
0x18002c7df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7e4  nop
0x18002c7e5  lea     rcx, [rsp+1D0h+var_160]
0x18002c7ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7ef  nop
0x18002c7f0  lea     rcx, [rsp+1D0h+var_158]
0x18002c7f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7fa  jmp     loc_18002C99F
0x18002c7ff  mov     [rsp+1D0h+ppv], r13
0x18002c804  lea     rcx, [rsp+1D0h+ppv]
0x18002c809  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c80e  lea     rax, [rsp+1D0h+ppv]
0x18002c813  mov     [rsp+1D0h+ReturnLength], rax; ppv
0x18002c818  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x18002c81f  xor     edx, edx; pUnkOuter
0x18002c821  lea     r8d, [rdx+4]; dwClsContext
0x18002c825  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x18002c82c  call    cs:__imp_CoCreateInstance
0x18002c832  test    eax, eax
0x18002c834  jns     short loc_18002C845
0x18002c836  lea     rdx, aCocreateinstan_0; "CoCreateInstance( __uuidof(XblAuthManag"...
0x18002c83d  mov     ecx, eax; this
0x18002c83f  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c845  lea     rcx, [rbp+0D0h+var_130]
0x18002c849  call    ??0?$weak_ptr@VAtomManager@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::AtomManager>::weak_ptr<ConnectedStorage::AtomManager>(void)
0x18002c84e  nop
0x18002c84f  test    r14b, r14b
0x18002c852  jz      loc_18002C914
0x18002c858  call    cs:__imp_CoImpersonateClient
0x18002c85e  test    eax, eax
0x18002c860  js      short loc_18002C86A
0x18002c862  call    cs:__imp_CoRevertToSelf
0x18002c868  jmp     short loc_18002C895
0x18002c86a  mov     dil, r13b
0x18002c86d  lea     rdx, [rsp+1D0h+var_180]
0x18002c872  lea     rcx, [rbp+0D0h+var_120]
0x18002c876  call    ??$make_shared@VContextImpersonator@ConnectedStorage@@AEAPEAX@std@@YA?AV?$shared_ptr@VContextImpersonator@ConnectedStorage@@@0@AEAPEAX@Z; std::make_shared<ConnectedStorage::ContextImpersonator,void * &>(void * &)
0x18002c87b  mov     rdx, rax
0x18002c87e  lea     rcx, [rbp+0D0h+var_130]
0x18002c882  call    ??4?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(std::shared_ptr<ConnectedStorage::ActivatingContainer const> &&)
0x18002c887  lea     rcx, [rbp+0D0h+var_120]
0x18002c88b  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x18002c890  mov     rbx, [rsp+1D0h+var_180]
0x18002c895  mov     [rsp+1D0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18002c89d  mov     [rsp+1D0h+pAuthInfo], r13; pAuthInfo
0x18002c8a2  mov     [rsp+1D0h+dwImpLevel], 3; dwImpLevel
0x18002c8aa  mov     dword ptr [rsp+1D0h+ReturnLength], r13d; dwAuthnLevel
0x18002c8af  xor     r9d, r9d; pServerPrincName
0x18002c8b2  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18002c8b5  mov     r8d, edx; dwAuthzSvc
0x18002c8b8  mov     rcx, [rsp+1D0h+ppv]; pProxy
0x18002c8bd  call    cs:__imp_CoSetProxyBlanket
0x18002c8c3  test    dil, dil
0x18002c8c6  jz      short loc_18002C914
0x18002c8c8  mov     dword ptr [rsp+1D0h+var_188], r13d
0x18002c8cd  mov     qword ptr [rbp+0D0h+hstringHeader.Reserved], rbx
0x18002c8d1  mov     qword ptr [rbp+0D0h+hstringHeader.Reserved+8], r15
0x18002c8d5  mov     qword ptr [rbp+0D0h+hstringHeader.Reserved+10h], r12
0x18002c8d9  mov     byte ptr [rbp+0D0h+var_F8], r14b
  ... truncated ...
```
