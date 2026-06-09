# CustomWriterRuntimeObjectCreator::BuildObjectWriterSettings(ObjectWriterSettings *)

- ea: `0x1800466bc`
- end: `0x180046edf`
- name: `?BuildObjectWriterSettings@CustomWriterRuntimeObjectCreator@@AEAAJPEAVObjectWriterSettings@@@Z`
- size: `2083`
- prototype: `HRESULT __fastcall(CustomWriterRuntimeObjectCreator *this, ObjectWriterSettings *pResult)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046238`

## callees

- `0x180004bc0`
- `0x18001f3c0`
- `0x1800217b8`
- `0x180021840`
- `0x180021970`
- `0x18002d990`
- `0x1800466bc`
- `0x180046ee8`
- `0x18006cfd0`
- `0x1800710d0`
- `0x18008e368`
- `0x1800ab600`
- `0x180131190`
- `0x1806877a8`
- `0x180687890`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046eab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046eab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004681d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004681d`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180046d9a`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180046d9a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180046d8a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180046d8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046c86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046c86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180046db4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180046db4`

## pseudocode

```c
__int64 __fastcall CustomWriterRuntimeObjectCreator::BuildObjectWriterSettings(
        CustomWriterRuntimeObjectCreator *this,
        ObjectWriterSettings *pResult)
{
  const CustomWriterRuntimeContext *m_context; // rax
  CDependencyObject *GetValue; // rbx
  IPALUri *m_ptr; // rdi
  CDependencyObject_vtbl *v6; // r15
  CAutomationPeer *(__fastcall *GetPopupAssociatedAutomationPeer)(CDependencyObject *); // rax
  ObjectWriterCallbacksDelegate *GetAPChildren; // rax
  std::_Ref_count_base *v9; // r15
  INameScope *OnCreateAutomationPeerImpl; // r12
  CDependencyObject_vtbl *v11; // r8
  volatile signed __int32 *SetValue; // rdx
  signed __int32 v13; // eax
  signed __int32 v14; // ett
  HANDLE ProcessHeap; // rax
  unsigned int m_ptr_high; // r14d
  _DWORD *v17; // rax
  _DWORD *v18; // rdi
  XamlQualifiedObject *v19; // r13
  KnownTypeIndex v20; // ax
  bool v21; // al
  int v22; // eax
  HRESULT v23; // eax
  HRESULT v24; // r14d
  std::_Ref_count_base *v25; // rbx
  __int64 v26; // r14
  __int64 v27; // rax
  XamlQualifiedObject *v28; // rax
  std::_Ref_count_base *v29; // r14
  std::_Ref_count_base *Rep; // rdi
  std::_Ref_count_base *v31; // rdi
  std::_Ref_count_base *v32; // rdi
  std::_Ref_count_base *v33; // rdi
  std::_Ref_count_base *v34; // rdi
  xref_ptr<INameScope> *p_m_spNameScope; // rdi
  INameScope *v36; // rcx
  xref_ptr<IPALUri> *p_m_spBaseUri; // rdi
  IPALUri *v38; // rcx
  xref_ptr<IPALUri> *p_m_spXamlResourceUri; // rdi
  IPALUri *v40; // rcx
  xstring_ptr *p_m_xbfHash; // rdi
  CDependencyObject *v42; // rax
  int v43; // edx
  const CClassInfo *ClassInfoByIndex; // rax
  wchar_t *Buffer; // rax
  UINT32 v47; // edx
  int String; // eax
  int v49; // eax
  INameScope *FailFast; // rax
  UINT32 length[2]; // [rsp+20h] [rbp-99h] BYREF
  xref_ptr<CDependencyObject> v52; // [rsp+28h] [rbp-91h] BYREF
  CValue source; // [rsp+30h] [rbp-89h] BYREF
  XamlQualifiedObject *v54; // [rsp+40h] [rbp-79h]
  ObjectWriterCallbacksDelegate *v55; // [rsp+48h] [rbp-71h]
  IPALUri *v56; // [rsp+50h] [rbp-69h]
  const xstring_ptr_storage *Storage; // [rsp+58h] [rbp-61h]
  ObjectWriterSettings objectWriterSettings; // [rsp+60h] [rbp-59h] BYREF

  Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
  objectWriterSettings.m_xbfHash.m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
  m_context = this->m_context;
  GetValue = (CDependencyObject *)this;
  v54 = (XamlQualifiedObject *)this;
  memset((void *)&objectWriterSettings.m_qoRootObjectInstance, 0, 64);
  m_ptr = m_context->m_baseUri.m_ptr;
  objectWriterSettings.m_spXamlResourceUri.m_ptr = 0;
  *(_WORD *)&objectWriterSettings.m_bExpandTemplates = 0;
  objectWriterSettings.m_bEnableEncoding = 0;
  v56 = m_ptr;
  if ( m_ptr )
    m_ptr->AddRef(m_ptr);
  v6 = GetValue->__vftable;
  objectWriterSettings.m_spBaseUri.m_ptr = m_ptr;
  GetPopupAssociatedAutomationPeer = v6->GetPopupAssociatedAutomationPeer;
  if ( GetPopupAssociatedAutomationPeer )
    _InterlockedIncrement((volatile signed __int32 *)GetPopupAssociatedAutomationPeer + 2);
  GetAPChildren = (ObjectWriterCallbacksDelegate *)v6->GetAPChildren;
  v9 = (std::_Ref_count_base *)v6->GetPopupAssociatedAutomationPeer;
  v55 = GetAPChildren;
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)&v9->_Uses);
  objectWriterSettings.m_spObjectWriterCallbacks._Ptr = GetAPChildren;
  objectWriterSettings.m_spObjectWriterCallbacks._Rep = v9;
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v9->_Uses, 0xFFFFFFFF) == 1 )
    {
      v9->_Destroy(v9);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v9->_Weaks, 0xFFFFFFFF) == 1 )
        v9->_Delete_this(v9);
    }
  }
  if ( HIDWORD(GetValue->m_strName.m_encodedStorage.RuntimeStringHandleMarker) )
  {
    FailFast = (INameScope *)XcpAllocation::OSMemoryAllocateFailFast(0x10u);
    OnCreateAutomationPeerImpl = FailFast;
    if ( FailFast )
    {
      HIDWORD(FailFast[1].__vftable) = 0;
      FailFast->__vftable = (INameScope_vtbl *)NullNameScopeHelper::`vftable';
      LODWORD(FailFast[1].__vftable) = 1;
    }
    else
    {
      OnCreateAutomationPeerImpl = 0;
    }
    source.m_value = 0;
    objectWriterSettings.m_spNameScope.m_ptr = OnCreateAutomationPeerImpl;
    xref_ptr<INameScope>::DecrementRefCount((xref_ptr<CMemorySurface> *)&source);
  }
  else
  {
    OnCreateAutomationPeerImpl = (INameScope *)GetValue->OnCreateAutomationPeerImpl;
    if ( OnCreateAutomationPeerImpl )
      OnCreateAutomationPeerImpl->AddRef((struct INameScope *)GetValue->OnCreateAutomationPeerImpl);
    objectWriterSettings.m_spNameScope.m_ptr = OnCreateAutomationPeerImpl;
  }
  v11 = GetValue->__vftable;
  LODWORD(GetValue) = 0;
  v52.m_ptr = 0;
  SetValue = (volatile signed __int32 *)v11->SetValue;
  if ( SetValue )
  {
    v13 = *SetValue;
    while ( v13 )
    {
      v14 = v13;
      v13 = _InterlockedCompareExchange(SetValue, v13 + 1, v13);
      if ( v14 == v13 )
      {
        GetValue = (CDependencyObject *)v11->GetValue;
        v52.m_ptr = GetValue;
        break;
      }
    }
  }
  ProcessHeap = ghHeap;
  m_ptr_high = HIDWORD(v52.m_ptr);
  if ( !ghHeap )
  {
    ProcessHeap = GetProcessHeap();
    ghHeap = ProcessHeap;
  }
  v17 = HeapAlloc(ProcessHeap, 0, 0x28u);
  v18 = v17;
  if ( v17 )
  {
    _InterlockedAdd64(&g_allocatedMemory, 0x28u);
    v17[2] = 1;
    v17[3] = 1;
    *(_QWORD *)v17 = std::_Ref_count_obj2<XamlQualifiedObject>::`vftable';
    *((_QWORD *)v17 + 2) = 0;
    *((_QWORD *)v17 + 3) = 0;
    *((_QWORD *)v17 + 4) = 0;
  }
  else
  {
    TerminateProcessOnMemoryExhaustion(0x28u);
    v18 = 0;
  }
  source.m_value = 0;
  v19 = (XamlQualifiedObject *)(v18 + 4);
  source.m_flags = 0;
  CValue::ReleaseAndReset(&source);
  *(_QWORD *)length = __PAIR64__(m_ptr_high, (unsigned int)GetValue);
  source.m_flags.m_state.m_asOne = source.m_flags.m_state.m_asOne & 0xFFFFFF80 | 0x58;
  source.m_value = (CValueDetails::Value)__PAIR64__(m_ptr_high, (unsigned int)GetValue);
  if ( __PAIR64__(m_ptr_high, (unsigned int)GetValue) )
    CDependencyObject::AddRef((CDependencyObject *)__PAIR64__(m_ptr_high, (unsigned int)GetValue));
  *(_QWORD *)length = __PAIR64__(m_ptr_high, (unsigned int)GetValue);
  if ( __PAIR64__(m_ptr_high, (unsigned int)GetValue)
    && ((v20 = (*(unsigned __int16 (__fastcall **)(unsigned __int64))(*(_QWORD *)__PAIR64__(
                                                                                   m_ptr_high,
                                                                                   (unsigned int)GetValue)
                                                                    + 600LL))(__PAIR64__(m_ptr_high, (unsigned int)GetValue)),
         v20 == TextElement)
     || ((unsigned __int16)v20 >= (XYFocusNavigationStrategy|IVectorOfUri)
       ? (ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex(v20),
          v21 = DirectUI::MetadataAPI::CompareCustomTypesHelper(ClassInfoByIndex, TextElement))
       : (v21 = LOBYTE(c_aTypeCheckData[(unsigned __int16)v20].m_handle) == 47),
         v21)) )
  {
    v22 = 0;
  }
  else
  {
    v22 = 16;
  }
  v19->m_typeToken.m_Data = 0;
  v18[5] = v22;
  v23 = CValue::CopyConverted((CValue *)(v18 + 6), &source);
  v24 = v23;
  if ( v23 < 0 )
  {
    v19 = 0;
    v25 = 0;
    OnFailure_2990_(v23);
    OnFailure_2990_(v24);
    CValue::ReleaseAndReset(&source);
    if ( v18 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v18);
  }
  else
  {
    v18[5] &= ~0x10u;
    if ( v18 )
      _InterlockedIncrement(v18 + 2);
    v25 = (std::_Ref_count_base *)v18;
    CValue::ReleaseAndReset(&source);
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(_DWORD *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    v24 = 0;
  }
  xref_ptr<CDependencyObject>::DecrementRefCount(&v52);
  if ( v24 >= 0 )
  {
    if ( v25 )
      _InterlockedIncrement((volatile signed __int32 *)&v25->_Uses);
    objectWriterSettings.m_qoEventRoot._Ptr = v19;
    objectWriterSettings.m_qoEventRoot._Rep = v25;
    v26 = *(_QWORD *)&v54->m_typeToken.m_Data;
    v27 = *(_QWORD *)(*(_QWORD *)&v54->m_typeToken.m_Data + 56LL);
    if ( v27 )
      _InterlockedIncrement((volatile signed __int32 *)(v27 + 8));
    v28 = *(XamlQualifiedObject **)(v26 + 48);
    v29 = *(std::_Ref_count_base **)(v26 + 56);
    v54 = v28;
    if ( v29 )
      _InterlockedIncrement((volatile signed __int32 *)&v29->_Uses);
    objectWriterSettings.m_qoXBindConnector._Ptr = v28;
    objectWriterSettings.m_qoXBindConnector._Rep = v29;
    if ( v29 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v29->_Uses, 0xFFFFFFFF) == 1 )
      {
        v29->_Destroy(v29);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v29->_Weaks, 0xFFFFFFFF) == 1 )
          v29->_Delete_this(v29);
      }
    }
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)&v9->_Uses);
    pResult->m_spObjectWriterCallbacks._Ptr = v55;
    Rep = pResult->m_spObjectWriterCallbacks._Rep;
    pResult->m_spObjectWriterCallbacks._Rep = v9;
    if ( Rep )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Rep->_Uses, 0xFFFFFFFF) == 1 )
      {
        Rep->_Destroy(Rep);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Rep->_Weaks, 0xFFFFFFFF) == 1 )
          Rep->_Delete_this(Rep);
      }
    }
    pResult->m_qoRootObjectInstance._Ptr = 0;
    v31 = pResult->m_qoRootObjectInstance._Rep;
    pResult->m_qoRootObjectInstance._Rep = 0;
    if ( v31 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v31->_Uses, 0xFFFFFFFF) == 1 )
      {
        v31->_Destroy(v31);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v31->_Weaks, 0xFFFFFFFF) == 1 )
          v31->_Delete_this(v31);
      }
    }
    if ( v25 )
      _InterlockedIncrement((volatile signed __int32 *)&v25->_Uses);
    pResult->m_qoEventRoot._Ptr = v19;
    v32 = pResult->m_qoEventRoot._Rep;
    pResult->m_qoEventRoot._Rep = v25;
    if ( v32 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v32->_Uses, 0xFFFFFFFF) == 1 )
      {
        v32->_Destroy(v32);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v32->_Weaks, 0xFFFFFFFF) == 1 )
          v32->_Delete_this(v32);
      }
    }
    if ( v29 )
      _InterlockedIncrement((volatile signed __int32 *)&v29->_Uses);
    pResult->m_qoXBindConnector._Ptr = v54;
    v33 = pResult->m_qoXBindConnector._Rep;
    pResult->m_qoXBindConnector._Rep = v29;
    if ( v33 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v33->_Uses, 0xFFFFFFFF) == 1 )
      {
        v33->_Destroy(v33);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v33->_Weaks, 0xFFFFFFFF) == 1 )
          v33->_Delete_this(v33);
      }
    }
    pResult->m_qoParentXBindConnector._Ptr = 0;
    v34 = pResult->m_qoParentXBindConnector._Rep;
    pResult->m_qoParentXBindConnector._Rep = 0;
    if ( v34 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v34->_Uses, 0xFFFFFFFF) == 1 )
      {
        v34->_Destroy(v34);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v34->_Weaks, 0xFFFFFFFF) == 1 )
          v34->_Delete_this(v34);
      }
    }
    p_m_spNameScope = &pResult->m_spNameScope;
    if ( &pResult->m_spNameScope != &objectWriterSettings.m_spNameScope )
    {
      v36 = p_m_spNameScope->m_ptr;
      p_m_spNameScope->m_ptr = OnCreateAutomationPeerImpl;
      if ( v36 )
        v36->Release(v36);
      if ( p_m_spNameScope->m_ptr )
        p_m_spNameScope->m_ptr->AddRef(p_m_spNameScope->m_ptr);
    }
    p_m_spBaseUri = &pResult->m_spBaseUri;
    if ( &pResult->m_spBaseUri != &objectWriterSettings.m_spBaseUri )
    {
      v38 = p_m_spBaseUri->m_ptr;
      p_m_spBaseUri->m_ptr = v56;
      if ( v38 )
        v38->Release(v38);
      if ( p_m_spBaseUri->m_ptr )
        p_m_spBaseUri->m_ptr->AddRef(p_m_spBaseUri->m_ptr);
    }
    p_m_spXamlResourceUri = &pResult->m_spXamlResourceUri;
    if ( &pResult->m_spXamlResourceUri != &objectWriterSettings.m_spXamlResourceUri )
    {
      v40 = p_m_spXamlResourceUri->m_ptr;
      p_m_spXamlResourceUri->m_ptr = 0;
      if ( v40 )
        v40->Release(v40);
      if ( p_m_spXamlResourceUri->m_ptr )
        p_m_spXamlResourceUri->m_ptr->AddRef(p_m_spXamlResourceUri->m_ptr);
    }
    p_m_xbfHash = &pResult->m_xbfHash;
    if ( &pResult->m_xbfHash == &objectWriterSettings.m_xbfHash )
      goto LABEL_100;
    v42 = (CDependencyObject *)Storage;
    if ( ((unsigned __int8)Storage & 1) != 0 )
    {
      v49 = WindowsDuplicateString((HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL), (HSTRING *)&v52);
      if ( v49 < 0 )
      {
        OnFailure_2990_(v49);
        goto LABEL_110;
      }
    }
    else
    {
      if ( !Storage )
      {
        v42 = 0;
        goto LABEL_96;
      }
      v43 = *((_DWORD *)Storage + 2);
      if ( (v43 & 0x40000000) == 0 )
      {
LABEL_96:
        v52.m_ptr = v42;
LABEL_97:
        if ( (p_m_xbfHash->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
          WindowsDeleteString((HSTRING)(p_m_xbfHash->m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
        p_m_xbfHash->m_encodedStorage.Storage = (const xstring_ptr_storage *)v52.m_ptr;
LABEL_100:
        *(_WORD *)&pResult->m_bExpandTemplates = 0;
        pResult->m_bEnableEncoding = 0;
        if ( v25 && _InterlockedExchangeAdd((volatile signed __int32 *)&v25->_Uses, 0xFFFFFFFF) == 1 )
        {
          v25->_Destroy(v25);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v25->_Weaks, 0xFFFFFFFF) == 1 )
            v25->_Delete_this(v25);
        }
        ObjectWriterSettings::~ObjectWriterSettings(&objectWriterSettings);
        return 0;
      }
      length[0] = 0;
      Buffer = (wchar_t *)Storage->Buffer;
      if ( v43 < 0 )
      {
        Buffer = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)Buffer, length);
        v47 = length[0];
      }
      else
      {
        v47 = v43 & 0x3FFFFFFF;
        length[0] = v47;
      }
      String = WindowsCreateString(Buffer, v47, (HSTRING *)&v52);
      if ( String < 0 )
      {
        OnFailure_2990_(String);
LABEL_110:
        source.m_value = 0;
        length[0] = 0;
        TraceForFailFast(-2147418113);
        OnNewFailureEncountered(-2147418113, 0, 0);
        GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&source, length);
        RoFailFastWithErrorContextInternal2(
          -2147418113,
          length[0],
          *(struct _STOWED_EXCEPTION_INFORMATION_V2 **const *)&source.m_value);
        goto LABEL_97;
      }
    }
    v52.m_ptr = (CDependencyObject *)((unsigned __int64)v52.m_ptr | 1);
    goto LABEL_97;
  }
  OnFailure_2990_(v24);
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  ObjectWriterSettings::~ObjectWriterSettings(&objectWriterSettings);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1800466bc  mov     [rsp-8+arg_10], rbx
0x1800466c1  push    rbp
0x1800466c2  push    rsi
0x1800466c3  push    rdi
0x1800466c4  push    r12
0x1800466c6  push    r13
0x1800466c8  push    r14
0x1800466ca  push    r15
0x1800466cc  lea     rbp, [rsp-27h]
0x1800466d1  sub     rsp, 0E0h
0x1800466d8  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800466df  xor     r13d, r13d
0x1800466e2  xorps   xmm0, xmm0
0x1800466e5  mov     [rbp+57h+var_B8], rax
0x1800466e9  xorps   xmm1, xmm1
0x1800466ec  mov     qword ptr [rbp+57h+objectWriterSettings.m_xbfHash.m_encodedStorage.___u0], rax
0x1800466f0  mov     rax, [this]
0x1800466f3  mov     rsi, pResult
0x1800466f6  mov     rbx, this
0x1800466f9  mov     [rbp+57h+var_D0], this
0x1800466fd  movdqa  xmmword ptr [rbp+57h+objectWriterSettings.m_qoRootObjectInstance._Ptr], xmm0
0x180046702  movdqa  xmmword ptr [rbp+57h+objectWriterSettings.m_qoEventRoot._Ptr], xmm1
0x180046707  mov     rdi, [rax+40h]
0x18004670b  movdqa  xmmword ptr [rbp+57h+objectWriterSettings.m_qoXBindConnector._Ptr], xmm0
0x180046710  movdqa  xmmword ptr [rbp+57h+objectWriterSettings.m_qoParentXBindConnector._Ptr], xmm1
0x180046715  mov     [rbp+57h+objectWriterSettings.m_spXamlResourceUri.m_ptr], r13
0x180046719  mov     word ptr [rbp+57h+objectWriterSettings.m_bExpandTemplates], r13w
0x18004671e  mov     [rbp+57h+objectWriterSettings.m_bEnableEncoding], r13b
0x180046722  mov     [rbp+57h+var_C0], rdi
0x180046726  test    rdi, rdi
0x180046729  jz      short loc_18004673A
0x18004672b  mov     rax, [rdi]
0x18004672e  mov     this, rdi
0x180046731  mov     rax, [rax+8]
0x180046735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004673a  mov     r15, [rbx]
0x18004673d  mov     [rbp+57h+objectWriterSettings.m_spBaseUri.m_ptr], rdi
0x180046741  mov     rax, [r15+78h]
0x180046745  test    rax, rax
0x180046748  jz      short loc_18004674E
0x18004674a  lock inc dword ptr [rax+8]
0x18004674e  mov     rax, [r15+70h]
0x180046752  mov     r15, [r15+78h]
0x180046756  mov     [rbp+57h+var_C8], rax
0x18004675a  test    r15, r15
0x18004675d  jz      short loc_180046764
0x18004675f  lock inc dword ptr [r15+8]
0x180046764  or      edi, 0FFFFFFFFh
0x180046767  mov     [rbp+57h+objectWriterSettings.m_spObjectWriterCallbacks._Ptr], rax
0x18004676b  mov     [rbp+57h+objectWriterSettings.m_spObjectWriterCallbacks._Rep], r15
0x18004676f  test    r15, r15
0x180046772  jz      short loc_1800467A9
0x180046774  mov     eax, edi
0x180046776  lock xadd [r15+8], eax
0x18004677c  add     eax, edi
0x18004677e  jnz     short loc_1800467A9
0x180046780  mov     rax, [r15]
0x180046783  mov     this, r15
0x180046786  mov     rax, [rax]
0x180046789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004678e  mov     eax, edi
0x180046790  lock xadd [r15+0Ch], eax
0x180046796  add     eax, edi
0x180046798  jnz     short loc_1800467A9
0x18004679a  mov     rax, [r15]
0x18004679d  mov     this, r15
0x1800467a0  mov     rax, [rax+8]
0x1800467a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467a9  cmp     [rbx+1Ch], r13d
0x1800467ad  jnz     loc_180046DCD
0x1800467b3  mov     rax, [rbx]
0x1800467b6  mov     r12, [rax+68h]
0x1800467ba  test    r12, r12
0x1800467bd  jz      short loc_1800467CE
0x1800467bf  mov     rax, [r12]
0x1800467c3  mov     this, r12
0x1800467c6  mov     rax, [rax]
0x1800467c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467ce  mov     [rbp+57h+objectWriterSettings.m_spNameScope.m_ptr], r12
0x1800467d2  mov     r8, [rbx]
0x1800467d5  mov     rbx, r13
0x1800467d8  mov     [rsp+110h+var_E8.m_ptr], rbx
0x1800467dd  mov     pResult, [r8+28h]
0x1800467e1  test    pResult, pResult
0x1800467e4  jz      short loc_1800467FF
0x1800467e6  mov     eax, [pResult]
0x1800467e8  nop
0x1800467e9  test    eax, eax
0x1800467eb  jz      short loc_1800467FF
0x1800467ed  lea     ecx, [rax+1]
0x1800467f0  lock cmpxchg [pResult], ecx
0x1800467f4  jnz     short loc_1800467E9
0x1800467f6  mov     rbx, [r8+20h]
0x1800467fa  mov     [rsp+110h+var_E8.m_ptr], rbx
0x1800467ff  mov     rax, cs:?ghHeap@@3PEAXEA; void * ghHeap
0x180046806  mov     r14d, dword ptr [rsp+110h+var_E8.m_ptr+4]
0x18004680b  test    rax, rax
0x18004680e  jz      loc_180046EAB
0x180046814  xor     edx, edx; dwFlags
0x180046816  mov     this, rax; hHeap
0x180046819  lea     r8d, [pResult+28h]; dwBytes
0x18004681d  call    cs:__imp_HeapAlloc
0x180046823  mov     rdi, rax
0x180046826  test    rax, rax
0x180046829  jz      loc_180046D95
0x18004682f  lock add cs:?g_allocatedMemory@@3_JA, 28h ; '('; __int64 g_allocatedMemory
0x180046838  mov     dword ptr [rax+8], 1
0x18004683f  mov     dword ptr [rax+0Ch], 1
0x180046846  lea     rax, ??_7?$_Ref_count_obj2@UXamlQualifiedObject@@@std@@6B@; const std::_Ref_count_obj2<XamlQualifiedObject>::`vftable'
0x18004684d  mov     [rdi], rax
0x180046850  mov     [rdi+10h], r13
0x180046854  mov     [rdi+18h], r13
0x180046858  mov     [rdi+20h], r13
0x18004685c  xor     eax, eax
0x18004685e  lea     this, [rsp+110h+source]; this
0x180046863  mov     qword ptr [rsp+110h+source.m_value], rax
0x180046868  lea     r13, [rdi+10h]
0x18004686c  mov     qword ptr [rsp+110h+source.m_flags], rax
0x180046871  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180046876  mov     eax, dword ptr [rsp+110h+source.m_flags]
0x18004687a  and     eax, 0FFFFFFD8h
0x18004687d  mov     [rsp+110h+length], ebx
0x180046881  or      eax, 58h
0x180046884  mov     [rsp+110h+length+4], r14d
0x180046889  mov     this, qword ptr [rsp+110h+length]; this
0x18004688e  mov     dword ptr [rsp+110h+source.m_flags], eax
0x180046892  mov     dword ptr [rsp+110h+source.m_value], ebx
0x180046896  mov     dword ptr [rsp+110h+source.m_value+4], r14d
0x18004689b  test    this, this
0x18004689e  jz      short loc_1800468A5
0x1800468a0  call    ?AddRef@CDependencyObject@@QEAAXXZ; CDependencyObject::AddRef(void)
0x1800468a5  mov     [rsp+110h+length], ebx
0x1800468a9  mov     [rsp+110h+length+4], r14d
0x1800468ae  mov     this, qword ptr [rsp+110h+length]
0x1800468b3  test    this, this
0x1800468b6  jz      loc_180046E48
0x1800468bc  mov     rax, [this]
0x1800468bf  mov     rax, [rax+258h]
0x1800468c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468cb  mov     ebx, 11Dh
0x1800468d0  cmp     bx, ax
0x1800468d3  jz      short loc_1800468FF
0x1800468d5  mov     ecx, 43Ch
0x1800468da  cmp     ax, cx
0x1800468dd  jnb     loc_180046CFF
0x1800468e3  movzx   eax, ax
0x1800468e6  lea     this, ?c_aTypeCheckData@@3QBUTypeCheckData@@B.m_handle; TypeCheckData const near * const c_aTypeCheckData ...
0x1800468ed  add     rax, rax
0x1800468f0  cmp     byte ptr [this+rax*8], 2Fh ; '/'
0x1800468f4  setz    al
0x1800468f7  test    al, al
0x1800468f9  jz      loc_180046E48
0x1800468ff  xor     eax, eax
0x180046901  mov     dword ptr [r13+0], 0
0x180046909  lea     this, [r13+8]; this
0x18004690d  lea     pResult, [rsp+110h+source]; source
0x180046912  mov     [r13+4], eax
0x180046916  call    ?CopyConverted@CValue@@QEAAJAEBV1@@Z; CValue::CopyConverted(CValue const &)
0x18004691b  mov     r14d, eax
0x18004691e  test    eax, eax
0x180046920  js      loc_180046E13
0x180046926  and     dword ptr [r13+4], 0FFFFFFEFh
0x18004692b  test    rdi, rdi
0x18004692e  jz      short loc_180046934
0x180046930  lock inc dword ptr [rdi+8]
0x180046934  lea     this, [rsp+110h+source]; this
0x180046939  mov     rbx, rdi
0x18004693c  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180046941  test    rdi, rdi
0x180046944  jz      short loc_180046981
0x180046946  or      r14d, 0FFFFFFFFh
0x18004694a  mov     eax, r14d
0x18004694d  lock xadd [rdi+8], eax
0x180046952  add     eax, r14d
0x180046955  jnz     short loc_180046981
0x180046957  mov     rax, [rdi]
0x18004695a  mov     this, rdi
0x18004695d  mov     rax, [rax]
0x180046960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046965  mov     eax, r14d
0x180046968  lock xadd [rdi+0Ch], eax
0x18004696d  add     eax, r14d
0x180046970  jnz     short loc_180046981
0x180046972  mov     rax, [rdi]
0x180046975  mov     this, rdi
0x180046978  mov     rax, [rax+8]
0x18004697c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046981  xor     r14d, r14d
0x180046984  lea     this, [rsp+110h+var_E8]; this
0x180046989  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x18004698e  test    r14d, r14d
0x180046991  js      loc_180046E85
0x180046997  test    rbx, rbx
0x18004699a  jz      short loc_1800469A0
0x18004699c  lock inc dword ptr [rbx+8]
0x1800469a0  mov     r14, [rbp+57h+var_D0]
0x1800469a4  mov     [rbp+57h+objectWriterSettings.m_qoEventRoot._Ptr], r13
0x1800469a8  mov     [rbp+57h+objectWriterSettings.m_qoEventRoot._Rep], rbx
0x1800469ac  mov     r14, [r14]
0x1800469af  mov     rax, [r14+38h]
0x1800469b3  test    rax, rax
0x1800469b6  jz      short loc_1800469BC
0x1800469b8  lock inc dword ptr [rax+8]
0x1800469bc  mov     rax, [r14+30h]
0x1800469c0  mov     r14, [r14+38h]
0x1800469c4  mov     [rbp+57h+var_D0], rax
0x1800469c8  test    r14, r14
0x1800469cb  jz      short loc_1800469D2
0x1800469cd  lock inc dword ptr [r14+8]
0x1800469d2  mov     [rbp+57h+objectWriterSettings.m_qoXBindConnector._Ptr], rax
0x1800469d6  mov     [rbp+57h+objectWriterSettings.m_qoXBindConnector._Rep], r14
0x1800469da  test    r14, r14
0x1800469dd  jz      short loc_180046A18
0x1800469df  or      eax, 0FFFFFFFFh
0x1800469e2  lock xadd [r14+8], eax
0x1800469e8  cmp     eax, 1
0x1800469eb  jnz     short loc_180046A18
0x1800469ed  mov     rax, [r14]
0x1800469f0  mov     this, r14
0x1800469f3  mov     rax, [rax]
0x1800469f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469fb  or      eax, 0FFFFFFFFh
0x1800469fe  lock xadd [r14+0Ch], eax
0x180046a04  cmp     eax, 1
0x180046a07  jnz     short loc_180046A18
0x180046a09  mov     rax, [r14]
0x180046a0c  mov     this, r14
0x180046a0f  mov     rax, [rax+8]
0x180046a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a18  test    r15, r15
0x180046a1b  jz      short loc_180046A22
0x180046a1d  lock inc dword ptr [r15+8]
0x180046a22  mov     rax, [rbp+57h+var_C8]
0x180046a26  mov     [rsi], rax
0x180046a29  mov     rdi, [rsi+8]
0x180046a2d  mov     [rsi+8], r15
0x180046a31  xor     r15d, r15d
0x180046a34  test    rdi, rdi
0x180046a37  jz      short loc_180046A70
0x180046a39  or      eax, 0FFFFFFFFh
0x180046a3c  lock xadd [rdi+8], eax
0x180046a41  cmp     eax, 1
0x180046a44  jnz     short loc_180046A70
0x180046a46  mov     rax, [rdi]
0x180046a49  mov     this, rdi
0x180046a4c  mov     rax, [rax]
0x180046a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a54  or      eax, 0FFFFFFFFh
0x180046a57  lock xadd [rdi+0Ch], eax
0x180046a5c  cmp     eax, 1
0x180046a5f  jnz     short loc_180046A70
0x180046a61  mov     rax, [rdi]
0x180046a64  mov     this, rdi
0x180046a67  mov     rax, [rax+8]
0x180046a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a70  mov     [rsi+10h], r15
0x180046a74  mov     rdi, [rsi+18h]
0x180046a78  mov     [rsi+18h], r15
0x180046a7c  test    rdi, rdi
0x180046a7f  jz      short loc_180046AB8
0x180046a81  or      eax, 0FFFFFFFFh
0x180046a84  lock xadd [rdi+8], eax
0x180046a89  cmp     eax, 1
0x180046a8c  jnz     short loc_180046AB8
0x180046a8e  mov     rax, [rdi]
0x180046a91  mov     this, rdi
0x180046a94  mov     rax, [rax]
0x180046a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a9c  or      eax, 0FFFFFFFFh
0x180046a9f  lock xadd [rdi+0Ch], eax
0x180046aa4  cmp     eax, 1
0x180046aa7  jnz     short loc_180046AB8
0x180046aa9  mov     rax, [rdi]
0x180046aac  mov     this, rdi
0x180046aaf  mov     rax, [rax+8]
0x180046ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ab8  test    rbx, rbx
0x180046abb  jz      short loc_180046AC1
0x180046abd  lock inc dword ptr [rbx+8]
0x180046ac1  mov     [rsi+20h], r13
0x180046ac5  or      r13d, 0FFFFFFFFh
0x180046ac9  mov     rdi, [rsi+28h]
0x180046acd  mov     [rsi+28h], rbx
0x180046ad1  test    rdi, rdi
0x180046ad4  jz      short loc_180046B0D
0x180046ad6  mov     eax, r13d
0x180046ad9  lock xadd [rdi+8], eax
0x180046ade  add     eax, r13d
0x180046ae1  jnz     short loc_180046B0D
0x180046ae3  mov     rax, [rdi]
0x180046ae6  mov     this, rdi
0x180046ae9  mov     rax, [rax]
0x180046aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046af1  mov     eax, r13d
0x180046af4  lock xadd [rdi+0Ch], eax
0x180046af9  add     eax, r13d
0x180046afc  jnz     short loc_180046B0D
0x180046afe  mov     rax, [rdi]
0x180046b01  mov     this, rdi
0x180046b04  mov     rax, [rax+8]
  ... truncated ...
```
