# WinRTLocalExpressionBuilder::ApplyRedirectionTransform(RedirectionTransformInfo *)

- ea: `0x180193160`
- end: `0x180193856`
- name: `?ApplyRedirectionTransform@WinRTLocalExpressionBuilder@@UEAAXPEAURedirectionTransformInfo@@@Z`
- size: `1782`
- prototype: `void __fastcall(WinRTLocalExpressionBuilder *this, RedirectionTransformInfo *redirInfo)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x180193160`
- `0x18019385c`
- `0x180216170`
- `0x1806877a8`
- `0x180687890`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193654`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18019366a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193680`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193696`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801936a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193736`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193785`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193812`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193654`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18019366a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193680`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193696`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801936a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193736`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193785`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180193812`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801936e2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019371f`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019376e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801937be`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801937fb`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019384a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801936e2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019371f`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019376e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801937be`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801937fb`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019384a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180193225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180193351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180193454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180193516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180193225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180193351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180193454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180193516`

## string_xrefs

- `0x18019329c`: `Matrix4x4.CreateFromTranslation(V.Offset) * PS.Redir * Matrix4x4.CreateFromTranslation(-Vector3(V.Offset.X, V.Offset.Y, 0))`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall WinRTLocalExpressionBuilder::ApplyRedirectionTransform(
        WinRTLocalExpressionBuilder *this,
        _STOWED_EXCEPTION_INFORMATION_V2 **redirInfo)
{
  Windows::UI::Composition::ICompositionPropertySet *ptr; // rdi
  Windows::UI::Composition::ICompositionPropertySet_vtbl *v4; // r13
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // rbx
  unsigned int v7; // eax
  UINT32 v8; // edx
  signed int v9; // eax
  HRESULT v10; // eax
  HRESULT v11; // ebx
  Windows::System::Internal::IUserManagerStatics *v12; // rsi
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v14; // eax
  HRESULT v15; // ebx
  Windows::UI::Composition::ICompositionObject *v16; // r12
  Windows::UI::Composition::ICompositionObject_vtbl *v17; // r13
  unsigned __int64 v18; // rbx
  unsigned int Size; // xmm6_4
  unsigned int Signature; // xmm7_4
  HRESULT ResultCode; // xmm8_4
  unsigned int v22; // xmm9_4
  float v23; // xmm10_4
  unsigned int ErrorText_high; // xmm11_4
  unsigned int v25; // eax
  UINT32 v26; // edx
  signed int v27; // eax
  HRESULT v28; // eax
  HRESULT v29; // ebx
  _STOWED_EXCEPTION_INFORMATION_V2 *v30; // rdi
  void (__fastcall *v31)(_STOWED_EXCEPTION_INFORMATION_V2 *, GUID *, Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> *); // rbx
  _STOWED_EXCEPTION_INFORMATION_V2 **v32; // r13
  unsigned __int64 v33; // rbx
  unsigned int v34; // eax
  UINT32 v35; // edx
  signed int v36; // eax
  HRESULT v37; // eax
  HRESULT v38; // ebx
  Windows::UI::Composition::ICompositionPropertySet *v39; // rdi
  HRESULT (__fastcall *v40)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v41; // eax
  HRESULT v42; // ebx
  Windows::UI::Composition::IExpressionAnimation *v43; // rbx
  Windows::UI::Composition::IExpressionAnimation_vtbl *v44; // r13
  unsigned int v45; // eax
  UINT32 v46; // edx
  signed int v47; // eax
  HRESULT v48; // eax
  HRESULT v49; // ebx
  WinRTLocalExpressionCache *m_cache; // rbx
  Windows::UI::Composition::IExpressionAnimation *v51; // rcx
  Windows::UI::Composition::ICompositionObject *v52; // rcx
  Windows::UI::Composition::IExpressionAnimation *v53; // rcx
  _STOWED_EXCEPTION_INFORMATION_V2 **v54; // rcx
  unsigned int pcStowedExceptions[2]; // [rsp+28h] [rbp-E0h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+30h] [rbp-D8h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> expressionCA; // [rsp+38h] [rbp-D0h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+40h] [rbp-C8h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> visualCO; // [rsp+48h] [rbp-C0h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> propertySetCO; // [rsp+50h] [rbp-B8h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::IExpressionAnimation> winRTExpression; // [rsp+58h] [rbp-B0h] BYREF
  Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> v62; // [rsp+60h] [rbp-A8h] BYREF
  Windows::Foundation::Numerics::Matrix4x4 v63; // [rsp+68h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-60h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-48h] BYREF

  pppStowedExceptions = redirInfo;
  ptr = this->m_cache->m_localExpressionComponentsPS.ptr_;
  v4 = ptr->__vftable;
  string = 0;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( ExpressionHelper::sc_propertyName_PostRedirectionTransform[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
LABEL_56:
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v7 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v6);
  v8 = v7 - 1;
  if ( (unsigned int)v6 < v7 )
    v8 = v6;
  v9 = WindowsCreateStringReference(
         ExpressionHelper::sc_propertyName_PostRedirectionTransform,
         v8,
         &hstringHeader,
         &string);
  if ( v9 < 0 )
  {
    RaiseException(v9, 1u, 0, 0);
    __debugbreak();
  }
  v63 = WinRTExpressionConversionContext::c_identityMatrix4x4;
  v10 = ((__int64 (__fastcall *)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING, Windows::Foundation::Numerics::Matrix4x4 *))v4->InsertMatrix4x4)(
          ptr,
          string,
          &v63);
  v11 = v10;
  if ( v10 < 0 )
  {
    OnFailure_2990_(v10);
    visualCO.ptr_ = 0;
    pcStowedExceptions[0] = 0;
    TraceForFailFast(v11);
    GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&visualCO, pcStowedExceptions);
    RoFailFastWithErrorContextInternal2(
      v11,
      pcStowedExceptions[0],
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)visualCO.ptr_);
  }
  v62.ptr_ = 0;
  ppStowedExceptions = 0;
  visualCO.ptr_ = 0;
  winRTExpression.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&visualCO);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  WinRTExpressionConversionContext::CreateExpression(
    &this->m_winrtContext,
    L"Matrix4x4.CreateFromTranslation(V.Offset) * PS.Redir * Matrix4x4.CreateFromTranslation(-Vector3(V.Offset.X, V.Offset.Y, 0))",
    (Windows::UI::Composition::IExpressionAnimation **)&v62,
    (Windows::UI::Composition::ICompositionPropertySet **)&visualCO);
  v12 = v62.ptr_;
  QueryInterface = v62.ptr_->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&ppStowedExceptions);
  v14 = QueryInterface(v12, &GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca, (void **)&ppStowedExceptions);
  v15 = v14;
  if ( v14 < 0 )
  {
    OnFailure_2990_(v14);
    expressionCA.ptr_ = 0;
    pcStowedExceptions[0] = 0;
    TraceForFailFast(v15);
    GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&expressionCA, pcStowedExceptions);
    RoFailFastWithErrorContextInternal2(
      v15,
      pcStowedExceptions[0],
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)expressionCA.ptr_);
  }
  v16 = visualCO.ptr_;
  v17 = visualCO.ptr_->__vftable;
  string = 0;
  v18 = -1;
  do
    ++v18;
  while ( ExpressionHelper::sc_propertyName_RedirectionTransform[v18] );
  if ( v18 > 0xFFFFFFFF )
  {
LABEL_55:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_56;
  }
  Size = (*pppStowedExceptions)->Header.Size;
  Signature = (*pppStowedExceptions)->Header.Signature;
  ResultCode = (*pppStowedExceptions)->ResultCode;
  v22 = *((_DWORD *)*pppStowedExceptions + 3);
  v23 = *(float *)&(*pppStowedExceptions)->ExceptionAddress;
  ErrorText_high = HIDWORD((*pppStowedExceptions)->ErrorText);
  v25 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v18);
  v26 = v25 - 1;
  if ( (unsigned int)v18 < v25 )
    v26 = v18;
  v27 = WindowsCreateStringReference(
          ExpressionHelper::sc_propertyName_RedirectionTransform,
          v26,
          &hstringHeader,
          &string);
  if ( v27 < 0 )
  {
    RaiseException(v27, 1u, 0, 0);
    __debugbreak();
  }
  *(_OWORD *)&v63.M11 = __PAIR64__(Signature, Size);
  *(_OWORD *)&v63.M21 = __PAIR64__(v22, ResultCode);
  *(__m128i *)&v63.M31 = _mm_load_si128((const __m128i *)&_xmm);
  v63.M41 = v23;
  *(_QWORD *)&v63.M42 = ErrorText_high;
  v63.M44 = 1.0;
  v28 = ((__int64 (__fastcall *)(Windows::UI::Composition::ICompositionObject *, HSTRING, Windows::Foundation::Numerics::Matrix4x4 *))v17->get_Properties)(
          v16,
          string,
          &v63);
  v29 = v28;
  if ( v28 < 0 )
  {
    OnFailure_2990_(v28);
    expressionCA.ptr_ = 0;
    pcStowedExceptions[0] = 0;
    TraceForFailFast(v29);
    GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&expressionCA, pcStowedExceptions);
    RoFailFastWithErrorContextInternal2(
      v29,
      pcStowedExceptions[0],
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)expressionCA.ptr_);
  }
  propertySetCO.ptr_ = 0;
  v30 = pppStowedExceptions[1];
  v31 = **(void (__fastcall ***)(_STOWED_EXCEPTION_INFORMATION_V2 *, GUID *, Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> *))&v30->Header;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&propertySetCO);
  v31(v30, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, &propertySetCO);
  v32 = ppStowedExceptions;
  expressionCA.ptr_ = (Windows::UI::Composition::ICompositionAnimation *)*ppStowedExceptions;
  string = 0;
  v33 = -1;
  do
    ++v33;
  while ( ExpressionHelper::sc_paramName_Visual[v33] );
  if ( v33 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_55;
  }
  pppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)propertySetCO.ptr_;
  v34 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v33);
  v35 = v34 - 1;
  if ( (unsigned int)v33 < v34 )
    v35 = v33;
  v36 = WindowsCreateStringReference(ExpressionHelper::sc_paramName_Visual, v35, &hstringHeader, &string);
  if ( v36 < 0 )
  {
    RaiseException(v36, 1u, 0, 0);
    __debugbreak();
  }
  v37 = ((__int64 (__fastcall *)(_STOWED_EXCEPTION_INFORMATION_V2 **, HSTRING, _STOWED_EXCEPTION_INFORMATION_V2 **))expressionCA.ptr_[12].__vftable)(
          v32,
          string,
          pppStowedExceptions);
  v38 = v37;
  if ( v37 < 0 )
  {
    OnFailure_2990_(v37);
    pppStowedExceptions = 0;
    pcStowedExceptions[0] = 0;
    TraceForFailFast(v38);
    GetStowedExceptionsForFailFast(&pppStowedExceptions, pcStowedExceptions);
    RoFailFastWithErrorContextInternal2(v38, pcStowedExceptions[0], pppStowedExceptions);
  }
  v39 = this->m_cache->m_localExpressionComponentsPS.ptr_;
  v40 = v39->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&winRTExpression);
  v41 = v40(v39, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, (void **)&winRTExpression.ptr_);
  v42 = v41;
  if ( v41 < 0 )
  {
    OnFailure_2990_(v41);
    pppStowedExceptions = 0;
    pcStowedExceptions[0] = 0;
    TraceForFailFast(v42);
    GetStowedExceptionsForFailFast(&pppStowedExceptions, pcStowedExceptions);
    RoFailFastWithErrorContextInternal2(v42, pcStowedExceptions[0], pppStowedExceptions);
  }
  v43 = winRTExpression.ptr_;
  v44 = winRTExpression.ptr_->__vftable;
  string = 0;
  do
    ++v5;
  while ( ExpressionHelper::sc_propertyName_PostRedirectionTransform[v5] );
  if ( v5 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  pppStowedExceptions = ppStowedExceptions;
  v45 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v5);
  v46 = v45 - 1;
  if ( (unsigned int)v5 < v45 )
    v46 = v5;
  v47 = WindowsCreateStringReference(
          ExpressionHelper::sc_propertyName_PostRedirectionTransform,
          v46,
          &hstringHeader,
          &string);
  if ( v47 < 0 )
  {
    RaiseException(v47, 1u, 0, 0);
    __debugbreak();
  }
  v48 = ((__int64 (__fastcall *)(Windows::UI::Composition::IExpressionAnimation *, HSTRING, _STOWED_EXCEPTION_INFORMATION_V2 **))v44[1].AddRef)(
          v43,
          string,
          pppStowedExceptions);
  v49 = v48;
  if ( v48 < 0 )
  {
    OnFailure_2990_(v48);
    pppStowedExceptions = 0;
    pcStowedExceptions[0] = 0;
    TraceForFailFast(v49);
    GetStowedExceptionsForFailFast(&pppStowedExceptions, pcStowedExceptions);
    RoFailFastWithErrorContextInternal2(v49, pcStowedExceptions[0], pppStowedExceptions);
  }
  m_cache = this->m_cache;
  if ( (Windows::System::Internal::IUserManagerStatics *)m_cache->m_redirectionExpression.ptr_ != v12 )
  {
    if ( v12 )
      v12->AddRef(v12);
    v51 = m_cache->m_redirectionExpression.ptr_;
    m_cache->m_redirectionExpression.ptr_ = (Windows::UI::Composition::IExpressionAnimation *)v12;
    if ( v51 )
      v51->Release(v51);
  }
  this->m_transformFlags |= 0x40u;
  v52 = propertySetCO.ptr_;
  if ( propertySetCO.ptr_ )
  {
    propertySetCO.ptr_ = 0;
    v52->Release(v52);
  }
  v53 = winRTExpression.ptr_;
  if ( winRTExpression.ptr_ )
  {
    winRTExpression.ptr_ = 0;
    v53->Release(v53);
  }
  if ( v16 )
    v16->Release(v16);
  v54 = ppStowedExceptions;
  if ( ppStowedExceptions )
  {
    ppStowedExceptions = 0;
    ((void (__fastcall *)(_STOWED_EXCEPTION_INFORMATION_V2 **))(*v54)->ExceptionAddress)(v54);
  }
  if ( v12 )
    v12->Release(v12);
}

```

## disassembly

```asm
0x180193160  mov     rax, rsp
0x180193163  mov     [rax+18h], rbx
0x180193167  push    rbp
0x180193168  push    rsi
0x180193169  push    rdi
0x18019316a  push    r12
0x18019316c  push    r13
0x18019316e  push    r14
0x180193170  push    r15
0x180193172  lea     rbp, [rax-68h]
0x180193176  sub     rsp, 130h
0x18019317d  movaps  xmmword ptr [rax-48h], xmm6
0x180193181  movaps  xmmword ptr [rax-58h], xmm7
0x180193185  movaps  xmmword ptr [rax-68h], xmm8
0x18019318a  movaps  xmmword ptr [rax-78h], xmm9
0x18019318f  movaps  xmmword ptr [rax-88h], xmm10
0x180193197  movaps  xmmword ptr [rax-98h], xmm11
0x18019319f  mov     rax, cs:__security_cookie
0x1801931a6  xor     rax, rsp
0x1801931a9  mov     [rbp+60h+var_A0], rax
0x1801931ad  mov     [rsp+160h+pppStowedExceptions], redirInfo
0x1801931b2  mov     r15, this
0x1801931b5  mov     rax, [this+30h]
0x1801931b9  mov     rdi, [rax+8]
0x1801931bd  mov     r13, [rdi]
0x1801931c0  xor     r12d, r12d
0x1801931c3  mov     [rbp+60h+string], r12
0x1801931c7  mov     rsi, cs:?sc_propertyName_PostRedirectionTransform@ExpressionHelper@@2QEBGEB; ushort const * const ExpressionHelper::sc_propertyName_PostRedirectionTransform
0x1801931ce  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801931d2  mov     rbx, r14
0x1801931d5  inc     rbx
0x1801931d8  cmp     [rsi+rbx*2], r12w
0x1801931dd  jnz     short loc_1801931D5
0x1801931df  mov     eax, 0FFFFFFFFh
0x1801931e4  cmp     rbx, rax
0x1801931e7  ja      loc_180193687
0x1801931ed  movaps  xmm6, xmmword ptr cs:?c_identityMatrix4x4@WinRTExpressionConversionContext@@2UMatrix4x4@Numerics@Foundation@Windows@@B.M11; Windows::Foundation::Numerics::Matrix4x4 const WinRTExpressionConversionContext::c_identityMatrix4x4 ...
0x1801931f4  movaps  xmm7, xmmword ptr cs:?c_identityMatrix4x4@WinRTExpressionConversionContext@@2UMatrix4x4@Numerics@Foundation@Windows@@B.M21; Windows::Foundation::Numerics::Matrix4x4 const WinRTExpressionConversionContext::c_identityMatrix4x4 ...
0x1801931fb  movaps  xmm8, xmmword ptr cs:?c_identityMatrix4x4@WinRTExpressionConversionContext@@2UMatrix4x4@Numerics@Foundation@Windows@@B.M31; Windows::Foundation::Numerics::Matrix4x4 const WinRTExpressionConversionContext::c_identityMatrix4x4 ...
0x180193203  movaps  xmm9, xmmword ptr cs:?c_identityMatrix4x4@WinRTExpressionConversionContext@@2UMatrix4x4@Numerics@Foundation@Windows@@B.M41; Windows::Foundation::Numerics::Matrix4x4 const WinRTExpressionConversionContext::c_identityMatrix4x4 ...
0x18019320b  mov     ecx, ebx; augend
0x18019320d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180193212  lea     edx, [rax-1]
0x180193215  cmp     ebx, eax
0x180193217  cmovb   edx, ebx; length
0x18019321a  lea     r9, [rbp+60h+string]; string
0x18019321e  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180193222  mov     this, rsi; sourceString
0x180193225  call    cs:__imp_WindowsCreateStringReference
0x18019322b  test    eax, eax
0x18019322d  js      loc_18019369D
0x180193233  movaps  xmmword ptr [rsp+160h+var_108.ptr_+8], xmm6
0x180193238  movaps  [rsp+160h+var_F8+8], xmm7
0x18019323d  movaps  [rbp+60h+var_E0], xmm8
0x180193242  movaps  [rbp+60h+var_D0], xmm9
0x180193247  lea     r8, [rsp+160h+var_108.ptr_+8]
0x18019324c  mov     redirInfo, [rbp+60h+string]
0x180193250  mov     this, rdi
0x180193253  mov     rax, [r13+40h]
0x180193257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019325c  mov     ebx, eax
0x18019325e  test    eax, eax
0x180193260  js      loc_1801936B0
0x180193266  mov     [rsp+160h+var_108.ptr_], r12
0x18019326b  mov     [rsp+160h+ppStowedExceptions], r12
0x180193270  mov     [rsp+160h+visualCO.ptr_], r12
0x180193275  mov     [rsp+160h+winRTExpression.ptr_], r12
0x18019327a  lea     this, [rsp+160h+visualCO]; this
0x18019327f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180193284  lea     this, [rsp+160h+var_108]; this
0x180193289  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019328e  lea     this, [r15+18h]; this
0x180193292  lea     r9, [rsp+160h+visualCO]; propertySet
0x180193297  lea     r8, [rsp+160h+var_108]; expression
0x18019329c  lea     redirInfo, aMatrix4x4Creat_12; "Matrix4x4.CreateFromTranslation(V.Offse"...
0x1801932a3  call    ?CreateExpression@WinRTExpressionConversionContext@@QEAAXPEBGPEAPEAUIExpressionAnimation@Composition@UI@Windows@@PEAPEAUICompositionPropertySet@345@@Z; WinRTExpressionConversionContext::CreateExpression(ushort const *,Windows::UI::Composition::IExpressionAnimation * *,Windows::UI::Composition::ICompositionPropertySet * *)
0x1801932a8  mov     rsi, [rsp+160h+var_108.ptr_]
0x1801932ad  mov     rax, [rsi]
0x1801932b0  mov     rbx, [rax]
0x1801932b3  lea     this, [rsp+160h+ppStowedExceptions]; this
0x1801932b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801932bd  lea     r8, [rsp+160h+ppStowedExceptions]
0x1801932c2  lea     redirInfo, _GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca
0x1801932c9  mov     this, rsi
0x1801932cc  mov     rax, rbx
0x1801932cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801932d4  mov     ebx, eax
0x1801932d6  test    eax, eax
0x1801932d8  js      loc_1801936ED
0x1801932de  mov     r12, [rsp+160h+visualCO.ptr_]
0x1801932e3  mov     r13, [r12]
0x1801932e7  xor     ecx, ecx
0x1801932e9  mov     [rbp+60h+string], this
0x1801932ed  mov     rdi, cs:?sc_propertyName_RedirectionTransform@ExpressionHelper@@2QEBGEB; ushort const * const ExpressionHelper::sc_propertyName_RedirectionTransform
0x1801932f4  mov     rbx, r14
0x1801932f7  inc     rbx
0x1801932fa  cmp     [rdi+rbx*2], cx
0x1801932fe  jnz     short loc_1801932F7
0x180193300  mov     eax, 0FFFFFFFFh
0x180193305  cmp     rbx, rax
0x180193308  ja      loc_180193671
0x18019330e  mov     rax, [rsp+160h+pppStowedExceptions]
0x180193313  mov     rax, [rax]
0x180193316  movss   xmm6, dword ptr [rax]
0x18019331a  movss   xmm7, dword ptr [rax+4]
0x18019331f  movss   xmm8, dword ptr [rax+8]
0x180193325  movss   xmm9, dword ptr [rax+0Ch]
0x18019332b  movss   xmm10, dword ptr [rax+10h]
0x180193331  movss   xmm11, dword ptr [rax+14h]
0x180193337  mov     ecx, ebx; augend
0x180193339  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18019333e  lea     edx, [rax-1]
0x180193341  cmp     ebx, eax
0x180193343  cmovb   edx, ebx; length
0x180193346  lea     r9, [rbp+60h+string]; string
0x18019334a  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x18019334e  mov     this, rdi; sourceString
0x180193351  call    cs:__imp_WindowsCreateStringReference
0x180193357  xor     edi, edi
0x180193359  test    eax, eax
0x18019335b  js      loc_18019372A
0x180193361  movss   dword ptr [rsp+160h+var_108.ptr_+8], xmm6
0x180193367  movss   dword ptr [rsp+160h+var_108.ptr_+0Ch], xmm7
0x18019336d  mov     qword ptr [rsp+160h+var_F8], rdi
0x180193372  movss   dword ptr [rsp+160h+var_F8+8], xmm8
0x180193379  movss   dword ptr [rsp+160h+var_F8+0Ch], xmm9
0x180193380  mov     [rsp+160h+var_E8], rdi
0x180193385  movdqa  xmm0, cs:__xmm@000000003f8000000000000000000000
0x18019338d  movaps  [rbp+60h+var_E0], xmm0
0x180193391  movss   dword ptr [rbp+60h+var_D0], xmm10
0x180193397  movss   dword ptr [rbp+60h+var_D0+4], xmm11
0x18019339d  mov     dword ptr [rbp+60h+var_D0+8], edi
0x1801933a0  mov     dword ptr [rbp+60h+var_D0+0Ch], 3F800000h
0x1801933a7  lea     r8, [rsp+160h+var_108.ptr_+8]
0x1801933ac  mov     redirInfo, [rbp+60h+string]
0x1801933b0  mov     this, r12
0x1801933b3  mov     rax, [r13+40h]
0x1801933b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801933bc  mov     ebx, eax
0x1801933be  test    eax, eax
0x1801933c0  js      loc_18019373D
0x1801933c6  mov     [rsp+160h+propertySetCO.ptr_], rdi
0x1801933cb  mov     rax, [rsp+160h+pppStowedExceptions]
0x1801933d0  mov     rdi, [rax+8]
0x1801933d4  mov     rax, [rdi]
0x1801933d7  mov     rbx, [rax]
0x1801933da  lea     this, [rsp+160h+propertySetCO]; this
0x1801933df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801933e4  lea     r8, [rsp+160h+propertySetCO]
0x1801933e9  lea     redirInfo, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x1801933f0  mov     this, rdi
0x1801933f3  mov     rax, rbx
0x1801933f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801933fb  mov     r13, [rsp+160h+ppStowedExceptions]
0x180193400  mov     rax, [r13+0]
0x180193404  mov     [rsp+160h+expressionCA.ptr_], rax
0x180193409  xor     eax, eax
0x18019340b  mov     [rbp+60h+string], rax
0x18019340f  mov     rdi, cs:?sc_paramName_Visual@ExpressionHelper@@2QEBGEB; ushort const * const ExpressionHelper::sc_paramName_Visual
0x180193416  mov     rbx, r14
0x180193419  inc     rbx
0x18019341c  cmp     [rdi+rbx*2], ax
0x180193420  jnz     short loc_180193419
0x180193422  mov     eax, 0FFFFFFFFh
0x180193427  cmp     rbx, rax
0x18019342a  ja      loc_18019365B
0x180193430  mov     rax, [rsp+160h+propertySetCO.ptr_]
0x180193435  mov     [rsp+160h+pppStowedExceptions], rax
0x18019343a  mov     ecx, ebx; augend
0x18019343c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180193441  lea     edx, [rax-1]
0x180193444  cmp     ebx, eax
0x180193446  cmovb   edx, ebx; length
0x180193449  lea     r9, [rbp+60h+string]; string
0x18019344d  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180193451  mov     this, rdi; sourceString
0x180193454  call    cs:__imp_WindowsCreateStringReference
0x18019345a  test    eax, eax
0x18019345c  js      loc_180193779
0x180193462  mov     r8, [rsp+160h+pppStowedExceptions]
0x180193467  mov     redirInfo, [rbp+60h+string]
0x18019346b  mov     this, r13
0x18019346e  mov     rax, [rsp+160h+expressionCA.ptr_]
0x180193473  mov     rax, [rax+60h]
0x180193477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019347c  mov     ebx, eax
0x18019347e  xor     r13d, r13d
0x180193481  test    eax, eax
0x180193483  js      loc_18019378C
0x180193489  mov     rax, [r15+30h]
0x18019348d  mov     rdi, [rax+8]
0x180193491  mov     rax, [rdi]
0x180193494  mov     rbx, [rax]
0x180193497  lea     this, [rsp+160h+winRTExpression]; this
0x18019349c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801934a1  lea     r8, [rsp+160h+winRTExpression]
0x1801934a6  lea     redirInfo, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x1801934ad  mov     this, rdi
0x1801934b0  mov     rax, rbx
0x1801934b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801934b8  mov     ebx, eax
0x1801934ba  test    eax, eax
0x1801934bc  js      loc_1801937C9
0x1801934c2  mov     rbx, [rsp+160h+winRTExpression.ptr_]
0x1801934c7  mov     r13, [rbx]
0x1801934ca  xor     eax, eax
0x1801934cc  mov     [rbp+60h+string], rax
0x1801934d0  mov     rdi, cs:?sc_propertyName_PostRedirectionTransform@ExpressionHelper@@2QEBGEB; ushort const * const ExpressionHelper::sc_propertyName_PostRedirectionTransform
0x1801934d7  inc     r14
0x1801934da  cmp     [rdi+r14*2], ax
0x1801934df  jnz     short loc_1801934D7
0x1801934e1  mov     eax, 0FFFFFFFFh
0x1801934e6  cmp     r14, rax
0x1801934e9  ja      loc_180193645
0x1801934ef  mov     rax, [rsp+160h+ppStowedExceptions]
0x1801934f4  mov     [rsp+160h+pppStowedExceptions], rax
0x1801934f9  mov     ecx, r14d; augend
0x1801934fc  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180193501  lea     edx, [rax-1]
0x180193504  cmp     r14d, eax
0x180193507  cmovb   edx, r14d; length
0x18019350b  lea     r9, [rbp+60h+string]; string
0x18019350f  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180193513  mov     this, rdi; sourceString
0x180193516  call    cs:__imp_WindowsCreateStringReference
0x18019351c  xor     edi, edi
0x18019351e  test    eax, eax
0x180193520  js      loc_180193806
0x180193526  mov     r8, [rsp+160h+pppStowedExceptions]
0x18019352b  mov     redirInfo, [rbp+60h+string]
0x18019352f  mov     this, rbx
0x180193532  mov     rax, [r13+48h]
0x180193536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019353b  mov     ebx, eax
0x18019353d  test    eax, eax
0x18019353f  js      loc_180193819
0x180193545  mov     rbx, [r15+30h]
0x180193549  cmp     [rbx+20h], rsi
0x18019354d  jz      short loc_18019357D
0x18019354f  test    rsi, rsi
0x180193552  jz      short loc_180193564
0x180193554  mov     rax, [rsi]
0x180193557  mov     this, rsi
0x18019355a  mov     rax, [rax+8]
0x18019355e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193563  nop
0x180193564  mov     this, [rbx+20h]
0x180193568  mov     [rbx+20h], rsi
0x18019356c  test    this, this
0x18019356f  jz      short loc_18019357D
0x180193571  mov     rax, [this]
0x180193574  mov     rax, [rax+10h]
0x180193578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019357d  or      dword ptr [r15+38h], 40h
0x180193582  mov     this, [rsp+160h+propertySetCO.ptr_]
0x180193587  test    this, this
0x18019358a  jz      short loc_18019359E
0x18019358c  mov     [rsp+160h+propertySetCO.ptr_], rdi
0x180193591  mov     rax, [this]
0x180193594  mov     rax, [rax+10h]
0x180193598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019359d  nop
0x18019359e  mov     this, [rsp+160h+winRTExpression.ptr_]
0x1801935a3  test    this, this
0x1801935a6  jz      short loc_1801935BA
0x1801935a8  mov     [rsp+160h+winRTExpression.ptr_], rdi
0x1801935ad  mov     rax, [this]
0x1801935b0  mov     rax, [rax+10h]
0x1801935b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801935b9  nop
0x1801935ba  test    r12, r12
0x1801935bd  jz      short loc_1801935D0
0x1801935bf  mov     rax, [r12]
0x1801935c3  mov     this, r12
0x1801935c6  mov     rax, [rax+10h]
0x1801935ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801935cf  nop
0x1801935d0  mov     this, [rsp+160h+ppStowedExceptions]
0x1801935d5  test    this, this
0x1801935d8  jz      short loc_1801935EC
0x1801935da  mov     [rsp+160h+ppStowedExceptions], rdi
0x1801935df  mov     rax, [this]
0x1801935e2  mov     rax, [rax+10h]
0x1801935e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801935eb  nop
0x1801935ec  test    rsi, rsi
0x1801935ef  jz      short loc_180193600
0x1801935f1  mov     rax, [rsi]
0x1801935f4  mov     this, rsi
0x1801935f7  mov     rax, [rax+10h]
0x1801935fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193600  mov     this, [rbp+60h+var_A0]
0x180193604  xor     this, rsp; StackCookie
0x180193607  call    __security_check_cookie
0x18019360c  lea     r11, [rsp+160h+var_30]
0x180193614  mov     rbx, [r11+50h]
0x180193618  movaps  xmm6, xmmword ptr [r11-10h]
0x18019361d  movaps  xmm7, xmmword ptr [r11-20h]
0x180193622  movaps  xmm8, xmmword ptr [r11-30h]
0x180193627  movaps  xmm9, xmmword ptr [r11-40h]
  ... truncated ...
```
