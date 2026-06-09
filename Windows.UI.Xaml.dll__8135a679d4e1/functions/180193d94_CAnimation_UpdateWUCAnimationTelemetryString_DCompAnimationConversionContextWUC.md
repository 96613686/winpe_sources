# CAnimation::UpdateWUCAnimationTelemetryString(DCompAnimationConversionContextWUC *)

- ea: `0x180193d94`
- end: `0x18019457c`
- name: `?UpdateWUCAnimationTelemetryString@CAnimation@@IEAAXPEAVDCompAnimationConversionContextWUC@@@Z`
- size: `2024`
- prototype: `void __fastcall(CAnimation *this, DCompAnimationConversionContextWUC *myContext)`
- caller_count: `4`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801244f0`
- `0x180250080`
- `0x1802507a0`
- `0x180571590`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x18001f3c0`
- `0x18007a328`
- `0x180091d20`
- `0x1800aabf0`
- `0x1800af8e0`
- `0x1800c0fdc`
- `0x1800fe130`
- `0x18019385c`
- `0x180193d94`
- `0x180194584`
- `0x180289f24`
- `0x180363614`
- `0x1806877a8`
- `0x180687890`
- `0x1806b2e84`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18019401b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180194538`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18019401b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180194538`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801941eb`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180194315`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801943c1`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801943fe`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019443b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180194478`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801944b5`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801944f2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180194571`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801941eb`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180194315`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801943c1`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801943fe`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18019443b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180194478`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801944b5`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1801944f2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180194571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801942c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801942c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180193e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180193e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180194288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180194288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180193fde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180193fde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180194329`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180194329`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180193f76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180193f76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1801942a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1801942a2`

## pseudocode

```c
void __fastcall CAnimation::UpdateWUCAnimationTelemetryString(
        CAnimation *this,
        DCompAnimationConversionContextWUC *myContext)
{
  xstring_ptr *p_m_storyboardTelemetryName; // rsi
  unsigned __int64 RuntimeStringHandleMarker; // rbx
  xref::details::control_block *m_ref_count; // rdx
  CDependencyObject *m_ptr; // rdi
  signed __int32 Value; // eax
  signed __int32 v8; // ett
  const CDependencyProperty *m_pTargetDependencyProperty; // rdx
  unsigned int m_cActual; // edi
  int String; // eax
  HRESULT v12; // esi
  HRESULT v13; // edi
  Windows::UI::Composition::IKeyFrameAnimation *ptr; // rsi
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  const wchar_t *StringRawBuffer; // rdi
  unsigned __int64 v17; // rbx
  unsigned int v18; // eax
  UINT32 v19; // edx
  signed int StringReference; // eax
  HRESULT v21; // eax
  HRESULT v22; // ebx
  Windows::UI::Composition::ICompositionObject2 *v23; // rcx
  bool IsNull; // al
  HRESULT v25; // eax
  HRESULT v26; // esi
  HRESULT v27; // eax
  HRESULT v28; // esi
  HRESULT v29; // eax
  HRESULT v30; // edi
  __int64 m_nIndex; // rax
  HRESULT v32; // eax
  HRESULT v33; // edi
  HRESULT v34; // eax
  HRESULT v35; // edi
  HRESULT v36; // eax
  HRESULT v37; // edi
  HRESULT v38; // eax
  HRESULT v39; // edi
  int v40; // eax
  UINT32 StringLen; // eax
  HRESULT v42; // eax
  HSTRING v43; // rcx
  xstring_ptr propertyName; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING cStowedExceptions; // [rsp+28h] [rbp-D8h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v47; // [rsp+38h] [rbp-C8h] BYREF
  int v48; // [rsp+40h] [rbp-C0h]
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject2> animationAsCO; // [rsp+48h] [rbp-B8h] BYREF
  Microsoft::WRL::Wrappers::HStringReference telemetryString; // [rsp+50h] [rbp-B0h] BYREF
  TStringBuilder<96> telemetryBuilder; // [rsp+70h] [rbp-90h] BYREF

  p_m_storyboardTelemetryName = &myContext->m_storyboardTelemetryName;
  *(_QWORD *)&telemetryBuilder.m_cBuffer = 96;
  telemetryBuilder.m_pBuffer = telemetryBuilder.m_inlineBuffer;
  telemetryBuilder.m_hPreallocatedBuffer = 0;
  RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  if ( !xencoded_string_ptr::IsNull(&myContext->m_storyboardTelemetryName.m_encodedStorage) )
  {
    ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)&xstring_ptr_constants::c_xstring_ptr_storage_null;
    v47 = L",SB:";
    v48 = 1073741828;
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&ppStowedExceptions);
    ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)&v47;
    v36 = TStringBuilder<96>::Append(&telemetryBuilder, (const xstring_ptr_view *)&ppStowedExceptions);
    v37 = v36;
    if ( v36 < 0 )
    {
      OnFailure_2990_(v36);
      propertyName.m_encodedStorage.Storage = 0;
      LODWORD(cStowedExceptions) = 0;
      TraceForFailFast(v37);
      GetStowedExceptionsForFailFast(
        (_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertyName,
        (unsigned int *)&cStowedExceptions);
      RoFailFastWithErrorContextInternal2(
        v37,
        (unsigned int)cStowedExceptions,
        (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertyName.m_encodedStorage.Storage);
    }
    v38 = TStringBuilder<96>::Append(&telemetryBuilder, p_m_storyboardTelemetryName);
    v39 = v38;
    if ( v38 < 0 )
    {
      OnFailure_2990_(v38);
      propertyName.m_encodedStorage.Storage = 0;
      LODWORD(cStowedExceptions) = 0;
      TraceForFailFast(v39);
      GetStowedExceptionsForFailFast(
        (_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertyName,
        (unsigned int *)&cStowedExceptions);
      RoFailFastWithErrorContextInternal2(
        v39,
        (unsigned int)cStowedExceptions,
        (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertyName.m_encodedStorage.Storage);
    }
  }
  m_ref_count = this->m_targetObjectWeakRef.m_ref_count;
  m_ptr = 0;
  propertyName.m_encodedStorage.Storage = 0;
  if ( m_ref_count )
  {
    Value = m_ref_count->m_strong._Storage._Value;
    while ( Value )
    {
      v8 = Value;
      Value = _InterlockedCompareExchange((volatile signed __int32 *)m_ref_count, Value + 1, Value);
      if ( v8 == Value )
      {
        m_ptr = this->m_targetObjectWeakRef.m_ptr;
        propertyName.m_encodedStorage.Storage = (const xstring_ptr_storage *)m_ptr;
        break;
      }
    }
  }
  xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&propertyName);
  if ( m_ptr )
  {
    IsNull = xencoded_string_ptr::IsNull(&m_ptr->m_strName.m_encodedStorage);
    ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)&xstring_ptr_constants::c_xstring_ptr_storage_null;
    if ( IsNull )
    {
      v48 = 1073741839;
      v47 = L",Unnamed target";
      xencoded_string_ptr::Reset((xruntime_string_ptr *)&ppStowedExceptions);
      ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)&v47;
      v27 = TStringBuilder<96>::Append(&telemetryBuilder, (const xstring_ptr_view *)&ppStowedExceptions);
      v28 = v27;
      if ( v27 >= 0 )
      {
LABEL_38:
        CDependencyObject::GetUIPathForTracing(m_ptr, (xstring_ptr *)&ppStowedExceptions, 1);
        v29 = TStringBuilder<96>::Append(&telemetryBuilder, (const xstring_ptr_view *)&ppStowedExceptions);
        v30 = v29;
        if ( v29 < 0 )
        {
          OnFailure_2990_(v29);
          propertyName.m_encodedStorage.Storage = 0;
          LODWORD(cStowedExceptions) = 0;
          TraceForFailFast(v30);
          GetStowedExceptionsForFailFast(
            (_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertyName,
            (unsigned int *)&cStowedExceptions);
          RoFailFastWithErrorContextInternal2(
            v30,
            (unsigned int)cStowedExceptions,
            (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertyName.m_encodedStorage.Storage);
        }
        xstring_ptr::~xstring_ptr((xstring_ptr *)&ppStowedExceptions);
        goto LABEL_8;
      }
    }
    else
    {
      v48 = 1073741832;
      v47 = L",Target:";
      xencoded_string_ptr::Reset((xruntime_string_ptr *)&ppStowedExceptions);
      ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)&v47;
      v25 = TStringBuilder<96>::Append(&telemetryBuilder, (const xstring_ptr_view *)&ppStowedExceptions);
      v26 = v25;
      if ( v25 < 0 )
      {
        OnFailure_2990_(v25);
        propertyName.m_encodedStorage.Storage = 0;
        LODWORD(cStowedExceptions) = 0;
        TraceForFailFast(v26);
        GetStowedExceptionsForFailFast(
          (_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertyName,
          (unsigned int *)&cStowedExceptions);
        RoFailFastWithErrorContextInternal2(
          v26,
          (unsigned int)cStowedExceptions,
          (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertyName.m_encodedStorage.Storage);
      }
      v27 = TStringBuilder<96>::Append(&telemetryBuilder, &m_ptr->m_strName);
      v28 = v27;
      if ( v27 >= 0 )
        goto LABEL_38;
    }
    OnFailure_2990_(v27);
    LODWORD(cStowedExceptions) = 0;
    propertyName.m_encodedStorage.Storage = 0;
    TraceForFailFast(v28);
    GetStowedExceptionsForFailFast(
      (_STOWED_EXCEPTION_INFORMATION_V2 ***)&propertyName,
      (unsigned int *)&cStowedExceptions);
    RoFailFastWithErrorContextInternal2(
      v28,
      (unsigned int)cStowedExceptions,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)propertyName.m_encodedStorage.Storage);
    goto LABEL_38;
  }
LABEL_8:
  m_pTargetDependencyProperty = this->m_pTargetDependencyProperty;
  if ( m_pTargetDependencyProperty )
  {
    m_nIndex = (unsigned __int16)m_pTargetDependencyProperty->m_nIndex;
    if ( (unsigned __int16)m_nIndex >= 0x82Fu )
    {
      if ( (m_pTargetDependencyProperty->m_flags & 0x1000) != 0 || (m_pTargetDependencyProperty->m_flags & 0x800) != 0 )
        xstring_ptr::xstring_ptr(&propertyName, (const xstring_ptr *)&m_pTargetDependencyProperty[1]);
      else
        propertyName.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
    }
    else
    {
      propertyName.m_encodedStorage.Storage = &c_aPropertyNames[m_nIndex];
    }
    ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)&xstring_ptr_constants::c_xstring_ptr_storage_null;
    v47 = L",Prop:";
    v48 = 1073741830;
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&ppStowedExceptions);
    ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)&v47;
    v32 = TStringBuilder<96>::Append(&telemetryBuilder, (const xstring_ptr_view *)&ppStowedExceptions);
    v33 = v32;
    if ( v32 < 0 )
    {
      OnFailure_2990_(v32);
      ppStowedExceptions = 0;
      LODWORD(cStowedExceptions) = 0;
      TraceForFailFast(v33);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
      RoFailFastWithErrorContextInternal2(v33, (unsigned int)cStowedExceptions, ppStowedExceptions);
    }
    v34 = TStringBuilder<96>::Append(&telemetryBuilder, &propertyName);
    v35 = v34;
    if ( v34 < 0 )
    {
      OnFailure_2990_(v34);
      ppStowedExceptions = 0;
      LODWORD(cStowedExceptions) = 0;
      TraceForFailFast(v35);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
      RoFailFastWithErrorContextInternal2(v35, (unsigned int)cStowedExceptions, ppStowedExceptions);
    }
    xstring_ptr::~xstring_ptr(&propertyName);
  }
  m_cActual = telemetryBuilder.m_cActual;
  propertyName.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  if ( !telemetryBuilder.m_cActual )
  {
    v13 = 0;
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&propertyName);
    goto LABEL_53;
  }
  if ( telemetryBuilder.m_pBuffer != telemetryBuilder.m_inlineBuffer )
  {
    cStowedExceptions = 0;
    v40 = WindowsPromoteStringBuffer(telemetryBuilder.m_hPreallocatedBuffer, &cStowedExceptions);
    v13 = v40;
    if ( v40 < 0 )
    {
      OnFailure_2990_(v40);
      goto LABEL_64;
    }
    telemetryBuilder.m_hPreallocatedBuffer = 0;
    StringLen = WindowsGetStringLen(cStowedExceptions);
    if ( StringLen == telemetryBuilder.m_cActual )
      v42 = xstring_ptr::CloneRuntimeStringHandle(cStowedExceptions, &propertyName);
    else
      v42 = xstring_ptr::CloneBuffer(telemetryBuilder.m_pBuffer, telemetryBuilder.m_cActual, &propertyName);
    v13 = v42;
    WindowsDeleteString(cStowedExceptions);
    if ( v13 < 0 )
    {
      OnFailure_2990_(v13);
      RuntimeStringHandleMarker = propertyName.m_encodedStorage.RuntimeStringHandleMarker;
      goto LABEL_64;
    }
LABEL_53:
    RuntimeStringHandleMarker = propertyName.m_encodedStorage.RuntimeStringHandleMarker;
LABEL_14:
    *(_QWORD *)&telemetryBuilder.m_cBuffer = 96;
    telemetryBuilder.m_pBuffer = telemetryBuilder.m_inlineBuffer;
    if ( v13 >= 0 )
      goto LABEL_15;
    goto LABEL_64;
  }
  ppStowedExceptions = 0;
  LODWORD(v47) = 0;
  if ( telemetryBuilder.m_cActual > 0x3FFFFFFF )
  {
    v13 = -2147467259;
    v12 = -2147467259;
    OnNewFailure_1208_((HRESULT)telemetryBuilder.m_pBuffer);
  }
  else
  {
    String = WindowsCreateString(telemetryBuilder.m_pBuffer, telemetryBuilder.m_cActual, (HSTRING *)&ppStowedExceptions);
    v12 = String;
    if ( String >= 0 )
    {
      RuntimeStringHandleMarker = (unsigned __int64)ppStowedExceptions | 1;
      LODWORD(v47) = m_cActual & 0x3FFFFFFF | 0x80000000;
      xencoded_string_ptr::Reset((xruntime_string_ptr *)&propertyName);
      propertyName.m_encodedStorage.Storage = (const xstring_ptr_storage *)RuntimeStringHandleMarker;
      v13 = v12;
      goto LABEL_14;
    }
    OnFailure_2990_(String);
    v13 = v12;
  }
  OnFailure_2990_(v12);
LABEL_64:
  OnFailure_2990_(v13);
  ppStowedExceptions = 0;
  LODWORD(cStowedExceptions) = 0;
  TraceForFailFast(v13);
  GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
  RoFailFastWithErrorContextInternal2(v13, (unsigned int)cStowedExceptions, ppStowedExceptions);
LABEL_15:
  if ( xencoded_string_ptr::IsNull(&propertyName.m_encodedStorage) )
  {
    ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)xstring_ptr_constants::c_xencoded_string_ptr_empty.Storage;
    xstring_ptr::operator=(&propertyName, (xstring_ptr *)&ppStowedExceptions);
    xstring_ptr::~xstring_ptr((xstring_ptr *)&ppStowedExceptions);
    RuntimeStringHandleMarker = propertyName.m_encodedStorage.RuntimeStringHandleMarker;
  }
  ptr = this->m_spWUCAnimation.ptr_;
  animationAsCO.ptr_ = 0;
  QueryInterface = ptr->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&animationAsCO);
  QueryInterface(ptr, &GUID_ef874ea1_5cff_4b68_9e30_a1519d08ba03, (void **)&animationAsCO.ptr_);
  if ( (RuntimeStringHandleMarker & 1) != 0 )
  {
    v43 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
LABEL_66:
    StringRawBuffer = WindowsGetStringRawBuffer(v43, 0);
    goto LABEL_20;
  }
  if ( *(int *)(RuntimeStringHandleMarker + 8) < 0 )
  {
    v43 = *(HSTRING *)RuntimeStringHandleMarker;
    goto LABEL_66;
  }
  StringRawBuffer = *(const wchar_t **)RuntimeStringHandleMarker;
LABEL_20:
  telemetryString.hstr_ = 0;
  v17 = -1;
  do
    ++v17;
  while ( StringRawBuffer[v17] );
  if ( v17 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v18 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v17);
  v19 = v18 - 1;
  if ( (unsigned int)v17 < v18 )
    v19 = v17;
  StringReference = WindowsCreateStringReference(StringRawBuffer, v19, &telemetryString.header_, &telemetryString.hstr_);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  v21 = animationAsCO.ptr_->put_Comment(animationAsCO.ptr_, telemetryString.hstr_);
  v22 = v21;
  if ( v21 < 0 )
  {
    OnFailure_2990_(v21);
    ppStowedExceptions = 0;
    LODWORD(cStowedExceptions) = 0;
    TraceForFailFast(v22);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v22, (unsigned int)cStowedExceptions, ppStowedExceptions);
  }
  v23 = animationAsCO.ptr_;
  telemetryString.hstr_ = 0;
  if ( animationAsCO.ptr_ )
  {
    animationAsCO.ptr_ = 0;
    v23->Release(v23);
  }
  xstring_ptr::~xstring_ptr(&propertyName);
  if ( telemetryBuilder.m_pBuffer != telemetryBuilder.m_inlineBuffer )
    WindowsDeleteStringBuffer(telemetryBuilder.m_hPreallocatedBuffer);
}

```

## disassembly

```asm
0x180193d94  mov     [rsp-8+arg_10], rbx
0x180193d99  mov     [rsp-8+arg_18], rsi
0x180193d9e  push    rbp
0x180193d9f  push    rdi
0x180193da0  push    r12
0x180193da2  push    r14
0x180193da4  push    r15
0x180193da6  lea     rbp, [rsp-60h]
0x180193dab  sub     rsp, 160h
0x180193db2  mov     rax, cs:__security_cookie
0x180193db9  xor     rax, rsp
0x180193dbc  mov     [rbp+80h+var_30], rax
0x180193dc0  lea     rsi, [myContext+0ACh]
0x180193dc7  mov     qword ptr [rbp+80h+telemetryBuilder.m_cBuffer], 60h ; '`'
0x180193dcf  mov     r15, this
0x180193dd2  lea     rax, [rbp+80h+telemetryBuilder.m_inlineBuffer]
0x180193dd6  xor     r12d, r12d
0x180193dd9  mov     [rsp+180h+telemetryBuilder.m_pBuffer], rax
0x180193dde  mov     this, rsi; this
0x180193de1  mov     [rsp+180h+telemetryBuilder.m_hPreallocatedBuffer], r12
0x180193de6  call    ?IsNull@xencoded_string_ptr@@QEBA_NXZ; xencoded_string_ptr::IsNull(void)
0x180193deb  lea     rbx, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x180193df2  test    al, al
0x180193df4  jz      loc_18019415C
0x180193dfa  mov     myContext, [r15+0D8h]
0x180193e01  mov     rdi, r12
0x180193e04  mov     qword ptr [rsp+180h+propertyName.m_encodedStorage.___u0], r12
0x180193e09  test    myContext, myContext
0x180193e0c  jz      short loc_180193E2A
0x180193e0e  mov     eax, [myContext]
0x180193e10  nop
0x180193e11  test    eax, eax
0x180193e13  jz      short loc_180193E2A
0x180193e15  lea     ecx, [rax+1]
0x180193e18  lock cmpxchg [myContext], ecx
0x180193e1c  jnz     short loc_180193E11
0x180193e1e  mov     rdi, [r15+0D0h]
0x180193e25  mov     qword ptr [rsp+180h+propertyName.m_encodedStorage.___u0], rdi
0x180193e2a  lea     this, [rsp+180h+propertyName]; this
0x180193e2f  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x180193e34  test    rdi, rdi
0x180193e37  jnz     loc_180194022
0x180193e3d  mov     myContext, [r15+0E8h]
0x180193e44  test    myContext, myContext
0x180193e47  jnz     loc_1801940C9
0x180193e4d  mov     edi, [rbp+80h+telemetryBuilder.m_cActual]
0x180193e50  mov     qword ptr [rsp+180h+propertyName.m_encodedStorage.___u0], rbx
0x180193e55  test    edi, edi
0x180193e57  jz      loc_1801941F6
0x180193e5d  mov     this, [rsp+180h+telemetryBuilder.m_pBuffer]; failedFrameHR
0x180193e62  lea     rax, [rbp+80h+telemetryBuilder.m_inlineBuffer]
0x180193e66  cmp     this, rax
0x180193e69  jnz     loc_180194279
0x180193e6f  xor     eax, eax
0x180193e71  mov     r14d, 3FFFFFFFh
0x180193e77  mov     [rsp+180h+ppStowedExceptions], rax
0x180193e7c  mov     dword ptr [rsp+180h+var_148], eax
0x180193e80  cmp     edi, r14d
0x180193e83  ja      loc_18019434E
0x180193e89  lea     r8, [rsp+180h+ppStowedExceptions]; string
0x180193e8e  mov     edx, edi; length
0x180193e90  call    cs:__imp_WindowsCreateString
0x180193e96  mov     esi, eax
0x180193e98  test    eax, eax
0x180193e9a  js      loc_180194337
0x180193ea0  mov     rbx, [rsp+180h+ppStowedExceptions]
0x180193ea5  lea     this, [rsp+180h+propertyName]; this
0x180193eaa  and     edi, r14d
0x180193ead  or      rbx, 1
0x180193eb1  bts     edi, 1Fh
0x180193eb5  mov     dword ptr [rsp+180h+var_148], edi
0x180193eb9  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x180193ebe  mov     qword ptr [rsp+180h+propertyName.m_encodedStorage.___u0], rbx
0x180193ec3  mov     edi, esi
0x180193ec5  lea     rax, [rbp+80h+telemetryBuilder.m_inlineBuffer]
0x180193ec9  mov     qword ptr [rbp+80h+telemetryBuilder.m_cBuffer], 60h ; '`'
0x180193ed1  mov     [rsp+180h+telemetryBuilder.m_pBuffer], rax
0x180193ed6  test    edi, edi
0x180193ed8  js      loc_1801942E3
0x180193ede  lea     this, [rsp+180h+propertyName]; this
0x180193ee3  call    ?IsNull@xencoded_string_ptr@@QEBA_NXZ; xencoded_string_ptr::IsNull(void)
0x180193ee8  test    al, al
0x180193eea  jnz     loc_1801944FD
0x180193ef0  mov     rsi, [r15+160h]
0x180193ef7  lea     this, [rsp+180h+animationAsCO]; this
0x180193efc  mov     [rsp+180h+animationAsCO.ptr_], r12
0x180193f01  mov     rax, [rsi]
0x180193f04  mov     rdi, [rax]
0x180193f07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180193f0c  lea     r8, [rsp+180h+animationAsCO]
0x180193f11  mov     this, rsi
0x180193f14  lea     myContext, _GUID_ef874ea1_5cff_4b68_9e30_a1519d08ba03
0x180193f1b  mov     rax, rdi
0x180193f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193f23  test    bl, 1
0x180193f26  jnz     loc_180194320
0x180193f2c  cmp     [rbx+8], r12d
0x180193f30  jl      loc_180194349
0x180193f36  mov     rdi, [rbx]
0x180193f39  mov     [rsp+180h+telemetryString.hstr_], r12
0x180193f3e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180193f42  inc     rbx
0x180193f45  cmp     [rdi+rbx*2], r12w
0x180193f4a  jnz     short loc_180193F42
0x180193f4c  mov     eax, 0FFFFFFFFh
0x180193f51  cmp     rbx, rax
0x180193f54  ja      loc_18019400C
0x180193f5a  mov     ecx, ebx; augend
0x180193f5c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180193f61  cmp     ebx, eax
0x180193f63  lea     r9, [rsp+180h+telemetryString.hstr_]; string
0x180193f68  lea     r8, [rsp+180h+telemetryString]; hstringHeader
0x180193f6d  mov     this, rdi; sourceString
0x180193f70  lea     edx, [rax-1]
0x180193f73  cmovb   edx, ebx; length
0x180193f76  call    cs:__imp_WindowsCreateStringReference
0x180193f7c  test    eax, eax
0x180193f7e  js      loc_18019452C
0x180193f84  mov     this, [rsp+180h+animationAsCO.ptr_]
0x180193f89  mov     myContext, [rsp+180h+telemetryString.hstr_]
0x180193f8e  mov     rax, [this]
0x180193f91  mov     rax, [rax+38h]
0x180193f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193f9a  mov     ebx, eax
0x180193f9c  test    eax, eax
0x180193f9e  js      loc_18019453F
0x180193fa4  mov     this, [rsp+180h+animationAsCO.ptr_]
0x180193fa9  mov     [rsp+180h+telemetryString.hstr_], r12
0x180193fae  test    this, this
0x180193fb1  jz      short loc_180193FC4
0x180193fb3  mov     [rsp+180h+animationAsCO.ptr_], r12
0x180193fb8  mov     rax, [this]
0x180193fbb  mov     rax, [rax+10h]
0x180193fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193fc4  lea     this, [rsp+180h+propertyName]; this
0x180193fc9  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180193fce  lea     rax, [rbp+80h+telemetryBuilder.m_inlineBuffer]
0x180193fd2  cmp     [rsp+180h+telemetryBuilder.m_pBuffer], rax
0x180193fd7  jz      short loc_180193FE4
0x180193fd9  mov     this, [rsp+180h+telemetryBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180193fde  call    cs:__imp_WindowsDeleteStringBuffer
0x180193fe4  mov     this, [rbp+80h+var_30]
0x180193fe8  xor     this, rsp; StackCookie
0x180193feb  call    __security_check_cookie
0x180193ff0  lea     r11, [rsp+180h+var_20]
0x180193ff8  mov     rbx, [r11+40h]
0x180193ffc  mov     rsi, [r11+48h]
0x180194000  mov     rsp, r11
0x180194003  pop     r15
0x180194005  pop     r14
0x180194007  pop     r12
0x180194009  pop     rdi
0x18019400a  pop     rbp
0x18019400b  retn
0x18019400c  xor     r9d, r9d; lpArguments
0x18019400f  xor     r8d, r8d; nNumberOfArguments
0x180194012  mov     ecx, 80070216h; dwExceptionCode
0x180194017  lea     edx, [r9+1]; dwExceptionFlags
0x18019401b  call    cs:__imp_RaiseException
0x180194021  int     3; Trap to Debugger
0x180194022  lea     this, [rdi+18h]; this
0x180194026  call    ?IsNull@xencoded_string_ptr@@QEBA_NXZ; xencoded_string_ptr::IsNull(void)
0x18019402b  mov     [rsp+180h+ppStowedExceptions], rbx
0x180194030  lea     this, [rsp+180h+ppStowedExceptions]; this
0x180194035  test    al, al
0x180194037  jnz     loc_180194231
0x18019403d  lea     rax, aTarget_1; ",Target:"
0x180194044  mov     [rsp+180h+var_140], 40000008h
0x18019404c  mov     [rsp+180h+var_148], rax
0x180194051  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x180194056  lea     rax, [rsp+180h+var_148]
0x18019405b  lea     myContext, [rsp+180h+ppStowedExceptions]; strToAppend
0x180194060  mov     [rsp+180h+ppStowedExceptions], rax
0x180194065  lea     this, [rsp+180h+telemetryBuilder]; this
0x18019406a  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x18019406f  mov     esi, eax
0x180194071  test    eax, eax
0x180194073  js      loc_1801943CC
0x180194079  lea     myContext, [rdi+18h]; strToAppend
0x18019407d  lea     this, [rsp+180h+telemetryBuilder]; this
0x180194082  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x180194087  mov     esi, eax
0x180194089  test    eax, eax
0x18019408b  js      loc_180194409
0x180194091  mov     r8b, 1; followDOParentChain
0x180194094  lea     myContext, [rsp+180h+ppStowedExceptions]; result
0x180194099  mov     this, rdi; this
0x18019409c  call    ?GetUIPathForTracing@CDependencyObject@@QEAA?AVxstring_ptr@@_N@Z; CDependencyObject::GetUIPathForTracing(bool)
0x1801940a1  lea     myContext, [rsp+180h+ppStowedExceptions]; strToAppend
0x1801940a6  lea     this, [rsp+180h+telemetryBuilder]; this
0x1801940ab  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x1801940b0  mov     edi, eax
0x1801940b2  test    eax, eax
0x1801940b4  js      loc_180194446
0x1801940ba  lea     this, [rsp+180h+ppStowedExceptions]; this
0x1801940bf  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801940c4  jmp     loc_180193E3D
0x1801940c9  movzx   eax, word ptr [myContext]
0x1801940cc  mov     ecx, 82Fh
0x1801940d1  cmp     ax, cx
0x1801940d4  jnb     loc_18019420D
0x1801940da  lea     this, [rax+rax*2]
0x1801940de  lea     rax, ?c_aPropertyNames@@3QBUxstring_ptr_storage@@B; xstring_ptr_storage const near * const c_aPropertyNames
0x1801940e5  lea     rax, [rax+this*4]
0x1801940e9  mov     qword ptr [rsp+180h+propertyName.m_encodedStorage.___u0], rax
0x1801940ee  lea     rax, aProp; ",Prop:"
0x1801940f5  mov     [rsp+180h+ppStowedExceptions], rbx
0x1801940fa  lea     this, [rsp+180h+ppStowedExceptions]; this
0x1801940ff  mov     [rsp+180h+var_148], rax
0x180194104  mov     [rsp+180h+var_140], 40000006h
0x18019410c  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x180194111  lea     rax, [rsp+180h+var_148]
0x180194116  lea     myContext, [rsp+180h+ppStowedExceptions]; strToAppend
0x18019411b  mov     [rsp+180h+ppStowedExceptions], rax
0x180194120  lea     this, [rsp+180h+telemetryBuilder]; this
0x180194125  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x18019412a  mov     edi, eax
0x18019412c  test    eax, eax
0x18019412e  js      loc_180194483
0x180194134  lea     myContext, [rsp+180h+propertyName]; strToAppend
0x180194139  lea     this, [rsp+180h+telemetryBuilder]; this
0x18019413e  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x180194143  mov     edi, eax
0x180194145  test    eax, eax
0x180194147  js      loc_1801944C0
0x18019414d  lea     this, [rsp+180h+propertyName]; this
0x180194152  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180194157  jmp     loc_180193E4D
0x18019415c  lea     rax, aSb; ",SB:"
0x180194163  mov     [rsp+180h+ppStowedExceptions], rbx
0x180194168  lea     this, [rsp+180h+ppStowedExceptions]; this
0x18019416d  mov     [rsp+180h+var_148], rax
0x180194172  mov     [rsp+180h+var_140], 40000004h
0x18019417a  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18019417f  lea     rax, [rsp+180h+var_148]
0x180194184  lea     myContext, [rsp+180h+ppStowedExceptions]; strToAppend
0x180194189  mov     [rsp+180h+ppStowedExceptions], rax
0x18019418e  lea     this, [rsp+180h+telemetryBuilder]; this
0x180194193  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x180194198  mov     edi, eax
0x18019419a  test    eax, eax
0x18019419c  js      loc_18019438F
0x1801941a2  mov     myContext, rsi; strToAppend
0x1801941a5  lea     this, [rsp+180h+telemetryBuilder]; this
0x1801941aa  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x1801941af  mov     edi, eax
0x1801941b1  test    eax, eax
0x1801941b3  jns     loc_180193DFA
0x1801941b9  mov     ecx, eax; failedFrameHR
0x1801941bb  call    OnFailure_2990_
0x1801941c0  mov     ecx, edi; errorCode
0x1801941c2  mov     qword ptr [rsp+180h+propertyName.m_encodedStorage.___u0], r12
0x1801941c7  mov     dword ptr [rsp+180h+cStowedExceptions], r12d
0x1801941cc  call    TraceForFailFast
0x1801941d1  lea     myContext, [rsp+180h+cStowedExceptions]; pcStowedExceptions
0x1801941d6  lea     this, [rsp+180h+propertyName]; pppStowedExceptions
0x1801941db  call    GetStowedExceptionsForFailFast
0x1801941e0  mov     r8, qword ptr [rsp+180h+propertyName.m_encodedStorage.___u0]
0x1801941e5  mov     ecx, edi
0x1801941e7  mov     edx, dword ptr [rsp+180h+cStowedExceptions]
0x1801941eb  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1801941f1  jmp     loc_180193DFA
0x1801941f6  lea     this, [rsp+180h+propertyName]; this
0x1801941fb  mov     edi, r12d
0x1801941fe  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x180194203  mov     rbx, qword ptr [rsp+180h+propertyName.m_encodedStorage.___u0]
0x180194208  jmp     loc_180193EC5
0x18019420d  test    dword ptr [myContext+8], 1000h
0x180194214  jnz     loc_18019435C
0x18019421a  test    dword ptr [myContext+8], 800h
0x180194221  jnz     loc_18019435C
0x180194227  mov     qword ptr [rsp+180h+propertyName.m_encodedStorage.___u0], rbx
0x18019422c  jmp     loc_1801940EE
0x180194231  lea     rax, aUnnamedTarget_0; ",Unnamed target"
0x180194238  mov     [rsp+180h+var_140], 4000000Fh
0x180194240  mov     [rsp+180h+var_148], rax
0x180194245  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18019424a  lea     rax, [rsp+180h+var_148]
0x18019424f  lea     myContext, [rsp+180h+ppStowedExceptions]; strToAppend
0x180194254  mov     [rsp+180h+ppStowedExceptions], rax
0x180194259  lea     this, [rsp+180h+telemetryBuilder]; this
0x18019425e  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x180194263  mov     esi, eax
0x180194265  test    eax, eax
0x180194267  jns     loc_180194091
0x18019426d  mov     ecx, eax; failedFrameHR
0x18019426f  call    OnFailure_2990_
0x180194274  jmp     loc_180194410
0x180194279  mov     this, [rsp+180h+telemetryBuilder.m_hPreallocatedBuffer]; bufferHandle
0x18019427e  lea     myContext, [rsp+180h+cStowedExceptions]; string
0x180194283  mov     [rsp+180h+cStowedExceptions], r12
0x180194288  call    cs:__imp_WindowsPromoteStringBuffer
0x18019428e  mov     edi, eax
0x180194290  test    eax, eax
0x180194292  js      loc_18019436F
0x180194298  mov     this, [rsp+180h+cStowedExceptions]; string
0x18019429d  mov     [rsp+180h+telemetryBuilder.m_hPreallocatedBuffer], r12
0x1801942a2  call    cs:__imp_WindowsGetStringLen
0x1801942a8  mov     edx, [rbp+80h+telemetryBuilder.m_cActual]; count
0x1801942ab  cmp     eax, edx
  ... truncated ...
```
