# ConvertStringToTypedCValue

- ea: `0x1800d260c`
- end: `0x1800d2fd5`
- name: `ConvertStringToTypedCValue`
- size: `2505`
- prototype: `HRESULT __fastcall(CCoreServices *pCore, const xstring_ptr *strClrTypeName, const xstring_ptr *strText, CValue *pValue)`
- caller_count: `2`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d0998`
- `0x1800d36f0`

## callees

- `0x180004bc0`
- `0x18001f3c0`
- `0x180020740`
- `0x180021970`
- `0x18004486c`
- `0x1800710d0`
- `0x18007a328`
- `0x180090880`
- `0x1800ab600`
- `0x1800d260c`
- `0x1800d2fdc`
- `0x1800d497c`
- `0x1800f85d0`
- `0x1800fe130`
- `0x180100b70`
- `0x180131190`
- `0x1802be9cc`
- `0x1804e7328`
- `0x1805d5540`
- `0x1806877a8`
- `0x180687890`
- `0x180687a78`
- `0x18069f6ac`
- `0x1806c4d84`
- `0x18076e110`
- `0x18076f08c`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d2a59`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d2c54`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d2e02`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d2e4c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d2a59`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d2c54`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d2e02`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d2e4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d28dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d28dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d2a0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d2c05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d2a0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d2c05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800d2681`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800d2681`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800d27e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800d2843`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800d2bd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800d2c81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800d27e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800d2843`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800d2bd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800d2c81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2d50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2d50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d2c9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d2cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d2c9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d2cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2d02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2d02`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall ConvertStringToTypedCValue(
        CCoreServices *pCore,
        const xstring_ptr *strClrTypeName,
        const xstring_ptr *strText,
        CValue *pValue)
{
  int v7; // eax
  HRESULT v8; // ebx
  unsigned __int64 RuntimeStringHandleMarker; // rcx
  int v10; // edi
  UINT32 StringLen; // edi
  unsigned __int64 v12; // rax
  PCWSTR StringRawBuffer; // r14
  __int64 v14; // rcx
  unsigned int v15; // edx
  int v16; // eax
  HSTRING v17; // rcx
  HSTRING v18; // rcx
  unsigned int v19; // eax
  HRESULT v20; // eax
  CDependencyObject *v22; // rbx
  unsigned __int64 v23; // rax
  int v24; // ebx
  const xstring_ptr_storage *Storage; // rcx
  HSTRING_BUFFER__ *m_hPreallocatedBuffer; // rdi
  const CClassInfo *BuiltinClassInfoByName; // rax
  const CClassInfo *v28; // rdi
  const xstring_ptr_storage *v29; // rcx
  int v30; // ebx
  HSTRING_BUFFER__ *v31; // rdi
  HRESULT v32; // ecx
  unsigned __int64 v33; // rcx
  int v34; // eax
  UINT32 v35; // eax
  unsigned __int64 m_ptr; // rbx
  int v37; // edx
  HSTRING v38; // rax
  UINT32 v39; // edx
  int String; // eax
  int v41; // edx
  HRESULT (__fastcall *m_pfnCreate)(CDependencyObject **, CREATEPARAMETERS *); // rbx
  HRESULT v43; // eax
  KnownTypeIndex v44; // ax
  const CClassInfo *ClassInformation; // rax
  HRESULT v46; // ecx
  CDependencyObject *v47; // rdx
  const wchar_t *v48; // rax
  UINT32 v49; // edx
  int v50; // eax
  HSTRING v51; // rcx
  CDependencyObject *v52; // rbx
  const xstring_ptr_storage *v53; // rax
  __int128 v54; // xmm0
  unsigned int v55; // edi
  CDependencyObject *v56; // rbx
  CDependencyObject *v57; // rbx
  XRECTF_WH *v58; // rax
  CDependencyObject *v59; // rbx
  const xstring_ptr_storage *FailFast; // rax
  CDependencyObject_vtbl *v61; // xmm0_8
  unsigned int RuntimeStringHandleMarker_high; // ecx
  CDependencyObject *v63; // rdi
  unsigned int v64; // xmm6_4
  unsigned int pcStowedExceptions[2]; // [rsp+28h] [rbp-E0h] BYREF
  xref_ptr<CDependencyObject> pDO; // [rsp+30h] [rbp-D8h] BYREF
  xref_ptr<CDependencyObject> v67; // [rsp+38h] [rbp-D0h] BYREF
  XRECTF_RB *pXf; // [rsp+40h] [rbp-C8h] BYREF
  xstring_ptr v69; // [rsp+48h] [rbp-C0h] BYREF
  xstring_ptr_view strTypeName; // [rsp+50h] [rbp-B8h] BYREF
  HSTRING_BUFFER__ *v71; // [rsp+58h] [rbp-B0h] BYREF
  int v72; // [rsp+60h] [rbp-A8h]
  xstring_ptr_view v73; // [rsp+64h] [rbp-A4h] BYREF
  _BYTE v74[52]; // [rsp+6Ch] [rbp-9Ch] OVERLAPPED BYREF
  TStringBuilder<96> coreTypeNameBuilder; // [rsp+A0h] [rbp-68h] BYREF

  *(_QWORD *)&v74[28] = pCore;
  *(_QWORD *)&coreTypeNameBuilder.m_cBuffer = 0;
  *(_QWORD *)&v74[12] = 0;
  *(_QWORD *)&v74[20] = 0;
  coreTypeNameBuilder.m_hPreallocatedBuffer = (HSTRING_BUFFER__ *)&coreTypeNameBuilder.m_inlineBuffer[4];
  *(_QWORD *)coreTypeNameBuilder.m_inlineBuffer = 96;
  *(_OWORD *)&v74[36] = 0;
  v7 = WindowsPreallocateStringBuffer(
         0x60u,
         (WCHAR **)&coreTypeNameBuilder.m_hPreallocatedBuffer,
         (HSTRING_BUFFER *)&coreTypeNameBuilder.m_cBuffer);
  v8 = v7;
  if ( v7 < 0 )
  {
    OnFailure_2990_(v7);
    OnFailure_2990_(v8);
    goto LABEL_27;
  }
  *(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2] = 0;
  wcscpy(coreTypeNameBuilder.m_inlineBuffer, L"a");
  *(_WORD *)coreTypeNameBuilder.m_hPreallocatedBuffer = 63;
  ++*(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2];
  *((_WORD *)coreTypeNameBuilder.m_hPreallocatedBuffer + *(unsigned int *)&coreTypeNameBuilder.m_inlineBuffer[2]) = 0;
  RuntimeStringHandleMarker = strClrTypeName->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (strClrTypeName->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v18 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v10 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
    if ( v10 >= 0 )
    {
      StringLen = v10 & 0x3FFFFFFF;
      goto LABEL_5;
    }
    v18 = *(HSTRING *)RuntimeStringHandleMarker;
  }
  StringLen = WindowsGetStringLen(v18);
LABEL_5:
  v12 = strClrTypeName->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (strClrTypeName->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v17 = (HSTRING)(v12 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    StringRawBuffer = *(PCWSTR *)v12;
    if ( *(int *)(v12 + 8) >= 0 )
      goto LABEL_7;
    v17 = *(HSTRING *)v12;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v17, 0);
LABEL_7:
  if ( !StringLen )
    goto LABEL_41;
  v14 = *(unsigned int *)&coreTypeNameBuilder.m_inlineBuffer[2];
  if ( *(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2] + StringLen < *(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2] )
    goto LABEL_39;
  v15 = *(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2] + StringLen + 1;
  if ( v15 < *(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2] )
    goto LABEL_39;
  v16 = *(_DWORD *)coreTypeNameBuilder.m_inlineBuffer;
  if ( v15 < *(_DWORD *)coreTypeNameBuilder.m_inlineBuffer )
  {
LABEL_11:
    memcpy_0((char *)coreTypeNameBuilder.m_hPreallocatedBuffer + 2 * v14, StringRawBuffer, 2LL * StringLen);
    *(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2] += StringLen;
    *((_WORD *)coreTypeNameBuilder.m_hPreallocatedBuffer + *(unsigned int *)&coreTypeNameBuilder.m_inlineBuffer[2]) = 0;
    goto LABEL_41;
  }
  if ( StringLen >= *(_DWORD *)coreTypeNameBuilder.m_inlineBuffer )
  {
    LODWORD(v14) = 96;
    if ( !*(_DWORD *)coreTypeNameBuilder.m_inlineBuffer )
      v16 = 96;
    v19 = v15 + v16;
  }
  else
  {
    if ( *(_DWORD *)coreTypeNameBuilder.m_inlineBuffer >= 0x7FFFFFFFu )
    {
LABEL_39:
      v8 = -2147418113;
      OnNewFailure_2955_(v14);
      goto LABEL_40;
    }
    v19 = 2 * *(_DWORD *)coreTypeNameBuilder.m_inlineBuffer;
  }
  if ( v19 < v15 )
    goto LABEL_39;
  v20 = TStringBuilder<96>::ExpandBuffer((TStringBuilder<96> *)&coreTypeNameBuilder.m_hPreallocatedBuffer, v19);
  v8 = v20;
  if ( v20 >= 0 )
  {
    v14 = *(unsigned int *)&coreTypeNameBuilder.m_inlineBuffer[2];
    goto LABEL_11;
  }
  OnFailure_2990_(v20);
LABEL_40:
  OnFailure_2990_(v8);
  if ( v8 < 0 )
  {
    OnFailure_2990_(v8);
LABEL_117:
    CREATEPARAMETERS::~CREATEPARAMETERS((CREATEPARAMETERS *)&v74[12]);
    TStringBuilder<16>::~TStringBuilder<16>((TStringBuilder<96> *)&coreTypeNameBuilder.m_hPreallocatedBuffer);
    return (unsigned int)v8;
  }
LABEL_41:
  v24 = *(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2];
  Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  m_hPreallocatedBuffer = coreTypeNameBuilder.m_hPreallocatedBuffer;
  strTypeName.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  if ( *(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2] > 0x3FFFFFFFu )
  {
    pDO.m_ptr = 0;
    pcStowedExceptions[0] = 0;
    TraceForFailFast(-2147418113);
    OnNewFailureEncountered(-2147418113, 0, 0);
    GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&pDO, pcStowedExceptions);
    RoFailFastWithErrorContextInternal2(
      -2147418113,
      pcStowedExceptions[0],
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)pDO.m_ptr);
    Storage = strTypeName.m_encodedStorage.Storage;
  }
  v71 = m_hPreallocatedBuffer;
  v72 = v24 & 0x3FFFFFFF | 0x40000000;
  if ( ((unsigned __int8)Storage & 1) != 0 )
    WindowsDeleteString((HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL));
  strTypeName.m_encodedStorage.Storage = (const xstring_ptr_storage *)&v71;
  BuiltinClassInfoByName = DirectUI::MetadataAPI::GetBuiltinClassInfoByName(&strTypeName);
  v71 = 0;
  strTypeName.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  v28 = BuiltinClassInfoByName;
  v72 = 0;
  if ( !BuiltinClassInfoByName )
  {
    v29 = &xstring_ptr_constants::c_xstring_ptr_storage_null;
    v73.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
    *(_WORD *)coreTypeNameBuilder.m_hPreallocatedBuffer = 46;
    v30 = *(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2];
    v31 = coreTypeNameBuilder.m_hPreallocatedBuffer;
    if ( *(_DWORD *)&coreTypeNameBuilder.m_inlineBuffer[2] > 0x3FFFFFFFu )
    {
      pDO.m_ptr = 0;
      pcStowedExceptions[0] = 0;
      TraceForFailFast(-2147418113);
      OnNewFailureEncountered(-2147418113, 0, 0);
      GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&pDO, pcStowedExceptions);
      RoFailFastWithErrorContextInternal2(
        -2147418113,
        pcStowedExceptions[0],
        (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)pDO.m_ptr);
      v29 = v73.m_encodedStorage.Storage;
    }
    *(_QWORD *)v74 = v31;
    *(_DWORD *)&v74[8] = v30 & 0x3FFFFFFF | 0x40000000;
    if ( ((unsigned __int8)v29 & 1) != 0 )
      WindowsDeleteString((HSTRING)((unsigned __int64)v29 & 0xFFFFFFFFFFFFFFFEuLL));
    v73.m_encodedStorage.Storage = (const xstring_ptr_storage *)v74;
    v28 = DirectUI::MetadataAPI::GetBuiltinClassInfoByName(&v73);
    *(_QWORD *)v74 = 0;
    *(_DWORD *)&v74[8] = 0;
    v73.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
    if ( !v28 )
    {
      v28 = DirectUI::MetadataAPI::GetBuiltinClassInfoByName(strClrTypeName);
      if ( !v28 )
      {
        OnFailure_1414_(v32);
        CREATEPARAMETERS::~CREATEPARAMETERS((CREATEPARAMETERS *)&v74[12]);
        if ( (wchar_t *)coreTypeNameBuilder.m_hPreallocatedBuffer != &coreTypeNameBuilder.m_inlineBuffer[4] )
          WindowsDeleteStringBuffer(*(HSTRING_BUFFER *)&coreTypeNameBuilder.m_cBuffer);
        return 2148468943LL;
      }
    }
  }
  v33 = strText->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (strText->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v51 = (HSTRING)(v33 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v34 = *(_DWORD *)(v33 + 8);
    if ( v34 >= 0 )
    {
      v35 = v34 & 0x3FFFFFFF;
      goto LABEL_55;
    }
    v51 = *(HSTRING *)v33;
  }
  v35 = WindowsGetStringLen(v51);
LABEL_55:
  if ( !v35 )
    goto LABEL_68;
  m_ptr = strText->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (strText->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    String = WindowsDuplicateString((HSTRING)(m_ptr & 0xFFFFFFFFFFFFFFFEuLL), (HSTRING *)&pDO);
    if ( String < 0 )
    {
LABEL_62:
      OnFailure_2990_(String);
      pXf = 0;
      pcStowedExceptions[0] = 0;
      TraceForFailFast(-2147418113);
      OnNewFailureEncountered(-2147418113, 0, 0);
      GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&pXf, pcStowedExceptions);
      RoFailFastWithErrorContextInternal2(
        -2147418113,
        pcStowedExceptions[0],
        (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)pXf);
      m_ptr = (unsigned __int64)pDO.m_ptr;
      goto LABEL_63;
    }
    goto LABEL_94;
  }
  if ( m_ptr )
  {
    v37 = *(_DWORD *)(m_ptr + 8);
    if ( (v37 & 0x40000000) != 0 )
    {
      pcStowedExceptions[0] = 0;
      v38 = *(HSTRING *)m_ptr;
      if ( v37 < 0 )
      {
        v38 = (HSTRING)WindowsGetStringRawBuffer(*(HSTRING *)m_ptr, pcStowedExceptions);
        v39 = pcStowedExceptions[0];
      }
      else
      {
        v39 = v37 & 0x3FFFFFFF;
        pcStowedExceptions[0] = v39;
      }
      String = WindowsCreateString((PCNZWCH)v38, v39, (HSTRING *)&pDO);
      if ( String < 0 )
        goto LABEL_62;
LABEL_94:
      m_ptr = (unsigned __int64)pDO.m_ptr | 1;
    }
  }
LABEL_63:
  v69.m_encodedStorage.Storage = (const xstring_ptr_storage *)m_ptr;
  CValue::ReleaseAndReset((CValue *)&v74[12]);
  *(_DWORD *)&v74[20] = *(_DWORD *)&v74[20] & 0xFFFFFF80 | 0x4E;
  if ( (m_ptr & 1) != 0 )
  {
    v50 = WindowsDuplicateString((HSTRING)(m_ptr & 0xFFFFFFFFFFFFFFFEuLL), (HSTRING *)&pDO);
    if ( v50 < 0 )
    {
LABEL_89:
      OnFailure_2990_(v50);
      pXf = 0;
      pcStowedExceptions[0] = 0;
      TraceForFailFast(-2147418113);
      OnNewFailureEncountered(-2147418113, 0, 0);
      GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&pXf, pcStowedExceptions);
      RoFailFastWithErrorContextInternal2(
        -2147418113,
        pcStowedExceptions[0],
        (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)pXf);
      LODWORD(m_ptr) = pDO.m_ptr;
      goto LABEL_67;
    }
LABEL_96:
    m_ptr = (unsigned __int64)pDO.m_ptr | 1;
    goto LABEL_66;
  }
  if ( !m_ptr )
  {
    m_ptr = 0;
    goto LABEL_66;
  }
  v41 = *(_DWORD *)(m_ptr + 8);
  if ( (v41 & 0x40000000) != 0 )
  {
    pcStowedExceptions[0] = 0;
    v48 = *(const wchar_t **)m_ptr;
    if ( v41 < 0 )
    {
      v48 = WindowsGetStringRawBuffer(*(HSTRING *)m_ptr, pcStowedExceptions);
      v49 = pcStowedExceptions[0];
    }
    else
    {
      v49 = v41 & 0x3FFFFFFF;
      pcStowedExceptions[0] = v49;
    }
    v50 = WindowsCreateString(v48, v49, (HSTRING *)&pDO);
    if ( v50 < 0 )
      goto LABEL_89;
    goto LABEL_96;
  }
LABEL_66:
  pDO.m_ptr = (CDependencyObject *)m_ptr;
LABEL_67:
  *(_DWORD *)&v74[16] = HIDWORD(pDO.m_ptr);
  *(_DWORD *)&v74[12] = m_ptr;
  xstring_ptr::~xstring_ptr(&v69);
LABEL_68:
  if ( v28->m_nIndex < (XYFocusNavigationStrategy|IVectorOfUri) )
  {
    m_pfnCreate = c_aTypeActivations[(unsigned __int16)v28->m_nIndex].m_pfnCreate;
    if ( m_pfnCreate )
    {
      v67.m_ptr = 0;
      xref_ptr<CDependencyObject>::DecrementRefCount(&v67);
      v43 = m_pfnCreate(&v67.m_ptr, (CREATEPARAMETERS *)&v74[12]);
      v8 = v43;
      if ( v43 >= 0 )
      {
        v44 = v67.m_ptr->GetTypeIndex(v67.m_ptr);
        if ( v44 == Color )
        {
          LODWORD(v22) = v67.m_ptr[1].__vftable;
          CValue::ReleaseAndReset(pValue);
          pValue->m_flags.m_state.m_asOne &= 0xFFFFFFCF;
          pValue->m_flags.m_state.m_asOne |= 0x4Fu;
          goto LABEL_32;
        }
        if ( v44 == Double )
        {
          v64 = (unsigned int)v67.m_ptr[1].__vftable;
          CValue::ReleaseAndReset(pValue);
          pValue->m_flags.m_state.m_asOne &= 0xFFFFFFC8;
          pValue->m_flags.m_state.m_asOne |= 0x48u;
          pValue->m_value.m_any[0] = v64;
          goto LABEL_33;
        }
        if ( v44 != GridLength )
        {
          switch ( v44 )
          {
            case Int32:
              LODWORD(v22) = v67.m_ptr[1].__vftable;
              CValue::ReleaseAndReset(pValue);
              pValue->m_flags.m_state.m_asOne &= 0xFFFFFFC4;
              pValue->m_flags.m_state.m_asOne |= 0x44u;
              goto LABEL_32;
            case Point:
              v59 = v67.m_ptr;
              FailFast = (const xstring_ptr_storage *)XcpAllocation::OSMemoryAllocateFailFast(8u);
              v61 = v59[1].__vftable;
              v55 = (unsigned int)FailFast;
              v69.m_encodedStorage.Storage = FailFast;
              FailFast->Buffer = (const wchar_t *)v61;
              CValue::ReleaseAndReset(pValue);
              pValue->m_flags.m_state.m_asOne &= 0xFFFFFFD0;
              pValue->m_flags.m_state.m_asOne |= 0x50u;
              break;
            case Rect:
              v57 = v67.m_ptr;
              v58 = (XRECTF_WH *)XcpAllocation::OSMemoryAllocateFailFast(0x10u);
              *v58 = *(XRECTF_WH *)&v57[1].__vftable;
              CValue::Set<18>(pValue, v58);
              goto LABEL_33;
            case String:
              v56 = v67.m_ptr;
              if ( !xencoded_string_ptr::IsNull((xencoded_string_ptr *)&v67.m_ptr[1]) )
              {
                CValue::SetString(pValue, (const xstring_ptr *)&v56[1]);
                goto LABEL_33;
              }
LABEL_116:
              OnFailure_977_(v46);
              xref_ptr<CDependencyObject>::DecrementRefCount(&v67);
              v8 = -2147467259;
              goto LABEL_117;
            case Thickness:
              v52 = v67.m_ptr;
              v53 = (const xstring_ptr_storage *)XcpAllocation::OSMemoryAllocateFailFast(0x10u);
              v54 = *(_OWORD *)&v52[1].__vftable;
              v69.m_encodedStorage.Storage = v53;
              v55 = (unsigned int)v53;
              *(_OWORD *)&v53->Buffer = v54;
              CValue::ReleaseAndReset(pValue);
              pValue->m_flags.m_state.m_asOne &= 0xFFFFFFD3;
              pValue->m_flags.m_state.m_asOne |= 0x53u;
              break;
            default:
              ClassInformation = CDependencyObject::GetClassInformation(v67.m_ptr);
              if ( ClassInformation->m_nIndex != Enumerated && (ClassInformation->m_flags & 0x800) == 0 )
              {
                if ( !CDependencyObject::OfTypeByIndex<305>(v67.m_ptr) )
                {
                  v47 = v67.m_ptr;
                  v67.m_ptr = 0;
                  CValue::Set<24>(pValue, v47);
                  goto LABEL_33;
                }
                goto LABEL_116;
              }
              v22 = v67.m_ptr;
              if ( (CDependencyObject::GetClassInformation(v67.m_ptr)->m_flags & 0x20000) != 0 )
              {
                CValue::SetEnum8(pValue, (unsigned __int8)v22[1].__vftable);
                goto LABEL_33;
              }
              LODWORD(v22) = v22[1].__vftable;
              pDO.m_ptr = (CDependencyObject *)(unsigned int)v22;
              CValue::ReleaseAndReset(pValue);
              pValue->m_flags.m_state.m_asOne &= 0xFFFFFFC3;
              pValue->m_flags.m_state.m_asOne |= 0x43u;
              v23 = (unsigned __int64)pDO.m_ptr >> 32;
              goto LABEL_31;
          }
          RuntimeStringHandleMarker_high = HIDWORD(v69.m_encodedStorage.RuntimeStringHandleMarker);
          pValue->m_value.m_any[0] = v55;
          pValue->m_value.m_any[1] = RuntimeStringHandleMarker_high;
          goto LABEL_33;
        }
        v63 = v67.m_ptr;
        v22 = (CDependencyObject *)XcpAllocation::OSMemoryAllocateFailFast(8u);
        if ( v22 )
        {
          *(_WORD *)((char *)&v22->__vftable + 1) = 0;
          BYTE3(v22->__vftable) = 0;
        }
        else
        {
          v22 = 0;
        }
        v22->__vftable = v63[1].__vftable;
        pDO.m_ptr = v22;
        CValue::ReleaseAndReset(pValue);
        pValue->m_flags.m_state.m_asOne &= 0xFFFFFFD4;
        pValue->m_flags.m_state.m_asOne |= 0x54u;
        LODWORD(v23) = HIDWORD(pDO.m_ptr);
LABEL_31:
        pValue->m_value.m_any[1] = v23;
LABEL_32:
        pValue->m_value.m_any[0] = (unsigned int)v22;
LABEL_33:
        xref_ptr<CDependencyObject>::DecrementRefCount(&v67);
        if ( *(_QWORD *)&v74[44] )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v74[44]);
        CValue::ReleaseAndReset((CValue *)&v74[12]);
        if ( (wchar_t *)coreTypeNameBuilder.m_hPreallocatedBuffer != &coreTypeNameBuilder.m_inlineBuffer[4] )
          WindowsDeleteStringBuffer(*(HSTRING_BUFFER *)&coreTypeNameBuilder.m_cBuffer);
        return 0;
      }
      OnFailure_2990_(v43);
      xref_ptr<CDependencyObject>::DecrementRefCount(&v67);
LABEL_27:
      CREATEPARAMETERS::~CREATEPARAMETERS((CREATEPARAMETERS *)&v74[12]);
      if ( (wchar_t *)coreTypeNameBuilder.m_hPreallocatedBuffer != &coreTypeNameBuilder.m_inlineBuffer[4] )
        WindowsDeleteStringBuffer(*(HSTRING_BUFFER *)&coreTypeNameBuilder.m_cBuffer);
      return (unsigned int)v8;
    }
  }
  CREATEPARAMETERS::~CREATEPARAMETERS((CREATEPARAMETERS *)&v74[12]);
  if ( (wchar_t *)coreTypeNameBuilder.m_hPreallocatedBuffer != &coreTypeNameBuilder.m_inlineBuffer[4] )
    WindowsDeleteStringBuffer(*(HSTRING_BUFFER *)&coreTypeNameBuilder.m_cBuffer);
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800d260c  mov     rax, rsp
0x1800d260f  mov     [rax+8], rbx
0x1800d2613  push    rbp
0x1800d2614  push    rsi
0x1800d2615  push    rdi
0x1800d2616  push    r12
0x1800d2618  push    r13
0x1800d261a  push    r14
0x1800d261c  push    r15
0x1800d261e  lea     rbp, [rax-0D8h]
0x1800d2625  sub     rsp, 1A0h
0x1800d262c  movaps  xmmword ptr [rax-48h], xmm6
0x1800d2630  mov     rax, cs:__security_cookie
0x1800d2637  xor     rax, rsp
0x1800d263a  mov     [rbp+0D0h+var_50], rax
0x1800d2641  xor     r13d, r13d
0x1800d2644  mov     [rbp+0D0h+cp.m_spServiceProviderContext._Ptr], pCore
0x1800d2648  mov     r12, strText
0x1800d264b  mov     qword ptr [rbp+0D0h+coreTypeNameBuilder.m_cBuffer], r13
0x1800d264f  mov     r15, strClrTypeName
0x1800d2652  mov     qword ptr [rsp+1D0h+cp.m_value.m_flags], r13
0x1800d2657  lea     rax, [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+8]
0x1800d265b  mov     [rsp+1D0h+cp.m_pCore], r13
0x1800d2660  lea     edi, [r13+60h]
0x1800d2664  mov     [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer], rax
0x1800d2668  xorps   xmm0, xmm0
0x1800d266b  mov     qword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer], rdi
0x1800d266f  mov     ecx, edi; length
0x1800d2671  lea     strText, [rbp+0D0h+coreTypeNameBuilder.m_cBuffer]; bufferHandle
0x1800d2675  lea     strClrTypeName, [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer]; charBuffer
0x1800d2679  mov     rsi, pValue
0x1800d267c  movdqu  xmmword ptr [rbp+0D0h+cp.m_spServiceProviderContext._Rep], xmm0
0x1800d2681  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800d2687  mov     ebx, eax
0x1800d2689  test    eax, eax
0x1800d268b  js      loc_1800D27A9
0x1800d2691  mov     rax, [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer]
0x1800d2695  lea     ecx, [rdi+1]
0x1800d2698  mov     edx, r13d
0x1800d269b  mov     dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+4], edx
0x1800d269e  mov     dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer], ecx
0x1800d26a1  mov     word ptr [rax+strClrTypeName*2], 3Fh ; '?'
0x1800d26a7  mov     eax, dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+4]
0x1800d26aa  inc     eax
0x1800d26ac  mov     dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+4], eax
0x1800d26af  mov     edx, eax
0x1800d26b1  mov     rax, [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer]
0x1800d26b5  mov     [rax+strClrTypeName*2], r13w
0x1800d26ba  mov     pCore, [r15]
0x1800d26bd  test    cl, 1
0x1800d26c0  jnz     loc_1800D2754
0x1800d26c6  mov     edi, [pCore+8]
0x1800d26c9  test    edi, edi
0x1800d26cb  js      loc_1800D2D15
0x1800d26d1  and     edi, 3FFFFFFFh
0x1800d26d7  mov     rax, [r15]
0x1800d26da  test    al, 1
0x1800d26dc  jnz     short loc_1800D2740
0x1800d26de  mov     r14, [rax]
0x1800d26e1  cmp     [rax+8], r13d
0x1800d26e5  jl      loc_1800D287A
0x1800d26eb  test    edi, edi
0x1800d26ed  jz      loc_1800D289B
0x1800d26f3  mov     ecx, dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+4]; failedFrameHR
0x1800d26f6  lea     edx, [pCore+rdi]
0x1800d26f9  cmp     edx, ecx
0x1800d26fb  jb      loc_1800D2882
0x1800d2701  inc     edx
0x1800d2703  cmp     edx, ecx
0x1800d2705  jb      loc_1800D2882
0x1800d270b  mov     eax, dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer]
0x1800d270e  cmp     edx, eax
0x1800d2710  jnb     short loc_1800D2765
0x1800d2712  mov     rax, [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer]
0x1800d2716  mov     strClrTypeName, r14; Src
0x1800d2719  mov     r8d, edi
0x1800d271c  add     strText, strText; Size
0x1800d271f  lea     pCore, [rax+pCore*2]; void *
0x1800d2723  call    memcpy_0
0x1800d2728  mov     eax, dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+4]
0x1800d272b  add     eax, edi
0x1800d272d  mov     dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+4], eax
0x1800d2730  mov     edx, eax
0x1800d2732  mov     rax, [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer]
0x1800d2736  mov     [rax+strClrTypeName*2], r13w
0x1800d273b  jmp     loc_1800D289B
0x1800d2740  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800d2744  mov     pCore, rax; string
0x1800d2747  xor     edx, edx; length
0x1800d2749  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d274f  mov     r14, rax
0x1800d2752  jmp     short loc_1800D26EB
0x1800d2754  and     pCore, 0FFFFFFFFFFFFFFFEh; string
0x1800d2758  call    cs:__imp_WindowsGetStringLen
0x1800d275e  mov     edi, eax
0x1800d2760  jmp     loc_1800D26D7
0x1800d2765  cmp     edi, eax
0x1800d2767  jnb     short loc_1800D279B
0x1800d2769  cmp     eax, 7FFFFFFFh
0x1800d276e  jnb     loc_1800D2D22
0x1800d2774  add     eax, eax
0x1800d2776  cmp     eax, edx
0x1800d2778  jb      loc_1800D2DAD
0x1800d277e  mov     edx, eax; uNewBufferSize
0x1800d2780  lea     pCore, [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer]; this
0x1800d2784  call    ?ExpandBuffer@?$TStringBuilder@$0GA@@@AEAAJI@Z; TStringBuilder<96>::ExpandBuffer(uint)
0x1800d2789  mov     ebx, eax
0x1800d278b  test    eax, eax
0x1800d278d  js      loc_1800D2DA1
0x1800d2793  mov     ecx, dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+4]
0x1800d2796  jmp     loc_1800D2712
0x1800d279b  test    eax, eax
0x1800d279d  mov     ecx, 60h ; '`'
0x1800d27a2  cmovz   eax, ecx
0x1800d27a5  add     eax, edx
0x1800d27a7  jmp     short loc_1800D2776
0x1800d27a9  mov     ecx, ebx; failedFrameHR
0x1800d27ab  call    OnFailure_2990_
0x1800d27b0  mov     ecx, ebx; failedFrameHR
0x1800d27b2  call    OnFailure_2990_
0x1800d27b7  jmp     short loc_1800D27CA
0x1800d27b9  mov     ecx, ebx; failedFrameHR
0x1800d27bb  call    OnFailure_2990_
0x1800d27c0  lea     pCore, [rsp+1D0h+var_1A0]; this
0x1800d27c5  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x1800d27ca  lea     pCore, [rsp+1D0h+cp.m_value.m_flags]; this
0x1800d27cf  call    ??1CREATEPARAMETERS@@QEAA@XZ; CREATEPARAMETERS::~CREATEPARAMETERS(void)
0x1800d27d4  lea     rax, [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+8]
0x1800d27d8  cmp     [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer], rax
0x1800d27dc  jz      short loc_1800D27E8
0x1800d27de  mov     pCore, qword ptr [rbp+0D0h+coreTypeNameBuilder.m_cBuffer]; bufferHandle
0x1800d27e2  call    cs:__imp_WindowsDeleteStringBuffer
0x1800d27e8  mov     eax, ebx
0x1800d27ea  jmp     short loc_1800D284B
0x1800d27ec  mov     ebx, [rbx+60h]
0x1800d27ef  mov     dword ptr [rsp+1D0h+pDO.m_ptr], ebx
0x1800d27f3  mov     dword ptr [rsp+1D0h+pDO.m_ptr+4], r13d
0x1800d27f8  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x1800d27fd  and     dword ptr [rsi+8], 0FFFFFFC3h
0x1800d2801  or      dword ptr [rsi+8], 43h
0x1800d2805  mov     rax, [rsp+1D0h+pDO.m_ptr]
0x1800d280a  shr     rax, 20h
0x1800d280e  mov     [rsi+4], eax
0x1800d2811  mov     [rsi], ebx
0x1800d2813  lea     pCore, [rsp+1D0h+var_1A0]; this
0x1800d2818  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x1800d281d  mov     pCore, [rbp+0D0h+var_140]; this
0x1800d2821  test    pCore, pCore
0x1800d2824  jz      short loc_1800D282B
0x1800d2826  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d282b  lea     pCore, [rsp+1D0h+cp.m_value.m_flags]; this
0x1800d2830  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x1800d2835  lea     rax, [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+8]
0x1800d2839  cmp     [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer], rax
0x1800d283d  jz      short loc_1800D2849
0x1800d283f  mov     pCore, qword ptr [rbp+0D0h+coreTypeNameBuilder.m_cBuffer]; bufferHandle
0x1800d2843  call    cs:__imp_WindowsDeleteStringBuffer
0x1800d2849  xor     eax, eax
0x1800d284b  mov     pCore, [rbp+0D0h+var_50]
0x1800d2852  xor     pCore, rsp; StackCookie
0x1800d2855  call    __security_check_cookie
0x1800d285a  lea     r11, [rsp+1D0h+var_30]
0x1800d2862  mov     rbx, [r11+40h]
0x1800d2866  movaps  xmm6, xmmword ptr [r11-10h]
0x1800d286b  mov     rsp, r11
0x1800d286e  pop     r15
0x1800d2870  pop     r14
0x1800d2872  pop     r13
0x1800d2874  pop     r12
0x1800d2876  pop     rdi
0x1800d2877  pop     rsi
0x1800d2878  pop     rbp
0x1800d2879  retn
0x1800d287a  mov     pCore, r14
0x1800d287d  jmp     loc_1800D2747
0x1800d2882  mov     ebx, 8000FFFFh
0x1800d2887  call    OnNewFailure_2955_
0x1800d288c  mov     ecx, ebx; failedFrameHR
0x1800d288e  call    OnFailure_2990_
0x1800d2893  test    ebx, ebx
0x1800d2895  js      loc_1800D2DBC
0x1800d289b  mov     ebx, dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+4]
0x1800d289e  lea     pCore, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800d28a5  mov     rdi, [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer]
0x1800d28a9  mov     r14d, 8000FFFFh
0x1800d28af  mov     qword ptr [rsp+1D0h+strTypeName.m_encodedStorage.___u0], pCore
0x1800d28b4  cmp     ebx, 3FFFFFFFh
0x1800d28ba  ja      loc_1800D2DC8
0x1800d28c0  and     ebx, 3FFFFFFFh
0x1800d28c6  mov     qword ptr [rsp+1D0h+var_180], rdi
0x1800d28cb  bts     ebx, 1Eh
0x1800d28cf  mov     dword ptr [rsp+1D0h+var_17C+4], ebx
0x1800d28d3  test    cl, 1
0x1800d28d6  jz      short loc_1800D28E2
0x1800d28d8  and     pCore, 0FFFFFFFFFFFFFFFEh; string
0x1800d28dc  call    cs:__imp_WindowsDeleteString
0x1800d28e2  lea     rax, [rsp+1D0h+var_180]
0x1800d28e7  lea     pCore, [rsp+1D0h+strTypeName]; strTypeName
0x1800d28ec  mov     qword ptr [rsp+1D0h+strTypeName.m_encodedStorage.___u0], rax
0x1800d28f1  call    ?GetBuiltinClassInfoByName@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@AEBVxstring_ptr_view@@@Z; DirectUI::MetadataAPI::GetBuiltinClassInfoByName(xstring_ptr_view const &)
0x1800d28f6  mov     qword ptr [rsp+1D0h+var_180], r13
0x1800d28fb  lea     strClrTypeName, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800d2902  mov     qword ptr [rsp+1D0h+strTypeName.m_encodedStorage.___u0], strClrTypeName
0x1800d2907  mov     rdi, rax
0x1800d290a  mov     dword ptr [rsp+1D0h+var_17C+4], r13d
0x1800d290f  test    rax, rax
0x1800d2912  jnz     loc_1800D29A4
0x1800d2918  mov     rax, [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer]
0x1800d291c  mov     pCore, strClrTypeName
0x1800d291f  mov     qword ptr [rsp+1D0h+var_174.m_encodedStorage.___u0], strClrTypeName
0x1800d2924  mov     word ptr [rax], 2Eh ; '.'
0x1800d2929  mov     ebx, dword ptr [rbp+0D0h+coreTypeNameBuilder.m_inlineBuffer+4]
0x1800d292c  mov     rdi, [rbp+0D0h+coreTypeNameBuilder.m_hPreallocatedBuffer]
0x1800d2930  cmp     ebx, 3FFFFFFFh
0x1800d2936  ja      loc_1800D2E12
0x1800d293c  and     ebx, 3FFFFFFFh
0x1800d2942  mov     qword ptr [rsp+1D0h+var_16C], rdi
0x1800d2947  bts     ebx, 1Eh
0x1800d294b  mov     dword ptr [rsp+1D0h+cp.m_value.m_value+4], ebx
0x1800d294f  test    cl, 1
0x1800d2952  jz      short loc_1800D295E
0x1800d2954  and     pCore, 0FFFFFFFFFFFFFFFEh; string
0x1800d2958  call    cs:__imp_WindowsDeleteString
0x1800d295e  lea     rax, [rsp+1D0h+var_16C]
0x1800d2963  lea     pCore, [rsp+1D0h+var_174]; strTypeName
0x1800d2968  mov     qword ptr [rsp+1D0h+var_174.m_encodedStorage.___u0], rax
0x1800d296d  call    ?GetBuiltinClassInfoByName@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@AEBVxstring_ptr_view@@@Z; DirectUI::MetadataAPI::GetBuiltinClassInfoByName(xstring_ptr_view const &)
0x1800d2972  mov     rdi, rax
0x1800d2975  mov     qword ptr [rsp+1D0h+var_16C], r13
0x1800d297a  mov     dword ptr [rsp+1D0h+cp.m_value.m_value+4], r13d
0x1800d297f  lea     rax, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800d2986  mov     qword ptr [rsp+1D0h+var_174.m_encodedStorage.___u0], rax
0x1800d298b  test    rdi, rdi
0x1800d298e  jnz     short loc_1800D29A4
0x1800d2990  mov     pCore, r15; strTypeName
0x1800d2993  call    ?GetBuiltinClassInfoByName@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@AEBVxstring_ptr_view@@@Z; DirectUI::MetadataAPI::GetBuiltinClassInfoByName(xstring_ptr_view const &)
0x1800d2998  mov     rdi, rax
0x1800d299b  test    rax, rax
0x1800d299e  jz      loc_1800D2C64
0x1800d29a4  mov     pCore, [r12]
0x1800d29a8  test    cl, 1
0x1800d29ab  jnz     loc_1800D2CFE
0x1800d29b1  mov     eax, [pCore+8]
0x1800d29b4  test    eax, eax
0x1800d29b6  js      loc_1800D2D1D
0x1800d29bc  and     eax, 3FFFFFFFh
0x1800d29c1  test    eax, eax
0x1800d29c3  jz      loc_1800D2ABB
0x1800d29c9  mov     rbx, [r12]
0x1800d29cd  test    bl, 1
0x1800d29d0  jnz     loc_1800D2C91
0x1800d29d6  test    rbx, rbx
0x1800d29d9  jz      loc_1800D2A64
0x1800d29df  mov     edx, [rbx+8]
0x1800d29e2  bt      edx, 1Eh
0x1800d29e6  jnb     short loc_1800D2A64
0x1800d29e8  mov     [rsp+1D0h+pcStowedExceptions], r13d
0x1800d29ed  mov     rax, [rbx]
0x1800d29f0  test    edx, edx
0x1800d29f2  js      loc_1800D2D31
0x1800d29f8  and     edx, 3FFFFFFFh; length
0x1800d29fe  mov     [rsp+1D0h+pcStowedExceptions], edx
0x1800d2a02  lea     strText, [rsp+1D0h+pDO]; string
0x1800d2a07  mov     pCore, rax; sourceString
0x1800d2a0a  call    cs:__imp_WindowsCreateString
0x1800d2a10  test    eax, eax
0x1800d2a12  jns     loc_1800D2CAB
0x1800d2a18  mov     ecx, eax; failedFrameHR
0x1800d2a1a  call    OnFailure_2990_
0x1800d2a1f  mov     ecx, r14d; errorCode
0x1800d2a22  mov     [rsp+1D0h+pXf], r13
0x1800d2a27  mov     [rsp+1D0h+pcStowedExceptions], r13d
0x1800d2a2c  call    TraceForFailFast
0x1800d2a31  xor     r8d, r8d; contextRecord
0x1800d2a34  xor     edx, edx; directCallerReturnAddress
0x1800d2a36  mov     ecx, r14d; failedFrameHR
0x1800d2a39  call    OnNewFailureEncountered
0x1800d2a3e  lea     strClrTypeName, [rsp+1D0h+pcStowedExceptions]; pcStowedExceptions
0x1800d2a43  lea     pCore, [rsp+1D0h+pXf]; pppStowedExceptions
0x1800d2a48  call    GetStowedExceptionsForFailFast
0x1800d2a4d  mov     strText, [rsp+1D0h+pXf]
0x1800d2a52  mov     ecx, r14d
0x1800d2a55  mov     edx, [rsp+1D0h+pcStowedExceptions]
0x1800d2a59  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1800d2a5f  mov     rbx, [rsp+1D0h+pDO.m_ptr]
0x1800d2a64  lea     pCore, [rsp+1D0h+cp.m_value.m_flags]; this
0x1800d2a69  mov     qword ptr [rsp+1D0h+var_190.m_encodedStorage.___u0], rbx
0x1800d2a6e  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x1800d2a73  mov     eax, dword ptr [rsp+1D0h+cp.m_pCore]
0x1800d2a77  and     eax, 0FFFFFFCEh
0x1800d2a7a  or      eax, 4Eh
0x1800d2a7d  mov     dword ptr [rsp+1D0h+cp.m_pCore], eax
0x1800d2a81  test    bl, 1
0x1800d2a84  jnz     loc_1800D2CB9
0x1800d2a8a  test    rbx, rbx
0x1800d2a8d  jz      loc_1800D2D0D
0x1800d2a93  mov     edx, [rbx+8]
0x1800d2a96  bt      edx, 1Eh
0x1800d2a9a  jb      loc_1800D2BE3
0x1800d2aa0  mov     [rsp+1D0h+pDO.m_ptr], rbx
  ... truncated ...
```
