# ModernResourceProvider::GetPropertyBag(IPALUri const *,xpairlist<xstring_ptr,xstring_ptr> * *)

- ea: `0x1801e0a40`
- end: `0x1801e1244`
- name: `?GetPropertyBag@ModernResourceProvider@@UEAAJPEBUIPALUri@@PEAPEAV?$xpairlist@Vxstring_ptr@@V1@@@@Z`
- size: `2052`
- prototype: `HRESULT __fastcall(ModernResourceProvider *this, const IPALUri *pUri, xpairlist<xstring_ptr,xstring_ptr> **ppPropertyBag)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004bc0`
- `0x18007a328`
- `0x180091d20`
- `0x1800aabf0`
- `0x1800c039c`
- `0x1800c0bc8`
- `0x1800fe130`
- `0x180131190`
- `0x18017233c`
- `0x180172850`
- `0x1801800b8`
- `0x1801e0a40`
- `0x1801e2980`
- `0x1801eb6f4`
- `0x1806c1dc0`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e0fa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e0fc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e0fe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e0fa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e0fc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e0fe9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e0daa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e0db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e0e52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e0e5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e0daa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e0db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e0e52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e0e5c`

## string_xrefs

- `0x1801e10c6`: `GetPropertyBag: GetMainResourceMap failed for resource URI %s`
- `0x1801e1192`: `GetPropertyBag: Failed to resolve resource URI %s`
- `0x1801e1136`: `GetPropertyBag: GetResourceMap (%s) failed for resource URI %s`

## pseudocode

```c
__int64 __fastcall ModernResourceProvider::GetPropertyBag(
        ModernResourceProvider *this,
        IPALUri *pUri,
        xpairlist<xstring_ptr,xstring_ptr> **ppPropertyBag)
{
  xpairlist<xstring_ptr,xstring_ptr> **v3; // r15
  HRESULT IsValid; // eax
  HRESULT v7; // ebx
  HRESULT v8; // ecx
  HRESULT v9; // eax
  const xstring_ptr_storage *Storage; // rbx
  int v11; // eax
  HSTRING StringRawBuffer; // rcx
  char v13; // al
  IMrtResourceManager *m_pResourceManager; // rsi
  IMrtResourceManager_vtbl *v15; // r9
  HRESULT (__fastcall *GetResourceMap)(IMrtResourceManager *, const wchar_t *, const _GUID *, void **); // r14
  PCWSTR Buffer; // rax
  xpairlist<xstring_ptr,xstring_ptr> *FailFast; // rax
  xpairlist<xstring_ptr,xstring_ptr> *v19; // r14
  HRESULT (__fastcall *GetSubtree)(IResourceMap *, const wchar_t *, IResourceMap **); // rsi
  const wchar_t *v21; // rax
  HRESULT v22; // eax
  unsigned int i; // esi
  HRESULT v24; // eax
  unsigned int v25; // eax
  HRESULT v26; // eax
  unsigned int v27; // eax
  _xlist_node<std::pair<xstring_ptr,xstring_ptr> > *m_tail; // r15
  xstring_ptr *v29; // rax
  xstring_ptr *v30; // rdi
  void (__fastcall *v31)(xlist<std::pair<xstring_ptr,unsigned int> > *, _xlist_node<std::pair<xstring_ptr,unsigned int> > *); // rax
  HSTRING v33; // rcx
  HSTRING v34; // rcx
  IPlatformServices *v35; // r14
  HRESULT (*v36)(struct IPlatformServices *, XDebugTraceType, const wchar_t *, ...); // r15
  const wchar_t *v37; // rdi
  IPlatformServices *m_pTarget; // r14
  HRESULT (*DebugTrace)(struct IPlatformServices *, XDebugTraceType, const wchar_t *, ...); // r15
  const wchar_t *v40; // rdi
  const wchar_t *v41; // rax
  IPlatformServices *v42; // r15
  HRESULT (*v43)(struct IPlatformServices *, XDebugTraceType, const wchar_t *, ...); // r12
  const wchar_t *v44; // rdi
  IPlatformServices *v45; // rsi
  unsigned int v46; // r15d
  HRESULT (*v47)(struct IPlatformServices *, XDebugTraceType, const wchar_t *, ...); // r12
  const wchar_t *v48; // rdi
  unsigned int *pHadFilePath; // [rsp+20h] [rbp-69h]
  xstring_ptr strCanonicalUri; // [rsp+30h] [rbp-59h] BYREF
  xstring_ptr strPropertyName; // [rsp+38h] [rbp-51h] BYREF
  unsigned int resourceCount; // [rsp+40h] [rbp-49h] BYREF
  wchar_t *pszPropertyUri; // [rsp+48h] [rbp-41h] BYREF
  wchar_t *pszPropertyValue; // [rsp+50h] [rbp-39h] BYREF
  IResourceMap *pCurrentResourceMap; // [rsp+58h] [rbp-31h] BYREF
  IResourceMap *pElementMap; // [rsp+60h] [rbp-29h] BYREF
  INamedResource *pNamedResource; // [rsp+68h] [rbp-21h] BYREF
  IResourceCandidate *pResourceCandidate; // [rsp+70h] [rbp-19h] BYREF
  xstring_ptr strPropertyBagPath; // [rsp+78h] [rbp-11h] BYREF
  xstring_ptr strResourceMapName; // [rsp+80h] [rbp-9h] BYREF
  xephemeral_string_ptr strPropertyUri; // [rsp+88h] [rbp-1h] BYREF
  xstring_ptr other; // [rsp+A0h] [rbp+17h] BYREF
  xstring_ptr v63; // [rsp+A8h] [rbp+1Fh] BYREF
  xstring_ptr strPropertyValue; // [rsp+108h] [rbp+7Fh] BYREF

  strResourceMapName.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  v3 = ppPropertyBag;
  strPropertyBagPath.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  pCurrentResourceMap = 0;
  pElementMap = 0;
  pNamedResource = 0;
  pResourceCandidate = 0;
  resourceCount = 0;
  pszPropertyUri = 0;
  pszPropertyValue = 0;
  LODWORD(strPropertyValue.m_encodedStorage.Storage) = 0;
  strCanonicalUri.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  IsValid = ModernResourceProvider::EnsureContextIsValid(this);
  v7 = IsValid;
  if ( IsValid < 0
    || (IsValid = MsUriHelpers::IsMsResourceUri(pUri, (unsigned int *)&strPropertyValue), v7 = IsValid, IsValid < 0) )
  {
    OnFailure_2990_(IsValid);
    goto $Cleanup_1109;
  }
  if ( !LODWORD(strPropertyValue.m_encodedStorage.Storage) )
  {
    v7 = -2147024809;
    OnFailure_1169_(v8);
    goto $Cleanup_1109;
  }
  v9 = MsUriHelpers::CrackMsResourceUri(pUri, &strResourceMapName, &strPropertyBagPath, 0, 0);
  v7 = v9;
  if ( v9 < 0 )
  {
    OnFailure_2990_(v9);
    goto $Cleanup_1109;
  }
  Storage = strResourceMapName.m_encodedStorage.Storage;
  LODWORD(strPropertyValue.m_encodedStorage.Storage) = 0;
  if ( ((__int64)strResourceMapName.m_encodedStorage.Storage & 1) != 0 )
  {
    StringRawBuffer = (HSTRING)(strResourceMapName.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_65;
  }
  v11 = *((_DWORD *)strResourceMapName.m_encodedStorage.Storage + 2);
  StringRawBuffer = *(HSTRING *)strResourceMapName.m_encodedStorage.Handle;
  if ( v11 < 0 )
  {
LABEL_65:
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(StringRawBuffer, (UINT32 *)&strPropertyValue);
    goto LABEL_8;
  }
  LODWORD(strPropertyValue.m_encodedStorage.Storage) = v11 & 0x3FFFFFFF;
LABEL_8:
  if ( !StringRawBuffer || !LODWORD(strPropertyValue.m_encodedStorage.Storage) || (v13 = 0, !*(_WORD *)StringRawBuffer) )
    v13 = 1;
  m_pResourceManager = this->m_pResourceManager;
  v15 = m_pResourceManager->__vftable;
  if ( !v13 )
  {
    GetResourceMap = v15->GetResourceMap;
    if ( ((unsigned __int8)Storage & 1) != 0 )
    {
      v34 = (HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL);
    }
    else
    {
      if ( *((int *)Storage + 2) >= 0 )
      {
        Buffer = Storage->Buffer;
LABEL_15:
        v7 = GetResourceMap(m_pResourceManager, Buffer, &IID_IResourceMap, (void **)&pCurrentResourceMap);
        if ( v7 >= 0 )
          goto LABEL_16;
        if ( gps.m_pTarget->IsDebugTraceTypeActive(gps.m_pTarget, XCP_TRACE_RESOURCELOADING|XCP_TRACE_ERROR) )
        {
          pUri->GetCanonical(pUri, &strCanonicalUri);
          m_pTarget = gps.m_pTarget;
          DebugTrace = gps.m_pTarget->DebugTrace;
          if ( xencoded_string_ptr::IsNull(&strCanonicalUri.m_encodedStorage) )
            v40 = L"NULL";
          else
            v40 = xstring_ptr_view::GetBuffer(&strCanonicalUri);
          v41 = xstring_ptr_view::GetBuffer(&strResourceMapName);
          DebugTrace(
            m_pTarget,
            XCP_TRACE_RESOURCELOADING|XCP_TRACE_ERROR,
            L"GetPropertyBag: GetResourceMap (%s) failed for resource URI %s",
            v41,
            v40);
        }
LABEL_55:
        OnFailure_2990_(v7);
        goto $Cleanup_1109;
      }
      v34 = (HSTRING)Storage->Buffer;
    }
    Buffer = WindowsGetStringRawBuffer(v34, 0);
    goto LABEL_15;
  }
  v7 = v15->GetMainResourceMap(this->m_pResourceManager, &IID_IResourceMap, (void **)&pCurrentResourceMap);
  if ( v7 < 0 )
  {
    if ( gps.m_pTarget->IsDebugTraceTypeActive(gps.m_pTarget, XCP_TRACE_RESOURCELOADING|XCP_TRACE_ERROR) )
    {
      pUri->GetCanonical(pUri, &strCanonicalUri);
      v35 = gps.m_pTarget;
      v36 = gps.m_pTarget->DebugTrace;
      if ( xencoded_string_ptr::IsNull(&strCanonicalUri.m_encodedStorage) )
        v37 = L"NULL";
      else
        v37 = xstring_ptr_view::GetBuffer(&strCanonicalUri);
      v36(
        v35,
        XCP_TRACE_RESOURCELOADING|XCP_TRACE_ERROR,
        L"GetPropertyBag: GetMainResourceMap failed for resource URI %s",
        v37);
    }
    goto LABEL_55;
  }
LABEL_16:
  FailFast = (xpairlist<xstring_ptr,xstring_ptr> *)XcpAllocation::OSMemoryAllocateFailFast(0x18u);
  v19 = FailFast;
  if ( FailFast )
  {
    FailFast->m_head = 0;
    FailFast->m_tail = 0;
    FailFast->m_size = 0;
  }
  else
  {
    v19 = 0;
  }
  GetSubtree = pCurrentResourceMap->GetSubtree;
  if ( ((__int64)strPropertyBagPath.m_encodedStorage.Storage & 1) != 0 )
  {
    v33 = (HSTRING)(strPropertyBagPath.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    if ( *((int *)strPropertyBagPath.m_encodedStorage.Storage + 2) >= 0 )
    {
      v21 = strPropertyBagPath.m_encodedStorage.Storage->Buffer;
      goto LABEL_21;
    }
    v33 = *(HSTRING *)strPropertyBagPath.m_encodedStorage.Handle;
  }
  v21 = WindowsGetStringRawBuffer(v33, 0);
LABEL_21:
  if ( GetSubtree(pCurrentResourceMap, v21, &pElementMap) < 0 )
  {
    if ( gps.m_pTarget->IsDebugTraceTypeActive(gps.m_pTarget, XCP_TRACE_RESOURCELOADING|XCP_TRACE_ERROR) )
    {
      pUri->GetCanonical(pUri, &strCanonicalUri);
      v42 = gps.m_pTarget;
      v43 = gps.m_pTarget->DebugTrace;
      if ( xencoded_string_ptr::IsNull(&strCanonicalUri.m_encodedStorage) )
        v44 = L"NULL";
      else
        v44 = xstring_ptr_view::GetBuffer(&strCanonicalUri);
      v43(v42, XCP_TRACE_RESOURCELOADING|XCP_TRACE_ERROR, L"GetPropertyBag: Failed to resolve resource URI %s", v44);
      v3 = ppPropertyBag;
    }
    *v3 = v19;
  }
  else
  {
    v22 = pElementMap->GetNamedResourceCount(pElementMap, &resourceCount);
    v7 = v22;
    if ( v22 < 0 )
    {
      OnFailure_2990_(v22);
    }
    else
    {
      if ( gps.m_pTarget->IsDebugTraceTypeActive(gps.m_pTarget, XCP_TRACE_RESOURCELOADING|XCP_TRACE_VERBOSE) )
      {
        pUri->GetCanonical(pUri, &strCanonicalUri);
        v45 = gps.m_pTarget;
        v46 = resourceCount;
        v47 = gps.m_pTarget->DebugTrace;
        if ( xencoded_string_ptr::IsNull(&strCanonicalUri.m_encodedStorage) )
          v48 = L"NULL";
        else
          v48 = xstring_ptr_view::GetBuffer(&strCanonicalUri);
        LODWORD(pHadFilePath) = v46;
        v47(v45, XCP_TRACE_RESOURCELOADING|XCP_TRACE_VERBOSE, L"GetPropertyBag: %s -> %d", v48, pHadFilePath);
      }
      for ( i = 0; i < resourceCount; ++i )
      {
        strPropertyName.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
        strPropertyValue.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
        v24 = pElementMap->GetNamedResourceUri(pElementMap, i, &pszPropertyUri);
        v7 = v24;
        if ( v24 < 0
          || (v24 = pElementMap->GetNamedResource(
                      pElementMap,
                      pszPropertyUri,
                      &IID_INamedResource,
                      (void **)&pNamedResource),
              v7 = v24,
              v24 < 0)
          || (v24 = pNamedResource->ResolveForContext(pNamedResource, this->m_pResourceContext, &pResourceCandidate),
              v7 = v24,
              v24 < 0)
          || (v24 = pResourceCandidate->ToString(pResourceCandidate, &pszPropertyValue), v7 = v24, v24 < 0) )
        {
          OnFailure_2990_(v24);
LABEL_43:
          xstring_ptr::~xstring_ptr(&strPropertyValue);
          xstring_ptr::~xstring_ptr(&strPropertyName);
          goto $Cleanup_1109;
        }
        v25 = xstrlen(pszPropertyUri);
        xephemeral_string_ptr::xephemeral_string_ptr(&strPropertyUri, pszPropertyUri, v25);
        v26 = ModernResourceManager_Internal::ExtractPropertyNameFromUri(
                &strPropertyUri,
                &strPropertyBagPath,
                &strPropertyName);
        v7 = v26;
        if ( v26 < 0
          || (v27 = xstrlen(pszPropertyValue),
              v26 = xstring_ptr::CloneBuffer(pszPropertyValue, v27, &strPropertyValue),
              v7 = v26,
              v26 < 0) )
        {
          OnFailure_2990_(v26);
          strPropertyUri.m_ephemeralStorage = xstring_ptr_constants::c_xstring_ptr_storage_null;
          strPropertyUri.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
          goto LABEL_43;
        }
        xstring_ptr::xstring_ptr(&other, &strPropertyName);
        xstring_ptr::xstring_ptr(&v63, &strPropertyValue);
        m_tail = v19->m_tail;
        v29 = (xstring_ptr *)XcpAllocation::OSMemoryAllocateFailFast(0x18u);
        v30 = v29;
        if ( v29 )
        {
          v29->m_encodedStorage.RuntimeStringHandleMarker = 0;
          xstring_ptr::xstring_ptr(v29 + 1, &other);
          xstring_ptr::xstring_ptr(v30 + 2, &v63);
        }
        else
        {
          v30 = 0;
        }
        v31 = xlist<std::pair<CUIElement *,HWCompTreeNode *>>::SetBothEnds;
        if ( m_tail )
          v31 = xlist<std::pair<std::shared_ptr<XamlProperty>,std::shared_ptr<XamlQualifiedObject>>>::AppendToTail;
        v31(
          (xlist<std::pair<xstring_ptr,unsigned int> > *)v19,
          (_xlist_node<std::pair<xstring_ptr,unsigned int> > *)v30);
        ++v19->m_size;
        v7 = 0;
        xstring_ptr::~xstring_ptr(&v63);
        xstring_ptr::~xstring_ptr(&other);
        CoTaskMemFree(pszPropertyUri);
        pszPropertyUri = 0;
        CoTaskMemFree(pszPropertyValue);
        pszPropertyValue = 0;
        if ( pNamedResource )
        {
          pNamedResource->Release(pNamedResource);
          pNamedResource = 0;
        }
        if ( pResourceCandidate )
        {
          pResourceCandidate->Release(pResourceCandidate);
          pResourceCandidate = 0;
        }
        strPropertyUri.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
        strPropertyUri.m_ephemeralStorage = xstring_ptr_constants::c_xstring_ptr_storage_null;
        xstring_ptr::~xstring_ptr(&strPropertyValue);
        xstring_ptr::~xstring_ptr(&strPropertyName);
      }
      *ppPropertyBag = v19;
    }
  }
$Cleanup_1109:
  CoTaskMemFree(pszPropertyUri);
  CoTaskMemFree(pszPropertyValue);
  if ( pCurrentResourceMap )
  {
    pCurrentResourceMap->Release(pCurrentResourceMap);
    pCurrentResourceMap = 0;
  }
  if ( pElementMap )
  {
    pElementMap->Release(pElementMap);
    pElementMap = 0;
  }
  if ( pNamedResource )
  {
    pNamedResource->Release(pNamedResource);
    pNamedResource = 0;
  }
  if ( pResourceCandidate )
  {
    pResourceCandidate->Release(pResourceCandidate);
    pResourceCandidate = 0;
  }
  xstring_ptr::~xstring_ptr(&strCanonicalUri);
  xstring_ptr::~xstring_ptr(&strPropertyBagPath);
  xstring_ptr::~xstring_ptr(&strResourceMapName);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801e0a40  mov     [rsp-8+arg_0], rbx
0x1801e0a45  mov     [rsp-8+arg_10], ppPropertyBag
0x1801e0a4a  push    rbp
0x1801e0a4b  push    rsi
0x1801e0a4c  push    rdi
0x1801e0a4d  push    r12
0x1801e0a4f  push    r13
0x1801e0a51  push    r14
0x1801e0a53  push    r15
0x1801e0a55  lea     rbp, [rsp-27h]
0x1801e0a5a  sub     rsp, 0B0h
0x1801e0a61  xor     r12d, r12d
0x1801e0a64  lea     rax, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1801e0a6b  mov     qword ptr [rbp+57h+strResourceMapName.m_encodedStorage.___u0], rax
0x1801e0a6f  mov     r15, ppPropertyBag
0x1801e0a72  mov     qword ptr [rbp+57h+strPropertyBagPath.m_encodedStorage.___u0], rax
0x1801e0a76  mov     rdi, pUri
0x1801e0a79  mov     [rbp+57h+pCurrentResourceMap], r12
0x1801e0a7d  mov     r13, this
0x1801e0a80  mov     [rbp+57h+pElementMap], r12
0x1801e0a84  mov     [rbp+57h+pNamedResource], r12
0x1801e0a88  mov     [rbp+57h+pResourceCandidate], r12
0x1801e0a8c  mov     [rbp+57h+resourceCount], r12d
0x1801e0a90  mov     [rbp+57h+pszPropertyUri], r12
0x1801e0a94  mov     [rbp+57h+pszPropertyValue], r12
0x1801e0a98  mov     dword ptr [rbp+57h+strPropertyValue.m_encodedStorage.___u0], r12d
0x1801e0a9c  mov     qword ptr [rbp+57h+strCanonicalUri.m_encodedStorage.___u0], rax
0x1801e0aa0  call    ?EnsureContextIsValid@ModernResourceProvider@@AEAAJXZ; ModernResourceProvider::EnsureContextIsValid(void)
0x1801e0aa5  mov     ebx, eax
0x1801e0aa7  test    eax, eax
0x1801e0aa9  js      loc_1801E0FD4
0x1801e0aaf  lea     pUri, [rbp+57h+strPropertyValue]; pResult
0x1801e0ab3  mov     this, rdi; pUri
0x1801e0ab6  call    ?IsMsResourceUri@MsUriHelpers@@YAJPEBUIPALUri@@PEAI@Z; MsUriHelpers::IsMsResourceUri(IPALUri const *,uint *)
0x1801e0abb  mov     ebx, eax
0x1801e0abd  test    eax, eax
0x1801e0abf  js      loc_1801E1238
0x1801e0ac5  cmp     dword ptr [rbp+57h+strPropertyValue.m_encodedStorage.___u0], r12d
0x1801e0ac9  jz      loc_1801E1071
0x1801e0acf  xor     r9d, r9d; pstrFilePath
0x1801e0ad2  mov     [rsp+0E0h+pHadFilePath], r12; pHadFilePath
0x1801e0ad7  lea     ppPropertyBag, [rbp+57h+strPropertyBagPath]; pstrResourcePath
0x1801e0adb  mov     this, rdi; pUri
0x1801e0ade  lea     pUri, [rbp+57h+strResourceMapName]; pstrResourceMap
0x1801e0ae2  call    ?CrackMsResourceUri@MsUriHelpers@@YAJPEBUIPALUri@@PEAVxstring_ptr@@11PEAI@Z; MsUriHelpers::CrackMsResourceUri(IPALUri const *,xstring_ptr *,xstring_ptr *,xstring_ptr *,uint *)
0x1801e0ae7  mov     ebx, eax
0x1801e0ae9  test    eax, eax
0x1801e0aeb  js      loc_1801E0F65
0x1801e0af1  mov     rbx, qword ptr [rbp+57h+strResourceMapName.m_encodedStorage.___u0]
0x1801e0af5  mov     dword ptr [rbp+57h+strPropertyValue.m_encodedStorage.___u0], r12d
0x1801e0af9  test    bl, 1
0x1801e0afc  jnz     loc_1801E0FBB
0x1801e0b02  mov     eax, [rbx+8]
0x1801e0b05  mov     this, [rbx]
0x1801e0b08  test    eax, eax
0x1801e0b0a  js      loc_1801E0FC2
0x1801e0b10  and     eax, 3FFFFFFFh
0x1801e0b15  mov     dword ptr [rbp+57h+strPropertyValue.m_encodedStorage.___u0], eax
0x1801e0b18  test    this, this
0x1801e0b1b  jz      loc_1801E0E2E
0x1801e0b21  cmp     dword ptr [rbp+57h+strPropertyValue.m_encodedStorage.___u0], r12d
0x1801e0b25  jz      loc_1801E0E2E
0x1801e0b2b  mov     al, r12b
0x1801e0b2e  cmp     r12w, [this]
0x1801e0b32  jz      loc_1801E0E2E
0x1801e0b38  mov     rsi, [r13+18h]
0x1801e0b3c  mov     r9, [rsi]
0x1801e0b3f  test    al, al
0x1801e0b41  jnz     loc_1801E0EFE
0x1801e0b47  mov     r14, [r9+40h]
0x1801e0b4b  test    bl, 1
0x1801e0b4e  jnz     loc_1801E0FE0
0x1801e0b54  cmp     [rbx+8], r12d
0x1801e0b58  jl      loc_1801E1046
0x1801e0b5e  mov     rax, [rbx]
0x1801e0b61  mov     pUri, rax
0x1801e0b64  lea     r9, [rbp+57h+pCurrentResourceMap]
0x1801e0b68  mov     rax, r14
0x1801e0b6b  lea     ppPropertyBag, IID_IResourceMap
0x1801e0b72  mov     this, rsi
0x1801e0b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0b7a  mov     ebx, eax
0x1801e0b7c  test    eax, eax
0x1801e0b7e  js      loc_1801E1004
0x1801e0b84  mov     ecx, 18h; cSize
0x1801e0b89  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x1801e0b8e  mov     r14, rax
0x1801e0b91  test    rax, rax
0x1801e0b94  jz      loc_1801E0FF4
0x1801e0b9a  mov     [rax], r12
0x1801e0b9d  mov     [rax+8], r12
0x1801e0ba1  mov     [rax+10h], r12d
0x1801e0ba5  mov     rax, [rbp+57h+pCurrentResourceMap]
0x1801e0ba9  mov     this, [rax]
0x1801e0bac  mov     rax, qword ptr [rbp+57h+strPropertyBagPath.m_encodedStorage.___u0]
0x1801e0bb0  mov     rsi, [this+20h]
0x1801e0bb4  test    al, 1
0x1801e0bb6  jnz     loc_1801E0F9B
0x1801e0bbc  cmp     [rax+8], r12d
0x1801e0bc0  jl      loc_1801E103E
0x1801e0bc6  mov     rax, [rax]
0x1801e0bc9  mov     this, [rbp+57h+pCurrentResourceMap]
0x1801e0bcd  lea     ppPropertyBag, [rbp+57h+pElementMap]
0x1801e0bd1  mov     pUri, rax
0x1801e0bd4  mov     rax, rsi
0x1801e0bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0bdc  test    eax, eax
0x1801e0bde  js      loc_1801E0F71
0x1801e0be4  mov     this, [rbp+57h+pElementMap]
0x1801e0be8  lea     pUri, [rbp+57h+resourceCount]
0x1801e0bec  mov     rax, [this]
0x1801e0bef  mov     rax, [rax+48h]
0x1801e0bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0bf8  mov     ebx, eax
0x1801e0bfa  test    eax, eax
0x1801e0bfc  js      loc_1801E1032
0x1801e0c02  mov     this, cs:?gps@@3V?$EncodedPtr@UIPlatformServices@@@@A.m_pTarget; EncodedPtr<IPlatformServices> gps ...
0x1801e0c09  mov     edx, 90040h
0x1801e0c0e  mov     rax, [this]
0x1801e0c11  mov     rax, [rax+40h]
0x1801e0c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0c1a  test    eax, eax
0x1801e0c1c  jnz     loc_1801E11B2
0x1801e0c22  mov     esi, r12d
0x1801e0c25  lea     rdi, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1801e0c2c  cmp     esi, [rbp+57h+resourceCount]
0x1801e0c2f  jnb     loc_1801E122C
0x1801e0c35  mov     this, [rbp+57h+pElementMap]
0x1801e0c39  lea     ppPropertyBag, [rbp+57h+pszPropertyUri]
0x1801e0c3d  mov     edx, esi
0x1801e0c3f  mov     qword ptr [rbp+57h+strPropertyName.m_encodedStorage.___u0], rdi
0x1801e0c43  mov     qword ptr [rbp+57h+strPropertyValue.m_encodedStorage.___u0], rdi
0x1801e0c47  mov     rax, [this]
0x1801e0c4a  mov     rax, [rax+50h]
0x1801e0c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0c53  mov     ebx, eax
0x1801e0c55  test    eax, eax
0x1801e0c57  js      loc_1801E0FAF
0x1801e0c5d  mov     this, [rbp+57h+pElementMap]
0x1801e0c61  lea     r9, [rbp+57h+pNamedResource]
0x1801e0c65  mov     pUri, [rbp+57h+pszPropertyUri]
0x1801e0c69  lea     ppPropertyBag, IID_INamedResource
0x1801e0c70  mov     rax, [this]
0x1801e0c73  mov     rax, [rax+58h]
0x1801e0c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0c7c  mov     ebx, eax
0x1801e0c7e  test    eax, eax
0x1801e0c80  js      loc_1801E0F59
0x1801e0c86  mov     this, [rbp+57h+pNamedResource]
0x1801e0c8a  lea     ppPropertyBag, [rbp+57h+pResourceCandidate]
0x1801e0c8e  mov     pUri, [r13+20h]
0x1801e0c92  mov     rax, [this]
0x1801e0c95  mov     rax, [rax+38h]
0x1801e0c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0c9e  mov     ebx, eax
0x1801e0ca0  test    eax, eax
0x1801e0ca2  js      loc_1801E0F4D
0x1801e0ca8  mov     this, [rbp+57h+pResourceCandidate]
0x1801e0cac  lea     pUri, [rbp+57h+pszPropertyValue]
0x1801e0cb0  mov     rax, [this]
0x1801e0cb3  mov     rax, [rax+18h]
0x1801e0cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0cbc  mov     ebx, eax
0x1801e0cbe  test    eax, eax
0x1801e0cc0  js      loc_1801E0E35
0x1801e0cc6  mov     this, [rbp+57h+pszPropertyUri]; pString
0x1801e0cca  call    ?xstrlen@@YAIPEBG@Z; xstrlen(ushort const *)
0x1801e0ccf  mov     pUri, [rbp+57h+pszPropertyUri]; buffer
0x1801e0cd3  lea     this, [rbp+57h+strPropertyUri]; this
0x1801e0cd7  mov     r8d, eax; count
0x1801e0cda  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x1801e0cdf  lea     ppPropertyBag, [rbp+57h+strPropertyName]; pstrPropertyName
0x1801e0ce3  lea     pUri, [rbp+57h+strPropertyBagPath]; strPropertyBagPath
0x1801e0ce7  lea     this, [rbp+57h+strPropertyUri]; strPropertyUri
0x1801e0ceb  call    ?ExtractPropertyNameFromUri@ModernResourceManager_Internal@@YAJAEBVxstring_ptr_view@@0PEAVxstring_ptr@@@Z; ModernResourceManager_Internal::ExtractPropertyNameFromUri(xstring_ptr_view const &,xstring_ptr_view const &,xstring_ptr *)
0x1801e0cf0  mov     ebx, eax
0x1801e0cf2  test    eax, eax
0x1801e0cf4  js      loc_1801E104B
0x1801e0cfa  mov     this, [rbp+57h+pszPropertyValue]; pString
0x1801e0cfe  call    ?xstrlen@@YAIPEBG@Z; xstrlen(ushort const *)
0x1801e0d03  mov     this, [rbp+57h+pszPropertyValue]; buffer
0x1801e0d07  lea     ppPropertyBag, [rbp+57h+strPropertyValue]; pstrCloned
0x1801e0d0b  mov     edx, eax; count
0x1801e0d0d  call    ?CloneBuffer@xstring_ptr@@SAJPEBGIPEAV1@@Z; xstring_ptr::CloneBuffer(ushort const *,uint,xstring_ptr *)
0x1801e0d12  mov     ebx, eax
0x1801e0d14  test    eax, eax
0x1801e0d16  js      loc_1801E1220
0x1801e0d1c  lea     pUri, [rbp+57h+strPropertyName]; other
0x1801e0d20  lea     this, [rbp+57h+other]; this
0x1801e0d24  call    ??0xstring_ptr@@QEAA@AEBV0@@Z; xstring_ptr::xstring_ptr(xstring_ptr const &)
0x1801e0d29  lea     pUri, [rbp+57h+strPropertyValue]; other
0x1801e0d2d  lea     this, [rbp+57h+var_38]; this
0x1801e0d31  call    ??0xstring_ptr@@QEAA@AEBV0@@Z; xstring_ptr::xstring_ptr(xstring_ptr const &)
0x1801e0d36  mov     r15, [r14+8]
0x1801e0d3a  mov     ecx, 18h; cSize
0x1801e0d3f  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x1801e0d44  mov     rdi, rax
0x1801e0d47  test    rax, rax
0x1801e0d4a  jz      loc_1801E0FFC
0x1801e0d50  lea     pUri, [rbp+57h+other]; other
0x1801e0d54  mov     [rax], r12
0x1801e0d57  lea     this, [rax+8]; this
0x1801e0d5b  call    ??0xstring_ptr@@QEAA@AEBV0@@Z; xstring_ptr::xstring_ptr(xstring_ptr const &)
0x1801e0d60  lea     this, [rdi+10h]; this
0x1801e0d64  lea     pUri, [rbp+57h+var_38]; other
0x1801e0d68  call    ??0xstring_ptr@@QEAA@AEBV0@@Z; xstring_ptr::xstring_ptr(xstring_ptr const &)
0x1801e0d6d  lea     this, ?AppendToTail@?$xlist@U?$pair@V?$shared_ptr@VXamlProperty@@@std@@V?$shared_ptr@UXamlQualifiedObject@@@2@@std@@@@AEAAXPEAV?$_xlist_node@U?$pair@V?$shared_ptr@VXamlProperty@@@std@@V?$shared_ptr@UXamlQualifiedObject@@@2@@std@@@@@Z; xlist<std::pair<std::shared_ptr<XamlProperty>,std::shared_ptr<XamlQualifiedObject>>>::AppendToTail(_xlist_node<std::pair<std::shared_ptr<XamlProperty>,std::shared_ptr<XamlQualifiedObject>>> *)
0x1801e0d74  test    r15, r15
0x1801e0d77  lea     rax, ?SetBothEnds@?$xlist@U?$pair@PEAVCUIElement@@PEAVHWCompTreeNode@@@std@@@@AEAAXPEAV?$_xlist_node@U?$pair@PEAVCUIElement@@PEAVHWCompTreeNode@@@std@@@@@Z; xlist<std::pair<CUIElement *,HWCompTreeNode *>>::SetBothEnds(_xlist_node<std::pair<CUIElement *,HWCompTreeNode *>> *)
0x1801e0d7e  mov     pUri, rdi
0x1801e0d81  cmovnz  rax, this
0x1801e0d85  mov     this, r14
0x1801e0d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0d8d  inc     dword ptr [r14+10h]
0x1801e0d91  lea     this, [rbp+57h+var_38]; this
0x1801e0d95  mov     ebx, r12d
0x1801e0d98  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801e0d9d  lea     this, [rbp+57h+other]; this
0x1801e0da1  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801e0da6  mov     this, [rbp+57h+pszPropertyUri]; pv
0x1801e0daa  call    cs:__imp_CoTaskMemFree
0x1801e0db0  mov     this, [rbp+57h+pszPropertyValue]; pv
0x1801e0db4  mov     [rbp+57h+pszPropertyUri], r12
0x1801e0db8  call    cs:__imp_CoTaskMemFree
0x1801e0dbe  mov     this, [rbp+57h+pNamedResource]
0x1801e0dc2  mov     [rbp+57h+pszPropertyValue], r12
0x1801e0dc6  test    this, this
0x1801e0dc9  jz      short loc_1801E0DDB
0x1801e0dcb  mov     rax, [this]
0x1801e0dce  mov     rax, [rax+10h]
0x1801e0dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0dd7  mov     [rbp+57h+pNamedResource], r12
0x1801e0ddb  mov     this, [rbp+57h+pResourceCandidate]
0x1801e0ddf  test    this, this
0x1801e0de2  jz      short loc_1801E0DF4
0x1801e0de4  mov     rax, [this]
0x1801e0de7  mov     rax, [rax+10h]
0x1801e0deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0df0  mov     [rbp+57h+pResourceCandidate], r12
0x1801e0df4  movsd   xmm0, qword ptr cs:?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B.___u0; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null ...
0x1801e0dfc  lea     rdi, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1801e0e03  mov     eax, cs:?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B.Count; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null ...
0x1801e0e09  lea     this, [rbp+57h+strPropertyValue]; this
0x1801e0e0d  mov     qword ptr [rbp+57h+strPropertyUri.m_encodedStorage.___u0], rdi
0x1801e0e11  movsd   qword ptr [rbp+57h+strPropertyUri.m_ephemeralStorage.___u0], xmm0
0x1801e0e16  mov     dword ptr [rbp+57h+strPropertyUri.m_ephemeralStorage.Count], eax
0x1801e0e19  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801e0e1e  lea     this, [rbp+57h+strPropertyName]; this
0x1801e0e22  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801e0e27  inc     esi
0x1801e0e29  jmp     loc_1801E0C2C
0x1801e0e2e  mov     al, 1
0x1801e0e30  jmp     loc_1801E0B38
0x1801e0e35  mov     ecx, eax; failedFrameHR
0x1801e0e37  call    OnFailure_2990_
0x1801e0e3c  lea     this, [rbp+57h+strPropertyValue]; this
0x1801e0e40  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801e0e45  lea     this, [rbp+57h+strPropertyName]; this
0x1801e0e49  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801e0e4e  mov     this, [rbp+57h+pszPropertyUri]; pv
0x1801e0e52  call    cs:__imp_CoTaskMemFree
0x1801e0e58  mov     this, [rbp+57h+pszPropertyValue]; pv
0x1801e0e5c  call    cs:__imp_CoTaskMemFree
0x1801e0e62  mov     this, [rbp+57h+pCurrentResourceMap]
0x1801e0e66  test    this, this
0x1801e0e69  jz      short loc_1801E0E7B
0x1801e0e6b  mov     rax, [this]
0x1801e0e6e  mov     rax, [rax+10h]
0x1801e0e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0e77  mov     [rbp+57h+pCurrentResourceMap], r12
0x1801e0e7b  mov     this, [rbp+57h+pElementMap]
0x1801e0e7f  test    this, this
0x1801e0e82  jz      short loc_1801E0E94
0x1801e0e84  mov     rax, [this]
0x1801e0e87  mov     rax, [rax+10h]
0x1801e0e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0e90  mov     [rbp+57h+pElementMap], r12
0x1801e0e94  mov     this, [rbp+57h+pNamedResource]
0x1801e0e98  test    this, this
0x1801e0e9b  jz      short loc_1801E0EAD
0x1801e0e9d  mov     rax, [this]
0x1801e0ea0  mov     rax, [rax+10h]
0x1801e0ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0ea9  mov     [rbp+57h+pNamedResource], r12
0x1801e0ead  mov     this, [rbp+57h+pResourceCandidate]
0x1801e0eb1  test    this, this
0x1801e0eb4  jz      short loc_1801E0EC6
0x1801e0eb6  mov     rax, [this]
0x1801e0eb9  mov     rax, [rax+10h]
0x1801e0ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0ec2  mov     [rbp+57h+pResourceCandidate], r12
0x1801e0ec6  lea     this, [rbp+57h+strCanonicalUri]; this
0x1801e0eca  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801e0ecf  lea     this, [rbp+57h+strPropertyBagPath]; this
0x1801e0ed3  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801e0ed8  lea     this, [rbp+57h+strResourceMapName]; this
0x1801e0edc  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801e0ee1  mov     eax, ebx
0x1801e0ee3  mov     rbx, [rsp+0E0h+arg_0]
0x1801e0eeb  add     rsp, 0B0h
  ... truncated ...
```
