# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::PollForExpectedPoliciesAndResources(EnterpriseDeviceManagement::Enrollment::ResourceToTrack,int,EnterpriseDeviceManagement::Enrollment::MDMProgressMode,Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress> * *)

- ea: `0x1800303e0`
- end: `0x1800306e3`
- name: `?PollForExpectedPoliciesAndResources@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJW4ResourceToTrack@23@HW4MDMProgressMode@23@PEAPEAU?$IAsyncOperationWithProgress@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@Z`
- size: `771`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004eb0`
- `0x180009be4`
- `0x18000a5c4`
- `0x180017298`
- `0x180017860`
- `0x180017b70`
- `0x180017bf0`
- `0x18001823c`
- `0x1800184e8`
- `0x180018738`
- `0x180019678`
- `0x18001c260`
- `0x18001c920`
- `0x18001d44c`
- `0x180020e84`
- `0x1800231e8`
- `0x18002d260`
- `0x1800303e0`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180030433`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180030433`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003057c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003057c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003055e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003055e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800304c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800304c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800304f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800304f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030516`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003047d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003047d`

## string_xrefs

- `0x180030557`: `EnterpriseDeviceManagement.Service.AutoPilot.EnrollmentStatusTrackingUtil`

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
  __int64 v10; // rax
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
  HSTRING *newString[2]; // [rsp+88h] [rbp-39h] BYREF
  _BYTE v28[48]; // [rsp+98h] [rbp-29h] BYREF
  HSTRING v29; // [rsp+C8h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v24 = a2;
  v23 = a3;
  v25 = a4;
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(newString);
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
      newString,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(newString) )
    {
      v10 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v22);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        newString,
        v10);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v22);
    }
    v11 = WindowsDuplicateString(string, newString[0]);
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
      newString,
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
            v29,
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
            (unsigned int)newString,
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
  std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(newString);
  return v9;
}

```

## disassembly

```asm
0x1800303e0  push    rbp
0x1800303e2  push    rbx
0x1800303e3  push    rsi
0x1800303e4  push    rdi
0x1800303e5  push    r14
0x1800303e7  lea     rbp, [rsp-2Fh]
0x1800303ec  sub     rsp, 0F0h
0x1800303f3  mov     rax, cs:__security_cookie
0x1800303fa  xor     rax, rsp
0x1800303fd  mov     [rbp+4Fh+var_28], rax
0x180030401  mov     esi, edx
0x180030403  mov     rdi, rcx
0x180030406  mov     [rbp+4Fh+var_A0], edx
0x180030409  mov     [rbp+4Fh+var_A8], r8d
0x18003040d  mov     [rbp+4Fh+var_98], r9d
0x180030411  mov     r14, [rbp+4Fh+arg_20]
0x180030415  lea     rcx, [rbp+4Fh+newString]
0x180030419  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18003041e  test    r9d, r9d
0x180030421  jz      loc_180030524
0x180030427  mov     [rbp+4Fh+hMem], 0
0x18003042f  lea     rcx, [rbp+4Fh+hMem]
0x180030433  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18003043a  nop     dword ptr [rax+rax+00h]
0x18003043f  mov     ebx, eax
0x180030441  test    eax, eax
0x180030443  jns     short loc_180030462
0x180030445  mov     rcx, [rbp+57h]; this
0x180030449  mov     r9d, eax; char *
0x18003044c  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180030453  mov     edx, 443h; void *
0x180030458  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003045d  jmp     loc_1800306BD
0x180030462  mov     [rsp+110h+string], 0
0x18003046b  lea     rdx, [rbp+4Fh+hMem]
0x18003046f  lea     rcx, [rsp+110h+string]
0x180030474  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180030479  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18003047d  call    cs:__imp_LocalFree
0x180030484  nop     dword ptr [rax+rax+00h]
0x180030489  xor     edx, edx
0x18003048b  lea     rcx, [rbp+4Fh+newString]
0x18003048f  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180030494  lea     rcx, [rbp+4Fh+newString]
0x180030498  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18003049d  test    al, al
0x18003049f  jnz     short loc_1800304BF
0x1800304a1  lea     rcx, [rbp+4Fh+var_B8]
0x1800304a5  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x1800304aa  mov     rdx, rax
0x1800304ad  lea     rcx, [rbp+4Fh+newString]
0x1800304b1  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x1800304b6  lea     rcx, [rbp+4Fh+var_B8]
0x1800304ba  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800304bf  mov     rdx, [rbp+4Fh+newString]; newString
0x1800304c3  mov     rcx, [rsp+110h+string]; string
0x1800304c8  call    cs:__imp_WindowsDuplicateString
0x1800304cf  nop     dword ptr [rax+rax+00h]
0x1800304d4  mov     ebx, eax
0x1800304d6  test    eax, eax
0x1800304d8  jns     short loc_180030511
0x1800304da  mov     rcx, [rbp+57h]; this
0x1800304de  mov     r9d, eax; char *
0x1800304e1  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800304e8  mov     edx, 447h; void *
0x1800304ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304f2  mov     rcx, [rsp+110h+string]; string
0x1800304f7  call    cs:__imp_WindowsDeleteString
0x1800304fe  nop     dword ptr [rax+rax+00h]
0x180030503  mov     [rsp+110h+string], 0
0x18003050c  jmp     loc_1800306BD
0x180030511  mov     rcx, [rsp+110h+string]; string
0x180030516  call    cs:__imp_WindowsDeleteString
0x18003051d  nop     dword ptr [rax+rax+00h]
0x180030522  jmp     short loc_180030530
0x180030524  xor     edx, edx
0x180030526  lea     rcx, [rbp+4Fh+newString]
0x18003052a  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18003052f  nop
0x180030530  mov     [rbp+4Fh+var_B8], rdi
0x180030534  lea     rcx, [rbp+4Fh+var_B8]
0x180030538  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18003053d  xor     ecx, ecx
0x18003053f  mov     [rbp+4Fh+var_C8], rcx
0x180030543  cmp     esi, 2
0x180030546  jnz     loc_1800305DB
0x18003054c  lea     r9, [rbp+4Fh+var_48]; string
0x180030550  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180030554  lea     edx, [rcx+49h]; length
0x180030557  lea     rcx, ?RuntimeClass_EnterpriseDeviceManagement_Service_AutoPilot_EnrollmentStatusTrackingUtil@@3QBGB; "EnterpriseDeviceManagement.Service.Auto"...
0x18003055e  call    cs:__imp_WindowsCreateStringReference
0x180030565  nop     dword ptr [rax+rax+00h]
0x18003056a  test    eax, eax
0x18003056c  jns     short loc_180030588
0x18003056e  xor     r9d, r9d; lpArguments
0x180030571  xor     r8d, r8d; nNumberOfArguments
0x180030574  lea     edx, [rsi-1]; dwExceptionFlags
0x180030577  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003057c  call    cs:__imp_RaiseException
0x180030583  nop     dword ptr [rax+rax+00h]
0x180030588  lea     rdx, [rbp+4Fh+var_C8]
0x18003058c  mov     rcx, [rbp+4Fh+var_48]
0x180030590  call    ??$ActivateInstance@V?$ComPtr@UIEnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<EnterpriseDeviceManagement::Service::AutoPilot::IEnrollmentStatusTrackingUtil>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<EnterpriseDeviceManagement::Service::AutoPilot::IEnrollmentStatusTrackingUtil>>)
0x180030595  mov     ebx, eax
0x180030597  test    eax, eax
0x180030599  jns     short loc_1800305D7
0x18003059b  mov     rcx, [rbp+57h]; this
0x18003059f  mov     r9d, eax; char *
0x1800305a2  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800305a9  mov     edx, 453h; void *
0x1800305ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800305b3  lea     rcx, [rbp+4Fh+var_C8]
0x1800305b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800305bc  nop
0x1800305bd  test    rdi, rdi
0x1800305c0  jz      short loc_1800305D2
0x1800305c2  mov     rax, [rdi]
0x1800305c5  mov     rcx, rdi
0x1800305c8  mov     rax, [rax+10h]
0x1800305cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305d1  nop
0x1800305d2  jmp     loc_1800306BD
0x1800305d7  mov     rcx, [rbp+4Fh+var_C8]
0x1800305db  mov     [rbp+4Fh+var_C0], 0
0x1800305e3  test    rcx, rcx
0x1800305e6  jz      short loc_18003063C
0x1800305e8  lea     rdx, [rbp+4Fh+var_C0]
0x1800305ec  call    ?GetAgileReferenceForType@?$AgileObjectConvertT@UIEnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@@SAJPEAUIEnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@AEAV?$com_ptr_t@UIAgileReference@@Uerr_returncode_policy@wil@@@wil@@@Z; AgileObjectConvertT<EnterpriseDeviceManagement::Service::AutoPilot::IEnrollmentStatusTrackingUtil>::GetAgileReferenceForType(EnterpriseDeviceManagement::Service::AutoPilot::IEnrollmentStatusTrackingUtil *,wil::com_ptr_t<IAgileReference,wil::err_returncode_policy> &)
0x1800305f1  mov     ebx, eax
0x1800305f3  test    eax, eax
0x1800305f5  jns     short loc_18003063C
0x1800305f7  mov     rcx, [rbp+57h]; this
0x1800305fb  mov     r9d, eax; char *
0x1800305fe  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180030605  mov     edx, 459h; void *
0x18003060a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003060f  lea     rcx, [rbp+4Fh+var_C0]
0x180030613  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180030618  lea     rcx, [rbp+4Fh+var_C8]
0x18003061c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030621  nop
0x180030622  test    rdi, rdi
0x180030625  jz      short loc_180030637
0x180030627  mov     rax, [rdi]
0x18003062a  mov     rcx, rdi
0x18003062d  mov     rax, [rax+10h]
0x180030631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030636  nop
0x180030637  jmp     loc_1800306BD
0x18003063c  lea     rax, [rbp+4Fh+var_A8]
0x180030640  mov     [rsp+110h+var_E0], rax
0x180030645  lea     rax, [rbp+4Fh+var_A0]
0x180030649  mov     [rsp+110h+var_E8], rax
0x18003064e  lea     rax, [rbp+4Fh+var_98]
0x180030652  mov     [rsp+110h+var_F0], rax
0x180030657  lea     r9, [rbp+4Fh+var_C0]
0x18003065b  lea     r8, [rbp+4Fh+newString]
0x18003065f  lea     rdx, [rbp+4Fh+var_B8]
0x180030663  lea     rcx, [rbp+4Fh+var_78]
0x180030667  call    _lambda_6e73326332f4df0235e1c9bdb5daeaef____lambda_6e73326332f4df0235e1c9bdb5daeaef_
0x18003066c  mov     dword ptr [rbp+4Fh+var_B8], 3
0x180030673  mov     [rbp+4Fh+var_B8+4], 80h
0x18003067b  mov     r9, rax
0x18003067e  mov     rdx, r14
0x180030681  lea     rcx, [rbp+4Fh+var_B8]
0x180030685  call    Windows__Internal__MakeAsyncOperationWithProgress_Windows__Internal__ProgressResult_Windows__Internal__CMarshaledInterfaceResult_EnterpriseDeviceManagement__Enrollment__IExpectedAndCurrentResourceAmount__EnterpriseDeviceManagement__Enrollment__ExpectedAndCurrentResourceProgress__EnterpriseDeviceManagement__Enrollment__ExpectedAndCurrentResourceAmount___EnterpriseDeviceManagement__Enrollment__ExpectedAndCurrentResourceProgress_Windows__Internal__ComTaskPoolHandler__lambda_6e73326332f4df0235e1c9bdb5daeaef___
0x18003068a  mov     ebx, eax
0x18003068c  lea     rcx, [rbp+4Fh+var_78]
0x180030690  call    _lambda_6e73326332f4df0235e1c9bdb5daeaef_____lambda_6e73326332f4df0235e1c9bdb5daeaef_
0x180030695  lea     rcx, [rbp+4Fh+var_C0]
0x180030699  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003069e  lea     rcx, [rbp+4Fh+var_C8]
0x1800306a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800306a7  nop
0x1800306a8  test    rdi, rdi
0x1800306ab  jz      short loc_1800306BD
0x1800306ad  mov     rcx, [rdi]
0x1800306b0  mov     rax, [rcx+10h]
0x1800306b4  mov     rcx, rdi
0x1800306b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306bc  nop
0x1800306bd  lea     rcx, [rbp+4Fh+newString]
0x1800306c1  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800306c6  mov     eax, ebx
0x1800306c8  mov     rcx, [rbp+4Fh+var_28]
0x1800306cc  xor     rcx, rsp; StackCookie
0x1800306cf  call    __security_check_cookie
0x1800306d4  add     rsp, 0F0h
0x1800306db  pop     r14
0x1800306dd  pop     rdi
0x1800306de  pop     rsi
0x1800306df  pop     rbx
0x1800306e0  pop     rbp
0x1800306e1  retn
```
