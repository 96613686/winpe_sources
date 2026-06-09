# OSIntegration::DEH::PackagedComExtensionHandler::ParseServer(IXMLDOMElement *,OSIntegration::DEH::IComServerRegistration *,std::optional<AppModel::TrustLevel>,std::optional<AppModel::RuntimeBehavior>,std::optional<AppModel::BnoIsolation>)

- ea: `0x18016b770`
- end: `0x18016bab1`
- name: `?ParseServer@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUIComServerRegistration@23@V?$optional@W4TrustLevel@AppModel@@@std@@V?$optional@W4RuntimeBehavior@AppModel@@@7@V?$optional@W4BnoIsolation@AppModel@@@7@@Z`
- size: `833`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801686ac`
- `0x18016bf0c`
- `0x18016c4e4`

## callees

- `0x18000b9e0`
- `0x18007ccec`
- `0x180083aa4`
- `0x18009aff4`
- `0x180139954`
- `0x18016b770`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b7a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b7ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b85c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b8d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ba78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ba83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ba8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ba9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b7a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b7ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b85c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b8d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ba78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ba83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ba8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ba9c`

## string_xrefs

- `0x18016b81c`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016b88f`: `ParseAndRetrieveLocalizableAttribute( root, Internal::PackagedComConstants::displayNameAttribute, displayName.GetAddressOf(), &displayNameFound)`
- `0x18016b908`: `ParseAndRetrieveAttribute( root, Internal::PackagedComConstants::launchAndActivationPermissionsAttribute, launchAndActivationPermission.GetAddressOf(), &launchAndActivationPermissionFound)`
- `0x18016b9a9`: `serverReg->SetTrustLevel(extensionTrustLevel.value())`
- `0x18016b9e1`: `serverReg->SetRuntimeBehavior(extensionRuntimeBehavior.value())`
- `0x18016b815`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 OSIntegration::DEH::PackagedComExtensionHandler::ParseServer(
        OSIntegration::Tools **a1,
        struct IXMLDOMElement *a2,
        __int64 a3,
        ...)
{
  int v6; // eax
  unsigned int v7; // ebx
  const char *v8; // rax
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 (__fastcall *v17)(__int64, _QWORD); // rbx
  unsigned int *v18; // rax
  int v19; // eax
  __int64 (__fastcall *v20)(__int64, _QWORD); // rbx
  unsigned int *v21; // rax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  char *v27; // [rsp+28h] [rbp-40h]
  int v28; // [rsp+30h] [rbp-38h] BYREF
  HSTRING v29; // [rsp+38h] [rbp-30h] BYREF
  HSTRING string; // [rsp+40h] [rbp-28h] BYREF
  HSTRING v31; // [rsp+48h] [rbp-20h] BYREF
  HSTRING v32; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+30h]
  __int64 v34; // [rsp+B8h] [rbp+50h] BYREF
  va_list va; // [rsp+B8h] [rbp+50h]
  __int64 v36; // [rsp+C0h] [rbp+58h] BYREF
  va_list va1; // [rsp+C0h] [rbp+58h]
  __int64 v38; // [rsp+C8h] [rbp+60h]
  va_list va2; // [rsp+D0h] [rbp+68h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v34 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v36 = va_arg(va2, _QWORD);
  v38 = va_arg(va2, _QWORD);
  string = 0;
  v29 = 0;
  LOWORD(v28) = 0;
  WindowsDeleteString(0);
  v31 = 0;
  WindowsDeleteString(0);
  v32 = 0;
  v6 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName(a1, a2, &v32, &v31);
  v7 = v6;
  if ( v6 < 0 )
  {
    LODWORD(v27) = v6;
    v8 = "ParseAndRetrieveApplicationIdAndDisplayName( root, applicationId.GetAddressOf(), applicationDisplayName.GetAddressOf())";
    v9 = 480;
LABEL_5:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseServer",
      v8,
      v27,
      v28);
    goto LABEL_36;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)a3 + 48LL))(a3, v32);
  v7 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v27) = v10;
    v8 = "serverReg->SetApplicationId(applicationId.Get())";
    v9 = 482;
    goto LABEL_5;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)a3 + 56LL))(a3, v31);
  v7 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v27) = v11;
    v8 = "serverReg->SetApplicationDisplayName(applicationDisplayName.Get())";
    v9 = 483;
    goto LABEL_5;
  }
  WindowsDeleteString(string);
  string = 0;
  v12 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveLocalizableAttribute(
          (OSIntegration::DEH::PackagedComExtensionHandler *)a1,
          a2,
          L"DisplayName",
          &string,
          (bool *)&v28);
  v7 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v27) = v12;
    v8 = "ParseAndRetrieveLocalizableAttribute( root, Internal::PackagedComConstants::displayNameAttribute, displayName.G"
         "etAddressOf(), &displayNameFound)";
    v9 = 489;
    goto LABEL_5;
  }
  if ( (_BYTE)v28 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)a3 + 64LL))(a3, string);
    v7 = v13;
    if ( v13 < 0 )
    {
      LODWORD(v27) = v13;
      v8 = "serverReg->SetDisplayName(displayName.Get())";
      v9 = 493;
      goto LABEL_5;
    }
  }
  WindowsDeleteString(v29);
  v29 = 0;
  v15 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
          v14,
          a2,
          L"LaunchAndActivationPermission",
          &v29,
          (bool *)&v28 + 1);
  v7 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v27) = v15;
    v8 = "ParseAndRetrieveAttribute( root, Internal::PackagedComConstants::launchAndActivationPermissionsAttribute, launc"
         "hAndActivationPermission.GetAddressOf(), &launchAndActivationPermissionFound)";
    v9 = 500;
    goto LABEL_5;
  }
  if ( BYTE1(v28) )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)a3 + 72LL))(a3, v29);
    v7 = v16;
    if ( v16 < 0 )
    {
      LODWORD(v27) = v16;
      v8 = "serverReg->SetLaunchAndActivationPermission(launchAndActivationPermission.Get())";
      v9 = 504;
      goto LABEL_5;
    }
  }
  if ( BYTE4(v34)
    && BYTE4(v36)
    && !*(_DWORD *)std::optional<unsigned int>::value((__int64 *)va)
    && *(_DWORD *)std::optional<unsigned int>::value((__int64 *)va1) == 3 )
  {
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a3 + 80LL);
    v18 = (unsigned int *)std::optional<unsigned int>::value((__int64 *)va);
    v19 = v17(a3, *v18);
    v7 = v19;
    if ( v19 < 0 )
    {
      LODWORD(v27) = v19;
      v8 = "serverReg->SetTrustLevel(extensionTrustLevel.value())";
      v9 = 515;
      goto LABEL_5;
    }
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a3 + 88LL);
    v21 = (unsigned int *)std::optional<unsigned int>::value((__int64 *)va1);
    v22 = v20(a3, *v21);
    v7 = v22;
    if ( v22 < 0 )
    {
      LODWORD(v27) = v22;
      v8 = "serverReg->SetRuntimeBehavior(extensionRuntimeBehavior.value())";
      v9 = 516;
      goto LABEL_5;
    }
  }
  else
  {
    v23 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a3 + 80LL))(a3, 1);
    v7 = v23;
    if ( v23 < 0 )
    {
      LODWORD(v27) = v23;
      v8 = "serverReg->SetTrustLevel(AppModel::TrustLevel_FullTrust)";
      v9 = 520;
      goto LABEL_5;
    }
    v24 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a3 + 88LL))(a3, 1);
    v7 = v24;
    if ( v24 < 0 )
    {
      LODWORD(v27) = v24;
      v8 = "serverReg->SetRuntimeBehavior(AppModel::RuntimeBehavior_DesktopBridge)";
      v9 = 521;
      goto LABEL_5;
    }
  }
  if ( BYTE4(v38) && BYTE4(v34) && (_DWORD)v34 == 1 )
    v25 = (unsigned int)v38;
  else
    v25 = 0;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a3 + 96LL))(a3, v25);
  v7 = 0;
LABEL_36:
  WindowsDeleteString(v31);
  WindowsDeleteString(v32);
  WindowsDeleteString(v29);
  v29 = 0;
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x18016b770  mov     [rsp-30h+arg_18], r9
0x18016b775  push    rbp
0x18016b776  push    rbx
0x18016b777  push    rsi
0x18016b778  push    rdi
0x18016b779  push    r14
0x18016b77b  push    r15
0x18016b77d  mov     rbp, rsp
0x18016b780  sub     rsp, 68h
0x18016b784  mov     rdi, r8
0x18016b787  mov     rsi, rdx
0x18016b78a  mov     r14, rcx
0x18016b78d  xor     r15d, r15d
0x18016b790  mov     [rbp+string], r15
0x18016b794  mov     [rbp+var_30], r15
0x18016b798  mov     [rbp+var_38], r15b
0x18016b79c  mov     [rbp+var_37], r15b
0x18016b7a0  xor     ecx, ecx; string
0x18016b7a2  call    cs:__imp_WindowsDeleteString
0x18016b7a8  mov     [rbp+var_20], r15
0x18016b7ac  xor     ecx, ecx; string
0x18016b7ae  call    cs:__imp_WindowsDeleteString
0x18016b7b4  mov     [rbp+var_18], r15
0x18016b7b8  lea     r9, [rbp+var_20]; HSTRING *
0x18016b7bc  lea     r8, [rbp+var_18]; HSTRING *
0x18016b7c0  mov     rdx, rsi; struct IXMLDOMElement *
0x18016b7c3  mov     rcx, r14; this
0x18016b7c6  call    ?ParseAndRetrieveApplicationIdAndDisplayName@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAPEAUHSTRING__@@1@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName(IXMLDOMElement *,HSTRING__ * *,HSTRING__ * *)
0x18016b7cb  mov     ebx, eax
0x18016b7cd  test    eax, eax
0x18016b7cf  jns     short loc_18016B7E3
0x18016b7d1  mov     dword ptr [rsp+68h+var_40], eax
0x18016b7d5  lea     rax, aParseandretrie_58; "ParseAndRetrieveApplicationIdAndDisplay"...
0x18016b7dc  mov     edx, 1E0h
0x18016b7e1  jmp     short loc_18016B80C
0x18016b7e3  mov     rax, [rdi]
0x18016b7e6  mov     rdx, [rbp+var_18]
0x18016b7ea  mov     rcx, rdi
0x18016b7ed  mov     rax, [rax+30h]
0x18016b7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b7f6  mov     ebx, eax
0x18016b7f8  test    eax, eax
0x18016b7fa  jns     short loc_18016B82D
0x18016b7fc  mov     dword ptr [rsp+68h+var_40], eax; char *
0x18016b800  lea     rax, aServerregSetap_0; "serverReg->SetApplicationId(application"...
0x18016b807  mov     edx, 1E2h; void *
0x18016b80c  mov     rcx, [rbp+30h]; this
0x18016b810  mov     [rsp+68h+var_48], rax; char *
0x18016b815  lea     r9, aOsintegrationD_409; "OSIntegration::DEH::PackagedComExtensio"...
0x18016b81c  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b823  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b828  jmp     loc_18016BA74
0x18016b82d  mov     rax, [rdi]
0x18016b830  mov     rdx, [rbp+var_20]
0x18016b834  mov     rcx, rdi
0x18016b837  mov     rax, [rax+38h]
0x18016b83b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b840  mov     ebx, eax
0x18016b842  test    eax, eax
0x18016b844  jns     short loc_18016B858
0x18016b846  mov     dword ptr [rsp+68h+var_40], eax
0x18016b84a  lea     rax, aServerregSetap; "serverReg->SetApplicationDisplayName(ap"...
0x18016b851  mov     edx, 1E3h
0x18016b856  jmp     short loc_18016B80C
0x18016b858  mov     rcx, [rbp+string]; string
0x18016b85c  call    cs:__imp_WindowsDeleteString
0x18016b862  mov     [rbp+string], r15
0x18016b866  lea     rax, [rbp+var_38]
0x18016b86a  mov     [rsp+68h+var_48], rax; bool *
0x18016b86f  lea     r9, [rbp+string]; HSTRING *
0x18016b873  lea     r8, aDisplayname; "DisplayName"
0x18016b87a  mov     rdx, rsi; struct IXMLDOMElement *
0x18016b87d  mov     rcx, r14; this
0x18016b880  call    ?ParseAndRetrieveLocalizableAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveLocalizableAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016b885  mov     ebx, eax
0x18016b887  test    eax, eax
0x18016b889  jns     short loc_18016B8A0
0x18016b88b  mov     dword ptr [rsp+68h+var_40], eax
0x18016b88f  lea     rax, aParseandretrie_37; "ParseAndRetrieveLocalizableAttribute( r"...
0x18016b896  mov     edx, 1E9h
0x18016b89b  jmp     loc_18016B80C
0x18016b8a0  cmp     [rbp+var_38], r15b
0x18016b8a4  jz      short loc_18016B8D4
0x18016b8a6  mov     rax, [rdi]
0x18016b8a9  mov     rdx, [rbp+string]
0x18016b8ad  mov     rcx, rdi
0x18016b8b0  mov     rax, [rax+40h]
0x18016b8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b8b9  mov     ebx, eax
0x18016b8bb  test    eax, eax
0x18016b8bd  jns     short loc_18016B8D4
0x18016b8bf  mov     dword ptr [rsp+68h+var_40], eax
0x18016b8c3  lea     rax, aServerregSetdi; "serverReg->SetDisplayName(displayName.G"...
0x18016b8ca  mov     edx, 1EDh
0x18016b8cf  jmp     loc_18016B80C
0x18016b8d4  mov     rcx, [rbp+var_30]; string
0x18016b8d8  call    cs:__imp_WindowsDeleteString
0x18016b8de  mov     [rbp+var_30], r15
0x18016b8e2  lea     rax, [rbp+var_37]
0x18016b8e6  mov     [rsp+68h+var_48], rax; bool *
0x18016b8eb  lea     r9, [rbp+var_30]; HSTRING *
0x18016b8ef  lea     r8, aLaunchandactiv; "LaunchAndActivationPermission"
0x18016b8f6  mov     rdx, rsi; struct IXMLDOMElement *
0x18016b8f9  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016b8fe  mov     ebx, eax
0x18016b900  test    eax, eax
0x18016b902  jns     short loc_18016B919
0x18016b904  mov     dword ptr [rsp+68h+var_40], eax
0x18016b908  lea     rax, aParseandretrie_83; "ParseAndRetrieveAttribute( root, Intern"...
0x18016b90f  mov     edx, 1F4h
0x18016b914  jmp     loc_18016B80C
0x18016b919  cmp     [rbp+var_37], r15b
0x18016b91d  jz      short loc_18016B94D
0x18016b91f  mov     rax, [rdi]
0x18016b922  mov     rdx, [rbp+var_30]
0x18016b926  mov     rcx, rdi
0x18016b929  mov     rax, [rax+48h]
0x18016b92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b932  mov     ebx, eax
0x18016b934  test    eax, eax
0x18016b936  jns     short loc_18016B94D
0x18016b938  mov     dword ptr [rsp+68h+var_40], eax
0x18016b93c  lea     rax, aServerregSetla; "serverReg->SetLaunchAndActivationPermis"...
0x18016b943  mov     edx, 1F8h
0x18016b948  jmp     loc_18016B80C
0x18016b94d  mov     esi, 1
0x18016b952  cmp     byte ptr [rbp+arg_18+4], r15b
0x18016b956  jz      loc_18016B9F2
0x18016b95c  cmp     byte ptr [rbp+arg_20+4], r15b
0x18016b960  jz      loc_18016B9F2
0x18016b966  lea     rcx, [rbp+arg_18]
0x18016b96a  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x18016b96f  cmp     [rax], r15d
0x18016b972  jnz     short loc_18016B9F2
0x18016b974  lea     rcx, [rbp+arg_20]
0x18016b978  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x18016b97d  cmp     dword ptr [rax], 3
0x18016b980  jnz     short loc_18016B9F2
0x18016b982  mov     rax, [rdi]
0x18016b985  mov     rbx, [rax+50h]
0x18016b989  lea     rcx, [rbp+arg_18]
0x18016b98d  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x18016b992  mov     edx, [rax]
0x18016b994  mov     rcx, rdi
0x18016b997  mov     rax, rbx
0x18016b99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b99f  mov     ebx, eax
0x18016b9a1  test    eax, eax
0x18016b9a3  jns     short loc_18016B9BA
0x18016b9a5  mov     dword ptr [rsp+68h+var_40], eax
0x18016b9a9  lea     rax, aServerregSettr; "serverReg->SetTrustLevel(extensionTrust"...
0x18016b9b0  mov     edx, 203h
0x18016b9b5  jmp     loc_18016B80C
0x18016b9ba  mov     rax, [rdi]
0x18016b9bd  mov     rbx, [rax+58h]
0x18016b9c1  lea     rcx, [rbp+arg_20]
0x18016b9c5  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x18016b9ca  mov     edx, [rax]
0x18016b9cc  mov     rcx, rdi
0x18016b9cf  mov     rax, rbx
0x18016b9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b9d7  mov     ebx, eax
0x18016b9d9  test    eax, eax
0x18016b9db  jns     short loc_18016BA4A
0x18016b9dd  mov     dword ptr [rsp+68h+var_40], eax
0x18016b9e1  lea     rax, aServerregSetru; "serverReg->SetRuntimeBehavior(extension"...
0x18016b9e8  mov     edx, 204h
0x18016b9ed  jmp     loc_18016B80C
0x18016b9f2  mov     rax, [rdi]
0x18016b9f5  mov     edx, esi
0x18016b9f7  mov     rcx, rdi
0x18016b9fa  mov     rax, [rax+50h]
0x18016b9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ba03  mov     ebx, eax
0x18016ba05  test    eax, eax
0x18016ba07  jns     short loc_18016BA1E
0x18016ba09  mov     dword ptr [rsp+68h+var_40], eax
0x18016ba0d  lea     rax, aServerregSettr_0; "serverReg->SetTrustLevel(AppModel::Trus"...
0x18016ba14  mov     edx, 208h
0x18016ba19  jmp     loc_18016B80C
0x18016ba1e  mov     rax, [rdi]
0x18016ba21  mov     edx, esi
0x18016ba23  mov     rcx, rdi
0x18016ba26  mov     rax, [rax+58h]
0x18016ba2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ba2f  mov     ebx, eax
0x18016ba31  test    eax, eax
0x18016ba33  jns     short loc_18016BA4A
0x18016ba35  mov     dword ptr [rsp+68h+var_40], eax
0x18016ba39  lea     rax, aServerregSetru_0; "serverReg->SetRuntimeBehavior(AppModel:"...
0x18016ba40  mov     edx, 209h
0x18016ba45  jmp     loc_18016B80C
0x18016ba4a  cmp     [rbp+arg_2C], r15b
0x18016ba4e  jz      short loc_18016BA60
0x18016ba50  cmp     byte ptr [rbp+arg_18+4], r15b
0x18016ba54  jz      short loc_18016BA60
0x18016ba56  cmp     dword ptr [rbp+arg_18], esi
0x18016ba59  jnz     short loc_18016BA60
0x18016ba5b  mov     edx, [rbp+arg_28]
0x18016ba5e  jmp     short loc_18016BA62
0x18016ba60  xor     edx, edx
0x18016ba62  mov     rax, [rdi]
0x18016ba65  mov     rcx, rdi
0x18016ba68  mov     rax, [rax+60h]
0x18016ba6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ba71  mov     ebx, r15d
0x18016ba74  mov     rcx, [rbp+var_20]; string
0x18016ba78  call    cs:__imp_WindowsDeleteString
0x18016ba7e  nop
0x18016ba7f  mov     rcx, [rbp+var_18]; string
0x18016ba83  call    cs:__imp_WindowsDeleteString
0x18016ba89  nop
0x18016ba8a  mov     rcx, [rbp+var_30]; string
0x18016ba8e  call    cs:__imp_WindowsDeleteString
0x18016ba94  mov     [rbp+var_30], r15
0x18016ba98  mov     rcx, [rbp+string]; string
0x18016ba9c  call    cs:__imp_WindowsDeleteString
0x18016baa2  mov     eax, ebx
0x18016baa4  add     rsp, 68h
0x18016baa8  pop     r15
0x18016baaa  pop     r14
0x18016baac  pop     rdi
0x18016baad  pop     rsi
0x18016baae  pop     rbx
0x18016baaf  pop     rbp
0x18016bab0  retn
```
