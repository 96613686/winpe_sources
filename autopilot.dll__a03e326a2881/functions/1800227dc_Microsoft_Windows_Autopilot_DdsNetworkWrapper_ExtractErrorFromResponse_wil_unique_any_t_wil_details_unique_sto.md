# Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractErrorFromResponse(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,long &)

- ea: `0x1800227dc`
- end: `0x180022baf`
- name: `?ExtractErrorFromResponse@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAJ@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800250d8`

## callees

- `0x1800045b0`
- `0x18000ec40`
- `0x1800105f4`
- `0x1800132d8`
- `0x18001f0ec`
- `0x1800227dc`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002285f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800228ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800229dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002285f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800228ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800229dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022b0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022b0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002296e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800229b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002296e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800229b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800228e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800228e5`

## string_xrefs

- `0x1800228f8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractErrorFromResponse(
        __int64 a1,
        unsigned int *a2)
{
  int v3; // ebx
  _QWORD *v4; // rcx
  _QWORD *v6; // rbx
  __int64 v7; // rdi
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  _QWORD *v11; // rbx
  __int64 v12; // rdi
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  HRESULT v16; // eax
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  _QWORD *v21; // rbx
  __int64 v22; // rdi
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  _QWORD *v26; // rcx
  _QWORD *v27; // rcx
  _QWORD *v28; // rcx
  _QWORD *v29; // rcx
  _QWORD *v30; // rbx
  __int64 v31; // rdi
  HRESULT v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  _QWORD *v35; // rcx
  _QWORD *v36; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v38; // rcx
  _QWORD *v39; // rcx
  _QWORD *v40; // rcx
  _QWORD *v41; // [rsp+20h] [rbp-60h] BYREF
  _QWORD *v42; // [rsp+28h] [rbp-58h] BYREF
  HSTRING newString; // [rsp+30h] [rbp-50h] BYREF
  double v44; // [rsp+38h] [rbp-48h] BYREF
  HSTRING v45; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v46; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v41 = 0;
  v3 = Microsoft::Windows::Autopilot::JsonHelpers::FromString(a1, &v41);
  if ( v3 < 0 )
  {
    v4 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
    }
    return (unsigned int)v3;
  }
  v42 = 0;
  v6 = v41;
  v7 = *v41;
  string = 0;
  v8 = WindowsCreateStringReference(L"Message", 7u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    __debugbreak();
  }
  if ( (*(int (__fastcall **)(_QWORD *, HSTRING, _QWORD **))(v7 + 64))(v6, string, &v42) < 0 )
  {
    v45 = 0;
    v11 = v41;
    v12 = *v41;
    string = 0;
    v13 = WindowsCreateStringReference(L"Message", 7u, &hstringHeader, &string);
    if ( v13 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
      __debugbreak();
    }
    v3 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING *))(v12 + 80))(v11, string, &v45);
    if ( v3 < 0 )
    {
      v28 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
      }
      v29 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
      }
      return (unsigned int)v3;
    }
    newString = 0;
    v16 = WindowsDuplicateString(v45, &newString);
    v3 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x376,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v16,
        (int)v41);
      if ( newString )
        WindowsDeleteString(newString);
      v17 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
      }
      v18 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
      }
      return (unsigned int)v3;
    }
    v3 = Microsoft::Windows::Autopilot::JsonHelpers::FromString(&newString, &v42);
    if ( v3 < 0 )
    {
      if ( newString )
        WindowsDeleteString(newString);
      v19 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
      }
      v20 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
      }
      return (unsigned int)v3;
    }
    if ( newString )
      WindowsDeleteString(newString);
  }
  v46 = 0;
  v21 = v42;
  v22 = *v42;
  string = 0;
  v23 = WindowsCreateStringReference(L"ErrorMessage", 0xCu, &hstringHeader, &string);
  if ( v23 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
    JUMPOUT(0x180022BAELL);
  }
  v3 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING *))(v22 + 80))(v21, string, &v46);
  if ( v3 < 0 )
  {
    v26 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
    }
    v27 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
    }
    return (unsigned int)v3;
  }
  v44 = 0.0;
  v30 = v42;
  v31 = *v42;
  string = 0;
  v32 = WindowsCreateStringReference(L"ErrorCodeNumber", 0xFu, &hstringHeader, &string);
  if ( v32 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
    __debugbreak();
  }
  v3 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, double *))(v31 + 88))(v30, string, &v44);
  if ( v3 < 0 )
  {
    v35 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
    }
    v36 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
    }
    return (unsigned int)v3;
  }
  if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v46, 0);
    McTemplateU0dz_EventWriteTransfer(v38, AutopilotDownloadLogResponseError, (unsigned int)(int)v44, StringRawBuffer);
  }
  *a2 = (int)v44 | 0x81038000;
  v39 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v39 + 16LL))(v39);
  }
  v40 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
  }
  return 0;
}

```

## disassembly

```asm
0x1800227dc  mov     [rsp-18h+arg_10], rbx
0x1800227e1  mov     [rsp-18h+arg_18], rsi
0x1800227e6  push    rbp
0x1800227e7  push    rdi
0x1800227e8  push    r14
0x1800227ea  mov     rbp, rsp
0x1800227ed  sub     rsp, 80h
0x1800227f4  mov     rax, cs:__security_cookie
0x1800227fb  xor     rax, rsp
0x1800227fe  mov     [rbp+var_10], rax
0x180022802  mov     rsi, rdx
0x180022805  xor     r14d, r14d
0x180022808  mov     [rbp+var_60], r14
0x18002280c  lea     rdx, [rbp+var_60]
0x180022810  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180022815  mov     ebx, eax
0x180022817  test    eax, eax
0x180022819  jns     short loc_18002283C
0x18002281b  mov     rcx, [rbp+var_60]
0x18002281f  test    rcx, rcx
0x180022822  jz      short loc_180022835
0x180022824  mov     [rbp+var_60], r14
0x180022828  mov     rdx, [rcx]
0x18002282b  mov     rax, [rdx+10h]
0x18002282f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022834  nop
0x180022835  mov     eax, ebx
0x180022837  jmp     loc_180022B6B
0x18002283c  mov     [rbp+var_58], r14
0x180022840  mov     rbx, [rbp+var_60]
0x180022844  mov     rdi, [rbx]
0x180022847  mov     [rbp+string], r14
0x18002284b  lea     r9, [rbp+string]; string
0x18002284f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180022853  mov     edx, 7; length
0x180022858  lea     rcx, sourceString; "Message"
0x18002285f  call    cs:__imp_WindowsCreateStringReference
0x180022865  test    eax, eax
0x180022867  js      loc_180022B97
0x18002286d  lea     r8, [rbp+var_58]
0x180022871  mov     rdx, [rbp+string]
0x180022875  mov     rcx, rbx
0x180022878  mov     rax, [rdi+40h]
0x18002287c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022881  nop
0x180022882  test    eax, eax
0x180022884  jns     loc_1800229B9
0x18002288a  mov     [rbp+var_40], r14
0x18002288e  mov     rbx, [rbp+var_60]
0x180022892  mov     rdi, [rbx]
0x180022895  mov     [rbp+string], r14
0x180022899  lea     r9, [rbp+string]; string
0x18002289d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800228a1  mov     edx, 7; length
0x1800228a6  lea     rcx, sourceString; "Message"
0x1800228ad  call    cs:__imp_WindowsCreateStringReference
0x1800228b3  test    eax, eax
0x1800228b5  js      loc_180022B9F
0x1800228bb  lea     r8, [rbp+var_40]
0x1800228bf  mov     rdx, [rbp+string]
0x1800228c3  mov     rcx, rbx
0x1800228c6  mov     rax, [rdi+50h]
0x1800228ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228cf  mov     ebx, eax
0x1800228d1  test    eax, eax
0x1800228d3  js      loc_180022A3D
0x1800228d9  mov     [rbp+newString], r14
0x1800228dd  lea     rdx, [rbp+newString]; newString
0x1800228e1  mov     rcx, [rbp+var_40]; string
0x1800228e5  call    cs:__imp_WindowsDuplicateString
0x1800228eb  mov     ebx, eax
0x1800228ed  test    eax, eax
0x1800228ef  jns     short loc_180022952
0x1800228f1  mov     rcx, [rbp+18h]; this
0x1800228f5  mov     r9d, eax; char *
0x1800228f8  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800228ff  mov     edx, 376h; void *
0x180022904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022909  mov     rcx, [rbp+newString]; string
0x18002290d  test    rcx, rcx
0x180022910  jz      short loc_180022919
0x180022912  call    cs:__imp_WindowsDeleteString
0x180022918  nop
0x180022919  mov     rcx, [rbp+var_58]
0x18002291d  test    rcx, rcx
0x180022920  jz      short loc_180022933
0x180022922  mov     [rbp+var_58], r14
0x180022926  mov     rax, [rcx]
0x180022929  mov     rax, [rax+10h]
0x18002292d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022932  nop
0x180022933  mov     rcx, [rbp+var_60]
0x180022937  test    rcx, rcx
0x18002293a  jz      short loc_18002294D
0x18002293c  mov     [rbp+var_60], r14
0x180022940  mov     rax, [rcx]
0x180022943  mov     rax, [rax+10h]
0x180022947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002294c  nop
0x18002294d  jmp     loc_180022835
0x180022952  lea     rdx, [rbp+var_58]
0x180022956  lea     rcx, [rbp+newString]
0x18002295a  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18002295f  mov     ebx, eax
0x180022961  mov     rcx, [rbp+newString]; string
0x180022965  test    eax, eax
0x180022967  jns     short loc_1800229AE
0x180022969  test    rcx, rcx
0x18002296c  jz      short loc_180022975
0x18002296e  call    cs:__imp_WindowsDeleteString
0x180022974  nop
0x180022975  mov     rcx, [rbp+var_58]
0x180022979  test    rcx, rcx
0x18002297c  jz      short loc_18002298F
0x18002297e  mov     [rbp+var_58], r14
0x180022982  mov     rax, [rcx]
0x180022985  mov     rax, [rax+10h]
0x180022989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002298e  nop
0x18002298f  mov     rcx, [rbp+var_60]
0x180022993  test    rcx, rcx
0x180022996  jz      short loc_1800229A9
0x180022998  mov     [rbp+var_60], r14
0x18002299c  mov     rax, [rcx]
0x18002299f  mov     rax, [rax+10h]
0x1800229a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229a8  nop
0x1800229a9  jmp     loc_180022835
0x1800229ae  test    rcx, rcx
0x1800229b1  jz      short loc_1800229B9
0x1800229b3  call    cs:__imp_WindowsDeleteString
0x1800229b9  mov     [rbp+var_38], r14
0x1800229bd  mov     rbx, [rbp+var_58]
0x1800229c1  mov     rdi, [rbx]
0x1800229c4  mov     [rbp+string], r14
0x1800229c8  lea     r9, [rbp+string]; string
0x1800229cc  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800229d0  mov     edx, 0Ch; length
0x1800229d5  lea     rcx, aErrormessage; "ErrorMessage"
0x1800229dc  call    cs:__imp_WindowsCreateStringReference
0x1800229e2  test    eax, eax
0x1800229e4  js      loc_180022BA7
0x1800229ea  lea     r8, [rbp+var_38]
0x1800229ee  mov     rdx, [rbp+string]
0x1800229f2  mov     rcx, rbx
0x1800229f5  mov     rax, [rdi+50h]
0x1800229f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229fe  mov     ebx, eax
0x180022a00  test    eax, eax
0x180022a02  jns     short loc_180022A76
0x180022a04  mov     rcx, [rbp+var_58]
0x180022a08  test    rcx, rcx
0x180022a0b  jz      short loc_180022A1E
0x180022a0d  mov     [rbp+var_58], r14
0x180022a11  mov     rdx, [rcx]
0x180022a14  mov     rax, [rdx+10h]
0x180022a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a1d  nop
0x180022a1e  mov     rcx, [rbp+var_60]
0x180022a22  test    rcx, rcx
0x180022a25  jz      short loc_180022A38
0x180022a27  mov     [rbp+var_60], r14
0x180022a2b  mov     rax, [rcx]
0x180022a2e  mov     rax, [rax+10h]
0x180022a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a37  nop
0x180022a38  jmp     loc_180022835
0x180022a3d  mov     rcx, [rbp+var_58]
0x180022a41  test    rcx, rcx
0x180022a44  jz      short loc_180022A57
0x180022a46  mov     [rbp+var_58], r14
0x180022a4a  mov     rax, [rcx]
0x180022a4d  mov     rax, [rax+10h]
0x180022a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a56  nop
0x180022a57  mov     rcx, [rbp+var_60]
0x180022a5b  test    rcx, rcx
0x180022a5e  jz      short loc_180022A71
0x180022a60  mov     [rbp+var_60], r14
0x180022a64  mov     rax, [rcx]
0x180022a67  mov     rax, [rax+10h]
0x180022a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a70  nop
0x180022a71  jmp     loc_180022835
0x180022a76  xorps   xmm0, xmm0
0x180022a79  movsd   [rbp+var_48], xmm0
0x180022a7e  mov     rbx, [rbp+var_58]
0x180022a82  mov     rdi, [rbx]
0x180022a85  mov     [rbp+string], r14
0x180022a89  lea     r9, [rbp+string]; string
0x180022a8d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180022a91  mov     edx, 0Fh; length
0x180022a96  lea     rcx, aErrorcodenumbe; "ErrorCodeNumber"
0x180022a9d  call    cs:__imp_WindowsCreateStringReference
0x180022aa3  test    eax, eax
0x180022aa5  js      loc_180022B8F
0x180022aab  lea     r8, [rbp+var_48]
0x180022aaf  mov     rdx, [rbp+string]
0x180022ab3  mov     rcx, rbx
0x180022ab6  mov     rax, [rdi+58h]
0x180022aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022abf  mov     ebx, eax
0x180022ac1  test    eax, eax
0x180022ac3  jns     short loc_180022AFE
0x180022ac5  mov     rcx, [rbp+var_58]
0x180022ac9  test    rcx, rcx
0x180022acc  jz      short loc_180022ADF
0x180022ace  mov     [rbp+var_58], r14
0x180022ad2  mov     rdx, [rcx]
0x180022ad5  mov     rax, [rdx+10h]
0x180022ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ade  nop
0x180022adf  mov     rcx, [rbp+var_60]
0x180022ae3  test    rcx, rcx
0x180022ae6  jz      short loc_180022AF9
0x180022ae8  mov     [rbp+var_60], r14
0x180022aec  mov     rax, [rcx]
0x180022aef  mov     rax, [rax+10h]
0x180022af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022af8  nop
0x180022af9  jmp     loc_180022835
0x180022afe  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x180022b05  jz      short loc_180022B28
0x180022b07  xor     edx, edx; length
0x180022b09  mov     rcx, [rbp+var_38]; string
0x180022b0d  call    cs:__imp_WindowsGetStringRawBuffer
0x180022b13  cvttsd2si r8, [rbp+var_48]
0x180022b19  mov     r9, rax
0x180022b1c  lea     rdx, AutopilotDownloadLogResponseError
0x180022b23  call    McTemplateU0dz_EventWriteTransfer
0x180022b28  cvttsd2si rax, [rbp+var_48]
0x180022b2e  or      eax, 81038000h
0x180022b33  mov     [rsi], eax
0x180022b35  mov     rcx, [rbp+var_58]
0x180022b39  test    rcx, rcx
0x180022b3c  jz      short loc_180022B4F
0x180022b3e  mov     [rbp+var_58], r14
0x180022b42  mov     rax, [rcx]
0x180022b45  mov     rax, [rax+10h]
0x180022b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b4e  nop
0x180022b4f  mov     rcx, [rbp+var_60]
0x180022b53  test    rcx, rcx
0x180022b56  jz      short loc_180022B69
0x180022b58  mov     [rbp+var_60], r14
0x180022b5c  mov     rax, [rcx]
0x180022b5f  mov     rax, [rax+10h]
0x180022b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b68  nop
0x180022b69  xor     eax, eax
0x180022b6b  mov     rcx, [rbp+var_10]
0x180022b6f  xor     rcx, rsp; StackCookie
0x180022b72  call    __security_check_cookie
0x180022b77  lea     r11, [rsp+80h+var_s0]
0x180022b7f  mov     rbx, [r11+30h]
0x180022b83  mov     rsi, [r11+38h]
0x180022b87  mov     rsp, r11
0x180022b8a  pop     r14
0x180022b8c  pop     rdi
0x180022b8d  pop     rbp
0x180022b8e  retn
0x180022b8f  mov     ecx, eax; this
0x180022b91  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180022b96  int     3; Trap to Debugger
0x180022b97  mov     ecx, eax; this
0x180022b99  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180022b9e  int     3; Trap to Debugger
0x180022b9f  mov     ecx, eax; this
0x180022ba1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180022ba6  int     3; Trap to Debugger
0x180022ba7  mov     ecx, eax; this
0x180022ba9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
