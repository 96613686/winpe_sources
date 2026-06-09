# WinRTExpressionConversionContext::ConnectSubExpression(bool,Windows::UI::Composition::IExpressionAnimation *,Windows::UI::Composition::IExpressionAnimation *,ushort const *)

- ea: `0x180192c24`
- end: `0x180193158`
- name: `?ConnectSubExpression@WinRTExpressionConversionContext@@QEAAX_NPEAUIExpressionAnimation@Composition@UI@Windows@@1PEBG@Z`
- size: `1332`
- prototype: `void __fastcall(WinRTExpressionConversionContext *this, bool useMatrix4x4, Windows::UI::Composition::IExpressionAnimation *overallExpression, Windows::UI::Composition::IExpressionAnimation *subExpression, const wchar_t *propertyName)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180191de0`
- `0x1804f3700`
- `0x1804f4f40`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x180192c24`
- `0x18019385c`
- `0x18039332c`
- `0x1806877a8`
- `0x180687890`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180192e71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180192f4b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193086`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193113`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180192e71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180192f4b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193086`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193113`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180192ff5`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180193032`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019306f`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801930bf`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801930fc`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019314c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180192ff5`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180193032`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019306f`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801930bf`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801930fc`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019314c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180192d90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180192eed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180192d90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180192eed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall WinRTExpressionConversionContext::ConnectSubExpression(
        WinRTExpressionConversionContext *this,
        bool useMatrix4x4,
        Windows::UI::Composition::IExpressionAnimation *overallExpression,
        Windows::UI::Composition::IExpressionAnimation *subExpression,
        Windows::UI::Composition::ICompositionObject *propertyName)
{
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v9; // eax
  HRESULT v10; // ebx
  Windows::System::Internal::IUserManagerStatics *ptr; // rbx
  HRESULT (__fastcall *CreateSponsoredProfile)(Windows::System::Internal::IUserManagerStatics *, unsigned int *); // rdi
  _STOWED_EXCEPTION_INFORMATION_V2 **v13; // rcx
  HRESULT v14; // eax
  HRESULT v15; // ebx
  _STOWED_EXCEPTION_INFORMATION_V2 **v16; // rbx
  __int64 (__fastcall *Header)(_STOWED_EXCEPTION_INFORMATION_V2 **, GUID *, Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> *); // rdi
  HRESULT v18; // eax
  Microsoft::WRL::Details::Dummy v19; // r8
  HRESULT v20; // ebx
  unsigned __int64 v21; // rsi
  __int64 (__fastcall **v22)(Windows::UI::Composition::ICompositionObject *, HSTRING__ *, Windows::UI::Composition::ICompositionPropertySet *); // rdi
  _STOWED_EXCEPTION_INFORMATION_V2 *v23; // r13
  unsigned __int64 v24; // rbx
  unsigned int v25; // eax
  UINT32 v26; // edx
  signed int StringReference; // eax
  HRESULT v28; // eax
  HRESULT v29; // ebx
  _STOWED_EXCEPTION_INFORMATION_V2 **v30; // rcx
  Windows::UI::Composition::ICompositionObject *v31; // rcx
  Windows::System::Internal::IUserManagerStatics *v32; // rcx
  HRESULT (__fastcall *v33)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v34; // eax
  HRESULT v35; // ebx
  Windows::UI::Composition::ICompositionObject *v36; // rbx
  Windows::UI::Composition::ICompositionPropertySet *v37; // r15
  unsigned int v38; // eax
  UINT32 v39; // edx
  signed int v40; // eax
  HRESULT v41; // eax
  HRESULT v42; // ebx
  Windows::UI::Composition::ICompositionPropertySet *v43; // rcx
  __int64 (__fastcall *v44)(_QWORD, _QWORD, Windows::Foundation::Numerics::Matrix4x4 *); // rbx
  __int64 v45; // rax
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> subExpressionCA; // [rsp+28h] [rbp-E0h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionPropertySet> propertySet; // [rsp+30h] [rbp-D8h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+38h] [rbp-D0h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> propertySetCO; // [rsp+40h] [rbp-C8h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> overallCO; // [rsp+48h] [rbp-C0h] BYREF
  Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> v51[4]; // [rsp+50h] [rbp-B8h] BYREF
  Windows::Foundation::Numerics::Matrix4x4 v52; // [rsp+78h] [rbp-90h] BYREF
  Microsoft::WRL::Wrappers::HStringReference hstringHeader; // [rsp+B8h] [rbp-50h] BYREF

  propertySetCO.ptr_ = propertyName;
  v51[0].ptr_ = 0;
  overallCO.ptr_ = 0;
  ppStowedExceptions = 0;
  QueryInterface = overallExpression->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v51);
  v9 = QueryInterface(overallExpression, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, (void **)&v51[0].ptr_);
  v10 = v9;
  if ( v9 < 0 )
  {
    OnFailure_2990_(v9);
    propertySet.ptr_ = 0;
    LODWORD(subExpressionCA.ptr_) = 0;
    TraceForFailFast(v10);
    GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertySet, (unsigned int *)&subExpressionCA);
    RoFailFastWithErrorContextInternal2(
      v10,
      (unsigned int)subExpressionCA.ptr_,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertySet.ptr_);
  }
  ptr = v51[0].ptr_;
  CreateSponsoredProfile = v51[0].ptr_->CreateSponsoredProfile;
  v13 = ppStowedExceptions;
  if ( ppStowedExceptions )
  {
    ppStowedExceptions = 0;
    ((void (__fastcall *)(_STOWED_EXCEPTION_INFORMATION_V2 **))(*v13)->ExceptionAddress)(v13);
  }
  v14 = CreateSponsoredProfile(ptr, (unsigned int *)&ppStowedExceptions);
  v15 = v14;
  if ( v14 < 0 )
  {
    OnFailure_2990_(v14);
    propertySet.ptr_ = 0;
    LODWORD(subExpressionCA.ptr_) = 0;
    TraceForFailFast(v15);
    GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertySet, (unsigned int *)&subExpressionCA);
    RoFailFastWithErrorContextInternal2(
      v15,
      (unsigned int)subExpressionCA.ptr_,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertySet.ptr_);
  }
  v16 = ppStowedExceptions;
  Header = (__int64 (__fastcall *)(_STOWED_EXCEPTION_INFORMATION_V2 **, GUID *, Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> *))(*ppStowedExceptions)->Header;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&overallCO);
  v18 = Header(v16, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, &overallCO);
  v20 = v18;
  if ( v18 < 0 )
  {
    OnFailure_2990_(v18);
    propertySet.ptr_ = 0;
    LODWORD(subExpressionCA.ptr_) = 0;
    TraceForFailFast(v20);
    GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertySet, (unsigned int *)&subExpressionCA);
    RoFailFastWithErrorContextInternal2(
      v20,
      (unsigned int)subExpressionCA.ptr_,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertySet.ptr_);
  }
  v21 = -1;
  v22 = (__int64 (__fastcall **)(Windows::UI::Composition::ICompositionObject *, HSTRING__ *, Windows::UI::Composition::ICompositionPropertySet *))ppStowedExceptions;
  if ( useMatrix4x4 )
    goto LABEL_39;
  v23 = *ppStowedExceptions;
  hstringHeader.hstr_ = 0;
  v24 = -1;
  do
    ++v24;
  while ( *((_WORD *)&propertyName->__vftable + v24) );
  if ( v24 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v25 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v24);
  v26 = v25 - 1;
  if ( (unsigned int)v24 < v25 )
    v26 = v24;
  StringReference = WindowsCreateStringReference(
                      (PCWSTR)propertyName,
                      v26,
                      &hstringHeader.header_,
                      &hstringHeader.hstr_);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  *(_OWORD *)&v51[1].ptr_ = *(_OWORD *)&WinRTExpressionConversionContext::c_identityMatrix3x2.M11;
  v51[3] = *(Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&WinRTExpressionConversionContext::c_identityMatrix3x2.M31;
  v28 = ((__int64 (__fastcall *)(void *, HSTRING__ *, Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *))v23[1].Header)(
          v22,
          hstringHeader.hstr_,
          &v51[1]);
  v29 = v28;
  if ( v28 < 0 )
    goto LABEL_42;
  while ( subExpression )
  {
    propertySet.ptr_ = 0;
    v33 = subExpression->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&propertySet);
    v34 = v33(subExpression, &GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca, (void **)&propertySet.ptr_);
    v35 = v34;
    if ( v34 < 0 )
    {
      OnFailure_2990_(v34);
      propertySetCO.ptr_ = 0;
      LODWORD(subExpressionCA.ptr_) = 0;
      TraceForFailFast(v35);
      GetStowedExceptionsForFailFast(
        (_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertySetCO,
        (unsigned int *)&subExpressionCA);
      RoFailFastWithErrorContextInternal2(
        v35,
        (unsigned int)subExpressionCA.ptr_,
        (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertySetCO.ptr_);
    }
    v36 = overallCO.ptr_;
    v22 = (__int64 (__fastcall **)(Windows::UI::Composition::ICompositionObject *, HSTRING__ *, Windows::UI::Composition::ICompositionPropertySet *))overallCO.ptr_->__vftable;
    hstringHeader.hstr_ = 0;
    do
      ++v21;
    while ( *((_WORD *)&propertyName->__vftable + v21) );
    if ( v21 <= 0xFFFFFFFF )
    {
      v37 = propertySet.ptr_;
      v38 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v21);
      v39 = v38 - 1;
      if ( (unsigned int)v21 < v38 )
        v39 = v21;
      v40 = WindowsCreateStringReference((PCWSTR)propertyName, v39, &hstringHeader.header_, &hstringHeader.hstr_);
      if ( v40 < 0 )
      {
        RaiseException(v40, 1u, 0, 0);
        __debugbreak();
      }
      v41 = v22[9](v36, hstringHeader.hstr_, v37);
      v42 = v41;
      if ( v41 < 0 )
      {
        OnFailure_2990_(v41);
        propertySetCO.ptr_ = 0;
        LODWORD(subExpressionCA.ptr_) = 0;
        TraceForFailFast(v42);
        GetStowedExceptionsForFailFast(
          (_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertySetCO,
          (unsigned int *)&subExpressionCA);
        RoFailFastWithErrorContextInternal2(
          v42,
          (unsigned int)subExpressionCA.ptr_,
          (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertySetCO.ptr_);
      }
      v43 = propertySet.ptr_;
      if ( propertySet.ptr_ )
      {
        propertySet.ptr_ = 0;
        v43->Release(v43);
      }
      break;
    }
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_39:
    v44 = (__int64 (__fastcall *)(_QWORD, _QWORD, Windows::Foundation::Numerics::Matrix4x4 *))*((_QWORD *)*v22 + 8);
    Microsoft::WRL::Wrappers::HStringReference::HStringReference(
      &hstringHeader,
      (const unsigned __int16 *const *)&propertySetCO,
      v19);
    v52 = WinRTExpressionConversionContext::c_identityMatrix4x4;
    v28 = v44(v22, *(_QWORD *)(v45 + 24), &v52);
    v29 = v28;
    if ( v28 < 0 )
    {
LABEL_42:
      OnFailure_2990_(v28);
      LODWORD(subExpressionCA.ptr_) = 0;
      propertySet.ptr_ = 0;
      TraceForFailFast(v29);
      GetStowedExceptionsForFailFast(
        (_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertySet,
        (unsigned int *)&subExpressionCA);
      RoFailFastWithErrorContextInternal2(
        v29,
        (unsigned int)subExpressionCA.ptr_,
        (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertySet.ptr_);
    }
  }
  v30 = ppStowedExceptions;
  if ( ppStowedExceptions )
  {
    ppStowedExceptions = 0;
    ((void (__fastcall *)(_STOWED_EXCEPTION_INFORMATION_V2 **))(*v30)->ExceptionAddress)(v30);
  }
  v31 = overallCO.ptr_;
  if ( overallCO.ptr_ )
  {
    overallCO.ptr_ = 0;
    v31->Release(v31);
  }
  v32 = v51[0].ptr_;
  if ( v51[0].ptr_ )
  {
    v51[0].ptr_ = 0;
    v32->Release(v32);
  }
}

```

## disassembly

```asm
0x180192c24  mov     rax, rsp
0x180192c27  mov     [rax+8], rbx
0x180192c2b  push    rbp
0x180192c2c  push    rsi
0x180192c2d  push    rdi
0x180192c2e  push    r12
0x180192c30  push    r13
0x180192c32  push    r14
0x180192c34  push    r15
0x180192c36  lea     rbp, [rax-58h]
0x180192c3a  sub     rsp, 120h
0x180192c41  movaps  xmmword ptr [rax-48h], xmm6
0x180192c45  movaps  xmmword ptr [rax-58h], xmm7
0x180192c49  movaps  xmmword ptr [rax-68h], xmm8
0x180192c4e  movaps  xmmword ptr [rax-78h], xmm9
0x180192c53  mov     rax, cs:__security_cookie
0x180192c5a  xor     rax, rsp
0x180192c5d  mov     [rbp+50h+var_80], rax
0x180192c61  mov     r15, subExpression
0x180192c64  mov     rdi, overallExpression
0x180192c67  mov     r12b, useMatrix4x4
0x180192c6a  mov     r14, [rbp+50h+sourceString]
0x180192c71  mov     [rsp+150h+propertySetCO.ptr_], r14
0x180192c76  xor     r13d, r13d
0x180192c79  mov     qword ptr [rsp+150h+var_108], r13
0x180192c7e  mov     [rsp+150h+overallCO.ptr_], r13
0x180192c83  mov     [rsp+150h+ppStowedExceptions], r13
0x180192c88  mov     rax, [overallExpression]
0x180192c8b  mov     rbx, [rax]
0x180192c8e  lea     rcx, [rsp+150h+var_108]; this
0x180192c93  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180192c98  lea     overallExpression, [rsp+150h+var_108]
0x180192c9d  lea     rdx, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x180192ca4  mov     rcx, rdi
0x180192ca7  mov     rax, rbx
0x180192caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192caf  mov     ebx, eax
0x180192cb1  test    eax, eax
0x180192cb3  js      loc_180192FC3
0x180192cb9  mov     rbx, qword ptr [rsp+150h+var_108]
0x180192cbe  mov     rax, [rbx]
0x180192cc1  mov     rdi, [rax+40h]
0x180192cc5  mov     rcx, [rsp+150h+ppStowedExceptions]
0x180192cca  test    rcx, rcx
0x180192ccd  jz      short loc_180192CE0
0x180192ccf  mov     [rsp+150h+ppStowedExceptions], r13
0x180192cd4  mov     rdx, [rcx]
0x180192cd7  mov     rax, [rdx+10h]
0x180192cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192ce0  lea     rdx, [rsp+150h+ppStowedExceptions]
0x180192ce5  mov     rcx, rbx
0x180192ce8  mov     rax, rdi
0x180192ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192cf0  mov     ebx, eax
0x180192cf2  test    eax, eax
0x180192cf4  js      loc_180193000
0x180192cfa  mov     rbx, [rsp+150h+ppStowedExceptions]
0x180192cff  mov     rax, [rbx]
0x180192d02  mov     rdi, [rax]
0x180192d05  lea     rcx, [rsp+150h+overallCO]; this
0x180192d0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180192d0f  lea     overallExpression, [rsp+150h+overallCO]
0x180192d14  lea     rdx, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x180192d1b  mov     rcx, rbx
0x180192d1e  mov     rax, rdi
0x180192d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192d26  mov     ebx, eax
0x180192d28  test    eax, eax
0x180192d2a  js      loc_18019303D
0x180192d30  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180192d34  mov     eax, 0FFFFFFFFh
0x180192d39  mov     rdi, [rsp+150h+ppStowedExceptions]
0x180192d3e  test    r12b, r12b
0x180192d41  jnz     loc_180192F52
0x180192d47  mov     r13, [rdi]
0x180192d4a  xor     r12d, r12d
0x180192d4d  mov     [rbp+50h+string], r12
0x180192d51  mov     rbx, rsi
0x180192d54  inc     rbx
0x180192d57  cmp     [r14+rbx*2], r12w
0x180192d5c  jnz     short loc_180192D54
0x180192d5e  cmp     rbx, rax
0x180192d61  ja      loc_180192E62
0x180192d67  movups  xmm6, xmmword ptr cs:?c_identityMatrix3x2@WinRTExpressionConversionContext@@2UMatrix3x2@Numerics@Foundation@Windows@@B.M11; Windows::Foundation::Numerics::Matrix3x2 const WinRTExpressionConversionContext::c_identityMatrix3x2 ...
0x180192d6e  movsd   xmm7, qword ptr cs:?c_identityMatrix3x2@WinRTExpressionConversionContext@@2UMatrix3x2@Numerics@Foundation@Windows@@B.M31; Windows::Foundation::Numerics::Matrix3x2 const WinRTExpressionConversionContext::c_identityMatrix3x2 ...
0x180192d76  mov     ecx, ebx; augend
0x180192d78  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180192d7d  lea     edx, [rax-1]
0x180192d80  cmp     ebx, eax
0x180192d82  cmovb   edx, ebx; length
0x180192d85  lea     subExpression, [rbp+50h+string]; string
0x180192d89  lea     overallExpression, [rbp+50h+hstringHeader]; hstringHeader
0x180192d8d  mov     rcx, r14; sourceString
0x180192d90  call    cs:__imp_WindowsCreateStringReference
0x180192d96  test    eax, eax
0x180192d98  js      loc_18019307A
0x180192d9e  movaps  xmmword ptr [rsp+150h+var_108+8], xmm6
0x180192da3  movsd   [rsp+150h+var_F0], xmm7
0x180192da9  lea     overallExpression, [rsp+150h+var_108+8]
0x180192dae  mov     rdx, [rbp+50h+string]
0x180192db2  mov     rcx, rdi
0x180192db5  mov     rax, [r13+38h]
0x180192db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192dbe  mov     ebx, eax
0x180192dc0  xor     r13d, r13d
0x180192dc3  test    eax, eax
0x180192dc5  js      loc_18019308D
0x180192dcb  test    r15, r15
0x180192dce  jnz     loc_180192E78
0x180192dd4  mov     rcx, [rsp+150h+ppStowedExceptions]
0x180192dd9  test    rcx, rcx
0x180192ddc  jz      short loc_180192DF0
0x180192dde  mov     [rsp+150h+ppStowedExceptions], r13
0x180192de3  mov     rax, [rcx]
0x180192de6  mov     rax, [rax+10h]
0x180192dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192def  nop
0x180192df0  mov     rcx, [rsp+150h+overallCO.ptr_]
0x180192df5  test    rcx, rcx
0x180192df8  jz      short loc_180192E0C
0x180192dfa  mov     [rsp+150h+overallCO.ptr_], r13
0x180192dff  mov     rax, [rcx]
0x180192e02  mov     rax, [rax+10h]
0x180192e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192e0b  nop
0x180192e0c  mov     rcx, qword ptr [rsp+150h+var_108]
0x180192e11  test    rcx, rcx
0x180192e14  jz      short loc_180192E27
0x180192e16  mov     qword ptr [rsp+150h+var_108], r13
0x180192e1b  mov     rax, [rcx]
0x180192e1e  mov     rax, [rax+10h]
0x180192e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192e27  mov     rcx, [rbp+50h+var_80]
0x180192e2b  xor     rcx, rsp; StackCookie
0x180192e2e  call    __security_check_cookie
0x180192e33  lea     r11, [rsp+150h+var_30]
0x180192e3b  mov     rbx, [r11+40h]
0x180192e3f  movaps  xmm6, xmmword ptr [r11-10h]
0x180192e44  movaps  xmm7, xmmword ptr [r11-20h]
0x180192e49  movaps  xmm8, xmmword ptr [r11-30h]
0x180192e4e  movaps  xmm9, xmmword ptr [r11-40h]
0x180192e53  mov     rsp, r11
0x180192e56  pop     r15
0x180192e58  pop     r14
0x180192e5a  pop     r13
0x180192e5c  pop     r12
0x180192e5e  pop     rdi
0x180192e5f  pop     rsi
0x180192e60  pop     rbp
0x180192e61  retn
0x180192e62  xor     r9d, r9d; lpArguments
0x180192e65  xor     r8d, r8d; nNumberOfArguments
0x180192e68  lea     edx, [subExpression+1]; dwExceptionFlags
0x180192e6c  mov     ecx, 80070216h; dwExceptionCode
0x180192e71  call    cs:__imp_RaiseException
0x180192e77  int     3; Trap to Debugger
0x180192e78  mov     [rsp+150h+propertySet.ptr_], r13
0x180192e7d  mov     rax, [r15]
0x180192e80  mov     rbx, [rax]
0x180192e83  lea     rcx, [rsp+150h+propertySet]; this
0x180192e88  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180192e8d  lea     overallExpression, [rsp+150h+propertySet]
0x180192e92  lea     rdx, _GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca
0x180192e99  mov     rcx, r15
0x180192e9c  mov     rax, rbx
0x180192e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192ea4  mov     ebx, eax
0x180192ea6  test    eax, eax
0x180192ea8  js      loc_1801930CA
0x180192eae  mov     rbx, [rsp+150h+overallCO.ptr_]
0x180192eb3  mov     rdi, [rbx]
0x180192eb6  mov     [rbp+50h+string], r13
0x180192eba  inc     rsi
0x180192ebd  cmp     [r14+rsi*2], r13w
0x180192ec2  jnz     short loc_180192EBA
0x180192ec4  mov     eax, 0FFFFFFFFh
0x180192ec9  cmp     rsi, rax
0x180192ecc  ja      short loc_180192F3C
0x180192ece  mov     r15, [rsp+150h+propertySet.ptr_]
0x180192ed3  mov     ecx, esi; augend
0x180192ed5  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180192eda  lea     edx, [rax-1]
0x180192edd  cmp     esi, eax
0x180192edf  cmovb   edx, esi; length
0x180192ee2  lea     subExpression, [rbp+50h+string]; string
0x180192ee6  lea     overallExpression, [rbp+50h+hstringHeader]; hstringHeader
0x180192eea  mov     rcx, r14; sourceString
0x180192eed  call    cs:__imp_WindowsCreateStringReference
0x180192ef3  test    eax, eax
0x180192ef5  js      loc_180193107
0x180192efb  mov     overallExpression, r15
0x180192efe  mov     rdx, [rbp+50h+string]
0x180192f02  mov     rcx, rbx
0x180192f05  mov     rax, [rdi+48h]
0x180192f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192f0e  mov     ebx, eax
0x180192f10  test    eax, eax
0x180192f12  js      loc_18019311A
0x180192f18  mov     rcx, [rsp+150h+propertySet.ptr_]
0x180192f1d  test    rcx, rcx
0x180192f20  jz      loc_180192DD4
0x180192f26  mov     [rsp+150h+propertySet.ptr_], r13
0x180192f2b  mov     rax, [rcx]
0x180192f2e  mov     rax, [rax+10h]
0x180192f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192f37  jmp     loc_180192DD4
0x180192f3c  xor     r9d, r9d; lpArguments
0x180192f3f  xor     r8d, r8d; nNumberOfArguments
0x180192f42  lea     edx, [subExpression+1]; dwExceptionFlags
0x180192f46  mov     ecx, 80070216h; dwExceptionCode
0x180192f4b  call    cs:__imp_RaiseException
0x180192f51  nop
0x180192f52  mov     rax, [rdi]
0x180192f55  mov     rbx, [rax+40h]
0x180192f59  movaps  xmm9, xmmword ptr cs:?c_identityMatrix4x4@WinRTExpressionConversionContext@@2UMatrix4x4@Numerics@Foundation@Windows@@B.M11; Windows::Foundation::Numerics::Matrix4x4 const WinRTExpressionConversionContext::c_identityMatrix4x4 ...
0x180192f61  movaps  xmm8, xmmword ptr cs:?c_identityMatrix4x4@WinRTExpressionConversionContext@@2UMatrix4x4@Numerics@Foundation@Windows@@B.M21; Windows::Foundation::Numerics::Matrix4x4 const WinRTExpressionConversionContext::c_identityMatrix4x4 ...
0x180192f69  movaps  xmm7, xmmword ptr cs:?c_identityMatrix4x4@WinRTExpressionConversionContext@@2UMatrix4x4@Numerics@Foundation@Windows@@B.M31; Windows::Foundation::Numerics::Matrix4x4 const WinRTExpressionConversionContext::c_identityMatrix4x4 ...
0x180192f70  movaps  xmm6, xmmword ptr cs:?c_identityMatrix4x4@WinRTExpressionConversionContext@@2UMatrix4x4@Numerics@Foundation@Windows@@B.M41; Windows::Foundation::Numerics::Matrix4x4 const WinRTExpressionConversionContext::c_identityMatrix4x4 ...
0x180192f77  lea     rdx, [rsp+150h+propertySetCO]; strRef
0x180192f7c  lea     rcx, [rbp+50h+hstringHeader]; this
0x180192f80  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180192f85  nop
0x180192f86  movaps  [rsp+150h+var_E8+8], xmm9
0x180192f8c  movaps  [rbp+50h+var_D0], xmm8
0x180192f91  movaps  [rbp+50h+var_C0], xmm7
0x180192f95  movaps  [rbp+50h+var_B0], xmm6
0x180192f99  lea     overallExpression, [rsp+150h+var_E8+8]
0x180192f9e  mov     rdx, [rax+18h]
0x180192fa2  mov     rcx, rdi
0x180192fa5  mov     rax, rbx
0x180192fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192fad  mov     ebx, eax
0x180192faf  test    eax, eax
0x180192fb1  jns     loc_180192DCB
0x180192fb7  mov     ecx, eax; failedFrameHR
0x180192fb9  call    OnFailure_2990_
0x180192fbe  jmp     loc_180193094
0x180192fc3  mov     ecx, ebx; failedFrameHR
0x180192fc5  call    OnFailure_2990_
0x180192fca  mov     [rsp+150h+propertySet.ptr_], r13
0x180192fcf  mov     dword ptr [rsp+150h+subExpressionCA.ptr_], r13d
0x180192fd4  mov     ecx, ebx; errorCode
0x180192fd6  call    TraceForFailFast
0x180192fdb  lea     rdx, [rsp+150h+subExpressionCA]; pcStowedExceptions
0x180192fe0  lea     rcx, [rsp+150h+propertySet]; pppStowedExceptions
0x180192fe5  call    GetStowedExceptionsForFailFast
0x180192fea  mov     overallExpression, [rsp+150h+propertySet.ptr_]
0x180192fef  mov     edx, dword ptr [rsp+150h+subExpressionCA.ptr_]
0x180192ff3  mov     ecx, ebx
0x180192ff5  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x180192ffb  jmp     loc_180192CB9
0x180193000  mov     ecx, ebx; failedFrameHR
0x180193002  call    OnFailure_2990_
0x180193007  mov     [rsp+150h+propertySet.ptr_], r13
0x18019300c  mov     dword ptr [rsp+150h+subExpressionCA.ptr_], r13d
0x180193011  mov     ecx, ebx; errorCode
0x180193013  call    TraceForFailFast
0x180193018  lea     rdx, [rsp+150h+subExpressionCA]; pcStowedExceptions
0x18019301d  lea     rcx, [rsp+150h+propertySet]; pppStowedExceptions
0x180193022  call    GetStowedExceptionsForFailFast
0x180193027  mov     overallExpression, [rsp+150h+propertySet.ptr_]
0x18019302c  mov     edx, dword ptr [rsp+150h+subExpressionCA.ptr_]
0x180193030  mov     ecx, ebx
0x180193032  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x180193038  jmp     loc_180192CFA
0x18019303d  mov     ecx, ebx; failedFrameHR
0x18019303f  call    OnFailure_2990_
0x180193044  mov     [rsp+150h+propertySet.ptr_], r13
0x180193049  mov     dword ptr [rsp+150h+subExpressionCA.ptr_], r13d
0x18019304e  mov     ecx, ebx; errorCode
0x180193050  call    TraceForFailFast
0x180193055  lea     rdx, [rsp+150h+subExpressionCA]; pcStowedExceptions
0x18019305a  lea     rcx, [rsp+150h+propertySet]; pppStowedExceptions
0x18019305f  call    GetStowedExceptionsForFailFast
0x180193064  mov     overallExpression, [rsp+150h+propertySet.ptr_]
0x180193069  mov     edx, dword ptr [rsp+150h+subExpressionCA.ptr_]
0x18019306d  mov     ecx, ebx
0x18019306f  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x180193075  jmp     loc_180192D30
0x18019307a  xor     r9d, r9d; lpArguments
0x18019307d  xor     r8d, r8d; nNumberOfArguments
0x180193080  lea     edx, [subExpression+1]; dwExceptionFlags
0x180193084  mov     ecx, eax; dwExceptionCode
0x180193086  call    cs:__imp_RaiseException
0x18019308c  int     3; Trap to Debugger
0x18019308d  mov     ecx, ebx; failedFrameHR
0x18019308f  call    OnFailure_2990_
0x180193094  mov     dword ptr [rsp+150h+subExpressionCA.ptr_], r13d
0x180193099  mov     [rsp+150h+propertySet.ptr_], r13
0x18019309e  mov     ecx, ebx; errorCode
0x1801930a0  call    TraceForFailFast
0x1801930a5  lea     rdx, [rsp+150h+subExpressionCA]; pcStowedExceptions
0x1801930aa  lea     rcx, [rsp+150h+propertySet]; pppStowedExceptions
0x1801930af  call    GetStowedExceptionsForFailFast
0x1801930b4  mov     overallExpression, [rsp+150h+propertySet.ptr_]
0x1801930b9  mov     edx, dword ptr [rsp+150h+subExpressionCA.ptr_]
0x1801930bd  mov     ecx, ebx
0x1801930bf  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1801930c5  jmp     loc_180192DCB
0x1801930ca  mov     ecx, ebx; failedFrameHR
  ... truncated ...
```
