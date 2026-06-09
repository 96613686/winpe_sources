# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::PollForExpectedPoliciesAndResources(EnterpriseDeviceManagement::Enrollment::ResourceToTrack,int,EnterpriseDeviceManagement::Enrollment::MDMProgressMode,Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress> * *)

- ea: `0x1800316d0`
- end: `0x1800319a8`
- name: `?PollForExpectedPoliciesAndResources@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJW4ResourceToTrack@23@HW4MDMProgressMode@23@PEAPEAU?$IAsyncOperationWithProgress@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@Z`
- size: `728`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004d50`
- `0x18000992c`
- `0x18000a2a4`
- `0x180016b54`
- `0x180017074`
- `0x18001736c`
- `0x1800173ec`
- `0x180018ff0`
- `0x180019b2c`
- `0x180019f1c`
- `0x18001b1c8`
- `0x18001dd64`
- `0x18001e414`
- `0x18001ef14`
- `0x180022830`
- `0x180024b60`
- `0x18002e79c`
- `0x1800316d0`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180031723`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180031723`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031848`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031848`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800317ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800317ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800317d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800317ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800317d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800317ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031767`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031767`

## string_xrefs

- `0x180031829`: `EnterpriseDeviceManagement.Service.AutoPilot.EnrollmentStatusTrackingUtil`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::PollForExpectedPoliciesAndResources(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5)
{
  int v7; // r9d
  int ActiveUserSid; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rax
  HRESULT v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  int AgileReferenceForType; // eax
  __int64 v15; // rax
  __int64 v16; // r8
  int v18; // [rsp+20h] [rbp-A1h]
  HSTRING string; // [rsp+40h] [rbp-81h] BYREF
  __int64 v20; // [rsp+48h] [rbp-79h] BYREF
  __int64 v21; // [rsp+50h] [rbp-71h] BYREF
  _BYTE v22[12]; // [rsp+58h] [rbp-69h] BYREF
  int v23; // [rsp+68h] [rbp-59h] BYREF
  int v24; // [rsp+70h] [rbp-51h] BYREF
  int v25; // [rsp+78h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-41h] BYREF
  __int128 newString; // [rsp+88h] [rbp-39h] BYREF
  _BYTE v28[48]; // [rsp+98h] [rbp-29h] BYREF
  HSTRING v29; // [rsp+C8h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v24 = a2;
  v23 = a3;
  v25 = a4;
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(&newString);
  if ( v7 )
  {
    hMem = 0;
    ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
    v9 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x443,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        v18);
      goto LABEL_25;
    }
    string = 0;
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, &hMem);
    LocalFree(hMem);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      &newString,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(&newString) )
    {
      v10 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v22);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        &newString,
        v10);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v22);
    }
    v11 = WindowsDuplicateString(string, (HSTRING *)newString);
    v9 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x447,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v11,
        v18);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_25;
    }
    WindowsDeleteString(string);
  }
  else
  {
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      &newString,
      0);
  }
  *(_QWORD *)v22 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(v22);
  v12 = 0;
  v20 = 0;
  if ( a2 == 2 )
  {
    if ( WindowsCreateStringReference(
           L"EnterpriseDeviceManagement.Service.AutoPilot.EnrollmentStatusTrackingUtil",
           0x49u,
           &hstringHeader,
           &v29) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v13 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<EnterpriseDeviceManagement::Service::AutoPilot::IEnrollmentStatusTrackingUtil>>(
            (__int64)v29,
            &v20);
    v9 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x453,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v13,
        v18);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
      goto LABEL_25;
    }
    v12 = v20;
  }
  v21 = 0;
  if ( v12
    && (AgileReferenceForType = AgileObjectConvertT<EnterpriseDeviceManagement::Service::AutoPilot::IEnrollmentStatusTrackingUtil>::GetAgileReferenceForType(
                                  v12,
                                  &v21),
        v9 = AgileReferenceForType,
        AgileReferenceForType < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x459,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)(unsigned int)AgileReferenceForType,
      v18);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
  else
  {
    v15 = lambda_6e73326332f4df0235e1c9bdb5daeaef_::_lambda_6e73326332f4df0235e1c9bdb5daeaef_(
            (unsigned int)v28,
            (unsigned int)v22,
            (unsigned int)&newString,
            (unsigned int)&v21,
            (__int64)&v25,
            (__int64)&v24,
            (__int64)&v23);
    *(_DWORD *)v22 = 3;
    *(_QWORD *)&v22[4] = 128;
    v9 = Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_EnterpriseDeviceManagement::Enrollment::IExpectedAndCurrentResourceAmount__EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress__EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount___EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress_Windows::Internal::ComTaskPoolHandler__lambda_6e73326332f4df0235e1c9bdb5daeaef___(
           v22,
           a5,
           v16,
           v15);
    lambda_6e73326332f4df0235e1c9bdb5daeaef_::__lambda_6e73326332f4df0235e1c9bdb5daeaef_(v28);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
LABEL_25:
  std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(&newString);
  return v9;
}

```

## disassembly

```asm
0x1800316d0  push    rbp
0x1800316d2  push    rbx
0x1800316d3  push    rsi
0x1800316d4  push    rdi
0x1800316d5  push    r14
0x1800316d7  lea     rbp, [rsp-2Fh]
0x1800316dc  sub     rsp, 0F0h
0x1800316e3  mov     rax, cs:__security_cookie
0x1800316ea  xor     rax, rsp
0x1800316ed  mov     [rbp+4Fh+var_28], rax
0x1800316f1  mov     esi, edx
0x1800316f3  mov     rdi, rcx
0x1800316f6  mov     [rbp+4Fh+var_A0], edx
0x1800316f9  mov     [rbp+4Fh+var_A8], r8d
0x1800316fd  mov     [rbp+4Fh+var_98], r9d
0x180031701  mov     r14, [rbp+4Fh+arg_20]
0x180031705  lea     rcx, [rbp+4Fh+newString]
0x180031709  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18003170e  test    r9d, r9d
0x180031711  jz      loc_1800317F6
0x180031717  mov     [rbp+4Fh+hMem], 0
0x18003171f  lea     rcx, [rbp+4Fh+hMem]
0x180031723  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180031729  mov     ebx, eax
0x18003172b  test    eax, eax
0x18003172d  jns     short loc_18003174C
0x18003172f  mov     rcx, [rbp+57h]; this
0x180031733  mov     r9d, eax; char *
0x180031736  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003173d  mov     edx, 443h; void *
0x180031742  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031747  jmp     loc_180031983
0x18003174c  mov     [rsp+110h+string], 0
0x180031755  lea     rdx, [rbp+4Fh+hMem]
0x180031759  lea     rcx, [rsp+110h+string]
0x18003175e  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180031763  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180031767  call    cs:__imp_LocalFree
0x18003176d  xor     edx, edx
0x18003176f  lea     rcx, [rbp+4Fh+newString]
0x180031773  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180031778  lea     rcx, [rbp+4Fh+newString]
0x18003177c  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x180031781  test    al, al
0x180031783  jnz     short loc_1800317A3
0x180031785  lea     rcx, [rbp+4Fh+var_B8]
0x180031789  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18003178e  mov     rdx, rax
0x180031791  lea     rcx, [rbp+4Fh+newString]
0x180031795  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18003179a  lea     rcx, [rbp+4Fh+var_B8]
0x18003179e  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800317a3  mov     rdx, qword ptr [rbp+4Fh+newString]; newString
0x1800317a7  mov     rcx, [rsp+110h+string]; string
0x1800317ac  call    cs:__imp_WindowsDuplicateString
0x1800317b2  mov     ebx, eax
0x1800317b4  test    eax, eax
0x1800317b6  jns     short loc_1800317E9
0x1800317b8  mov     rcx, [rbp+57h]; this
0x1800317bc  mov     r9d, eax; char *
0x1800317bf  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800317c6  mov     edx, 447h; void *
0x1800317cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800317d0  mov     rcx, [rsp+110h+string]; string
0x1800317d5  call    cs:__imp_WindowsDeleteString
0x1800317db  mov     [rsp+110h+string], 0
0x1800317e4  jmp     loc_180031983
0x1800317e9  mov     rcx, [rsp+110h+string]; string
0x1800317ee  call    cs:__imp_WindowsDeleteString
0x1800317f4  jmp     short loc_180031802
0x1800317f6  xor     edx, edx
0x1800317f8  lea     rcx, [rbp+4Fh+newString]
0x1800317fc  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180031801  nop
0x180031802  mov     [rbp+4Fh+var_B8], rdi
0x180031806  lea     rcx, [rbp+4Fh+var_B8]
0x18003180a  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18003180f  xor     ecx, ecx
0x180031811  mov     [rbp+4Fh+var_C8], rcx
0x180031815  cmp     esi, 2
0x180031818  jnz     loc_1800318A1
0x18003181e  lea     r9, [rbp+4Fh+var_48]; string
0x180031822  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180031826  lea     edx, [rcx+49h]; length
0x180031829  lea     rcx, ?RuntimeClass_EnterpriseDeviceManagement_Service_AutoPilot_EnrollmentStatusTrackingUtil@@3QBGB; "EnterpriseDeviceManagement.Service.Auto"...
0x180031830  call    cs:__imp_WindowsCreateStringReference
0x180031836  test    eax, eax
0x180031838  jns     short loc_18003184E
0x18003183a  xor     r9d, r9d; lpArguments
0x18003183d  xor     r8d, r8d; nNumberOfArguments
0x180031840  lea     edx, [rsi-1]; dwExceptionFlags
0x180031843  mov     ecx, 0C000000Dh; dwExceptionCode
0x180031848  call    cs:__imp_RaiseException
0x18003184e  lea     rdx, [rbp+4Fh+var_C8]
0x180031852  mov     rcx, [rbp+4Fh+var_48]
0x180031856  call    ??$ActivateInstance@V?$ComPtr@UIEnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<EnterpriseDeviceManagement::Service::AutoPilot::IEnrollmentStatusTrackingUtil>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<EnterpriseDeviceManagement::Service::AutoPilot::IEnrollmentStatusTrackingUtil>>)
0x18003185b  mov     ebx, eax
0x18003185d  test    eax, eax
0x18003185f  jns     short loc_18003189D
0x180031861  mov     rcx, [rbp+57h]; this
0x180031865  mov     r9d, eax; char *
0x180031868  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003186f  mov     edx, 453h; void *
0x180031874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031879  lea     rcx, [rbp+4Fh+var_C8]
0x18003187d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180031882  nop
0x180031883  test    rdi, rdi
0x180031886  jz      short loc_180031898
0x180031888  mov     rax, [rdi]
0x18003188b  mov     rcx, rdi
0x18003188e  mov     rax, [rax+10h]
0x180031892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031897  nop
0x180031898  jmp     loc_180031983
0x18003189d  mov     rcx, [rbp+4Fh+var_C8]
0x1800318a1  mov     [rbp+4Fh+var_C0], 0
0x1800318a9  test    rcx, rcx
0x1800318ac  jz      short loc_180031902
0x1800318ae  lea     rdx, [rbp+4Fh+var_C0]
0x1800318b2  call    ?GetAgileReferenceForType@?$AgileObjectConvertT@UIEnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@@SAJPEAUIEnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@AEAV?$com_ptr_t@UIAgileReference@@Uerr_returncode_policy@wil@@@wil@@@Z; AgileObjectConvertT<EnterpriseDeviceManagement::Service::AutoPilot::IEnrollmentStatusTrackingUtil>::GetAgileReferenceForType(EnterpriseDeviceManagement::Service::AutoPilot::IEnrollmentStatusTrackingUtil *,wil::com_ptr_t<IAgileReference,wil::err_returncode_policy> &)
0x1800318b7  mov     ebx, eax
0x1800318b9  test    eax, eax
0x1800318bb  jns     short loc_180031902
0x1800318bd  mov     rcx, [rbp+57h]; this
0x1800318c1  mov     r9d, eax; char *
0x1800318c4  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800318cb  mov     edx, 459h; void *
0x1800318d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800318d5  lea     rcx, [rbp+4Fh+var_C0]
0x1800318d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800318de  lea     rcx, [rbp+4Fh+var_C8]
0x1800318e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800318e7  nop
0x1800318e8  test    rdi, rdi
0x1800318eb  jz      short loc_1800318FD
0x1800318ed  mov     rax, [rdi]
0x1800318f0  mov     rcx, rdi
0x1800318f3  mov     rax, [rax+10h]
0x1800318f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318fc  nop
0x1800318fd  jmp     loc_180031983
0x180031902  lea     rax, [rbp+4Fh+var_A8]
0x180031906  mov     [rsp+110h+var_E0], rax
0x18003190b  lea     rax, [rbp+4Fh+var_A0]
0x18003190f  mov     [rsp+110h+var_E8], rax
0x180031914  lea     rax, [rbp+4Fh+var_98]
0x180031918  mov     [rsp+110h+var_F0], rax
0x18003191d  lea     r9, [rbp+4Fh+var_C0]
0x180031921  lea     r8, [rbp+4Fh+newString]
0x180031925  lea     rdx, [rbp+4Fh+var_B8]
0x180031929  lea     rcx, [rbp+4Fh+var_78]
0x18003192d  call    _lambda_6e73326332f4df0235e1c9bdb5daeaef____lambda_6e73326332f4df0235e1c9bdb5daeaef_
0x180031932  mov     dword ptr [rbp+4Fh+var_B8], 3
0x180031939  mov     [rbp+4Fh+var_B8+4], 80h
0x180031941  mov     r9, rax
0x180031944  mov     rdx, r14
0x180031947  lea     rcx, [rbp+4Fh+var_B8]
0x18003194b  call    Windows__Internal__MakeAsyncOperationWithProgress_Windows__Internal__ProgressResult_Windows__Internal__CMarshaledInterfaceResult_EnterpriseDeviceManagement__Enrollment__IExpectedAndCurrentResourceAmount__EnterpriseDeviceManagement__Enrollment__ExpectedAndCurrentResourceProgress__EnterpriseDeviceManagement__Enrollment__ExpectedAndCurrentResourceAmount___EnterpriseDeviceManagement__Enrollment__ExpectedAndCurrentResourceProgress_Windows__Internal__ComTaskPoolHandler__lambda_6e73326332f4df0235e1c9bdb5daeaef___
0x180031950  mov     ebx, eax
0x180031952  lea     rcx, [rbp+4Fh+var_78]
0x180031956  call    _lambda_6e73326332f4df0235e1c9bdb5daeaef_____lambda_6e73326332f4df0235e1c9bdb5daeaef_
0x18003195b  lea     rcx, [rbp+4Fh+var_C0]
0x18003195f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031964  lea     rcx, [rbp+4Fh+var_C8]
0x180031968  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003196d  nop
0x18003196e  test    rdi, rdi
0x180031971  jz      short loc_180031983
0x180031973  mov     rcx, [rdi]
0x180031976  mov     rax, [rcx+10h]
0x18003197a  mov     rcx, rdi
0x18003197d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031982  nop
0x180031983  lea     rcx, [rbp+4Fh+newString]
0x180031987  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18003198c  mov     eax, ebx
0x18003198e  mov     rcx, [rbp+4Fh+var_28]
0x180031992  xor     rcx, rsp; StackCookie
0x180031995  call    __security_check_cookie
0x18003199a  add     rsp, 0F0h
0x1800319a1  pop     r14
0x1800319a3  pop     rdi
0x1800319a4  pop     rsi
0x1800319a5  pop     rbx
0x1800319a6  pop     rbp
0x1800319a7  retn
```
