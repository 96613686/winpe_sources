# Microsoft::Windows::Autopilot::DeviceTicketRequest::ExtractEndpointsFromWebResult(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *,bool &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18018303c`
- end: `0x180183716`
- name: `?ExtractEndpointsFromWebResult@DeviceTicketRequest@Autopilot@Windows@Microsoft@@AEAAJPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@3@AEA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@2@Z`
- size: `1754`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180182ee4`

## callees

- `0x180067398`
- `0x180067e54`
- `0x18008aecc`
- `0x1800fb080`
- `0x18018303c`
- `0x18018371c`
- `0x180183aa4`
- `0x180200010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801833f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801833f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801833dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180183442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18018358d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801835b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801833dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180183442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18018358d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801835b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801833ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180183413`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801833ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180183413`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Microsoft::Windows::Autopilot::DeviceTicketRequest::ExtractEndpointsFromWebResult(
        __int64 a1,
        __int64 a2,
        char *a3,
        HSTRING *a4,
        HSTRING *a5)
{
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64 *); // rdi
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 *); // rbx
  int v29; // eax
  __int64 (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v31; // rsi
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, __int64 *); // rbx
  int v34; // eax
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, HSTRING *); // rbx
  int v37; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, HSTRING *); // rbx
  int v41; // eax
  PCWSTR v42; // rax
  __int64 v43; // rcx
  __int64 (__fastcall ***v44)(_QWORD, _QWORD, _QWORD); // rcx
  HSTRING *v45; // rdi
  int v46; // eax
  __int64 (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rcx
  PCWSTR v48; // rax
  __int64 v49; // rdx
  PCWSTR v50; // rax
  char v51; // al
  __int64 (__fastcall ***v52)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v53)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v54)(_QWORD, _QWORD, _QWORD); // rcx
  int v55; // [rsp+20h] [rbp-60h]
  const char *v56; // [rsp+28h] [rbp-58h]
  __int64 (__fastcall ***v57)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-50h] BYREF
  __int64 v58; // [rsp+38h] [rbp-48h] BYREF
  __int64 v59; // [rsp+40h] [rbp-40h] BYREF
  __int64 v60; // [rsp+48h] [rbp-38h] BYREF
  __int64 v61; // [rsp+50h] [rbp-30h] BYREF
  __int64 v62; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-20h] BYREF
  HSTRING v64; // [rsp+68h] [rbp-18h] BYREF
  __int64 v65; // [rsp+70h] [rbp-10h] BYREF
  int v66; // [rsp+78h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  __int64 v68; // [rsp+C0h] [rbp+40h] BYREF
  int v69; // [rsp+C8h] [rbp+48h] BYREF
  int v70; // [rsp+D0h] [rbp+50h] BYREF

  v68 = a1;
  *a3 = 0;
  v69 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 56LL))(a2, &v69);
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
      (const char *)v9,
      (int)"Failed to get response status from web request",
      v56);
    return v9;
  }
  if ( v69 )
    return Microsoft::Windows::Autopilot::DeviceTicketRequest::ExtractFailureFromWebResult(v8, a2);
  v65 = 0;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  v12 = v11(a2, &v65);
  v9 = v12;
  if ( v12 < 0 )
  {
    v13 = 260;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
      (const char *)(unsigned int)v12,
      v55);
    goto LABEL_47;
  }
  v66 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v65 + 56LL))(v65, &v66);
  v9 = v12;
  if ( v12 < 0 )
  {
    v13 = 263;
    goto LABEL_9;
  }
  v59 = 0;
  v14 = v65;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v65 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  v16 = v15(v14, 0, &v59);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
      (const char *)(unsigned int)v16,
      v55);
LABEL_12:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    goto LABEL_47;
  }
  v58 = 0;
  v17 = v59;
  v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  v19 = v18(v17, &v58);
  v9 = v19;
  if ( v19 < 0 )
  {
    v20 = 271;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
      (const char *)(unsigned int)v19,
      v55);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    goto LABEL_12;
  }
  v70 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v58 + 56LL))(v58, &v70);
  v9 = v19;
  if ( v19 < 0 )
  {
    v20 = 274;
    goto LABEL_15;
  }
  if ( !v70 )
    goto LABEL_46;
  v57 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v58 + 72LL))(
          v58,
          &v57);
  v9 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
      (const char *)(unsigned int)v21,
      v55);
    v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
    if ( v57 )
    {
      v57 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v22)[2])(v22);
    }
    goto LABEL_16;
  }
  v62 = 0;
  v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
  v24 = **v57;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  v25 = v24(v23, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v62);
  v9 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
      (const char *)(unsigned int)v25,
      v55);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
    if ( v57 )
    {
      v57 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v26)[2])(v26);
    }
    goto LABEL_16;
  }
  v60 = 0;
  v27 = v62;
  v28 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  v29 = v28(v27, &v60);
  v9 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
      (const char *)(unsigned int)v29,
      v55);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v30 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
    if ( v57 )
    {
      v57 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v30)[2])(v30);
    }
    goto LABEL_16;
  }
  LOBYTE(v68) = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 56LL))(v60, &v68);
  if ( !(_BYTE)v68 )
    goto LABEL_44;
  v31 = -1;
  while ( 1 )
  {
    v61 = 0;
    v32 = v60;
    v33 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    v34 = v33(v32, &v61);
    v9 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x122,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
        (const char *)(unsigned int)v34,
        v55);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
      v54 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
      if ( v57 )
      {
        v57 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v54)[2])(v54);
      }
      goto LABEL_16;
    }
    string = 0;
    v35 = v61;
    v36 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v61 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v37 = v36(v35, &string);
    v9 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
        (const char *)(unsigned int)v37,
        v55);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
      v53 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
      if ( v57 )
      {
        v57 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v53)[2])(v53);
      }
      goto LABEL_16;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !(unsigned int)_o__wcsicmp(StringRawBuffer, L"mdm_enrollment_url") )
      break;
LABEL_43:
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 64LL))(v60, &v68);
    if ( !(_BYTE)v68 )
      goto LABEL_44;
  }
  v64 = 0;
  v39 = v61;
  v40 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v61 + 56LL);
  WindowsDeleteString(0);
  v64 = 0;
  v41 = v40(v39, &v64);
  v9 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
      (const char *)(unsigned int)v41,
      v55);
    Windows::Internal::String::~String((Windows::Internal::String *)&v64);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v52 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
    if ( v57 )
    {
      v57 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v52)[2])(v52);
    }
    goto LABEL_16;
  }
  v42 = WindowsGetStringRawBuffer(v64, 0);
  if ( !v42 )
    goto LABEL_42;
  v43 = -1;
  do
    ++v43;
  while ( v42[v43] );
  if ( !v43 )
  {
LABEL_42:
    Windows::Internal::String::~String((Windows::Internal::String *)&v64);
    goto LABEL_43;
  }
  v45 = a5;
  v46 = Microsoft::Windows::Autopilot::DeviceTicketRequest::PopulateEndpointDataFromMdmEnrollmentUri(v43, v42, a4, a5);
  v9 = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\deviceticketrequest.cpp",
      (const char *)(unsigned int)v46,
      v55);
    Windows::Internal::String::~String((Windows::Internal::String *)&v64);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v47 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
    if ( v57 )
    {
      v57 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v47)[2])(v47);
    }
    goto LABEL_16;
  }
  v48 = WindowsGetStringRawBuffer(*a4, 0);
  v49 = -1;
  do
    ++v49;
  while ( v48[v49] );
  if ( !v49 )
    goto LABEL_59;
  v50 = WindowsGetStringRawBuffer(*v45, 0);
  do
    ++v31;
  while ( v50[v31] );
  v51 = 1;
  if ( !v31 )
LABEL_59:
    v51 = 0;
  *a3 = v51;
  Windows::Internal::String::~String((Windows::Internal::String *)&v64);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
LABEL_44:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  v44 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
  if ( v57 )
  {
    v57 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v44)[2])(v44);
  }
LABEL_46:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  v9 = 0;
LABEL_47:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  return v9;
}

```

## disassembly

```asm
0x18018303c  mov     [rsp-38h+arg_0], rcx
0x180183041  push    rbp
0x180183042  push    rbx
0x180183043  push    rsi
0x180183044  push    rdi
0x180183045  push    r12
0x180183047  push    r14
0x180183049  push    r15
0x18018304b  mov     rbp, rsp
0x18018304e  sub     rsp, 80h
0x180183055  mov     r14, r9
0x180183058  mov     r15, r8
0x18018305b  mov     rdi, rdx
0x18018305e  xor     r12d, r12d
0x180183061  mov     [r8], r12b
0x180183064  mov     [rbp+arg_8], r12d
0x180183068  mov     rax, [rdx]
0x18018306b  lea     rdx, [rbp+arg_8]
0x18018306f  mov     rcx, rdi
0x180183072  mov     rax, [rax+38h]
0x180183076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018307b  mov     ebx, eax
0x18018307d  test    eax, eax
0x18018307f  jns     short loc_1801830AA
0x180183081  mov     rcx, [rbp+38h]; this
0x180183085  lea     rax, aFailedToGetRes; "Failed to get response status from web "...
0x18018308c  mov     qword ptr [rsp+80h+var_60], rax; int
0x180183091  mov     r9d, ebx; char *
0x180183094  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018309b  mov     edx, 0FCh; void *
0x1801830a0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801830a5  jmp     loc_1801834F1
0x1801830aa  mov     r8d, [rbp+arg_8]
0x1801830ae  test    r8d, r8d
0x1801830b1  jz      short loc_1801830C0
0x1801830b3  mov     rdx, rdi
0x1801830b6  call    ?ExtractFailureFromWebResult@DeviceTicketRequest@Autopilot@Windows@Microsoft@@AEAAJPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@3@W4WebTokenRequestStatus@67893@@Z; Microsoft::Windows::Autopilot::DeviceTicketRequest::ExtractFailureFromWebResult(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus)
0x1801830bb  jmp     loc_1801834F3
0x1801830c0  mov     [rbp+var_10], r12
0x1801830c4  mov     rax, [rdi]
0x1801830c7  mov     rbx, [rax+30h]
0x1801830cb  lea     rcx, [rbp+var_10]
0x1801830cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801830d4  lea     rdx, [rbp+var_10]
0x1801830d8  mov     rcx, rdi
0x1801830db  mov     rax, rbx
0x1801830de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801830e3  mov     ebx, eax
0x1801830e5  test    eax, eax
0x1801830e7  jns     short loc_1801830F0
0x1801830e9  mov     edx, 104h
0x1801830ee  jmp     short loc_180183113
0x1801830f0  mov     [rbp+var_8], r12d
0x1801830f4  mov     rcx, [rbp+var_10]
0x1801830f8  mov     rax, [rcx]
0x1801830fb  lea     rdx, [rbp+var_8]
0x1801830ff  mov     rax, [rax+38h]
0x180183103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183108  mov     ebx, eax
0x18018310a  test    eax, eax
0x18018310c  jns     short loc_18018312B
0x18018310e  mov     edx, 107h; void *
0x180183113  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018311a  mov     r9d, eax; char *
0x18018311d  mov     rcx, [rbp+38h]; this
0x180183121  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180183126  jmp     loc_1801834E8
0x18018312b  mov     [rbp+var_40], r12
0x18018312f  mov     rdi, [rbp+var_10]
0x180183133  mov     rax, [rdi]
0x180183136  mov     rbx, [rax+30h]
0x18018313a  lea     rcx, [rbp+var_40]
0x18018313e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180183143  lea     r8, [rbp+var_40]
0x180183147  xor     edx, edx
0x180183149  mov     rcx, rdi
0x18018314c  mov     rax, rbx
0x18018314f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183154  mov     ebx, eax
0x180183156  test    eax, eax
0x180183158  jns     short loc_180183181
0x18018315a  mov     rcx, [rbp+38h]; this
0x18018315e  mov     r9d, eax; char *
0x180183161  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x180183168  mov     edx, 10Ah; void *
0x18018316d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180183172  nop
0x180183173  lea     rcx, [rbp+var_40]
0x180183177  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018317c  jmp     loc_1801834E8
0x180183181  mov     [rbp+var_48], r12
0x180183185  mov     rdi, [rbp+var_40]
0x180183189  mov     rax, [rdi]
0x18018318c  mov     rbx, [rax+48h]
0x180183190  lea     rcx, [rbp+var_48]
0x180183194  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180183199  lea     rdx, [rbp+var_48]
0x18018319d  mov     rcx, rdi
0x1801831a0  mov     rax, rbx
0x1801831a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801831a8  mov     ebx, eax
0x1801831aa  test    eax, eax
0x1801831ac  jns     short loc_1801831D2
0x1801831ae  mov     edx, 10Fh; void *
0x1801831b3  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801831ba  mov     r9d, eax; char *
0x1801831bd  mov     rcx, [rbp+38h]; this
0x1801831c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801831c6  nop
0x1801831c7  lea     rcx, [rbp+var_48]
0x1801831cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801831d0  jmp     short loc_180183173
0x1801831d2  mov     [rbp+arg_10], r12d
0x1801831d6  mov     rcx, [rbp+var_48]
0x1801831da  mov     rax, [rcx]
0x1801831dd  lea     rdx, [rbp+arg_10]
0x1801831e1  mov     rax, [rax+38h]
0x1801831e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801831ea  mov     ebx, eax
0x1801831ec  test    eax, eax
0x1801831ee  jns     short loc_1801831F7
0x1801831f0  mov     edx, 112h
0x1801831f5  jmp     short loc_1801831B3
0x1801831f7  cmp     [rbp+arg_10], r12d
0x1801831fb  jbe     loc_1801834D2
0x180183201  mov     [rbp+var_50], r12
0x180183205  mov     rcx, [rbp+var_48]
0x180183209  mov     rax, [rcx]
0x18018320c  lea     rdx, [rbp+var_50]
0x180183210  mov     rax, [rax+48h]
0x180183214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183219  mov     ebx, eax
0x18018321b  test    eax, eax
0x18018321d  jns     short loc_180183257
0x18018321f  mov     rcx, [rbp+38h]; this
0x180183223  mov     r9d, eax; char *
0x180183226  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018322d  mov     edx, 116h; void *
0x180183232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180183237  nop
0x180183238  mov     rcx, [rbp+var_50]
0x18018323c  test    rcx, rcx
0x18018323f  jz      short loc_180183252
0x180183241  mov     [rbp+var_50], r12
0x180183245  mov     rax, [rcx]
0x180183248  mov     rax, [rax+10h]
0x18018324c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183251  nop
0x180183252  jmp     loc_1801831C7
0x180183257  mov     [rbp+var_28], r12
0x18018325b  mov     rbx, [rbp+var_50]
0x18018325f  mov     rax, [rbx]
0x180183262  mov     rdi, [rax]
0x180183265  lea     rcx, [rbp+var_28]
0x180183269  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018326e  lea     r8, [rbp+var_28]
0x180183272  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x180183279  mov     rcx, rbx
0x18018327c  mov     rax, rdi
0x18018327f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183284  mov     ebx, eax
0x180183286  test    eax, eax
0x180183288  jns     short loc_1801832CC
0x18018328a  mov     rcx, [rbp+38h]; this
0x18018328e  mov     r9d, eax; char *
0x180183291  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x180183298  mov     edx, 119h; void *
0x18018329d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801832a2  nop
0x1801832a3  lea     rcx, [rbp+var_28]
0x1801832a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801832ac  nop
0x1801832ad  mov     rcx, [rbp+var_50]
0x1801832b1  test    rcx, rcx
0x1801832b4  jz      short loc_1801832C7
0x1801832b6  mov     [rbp+var_50], r12
0x1801832ba  mov     rax, [rcx]
0x1801832bd  mov     rax, [rax+10h]
0x1801832c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801832c6  nop
0x1801832c7  jmp     loc_1801831C7
0x1801832cc  mov     [rbp+var_38], r12
0x1801832d0  mov     rdi, [rbp+var_28]
0x1801832d4  mov     rax, [rdi]
0x1801832d7  mov     rbx, [rax+30h]
0x1801832db  lea     rcx, [rbp+var_38]
0x1801832df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801832e4  lea     rdx, [rbp+var_38]
0x1801832e8  mov     rcx, rdi
0x1801832eb  mov     rax, rbx
0x1801832ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801832f3  mov     ebx, eax
0x1801832f5  test    eax, eax
0x1801832f7  jns     short loc_180183345
0x1801832f9  mov     rcx, [rbp+38h]; this
0x1801832fd  mov     r9d, eax; char *
0x180183300  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x180183307  mov     edx, 11Ch; void *
0x18018330c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180183311  nop
0x180183312  lea     rcx, [rbp+var_38]
0x180183316  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018331b  nop
0x18018331c  lea     rcx, [rbp+var_28]
0x180183320  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180183325  nop
0x180183326  mov     rcx, [rbp+var_50]
0x18018332a  test    rcx, rcx
0x18018332d  jz      short loc_180183340
0x18018332f  mov     [rbp+var_50], r12
0x180183333  mov     rax, [rcx]
0x180183336  mov     rax, [rax+10h]
0x18018333a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018333f  nop
0x180183340  jmp     loc_1801831C7
0x180183345  mov     byte ptr [rbp+arg_0], r12b
0x180183349  mov     rcx, [rbp+var_38]
0x18018334d  mov     rax, [rcx]
0x180183350  lea     rdx, [rbp+arg_0]
0x180183354  mov     rax, [rax+38h]
0x180183358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018335d  cmp     byte ptr [rbp+arg_0], r12b
0x180183361  jz      loc_1801834A4
0x180183367  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18018336b  mov     [rbp+var_30], r12
0x18018336f  mov     rdi, [rbp+var_38]
0x180183373  mov     rax, [rdi]
0x180183376  mov     rbx, [rax+30h]
0x18018337a  lea     rcx, [rbp+var_30]
0x18018337e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180183383  lea     rdx, [rbp+var_30]
0x180183387  mov     rcx, rdi
0x18018338a  mov     rax, rbx
0x18018338d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183392  mov     ebx, eax
0x180183394  test    eax, eax
0x180183396  js      loc_1801836BF
0x18018339c  mov     [rbp+string], r12
0x1801833a0  mov     rdi, [rbp+var_30]
0x1801833a4  mov     rax, [rdi]
0x1801833a7  mov     rbx, [rax+30h]
0x1801833ab  xor     ecx, ecx; string
0x1801833ad  call    cs:__imp_WindowsDeleteString
0x1801833b4  nop     dword ptr [rax+rax+00h]
0x1801833b9  mov     [rbp+string], r12
0x1801833bd  lea     rdx, [rbp+string]
0x1801833c1  mov     rcx, rdi
0x1801833c4  mov     rax, rbx
0x1801833c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801833cc  mov     ebx, eax
0x1801833ce  test    eax, eax
0x1801833d0  js      loc_18018365F
0x1801833d6  xor     edx, edx; length
0x1801833d8  mov     rcx, [rbp+string]; string
0x1801833dc  call    cs:__imp_WindowsGetStringRawBuffer
0x1801833e3  nop     dword ptr [rax+rax+00h]
0x1801833e8  lea     rdx, aMdmEnrollmentU; "mdm_enrollment_url"
0x1801833ef  mov     rcx, rax
0x1801833f2  call    cs:__imp__o__wcsicmp
0x1801833f9  nop     dword ptr [rax+rax+00h]
0x1801833fe  test    eax, eax
0x180183400  jnz     short loc_180183473
0x180183402  mov     [rbp+var_18], r12
0x180183406  mov     rdi, [rbp+var_30]
0x18018340a  mov     rax, [rdi]
0x18018340d  mov     rbx, [rax+38h]
0x180183411  xor     ecx, ecx; string
0x180183413  call    cs:__imp_WindowsDeleteString
0x18018341a  nop     dword ptr [rax+rax+00h]
0x18018341f  mov     [rbp+var_18], r12
0x180183423  lea     rdx, [rbp+var_18]
0x180183427  mov     rcx, rdi
0x18018342a  mov     rax, rbx
0x18018342d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183432  mov     ebx, eax
0x180183434  test    eax, eax
0x180183436  js      loc_1801835F5
0x18018343c  xor     edx, edx; length
0x18018343e  mov     rcx, [rbp+var_18]; string
0x180183442  call    cs:__imp_WindowsGetStringRawBuffer
0x180183449  nop     dword ptr [rax+rax+00h]
0x18018344e  test    rax, rax
0x180183451  jz      short loc_180183469
0x180183453  mov     rcx, rsi
0x180183456  inc     rcx
0x180183459  cmp     [rax+rcx*2], r12w
0x18018345e  jnz     short loc_180183456
0x180183460  test    rcx, rcx
0x180183463  jnz     loc_180183506
0x180183469  lea     rcx, [rbp+var_18]; this
0x18018346d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180183472  nop
0x180183473  lea     rcx, [rbp+string]; this
0x180183477  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18018347c  nop
0x18018347d  lea     rcx, [rbp+var_30]
0x180183481  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180183486  mov     rcx, [rbp+var_38]
0x18018348a  mov     rax, [rcx]
0x18018348d  lea     rdx, [rbp+arg_0]
  ... truncated ...
```
