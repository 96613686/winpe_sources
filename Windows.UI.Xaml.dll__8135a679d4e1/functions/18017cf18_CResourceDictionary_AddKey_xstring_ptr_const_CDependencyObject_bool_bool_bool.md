# CResourceDictionary::AddKey(xstring_ptr const &,CDependencyObject *,bool,bool,bool)

- ea: `0x18017cf18`
- end: `0x18017d846`
- name: `?AddKey@CResourceDictionary@@AEAAJAEBVxstring_ptr@@PEAVCDependencyObject@@_N22@Z`
- size: `2350`
- prototype: `HRESULT __fastcall(CResourceDictionary *this, const xstring_ptr *strKey, CDependencyObject *pValue, bool fKeyIsType, bool keyIsOverride, bool undeferringKey)`
- caller_count: `1`
- callee_count: `36`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18017cb50`

## callees

- `0x180004bc0`
- `0x1800207b0`
- `0x1800217b8`
- `0x180021840`
- `0x180021970`
- `0x180040ce8`
- `0x180095258`
- `0x1800aabf0`
- `0x1800ab600`
- `0x1800adbb0`
- `0x1800af8e0`
- `0x1800fe130`
- `0x180100ca0`
- `0x18017c170`
- `0x18017cf18`
- `0x18017d850`
- `0x18017d880`
- `0x18017d92c`
- `0x18017d958`
- `0x18017da40`
- `0x1801800b8`
- `0x18021e4e0`
- `0x1802f39e8`
- `0x18037aaa4`
- `0x1803c892c`
- `0x180494d9c`
- `0x180643a3c`
- `0x180675e3c`
- `0x180687744`
- `0x1806877a8`
- `0x180687890`
- `0x180688308`
- `0x18076e110`
- `0x180798710`
- `0x180884388`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18017d08c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18017d08c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18017d042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18017d042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017d4df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017d5e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017d4df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017d5e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18017d3d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18017d3d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CResourceDictionary::AddKey(
        CResourceDictionary *this,
        xstring_ptr *strKey,
        _GUID *pValue,
        bool fKeyIsType,
        bool keyIsOverride,
        bool undeferringKey)
{
  unsigned int EventGuid; // edi
  xstring_ptr *v8; // r14
  char v10; // r13
  unsigned __int64 RuntimeStringHandleMarker; // rax
  _MCGEN_TRACE_CONTEXT *StringRawBuffer; // rcx
  KnownTypeIndex v13; // ax
  bool v14; // al
  _GUID *v15; // rax
  unsigned __int64 v16; // rax
  int v17; // edx
  wchar_t *v18; // rax
  UINT32 v19; // edx
  int v20; // eax
  unsigned __int64 v21; // r14
  std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *> > > > *Myfirst; // rdx
  std::_List_node<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *>,void *> *Ptr; // rbx
  std::list<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *>> *p_List; // rax
  std::_List_node<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *>,void *> *Myhead; // rdi
  std::_List_node<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *>,void *> *v26; // r13
  unsigned int Count; // edi
  std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *> > > > *v28; // rcx
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // r13
  unsigned __int64 v31; // rdx
  float v32; // xmm0_4
  signed __int64 Maxidx; // rcx
  float v34; // xmm1_4
  std::_List_node<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *>,void *> *Prev; // rdx
  unsigned __int64 v36; // rax
  std::_List_node<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *>,void *> *v37; // r8
  char v38; // di
  std::vector<std::pair<xstring_ptr,CResourceDictionary::KeyInfo>> *p_m_keyByIndex; // rsi
  bool v40; // r14
  CResourceDictionary::KeyInfo v41; // di
  std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *Myend; // r8
  std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *Mylast; // rcx
  const xstring_ptr_storage *Storage; // r13
  signed __int64 v46; // rcx
  __int64 v47; // r13
  unsigned __int64 v48; // r14
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // rcx
  unsigned __int64 size_of; // rax
  std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *v52; // rax
  std::allocator<std::pair<xstring_ptr,CResourceDictionary::KeyInfo> > *v53; // r9
  HSTRING v54; // rdx
  std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *v55; // rdx
  std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *v56; // rcx
  std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *v57; // rdi
  const CClassInfo *ClassInfoByIndex; // rax
  unsigned __int64 v59; // rax
  unsigned __int64 v60; // rax
  std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *> > > > *v61; // rcx
  HSTRING v62; // r14
  HRESULT v63; // ebx
  DesignerMode v64; // ecx
  CUIElement *v65; // rax
  CCoreServices *m_coreServices; // rcx
  HRESULT updated; // eax
  unsigned __int64 v68; // rax
  const wchar_t *Context; // r14
  unsigned int _Arg5; // esi
  int v71; // ebx
  const wchar_t *Buffer; // rax
  std::allocator<std::pair<xstring_ptr,CResourceDictionary::KeyInfo> > *v73; // r9
  std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *const v74; // r11
  BOOL strParameter3; // [rsp+20h] [rbp-99h]
  BOOL Descriptor; // [rsp+28h] [rbp-91h]
  unsigned int pcStowedExceptions[2]; // [rsp+58h] [rbp-61h] BYREF
  char v79; // [rsp+60h] [rbp-59h]
  HSTRING string; // [rsp+68h] [rbp-51h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+70h] [rbp-49h] BYREF
  xstring_ptr *other; // [rsp+78h] [rbp-41h]
  CValue column; // [rsp+80h] [rbp-39h] BYREF
  CValue line; // [rsp+90h] [rbp-29h] BYREF
  CValue uri; // [rsp+A0h] [rbp-19h] BYREF
  CValue hash; // [rsp+B0h] [rbp-9h] BYREF

  EventGuid = fKeyIsType;
  v8 = strKey;
  other = strKey;
  v10 = 0;
  pcStowedExceptions[0] = 0;
  RuntimeStringHandleMarker = strKey->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (strKey->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    StringRawBuffer = (_MCGEN_TRACE_CONTEXT *)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    StringRawBuffer = *(_MCGEN_TRACE_CONTEXT **)RuntimeStringHandleMarker;
    if ( *(int *)(RuntimeStringHandleMarker + 8) >= 0 )
      goto LABEL_3;
  }
  StringRawBuffer = (_MCGEN_TRACE_CONTEXT *)WindowsGetStringRawBuffer((HSTRING)StringRawBuffer, 0);
LABEL_3:
  if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x40000) != 0 )
    McTemplateMofU0xxzt(
      StringRawBuffer,
      (const _EVENT_DESCRIPTOR *)strKey,
      pValue,
      (const unsigned __int64)this,
      (const unsigned __int64)pValue,
      (const wchar_t *)StringRawBuffer,
      EventGuid);
  if ( (Microsoft_Windows_XAML_DiagnosticsEnableBits[0] & 2) != 0 )
  {
    line.m_value = 0;
    line.m_flags = 0;
    column.m_value = 0;
    column.m_flags = 0;
    uri = 0;
    hash = 0;
    CDependencyObject::GetValueByIndex((CDependencyObject *)pValue, DependencyObject_Line, &line);
    CDependencyObject::GetValueByIndex((CDependencyObject *)pValue, DependencyObject_Column, &column);
    CDependencyObject::GetValueByIndex((CDependencyObject *)pValue, DependencyObject_ParseUri, &uri);
    CDependencyObject::GetValueByIndex((CDependencyObject *)pValue, DependencyObject_XbfHash, &hash);
    if ( (Microsoft_Windows_XAML_DiagnosticsEnableBits[0] & 2) != 0 )
    {
      CValue::As<14>(&hash, (xstring_ptr *)&pppStowedExceptions);
      pcStowedExceptions[0] = 1;
      Context = xstring_ptr_view::GetBuffer((xstring_ptr_view *)&pppStowedExceptions);
      if ( (*(_BYTE *)&column.m_flags.m_state.0 & 0x3F) == 4 )
        _Arg5 = column.m_value.m_any[0];
      else
        _Arg5 = 0;
      v71 = *(_BYTE *)&line.m_flags.m_state.0 & 0x3F;
      EventGuid = 0;
      if ( v71 == 4 )
        EventGuid = line.m_value.m_any[0];
      CValue::As<14>(&uri, (xstring_ptr *)&string);
      v10 = 3;
      Buffer = xstring_ptr_view::GetBuffer((xstring_ptr_view *)&string);
      if ( v71 != 4 )
        EventGuid = 0;
      McTemplateMofU0xxzqqz(
        0,
        &ResourceDictionaryAddWithSourceInfo,
        &ResourceDictionaryAddWithSourceId,
        (const unsigned __int64)this,
        (const unsigned __int64)pValue,
        Buffer,
        EventGuid,
        _Arg5,
        Context);
      LOBYTE(EventGuid) = fKeyIsType;
      v8 = other;
    }
    if ( (v10 & 2) != 0 )
    {
      v10 &= ~2u;
      xstring_ptr::~xstring_ptr((xstring_ptr *)&string);
    }
    if ( (v10 & 1) != 0 )
      xstring_ptr::~xstring_ptr((xstring_ptr *)&pppStowedExceptions);
    CValue::ReleaseAndReset(&hash);
    CValue::ReleaseAndReset(&uri);
    CValue::ReleaseAndReset(&column);
    CValue::ReleaseAndReset(&line);
  }
  if ( pValue
    && ((v13 = (*(unsigned __int16 (__fastcall **)(_GUID *))(*(_QWORD *)&pValue->Data1 + 600LL))(pValue),
         v13 == ResourceDictionary)
     || ((unsigned __int16)v13 >= (XYFocusNavigationStrategy|IVectorOfUri)
       ? (ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex(v13),
          v14 = DirectUI::MetadataAPI::CompareCustomTypesHelper(ClassInfoByIndex, ResourceDictionary))
       : (v14 = (c_aTypeCheckData[(unsigned __int16)v13].m_handle & 0xFFFFF) == 327943),
         v14)) )
  {
    v15 = pValue;
  }
  else
  {
    v15 = 0;
  }
  if ( (*((_BYTE *)this + 304) & 4) == 0 )
  {
    if ( !v15 )
      goto LABEL_14;
    goto LABEL_75;
  }
  if ( v15 )
  {
    v15[19].Data1 |= 0x10u;
LABEL_75:
    if ( *((char *)this + 304) < 0 )
      v15[19].Data1 |= 0x80u;
LABEL_14:
    v16 = v8->m_encodedStorage.RuntimeStringHandleMarker;
    if ( (v8->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
    {
      v20 = WindowsDuplicateString((HSTRING)(v16 & 0xFFFFFFFFFFFFFFFEuLL), &string);
      if ( v20 < 0 )
      {
LABEL_20:
        OnFailure_2990_(v20);
        pppStowedExceptions = 0;
        pcStowedExceptions[0] = 0;
        TraceForFailFast(-2147418113);
        OnNewFailureEncountered(-2147418113, 0, 0);
        GetStowedExceptionsForFailFast(&pppStowedExceptions, pcStowedExceptions);
        RoFailFastWithErrorContextInternal2(-2147418113, pcStowedExceptions[0], pppStowedExceptions);
        v16 = (unsigned __int64)string;
        goto LABEL_21;
      }
    }
    else
    {
      if ( !v16 || (v17 = *(_DWORD *)(v16 + 8), (v17 & 0x40000000) == 0) )
      {
LABEL_21:
        *(_QWORD *)pcStowedExceptions = v16;
        v79 = EventGuid;
        v21 = xstring_ptr_view::GetHash((xstring_ptr_view *)pcStowedExceptions);
        pppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)v21;
        Myfirst = this->m_resourceMap._Vec._Mypair._Myval2._Myfirst;
        Ptr = Myfirst[2 * (this->m_resourceMap._Mask & v21) + 1]._Ptr;
        p_List = &this->m_resourceMap._List;
        Myhead = this->m_resourceMap._List._Mypair._Myval2._Myhead;
        if ( Ptr != Myhead )
        {
          v26 = Myfirst[2 * (this->m_resourceMap._Mask & v21)]._Ptr;
          while ( 1 )
          {
            Count = xstring_ptr_view::GetCount(&Ptr->_Myval.first.first);
            if ( xstring_ptr_view::GetCount((xstring_ptr_view *)pcStowedExceptions) == Count
              && !xstring_ptr_view::Compare(
                    (xstring_ptr_view *)pcStowedExceptions,
                    &Ptr->_Myval.first.first,
                    xstrCompareCaseSensitive)
              && v79 == Ptr->_Myval.first.second )
            {
              break;
            }
            if ( Ptr == v26 )
            {
              Myhead = Ptr;
              p_List = &this->m_resourceMap._List;
              goto LABEL_27;
            }
            Ptr = Ptr->_Prev;
          }
          v38 = 0;
          v30 = *(_QWORD *)pcStowedExceptions;
LABEL_37:
          if ( (v30 & 1) != 0 )
            WindowsDeleteString((HSTRING)(v30 & 0xFFFFFFFFFFFFFFFEuLL));
          if ( !v38 )
          {
            OnFailure_918_((HRESULT)v28);
            return 2148468994LL;
          }
          p_m_keyByIndex = &this->m_keyByIndex;
          v40 = fKeyIsType;
          v41 = (CResourceDictionary::KeyInfo)(fKeyIsType | (2 * keyIsOverride) | fKeyIsType & 0xFC);
          xstring_ptr::xstring_ptr((xstring_ptr *)&column, other);
          *(CResourceDictionary::KeyInfo *)&column.m_flags.m_state.0 = v41;
          Myend = this->m_keyByIndex._Mypair._Myval2._Myend;
          Mylast = this->m_keyByIndex._Mypair._Myval2._Mylast;
          pppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)Mylast;
          if ( Mylast == Myend )
          {
            v46 = (char *)Mylast - (char *)p_m_keyByIndex->_Mypair._Myval2._Myfirst;
            v47 = v46 / 12;
            v48 = 0x1555555555555555LL;
            if ( v46 / 12 == 0x1555555555555555LL )
              std::_Xlength_error((const char *)v46);
            *(_QWORD *)pcStowedExceptions = v47 + 1;
            v49 = Myend - p_m_keyByIndex->_Mypair._Myval2._Myfirst;
            v50 = v49 >> 1;
            if ( v49 <= 0x1555555555555555LL - (v49 >> 1) )
            {
              v48 = v50 + v49;
              if ( v50 + v49 < v47 + 1 )
                v48 = v47 + 1;
            }
            size_of = std::_Get_size_of_n<12>(v48);
            v52 = (std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
            other = &v52->first;
            v54 = (HSTRING)(3 * v47);
            string = v54;
            Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
            *(unsigned __int64 *)((char *)&v52->first.m_encodedStorage.RuntimeStringHandleMarker + 4 * (_QWORD)v54) = (unsigned __int64)column.m_value;
            *(&v52->second + 4 * (_QWORD)v54) = v41;
            v55 = this->m_keyByIndex._Mypair._Myval2._Mylast;
            v56 = p_m_keyByIndex->_Mypair._Myval2._Myfirst;
            if ( pppStowedExceptions == (_STOWED_EXCEPTION_INFORMATION_V2 **)v55 )
            {
              std::_Uninitialized_move<std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *,std::allocator<std::pair<xstring_ptr,CResourceDictionary::KeyInfo>>>(
                v56,
                v55,
                v52,
                v53);
              v57 = (std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *)other;
            }
            else
            {
              std::_Uninitialized_move<std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *,std::allocator<std::pair<xstring_ptr,CResourceDictionary::KeyInfo>>>(
                v56,
                (std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *const)pppStowedExceptions,
                v52,
                v53);
              v57 = (std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *)other;
              std::_Uninitialized_move<std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *,std::allocator<std::pair<xstring_ptr,CResourceDictionary::KeyInfo>>>(
                v74,
                this->m_keyByIndex._Mypair._Myval2._Mylast,
                (std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *)((char *)other + 4 * ((_QWORD)string + 3)),
                v73);
            }
            std::vector<std::pair<xstring_ptr,CResourceDictionary::KeyInfo>>::_Change_array(
              &this->m_keyByIndex,
              v57,
              *(const unsigned __int64 *)pcStowedExceptions,
              v48);
            v40 = fKeyIsType;
          }
          else
          {
            Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
            Mylast->first.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)column.m_value;
            Mylast->second = v41;
            ++this->m_keyByIndex._Mypair._Myval2._Mylast;
          }
          if ( ((unsigned __int8)Storage & 1) != 0 )
            WindowsDeleteString((HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL));
          Ptr->_Myval.second = (CDependencyObject *)pValue;
          if ( undeferringKey )
            ++this->m_undeferredKeyCount;
          if ( v40 && pValue && !undeferringKey )
          {
            if ( CDependencyObject::OfTypeByIndex<270>((CDependencyObject *)pValue) )
            {
              ++this->m_nImplicitStylesCount;
              if ( (this->m_bitFields.m_bitFieldsAsDWORD & 0x4000) == 0 )
              {
                v65 = do_pointer_cast<CUIElement>(this->m_pResourceOwner);
                if ( v65 )
                {
                  LOBYTE(Descriptor) = 0;
                  LOBYTE(strParameter3) = 1;
                  updated = v65->UpdateImplicitStyle(v65, 0, (CStyle *)pValue, 0, strParameter3, Descriptor);
                  v63 = updated;
                  if ( updated < 0 )
                  {
LABEL_87:
                    OnFailure_2990_(updated);
                    goto LABEL_69;
                  }
                }
                else if ( do_pointer_cast<CApplication>(this->m_pResourceOwner) )
                {
                  m_coreServices = this->m_sharedState.m_ptr->m_value.m_coreServices;
                  if ( m_coreServices )
                  {
                    updated = CCoreServices::UpdateImplicitStylesOnRoots(m_coreServices, 0, (CStyle *)pValue, 0);
                    v63 = updated;
                    if ( updated < 0 )
                      goto LABEL_87;
                  }
                }
              }
            }
            else
            {
              LOBYTE(v64) = 1;
              if ( DesignerInterop::GetDesignerMode(v64) )
                ++this->m_nImplicitStylesCount;
            }
          }
          return 0;
        }
LABEL_27:
        if ( this->m_resourceMap._List._Mypair._Myval2._Mysize == 0x666666666666666LL )
          std::_Xlength_error((const char *)0x666666666666666LL);
        uri.m_value = (CValueDetails::Value)p_List;
        uri.m_flags = 0;
        Ptr = (std::_List_node<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *>,void *> *)std::_Allocate<16,std::_Default_allocate_traits>(0x28u);
        uri.m_flags = (CValueDetails::Flags)Ptr;
        v29 = *(_QWORD *)pcStowedExceptions;
        v30 = xstring_ptr_constants::c_xencoded_string_ptr_null.RuntimeStringHandleMarker;
        *(xencoded_string_ptr *)pcStowedExceptions = xstring_ptr_constants::c_xencoded_string_ptr_null;
        Ptr->_Myval.first.first.m_encodedStorage.RuntimeStringHandleMarker = v29;
        Ptr->_Myval.first.second = v79;
        Ptr->_Myval.second = 0;
        v31 = this->m_resourceMap._List._Mypair._Myval2._Mysize + 1;
        if ( (v31 & 0x8000000000000000uLL) != 0LL )
          v32 = (float)(int)(v31 & 1 | (v31 >> 1)) + (float)(int)(v31 & 1 | (v31 >> 1));
        else
          v32 = (float)(int)v31;
        Maxidx = this->m_resourceMap._Maxidx;
        if ( Maxidx < 0 )
        {
          v68 = this->m_resourceMap._Maxidx & 1 | ((unsigned __int64)Maxidx >> 1);
          v34 = (float)(int)v68 + (float)(int)v68;
        }
        else
        {
          v34 = (float)(int)Maxidx;
        }
        if ( (float)(v32 / v34) > this->m_resourceMap._Traitsobj._Mypair._Myval2._Myval2 )
        {
          v59 = std::_Hash<std::_Umap_traits<XamlPropertyToken,unsigned int,std::_Uhash_compare<XamlPropertyToken,std::hash<XamlPropertyToken>,std::equal_to<XamlPropertyToken>>,std::allocator<std::pair<XamlPropertyToken const,unsigned int>>,0>>::_Desired_grow_bucket_count(
                  (std::_Hash<std::_Umap_traits<XamlTypeToken,unsigned int,std::_Uhash_compare<XamlTypeToken,std::hash<XamlTypeToken>,std::equal_to<XamlTypeToken> >,std::allocator<std::pair<XamlTypeToken const ,unsigned int> >,0> > *)&this->m_resourceMap,
                  v31);
          std::_Hash<std::_Umap_traits<std::pair<xstring_ptr,bool>,CDependencyObject *,std::_Uhash_compare<std::pair<xstring_ptr,bool>,ResourceKeyHasher,std::equal_to<std::pair<xstring_ptr,bool>>>,std::allocator<std::pair<std::pair<xstring_ptr,bool> const,CDependencyObject *>>,0>>::_Forced_rehash(
            &this->m_resourceMap,
            v59);
          v60 = 2 * (v21 & this->m_resourceMap._Mask);
          v61 = this->m_resourceMap._Vec._Mypair._Myval2._Myfirst;
          v62 = (HSTRING)v61[2 * (v21 & this->m_resourceMap._Mask) + 1]._Ptr;
          Myhead = this->m_resourceMap._List._Mypair._Myval2._Myhead;
          if ( v62 != (HSTRING)Myhead )
          {
            string = (HSTRING)v61[v60]._Ptr;
            while ( 1 )
            {
              if ( std::operator==<xstring_ptr,bool,xstring_ptr,bool>(
                     &Ptr->_Myval.first,
                     (const std::pair<xstring_ptr,bool> *)(v62 + 4)) )
              {
                Myhead = *(std::_List_node<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *>,void *> **)v62;
                goto LABEL_33;
              }
              if ( v62 == string )
                break;
              v62 = (HSTRING)*((_QWORD *)v62 + 1);
            }
            Myhead = (std::_List_node<std::pair<std::pair<xstring_ptr,bool> const ,CDependencyObject *>,void *> *)v62;
          }
        }
LABEL_33:
        Prev = Myhead->_Prev;
        ++this->m_resourceMap._List._Mypair._Myval2._Mysize;
        Ptr->_Next = Myhead;
        Ptr->_Prev = Prev;
        Prev->_Next = Ptr;
        Myhead->_Prev = Ptr;
        v36 = 2 * ((unsigned __int64)pppStowedExceptions & this->m_resourceMap._Mask);
        v28 = this->m_resourceMap._Vec._Mypair._Myval2._Myfirst;
        v37 = v28[2 * ((unsigned __int64)pppStowedExceptions & this->m_resourceMap._Mask)]._Ptr;
        if ( v37 == this->m_resourceMap._List._Mypair._Myval2._Myhead )
        {
          v28[2 * ((unsigned __int64)pppStowedExceptions & this->m_resourceMap._Mask)]._Ptr = Ptr;
        }
        else
        {
          if ( v37 == Myhead )
          {
            v28[2 * ((unsigned __int64)pppStowedExceptions & this->m_resourceMap._Mask)]._Ptr = Ptr;
            goto LABEL_36;
          }
          if ( v28[2 * ((unsigned __int64)pppStowedExceptions & this->m_resourceMap._Mask) + 1]._Ptr != Prev )
            goto LABEL_36;
        }
        v28[v36 + 1]._Ptr = Ptr;
LABEL_36:
        v38 = 1;
        goto LABEL_37;
      }
      pcStowedExceptions[0] = 0;
      v18 = *(wchar_t **)v16;
      if ( v17 < 0 )
      {
        v18 = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)v18, pcStowedExceptions);
        v19 = pcStowedExceptions[0];
      }
      else
      {
        v19 = v17 & 0x3FFFFFFF;
        pcStowedExceptions[0] = v19;
      }
      v20 = WindowsCreateString(v18, v19, &string);
      if ( v20 < 0 )
        goto LABEL_20;
    }
    v16 = (unsigned __int64)string | 1;
    goto LABEL_21;
  }
  *(xencoded_string_ptr *)pcStowedExceptions = xstring_ptr_constants::c_xencoded_string_ptr_null;
  string = xstring_ptr_constants::c_xencoded_string_ptr_null.Handle;
  pppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
  v63 = CErrorService::OriginateInvalidOperationError(
          this->m_sharedState.m_ptr->m_value.m_coreServices,
          0xFC4u,
          (const xstring_ptr_view *)&pppStowedExceptions,
          (const xstring_ptr_view *)&string,
          (const xstring_ptr_view *)pcStowedExceptions);
  xencoded_string_ptr::Reset((xruntime_string_ptr *)&pppStowedExceptions);
  xencoded_string_ptr::Reset((xruntime_string_ptr *)&string);
  xencoded_string_ptr::Reset((xruntime_string_ptr *)pcStowedExceptions);
  if ( v63 >= 0 )
    goto LABEL_14;
LABEL_69:
  OnFailure_2990_(v63);
  return (unsigned int)v63;
}

```

## disassembly

```asm
0x18017cf18  mov     [rsp-8+arg_18], rbx
0x18017cf1d  push    rbp
0x18017cf1e  push    rsi
0x18017cf1f  push    rdi
0x18017cf20  push    r12
0x18017cf22  push    r13
0x18017cf24  push    r14
0x18017cf26  push    r15
0x18017cf28  lea     rbp, [rsp-17h]
0x18017cf2d  sub     rsp, 0D0h
0x18017cf34  mov     rax, cs:__security_cookie
0x18017cf3b  xor     rax, rsp
0x18017cf3e  mov     [rbp+47h+var_40], rax
0x18017cf42  movzx   edi, fKeyIsType
0x18017cf46  mov     [rbp+47h+var_B0], dil
0x18017cf4a  mov     r12, pValue
0x18017cf4d  mov     r14, strKey
0x18017cf50  mov     [rbp+47h+other], strKey
0x18017cf54  mov     r15, this
0x18017cf57  xor     ebx, ebx
0x18017cf59  mov     r13d, ebx
0x18017cf5c  mov     [rbp+47h+pcStowedExceptions], ebx
0x18017cf5f  mov     rax, [strKey]
0x18017cf62  test    al, 1
0x18017cf64  jnz     loc_18017D4D6
0x18017cf6a  mov     this, [rax]; _Arg0
0x18017cf6d  cmp     [rax+8], ebx
0x18017cf70  jl      loc_18017D4DD
0x18017cf76  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits+2, 4
0x18017cf7d  jnz     loc_18017D601
0x18017cf83  test    byte ptr cs:Microsoft_Windows_XAML_DiagnosticsEnableBits, 2
0x18017cf8a  jnz     loc_18017D653
0x18017cf90  test    r12, r12
0x18017cf93  jz      loc_18017D2B2
0x18017cf99  mov     rax, [r12]
0x18017cf9d  mov     this, r12
0x18017cfa0  mov     rax, [rax+258h]
0x18017cfa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017cfac  mov     esi, 28Bh
0x18017cfb1  cmp     si, ax
0x18017cfb4  jz      short loc_18017CFEA
0x18017cfb6  mov     ecx, 43Ch
0x18017cfbb  cmp     ax, cx
0x18017cfbe  jnb     loc_18017D39C
0x18017cfc4  movzx   eax, ax
0x18017cfc7  add     rax, rax
0x18017cfca  lea     this, ?c_aTypeCheckData@@3QBUTypeCheckData@@B.m_handle; TypeCheckData const near * const c_aTypeCheckData ...
0x18017cfd1  mov     eax, [this+rax*8]
0x18017cfd4  and     eax, 0FFFFFh
0x18017cfd9  cmp     rax, 50107h
0x18017cfdf  setz    al
0x18017cfe2  test    al, al
0x18017cfe4  jz      loc_18017D2B2
0x18017cfea  mov     rax, r12
0x18017cfed  test    byte ptr [r15+130h], 4
0x18017cff5  jnz     loc_18017D462
0x18017cffb  test    rax, rax
0x18017cffe  jnz     loc_18017D506
0x18017d004  lea     rsi, [r15+0D8h]
0x18017d00b  mov     rax, [r14]
0x18017d00e  test    al, 1
0x18017d010  jnz     loc_18017D3CC
0x18017d016  test    rax, rax
0x18017d019  jz      short loc_18017D096
0x18017d01b  mov     edx, [rax+8]
0x18017d01e  bt      edx, 1Eh
0x18017d022  jnb     short loc_18017D096
0x18017d024  mov     [rbp+47h+pcStowedExceptions], ebx
0x18017d027  mov     rax, [rax]
0x18017d02a  test    edx, edx
0x18017d02c  js      loc_18017D5E0
0x18017d032  and     edx, 3FFFFFFFh; length
0x18017d038  mov     [rbp+47h+pcStowedExceptions], edx
0x18017d03b  lea     pValue, [rbp+47h+string]; string
0x18017d03f  mov     this, rax; sourceString
0x18017d042  call    cs:__imp_WindowsCreateString
0x18017d048  test    eax, eax
0x18017d04a  jns     loc_18017D3E5
0x18017d050  mov     ecx, eax; failedFrameHR
0x18017d052  call    OnFailure_2990_
0x18017d057  mov     [rbp+47h+pppStowedExceptions], rbx
0x18017d05b  mov     [rbp+47h+pcStowedExceptions], ebx
0x18017d05e  mov     ebx, 8000FFFFh
0x18017d063  mov     ecx, ebx; errorCode
0x18017d065  call    TraceForFailFast
0x18017d06a  xor     r8d, r8d; contextRecord
0x18017d06d  xor     edx, edx; directCallerReturnAddress
0x18017d06f  mov     ecx, ebx; failedFrameHR
0x18017d071  call    OnNewFailureEncountered
0x18017d076  lea     strKey, [rbp+47h+pcStowedExceptions]; pcStowedExceptions
0x18017d07a  lea     this, [rbp+47h+pppStowedExceptions]; pppStowedExceptions
0x18017d07e  call    GetStowedExceptionsForFailFast
0x18017d083  mov     pValue, [rbp+47h+pppStowedExceptions]
0x18017d087  mov     edx, [rbp+47h+pcStowedExceptions]
0x18017d08a  mov     ecx, ebx
0x18017d08c  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x18017d092  mov     rax, [rbp+47h+string]
0x18017d096  mov     qword ptr [rbp+47h+pcStowedExceptions], rax
0x18017d09a  mov     [rbp+47h+var_A0], dil
0x18017d09e  lea     this, [rbp+47h+pcStowedExceptions]; this
0x18017d0a2  call    ?GetHash@xstring_ptr_view@@QEBA_KXZ; xstring_ptr_view::GetHash(void)
0x18017d0a7  mov     r14, rax
0x18017d0aa  mov     [rbp+47h+pppStowedExceptions], rax
0x18017d0ae  mov     this, rax
0x18017d0b1  and     this, [rsi+30h]
0x18017d0b5  add     this, this
0x18017d0b8  mov     strKey, [rsi+18h]
0x18017d0bc  mov     rbx, [strKey+this*8+8]
0x18017d0c1  lea     rax, [rsi+8]
0x18017d0c5  mov     rdi, [rax]
0x18017d0c8  cmp     rbx, rdi
0x18017d0cb  jz      short loc_18017D111
0x18017d0cd  mov     r13, [strKey+this*8]
0x18017d0d1  lea     this, [rbx+10h]; this
0x18017d0d5  call    ?GetCount@xstring_ptr_view@@QEBAIXZ; xstring_ptr_view::GetCount(void)
0x18017d0da  mov     edi, eax
0x18017d0dc  lea     this, [rbp+47h+pcStowedExceptions]; this
0x18017d0e0  call    ?GetCount@xstring_ptr_view@@QEBAIXZ; xstring_ptr_view::GetCount(void)
0x18017d0e5  cmp     eax, edi
0x18017d0e7  jnz     short loc_18017D101
0x18017d0e9  xor     r8d, r8d; eCompareBehavior
0x18017d0ec  lea     strKey, [rbx+10h]; other
0x18017d0f0  lea     this, [rbp+47h+pcStowedExceptions]; this
0x18017d0f4  call    ?Compare@xstring_ptr_view@@QEBAHAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::Compare(xstring_ptr_view const &,xstrCompareBehavior)
0x18017d0f9  test    eax, eax
0x18017d0fb  jz      loc_18017D3B4
0x18017d101  cmp     rbx, r13
0x18017d104  jnz     loc_18017D3F2
0x18017d10a  mov     rdi, rbx
0x18017d10d  lea     rax, [rsi+8]
0x18017d111  mov     this, 666666666666666h; __formal
0x18017d11b  cmp     [rsi+10h], this
0x18017d11f  jz      loc_18017D7AC
0x18017d125  mov     qword ptr [rbp+47h+uri.m_value], rax
0x18017d129  mov     qword ptr [rbp+47h+uri.m_flags], 0
0x18017d131  mov     ecx, 28h ; '('; _Bytes
0x18017d136  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18017d13b  mov     rbx, rax
0x18017d13e  mov     qword ptr [rbp+47h+uri.m_flags], rax
0x18017d142  mov     rax, qword ptr [rbp+47h+pcStowedExceptions]
0x18017d146  mov     r13, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x18017d14d  mov     qword ptr [rbp+47h+pcStowedExceptions], r13
0x18017d151  mov     [rbx+10h], rax
0x18017d155  mov     al, [rbp+47h+var_A0]
0x18017d158  mov     [rbx+18h], al
0x18017d15b  mov     qword ptr [rbx+20h], 0
0x18017d163  mov     strKey, [rsi+10h]
0x18017d167  add     strKey, 1; _For_size
0x18017d16b  xorps   xmm0, xmm0
0x18017d16e  js      loc_18017D61C
0x18017d174  cvtsi2ss xmm0, strKey
0x18017d179  mov     this, [rsi+38h]
0x18017d17d  xorps   xmm1, xmm1
0x18017d180  test    this, this
0x18017d183  js      loc_18017D639
0x18017d189  cvtsi2ss xmm1, this
0x18017d18e  divss   xmm0, xmm1
0x18017d192  comiss  xmm0, dword ptr [rsi]
0x18017d195  ja      loc_18017D40A
0x18017d19b  mov     strKey, [rdi+8]
0x18017d19f  inc     qword ptr [rsi+10h]
0x18017d1a3  mov     [rbx], rdi
0x18017d1a6  mov     [rbx+8], strKey
0x18017d1aa  mov     [strKey], rbx
0x18017d1ad  mov     [rdi+8], rbx
0x18017d1b1  mov     rax, [rsi+30h]
0x18017d1b5  and     rax, [rbp+47h+pppStowedExceptions]
0x18017d1b9  add     rax, rax
0x18017d1bc  mov     this, [rsi+18h]; failedFrameHR
0x18017d1c0  mov     pValue, [this+rax*8]
0x18017d1c4  cmp     pValue, [rsi+8]
0x18017d1c8  jnz     loc_18017D4ED
0x18017d1ce  mov     [this+rax*8], rbx
0x18017d1d2  mov     [this+rax*8+8], rbx
0x18017d1d7  mov     dil, 1
0x18017d1da  test    r13b, 1
0x18017d1de  jnz     loc_18017D2A0
0x18017d1e4  test    dil, dil
0x18017d1e7  jz      loc_18017D3FB
0x18017d1ed  lea     rsi, [r15+0C0h]
0x18017d1f4  mov     dil, [rbp+47h+var_B0]
0x18017d1f8  and     dil, 0FCh
0x18017d1fc  mov     al, [rbp+47h+arg_20]
0x18017d1ff  add     al, al
0x18017d201  or      dil, al
0x18017d204  mov     r14b, [rbp+47h+var_B0]
0x18017d208  or      dil, r14b
0x18017d20b  mov     strKey, [rbp+47h+other]; other
0x18017d20f  lea     this, [rbp+47h+column]; this
0x18017d213  call    ??0xstring_ptr@@QEAA@AEBV0@@Z; xstring_ptr::xstring_ptr(xstring_ptr const &)
0x18017d218  mov     byte ptr [rbp+47h+column.m_flags], dil
0x18017d21c  mov     pValue, [rsi+10h]
0x18017d220  mov     this, [rsi+8]
0x18017d224  mov     [rbp+47h+pppStowedExceptions], this
0x18017d228  cmp     this, pValue
0x18017d22b  jz      loc_18017D2BA
0x18017d231  mov     r13, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x18017d238  mov     rax, qword ptr [rbp+47h+column.m_value]
0x18017d23c  mov     [this], rax
0x18017d23f  mov     [this+8], dil
0x18017d243  add     qword ptr [rsi+8], 0Ch
0x18017d248  test    r13b, 1
0x18017d24c  jz      short loc_18017D25C
0x18017d24e  and     r13, 0FFFFFFFFFFFFFFFEh
0x18017d252  mov     this, r13; string
0x18017d255  call    cs:__imp_WindowsDeleteString
0x18017d25b  nop
0x18017d25c  mov     [rbx+20h], r12
0x18017d260  mov     al, [rbp+47h+arg_28]
0x18017d263  test    al, al
0x18017d265  jz      short loc_18017D26E
0x18017d267  inc     dword ptr [r15+0B8h]
0x18017d26e  test    r14b, r14b
0x18017d271  jnz     loc_18017D533
0x18017d277  xor     eax, eax
0x18017d279  mov     this, [rbp+47h+var_40]
0x18017d27d  xor     this, rsp; StackCookie
0x18017d280  call    __security_check_cookie
0x18017d285  mov     rbx, [rsp+100h+arg_18]
0x18017d28d  add     rsp, 0D0h
0x18017d294  pop     r15
0x18017d296  pop     r14
0x18017d298  pop     r13
0x18017d29a  pop     r12
0x18017d29c  pop     rdi
0x18017d29d  pop     rsi
0x18017d29e  pop     rbp
0x18017d29f  retn
0x18017d2a0  and     r13, 0FFFFFFFFFFFFFFFEh
0x18017d2a4  mov     this, r13; string
0x18017d2a7  call    cs:__imp_WindowsDeleteString
0x18017d2ad  jmp     loc_18017D1E4
0x18017d2b2  mov     rax, rbx
0x18017d2b5  jmp     loc_18017CFED
0x18017d2ba  sub     this, [rsi]; __formal
0x18017d2bd  mov     r10, 2AAAAAAAAAAAAAABh
0x18017d2c7  mov     rax, r10
0x18017d2ca  imul    this
0x18017d2cd  mov     r13, strKey
0x18017d2d0  sar     r13, 1
0x18017d2d3  mov     rax, r13
0x18017d2d6  shr     rax, 3Fh
0x18017d2da  add     r13, rax
0x18017d2dd  mov     r14, 1555555555555555h
0x18017d2e7  cmp     r13, r14
0x18017d2ea  jz      loc_18017D7C2
0x18017d2f0  lea     r9, [r13+1]
0x18017d2f4  mov     qword ptr [rbp+47h+pcStowedExceptions], r9
0x18017d2f8  sub     pValue, [rsi]
0x18017d2fb  mov     rax, r10
0x18017d2fe  imul    pValue
0x18017d301  sar     strKey, 1
0x18017d304  mov     rax, strKey
0x18017d307  shr     rax, 3Fh
0x18017d30b  add     strKey, rax
0x18017d30e  mov     this, strKey
0x18017d311  shr     this, 1
0x18017d314  mov     rax, r14
0x18017d317  sub     rax, this
0x18017d31a  cmp     strKey, rax
0x18017d31d  ja      short loc_18017D32A
0x18017d31f  lea     r14, [this+strKey]
0x18017d323  cmp     r14, r9
0x18017d326  cmovb   r14, r9
0x18017d32a  mov     this, r14; _Count
0x18017d32d  call    ??$_Get_size_of_n@$0M@@std@@YA_K_K@Z; std::_Get_size_of_n<12>(unsigned __int64)
0x18017d332  mov     this, rax; _Bytes
0x18017d335  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18017d33a  mov     [rbp+47h+other], rax
0x18017d33e  lea     strKey, ds:0[r13*2]
0x18017d346  add     strKey, r13
0x18017d349  mov     [rbp+47h+string], strKey
0x18017d34d  mov     r13, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x18017d354  mov     this, qword ptr [rbp+47h+column.m_value]
0x18017d358  mov     [rax+strKey*4], this
0x18017d35c  mov     [rax+strKey*4+8], dil
0x18017d361  mov     strKey, [rsi+8]; _Last
0x18017d365  mov     r11, [rbp+47h+pppStowedExceptions]
0x18017d369  mov     pValue, rax; _Dest
0x18017d36c  mov     this, [rsi]; _First
0x18017d36f  cmp     r11, strKey
0x18017d372  jnz     loc_18017D7C8
0x18017d378  call    ??$_Uninitialized_move@PEAU?$pair@Vxstring_ptr@@UKeyInfo@CResourceDictionary@@@std@@V?$allocator@U?$pair@Vxstring_ptr@@UKeyInfo@CResourceDictionary@@@std@@@2@@std@@YAPEAU?$pair@Vxstring_ptr@@UKeyInfo@CResourceDictionary@@@0@QEAU10@0PEAU10@AEAV?$allocator@U?$pair@Vxstring_ptr@@UKeyInfo@CResourceDictionary@@@std@@@0@@Z; std::_Uninitialized_move<std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *,std::allocator<std::pair<xstring_ptr,CResourceDictionary::KeyInfo>>>(std::pair<xstring_ptr,CResourceDictionary::KeyInfo> * const,std::pair<xstring_ptr,CResourceDictionary::KeyInfo> * const,std::pair<xstring_ptr,CResourceDictionary::KeyInfo> *,std::allocator<std::pair<xstring_ptr,CResourceDictionary::KeyInfo>> &)
0x18017d37d  mov     rdi, [rbp+47h+other]
0x18017d381  mov     r9, r14; _Newcapacity
0x18017d384  mov     pValue, qword ptr [rbp+47h+pcStowedExceptions]; _Newsize
0x18017d388  mov     strKey, rdi; _Newvec
0x18017d38b  mov     this, rsi; this
0x18017d38e  call    ?_Change_array@?$vector@U?$pair@Vxstring_ptr@@UKeyInfo@CResourceDictionary@@@std@@V?$allocator@U?$pair@Vxstring_ptr@@UKeyInfo@CResourceDictionary@@@std@@@2@@std@@AEAAXQEAU?$pair@Vxstring_ptr@@UKeyInfo@CResourceDictionary@@@2@_K1@Z; std::vector<std::pair<xstring_ptr,CResourceDictionary::KeyInfo>>::_Change_array(std::pair<xstring_ptr,CResourceDictionary::KeyInfo> * const,unsigned __int64,unsigned __int64)
0x18017d393  mov     r14b, [rbp+47h+var_B0]
0x18017d397  jmp     loc_18017D248
0x18017d39c  movzx   ecx, ax; eTypeIndex
0x18017d39f  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x18017d3a4  mov     this, rax; typeClass
0x18017d3a7  movzx   edx, si; targetType
0x18017d3aa  call    ?CompareCustomTypesHelper@MetadataAPI@DirectUI@@CA_NPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::CompareCustomTypesHelper(CClassInfo const *,KnownTypeIndex)
0x18017d3af  jmp     loc_18017CFE2
0x18017d3b4  mov     al, [rbx+18h]
0x18017d3b7  cmp     [rbp+47h+var_A0], al
0x18017d3ba  jnz     loc_18017D101
  ... truncated ...
```
