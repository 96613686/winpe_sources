# BinaryFormatObjectWriter::ProvideStaticResourceReference(ObjectWriterNode const &,CStyle *,KnownPropertyIndex)

- ea: `0x1800a535c`
- end: `0x1800a5c84`
- name: `?ProvideStaticResourceReference@BinaryFormatObjectWriter@@QEAAJAEBVObjectWriterNode@@PEAVCStyle@@W4KnownPropertyIndex@@@Z`
- size: `2344`
- prototype: `HRESULT __fastcall(BinaryFormatObjectWriter *this, const ObjectWriterNode *node, CStyle *optimizedStyleParent, KnownPropertyIndex stylePropertyIndex)`
- caller_count: `2`
- callee_count: `27`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a487c`
- `0x1800b0e90`

## callees

- `0x180004bc0`
- `0x180021840`
- `0x180021970`
- `0x18004755c`
- `0x18004b99c`
- `0x1800710d0`
- `0x180073990`
- `0x180074204`
- `0x180075c70`
- `0x1800a26f0`
- `0x1800a5248`
- `0x1800a52b0`
- `0x1800a535c`
- `0x1800a7ba0`
- `0x1800aabf0`
- `0x1800ab600`
- `0x1800af8e0`
- `0x1800fe130`
- `0x1801758d4`
- `0x1802ec53c`
- `0x18037aaa4`
- `0x1806877a8`
- `0x180687890`
- `0x180687a78`
- `0x180688828`
- `0x1806ba4c4`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5b9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5c42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5b9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5c42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a54b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5676`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a54b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5676`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800a59f8`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800a5a08`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800a59f8`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800a5a08`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800a5a52`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800a5a52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a590c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a59be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a590c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a59be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800a59d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800a59d5`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=19
__int64 __fastcall BinaryFormatObjectWriter::ProvideStaticResourceReference(
        BinaryFormatObjectWriter *this,
        const ObjectWriterNode *node,
        CStyle *optimizedStyleParent,
        KnownPropertyIndex stylePropertyIndex)
{
  XamlQualifiedObject *Ptr; // r8
  const xstring_ptr_storage *Storage; // rax
  const xstring_ptr_storage *v8; // rbx
  HRESULT v9; // ecx
  ObjectWriterContext *v10; // r8
  XamlSchemaContext *v11; // rsi
  std::_Ref_count_base *v12; // r15
  std::_Ref_count_base *Rep; // rdx
  signed __int32 Uses; // eax
  signed __int32 v15; // ett
  CCoreServices *v16; // r14
  const std::shared_ptr<DirectUI::CTimedTextSource::CTrackTokens> *v17; // rdi
  HANDLE ProcessHeap; // rax
  std::shared_ptr<DirectUI::CTimedTextSource::CTrackTokens> *v19; // rax
  std::shared_ptr<DirectUI::CTimedTextSource::CTrackTokens> *v20; // rbx
  std::_Ref_count_base *v21; // rbx
  HRESULT v22; // ecx
  HRESULT XamlType; // edi
  std::_Ref_count_base *v24; // rbx
  CDependencyObject *v25; // rbx
  CDependencyObject *v26; // rbx
  KnownTypeIndex v27; // di
  KnownTypeIndex v28; // ax
  const CClassInfo *ClassInfoByIndex; // rax
  HANDLE v30; // rax
  HSTRING v31; // rax
  HSTRING v32; // r14
  XamlQualifiedObject *v33; // r13
  int v34; // ebx
  int v35; // edi
  KnownTypeIndex v36; // ax
  KnownTypeIndex i; // cx
  const CClassInfo *v38; // rax
  char v39; // al
  std::_Ref_count_base *v40; // rbx
  std::_Ref_count_base *v41; // rbx
  std::_Ref_count_base *v42; // rbx
  std::_Ref_count_base *v43; // rdi
  std::shared_ptr<PointerSourceWrapper> *NullKeyedResourceXQO; // rax
  HRESULT XamlTypeFromStableXbfIndex; // eax
  unsigned int v47; // ebx
  HRESULT v48; // ebx
  HRESULT v49; // eax
  xstring_ptr staticResourceKey; // [rsp+40h] [rbp-69h] BYREF
  CDependencyObject *pObjectNoRef; // [rsp+48h] [rbp-61h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+50h] [rbp-59h] BYREF
  wil::details::ScopeExitFn<<lambda_23cba402eb3cef085f551b0b2df12626> > traceGuard; // [rsp+58h] [rbp-51h] BYREF
  std::shared_ptr<XamlType> spXamlType; // [rsp+70h] [rbp-39h] BYREF
  HSTRING newString[2]; // [rsp+80h] [rbp-29h] BYREF
  std::shared_ptr<Diagnostics::ResourceDependency> result; // [rsp+90h] [rbp-19h] BYREF
  std::shared_ptr<XamlSchemaContext> spSchemaContext; // [rsp+A0h] [rbp-9h]
  std::shared_ptr<XamlQualifiedObject> qoValue; // [rsp+B0h] [rbp+7h]
  xstring_ptr typeToken; // [rsp+110h] [rbp+67h] OVERLAPPED BYREF
  xstring_ptr inTypeName; // [rsp+118h] [rbp+6Fh] BYREF
  CStyle *v61; // [rsp+120h] [rbp+77h]
  KnownPropertyIndex v62; // [rsp+128h] [rbp+7Fh]

  v62 = stylePropertyIndex;
  v61 = optimizedStyleParent;
  LODWORD(inTypeName.m_encodedStorage.Storage) = 0;
  if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x40000) != 0 )
    McTemplateMofU0(
      &WINDOWS_UI_XAML_ETW_PROVIDER_Context,
      &ProvideStaticResourceReferenceBegin,
      &ProvideStaticResourceReferenceId);
  spSchemaContext = 0;
  qoValue = 0;
  pObjectNoRef = 0;
  traceGuard.m_exitFunctor.pObjectNoRef = &pObjectNoRef;
  traceGuard.m_exitFunctor.__this = this;
  traceGuard.m_shouldRun = 1;
  Ptr = node->m_spValue._Ptr;
  Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
  typeToken.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
  if ( (*(_BYTE *)&Ptr->m_value.m_flags.m_state.0 & 0x3F) == 0xE )
  {
    typeToken.m_encodedStorage.Storage = (const xstring_ptr_storage *)Ptr->m_value.m_value;
    if ( ((__int64)typeToken.m_encodedStorage.Storage & 1) != 0 )
    {
      if ( WindowsDuplicateString(
             (HSTRING)(typeToken.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL),
             newString) < 0 )
      {
        pppStowedExceptions = 0;
        LODWORD(typeToken.m_encodedStorage.Storage) = 0;
        TraceForFailFast(-2147418113);
        OnNewFailureEncountered(-2147418113, 0, 0);
        GetStowedExceptionsForFailFast(&pppStowedExceptions, (unsigned int *)&typeToken);
        RoFailFastWithErrorContextInternal2(
          -2147418113,
          typeToken.m_encodedStorage.RuntimeStringHandleMarker,
          pppStowedExceptions);
      }
      v8 = (const xstring_ptr_storage *)((unsigned __int64)newString[0] | 1);
      Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    }
    else
    {
      v8 = typeToken.m_encodedStorage.Storage;
    }
    typeToken.m_encodedStorage.Storage = Storage;
    if ( ((__int64)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage & 1) != 0 )
      WindowsDeleteString((HSTRING)(xstring_ptr_constants::c_xencoded_string_ptr_null.RuntimeStringHandleMarker
                                  & 0xFFFFFFFFFFFFFFFEuLL));
    xstring_ptr::~xstring_ptr(&typeToken);
    typeToken.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    staticResourceKey.m_encodedStorage.Storage = v8;
    xstring_ptr::~xstring_ptr(&typeToken);
  }
  else
  {
    xstring_ptr::xstring_ptr(&staticResourceKey, &CValueDetails::ValueTypeInfo<14>::Empty);
    xstring_ptr::~xstring_ptr(&typeToken);
  }
  v10 = this->m_spContext._Ptr;
  v11 = 0;
  pppStowedExceptions = 0;
  v12 = 0;
  Rep = v10->m_SchemaContext._Rep;
  if ( Rep )
  {
    Uses = Rep->_Uses;
    while ( Uses )
    {
      v9 = Uses + 1;
      v15 = Uses;
      Uses = _InterlockedCompareExchange((volatile signed __int32 *)&Rep->_Uses, Uses + 1, Uses);
      if ( v15 == Uses )
      {
        v11 = v10->m_SchemaContext._Ptr;
        pppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)v11;
        v12 = v10->m_SchemaContext._Rep;
        break;
      }
    }
  }
  spSchemaContext._Ptr = v11;
  spSchemaContext._Rep = v12;
  if ( !v11 )
  {
    OnFailure_977_(v9);
    XamlType = -2147467259;
    OnFailure_2990_(-2147467259);
    xstring_ptr::~xstring_ptr(&staticResourceKey);
    traceGuard.m_shouldRun = 0;
    lambda_23cba402eb3cef085f551b0b2df12626_::operator()(&traceGuard);
LABEL_82:
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    return (unsigned int)XamlType;
  }
  v16 = (CCoreServices *)((__int64)&v11->m_pCore[-1] & -(__int64)(v11->m_pCore != 0));
  v17 = (const std::shared_ptr<DirectUI::CTimedTextSource::CTrackTokens> *)std::enable_shared_from_this<Diagnostics::ResourceDependency>::shared_from_this(
                                                                             (std::enable_shared_from_this<Diagnostics::ResourceDependency> *)&this->m_spContext._Ptr->std::enable_shared_from_this<ObjectWriterContext>,
                                                                             &result);
  ProcessHeap = ghHeap;
  if ( !ghHeap )
  {
    ProcessHeap = GetProcessHeap();
    ghHeap = ProcessHeap;
  }
  v19 = (std::shared_ptr<DirectUI::CTimedTextSource::CTrackTokens> *)HeapAlloc(ProcessHeap, 0, 0x20u);
  v20 = v19;
  if ( v19 )
  {
    _InterlockedAdd64(&g_allocatedMemory, 0x20u);
    LODWORD(v19->_Rep) = 1;
    HIDWORD(v19->_Rep) = 1;
    v19->_Ptr = (DirectUI::CTimedTextSource::CTrackTokens *)std::_Ref_count_obj2<XamlServiceProviderContext>::`vftable';
    std::shared_ptr<ObjectWriterStack>::shared_ptr<ObjectWriterStack>(v19 + 1, v17);
  }
  else
  {
    TerminateProcessOnMemoryExhaustion(0x20u);
    v20 = 0;
  }
  spXamlType._Ptr = (XamlType *)&v20[1];
  spXamlType._Rep = (std::_Ref_count_base *)v20;
  LODWORD(inTypeName.m_encodedStorage.Storage) = 5;
  v21 = result._Rep;
  if ( result._Rep )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&result._Rep->_Uses, 0xFFFFFFFF) == 1 )
    {
      v21->_Destroy(v21);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v21->_Weaks, 0xFFFFFFFF) == 1 )
        v21->_Delete_this(v21);
    }
  }
  XamlType = CStaticResourceExtension::LookupResourceNoRef(
               &staticResourceKey,
               (const std::shared_ptr<XamlServiceProviderContext> *)&spXamlType,
               v16,
               &pObjectNoRef,
               1u,
               v61,
               v62);
  v24 = spXamlType._Rep;
  if ( spXamlType._Rep )
  {
    v22 = _InterlockedExchangeAdd((volatile signed __int32 *)&spXamlType._Rep->_Uses, 0xFFFFFFFF);
    if ( v22 == 1 )
    {
      v24->_Destroy(v24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v24->_Weaks, 0xFFFFFFFF) == 1 )
        v24->_Delete_this(v24);
    }
  }
  if ( XamlType < 0 )
  {
    OnFailure_2990_(XamlType);
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&staticResourceKey);
    traceGuard.m_shouldRun = 0;
    lambda_23cba402eb3cef085f551b0b2df12626_::operator()(&traceGuard);
    goto LABEL_82;
  }
  v25 = pObjectNoRef;
  if ( !pObjectNoRef )
  {
    inTypeName.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    typeToken.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    v48 = CErrorService::OriginateInvalidOperationError(v16, 0x8E0u, &staticResourceKey, &typeToken, &inTypeName);
    xstring_ptr::~xstring_ptr(&typeToken);
    xstring_ptr::~xstring_ptr(&inTypeName);
    v49 = ObjectWriterErrorService::WrapErrorWithParserErrorAndRethrow(
            this->m_spErrorService._Ptr,
            v48,
            &node->m_LineInfo);
    v47 = v49;
    if ( v49 < 0 )
    {
      OnFailure_2990_(v49);
      xstring_ptr::~xstring_ptr(&staticResourceKey);
      traceGuard.m_shouldRun = 0;
      lambda_23cba402eb3cef085f551b0b2df12626_::operator()(&traceGuard);
      goto LABEL_101;
    }
    v25 = pObjectNoRef;
  }
  *(_OWORD *)newString = 0;
  spXamlType = 0;
  if ( v25 )
  {
    if ( CDependencyObject::OfTypeByIndex<220>(v25) )
    {
      NullKeyedResourceXQO = (std::shared_ptr<PointerSourceWrapper> *)XamlSchemaContext::get_NullKeyedResourceXQO(
                                                                        v11,
                                                                        (std::shared_ptr<XamlQualifiedObject> *)&result);
      std::shared_ptr<Diagnostics::ResourceDependency>::operator=(
        (std::shared_ptr<PointerSourceWrapper> *)newString,
        NullKeyedResourceXQO);
      if ( result._Rep )
        std::_Ref_count_base::_Decref(result._Rep);
      XamlTypeFromStableXbfIndex = XamlSchemaContext::GetXamlTypeFromStableXbfIndex(
                                     v11,
                                     ContentDialogButton,
                                     &spXamlType);
      v47 = XamlTypeFromStableXbfIndex;
      if ( XamlTypeFromStableXbfIndex >= 0 )
      {
        v32 = newString[1];
        v33 = (XamlQualifiedObject *)newString[0];
LABEL_54:
        if ( v32 )
          _InterlockedIncrement((volatile signed __int32 *)v32 + 2);
        this->m_qoLastInstance._Ptr = v33;
        v41 = this->m_qoLastInstance._Rep;
        this->m_qoLastInstance._Rep = (std::_Ref_count_base *)v32;
        if ( v41 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v41->_Uses, 0xFFFFFFFF) == 1 )
          {
            v41->_Destroy(v41);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v41->_Weaks, 0xFFFFFFFF) == 1 )
              v41->_Delete_this(v41);
          }
        }
        v42 = spXamlType._Rep;
        if ( spXamlType._Rep )
          _InterlockedIncrement((volatile signed __int32 *)&spXamlType._Rep->_Uses);
        this->m_qoLastType._Ptr = spXamlType._Ptr;
        v43 = this->m_qoLastType._Rep;
        this->m_qoLastType._Rep = v42;
        if ( v43 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v43->_Uses, 0xFFFFFFFF) == 1 )
          {
            v43->_Destroy(v43);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v43->_Weaks, 0xFFFFFFFF) == 1 )
              v43->_Delete_this(v43);
          }
        }
        if ( v42 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v42->_Uses, 0xFFFFFFFF) == 1 )
          {
            v42->_Destroy(v42);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v42->_Weaks, 0xFFFFFFFF) == 1 )
              v42->_Delete_this(v42);
          }
        }
        if ( v32 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v32 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(HSTRING))v32)(v32);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v32 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v32 + 8LL))(v32);
          }
        }
        if ( ((__int64)staticResourceKey.m_encodedStorage.Storage & 1) != 0 )
          WindowsDeleteString((HSTRING)(staticResourceKey.m_encodedStorage.RuntimeStringHandleMarker
                                      & 0xFFFFFFFFFFFFFFFEuLL));
        staticResourceKey.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
        traceGuard.m_shouldRun = 0;
        lambda_23cba402eb3cef085f551b0b2df12626_::operator()(&traceGuard);
        if ( v12 && _InterlockedExchangeAdd((volatile signed __int32 *)&v12->_Uses, 0xFFFFFFFF) == 1 )
        {
          v12->_Destroy(v12);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v12->_Weaks, 0xFFFFFFFF) == 1 )
            v12->_Delete_this(v12);
        }
        return 0;
      }
      OnFailure_2990_(XamlTypeFromStableXbfIndex);
      if ( spXamlType._Rep )
        std::_Ref_count_base::_Decref(spXamlType._Rep);
      if ( newString[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)newString[1]);
      xstring_ptr::~xstring_ptr(&staticResourceKey);
      traceGuard.m_shouldRun = 0;
      lambda_23cba402eb3cef085f551b0b2df12626_::operator()(&traceGuard);
      goto LABEL_101;
    }
    v26 = pObjectNoRef;
    if ( pObjectNoRef )
    {
      v27 = pObjectNoRef->GetTypeIndex(pObjectNoRef);
      v28 = v26->GetTypeIndex(v26);
      ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex(v28);
      if ( ClassInfoByIndex->m_nIndex == Enumerated || (ClassInfoByIndex->m_flags & 0x800) != 0 )
        v27 = WORD2(v26[1].__vftable);
      LODWORD(typeToken.m_encodedStorage.Storage) = (unsigned __int16)v27 | 0x10000000;
      v30 = ghHeap;
      if ( !ghHeap )
      {
        v30 = GetProcessHeap();
        ghHeap = v30;
      }
      v31 = (HSTRING)HeapAlloc(v30, 0, 0x28u);
      v32 = v31;
      if ( v31 )
      {
        _InterlockedAdd64(&g_allocatedMemory, 0x28u);
        *((_DWORD *)v31 + 2) = 1;
        *((_DWORD *)v31 + 3) = 1;
        *(_QWORD *)v31 = std::_Ref_count_obj2<XamlQualifiedObject>::`vftable';
        *((_DWORD *)v31 + 4) = (unsigned __int16)v27 | 0x10000000;
        *(_QWORD *)(v31 + 5) = 0;
        *(_QWORD *)(v31 + 7) = 0;
        *((_DWORD *)v31 + 9) = 0;
      }
      else
      {
        TerminateProcessOnMemoryExhaustion(0x28u);
        v32 = 0;
      }
      v33 = (XamlQualifiedObject *)(v32 + 4);
      newString[0] = v32 + 4;
      newString[1] = v32;
      v34 = (int)pObjectNoRef;
      v35 = HIDWORD(pObjectNoRef);
      CValue::ReleaseAndReset((CValue *)(v32 + 6));
      *((_DWORD *)v32 + 8) &= 0xFFFFFFD8;
      *((_DWORD *)v32 + 8) |= 0x58u;
      *((_DWORD *)v32 + 6) = v34;
      *((_DWORD *)v32 + 7) = v35;
      CValueDetails::ValueStores::RefCounted<24,CDependencyObject>::AddRef((CValue *)(v32 + 6));
      v36 = pObjectNoRef->GetTypeIndex(pObjectNoRef);
      if ( v36 == ExternalObjectReference )
        goto LABEL_46;
      if ( (unsigned __int16)v36 >= (XYFocusNavigationStrategy|IVectorOfUri) )
      {
        for ( i = v36; ; i = v38->m_nBaseTypeIndex )
        {
          v38 = DirectUI::MetadataAPI::GetClassInfoByIndex(i);
          if ( v38->m_nIndex == UnknownType )
            break;
          if ( v38->m_nIndex == ExternalObjectReference )
          {
            v39 = 1;
            goto LABEL_45;
          }
        }
        v39 = 0;
LABEL_45:
        if ( v39 )
LABEL_46:
          *((_DWORD *)v32 + 5) |= 0x10u;
      }
      inTypeName.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
      result = 0;
      XamlType = XamlSchemaContext::GetXamlType(
                   (XamlSchemaContext *)pppStowedExceptions,
                   (const XamlTypeToken *)&typeToken,
                   (const std::shared_ptr<XamlNamespace> *)&result,
                   &inTypeName,
                   &spXamlType);
      v40 = result._Rep;
      if ( result._Rep )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&result._Rep->_Uses, 0xFFFFFFFF) == 1 )
        {
          v40->_Destroy(v40);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v40->_Weaks, 0xFFFFFFFF) == 1 )
            v40->_Delete_this(v40);
        }
      }
      if ( ((__int64)inTypeName.m_encodedStorage.Storage & 1) != 0 )
        WindowsDeleteString((HSTRING)(inTypeName.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
      if ( XamlType >= 0 )
        goto LABEL_54;
      OnFailure_2990_(XamlType);
      if ( spXamlType._Rep )
        std::_Ref_count_base::_Decref(spXamlType._Rep);
      if ( v32 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v32);
      xstring_ptr::~xstring_ptr(&staticResourceKey);
      traceGuard.m_shouldRun = 0;
      lambda_23cba402eb3cef085f551b0b2df12626_::operator()(&traceGuard);
      goto LABEL_82;
    }
  }
  OnNewFailure_1172_(v22);
  v47 = -2147467261;
  OnFailure_2990_(-2147467261);
  xstring_ptr::~xstring_ptr(&staticResourceKey);
  traceGuard.m_shouldRun = 0;
  lambda_23cba402eb3cef085f551b0b2df12626_::operator()(&traceGuard);
LABEL_101:
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  return v47;
}

```

## disassembly

```asm
0x1800a535c  mov     [rsp-8+arg_18], stylePropertyIndex
0x1800a5362  mov     [rsp-8+arg_10], optimizedStyleParent
0x1800a5367  push    rbp
0x1800a5368  push    rbx
0x1800a5369  push    rsi
0x1800a536a  push    rdi
0x1800a536b  push    r12
0x1800a536d  push    r13
0x1800a536f  push    r14
0x1800a5371  push    r15
0x1800a5373  lea     rbp, [rsp-1Fh]
0x1800a5378  sub     rsp, 0C8h
0x1800a537f  mov     r13, node
0x1800a5382  mov     r12, this
0x1800a5385  xor     ebx, ebx
0x1800a5387  mov     dword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0], ebx
0x1800a538a  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits+2, 4
0x1800a5391  jnz     loc_1800A5A5A
0x1800a5397  xorps   xmm0, xmm0
0x1800a539a  movdqu  xmmword ptr [rbp+57h+spSchemaContext._Ptr], xmm0
0x1800a539f  movdqu  xmmword ptr [rbp+57h+qoValue._Ptr], xmm0
0x1800a53a4  mov     [rbp+57h+pObjectNoRef], rbx
0x1800a53a8  lea     rax, [rbp+57h+pObjectNoRef]
0x1800a53ac  mov     [rbp+57h+traceGuard.m_exitFunctor.pObjectNoRef], rax
0x1800a53b0  mov     [rbp+57h+traceGuard.m_exitFunctor.__this], r12
0x1800a53b4  mov     [rbp+57h+traceGuard.m_shouldRun], 1
0x1800a53b8  mov     optimizedStyleParent, [r13+70h]
0x1800a53bc  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800a53c3  mov     qword ptr [rbp+57h+typeToken.m_Data], rax
0x1800a53c7  mov     ecx, [optimizedStyleParent+10h]
0x1800a53cb  and     ecx, 3Fh
0x1800a53ce  cmp     cl, 0Eh
0x1800a53d1  jnz     loc_1800A5B7D
0x1800a53d7  mov     rdi, rax
0x1800a53da  mov     edx, [optimizedStyleParent+8]
0x1800a53de  mov     [rbp+57h+typeToken.m_Data], edx
0x1800a53e1  mov     ecx, [optimizedStyleParent+0Ch]
0x1800a53e5  mov     [rbp+57h+arg_4], ecx
0x1800a53e8  test    dl, 1
0x1800a53eb  jnz     loc_1800A59C9
0x1800a53f1  mov     rbx, qword ptr [rbp+57h+typeToken.m_Data]
0x1800a53f5  mov     qword ptr [rbp+57h+typeToken.m_Data], rax
0x1800a53f9  test    dil, 1
0x1800a53fd  jz      short loc_1800A540C
0x1800a53ff  and     rdi, 0FFFFFFFFFFFFFFFEh
0x1800a5403  mov     this, rdi; string
0x1800a5406  call    cs:__imp_WindowsDeleteString
0x1800a540c  lea     this, [rbp+57h+typeToken]; this
0x1800a5410  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800a5415  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800a541c  mov     qword ptr [rbp+57h+typeToken.m_Data], rax
0x1800a5420  mov     qword ptr [rbp+57h+staticResourceKey.m_encodedStorage.___u0], rbx
0x1800a5424  lea     this, [rbp+57h+typeToken]; this
0x1800a5428  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800a542d  xor     ebx, ebx
0x1800a542f  mov     optimizedStyleParent, [r12+70h]
0x1800a5434  mov     rsi, rbx
0x1800a5437  mov     [rbp+57h+pppStowedExceptions], rbx
0x1800a543b  mov     r15, rbx
0x1800a543e  mov     node, [optimizedStyleParent+10h]
0x1800a5442  test    node, node
0x1800a5445  jz      short loc_1800A5464
0x1800a5447  mov     eax, [node+8]
0x1800a544a  test    eax, eax
0x1800a544c  jz      short loc_1800A5464
0x1800a544e  lea     ecx, [rax+1]; failedFrameHR
0x1800a5451  lock cmpxchg [node+8], ecx
0x1800a5456  jnz     short loc_1800A544A
0x1800a5458  mov     rsi, [optimizedStyleParent+8]
0x1800a545c  mov     [rbp+57h+pppStowedExceptions], rsi
0x1800a5460  mov     r15, [optimizedStyleParent+10h]
0x1800a5464  mov     [rbp+57h+spSchemaContext._Ptr], rsi
0x1800a5468  mov     [rbp+57h+spSchemaContext._Rep], r15
0x1800a546c  test    rsi, rsi
0x1800a546f  jz      loc_1800A597F
0x1800a5475  mov     rax, [rsi+2B0h]
0x1800a547c  lea     this, [rax-8]
0x1800a5480  neg     rax
0x1800a5483  sbb     r14, r14
0x1800a5486  and     r14, this
0x1800a5489  mov     this, [r12+70h]
0x1800a548e  add     this, 18h; this
0x1800a5492  lea     node, [rbp+57h+result]; result
0x1800a5496  call    ?shared_from_this@?$enable_shared_from_this@VResourceDependency@Diagnostics@@@std@@QEAA?AV?$shared_ptr@VResourceDependency@Diagnostics@@@2@XZ; std::enable_shared_from_this<Diagnostics::ResourceDependency>::shared_from_this(void)
0x1800a549b  mov     rdi, rax
0x1800a549e  mov     rax, cs:?ghHeap@@3PEAXEA; void * ghHeap
0x1800a54a5  test    rax, rax
0x1800a54a8  jz      loc_1800A5B9B
0x1800a54ae  xor     edx, edx; dwFlags
0x1800a54b0  lea     r8d, [node+20h]; dwBytes
0x1800a54b4  mov     this, rax; hHeap
0x1800a54b7  call    cs:__imp_HeapAlloc
0x1800a54bd  mov     rbx, rax
0x1800a54c0  test    rax, rax
0x1800a54c3  jz      loc_1800A59F3
0x1800a54c9  lock add cs:?g_allocatedMemory@@3_JA, 20h ; ' '; __int64 g_allocatedMemory
0x1800a54d2  mov     dword ptr [rax+8], 1
0x1800a54d9  mov     dword ptr [rax+0Ch], 1
0x1800a54e0  lea     rax, ??_7?$_Ref_count_obj2@VXamlServiceProviderContext@@@std@@6B@; const std::_Ref_count_obj2<XamlServiceProviderContext>::`vftable'
0x1800a54e7  mov     [rbx], rax
0x1800a54ea  lea     this, [rbx+10h]; this
0x1800a54ee  mov     node, rdi; _Other
0x1800a54f1  call    ??0?$shared_ptr@VObjectWriterStack@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ObjectWriterStack>::shared_ptr<ObjectWriterStack>(std::shared_ptr<ObjectWriterStack> const &)
0x1800a54f6  lea     rax, [rbx+10h]
0x1800a54fa  mov     [rbp+57h+spXamlType._Ptr], rax
0x1800a54fe  mov     [rbp+57h+spXamlType._Rep], rbx
0x1800a5502  mov     dword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0], 5
0x1800a5509  or      edi, 0FFFFFFFFh
0x1800a550c  mov     rbx, [rbp+57h+result._Rep]
0x1800a5510  test    rbx, rbx
0x1800a5513  jz      short loc_1800A5548
0x1800a5515  mov     eax, edi
0x1800a5517  lock xadd [rbx+8], eax
0x1800a551c  add     eax, edi
0x1800a551e  jnz     short loc_1800A5548
0x1800a5520  mov     rax, [rbx]
0x1800a5523  mov     this, rbx
0x1800a5526  mov     rax, [rax]
0x1800a5529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a552e  mov     eax, edi
0x1800a5530  lock xadd [rbx+0Ch], eax
0x1800a5535  add     eax, edi
0x1800a5537  jnz     short loc_1800A5548
0x1800a5539  mov     rax, [rbx]
0x1800a553c  mov     this, rbx
0x1800a553f  mov     rax, [rax+8]
0x1800a5543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5548  movzx   eax, [rbp+57h+arg_18]
0x1800a554c  mov     [rsp+100h+var_D0], ax; stylePropertyIndex
0x1800a5551  mov     rax, [rbp+57h+arg_10]
0x1800a5555  mov     [rsp+100h+var_D8], rax; optimizedStyleParent
0x1800a555a  mov     [rsp+100h+bShouldCheckThemeResources], 1; bShouldCheckThemeResources
0x1800a5562  lea     r9, [rbp+57h+pObjectNoRef]; ppObject
0x1800a5566  mov     optimizedStyleParent, r14; pCore
0x1800a5569  lea     node, [rbp+57h+spXamlType]; spServiceProviderContext
0x1800a556d  lea     this, [rbp+57h+staticResourceKey]; strKey
0x1800a5571  call    ?LookupResourceNoRef@CStaticResourceExtension@@SAJAEBVxstring_ptr@@AEBV?$shared_ptr@VXamlServiceProviderContext@@@std@@PEAVCCoreServices@@PEAPEAVCDependencyObject@@IPEAVCStyle@@W4KnownPropertyIndex@@@Z; CStaticResourceExtension::LookupResourceNoRef(xstring_ptr const &,std::shared_ptr<XamlServiceProviderContext> const &,CCoreServices *,CDependencyObject * *,uint,CStyle *,KnownPropertyIndex)
0x1800a5576  mov     edi, eax
0x1800a5578  mov     rbx, [rbp+57h+spXamlType._Rep]
0x1800a557c  test    rbx, rbx
0x1800a557f  jz      short loc_1800A55B8
0x1800a5581  or      ecx, 0FFFFFFFFh
0x1800a5584  lock xadd [rbx+8], ecx
0x1800a5589  cmp     ecx, 1
0x1800a558c  jnz     short loc_1800A55B8
0x1800a558e  mov     node, [rbx]
0x1800a5591  mov     this, rbx
0x1800a5594  mov     rax, [node]
0x1800a5597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a559c  or      eax, 0FFFFFFFFh
0x1800a559f  lock xadd [rbx+0Ch], eax
0x1800a55a4  cmp     eax, 1
0x1800a55a7  jnz     short loc_1800A55B8
0x1800a55a9  mov     rax, [rbx]
0x1800a55ac  mov     this, rbx
0x1800a55af  mov     rax, [rax+8]
0x1800a55b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a55b8  xor     ebx, ebx
0x1800a55ba  test    edi, edi
0x1800a55bc  js      loc_1800A5A79
0x1800a55c2  mov     rbx, [rbp+57h+pObjectNoRef]
0x1800a55c6  test    rbx, rbx
0x1800a55c9  jz      loc_1800A5BAD
0x1800a55cf  xor     r13d, r13d
0x1800a55d2  xorps   xmm0, xmm0
0x1800a55d5  movdqu  xmmword ptr [rbp+57h+newString], xmm0
0x1800a55da  movdqu  xmmword ptr [rbp+57h+spXamlType._Ptr], xmm0
0x1800a55df  test    rbx, rbx
0x1800a55e2  jz      loc_1800A5C54
0x1800a55e8  mov     this, rbx; this
0x1800a55eb  call    ??$OfTypeByIndex@$0NM@@CDependencyObject@@QEBA_NXZ; CDependencyObject::OfTypeByIndex<220>(void)
0x1800a55f0  test    al, al
0x1800a55f2  jnz     loc_1800A5A9D
0x1800a55f8  mov     rbx, [rbp+57h+pObjectNoRef]
0x1800a55fc  test    rbx, rbx
0x1800a55ff  jz      loc_1800A5C54
0x1800a5605  mov     rax, [rbx]
0x1800a5608  mov     this, rbx
0x1800a560b  mov     rax, [rax+258h]
0x1800a5612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5617  movzx   edi, ax
0x1800a561a  mov     this, [rbx]
0x1800a561d  mov     rax, [this+258h]
0x1800a5624  mov     this, rbx
0x1800a5627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a562c  movzx   ecx, ax; eTypeIndex
0x1800a562f  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x1800a5634  mov     ecx, 95h
0x1800a5639  cmp     [rax], cx
0x1800a563c  jz      loc_1800A5C39
0x1800a5642  test    dword ptr [rax+4], 800h
0x1800a5649  jnz     loc_1800A5C39
0x1800a564f  movzx   ebx, di
0x1800a5652  bts     ebx, 1Ch
0x1800a5656  mov     [rbp+57h+typeToken.m_Data], ebx
0x1800a5659  mov     rax, cs:?ghHeap@@3PEAXEA; void * ghHeap
0x1800a5660  test    rax, rax
0x1800a5663  jz      loc_1800A5C42
0x1800a5669  mov     edi, 28h ; '('
0x1800a566e  mov     r8d, edi; dwBytes
0x1800a5671  xor     edx, edx; dwFlags
0x1800a5673  mov     this, rax; hHeap
0x1800a5676  call    cs:__imp_HeapAlloc
0x1800a567c  mov     r14, rax
0x1800a567f  test    rax, rax
0x1800a5682  jz      loc_1800A5A05
0x1800a5688  lock add cs:?g_allocatedMemory@@3_JA, rdi; __int64 g_allocatedMemory
0x1800a5690  mov     dword ptr [rax+8], 1
0x1800a5697  mov     dword ptr [rax+0Ch], 1
0x1800a569e  lea     rax, ??_7?$_Ref_count_obj2@UXamlQualifiedObject@@@std@@6B@; const std::_Ref_count_obj2<XamlQualifiedObject>::`vftable'
0x1800a56a5  mov     [r14], rax
0x1800a56a8  mov     [r14+10h], ebx
0x1800a56ac  mov     qword ptr [r14+14h], 0
0x1800a56b4  mov     qword ptr [r14+1Ch], 0
0x1800a56bc  mov     [r14+24h], r13d
0x1800a56c0  lea     r13, [r14+10h]
0x1800a56c4  mov     [rbp+57h+newString], r13
0x1800a56c8  mov     [rbp+57h+newString+8], r14
0x1800a56cc  mov     ebx, dword ptr [rbp+57h+pObjectNoRef]
0x1800a56cf  mov     edi, dword ptr [rbp+57h+pObjectNoRef+4]
0x1800a56d2  lea     rsi, [r13+8]
0x1800a56d6  mov     this, rsi; this
0x1800a56d9  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x1800a56de  and     dword ptr [rsi+8], 0FFFFFFD8h
0x1800a56e2  or      dword ptr [rsi+8], 58h
0x1800a56e6  mov     [rsi], ebx
0x1800a56e8  mov     [rsi+4], edi
0x1800a56eb  mov     this, rsi; target
0x1800a56ee  call    ?AddRef@?$RefCounted@$0BI@VCDependencyObject@@@ValueStores@CValueDetails@@SAXAEAVCValue@@@Z; CValueDetails::ValueStores::RefCounted<24,CDependencyObject>::AddRef(CValue &)
0x1800a56f3  mov     this, [rbp+57h+pObjectNoRef]
0x1800a56f7  mov     rax, [this]
0x1800a56fa  mov     rax, [rax+258h]
0x1800a5701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5706  mov     ebx, 98h
0x1800a570b  cmp     bx, ax
0x1800a570e  jz      short loc_1800A573E
0x1800a5710  mov     ecx, 43Ch
0x1800a5715  cmp     ax, cx
0x1800a5718  jb      short loc_1800A5743
0x1800a571a  movzx   ecx, ax; eTypeIndex
0x1800a571d  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x1800a5722  xor     ecx, ecx
0x1800a5724  cmp     [rax], cx
0x1800a5727  jz      loc_1800A5A16
0x1800a572d  cmp     [rax], bx
0x1800a5730  jz      short loc_1800A5738
0x1800a5732  movzx   ecx, word ptr [rax+2]
0x1800a5736  jmp     short loc_1800A571D
0x1800a5738  mov     al, 1
0x1800a573a  test    al, al
0x1800a573c  jz      short loc_1800A5743
0x1800a573e  or      dword ptr [r13+4], 10h
0x1800a5743  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800a574a  mov     qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0], rax
0x1800a574e  xorps   xmm1, xmm1
0x1800a5751  movdqu  xmmword ptr [rbp+57h+result._Ptr], xmm1
0x1800a5756  lea     rax, [rbp+57h+spXamlType]
0x1800a575a  mov     qword ptr [rsp+100h+bShouldCheckThemeResources], rax; outXamlType
0x1800a575f  lea     r9, [rbp+57h+inTypeName]; inTypeName
0x1800a5763  lea     optimizedStyleParent, [rbp+57h+result]; inNamespace
0x1800a5767  lea     node, [rbp+57h+typeToken]; inTypeToken
0x1800a576b  mov     this, [rbp+57h+pppStowedExceptions]; this
0x1800a576f  call    ?GetXamlType@XamlSchemaContext@@QEAAJAEBUXamlTypeToken@@AEBV?$shared_ptr@VXamlNamespace@@@std@@AEBVxstring_ptr@@AEAV?$shared_ptr@VXamlType@@@4@@Z; XamlSchemaContext::GetXamlType(XamlTypeToken const &,std::shared_ptr<XamlNamespace> const &,xstring_ptr const &,std::shared_ptr<XamlType> &)
0x1800a5774  mov     edi, eax
0x1800a5776  mov     rbx, [rbp+57h+result._Rep]
0x1800a577a  xor     esi, esi
0x1800a577c  test    rbx, rbx
0x1800a577f  jz      short loc_1800A57B9
0x1800a5781  or      ecx, 0FFFFFFFFh
0x1800a5784  lock xadd [rbx+8], ecx
0x1800a5789  cmp     ecx, 1
0x1800a578c  jnz     short loc_1800A57B9
0x1800a578e  mov     node, [rbx]
0x1800a5791  mov     this, rbx
0x1800a5794  mov     rax, [node]
0x1800a5797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a579c  or      eax, 0FFFFFFFFh
0x1800a579f  lock xadd [rbx+0Ch], eax
0x1800a57a4  cmp     eax, 1
0x1800a57a7  jnz     short loc_1800A57B9
0x1800a57a9  mov     rax, [rbx]
0x1800a57ac  mov     this, rbx
0x1800a57af  mov     rax, [rax+8]
0x1800a57b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a57b8  nop
0x1800a57b9  mov     this, qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0]
0x1800a57bd  test    cl, 1
0x1800a57c0  jnz     loc_1800A59BA
0x1800a57c6  test    edi, edi
0x1800a57c8  js      loc_1800A5B3B
0x1800a57ce  test    r14, r14
0x1800a57d1  jz      short loc_1800A57D8
0x1800a57d3  lock inc dword ptr [r14+8]
0x1800a57d8  mov     [r12], r13
0x1800a57dc  mov     rbx, [r12+8]
0x1800a57e1  mov     [r12+8], r14
0x1800a57e6  or      r13d, 0FFFFFFFFh
0x1800a57ea  test    rbx, rbx
0x1800a57ed  jz      short loc_1800A5826
0x1800a57ef  mov     eax, r13d
  ... truncated ...
```
