# ResourceManager::GetUriForPropertyBagLookup(xstring_ptr_view const &,xref_ptr<IPALUri> const &,uint,xref_ptr<IPALUri> &)

- ea: `0x180171860`
- end: `0x18017208b`
- name: `?GetUriForPropertyBagLookup@ResourceManager@@UEAAJAEBVxstring_ptr_view@@AEBV?$xref_ptr@UIPALUri@@@@IAEAV3@@Z`
- size: `2091`
- prototype: `HRESULT __fastcall(ResourceManager *this, const xstring_ptr_view *strXUid, const xref_ptr<IPALUri> *spBaseUri, const unsigned int shouldReturnFullyQualifiedUri, xref_ptr<IPALUri> *spPropertyBagUri)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801716a0`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x1800913b4`
- `0x1800c039c`
- `0x1800fe130`
- `0x180171860`
- `0x18017233c`
- `0x180174290`
- `0x18017d850`
- `0x1801800b8`
- `0x180194584`
- `0x1801952a8`
- `0x180281704`
- `0x1804ab398`
- `0x1804e7328`
- `0x18069f6ac`
- `0x1806c1dc0`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180171a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180171a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180171c59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180171cfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180171def`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180171f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180171c59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180171cfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180171def`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180171f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180171e9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180171e9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180171e6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180171e81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180171e6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180171e81`

## pseudocode

```c
__int64 __fastcall ResourceManager::GetUriForPropertyBagLookup(
        ResourceManager *this,
        const xstring_ptr_storage *strXUid,
        const xref_ptr<IPALUri> *spBaseUri,
        const unsigned int shouldReturnFullyQualifiedUri,
        ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *spPropertyBagUri)
{
  IPALUri *m_ptr; // rcx
  unsigned int m_cBuffer; // r15d
  HRESULT v9; // eax
  unsigned int v10; // ebx
  IPALUri *v11; // rbx
  IPALUri_vtbl *v12; // rax
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // ecx
  const wchar_t *v16; // rbx
  __int64 v18; // rbx
  int v19; // r14d
  UINT32 StringLen; // r14d
  int v21; // esi
  UINT32 v22; // esi
  const char *v23; // rdi
  __int16 v24; // ax
  unsigned int v25; // edi
  int v26; // eax
  HRESULT v27; // eax
  __int64 m_cActual; // rcx
  wchar_t *m_pBuffer; // rax
  HRESULT appended; // eax
  int v31; // edx
  HSTRING StringRawBuffer; // rcx
  __int64 v33; // rcx
  wchar_t *v34; // rax
  IPlatformServices *m_pTarget; // rbx
  IPALUri *v36; // rcx
  HRESULT (__fastcall *UriCreate)(IPALURIServices *, unsigned int, const wchar_t *, IPALUri **); // rdi
  HRESULT v38; // eax
  IPALUri *v39; // rsi
  HRESULT (__fastcall *Combine)(IPALUri *, unsigned int, const wchar_t *, IPALUri **); // rdi
  const wchar_t *Buffer; // rbx
  unsigned int Count; // eax
  IPALUri *v43; // rcx
  IPALUri *v44; // rcx
  IPALUri *v46; // rcx
  IPALUri *v47; // rcx
  IPALUri *v48; // rcx
  unsigned int Char; // eax
  HSTRING v50; // rcx
  HSTRING Handle; // rcx
  HRESULT v52; // eax
  xref_ptr<IPALUri> spMsResourceBaseUri; // [rsp+30h] [rbp-D0h] BYREF
  xref_ptr<IPALUri> spBaseResourceUri; // [rsp+38h] [rbp-C8h] BYREF
  xephemeral_string_ptr strComponentName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int isMsResourceUri; // [rsp+58h] [rbp-A8h] BYREF
  xref_ptr<IPALUri> spPropertyBagUriFull; // [rsp+60h] [rbp-A0h] BYREF
  xstring_ptr strFilePath; // [rsp+68h] [rbp-98h] BYREF
  xstring_ptr strResourceMap; // [rsp+70h] [rbp-90h] BYREF
  xstring_ptr strUriFull; // [rsp+78h] [rbp-88h] BYREF
  ResourceManager *v61; // [rsp+80h] [rbp-80h]
  TStringBuilder<96> baseResourceUriStrBuilder; // [rsp+90h] [rbp-70h] BYREF

  strUriFull.m_encodedStorage.Storage = strXUid;
  v61 = this;
  m_ptr = spBaseUri->m_ptr;
  isMsResourceUri = 0;
  m_cBuffer = 96;
  LODWORD(spPropertyBagUriFull.m_ptr) = 0;
  *(_QWORD *)&baseResourceUriStrBuilder.m_cBuffer = 96;
  strResourceMap.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  strFilePath.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  spMsResourceBaseUri.m_ptr = 0;
  spBaseResourceUri.m_ptr = 0;
  baseResourceUriStrBuilder.m_pBuffer = baseResourceUriStrBuilder.m_inlineBuffer;
  baseResourceUriStrBuilder.m_hPreallocatedBuffer = 0;
  strComponentName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  v9 = MsUriHelpers::IsMsResourceUri(m_ptr, &isMsResourceUri);
  v10 = v9;
  if ( v9 < 0 )
  {
    OnFailure_2990_(v9);
    *((_DWORD *)&strComponentName.m_ephemeralStorage + 2) = *((_DWORD *)&xstring_ptr_constants::c_xstring_ptr_storage_null
                                                            + 2);
    strComponentName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
    goto LABEL_91;
  }
  v11 = spBaseUri->m_ptr;
  v12 = spBaseUri->m_ptr->__vftable;
  if ( isMsResourceUri )
  {
    v13 = v12->Clone(v11, &spMsResourceBaseUri.m_ptr);
    v10 = v13;
    if ( v13 < 0 )
      goto LABEL_80;
  }
  else
  {
    v14 = v12->TransformToMsResourceUri(v11, &spMsResourceBaseUri.m_ptr);
    v10 = v14;
    if ( v14 < 0 )
    {
LABEL_57:
      OnFailure_2990_(v14);
      strComponentName.m_ephemeralStorage = xstring_ptr_constants::c_xstring_ptr_storage_null;
      strComponentName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
      if ( baseResourceUriStrBuilder.m_pBuffer != baseResourceUriStrBuilder.m_inlineBuffer )
      {
        WindowsDeleteStringBuffer(baseResourceUriStrBuilder.m_hPreallocatedBuffer);
        baseResourceUriStrBuilder.m_hPreallocatedBuffer = 0;
      }
      v48 = spBaseResourceUri.m_ptr;
      baseResourceUriStrBuilder.m_pBuffer = 0;
      if ( spBaseResourceUri.m_ptr )
      {
        spBaseResourceUri.m_ptr = 0;
        v48->Release(v48);
      }
      v47 = spMsResourceBaseUri.m_ptr;
      if ( !spMsResourceBaseUri.m_ptr )
        goto LABEL_55;
      spMsResourceBaseUri.m_ptr = 0;
LABEL_54:
      v47->Release(v47);
LABEL_55:
      xstring_ptr::~xstring_ptr(&strFilePath);
      xstring_ptr::~xstring_ptr(&strResourceMap);
      return v10;
    }
  }
  v14 = MsUriHelpers::CrackMsResourceUri(
          spMsResourceBaseUri.m_ptr,
          &strResourceMap,
          0,
          &strFilePath,
          (unsigned int *)&spPropertyBagUriFull);
  v10 = v14;
  if ( v14 < 0 )
    goto LABEL_57;
  if ( !LODWORD(spPropertyBagUriFull.m_ptr) )
    goto LABEL_81;
  if ( ((unsigned int (__fastcall *)(IPALUri *))spBaseUri->m_ptr->GetComponentResourceLocation)(spBaseUri->m_ptr) == 1 )
  {
    Char = xstring_ptr_view::FindChar(&strFilePath, 0x2Fu, 0);
    if ( Char )
    {
      xstring_ptr_view::SubString(&strFilePath, 0, Char, &strComponentName);
      goto LABEL_7;
    }
LABEL_81:
    OnFailure_1169_(v15);
    strComponentName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
    strComponentName.m_ephemeralStorage = xstring_ptr_constants::c_xstring_ptr_storage_null;
    TStringBuilder<16>::~TStringBuilder<16>(&baseResourceUriStrBuilder);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spBaseResourceUri);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMsResourceBaseUri);
    v10 = -2147024809;
    goto LABEL_55;
  }
LABEL_7:
  v16 = L"ms-resource://";
  while ( *v16++ )
    ;
  v18 = v16 - L"ms-resource://";
  if ( ((__int64)strResourceMap.m_encodedStorage.Storage & 1) != 0 )
  {
    v50 = (HSTRING)(strResourceMap.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v19 = *((_DWORD *)strResourceMap.m_encodedStorage.Storage + 2);
    if ( v19 >= 0 )
    {
      StringLen = v19 & 0x3FFFFFFF;
      goto LABEL_12;
    }
    v50 = *(HSTRING *)strResourceMap.m_encodedStorage.Handle;
  }
  StringLen = WindowsGetStringLen(v50);
LABEL_12:
  if ( ((__int64)strComponentName.m_encodedStorage.Storage & 1) != 0 )
  {
    Handle = (HSTRING)(strComponentName.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
LABEL_69:
    v22 = WindowsGetStringLen(Handle);
    goto LABEL_15;
  }
  v21 = *(_DWORD *)(strComponentName.m_encodedStorage.RuntimeStringHandleMarker + 8);
  if ( v21 < 0 )
  {
    Handle = strComponentName.m_encodedStorage.Storage->Handle;
    goto LABEL_69;
  }
  v22 = v21 & 0x3FFFFFFF;
LABEL_15:
  v23 = L"/Resources/";
  do
  {
    v24 = *(_WORD *)v23;
    v23 += 2;
  }
  while ( v24 );
  v25 = v18
      + StringLen
      + v22
      + xstring_ptr_view::GetCount((xstring_ptr_view *)strUriFull.m_encodedStorage.Storage)
      + ((v23 - L"/Resources/") >> 1);
  if ( v25 - 1 >= 0x7FFFFF9F )
  {
    v10 = -2147418113;
    OnNewFailure_2955_((HRESULT)L"/Resources/");
    goto LABEL_47;
  }
  if ( baseResourceUriStrBuilder.m_pBuffer == baseResourceUriStrBuilder.m_inlineBuffer )
  {
    m_cBuffer = baseResourceUriStrBuilder.m_cBuffer;
  }
  else
  {
    WindowsDeleteStringBuffer(baseResourceUriStrBuilder.m_hPreallocatedBuffer);
    baseResourceUriStrBuilder.m_hPreallocatedBuffer = 0;
    baseResourceUriStrBuilder.m_pBuffer = baseResourceUriStrBuilder.m_inlineBuffer;
    baseResourceUriStrBuilder.m_cBuffer = 96;
  }
  if ( v25 > m_cBuffer )
  {
    v26 = WindowsPreallocateStringBuffer(
            v25 - 1,
            &baseResourceUriStrBuilder.m_pBuffer,
            &baseResourceUriStrBuilder.m_hPreallocatedBuffer);
    v10 = v26;
    if ( v26 >= 0 )
    {
      baseResourceUriStrBuilder.m_cBuffer = v25;
      goto LABEL_23;
    }
    OnFailure_2990_(v26);
LABEL_47:
    OnFailure_2990_(v10);
LABEL_48:
    strComponentName.m_ephemeralStorage = xstring_ptr_constants::c_xstring_ptr_storage_null;
    strComponentName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
    if ( baseResourceUriStrBuilder.m_pBuffer != baseResourceUriStrBuilder.m_inlineBuffer )
    {
      WindowsDeleteStringBuffer(baseResourceUriStrBuilder.m_hPreallocatedBuffer);
      baseResourceUriStrBuilder.m_hPreallocatedBuffer = 0;
    }
    v46 = spBaseResourceUri.m_ptr;
    baseResourceUriStrBuilder.m_pBuffer = 0;
    if ( spBaseResourceUri.m_ptr )
    {
      spBaseResourceUri.m_ptr = 0;
      v46->Release(v46);
    }
    v47 = spMsResourceBaseUri.m_ptr;
    if ( !spMsResourceBaseUri.m_ptr )
      goto LABEL_55;
    spMsResourceBaseUri.m_ptr = 0;
    goto LABEL_54;
  }
LABEL_23:
  baseResourceUriStrBuilder.m_cActual = 0;
  v27 = TStringBuilder<96>::EnsureBufferForAdding(&baseResourceUriStrBuilder, 0xEu);
  v10 = v27;
  if ( v27 < 0 )
    goto LABEL_72;
  m_cActual = baseResourceUriStrBuilder.m_cActual;
  m_pBuffer = baseResourceUriStrBuilder.m_pBuffer;
  *(_OWORD *)&baseResourceUriStrBuilder.m_pBuffer[baseResourceUriStrBuilder.m_cActual] = *(_OWORD *)L"ms-resource://";
  *(_OWORD *)&m_pBuffer[m_cActual + 6] = *(_OWORD *)L"ource://";
  baseResourceUriStrBuilder.m_cActual += 14;
  baseResourceUriStrBuilder.m_pBuffer[baseResourceUriStrBuilder.m_cActual] = 0;
  appended = TStringBuilder<96>::Append(&baseResourceUriStrBuilder, &strResourceMap);
  v10 = appended;
  if ( appended < 0 )
    goto LABEL_87;
  isMsResourceUri = 0;
  if ( ((__int64)strComponentName.m_encodedStorage.Storage & 1) != 0 )
  {
    StringRawBuffer = (HSTRING)(strComponentName.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_71;
  }
  v31 = *(_DWORD *)(strComponentName.m_encodedStorage.RuntimeStringHandleMarker + 8);
  StringRawBuffer = strComponentName.m_encodedStorage.Storage->Handle;
  if ( v31 < 0 )
  {
LABEL_71:
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(StringRawBuffer, &isMsResourceUri);
    goto LABEL_28;
  }
  isMsResourceUri = v31 & 0x3FFFFFFF;
LABEL_28:
  if ( StringRawBuffer && isMsResourceUri && *(_WORD *)StringRawBuffer )
  {
    appended = TStringBuilder<96>::AppendChar(&baseResourceUriStrBuilder, 0x2Fu);
    v10 = appended;
    if ( appended >= 0 )
    {
      v13 = TStringBuilder<96>::Append(&baseResourceUriStrBuilder, &strComponentName);
      v10 = v13;
      if ( v13 >= 0 )
        goto LABEL_33;
LABEL_80:
      OnFailure_2990_(v13);
      *((_DWORD *)&strComponentName.m_ephemeralStorage + 2) = *((_DWORD *)&xstring_ptr_constants::c_xstring_ptr_storage_null
                                                              + 2);
LABEL_89:
      strComponentName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
LABEL_91:
      strComponentName.m_ephemeralStorage.Buffer = xstring_ptr_constants::c_xstring_ptr_storage_null.Buffer;
      TStringBuilder<16>::~TStringBuilder<16>(&baseResourceUriStrBuilder);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spBaseResourceUri);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMsResourceBaseUri);
      goto LABEL_55;
    }
LABEL_87:
    OnFailure_2990_(appended);
LABEL_88:
    *((_DWORD *)&strComponentName.m_ephemeralStorage + 2) = *((_DWORD *)&xstring_ptr_constants::c_xstring_ptr_storage_null
                                                            + 2);
    goto LABEL_89;
  }
LABEL_33:
  v27 = TStringBuilder<96>::EnsureBufferForAdding(&baseResourceUriStrBuilder, 0xBu);
  v10 = v27;
  if ( v27 < 0 )
  {
LABEL_72:
    OnFailure_2990_(v27);
    OnFailure_2990_(v10);
    goto LABEL_48;
  }
  v33 = baseResourceUriStrBuilder.m_cActual;
  v34 = baseResourceUriStrBuilder.m_pBuffer;
  *(_OWORD *)&baseResourceUriStrBuilder.m_pBuffer[baseResourceUriStrBuilder.m_cActual] = *(_OWORD *)L"/Resources/";
  *(_QWORD *)&v34[v33 + 7] = *(_QWORD *)L"ces/";
  baseResourceUriStrBuilder.m_cActual += 11;
  baseResourceUriStrBuilder.m_pBuffer[baseResourceUriStrBuilder.m_cActual] = 0;
  m_pTarget = gps.m_pTarget;
  v36 = spBaseResourceUri.m_ptr;
  UriCreate = gps.m_pTarget->UriCreate;
  if ( spBaseResourceUri.m_ptr )
  {
    spBaseResourceUri.m_ptr = 0;
    v36->Release(v36);
  }
  v38 = UriCreate(
          &m_pTarget->IPALURIServices,
          baseResourceUriStrBuilder.m_cActual,
          baseResourceUriStrBuilder.m_pBuffer,
          &spBaseResourceUri.m_ptr);
  v10 = v38;
  if ( v38 < 0
    || (v39 = spBaseResourceUri.m_ptr,
        Combine = spBaseResourceUri.m_ptr->Combine,
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(spPropertyBagUri),
        Buffer = xstring_ptr_view::GetBuffer((xstring_ptr_view *)strUriFull.m_encodedStorage.Storage),
        Count = xstring_ptr_view::GetCount((xstring_ptr_view *)strUriFull.m_encodedStorage.Storage),
        v38 = Combine(v39, Count, Buffer, (IPALUri **)spPropertyBagUri),
        v10 = v38,
        v38 < 0) )
  {
    OnFailure_2990_(v38);
    goto LABEL_48;
  }
  if ( shouldReturnFullyQualifiedUri )
  {
    spPropertyBagUriFull.m_ptr = 0;
    strUriFull.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
    v52 = v61->m_pResourceProvider->ConvertResourceMapUriToFullyQualified(
            v61->m_pResourceProvider,
            (const xref_ptr<IPALUri> *)spPropertyBagUri,
            &spPropertyBagUriFull);
    v10 = v52;
    if ( v52 >= 0 )
    {
      xref_ptr<IPALUri>::operator=((xref_ptr<IPALUri> *)spPropertyBagUri, &spPropertyBagUriFull);
      xstring_ptr::~xstring_ptr(&strUriFull);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyBagUriFull);
      goto LABEL_39;
    }
    OnFailure_2990_(v52);
    xstring_ptr::~xstring_ptr(&strUriFull);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyBagUriFull);
    goto LABEL_88;
  }
LABEL_39:
  strComponentName.m_ephemeralStorage = xstring_ptr_constants::c_xstring_ptr_storage_null;
  strComponentName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  if ( baseResourceUriStrBuilder.m_pBuffer != baseResourceUriStrBuilder.m_inlineBuffer )
  {
    WindowsDeleteStringBuffer(baseResourceUriStrBuilder.m_hPreallocatedBuffer);
    baseResourceUriStrBuilder.m_hPreallocatedBuffer = 0;
  }
  v43 = spBaseResourceUri.m_ptr;
  baseResourceUriStrBuilder.m_pBuffer = 0;
  if ( spBaseResourceUri.m_ptr )
  {
    spBaseResourceUri.m_ptr = 0;
    v43->Release(v43);
  }
  v44 = spMsResourceBaseUri.m_ptr;
  if ( spMsResourceBaseUri.m_ptr )
  {
    spMsResourceBaseUri.m_ptr = 0;
    v44->Release(v44);
  }
  xstring_ptr::~xstring_ptr(&strFilePath);
  xstring_ptr::~xstring_ptr(&strResourceMap);
  return 0;
}

```

## disassembly

```asm
0x180171860  mov     [rsp-8+arg_18], rbx
0x180171865  push    rbp
0x180171866  push    rsi
0x180171867  push    rdi
0x180171868  push    r12
0x18017186a  push    r13
0x18017186c  push    r14
0x18017186e  push    r15
0x180171870  lea     rbp, [rsp-80h]
0x180171875  sub     rsp, 180h
0x18017187c  mov     rax, cs:__security_cookie
0x180171883  xor     rax, rsp
0x180171886  mov     [rbp+0B0h+var_40], rax
0x18017188a  mov     r12, [rbp+0B0h+arg_20]
0x180171891  lea     rsi, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x180171898  xor     r14d, r14d
0x18017189b  mov     qword ptr [rsp+1B0h+strUriFull.m_encodedStorage.___u0], strXUid
0x1801718a0  mov     [rbp+0B0h+var_130], this
0x1801718a4  lea     rax, [rbp+0B0h+baseResourceUriStrBuilder.m_inlineBuffer]
0x1801718a8  mov     this, [spBaseUri]; pUri
0x1801718ab  lea     strXUid, [rsp+1B0h+isMsResourceUri]; pResult
0x1801718b0  mov     r13d, shouldReturnFullyQualifiedUri
0x1801718b3  mov     [rsp+1B0h+isMsResourceUri], r14d
0x1801718b8  lea     r15d, [r14+60h]
0x1801718bc  mov     dword ptr [rsp+1B0h+spPropertyBagUriFull.m_ptr], r14d
0x1801718c1  mov     qword ptr [rbp+0B0h+baseResourceUriStrBuilder.m_cBuffer], r15
0x1801718c5  mov     rdi, spBaseUri
0x1801718c8  mov     qword ptr [rsp+1B0h+strResourceMap.m_encodedStorage.___u0], rsi
0x1801718cd  mov     qword ptr [rsp+1B0h+strFilePath.m_encodedStorage.___u0], rsi
0x1801718d2  mov     [rsp+1B0h+spMsResourceBaseUri.m_ptr], r14
0x1801718d7  mov     [rsp+1B0h+spBaseResourceUri.m_ptr], r14
0x1801718dc  mov     [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer], rax
0x1801718e0  mov     [rbp+0B0h+baseResourceUriStrBuilder.m_hPreallocatedBuffer], r14
0x1801718e4  mov     qword ptr [rsp+1B0h+strComponentName.m_encodedStorage.___u0], rsi
0x1801718e9  call    ?IsMsResourceUri@MsUriHelpers@@YAJPEBUIPALUri@@PEAI@Z; MsUriHelpers::IsMsResourceUri(IPALUri const *,uint *)
0x1801718ee  mov     ebx, eax
0x1801718f0  test    eax, eax
0x1801718f2  js      loc_180172045
0x1801718f8  mov     rbx, [rdi]
0x1801718fb  mov     this, [rsp+1B0h+spMsResourceBaseUri.m_ptr]
0x180171900  mov     rax, [rbx]
0x180171903  cmp     [rsp+1B0h+isMsResourceUri], r14d
0x180171908  jz      loc_180171D7F
0x18017190e  mov     rsi, [rax+18h]
0x180171912  test    this, this
0x180171915  jz      short loc_180171928
0x180171917  mov     [rsp+1B0h+spMsResourceBaseUri.m_ptr], r14
0x18017191c  mov     strXUid, [this]
0x18017191f  mov     rax, [strXUid+10h]
0x180171923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171928  lea     strXUid, [rsp+1B0h+spMsResourceBaseUri]
0x18017192d  mov     this, rbx
0x180171930  mov     rax, rsi
0x180171933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171938  mov     ebx, eax
0x18017193a  test    eax, eax
0x18017193c  js      loc_180171F0E
0x180171942  mov     this, [rsp+1B0h+spMsResourceBaseUri.m_ptr]; pUri
0x180171947  lea     rax, [rsp+1B0h+spPropertyBagUriFull]
0x18017194c  lea     r9, [rsp+1B0h+strFilePath]; pstrFilePath
0x180171951  mov     [rsp+1B0h+pHadFilePath], rax; pHadFilePath
0x180171956  xor     r8d, r8d; pstrResourcePath
0x180171959  lea     strXUid, [rsp+1B0h+strResourceMap]; pstrResourceMap
0x18017195e  call    ?CrackMsResourceUri@MsUriHelpers@@YAJPEBUIPALUri@@PEAVxstring_ptr@@11PEAI@Z; MsUriHelpers::CrackMsResourceUri(IPALUri const *,xstring_ptr *,xstring_ptr *,xstring_ptr *,uint *)
0x180171963  mov     ebx, eax
0x180171965  test    eax, eax
0x180171967  js      loc_180171EF2
0x18017196d  cmp     dword ptr [rsp+1B0h+spPropertyBagUriFull.m_ptr], r14d
0x180171972  jz      loc_180171F34
0x180171978  mov     this, [rdi]
0x18017197b  mov     rax, [this]
0x18017197e  mov     rax, [rax+0A0h]
0x180171985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017198a  cmp     eax, 1
0x18017198d  jz      loc_180171E30
0x180171993  lea     this, aMsResource; "ms-resource://"
0x18017199a  mov     rbx, this
0x18017199d  movzx   eax, word ptr [rbx]
0x1801719a0  add     rbx, 2
0x1801719a4  test    ax, ax
0x1801719a7  jnz     short loc_18017199D
0x1801719a9  sub     rbx, this
0x1801719ac  mov     this, qword ptr [rsp+1B0h+strResourceMap.m_encodedStorage.___u0]
0x1801719b1  sar     rbx, 1
0x1801719b4  test    cl, 1
0x1801719b7  jnz     loc_180171E6B
0x1801719bd  mov     r14d, [this+8]
0x1801719c1  test    r14d, r14d
0x1801719c4  js      loc_180171EFE
0x1801719ca  and     r14d, 3FFFFFFFh
0x1801719d1  mov     this, qword ptr [rsp+1B0h+strComponentName.m_encodedStorage.___u0]
0x1801719d6  test    cl, 1
0x1801719d9  jnz     loc_180171E7D
0x1801719df  mov     esi, [this+8]
0x1801719e2  test    esi, esi
0x1801719e4  js      loc_180171F06
0x1801719ea  and     esi, 3FFFFFFFh
0x1801719f0  lea     rdi, aResources; "/Resources/"
0x1801719f7  movzx   eax, word ptr [rdi]
0x1801719fa  add     rdi, 2
0x1801719fe  test    ax, ax
0x180171a01  jnz     short loc_1801719F7
0x180171a03  mov     this, qword ptr [rsp+1B0h+strUriFull.m_encodedStorage.___u0]; this
0x180171a08  call    ?GetCount@xstring_ptr_view@@QEBAIXZ; xstring_ptr_view::GetCount(void)
0x180171a0d  add     eax, esi
0x180171a0f  lea     this, aResources; "/Resources/"
0x180171a16  sub     rdi, this
0x180171a19  sar     rdi, 1
0x180171a1c  add     edi, eax
0x180171a1e  add     edi, r14d
0x180171a21  add     edi, ebx
0x180171a23  lea     ebx, [rdi-1]
0x180171a26  cmp     ebx, 7FFFFF9Fh
0x180171a2c  jnb     loc_180171CB8
0x180171a32  lea     rax, [rbp+0B0h+baseResourceUriStrBuilder.m_inlineBuffer]
0x180171a36  cmp     [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer], rax
0x180171a3a  jnz     loc_180171F8B
0x180171a40  mov     r15d, [rbp+0B0h+baseResourceUriStrBuilder.m_cBuffer]
0x180171a44  cmp     edi, r15d
0x180171a47  jbe     loc_180171E63
0x180171a4d  lea     spBaseUri, [rbp+0B0h+baseResourceUriStrBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180171a51  mov     ecx, ebx; length
0x180171a53  lea     strXUid, [rbp+0B0h+baseResourceUriStrBuilder]; charBuffer
0x180171a57  call    cs:__imp_WindowsPreallocateStringBuffer
0x180171a5d  xor     r15d, r15d
0x180171a60  mov     ebx, eax
0x180171a62  test    eax, eax
0x180171a64  js      loc_180171ECE
0x180171a6a  mov     [rbp+0B0h+baseResourceUriStrBuilder.m_cBuffer], edi
0x180171a6d  mov     edx, 0Eh; uNumberOfCharsToBeAdded
0x180171a72  mov     [rbp+0B0h+baseResourceUriStrBuilder.m_cActual], r15d
0x180171a76  lea     this, [rbp+0B0h+baseResourceUriStrBuilder]; this
0x180171a7a  call    ?EnsureBufferForAdding@?$TStringBuilder@$0GA@@@AEAAJI@Z; TStringBuilder<96>::EnsureBufferForAdding(uint)
0x180171a7f  mov     ebx, eax
0x180171a81  test    eax, eax
0x180171a83  js      loc_180171EBB
0x180171a89  mov     ecx, [rbp+0B0h+baseResourceUriStrBuilder.m_cActual]
0x180171a8c  mov     rax, [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer]
0x180171a90  movups  xmm0, xmmword ptr cs:aMsResource; "ms-resource://"
0x180171a97  movups  xmmword ptr [rax+this*2], xmm0
0x180171a9b  movups  xmm1, xmmword ptr cs:aMsResource+0Ch; "ource://"
0x180171aa2  movups  xmmword ptr [rax+this*2+0Ch], xmm1
0x180171aa7  mov     eax, [rbp+0B0h+baseResourceUriStrBuilder.m_cActual]
0x180171aaa  lea     this, [rbp+0B0h+baseResourceUriStrBuilder]; this
0x180171aae  add     eax, 0Eh
0x180171ab1  mov     edx, eax
0x180171ab3  mov     [rbp+0B0h+baseResourceUriStrBuilder.m_cActual], eax
0x180171ab6  mov     rax, [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer]
0x180171aba  mov     [rax+strXUid*2], r15w
0x180171abf  lea     strXUid, [rsp+1B0h+strResourceMap]; strToAppend
0x180171ac4  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x180171ac9  mov     ebx, eax
0x180171acb  test    eax, eax
0x180171acd  js      loc_180172026
0x180171ad3  mov     rax, qword ptr [rsp+1B0h+strComponentName.m_encodedStorage.___u0]
0x180171ad8  mov     [rsp+1B0h+isMsResourceUri], r15d
0x180171add  test    al, 1
0x180171adf  jnz     loc_180171E8E
0x180171ae5  mov     edx, [rax+8]
0x180171ae8  mov     this, [rax]
0x180171aeb  test    edx, edx
0x180171aed  js      loc_180171E95
0x180171af3  and     edx, 3FFFFFFFh
0x180171af9  mov     [rsp+1B0h+isMsResourceUri], edx
0x180171afd  test    this, this
0x180171b00  jz      short loc_180171B3F
0x180171b02  cmp     [rsp+1B0h+isMsResourceUri], r15d
0x180171b07  jz      short loc_180171B3F
0x180171b09  cmp     r15w, [this]
0x180171b0d  jz      short loc_180171B3F
0x180171b0f  mov     edx, 2Fh ; '/'; ch
0x180171b14  lea     this, [rbp+0B0h+baseResourceUriStrBuilder]; this
0x180171b18  call    ?AppendChar@?$TStringBuilder@$0GA@@@QEAAJG@Z; TStringBuilder<96>::AppendChar(ushort)
0x180171b1d  mov     ebx, eax
0x180171b1f  test    eax, eax
0x180171b21  js      loc_180171FAE
0x180171b27  lea     strXUid, [rsp+1B0h+strComponentName]; strToAppend
0x180171b2c  lea     this, [rbp+0B0h+baseResourceUriStrBuilder]; this
0x180171b30  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x180171b35  mov     ebx, eax
0x180171b37  test    eax, eax
0x180171b39  js      loc_180171F17
0x180171b3f  mov     edx, 0Bh; uNumberOfCharsToBeAdded
0x180171b44  lea     this, [rbp+0B0h+baseResourceUriStrBuilder]; this
0x180171b48  call    ?EnsureBufferForAdding@?$TStringBuilder@$0GA@@@AEAAJI@Z; TStringBuilder<96>::EnsureBufferForAdding(uint)
0x180171b4d  mov     ebx, eax
0x180171b4f  test    eax, eax
0x180171b51  js      loc_180171EA8
0x180171b57  mov     ecx, [rbp+0B0h+baseResourceUriStrBuilder.m_cActual]
0x180171b5a  mov     rax, [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer]
0x180171b5e  movups  xmm0, xmmword ptr cs:aResources; "/Resources/"
0x180171b65  movups  xmmword ptr [rax+this*2], xmm0
0x180171b69  movsd   xmm1, qword ptr cs:aResources+0Eh; "ces/"
0x180171b71  movsd   qword ptr [rax+this*2+0Eh], xmm1
0x180171b77  mov     eax, [rbp+0B0h+baseResourceUriStrBuilder.m_cActual]
0x180171b7a  add     eax, 0Bh
0x180171b7d  mov     [rbp+0B0h+baseResourceUriStrBuilder.m_cActual], eax
0x180171b80  mov     edx, eax
0x180171b82  mov     rax, [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer]
0x180171b86  mov     [rax+strXUid*2], r15w
0x180171b8b  mov     rbx, cs:?gps@@3V?$EncodedPtr@UIPlatformServices@@@@A.m_pTarget; EncodedPtr<IPlatformServices> gps ...
0x180171b92  mov     this, [rsp+1B0h+spBaseResourceUri.m_ptr]
0x180171b97  mov     rax, [rbx+10h]
0x180171b9b  mov     rdi, [rax]
0x180171b9e  test    this, this
0x180171ba1  jz      short loc_180171BB4
0x180171ba3  mov     [rsp+1B0h+spBaseResourceUri.m_ptr], r15
0x180171ba8  mov     strXUid, [this]
0x180171bab  mov     rax, [strXUid+10h]
0x180171baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171bb4  mov     spBaseUri, [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer]
0x180171bb8  lea     r9, [rsp+1B0h+spBaseResourceUri]
0x180171bbd  mov     edx, [rbp+0B0h+baseResourceUriStrBuilder.m_cActual]
0x180171bc0  lea     this, [rbx+10h]
0x180171bc4  mov     rax, rdi
0x180171bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171bcc  mov     ebx, eax
0x180171bce  test    eax, eax
0x180171bd0  js      loc_180171EE6
0x180171bd6  mov     rsi, [rsp+1B0h+spBaseResourceUri.m_ptr]
0x180171bdb  mov     this, r12; this
0x180171bde  mov     rax, [rsi]
0x180171be1  mov     rdi, [rax+20h]
0x180171be5  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180171bea  mov     this, qword ptr [rsp+1B0h+strUriFull.m_encodedStorage.___u0]; this
0x180171bef  call    ?GetBuffer@xstring_ptr_view@@QEBAPEBGXZ; xstring_ptr_view::GetBuffer(void)
0x180171bf4  mov     this, qword ptr [rsp+1B0h+strUriFull.m_encodedStorage.___u0]; this
0x180171bf9  mov     rbx, rax
0x180171bfc  call    ?GetCount@xstring_ptr_view@@QEBAIXZ; xstring_ptr_view::GetCount(void)
0x180171c01  mov     edx, eax
0x180171c03  mov     r9, r12
0x180171c06  mov     rax, rdi
0x180171c09  mov     spBaseUri, rbx
0x180171c0c  mov     this, rsi
0x180171c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171c14  mov     ebx, eax
0x180171c16  test    eax, eax
0x180171c18  js      loc_180171EDA
0x180171c1e  lea     rdi, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x180171c25  test    r13d, r13d
0x180171c28  jnz     loc_180171FB7
0x180171c2e  mov     eax, cs:?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B.Count; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null ...
0x180171c34  movsd   xmm0, qword ptr cs:?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B.___u0; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null ...
0x180171c3c  mov     dword ptr [rsp+1B0h+strComponentName.m_ephemeralStorage.Count], eax
0x180171c40  lea     rax, [rbp+0B0h+baseResourceUriStrBuilder.m_inlineBuffer]
0x180171c44  mov     qword ptr [rsp+1B0h+strComponentName.m_encodedStorage.___u0], rdi
0x180171c49  movsd   qword ptr [rsp+1B0h+strComponentName.m_ephemeralStorage.___u0], xmm0
0x180171c4f  cmp     [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer], rax
0x180171c53  jz      short loc_180171C63
0x180171c55  mov     this, [rbp+0B0h+baseResourceUriStrBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180171c59  call    cs:__imp_WindowsDeleteStringBuffer
0x180171c5f  mov     [rbp+0B0h+baseResourceUriStrBuilder.m_hPreallocatedBuffer], r15
0x180171c63  mov     this, [rsp+1B0h+spBaseResourceUri.m_ptr]
0x180171c68  mov     [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer], r15
0x180171c6c  test    this, this
0x180171c6f  jz      short loc_180171C82
0x180171c71  mov     [rsp+1B0h+spBaseResourceUri.m_ptr], r15
0x180171c76  mov     rax, [this]
0x180171c79  mov     rax, [rax+10h]
0x180171c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171c82  mov     this, [rsp+1B0h+spMsResourceBaseUri.m_ptr]
0x180171c87  test    this, this
0x180171c8a  jz      short loc_180171C9D
0x180171c8c  mov     [rsp+1B0h+spMsResourceBaseUri.m_ptr], r15
0x180171c91  mov     rax, [this]
0x180171c94  mov     rax, [rax+10h]
0x180171c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171c9d  lea     this, [rsp+1B0h+strFilePath]; this
0x180171ca2  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180171ca7  lea     this, [rsp+1B0h+strResourceMap]; this
0x180171cac  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180171cb1  xor     eax, eax
0x180171cb3  jmp     loc_180171D58
0x180171cb8  mov     ebx, 8000FFFFh
0x180171cbd  call    OnNewFailure_2955_
0x180171cc2  xor     r15d, r15d
0x180171cc5  mov     ecx, ebx; failedFrameHR
0x180171cc7  call    OnFailure_2990_
0x180171ccc  mov     eax, cs:?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B.Count; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null ...
0x180171cd2  lea     rdi, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x180171cd9  movsd   xmm0, qword ptr cs:?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B.___u0; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null ...
0x180171ce1  mov     dword ptr [rsp+1B0h+strComponentName.m_ephemeralStorage.Count], eax
0x180171ce5  lea     rax, [rbp+0B0h+baseResourceUriStrBuilder.m_inlineBuffer]
0x180171ce9  mov     qword ptr [rsp+1B0h+strComponentName.m_encodedStorage.___u0], rdi
0x180171cee  movsd   qword ptr [rsp+1B0h+strComponentName.m_ephemeralStorage.___u0], xmm0
0x180171cf4  cmp     [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer], rax
0x180171cf8  jz      short loc_180171D08
0x180171cfa  mov     this, [rbp+0B0h+baseResourceUriStrBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180171cfe  call    cs:__imp_WindowsDeleteStringBuffer
0x180171d04  mov     [rbp+0B0h+baseResourceUriStrBuilder.m_hPreallocatedBuffer], r15
0x180171d08  mov     this, [rsp+1B0h+spBaseResourceUri.m_ptr]
0x180171d0d  mov     [rbp+0B0h+baseResourceUriStrBuilder.m_pBuffer], r15
0x180171d11  test    this, this
0x180171d14  jz      short loc_180171D27
0x180171d16  mov     [rsp+1B0h+spBaseResourceUri.m_ptr], r15
0x180171d1b  mov     rax, [this]
0x180171d1e  mov     rax, [rax+10h]
0x180171d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171d27  mov     this, [rsp+1B0h+spMsResourceBaseUri.m_ptr]
0x180171d2c  test    this, this
  ... truncated ...
```
