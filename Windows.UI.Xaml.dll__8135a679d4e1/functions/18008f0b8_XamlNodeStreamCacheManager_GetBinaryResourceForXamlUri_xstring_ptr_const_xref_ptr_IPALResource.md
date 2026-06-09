# XamlNodeStreamCacheManager::GetBinaryResourceForXamlUri(xstring_ptr const &,xref_ptr<IPALResource> &)

- ea: `0x18008f0b8`
- end: `0x18008fc00`
- name: `?GetBinaryResourceForXamlUri@XamlNodeStreamCacheManager@@QEAAJAEBVxstring_ptr@@AEAV?$xref_ptr@UIPALResource@@@@@Z`
- size: `2888`
- prototype: `HRESULT __fastcall(XamlNodeStreamCacheManager *this, const xstring_ptr *strUri, xref_ptr<IPALResource> *spXbfResourceOut)`
- caller_count: `2`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008df04`
- `0x1802838d0`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18008e368`
- `0x18008f0b8`
- `0x18008fc08`
- `0x18008fc2c`
- `0x180090138`
- `0x1800907a4`
- `0x180090dec`
- `0x1800aabf0`
- `0x1800adbb0`
- `0x1800af8e0`
- `0x1800fe130`
- `0x18017d850`
- `0x18017d880`
- `0x1801800b8`
- `0x1801952a8`
- `0x1804c74a0`
- `0x1804d1bd4`
- `0x1804e7328`
- `0x18069f6ac`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18008f20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18008f20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008f411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008f78a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008f80c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008f8c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008f9c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008fa64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008fafe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008f411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008f78a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008f80c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008f8c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008f9c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008fa64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18008fafe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f88d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f88d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18008f8a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18008f941`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18008fa43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18008f8a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18008f941`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18008fa43`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall XamlNodeStreamCacheManager::GetBinaryResourceForXamlUri(
        XamlNodeStreamCacheManager *this,
        const xstring_ptr *strUri,
        xref_ptr<IPALResource> *spXbfResourceOut)
{
  IPALUri *v6; // rdi
  IPALResource *m_ptr; // rcx
  unsigned __int64 v8; // rcx
  std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<xstring_ptr const ,xref_ptr<IPALResource> > > > > *Myfirst; // rax
  std::_List_node<std::pair<xstring_ptr const ,xref_ptr<IPALResource> >,void *> *Ptr; // rbx
  std::_List_node<std::pair<xstring_ptr const ,xref_ptr<IPALResource> >,void *> *v11; // rsi
  unsigned __int64 RuntimeStringHandleMarker; // rcx
  int v13; // eax
  PCWSTR StringRawBuffer; // r8
  UINT32 v15; // eax
  _WORD *i; // rbx
  __int64 v17; // rbx
  UINT32 v18; // ecx
  int v19; // eax
  unsigned int v20; // edi
  const wchar_t *Buffer; // rax
  HRESULT v22; // eax
  unsigned int v23; // ebx
  HRESULT v24; // eax
  HRESULT v25; // eax
  HRESULT v26; // eax
  const xstring_ptr_storage *Storage; // rbx
  int v28; // eax
  UINT32 v29; // eax
  IParserCoreServices *m_pCore; // rbx
  HRESULT (__fastcall *GetResourceManager)(IParserCoreServices *, IPALResourceManager **); // rsi
  IPALResourceManager *v32; // rcx
  HRESULT v33; // eax
  IPALResourceManager *v34; // rbx
  HRESULT (__fastcall *TryGetLocalResource)(IPALResourceManager *, IPALUri *, IPALResource **); // rsi
  IPALResource *v36; // rcx
  HRESULT v37; // eax
  IPALUri *v38; // rax
  HRESULT v39; // eax
  int v40; // eax
  UINT32 StringLen; // eax
  unsigned __int64 v42; // rax
  std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<xstring_ptr const ,xref_ptr<IPALResource> > > > > *v43; // rcx
  std::_List_node<std::pair<xstring_ptr const ,xref_ptr<IPALResource> >,void *> *Myhead; // rbx
  std::_List_node<std::pair<xstring_ptr const ,xref_ptr<IPALResource> >,void *> *v45; // rsi
  IPALResource *v46; // rcx
  IPALResource *v47; // rcx
  char v48; // cl
  IPALResource *v49; // rax
  xref_ptr<IPALResource> *Mylast; // rdx
  IPALResource *v51; // rcx
  IPALResourceManager *v52; // rcx
  IPALResource *v53; // rcx
  int v55; // eax
  UINT32 v56; // eax
  IPALResourceManager *v57; // rcx
  IPALResource *v58; // rcx
  IPALResourceManager *v59; // rcx
  IPALResource *v60; // rcx
  HSTRING v61; // rcx
  HSTRING v62; // rcx
  IPALResourceManager *v63; // rcx
  IPALResource *v64; // rcx
  HSTRING v65; // rcx
  IPALResourceManager *v66; // rcx
  IPALResource *v67; // rcx
  HSTRING v68; // rcx
  IPALResourceManager *v69; // rcx
  IPALResource *v70; // rcx
  IPALResourceManager *v71; // rcx
  IPALResource *v72; // rcx
  xref_ptr<IPALResource> spXbfResource; // [rsp+20h] [rbp-E0h] BYREF
  char v74; // [rsp+28h] [rbp-D8h]
  xref_ptr<IPALResourceManager> spResourceManager; // [rsp+30h] [rbp-D0h] BYREF
  xstring_ptr strPhysicalUri; // [rsp+38h] [rbp-C8h] BYREF
  xstring_ptr strScheme; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 length; // [rsp+48h] [rbp-B8h] BYREF
  std::pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xstring_ptr const ,xref_ptr<IPALResource> > > > >,bool> v79; // [rsp+50h] [rbp-B0h] BYREF
  int v80; // [rsp+60h] [rbp-A0h]
  xref_ptr<IPALUri> pXbfUri; // [rsp+68h] [rbp-98h] BYREF
  std::pair<xstring_ptr const ,xref_ptr<IPALResource> > v82; // [rsp+70h] [rbp-90h] BYREF
  TStringBuilder<96> xbfUriBuilder; // [rsp+80h] [rbp-80h] BYREF

  spXbfResource.m_ptr = 0;
  spResourceManager.m_ptr = 0;
  v6 = 0;
  pXbfUri.m_ptr = 0;
  strScheme.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  strPhysicalUri.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  v74 = 0;
  m_ptr = spXbfResourceOut->m_ptr;
  if ( spXbfResourceOut->m_ptr )
  {
    spXbfResourceOut->m_ptr = 0;
    m_ptr->Release(m_ptr);
    xref_ptr<HWTexture>::IncrementRefCount((xref_ptr<SharedShadowCasterPair> *)spXbfResourceOut);
  }
  v8 = 2 * (xstring_ptr_view::GetHash(&strUri->xstring_ptr_view) & this->m_UriToXbfResourceMap._Mask);
  Myfirst = this->m_UriToXbfResourceMap._Vec._Mypair._Myval2._Myfirst;
  Ptr = Myfirst[v8 + 1]._Ptr;
  if ( Ptr == this->m_UriToXbfResourceMap._List._Mypair._Myval2._Myhead )
  {
LABEL_57:
    Ptr = 0;
  }
  else
  {
    v11 = Myfirst[v8]._Ptr;
    while ( !xstring_ptr_view::operator==(&strUri->xstring_ptr_view, &Ptr->_Myval.first) )
    {
      if ( Ptr == v11 )
        goto LABEL_57;
      Ptr = Ptr->_Prev;
    }
  }
  if ( !Ptr )
    Ptr = this->m_UriToXbfResourceMap._List._Mypair._Myval2._Myhead;
  if ( Ptr != this->m_UriToXbfResourceMap._List._Mypair._Myval2._Myhead )
  {
    if ( &spXbfResource == &Ptr->_Myval.second )
    {
LABEL_63:
      v48 = v74;
      goto LABEL_66;
    }
    v46 = spXbfResource.m_ptr;
    spXbfResource.m_ptr = Ptr->_Myval.second.m_ptr;
    if ( v46 )
      v46->Release(v46);
LABEL_62:
    xref_ptr<HWTexture>::IncrementRefCount((xref_ptr<SharedShadowCasterPair> *)&spXbfResource);
    goto LABEL_63;
  }
  if ( !xstring_ptr_view::GetCount(&strUri->xstring_ptr_view) )
  {
LABEL_42:
    if ( ((__int64)strPhysicalUri.m_encodedStorage.Storage & 1) != 0 )
    {
      v65 = (HSTRING)(strPhysicalUri.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
    }
    else
    {
      v40 = *((_DWORD *)strPhysicalUri.m_encodedStorage.Storage + 2);
      if ( v40 >= 0 )
      {
        StringLen = v40 & 0x3FFFFFFF;
LABEL_45:
        if ( !StringLen )
        {
          xstring_ptr::xstring_ptr((xstring_ptr *)&v82.first, strUri);
          v82.second = spXbfResource;
          xref_ptr<HWTexture>::IncrementRefCount((xref_ptr<SharedShadowCasterPair> *)&v82.second);
          std::_Hash<std::_Umap_traits<xstring_ptr,xref_ptr<IPALResource>,std::_Uhash_compare<xstring_ptr,std::hash<xstring_ptr>,std::equal_to<xstring_ptr>>,std::allocator<std::pair<xstring_ptr const,xref_ptr<IPALResource>>>,0>>::emplace<std::pair<xstring_ptr const,xref_ptr<IPALResource>>>(
            &this->m_UriToXbfResourceMap,
            &v79,
            &v82);
          xref_ptr<INameScope>::DecrementRefCount((xref_ptr<CMemorySurface> *)&v82.second);
          goto LABEL_65;
        }
        v42 = 2 * (this->m_UriToXbfResourceMap._Mask & xstring_ptr_view::GetHash(&strPhysicalUri));
        v43 = this->m_UriToXbfResourceMap._Vec._Mypair._Myval2._Myfirst;
        Myhead = v43[v42 + 1]._Ptr;
        if ( Myhead == this->m_UriToXbfResourceMap._List._Mypair._Myval2._Myhead )
        {
LABEL_84:
          Myhead = 0;
        }
        else
        {
          v45 = v43[v42]._Ptr;
          while ( !xstring_ptr_view::operator==(&strPhysicalUri, &Myhead->_Myval.first) )
          {
            if ( Myhead == v45 )
              goto LABEL_84;
            Myhead = Myhead->_Prev;
          }
        }
        if ( !Myhead )
          Myhead = this->m_UriToXbfResourceMap._List._Mypair._Myval2._Myhead;
        if ( Myhead == this->m_UriToXbfResourceMap._List._Mypair._Myval2._Myhead )
        {
          xstring_ptr::xstring_ptr((xstring_ptr *)&v82.first, &strPhysicalUri);
          v82.second = spXbfResource;
          xref_ptr<HWTexture>::IncrementRefCount((xref_ptr<SharedShadowCasterPair> *)&v82.second);
          std::_Hash<std::_Umap_traits<xstring_ptr,xref_ptr<IPALResource>,std::_Uhash_compare<xstring_ptr,std::hash<xstring_ptr>,std::equal_to<xstring_ptr>>,std::allocator<std::pair<xstring_ptr const,xref_ptr<IPALResource>>>,0>>::emplace<std::pair<xstring_ptr const,xref_ptr<IPALResource>>>(
            &this->m_UriToXbfResourceMap,
            &v79,
            &v82);
          xref_ptr<INameScope>::DecrementRefCount((xref_ptr<CMemorySurface> *)&v82.second);
LABEL_65:
          xstring_ptr::~xstring_ptr((xstring_ptr *)&v82.first);
          v48 = 1;
LABEL_66:
          v49 = spXbfResource.m_ptr;
          if ( spXbfResource.m_ptr )
          {
            if ( v48 )
            {
              Mylast = this->m_XbfResourceStorage._Mypair._Myval2._Mylast;
              if ( Mylast == this->m_XbfResourceStorage._Mypair._Myval2._Myend )
              {
                std::vector<xref_ptr<IPALResource>>::_Emplace_reallocate<xref_ptr<IPALResource> &>(
                  &this->m_XbfResourceStorage,
                  Mylast,
                  &spXbfResource);
              }
              else
              {
                Mylast->m_ptr = spXbfResource.m_ptr;
                xref_ptr<HWTexture>::IncrementRefCount((xref_ptr<SharedShadowCasterPair> *)Mylast);
                ++this->m_XbfResourceStorage._Mypair._Myval2._Mylast;
              }
              v49 = spXbfResource.m_ptr;
            }
            if ( spXbfResourceOut != &spXbfResource )
            {
              v51 = spXbfResourceOut->m_ptr;
              spXbfResourceOut->m_ptr = v49;
              if ( v51 )
                v51->Release(v51);
              xref_ptr<HWTexture>::IncrementRefCount((xref_ptr<SharedShadowCasterPair> *)spXbfResourceOut);
            }
          }
LABEL_75:
          xencoded_string_ptr::Reset((xruntime_string_ptr *)&strPhysicalUri);
          xencoded_string_ptr::Reset((xruntime_string_ptr *)&strScheme);
          if ( v6 )
            v6->Release(v6);
          v52 = spResourceManager.m_ptr;
          if ( spResourceManager.m_ptr )
          {
            spResourceManager.m_ptr = 0;
            v52->Release(v52);
          }
          v53 = spXbfResource.m_ptr;
          if ( spXbfResource.m_ptr )
          {
            spXbfResource.m_ptr = 0;
            v53->Release(v53);
          }
          return 0;
        }
        v47 = spXbfResource.m_ptr;
        if ( spXbfResource.m_ptr )
        {
          spXbfResource.m_ptr = 0;
          v47->Release(v47);
        }
        spXbfResource.m_ptr = 0;
        if ( &spXbfResource == &Myhead->_Myval.second )
          goto LABEL_75;
        spXbfResource.m_ptr = Myhead->_Myval.second.m_ptr;
        goto LABEL_62;
      }
      v65 = *(HSTRING *)strPhysicalUri.m_encodedStorage.Handle;
    }
    StringLen = WindowsGetStringLen(v65);
    goto LABEL_45;
  }
  length = 0;
  RuntimeStringHandleMarker = strUri->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (strUri->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v61 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
LABEL_112:
    StringRawBuffer = WindowsGetStringRawBuffer(v61, &length);
    v15 = length;
    goto LABEL_13;
  }
  v13 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
  StringRawBuffer = *(PCWSTR *)RuntimeStringHandleMarker;
  if ( v13 < 0 )
  {
    v61 = *(HSTRING *)RuntimeStringHandleMarker;
    goto LABEL_112;
  }
  v15 = v13 & 0x3FFFFFFF;
  length = v15;
LABEL_13:
  if ( !v15 )
    goto LABEL_126;
  for ( i = &StringRawBuffer[v15 - 1]; *i != 46; --i )
  {
    if ( i == StringRawBuffer )
      goto LABEL_126;
  }
  v17 = i - StringRawBuffer;
  if ( (_DWORD)v17 == -1 )
LABEL_126:
    LODWORD(v17) = xstring_ptr_view::GetCount(&strUri->xstring_ptr_view);
  xbfUriBuilder.m_pBuffer = xbfUriBuilder.m_inlineBuffer;
  xbfUriBuilder.m_hPreallocatedBuffer = 0;
  *(_QWORD *)&xbfUriBuilder.m_cBuffer = 96;
  v18 = v17 + 4;
  if ( (unsigned int)(v17 + 4) >= 0x7FFFFF9F )
  {
    v20 = -2147418113;
    OnNewFailure_2955_(v18);
  }
  else
  {
    if ( (unsigned int)(v17 + 5) <= 0x60 )
      goto LABEL_23;
    v19 = WindowsPreallocateStringBuffer(v18, &xbfUriBuilder.m_pBuffer, &xbfUriBuilder.m_hPreallocatedBuffer);
    v20 = v19;
    if ( v19 >= 0 )
    {
      xbfUriBuilder.m_cBuffer = v17 + 5;
LABEL_23:
      xbfUriBuilder.m_cActual = 0;
      Buffer = xstring_ptr_view::GetBuffer(&strUri->xstring_ptr_view);
      v22 = TStringBuilder<96>::Append(&xbfUriBuilder, Buffer, v17);
      v23 = v22;
      if ( v22 < 0 )
      {
        OnFailure_2990_(v22);
        TStringBuilder<16>::~TStringBuilder<16>(&xbfUriBuilder);
        xstring_ptr::~xstring_ptr(&strPhysicalUri);
        xstring_ptr::~xstring_ptr(&strScheme);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pXbfUri);
        xref_ptr<INameScope>::DecrementRefCount((xref_ptr<CMemorySurface> *)&spResourceManager);
        xref_ptr<INameScope>::DecrementRefCount((xref_ptr<CMemorySurface> *)&spXbfResource);
        return v23;
      }
      v24 = TStringBuilder<96>::EnsureBufferForAdding(&xbfUriBuilder, 4u);
      v23 = v24;
      if ( v24 < 0 )
      {
        OnFailure_2990_(v24);
        OnFailure_2990_(v23);
        TStringBuilder<16>::~TStringBuilder<16>(&xbfUriBuilder);
        xstring_ptr::~xstring_ptr(&strPhysicalUri);
        xstring_ptr::~xstring_ptr(&strScheme);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pXbfUri);
        xref_ptr<INameScope>::DecrementRefCount((xref_ptr<CMemorySurface> *)&spResourceManager);
        xref_ptr<INameScope>::DecrementRefCount((xref_ptr<CMemorySurface> *)&spXbfResource);
        return v23;
      }
      *(_QWORD *)&xbfUriBuilder.m_pBuffer[xbfUriBuilder.m_cActual] = 0x6600620078002ELL;
      xbfUriBuilder.m_cActual += 4;
      xbfUriBuilder.m_pBuffer[xbfUriBuilder.m_cActual] = 0;
      v25 = CWinUriFactory::Create(xbfUriBuilder.m_cActual, xbfUriBuilder.m_pBuffer, &pXbfUri.m_ptr);
      v23 = v25;
      if ( v25 < 0 )
      {
        OnFailure_2990_(v25);
        if ( xbfUriBuilder.m_pBuffer != xbfUriBuilder.m_inlineBuffer )
        {
          WindowsDeleteStringBuffer(xbfUriBuilder.m_hPreallocatedBuffer);
          xbfUriBuilder.m_hPreallocatedBuffer = 0;
        }
        xbfUriBuilder.m_pBuffer = 0;
        xencoded_string_ptr::Reset((xruntime_string_ptr *)&strPhysicalUri);
        xencoded_string_ptr::Reset((xruntime_string_ptr *)&strScheme);
        if ( pXbfUri.m_ptr )
          pXbfUri.m_ptr->Release(pXbfUri.m_ptr);
        v71 = spResourceManager.m_ptr;
        if ( spResourceManager.m_ptr )
        {
          spResourceManager.m_ptr = 0;
          v71->Release(v71);
        }
        v72 = spXbfResource.m_ptr;
        if ( spXbfResource.m_ptr )
        {
          spXbfResource.m_ptr = 0;
          v72->Release(v72);
        }
        return v23;
      }
      v6 = pXbfUri.m_ptr;
      v26 = UriXStringGetters_Internal::GetUriPart<long (IPALUri::*)(unsigned int *,unsigned short *)const>(
              pXbfUri.m_ptr,
               Windows::UI::Composition::Scenes::IScenePbrMaterial::`vcall'{104,{flat}},
              &strScheme);
      v23 = v26;
      if ( v26 < 0 )
      {
        OnFailure_2990_(v26);
        if ( xbfUriBuilder.m_pBuffer != xbfUriBuilder.m_inlineBuffer )
        {
          WindowsDeleteStringBuffer(xbfUriBuilder.m_hPreallocatedBuffer);
          xbfUriBuilder.m_hPreallocatedBuffer = 0;
        }
        xbfUriBuilder.m_pBuffer = 0;
        xencoded_string_ptr::Reset((xruntime_string_ptr *)&strPhysicalUri);
        xencoded_string_ptr::Reset((xruntime_string_ptr *)&strScheme);
        if ( v6 )
          v6->Release(v6);
        v66 = spResourceManager.m_ptr;
        if ( spResourceManager.m_ptr )
        {
          spResourceManager.m_ptr = 0;
          v66->Release(v66);
        }
        v67 = spXbfResource.m_ptr;
        if ( spXbfResource.m_ptr )
        {
          spXbfResource.m_ptr = 0;
          v67->Release(v67);
        }
        return v23;
      }
      Storage = strScheme.m_encodedStorage.Storage;
      if ( ((__int64)strScheme.m_encodedStorage.Storage & 1) != 0 )
      {
        v62 = (HSTRING)(strScheme.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
      }
      else
      {
        v28 = *((_DWORD *)strScheme.m_encodedStorage.Storage + 2);
        if ( v28 >= 0 )
        {
          v29 = v28 & 0x3FFFFFFF;
          goto LABEL_30;
        }
        v62 = *(HSTRING *)strScheme.m_encodedStorage.Handle;
      }
      v29 = WindowsGetStringLen(v62);
LABEL_30:
      if ( v29 == 7 )
      {
        v79.first._Ptr = (std::_List_node<std::pair<xstring_ptr const ,xref_ptr<IPALResource> >,void *> *)&xstring_ptr_constants::c_xstring_ptr_storage_null;
        *(_QWORD *)&v79.second = L"ms-appx";
        v80 = 1073741831;
        xencoded_string_ptr::Reset((xruntime_string_ptr *)&v79);
        v79.first._Ptr = (std::_List_node<std::pair<xstring_ptr const ,xref_ptr<IPALResource> >,void *> *)&v79.second;
        if ( !xstring_ptr_view::Compare(&strScheme, (const xstring_ptr_view *)&v79, xstrCompareCaseInsensitive) )
        {
LABEL_32:
          m_pCore = this->m_pCore;
          GetResourceManager = this->m_pCore->GetResourceManager;
          v32 = spResourceManager.m_ptr;
          if ( spResourceManager.m_ptr )
          {
            spResourceManager.m_ptr = 0;
            v32->Release(v32);
          }
          v33 = GetResourceManager(m_pCore, &spResourceManager.m_ptr);
          v23 = v33;
          if ( v33 < 0 )
          {
            OnFailure_2990_(v33);
            if ( xbfUriBuilder.m_pBuffer != xbfUriBuilder.m_inlineBuffer )
            {
              WindowsDeleteStringBuffer(xbfUriBuilder.m_hPreallocatedBuffer);
              xbfUriBuilder.m_hPreallocatedBuffer = 0;
            }
            xbfUriBuilder.m_pBuffer = 0;
            xencoded_string_ptr::Reset((xruntime_string_ptr *)&strPhysicalUri);
            xencoded_string_ptr::Reset((xruntime_string_ptr *)&strScheme);
            if ( v6 )
              v6->Release(v6);
            v69 = spResourceManager.m_ptr;
            if ( spResourceManager.m_ptr )
            {
              spResourceManager.m_ptr = 0;
              v69->Release(v69);
            }
            v70 = spXbfResource.m_ptr;
            if ( spXbfResource.m_ptr )
            {
              spXbfResource.m_ptr = 0;
              v70->Release(v70);
            }
          }
          else
          {
            v34 = spResourceManager.m_ptr;
            TryGetLocalResource = spResourceManager.m_ptr->TryGetLocalResource;
            v36 = spXbfResource.m_ptr;
            if ( spXbfResource.m_ptr )
            {
              spXbfResource.m_ptr = 0;
              v36->Release(v36);
            }
            v37 = TryGetLocalResource(v34, v6, &spXbfResource.m_ptr);
            v23 = v37;
            if ( v37 < 0 )
            {
              OnFailure_2990_(v37);
              if ( xbfUriBuilder.m_pBuffer != xbfUriBuilder.m_inlineBuffer )
              {
                WindowsDeleteStringBuffer(xbfUriBuilder.m_hPreallocatedBuffer);
                xbfUriBuilder.m_hPreallocatedBuffer = 0;
              }
              xbfUriBuilder.m_pBuffer = 0;
              xencoded_string_ptr::Reset((xruntime_string_ptr *)&strPhysicalUri);
              xencoded_string_ptr::Reset((xruntime_string_ptr *)&strScheme);
              if ( v6 )
                v6->Release(v6);
              v59 = spResourceManager.m_ptr;
              if ( spResourceManager.m_ptr )
              {
                spResourceManager.m_ptr = 0;
                v59->Release(v59);
              }
              v60 = spXbfResource.m_ptr;
              if ( spXbfResource.m_ptr )
              {
                spXbfResource.m_ptr = 0;
                v60->Release(v60);
              }
            }
            else
            {
              if ( !spXbfResource.m_ptr )
                goto LABEL_40;
              v38 = spXbfResource.m_ptr->GetPhysicalResourceUriNoRef(spXbfResource.m_ptr);
              v39 = v38->GetCanonical(v38, &strPhysicalUri);
              v23 = v39;
              if ( v39 >= 0 )
                goto LABEL_40;
              OnFailure_2990_(v39);
              if ( xbfUriBuilder.m_pBuffer != xbfUriBuilder.m_inlineBuffer )
              {
                WindowsDeleteStringBuffer(xbfUriBuilder.m_hPreallocatedBuffer);
                xbfUriBuilder.m_hPreallocatedBuffer = 0;
              }
              xbfUriBuilder.m_pBuffer = 0;
              xencoded_string_ptr::Reset((xruntime_string_ptr *)&strPhysicalUri);
              xencoded_string_ptr::Reset((xruntime_string_ptr *)&strScheme);
              if ( v6 )
                v6->Release(v6);
              v63 = spResourceManager.m_ptr;
              if ( spResourceManager.m_ptr )
              {
                spResourceManager.m_ptr = 0;
                v63->Release(v63);
              }
              v64 = spXbfResource.m_ptr;
              if ( spXbfResource.m_ptr )
              {
                spXbfResource.m_ptr = 0;
                v64->Release(v64);
              }
            }
          }
          return v23;
        }
        Storage = strScheme.m_encodedStorage.Storage;
      }
      if ( ((unsigned __int8)Storage & 1) != 0 )
      {
        v68 = (HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL);
      }
      else
      {
        v55 = *((_DWORD *)Storage + 2);
        if ( v55 >= 0 )
        {
          v56 = v55 & 0x3FFFFFFF;
LABEL_89:
          if ( v56 != 11
            || (v79.first._Ptr = (std::_List_node<std::pair<xstring_ptr const ,xref_ptr<IPALResource> >,void *> *)&xstring_ptr_constants::c_xstring_ptr_storage_null,
                *(_QWORD *)&v79.second = L"ms-resource",
                v80 = 1073741835,
                xencoded_string_ptr::Reset((xruntime_string_ptr *)&v79),
                v79.first._Ptr = (std::_List_node<std::pair<xstring_ptr const ,xref_ptr<IPALResource> >,void *> *)&v79.second,
                xstring_ptr_view::Compare(&strScheme, (const xstring_ptr_view *)&v79, xstrCompareCaseInsensitive)) )
          {
LABEL_40:
            if ( xbfUriBuilder.m_pBuffer != xbfUriBuilder.m_inlineBuffer )
              WindowsDeleteStringBuffer(xbfUriBuilder.m_hPreallocatedBuffer);
            goto LABEL_42;
          }
          goto LABEL_32;
        }
        v68 = (HSTRING)Storage->Buffer;
      }
      v56 = WindowsGetStringLen(v68);
      goto LABEL_89;
    }
    OnFailure_2990_(v19);
  }
  OnFailure_2990_(v20);
  if ( xbfUriBuilder.m_pBuffer != xbfUriBuilder.m_inlineBuffer )
  {
    WindowsDeleteStringBuffer(xbfUriBuilder.m_hPreallocatedBuffer);
    xbfUriBuilder.m_hPreallocatedBuffer = 0;
  }
  xbfUriBuilder.m_pBuffer = 0;
  xencoded_string_ptr::Reset((xruntime_string_ptr *)&strPhysicalUri);
  xencoded_string_ptr::Reset((xruntime_string_ptr *)&strScheme);
  v57 = spResourceManager.m_ptr;
  if ( spResourceManager.m_ptr )
  {
    spResourceManager.m_ptr = 0;
    v57->Release(v57);
  }
  v58 = spXbfResource.m_ptr;
  if ( spXbfResource.m_ptr )
  {
    spXbfResource.m_ptr = 0;
    v58->Release(v58);
  }
  return v20;
}

```

## disassembly

```asm
0x18008f0b8  mov     [rsp-8+arg_18], rbx
0x18008f0bd  push    rbp
0x18008f0be  push    rsi
0x18008f0bf  push    rdi
0x18008f0c0  push    r12
0x18008f0c2  push    r13
0x18008f0c4  push    r14
0x18008f0c6  push    r15
0x18008f0c8  lea     rbp, [rsp-70h]
0x18008f0cd  sub     rsp, 170h
0x18008f0d4  mov     rax, cs:__security_cookie
0x18008f0db  xor     rax, rsp
0x18008f0de  mov     [rbp+0A0h+var_40], rax
0x18008f0e2  mov     r15, spXbfResourceOut
0x18008f0e5  mov     r12, strUri
0x18008f0e8  mov     r13, this
0x18008f0eb  xor     esi, esi
0x18008f0ed  mov     [rsp+1A0h+spXbfResource.m_ptr], rsi
0x18008f0f2  mov     [rsp+1A0h+spResourceManager.m_ptr], rsi
0x18008f0f7  mov     edi, esi
0x18008f0f9  mov     [rsp+1A0h+pXbfUri.m_ptr], rsi
0x18008f0fe  lea     rax, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x18008f105  mov     qword ptr [rsp+1A0h+strScheme.m_encodedStorage.___u0], rax
0x18008f10a  mov     qword ptr [rsp+1A0h+strPhysicalUri.m_encodedStorage.___u0], rax
0x18008f10f  mov     [rsp+1A0h+var_178], sil
0x18008f114  mov     this, [spXbfResourceOut]
0x18008f117  test    this, this
0x18008f11a  jnz     loc_18008FB96
0x18008f120  mov     this, r12; this
0x18008f123  call    ?GetHash@xstring_ptr_view@@QEBA_KXZ; xstring_ptr_view::GetHash(void)
0x18008f128  mov     this, [r13+38h]
0x18008f12c  and     this, rax
0x18008f12f  add     this, this
0x18008f132  mov     rax, [r13+20h]
0x18008f136  mov     rbx, [rax+this*8+8]
0x18008f13b  cmp     rbx, [r13+10h]
0x18008f13f  jz      loc_18008F516
0x18008f145  mov     rsi, [rax+this*8]
0x18008f149  lea     strUri, [rbx+10h]; strSource
0x18008f14d  mov     this, r12; this
0x18008f150  call    ??8xstring_ptr_view@@QEBA_NAEBV0@@Z; xstring_ptr_view::operator==(xstring_ptr_view const &)
0x18008f155  test    al, al
0x18008f157  jz      loc_18008F50B
0x18008f15d  xor     esi, esi
0x18008f15f  test    rbx, rbx
0x18008f162  jz      loc_18008F51E
0x18008f168  cmp     rbx, [r13+10h]
0x18008f16c  jnz     loc_18008F4D9
0x18008f172  mov     this, r12; this
0x18008f175  call    ?GetCount@xstring_ptr_view@@QEBAIXZ; xstring_ptr_view::GetCount(void)
0x18008f17a  test    eax, eax
0x18008f17c  jz      loc_18008F417
0x18008f182  mov     [rsp+1A0h+length], esi
0x18008f186  mov     this, [r12]
0x18008f18a  test    cl, 1
0x18008f18d  jnz     loc_18008F884
0x18008f193  mov     eax, [this+8]
0x18008f196  mov     spXbfResourceOut, [this]
0x18008f199  test    eax, eax
0x18008f19b  js      loc_18008FB76
0x18008f1a1  and     eax, 3FFFFFFFh
0x18008f1a6  mov     [rsp+1A0h+length], eax
0x18008f1aa  test    eax, eax
0x18008f1ac  jz      loc_18008F94C
0x18008f1b2  dec     eax
0x18008f1b4  lea     rbx, [spXbfResourceOut+rax*2]
0x18008f1b8  cmp     word ptr [rbx], 2Eh ; '.'
0x18008f1bc  jz      short loc_18008F1CD
0x18008f1be  cmp     rbx, spXbfResourceOut
0x18008f1c1  jz      loc_18008F94C
0x18008f1c7  sub     rbx, 2
0x18008f1cb  jmp     short loc_18008F1B8
0x18008f1cd  sub     rbx, spXbfResourceOut
0x18008f1d0  sar     rbx, 1
0x18008f1d3  cmp     ebx, 0FFFFFFFFh
0x18008f1d6  jz      loc_18008F94C
0x18008f1dc  lea     rax, [rbp+0A0h+xbfUriBuilder.m_inlineBuffer]
0x18008f1e0  mov     [rbp+0A0h+xbfUriBuilder.m_pBuffer], rax
0x18008f1e4  mov     [rbp+0A0h+xbfUriBuilder.m_hPreallocatedBuffer], rsi
0x18008f1e8  mov     qword ptr [rbp+0A0h+xbfUriBuilder.m_cBuffer], 60h ; '`'
0x18008f1f0  lea     ecx, [rbx+4]; failedFrameHR
0x18008f1f3  cmp     ecx, 7FFFFF9Fh
0x18008f1f9  jnb     loc_18008F76A
0x18008f1ff  lea     esi, [this+1]
0x18008f202  cmp     esi, 60h ; '`'
0x18008f205  jbe     short loc_18008F222
0x18008f207  lea     spXbfResourceOut, [rbp+0A0h+xbfUriBuilder.m_hPreallocatedBuffer]; bufferHandle
0x18008f20b  lea     strUri, [rbp+0A0h+xbfUriBuilder]; charBuffer
0x18008f20f  call    cs:__imp_WindowsPreallocateStringBuffer
0x18008f215  mov     edi, eax
0x18008f217  test    eax, eax
0x18008f219  js      loc_18008FADA
0x18008f21f  mov     [rbp+0A0h+xbfUriBuilder.m_cBuffer], esi
0x18008f222  xor     esi, esi
0x18008f224  mov     [rbp+0A0h+xbfUriBuilder.m_cActual], esi
0x18008f227  mov     this, r12; this
0x18008f22a  call    ?GetBuffer@xstring_ptr_view@@QEBAPEBGXZ; xstring_ptr_view::GetBuffer(void)
0x18008f22f  mov     strUri, rax; pBuffer
0x18008f232  mov     r8d, ebx; cBuffer
0x18008f235  lea     this, [rbp+0A0h+xbfUriBuilder]; this
0x18008f239  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJPEBGI@Z; TStringBuilder<96>::Append(ushort const *,uint)
0x18008f23e  mov     ebx, eax
0x18008f240  test    eax, eax
0x18008f242  js      loc_18008FBB2
0x18008f248  lea     edx, [rsi+4]; uNumberOfCharsToBeAdded
0x18008f24b  lea     this, [rbp+0A0h+xbfUriBuilder]; this
0x18008f24f  call    ?EnsureBufferForAdding@?$TStringBuilder@$0GA@@@AEAAJI@Z; TStringBuilder<96>::EnsureBufferForAdding(uint)
0x18008f254  mov     ebx, eax
0x18008f256  test    eax, eax
0x18008f258  js      loc_18008F95B
0x18008f25e  mov     ecx, [rbp+0A0h+xbfUriBuilder.m_cActual]
0x18008f261  mov     strUri, 6600620078002Eh
0x18008f26b  mov     rax, [rbp+0A0h+xbfUriBuilder.m_pBuffer]
0x18008f26f  mov     [rax+this*2], strUri
0x18008f273  mov     eax, [rbp+0A0h+xbfUriBuilder.m_cActual]
0x18008f276  add     eax, 4
0x18008f279  mov     [rbp+0A0h+xbfUriBuilder.m_cActual], eax
0x18008f27c  mov     edx, eax
0x18008f27e  mov     rax, [rbp+0A0h+xbfUriBuilder.m_pBuffer]
0x18008f282  mov     [rax+strUri*2], si
0x18008f286  lea     spXbfResourceOut, [rsp+1A0h+pXbfUri]; ppUri
0x18008f28b  mov     strUri, [rbp+0A0h+xbfUriBuilder.m_pBuffer]; pString
0x18008f28f  mov     ecx, [rbp+0A0h+xbfUriBuilder.m_cActual]; cString
0x18008f292  call    ?Create@CWinUriFactory@@SAJIPEBGPEAPEAUIPALUri@@@Z; CWinUriFactory::Create(uint,ushort const *,IPALUri * *)
0x18008f297  mov     ebx, eax
0x18008f299  test    eax, eax
0x18008f29b  js      loc_18008FAE8
0x18008f2a1  lea     spXbfResourceOut, [rsp+1A0h+strScheme]; pstrValue
0x18008f2a6  lea     strUri, ??_9IScenePbrMaterial@Scenes@Composition@UI@Windows@@$BGI@AA; pMemberGetter
0x18008f2ad  mov     rdi, [rsp+1A0h+pXbfUri.m_ptr]
0x18008f2b2  mov     this, rdi; pUri
0x18008f2b5  call    ??$GetUriPart@P8IPALUri@@EBAJPEAIPEAG@Z@UriXStringGetters_Internal@@YAJPEBUIPALUri@@P81@EBAJPEAIPEAG@ZPEAVxstring_ptr@@@Z; UriXStringGetters_Internal::GetUriPart<long (IPALUri::*)(uint *,ushort *)>(IPALUri const *,long (IPALUri::*)(uint *,ushort *),xstring_ptr *)
0x18008f2ba  mov     ebx, eax
0x18008f2bc  test    eax, eax
0x18008f2be  js      loc_18008F9B0
0x18008f2c4  mov     rbx, qword ptr [rsp+1A0h+strScheme.m_encodedStorage.___u0]
0x18008f2c9  test    bl, 1
0x18008f2cc  jnz     loc_18008F89F
0x18008f2d2  mov     eax, [rbx+8]
0x18008f2d5  test    eax, eax
0x18008f2d7  js      loc_18008FB7E
0x18008f2dd  and     eax, 3FFFFFFFh
0x18008f2e2  cmp     eax, 7
0x18008f2e5  jnz     loc_18008F6D7
0x18008f2eb  lea     rax, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x18008f2f2  mov     qword ptr [rsp+1A0h+var_150.m_encodedStorage.___u0], rax
0x18008f2f7  lea     rax, aMsAppx_0; "ms-appx"
0x18008f2fe  mov     [rsp+1A0h+var_148], rax
0x18008f303  mov     [rsp+1A0h+var_140], 40000007h
0x18008f30b  lea     this, [rsp+1A0h+var_150]; this
0x18008f310  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18008f315  lea     rax, [rsp+1A0h+var_148]
0x18008f31a  mov     qword ptr [rsp+1A0h+var_150.m_encodedStorage.___u0], rax
0x18008f31f  mov     r8d, 1; eCompareBehavior
0x18008f325  lea     strUri, [rsp+1A0h+var_150]; other
0x18008f32a  lea     this, [rsp+1A0h+strScheme]; this
0x18008f32f  call    ?Compare@xstring_ptr_view@@QEBAHAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::Compare(xstring_ptr_view const &,xstrCompareBehavior)
0x18008f334  test    eax, eax
0x18008f336  jnz     loc_18008F6D2
0x18008f33c  mov     rbx, [r13+0]
0x18008f340  mov     rax, [rbx]
0x18008f343  mov     rsi, [rax+10h]
0x18008f347  mov     this, [rsp+1A0h+spResourceManager.m_ptr]
0x18008f34c  test    this, this
0x18008f34f  jz      short loc_18008F366
0x18008f351  mov     [rsp+1A0h+spResourceManager.m_ptr], 0
0x18008f35a  mov     strUri, [this]
0x18008f35d  mov     rax, [strUri+8]
0x18008f361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f366  lea     strUri, [rsp+1A0h+spResourceManager]
0x18008f36b  mov     this, rbx
0x18008f36e  mov     rax, rsi
0x18008f371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f376  mov     ebx, eax
0x18008f378  xor     esi, esi
0x18008f37a  test    eax, eax
0x18008f37c  js      loc_18008FA4E
0x18008f382  mov     rbx, [rsp+1A0h+spResourceManager.m_ptr]
0x18008f387  mov     rax, [rbx]
0x18008f38a  mov     rsi, [rax+20h]
0x18008f38e  mov     this, [rsp+1A0h+spXbfResource.m_ptr]
0x18008f393  test    this, this
0x18008f396  jz      short loc_18008F3AD
0x18008f398  mov     [rsp+1A0h+spXbfResource.m_ptr], 0
0x18008f3a1  mov     strUri, [this]
0x18008f3a4  mov     rax, [strUri+8]
0x18008f3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f3ad  lea     spXbfResourceOut, [rsp+1A0h+spXbfResource]
0x18008f3b2  mov     strUri, rdi
0x18008f3b5  mov     this, rbx
0x18008f3b8  mov     rax, rsi
0x18008f3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f3c0  mov     ebx, eax
0x18008f3c2  xor     esi, esi
0x18008f3c4  test    eax, eax
0x18008f3c6  js      loc_18008F7F6
0x18008f3cc  mov     this, [rsp+1A0h+spXbfResource.m_ptr]
0x18008f3d1  test    this, this
0x18008f3d4  jz      short loc_18008F403
0x18008f3d6  mov     rax, [this]
0x18008f3d9  mov     rax, [rax+28h]
0x18008f3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f3e2  mov     spXbfResourceOut, rax
0x18008f3e5  mov     this, [rax]
0x18008f3e8  mov     rax, [this+30h]
0x18008f3ec  lea     strUri, [rsp+1A0h+strPhysicalUri]
0x18008f3f1  mov     this, spXbfResourceOut
0x18008f3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f3f9  mov     ebx, eax
0x18008f3fb  test    eax, eax
0x18008f3fd  js      loc_18008F8B1
0x18008f403  lea     rax, [rbp+0A0h+xbfUriBuilder.m_inlineBuffer]
0x18008f407  cmp     [rbp+0A0h+xbfUriBuilder.m_pBuffer], rax
0x18008f40b  jz      short loc_18008F417
0x18008f40d  mov     this, [rbp+0A0h+xbfUriBuilder.m_hPreallocatedBuffer]; bufferHandle
0x18008f411  call    cs:__imp_WindowsDeleteStringBuffer
0x18008f417  mov     this, qword ptr [rsp+1A0h+strPhysicalUri.m_encodedStorage.___u0]
0x18008f41c  test    cl, 1
0x18008f41f  jnz     loc_18008F93D
0x18008f425  mov     eax, [this+8]
0x18008f428  test    eax, eax
0x18008f42a  js      loc_18008FB86
0x18008f430  and     eax, 3FFFFFFFh
0x18008f435  test    eax, eax
0x18008f437  jz      loc_18008F571
0x18008f43d  lea     this, [rsp+1A0h+strPhysicalUri]; this
0x18008f442  call    ?GetHash@xstring_ptr_view@@QEBA_KXZ; xstring_ptr_view::GetHash(void)
0x18008f447  and     rax, [r13+38h]
0x18008f44b  add     rax, rax
0x18008f44e  mov     this, [r13+20h]
0x18008f452  mov     rbx, [this+rax*8+8]
0x18008f457  cmp     rbx, [r13+10h]
0x18008f45b  jz      loc_18008F6CA
0x18008f461  mov     rsi, [this+rax*8]
0x18008f465  lea     strUri, [rbx+10h]; strSource
0x18008f469  lea     this, [rsp+1A0h+strPhysicalUri]; this
0x18008f46e  call    ??8xstring_ptr_view@@QEBA_NAEBV0@@Z; xstring_ptr_view::operator==(xstring_ptr_view const &)
0x18008f473  test    al, al
0x18008f475  jz      loc_18008F6BF
0x18008f47b  xor     esi, esi
0x18008f47d  test    rbx, rbx
0x18008f480  jz      loc_18008F74F
0x18008f486  cmp     rbx, [r13+10h]
0x18008f48a  jnz     loc_18008F527
0x18008f490  lea     strUri, [rsp+1A0h+strPhysicalUri]; other
0x18008f495  lea     this, [rsp+1A0h+var_130]; this
0x18008f49a  call    ??0xstring_ptr@@QEAA@AEBV0@@Z; xstring_ptr::xstring_ptr(xstring_ptr const &)
0x18008f49f  nop
0x18008f4a0  mov     rax, [rsp+1A0h+spXbfResource.m_ptr]
0x18008f4a5  mov     [rsp+1A0h+var_128.m_ptr], rax
0x18008f4aa  lea     this, [rsp+1A0h+var_128]; this
0x18008f4af  call    ?IncrementRefCount@?$xref_ptr@VHWTexture@@@@AEAAXXZ; xref_ptr<HWTexture>::IncrementRefCount(void)
0x18008f4b4  nop
0x18008f4b5  lea     spXbfResourceOut, [rsp+1A0h+var_130]; <_Vals_0>
0x18008f4ba  lea     strUri, [rsp+1A0h+var_150]; result
0x18008f4bf  lea     this, [r13+8]; this
0x18008f4c3  call    ??$emplace@U?$pair@$$CBVxstring_ptr@@V?$xref_ptr@UIPALResource@@@@@std@@@?$_Hash@V?$_Umap_traits@Vxstring_ptr@@V?$xref_ptr@UIPALResource@@@@V?$_Uhash_compare@Vxstring_ptr@@U?$hash@Vxstring_ptr@@@std@@U?$equal_to@Vxstring_ptr@@@3@@std@@V?$allocator@U?$pair@$$CBVxstring_ptr@@V?$xref_ptr@UIPALResource@@@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVxstring_ptr@@V?$xref_ptr@UIPALResource@@@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBVxstring_ptr@@V?$xref_ptr@UIPALResource@@@@@1@@Z; std::_Hash<std::_Umap_traits<xstring_ptr,xref_ptr<IPALResource>,std::_Uhash_compare<xstring_ptr,std::hash<xstring_ptr>,std::equal_to<xstring_ptr>>,std::allocator<std::pair<xstring_ptr const,xref_ptr<IPALResource>>>,0>>::emplace<std::pair<xstring_ptr const,xref_ptr<IPALResource>>>(std::pair<xstring_ptr const,xref_ptr<IPALResource>> &&)
0x18008f4c8  nop
0x18008f4c9  lea     this, [rsp+1A0h+var_128]; this
0x18008f4ce  call    ?DecrementRefCount@?$xref_ptr@VINameScope@@@@AEAAXXZ; xref_ptr<INameScope>::DecrementRefCount(void)
0x18008f4d3  nop
0x18008f4d4  jmp     loc_18008F5B3
0x18008f4d9  lea     rax, [rbx+18h]
0x18008f4dd  lea     this, [rsp+1A0h+spXbfResource]
0x18008f4e2  cmp     this, rax
0x18008f4e5  jz      loc_18008F56B
0x18008f4eb  mov     this, [rsp+1A0h+spXbfResource.m_ptr]
0x18008f4f0  mov     rax, [rax]
0x18008f4f3  mov     [rsp+1A0h+spXbfResource.m_ptr], rax
0x18008f4f8  test    this, this
0x18008f4fb  jz      short loc_18008F561
0x18008f4fd  mov     rax, [this]
0x18008f500  mov     rax, [rax+8]
0x18008f504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f509  jmp     short loc_18008F561
0x18008f50b  cmp     rbx, rsi
0x18008f50e  jnz     loc_18008F6B6
0x18008f514  xor     esi, esi
0x18008f516  mov     rbx, rsi
0x18008f519  jmp     loc_18008F15F
0x18008f51e  mov     rbx, [r13+10h]
0x18008f522  jmp     loc_18008F168
0x18008f527  mov     this, [rsp+1A0h+spXbfResource.m_ptr]
0x18008f52c  test    this, this
0x18008f52f  jz      short loc_18008F542
0x18008f531  mov     [rsp+1A0h+spXbfResource.m_ptr], rsi
0x18008f536  mov     rax, [this]
0x18008f539  mov     rax, [rax+8]
0x18008f53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f542  mov     [rsp+1A0h+spXbfResource.m_ptr], rsi
0x18008f547  lea     rax, [rbx+18h]
0x18008f54b  lea     this, [rsp+1A0h+spXbfResource]
0x18008f550  cmp     this, rax
0x18008f553  jz      loc_18008F619
0x18008f559  mov     rax, [rax]
0x18008f55c  mov     [rsp+1A0h+spXbfResource.m_ptr], rax
0x18008f561  lea     this, [rsp+1A0h+spXbfResource]; this
0x18008f566  call    ?IncrementRefCount@?$xref_ptr@VHWTexture@@@@AEAAXXZ; xref_ptr<HWTexture>::IncrementRefCount(void)
0x18008f56b  mov     cl, [rsp+1A0h+var_178]
0x18008f56f  jmp     short loc_18008F5BF
  ... truncated ...
```
