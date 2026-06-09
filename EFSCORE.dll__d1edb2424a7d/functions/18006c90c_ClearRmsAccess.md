# ClearRmsAccess

- ea: `0x18006c90c`
- end: `0x18006cc7d`
- name: `ClearRmsAccess`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006c764`

## callees

- `0x18000b12c`
- `0x180061e84`
- `0x18006ae90`
- `0x18006af0c`
- `0x18006af54`
- `0x18006af9c`
- `0x18006b878`
- `0x18006c90c`
- `0x18006d458`
- `0x18006db58`
- `0x1800dddf0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18006c95f`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18006c95f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18006c9c9`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18006cc5d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18006c9c9`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18006cc5d`
- `winmsipc!__imp_IpcpClearKeys` at `0x18006c92f`
- `winmsipc!__imp_IpcpClearKeys` at `0x18006c92f`

## string_xrefs

- `0x18006c93f`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`
- `0x18006c9a8`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`
- `0x18006ca31`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`
- `0x18006ca72`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`
- `0x18006cadb`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`
- `0x18006cb1e`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`
- `0x18006cb7c`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`
- `0x18006cbd5`: `onecoreuap\ds\security\efs\rmshost\rmsinterface\rmsinterface.cxx`
- `0x18006c973`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
__int64 __fastcall ClearRmsAccess(int (__fastcall ***a1)(_QWORD, GUID *, __int64 *))
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  int v7; // edi
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rdi
  int v10; // eax
  int v11; // eax
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, __int64, _QWORD, __int64 *); // rdi
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rcx
  __int64 v17; // rdx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rsi
  int v20; // eax
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rdi
  int v23; // edx
  __int64 v24; // r8
  __int64 v25; // rdx
  int v26; // [rsp+20h] [rbp-39h]
  __int64 v27; // [rsp+30h] [rbp-29h] BYREF
  __int64 v28; // [rsp+38h] [rbp-21h] BYREF
  __int64 v29; // [rsp+40h] [rbp-19h] BYREF
  __int64 v30; // [rsp+48h] [rbp-11h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-9h] BYREF
  int (__fastcall ***v32)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-1h] BYREF
  __int64 v33; // [rsp+60h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v35; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v32 = a1;
  v1 = IpcpClearKeys();
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x161,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
      (const char *)(unsigned int)v1,
      v26);
    return v2;
  }
  v4 = RoInitialize(1);
  v27 = 0;
  v35 = 0;
  v5 = v4;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
         v35,
         (__int64)&v27);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
      (const char *)(unsigned int)v6,
      v26);
LABEL_5:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    if ( v5 >= 0 )
      RoUninitialize();
    return (unsigned int)v7;
  }
  v8 = v27;
  v28 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 88LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v35 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"https://login.windows.net",
    0x1Au,
    0x19u);
  v10 = v9(v8, v35, &v28);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
      (const char *)(unsigned int)v10,
      v26);
LABEL_10:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    goto LABEL_5;
  }
  v30 = 0;
  v11 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
          v28,
          (__int64)&v30);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
      (const char *)(unsigned int)v11,
      v26);
LABEL_13:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    goto LABEL_10;
  }
  v12 = v27;
  v29 = 0;
  v13 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v32);
  v15 = v13(v12, v30, *(_QWORD *)(v14 + 24), &v29);
  v7 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
      (const char *)(unsigned int)v15,
      v26);
LABEL_16:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    goto LABEL_13;
  }
  v31 = 0;
  v7 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccount *,Windows::Security::Credentials::IWebAccount>(
         v29,
         (__int64)&v31);
  if ( v7 < 0 )
  {
    v17 = 369;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
      (const char *)(unsigned int)v7,
      v26);
LABEL_20:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    goto LABEL_16;
  }
  v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
  if ( v31 )
  {
    v33 = 0;
    v19 = **v31;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v20 = v19(v18, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v33);
    v7 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x175,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
        (const char *)(unsigned int)v20,
        v26);
LABEL_24:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      goto LABEL_20;
    }
    v21 = v33;
    v32 = 0;
    v22 = *(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v33 + 72LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v7 = v22(v21, &v32);
    if ( v7 < 0 )
    {
      v25 = 377;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\rmshost\\rmsinterface\\rmsinterface.cxx",
        (const char *)(unsigned int)v7,
        v26);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
      goto LABEL_24;
    }
    v7 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
           v32,
           v23,
           v24);
    if ( v7 < 0 )
    {
      v25 = 378;
      goto LABEL_27;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  }
  v7 = EfsConfig_SetRmsWebAccountId(v16);
  if ( v7 < 0 )
  {
    v17 = 382;
    goto LABEL_19;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  if ( v5 >= 0 )
    RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18006c90c  push    rbp
0x18006c90e  push    rbx
0x18006c90f  push    rsi
0x18006c910  push    rdi
0x18006c911  lea     rbp, [rsp-3Fh]
0x18006c916  sub     rsp, 98h
0x18006c91d  mov     rax, cs:__security_cookie
0x18006c924  xor     rax, rsp
0x18006c927  mov     [rbp+57h+var_28], rax
0x18006c92b  mov     [rbp+57h+var_58], rcx
0x18006c92f  call    cs:__imp_IpcpClearKeys
0x18006c935  mov     ebx, eax
0x18006c937  test    eax, eax
0x18006c939  jns     short loc_18006C95A
0x18006c93b  mov     rcx, [rbp+5Fh]; this
0x18006c93f  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006c946  mov     r9d, eax; char *
0x18006c949  mov     edx, 161h; void *
0x18006c94e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c953  mov     eax, ebx
0x18006c955  jmp     loc_18006CC65
0x18006c95a  mov     ecx, 1
0x18006c95f  call    cs:__imp_RoInitialize
0x18006c965  mov     r9d, 45h ; 'E'; unsigned int
0x18006c96b  mov     [rbp+57h+var_80], 0
0x18006c973  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18006c97a  mov     [rbp+57h+var_30], 0
0x18006c982  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18006c986  mov     ebx, eax
0x18006c988  lea     r8d, [r9+1]; unsigned int
0x18006c98c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006c991  mov     rcx, [rbp+57h+var_30]
0x18006c995  lea     rdx, [rbp+57h+var_80]
0x18006c999  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x18006c99e  mov     edi, eax
0x18006c9a0  test    eax, eax
0x18006c9a2  jns     short loc_18006C9D6
0x18006c9a4  mov     rcx, [rbp+5Fh]; this
0x18006c9a8  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006c9af  mov     r9d, eax; char *
0x18006c9b2  mov     edx, 169h; void *
0x18006c9b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c9bc  lea     rcx, [rbp+57h+var_80]
0x18006c9c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c9c5  test    ebx, ebx
0x18006c9c7  js      short loc_18006C9CF
0x18006c9c9  call    cs:__imp_RoUninitialize
0x18006c9cf  mov     eax, edi
0x18006c9d1  jmp     loc_18006CC65
0x18006c9d6  mov     rsi, [rbp+57h+var_80]
0x18006c9da  lea     rcx, [rbp+57h+var_78]
0x18006c9de  mov     [rbp+57h+var_78], 0
0x18006c9e6  mov     rax, [rsi]
0x18006c9e9  mov     rdi, [rax+58h]
0x18006c9ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c9f2  mov     r9d, 19h; unsigned int
0x18006c9f8  mov     [rbp+57h+var_30], 0
0x18006ca00  lea     rdx, aHttpsLoginWind; "https://login.windows.net"
0x18006ca07  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18006ca0b  lea     r8d, [r9+1]; unsigned int
0x18006ca0f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006ca14  mov     rdx, [rbp+57h+var_30]
0x18006ca18  lea     r8, [rbp+57h+var_78]
0x18006ca1c  mov     rcx, rsi
0x18006ca1f  mov     rax, rdi
0x18006ca22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca27  mov     edi, eax
0x18006ca29  test    eax, eax
0x18006ca2b  jns     short loc_18006CA53
0x18006ca2d  mov     rcx, [rbp+5Fh]; this
0x18006ca31  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006ca38  mov     r9d, eax; char *
0x18006ca3b  mov     edx, 16Bh; void *
0x18006ca40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ca45  lea     rcx, [rbp+57h+var_78]
0x18006ca49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ca4e  jmp     loc_18006C9BC
0x18006ca53  mov     rcx, [rbp+57h+var_78]
0x18006ca57  lea     rdx, [rbp+57h+var_68]
0x18006ca5b  mov     [rbp+57h+var_68], 0
0x18006ca63  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *)
0x18006ca68  mov     edi, eax
0x18006ca6a  test    eax, eax
0x18006ca6c  jns     short loc_18006CA91
0x18006ca6e  mov     rcx, [rbp+5Fh]; this
0x18006ca72  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006ca79  mov     r9d, eax; char *
0x18006ca7c  mov     edx, 16Dh; void *
0x18006ca81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ca86  lea     rcx, [rbp+57h+var_68]
0x18006ca8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ca8f  jmp     short loc_18006CA45
0x18006ca91  mov     rsi, [rbp+57h+var_80]
0x18006ca95  lea     rcx, [rbp+57h+var_70]
0x18006ca99  mov     [rbp+57h+var_70], 0
0x18006caa1  mov     rax, [rsi]
0x18006caa4  mov     rdi, [rax+50h]
0x18006caa8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006caad  lea     rdx, [rbp+57h+var_58]
0x18006cab1  lea     rcx, [rbp+57h+hstringHeader]
0x18006cab5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18006caba  mov     rdx, [rbp+57h+var_68]
0x18006cabe  lea     r9, [rbp+57h+var_70]
0x18006cac2  mov     rcx, rsi
0x18006cac5  mov     r8, [rax+18h]
0x18006cac9  mov     rax, rdi
0x18006cacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cad1  mov     edi, eax
0x18006cad3  test    eax, eax
0x18006cad5  jns     short loc_18006CAFA
0x18006cad7  mov     rcx, [rbp+5Fh]; this
0x18006cadb  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006cae2  mov     r9d, eax; char *
0x18006cae5  mov     edx, 16Fh; void *
0x18006caea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006caef  lea     rcx, [rbp+57h+var_70]
0x18006caf3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006caf8  jmp     short loc_18006CA86
0x18006cafa  mov     rcx, [rbp+57h+var_70]
0x18006cafe  lea     rdx, [rbp+57h+var_60]
0x18006cb02  mov     [rbp+57h+var_60], 0
0x18006cb0a  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccount@Credentials@Security@Windows@@UIWebAccount@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccount *,Windows::Security::Credentials::IWebAccount>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>>,tagCOWAIT_FLAGS,void *)
0x18006cb0f  mov     edi, eax
0x18006cb11  test    eax, eax
0x18006cb13  jns     short loc_18006CB38
0x18006cb15  mov     edx, 171h; void *
0x18006cb1a  mov     rcx, [rbp+5Fh]; this
0x18006cb1e  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006cb25  mov     r9d, edi; char *
0x18006cb28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cb2d  lea     rcx, [rbp+57h+var_60]
0x18006cb31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cb36  jmp     short loc_18006CAEF
0x18006cb38  mov     rdi, [rbp+57h+var_60]
0x18006cb3c  test    rdi, rdi
0x18006cb3f  jz      loc_18006CC17
0x18006cb45  mov     [rbp+57h+var_50], 0
0x18006cb4d  lea     rcx, [rbp+57h+var_50]
0x18006cb51  mov     rax, [rdi]
0x18006cb54  mov     rsi, [rax]
0x18006cb57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cb5c  lea     r8, [rbp+57h+var_50]
0x18006cb60  mov     rcx, rdi
0x18006cb63  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x18006cb6a  mov     rax, rsi
0x18006cb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb72  mov     edi, eax
0x18006cb74  test    eax, eax
0x18006cb76  jns     short loc_18006CB9B
0x18006cb78  mov     rcx, [rbp+5Fh]; this
0x18006cb7c  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006cb83  mov     r9d, eax; char *
0x18006cb86  mov     edx, 175h; void *
0x18006cb8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cb90  lea     rcx, [rbp+57h+var_50]
0x18006cb94  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cb99  jmp     short loc_18006CB2D
0x18006cb9b  mov     rsi, [rbp+57h+var_50]
0x18006cb9f  lea     rcx, [rbp+57h+var_58]
0x18006cba3  mov     [rbp+57h+var_58], 0
0x18006cbab  mov     rax, [rsi]
0x18006cbae  mov     rdi, [rax+48h]
0x18006cbb2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cbb7  lea     rdx, [rbp+57h+var_58]
0x18006cbbb  mov     rcx, rsi
0x18006cbbe  mov     rax, rdi
0x18006cbc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cbc6  mov     edi, eax
0x18006cbc8  test    eax, eax
0x18006cbca  jns     short loc_18006CBEF
0x18006cbcc  mov     edx, 179h; void *
0x18006cbd1  mov     rcx, [rbp+5Fh]; this
0x18006cbd5  lea     r8, aOnecoreuapDsSe_7; "onecoreuap\\ds\\security\\efs\\rmshost"...
0x18006cbdc  mov     r9d, edi; char *
0x18006cbdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cbe4  lea     rcx, [rbp+57h+var_58]
0x18006cbe8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cbed  jmp     short loc_18006CB90
0x18006cbef  mov     rcx, [rbp+57h+var_58]
0x18006cbf3  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x18006cbf8  mov     edi, eax
0x18006cbfa  test    eax, eax
0x18006cbfc  jns     short loc_18006CC05
0x18006cbfe  mov     edx, 17Ah
0x18006cc03  jmp     short loc_18006CBD1
0x18006cc05  lea     rcx, [rbp+57h+var_58]
0x18006cc09  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cc0e  lea     rcx, [rbp+57h+var_50]
0x18006cc12  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cc17  call    ?EfsConfig_SetRmsWebAccountId@@YAJPEBG@Z; EfsConfig_SetRmsWebAccountId(ushort const *)
0x18006cc1c  mov     edi, eax
0x18006cc1e  test    eax, eax
0x18006cc20  jns     short loc_18006CC2C
0x18006cc22  mov     edx, 17Eh
0x18006cc27  jmp     loc_18006CB1A
0x18006cc2c  lea     rcx, [rbp+57h+var_60]
0x18006cc30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cc35  lea     rcx, [rbp+57h+var_70]
0x18006cc39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cc3e  lea     rcx, [rbp+57h+var_68]
0x18006cc42  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cc47  lea     rcx, [rbp+57h+var_78]
0x18006cc4b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cc50  lea     rcx, [rbp+57h+var_80]
0x18006cc54  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006cc59  test    ebx, ebx
0x18006cc5b  js      short loc_18006CC63
0x18006cc5d  call    cs:__imp_RoUninitialize
0x18006cc63  xor     eax, eax
0x18006cc65  mov     rcx, [rbp+57h+var_28]
0x18006cc69  xor     rcx, rsp; StackCookie
0x18006cc6c  call    __security_check_cookie
0x18006cc71  add     rsp, 98h
0x18006cc78  pop     rdi
0x18006cc79  pop     rsi
0x18006cc7a  pop     rbx
0x18006cc7b  pop     rbp
0x18006cc7c  retn
```
