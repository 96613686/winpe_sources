# Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractErrorFromResponse(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,long &)

- ea: `0x1800232dc`
- end: `0x1800236e6`
- name: `?ExtractErrorFromResponse@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAJ@Z`
- size: `1034`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025e74`

## callees

- `0x1800045d0`
- `0x18000ed44`
- `0x180010764`
- `0x180013580`
- `0x18001f98c`
- `0x1800232dc`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002335f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800233b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800235c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002335f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800233b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800235c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002363d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002363d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023424`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023486`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800234d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023424`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023486`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800234d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800233f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800233f1`

## string_xrefs

- `0x18002340a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
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
    JUMPOUT(0x1800236E5LL);
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
    McTemplateU0dz_EventWriteTransfer(
      v38,
      AutopilotDownloadLogResponseError,
      (unsigned int)(int)v44,
      StringRawBuffer,
      v41);
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
0x1800232dc  mov     [rsp-18h+arg_10], rbx
0x1800232e1  mov     [rsp-18h+arg_18], rsi
0x1800232e6  push    rbp
0x1800232e7  push    rdi
0x1800232e8  push    r14
0x1800232ea  mov     rbp, rsp
0x1800232ed  sub     rsp, 80h
0x1800232f4  mov     rax, cs:__security_cookie
0x1800232fb  xor     rax, rsp
0x1800232fe  mov     [rbp+var_10], rax
0x180023302  mov     rsi, rdx
0x180023305  xor     r14d, r14d
0x180023308  mov     [rbp+var_60], r14
0x18002330c  lea     rdx, [rbp+var_60]
0x180023310  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180023315  mov     ebx, eax
0x180023317  test    eax, eax
0x180023319  jns     short loc_18002333C
0x18002331b  mov     rcx, [rbp+var_60]
0x18002331f  test    rcx, rcx
0x180023322  jz      short loc_180023335
0x180023324  mov     [rbp+var_60], r14
0x180023328  mov     rdx, [rcx]
0x18002332b  mov     rax, [rdx+10h]
0x18002332f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023334  nop
0x180023335  mov     eax, ebx
0x180023337  jmp     loc_1800236A1
0x18002333c  mov     [rbp+var_58], r14
0x180023340  mov     rbx, [rbp+var_60]
0x180023344  mov     rdi, [rbx]
0x180023347  mov     [rbp+string], r14
0x18002334b  lea     r9, [rbp+string]; string
0x18002334f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180023353  mov     edx, 7; length
0x180023358  lea     rcx, sourceString; "Message"
0x18002335f  call    cs:__imp_WindowsCreateStringReference
0x180023366  nop     dword ptr [rax+rax+00h]
0x18002336b  test    eax, eax
0x18002336d  js      loc_1800236CE
0x180023373  lea     r8, [rbp+var_58]
0x180023377  mov     rdx, [rbp+string]
0x18002337b  mov     rcx, rbx
0x18002337e  mov     rax, [rdi+40h]
0x180023382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023387  nop
0x180023388  test    eax, eax
0x18002338a  jns     loc_1800234DD
0x180023390  mov     [rbp+var_40], r14
0x180023394  mov     rbx, [rbp+var_60]
0x180023398  mov     rdi, [rbx]
0x18002339b  mov     [rbp+string], r14
0x18002339f  lea     r9, [rbp+string]; string
0x1800233a3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800233a7  mov     edx, 7; length
0x1800233ac  lea     rcx, sourceString; "Message"
0x1800233b3  call    cs:__imp_WindowsCreateStringReference
0x1800233ba  nop     dword ptr [rax+rax+00h]
0x1800233bf  test    eax, eax
0x1800233c1  js      loc_1800236D6
0x1800233c7  lea     r8, [rbp+var_40]
0x1800233cb  mov     rdx, [rbp+string]
0x1800233cf  mov     rcx, rbx
0x1800233d2  mov     rax, [rdi+50h]
0x1800233d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233db  mov     ebx, eax
0x1800233dd  test    eax, eax
0x1800233df  js      loc_180023567
0x1800233e5  mov     [rbp+newString], r14
0x1800233e9  lea     rdx, [rbp+newString]; newString
0x1800233ed  mov     rcx, [rbp+var_40]; string
0x1800233f1  call    cs:__imp_WindowsDuplicateString
0x1800233f8  nop     dword ptr [rax+rax+00h]
0x1800233fd  mov     ebx, eax
0x1800233ff  test    eax, eax
0x180023401  jns     short loc_18002346A
0x180023403  mov     rcx, [rbp+18h]; this
0x180023407  mov     r9d, eax; char *
0x18002340a  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180023411  mov     edx, 376h; void *
0x180023416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002341b  mov     rcx, [rbp+newString]; string
0x18002341f  test    rcx, rcx
0x180023422  jz      short loc_180023431
0x180023424  call    cs:__imp_WindowsDeleteString
0x18002342b  nop     dword ptr [rax+rax+00h]
0x180023430  nop
0x180023431  mov     rcx, [rbp+var_58]
0x180023435  test    rcx, rcx
0x180023438  jz      short loc_18002344B
0x18002343a  mov     [rbp+var_58], r14
0x18002343e  mov     rax, [rcx]
0x180023441  mov     rax, [rax+10h]
0x180023445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002344a  nop
0x18002344b  mov     rcx, [rbp+var_60]
0x18002344f  test    rcx, rcx
0x180023452  jz      short loc_180023465
0x180023454  mov     [rbp+var_60], r14
0x180023458  mov     rax, [rcx]
0x18002345b  mov     rax, [rax+10h]
0x18002345f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023464  nop
0x180023465  jmp     loc_180023335
0x18002346a  lea     rdx, [rbp+var_58]
0x18002346e  lea     rcx, [rbp+newString]
0x180023472  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180023477  mov     ebx, eax
0x180023479  mov     rcx, [rbp+newString]; string
0x18002347d  test    eax, eax
0x18002347f  jns     short loc_1800234CC
0x180023481  test    rcx, rcx
0x180023484  jz      short loc_180023493
0x180023486  call    cs:__imp_WindowsDeleteString
0x18002348d  nop     dword ptr [rax+rax+00h]
0x180023492  nop
0x180023493  mov     rcx, [rbp+var_58]
0x180023497  test    rcx, rcx
0x18002349a  jz      short loc_1800234AD
0x18002349c  mov     [rbp+var_58], r14
0x1800234a0  mov     rax, [rcx]
0x1800234a3  mov     rax, [rax+10h]
0x1800234a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234ac  nop
0x1800234ad  mov     rcx, [rbp+var_60]
0x1800234b1  test    rcx, rcx
0x1800234b4  jz      short loc_1800234C7
0x1800234b6  mov     [rbp+var_60], r14
0x1800234ba  mov     rax, [rcx]
0x1800234bd  mov     rax, [rax+10h]
0x1800234c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234c6  nop
0x1800234c7  jmp     loc_180023335
0x1800234cc  test    rcx, rcx
0x1800234cf  jz      short loc_1800234DD
0x1800234d1  call    cs:__imp_WindowsDeleteString
0x1800234d8  nop     dword ptr [rax+rax+00h]
0x1800234dd  mov     [rbp+var_38], r14
0x1800234e1  mov     rbx, [rbp+var_58]
0x1800234e5  mov     rdi, [rbx]
0x1800234e8  mov     [rbp+string], r14
0x1800234ec  lea     r9, [rbp+string]; string
0x1800234f0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800234f4  mov     edx, 0Ch; length
0x1800234f9  lea     rcx, aErrormessage; "ErrorMessage"
0x180023500  call    cs:__imp_WindowsCreateStringReference
0x180023507  nop     dword ptr [rax+rax+00h]
0x18002350c  test    eax, eax
0x18002350e  js      loc_1800236DE
0x180023514  lea     r8, [rbp+var_38]
0x180023518  mov     rdx, [rbp+string]
0x18002351c  mov     rcx, rbx
0x18002351f  mov     rax, [rdi+50h]
0x180023523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023528  mov     ebx, eax
0x18002352a  test    eax, eax
0x18002352c  jns     short loc_1800235A0
0x18002352e  mov     rcx, [rbp+var_58]
0x180023532  test    rcx, rcx
0x180023535  jz      short loc_180023548
0x180023537  mov     [rbp+var_58], r14
0x18002353b  mov     rdx, [rcx]
0x18002353e  mov     rax, [rdx+10h]
0x180023542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023547  nop
0x180023548  mov     rcx, [rbp+var_60]
0x18002354c  test    rcx, rcx
0x18002354f  jz      short loc_180023562
0x180023551  mov     [rbp+var_60], r14
0x180023555  mov     rax, [rcx]
0x180023558  mov     rax, [rax+10h]
0x18002355c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023561  nop
0x180023562  jmp     loc_180023335
0x180023567  mov     rcx, [rbp+var_58]
0x18002356b  test    rcx, rcx
0x18002356e  jz      short loc_180023581
0x180023570  mov     [rbp+var_58], r14
0x180023574  mov     rax, [rcx]
0x180023577  mov     rax, [rax+10h]
0x18002357b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023580  nop
0x180023581  mov     rcx, [rbp+var_60]
0x180023585  test    rcx, rcx
0x180023588  jz      short loc_18002359B
0x18002358a  mov     [rbp+var_60], r14
0x18002358e  mov     rax, [rcx]
0x180023591  mov     rax, [rax+10h]
0x180023595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002359a  nop
0x18002359b  jmp     loc_180023335
0x1800235a0  xorps   xmm0, xmm0
0x1800235a3  movsd   [rbp+var_48], xmm0
0x1800235a8  mov     rbx, [rbp+var_58]
0x1800235ac  mov     rdi, [rbx]
0x1800235af  mov     [rbp+string], r14
0x1800235b3  lea     r9, [rbp+string]; string
0x1800235b7  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800235bb  mov     edx, 0Fh; length
0x1800235c0  lea     rcx, aErrorcodenumbe; "ErrorCodeNumber"
0x1800235c7  call    cs:__imp_WindowsCreateStringReference
0x1800235ce  nop     dword ptr [rax+rax+00h]
0x1800235d3  test    eax, eax
0x1800235d5  js      loc_1800236C6
0x1800235db  lea     r8, [rbp+var_48]
0x1800235df  mov     rdx, [rbp+string]
0x1800235e3  mov     rcx, rbx
0x1800235e6  mov     rax, [rdi+58h]
0x1800235ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235ef  mov     ebx, eax
0x1800235f1  test    eax, eax
0x1800235f3  jns     short loc_18002362E
0x1800235f5  mov     rcx, [rbp+var_58]
0x1800235f9  test    rcx, rcx
0x1800235fc  jz      short loc_18002360F
0x1800235fe  mov     [rbp+var_58], r14
0x180023602  mov     rdx, [rcx]
0x180023605  mov     rax, [rdx+10h]
0x180023609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002360e  nop
0x18002360f  mov     rcx, [rbp+var_60]
0x180023613  test    rcx, rcx
0x180023616  jz      short loc_180023629
0x180023618  mov     [rbp+var_60], r14
0x18002361c  mov     rax, [rcx]
0x18002361f  mov     rax, [rax+10h]
0x180023623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023628  nop
0x180023629  jmp     loc_180023335
0x18002362e  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x180023635  jz      short loc_18002365E
0x180023637  xor     edx, edx; length
0x180023639  mov     rcx, [rbp+var_38]; string
0x18002363d  call    cs:__imp_WindowsGetStringRawBuffer
0x180023644  nop     dword ptr [rax+rax+00h]
0x180023649  cvttsd2si r8, [rbp+var_48]
0x18002364f  mov     r9, rax
0x180023652  lea     rdx, AutopilotDownloadLogResponseError
0x180023659  call    McTemplateU0dz_EventWriteTransfer
0x18002365e  cvttsd2si rax, [rbp+var_48]
0x180023664  or      eax, 81038000h
0x180023669  mov     [rsi], eax
0x18002366b  mov     rcx, [rbp+var_58]
0x18002366f  test    rcx, rcx
0x180023672  jz      short loc_180023685
0x180023674  mov     [rbp+var_58], r14
0x180023678  mov     rax, [rcx]
0x18002367b  mov     rax, [rax+10h]
0x18002367f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023684  nop
0x180023685  mov     rcx, [rbp+var_60]
0x180023689  test    rcx, rcx
0x18002368c  jz      short loc_18002369F
0x18002368e  mov     [rbp+var_60], r14
0x180023692  mov     rax, [rcx]
0x180023695  mov     rax, [rax+10h]
0x180023699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002369e  nop
0x18002369f  xor     eax, eax
0x1800236a1  mov     rcx, [rbp+var_10]
0x1800236a5  xor     rcx, rsp; StackCookie
0x1800236a8  call    __security_check_cookie
0x1800236ad  lea     r11, [rsp+80h+var_s0]
0x1800236b5  mov     rbx, [r11+30h]
0x1800236b9  mov     rsi, [r11+38h]
0x1800236bd  mov     rsp, r11
0x1800236c0  pop     r14
0x1800236c2  pop     rdi
0x1800236c3  pop     rbp
0x1800236c4  retn
0x1800236c6  mov     ecx, eax; this
0x1800236c8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800236cd  int     3; Trap to Debugger
0x1800236ce  mov     ecx, eax; this
0x1800236d0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800236d5  int     3; Trap to Debugger
0x1800236d6  mov     ecx, eax; this
0x1800236d8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800236dd  int     3; Trap to Debugger
0x1800236de  mov     ecx, eax; this
0x1800236e0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
