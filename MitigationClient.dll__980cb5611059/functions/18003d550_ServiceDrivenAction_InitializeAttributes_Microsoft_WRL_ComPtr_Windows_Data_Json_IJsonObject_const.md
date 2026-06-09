# ServiceDrivenAction::InitializeAttributes(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x18003d550`
- end: `0x18003da87`
- name: `?InitializeAttributes@ServiceDrivenAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `1335`
- prototype: `__int64 __fastcall(_DWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800373f8`
- `0x18003f790`

## callees

- `0x18000a6e0`
- `0x18001055c`
- `0x18001208c`
- `0x180017670`
- `0x180017cb4`
- `0x180019750`
- `0x1800240b8`
- `0x180024e70`
- `0x1800253bc`
- `0x180026930`
- `0x18003d550`
- `0x18003da90`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d85d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d85d`

## string_xrefs

- `0x18003d5f6`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenaction.cpp`
- `0x18003d688`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenaction.cpp`
- `0x18003d717`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenaction.cpp`
- `0x18003d787`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenaction.cpp`
- `0x18003d800`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenaction.cpp`
- `0x18003d883`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenaction.cpp`
- `0x18003d929`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenaction.cpp`
- `0x18003d9ad`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenaction.cpp`

## pseudocode

```c
__int64 __fastcall ServiceDrivenAction::InitializeAttributes(_DWORD *a1, __int64 *a2)
{
  __int64 v4; // rax
  int *v5; // r14
  double v6; // rsi
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, double *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // rdi
  unsigned __int64 v12; // rdx
  unsigned __int8 v13; // cl
  __int64 v14; // rcx
  MitigationTelemetryClass *v15; // rax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, double *); // rbx
  int v19; // eax
  const unsigned __int16 *v20; // rdi
  unsigned __int64 v21; // rdx
  unsigned __int8 v22; // cl
  __int64 v23; // rcx
  MitigationTelemetryClass *v24; // rax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, double *); // rbx
  int v27; // eax
  const unsigned __int16 *v28; // rdi
  unsigned __int64 v29; // rdx
  unsigned __int8 v30; // cl
  __int64 v31; // rcx
  MitigationTelemetryClass *v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdi
  unsigned __int64 v35; // rdx
  unsigned __int8 v36; // cl
  __int64 v37; // rcx
  MitigationTelemetryClass *v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rdi
  unsigned __int64 v41; // rdx
  unsigned __int8 v42; // cl
  __int64 v43; // rcx
  MitigationTelemetryClass *v44; // rax
  PCWSTR StringRawBuffer; // rax
  int v46; // eax
  const unsigned __int16 *v47; // rdi
  unsigned __int64 v48; // rdx
  unsigned __int8 v49; // cl
  __int64 v50; // rcx
  MitigationTelemetryClass *v51; // rax
  __int64 v52; // rdi
  __int64 (__fastcall *v53)(__int64, _QWORD, __int64 *); // rbx
  int v54; // eax
  const unsigned __int16 *v55; // rdi
  unsigned __int64 v56; // rdx
  unsigned __int8 v57; // cl
  __int64 v58; // rcx
  MitigationTelemetryClass *v59; // rax
  int v60; // eax
  const unsigned __int16 *v61; // rdi
  unsigned __int64 v62; // rdx
  unsigned __int8 v63; // cl
  __int64 v64; // rcx
  MitigationTelemetryClass *v65; // rax
  const unsigned __int16 *v66; // rbx
  unsigned __int64 v67; // rdx
  unsigned __int8 v68; // cl
  __int64 v69; // rcx
  MitigationTelemetryClass *v70; // rax
  int v71; // [rsp+28h] [rbp-69h] BYREF
  __int64 v72; // [rsp+30h] [rbp-61h] BYREF
  HSTRING string; // [rsp+38h] [rbp-59h] BYREF
  __int64 v74; // [rsp+40h] [rbp-51h] BYREF
  double v75; // [rsp+48h] [rbp-49h] BYREF
  double v76; // [rsp+50h] [rbp-41h] BYREF
  double v77[3]; // [rsp+58h] [rbp-39h] BYREF
  char v78; // [rsp+70h] [rbp-21h]
  _BYTE v79[16]; // [rsp+78h] [rbp-19h] BYREF
  _QWORD v80[4]; // [rsp+88h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v71 = 0;
  v4 = _lambda_e380becb44ad60157fc94fb792e326fc_::_lambda_e380becb44ad60157fc94fb792e326fc_(v79, &v71, a1);
  v5 = *(int **)v4;
  v77[1] = *(double *)v4;
  v6 = *(double *)(v4 + 8);
  v77[2] = v6;
  v78 = 1;
  v75 = 0.0;
  v7 = *a2;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)*a2 + 88LL);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v80,
    ServiceDrivenAction::s_actionIdTag);
  v9 = v8(v7, v80[0], &v75);
  v10 = v9;
  v71 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenaction.cpp",
      (const char *)(unsigned int)v9,
      v71);
    v11 = *(const unsigned __int16 **)(*(_QWORD *)&v6 + 32LL);
    if ( MitigationTelemetryClass::IsEnabled(v13, v12) )
    {
      v15 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                          v14,
                                          _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
      MitigationTelemetryClass::ServiceDrivenActionInitialize_(v15, *v5, *(_DWORD *)(*(_QWORD *)&v6 + 16LL), v11);
    }
    return v10;
  }
  a1[4] = (int)v75;
  v76 = 0.0;
  v17 = *a2;
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)*a2 + 88LL);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v80,
    ServiceDrivenAction::s_orderTag);
  v19 = v18(v17, v80[0], &v76);
  v10 = v19;
  v71 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenaction.cpp",
      (const char *)(unsigned int)v19,
      v71);
    v20 = *(const unsigned __int16 **)(*(_QWORD *)&v6 + 32LL);
    if ( MitigationTelemetryClass::IsEnabled(v22, v21) )
    {
      v24 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                          v23,
                                          _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
      MitigationTelemetryClass::ServiceDrivenActionInitialize_(v24, *v5, *(_DWORD *)(*(_QWORD *)&v6 + 16LL), v20);
    }
    return v10;
  }
  a1[5] = (int)v76;
  v77[0] = 0.0;
  v25 = *a2;
  v26 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)*a2 + 88LL);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v80,
    ServiceDrivenAction::s_onErrorTag);
  v27 = v26(v25, v80[0], v77);
  v10 = v27;
  v71 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenaction.cpp",
      (const char *)(unsigned int)v27,
      v71);
    v28 = *(const unsigned __int16 **)(*(_QWORD *)&v6 + 32LL);
    if ( MitigationTelemetryClass::IsEnabled(v30, v29) )
    {
      v32 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                          v31,
                                          _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
      MitigationTelemetryClass::ServiceDrivenActionInitialize_(v32, *v5, *(_DWORD *)(*(_QWORD *)&v6 + 16LL), v28);
    }
    return v10;
  }
  a1[6] = (int)v77[0];
  v72 = 0;
  v33 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(a2, &v72);
  v10 = v33;
  v71 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenaction.cpp",
      (const char *)(unsigned int)v33,
      v71);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
    v34 = *(const unsigned __int16 **)(*(_QWORD *)&v6 + 32LL);
    if ( MitigationTelemetryClass::IsEnabled(v36, v35) )
    {
      v38 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                          v37,
                                          _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
      MitigationTelemetryClass::ServiceDrivenActionInitialize_(v38, *v5, *(_DWORD *)(*(_QWORD *)&v6 + 16LL), v34);
    }
    return v10;
  }
  string = 0;
  v39 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v72 + 56LL))(v72, &string);
  v10 = v39;
  v71 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenaction.cpp",
      (const char *)(unsigned int)v39,
      v71);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
    v40 = *(const unsigned __int16 **)(*(_QWORD *)&v6 + 32LL);
    if ( MitigationTelemetryClass::IsEnabled(v42, v41) )
    {
      v44 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                          v43,
                                          _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
      MitigationTelemetryClass::ServiceDrivenActionInitialize_(v44, *v5, *(_DWORD *)(*(_QWORD *)&v6 + 16LL), v40);
    }
    return v10;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v46 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          a1 + 8,
          StringRawBuffer,
          -1);
  v10 = v46;
  v71 = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenaction.cpp",
      (const char *)(unsigned int)v46,
      v71);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
    v47 = *(const unsigned __int16 **)(*(_QWORD *)&v6 + 32LL);
    if ( MitigationTelemetryClass::IsEnabled(v49, v48) )
    {
      v51 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                          v50,
                                          _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
      MitigationTelemetryClass::ServiceDrivenActionInitialize_(v51, *v5, *(_DWORD *)(*(_QWORD *)&v6 + 16LL), v47);
    }
    return v10;
  }
  v74 = 0;
  v52 = *a2;
  v53 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a2 + 64LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v80,
    ServiceDrivenAction::s_parametersTag);
  v54 = v53(v52, v80[0], &v74);
  v10 = v54;
  v71 = v54;
  if ( v54 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenaction.cpp",
      (const char *)(unsigned int)v54,
      v71);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
    v55 = *(const unsigned __int16 **)(*(_QWORD *)&v6 + 32LL);
    if ( MitigationTelemetryClass::IsEnabled(v57, v56) )
    {
      v59 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                          v58,
                                          _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
      MitigationTelemetryClass::ServiceDrivenActionInitialize_(v59, *v5, *(_DWORD *)(*(_QWORD *)&v6 + 16LL), v55);
    }
    return v10;
  }
  v60 = (*(__int64 (__fastcall **)(_DWORD *, __int64 *))(*(_QWORD *)a1 + 96LL))(a1, &v74);
  v10 = v60;
  v71 = v60;
  if ( v60 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenaction.cpp",
      (const char *)(unsigned int)v60,
      v71);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
    v61 = *(const unsigned __int16 **)(*(_QWORD *)&v6 + 32LL);
    if ( MitigationTelemetryClass::IsEnabled(v63, v62) )
    {
      v65 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                          v64,
                                          _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
      MitigationTelemetryClass::ServiceDrivenActionInitialize_(v65, *v5, *(_DWORD *)(*(_QWORD *)&v6 + 16LL), v61);
    }
    return v10;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
  v66 = *(const unsigned __int16 **)(*(_QWORD *)&v6 + 32LL);
  if ( MitigationTelemetryClass::IsEnabled(v68, v67) )
  {
    v70 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                        v69,
                                        _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
    MitigationTelemetryClass::ServiceDrivenActionInitialize_(v70, *v5, *(_DWORD *)(*(_QWORD *)&v6 + 16LL), v66);
  }
  return 0;
}

```

## disassembly

```asm
0x18003d550  mov     rax, rsp
0x18003d553  mov     [rax+18h], rbx
0x18003d557  mov     [rax+20h], rsi
0x18003d55b  push    rbp
0x18003d55c  push    rdi
0x18003d55d  push    r12
0x18003d55f  push    r14
0x18003d561  push    r15
0x18003d563  lea     rbp, [rax-5Fh]
0x18003d567  sub     rsp, 0C0h
0x18003d56e  movaps  xmmword ptr [rax-38h], xmm6
0x18003d572  mov     rax, cs:__security_cookie
0x18003d579  xor     rax, rsp
0x18003d57c  mov     [rbp+57h+var_40], rax
0x18003d580  mov     r12, rdx
0x18003d583  mov     r15, rcx
0x18003d586  mov     [rbp+57h+var_C0], 0
0x18003d58d  mov     r8, rcx
0x18003d590  lea     rdx, [rbp+57h+var_C0]
0x18003d594  lea     rcx, [rbp+57h+var_70]
0x18003d598  call    ??0_lambda_e380becb44ad60157fc94fb792e326fc_@@QEAA@PEAV?$SimpleVectorView@PEAUIUnknown@@V?$Vector@PEAUIUnknown@@U?$DefaultEqualityPredicate@PEAUIUnknown@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIUnknown@@@3456@U?$VectorOptions@PEAUIUnknown@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIUnknown@@@3456@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAPEAI@Z; _lambda_e380becb44ad60157fc94fb792e326fc_::_lambda_e380becb44ad60157fc94fb792e326fc_(Windows::Foundation::Collections::Internal::SimpleVectorView<IUnknown *,Windows::Foundation::Collections::Internal::Vector<IUnknown *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IUnknown *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,Windows::Foundation::Collections::Internal::VectorOptions<IUnknown *,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,XWinRT::IntVersionTag,1> *,uint * &)
0x18003d59d  mov     r14, [rax]
0x18003d5a0  mov     [rbp+57h+var_88], r14
0x18003d5a4  mov     rsi, [rax+8]
0x18003d5a8  mov     [rbp+57h+var_80], rsi
0x18003d5ac  mov     [rbp+57h+var_78], 1
0x18003d5b0  xorps   xmm6, xmm6
0x18003d5b3  movsd   [rbp+57h+var_A0], xmm6
0x18003d5b8  mov     rdi, [r12]
0x18003d5bc  mov     rax, [rdi]
0x18003d5bf  mov     rbx, [rax+58h]
0x18003d5c3  mov     rdx, cs:?s_actionIdTag@ServiceDrivenAction@@0QEBGEB; unsigned __int16 *
0x18003d5ca  lea     rcx, [rbp+57h+var_60]; this
0x18003d5ce  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003d5d3  lea     r8, [rbp+57h+var_A0]
0x18003d5d7  mov     rdx, [rbp+57h+var_60]
0x18003d5db  mov     rcx, rdi
0x18003d5de  mov     rax, rbx
0x18003d5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5e6  mov     ebx, eax
0x18003d5e8  mov     [rbp+57h+var_C0], eax
0x18003d5eb  test    eax, eax
0x18003d5ed  jns     short loc_18003D63B
0x18003d5ef  mov     rcx, [rbp+5Fh]; this
0x18003d5f3  mov     r9d, eax; char *
0x18003d5f6  lea     r8, aOnecoreBaseDia_35; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003d5fd  mov     edx, 19h; void *
0x18003d602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d607  nop
0x18003d608  mov     rdi, [rsi+20h]
0x18003d60c  call    ?IsEnabled@MitigationTelemetryClass@@SA_NE_K@Z; MitigationTelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18003d611  test    al, al
0x18003d613  jz      short loc_18003D634
0x18003d615  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a44fdf97cbcc0b6240bb4609dde993dd_@@CA@XZ; _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_(void)
0x18003d61c  call    ?get@?$static_lazy@VMitigationTelemetryClass@@@details@wil@@QEAAPEAVMitigationTelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<MitigationTelemetryClass>::get(void (*)(void))
0x18003d621  mov     r9, rdi; unsigned __int16 *
0x18003d624  mov     r8d, [rsi+10h]; int
0x18003d628  mov     edx, [r14]; int
0x18003d62b  mov     rcx, rax; this
0x18003d62e  call    ?ServiceDrivenActionInitialize_@MitigationTelemetryClass@@QEAAXJHPEBG@Z; MitigationTelemetryClass::ServiceDrivenActionInitialize_(long,int,ushort const *)
0x18003d633  nop
0x18003d634  mov     eax, ebx
0x18003d636  jmp     loc_18003DA5A
0x18003d63b  cvttsd2si rax, [rbp+57h+var_A0]
0x18003d641  mov     [r15+10h], eax
0x18003d645  movsd   [rbp+57h+var_98], xmm6
0x18003d64a  mov     rdi, [r12]
0x18003d64e  mov     rax, [rdi]
0x18003d651  mov     rbx, [rax+58h]
0x18003d655  mov     rdx, cs:?s_orderTag@ServiceDrivenAction@@0QEBGEB; unsigned __int16 *
0x18003d65c  lea     rcx, [rbp+57h+var_60]; this
0x18003d660  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003d665  lea     r8, [rbp+57h+var_98]
0x18003d669  mov     rdx, [rbp+57h+var_60]
0x18003d66d  mov     rcx, rdi
0x18003d670  mov     rax, rbx
0x18003d673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d678  mov     ebx, eax
0x18003d67a  mov     [rbp+57h+var_C0], eax
0x18003d67d  test    eax, eax
0x18003d67f  jns     short loc_18003D6CB
0x18003d681  mov     rcx, [rbp+5Fh]; this
0x18003d685  mov     r9d, eax; char *
0x18003d688  lea     r8, aOnecoreBaseDia_35; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003d68f  mov     edx, 1Eh; void *
0x18003d694  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d699  nop
0x18003d69a  mov     rdi, [rsi+20h]
0x18003d69e  call    ?IsEnabled@MitigationTelemetryClass@@SA_NE_K@Z; MitigationTelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18003d6a3  test    al, al
0x18003d6a5  jz      short loc_18003D6C6
0x18003d6a7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a44fdf97cbcc0b6240bb4609dde993dd_@@CA@XZ; _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_(void)
0x18003d6ae  call    ?get@?$static_lazy@VMitigationTelemetryClass@@@details@wil@@QEAAPEAVMitigationTelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<MitigationTelemetryClass>::get(void (*)(void))
0x18003d6b3  mov     r9, rdi; unsigned __int16 *
0x18003d6b6  mov     r8d, [rsi+10h]; int
0x18003d6ba  mov     edx, [r14]; int
0x18003d6bd  mov     rcx, rax; this
0x18003d6c0  call    ?ServiceDrivenActionInitialize_@MitigationTelemetryClass@@QEAAXJHPEBG@Z; MitigationTelemetryClass::ServiceDrivenActionInitialize_(long,int,ushort const *)
0x18003d6c5  nop
0x18003d6c6  jmp     loc_18003D634
0x18003d6cb  cvttsd2si eax, [rbp+57h+var_98]
0x18003d6d0  mov     [r15+14h], eax
0x18003d6d4  movsd   [rbp+57h+var_90], xmm6
0x18003d6d9  mov     rdi, [r12]
0x18003d6dd  mov     rax, [rdi]
0x18003d6e0  mov     rbx, [rax+58h]
0x18003d6e4  mov     rdx, cs:?s_onErrorTag@ServiceDrivenAction@@0QEBGEB; unsigned __int16 *
0x18003d6eb  lea     rcx, [rbp+57h+var_60]; this
0x18003d6ef  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003d6f4  lea     r8, [rbp+57h+var_90]
0x18003d6f8  mov     rdx, [rbp+57h+var_60]
0x18003d6fc  mov     rcx, rdi
0x18003d6ff  mov     rax, rbx
0x18003d702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d707  mov     ebx, eax
0x18003d709  mov     [rbp+57h+var_C0], eax
0x18003d70c  test    eax, eax
0x18003d70e  jns     short loc_18003D75A
0x18003d710  mov     rcx, [rbp+5Fh]; this
0x18003d714  mov     r9d, eax; char *
0x18003d717  lea     r8, aOnecoreBaseDia_35; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003d71e  mov     edx, 23h ; '#'; void *
0x18003d723  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d728  nop
0x18003d729  mov     rdi, [rsi+20h]
0x18003d72d  call    ?IsEnabled@MitigationTelemetryClass@@SA_NE_K@Z; MitigationTelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18003d732  test    al, al
0x18003d734  jz      short loc_18003D755
0x18003d736  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a44fdf97cbcc0b6240bb4609dde993dd_@@CA@XZ; _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_(void)
0x18003d73d  call    ?get@?$static_lazy@VMitigationTelemetryClass@@@details@wil@@QEAAPEAVMitigationTelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<MitigationTelemetryClass>::get(void (*)(void))
0x18003d742  mov     r9, rdi; unsigned __int16 *
0x18003d745  mov     r8d, [rsi+10h]; int
0x18003d749  mov     edx, [r14]; int
0x18003d74c  mov     rcx, rax; this
0x18003d74f  call    ?ServiceDrivenActionInitialize_@MitigationTelemetryClass@@QEAAXJHPEBG@Z; MitigationTelemetryClass::ServiceDrivenActionInitialize_(long,int,ushort const *)
0x18003d754  nop
0x18003d755  jmp     loc_18003D634
0x18003d75a  cvttsd2si eax, [rbp+57h+var_90]
0x18003d75f  mov     [r15+18h], eax
0x18003d763  mov     [rbp+57h+var_B8], 0
0x18003d76b  lea     rdx, [rbp+57h+var_B8]
0x18003d76f  mov     rcx, r12
0x18003d772  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18003d777  mov     ebx, eax
0x18003d779  mov     [rbp+57h+var_C0], eax
0x18003d77c  test    eax, eax
0x18003d77e  jns     short loc_18003D7D4
0x18003d780  mov     rcx, [rbp+5Fh]; this
0x18003d784  mov     r9d, eax; char *
0x18003d787  lea     r8, aOnecoreBaseDia_35; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003d78e  mov     edx, 28h ; '('; void *
0x18003d793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d798  nop
0x18003d799  lea     rcx, [rbp+57h+var_B8]
0x18003d79d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d7a2  nop
0x18003d7a3  mov     rdi, [rsi+20h]
0x18003d7a7  call    ?IsEnabled@MitigationTelemetryClass@@SA_NE_K@Z; MitigationTelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18003d7ac  test    al, al
0x18003d7ae  jz      short loc_18003D7CF
0x18003d7b0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a44fdf97cbcc0b6240bb4609dde993dd_@@CA@XZ; _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_(void)
0x18003d7b7  call    ?get@?$static_lazy@VMitigationTelemetryClass@@@details@wil@@QEAAPEAVMitigationTelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<MitigationTelemetryClass>::get(void (*)(void))
0x18003d7bc  mov     r9, rdi; unsigned __int16 *
0x18003d7bf  mov     r8d, [rsi+10h]; int
0x18003d7c3  mov     edx, [r14]; int
0x18003d7c6  mov     rcx, rax; this
0x18003d7c9  call    ?ServiceDrivenActionInitialize_@MitigationTelemetryClass@@QEAAXJHPEBG@Z; MitigationTelemetryClass::ServiceDrivenActionInitialize_(long,int,ushort const *)
0x18003d7ce  nop
0x18003d7cf  jmp     loc_18003D634
0x18003d7d4  mov     [rbp+57h+string], 0
0x18003d7dc  mov     rcx, [rbp+57h+var_B8]
0x18003d7e0  mov     rax, [rcx]
0x18003d7e3  lea     rdx, [rbp+57h+string]
0x18003d7e7  mov     rax, [rax+38h]
0x18003d7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7f0  mov     ebx, eax
0x18003d7f2  mov     [rbp+57h+var_C0], eax
0x18003d7f5  test    eax, eax
0x18003d7f7  jns     short loc_18003D857
0x18003d7f9  mov     rcx, [rbp+5Fh]; this
0x18003d7fd  mov     r9d, eax; char *
0x18003d800  lea     r8, aOnecoreBaseDia_35; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003d807  mov     edx, 2Ah ; '*'; void *
0x18003d80c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d811  nop
0x18003d812  lea     rcx, [rbp+57h+string]; this
0x18003d816  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003d81b  nop
0x18003d81c  lea     rcx, [rbp+57h+var_B8]
0x18003d820  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d825  nop
0x18003d826  mov     rdi, [rsi+20h]
0x18003d82a  call    ?IsEnabled@MitigationTelemetryClass@@SA_NE_K@Z; MitigationTelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18003d82f  test    al, al
0x18003d831  jz      short loc_18003D852
0x18003d833  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a44fdf97cbcc0b6240bb4609dde993dd_@@CA@XZ; _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_(void)
0x18003d83a  call    ?get@?$static_lazy@VMitigationTelemetryClass@@@details@wil@@QEAAPEAVMitigationTelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<MitigationTelemetryClass>::get(void (*)(void))
0x18003d83f  mov     r9, rdi; unsigned __int16 *
0x18003d842  mov     r8d, [rsi+10h]; int
0x18003d846  mov     edx, [r14]; int
0x18003d849  mov     rcx, rax; this
0x18003d84c  call    ?ServiceDrivenActionInitialize_@MitigationTelemetryClass@@QEAAXJHPEBG@Z; MitigationTelemetryClass::ServiceDrivenActionInitialize_(long,int,ushort const *)
0x18003d851  nop
0x18003d852  jmp     loc_18003D634
0x18003d857  xor     edx, edx; length
0x18003d859  mov     rcx, [rbp+57h+string]; string
0x18003d85d  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d863  lea     rcx, [r15+20h]
0x18003d867  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003d86b  mov     rdx, rax
0x18003d86e  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003d873  mov     ebx, eax
0x18003d875  mov     [rbp+57h+var_C0], eax
0x18003d878  test    eax, eax
0x18003d87a  jns     short loc_18003D8DA
0x18003d87c  mov     rcx, [rbp+5Fh]; this
0x18003d880  mov     r9d, eax; char *
0x18003d883  lea     r8, aOnecoreBaseDia_35; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003d88a  mov     edx, 2Bh ; '+'; void *
0x18003d88f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d894  nop
0x18003d895  lea     rcx, [rbp+57h+string]; this
0x18003d899  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003d89e  nop
0x18003d89f  lea     rcx, [rbp+57h+var_B8]
0x18003d8a3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d8a8  nop
0x18003d8a9  mov     rdi, [rsi+20h]
0x18003d8ad  call    ?IsEnabled@MitigationTelemetryClass@@SA_NE_K@Z; MitigationTelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18003d8b2  test    al, al
0x18003d8b4  jz      short loc_18003D8D5
0x18003d8b6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a44fdf97cbcc0b6240bb4609dde993dd_@@CA@XZ; _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_(void)
0x18003d8bd  call    ?get@?$static_lazy@VMitigationTelemetryClass@@@details@wil@@QEAAPEAVMitigationTelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<MitigationTelemetryClass>::get(void (*)(void))
0x18003d8c2  mov     r9, rdi; unsigned __int16 *
0x18003d8c5  mov     r8d, [rsi+10h]; int
0x18003d8c9  mov     edx, [r14]; int
0x18003d8cc  mov     rcx, rax; this
0x18003d8cf  call    ?ServiceDrivenActionInitialize_@MitigationTelemetryClass@@QEAAXJHPEBG@Z; MitigationTelemetryClass::ServiceDrivenActionInitialize_(long,int,ushort const *)
0x18003d8d4  nop
0x18003d8d5  jmp     loc_18003D634
0x18003d8da  mov     [rbp+57h+var_A8], 0
0x18003d8e2  mov     rdi, [r12]
0x18003d8e6  mov     rax, [rdi]
0x18003d8e9  mov     rbx, [rax+40h]
0x18003d8ed  lea     rcx, [rbp+57h+var_A8]
0x18003d8f1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d8f6  mov     rdx, cs:?s_parametersTag@ServiceDrivenAction@@0QEBGEB; unsigned __int16 *
0x18003d8fd  lea     rcx, [rbp+57h+var_60]; this
0x18003d901  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003d906  lea     r8, [rbp+57h+var_A8]
0x18003d90a  mov     rdx, [rbp+57h+var_60]
0x18003d90e  mov     rcx, rdi
0x18003d911  mov     rax, rbx
0x18003d914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d919  mov     ebx, eax
0x18003d91b  mov     [rbp+57h+var_C0], eax
0x18003d91e  test    eax, eax
0x18003d920  jns     short loc_18003D98A
0x18003d922  mov     rcx, [rbp+5Fh]; this
0x18003d926  mov     r9d, eax; char *
0x18003d929  lea     r8, aOnecoreBaseDia_35; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003d930  mov     edx, 30h ; '0'; void *
0x18003d935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d93a  nop
0x18003d93b  lea     rcx, [rbp+57h+var_A8]
0x18003d93f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d944  nop
0x18003d945  lea     rcx, [rbp+57h+string]; this
0x18003d949  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003d94e  nop
0x18003d94f  lea     rcx, [rbp+57h+var_B8]
0x18003d953  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d958  nop
0x18003d959  mov     rdi, [rsi+20h]
0x18003d95d  call    ?IsEnabled@MitigationTelemetryClass@@SA_NE_K@Z; MitigationTelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18003d962  test    al, al
0x18003d964  jz      short loc_18003D985
0x18003d966  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a44fdf97cbcc0b6240bb4609dde993dd_@@CA@XZ; _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_(void)
0x18003d96d  call    ?get@?$static_lazy@VMitigationTelemetryClass@@@details@wil@@QEAAPEAVMitigationTelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<MitigationTelemetryClass>::get(void (*)(void))
0x18003d972  mov     r9, rdi; unsigned __int16 *
0x18003d975  mov     r8d, [rsi+10h]; int
0x18003d979  mov     edx, [r14]; int
0x18003d97c  mov     rcx, rax; this
0x18003d97f  call    ?ServiceDrivenActionInitialize_@MitigationTelemetryClass@@QEAAXJHPEBG@Z; MitigationTelemetryClass::ServiceDrivenActionInitialize_(long,int,ushort const *)
0x18003d984  nop
0x18003d985  jmp     loc_18003D634
0x18003d98a  mov     rax, [r15]
0x18003d98d  lea     rdx, [rbp+57h+var_A8]
0x18003d991  mov     rcx, r15
0x18003d994  mov     rax, [rax+60h]
0x18003d998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d99d  mov     ebx, eax
0x18003d99f  mov     [rbp+57h+var_C0], eax
0x18003d9a2  test    eax, eax
0x18003d9a4  jns     short loc_18003DA0E
0x18003d9a6  mov     rcx, [rbp+5Fh]; this
0x18003d9aa  mov     r9d, eax; char *
0x18003d9ad  lea     r8, aOnecoreBaseDia_35; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003d9b4  mov     edx, 31h ; '1'; void *
0x18003d9b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
