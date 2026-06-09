# AppServiceHelper::OpenAppServiceAndSendMessageAsync(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet * *,HSTRING__ * *)

- ea: `0x18001e0f0`
- end: `0x18001e721`
- name: `?OpenAppServiceAndSendMessageAsync@AppServiceHelper@@QEAAJPEAUHSTRING__@@000PEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU3456@PEAPEAU2@@Z`
- size: `1585`
- prototype: `__int64 __usercall@<rax>(AppServiceHelper *__hidden this@<rcx>, HSTRING@<rdx>, HSTRING@<r8>, HSTRING@<r9>, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, struct Windows::Foundation::Collections::IPropertySet **, HSTRING *)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028a64`
- `0x180028eb4`
- `0x18004bdac`

## callees

- `0x180003678`
- `0x18000c2f4`
- `0x18000eb48`
- `0x1800198bc`
- `0x18001d1a4`
- `0x18001e0f0`
- `0x18001e728`
- `0x18001e77c`
- `0x18001e798`
- `0x18001e820`
- `0x18002c570`
- `0x18002d1a4`
- `0x18003a524`
- `0x18003afb0`
- `0x18003b58c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001e18e`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001e18e`
- `cdp!CDPAcquireNetworkingInternal` at `0x18001e2c5`
- `cdp!CDPAcquireNetworkingInternal` at `0x18001e2c5`

## string_xrefs

- `0x18001e23c`: `..\appservicehelper.cpp`
- `0x18001e330`: `..\appservicehelper.cpp`
- `0x18001e3d6`: `..\appservicehelper.cpp`
- `0x18001e416`: `..\appservicehelper.cpp`
- `0x18001e4da`: `..\appservicehelper.cpp`
- `0x18001e544`: `..\appservicehelper.cpp`
- `0x18001e693`: `..\appservicehelper.cpp`
- `0x18001e2be`: `CDP Call App Service`
- `0x18001e383`: `Opening App Service connection...`
- `0x18001e49b`: `Successfully opened connection to App Service.`
- `0x18001e5c4`: `Failure opening App Service connection. AppServiceConnectionStatus = %d.`
- `0x18001e163`: `Windows.ApplicationModel.AppService.AppServiceConnection`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall AppServiceHelper::OpenAppServiceAndSendMessageAsync(
        AppServiceHelper *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING a5,
        struct Windows::Foundation::Collections::IPropertySet *a6,
        struct Windows::Foundation::Collections::IPropertySet **a7,
        HSTRING *a8)
{
  HSTRING v12; // rsi
  __int64 v13; // rbx
  int v14; // edi
  struct Windows::ApplicationModel::AppService::IAppServiceConnection *v15; // rbx
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  __int64 (__fastcall *v18)(struct Windows::ApplicationModel::AppService::IAppServiceConnection *, GUID *, __int64 *); // rdi
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  struct Windows::ApplicationModel::AppService::IAppServiceConnection *v22; // rbx
  __int64 (__fastcall *v23)(struct Windows::ApplicationModel::AppService::IAppServiceConnection *, GUID *, __int64 *); // rdi
  int v24; // eax
  int v25; // eax
  HRESULT v26; // edx
  __int64 v27; // r8
  int (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // rcx
  int (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v30; // rcx
  int v31; // eax
  int (__fastcall ***v32)(_QWORD, GUID *, __int64 *); // rcx
  int v33; // eax
  int (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // rcx
  int v35; // ebx
  int (__fastcall ***v36)(_QWORD, GUID *, __int64 *); // rcx
  int (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // rcx
  int v39; // [rsp+20h] [rbp-B1h]
  HSTRING v40; // [rsp+30h] [rbp-A1h] BYREF
  int (__fastcall ***v41)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-99h] BYREF
  struct Windows::ApplicationModel::AppService::IAppServiceConnection *v42; // [rsp+40h] [rbp-91h] BYREF
  struct Windows::ApplicationModel::AppService::IAppServiceConnection *v43; // [rsp+48h] [rbp-89h] BYREF
  __int64 v44; // [rsp+50h] [rbp-81h] BYREF
  int v45; // [rsp+58h] [rbp-79h] BYREF
  int v46; // [rsp+5Ch] [rbp-75h] BYREF
  int v47; // [rsp+60h] [rbp-71h] BYREF
  __int64 v48; // [rsp+68h] [rbp-69h] BYREF
  HSTRING v49; // [rsp+70h] [rbp-61h] BYREF
  struct Windows::ApplicationModel::AppService::IAppServiceConnection **v50; // [rsp+78h] [rbp-59h] BYREF
  __int16 v51; // [rsp+80h] [rbp-51h]
  HSTRING *v52; // [rsp+88h] [rbp-49h]
  struct Windows::Foundation::Collections::IPropertySet **v53; // [rsp+90h] [rbp-41h]
  struct Windows::Foundation::Collections::IPropertySet *v54; // [rsp+98h] [rbp-39h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v12 = a5;
  v49 = a5;
  v54 = a6;
  v53 = a7;
  v52 = a8;
  *a7 = 0;
  *a8 = 0;
  v42 = 0;
  v48 = 0;
  v56 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.AppService.AppServiceConnection",
    0x39u,
    0x38u);
  v13 = v56;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  v42 = 0;
  v14 = RoActivateInstance(v13, &v43);
  if ( v14 >= 0 )
  {
    if ( !memcmp_0(&GUID_9dd474a2_871f_4d52_89a9_9e090531bd27, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v15 = v43;
      v42 = v43;
      goto LABEL_6;
    }
    v14 = (**(__int64 (__fastcall ***)(struct Windows::ApplicationModel::AppService::IAppServiceConnection *, GUID *, struct Windows::ApplicationModel::AppService::IAppServiceConnection **))v43)(
            v43,
            &GUID_9dd474a2_871f_4d52_89a9_9e090531bd27,
            &v42);
    (*(void (__fastcall **)(struct Windows::ApplicationModel::AppService::IAppServiceConnection *))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v15 = v42;
LABEL_6:
  if ( v14 < 0 )
  {
    v16 = (unsigned int)v14;
    v17 = 61;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"..\\appservicehelper.cpp",
      (const char *)v16,
      v39);
    goto LABEL_74;
  }
  v18 = **(__int64 (__fastcall ***)(struct Windows::ApplicationModel::AppService::IAppServiceConnection *, GUID *, __int64 *))v15;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  v19 = v18(v15, &GUID_5589d172_e359_4531_b856_f5c6c46bda54, &v48);
  v14 = v19;
  if ( v19 < 0 )
  {
    v17 = 63;
LABEL_10:
    v16 = (unsigned int)v19;
    goto LABEL_11;
  }
  v19 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::AppService::IAppServiceConnection *, HSTRING))(*(_QWORD *)v42 + 56LL))(
          v42,
          a3);
  v14 = v19;
  if ( v19 < 0 )
  {
    v17 = 65;
    goto LABEL_10;
  }
  v19 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::AppService::IAppServiceConnection *, HSTRING))(*(_QWORD *)v42 + 72LL))(
          v42,
          a2);
  v14 = v19;
  if ( v19 < 0 )
  {
    v17 = 66;
    goto LABEL_10;
  }
  v19 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v48 + 64LL))(v48, a4);
  v14 = v19;
  if ( v19 < 0 )
  {
    v17 = 67;
    goto LABEL_10;
  }
  v47 = 0;
  v46 = CDPAcquireNetworkingInternal("CDP Call App Service", 12, &v47);
  if ( v46 < 0 )
    Log<long &>(1, "Failure acquiring networking. hr = 0x%08x.", (unsigned int)&v46);
  hstringHeader.Reserved.Reserved1 = &v46;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v47;
  *(_WORD *)&hstringHeader.Reserved.Reserved2[16] = 258;
  v43 = 0;
  if ( a5 )
  {
    v40 = 0;
    v20 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,HSTRING__ *,unsigned short [3]>(
            &v40,
            &v49,
            (__int64)L".0");
    v14 = v20;
    if ( v20 < 0 )
    {
      v21 = 97;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"..\\appservicehelper.cpp",
        (const char *)(unsigned int)v20,
        v39);
      Windows::Internal::String::~String((Windows::Internal::String *)&v40);
LABEL_73:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      wil::details::ScopeExitFnGuard__lambda_0dec34c376930ac50f1e03ef428d1639___::operator()(&hstringHeader);
      goto LABEL_74;
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 4) + 64LL))(*((_QWORD *)this + 4), v40);
    v14 = v20;
    if ( v20 < 0 )
    {
      v21 = 98;
      goto LABEL_23;
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&v40);
    v12 = v49;
  }
  Log<>(4u, "Opening App Service connection...");
  v44 = 0;
  v22 = v42;
  v23 = **(__int64 (__fastcall ***)(struct Windows::ApplicationModel::AppService::IAppServiceConnection *, GUID *, __int64 *))v42;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  v24 = v23(v22, &GUID_7223c1d7_ab9b_46ab_9a82_1dac56158529, &v44);
  v14 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"..\\appservicehelper.cpp",
      (const char *)(unsigned int)v24,
      v39);
LABEL_72:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    goto LABEL_73;
  }
  v41 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v44 + 48LL))(v44, 1, &v41);
  v14 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"..\\appservicehelper.cpp",
      (const char *)(unsigned int)v25,
      v39);
    v28 = v41;
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v28)[2])(v28);
    }
    goto LABEL_72;
  }
  v50 = &v42;
  v51 = 258;
  v45 = 4;
  v29 = v41;
  v14 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(
          v41,
          v26,
          v27);
  if ( v14 < 0
    || (v14 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), int *))(*v29)[8])(v29, &v45),
        v14 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"..\\appservicehelper.cpp",
      (const char *)(unsigned int)v14,
      v39);
    wil::details::ScopeExitFnGuard__lambda_da820c26f9e92d7bbd7d39f2b8f752f1___::operator()(&v50);
    v37 = v41;
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v37)[2])(v37);
    }
    goto LABEL_72;
  }
  if ( v45 )
  {
    LODWORD(v40) = v45;
    Log<int>(v30, "Failure opening App Service connection. AppServiceConnectionStatus = %d.", (unsigned int)&v40);
    if ( v45 > 6 )
    {
      switch ( v45 )
      {
        case 8:
          v35 = -2147221238;
          goto LABEL_67;
        case 9:
          v35 = -2147218425;
          goto LABEL_67;
        case 10:
          v35 = -2147221222;
          goto LABEL_67;
        case 11:
          v35 = -2147220734;
          goto LABEL_67;
      }
    }
    else
    {
      switch ( v45 )
      {
        case 6:
          v35 = -2147217655;
          goto LABEL_67;
        case 0:
          v35 = 0;
          goto LABEL_67;
        case 1:
          v35 = -2147217663;
          goto LABEL_67;
        case 2:
          v35 = -2147217662;
          goto LABEL_67;
        case 3:
          v35 = -2147217661;
          goto LABEL_67;
      }
    }
    v35 = -2147217660;
  }
  else
  {
    Log<>(4u, "Successfully opened connection to App Service.");
    if ( v12 )
    {
      v40 = 0;
      v31 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,HSTRING__ *,unsigned short [3]>(
              &v40,
              &v49,
              (__int64)L".1");
      v14 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x88,
          (unsigned int)"..\\appservicehelper.cpp",
          (const char *)(unsigned int)v31,
          v39);
        Windows::Internal::String::~String((Windows::Internal::String *)&v40);
        wil::details::ScopeExitFnGuard__lambda_da820c26f9e92d7bbd7d39f2b8f752f1___::operator()(&v50);
        v32 = v41;
        if ( v41 )
        {
          v41 = 0;
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v32)[2])(v32);
        }
        goto LABEL_72;
      }
      v33 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 4) + 64LL))(*((_QWORD *)this + 4), v40);
      v14 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89,
          (unsigned int)"..\\appservicehelper.cpp",
          (const char *)(unsigned int)v33,
          v39);
        Windows::Internal::String::~String((Windows::Internal::String *)&v40);
        wil::details::ScopeExitFnGuard__lambda_da820c26f9e92d7bbd7d39f2b8f752f1___::operator()(&v50);
        v34 = v41;
        if ( v41 )
        {
          v41 = 0;
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v34)[2])(v34);
        }
        goto LABEL_72;
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&v40);
    }
    v35 = AppServiceHelper::AppServiceSendMessageAsync(this, v42, v54, v53, v52);
  }
LABEL_67:
  wil::details::ScopeExitFnGuard__lambda_da820c26f9e92d7bbd7d39f2b8f752f1___::operator()(&v50);
  v36 = v41;
  if ( v41 )
  {
    v41 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v36)[2])(v36);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
  wil::details::ScopeExitFnGuard__lambda_0dec34c376930ac50f1e03ef428d1639___::operator()(&hstringHeader);
  v14 = v35;
LABEL_74:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001e0f0  push    rbp
0x18001e0f2  push    rbx
0x18001e0f3  push    rsi
0x18001e0f4  push    rdi
0x18001e0f5  push    r12
0x18001e0f7  push    r13
0x18001e0f9  push    r14
0x18001e0fb  push    r15
0x18001e0fd  lea     rbp, [rsp-7]
0x18001e102  sub     rsp, 0D8h
0x18001e109  mov     rax, cs:__security_cookie
0x18001e110  xor     rax, rsp
0x18001e113  mov     [rbp+3Fh+var_50], rax
0x18001e117  mov     r13, r9
0x18001e11a  mov     r15, r8
0x18001e11d  mov     r12, rdx
0x18001e120  mov     r14, rcx
0x18001e123  mov     rsi, [rbp+3Fh+arg_20]
0x18001e127  mov     [rbp+3Fh+var_A0], rsi
0x18001e12b  mov     rax, [rbp+3Fh+arg_28]
0x18001e12f  mov     [rbp+3Fh+var_78], rax
0x18001e133  mov     rax, [rbp+3Fh+arg_30]
0x18001e137  mov     [rbp+3Fh+var_80], rax
0x18001e13b  mov     rcx, [rbp+3Fh+arg_38]
0x18001e142  mov     [rbp+3Fh+var_88], rcx
0x18001e146  xor     edi, edi
0x18001e148  mov     [rax], rdi
0x18001e14b  mov     [rcx], rdi
0x18001e14e  mov     [rsp+110h+var_D0], rdi
0x18001e153  mov     [rbp+3Fh+var_A8], rdi
0x18001e157  mov     [rbp+3Fh+var_58], rdi
0x18001e15b  lea     r9d, [rdi+38h]; unsigned int
0x18001e15f  lea     r8d, [rdi+39h]; unsigned int
0x18001e163  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_AppService_AppServiceConnection@@3QBGB; "Windows.ApplicationModel.AppService.App"...
0x18001e16a  lea     rcx, [rbp+3Fh+hstringHeader]; hstringHeader
0x18001e16e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001e173  mov     rbx, [rbp+3Fh+var_58]
0x18001e177  lea     rcx, [rsp+110h+var_D0]
0x18001e17c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e181  mov     [rsp+110h+var_D0], rdi
0x18001e186  lea     rdx, [rsp+110h+var_C8]
0x18001e18b  mov     rcx, rbx
0x18001e18e  call    cs:__imp_RoActivateInstance
0x18001e194  mov     edi, eax
0x18001e196  test    eax, eax
0x18001e198  js      short loc_18001E1F2
0x18001e19a  mov     r8d, 10h; Size
0x18001e1a0  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18001e1a7  lea     rcx, _GUID_9dd474a2_871f_4d52_89a9_9e090531bd27; Buf1
0x18001e1ae  call    memcmp_0
0x18001e1b3  test    eax, eax
0x18001e1b5  jnz     short loc_18001E1C3
0x18001e1b7  mov     rbx, [rsp+110h+var_C8]
0x18001e1bc  mov     [rsp+110h+var_D0], rbx
0x18001e1c1  jmp     short loc_18001E1F7
0x18001e1c3  mov     rcx, [rsp+110h+var_C8]
0x18001e1c8  mov     rax, [rcx]
0x18001e1cb  lea     r8, [rsp+110h+var_D0]
0x18001e1d0  lea     rdx, _GUID_9dd474a2_871f_4d52_89a9_9e090531bd27
0x18001e1d7  mov     rax, [rax]
0x18001e1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1df  mov     edi, eax
0x18001e1e1  mov     rcx, [rsp+110h+var_C8]
0x18001e1e6  mov     rax, [rcx]
0x18001e1e9  mov     rax, [rax+10h]
0x18001e1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1f2  mov     rbx, [rsp+110h+var_D0]
0x18001e1f7  test    edi, edi
0x18001e1f9  jns     short loc_18001E205
0x18001e1fb  mov     r9d, edi
0x18001e1fe  mov     edx, 3Dh ; '='
0x18001e203  jmp     short loc_18001E238
0x18001e205  mov     rax, [rbx]
0x18001e208  mov     rdi, [rax]
0x18001e20b  lea     rcx, [rbp+3Fh+var_A8]
0x18001e20f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e214  lea     r8, [rbp+3Fh+var_A8]
0x18001e218  lea     rdx, _GUID_5589d172_e359_4531_b856_f5c6c46bda54
0x18001e21f  mov     rcx, rbx
0x18001e222  mov     rax, rdi
0x18001e225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e22a  mov     edi, eax
0x18001e22c  test    eax, eax
0x18001e22e  jns     short loc_18001E24D
0x18001e230  mov     edx, 3Fh ; '?'; void *
0x18001e235  mov     r9d, eax; char *
0x18001e238  mov     rcx, [rbp+47h]; this
0x18001e23c  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001e243  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e248  jmp     loc_18001E6EB
0x18001e24d  mov     rcx, [rsp+110h+var_D0]
0x18001e252  mov     rax, [rcx]
0x18001e255  mov     rdx, r15
0x18001e258  mov     rax, [rax+38h]
0x18001e25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e261  mov     edi, eax
0x18001e263  xor     r15d, r15d
0x18001e266  test    eax, eax
0x18001e268  jns     short loc_18001E270
0x18001e26a  lea     edx, [r15+41h]
0x18001e26e  jmp     short loc_18001E235
0x18001e270  mov     rcx, [rsp+110h+var_D0]
0x18001e275  mov     rax, [rcx]
0x18001e278  mov     rdx, r12
0x18001e27b  mov     rax, [rax+48h]
0x18001e27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e284  mov     edi, eax
0x18001e286  test    eax, eax
0x18001e288  jns     short loc_18001E291
0x18001e28a  mov     edx, 42h ; 'B'
0x18001e28f  jmp     short loc_18001E235
0x18001e291  mov     rcx, [rbp+3Fh+var_A8]
0x18001e295  mov     rax, [rcx]
0x18001e298  mov     rdx, r13
0x18001e29b  mov     rax, [rax+40h]
0x18001e29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2a4  mov     edi, eax
0x18001e2a6  test    eax, eax
0x18001e2a8  jns     short loc_18001E2B1
0x18001e2aa  mov     edx, 43h ; 'C'
0x18001e2af  jmp     short loc_18001E235
0x18001e2b1  mov     [rbp+3Fh+var_B0], r15d
0x18001e2b5  lea     r8, [rbp+3Fh+var_B0]
0x18001e2b9  mov     edx, 0Ch
0x18001e2be  lea     rcx, aCdpCallAppServ; "CDP Call App Service"
0x18001e2c5  call    cs:__imp_CDPAcquireNetworkingInternal
0x18001e2cb  mov     [rbp+3Fh+var_B4], eax
0x18001e2ce  mov     r12d, 1
0x18001e2d4  test    eax, eax
0x18001e2d6  jns     short loc_18001E2EB
0x18001e2d8  lea     r8, [rbp+3Fh+var_B4]
0x18001e2dc  lea     rdx, aFailureAcquiri; "Failure acquiring networking. hr = 0x%0"...
0x18001e2e3  mov     ecx, r12d
0x18001e2e6  call    ??$Log@AEAJ@@YAXW4CDPLogLevel@@PEBDAEAJ@Z; Log<long &>(CDPLogLevel,char const *,long &)
0x18001e2eb  lea     rax, [rbp+3Fh+var_B4]
0x18001e2ef  mov     qword ptr [rbp+3Fh+hstringHeader.Reserved], rax
0x18001e2f3  lea     rax, [rbp+3Fh+var_B0]
0x18001e2f7  mov     qword ptr [rbp+3Fh+hstringHeader.Reserved+8], rax
0x18001e2fb  mov     word ptr [rbp+3Fh+hstringHeader.Reserved+10h], 102h
0x18001e301  mov     [rsp+110h+var_C8], r15
0x18001e306  test    rsi, rsi
0x18001e309  jz      short loc_18001E383
0x18001e30b  mov     [rsp+110h+var_E0], r15
0x18001e310  lea     r8, a0; ".0"
0x18001e317  lea     rdx, [rbp+3Fh+var_A0]
0x18001e31b  lea     rcx, [rsp+110h+var_E0]
0x18001e320  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@$$BY02G@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@AEBQEAUHSTRING__@@AEAY02$$CBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,HSTRING__ *,ushort [3]>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &,HSTRING__ * const &,ushort const (&)[3])
0x18001e325  mov     edi, eax
0x18001e327  test    eax, eax
0x18001e329  jns     short loc_18001E353
0x18001e32b  mov     edx, 61h ; 'a'; void *
0x18001e330  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001e337  mov     r9d, eax; char *
0x18001e33a  mov     rcx, [rbp+47h]; this
0x18001e33e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e343  nop
0x18001e344  lea     rcx, [rsp+110h+var_E0]; this
0x18001e349  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001e34e  jmp     loc_18001E6D6
0x18001e353  mov     rcx, [r14+20h]
0x18001e357  mov     rax, [rcx]
0x18001e35a  mov     rdx, [rsp+110h+var_E0]
0x18001e35f  mov     rax, [rax+40h]
0x18001e363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e368  mov     edi, eax
0x18001e36a  test    eax, eax
0x18001e36c  jns     short loc_18001E375
0x18001e36e  mov     edx, 62h ; 'b'
0x18001e373  jmp     short loc_18001E330
0x18001e375  lea     rcx, [rsp+110h+var_E0]; this
0x18001e37a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001e37f  mov     rsi, [rbp+3Fh+var_A0]
0x18001e383  lea     rdx, aOpeningAppServ; "Opening App Service connection..."
0x18001e38a  mov     r13d, 4
0x18001e390  mov     ecx, r13d
0x18001e393  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18001e398  mov     [rsp+110h+var_C0], r15
0x18001e39d  mov     rbx, [rsp+110h+var_D0]
0x18001e3a2  mov     rax, [rbx]
0x18001e3a5  mov     rdi, [rax]
0x18001e3a8  lea     rcx, [rsp+110h+var_C0]
0x18001e3ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e3b2  lea     r8, [rsp+110h+var_C0]
0x18001e3b7  lea     rdx, _GUID_7223c1d7_ab9b_46ab_9a82_1dac56158529
0x18001e3be  mov     rcx, rbx
0x18001e3c1  mov     rax, rdi
0x18001e3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3c9  mov     edi, eax
0x18001e3cb  test    eax, eax
0x18001e3cd  jns     short loc_18001E3EB
0x18001e3cf  mov     rcx, [rbp+47h]; this
0x18001e3d3  mov     r9d, eax; char *
0x18001e3d6  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001e3dd  lea     edx, [r13+64h]; void *
0x18001e3e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e3e6  jmp     loc_18001E6CB
0x18001e3eb  mov     [rsp+110h+var_D8], r15
0x18001e3f0  mov     rcx, [rsp+110h+var_C0]
0x18001e3f5  mov     rax, [rcx]
0x18001e3f8  lea     r8, [rsp+110h+var_D8]
0x18001e3fd  mov     edx, r12d
0x18001e400  mov     rax, [rax+30h]
0x18001e404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e409  mov     edi, eax
0x18001e40b  test    eax, eax
0x18001e40d  jns     short loc_18001E449
0x18001e40f  mov     rcx, [rbp+47h]; this
0x18001e413  mov     r9d, eax; char *
0x18001e416  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001e41d  mov     edx, 6Ch ; 'l'; void *
0x18001e422  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e427  nop
0x18001e428  mov     rcx, [rsp+110h+var_D8]
0x18001e42d  test    rcx, rcx
0x18001e430  jz      short loc_18001E444
0x18001e432  mov     [rsp+110h+var_D8], r15
0x18001e437  mov     rax, [rcx]
0x18001e43a  mov     rax, [rax+10h]
0x18001e43e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e443  nop
0x18001e444  jmp     loc_18001E6CB
0x18001e449  lea     rax, [rsp+110h+var_D0]
0x18001e44e  mov     [rbp+3Fh+var_98], rax
0x18001e452  mov     [rbp+3Fh+var_90], 102h
0x18001e458  mov     [rbp+3Fh+var_B8], r13d
0x18001e45c  mov     rbx, [rsp+110h+var_D8]
0x18001e461  mov     rcx, rbx
0x18001e464  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)
0x18001e469  mov     edi, eax
0x18001e46b  test    eax, eax
0x18001e46d  js      loc_18001E68C
0x18001e473  mov     rax, [rbx]
0x18001e476  lea     rdx, [rbp+3Fh+var_B8]
0x18001e47a  mov     rcx, rbx
0x18001e47d  mov     rax, [rax+40h]
0x18001e481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e486  mov     edi, eax
0x18001e488  test    eax, eax
0x18001e48a  js      loc_18001E68C
0x18001e490  mov     eax, [rbp+3Fh+var_B8]
0x18001e493  test    eax, eax
0x18001e495  jnz     loc_18001E5BB
0x18001e49b  lea     rdx, aSuccessfullyOp; "Successfully opened connection to App S"...
0x18001e4a2  mov     ecx, r13d
0x18001e4a5  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18001e4aa  test    rsi, rsi
0x18001e4ad  jz      loc_18001E596
0x18001e4b3  mov     [rsp+110h+var_E0], r15
0x18001e4b8  lea     r8, a1; ".1"
0x18001e4bf  lea     rdx, [rbp+3Fh+var_A0]
0x18001e4c3  lea     rcx, [rsp+110h+var_E0]
0x18001e4c8  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@$$BY02G@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@AEBQEAUHSTRING__@@AEAY02$$CBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,HSTRING__ *,ushort [3]>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &,HSTRING__ * const &,ushort const (&)[3])
0x18001e4cd  mov     edi, eax
0x18001e4cf  test    eax, eax
0x18001e4d1  jns     short loc_18001E522
0x18001e4d3  mov     rcx, [rbp+47h]; this
0x18001e4d7  mov     r9d, eax; char *
0x18001e4da  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001e4e1  mov     edx, 88h; void *
0x18001e4e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e4eb  nop
0x18001e4ec  lea     rcx, [rsp+110h+var_E0]; this
0x18001e4f1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001e4f6  nop
0x18001e4f7  lea     rcx, [rbp+3Fh+var_98]
0x18001e4fb  call    wil__details__ScopeExitFnGuard__lambda_da820c26f9e92d7bbd7d39f2b8f752f1_____operator__
0x18001e500  nop
0x18001e501  mov     rcx, [rsp+110h+var_D8]
0x18001e506  test    rcx, rcx
0x18001e509  jz      short loc_18001E51D
0x18001e50b  mov     [rsp+110h+var_D8], r15
0x18001e510  mov     rax, [rcx]
0x18001e513  mov     rax, [rax+10h]
0x18001e517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e51c  nop
0x18001e51d  jmp     loc_18001E6CB
0x18001e522  mov     rcx, [r14+20h]
0x18001e526  mov     rax, [rcx]
0x18001e529  mov     rdx, [rsp+110h+var_E0]
0x18001e52e  mov     rax, [rax+40h]
0x18001e532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e537  mov     edi, eax
0x18001e539  test    eax, eax
0x18001e53b  jns     short loc_18001E58C
0x18001e53d  mov     rcx, [rbp+47h]; this
0x18001e541  mov     r9d, eax; char *
0x18001e544  lea     r8, aAppservicehelp; "..\\appservicehelper.cpp"
0x18001e54b  mov     edx, 89h; void *
0x18001e550  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e555  nop
0x18001e556  lea     rcx, [rsp+110h+var_E0]; this
0x18001e55b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001e560  nop
0x18001e561  lea     rcx, [rbp+3Fh+var_98]
0x18001e565  call    wil__details__ScopeExitFnGuard__lambda_da820c26f9e92d7bbd7d39f2b8f752f1_____operator__
0x18001e56a  nop
0x18001e56b  mov     rcx, [rsp+110h+var_D8]
0x18001e570  test    rcx, rcx
0x18001e573  jz      short loc_18001E587
0x18001e575  mov     [rsp+110h+var_D8], r15
  ... truncated ...
```
