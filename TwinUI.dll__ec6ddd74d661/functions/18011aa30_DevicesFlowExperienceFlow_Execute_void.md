# DevicesFlowExperienceFlow::Execute(void)

- ea: `0x18011aa30`
- end: `0x18011ae36`
- name: `?Execute@DevicesFlowExperienceFlow@@UEAAJXZ`
- size: `1030`
- prototype: `__int64 __fastcall(DevicesFlowExperienceFlow *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009dd0`
- `0x18000aa70`
- `0x18000b370`
- `0x18000e498`
- `0x18001c710`
- `0x1800378dc`
- `0x180037b9c`
- `0x180053740`
- `0x180055268`
- `0x18011aa30`
- `0x180142e10`
- `0x1802b93c4`
- `0x1802e1d08`
- `0x1802e1ef8`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011acb1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011acf1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011acb1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011acf1`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18011ad58`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18011ad58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ac35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ac76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011adaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ac35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ac76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011adaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011ac8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011acd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011ac8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011acd1`

## string_xrefs

- `0x18011ab72`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall DevicesFlowExperienceFlow::Execute(DevicesFlowExperienceFlow *this)
{
  _QWORD *v2; // r14
  int v3; // edi
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(__int64, _QWORD, wchar_t **); // rbx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, wchar_t **); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v21; // rbx
  const WCHAR *v22; // rax
  DevicesFlowExperienceFlow *v23; // rcx
  int ExperienceManager; // eax
  __int64 v25; // rdx
  HRESULT v26; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-49h]
  HSTRING string; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-31h] BYREF
  __int64 v31; // [rsp+40h] [rbp-29h] BYREF
  __int64 v32; // [rsp+48h] [rbp-21h] BYREF
  IUnknown *pUnk; // [rsp+50h] [rbp-19h] BYREF
  wchar_t *v34; // [rsp+58h] [rbp-11h] BYREF
  __int64 v35; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  __int64 v37; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v35 = 0;
  v2 = (_QWORD *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(&v35);
  v3 = -2147024809;
  *v2 = 0;
  v4 = *((_QWORD *)this + 15);
  if ( !v4 )
    goto LABEL_33;
  v34 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)v4 + 64LL);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v34);
  v3 = v5(v4, 0, &v34);
  if ( v3 >= 0 )
    v3 = Microsoft::WRL::ComPtr<IShellItem>::CopyTo(&v34, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, v2);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v34);
  if ( v3 < 0 )
  {
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
    v9 = v3;
    goto LABEL_34;
  }
  v6 = v35;
  String1 = 0;
  v7 = *(__int64 (__fastcall **)(__int64, __int64, wchar_t **))(*(_QWORD *)v35 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &String1,
    0);
  v8 = v7(v6, 2147909632LL, &String1);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v34 = String1;
    if ( !IsMsDevicesFlowUri(String1) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
        (const char *)0x80070057LL,
        bIgnoreCase);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String1);
      v9 = -2147024809;
      goto LABEL_34;
    }
    v32 = 0;
    v37 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
            v37,
            &v32);
    v9 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
        (const char *)(unsigned int)v10,
        bIgnoreCase);
LABEL_12:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
      goto LABEL_7;
    }
    v11 = v32;
    v31 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 48LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
    v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v34);
    v14 = v12(v11, *(_QWORD *)(v13 + 24), &v31);
    v9 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
        (const char *)(unsigned int)v14,
        bIgnoreCase);
LABEL_15:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
      goto LABEL_12;
    }
    v15 = v31;
    string = 0;
    v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 104LL);
    WindowsDeleteString(0);
    string = 0;
    v17 = v16(v15, &string);
    v9 = v17;
    if ( v17 < 0 )
    {
      v18 = (unsigned int)v17;
      v19 = 37;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
        (const char *)v18,
        bIgnoreCase);
LABEL_19:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_15;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"devicediscovery", -1, 0) == 2 )
    {
      v21 = L"Windows.Internal.ShellExperience.DeviceDiscovery";
    }
    else
    {
      v22 = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(v22, -1, L"projection", -1, 0) != 2 )
      {
        v9 = -2147418113;
        v19 = 50;
        v18 = 2147549183LL;
        goto LABEL_18;
      }
      v21 = L"Windows.Internal.ShellExperience.DisplayTopology";
    }
    pUnk = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pUnk);
    ExperienceManager = DevicesFlowExperienceFlow::GetExperienceManager(
                          v23,
                          v21,
                          (struct Windows::Internal::Shell::Experience::IDeviceDiscoveryExperienceManager **)&pUnk);
    v9 = ExperienceManager;
    if ( ExperienceManager >= 0 )
    {
      v26 = CoAllowSetForegroundWindow(pUnk, 0);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
          (const char *)(unsigned int)v26,
          bIgnoreCase);
      ExperienceManager = ((__int64 (__fastcall *)(IUnknown *))pUnk->lpVtbl[2].QueryInterface)(pUnk);
      v9 = ExperienceManager;
      if ( ExperienceManager >= 0 )
      {
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pUnk);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String1);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v35);
        return 0;
      }
      v25 = 56;
    }
    else
    {
      v25 = 54;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
      (const char *)(unsigned int)ExperienceManager,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pUnk);
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A,
    (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
    (const char *)(unsigned int)v8,
    bIgnoreCase);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String1);
LABEL_34:
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v35);
  return v9;
}

```

## disassembly

```asm
0x18011aa30  push    rbp
0x18011aa32  push    rbx
0x18011aa33  push    rsi
0x18011aa34  push    rdi
0x18011aa35  push    r14
0x18011aa37  push    r15
0x18011aa39  lea     rbp, [rsp-2Fh]
0x18011aa3e  sub     rsp, 98h
0x18011aa45  mov     rax, cs:__security_cookie
0x18011aa4c  xor     rax, rsp
0x18011aa4f  mov     [rbp+57h+var_38], rax
0x18011aa53  mov     rbx, rcx
0x18011aa56  xor     r15d, r15d
0x18011aa59  lea     rcx, [rbp+57h+var_60]
0x18011aa5d  mov     [rbp+57h+var_60], r15
0x18011aa61  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x18011aa66  mov     r14, rax
0x18011aa69  mov     edi, 80070057h
0x18011aa6e  mov     [rax], r15
0x18011aa71  mov     rsi, [rbx+78h]
0x18011aa75  test    rsi, rsi
0x18011aa78  jz      loc_18011ADF4
0x18011aa7e  mov     [rbp+57h+var_68], r15
0x18011aa82  lea     rcx, [rbp+57h+var_68]
0x18011aa86  mov     rdx, [rsi]
0x18011aa89  mov     rbx, [rdx+40h]
0x18011aa8d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011aa92  lea     r8, [rbp+57h+var_68]
0x18011aa96  xor     edx, edx
0x18011aa98  mov     rcx, rsi
0x18011aa9b  mov     rax, rbx
0x18011aa9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011aaa3  mov     edi, eax
0x18011aaa5  test    eax, eax
0x18011aaa7  js      short loc_18011AABE
0x18011aaa9  mov     r8, r14
0x18011aaac  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x18011aab3  lea     rcx, [rbp+57h+var_68]
0x18011aab7  call    ?CopyTo@?$ComPtr@UIShellItem@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<IShellItem>::CopyTo(_GUID const &,void * *)
0x18011aabc  mov     edi, eax
0x18011aabe  lea     rcx, [rbp+57h+var_68]
0x18011aac2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011aac7  test    edi, edi
0x18011aac9  js      loc_18011ADF4
0x18011aacf  mov     rdi, [rbp+57h+var_60]
0x18011aad3  lea     rcx, [rbp+57h+String1]
0x18011aad7  mov     [rbp+57h+String1], r15
0x18011aadb  xor     edx, edx
0x18011aadd  mov     rax, [rdi]
0x18011aae0  mov     rbx, [rax+28h]
0x18011aae4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18011aae9  lea     r8, [rbp+57h+String1]
0x18011aaed  mov     edx, 80068000h
0x18011aaf2  mov     rcx, rdi
0x18011aaf5  mov     rax, rbx
0x18011aaf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011aafd  mov     ebx, eax
0x18011aaff  test    eax, eax
0x18011ab01  jns     short loc_18011AB29
0x18011ab03  mov     rcx, [rbp+5Fh]; this
0x18011ab07  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x18011ab0e  mov     r9d, eax; char *
0x18011ab11  mov     edx, 1Ah; void *
0x18011ab16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ab1b  lea     rcx, [rbp+57h+String1]
0x18011ab1f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18011ab24  jmp     loc_18011AE0E
0x18011ab29  mov     rcx, [rbp+57h+String1]; String1
0x18011ab2d  mov     [rbp+57h+var_68], rcx
0x18011ab31  call    ?IsMsDevicesFlowUri@@YA_NPEBG@Z; IsMsDevicesFlowUri(ushort const *)
0x18011ab36  test    al, al
0x18011ab38  jnz     short loc_18011AB68
0x18011ab3a  mov     rcx, [rbp+5Fh]; this
0x18011ab3e  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x18011ab45  mov     r9d, 80070057h; char *
0x18011ab4b  mov     edx, 1Ch; void *
0x18011ab50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ab55  lea     rcx, [rbp+57h+String1]
0x18011ab59  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18011ab5e  mov     ebx, 80070057h
0x18011ab63  jmp     loc_18011AE0E
0x18011ab68  mov     r9d, 16h; unsigned int
0x18011ab6e  mov     [rbp+57h+var_78], r15
0x18011ab72  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18011ab79  mov     [rbp+57h+var_40], r15
0x18011ab7d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18011ab81  lea     r8d, [r9+1]; unsigned int
0x18011ab85  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18011ab8a  mov     rcx, [rbp+57h+var_40]
0x18011ab8e  lea     rdx, [rbp+57h+var_78]
0x18011ab92  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18011ab97  mov     ebx, eax
0x18011ab99  test    eax, eax
0x18011ab9b  jns     short loc_18011ABC3
0x18011ab9d  mov     rcx, [rbp+5Fh]; this
0x18011aba1  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x18011aba8  mov     r9d, eax; char *
0x18011abab  mov     edx, 1Fh; void *
0x18011abb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011abb5  lea     rcx, [rbp+57h+var_78]
0x18011abb9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011abbe  jmp     loc_18011AB1B
0x18011abc3  mov     rdi, [rbp+57h+var_78]
0x18011abc7  lea     rcx, [rbp+57h+var_80]
0x18011abcb  mov     [rbp+57h+var_80], r15
0x18011abcf  mov     rax, [rdi]
0x18011abd2  mov     rbx, [rax+30h]
0x18011abd6  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011abdb  lea     rdx, [rbp+57h+var_68]
0x18011abdf  lea     rcx, [rbp+57h+hstringHeader]
0x18011abe3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18011abe8  lea     r8, [rbp+57h+var_80]
0x18011abec  mov     rcx, rdi
0x18011abef  mov     rdx, [rax+18h]
0x18011abf3  mov     rax, rbx
0x18011abf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011abfb  mov     ebx, eax
0x18011abfd  test    eax, eax
0x18011abff  jns     short loc_18011AC24
0x18011ac01  mov     rcx, [rbp+5Fh]; this
0x18011ac05  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x18011ac0c  mov     r9d, eax; char *
0x18011ac0f  mov     edx, 22h ; '"'; void *
0x18011ac14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ac19  lea     rcx, [rbp+57h+var_80]
0x18011ac1d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011ac22  jmp     short loc_18011ABB5
0x18011ac24  mov     rdi, [rbp+57h+var_80]
0x18011ac28  xor     ecx, ecx; string
0x18011ac2a  mov     [rbp+57h+string], r15
0x18011ac2e  mov     rax, [rdi]
0x18011ac31  mov     rbx, [rax+68h]
0x18011ac35  call    cs:__imp_WindowsDeleteString
0x18011ac3c  nop     dword ptr [rax+rax+00h]
0x18011ac41  lea     rdx, [rbp+57h+string]
0x18011ac45  mov     [rbp+57h+string], r15
0x18011ac49  mov     rcx, rdi
0x18011ac4c  mov     rax, rbx
0x18011ac4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011ac54  mov     ebx, eax
0x18011ac56  test    eax, eax
0x18011ac58  jns     short loc_18011AC88
0x18011ac5a  mov     r9d, eax; char *
0x18011ac5d  mov     edx, 25h ; '%'; void *
0x18011ac62  mov     rcx, [rbp+5Fh]; this
0x18011ac66  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x18011ac6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ac72  mov     rcx, [rbp+57h+string]; string
0x18011ac76  call    cs:__imp_WindowsDeleteString
0x18011ac7d  nop     dword ptr [rax+rax+00h]
0x18011ac82  mov     [rbp+57h+string], r15
0x18011ac86  jmp     short loc_18011AC19
0x18011ac88  mov     rcx, [rbp+57h+string]; string
0x18011ac8c  xor     edx, edx; length
0x18011ac8e  call    cs:__imp_WindowsGetStringRawBuffer
0x18011ac95  nop     dword ptr [rax+rax+00h]
0x18011ac9a  or      ebx, 0FFFFFFFFh
0x18011ac9d  mov     [rsp+0C0h+bIgnoreCase], r15d; bIgnoreCase
0x18011aca2  mov     r9d, ebx; cchCount2
0x18011aca5  lea     r8, aDevicediscover; "devicediscovery"
0x18011acac  mov     edx, ebx; cchCount1
0x18011acae  mov     rcx, rax; lpString1
0x18011acb1  call    cs:__imp_CompareStringOrdinal
0x18011acb8  nop     dword ptr [rax+rax+00h]
0x18011acbd  cmp     eax, 2
0x18011acc0  jnz     short loc_18011ACCB
0x18011acc2  lea     rbx, aWindowsInterna_3; "Windows.Internal.ShellExperience.Device"...
0x18011acc9  jmp     short loc_18011AD0D
0x18011accb  mov     rcx, [rbp+57h+string]; string
0x18011accf  xor     edx, edx; length
0x18011acd1  call    cs:__imp_WindowsGetStringRawBuffer
0x18011acd8  nop     dword ptr [rax+rax+00h]
0x18011acdd  mov     r9d, ebx; cchCount2
0x18011ace0  mov     [rsp+0C0h+bIgnoreCase], r15d; int
0x18011ace5  mov     rcx, rax; lpString1
0x18011ace8  lea     r8, aProjection; "projection"
0x18011acef  mov     edx, ebx; cchCount1
0x18011acf1  call    cs:__imp_CompareStringOrdinal
0x18011acf8  nop     dword ptr [rax+rax+00h]
0x18011acfd  cmp     eax, 2
0x18011ad00  jnz     loc_18011ADE2
0x18011ad06  lea     rbx, aWindowsInterna_38; "Windows.Internal.ShellExperience.Displa"...
0x18011ad0d  lea     rcx, [rbp+57h+pUnk]
0x18011ad11  mov     [rbp+57h+pUnk], r15
0x18011ad15  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011ad1a  lea     r8, [rbp+57h+pUnk]; struct Windows::Internal::Shell::Experience::IDeviceDiscoveryExperienceManager **
0x18011ad1e  mov     rdx, rbx; unsigned __int16 *
0x18011ad21  call    ?GetExperienceManager@DevicesFlowExperienceFlow@@AEAAJPEBGPEAPEAUIDeviceDiscoveryExperienceManager@Experience@Shell@Internal@Windows@@@Z; DevicesFlowExperienceFlow::GetExperienceManager(ushort const *,Windows::Internal::Shell::Experience::IDeviceDiscoveryExperienceManager * *)
0x18011ad26  mov     ebx, eax
0x18011ad28  test    eax, eax
0x18011ad2a  jns     short loc_18011AD52
0x18011ad2c  mov     edx, 36h ; '6'; void *
0x18011ad31  mov     rcx, [rbp+5Fh]; this
0x18011ad35  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x18011ad3c  mov     r9d, eax; char *
0x18011ad3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ad44  lea     rcx, [rbp+57h+pUnk]
0x18011ad48  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011ad4d  jmp     loc_18011AC72
0x18011ad52  mov     rcx, [rbp+57h+pUnk]; pUnk
0x18011ad56  xor     edx, edx; lpvReserved
0x18011ad58  call    cs:__imp_CoAllowSetForegroundWindow
0x18011ad5f  nop     dword ptr [rax+rax+00h]
0x18011ad64  test    eax, eax
0x18011ad66  jns     short loc_18011AD80
0x18011ad68  mov     rcx, [rbp+5Fh]; this
0x18011ad6c  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x18011ad73  mov     r9d, eax; char *
0x18011ad76  mov     edx, 37h ; '7'; void *
0x18011ad7b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18011ad80  mov     rcx, [rbp+57h+pUnk]
0x18011ad84  mov     rax, [rcx]
0x18011ad87  mov     rax, [rax+30h]
0x18011ad8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011ad90  mov     ebx, eax
0x18011ad92  test    eax, eax
0x18011ad94  jns     short loc_18011AD9D
0x18011ad96  mov     edx, 38h ; '8'
0x18011ad9b  jmp     short loc_18011AD31
0x18011ad9d  lea     rcx, [rbp+57h+pUnk]
0x18011ada1  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011ada6  mov     rcx, [rbp+57h+string]; string
0x18011adaa  call    cs:__imp_WindowsDeleteString
0x18011adb1  nop     dword ptr [rax+rax+00h]
0x18011adb6  lea     rcx, [rbp+57h+var_80]
0x18011adba  mov     [rbp+57h+string], r15
0x18011adbe  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011adc3  lea     rcx, [rbp+57h+var_78]
0x18011adc7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011adcc  lea     rcx, [rbp+57h+String1]
0x18011add0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18011add5  lea     rcx, [rbp+57h+var_60]
0x18011add9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011adde  xor     eax, eax
0x18011ade0  jmp     short loc_18011AE19
0x18011ade2  mov     ebx, 8000FFFFh
0x18011ade7  mov     edx, 32h ; '2'
0x18011adec  mov     r9d, ebx
0x18011adef  jmp     loc_18011AC62
0x18011adf4  mov     rcx, [rbp+5Fh]; this
0x18011adf8  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x18011adff  mov     r9d, edi; char *
0x18011ae02  mov     edx, 17h; void *
0x18011ae07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011ae0c  mov     ebx, edi
0x18011ae0e  lea     rcx, [rbp+57h+var_60]
0x18011ae12  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011ae17  mov     eax, ebx
0x18011ae19  mov     rcx, [rbp+57h+var_38]
0x18011ae1d  xor     rcx, rsp; StackCookie
0x18011ae20  call    __security_check_cookie
0x18011ae25  add     rsp, 98h
0x18011ae2c  pop     r15
0x18011ae2e  pop     r14
0x18011ae30  pop     rdi
0x18011ae31  pop     rsi
0x18011ae32  pop     rbx
0x18011ae33  pop     rbp
0x18011ae34  retn
```
