# CTargetPropertyPath::FromString(CREATEPARAMETERS *)

- ea: `0x18007171c`
- end: `0x180072474`
- name: `?FromString@CTargetPropertyPath@@QEAAJPEAVCREATEPARAMETERS@@@Z`
- size: `3416`
- prototype: `HRESULT __fastcall(CTargetPropertyPath *this, CREATEPARAMETERS *pCreate)`
- caller_count: `1`
- callee_count: `41`
- tags: `service_task`

## callers

- `0x18013394c`

## callees

- `0x180004bc0`
- `0x180021840`
- `0x180021970`
- `0x18003f598`
- `0x18006c2b0`
- `0x1800710d0`
- `0x18007171c`
- `0x1800738f0`
- `0x180083cf4`
- `0x18008e4e0`
- `0x180090014`
- `0x1800aabf0`
- `0x1800ab600`
- `0x1800af8e0`
- `0x1800c1484`
- `0x1800d627c`
- `0x1800f8380`
- `0x1800fdd4c`
- `0x1800fe130`
- `0x180100d88`
- `0x180131190`
- `0x180134408`
- `0x18017389c`
- `0x18017d850`
- `0x1801887c0`
- `0x18018fa54`
- `0x1802be9cc`
- `0x1802eb450`
- `0x180421044`
- `0x180430ae4`
- `0x1804828c4`
- `0x180494e04`
- `0x1804e025c`
- `0x18059ef38`
- `0x1805ead28`
- `0x1806877a8`
- `0x180687890`
- `0x180708660`
- `0x18076d6e0`
- `0x18076e110`
- `0x1807977b8`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18007200c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180072427`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18007200c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180072427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007179b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007179b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180071ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180071ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071f5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071f79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071f93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071fad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071fc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072035`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071f5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071f79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071f93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071fad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071fc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072035`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180071afe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180071f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180071afe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180071f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18007201e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18007201e`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall CTargetPropertyPath::FromString(CTargetPropertyPath *this, CREATEPARAMETERS *pCreate)
{
  XamlProperty *v2; // rdi
  unsigned int v3; // eax
  unsigned int v5; // eax
  __int64 Storage; // rbx
  std::_Ref_count_base *Rep; // rax
  XamlProperty *Ptr; // r12
  std::_Ref_count_base *v9; // r14
  HRESULT v10; // eax
  HRESULT AmbientValue; // esi
  XamlSchemaContext *v12; // r15
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  HRESULT v16; // r8d
  int v17; // ecx
  HSTRING v18; // r12
  CTargetPropertyPath *Ptr_low; // rcx
  char *v20; // rsi
  char *trivial_2; // rax
  __int64 v22; // r15
  char v23; // si
  bool v24; // r12
  int v25; // eax
  PCWSTR v26; // rsi
  int v27; // eax
  CValueDetails::Flags *m_value; // rax
  int m_asOne; // ecx
  wchar_t *v30; // rax
  int String; // eax
  std::_Ref_count_base *v32; // rcx
  int v34; // edx
  HSTRING v35; // rcx
  CTargetPropertyPath *v36; // r15
  HRESULT IsLocal; // eax
  int m_Bits; // eax
  HSTRING v39; // rcx
  const xstring_ptr_storage *v40; // rbx
  const CDependencyProperty *PropertyByIndexInline; // rax
  int v42; // edx
  HSTRING v43; // rcx
  const CDependencyProperty *v44; // rax
  unsigned int v45; // eax
  KnownTypeIndex m_typeHandle; // cx
  const CClassInfo *ClassInfoByIndex; // rax
  HRESULT v48; // eax
  int v49; // eax
  unsigned int StringLen; // eax
  HSTRING v51; // rcx
  PCWSTR StringRawBuffer; // rax
  HSTRING v53; // rcx
  CDependencyObject *v54; // rcx
  HRESULT v55; // eax
  HRESULT v56; // eax
  bool IsPathFullyQualifiedPropertyName; // bl
  HRESULT v58; // eax
  unsigned int Count; // eax
  CTargetPropertyPath *v60; // r15
  CNoParentShareableDependencyObject *FailFast; // rax
  CDependencyPropertyProxy *v62; // rbx
  HRESULT v63; // eax
  CDependencyObject *v64; // rbx
  HRESULT v65; // eax
  std::shared_ptr<XamlType> typeName; // [rsp+40h] [rbp-C0h] OVERLAPPED BYREF
  xstring_ptr targetName; // [rsp+50h] [rbp-B0h] BYREF
  std::shared_ptr<XamlSchemaContext> schemaContext; // [rsp+58h] [rbp-A8h] BYREF
  std::shared_ptr<XamlProperty> propertyName; // [rsp+68h] [rbp-98h] OVERLAPPED BYREF
  xstring_ptr fullPath; // [rsp+78h] [rbp-88h] BYREF
  bool v71; // [rsp+80h] [rbp-80h]
  std::shared_ptr<XamlType> xamlType; // [rsp+88h] [rbp-78h] BYREF
  std::shared_ptr<XamlType> spResolvedProperty; // [rsp+98h] [rbp-68h] OVERLAPPED BYREF
  CTargetPropertyPath *v74; // [rsp+A8h] [rbp-58h]
  std::shared_ptr<XamlProperty> xamlProperty; // [rsp+B0h] [rbp-50h] BYREF
  xephemeral_string_ptr parameters[1]; // [rsp+C0h] [rbp-40h] BYREF
  xruntime_string_ptr v77; // [rsp+D8h] [rbp-28h] BYREF
  CValueDetails::Flags v78; // [rsp+E0h] [rbp-20h] BYREF
  int v79; // [rsp+E8h] [rbp-18h]
  std::shared_ptr<XamlQualifiedObject> targetTypeValue; // [rsp+F0h] [rbp-10h] BYREF
  CValue propAsValue; // [rsp+100h] [rbp+0h] BYREF
  int v82; // [rsp+110h] [rbp+10h]

  v2 = (XamlProperty *)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  v3 = pCreate->m_value.m_flags.m_state.m_asOne & 0x3F;
  v74 = this;
  schemaContext._Ptr = (XamlSchemaContext *)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  if ( (_BYTE)v3 == 14 )
  {
    v5 = pCreate->m_value.m_value.m_any[1];
    LODWORD(fullPath.m_encodedStorage.Storage) = pCreate->m_value.m_value.m_any[0];
    HIDWORD(fullPath.m_encodedStorage.RuntimeStringHandleMarker) = v5;
    if ( ((__int64)fullPath.m_encodedStorage.Storage & 1) != 0 )
    {
      if ( WindowsDuplicateString(
             (HSTRING)(fullPath.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL),
             (HSTRING *)&xamlProperty) < 0 )
      {
        spResolvedProperty._Ptr = 0;
        LODWORD(typeName._Ptr) = 0;
        TraceForFailFast(-2147418113);
        OnNewFailureEncountered(-2147418113, 0, 0);
        GetStowedExceptionsForFailFast(
          (_STOWED_EXCEPTION_INFORMATION_V2 ***)&spResolvedProperty,
          (unsigned int *)&typeName);
        RoFailFastWithErrorContextInternal2(
          -2147418113,
          (unsigned int)typeName._Ptr,
          (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)spResolvedProperty._Ptr);
      }
      Storage = (__int64)xamlProperty._Ptr | 1;
    }
    else
    {
      Storage = (__int64)fullPath.m_encodedStorage.Storage;
    }
    xamlProperty._Ptr = (XamlProperty *)&xstring_ptr_constants::c_xstring_ptr_storage_null;
    if ( ((unsigned __int8)&xstring_ptr_constants::c_xstring_ptr_storage_null & 1) != 0 )
      WindowsDeleteString((HSTRING)((unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null
                                  & 0xFFFFFFFFFFFFFFFEuLL));
    xstring_ptr::~xstring_ptr((xstring_ptr *)&xamlProperty);
    fullPath.m_encodedStorage.Storage = (const xstring_ptr_storage *)Storage;
  }
  else
  {
    xstring_ptr::xstring_ptr(&fullPath, &CValueDetails::ValueTypeInfo<14>::Empty);
    Storage = (__int64)fullPath.m_encodedStorage.Storage;
  }
  xstring_ptr::~xstring_ptr((xstring_ptr *)&schemaContext);
  Rep = pCreate->m_spServiceProviderContext._Rep;
  xamlType = 0;
  if ( Rep )
    _InterlockedIncrement((volatile signed __int32 *)&Rep->_Uses);
  Ptr = (XamlProperty *)pCreate->m_spServiceProviderContext._Ptr;
  v9 = pCreate->m_spServiceProviderContext._Rep;
  xamlProperty._Ptr = Ptr;
  schemaContext = 0;
  v10 = XamlServiceProviderContext::GetSchemaContext((XamlServiceProviderContext *)Ptr, &schemaContext);
  AmbientValue = v10;
  if ( v10 < 0 )
  {
    OnFailure_2990_(v10);
LABEL_65:
    if ( schemaContext._Rep )
      std::_Ref_count_base::_Decref(schemaContext._Rep);
    goto LABEL_67;
  }
  v12 = schemaContext._Ptr;
  LODWORD(propertyName._Ptr) = 268435726;
  targetTypeValue = 0;
  spResolvedProperty = 0;
  *(_OWORD *)&parameters[0].m_encodedStorage.Storage = 0;
  propAsValue = 0;
  v13 = XamlSchemaContext::GetXamlType(schemaContext._Ptr, (const XamlTypeToken *)&propertyName, &spResolvedProperty);
  AmbientValue = v13;
  if ( v13 < 0 )
  {
    OnFailure_2990_(v13);
LABEL_62:
    v32 = spResolvedProperty._Rep;
    goto LABEL_63;
  }
  LODWORD(propertyName._Ptr) = 268436163;
  v14 = XamlSchemaContext::GetXamlType(
          v12,
          (const XamlTypeToken *)&propertyName,
          (std::shared_ptr<XamlType> *)parameters);
  AmbientValue = v14;
  if ( v14 < 0 )
  {
    OnFailure_2990_(v14);
LABEL_60:
    if ( parameters[0].m_ephemeralStorage.Buffer )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)parameters[0].m_ephemeralStorage.Buffer);
    goto LABEL_62;
  }
  LODWORD(propertyName._Ptr) = 268435499;
  LODWORD(typeName._Ptr) = 268435813;
  v15 = XamlSchemaContext::GetXamlProperty(
          v12,
          (const XamlPropertyToken *)&typeName,
          (const XamlTypeToken *)&propertyName,
          (std::shared_ptr<XamlProperty> *)&propAsValue);
  AmbientValue = v15;
  if ( v15 < 0 )
  {
    OnFailure_2990_(v15);
    if ( propAsValue.m_flags )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&propAsValue.m_flags);
    goto LABEL_60;
  }
  typeName = 0;
  propertyName = 0;
  AmbientValue = XamlServiceProviderContext::GetAmbientValue(
                   (XamlServiceProviderContext *)Ptr,
                   &spResolvedProperty,
                   (const std::shared_ptr<XamlType> *)parameters,
                   (const std::shared_ptr<XamlProperty> *)&propAsValue,
                   &propertyName,
                   &typeName,
                   None,
                   &targetTypeValue);
  if ( propertyName._Rep )
    std::_Ref_count_base::_Decref(propertyName._Rep);
  if ( typeName._Rep )
    std::_Ref_count_base::_Decref(typeName._Rep);
  if ( AmbientValue < 0 )
  {
    OnFailure_2990_(AmbientValue);
    if ( propAsValue.m_flags )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&propAsValue.m_flags);
    if ( parameters[0].m_ephemeralStorage.Buffer )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)parameters[0].m_ephemeralStorage.Buffer);
    if ( spResolvedProperty._Rep )
      std::_Ref_count_base::_Decref(spResolvedProperty._Rep);
    goto LABEL_109;
  }
  if ( propAsValue.m_flags )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&propAsValue.m_flags);
  if ( parameters[0].m_ephemeralStorage.Buffer )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)parameters[0].m_ephemeralStorage.Buffer);
  if ( spResolvedProperty._Rep )
    std::_Ref_count_base::_Decref(spResolvedProperty._Rep);
  if ( targetTypeValue._Ptr )
  {
    v45 = targetTypeValue._Ptr->m_value.m_flags.m_state.m_asOne & 0x3F;
    if ( v45 == 24 )
    {
      spResolvedProperty._Ptr = 0;
      v48 = DoPointerCast<CType>((CType **)&spResolvedProperty, &targetTypeValue._Ptr->m_value, v16);
      AmbientValue = v48;
      if ( v48 < 0 )
      {
LABEL_116:
        OnFailure_2990_(v48);
LABEL_109:
        v32 = targetTypeValue._Rep;
LABEL_63:
        if ( v32 )
          std::_Ref_count_base::_Decref(v32);
        goto LABEL_65;
      }
      if ( !spResolvedProperty._Ptr )
        goto LABEL_25;
      m_typeHandle = (KnownTypeIndex)spResolvedProperty._Ptr->m_spXamlNamespace._Rep;
    }
    else
    {
      if ( v45 != 28 )
        goto LABEL_25;
      m_typeHandle = targetTypeValue._Ptr->m_value.m_value.m_typeHandle;
    }
    if ( m_typeHandle == UnknownType )
      goto LABEL_25;
    ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex(m_typeHandle);
    XamlTypeToken::FromType((XamlTypeToken *)&propertyName, ClassInfoByIndex);
    v48 = XamlSchemaContext::GetXamlType(v12, (const XamlTypeToken *)&propertyName, &xamlType);
    AmbientValue = v48;
    if ( v48 >= 0 )
      goto LABEL_25;
    goto LABEL_116;
  }
LABEL_25:
  if ( targetTypeValue._Rep )
    std::_Ref_count_base::_Decref(targetTypeValue._Rep);
  if ( schemaContext._Rep )
    std::_Ref_count_base::_Decref(schemaContext._Rep);
  LODWORD(typeName._Ptr) = 0;
  v71 = xamlType._Ptr != 0;
  targetName.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  schemaContext._Ptr = (XamlSchemaContext *)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  if ( (Storage & 1) != 0 )
  {
    v51 = (HSTRING)(Storage & 0xFFFFFFFFFFFFFFFEuLL);
LABEL_138:
    StringRawBuffer = WindowsGetStringRawBuffer(v51, (UINT32 *)&typeName);
    Ptr_low = (CTargetPropertyPath *)LODWORD(typeName._Ptr);
    v18 = (HSTRING)StringRawBuffer;
    goto LABEL_32;
  }
  v17 = *(_DWORD *)(Storage + 8);
  v18 = *(HSTRING *)Storage;
  if ( v17 < 0 )
  {
    v51 = *(HSTRING *)Storage;
    goto LABEL_138;
  }
  Ptr_low = (CTargetPropertyPath *)(v17 & 0x3FFFFFFF);
  LODWORD(typeName._Ptr) = (_DWORD)Ptr_low;
LABEL_32:
  if ( !(_DWORD)Ptr_low
    || (v20 = (char *)v18 + 2 * (unsigned int)Ptr_low,
        trivial_2 = (char *)_std_find_trivial_2(v18, v20, 0x2Eu),
        trivial_2 == v20) )
  {
    LODWORD(v22) = -1;
  }
  else
  {
    v22 = (trivial_2 - (char *)v18) >> 1;
    if ( (_DWORD)v22 != -1 )
    {
      v23 = 1;
      goto LABEL_36;
    }
  }
  v23 = 0;
LABEL_36:
  v24 = v71;
  if ( v71 )
  {
    typeName._Ptr = (XamlType *)&xstring_ptr_constants::c_xstring_ptr_storage_null;
    propertyName._Ptr = (XamlProperty *)&xstring_ptr_constants::c_xstring_ptr_storage_null;
    IsPathFullyQualifiedPropertyName = CTargetPropertyPath::IsPathFullyQualifiedPropertyName(Ptr_low, &fullPath, v22);
    xstring_ptr::operator=((xstring_ptr *)&schemaContext, &fullPath);
    if ( IsPathFullyQualifiedPropertyName )
    {
      v58 = xstring_ptr_view::SubString(&fullPath, 1u, v22, (xstring_ptr *)&typeName);
      AmbientValue = v58;
      if ( v58 < 0
        || (Count = xstring_ptr_view::GetCount(&fullPath),
            v58 = xstring_ptr_view::SubString(&fullPath, (int)v22 + 1, Count - 1, (xstring_ptr *)&propertyName),
            AmbientValue = v58,
            v58 < 0)
        || (v58 = XamlServiceProviderContext::ResolveXamlType(
                    (XamlServiceProviderContext *)xamlProperty._Ptr,
                    (const xstring_ptr_view *)&typeName,
                    &xamlType),
            AmbientValue = v58,
            v58 < 0) )
      {
LABEL_183:
        OnFailure_2990_(v58);
LABEL_161:
        xstring_ptr::~xstring_ptr((xstring_ptr *)&propertyName);
        xstring_ptr::~xstring_ptr((xstring_ptr *)&typeName);
        goto LABEL_129;
      }
      v60 = v74;
    }
    else
    {
      v60 = v74;
      if ( v23 )
      {
        v58 = CDependencyObject::SetAndOriginateError(v74, -2146496512, RuntimeError, 0xFD0u, 0, 0);
        AmbientValue = v58;
        if ( v58 < 0 )
          goto LABEL_183;
      }
      xstring_ptr::operator=((xstring_ptr *)&propertyName, &fullPath);
    }
    xamlProperty = 0;
    if ( xamlType._Ptr
      && XamlType::GetDependencyProperty(xamlType._Ptr, (const xstring_ptr *)&propertyName, &xamlProperty) >= 0 )
    {
      spResolvedProperty._Ptr = 0;
      FailFast = (CNoParentShareableDependencyObject *)XcpAllocation::OSMemoryAllocateFailFast(0x78u);
      v62 = (CDependencyPropertyProxy *)FailFast;
      if ( FailFast )
      {
        CNoParentShareableDependencyObject::CNoParentShareableDependencyObject(
          FailFast,
          v60->m_sharedState.m_ptr->m_value.m_coreServices);
        v62->m_nPropertyIndex = 0;
        v62->__vftable = (CDependencyPropertyProxy_vtbl *)CDependencyPropertyProxy::`vftable';
      }
      else
      {
        v62 = 0;
      }
      v63 = xref_ptr<CDependencyPropertyProxy>::init<CDependencyPropertyProxy>(
              (xref_ptr<CDependencyPropertyProxy> *)&spResolvedProperty,
              v62);
      AmbientValue = v63;
      if ( v63 < 0 )
      {
        OnFailure_2990_(v63);
        v54 = (CDependencyObject *)spResolvedProperty._Ptr;
        if ( !spResolvedProperty._Ptr )
          goto LABEL_159;
        goto LABEL_158;
      }
      v64 = (CDependencyObject *)spResolvedProperty._Ptr;
      v65 = CDependencyPropertyProxy::FromXamlProperty(
              (CDependencyPropertyProxy *)spResolvedProperty._Ptr,
              &xamlProperty);
      AmbientValue = v65;
      if ( v65 >= 0 )
      {
        propAsValue = 0;
        CValue::Set<24>(&propAsValue, v64);
        v56 = CDependencyObject::SetValueByKnownIndex(v60, TargetPropertyPath_CachedStyleSetterProperty, &propAsValue);
        AmbientValue = v56;
        if ( v56 < 0 )
        {
          OnFailure_2990_(v56);
          CValue::ReleaseAndReset(&propAsValue);
          goto LABEL_159;
        }
        CValue::ReleaseAndReset(&propAsValue);
LABEL_119:
        if ( xamlProperty._Rep )
          std::_Ref_count_base::_Decref(xamlProperty._Rep);
        xstring_ptr::~xstring_ptr((xstring_ptr *)&propertyName);
        xstring_ptr::~xstring_ptr((xstring_ptr *)&typeName);
        goto LABEL_122;
      }
      OnFailure_2990_(v65);
      if ( v64 )
      {
        v54 = v64;
LABEL_158:
        CDependencyObject::Release(v54);
      }
    }
    else
    {
      `vector constructor iterator'(
        (void *)parameters,
        0x14u,
        1u,
        (void *(__fastcall *)(void *))xstring_ptr::xstring_ptr);
      xephemeral_string_ptr::Decode((const xencoded_string_ptr *)&schemaContext, parameters);
      v55 = CDependencyObject::SetAndOriginateError(v60, -2146496512, RuntimeError, 0xFCFu, 1u, parameters);
      AmbientValue = v55;
      if ( v55 >= 0 )
      {
        `vector destructor iterator'(
          (void *)parameters,
          0x14u,
          1u,
          (void (__fastcall *)(void *))xephemeral_string_ptr::~xephemeral_string_ptr);
        goto LABEL_119;
      }
      OnFailure_2990_(v55);
      `vector destructor iterator'(
        (void *)parameters,
        0x14u,
        1u,
        (void (__fastcall *)(void *))xephemeral_string_ptr::~xephemeral_string_ptr);
    }
LABEL_159:
    if ( xamlProperty._Rep )
      std::_Ref_count_base::_Decref(xamlProperty._Rep);
    goto LABEL_161;
  }
  if ( !v23 )
    goto LABEL_73;
  propAsValue.m_value = (CValueDetails::Value)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  LODWORD(typeName._Ptr) = 0;
  if ( (Storage & 1) != 0 )
  {
    v26 = WindowsGetStringRawBuffer((HSTRING)(Storage & 0xFFFFFFFFFFFFFFFEuLL), (UINT32 *)&typeName);
  }
  else
  {
    v25 = *(_DWORD *)(Storage + 8);
    v26 = *(PCWSTR *)Storage;
    if ( v25 < 0 )
      v26 = WindowsGetStringRawBuffer(*(HSTRING *)Storage, (UINT32 *)&typeName);
    else
      LODWORD(typeName._Ptr) = v25 & 0x3FFFFFFF;
  }
  if ( (unsigned int)v22 > LODWORD(typeName._Ptr) )
  {
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&propAsValue);
    m_value = (CValueDetails::Flags *)propAsValue.m_value;
  }
  else
  {
    v77.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
    if ( (unsigned int)v22 > 0x3FFFFFFF )
    {
      spResolvedProperty._Ptr = 0;
      LODWORD(propertyName._Ptr) = 0;
      TraceForFailFast(-2147418113);
      OnNewFailureEncountered(-2147418113, 0, 0);
      GetStowedExceptionsForFailFast(
        (_STOWED_EXCEPTION_INFORMATION_V2 ***)&spResolvedProperty,
        (unsigned int *)&propertyName);
      RoFailFastWithErrorContextInternal2(
        -2147418113,
        (unsigned int)propertyName._Ptr,
        (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)spResolvedProperty._Ptr);
    }
    v78 = (CValueDetails::Flags)v26;
    v79 = v22 & 0x3FFFFFFF | 0x40000000;
    xencoded_string_ptr::Reset(&v77);
    v77.m_encodedStorage.Storage = (const xstring_ptr_storage *)&v78;
    if ( ((unsigned __int8)&v78 & 1) != 0 )
    {
      LODWORD(propertyName._Ptr) = 0;
      propAsValue.m_flags = (CValueDetails::Flags)WindowsGetStringRawBuffer((HSTRING)&v78, (UINT32 *)&propertyName);
      v27 = (__int64)propertyName._Ptr & 0x3FFFFFFF;
    }
    else
    {
      propAsValue.m_flags = v78;
      v27 = v79;
    }
    v82 = v27 & 0x3FFFFFFF | 0x40000000;
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&propAsValue);
    m_value = &propAsValue.m_flags;
    propAsValue.m_value = (CValueDetails::Value)&propAsValue.m_flags;
  }
  if ( !propAsValue.m_value.m_bool )
  {
    if ( !m_value || (m_value[1].m_state.m_asOne & 0x40000000) == 0 )
    {
      propertyName._Ptr = (XamlProperty *)m_value;
      goto LABEL_124;
    }
    LODWORD(typeName._Ptr) = 0;
    if ( ((unsigned __int8)m_value & 1) != 0 )
    {
      v30 = (wchar_t *)((unsigned __int64)m_value & 0xFFFFFFFFFFFFFFFEuLL);
    }
    else
    {
      m_asOne = m_value[1].m_state.m_asOne;
      v30 = (wchar_t *)*m_value;
      if ( m_asOne >= 0 )
      {
        LODWORD(typeName._Ptr) = m_asOne & 0x3FFFFFFF;
        goto LABEL_53;
      }
    }
    v30 = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)v30, (UINT32 *)&typeName);
LABEL_53:
    String = WindowsCreateString(v30, (UINT32)typeName._Ptr, (HSTRING *)&propertyName);
    AmbientValue = String;
    if ( String < 0 )
    {
LABEL_54:
      OnFailure_2990_(String);
      OnFailure_2990_(AmbientValue);
      OnFailure_2990_(AmbientValue);
LABEL_129:
      xstring_ptr::~xstring_ptr((xstring_ptr *)&schemaContext);
      xstring_ptr::~xstring_ptr(&targetName);
LABEL_67:
      if ( v9 )
        std::_Ref_count_base::_Decref(v9);
      if ( xamlType._Rep )
        std::_Ref_count_base::_Decref(xamlType._Rep);
      xstring_ptr::~xstring_ptr(&fullPath);
      return (unsigned int)AmbientValue;
    }
    goto LABEL_134;
  }
  String = WindowsDuplicateString(
             (HSTRING)((unsigned __int64)m_value & 0xFFFFFFFFFFFFFFFEuLL),
             (HSTRING *)&propertyName);
  AmbientValue = String;
  if ( String < 0 )
    goto LABEL_54;
LABEL_134:
  propertyName._Ptr = (XamlProperty *)((unsigned __int64)propertyName._Ptr | 1);
LABEL_124:
  xencoded_string_ptr::Reset((xruntime_string_ptr *)&targetName);
  v2 = propertyName._Ptr;
  targetName.m_encodedStorage.Storage = (const xstring_ptr_storage *)propertyName._Ptr;
  if ( (Storage & 1) != 0 )
  {
    v53 = (HSTRING)(Storage & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v49 = *(_DWORD *)(Storage + 8);
    if ( v49 >= 0 )
    {
      StringLen = v49 & 0x3FFFFFFF;
      goto LABEL_127;
    }
    v53 = *(HSTRING *)Storage;
  }
  StringLen = WindowsGetStringLen(v53);
LABEL_127:
  IsLocal = xstring_ptr_view::SubString(&fullPath, (int)v22 + 1, StringLen, (xstring_ptr *)&schemaContext);
  AmbientValue = IsLocal;
  if ( IsLocal < 0 )
  {
LABEL_128:
    OnFailure_2990_(IsLocal);
    goto LABEL_129;
  }
LABEL_73:
  if ( CQuirksMode2::XamlQuirkIsEnabled(0x200C6u) )
  {
LABEL_122:
    v36 = v74;
    goto LABEL_81;
  }
  LODWORD(typeName._Ptr) = 0;
  if ( ((__int64)schemaContext._Ptr & 1) != 0 )
  {
    v35 = (HSTRING)((unsigned __int64)schemaContext._Ptr & 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_140;
  }
  v34 = (int)schemaContext._Ptr->_Wptr._Rep;
  v35 = (HSTRING)schemaContext._Ptr->_Wptr._Ptr;
  if ( v34 < 0 )
  {
LABEL_140:
    v35 = (HSTRING)WindowsGetStringRawBuffer(v35, (UINT32 *)&typeName);
    goto LABEL_77;
  }
  LODWORD(typeName._Ptr) = v34 & 0x3FFFFFFF;
LABEL_77:
  if ( !v35 || !LODWORD(typeName._Ptr) )
    goto LABEL_122;
  v36 = v74;
  if ( *(_WORD *)v35 )
  {
    IsLocal = CTargetPropertyPath::ResolveFullyQualifiedPropertyNames(
                v74,
                (const xstring_ptr *)&schemaContext,
                (XamlServiceProviderContext *)xamlProperty._Ptr);
    AmbientValue = IsLocal;
    if ( IsLocal < 0 )
      goto LABEL_128;
  }
LABEL_81:
  LODWORD(typeName._Ptr) = 0;
  if ( ((unsigned __int8)v2 & 1) != 0 )
  {
    v39 = (HSTRING)((unsigned __int64)v2 & 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_142;
  }
  m_Bits = v2->m_flagsBoolPropertyBits.m_Bits;
  v39 = (HSTRING)v2->__vftable;
  if ( m_Bits < 0 )
  {
LABEL_142:
    v39 = (HSTRING)WindowsGetStringRawBuffer(v39, (UINT32 *)&typeName);
    goto LABEL_84;
  }
  LODWORD(typeName._Ptr) = m_Bits & 0x3FFFFFFF;
LABEL_84:
  if ( v39 && LODWORD(typeName._Ptr) && *(_WORD *)v39 )
  {
    if ( &v36->m_targetName != &targetName )
    {
      v40 = xstring_ptr::CloneNonEphemeralEncodedStorage(&targetName).Storage;
      xencoded_string_ptr::Reset((xruntime_string_ptr *)&v36->m_targetName);
      v36->m_targetName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)v40->Buffer;
    }
    PropertyByIndexInline = CDependencyObject::GetPropertyByIndexInline(v36, TargetPropertyPath_Target);
    IsLocal = CDependencyObject::SetPropertyIsLocal(v36, PropertyByIndexInline);
    AmbientValue = IsLocal;
    if ( IsLocal < 0 )
      goto LABEL_128;
  }
  else if ( !v24 )
  {
    IsLocal = CDependencyObject::SetAndOriginateError(v36, -2146496512, RuntimeError, 0xFCBu, 0, 0);
    AmbientValue = IsLocal;
    if ( IsLocal < 0 )
      goto LABEL_128;
  }
  LODWORD(typeName._Ptr) = 0;
  if ( ((__int64)schemaContext._Ptr & 1) != 0 )
  {
    v43 = (HSTRING)((unsigned __int64)schemaContext._Ptr & 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_144;
  }
  v42 = (int)schemaContext._Ptr->_Wptr._Rep;
  v43 = (HSTRING)schemaContext._Ptr->_Wptr._Ptr;
  if ( v42 < 0 )
  {
LABEL_144:
    v43 = (HSTRING)WindowsGetStringRawBuffer(v43, (UINT32 *)&typeName);
    goto LABEL_93;
  }
  LODWORD(typeName._Ptr) = v42 & 0x3FFFFFFF;
LABEL_93:
  if ( v43 && LODWORD(typeName._Ptr) && *(_WORD *)v43 )
  {
    v44 = CDependencyObject::GetPropertyByIndexInline(v36, TargetPropertyPath_Path);
    IsLocal = CDependencyObject::SetPropertyIsLocal(v36, v44);
    AmbientValue = IsLocal;
    if ( IsLocal < 0 )
      goto LABEL_128;
    xstring_ptr::operator=(&v36->m_pathString, (const xstring_ptr *)&schemaContext);
  }
  else
  {
    IsLocal = CDependencyObject::SetAndOriginateError(v36, -2146496512, RuntimeError, 0xFCAu, 0, 0);
    AmbientValue = IsLocal;
    if ( IsLocal < 0 )
      goto LABEL_128;
  }
  xstring_ptr::~xstring_ptr((xstring_ptr *)&schemaContext);
  xstring_ptr::~xstring_ptr(&targetName);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  if ( xamlType._Rep )
    std::_Ref_count_base::_Decref(xamlType._Rep);
  xstring_ptr::~xstring_ptr(&fullPath);
  return 0;
}

```

## disassembly

```asm
0x18007171c  mov     [rsp-8+arg_10], rbx
0x180071721  push    rbp
0x180071722  push    rsi
0x180071723  push    rdi
0x180071724  push    r12
0x180071726  push    r13
0x180071728  push    r14
0x18007172a  push    r15
0x18007172c  lea     rbp, [rsp-20h]
0x180071731  sub     rsp, 120h
0x180071738  mov     rax, cs:__security_cookie
0x18007173f  xor     rax, rsp
0x180071742  mov     [rbp+50h+var_38], rax
0x180071746  mov     eax, [pCreate+8]
0x180071749  lea     rdi, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x180071750  and     eax, 3Fh
0x180071753  mov     [rbp+50h+var_A8], this
0x180071757  xor     r13d, r13d
0x18007175a  mov     [rsp+150h+schemaContext._Ptr], rdi
0x18007175f  mov     r14, pCreate
0x180071762  mov     ebx, 8000FFFFh
0x180071767  cmp     al, 0Eh
0x180071769  jnz     loc_1800721D0
0x18007176f  mov     ecx, [pCreate]
0x180071771  mov     eax, [pCreate+4]
0x180071774  mov     dword ptr [rsp+150h+fullPath.m_encodedStorage.___u0], ecx
0x180071778  mov     dword ptr [rsp+150h+fullPath.m_encodedStorage.___u0+4], eax
0x18007177c  test    cl, 1
0x18007177f  jnz     loc_180071AF1
0x180071785  mov     rbx, qword ptr [rsp+150h+fullPath.m_encodedStorage.___u0]
0x18007178a  mov     [rbp+50h+xamlProperty._Ptr], rdi
0x18007178e  test    dil, 1
0x180071792  jz      short loc_1800717A1
0x180071794  mov     this, rdi
0x180071797  and     this, 0FFFFFFFFFFFFFFFEh; string
0x18007179b  call    cs:__imp_WindowsDeleteString
0x1800717a1  lea     this, [rbp+50h+xamlProperty]; this
0x1800717a5  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800717aa  mov     qword ptr [rsp+150h+fullPath.m_encodedStorage.___u0], rbx
0x1800717af  lea     this, [rsp+150h+schemaContext]; this
0x1800717b4  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800717b9  mov     rax, [r14+20h]
0x1800717bd  xorps   xmm0, xmm0
0x1800717c0  movdqu  xmmword ptr [rbp+50h+xamlType._Ptr], xmm0
0x1800717c5  test    rax, rax
0x1800717c8  jz      short loc_1800717CE
0x1800717ca  lock inc dword ptr [rax+8]
0x1800717ce  mov     r12, [r14+18h]
0x1800717d2  lea     pCreate, [rsp+150h+schemaContext]; rspSchemaContext
0x1800717d7  mov     r14, [r14+20h]
0x1800717db  mov     this, r12; this
0x1800717de  mov     [rbp+50h+xamlProperty._Ptr], r12
0x1800717e2  movdqu  xmmword ptr [rsp+150h+schemaContext._Ptr], xmm0
0x1800717e8  call    ?GetSchemaContext@XamlServiceProviderContext@@QEAAJAEAV?$shared_ptr@VXamlSchemaContext@@@std@@@Z; XamlServiceProviderContext::GetSchemaContext(std::shared_ptr<XamlSchemaContext> &)
0x1800717ed  mov     esi, eax
0x1800717ef  test    eax, eax
0x1800717f1  js      loc_180072067
0x1800717f7  mov     r15, [rsp+150h+schemaContext._Ptr]
0x1800717fc  lea     r8, [rbp+50h+spResolvedProperty]; outXamlType
0x180071800  xorps   xmm0, xmm0
0x180071803  mov     dword ptr [rsp+150h+propertyName.m_encodedStorage.___u0], 1000010Eh
0x18007180b  xorps   xmm1, xmm1
0x18007180e  lea     pCreate, [rsp+150h+propertyName]; inTypeToken
0x180071813  mov     this, r15; this
0x180071816  movdqu  xmmword ptr [rbp+50h+targetTypeValue._Ptr], xmm0
0x18007181b  movdqu  xmmword ptr [rbp+50h+spResolvedProperty.m_ptr], xmm1
0x180071820  movdqu  xmmword ptr [rbp+50h+parameters.m_encodedStorage.___u0], xmm0
0x180071825  movdqu  xmmword ptr [rbp+50h+propAsValue.m_value], xmm1
0x18007182a  call    ?GetXamlType@XamlSchemaContext@@QEAAJAEBUXamlTypeToken@@AEAV?$shared_ptr@VXamlType@@@std@@@Z; XamlSchemaContext::GetXamlType(XamlTypeToken const &,std::shared_ptr<XamlType> &)
0x18007182f  mov     esi, eax
0x180071831  test    eax, eax
0x180071833  js      loc_180071DB3
0x180071839  lea     r8, [rbp+50h+parameters]; outXamlType
0x18007183d  mov     dword ptr [rsp+150h+propertyName.m_encodedStorage.___u0], 100002C3h
0x180071845  lea     pCreate, [rsp+150h+propertyName]; inTypeToken
0x18007184a  mov     this, r15; this
0x18007184d  call    ?GetXamlType@XamlSchemaContext@@QEAAJAEBUXamlTypeToken@@AEAV?$shared_ptr@VXamlType@@@std@@@Z; XamlSchemaContext::GetXamlType(XamlTypeToken const &,std::shared_ptr<XamlType> &)
0x180071852  mov     esi, eax
0x180071854  test    eax, eax
0x180071856  js      loc_180071BA7
0x18007185c  lea     r9, [rbp+50h+propAsValue]; outXamlProperty
0x180071860  mov     dword ptr [rsp+150h+propertyName.m_encodedStorage.___u0], 1000002Bh
0x180071868  lea     r8, [rsp+150h+propertyName]; inPropertyTypeToken
0x18007186d  mov     dword ptr [rsp+150h+typeName.m_encodedStorage.___u0], 10000165h
0x180071875  lea     pCreate, [rsp+150h+typeName]; inPropertyToken
0x18007187a  mov     this, r15; this
0x18007187d  call    ?GetXamlProperty@XamlSchemaContext@@QEAAJAEBUXamlPropertyToken@@AEBUXamlTypeToken@@AEAV?$shared_ptr@VXamlProperty@@@std@@@Z; XamlSchemaContext::GetXamlProperty(XamlPropertyToken const &,XamlTypeToken const &,std::shared_ptr<XamlProperty> &)
0x180071882  mov     esi, eax
0x180071884  test    eax, eax
0x180071886  js      loc_180071B19
0x18007188c  lea     rax, [rbp+50h+targetTypeValue]
0x180071890  xorps   xmm0, xmm0
0x180071893  mov     [rsp+150h+rqoValue], rax; rqoValue
0x180071898  lea     r9, [rbp+50h+propAsValue]; spProperty1
0x18007189c  lea     rax, [rsp+150h+typeName]
0x1800718a1  mov     [rsp+150h+cacheHint], r13d; cacheHint
0x1800718a6  mov     [rsp+150h+spTypeToFind], rax; spTypeToFind
0x1800718ab  lea     r8, [rbp+50h+parameters]; spCeilingType2
0x1800718af  lea     rax, [rsp+150h+propertyName]
0x1800718b4  xorps   xmm1, xmm1
0x1800718b7  lea     pCreate, [rbp+50h+spResolvedProperty]; spCeilingType1
0x1800718bb  mov     [rsp+150h+spProperty2], rax; spProperty2
0x1800718c0  mov     this, r12; this
0x1800718c3  movdqu  xmmword ptr [rsp+150h+typeName.m_encodedStorage.___u0], xmm0
0x1800718c9  movdqu  xmmword ptr [rsp+150h+propertyName.m_encodedStorage.___u0], xmm1
0x1800718cf  call    ?GetAmbientValue@XamlServiceProviderContext@@QEAAJAEBV?$shared_ptr@VXamlType@@@std@@0AEBV?$shared_ptr@VXamlProperty@@@3@10W4CompressedStackCacheHint@@AEAV?$shared_ptr@UXamlQualifiedObject@@@3@@Z; XamlServiceProviderContext::GetAmbientValue(std::shared_ptr<XamlType> const &,std::shared_ptr<XamlType> const &,std::shared_ptr<XamlProperty> const &,std::shared_ptr<XamlProperty> const &,std::shared_ptr<XamlType> const &,CompressedStackCacheHint,std::shared_ptr<XamlQualifiedObject> &)
0x1800718d4  mov     this, [rsp+150h+var_E0]; this
0x1800718d9  mov     esi, eax
0x1800718db  test    this, this
0x1800718de  jz      short loc_1800718E5
0x1800718e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800718e5  mov     this, [rsp+150h+var_108]; this
0x1800718ea  test    this, this
0x1800718ed  jz      short loc_1800718F4
0x1800718ef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800718f4  test    esi, esi
0x1800718f6  js      loc_180071D79
0x1800718fc  mov     this, qword ptr [rbp+50h+propAsValue.m_flags]; this
0x180071900  test    this, this
0x180071903  jz      short loc_18007190A
0x180071905  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007190a  mov     this, qword ptr [rbp+50h+parameters.m_ephemeralStorage.___u0]; this
0x18007190e  test    this, this
0x180071911  jz      short loc_180071918
0x180071913  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071918  mov     this, [rbp+50h+var_B0]; this
0x18007191c  test    this, this
0x18007191f  jz      short loc_180071926
0x180071921  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071926  mov     this, [rbp+50h+targetTypeValue._Ptr]
0x18007192a  test    this, this
0x18007192d  jnz     loc_180071DBF
0x180071933  mov     this, [rbp+50h+targetTypeValue._Rep]; this
0x180071937  test    this, this
0x18007193a  jz      short loc_180071941
0x18007193c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071941  mov     this, [rsp+150h+schemaContext._Rep]; this
0x180071946  test    this, this
0x180071949  jz      short loc_180071950
0x18007194b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071950  cmp     [rbp+50h+xamlType._Ptr], r13
0x180071954  mov     dword ptr [rsp+150h+typeName.m_encodedStorage.___u0], r13d
0x180071959  mov     r13, rbx
0x18007195c  setnz   [rbp+50h+var_D0]
0x180071960  mov     qword ptr [rsp+150h+targetName.m_encodedStorage.___u0], rdi
0x180071965  mov     [rsp+150h+schemaContext._Ptr], rdi
0x18007196a  and     r13d, 1
0x18007196e  jnz     loc_180071F4F
0x180071974  mov     ecx, [rbx+8]
0x180071977  mov     r12, [rbx]
0x18007197a  test    ecx, ecx
0x18007197c  js      loc_180072073
0x180071982  and     ecx, 3FFFFFFFh
0x180071988  mov     dword ptr [rsp+150h+typeName.m_encodedStorage.___u0], ecx
0x18007198c  test    ecx, ecx
0x18007198e  jz      loc_180071EF0
0x180071994  mov     eax, ecx
0x180071996  mov     r8d, 2Eh ; '.'; _Val
0x18007199c  mov     this, r12; _First
0x18007199f  lea     rsi, [r12+rax*2]
0x1800719a3  mov     pCreate, rsi; _Last
0x1800719a6  call    __std_find_trivial_2
0x1800719ab  mov     r15, rax
0x1800719ae  cmp     rax, rsi
0x1800719b1  jz      loc_180071EF0
0x1800719b7  sub     r15, r12
0x1800719ba  sar     r15, 1
0x1800719bd  cmp     r15d, 0FFFFFFFFh
0x1800719c1  jz      loc_180071EF4
0x1800719c7  mov     sil, 1
0x1800719ca  mov     r12b, [rbp+50h+var_D0]
0x1800719ce  test    r12b, r12b
0x1800719d1  jnz     loc_180072224
0x1800719d7  test    sil, sil
0x1800719da  jz      loc_180071BB3
0x1800719e0  mov     qword ptr [rbp+50h+propAsValue.m_value], rdi
0x1800719e4  mov     dword ptr [rsp+150h+typeName.m_encodedStorage.___u0], 0
0x1800719ec  test    r13, r13
0x1800719ef  jnz     loc_180071FBB
0x1800719f5  mov     eax, [rbx+8]
0x1800719f8  mov     rsi, [rbx]
0x1800719fb  test    eax, eax
0x1800719fd  js      loc_18007207B
0x180071a03  and     eax, 3FFFFFFFh
0x180071a08  mov     dword ptr [rsp+150h+typeName.m_encodedStorage.___u0], eax
0x180071a0c  cmp     r15d, dword ptr [rsp+150h+typeName.m_encodedStorage.___u0]
0x180071a11  ja      loc_180071F35
0x180071a17  mov     qword ptr [rbp+50h+var_78.m_encodedStorage.___u0], rdi
0x180071a1b  cmp     r15d, 3FFFFFFFh
0x180071a22  ja      loc_1800723EE
0x180071a28  mov     [rbp+50h+var_70], rsi
0x180071a2c  lea     this, [rbp+50h+var_78]; this
0x180071a30  mov     esi, 3FFFFFFFh
0x180071a35  mov     eax, r15d
0x180071a38  and     eax, esi
0x180071a3a  lea     edi, [rsi+1]
0x180071a3d  or      eax, edi
0x180071a3f  mov     [rbp+50h+var_68], eax
0x180071a42  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x180071a47  lea     rax, [rbp+50h+var_70]
0x180071a4b  mov     qword ptr [rbp+50h+var_78.m_encodedStorage.___u0], rax
0x180071a4f  lea     rax, [rbp+50h+var_70]
0x180071a53  test    al, 1
0x180071a55  jnz     loc_180072040
0x180071a5b  mov     rax, [rbp+50h+var_70]
0x180071a5f  mov     qword ptr [rbp+50h+propAsValue.m_flags], rax
0x180071a63  mov     eax, [rbp+50h+var_68]
0x180071a66  and     eax, esi
0x180071a68  lea     this, [rbp+50h+propAsValue]; this
0x180071a6c  or      eax, edi
0x180071a6e  mov     [rbp+50h+var_40], eax
0x180071a71  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x180071a76  lea     rax, [rbp+50h+propAsValue.m_flags]
0x180071a7a  mov     qword ptr [rbp+50h+propAsValue.m_value], rax
0x180071a7e  test    byte ptr [rbp+50h+propAsValue.m_value], 1
0x180071a82  jnz     loc_180071F05
0x180071a88  test    rax, rax
0x180071a8b  jz      loc_180071E7E
0x180071a91  test    [rax+8], edi
0x180071a94  jz      loc_180071E7E
0x180071a9a  mov     dword ptr [rsp+150h+typeName.m_encodedStorage.___u0], r13d
0x180071a9f  test    al, 1
0x180071aa1  jnz     loc_180072029
0x180071aa7  mov     ecx, [rax+8]
0x180071aaa  mov     rax, [rax]
0x180071aad  test    ecx, ecx
0x180071aaf  js      loc_18007202D
0x180071ab5  and     ecx, esi
0x180071ab7  mov     dword ptr [rsp+150h+typeName.m_encodedStorage.___u0], ecx
0x180071abb  mov     edx, dword ptr [rsp+150h+typeName.m_encodedStorage.___u0]; length
0x180071abf  lea     r8, [rsp+150h+propertyName]; string
0x180071ac4  mov     this, rax; sourceString
0x180071ac7  call    cs:__imp_WindowsCreateString
0x180071acd  mov     esi, eax
0x180071acf  test    eax, eax
0x180071ad1  jns     loc_180071F21
0x180071ad7  mov     ecx, eax; failedFrameHR
0x180071ad9  call    OnFailure_2990_
0x180071ade  mov     ecx, esi; failedFrameHR
0x180071ae0  call    OnFailure_2990_
0x180071ae5  mov     ecx, esi; failedFrameHR
0x180071ae7  call    OnFailure_2990_
0x180071aec  jmp     loc_180071ED7
0x180071af1  mov     this, qword ptr [rsp+150h+fullPath.m_encodedStorage.___u0]
0x180071af6  lea     pCreate, [rbp+50h+xamlProperty]; newString
0x180071afa  and     this, 0FFFFFFFFFFFFFFFEh; string
0x180071afe  call    cs:__imp_WindowsDuplicateString
0x180071b04  test    eax, eax
0x180071b06  js      loc_180071FD8
0x180071b0c  mov     rbx, [rbp+50h+xamlProperty._Ptr]
0x180071b10  or      rbx, 1
0x180071b14  jmp     loc_18007178A
0x180071b19  mov     ecx, eax; failedFrameHR
0x180071b1b  call    OnFailure_2990_
0x180071b20  mov     this, qword ptr [rbp+50h+propAsValue.m_flags]; this
0x180071b24  test    this, this
0x180071b27  jz      short loc_180071B2E
0x180071b29  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071b2e  mov     this, qword ptr [rbp+50h+parameters.m_ephemeralStorage.___u0]; this
0x180071b32  test    this, this
0x180071b35  jz      short loc_180071B3C
0x180071b37  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071b3c  mov     this, [rbp+50h+var_B0]; this
0x180071b40  test    this, this
0x180071b43  jz      short loc_180071B4A
0x180071b45  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071b4a  mov     this, [rsp+150h+schemaContext._Rep]; this
0x180071b4f  test    this, this
0x180071b52  jz      short loc_180071B59
0x180071b54  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071b59  test    r14, r14
0x180071b5c  jz      short loc_180071B66
0x180071b5e  mov     this, r14; this
0x180071b61  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071b66  mov     this, [rbp+50h+xamlType._Rep]; this
0x180071b6a  test    this, this
0x180071b6d  jz      short loc_180071B74
0x180071b6f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071b74  lea     this, [rsp+150h+fullPath]; this
0x180071b79  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180071b7e  mov     eax, esi
0x180071b80  mov     this, [rbp+50h+var_38]
0x180071b84  xor     this, rsp; StackCookie
0x180071b87  call    __security_check_cookie
0x180071b8c  mov     rbx, [rsp+150h+arg_10]
0x180071b94  add     rsp, 120h
0x180071b9b  pop     r15
0x180071b9d  pop     r14
0x180071b9f  pop     r13
0x180071ba1  pop     r12
0x180071ba3  pop     rdi
0x180071ba4  pop     rsi
0x180071ba5  pop     rbp
0x180071ba6  retn
0x180071ba7  mov     ecx, eax; failedFrameHR
0x180071ba9  call    OnFailure_2990_
0x180071bae  jmp     loc_180071B2E
0x180071bb3  xor     r13d, r13d
0x180071bb6  mov     ecx, 200C6h; quirk
0x180071bbb  call    ?XamlQuirkIsEnabled@CQuirksMode2@@SA_NK@Z; CQuirksMode2::XamlQuirkIsEnabled(ulong)
  ... truncated ...
```
