# BinaryFormatObjectWriter::ProvideThemeResourceValue(ObjectWriterNode const &,CStyle *,KnownPropertyIndex)

- ea: `0x1800a7c24`
- end: `0x1800a8747`
- name: `?ProvideThemeResourceValue@BinaryFormatObjectWriter@@QEAAJAEBVObjectWriterNode@@PEAVCStyle@@W4KnownPropertyIndex@@@Z`
- size: `2851`
- prototype: `HRESULT __fastcall(BinaryFormatObjectWriter *this, const ObjectWriterNode *node, CStyle *optimizedStyleParent, KnownPropertyIndex stylePropertyIndex)`
- caller_count: `2`
- callee_count: `37`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b0e90`
- `0x180251acc`

## callees

- `0x180004bc0`
- `0x18000b6c0`
- `0x18001f3c0`
- `0x180021840`
- `0x180021970`
- `0x18002d990`
- `0x180045d64`
- `0x18004755c`
- `0x18004b99c`
- `0x180065258`
- `0x1800710d0`
- `0x180073990`
- `0x180074204`
- `0x180075c70`
- `0x1800a7afc`
- `0x1800a7c24`
- `0x1800aabf0`
- `0x1800ab600`
- `0x1800af8e0`
- `0x1800b54b8`
- `0x1800fe130`
- `0x18010a79c`
- `0x18010a830`
- `0x18010b1a0`
- `0x18010c34c`
- `0x180131190`
- `0x18018dfe0`
- `0x18018fa14`
- `0x180202800`
- `0x18037aaa4`
- `0x18037adfc`
- `0x1806877a8`
- `0x180687890`
- `0x180687a78`
- `0x180688828`
- `0x18076e134`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a86f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a8734`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a86f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a8734`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7d70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7fc7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7d70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7fc7`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800a8532`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800a8543`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800a8532`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800a8543`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800a8411`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800a85c5`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800a8411`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800a85c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a80c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a81cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a80c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a81cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a83c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a83c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a864d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a864d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800a850f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800a857c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800a850f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800a857c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=15
__int64 __fastcall BinaryFormatObjectWriter::ProvideThemeResourceValue(
        BinaryFormatObjectWriter *this,
        const ObjectWriterNode *node,
        CStyle *optimizedStyleParent,
        KnownPropertyIndex stylePropertyIndex)
{
  CThemeResource *v7; // r12
  XamlQualifiedObject *Ptr; // r8
  const xstring_ptr_storage *Storage; // rax
  const xstring_ptr_storage *v10; // rbx
  ObjectWriterContext *v11; // r8
  XamlSchemaContext *v12; // rcx
  std::_Ref_count_base *v13; // r14
  std::_Ref_count_base *Rep; // rdx
  signed __int32 Uses; // eax
  signed __int32 v16; // ett
  const std::shared_ptr<DirectUI::CTimedTextSource::CTrackTokens> *v17; // rdi
  HANDLE ProcessHeap; // rax
  std::shared_ptr<DirectUI::CTimedTextSource::CTrackTokens> *v19; // rax
  std::shared_ptr<DirectUI::CTimedTextSource::CTrackTokens> *v20; // rbx
  std::_Ref_count_base *v21; // rbx
  xref_ptr<CThemeResource> v22; // rbx
  CCoreServices *v23; // rsi
  HRESULT v24; // eax
  HRESULT XamlType; // edi
  XamlType *m_ptr; // rsi
  KnownTypeIndex v27; // ax
  KnownTypeIndex i; // cx
  const CClassInfo *ClassInfoByIndex; // rax
  char v30; // al
  xref_ptr<CThemeResource> *v31; // rax
  CThemeResource *v32; // rcx
  std::_Ref_count_base *v33; // rbx
  const CClassInfo *v34; // rax
  int m_nIndex; // ecx
  bool v36; // zf
  int v37; // eax
  int v38; // ebx
  HANDLE v39; // rax
  char *v40; // rax
  char *v41; // rsi
  int m_ptr_high; // ebx
  std::_Ref_count_base *v43; // rbx
  std::_Ref_count_base *v44; // rbx
  std::_Ref_count_base *v45; // rbx
  std::_Ref_count_base *v46; // rdi
  unsigned int v48; // ebx
  HRESULT v49; // ebx
  HRESULT v50; // eax
  ThemeWalkResourceCache *Myval2; // rdi
  CThemeResource *FailFast; // rax
  _QWORD *p_RuntimeStringHandleMarker; // rdi
  int v54; // edx
  wchar_t *Buffer; // rax
  UINT32 v56; // edx
  int v57; // eax
  xref::weakref_ptr<CResourceDictionary> *v58; // r15
  xref::weakref_ptr<CResourceDictionary> *p_m_pTargetDictionaryWeakRef; // rdi
  xref::details::control_block *m_ref_count; // rcx
  std::_Ref_count_base *v61; // rcx
  HRESULT v62; // ecx
  CManagedObjectReference *v63; // rax
  CNullKeyedResource *v64; // rax
  __int16 v65; // dx
  CValue *p_m_lastResolvedThemeValue; // rcx
  unsigned int RuntimeStringHandleMarker_high; // eax
  const CValue *p_m_nativeValue; // r15
  HRESULT v69; // eax
  KnownPropertyIndex v70; // [rsp+38h] [rbp-71h]
  xstring_ptr themeResourceKey; // [rsp+40h] [rbp-69h] BYREF
  std::shared_ptr<XamlType> spXamlType; // [rsp+48h] [rbp-61h] BYREF
  xref_ptr<CThemeResource> spThemeResource; // [rsp+58h] [rbp-51h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+60h] [rbp-49h] BYREF
  HSTRING string; // [rsp+68h] [rbp-41h] BYREF
  CCoreServices *pCore; // [rsp+70h] [rbp-39h]
  xref_ptr<CBinding> ppTargetDictionary; // [rsp+78h] [rbp-31h] BYREF
  xref_ptr<CDependencyObject> ppObject; // [rsp+80h] [rbp-29h] BYREF
  int v79; // [rsp+88h] [rbp-21h]
  std::shared_ptr<XamlServiceProviderContext> spServiceProviderContext; // [rsp+90h] [rbp-19h] BYREF
  xref_ptr<CThemeResource> v81; // [rsp+A0h] [rbp-9h] BYREF
  std::shared_ptr<XamlSchemaContext> spSchemaContext; // [rsp+A8h] [rbp-1h]
  std::shared_ptr<XamlQualifiedObject> qoValue; // [rsp+B8h] [rbp+Fh]
  xstring_ptr inTypeName; // [rsp+110h] [rbp+67h] BYREF
  const ObjectWriterNode *typeToken; // [rsp+118h] [rbp+6Fh] OVERLAPPED BYREF

  typeToken = node;
  v7 = 0;
  v79 = 0;
  spSchemaContext = 0;
  qoValue = 0;
  spThemeResource.m_ptr = 0;
  Ptr = node->m_spValue._Ptr;
  Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
  inTypeName.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
  if ( (*(_BYTE *)&Ptr->m_value.m_flags.m_state.0 & 0x3F) == 0xE )
  {
    inTypeName.m_encodedStorage.Storage = (const xstring_ptr_storage *)Ptr->m_value.m_value;
    if ( ((__int64)inTypeName.m_encodedStorage.Storage & 1) != 0 )
    {
      if ( WindowsDuplicateString(
             (HSTRING)(inTypeName.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL),
             (HSTRING *)&spXamlType) < 0 )
      {
        pppStowedExceptions = 0;
        LODWORD(inTypeName.m_encodedStorage.Storage) = 0;
        TraceForFailFast(-2147418113);
        OnNewFailureEncountered(-2147418113, 0, 0);
        GetStowedExceptionsForFailFast(&pppStowedExceptions, (unsigned int *)&inTypeName);
        RoFailFastWithErrorContextInternal2(
          -2147418113,
          inTypeName.m_encodedStorage.RuntimeStringHandleMarker,
          pppStowedExceptions);
      }
      v10 = (const xstring_ptr_storage *)((__int64)spXamlType._Ptr | 1);
      Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    }
    else
    {
      v10 = inTypeName.m_encodedStorage.Storage;
    }
    inTypeName.m_encodedStorage.Storage = Storage;
    if ( ((__int64)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage & 1) != 0 )
      WindowsDeleteString((HSTRING)(xstring_ptr_constants::c_xencoded_string_ptr_null.RuntimeStringHandleMarker
                                  & 0xFFFFFFFFFFFFFFFEuLL));
    xstring_ptr::~xstring_ptr(&inTypeName);
    inTypeName.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    themeResourceKey.m_encodedStorage.Storage = v10;
  }
  else
  {
    xstring_ptr::xstring_ptr(&themeResourceKey, &CValueDetails::ValueTypeInfo<14>::Empty);
  }
  xstring_ptr::~xstring_ptr(&inTypeName);
  v11 = this->m_spContext._Ptr;
  v12 = 0;
  pppStowedExceptions = 0;
  v13 = 0;
  Rep = v11->m_SchemaContext._Rep;
  if ( Rep )
  {
    Uses = Rep->_Uses;
    while ( Uses )
    {
      v16 = Uses;
      Uses = _InterlockedCompareExchange((volatile signed __int32 *)&Rep->_Uses, Uses + 1, Uses);
      if ( v16 == Uses )
      {
        v12 = v11->m_SchemaContext._Ptr;
        pppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)v12;
        v13 = v11->m_SchemaContext._Rep;
        goto LABEL_12;
      }
    }
    v12 = 0;
  }
LABEL_12:
  spSchemaContext._Ptr = v12;
  spSchemaContext._Rep = v13;
  if ( !v12 )
  {
    OnFailure_977_(0);
    v48 = -2147467259;
    OnFailure_2990_(-2147467259);
    xstring_ptr::~xstring_ptr(&themeResourceKey);
    xref_ptr<CThemeResource>::DecrementRefCount(&spThemeResource);
LABEL_87:
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    return v48;
  }
  pCore = (CCoreServices *)((__int64)&v12->m_pCore[-1] & -(__int64)(v12->m_pCore != 0));
  v17 = (const std::shared_ptr<DirectUI::CTimedTextSource::CTrackTokens> *)std::enable_shared_from_this<Diagnostics::ResourceDependency>::shared_from_this(
                                                                             (std::enable_shared_from_this<Diagnostics::ResourceDependency> *)&this->m_spContext._Ptr->std::enable_shared_from_this<ObjectWriterContext>,
                                                                             (std::shared_ptr<Diagnostics::ResourceDependency> *)&spXamlType);
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
  spServiceProviderContext._Ptr = (XamlServiceProviderContext *)&v20[1];
  spServiceProviderContext._Rep = (std::_Ref_count_base *)v20;
  v79 = 5;
  v21 = spXamlType._Rep;
  if ( spXamlType._Rep )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&spXamlType._Rep->_Uses, 0xFFFFFFFF) == 1 )
    {
      v21->_Destroy(v21);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v21->_Weaks, 0xFFFFFFFF) == 1 )
        v21->_Delete_this(v21);
    }
  }
  ppObject.m_ptr = 0;
  ppTargetDictionary.m_ptr = 0;
  v22.m_ptr = 0;
  v81.m_ptr = 0;
  inTypeName.m_encodedStorage.Storage = 0;
  spThemeResource.m_ptr = 0;
  xref_ptr<CUIElement>::~xref_ptr<CUIElement>(&ppTargetDictionary);
  xref_ptr<CDependencyObject>::DecrementRefCount(&ppObject);
  v70 = stylePropertyIndex;
  v23 = pCore;
  v24 = CThemeResourceExtension::ResolveInitialValueAndTargetDictionary(
          &themeResourceKey,
          &spServiceProviderContext,
          pCore,
          1u,
          &ppObject.m_ptr,
          (CResourceDictionary **)&ppTargetDictionary,
          optimizedStyleParent,
          v70);
  XamlType = v24;
  if ( v24 < 0 )
  {
    OnFailure_2990_(v24);
    xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&inTypeName);
    xref_ptr<CThemeResource>::DecrementRefCount(&v81);
    goto LABEL_38;
  }
  m_ptr = (XamlType *)ppObject.m_ptr;
  if ( !ppObject.m_ptr )
    goto LABEL_36;
  v27 = ppObject.m_ptr->GetTypeIndex(ppObject.m_ptr);
  if ( v27 == ThemeResource )
    goto LABEL_31;
  if ( (unsigned __int16)v27 >= (XYFocusNavigationStrategy|IVectorOfUri) )
  {
    for ( i = v27; ; i = ClassInfoByIndex->m_nBaseTypeIndex )
    {
      ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex(i);
      if ( ClassInfoByIndex->m_nIndex == UnknownType )
        break;
      if ( ClassInfoByIndex->m_nIndex == ThemeResource )
      {
        v30 = 1;
        goto LABEL_30;
      }
    }
    v30 = 0;
LABEL_30:
    if ( v30 )
    {
LABEL_31:
      spXamlType._Ptr = m_ptr;
      v31 = make_xref<CThemeResource,CThemeResourceExtension *>(
              (xref_ptr<CThemeResource> *)&inTypeName,
              (CThemeResourceExtension **)&spXamlType);
      if ( &v81 != v31 )
      {
        v22.m_ptr = v31->m_ptr;
        v31->m_ptr = 0;
      }
      v32 = (CThemeResource *)inTypeName.m_encodedStorage.Storage;
      if ( inTypeName.m_encodedStorage.Storage )
      {
        inTypeName.m_encodedStorage.Storage = 0;
        CThemeResource::Release(v32);
      }
      goto LABEL_35;
    }
  }
  Myval2 = pCore->m_themeWalkResourceCache._Mypair._Myval2;
  FailFast = (CThemeResource *)XcpAllocation::OSMemoryAllocateFailFast(0x38u);
  v22.m_ptr = FailFast;
  if ( FailFast )
  {
    FailFast->m_cRef = 1;
    *((_BYTE *)FailFast + 4) |= 1u;
    FailFast->m_strResourceKey.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
    FailFast->m_lastResolvedThemeValue.m_value = 0;
    FailFast->m_lastResolvedThemeValue.m_flags = 0;
    FailFast->m_pTargetDictionaryWeakRef.m_ptr = 0;
    FailFast->m_pTargetDictionaryWeakRef.m_ref_count = 0;
    FailFast->m_themeWalkResourceCache = Myval2;
  }
  else
  {
    v22.m_ptr = 0;
  }
  p_RuntimeStringHandleMarker = &v22.m_ptr->m_strResourceKey.m_encodedStorage.RuntimeStringHandleMarker;
  if ( &v22.m_ptr->m_strResourceKey != &themeResourceKey )
  {
    if ( ((__int64)themeResourceKey.m_encodedStorage.Storage & 1) != 0 )
    {
      v57 = WindowsDuplicateString(
              (HSTRING)(themeResourceKey.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL),
              &string);
      if ( v57 < 0 )
        goto LABEL_101;
    }
    else
    {
      if ( !themeResourceKey.m_encodedStorage.Storage
        || (v54 = *((_DWORD *)themeResourceKey.m_encodedStorage.Storage + 2), (v54 & 0x40000000) == 0) )
      {
        string = themeResourceKey.m_encodedStorage.Handle;
        goto LABEL_102;
      }
      LODWORD(inTypeName.m_encodedStorage.Storage) = 0;
      Buffer = (wchar_t *)themeResourceKey.m_encodedStorage.Storage->Buffer;
      if ( v54 < 0 )
      {
        Buffer = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)Buffer, (UINT32 *)&inTypeName);
        v56 = (UINT32)inTypeName.m_encodedStorage.Storage;
      }
      else
      {
        v56 = v54 & 0x3FFFFFFF;
        LODWORD(inTypeName.m_encodedStorage.Storage) = v56;
      }
      v57 = WindowsCreateString(Buffer, v56, &string);
      if ( v57 < 0 )
      {
LABEL_101:
        OnFailure_2990_(v57);
        spXamlType._Ptr = 0;
        LODWORD(inTypeName.m_encodedStorage.Storage) = 0;
        TraceForFailFast(-2147418113);
        OnNewFailureEncountered(-2147418113, 0, 0);
        GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&spXamlType, (unsigned int *)&inTypeName);
        RoFailFastWithErrorContextInternal2(
          -2147418113,
          inTypeName.m_encodedStorage.RuntimeStringHandleMarker,
          (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)spXamlType._Ptr);
LABEL_102:
        if ( (*p_RuntimeStringHandleMarker & 1) != 0 )
          WindowsDeleteString((HSTRING)(*p_RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
        *p_RuntimeStringHandleMarker = string;
        goto LABEL_105;
      }
    }
    string = (HSTRING)((unsigned __int64)string | 1);
    goto LABEL_102;
  }
LABEL_105:
  v58 = xref::get_weakref<CResourceDictionary>(
          (xref::weakref_ptr<CResourceDictionary> *)&spXamlType,
          (CResourceDictionary *)ppTargetDictionary.m_ptr);
  p_m_pTargetDictionaryWeakRef = &v22.m_ptr->m_pTargetDictionaryWeakRef;
  if ( v58 != &v22.m_ptr->m_pTargetDictionaryWeakRef )
  {
    m_ref_count = v22.m_ptr->m_pTargetDictionaryWeakRef.m_ref_count;
    if ( m_ref_count )
      xref::details::control_block::ReleaseWeak(m_ref_count);
    v22.m_ptr->m_pTargetDictionaryWeakRef.m_ref_count = 0;
    p_m_pTargetDictionaryWeakRef->m_ptr = 0;
    p_m_pTargetDictionaryWeakRef->m_ptr = v58->m_ptr;
    v22.m_ptr->m_pTargetDictionaryWeakRef.m_ref_count = v58->m_ref_count;
    v58->m_ptr = 0;
    v58->m_ref_count = 0;
  }
  v61 = spXamlType._Rep;
  if ( spXamlType._Rep
    && _InterlockedExchangeAdd((volatile signed __int32 *)&spXamlType._Rep->__vftable + 1, 0xFFFFFFFF) == 1 )
  {
    operator delete(v61, 0xCu);
  }
  inTypeName.m_encodedStorage.Storage = (const xstring_ptr_storage *)m_ptr;
  *((_BYTE *)v22.m_ptr + 4) &= ~1u;
  *((_BYTE *)v22.m_ptr + 4) |= (*(_BYTE *)&v22.m_ptr->m_lastResolvedThemeValue.m_flags.m_state.0 & 0x3F) == 0;
  if ( CDependencyObject::OfTypeByIndex<135>((CDependencyObject *)m_ptr) )
  {
    m_ptr = (XamlType *)m_ptr->m_spXamlNamespace._Rep;
    inTypeName.m_encodedStorage.Storage = (const xstring_ptr_storage *)m_ptr;
    if ( !m_ptr )
    {
      OnNewFailure_1172_(v62);
      XamlType = -2147467261;
LABEL_127:
      OnFailure_2990_(XamlType);
      OnFailure_2990_(XamlType);
      CThemeResource::Release(v22.m_ptr);
      goto LABEL_37;
    }
  }
  v63 = do_pointer_cast<CManagedObjectReference>((CDependencyObject *)m_ptr);
  if ( !v63 || (p_m_nativeValue = &v63->m_nativeValue, CValue::IsNull(&v63->m_nativeValue)) )
  {
    v64 = do_pointer_cast<CNullKeyedResource>((CDependencyObject *)m_ptr);
    p_m_lastResolvedThemeValue = &v22.m_ptr->m_lastResolvedThemeValue;
    if ( v64 )
    {
      CValue::Set<1>(p_m_lastResolvedThemeValue, v65);
    }
    else
    {
      CValue::ReleaseAndReset(p_m_lastResolvedThemeValue);
      v22.m_ptr->m_lastResolvedThemeValue.m_flags.m_state.m_asOne = v22.m_ptr->m_lastResolvedThemeValue.m_flags.m_state.m_asOne
                                                                  & 0xFFFFFF80
                                                                  | 0x58;
      RuntimeStringHandleMarker_high = HIDWORD(inTypeName.m_encodedStorage.RuntimeStringHandleMarker);
      v22.m_ptr->m_lastResolvedThemeValue.m_value.m_any[0] = (unsigned int)m_ptr;
      v22.m_ptr->m_lastResolvedThemeValue.m_value.m_any[1] = RuntimeStringHandleMarker_high;
      CValueDetails::ValueStores::RefCounted<24,CDependencyObject>::AddRef(&v22.m_ptr->m_lastResolvedThemeValue);
    }
  }
  else
  {
    v69 = CValue::CopyConverted(&v22.m_ptr->m_lastResolvedThemeValue, p_m_nativeValue);
    XamlType = v69;
    if ( v69 < 0 )
    {
      OnFailure_2990_(v69);
      goto LABEL_127;
    }
  }
LABEL_35:
  v7 = v22.m_ptr;
  spThemeResource.m_ptr = v22.m_ptr;
LABEL_36:
  XamlType = 0;
LABEL_37:
  v23 = pCore;
LABEL_38:
  xref_ptr<CUIElement>::~xref_ptr<CUIElement>(&ppTargetDictionary);
  xref_ptr<CDependencyObject>::DecrementRefCount(&ppObject);
  v33 = spServiceProviderContext._Rep;
  if ( spServiceProviderContext._Rep )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&spServiceProviderContext._Rep->_Uses, 0xFFFFFFFF) == 1 )
    {
      v33->_Destroy(v33);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v33->_Weaks, 0xFFFFFFFF) == 1 )
        v33->_Delete_this(v33);
    }
  }
  if ( XamlType < 0 )
  {
    OnFailure_2990_(XamlType);
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&themeResourceKey);
    if ( v7 )
      CThemeResource::Release(v7);
  }
  else
  {
    if ( !v7 )
    {
      spXamlType._Ptr = (XamlType *)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
      inTypeName.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
      v49 = CErrorService::OriginateInvalidOperationError(
              v23,
              0x8E0u,
              &themeResourceKey,
              &inTypeName,
              (const xstring_ptr_view *)&spXamlType);
      xencoded_string_ptr::Reset((xruntime_string_ptr *)&inTypeName);
      xencoded_string_ptr::Reset((xruntime_string_ptr *)&spXamlType);
      v50 = ObjectWriterErrorService::WrapErrorWithParserErrorAndRethrow(
              this->m_spErrorService._Ptr,
              v49,
              &typeToken->m_LineInfo);
      v48 = v50;
      if ( v50 < 0 )
      {
        OnFailure_2990_(v50);
        xencoded_string_ptr::Reset((xruntime_string_ptr *)&themeResourceKey);
        goto LABEL_87;
      }
    }
    v34 = DirectUI::MetadataAPI::GetClassInfoByIndex(ThemeResource);
    m_nIndex = (unsigned __int16)v34->m_nIndex;
    if ( (v34->m_flags & 0x8000) != 0
      || (v34->m_flags & 0x40) != 0
      || (v36 = (v34->m_flags & 4) == 0, v37 = 0x10000000, !v36) )
    {
      v37 = 0x20000000;
    }
    v38 = v37 | m_nIndex;
    LODWORD(typeToken) = v37 | m_nIndex;
    spXamlType = 0;
    v39 = ghHeap;
    if ( !ghHeap )
    {
      v39 = GetProcessHeap();
      ghHeap = v39;
    }
    v40 = (char *)HeapAlloc(v39, 0, 0x28u);
    v41 = v40;
    if ( v40 )
    {
      _InterlockedAdd64(&g_allocatedMemory, 0x28u);
      *((_DWORD *)v40 + 2) = 1;
      *((_DWORD *)v40 + 3) = 1;
      *(_QWORD *)v40 = std::_Ref_count_obj2<XamlQualifiedObject>::`vftable';
      *((_DWORD *)v40 + 4) = v38;
      *(_QWORD *)(v40 + 20) = 0;
      *(_QWORD *)(v40 + 28) = 0;
      *((_DWORD *)v40 + 9) = 0;
    }
    else
    {
      TerminateProcessOnMemoryExhaustion(0x28u);
      v41 = 0;
    }
    qoValue._Ptr = (XamlQualifiedObject *)(v41 + 16);
    qoValue._Rep = (std::_Ref_count_base *)v41;
    m_ptr_high = HIDWORD(spThemeResource.m_ptr);
    spThemeResource.m_ptr = 0;
    CValue::ReleaseAndReset((CValue *)(v41 + 24));
    *((_DWORD *)v41 + 8) &= 0xFFFFFFDD;
    *((_DWORD *)v41 + 8) |= 0x5Du;
    *((_DWORD *)v41 + 6) = (_DWORD)v7;
    *((_DWORD *)v41 + 7) = m_ptr_high;
    inTypeName.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    spServiceProviderContext = 0;
    XamlType = XamlSchemaContext::GetXamlType(
                 (XamlSchemaContext *)pppStowedExceptions,
                 (const XamlTypeToken *)&typeToken,
                 (const std::shared_ptr<XamlNamespace> *)&spServiceProviderContext,
                 &inTypeName,
                 &spXamlType);
    v43 = spServiceProviderContext._Rep;
    if ( spServiceProviderContext._Rep )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&spServiceProviderContext._Rep->_Uses, 0xFFFFFFFF) == 1 )
      {
        v43->_Destroy(v43);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v43->_Weaks, 0xFFFFFFFF) == 1 )
          v43->_Delete_this(v43);
      }
    }
    if ( ((__int64)inTypeName.m_encodedStorage.Storage & 1) != 0 )
      WindowsDeleteString((HSTRING)(inTypeName.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
    if ( XamlType >= 0 )
    {
      if ( v41 )
        _InterlockedIncrement((volatile signed __int32 *)v41 + 2);
      this->m_qoLastInstance._Ptr = (XamlQualifiedObject *)(v41 + 16);
      v44 = this->m_qoLastInstance._Rep;
      this->m_qoLastInstance._Rep = (std::_Ref_count_base *)v41;
      if ( v44 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v44->_Uses, 0xFFFFFFFF) == 1 )
        {
          v44->_Destroy(v44);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v44->_Weaks, 0xFFFFFFFF) == 1 )
            v44->_Delete_this(v44);
        }
      }
      v45 = spXamlType._Rep;
      if ( spXamlType._Rep )
        _InterlockedIncrement((volatile signed __int32 *)&spXamlType._Rep->_Uses);
      this->m_qoLastType._Ptr = spXamlType._Ptr;
      v46 = this->m_qoLastType._Rep;
      this->m_qoLastType._Rep = v45;
      if ( v46 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v46->_Uses, 0xFFFFFFFF) == 1 )
        {
          v46->_Destroy(v46);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v46->_Weaks, 0xFFFFFFFF) == 1 )
            v46->_Delete_this(v46);
        }
      }
      if ( v45 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v45->_Uses, 0xFFFFFFFF) == 1 )
        {
          v45->_Destroy(v45);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v45->_Weaks, 0xFFFFFFFF) == 1 )
            v45->_Delete_this(v45);
        }
      }
      if ( ((__int64)themeResourceKey.m_encodedStorage.Storage & 1) != 0 )
        WindowsDeleteString((HSTRING)(themeResourceKey.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
      themeResourceKey.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
      if ( v41 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(char *))v41)(v41);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v41 + 8LL))(v41);
        }
      }
      if ( v13 && _InterlockedExchangeAdd((volatile signed __int32 *)&v13->_Uses, 0xFFFFFFFF) == 1 )
      {
        v13->_Destroy(v13);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v13->_Weaks, 0xFFFFFFFF) == 1 )
          v13->_Delete_this(v13);
      }
      return 0;
    }
    OnFailure_2990_(XamlType);
    if ( spXamlType._Rep )
      std::_Ref_count_base::_Decref(spXamlType._Rep);
    xstring_ptr::~xstring_ptr(&themeResourceKey);
    xref_ptr<CThemeResource>::DecrementRefCount(&spThemeResource);
    if ( v41 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v41);
  }
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  return (unsigned int)XamlType;
}

```

## disassembly

```asm
0x1800a7c24  mov     [rsp-8+arg_10], rbx
0x1800a7c29  mov     qword ptr [rsp-8+typeToken.m_Data], node
0x1800a7c2e  push    rbp
0x1800a7c2f  push    rsi
0x1800a7c30  push    rdi
0x1800a7c31  push    r12
0x1800a7c33  push    r13
0x1800a7c35  push    r14
0x1800a7c37  push    r15
0x1800a7c39  lea     rbp, [rsp-27h]
0x1800a7c3e  sub     rsp, 0D0h
0x1800a7c45  movzx   esi, stylePropertyIndex
0x1800a7c49  mov     r15, optimizedStyleParent
0x1800a7c4c  mov     r13, this
0x1800a7c4f  xor     r12d, r12d
0x1800a7c52  mov     [rbp+57h+var_78], r12d
0x1800a7c56  xorps   xmm0, xmm0
0x1800a7c59  movdqu  xmmword ptr [rbp+57h+spSchemaContext._Ptr], xmm0
0x1800a7c5e  movdqu  xmmword ptr [rbp+57h+qoValue._Ptr], xmm0
0x1800a7c63  mov     [rbp+57h+spThemeResource.m_ptr], r12
0x1800a7c67  mov     optimizedStyleParent, [node+70h]
0x1800a7c6b  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800a7c72  mov     qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0], rax
0x1800a7c76  mov     ecx, [optimizedStyleParent+10h]
0x1800a7c7a  and     ecx, 3Fh
0x1800a7c7d  mov     ebx, 8000FFFFh
0x1800a7c82  cmp     cl, 0Eh
0x1800a7c85  jnz     loc_1800A86DF
0x1800a7c8b  mov     rdi, rax
0x1800a7c8e  mov     edx, [optimizedStyleParent+8]
0x1800a7c92  mov     dword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0], edx
0x1800a7c95  mov     ecx, [optimizedStyleParent+0Ch]
0x1800a7c99  mov     dword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0+4], ecx
0x1800a7c9c  test    dl, 1
0x1800a7c9f  jnz     loc_1800A8503
0x1800a7ca5  mov     rbx, qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0]
0x1800a7ca9  mov     qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0], rax
0x1800a7cad  test    dil, 1
0x1800a7cb1  jz      short loc_1800A7CC0
0x1800a7cb3  and     rdi, 0FFFFFFFFFFFFFFFEh
0x1800a7cb7  mov     this, rdi; string
0x1800a7cba  call    cs:__imp_WindowsDeleteString
0x1800a7cc0  lea     this, [rbp+57h+inTypeName]; this
0x1800a7cc4  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800a7cc9  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800a7cd0  mov     qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0], rax
0x1800a7cd4  mov     qword ptr [rbp+57h+themeResourceKey.m_encodedStorage.___u0], rbx
0x1800a7cd8  lea     this, [rbp+57h+inTypeName]; this
0x1800a7cdc  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800a7ce1  nop
0x1800a7ce2  mov     optimizedStyleParent, [r13+70h]
0x1800a7ce6  mov     this, r12
0x1800a7ce9  mov     [rbp+57h+pppStowedExceptions], this
0x1800a7ced  mov     r14, r12
0x1800a7cf0  mov     node, [optimizedStyleParent+10h]
0x1800a7cf4  test    node, node
0x1800a7cf7  jz      short loc_1800A7D1A
0x1800a7cf9  mov     eax, [node+8]
0x1800a7cfc  test    eax, eax
0x1800a7cfe  jz      loc_1800A8609
0x1800a7d04  lea     ecx, [rax+1]
0x1800a7d07  lock cmpxchg [node+8], ecx
0x1800a7d0c  jnz     short loc_1800A7CFC
0x1800a7d0e  mov     this, [optimizedStyleParent+8]; failedFrameHR
0x1800a7d12  mov     [rbp+57h+pppStowedExceptions], this
0x1800a7d16  mov     r14, [optimizedStyleParent+10h]
0x1800a7d1a  mov     [rbp+57h+spSchemaContext._Ptr], this
0x1800a7d1e  mov     [rbp+57h+spSchemaContext._Rep], r14
0x1800a7d22  test    this, this
0x1800a7d25  jz      loc_1800A8274
0x1800a7d2b  mov     rax, [this+2B0h]
0x1800a7d32  lea     this, [rax-8]
0x1800a7d36  neg     rax
0x1800a7d39  sbb     rax, rax
0x1800a7d3c  and     rax, this
0x1800a7d3f  mov     [rbp+57h+pCore], rax
0x1800a7d43  mov     this, [r13+70h]
0x1800a7d47  add     this, 18h; this
0x1800a7d4b  lea     node, [rbp+57h+spXamlType]; result
0x1800a7d4f  call    ?shared_from_this@?$enable_shared_from_this@VResourceDependency@Diagnostics@@@std@@QEAA?AV?$shared_ptr@VResourceDependency@Diagnostics@@@2@XZ; std::enable_shared_from_this<Diagnostics::ResourceDependency>::shared_from_this(void)
0x1800a7d54  mov     rdi, rax
0x1800a7d57  mov     rax, cs:?ghHeap@@3PEAXEA; void * ghHeap
0x1800a7d5e  test    rax, rax
0x1800a7d61  jz      loc_1800A86F4
0x1800a7d67  xor     edx, edx; dwFlags
0x1800a7d69  lea     r8d, [node+20h]; dwBytes
0x1800a7d6d  mov     this, rax; hHeap
0x1800a7d70  call    cs:__imp_HeapAlloc
0x1800a7d76  mov     rbx, rax
0x1800a7d79  test    rax, rax
0x1800a7d7c  jz      loc_1800A852D
0x1800a7d82  lock add cs:?g_allocatedMemory@@3_JA, 20h ; ' '; __int64 g_allocatedMemory
0x1800a7d8b  mov     dword ptr [rax+8], 1
0x1800a7d92  mov     dword ptr [rax+0Ch], 1
0x1800a7d99  lea     rax, ??_7?$_Ref_count_obj2@VXamlServiceProviderContext@@@std@@6B@; const std::_Ref_count_obj2<XamlServiceProviderContext>::`vftable'
0x1800a7da0  mov     [rbx], rax
0x1800a7da3  lea     this, [rbx+10h]; this
0x1800a7da7  mov     node, rdi; _Other
0x1800a7daa  call    ??0?$shared_ptr@VObjectWriterStack@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ObjectWriterStack>::shared_ptr<ObjectWriterStack>(std::shared_ptr<ObjectWriterStack> const &)
0x1800a7daf  lea     rax, [rbx+10h]
0x1800a7db3  mov     [rbp+57h+spServiceProviderContext._Ptr], rax
0x1800a7db7  mov     [rbp+57h+spServiceProviderContext._Rep], rbx
0x1800a7dbb  mov     [rbp+57h+var_78], 5
0x1800a7dc2  or      edi, 0FFFFFFFFh
0x1800a7dc5  mov     rbx, [rbp+57h+spXamlType._Rep]
0x1800a7dc9  test    rbx, rbx
0x1800a7dcc  jz      short loc_1800A7E01
0x1800a7dce  mov     eax, edi
0x1800a7dd0  lock xadd [rbx+8], eax
0x1800a7dd5  add     eax, edi
0x1800a7dd7  jnz     short loc_1800A7E01
0x1800a7dd9  mov     rax, [rbx]
0x1800a7ddc  mov     this, rbx
0x1800a7ddf  mov     rax, [rax]
0x1800a7de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7de7  mov     eax, edi
0x1800a7de9  lock xadd [rbx+0Ch], eax
0x1800a7dee  add     eax, edi
0x1800a7df0  jnz     short loc_1800A7E01
0x1800a7df2  mov     rax, [rbx]
0x1800a7df5  mov     this, rbx
0x1800a7df8  mov     rax, [rax+8]
0x1800a7dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7e01  mov     [rbp+57h+var_80.m_ptr], r12
0x1800a7e05  mov     [rbp+57h+var_88.m_ptr], r12
0x1800a7e09  mov     rbx, r12
0x1800a7e0c  mov     [rbp+57h+var_60.m_ptr], rbx
0x1800a7e10  mov     qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0], r12
0x1800a7e14  mov     [rbp+57h+spThemeResource.m_ptr], r12
0x1800a7e18  lea     this, [rbp+57h+var_88]; this
0x1800a7e1c  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x1800a7e21  lea     this, [rbp+57h+var_80]; this
0x1800a7e25  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x1800a7e2a  mov     [rsp+100h+var_C8], si; stylePropertyIndex
0x1800a7e2f  mov     [rsp+100h+var_D0], r15; optimizedStyleParent
0x1800a7e34  lea     rax, [rbp+57h+var_88]
0x1800a7e38  mov     [rsp+100h+ppTargetDictionary], rax; ppTargetDictionary
0x1800a7e3d  lea     rax, [rbp+57h+var_80]
0x1800a7e41  mov     [rsp+100h+ppObject], rax; ppObject
0x1800a7e46  mov     r9d, 1; bShouldCheckThemeResources
0x1800a7e4c  mov     rsi, [rbp+57h+pCore]
0x1800a7e50  mov     optimizedStyleParent, rsi; pCore
0x1800a7e53  lea     node, [rbp+57h+spServiceProviderContext]; spServiceProviderContext
0x1800a7e57  lea     this, [rbp+57h+themeResourceKey]; strResourceKey
0x1800a7e5b  call    ?ResolveInitialValueAndTargetDictionary@CThemeResourceExtension@@SAJAEBVxstring_ptr@@AEBV?$shared_ptr@VXamlServiceProviderContext@@@std@@PEAVCCoreServices@@IPEAPEAVCDependencyObject@@PEAPEAVCResourceDictionary@@PEAVCStyle@@W4KnownPropertyIndex@@@Z; CThemeResourceExtension::ResolveInitialValueAndTargetDictionary(xstring_ptr const &,std::shared_ptr<XamlServiceProviderContext> const &,CCoreServices *,uint,CDependencyObject * *,CResourceDictionary * *,CStyle *,KnownPropertyIndex)
0x1800a7e60  mov     edi, eax
0x1800a7e62  xor     r15d, r15d
0x1800a7e65  test    eax, eax
0x1800a7e67  js      loc_1800A8716
0x1800a7e6d  mov     rsi, [rbp+57h+var_80.m_ptr]
0x1800a7e71  test    rsi, rsi
0x1800a7e74  jz      loc_1800A7F04
0x1800a7e7a  mov     rax, [rsi]
0x1800a7e7d  mov     this, rsi
0x1800a7e80  mov     rax, [rax+258h]
0x1800a7e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7e8c  mov     edi, 210h
0x1800a7e91  cmp     di, ax
0x1800a7e94  jz      short loc_1800A7ECB
0x1800a7e96  mov     ecx, 43Ch
0x1800a7e9b  cmp     ax, cx
0x1800a7e9e  jb      loc_1800A8326
0x1800a7ea4  movzx   ecx, ax; eTypeIndex
0x1800a7ea7  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x1800a7eac  cmp     [rax], r15w
0x1800a7eb0  jz      loc_1800A8551
0x1800a7eb6  cmp     [rax], di
0x1800a7eb9  jz      short loc_1800A7EC1
0x1800a7ebb  movzx   ecx, word ptr [rax+2]
0x1800a7ebf  jmp     short loc_1800A7EA7
0x1800a7ec1  mov     al, 1
0x1800a7ec3  test    al, al
0x1800a7ec5  jz      loc_1800A8326
0x1800a7ecb  mov     [rbp+57h+spXamlType._Ptr], rsi
0x1800a7ecf  lea     node, [rbp+57h+spXamlType]; <Args_0>
0x1800a7ed3  lea     this, [rbp+57h+inTypeName]; result
0x1800a7ed7  call    ??$make_xref@VCThemeResource@@PEAVCThemeResourceExtension@@@@YA?AV?$xref_ptr@VCThemeResource@@@@$$QEAPEAVCThemeResourceExtension@@@Z; make_xref<CThemeResource,CThemeResourceExtension *>(CThemeResourceExtension * &&)
0x1800a7edc  lea     this, [rbp+57h+var_60]
0x1800a7ee0  cmp     this, rax
0x1800a7ee3  jz      short loc_1800A7EEB
0x1800a7ee5  mov     rbx, [rax]
0x1800a7ee8  mov     [rax], r15
0x1800a7eeb  mov     this, qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0]; this
0x1800a7eef  test    this, this
0x1800a7ef2  jz      short loc_1800A7EFD
0x1800a7ef4  mov     qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0], r15
0x1800a7ef8  call    ?Release@CThemeResource@@QEAAIXZ; CThemeResource::Release(void)
0x1800a7efd  mov     r12, rbx
0x1800a7f00  mov     [rbp+57h+spThemeResource.m_ptr], rbx
0x1800a7f04  mov     edi, r15d
0x1800a7f07  mov     rsi, [rbp+57h+pCore]
0x1800a7f0b  lea     this, [rbp+57h+var_88]; this
0x1800a7f0f  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x1800a7f14  lea     this, [rbp+57h+var_80]; this
0x1800a7f18  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x1800a7f1d  nop
0x1800a7f1e  mov     rbx, [rbp+57h+spServiceProviderContext._Rep]
0x1800a7f22  test    rbx, rbx
0x1800a7f25  jz      short loc_1800A7F5E
0x1800a7f27  or      eax, 0FFFFFFFFh
0x1800a7f2a  lock xadd [rbx+8], eax
0x1800a7f2f  cmp     eax, 1
0x1800a7f32  jnz     short loc_1800A7F5E
0x1800a7f34  mov     rax, [rbx]
0x1800a7f37  mov     this, rbx
0x1800a7f3a  mov     rax, [rax]
0x1800a7f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7f42  or      eax, 0FFFFFFFFh
0x1800a7f45  lock xadd [rbx+0Ch], eax
0x1800a7f4a  cmp     eax, 1
0x1800a7f4d  jnz     short loc_1800A7F5E
0x1800a7f4f  mov     rax, [rbx]
0x1800a7f52  mov     this, rbx
0x1800a7f55  mov     rax, [rax+8]
0x1800a7f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7f5e  test    edi, edi
0x1800a7f60  js      loc_1800A8667
0x1800a7f66  test    r12, r12
0x1800a7f69  jz      loc_1800A82AC
0x1800a7f6f  mov     ecx, 210h; eTypeIndex
0x1800a7f74  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x1800a7f79  movzx   ecx, word ptr [rax]
0x1800a7f7c  test    dword ptr [rax+4], 8000h
0x1800a7f83  jnz     short loc_1800A7F96
0x1800a7f85  test    byte ptr [rax+4], 40h
0x1800a7f89  jnz     short loc_1800A7F96
0x1800a7f8b  test    byte ptr [rax+4], 4
0x1800a7f8f  mov     eax, 10000000h
0x1800a7f94  jz      short loc_1800A7F9B
0x1800a7f96  mov     eax, 20000000h
0x1800a7f9b  mov     ebx, ecx
0x1800a7f9d  or      ebx, eax
0x1800a7f9f  mov     [rbp+57h+typeToken.m_Data], ebx
0x1800a7fa2  xorps   xmm0, xmm0
0x1800a7fa5  movdqu  xmmword ptr [rbp+57h+spXamlType._Ptr], xmm0
0x1800a7faa  mov     rax, cs:?ghHeap@@3PEAXEA; void * ghHeap
0x1800a7fb1  test    rax, rax
0x1800a7fb4  jz      loc_1800A8734
0x1800a7fba  mov     edi, 28h ; '('
0x1800a7fbf  mov     r8d, edi; dwBytes
0x1800a7fc2  xor     edx, edx; dwFlags
0x1800a7fc4  mov     this, rax; hHeap
0x1800a7fc7  call    cs:__imp_HeapAlloc
0x1800a7fcd  mov     rsi, rax
0x1800a7fd0  test    rax, rax
0x1800a7fd3  jz      loc_1800A8540
0x1800a7fd9  lock add cs:?g_allocatedMemory@@3_JA, rdi; __int64 g_allocatedMemory
0x1800a7fe1  mov     dword ptr [rax+8], 1
0x1800a7fe8  mov     dword ptr [rax+0Ch], 1
0x1800a7fef  lea     rax, ??_7?$_Ref_count_obj2@UXamlQualifiedObject@@@std@@6B@; const std::_Ref_count_obj2<XamlQualifiedObject>::`vftable'
0x1800a7ff6  mov     [rsi], rax
0x1800a7ff9  mov     [rsi+10h], ebx
0x1800a7ffc  mov     qword ptr [rsi+14h], 0
0x1800a8004  mov     qword ptr [rsi+1Ch], 0
0x1800a800c  mov     [rsi+24h], r15d
0x1800a8010  lea     r15, [rsi+10h]
0x1800a8014  mov     [rbp+57h+qoValue._Ptr], r15
0x1800a8018  mov     [rbp+57h+qoValue._Rep], rsi
0x1800a801c  mov     ebx, dword ptr [rbp+57h+spThemeResource.m_ptr+4]
0x1800a801f  mov     [rbp+57h+spThemeResource.m_ptr], 0
0x1800a8027  lea     this, [r15+8]; this
0x1800a802b  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x1800a8030  and     dword ptr [r15+10h], 0FFFFFFDDh
0x1800a8035  or      dword ptr [r15+10h], 5Dh
0x1800a803a  mov     [r15+8], r12d
0x1800a803e  mov     [r15+0Ch], ebx
0x1800a8042  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800a8049  mov     qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0], rax
0x1800a804d  xorps   xmm1, xmm1
0x1800a8050  movdqu  xmmword ptr [rbp+57h+spServiceProviderContext._Ptr], xmm1
0x1800a8055  lea     rax, [rbp+57h+spXamlType]
0x1800a8059  mov     [rsp+100h+ppObject], rax; outXamlType
0x1800a805e  lea     r9, [rbp+57h+inTypeName]; inTypeName
0x1800a8062  lea     optimizedStyleParent, [rbp+57h+spServiceProviderContext]; inNamespace
0x1800a8066  lea     node, [rbp+57h+typeToken]; inTypeToken
0x1800a806a  mov     this, [rbp+57h+pppStowedExceptions]; this
0x1800a806e  call    ?GetXamlType@XamlSchemaContext@@QEAAJAEBUXamlTypeToken@@AEBV?$shared_ptr@VXamlNamespace@@@std@@AEBVxstring_ptr@@AEAV?$shared_ptr@VXamlType@@@4@@Z; XamlSchemaContext::GetXamlType(XamlTypeToken const &,std::shared_ptr<XamlNamespace> const &,xstring_ptr const &,std::shared_ptr<XamlType> &)
0x1800a8073  mov     edi, eax
0x1800a8075  mov     rbx, [rbp+57h+spServiceProviderContext._Rep]
0x1800a8079  or      r12d, 0FFFFFFFFh
0x1800a807d  test    rbx, rbx
0x1800a8080  jz      short loc_1800A80BA
0x1800a8082  mov     ecx, r12d
0x1800a8085  lock xadd [rbx+8], ecx
0x1800a808a  add     ecx, r12d
0x1800a808d  jnz     short loc_1800A80BA
0x1800a808f  mov     node, [rbx]
0x1800a8092  mov     this, rbx
0x1800a8095  mov     rax, [node]
0x1800a8098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a809d  mov     eax, r12d
0x1800a80a0  lock xadd [rbx+0Ch], eax
0x1800a80a5  add     eax, r12d
0x1800a80a8  jnz     short loc_1800A80BA
0x1800a80aa  mov     rax, [rbx]
0x1800a80ad  mov     this, rbx
0x1800a80b0  mov     rax, [rax+8]
0x1800a80b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a80b9  nop
0x1800a80ba  mov     this, qword ptr [rbp+57h+inTypeName.m_encodedStorage.___u0]
  ... truncated ...
```
