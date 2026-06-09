# ObjectWriterContext::Create(std::shared_ptr<XamlSavedContext> const &,std::shared_ptr<XamlQualifiedObject>,uint,std::shared_ptr<XamlQualifiedObject> const &,std::shared_ptr<ObjectWriterContext> &)

- ea: `0x1800b4be4`
- end: `0x1800b51ae`
- name: `?Create@ObjectWriterContext@@SAJAEBV?$shared_ptr@VXamlSavedContext@@@std@@V?$shared_ptr@UXamlQualifiedObject@@@3@IAEBV43@AEAV?$shared_ptr@VObjectWriterContext@@@3@@Z`
- size: `1482`
- prototype: `HRESULT __fastcall(const std::shared_ptr<XamlSavedContext> *spXamlSavedContext, std::shared_ptr<XamlQualifiedObject> spEventRoot, unsigned int bExpandTemplates, const std::shared_ptr<XamlQualifiedObject> *spParentXBindConnector, std::shared_ptr<ObjectWriterContext> *rspObjectWriterContext)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180170864`
- `0x1806aab04`

## callees

- `0x180004bc0`
- `0x1800710d0`
- `0x180071458`
- `0x1800ab600`
- `0x1800b3cd4`
- `0x1800b440c`
- `0x1800b4be4`
- `0x1806877a8`
- `0x180687890`
- `0x180687a78`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800b4e7e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800b4f53`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800b4e7e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800b4f53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4f79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b5105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4f79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b5105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b4e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b4f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b4e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b4f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b513c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b515d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b513c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b515d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800b4e92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800b5121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800b4e92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800b5121`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=8
__int64 __fastcall ObjectWriterContext::Create(
        const std::shared_ptr<XamlSavedContext> *spXamlSavedContext,
        std::shared_ptr<XamlQualifiedObject> *spEventRoot,
        unsigned int bExpandTemplates,
        const std::shared_ptr<XamlQualifiedObject> *spParentXBindConnector,
        std::shared_ptr<ObjectWriterContext> *rspObjectWriterContext)
{
  const std::shared_ptr<XamlSavedContext> *v7; // r15
  XamlSavedContext *Ptr; // r9
  XamlSchemaContext *v9; // rdx
  std::_Ref_count_base *v10; // rbx
  std::_Ref_count_base *Rep; // r8
  signed __int32 Uses; // eax
  signed __int32 v13; // ett
  XamlSavedContext *v14; // rsi
  std::_Ref_count_base *v15; // rax
  volatile signed __int32 *v16; // rsi
  ObjectWriterStack *v17; // rbx
  ObjectWriterContext *v18; // r13
  ObjectWriterFrame **v19; // rdi
  ObjectWriterFrame **v20; // r14
  ObjectWriterFrame *v21; // rdx
  ObjectWriterFrame *v22; // rcx
  ObjectWriterFrame *Mylast; // rdx
  ObjectWriterFrame *Myfirst; // rcx
  IPALUri *m_ptr; // rbx
  XamlSavedContext *v26; // rax
  xref_ptr<IPALUri> *p_m_spBaseUri; // rcx
  IPALUri *v28; // rcx
  xref_ptr<IPALUri> *v29; // rdi
  IPALUri *v30; // rcx
  IPALUri *v31; // rcx
  unsigned __int64 RuntimeStringHandleMarker; // rcx
  int v33; // edx
  HSTRING StringRawBuffer; // rax
  UINT32 v35; // edx
  int v36; // eax
  _QWORD *p_RuntimeStringHandleMarker; // rdi
  int v38; // edx
  const wchar_t *v39; // rax
  UINT32 v40; // edx
  int v41; // eax
  std::_Ref_count_base *v42; // rcx
  std::shared_ptr<ObjectWriterContext> *v43; // rax
  volatile signed __int32 *v44; // rdi
  volatile signed __int32 *v45; // rbx
  std::_Ref_count_base *v46; // rbx
  std::_Ref_count_base *v48; // rcx
  xref_ptr<IPALUri> *p_m_spXamlResourceUri; // rax
  HSTRING string; // [rsp+38h] [rbp-71h] BYREF
  IPALUri *v51; // [rsp+40h] [rbp-69h] BYREF
  xref_ptr<IPALUri> spUri; // [rsp+48h] [rbp-61h] BYREF
  IPALUri *v53; // [rsp+50h] [rbp-59h] BYREF
  _BYTE spSchemaContext[40]; // [rsp+58h] [rbp-51h] OVERLAPPED BYREF
  std::shared_ptr<ObjectWriterStack> spSavedStack; // [rsp+80h] [rbp-29h]
  volatile signed __int32 *v56; // [rsp+90h] [rbp-19h]
  ObjectWriterStack result; // [rsp+98h] [rbp-11h] BYREF
  IPALUri **length; // [rsp+108h] [rbp+5Fh] BYREF
  std::shared_ptr<XamlQualifiedObject> *v59; // [rsp+110h] [rbp+67h]
  unsigned int v60; // [rsp+118h] [rbp+6Fh] BYREF

  v60 = bExpandTemplates;
  v59 = spEventRoot;
  v7 = spXamlSavedContext;
  *(_OWORD *)&spSchemaContext[8] = 0;
  Ptr = spXamlSavedContext->_Ptr;
  v9 = 0;
  v10 = 0;
  Rep = spXamlSavedContext->_Ptr->m_spSchemaContext._Rep;
  if ( Rep )
  {
    Uses = Rep->_Uses;
    while ( Uses )
    {
      LODWORD(spXamlSavedContext) = Uses + 1;
      v13 = Uses;
      Uses = _InterlockedCompareExchange((volatile signed __int32 *)&Rep->_Uses, Uses + 1, Uses);
      if ( v13 == Uses )
      {
        v9 = Ptr->m_spSchemaContext._Ptr;
        v10 = Ptr->m_spSchemaContext._Rep;
        break;
      }
    }
  }
  *(_QWORD *)&spSchemaContext[8] = v9;
  *(_QWORD *)&spSchemaContext[16] = v10;
  if ( v9 )
  {
    LOBYTE(length) = 1;
    std::make_shared<ObjectWriterContext,std::shared_ptr<XamlSchemaContext> &,std::shared_ptr<XamlQualifiedObject> &,unsigned int &,bool,std::shared_ptr<XamlQualifiedObject> const &>(
      (std::shared_ptr<ObjectWriterContext> *)&spSchemaContext[24],
      (std::shared_ptr<XamlSchemaContext> *)&spSchemaContext[8],
      spEventRoot,
      &v60,
      (bool *)&length,
      spParentXBindConnector);
    v14 = v7->_Ptr;
    v15 = v7->_Ptr->m_spObjectWriterStack._Rep;
    if ( v15 )
      _InterlockedIncrement((volatile signed __int32 *)&v15->_Uses);
    spSavedStack._Rep = (std::_Ref_count_base *)v14->m_spObjectWriterStack._Ptr;
    v16 = (volatile signed __int32 *)v14->m_spObjectWriterStack._Rep;
    v56 = v16;
    v17 = ObjectWriterStack::CopyStack((ObjectWriterStack *)spSavedStack._Rep, &result);
    v18 = *(ObjectWriterContext **)&spSchemaContext[24];
    v19 = (ObjectWriterFrame **)(*(_QWORD *)&spSchemaContext[24] + 40LL);
    v20 = (ObjectWriterFrame **)(*(_QWORD *)&spSchemaContext[24] + 48LL);
    if ( (ObjectWriterStack *)(*(_QWORD *)&spSchemaContext[24] + 40LL) != v17 )
    {
      std::vector<ObjectWriterFrame>::_Tidy((std::vector<ObjectWriterFrame> *)(*(_QWORD *)&spSchemaContext[24] + 40LL));
      *v19 = v17->m_Stack._Mypair._Myval2._Myfirst;
      *v20 = v17->m_Stack._Mypair._Myval2._Mylast;
      v19[2] = v17->m_Stack._Mypair._Myval2._Myend;
      v17->m_Stack._Mypair._Myval2._Myfirst = 0;
      v17->m_Stack._Mypair._Myval2._Mylast = 0;
      v17->m_Stack._Mypair._Myval2._Myend = 0;
      v21 = *v20;
      v19[3] = *v20;
      v22 = *v19;
      if ( (unsigned int)(v21 - *v19) > 1 )
        v22 = v21 - 1;
      v19[4] = v22;
      Mylast = v17->m_Stack._Mypair._Myval2._Mylast;
      v17->m_itCurrent.current._Ptr = Mylast;
      Myfirst = v17->m_Stack._Mypair._Myval2._Myfirst;
      if ( (unsigned int)(Mylast - v17->m_Stack._Mypair._Myval2._Myfirst) > 1 )
        Myfirst = Mylast - 1;
      v17->m_itParent.current._Ptr = Myfirst;
    }
    std::vector<ObjectWriterFrame>::_Tidy(&result.m_Stack);
    v18->m_uiSavedDepth = *v20 - *v19;
    m_ptr = 0;
    v53 = 0;
    v26 = v7->_Ptr;
    p_m_spBaseUri = &v7->_Ptr->m_spBaseUri;
    if ( &v53 != (IPALUri **)p_m_spBaseUri && (m_ptr = p_m_spBaseUri->m_ptr, (v53 = m_ptr) != 0)
      || (p_m_spXamlResourceUri = &v26->m_spXamlResourceUri, &v53 != (IPALUri **)p_m_spXamlResourceUri)
      && (m_ptr = p_m_spXamlResourceUri->m_ptr, (v53 = m_ptr) != 0) )
    {
      m_ptr->AddRef(m_ptr);
      v28 = m_ptr;
    }
    else
    {
      v28 = 0;
    }
    v51 = v28;
    if ( v28 )
      v28->AddRef(v28);
    length = &v51;
    v29 = &v18->m_spXamlResourceUri;
    if ( &v18->m_spXamlResourceUri != (xref_ptr<IPALUri> *)&v51 )
    {
      v30 = v29->m_ptr;
      v29->m_ptr = v51;
      if ( v30 )
        v30->Release(v30);
      if ( v29->m_ptr )
        v29->m_ptr->AddRef(v29->m_ptr);
    }
    v31 = v51;
    if ( v51 )
    {
      v51 = 0;
      v31->Release(v31);
    }
    RuntimeStringHandleMarker = v7->_Ptr->m_xbfHash.m_encodedStorage.RuntimeStringHandleMarker;
    if ( (RuntimeStringHandleMarker & 1) != 0 )
    {
      v36 = WindowsDuplicateString((HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL), &string);
      if ( v36 < 0 )
      {
LABEL_33:
        OnFailure_2990_(v36);
        spUri.m_ptr = 0;
        LODWORD(length) = 0;
        TraceForFailFast(-2147418113);
        OnNewFailureEncountered(-2147418113, 0, 0);
        GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&spUri, (unsigned int *)&length);
        RoFailFastWithErrorContextInternal2(
          -2147418113,
          (unsigned int)length,
          (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)spUri.m_ptr);
        RuntimeStringHandleMarker = (unsigned __int64)string;
        goto LABEL_37;
      }
    }
    else
    {
      if ( !RuntimeStringHandleMarker )
        goto LABEL_36;
      v33 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
      if ( (v33 & 0x40000000) == 0 )
        goto LABEL_36;
      LODWORD(length) = 0;
      StringRawBuffer = *(HSTRING *)RuntimeStringHandleMarker;
      if ( v33 < 0 )
      {
        StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(*(HSTRING *)RuntimeStringHandleMarker, (UINT32 *)&length);
        v35 = (unsigned int)length;
      }
      else
      {
        v35 = v33 & 0x3FFFFFFF;
        LODWORD(length) = v35;
      }
      v36 = WindowsCreateString((PCNZWCH)StringRawBuffer, v35, &string);
      if ( v36 < 0 )
        goto LABEL_33;
    }
    RuntimeStringHandleMarker = (unsigned __int64)string | 1;
LABEL_36:
    string = (HSTRING)RuntimeStringHandleMarker;
LABEL_37:
    *(_QWORD *)spSchemaContext = RuntimeStringHandleMarker;
    spSavedStack._Ptr = (ObjectWriterStack *)spSchemaContext;
    p_RuntimeStringHandleMarker = &v18->m_xbfHash.m_encodedStorage.RuntimeStringHandleMarker;
    if ( &v18->m_xbfHash == (xstring_ptr *)spSchemaContext )
    {
LABEL_48:
      if ( (RuntimeStringHandleMarker & 1) != 0 )
        WindowsDeleteString((HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
      v42 = *(std::_Ref_count_base **)&spSchemaContext[32];
      *(_OWORD *)&spSchemaContext[24] = 0;
      v43 = rspObjectWriterContext;
      rspObjectWriterContext->_Ptr = v18;
      v44 = (volatile signed __int32 *)v43->_Rep;
      v43->_Rep = v42;
      if ( v44 )
      {
        if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
          if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
        }
      }
      if ( m_ptr )
        m_ptr->Release(m_ptr);
      if ( v16 )
      {
        if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      v45 = *(volatile signed __int32 **)&spSchemaContext[16];
      if ( *(_QWORD *)&spSchemaContext[16] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&spSchemaContext[16] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
          if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
        }
      }
      v46 = spEventRoot->_Rep;
      if ( v46 && _InterlockedExchangeAdd((volatile signed __int32 *)&v46->_Uses, 0xFFFFFFFF) == 1 )
      {
        v46->_Destroy(v46);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v46->_Weaks, 0xFFFFFFFF) == 1 )
          v46->_Delete_this(v46);
      }
      return 0;
    }
    if ( (RuntimeStringHandleMarker & 1) != 0 )
    {
      v41 = WindowsDuplicateString((HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL), &string);
      if ( v41 < 0 )
        goto LABEL_44;
    }
    else
    {
      if ( !RuntimeStringHandleMarker || (v38 = *(_DWORD *)(RuntimeStringHandleMarker + 8), (v38 & 0x40000000) == 0) )
      {
        string = (HSTRING)RuntimeStringHandleMarker;
        goto LABEL_45;
      }
      LODWORD(length) = 0;
      if ( v38 < 0 )
      {
        v39 = WindowsGetStringRawBuffer(*(HSTRING *)RuntimeStringHandleMarker, (UINT32 *)&length);
        v40 = (unsigned int)length;
      }
      else
      {
        v39 = *(const wchar_t **)RuntimeStringHandleMarker;
        v40 = v38 & 0x3FFFFFFF;
        LODWORD(length) = v40;
      }
      v41 = WindowsCreateString(v39, v40, &string);
      if ( v41 < 0 )
      {
LABEL_44:
        OnFailure_2990_(v41);
        spUri.m_ptr = 0;
        LODWORD(length) = 0;
        TraceForFailFast(-2147418113);
        OnNewFailureEncountered(-2147418113, 0, 0);
        GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&spUri, (unsigned int *)&length);
        RoFailFastWithErrorContextInternal2(
          -2147418113,
          (unsigned int)length,
          (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)spUri.m_ptr);
LABEL_45:
        if ( (*p_RuntimeStringHandleMarker & 1) != 0 )
          WindowsDeleteString((HSTRING)(*p_RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
        *p_RuntimeStringHandleMarker = string;
        RuntimeStringHandleMarker = *(_QWORD *)spSchemaContext;
        goto LABEL_48;
      }
    }
    string = (HSTRING)((unsigned __int64)string | 1);
    goto LABEL_45;
  }
  OnFailure_977_((HRESULT)spXamlSavedContext);
  OnFailure_2990_(-2147467259);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  v48 = spEventRoot->_Rep;
  if ( v48 )
    std::_Ref_count_base::_Decref(v48);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800b4be4  mov     rax, rsp
0x1800b4be7  mov     [rax+20h], rbx
0x1800b4beb  mov     [rax+18h], bExpandTemplates
0x1800b4bef  mov     [rax+10h], spEventRoot
0x1800b4bf3  push    rbp
0x1800b4bf4  push    rsi
0x1800b4bf5  push    rdi
0x1800b4bf6  push    r12
0x1800b4bf8  push    r13
0x1800b4bfa  push    r14
0x1800b4bfc  push    r15
0x1800b4bfe  lea     rbp, [rax-57h]
0x1800b4c02  sub     rsp, 0C0h
0x1800b4c09  mov     r10, spParentXBindConnector
0x1800b4c0c  mov     r12, spEventRoot
0x1800b4c0f  mov     r15, spXamlSavedContext
0x1800b4c12  xorps   xmm0, xmm0
0x1800b4c15  movdqu  xmmword ptr [rbp+4Fh+spSchemaContext._Rep], xmm0
0x1800b4c1a  mov     spParentXBindConnector, [spXamlSavedContext]
0x1800b4c1d  xor     edx, edx
0x1800b4c1f  xor     ebx, ebx
0x1800b4c21  mov     r8, [spParentXBindConnector+8]
0x1800b4c25  test    r8, r8
0x1800b4c28  jz      short loc_1800B4C44
0x1800b4c2a  mov     eax, [r8+8]
0x1800b4c2e  test    eax, eax
0x1800b4c30  jz      short loc_1800B4C44
0x1800b4c32  lea     ecx, [rax+1]; failedFrameHR
0x1800b4c35  lock cmpxchg [r8+8], ecx
0x1800b4c3b  jnz     short loc_1800B4C2E
0x1800b4c3d  mov     spEventRoot, [spParentXBindConnector]
0x1800b4c40  mov     rbx, [spParentXBindConnector+8]
0x1800b4c44  mov     [rbp+4Fh+spSchemaContext._Rep], spEventRoot
0x1800b4c48  mov     [rbp+4Fh+writerContext._Ptr], rbx
0x1800b4c4c  test    spEventRoot, spEventRoot
0x1800b4c4f  jz      loc_1800B50CD
0x1800b4c55  mov     byte ptr [rbp+4Fh+length], 1
0x1800b4c59  mov     [rsp+28h], r10; <_Args_4>
0x1800b4c5e  lea     rax, [rbp+4Fh+length]
0x1800b4c62  mov     [rsp+0F0h+var_D0], rax; <_Args_3>
0x1800b4c67  lea     spParentXBindConnector, [rbp+4Fh+arg_10]; <_Args_2>
0x1800b4c6b  mov     r8, r12; <_Args_1>
0x1800b4c6e  lea     spEventRoot, [rbp+4Fh+spSchemaContext._Rep]; <_Args_0>
0x1800b4c72  lea     spXamlSavedContext, [rbp+4Fh+writerContext._Rep]; result
0x1800b4c76  call    ??$make_shared@VObjectWriterContext@@AEAV?$shared_ptr@VXamlSchemaContext@@@std@@AEAV?$shared_ptr@UXamlQualifiedObject@@@3@AEAI_NAEBV43@@std@@YA?AV?$shared_ptr@VObjectWriterContext@@@0@AEAV?$shared_ptr@VXamlSchemaContext@@@0@AEAV?$shared_ptr@UXamlQualifiedObject@@@0@AEAI$$QEA_NAEBV30@@Z; std::make_shared<ObjectWriterContext,std::shared_ptr<XamlSchemaContext> &,std::shared_ptr<XamlQualifiedObject> &,uint &,bool,std::shared_ptr<XamlQualifiedObject> const &>(std::shared_ptr<XamlSchemaContext> &,std::shared_ptr<XamlQualifiedObject> &,uint &,bool &&,std::shared_ptr<XamlQualifiedObject> const &)
0x1800b4c7b  nop
0x1800b4c7c  mov     rsi, [r15]
0x1800b4c7f  mov     rax, [rsi+18h]
0x1800b4c83  test    rax, rax
0x1800b4c86  jz      short loc_1800B4C8C
0x1800b4c88  lock inc dword ptr [rax+8]
0x1800b4c8c  mov     spXamlSavedContext, [rsi+10h]; this
0x1800b4c90  mov     [rbp+4Fh+spSavedStack._Rep], spXamlSavedContext
0x1800b4c94  mov     rsi, [rsi+18h]
0x1800b4c98  mov     [rbp+4Fh+var_68], rsi
0x1800b4c9c  lea     spEventRoot, [rbp+4Fh+result]; result
0x1800b4ca0  call    ?CopyStack@ObjectWriterStack@@QEBA?AV1@XZ; ObjectWriterStack::CopyStack(void)
0x1800b4ca5  mov     rbx, rax
0x1800b4ca8  mov     r13, [rbp+4Fh+writerContext._Rep]
0x1800b4cac  lea     rdi, [r13+28h]
0x1800b4cb0  lea     r14, [rdi+8]
0x1800b4cb4  cmp     rdi, rax
0x1800b4cb7  jz      short loc_1800B4D26
0x1800b4cb9  mov     spXamlSavedContext, rdi; this
0x1800b4cbc  call    ?_Tidy@?$vector@VObjectWriterFrame@@V?$allocator@VObjectWriterFrame@@@std@@@std@@AEAAXXZ; std::vector<ObjectWriterFrame>::_Tidy(void)
0x1800b4cc1  mov     spXamlSavedContext, [rbx]
0x1800b4cc4  mov     [rdi], spXamlSavedContext
0x1800b4cc7  mov     spXamlSavedContext, [rbx+8]
0x1800b4ccb  mov     [r14], spXamlSavedContext
0x1800b4cce  mov     rax, [rbx+10h]
0x1800b4cd2  mov     [rdi+10h], rax
0x1800b4cd6  xor     eax, eax
0x1800b4cd8  mov     [rbx], rax
0x1800b4cdb  mov     [rbx+8], rax
0x1800b4cdf  mov     [rbx+10h], rax
0x1800b4ce3  mov     spEventRoot, [r14]
0x1800b4ce6  mov     [rdi+18h], spEventRoot
0x1800b4cea  mov     spXamlSavedContext, [rdi]
0x1800b4ced  mov     rax, spEventRoot
0x1800b4cf0  sub     rax, spXamlSavedContext
0x1800b4cf3  sar     rax, 6
0x1800b4cf7  cmp     eax, 1
0x1800b4cfa  jbe     short loc_1800B4D00
0x1800b4cfc  lea     spXamlSavedContext, [spEventRoot-40h]
0x1800b4d00  mov     [rdi+20h], spXamlSavedContext
0x1800b4d04  mov     spEventRoot, [rbx+8]
0x1800b4d08  mov     [rbx+18h], spEventRoot
0x1800b4d0c  mov     spXamlSavedContext, [rbx]
0x1800b4d0f  mov     rax, spEventRoot
0x1800b4d12  sub     rax, spXamlSavedContext
0x1800b4d15  sar     rax, 6
0x1800b4d19  cmp     eax, 1
0x1800b4d1c  jbe     short loc_1800B4D22
0x1800b4d1e  lea     spXamlSavedContext, [spEventRoot-40h]
0x1800b4d22  mov     [rbx+20h], spXamlSavedContext
0x1800b4d26  lea     spXamlSavedContext, [rbp+4Fh+result]; this
0x1800b4d2a  call    ?_Tidy@?$vector@VObjectWriterFrame@@V?$allocator@VObjectWriterFrame@@@std@@@std@@AEAAXXZ; std::vector<ObjectWriterFrame>::_Tidy(void)
0x1800b4d2f  mov     rax, [r14]
0x1800b4d32  sub     rax, [rdi]
0x1800b4d35  sar     rax, 6
0x1800b4d39  mov     [r13+0E0h], eax
0x1800b4d40  xor     r14d, r14d
0x1800b4d43  mov     ebx, r14d
0x1800b4d46  mov     [rbp+4Fh+var_A8], rbx
0x1800b4d4a  mov     rax, [r15]
0x1800b4d4d  lea     spXamlSavedContext, [rax+20h]
0x1800b4d51  lea     spEventRoot, [rbp+4Fh+var_A8]
0x1800b4d55  cmp     spEventRoot, spXamlSavedContext
0x1800b4d58  jz      loc_1800B5177
0x1800b4d5e  mov     rbx, [spXamlSavedContext]
0x1800b4d61  mov     [rbp+4Fh+var_A8], rbx
0x1800b4d65  test    rbx, rbx
0x1800b4d68  jz      loc_1800B5177
0x1800b4d6e  mov     rax, [rbx]
0x1800b4d71  mov     spXamlSavedContext, rbx
0x1800b4d74  mov     rax, [rax+8]
0x1800b4d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d7d  mov     spXamlSavedContext, rbx
0x1800b4d80  mov     [rbp+4Fh+var_B8], spXamlSavedContext
0x1800b4d84  test    spXamlSavedContext, spXamlSavedContext
0x1800b4d87  jz      short loc_1800B4D95
0x1800b4d89  mov     rax, [spXamlSavedContext]
0x1800b4d8c  mov     rax, [rax+8]
0x1800b4d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d95  lea     rax, [rbp+4Fh+var_B8]
0x1800b4d99  mov     [rbp+4Fh+length], rax
0x1800b4d9d  lea     rdi, [r13+0D0h]
0x1800b4da4  lea     rax, [rbp+4Fh+var_B8]
0x1800b4da8  cmp     rdi, rax
0x1800b4dab  jz      short loc_1800B4DD5
0x1800b4dad  mov     spXamlSavedContext, [rdi]
0x1800b4db0  mov     rax, [rbp+4Fh+var_B8]
0x1800b4db4  mov     [rdi], rax
0x1800b4db7  test    spXamlSavedContext, spXamlSavedContext
0x1800b4dba  jnz     loc_1800B519C
0x1800b4dc0  mov     spXamlSavedContext, [rdi]
0x1800b4dc3  test    spXamlSavedContext, spXamlSavedContext
0x1800b4dc6  jz      short loc_1800B4DD5
0x1800b4dc8  mov     rax, [spXamlSavedContext]
0x1800b4dcb  mov     rax, [rax+8]
0x1800b4dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4dd4  nop
0x1800b4dd5  mov     spXamlSavedContext, [rbp+4Fh+var_B8]
0x1800b4dd9  test    spXamlSavedContext, spXamlSavedContext
0x1800b4ddc  jz      short loc_1800B4DEE
0x1800b4dde  mov     [rbp+4Fh+var_B8], r14
0x1800b4de2  mov     rax, [spXamlSavedContext]
0x1800b4de5  mov     rax, [rax+10h]
0x1800b4de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4dee  mov     spXamlSavedContext, [r15]
0x1800b4df1  mov     spXamlSavedContext, [spXamlSavedContext+30h]
0x1800b4df5  mov     r15d, 8000FFFFh
0x1800b4dfb  test    cl, 1
0x1800b4dfe  jnz     loc_1800B4E8A
0x1800b4e04  test    spXamlSavedContext, spXamlSavedContext
0x1800b4e07  jz      loc_1800B4EA8
0x1800b4e0d  mov     edx, [spXamlSavedContext+8]
0x1800b4e10  bt      edx, 1Eh
0x1800b4e14  jnb     loc_1800B4EA8
0x1800b4e1a  mov     dword ptr [rbp+4Fh+length], r14d
0x1800b4e1e  mov     rax, [spXamlSavedContext]
0x1800b4e21  test    edx, edx
0x1800b4e23  js      loc_1800B5135
0x1800b4e29  and     edx, 3FFFFFFFh; length
0x1800b4e2f  mov     dword ptr [rbp+4Fh+length], edx
0x1800b4e32  lea     r8, [rbp+4Fh+string]; string
0x1800b4e36  mov     spXamlSavedContext, rax; sourceString
0x1800b4e39  call    cs:__imp_WindowsCreateString
0x1800b4e3f  test    eax, eax
0x1800b4e41  jns     short loc_1800B4EA0
0x1800b4e43  mov     ecx, eax; failedFrameHR
0x1800b4e45  call    OnFailure_2990_
0x1800b4e4a  mov     [rbp+4Fh+spUri.m_ptr], r14
0x1800b4e4e  mov     dword ptr [rbp+4Fh+length], r14d
0x1800b4e52  mov     ecx, r15d; errorCode
0x1800b4e55  call    TraceForFailFast
0x1800b4e5a  xor     bExpandTemplates, bExpandTemplates; contextRecord
0x1800b4e5d  xor     edx, edx; directCallerReturnAddress
0x1800b4e5f  mov     ecx, r15d; failedFrameHR
0x1800b4e62  call    OnNewFailureEncountered
0x1800b4e67  lea     spEventRoot, [rbp+4Fh+length]; pcStowedExceptions
0x1800b4e6b  lea     spXamlSavedContext, [rbp+4Fh+spUri]; pppStowedExceptions
0x1800b4e6f  call    GetStowedExceptionsForFailFast
0x1800b4e74  mov     r8, [rbp+4Fh+spUri.m_ptr]
0x1800b4e78  mov     edx, dword ptr [rbp+4Fh+length]
0x1800b4e7b  mov     ecx, r15d
0x1800b4e7e  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1800b4e84  mov     spXamlSavedContext, [rbp+4Fh+string]
0x1800b4e88  jmp     short loc_1800B4EAC
0x1800b4e8a  and     spXamlSavedContext, 0FFFFFFFFFFFFFFFEh; string
0x1800b4e8e  lea     spEventRoot, [rbp+4Fh+string]; newString
0x1800b4e92  call    cs:__imp_WindowsDuplicateString
0x1800b4e98  test    eax, eax
0x1800b4e9a  js      loc_1800B514A
0x1800b4ea0  mov     spXamlSavedContext, [rbp+4Fh+string]
0x1800b4ea4  or      spXamlSavedContext, 1
0x1800b4ea8  mov     [rbp+4Fh+string], spXamlSavedContext
0x1800b4eac  mov     [rbp+4Fh+spSchemaContext._Ptr], spXamlSavedContext
0x1800b4eb0  lea     rax, [rbp+4Fh+spSchemaContext]
0x1800b4eb4  mov     [rbp+4Fh+spSavedStack._Ptr], rax
0x1800b4eb8  lea     rdi, [r13+0D8h]
0x1800b4ebf  lea     rax, [rbp+4Fh+spSchemaContext]
0x1800b4ec3  cmp     rdi, rax
0x1800b4ec6  jz      loc_1800B4F70
0x1800b4ecc  test    cl, 1
0x1800b4ecf  jnz     loc_1800B5119
0x1800b4ed5  test    spXamlSavedContext, spXamlSavedContext
0x1800b4ed8  jz      loc_1800B5110
0x1800b4ede  mov     edx, [spXamlSavedContext+8]
0x1800b4ee1  bt      edx, 1Eh
0x1800b4ee5  jnb     loc_1800B5110
0x1800b4eeb  mov     dword ptr [rbp+4Fh+length], r14d
0x1800b4eef  test    edx, edx
0x1800b4ef1  js      loc_1800B5156
0x1800b4ef7  mov     rax, [spXamlSavedContext]
0x1800b4efa  and     edx, 3FFFFFFFh; length
0x1800b4f00  mov     dword ptr [rbp+4Fh+length], edx
0x1800b4f03  lea     r8, [rbp+4Fh+string]; string
0x1800b4f07  mov     spXamlSavedContext, rax; sourceString
0x1800b4f0a  call    cs:__imp_WindowsCreateString
0x1800b4f10  test    eax, eax
0x1800b4f12  jns     loc_1800B512B
0x1800b4f18  mov     ecx, eax; failedFrameHR
0x1800b4f1a  call    OnFailure_2990_
0x1800b4f1f  mov     [rbp+4Fh+spUri.m_ptr], r14
0x1800b4f23  mov     dword ptr [rbp+4Fh+length], r14d
0x1800b4f27  mov     ecx, r15d; errorCode
0x1800b4f2a  call    TraceForFailFast
0x1800b4f2f  xor     bExpandTemplates, bExpandTemplates; contextRecord
0x1800b4f32  xor     edx, edx; directCallerReturnAddress
0x1800b4f34  mov     ecx, r15d; failedFrameHR
0x1800b4f37  call    OnNewFailureEncountered
0x1800b4f3c  lea     spEventRoot, [rbp+4Fh+length]; pcStowedExceptions
0x1800b4f40  lea     spXamlSavedContext, [rbp+4Fh+spUri]; pppStowedExceptions
0x1800b4f44  call    GetStowedExceptionsForFailFast
0x1800b4f49  mov     r8, [rbp+4Fh+spUri.m_ptr]
0x1800b4f4d  mov     edx, dword ptr [rbp+4Fh+length]
0x1800b4f50  mov     ecx, r15d
0x1800b4f53  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1800b4f59  mov     spXamlSavedContext, [rdi]
0x1800b4f5c  test    cl, 1
0x1800b4f5f  jnz     loc_1800B5101
0x1800b4f65  mov     rax, [rbp+4Fh+string]
0x1800b4f69  mov     [rdi], rax
0x1800b4f6c  mov     spXamlSavedContext, [rbp+4Fh+spSchemaContext._Ptr]
0x1800b4f70  test    cl, 1
0x1800b4f73  jz      short loc_1800B4F80
0x1800b4f75  and     spXamlSavedContext, 0FFFFFFFFFFFFFFFEh; string
0x1800b4f79  call    cs:__imp_WindowsDeleteString
0x1800b4f7f  nop
0x1800b4f80  mov     spXamlSavedContext, [rbp+4Fh+var_80]
0x1800b4f84  xorps   xmm0, xmm0
0x1800b4f87  movdqu  xmmword ptr [rbp+4Fh+writerContext._Rep], xmm0
0x1800b4f8c  mov     rax, [rbp+4Fh+arg_20]
0x1800b4f90  mov     [rax], r13
0x1800b4f93  mov     rdi, [rax+8]
0x1800b4f97  mov     [rax+8], spXamlSavedContext
0x1800b4f9b  or      r15d, 0FFFFFFFFh
0x1800b4f9f  test    rdi, rdi
0x1800b4fa2  jz      short loc_1800B4FDC
0x1800b4fa4  mov     eax, r15d
0x1800b4fa7  lock xadd [rdi+8], eax
0x1800b4fac  add     eax, r15d
0x1800b4faf  jnz     short loc_1800B4FDC
0x1800b4fb1  mov     rax, [rdi]
0x1800b4fb4  mov     spXamlSavedContext, rdi
0x1800b4fb7  mov     rax, [rax]
0x1800b4fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4fbf  mov     eax, r15d
0x1800b4fc2  lock xadd [rdi+0Ch], eax
0x1800b4fc7  add     eax, r15d
0x1800b4fca  jnz     short loc_1800B4FDC
0x1800b4fcc  mov     rax, [rdi]
0x1800b4fcf  mov     spXamlSavedContext, rdi
0x1800b4fd2  mov     rax, [rax+8]
0x1800b4fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4fdb  nop
0x1800b4fdc  test    rbx, rbx
0x1800b4fdf  jz      short loc_1800B4FF1
0x1800b4fe1  mov     rax, [rbx]
0x1800b4fe4  mov     spXamlSavedContext, rbx
0x1800b4fe7  mov     rax, [rax+10h]
0x1800b4feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ff0  nop
0x1800b4ff1  test    rsi, rsi
0x1800b4ff4  jz      short loc_1800B502E
0x1800b4ff6  mov     eax, r15d
0x1800b4ff9  lock xadd [rsi+8], eax
0x1800b4ffe  add     eax, r15d
0x1800b5001  jnz     short loc_1800B502E
0x1800b5003  mov     rax, [rsi]
0x1800b5006  mov     spXamlSavedContext, rsi
0x1800b5009  mov     rax, [rax]
0x1800b500c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5011  mov     eax, r15d
0x1800b5014  lock xadd [rsi+0Ch], eax
0x1800b5019  add     eax, r15d
0x1800b501c  jnz     short loc_1800B502E
0x1800b501e  mov     rax, [rsi]
0x1800b5021  mov     spXamlSavedContext, rsi
  ... truncated ...
```
