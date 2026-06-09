# DirectUI::MetadataAPI::GetClassInfoFromObject_Helper(IInspectable *,CClassInfo const * *,bool)

- ea: `0x1801e67c4`
- end: `0x1801e6f47`
- name: `?GetClassInfoFromObject_Helper@MetadataAPI@DirectUI@@CAJPEAUIInspectable@@PEAPEBVCClassInfo@@_N@Z`
- size: `1923`
- prototype: `HRESULT __fastcall(IInspectable *pInstance, const CClassInfo **ppType, bool resolveWinRTPropertyOtherType)`
- caller_count: `28`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800cdbe4`
- `0x1800cea98`
- `0x1800f46e8`
- `0x1801e4588`
- `0x1801e5dbc`
- `0x1801e6470`
- `0x1801e7368`
- `0x180373cf4`
- `0x18045acb0`
- `0x1805aab30`
- `0x1805e378c`
- `0x18061dd58`
- `0x18068a0b8`
- `0x1806ab044`
- `0x1806abaac`
- `0x1806c9df4`
- `0x180755450`
- `0x18087c640`
- `0x1808fcf20`
- `0x18090ec3c`
- `0x180914320`
- `0x180914510`
- `0x1809146f0`
- `0x180914aa0`
- `0x180915210`
- `0x1809233d0`
- `0x1809fe630`
- `0x180a00c0c`

## callees

- `0x180004bc0`
- `0x180021840`
- `0x1800adbb0`
- `0x1800d0c0c`
- `0x1800d0fc4`
- `0x1800d1f5c`
- `0x1800fe130`
- `0x180100978`
- `0x18017ffdc`
- `0x18018fa54`
- `0x1801e67c4`
- `0x1801e783c`
- `0x1801e9520`
- `0x18021e4e0`
- `0x1804c7a1c`
- `0x180598bc0`
- `0x1806b2e84`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801e6bdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801e6bdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801e6c72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801e6de5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801e6c72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801e6de5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e68bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e698c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6a0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6afc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6ccc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e68bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e698c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6a0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6afc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6ccc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e6cf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e6cf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801e6b32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801e6b32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1801e6b47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1801e6b47`

## pseudocode

```c
__int64 __fastcall DirectUI::MetadataAPI::GetClassInfoFromObject_Helper(
        IInspectable *pInstance,
        const CClassInfo **ppType,
        bool resolveWinRTPropertyOtherType)
{
  IInspectable *v4; // rbx
  HRESULT ClassInfoByTypeName; // r12d
  Windows::Foundation::IPropertyValue *v6; // r15
  __int64 v7; // r14
  Windows::Foundation::IPropertyValue *v8; // rdi
  Windows::Foundation::IPropertyValue_vtbl *v9; // rax
  HRESULT v10; // eax
  int v11; // ecx
  HRESULT v12; // ebx
  int v13; // ecx
  int v14; // ecx
  KnownTypeIndex v15; // cx
  IInspectable_vtbl *v17; // rax
  IInspectable *v18; // r12
  Windows::UI::Xaml::Data::ICustomPropertyProvider_vtbl **v19; // rbx
  Windows::UI::Xaml::Data::ICustomPropertyProvider *v20; // rax
  Windows::UI::Xaml::Data::ICustomPropertyProvider *v21; // rdi
  Windows::UI::Xaml::Data::ICustomPropertyProvider_vtbl *v22; // rdx
  HRESULT (__fastcall *get_Type)(Windows::UI::Xaml::Data::ICustomPropertyProvider *, Windows::UI::Xaml::Interop::TypeName *); // rbx
  HSTRING__ *Name; // rcx
  Windows::UI::Xaml::Data::ICustomPropertyProvider_vtbl *v25; // rax
  IUnknown *v26; // rcx
  KnownTypeIndex v27; // ax
  const CClassInfo *ClassInfoByIndex; // rax
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  HRESULT ClassInfoFromOtherTypeBox; // eax
  HRESULT v35; // eax
  int v36; // eax
  UINT32 StringLen; // eax
  HRESULT v38; // ecx
  __int64 v39; // rdi
  int v40; // eax
  HSTRING StringRawBuffer; // rcx
  HRESULT v42; // ecx
  const CClassInfo *second; // rdi
  const CClassInfo *Instance; // rax
  std::pair<xstring_ptr,CClassInfo const *> *v45; // rdi
  __int64 v46; // rsi
  DesignerMode v47; // ecx
  HRESULT v48; // eax
  HRESULT v49; // edi
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  int v56; // ecx
  int v57; // ecx
  DirectUI::DynamicMetadataStorage *v58; // rax
  std::pair<xstring_ptr,CClassInfo const *> *Ptr; // rdi
  HRESULT v60; // eax
  xstring_ptr pstrAssemblyName; // [rsp+20h] [rbp-48h] BYREF
  HSTRING__ *hRuntimeClassName; // [rsp+28h] [rbp-40h] BYREF
  Windows::Foundation::IPropertyValue *pValue; // [rsp+30h] [rbp-38h] BYREF
  __int64 v64; // [rsp+38h] [rbp-30h] BYREF
  const CClassInfo *v65[2]; // [rsp+40h] [rbp-28h] BYREF
  TypeNamePtr typeName; // [rsp+50h] [rbp-18h] BYREF
  IInspectable *pOther; // [rsp+B0h] [rbp+48h] BYREF
  const CClassInfo *pType; // [rsp+B8h] [rbp+50h] BYREF
  bool v69; // [rsp+C0h] [rbp+58h]
  xstring_ptr strClassName; // [rsp+C8h] [rbp+60h] BYREF

  v69 = resolveWinRTPropertyOtherType;
  pOther = pInstance;
  strClassName.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
  hRuntimeClassName = 0;
  v4 = pInstance;
  *ppType = 0;
  ClassInfoByTypeName = 0;
  v6 = 0;
  v7 = 0;
  if ( !pInstance )
    goto LABEL_13;
  pValue = 0;
  if ( pInstance->QueryInterface(pInstance, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, (void **)&pValue) >= 0 )
  {
    v8 = pValue;
    if ( pValue )
    {
      v9 = pValue->__vftable;
      LODWORD(pType) = 0;
      v6 = pValue;
      v10 = v9->get_Type(pValue, (Windows::Foundation::PropertyType *)&pType);
      ClassInfoByTypeName = v10;
      if ( v10 < 0 )
      {
        OnFailure_2990_(v10);
        goto $Cleanup_1146;
      }
      v11 = (int)pType;
      if ( (_DWORD)pType == 20 )
      {
        if ( CQuirksMode2::XamlQuirkIsEnabled(0x2008Bu) || !v69 )
          goto LABEL_20;
        v11 = (int)pType;
      }
      v12 = 0;
      *ppType = 0;
      if ( v11 <= 10 )
      {
        if ( v11 == 10 )
        {
          v15 = Char16;
          goto LABEL_10;
        }
        v50 = v11 - 1;
        if ( !v50 )
          goto LABEL_110;
        v51 = v50 - 1;
        if ( !v51 )
        {
          v15 = Int16;
          goto LABEL_10;
        }
        v52 = v51 - 1;
        if ( !v52 )
        {
          v15 = UInt16;
          goto LABEL_10;
        }
        v53 = v52 - 1;
        if ( !v53 || (v54 = v53 - 1) == 0 )
        {
LABEL_110:
          v15 = Int32;
          goto LABEL_10;
        }
        v55 = v54 - 1;
        if ( !v55 || (v56 = v55 - 1) == 0 )
        {
          v15 = Int64;
          goto LABEL_10;
        }
        v57 = v56 - 1;
        if ( !v57 )
        {
          v15 = Float;
          goto LABEL_10;
        }
        if ( v57 == 1 )
        {
          v15 = Double;
          goto LABEL_10;
        }
      }
      else
      {
        v13 = v11 - 11;
        if ( !v13 )
        {
          v15 = Boolean;
          goto LABEL_10;
        }
        v14 = v13 - 1;
        if ( !v14 )
        {
          v15 = String;
LABEL_10:
          *ppType = DirectUI::MetadataAPI::GetClassInfoByIndex(v15);
          ClassInfoByTypeName = 0;
LABEL_11:
          if ( *ppType )
            goto $Cleanup_1146;
          v4 = pOther;
          goto LABEL_20;
        }
        v29 = v14 - 3;
        if ( !v29 )
        {
          v15 = TimeSpan;
          goto LABEL_10;
        }
        v30 = v29 - 1;
        if ( !v30 )
        {
          v15 = Guid;
          goto LABEL_10;
        }
        v31 = v30 - 1;
        if ( !v31 )
        {
          v15 = Point;
          goto LABEL_10;
        }
        v32 = v31 - 1;
        if ( !v32 )
        {
          v15 = Size;
          goto LABEL_10;
        }
        v33 = v32 - 1;
        if ( !v33 )
        {
          v15 = Rect;
          goto LABEL_10;
        }
        if ( v33 == 1 )
        {
          ClassInfoFromOtherTypeBox = DirectUI::MetadataAPI::GetClassInfoFromOtherTypeBox(v8, ppType);
          v12 = ClassInfoFromOtherTypeBox;
          if ( ClassInfoFromOtherTypeBox < 0 )
          {
            OnFailure_2990_(ClassInfoFromOtherTypeBox);
            ClassInfoByTypeName = v12;
            goto LABEL_103;
          }
        }
      }
      ClassInfoByTypeName = v12;
      if ( v12 >= 0 )
        goto LABEL_11;
LABEL_103:
      OnFailure_2990_(v12);
      goto $Cleanup_1146;
    }
  }
LABEL_20:
  v17 = v4->__vftable;
  v64 = 0;
  if ( v17->QueryInterface(v4, &GUID_659a8956_ef29_4f50_8724_7e3207d23076, (void **)&v64) >= 0 )
  {
    if ( v64 )
    {
      v7 = v64;
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v64 + 8) + 64LL))(v64 + 8) )
        goto LABEL_29;
    }
  }
  v18 = pOther;
  v19 = 0;
  v20 = ctl::query_interface<Windows::UI::Xaml::Data::ICustomPropertyProvider,IInspectable>(pOther);
  v21 = v20;
  if ( v20 )
  {
    v22 = v20->__vftable;
    typeName.m_typeName.Name = 0;
    *(_QWORD *)&typeName.m_typeName.Kind = 0;
    get_Type = v22->get_Type;
    WindowsDeleteString(0);
    typeName.m_typeName.Name = 0;
    *(_QWORD *)&typeName.m_typeName.Kind = 0;
    if ( get_Type(v21, &typeName.m_typeName) >= 0 )
    {
      *(TypeNamePtr *)v65 = typeName;
      pType = 0;
      ClassInfoByTypeName = DirectUI::MetadataAPI::GetClassInfoByTypeName(
                              (Windows::UI::Xaml::Interop::TypeName *)v65,
                              &pType);
      if ( ClassInfoByTypeName >= 0 && pType && ((pType->m_flags & 1) != 0 || !v7) )
      {
        Name = typeName.m_typeName.Name;
        *ppType = pType;
        WindowsDeleteString(Name);
        v25 = v21->__vftable;
        v26 = v21;
        typeName.m_typeName.Name = 0;
        *(_QWORD *)&typeName.m_typeName.Kind = 0;
LABEL_45:
        v25->Release(v26);
        goto $Cleanup_1146;
      }
      v18 = pOther;
    }
    v19 = (Windows::UI::Xaml::Data::ICustomPropertyProvider_vtbl **)v21;
    WindowsDeleteString(typeName.m_typeName.Name);
  }
  v35 = v18->GetRuntimeClassName(v18, &hRuntimeClassName);
  ClassInfoByTypeName = v35;
  if ( v35 < 0 )
  {
    OnFailure_2990_(v35);
LABEL_43:
    if ( !v19 )
      goto $Cleanup_1146;
    v25 = *v19;
    v26 = (IUnknown *)v19;
    goto LABEL_45;
  }
  typeName.m_typeName.Name = 0;
  typeName.m_typeName.Kind = TypeKind_Primitive;
  v36 = WindowsDuplicateString(hRuntimeClassName, &typeName.m_typeName.Name);
  ClassInfoByTypeName = v36;
  if ( v36 < 0 )
  {
    OnFailure_2990_(v36);
LABEL_101:
    OnFailure_2990_(ClassInfoByTypeName);
    goto LABEL_43;
  }
  StringLen = WindowsGetStringLen(typeName.m_typeName.Name);
  if ( StringLen > 0x3FFFFFFF )
  {
    OnNewFailure_1208_(v38);
    ClassInfoByTypeName = -2147467259;
    goto LABEL_101;
  }
  v39 = (__int64)typeName.m_typeName.Name | 1;
  typeName.m_typeName.Kind = StringLen & 0x3FFFFFFF | 0x80000000;
  if ( ((__int64)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage & 1) != 0 )
    WindowsDeleteString((HSTRING)(xstring_ptr_constants::c_xencoded_string_ptr_null.RuntimeStringHandleMarker
                                & 0xFFFFFFFFFFFFFFFEuLL));
  strClassName.m_encodedStorage.Storage = (const xstring_ptr_storage *)v39;
  LODWORD(pOther) = 0;
  if ( (v39 & 1) != 0 )
  {
    StringRawBuffer = (HSTRING)(v39 & 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_82;
  }
  v40 = *(_DWORD *)(v39 + 8);
  StringRawBuffer = *(HSTRING *)v39;
  if ( v40 < 0 )
  {
LABEL_82:
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(StringRawBuffer, (UINT32 *)&pOther);
    goto LABEL_57;
  }
  LODWORD(pOther) = v40 & 0x3FFFFFFF;
LABEL_57:
  if ( !StringRawBuffer || !(_DWORD)pOther || !*(_WORD *)StringRawBuffer )
    goto LABEL_75;
  v65[0] = DirectUI::MetadataAPI::TryGetBuiltinClassInfoByFullName(&strClassName);
  second = v65[0];
  if ( !v65[0] )
  {
    EnterCriticalSection(&g_csStatic);
    Instance = (const CClassInfo *)DirectUI::DynamicMetadataStorage::GetInstance();
    pType = Instance;
    v45 = (std::pair<xstring_ptr,CClassInfo const *> *)Instance[6];
    v46 = (__int64)(*(_QWORD *)&Instance[7] - (_QWORD)v45) >> 4;
    if ( v46 > 0 )
    {
      do
      {
        pOther = (IInspectable *)((unsigned __int64)v46 >> 1);
        pstrAssemblyName.m_encodedStorage.Storage = (const xstring_ptr_storage *)&v45[(unsigned __int64)v46 >> 1];
        if ( xstring_ptr_view::Compare(
               (xstring_ptr_view *)pstrAssemblyName.m_encodedStorage.Storage,
               &strClassName,
               xstrCompareCaseSensitive) < 0 )
        {
          v45 = (std::pair<xstring_ptr,CClassInfo const *> *)((char *)&pstrAssemblyName.m_encodedStorage.Storage[1].Handle
                                                            + 4);
          v46 += -1LL - (_QWORD)pOther;
        }
        else
        {
          v46 = (__int64)pOther;
        }
      }
      while ( v46 > 0 );
      Instance = pType;
    }
    if ( v45 != (std::pair<xstring_ptr,CClassInfo const *> *)Instance[7] )
    {
      if ( xstring_ptr_view::Compare(&strClassName, &v45->first, xstrCompareCaseSensitive) >= 0 )
        goto LABEL_70;
      Instance = pType;
    }
    v45 = (std::pair<xstring_ptr,CClassInfo const *> *)Instance[7];
LABEL_70:
    if ( v45 != DirectUI::DynamicMetadataStorage::GetInstance()->m_customTypesByNameCache.m_data.m_vector._Mypair._Myval2._Mylast )
    {
      second = v45->second;
LABEL_72:
      LeaveCriticalSection(&g_csStatic);
      goto LABEL_73;
    }
    LOBYTE(v47) = 1;
    if ( DesignerInterop::GetDesignerMode(v47) )
    {
      pType = (const CClassInfo *)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
      pstrAssemblyName.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
      pOther = (IInspectable *)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
      v60 = xstring_ptr_view::Promote(&strClassName, (xstring_ptr *)&pOther);
      v49 = v60;
      if ( v60 < 0 )
      {
        OnFailure_2990_(v60);
        xstring_ptr::~xstring_ptr((xstring_ptr *)&pOther);
        xstring_ptr::~xstring_ptr(&pstrAssemblyName);
        xstring_ptr::~xstring_ptr((xstring_ptr *)&pType);
        goto LABEL_105;
      }
      if ( TypeNameHelper::ParseAssemblyQualifiedTypeName(
             (const xstring_ptr *)&pOther,
             (xstring_ptr *)&pType,
             &pstrAssemblyName) >= 0 )
      {
        v58 = DirectUI::DynamicMetadataStorage::GetInstance();
        Ptr = containers::detail::vector_tree<containers::detail::map_traits<xstring_ptr,CClassInfo const *,std::less<void>,std::allocator<std::pair<xstring_ptr,CClassInfo const *>>,0>>::find(
                &v58->m_customTypesByNameCache,
                (std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<xstring_ptr,CClassInfo const *> > > > *)&typeName,
                (const xstring_ptr *)&pType)->_Ptr;
        if ( Ptr != DirectUI::DynamicMetadataStorage::GetInstance()->m_customTypesByNameCache.m_data.m_vector._Mypair._Myval2._Mylast )
        {
          second = Ptr->second;
          xstring_ptr::~xstring_ptr((xstring_ptr *)&pOther);
          xstring_ptr::~xstring_ptr(&pstrAssemblyName);
          xstring_ptr::~xstring_ptr((xstring_ptr *)&pType);
          goto LABEL_72;
        }
      }
      xstring_ptr::~xstring_ptr((xstring_ptr *)&pOther);
      xstring_ptr::~xstring_ptr(&pstrAssemblyName);
      xstring_ptr::~xstring_ptr((xstring_ptr *)&pType);
    }
    v48 = DirectUI::MetadataAPI::ImportClassInfoFromMetadataProvider(&strClassName, v65);
    v49 = v48;
    if ( v48 >= 0 )
    {
      second = v65[0];
      goto LABEL_72;
    }
    OnFailure_2990_(v48);
LABEL_105:
    LeaveCriticalSection(&g_csStatic);
    OnFailure_2990_(v49);
    goto LABEL_75;
  }
LABEL_73:
  if ( second )
  {
    if ( (second->m_flags & 1) == 0 )
      goto LABEL_75;
    *ppType = second;
    goto LABEL_43;
  }
  OnNewFailure_1208_(v42);
LABEL_75:
  if ( v19 )
    (*v19)->Release((IUnknown *)v19);
  if ( !v7 )
    goto LABEL_13;
LABEL_29:
  v27 = (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)(v7 + 8) + 56LL))(v7 + 8);
  ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex(v27);
  *ppType = ClassInfoByIndex;
  if ( !ClassInfoByIndex )
LABEL_13:
    *ppType = DirectUI::MetadataAPI::GetClassInfoByIndex(Object);
$Cleanup_1146:
  WindowsDeleteString(hRuntimeClassName);
  xstring_ptr::~xstring_ptr(&strClassName);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v7 + 8) + 16LL))(v7 + 8);
  if ( v6 )
    v6->Release(v6);
  return (unsigned int)ClassInfoByTypeName;
}

```

## disassembly

```asm
0x1801e67c4  mov     [rsp-40h+arg_10], resolveWinRTPropertyOtherType
0x1801e67c9  mov     [rsp-40h+pOther], pInstance
0x1801e67ce  push    rbp
0x1801e67cf  push    rbx
0x1801e67d0  push    rsi
0x1801e67d1  push    rdi
0x1801e67d2  push    r12
0x1801e67d4  push    r13
0x1801e67d6  push    r14
0x1801e67d8  push    r15
0x1801e67da  mov     rbp, rsp
0x1801e67dd  sub     rsp, 68h
0x1801e67e1  mov     rsi, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1801e67e8  xor     eax, eax
0x1801e67ea  mov     qword ptr [rbp+strClassName.m_encodedStorage.___u0], rsi
0x1801e67ee  mov     r13, ppType
0x1801e67f1  mov     [rbp+hRuntimeClassName], rax
0x1801e67f5  mov     rbx, pInstance
0x1801e67f8  mov     [ppType], rax
0x1801e67fb  mov     r12d, eax
0x1801e67fe  mov     r15d, eax
0x1801e6801  mov     r14d, eax
0x1801e6804  test    pInstance, pInstance
0x1801e6807  jz      loc_1801E68AB
0x1801e680d  mov     [rbp+pValue], rax
0x1801e6811  lea     r8, [rbp+pValue]
0x1801e6815  mov     rax, [pInstance]
0x1801e6818  lea     ppType, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1801e681f  mov     rax, [rax]
0x1801e6822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6827  test    eax, eax
0x1801e6829  js      loc_1801E691B
0x1801e682f  mov     rdi, [rbp+pValue]
0x1801e6833  test    rdi, rdi
0x1801e6836  jz      loc_1801E691B
0x1801e683c  mov     rax, [rdi]
0x1801e683f  lea     ppType, [rbp+pType]
0x1801e6843  mov     pInstance, rdi
0x1801e6846  mov     dword ptr [rbp+pType], r12d
0x1801e684a  mov     r15, rdi
0x1801e684d  mov     rax, [rax+30h]
0x1801e6851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6856  mov     r12d, eax
0x1801e6859  test    eax, eax
0x1801e685b  js      loc_1801E6DA1
0x1801e6861  mov     ecx, dword ptr [rbp+pType]
0x1801e6864  cmp     ecx, 14h
0x1801e6867  jz      loc_1801E6909
0x1801e686d  xor     ebx, ebx
0x1801e686f  mov     [r13+0], rbx
0x1801e6873  cmp     ecx, 0Ah
0x1801e6876  jle     loc_1801E6D3A
0x1801e687c  sub     ecx, 0Bh
0x1801e687f  jz      loc_1801E6D01
0x1801e6885  sub     ecx, 1
0x1801e6888  jnz     loc_1801E6A5E
0x1801e688e  mov     ecx, 10Dh; eTypeIndex
0x1801e6893  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x1801e6898  mov     [r13+0], rax
0x1801e689c  xor     r12d, r12d
0x1801e689f  cmp     [r13+0], r14
0x1801e68a3  jnz     short $Cleanup_1146
0x1801e68a5  mov     rbx, [rbp+pOther]
0x1801e68a9  jmp     short loc_1801E691B
0x1801e68ab  mov     ecx, 28h ; '('; eTypeIndex
0x1801e68b0  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x1801e68b5  mov     [r13+0], rax
0x1801e68b9  mov     pInstance, [rbp+hRuntimeClassName]; string
0x1801e68bd  call    cs:__imp_WindowsDeleteString
0x1801e68c3  lea     pInstance, [rbp+strClassName]; this
0x1801e68c7  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801e68cc  test    r14, r14
0x1801e68cf  jz      short loc_1801E68E1
0x1801e68d1  lea     pInstance, [r14+8]
0x1801e68d5  mov     rax, [pInstance]
0x1801e68d8  mov     rax, [rax+10h]
0x1801e68dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e68e1  test    r15, r15
0x1801e68e4  jz      short loc_1801E68F5
0x1801e68e6  mov     rax, [r15]
0x1801e68e9  mov     pInstance, r15
0x1801e68ec  mov     rax, [rax+10h]
0x1801e68f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e68f5  mov     eax, r12d
0x1801e68f8  add     rsp, 68h
0x1801e68fc  pop     r15
0x1801e68fe  pop     r14
0x1801e6900  pop     r13
0x1801e6902  pop     r12
0x1801e6904  pop     rdi
0x1801e6905  pop     rsi
0x1801e6906  pop     rbx
0x1801e6907  pop     rbp
0x1801e6908  retn
0x1801e6909  mov     ecx, 2008Bh; quirk
0x1801e690e  call    ?XamlQuirkIsEnabled@CQuirksMode2@@SA_NK@Z; CQuirksMode2::XamlQuirkIsEnabled(ulong)
0x1801e6913  cmp     al, 1
0x1801e6915  jnz     loc_1801E6AB5
0x1801e691b  mov     rax, [rbx]
0x1801e691e  lea     r8, [rbp+var_30]
0x1801e6922  lea     ppType, _GUID_659a8956_ef29_4f50_8724_7e3207d23076
0x1801e6929  mov     [rbp+var_30], r14
0x1801e692d  mov     pInstance, rbx
0x1801e6930  mov     rax, [rax]
0x1801e6933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6938  test    eax, eax
0x1801e693a  js      short loc_1801E6961
0x1801e693c  mov     pInstance, [rbp+var_30]
0x1801e6940  test    pInstance, pInstance
0x1801e6943  jz      short loc_1801E6961
0x1801e6945  mov     r14, pInstance
0x1801e6948  add     pInstance, 8
0x1801e694c  mov     rax, [pInstance]
0x1801e694f  mov     rax, [rax+40h]
0x1801e6953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6958  test    rax, rax
0x1801e695b  jz      loc_1801E6A34
0x1801e6961  mov     r12, [rbp+pOther]
0x1801e6965  xor     ebx, ebx
0x1801e6967  mov     pInstance, r12; pOther
0x1801e696a  call    ??$query_interface@UICustomPropertyProvider@Data@Xaml@UI@Windows@@UIInspectable@@@ctl@@YAPEAUICustomPropertyProvider@Data@Xaml@UI@Windows@@PEAUIInspectable@@@Z; ctl::query_interface<Windows::UI::Xaml::Data::ICustomPropertyProvider,IInspectable>(IInspectable *)
0x1801e696f  mov     rdi, rax
0x1801e6972  test    rax, rax
0x1801e6975  jz      loc_1801E6B02
0x1801e697b  mov     ppType, [rax]
0x1801e697e  xor     ecx, ecx; string
0x1801e6980  mov     [rbp+typeName.m_typeName.Name], pInstance
0x1801e6984  mov     qword ptr [rbp+typeName.m_typeName.Kind], pInstance
0x1801e6988  mov     rbx, [ppType+48h]
0x1801e698c  call    cs:__imp_WindowsDeleteString
0x1801e6992  mov     [rbp+typeName.m_typeName.Name], 0
0x1801e699a  lea     ppType, [rbp+typeName]
0x1801e699e  mov     qword ptr [rbp+typeName.m_typeName.Kind], 0
0x1801e69a6  mov     pInstance, rdi
0x1801e69a9  movaps  xmm0, xmmword ptr [rbp+typeName.m_typeName.Name]
0x1801e69ad  mov     rax, rbx
0x1801e69b0  movdqa  xmmword ptr [rbp+typeName.m_typeName.Name], xmm0
0x1801e69b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e69ba  test    eax, eax
0x1801e69bc  js      loc_1801E6AF5
0x1801e69c2  movaps  xmm0, xmmword ptr [rbp+typeName.m_typeName.Name]
0x1801e69c6  lea     ppType, [rbp+pType]
0x1801e69ca  lea     pInstance, [rbp+var_28]
0x1801e69ce  movdqa  xmmword ptr [rbp+var_28], xmm0
0x1801e69d3  mov     [rbp+pType], 0
0x1801e69db  call    ?GetClassInfoByTypeName@MetadataAPI@DirectUI@@SAJUTypeName@Interop@Xaml@UI@Windows@@PEAPEBVCClassInfo@@@Z; DirectUI::MetadataAPI::GetClassInfoByTypeName(Windows::UI::Xaml::Interop::TypeName,CClassInfo const * *)
0x1801e69e0  mov     r12d, eax
0x1801e69e3  test    eax, eax
0x1801e69e5  js      loc_1801E6AF1
0x1801e69eb  mov     rax, [rbp+pType]
0x1801e69ef  test    rax, rax
0x1801e69f2  jz      loc_1801E6AF1
0x1801e69f8  test    byte ptr [rax+4], 1
0x1801e69fc  jz      loc_1801E6AE8
0x1801e6a02  mov     pInstance, [rbp+typeName.m_typeName.Name]; string
0x1801e6a06  mov     [r13+0], rax
0x1801e6a0a  call    cs:__imp_WindowsDeleteString
0x1801e6a10  mov     rax, [rdi]
0x1801e6a13  mov     pInstance, rdi
0x1801e6a16  mov     [rbp+typeName.m_typeName.Name], 0
0x1801e6a1e  mov     qword ptr [rbp+typeName.m_typeName.Kind], 0
0x1801e6a26  movaps  xmm0, xmmword ptr [rbp+typeName.m_typeName.Name]
0x1801e6a2a  movdqa  xmmword ptr [rbp+typeName.m_typeName.Name], xmm0
0x1801e6a2f  jmp     loc_1801E6ADA
0x1801e6a34  lea     pInstance, [r14+8]
0x1801e6a38  mov     rax, [pInstance]
0x1801e6a3b  mov     rax, [rax+38h]
0x1801e6a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6a44  movzx   ecx, ax; eTypeIndex
0x1801e6a47  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x1801e6a4c  mov     [r13+0], rax
0x1801e6a50  test    rax, rax
0x1801e6a53  jnz     $Cleanup_1146
0x1801e6a59  jmp     loc_1801E68AB
0x1801e6a5e  sub     ecx, 3
0x1801e6a61  jz      loc_1801E6E9D
0x1801e6a67  sub     ecx, 1
0x1801e6a6a  jz      loc_1801E6E93
0x1801e6a70  sub     ecx, 1
0x1801e6a73  jz      loc_1801E6E89
0x1801e6a79  sub     ecx, 1
0x1801e6a7c  jz      loc_1801E6E7F
0x1801e6a82  sub     ecx, 1
0x1801e6a85  jz      loc_1801E6D97
0x1801e6a8b  cmp     ecx, 1
0x1801e6a8e  jnz     short loc_1801E6AA5
0x1801e6a90  mov     ppType, r13; ppType
0x1801e6a93  mov     pInstance, rdi; pValue
0x1801e6a96  call    ?GetClassInfoFromOtherTypeBox@MetadataAPI@DirectUI@@CAJPEAUIPropertyValue@Foundation@Windows@@PEAPEBVCClassInfo@@@Z; DirectUI::MetadataAPI::GetClassInfoFromOtherTypeBox(Windows::Foundation::IPropertyValue *,CClassInfo const * *)
0x1801e6a9b  mov     ebx, eax
0x1801e6a9d  test    eax, eax
0x1801e6a9f  js      loc_1801E6DC1
0x1801e6aa5  mov     r12d, ebx
0x1801e6aa8  test    ebx, ebx
0x1801e6aaa  jns     loc_1801E689F
0x1801e6ab0  jmp     loc_1801E6DCB
0x1801e6ab5  cmp     [rbp+arg_10], r14b
0x1801e6ab9  jz      loc_1801E691B
0x1801e6abf  mov     ecx, dword ptr [rbp+pType]
0x1801e6ac2  jmp     loc_1801E686D
0x1801e6ac7  mov     [r13+0], rdi
0x1801e6acb  test    rbx, rbx
0x1801e6ace  jz      $Cleanup_1146
0x1801e6ad4  mov     rax, [rbx]
0x1801e6ad7  mov     pInstance, rbx
0x1801e6ada  mov     rax, [rax+10h]
0x1801e6ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6ae3  jmp     $Cleanup_1146
0x1801e6ae8  test    r14, r14
0x1801e6aeb  jz      loc_1801E6A02
0x1801e6af1  mov     r12, [rbp+pOther]
0x1801e6af5  mov     pInstance, [rbp+typeName.m_typeName.Name]; string
0x1801e6af9  mov     rbx, rdi
0x1801e6afc  call    cs:__imp_WindowsDeleteString
0x1801e6b02  mov     rax, [r12]
0x1801e6b06  lea     ppType, [rbp+hRuntimeClassName]
0x1801e6b0a  mov     pInstance, r12
0x1801e6b0d  mov     rax, [rax+20h]
0x1801e6b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6b16  mov     r12d, eax
0x1801e6b19  test    eax, eax
0x1801e6b1b  js      loc_1801E6CDC
0x1801e6b21  mov     pInstance, [rbp+hRuntimeClassName]; string
0x1801e6b25  lea     ppType, [rbp+typeName]; newString
0x1801e6b29  xor     eax, eax
0x1801e6b2b  mov     [rbp+typeName.m_typeName.Name], rax
0x1801e6b2f  mov     [rbp+typeName.m_typeName.Kind], eax
0x1801e6b32  call    cs:__imp_WindowsDuplicateString
0x1801e6b38  mov     r12d, eax
0x1801e6b3b  test    eax, eax
0x1801e6b3d  js      loc_1801E6DAD
0x1801e6b43  mov     pInstance, [rbp+typeName.m_typeName.Name]; string
0x1801e6b47  call    cs:__imp_WindowsGetStringLen
0x1801e6b4d  mov     edx, 3FFFFFFFh
0x1801e6b52  cmp     eax, edx
0x1801e6b54  ja      loc_1801E6F37
0x1801e6b5a  mov     rdi, [rbp+typeName.m_typeName.Name]
0x1801e6b5e  and     eax, edx
0x1801e6b60  bts     eax, 1Fh
0x1801e6b64  or      rdi, 1
0x1801e6b68  mov     [rbp+typeName.m_typeName.Kind], eax
0x1801e6b6b  test    sil, 1
0x1801e6b6f  jnz     loc_1801E6CC5
0x1801e6b75  mov     qword ptr [rbp+strClassName.m_encodedStorage.___u0], rdi
0x1801e6b79  mov     dword ptr [rbp+pOther], 0
0x1801e6b80  test    dil, 1
0x1801e6b84  jnz     loc_1801E6CE8
0x1801e6b8a  mov     eax, [rdi+8]
0x1801e6b8d  mov     pInstance, [rdi]
0x1801e6b90  test    eax, eax
0x1801e6b92  js      loc_1801E6CEF
0x1801e6b98  and     eax, edx
0x1801e6b9a  mov     dword ptr [rbp+pOther], eax
0x1801e6b9d  test    pInstance, pInstance
0x1801e6ba0  jz      loc_1801E6C8B
0x1801e6ba6  cmp     dword ptr [rbp+pOther], 0
0x1801e6baa  jz      loc_1801E6C8B
0x1801e6bb0  xor     eax, eax
0x1801e6bb2  cmp     ax, [pInstance]
0x1801e6bb5  jz      loc_1801E6C8B
0x1801e6bbb  lea     pInstance, [rbp+strClassName]; strTypeFullName
0x1801e6bbf  call    ?TryGetBuiltinClassInfoByFullName@MetadataAPI@DirectUI@@CAPEBVCClassInfo@@AEBVxstring_ptr_view@@@Z; DirectUI::MetadataAPI::TryGetBuiltinClassInfoByFullName(xstring_ptr_view const &)
0x1801e6bc4  mov     [rbp+var_28], rax
0x1801e6bc8  mov     rdi, rax
0x1801e6bcb  test    rax, rax
0x1801e6bce  jnz     loc_1801E6C78
0x1801e6bd4  lea     pInstance, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801e6bdb  call    cs:__imp_EnterCriticalSection
0x1801e6be1  call    ?GetInstance@DynamicMetadataStorage@DirectUI@@CAPEAV12@XZ; DirectUI::DynamicMetadataStorage::GetInstance(void)
0x1801e6be6  mov     [rbp+pType], rax
0x1801e6bea  mov     rdi, [rax+30h]
0x1801e6bee  mov     rsi, [rax+38h]
0x1801e6bf2  sub     rsi, rdi
0x1801e6bf5  sar     rsi, 4
0x1801e6bf9  test    rsi, rsi
0x1801e6bfc  jle     short loc_1801E6C37
0x1801e6bfe  mov     rax, rsi
0x1801e6c01  lea     ppType, [rbp+strClassName]; other
0x1801e6c05  shr     rax, 1
0x1801e6c08  xor     r8d, r8d; eCompareBehavior
0x1801e6c0b  mov     [rbp+pOther], rax
0x1801e6c0f  shl     rax, 4
0x1801e6c13  add     rax, rdi
0x1801e6c16  mov     pInstance, rax; this
0x1801e6c19  mov     qword ptr [rbp+pstrAssemblyName.m_encodedStorage.___u0], rax
0x1801e6c1d  call    ?Compare@xstring_ptr_view@@QEBAHAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::Compare(xstring_ptr_view const &,xstrCompareBehavior)
0x1801e6c22  test    eax, eax
0x1801e6c24  js      loc_1801E6CAD
0x1801e6c2a  mov     rsi, [rbp+pOther]
0x1801e6c2e  test    rsi, rsi
0x1801e6c31  jg      short loc_1801E6BFE
0x1801e6c33  mov     rax, [rbp+pType]
0x1801e6c37  cmp     rdi, [rax+38h]
0x1801e6c3b  jz      short loc_1801E6C54
0x1801e6c3d  xor     r8d, r8d; eCompareBehavior
0x1801e6c40  lea     pInstance, [rbp+strClassName]; this
0x1801e6c44  mov     ppType, rdi; other
0x1801e6c47  call    ?Compare@xstring_ptr_view@@QEBAHAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::Compare(xstring_ptr_view const &,xstrCompareBehavior)
0x1801e6c4c  test    eax, eax
0x1801e6c4e  jns     short loc_1801E6C58
  ... truncated ...
```
