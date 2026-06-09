# Microsoft::Windows::Autopilot::DeviceTicketRequest::ExtractEndpointsFromWebResult(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *,bool &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18017e710`
- end: `0x18017edbf`
- name: `?ExtractEndpointsFromWebResult@DeviceTicketRequest@Autopilot@Windows@Microsoft@@AEAAJPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@3@AEA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@2@Z`
- size: `1711`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18017e5b8`

## callees

- `0x180067008`
- `0x180067a54`
- `0x18008a014`
- `0x1800f810c`
- `0x18017e710`
- `0x18017edc8`
- `0x18017f0cc`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18017eaba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18017eaba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017eaaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017eafe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017ec42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017ec5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017eaaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017eafe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017ec42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017ec5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017ea81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017ead5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017ea81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017ead5`

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
0x18017e710  mov     [rsp-38h+arg_0], rcx
0x18017e715  push    rbp
0x18017e716  push    rbx
0x18017e717  push    rsi
0x18017e718  push    rdi
0x18017e719  push    r12
0x18017e71b  push    r14
0x18017e71d  push    r15
0x18017e71f  mov     rbp, rsp
0x18017e722  sub     rsp, 80h
0x18017e729  mov     r14, r9
0x18017e72c  mov     r15, r8
0x18017e72f  mov     rdi, rdx
0x18017e732  xor     r12d, r12d
0x18017e735  mov     [r8], r12b
0x18017e738  mov     [rbp+arg_8], r12d
0x18017e73c  mov     rax, [rdx]
0x18017e73f  lea     rdx, [rbp+arg_8]
0x18017e743  mov     rcx, rdi
0x18017e746  mov     rax, [rax+38h]
0x18017e74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e74f  mov     ebx, eax
0x18017e751  test    eax, eax
0x18017e753  jns     short loc_18017E77E
0x18017e755  mov     rcx, [rbp+38h]; this
0x18017e759  lea     rax, aFailedToGetRes; "Failed to get response status from web "...
0x18017e760  mov     qword ptr [rsp+80h+var_60], rax; int
0x18017e765  mov     r9d, ebx; char *
0x18017e768  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017e76f  mov     edx, 0FCh; void *
0x18017e774  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18017e779  jmp     loc_18017EBA7
0x18017e77e  mov     r8d, [rbp+arg_8]
0x18017e782  test    r8d, r8d
0x18017e785  jz      short loc_18017E794
0x18017e787  mov     rdx, rdi
0x18017e78a  call    ?ExtractFailureFromWebResult@DeviceTicketRequest@Autopilot@Windows@Microsoft@@AEAAJPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@3@W4WebTokenRequestStatus@67893@@Z; Microsoft::Windows::Autopilot::DeviceTicketRequest::ExtractFailureFromWebResult(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus)
0x18017e78f  jmp     loc_18017EBA9
0x18017e794  mov     [rbp+var_10], r12
0x18017e798  mov     rax, [rdi]
0x18017e79b  mov     rbx, [rax+30h]
0x18017e79f  lea     rcx, [rbp+var_10]
0x18017e7a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e7a8  lea     rdx, [rbp+var_10]
0x18017e7ac  mov     rcx, rdi
0x18017e7af  mov     rax, rbx
0x18017e7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e7b7  mov     ebx, eax
0x18017e7b9  test    eax, eax
0x18017e7bb  jns     short loc_18017E7C4
0x18017e7bd  mov     edx, 104h
0x18017e7c2  jmp     short loc_18017E7E7
0x18017e7c4  mov     [rbp+var_8], r12d
0x18017e7c8  mov     rcx, [rbp+var_10]
0x18017e7cc  mov     rax, [rcx]
0x18017e7cf  lea     rdx, [rbp+var_8]
0x18017e7d3  mov     rax, [rax+38h]
0x18017e7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e7dc  mov     ebx, eax
0x18017e7de  test    eax, eax
0x18017e7e0  jns     short loc_18017E7FF
0x18017e7e2  mov     edx, 107h; void *
0x18017e7e7  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017e7ee  mov     r9d, eax; char *
0x18017e7f1  mov     rcx, [rbp+38h]; this
0x18017e7f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017e7fa  jmp     loc_18017EB9E
0x18017e7ff  mov     [rbp+var_40], r12
0x18017e803  mov     rdi, [rbp+var_10]
0x18017e807  mov     rax, [rdi]
0x18017e80a  mov     rbx, [rax+30h]
0x18017e80e  lea     rcx, [rbp+var_40]
0x18017e812  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e817  lea     r8, [rbp+var_40]
0x18017e81b  xor     edx, edx
0x18017e81d  mov     rcx, rdi
0x18017e820  mov     rax, rbx
0x18017e823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e828  mov     ebx, eax
0x18017e82a  test    eax, eax
0x18017e82c  jns     short loc_18017E855
0x18017e82e  mov     rcx, [rbp+38h]; this
0x18017e832  mov     r9d, eax; char *
0x18017e835  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017e83c  mov     edx, 10Ah; void *
0x18017e841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017e846  nop
0x18017e847  lea     rcx, [rbp+var_40]
0x18017e84b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e850  jmp     loc_18017EB9E
0x18017e855  mov     [rbp+var_48], r12
0x18017e859  mov     rdi, [rbp+var_40]
0x18017e85d  mov     rax, [rdi]
0x18017e860  mov     rbx, [rax+48h]
0x18017e864  lea     rcx, [rbp+var_48]
0x18017e868  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e86d  lea     rdx, [rbp+var_48]
0x18017e871  mov     rcx, rdi
0x18017e874  mov     rax, rbx
0x18017e877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e87c  mov     ebx, eax
0x18017e87e  test    eax, eax
0x18017e880  jns     short loc_18017E8A6
0x18017e882  mov     edx, 10Fh; void *
0x18017e887  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017e88e  mov     r9d, eax; char *
0x18017e891  mov     rcx, [rbp+38h]; this
0x18017e895  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017e89a  nop
0x18017e89b  lea     rcx, [rbp+var_48]
0x18017e89f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e8a4  jmp     short loc_18017E847
0x18017e8a6  mov     [rbp+arg_10], r12d
0x18017e8aa  mov     rcx, [rbp+var_48]
0x18017e8ae  mov     rax, [rcx]
0x18017e8b1  lea     rdx, [rbp+arg_10]
0x18017e8b5  mov     rax, [rax+38h]
0x18017e8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e8be  mov     ebx, eax
0x18017e8c0  test    eax, eax
0x18017e8c2  jns     short loc_18017E8CB
0x18017e8c4  mov     edx, 112h
0x18017e8c9  jmp     short loc_18017E887
0x18017e8cb  cmp     [rbp+arg_10], r12d
0x18017e8cf  jbe     loc_18017EB88
0x18017e8d5  mov     [rbp+var_50], r12
0x18017e8d9  mov     rcx, [rbp+var_48]
0x18017e8dd  mov     rax, [rcx]
0x18017e8e0  lea     rdx, [rbp+var_50]
0x18017e8e4  mov     rax, [rax+48h]
0x18017e8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e8ed  mov     ebx, eax
0x18017e8ef  test    eax, eax
0x18017e8f1  jns     short loc_18017E92B
0x18017e8f3  mov     rcx, [rbp+38h]; this
0x18017e8f7  mov     r9d, eax; char *
0x18017e8fa  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017e901  mov     edx, 116h; void *
0x18017e906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017e90b  nop
0x18017e90c  mov     rcx, [rbp+var_50]
0x18017e910  test    rcx, rcx
0x18017e913  jz      short loc_18017E926
0x18017e915  mov     [rbp+var_50], r12
0x18017e919  mov     rax, [rcx]
0x18017e91c  mov     rax, [rax+10h]
0x18017e920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e925  nop
0x18017e926  jmp     loc_18017E89B
0x18017e92b  mov     [rbp+var_28], r12
0x18017e92f  mov     rbx, [rbp+var_50]
0x18017e933  mov     rax, [rbx]
0x18017e936  mov     rdi, [rax]
0x18017e939  lea     rcx, [rbp+var_28]
0x18017e93d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e942  lea     r8, [rbp+var_28]
0x18017e946  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x18017e94d  mov     rcx, rbx
0x18017e950  mov     rax, rdi
0x18017e953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e958  mov     ebx, eax
0x18017e95a  test    eax, eax
0x18017e95c  jns     short loc_18017E9A0
0x18017e95e  mov     rcx, [rbp+38h]; this
0x18017e962  mov     r9d, eax; char *
0x18017e965  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017e96c  mov     edx, 119h; void *
0x18017e971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017e976  nop
0x18017e977  lea     rcx, [rbp+var_28]
0x18017e97b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e980  nop
0x18017e981  mov     rcx, [rbp+var_50]
0x18017e985  test    rcx, rcx
0x18017e988  jz      short loc_18017E99B
0x18017e98a  mov     [rbp+var_50], r12
0x18017e98e  mov     rax, [rcx]
0x18017e991  mov     rax, [rax+10h]
0x18017e995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e99a  nop
0x18017e99b  jmp     loc_18017E89B
0x18017e9a0  mov     [rbp+var_38], r12
0x18017e9a4  mov     rdi, [rbp+var_28]
0x18017e9a8  mov     rax, [rdi]
0x18017e9ab  mov     rbx, [rax+30h]
0x18017e9af  lea     rcx, [rbp+var_38]
0x18017e9b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e9b8  lea     rdx, [rbp+var_38]
0x18017e9bc  mov     rcx, rdi
0x18017e9bf  mov     rax, rbx
0x18017e9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e9c7  mov     ebx, eax
0x18017e9c9  test    eax, eax
0x18017e9cb  jns     short loc_18017EA19
0x18017e9cd  mov     rcx, [rbp+38h]; this
0x18017e9d1  mov     r9d, eax; char *
0x18017e9d4  lea     r8, aOnecoreuapAdmi_118; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017e9db  mov     edx, 11Ch; void *
0x18017e9e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017e9e5  nop
0x18017e9e6  lea     rcx, [rbp+var_38]
0x18017e9ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e9ef  nop
0x18017e9f0  lea     rcx, [rbp+var_28]
0x18017e9f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e9f9  nop
0x18017e9fa  mov     rcx, [rbp+var_50]
0x18017e9fe  test    rcx, rcx
0x18017ea01  jz      short loc_18017EA14
0x18017ea03  mov     [rbp+var_50], r12
0x18017ea07  mov     rax, [rcx]
0x18017ea0a  mov     rax, [rax+10h]
0x18017ea0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ea13  nop
0x18017ea14  jmp     loc_18017E89B
0x18017ea19  mov     byte ptr [rbp+arg_0], r12b
0x18017ea1d  mov     rcx, [rbp+var_38]
0x18017ea21  mov     rax, [rcx]
0x18017ea24  lea     rdx, [rbp+arg_0]
0x18017ea28  mov     rax, [rax+38h]
0x18017ea2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ea31  cmp     byte ptr [rbp+arg_0], r12b
0x18017ea35  jz      loc_18017EB5A
0x18017ea3b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18017ea3f  mov     [rbp+var_30], r12
0x18017ea43  mov     rdi, [rbp+var_38]
0x18017ea47  mov     rax, [rdi]
0x18017ea4a  mov     rbx, [rax+30h]
0x18017ea4e  lea     rcx, [rbp+var_30]
0x18017ea52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017ea57  lea     rdx, [rbp+var_30]
0x18017ea5b  mov     rcx, rdi
0x18017ea5e  mov     rax, rbx
0x18017ea61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ea66  mov     ebx, eax
0x18017ea68  test    eax, eax
0x18017ea6a  js      loc_18017ED68
0x18017ea70  mov     [rbp+string], r12
0x18017ea74  mov     rdi, [rbp+var_30]
0x18017ea78  mov     rax, [rdi]
0x18017ea7b  mov     rbx, [rax+30h]
0x18017ea7f  xor     ecx, ecx; string
0x18017ea81  call    cs:__imp_WindowsDeleteString
0x18017ea87  mov     [rbp+string], r12
0x18017ea8b  lea     rdx, [rbp+string]
0x18017ea8f  mov     rcx, rdi
0x18017ea92  mov     rax, rbx
0x18017ea95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ea9a  mov     ebx, eax
0x18017ea9c  test    eax, eax
0x18017ea9e  js      loc_18017ED08
0x18017eaa4  xor     edx, edx; length
0x18017eaa6  mov     rcx, [rbp+string]; string
0x18017eaaa  call    cs:__imp_WindowsGetStringRawBuffer
0x18017eab0  lea     rdx, aMdmEnrollmentU; "mdm_enrollment_url"
0x18017eab7  mov     rcx, rax
0x18017eaba  call    cs:__imp__o__wcsicmp
0x18017eac0  test    eax, eax
0x18017eac2  jnz     short loc_18017EB29
0x18017eac4  mov     [rbp+var_18], r12
0x18017eac8  mov     rdi, [rbp+var_30]
0x18017eacc  mov     rax, [rdi]
0x18017eacf  mov     rbx, [rax+38h]
0x18017ead3  xor     ecx, ecx; string
0x18017ead5  call    cs:__imp_WindowsDeleteString
0x18017eadb  mov     [rbp+var_18], r12
0x18017eadf  lea     rdx, [rbp+var_18]
0x18017eae3  mov     rcx, rdi
0x18017eae6  mov     rax, rbx
0x18017eae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017eaee  mov     ebx, eax
0x18017eaf0  test    eax, eax
0x18017eaf2  js      loc_18017EC9E
0x18017eaf8  xor     edx, edx; length
0x18017eafa  mov     rcx, [rbp+var_18]; string
0x18017eafe  call    cs:__imp_WindowsGetStringRawBuffer
0x18017eb04  test    rax, rax
0x18017eb07  jz      short loc_18017EB1F
0x18017eb09  mov     rcx, rsi
0x18017eb0c  inc     rcx
0x18017eb0f  cmp     [rax+rcx*2], r12w
0x18017eb14  jnz     short loc_18017EB0C
0x18017eb16  test    rcx, rcx
0x18017eb19  jnz     loc_18017EBBB
0x18017eb1f  lea     rcx, [rbp+var_18]; this
0x18017eb23  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18017eb28  nop
0x18017eb29  lea     rcx, [rbp+string]; this
0x18017eb2d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18017eb32  nop
0x18017eb33  lea     rcx, [rbp+var_30]
0x18017eb37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017eb3c  mov     rcx, [rbp+var_38]
0x18017eb40  mov     rax, [rcx]
0x18017eb43  lea     rdx, [rbp+arg_0]
0x18017eb47  mov     rax, [rax+40h]
0x18017eb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017eb50  cmp     byte ptr [rbp+arg_0], r12b
0x18017eb54  jnz     loc_18017EA3F
0x18017eb5a  lea     rcx, [rbp+var_38]
  ... truncated ...
```
