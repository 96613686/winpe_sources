# CDependencyObject::SetName(xstring_ptr const &)

- ea: `0x1800a1868`
- end: `0x1800a1c76`
- name: `?SetName@CDependencyObject@@QEAAJAEBVxstring_ptr@@@Z`
- size: `1038`
- prototype: `HRESULT __fastcall(CDependencyObject *this, const xstring_ptr *strName)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a1750`

## callees

- `0x180004bc0`
- `0x180020740`
- `0x1800267fc`
- `0x180029570`
- `0x1800a1868`
- `0x1800a1c7c`
- `0x1800a2a4c`
- `0x1800ab600`
- `0x1800adbb0`
- `0x1800d5330`
- `0x1800fdd4c`
- `0x1800fe130`
- `0x1801800b8`
- `0x1806877a8`
- `0x180687890`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800a1a2a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800a1a2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a194d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a197a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1a3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a194d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a197a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1a3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a19df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a19df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800a1aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800a1aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800a1b0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800a1b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800a1b0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800a1b1c`

## pseudocode

```c
__int64 __fastcall CDependencyObject::SetName(CDependencyObject *this, const xstring_ptr *strName)
{
  xstring_ptr *p_m_strName; // rsi
  unsigned __int64 RuntimeStringHandleMarker; // rcx
  unsigned int v6; // r13d
  int v7; // edi
  UINT32 StringLen; // edi
  xencoded_string_ptr v9; // rcx
  int v10; // eax
  UINT32 v11; // eax
  CDependencyObject *StandardNameScopeOwnerInternal; // rdi
  unsigned int m_bitFieldsAsDWORD; // ecx
  Flyweight::ValueObjectWrapper<CDOSharedState> *m_ptr; // rax
  const xstring_ptr_storage *Storage; // rax
  const xstring_ptr_storage *v16; // r15
  xstring_ptr v17; // rcx
  unsigned __int64 v18; // rax
  int v19; // edx
  wchar_t *StringRawBuffer; // rax
  unsigned int v21; // edx
  int v22; // eax
  unsigned int v23; // eax
  CDependencyObject *v25; // rax
  HRESULT v26; // eax
  HSTRING v27; // rcx
  HSTRING v28; // rcx
  HRESULT v29; // r14d
  const wchar_t *Context; // rax
  const wchar_t *BufferAndCount; // rax
  _MCGEN_TRACE_CONTEXT *v32; // rcx
  INameScope *v33; // rcx
  xstring_ptr strOldName; // [rsp+30h] [rbp-10h] BYREF
  xstring_ptr v35; // [rsp+38h] [rbp-8h] BYREF
  unsigned int pcStowedExceptions; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+90h] [rbp+50h] BYREF

  p_m_strName = &this->m_strName;
  RuntimeStringHandleMarker = strName->m_encodedStorage.RuntimeStringHandleMarker;
  v6 = 0;
  if ( (strName->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v27 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v7 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
    if ( v7 >= 0 )
    {
      StringLen = v7 & 0x3FFFFFFF;
      goto LABEL_4;
    }
    v27 = *(HSTRING *)RuntimeStringHandleMarker;
  }
  StringLen = WindowsGetStringLen(v27);
LABEL_4:
  v9.Storage = (const xstring_ptr_storage *)p_m_strName->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (p_m_strName->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v28 = (HSTRING)(v9.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
LABEL_51:
    v11 = WindowsGetStringLen(v28);
    goto LABEL_7;
  }
  v10 = *((_DWORD *)v9.Storage + 2);
  if ( v10 < 0 )
  {
    v28 = *(HSTRING *)v9.Handle;
    goto LABEL_51;
  }
  v11 = v10 & 0x3FFFFFFF;
LABEL_7:
  if ( StringLen != v11 || xstring_ptr_view::Compare(&strName->xstring_ptr_view, p_m_strName, xstrCompareCaseSensitive) )
  {
    StandardNameScopeOwnerInternal = 0;
    if ( (Microsoft_Windows_XAMLEnableBits[0] & 0x40) != 0
      && CDependencyObject::OfTypeByIndex<305>(this)
      && (Microsoft_Windows_XAMLEnableBits[0] & 0x40) != 0 )
    {
      pcStowedExceptions = 0;
      BufferAndCount = xencoded_string_ptr::GetBufferAndCount(&strName->m_encodedStorage, &pcStowedExceptions);
      if ( BufferAndCount && pcStowedExceptions && *BufferAndCount )
        Context = xstring_ptr_view::GetBuffer(&strName->xstring_ptr_view);
      else
        Context = &pressedKeys;
      McTemplateMofU0xz(v32, &ElementSetNameInfo, &ElementSetNameId, (const unsigned __int64)this, Context);
    }
    m_bitFieldsAsDWORD = this->m_bitFields.m_bitFieldsAsDWORD;
    if ( (m_bitFieldsAsDWORD & 0x20) != 0 || (m_bitFieldsAsDWORD & 0x800) != 0 )
      goto LABEL_75;
    v25 = this;
    if ( (m_bitFieldsAsDWORD & 4) != 0 && (m_bitFieldsAsDWORD & 0x10) != 0 )
      v25 = this->GetStandardNameScopeParent(this);
    if ( !v25 || (StandardNameScopeOwnerInternal = CDependencyObject::GetStandardNameScopeOwnerInternal(v25, 0)) == 0 )
    {
LABEL_75:
      if ( (this->m_bitFields.m_bitFieldsAsDWORD & 0x800) != 0 )
      {
        m_ptr = this->m_sharedState.m_ptr;
        if ( this == m_ptr->m_value.m_coreServices->m_pdoInSetValueFromManaged )
        {
          v33 = m_ptr->m_value.m_coreServices->m_parserNamescope.m_ptr;
          if ( v33 )
            StandardNameScopeOwnerInternal = v33->GetNamescopeOwner(v33);
          else
            StandardNameScopeOwnerInternal = 0;
        }
      }
    }
    Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    strOldName.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    v35.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
    if ( &strOldName != p_m_strName )
    {
      v16 = (const xstring_ptr_storage *)p_m_strName->m_encodedStorage.RuntimeStringHandleMarker;
      p_m_strName->m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
      if ( ((__int64)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage & 1) != 0 )
        WindowsDeleteString((HSTRING)(xstring_ptr_constants::c_xencoded_string_ptr_null.RuntimeStringHandleMarker
                                    & 0xFFFFFFFFFFFFFFFEuLL));
      Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
      strOldName.m_encodedStorage.Storage = v16;
    }
    if ( p_m_strName != &v35 )
    {
      v17.m_encodedStorage.Storage = (const xstring_ptr_storage *)p_m_strName->m_encodedStorage.RuntimeStringHandleMarker;
      v35.m_encodedStorage.Storage = Storage;
      if ( ((__int64)v17.m_encodedStorage.Storage & 1) != 0 )
        WindowsDeleteString((HSTRING)(v17.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
      p_m_strName->m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
    }
    xstring_ptr::~xstring_ptr(&v35);
    if ( !StandardNameScopeOwnerInternal )
    {
      if ( p_m_strName != strName )
      {
        v18 = strName->m_encodedStorage.RuntimeStringHandleMarker;
        if ( (strName->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
        {
          v22 = WindowsDuplicateString((HSTRING)(v18 & 0xFFFFFFFFFFFFFFFEuLL), &string);
          if ( v22 < 0 )
            goto LABEL_29;
        }
        else
        {
          if ( !v18 || (v19 = *(_DWORD *)(v18 + 8), (v19 & 0x40000000) == 0) )
          {
            string = (HSTRING)strName->m_encodedStorage.RuntimeStringHandleMarker;
            goto LABEL_30;
          }
          pcStowedExceptions = 0;
          StringRawBuffer = *(wchar_t **)v18;
          if ( v19 < 0 )
          {
            StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)StringRawBuffer, &pcStowedExceptions);
            v21 = pcStowedExceptions;
          }
          else
          {
            v21 = v19 & 0x3FFFFFFF;
            pcStowedExceptions = v21;
          }
          v22 = WindowsCreateString(StringRawBuffer, v21, &string);
          if ( v22 < 0 )
          {
LABEL_29:
            OnFailure_2990_(v22);
            pppStowedExceptions = 0;
            pcStowedExceptions = 0;
            TraceForFailFast(-2147418113);
            OnNewFailureEncountered(-2147418113, 0, 0);
            GetStowedExceptionsForFailFast(&pppStowedExceptions, &pcStowedExceptions);
            RoFailFastWithErrorContextInternal2(-2147418113, pcStowedExceptions, pppStowedExceptions);
LABEL_30:
            if ( (p_m_strName->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
              WindowsDeleteString((HSTRING)(p_m_strName->m_encodedStorage.RuntimeStringHandleMarker
                                          & 0xFFFFFFFFFFFFFFFEuLL));
            p_m_strName->m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)string;
            goto LABEL_33;
          }
        }
        string = (HSTRING)((unsigned __int64)string | 1);
        goto LABEL_30;
      }
LABEL_33:
      xstring_ptr::~xstring_ptr(&strOldName);
      goto LABEL_34;
    }
    v26 = CDependencyObject::UnregisterName(this, StandardNameScopeOwnerInternal);
    v6 = v26;
    if ( v26 >= 0 )
    {
      xstring_ptr::operator=(p_m_strName, strName);
      v29 = this->RegisterName(this, StandardNameScopeOwnerInternal, 0);
      if ( v29 >= 0 )
        goto LABEL_33;
      std::swap<xstring_ptr,0>(p_m_strName, &strOldName);
      this->RegisterName(this, StandardNameScopeOwnerInternal, 0);
      v6 = v29;
      OnFailure_2990_(v29);
    }
    else
    {
      OnFailure_2990_(v26);
    }
    xstring_ptr::~xstring_ptr(&strOldName);
    return v6;
  }
LABEL_34:
  v23 = this->m_bitFields.m_bitFieldsAsDWORD;
  if ( (v23 & 0x10) != 0 )
    this->m_bitFields.m_bitFieldsAsDWORD = v23 | 0x400000;
  return v6;
}

```

## disassembly

```asm
0x1800a1868  mov     [rsp-38h+arg_18], rbx
0x1800a186d  push    rbp
0x1800a186e  push    rsi
0x1800a186f  push    rdi
0x1800a1870  push    r12
0x1800a1872  push    r13
0x1800a1874  push    r14
0x1800a1876  push    r15
0x1800a1878  mov     rbp, rsp
0x1800a187b  sub     rsp, 40h
0x1800a187f  xor     r15d, r15d
0x1800a1882  lea     rsi, [this+18h]
0x1800a1886  mov     rbx, this
0x1800a1889  mov     r12, strName
0x1800a188c  mov     this, [strName]
0x1800a188f  mov     r13d, r15d
0x1800a1892  test    cl, 1
0x1800a1895  jnz     loc_1800A1B07
0x1800a189b  mov     edi, [this+8]
0x1800a189e  test    edi, edi
0x1800a18a0  js      loc_1800A1B89
0x1800a18a6  and     edi, 3FFFFFFFh
0x1800a18ac  mov     this, [rsi]
0x1800a18af  test    cl, 1
0x1800a18b2  jnz     loc_1800A1B18
0x1800a18b8  mov     eax, [this+8]
0x1800a18bb  test    eax, eax
0x1800a18bd  js      loc_1800A1B91
0x1800a18c3  and     eax, 3FFFFFFFh
0x1800a18c8  cmp     edi, eax
0x1800a18ca  jnz     short loc_1800A18E2
0x1800a18cc  xor     r8d, r8d; eCompareBehavior
0x1800a18cf  mov     strName, rsi; other
0x1800a18d2  mov     this, r12; this
0x1800a18d5  call    ?Compare@xstring_ptr_view@@QEBAHAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::Compare(xstring_ptr_view const &,xstrCompareBehavior)
0x1800a18da  test    eax, eax
0x1800a18dc  jz      loc_1800A1A52
0x1800a18e2  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits, 40h
0x1800a18e9  mov     rdi, r15
0x1800a18ec  jnz     loc_1800A1C36
0x1800a18f2  mov     ecx, [rbx+50h]
0x1800a18f5  mov     r14d, 800h
0x1800a18fb  mov     eax, ecx
0x1800a18fd  shr     eax, 5
0x1800a1900  test    al, 1
0x1800a1902  jz      loc_1800A1A7B
0x1800a1908  test    [rbx+50h], r14d
0x1800a190c  jz      short loc_1800A191F
0x1800a190e  mov     rax, [rbx+10h]
0x1800a1912  mov     this, [rax]
0x1800a1915  cmp     rbx, [this+68h]
0x1800a1919  jz      loc_1800A1C25
0x1800a191f  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800a1926  lea     this, [rbp+strOldName]
0x1800a192a  mov     qword ptr [rbp+strOldName.m_encodedStorage.___u0], rax
0x1800a192e  mov     r14, rax
0x1800a1931  mov     qword ptr [rbp+var_8.m_encodedStorage.___u0], rax
0x1800a1935  cmp     this, rsi
0x1800a1938  jz      short loc_1800A1961
0x1800a193a  mov     r15, [rsi]
0x1800a193d  mov     [rsi], rax
0x1800a1940  test    r14b, 1
0x1800a1944  jz      short loc_1800A1953
0x1800a1946  mov     this, rax
0x1800a1949  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800a194d  call    cs:__imp_WindowsDeleteString
0x1800a1953  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800a195a  mov     qword ptr [rbp+strOldName.m_encodedStorage.___u0], r15
0x1800a195e  xor     r15d, r15d
0x1800a1961  lea     this, [rbp+var_8]
0x1800a1965  cmp     rsi, this
0x1800a1968  jz      short loc_1800A1983
0x1800a196a  mov     this, [rsi]
0x1800a196d  mov     qword ptr [rbp+var_8.m_encodedStorage.___u0], rax
0x1800a1971  test    cl, 1
0x1800a1974  jz      short loc_1800A1980
0x1800a1976  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800a197a  call    cs:__imp_WindowsDeleteString
0x1800a1980  mov     [rsi], r14
0x1800a1983  lea     this, [rbp+var_8]; this
0x1800a1987  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800a198c  test    rdi, rdi
0x1800a198f  jnz     loc_1800A1ABD
0x1800a1995  cmp     rsi, r12
0x1800a1998  jz      loc_1800A1A49
0x1800a199e  mov     rax, [r12]
0x1800a19a2  test    al, 1
0x1800a19a4  jnz     loc_1800A1AE4
0x1800a19aa  test    rax, rax
0x1800a19ad  jz      loc_1800A1AB4
0x1800a19b3  mov     edx, [rax+8]
0x1800a19b6  bt      edx, 1Eh
0x1800a19ba  jnb     loc_1800A1AB4
0x1800a19c0  mov     [rbp+pcStowedExceptions], r15d
0x1800a19c4  mov     rax, [rax]
0x1800a19c7  test    edx, edx
0x1800a19c9  js      loc_1800A1B96
0x1800a19cf  and     edx, 3FFFFFFFh; length
0x1800a19d5  mov     [rbp+pcStowedExceptions], edx
0x1800a19d8  lea     r8, [rbp+string]; string
0x1800a19dc  mov     this, rax; sourceString
0x1800a19df  call    cs:__imp_WindowsCreateString
0x1800a19e5  test    eax, eax
0x1800a19e7  jns     loc_1800A1AFD
0x1800a19ed  mov     ecx, eax; failedFrameHR
0x1800a19ef  call    OnFailure_2990_
0x1800a19f4  mov     edi, 8000FFFFh
0x1800a19f9  mov     [rbp+pppStowedExceptions], r15
0x1800a19fd  mov     ecx, edi; errorCode
0x1800a19ff  mov     [rbp+pcStowedExceptions], r15d
0x1800a1a03  call    TraceForFailFast
0x1800a1a08  xor     r8d, r8d; contextRecord
0x1800a1a0b  xor     edx, edx; directCallerReturnAddress
0x1800a1a0d  mov     ecx, edi; failedFrameHR
0x1800a1a0f  call    OnNewFailureEncountered
0x1800a1a14  lea     strName, [rbp+pcStowedExceptions]; pcStowedExceptions
0x1800a1a18  lea     this, [rbp+pppStowedExceptions]; pppStowedExceptions
0x1800a1a1c  call    GetStowedExceptionsForFailFast
0x1800a1a21  mov     r8, [rbp+pppStowedExceptions]
0x1800a1a25  mov     ecx, edi
0x1800a1a27  mov     edx, [rbp+pcStowedExceptions]
0x1800a1a2a  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1800a1a30  mov     this, [rsi]
0x1800a1a33  test    cl, 1
0x1800a1a36  jz      short loc_1800A1A42
0x1800a1a38  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800a1a3c  call    cs:__imp_WindowsDeleteString
0x1800a1a42  mov     rax, [rbp+string]
0x1800a1a46  mov     [rsi], rax
0x1800a1a49  lea     this, [rbp+strOldName]; this
0x1800a1a4d  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800a1a52  mov     eax, [rbx+50h]
0x1800a1a55  test    al, 10h
0x1800a1a57  jz      short $Cleanup_355
0x1800a1a59  bts     eax, 16h
0x1800a1a5d  mov     [rbx+50h], eax
0x1800a1a60  mov     rbx, [rsp+40h+arg_18]
0x1800a1a68  mov     eax, r13d
0x1800a1a6b  add     rsp, 40h
0x1800a1a6f  pop     r15
0x1800a1a71  pop     r14
0x1800a1a73  pop     r13
0x1800a1a75  pop     r12
0x1800a1a77  pop     rdi
0x1800a1a78  pop     rsi
0x1800a1a79  pop     rbp
0x1800a1a7a  retn
0x1800a1a7b  test    r14d, ecx
0x1800a1a7e  jnz     loc_1800A1908
0x1800a1a84  mov     rax, rbx
0x1800a1a87  test    cl, 4
0x1800a1a8a  jnz     loc_1800A1C05
0x1800a1a90  test    rax, rax
0x1800a1a93  jz      loc_1800A1908
0x1800a1a99  xor     edx, edx; pFirstOwner
0x1800a1a9b  mov     this, rax; this
0x1800a1a9e  call    ?GetStandardNameScopeOwnerInternal@CDependencyObject@@IEAAPEAV1@PEAV1@@Z; CDependencyObject::GetStandardNameScopeOwnerInternal(CDependencyObject *)
0x1800a1aa3  mov     rdi, rax
0x1800a1aa6  test    rax, rax
0x1800a1aa9  jnz     loc_1800A191F
0x1800a1aaf  jmp     loc_1800A1908
0x1800a1ab4  mov     [rbp+string], rax
0x1800a1ab8  jmp     loc_1800A1A30
0x1800a1abd  mov     strName, rdi; pNamescopeOwner
0x1800a1ac0  mov     this, rbx; this
0x1800a1ac3  call    ?UnregisterName@CDependencyObject@@QEAAJPEAV1@@Z; CDependencyObject::UnregisterName(CDependencyObject *)
0x1800a1ac8  mov     r13d, eax
0x1800a1acb  test    eax, eax
0x1800a1acd  jns     short loc_1800A1B27
0x1800a1acf  mov     ecx, eax; failedFrameHR
0x1800a1ad1  call    OnFailure_2990_
0x1800a1ad6  lea     this, [rbp+strOldName]; this
0x1800a1ada  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800a1adf  jmp     $Cleanup_355
0x1800a1ae4  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800a1ae8  lea     strName, [rbp+string]; newString
0x1800a1aec  mov     this, rax; string
0x1800a1aef  call    cs:__imp_WindowsDuplicateString
0x1800a1af5  test    eax, eax
0x1800a1af7  js      loc_1800A1BAB
0x1800a1afd  or      [rbp+string], 1
0x1800a1b02  jmp     loc_1800A1A30
0x1800a1b07  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800a1b0b  call    cs:__imp_WindowsGetStringLen
0x1800a1b11  mov     edi, eax
0x1800a1b13  jmp     loc_1800A18AC
0x1800a1b18  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800a1b1c  call    cs:__imp_WindowsGetStringLen
0x1800a1b22  jmp     loc_1800A18C8
0x1800a1b27  mov     strName, r12; other
0x1800a1b2a  mov     this, rsi; this
0x1800a1b2d  call    ??4xstring_ptr@@QEAAAEAV0@AEBV0@@Z; xstring_ptr::operator=(xstring_ptr const &)
0x1800a1b32  mov     strName, [rbx]
0x1800a1b35  xor     r8d, r8d
0x1800a1b38  mov     this, rbx
0x1800a1b3b  mov     rax, [strName+168h]
0x1800a1b42  mov     strName, rdi
0x1800a1b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b4a  mov     r14d, eax
0x1800a1b4d  test    eax, eax
0x1800a1b4f  jns     loc_1800A1A49
0x1800a1b55  lea     strName, [rbp+strOldName]; _Right
0x1800a1b59  mov     this, rsi; _Left
0x1800a1b5c  call    ??$swap@Vxstring_ptr@@$0A@@std@@YAXAEAVxstring_ptr@@0@Z; std::swap<xstring_ptr,0>(xstring_ptr &,xstring_ptr &)
0x1800a1b61  mov     this, [rbx]
0x1800a1b64  xor     r8d, r8d
0x1800a1b67  mov     strName, rdi
0x1800a1b6a  mov     rax, [this+168h]
0x1800a1b71  mov     this, rbx
0x1800a1b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b79  mov     ecx, r14d; failedFrameHR
0x1800a1b7c  mov     r13d, r14d
0x1800a1b7f  call    OnFailure_2990_
0x1800a1b84  jmp     loc_1800A1AD6
0x1800a1b89  mov     this, [this]
0x1800a1b8c  jmp     loc_1800A1B0B
0x1800a1b91  mov     this, [this]
0x1800a1b94  jmp     short loc_1800A1B1C
0x1800a1b96  lea     strName, [rbp+pcStowedExceptions]; length
0x1800a1b9a  mov     this, rax; string
0x1800a1b9d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a1ba3  mov     edx, [rbp+pcStowedExceptions]
0x1800a1ba6  jmp     loc_1800A19D8
0x1800a1bab  mov     ecx, eax; failedFrameHR
0x1800a1bad  call    OnFailure_2990_
0x1800a1bb2  jmp     loc_1800A19F4
0x1800a1bb7  cmp     r15w, [rax]
0x1800a1bbb  jnz     loc_1800A1C55
0x1800a1bc1  lea     rax, pressedKeys
0x1800a1bc8  mov     r9, rbx; _Arg1
0x1800a1bcb  mov     [rsp+40h+Context], rax; Context
0x1800a1bd0  lea     r8, ElementSetNameId; _Arg0
0x1800a1bd7  lea     strName, ElementSetNameInfo; EventGuid
0x1800a1bde  call    McTemplateMofU0xz
0x1800a1be3  jmp     loc_1800A18F2
0x1800a1be8  lea     strName, [rbp+pcStowedExceptions]; pCount
0x1800a1bec  mov     [rbp+pcStowedExceptions], r15d
0x1800a1bf0  mov     this, r12; this
0x1800a1bf3  call    ?GetBufferAndCount@xencoded_string_ptr@@QEBAPEBGPEAI@Z; xencoded_string_ptr::GetBufferAndCount(uint *)
0x1800a1bf8  test    rax, rax
0x1800a1bfb  jz      short loc_1800A1BC1
0x1800a1bfd  cmp     [rbp+pcStowedExceptions], r15d
0x1800a1c01  jz      short loc_1800A1BC1
0x1800a1c03  jmp     short loc_1800A1BB7
0x1800a1c05  test    cl, 10h
0x1800a1c08  jz      loc_1800A1A90
0x1800a1c0e  mov     rax, [rbx]
0x1800a1c11  mov     this, rbx
0x1800a1c14  mov     rax, [rax+178h]
0x1800a1c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c20  jmp     loc_1800A1A90
0x1800a1c25  mov     this, [this+10h]
0x1800a1c29  test    this, this
0x1800a1c2c  jnz     short loc_1800A1C62
0x1800a1c2e  mov     rdi, r15
0x1800a1c31  jmp     loc_1800A191F
0x1800a1c36  mov     this, rbx; this
0x1800a1c39  call    ??$OfTypeByIndex@$0BDB@@CDependencyObject@@QEBA_NXZ; CDependencyObject::OfTypeByIndex<305>(void)
0x1800a1c3e  test    al, al
0x1800a1c40  jz      loc_1800A18F2
0x1800a1c46  test    byte ptr cs:Microsoft_Windows_XAMLEnableBits, 40h
0x1800a1c4d  jz      loc_1800A18F2
0x1800a1c53  jmp     short loc_1800A1BE8
0x1800a1c55  mov     this, r12; this
0x1800a1c58  call    ?GetBuffer@xstring_ptr_view@@QEBAPEBGXZ; xstring_ptr_view::GetBuffer(void)
0x1800a1c5d  jmp     loc_1800A1BC8
0x1800a1c62  mov     rax, [this]
0x1800a1c65  mov     rax, [rax+20h]
0x1800a1c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c6e  mov     rdi, rax
0x1800a1c71  jmp     loc_1800A191F
```
