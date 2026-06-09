# DirectUI::MetadataAPI::ImportClassInfo(Windows::UI::Xaml::Markup::IXamlType *,CClassInfo const * *)

- ea: `0x1801e99d4`
- end: `0x1801ea1b7`
- name: `?ImportClassInfo@MetadataAPI@DirectUI@@CAJPEAUIXamlType@Markup@Xaml@UI@Windows@@PEAPEBVCClassInfo@@@Z`
- size: `2019`
- prototype: `HRESULT __fastcall(Windows::UI::Xaml::Markup::IXamlType *pXamlType, const CClassInfo **ppType)`
- caller_count: `2`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801e9520`
- `0x180591518`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x180021840`
- `0x1800af8e0`
- `0x1800d0fc4`
- `0x1800fdd4c`
- `0x1800fe130`
- `0x180100978`
- `0x180131190`
- `0x18017ffdc`
- `0x18018fa54`
- `0x1801e99d4`
- `0x1801ea1c0`
- `0x1801ea358`
- `0x1801eae28`
- `0x1801eaf54`
- `0x1801ed584`
- `0x1801edb58`
- `0x18021e4e0`
- `0x180363614`
- `0x18055214c`
- `0x18059a7f8`
- `0x1806b2e84`
- `0x1807796ac`
- `0x180779718`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801e9a3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801e9a3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801e9edc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801e9edc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9e80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9e8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9e80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9e8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ea05a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ea05a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801e9b4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801e9b4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1801e9b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1801e9b61`

## pseudocode

```c
__int64 __fastcall DirectUI::MetadataAPI::ImportClassInfo(
        Windows::UI::Xaml::Markup::IXamlType *pXamlType,
        const CClassInfo **ppType)
{
  Windows::UI::Xaml::Markup::IXamlType_vtbl *v3; // rax
  HRESULT (__fastcall *get_BaseType)(Windows::UI::Xaml::Markup::IXamlType *, Windows::UI::Xaml::Markup::IXamlType **); // rbx
  HRESULT v5; // eax
  HRESULT v6; // ebx
  Windows::UI::Xaml::Markup::IXamlType_vtbl *v7; // rax
  HRESULT ClassInfoByTypeName; // eax
  HRESULT ClassInfoByXamlType; // eax
  int v10; // eax
  UINT32 StringLen; // eax
  HRESULT v12; // ecx
  const xstring_ptr_storage *v13; // rbx
  HRESULT NamespaceByName; // eax
  KnownPropertyIndex v15; // r12
  int v16; // edx
  HSTRING Handle; // rcx
  int v18; // ebx
  DesignerMode v19; // ecx
  const Windows::UI::Xaml::Interop::TypeName *v20; // r14
  DirectUI::DynamicMetadataStorage *Instance; // rax
  const CClassInfo *v22; // r13
  KnownPropertyIndex v23; // r15
  const CDependencyProperty *FailFast; // rdi
  __int64 v25; // rcx
  KnownPropertyIndex v26; // cx
  KnownTypeIndex v27; // ax
  HRESULT v28; // eax
  DirectUI::DynamicMetadataStorage *v29; // rax
  DirectUI::DynamicMetadataStorage *v30; // rax
  DirectUI::DynamicMetadataStorage *v31; // rax
  std::unique_ptr<CCustomClassInfo> *Mylast; // rdx
  HRESULT (__fastcall *get_ContentProperty)(Windows::UI::Xaml::Markup::IXamlType *, Windows::UI::Xaml::Markup::IXamlMember **); // rbx
  Windows::UI::Xaml::Markup::IXamlType *v34; // rcx
  Windows::UI::Xaml::Markup::IXamlType2 *v35; // rcx
  Windows::UI::Xaml::Markup::IXamlMember *v36; // rcx
  Windows::UI::Xaml::Markup::IXamlType *v37; // rcx
  Windows::UI::Xaml::Markup::IXamlType2 *ptr; // rdi
  HRESULT (__fastcall *get_BoxedType)(Windows::UI::Xaml::Markup::IXamlType2 *, Windows::UI::Xaml::Markup::IXamlType **); // rbx
  std::default_delete<TypeNamePtr> **v41; // rax
  std::default_delete<TypeNamePtr> *v42; // rcx
  TypeNamePtr *v43; // rdx
  xstring_ptr strFullName; // [rsp+20h] [rbp-A9h] BYREF
  int m_nIndex; // [rsp+28h] [rbp-A1h]
  ctl::ComPtr<Windows::UI::Xaml::Markup::IXamlType> spBoxedType; // [rsp+30h] [rbp-99h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Markup::IXamlType2> spXamlType2; // [rsp+38h] [rbp-91h] BYREF
  xstring_ptr strKey; // [rsp+40h] [rbp-89h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Markup::IXamlMember> spXamlContentProperty; // [rsp+48h] [rbp-81h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Markup::IXamlType> spBaseXamlType; // [rsp+50h] [rbp-79h] BYREF
  HSTRING string[2]; // [rsp+60h] [rbp-69h] BYREF
  const CClassInfo *pBaseType; // [rsp+70h] [rbp-59h] BYREF
  HSTRING__ *hFullName; // [rsp+78h] [rbp-51h] BYREF
  Windows::UI::Xaml::Interop::TypeName typeName; // [rsp+80h] [rbp-49h] BYREF
  const CClassInfo *boxedType; // [rsp+90h] [rbp-39h] BYREF
  xephemeral_string_ptr strNamespaceName; // [rsp+98h] [rbp-31h] BYREF
  xephemeral_string_ptr strTypeName; // [rsp+B0h] [rbp-19h] BYREF
  Windows::UI::Xaml::Interop::TypeName v58; // [rsp+D0h] [rbp+7h] BYREF
  unsigned __int8 bFlag; // [rsp+130h] [rbp+67h] BYREF
  const CClassInfo **v60; // [rsp+138h] [rbp+6Fh]
  unsigned __int8 isBindable; // [rsp+140h] [rbp+77h] BYREF
  const CDependencyProperty *pContentProperty; // [rsp+148h] [rbp+7Fh] BYREF

  v60 = ppType;
  spBaseXamlType.ptr_ = 0;
  spXamlContentProperty.ptr_ = 0;
  pBaseType = 0;
  boxedType = 0;
  typeName = 0;
  hFullName = 0;
  strKey.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  strFullName.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  strNamespaceName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  strTypeName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  bFlag = 0;
  isBindable = 0;
  EnterCriticalSection(&g_csStatic);
  if ( pXamlType )
    pXamlType->AddRef(pXamlType);
  v3 = pXamlType->__vftable;
  spXamlType2.ptr_ = 0;
  spBoxedType.ptr_ = 0;
  get_BaseType = v3->get_BaseType;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spBaseXamlType);
  v5 = get_BaseType(pXamlType, &spBaseXamlType.ptr_);
  v6 = v5;
  if ( v5 < 0 )
  {
    OnFailure_2990_(v5);
    goto $Cleanup_1159;
  }
  if ( spBaseXamlType.ptr_ )
  {
    v7 = spBaseXamlType.ptr_->__vftable;
    *(_OWORD *)string = 0;
    ClassInfoByTypeName = v7->get_UnderlyingType(spBaseXamlType.ptr_, (Windows::UI::Xaml::Interop::TypeName *)string);
    v6 = ClassInfoByTypeName;
    if ( ClassInfoByTypeName < 0
      || (v58 = *(Windows::UI::Xaml::Interop::TypeName *)string,
          ClassInfoByTypeName = DirectUI::MetadataAPI::GetClassInfoByTypeName(&v58, &pBaseType),
          v6 = ClassInfoByTypeName,
          ClassInfoByTypeName < 0) )
    {
      OnFailure_2990_(ClassInfoByTypeName);
    }
    WindowsDeleteString(string[0]);
    if ( v6 < 0 )
    {
      OnFailure_2990_(v6);
      goto $Cleanup_1159;
    }
  }
  else
  {
    pBaseType = DirectUI::MetadataAPI::GetClassInfoByIndex(UnknownType);
  }
  m_nIndex = 0;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spXamlType2);
  if ( pXamlType->QueryInterface(pXamlType, &GUID_9f0c6e3b_433b_56ad_8f69_78a4dd3e64f9, (void **)&spXamlType2) >= 0 )
  {
    ptr = spXamlType2.ptr_;
    get_BoxedType = spXamlType2.ptr_->get_BoxedType;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spBoxedType);
    ClassInfoByXamlType = get_BoxedType(ptr, &spBoxedType.ptr_);
    v6 = ClassInfoByXamlType;
    if ( ClassInfoByXamlType < 0 )
      goto LABEL_88;
    if ( spBoxedType.ptr_ )
    {
      ClassInfoByXamlType = DirectUI::MetadataAPI::GetClassInfoByXamlType(spBoxedType.ptr_, &boxedType);
      v6 = ClassInfoByXamlType;
      if ( ClassInfoByXamlType < 0 )
        goto LABEL_88;
      m_nIndex = (unsigned __int16)boxedType->m_nIndex;
    }
  }
  ClassInfoByXamlType = pXamlType->get_UnderlyingType(pXamlType, &typeName);
  v6 = ClassInfoByXamlType;
  if ( ClassInfoByXamlType >= 0 )
  {
    string[0] = 0;
    LODWORD(string[1]) = 0;
    v10 = WindowsDuplicateString(typeName.Name, string);
    v6 = v10;
    if ( v10 < 0 )
    {
      OnFailure_2990_(v10);
    }
    else
    {
      StringLen = WindowsGetStringLen(string[0]);
      if ( StringLen <= 0x3FFFFFFF )
      {
        v13 = (const xstring_ptr_storage *)((unsigned __int64)string[0] | 1);
        LODWORD(string[1]) = StringLen & 0x3FFFFFFF | 0x80000000;
        xencoded_string_ptr::Reset((xruntime_string_ptr *)&strKey);
        strKey.m_encodedStorage.Storage = v13;
        if ( typeName.Kind != TypeKind_Custom )
        {
          xstring_ptr::operator=(&strFullName, &strKey);
          goto LABEL_15;
        }
        ClassInfoByXamlType = pXamlType->get_FullName(pXamlType, &hFullName);
        v6 = ClassInfoByXamlType;
        if ( ClassInfoByXamlType >= 0 )
        {
          NamespaceByName = xstring_ptr::CloneRuntimeStringHandle(hFullName, &strFullName);
          v6 = NamespaceByName;
          if ( NamespaceByName < 0 )
            goto LABEL_69;
LABEL_15:
          NamespaceByName = DirectUI::MetadataAPI::ExtractNamespaceNameAndShortName(
                              &strFullName,
                              &strNamespaceName,
                              &strTypeName);
          v6 = NamespaceByName;
          if ( NamespaceByName < 0 )
            goto LABEL_69;
          v15 = UnknownType_UnknownProperty;
          LODWORD(pContentProperty) = 0;
          if ( ((__int64)strNamespaceName.m_encodedStorage.Storage & 1) != 0 )
          {
            Handle = (HSTRING)(strNamespaceName.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
          }
          else
          {
            v16 = *(_DWORD *)(strNamespaceName.m_encodedStorage.RuntimeStringHandleMarker + 8);
            Handle = strNamespaceName.m_encodedStorage.Storage->Handle;
            if ( v16 >= 0 )
            {
              LODWORD(pContentProperty) = v16 & 0x3FFFFFFF;
              goto LABEL_19;
            }
          }
          Handle = (HSTRING)WindowsGetStringRawBuffer(Handle, (UINT32 *)&pContentProperty);
LABEL_19:
          if ( Handle && (_DWORD)pContentProperty && *(_WORD *)Handle )
          {
            pContentProperty = 0;
            NamespaceByName = DirectUI::MetadataAPI::GetNamespaceByName(
                                &strNamespaceName,
                                (const CNamespaceInfo **)&pContentProperty);
            v6 = NamespaceByName;
            if ( NamespaceByName < 0 )
              goto LABEL_69;
            v15 = pContentProperty->m_nIndex;
          }
          v18 = 37121;
          if ( pXamlType->get_IsConstructible(pXamlType, &bFlag) >= 0 && bFlag )
            v18 = 37123;
          if ( pXamlType->get_IsCollection(pXamlType, &bFlag) >= 0 && bFlag )
            v18 |= 8u;
          if ( pXamlType->get_IsDictionary(pXamlType, &bFlag) >= 0 && bFlag )
            v18 |= 0x10u;
          if ( pXamlType->get_IsMarkupExtension(pXamlType, &bFlag) >= 0 && bFlag )
            v18 |= 0x20u;
          pXamlType->get_IsBindable(pXamlType, &isBindable);
          LOBYTE(v19) = 1;
          v20 = (const Windows::UI::Xaml::Interop::TypeName *)((unsigned __int64)&typeName
                                                             & -(__int64)DesignerInterop::GetDesignerMode(v19));
          LOBYTE(pContentProperty) = isBindable != 0;
          Instance = DirectUI::DynamicMetadataStorage::GetInstance();
          v22 = pBaseType;
          v23 = ((__int64)(unsigned int)(LODWORD(Instance->m_customTypesCache._Mypair._Myval2._Mylast)
                                       - LODWORD(Instance->m_customTypesCache._Mypair._Myval2._Myfirst)) >> 3)
              + 1084;
          FailFast = (const CDependencyProperty *)XcpAllocation::OSMemoryAllocateFailFast(0x30u);
          if ( FailFast )
          {
            *(_DWORD *)&FailFast[3].m_nDeclaringTypeIndex = 0;
            HIBYTE(FailFast[3].m_flags) = 0;
            *(_QWORD *)&FailFast->m_nIndex = 0;
            *(_QWORD *)&FailFast->m_flags = 0;
            *(_QWORD *)&FailFast[1].m_nDeclaringTypeIndex = 0;
            *(_QWORD *)&FailFast[2].m_nIndex = &xstring_ptr_constants::c_xstring_ptr_storage_null;
            *(_QWORD *)&FailFast[2].m_flags = &xstring_ptr_constants::c_xstring_ptr_storage_null;
          }
          else
          {
            FailFast = 0;
          }
          BYTE2(FailFast[3].m_flags) = (_BYTE)pContentProperty;
          LOWORD(FailFast[3].m_flags) = v15;
          FailFast->m_nPropertyTypeIndex = v22->m_nIndex;
          FailFast->m_nIndex = v23;
          *(_DWORD *)&FailFast->m_nDeclaringTypeIndex = v18;
          if ( *(Windows::UI::Xaml::Markup::IXamlType **)&FailFast->m_flags != pXamlType )
          {
            pXamlType->AddRef(pXamlType);
            v25 = *(_QWORD *)&FailFast->m_flags;
            *(_QWORD *)&FailFast->m_flags = pXamlType;
            if ( v25 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          v26 = CClassInfo::GetContentProperty(v22)->m_nIndex;
          v27 = (__int16)m_nIndex;
          FailFast[3].m_nDeclaringTypeIndex = v26;
          FailFast[3].m_nTargetTypeIndex = v27;
          if ( v20 )
          {
            v41 = (std::default_delete<TypeNamePtr> **)std::make_unique<TypeNamePtr,Windows::UI::Xaml::Interop::TypeName const &,0>(
                                                         (std::unique_ptr<TypeNamePtr> *)&pContentProperty,
                                                         v20);
            v42 = *v41;
            *v41 = 0;
            v43 = *(TypeNamePtr **)&FailFast[1].m_nDeclaringTypeIndex;
            *(_QWORD *)&FailFast[1].m_nDeclaringTypeIndex = v42;
            if ( v43 )
              std::default_delete<TypeNamePtr>::operator()(v42, v43);
            if ( pContentProperty )
              std::default_delete<TypeNamePtr>::operator()(v42, (TypeNamePtr *)pContentProperty);
          }
          v28 = xstring_ptr_view::Promote(&strTypeName.xstring_ptr_view, (xstring_ptr *)&FailFast[2]);
          v6 = v28;
          if ( v28 < 0
            || (v28 = xstring_ptr_view::Promote(&strFullName, (xstring_ptr *)&FailFast[2].m_flags), v6 = v28, v28 < 0) )
          {
            OnFailure_2990_(v28);
            OnFailure_2990_(v6);
            goto $Cleanup_1159;
          }
          pContentProperty = FailFast;
          v29 = DirectUI::DynamicMetadataStorage::GetInstance();
          *containers::vector_map<xstring_ptr,CClassInfo const *,std::less<void>,std::allocator<std::pair<xstring_ptr,CClassInfo const *>>>::operator[](
             &v29->m_customTypesByNameCache,
             &strFullName) = (const CClassInfo *)FailFast;
          if ( typeName.Kind == TypeKind_Custom )
          {
            v30 = DirectUI::DynamicMetadataStorage::GetInstance();
            *containers::vector_map<xstring_ptr,CClassInfo const *,std::less<void>,std::allocator<std::pair<xstring_ptr,CClassInfo const *>>>::operator[](
               &v30->m_customTypesByCustomNameCache,
               &strKey) = (const CClassInfo *)FailFast;
          }
          v31 = DirectUI::DynamicMetadataStorage::GetInstance();
          Mylast = v31->m_customTypesCache._Mypair._Myval2._Mylast;
          if ( Mylast == v31->m_customTypesCache._Mypair._Myval2._Myend )
          {
            std::vector<std::unique_ptr<CCustomClassInfo>>::_Emplace_reallocate<CCustomClassInfo * &>(
              &v31->m_customTypesCache,
              Mylast,
              (CCustomClassInfo **)&pContentProperty);
            FailFast = pContentProperty;
          }
          else
          {
            Mylast->_Mypair._Myval2 = (CCustomClassInfo *)FailFast;
            ++v31->m_customTypesCache._Mypair._Myval2._Mylast;
          }
          get_ContentProperty = pXamlType->get_ContentProperty;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spXamlContentProperty);
          NamespaceByName = get_ContentProperty(pXamlType, &spXamlContentProperty.ptr_);
          v6 = NamespaceByName;
          if ( NamespaceByName < 0 )
            goto LABEL_69;
          if ( !spXamlContentProperty.ptr_ )
            goto LABEL_50;
          pContentProperty = 0;
          NamespaceByName = DirectUI::MetadataAPI::ImportPropertyInfo(
                              (const CClassInfo *)FailFast,
                              spXamlContentProperty.ptr_,
                              &pContentProperty);
          v6 = NamespaceByName;
          if ( NamespaceByName >= 0 )
          {
            FailFast[3].m_nDeclaringTypeIndex = pContentProperty->m_nIndex;
LABEL_50:
            if ( !CQuirksMode2::XamlQuirkIsEnabled(0x20086u)
              || (NamespaceByName = CClassInfo::RunClassConstructorIfNecessary((CClassInfo *)FailFast),
                  v6 = NamespaceByName,
                  NamespaceByName >= 0) )
            {
              *v60 = (const CClassInfo *)FailFast;
              goto $Cleanup_1159;
            }
          }
LABEL_69:
          OnFailure_2990_(NamespaceByName);
          goto $Cleanup_1159;
        }
        goto LABEL_88;
      }
      v6 = -2147467259;
      OnNewFailure_1208_(v12);
    }
    OnFailure_2990_(v6);
    goto $Cleanup_1159;
  }
LABEL_88:
  OnFailure_2990_(ClassInfoByXamlType);
$Cleanup_1159:
  WindowsDeleteString(typeName.Name);
  WindowsDeleteString(hFullName);
  v34 = spBoxedType.ptr_;
  if ( spBoxedType.ptr_ )
  {
    spBoxedType.ptr_ = 0;
    v34->Release(v34);
  }
  v35 = spXamlType2.ptr_;
  if ( spXamlType2.ptr_ )
  {
    spXamlType2.ptr_ = 0;
    v35->Release(v35);
  }
  pXamlType->Release(pXamlType);
  LeaveCriticalSection(&g_csStatic);
  strTypeName.m_ephemeralStorage = xstring_ptr_constants::c_xstring_ptr_storage_null;
  strNamespaceName.m_ephemeralStorage = xstring_ptr_constants::c_xstring_ptr_storage_null;
  strTypeName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  strNamespaceName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  xstring_ptr::~xstring_ptr(&strFullName);
  xstring_ptr::~xstring_ptr(&strKey);
  v36 = spXamlContentProperty.ptr_;
  if ( spXamlContentProperty.ptr_ )
  {
    spXamlContentProperty.ptr_ = 0;
    v36->Release(v36);
  }
  v37 = spBaseXamlType.ptr_;
  if ( spBaseXamlType.ptr_ )
  {
    spBaseXamlType.ptr_ = 0;
    v37->Release(v37);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801e99d4  mov     [rsp-8+arg_8], ppType
0x1801e99d9  push    rbp
0x1801e99da  push    rbx
0x1801e99db  push    rsi
0x1801e99dc  push    rdi
0x1801e99dd  push    r12
0x1801e99df  push    r13
0x1801e99e1  push    r14
0x1801e99e3  push    r15
0x1801e99e5  lea     rbp, [rsp-1Fh]
0x1801e99ea  sub     rsp, 0E8h
0x1801e99f1  xor     r15d, r15d
0x1801e99f4  lea     r14, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1801e99fb  mov     rsi, pXamlType
0x1801e99fe  mov     [rbp+57h+spBaseXamlType.ptr_], r15
0x1801e9a02  xorps   xmm0, xmm0
0x1801e9a05  mov     [rsp+120h+spXamlContentProperty.ptr_], r15
0x1801e9a0a  lea     pXamlType, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801e9a11  mov     [rbp+57h+pBaseType], r15
0x1801e9a15  mov     [rbp+57h+boxedType], r15
0x1801e9a19  movups  xmmword ptr [rbp+57h+typeName.Name], xmm0
0x1801e9a1d  mov     [rbp+57h+hFullName], r15
0x1801e9a21  mov     qword ptr [rsp+120h+strKey.m_encodedStorage.___u0], r14
0x1801e9a26  mov     qword ptr [rsp+120h+strFullName.m_encodedStorage.___u0], r14
0x1801e9a2b  mov     qword ptr [rbp+57h+strNamespaceName.m_encodedStorage.___u0], r14
0x1801e9a2f  mov     qword ptr [rbp+57h+strTypeName.m_encodedStorage.___u0], r14
0x1801e9a33  mov     [rbp+57h+bFlag], r15b
0x1801e9a37  mov     [rbp+57h+isBindable], r15b
0x1801e9a3b  call    cs:__imp_EnterCriticalSection
0x1801e9a41  test    rsi, rsi
0x1801e9a44  jz      short loc_1801E9A55
0x1801e9a46  mov     rax, [rsi]
0x1801e9a49  mov     pXamlType, rsi
0x1801e9a4c  mov     rax, [rax+8]
0x1801e9a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9a55  mov     rax, [rsi]
0x1801e9a58  lea     pXamlType, [rbp+57h+spBaseXamlType]; this
0x1801e9a5c  mov     [rsp+120h+spXamlType2.ptr_], r15
0x1801e9a61  mov     [rsp+120h+spBoxedType.ptr_], r15
0x1801e9a66  mov     rbx, [rax+30h]
0x1801e9a6a  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1801e9a6f  lea     ppType, [rbp+57h+spBaseXamlType]
0x1801e9a73  mov     pXamlType, rsi
0x1801e9a76  mov     rax, rbx
0x1801e9a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9a7e  mov     ebx, eax
0x1801e9a80  test    eax, eax
0x1801e9a82  js      loc_1801EA0E3
0x1801e9a88  mov     pXamlType, [rbp+57h+spBaseXamlType.ptr_]; eTypeIndex
0x1801e9a8c  test    pXamlType, pXamlType
0x1801e9a8f  jz      loc_1801E9F66
0x1801e9a95  mov     rax, [pXamlType]
0x1801e9a98  lea     ppType, [rbp+57h+string]
0x1801e9a9c  xorps   xmm0, xmm0
0x1801e9a9f  movups  xmmword ptr [rbp+57h+string], xmm0
0x1801e9aa3  mov     rax, [rax+88h]
0x1801e9aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9aaf  mov     ebx, eax
0x1801e9ab1  test    eax, eax
0x1801e9ab3  js      loc_1801EA0B0
0x1801e9ab9  movaps  xmm0, xmmword ptr [rbp+57h+string]
0x1801e9abd  lea     ppType, [rbp+57h+pBaseType]
0x1801e9ac1  lea     pXamlType, [rbp+57h+var_50]
0x1801e9ac5  movdqa  [rbp+57h+var_50], xmm0
0x1801e9aca  call    ?GetClassInfoByTypeName@MetadataAPI@DirectUI@@SAJUTypeName@Interop@Xaml@UI@Windows@@PEAPEBVCClassInfo@@@Z; DirectUI::MetadataAPI::GetClassInfoByTypeName(Windows::UI::Xaml::Interop::TypeName,CClassInfo const * *)
0x1801e9acf  mov     ebx, eax
0x1801e9ad1  test    eax, eax
0x1801e9ad3  js      loc_1801EA112
0x1801e9ad9  mov     pXamlType, [rbp+57h+string]; string
0x1801e9add  call    cs:__imp_WindowsDeleteString
0x1801e9ae3  test    ebx, ebx
0x1801e9ae5  js      loc_1801EA11E
0x1801e9aeb  lea     pXamlType, [rsp+120h+spXamlType2]; this
0x1801e9af0  mov     [rsp+120h+var_F8], r15d
0x1801e9af5  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1801e9afa  mov     rax, [rsi]
0x1801e9afd  lea     r8, [rsp+120h+spXamlType2]
0x1801e9b02  lea     ppType, _GUID_9f0c6e3b_433b_56ad_8f69_78a4dd3e64f9
0x1801e9b09  mov     pXamlType, rsi
0x1801e9b0c  mov     rax, [rax]
0x1801e9b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9b14  test    eax, eax
0x1801e9b16  jns     loc_1801E9F74
0x1801e9b1c  mov     rax, [rsi]
0x1801e9b1f  lea     ppType, [rbp+57h+typeName]
0x1801e9b23  mov     pXamlType, rsi
0x1801e9b26  mov     rax, [rax+88h]
0x1801e9b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9b32  mov     ebx, eax
0x1801e9b34  test    eax, eax
0x1801e9b36  js      loc_1801EA1AB
0x1801e9b3c  mov     pXamlType, [rbp+57h+typeName.Name]; string
0x1801e9b40  lea     ppType, [rbp+57h+string]; newString
0x1801e9b44  xor     eax, eax
0x1801e9b46  mov     [rbp+57h+string], rax
0x1801e9b4a  mov     dword ptr [rbp+57h+string+8], eax
0x1801e9b4d  call    cs:__imp_WindowsDuplicateString
0x1801e9b53  mov     ebx, eax
0x1801e9b55  test    eax, eax
0x1801e9b57  js      loc_1801EA0C8
0x1801e9b5d  mov     pXamlType, [rbp+57h+string]; string
0x1801e9b61  call    cs:__imp_WindowsGetStringLen
0x1801e9b67  mov     edi, 3FFFFFFFh
0x1801e9b6c  cmp     eax, edi
0x1801e9b6e  ja      loc_1801EA19C
0x1801e9b74  mov     rbx, [rbp+57h+string]
0x1801e9b78  lea     pXamlType, [rsp+120h+strKey]; this
0x1801e9b7d  and     eax, edi
0x1801e9b7f  or      rbx, 1
0x1801e9b83  bts     eax, 1Fh
0x1801e9b87  mov     dword ptr [rbp+57h+string+8], eax
0x1801e9b8a  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1801e9b8f  cmp     [rbp+57h+typeName.Kind], 2
0x1801e9b93  mov     qword ptr [rsp+120h+strKey.m_encodedStorage.___u0], rbx
0x1801e9b98  jz      loc_1801E9FF0
0x1801e9b9e  lea     ppType, [rsp+120h+strKey]; other
0x1801e9ba3  lea     pXamlType, [rsp+120h+strFullName]; this
0x1801e9ba8  call    ??4xstring_ptr@@QEAAAEAV0@AEBV0@@Z; xstring_ptr::operator=(xstring_ptr const &)
0x1801e9bad  lea     r8, [rbp+57h+strTypeName]; pstrTypeName
0x1801e9bb1  lea     ppType, [rbp+57h+strNamespaceName]; pstrNamespaceName
0x1801e9bb5  lea     pXamlType, [rsp+120h+strFullName]; strTypeFullName
0x1801e9bba  call    ?ExtractNamespaceNameAndShortName@MetadataAPI@DirectUI@@CAJAEBVxstring_ptr_view@@PEAVxephemeral_string_ptr@@1@Z; DirectUI::MetadataAPI::ExtractNamespaceNameAndShortName(xstring_ptr_view const &,xephemeral_string_ptr *,xephemeral_string_ptr *)
0x1801e9bbf  mov     ebx, eax
0x1801e9bc1  test    eax, eax
0x1801e9bc3  js      loc_1801EA190
0x1801e9bc9  mov     rax, qword ptr [rbp+57h+strNamespaceName.m_encodedStorage.___u0]
0x1801e9bcd  mov     r12d, r15d
0x1801e9bd0  mov     dword ptr [rbp+57h+pContentProperty], r15d
0x1801e9bd4  test    al, 1
0x1801e9bd6  jnz     loc_1801EA04F
0x1801e9bdc  mov     edx, [rax+8]
0x1801e9bdf  mov     pXamlType, [rax]
0x1801e9be2  test    edx, edx
0x1801e9be4  js      loc_1801EA056
0x1801e9bea  and     edx, edi
0x1801e9bec  mov     dword ptr [rbp+57h+pContentProperty], edx
0x1801e9bef  test    pXamlType, pXamlType
0x1801e9bf2  jz      short loc_1801E9C23
0x1801e9bf4  cmp     dword ptr [rbp+57h+pContentProperty], r15d
0x1801e9bf8  jz      short loc_1801E9C23
0x1801e9bfa  cmp     r15w, [pXamlType]
0x1801e9bfe  jz      short loc_1801E9C23
0x1801e9c00  lea     ppType, [rbp+57h+pContentProperty]; ppNamespace
0x1801e9c04  mov     [rbp+57h+pContentProperty], r15
0x1801e9c08  lea     pXamlType, [rbp+57h+strNamespaceName]; strNamespaceName
0x1801e9c0c  call    ?GetNamespaceByName@MetadataAPI@DirectUI@@SAJAEBVxstring_ptr_view@@PEAPEBVCNamespaceInfo@@@Z; DirectUI::MetadataAPI::GetNamespaceByName(xstring_ptr_view const &,CNamespaceInfo const * *)
0x1801e9c11  mov     ebx, eax
0x1801e9c13  test    eax, eax
0x1801e9c15  js      loc_1801EA031
0x1801e9c1b  mov     rax, [rbp+57h+pContentProperty]
0x1801e9c1f  movzx   r12d, word ptr [rax]
0x1801e9c23  mov     rax, [rsi]
0x1801e9c26  lea     ppType, [rbp+57h+bFlag]
0x1801e9c2a  mov     pXamlType, rsi
0x1801e9c2d  mov     ebx, 9101h
0x1801e9c32  mov     rax, [rax+58h]
0x1801e9c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9c3b  test    eax, eax
0x1801e9c3d  js      short loc_1801E9C49
0x1801e9c3f  cmp     [rbp+57h+bFlag], r15b
0x1801e9c43  lea     eax, [rbx+2]
0x1801e9c46  cmovnz  ebx, eax
0x1801e9c49  mov     rax, [rsi]
0x1801e9c4c  lea     ppType, [rbp+57h+bFlag]
0x1801e9c50  mov     pXamlType, rsi
0x1801e9c53  mov     rax, [rax+50h]
0x1801e9c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9c5c  test    eax, eax
0x1801e9c5e  js      short loc_1801E9C69
0x1801e9c60  cmp     [rbp+57h+bFlag], r15b
0x1801e9c64  jz      short loc_1801E9C69
0x1801e9c66  or      ebx, 8
0x1801e9c69  mov     rax, [rsi]
0x1801e9c6c  lea     ppType, [rbp+57h+bFlag]
0x1801e9c70  mov     pXamlType, rsi
0x1801e9c73  mov     rax, [rax+60h]
0x1801e9c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9c7c  test    eax, eax
0x1801e9c7e  js      short loc_1801E9C8A
0x1801e9c80  cmp     [rbp+57h+bFlag], r15b
0x1801e9c84  jnz     loc_1801E9FD5
0x1801e9c8a  mov     rax, [rsi]
0x1801e9c8d  lea     ppType, [rbp+57h+bFlag]
0x1801e9c91  mov     pXamlType, rsi
0x1801e9c94  mov     rax, [rax+68h]
0x1801e9c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9c9d  test    eax, eax
0x1801e9c9f  js      short loc_1801E9CAB
0x1801e9ca1  cmp     [rbp+57h+bFlag], r15b
0x1801e9ca5  jnz     loc_1801EA142
0x1801e9cab  mov     rax, [rsi]
0x1801e9cae  lea     ppType, [rbp+57h+isBindable]
0x1801e9cb2  mov     pXamlType, rsi
0x1801e9cb5  mov     rax, [rax+70h]
0x1801e9cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9cbe  mov     cl, 1; mode
0x1801e9cc0  call    ?GetDesignerMode@DesignerInterop@@SA_NW4DesignerMode@@@Z; DesignerInterop::GetDesignerMode(DesignerMode)
0x1801e9cc5  neg     al
0x1801e9cc7  lea     rax, [rbp+57h+typeName]
0x1801e9ccb  sbb     r14, r14
0x1801e9cce  and     r14, rax
0x1801e9cd1  cmp     [rbp+57h+isBindable], r15b
0x1801e9cd5  setnz   byte ptr [rbp+57h+pContentProperty]
0x1801e9cd9  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x1801e9cde  mov     r13, [rbp+57h+pBaseType]
0x1801e9ce2  mov     ecx, 30h ; '0'; cSize
0x1801e9ce7  mov     r15d, [rax+68h]
0x1801e9ceb  sub     r15d, [rax+60h]
0x1801e9cef  mov     eax, 43Ch
0x1801e9cf4  sar     r15, 3
0x1801e9cf8  add     r15w, ax
0x1801e9cfc  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x1801e9d01  mov     rdi, rax
0x1801e9d04  xor     eax, eax
0x1801e9d06  test    rdi, rdi
0x1801e9d09  jz      loc_1801EA0DB
0x1801e9d0f  mov     [rdi+28h], eax
0x1801e9d12  mov     [rdi+2Fh], al
0x1801e9d15  mov     [rdi], rax
0x1801e9d18  mov     [rdi+8], rax
0x1801e9d1c  mov     [rdi+10h], rax
0x1801e9d20  lea     rax, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1801e9d27  mov     [rdi+18h], rax
0x1801e9d2b  mov     [rdi+20h], rax
0x1801e9d2f  mov     al, byte ptr [rbp+57h+pContentProperty]
0x1801e9d32  mov     [rdi+2Eh], al
0x1801e9d35  mov     [rdi+2Ch], r12w
0x1801e9d3a  movzx   eax, word ptr [r13+0]
0x1801e9d3f  mov     [rdi+2], ax
0x1801e9d43  mov     [rdi], r15w
0x1801e9d47  mov     [rdi+4], ebx
0x1801e9d4a  cmp     [rdi+8], rsi
0x1801e9d4e  jz      loc_1801EA14A
0x1801e9d54  mov     rax, [rsi]
0x1801e9d57  mov     pXamlType, rsi
0x1801e9d5a  mov     rax, [rax+8]
0x1801e9d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9d63  mov     pXamlType, [rdi+8]
0x1801e9d67  xor     r15d, r15d
0x1801e9d6a  mov     [rdi+8], rsi
0x1801e9d6e  test    pXamlType, pXamlType
0x1801e9d71  jz      short loc_1801E9D7F
0x1801e9d73  mov     rax, [pXamlType]
0x1801e9d76  mov     rax, [rax+10h]
0x1801e9d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9d7f  mov     pXamlType, r13; this
0x1801e9d82  call    ?GetContentProperty@CClassInfo@@QEBAPEBVCDependencyProperty@@XZ; CClassInfo::GetContentProperty(void)
0x1801e9d87  movzx   ecx, word ptr [rax]
0x1801e9d8a  mov     eax, [rsp+120h+var_F8]
0x1801e9d8e  mov     [rdi+28h], cx
0x1801e9d92  mov     [rdi+2Ah], ax
0x1801e9d96  test    r14, r14
0x1801e9d99  jnz     loc_1801EA152
0x1801e9d9f  lea     ppType, [rdi+18h]; pstrPromoted
0x1801e9da3  lea     pXamlType, [rbp+57h+strTypeName]; this
0x1801e9da7  call    ?Promote@xstring_ptr_view@@QEBAJPEAVxstring_ptr@@@Z; xstring_ptr_view::Promote(xstring_ptr *)
0x1801e9dac  mov     ebx, eax
0x1801e9dae  test    eax, eax
0x1801e9db0  js      loc_1801E9FDD
0x1801e9db6  lea     ppType, [rdi+20h]; pstrPromoted
0x1801e9dba  lea     pXamlType, [rsp+120h+strFullName]; this
0x1801e9dbf  call    ?Promote@xstring_ptr_view@@QEBAJPEAVxstring_ptr@@@Z; xstring_ptr_view::Promote(xstring_ptr *)
0x1801e9dc4  mov     ebx, eax
0x1801e9dc6  test    eax, eax
0x1801e9dc8  js      loc_1801EA184
0x1801e9dce  mov     [rbp+57h+pContentProperty], rdi
0x1801e9dd2  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x1801e9dd7  lea     ppType, [rsp+120h+strFullName]; key
0x1801e9ddc  lea     pXamlType, [rax+30h]; this
0x1801e9de0  call    ??A?$vector_map@Vxstring_ptr@@PEBVCClassInfo@@U?$less@X@std@@V?$allocator@U?$pair@Vxstring_ptr@@PEBVCClassInfo@@@std@@@4@@containers@@QEAAAEAPEBVCClassInfo@@AEBVxstring_ptr@@@Z; containers::vector_map<xstring_ptr,CClassInfo const *,std::less<void>,std::allocator<std::pair<xstring_ptr,CClassInfo const *>>>::operator[](xstring_ptr const &)
0x1801e9de5  mov     [rax], rdi
0x1801e9de8  cmp     [rbp+57h+typeName.Kind], 2
0x1801e9dec  jnz     short loc_1801E9E04
0x1801e9dee  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x1801e9df3  lea     ppType, [rsp+120h+strKey]; key
0x1801e9df8  lea     pXamlType, [rax+48h]; this
0x1801e9dfc  call    ??A?$vector_map@Vxstring_ptr@@PEBVCClassInfo@@U?$less@X@std@@V?$allocator@U?$pair@Vxstring_ptr@@PEBVCClassInfo@@@std@@@4@@containers@@QEAAAEAPEBVCClassInfo@@AEBVxstring_ptr@@@Z; containers::vector_map<xstring_ptr,CClassInfo const *,std::less<void>,std::allocator<std::pair<xstring_ptr,CClassInfo const *>>>::operator[](xstring_ptr const &)
0x1801e9e01  mov     [rax], rdi
0x1801e9e04  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x1801e9e09  lea     pXamlType, [rax+60h]; this
0x1801e9e0d  mov     ppType, [pXamlType+8]; _Whereptr
0x1801e9e11  cmp     ppType, [pXamlType+10h]
0x1801e9e15  jz      loc_1801EA03D
0x1801e9e1b  mov     [ppType], rdi
0x1801e9e1e  add     qword ptr [pXamlType+8], 8
0x1801e9e23  mov     rax, [rsi]
0x1801e9e26  lea     pXamlType, [rsp+120h+spXamlContentProperty]; this
0x1801e9e2b  mov     rbx, [rax+38h]
0x1801e9e2f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1801e9e34  lea     ppType, [rsp+120h+spXamlContentProperty]
0x1801e9e39  mov     pXamlType, rsi
0x1801e9e3c  mov     rax, rbx
0x1801e9e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9e44  mov     ebx, eax
0x1801e9e46  test    eax, eax
0x1801e9e48  js      loc_1801EA0BC
0x1801e9e4e  mov     ppType, [rsp+120h+spXamlContentProperty.ptr_]; pXamlProperty
0x1801e9e53  test    ppType, ppType
0x1801e9e56  jnz     loc_1801EA068
0x1801e9e5c  mov     ecx, 20086h; quirk
  ... truncated ...
```
