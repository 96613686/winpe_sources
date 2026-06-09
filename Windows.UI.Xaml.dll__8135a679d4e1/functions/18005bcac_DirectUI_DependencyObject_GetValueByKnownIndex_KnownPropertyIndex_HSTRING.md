# DirectUI::DependencyObject::GetValueByKnownIndex(KnownPropertyIndex,HSTRING__ * *)

- ea: `0x18005bcac`
- end: `0x18005c1c0`
- name: `?GetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAPEAUHSTRING__@@@Z`
- size: `1300`
- prototype: `HRESULT __fastcall(DirectUI::DependencyObject *this, KnownPropertyIndex nPropertyIndex, HSTRING__ **pValue)`
- caller_count: `172`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005abdc`
- `0x18005bb70`
- `0x18005bb8c`
- `0x18005bc90`
- `0x18005d590`
- `0x18005d848`
- `0x180167bd0`
- `0x180303154`
- `0x1803038d0`
- `0x180305770`
- `0x180348f08`
- `0x18034c960`
- `0x18034ca9c`
- `0x18037c410`
- `0x18037dda0`
- `0x180381280`
- `0x180387a50`
- `0x18051d250`
- `0x18052c2a0`
- `0x18052c79c`
- `0x18057ebe0`
- `0x1805b60f0`
- `0x1805d8cc4`
- `0x1805e0760`
- `0x180607d60`
- `0x180609a90`
- `0x18060f0f0`
- `0x180611310`
- `0x18061eab0`
- `0x180626840`
- `0x1806284d0`
- `0x18062c980`
- `0x180635e68`
- `0x180643e00`
- `0x180646280`
- `0x18064c9c0`
- `0x18064cd00`
- `0x180654740`
- `0x18065a1f0`
- `0x18065c320`
- `0x1806658f0`
- `0x180666a70`
- `0x18066c1d0`
- `0x18066d260`
- `0x18066eb80`
- `0x1806781e0`
- `0x180678220`
- `0x1806810d0`
- `0x1806d84e0`
- `0x1806f8520`

## callees

- `0x180004bc0`
- `0x1800217b8`
- `0x180021840`
- `0x180021970`
- `0x18005bcac`
- `0x180065258`
- `0x1800ab600`
- `0x1800af8e0`
- `0x1800cb024`
- `0x1800cc4a4`
- `0x1800fe130`
- `0x180101870`
- `0x18018fa54`
- `0x1801e9130`
- `0x180254ef4`
- `0x18046d9c4`
- `0x1806877a8`
- `0x180687890`
- `0x180688828`
- `0x18069f6ac`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bd06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bd06`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005bd4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005bd4b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18005c13c`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18005c13c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bff1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bff1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005be7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005be7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c08b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c161`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c08b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c161`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005c02c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005c02c`

## pseudocode

```c
HRESULT __fastcall DirectUI::DependencyObject::GetValueByKnownIndex(
        DirectUI::DependencyObject *this,
        KnownPropertyIndex nPropertyIndex,
        HSTRING__ **pValue)
{
  unsigned int m_uThreadId; // edi
  const CDependencyProperty *DependencyPropertyByIndex; // r14
  unsigned __int64 m_handleMask; // rcx
  __int64 v9; // rsi
  __int64 m_nIndex; // rdi
  const CClassInfo *ClassInfoByIndex; // rax
  bool v12; // al
  HRESULT v13; // eax
  HRESULT v14; // ecx
  HRESULT v15; // ebx
  unsigned __int64 v16; // rsi
  int v17; // eax
  unsigned __int64 RuntimeStringHandleMarker; // rbx
  int v19; // edx
  wchar_t *StringRawBuffer; // rax
  UINT32 v21; // edx
  int v22; // eax
  HRESULT v23; // edi
  unsigned __int64 m_handle; // rdx
  HRESULT v26; // ecx
  HSTRING v27; // rax
  int v28; // eax
  HSTRING v29; // rcx
  HSTRING__ *v30; // rax
  CDependencyObject *v31; // rax
  CString *v32; // rax
  HRESULT v33; // eax
  UINT32 length; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  xruntime_string_ptr pstrPromoted; // [rsp+30h] [rbp-40h] BYREF
  xstring_ptr v37; // [rsp+38h] [rbp-38h] BYREF
  xruntime_string_ptr v38; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v39; // [rsp+48h] [rbp-28h] BYREF
  int v40; // [rsp+50h] [rbp-20h]
  CValue boxedValue; // [rsp+58h] [rbp-18h] BYREF

  if ( !DirectUI::DXamlCore::s_quirkValidateRetVal && !pValue )
  {
    v40 = 1073741835;
    v39 = L"returnValue";
    v38.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
    xencoded_string_ptr::Reset(&v38);
    v38.m_encodedStorage.Storage = (const xstring_ptr_storage *)&v39;
    return DirectUI::ErrorHelper::OriginateError(-2147024809, &v38);
  }
  if ( (*((_BYTE *)&this->ctl::WeakReferenceSourceNoThreadId + 62) & 2) != 0 )
    m_uThreadId = this->m_uThreadId;
  else
    m_uThreadId = this->m_pDO->m_sharedState.m_ptr->m_value.m_coreServices->m_nThreadID;
  if ( m_uThreadId != GetCurrentThreadId() )
  {
    OnFailure_2990_(-2147417842);
    return -2147417842;
  }
  boxedValue = 0;
  DependencyPropertyByIndex = DirectUI::MetadataAPI::GetDependencyPropertyByIndex(nPropertyIndex);
  if ( !CQuirksMode2::m_quirkCacheSuppressions )
  {
    InitOnceExecuteOnce(&InitOnce, CQuirksMode2::InitOnceCallback, &qword_180F72750, 0);
    LODWORD(m_handleMask) = qword_180F72750;
    if ( ((*(unsigned __int8 *)qword_180F72750 >> 1) & 1) == 0 )
      goto LABEL_8;
LABEL_53:
    if ( (DependencyPropertyByIndex->m_flags & 0x20000) == 0 )
      goto LABEL_15;
    goto LABEL_8;
  }
  if ( CQuirksMode2::XamlQuirkIsEnabled(0x2004Bu) )
    goto LABEL_53;
LABEL_8:
  LODWORD(m_handleMask) = 648;
  if ( (DependencyPropertyByIndex->m_flags & 0x288) != 0x288 && (DependencyPropertyByIndex->m_flags & 0x1000) == 0 )
  {
    v9 = (unsigned __int16)this->GetTypeIndex(&this->ctl::WeakReferenceSourceNoThreadId);
    m_nIndex = (unsigned __int16)CPropertyBase::GetTargetType(&DependencyPropertyByIndex->CPropertyBase)->m_nIndex;
    if ( (_WORD)m_nIndex != (_WORD)v9 && (_DWORD)m_nIndex != 40 )
    {
      if ( (unsigned __int16)m_nIndex >= 0x43Cu || (unsigned __int16)v9 >= 0x43Cu )
      {
        ClassInfoByIndex = DirectUI::MetadataAPI::GetClassInfoByIndex((KnownTypeIndex)v9);
        v12 = DirectUI::MetadataAPI::CompareCustomTypesHelper(ClassInfoByIndex, (KnownTypeIndex)m_nIndex);
      }
      else
      {
        m_handle = c_aTypeCheckData[m_nIndex].m_handle;
        v12 = m_handle
           && (m_handleMask = c_aTypeCheckData[m_nIndex].m_handleMask, (m_handleMask & 0x800000000000LL) == 0)
           && (m_handleMask & c_aTypeCheckData[v9].m_handle) == m_handle;
      }
      if ( !v12 )
      {
        v23 = -2147418113;
        OnNewFailure_2955_(m_handleMask);
LABEL_65:
        OnFailure_2990_(v23);
        goto LABEL_62;
      }
    }
  }
LABEL_15:
  if ( (*((_BYTE *)&this->ctl::WeakReferenceSourceNoThreadId + 62) & 2) != 0
    || (m_handleMask = (unsigned __int64)this->m_pDO) == 0 )
  {
    v23 = -2147418113;
    v15 = -2147418113;
    OnNewFailure_2955_(m_handleMask);
    goto LABEL_68;
  }
  v13 = (*(__int64 (__fastcall **)(unsigned __int64, const CDependencyProperty *, CValue *))(*(_QWORD *)m_handleMask
                                                                                           + 32LL))(
          m_handleMask,
          DependencyPropertyByIndex,
          &boxedValue);
  v15 = v13;
  if ( v13 < 0 )
  {
    OnFailure_2990_(v13);
    v23 = v15;
LABEL_68:
    OnFailure_2990_(v15);
    goto LABEL_65;
  }
  if ( !pValue )
  {
    OnNewFailure_1172_(v14);
    v23 = -2147467261;
    goto LABEL_61;
  }
  v16 = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  v17 = *(_BYTE *)&boxedValue.m_flags.m_state.0 & 0x3F;
  RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  pstrPromoted.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  if ( v17 != 14 )
  {
    if ( v17 == 24 )
    {
      v31 = CValue::As<24>(&boxedValue);
      v32 = do_pointer_cast<CString>(v31);
      v33 = xstring_ptr_view::Promote(&v32->m_strString, &pstrPromoted);
      v23 = v33;
      if ( v33 >= 0 )
      {
        RuntimeStringHandleMarker = pstrPromoted.m_encodedStorage.RuntimeStringHandleMarker;
        goto LABEL_38;
      }
      OnFailure_2990_(v33);
      xencoded_string_ptr::Reset(&pstrPromoted);
    }
    else
    {
      if ( CValue::IsNull(&boxedValue) )
        goto LABEL_38;
      OnNewFailure_2955_(v26);
      xencoded_string_ptr::Reset(&pstrPromoted);
      v23 = -2147418113;
    }
LABEL_61:
    OnFailure_2990_(v23);
LABEL_62:
    CValue::ReleaseAndReset(&boxedValue);
    return v23;
  }
  string = (HSTRING)boxedValue.m_value;
  if ( !boxedValue.m_value.m_bool )
  {
    v37.m_encodedStorage.Storage = (const xstring_ptr_storage *)string;
    if ( string )
    {
      v19 = *((_DWORD *)string + 2);
      length = 0;
      StringRawBuffer = *(wchar_t **)string;
      if ( v19 < 0 )
      {
        StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)StringRawBuffer, &length);
        v21 = length;
      }
      else
      {
        v21 = v19 & 0x3FFFFFFF;
        length = v21;
      }
      v22 = WindowsCreateString(StringRawBuffer, v21, &string);
      v23 = v22;
      if ( v22 < 0 )
      {
        OnFailure_2990_(v22);
        OnFailure_2990_(v23);
LABEL_37:
        xstring_ptr::~xstring_ptr(&v37);
        if ( v23 >= 0 )
          goto LABEL_38;
        OnFailure_2990_(v23);
        OnFailure_2990_(v23);
        xencoded_string_ptr::Reset(&pstrPromoted);
        goto LABEL_61;
      }
      v27 = (HSTRING)((unsigned __int64)string | 1);
    }
    else
    {
      v23 = 0;
      v27 = 0;
    }
    string = v27;
    xencoded_string_ptr::Reset(&pstrPromoted);
    RuntimeStringHandleMarker = (unsigned __int64)string;
    pstrPromoted.m_encodedStorage.Storage = (const xstring_ptr_storage *)string;
    goto LABEL_37;
  }
  if ( WindowsDuplicateString((HSTRING)((unsigned __int64)string & 0xFFFFFFFFFFFFFFFEuLL), &string) < 0 )
  {
    v37.m_encodedStorage.Storage = 0;
    length = 0;
    TraceForFailFast(-2147418113);
    OnNewFailureEncountered(-2147418113, 0, 0);
    GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&v37, &length);
    RoFailFastWithErrorContextInternal2(
      -2147418113,
      length,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)v37.m_encodedStorage.Storage);
  }
  string = (HSTRING)((unsigned __int64)string | 1);
  xencoded_string_ptr::Reset(&pstrPromoted);
  RuntimeStringHandleMarker = (unsigned __int64)string;
LABEL_38:
  length = 0;
  if ( (RuntimeStringHandleMarker & 1) != 0 )
  {
    v29 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v28 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
    v29 = *(HSTRING *)RuntimeStringHandleMarker;
    if ( v28 >= 0 )
    {
      length = v28 & 0x3FFFFFFF;
      goto LABEL_41;
    }
  }
  v29 = (HSTRING)WindowsGetStringRawBuffer(v29, &length);
LABEL_41:
  if ( v29 && length && *(_WORD *)v29 )
  {
    v30 = (HSTRING__ *)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v30 = 0;
    v16 = RuntimeStringHandleMarker;
  }
  *pValue = v30;
  if ( (v16 & 1) != 0 )
    WindowsDeleteString((HSTRING)(v16 & 0xFFFFFFFFFFFFFFFEuLL));
  CValue::ReleaseAndReset(&boxedValue);
  return 0;
}

```

## disassembly

```asm
0x18005bcac  mov     [rsp-28h+arg_18], rbx
0x18005bcb1  push    rbp
0x18005bcb2  push    rsi
0x18005bcb3  push    rdi
0x18005bcb4  push    r14
0x18005bcb6  push    r15
0x18005bcb8  mov     rbp, rsp
0x18005bcbb  sub     rsp, 70h
0x18005bcbf  mov     rax, cs:__security_cookie
0x18005bcc6  xor     rax, rsp
0x18005bcc9  mov     [rbp+var_8], rax
0x18005bccd  cmp     cs:?s_quirkValidateRetVal@DXamlCore@DirectUI@@0EA, 0; uchar DirectUI::DXamlCore::s_quirkValidateRetVal
0x18005bcd4  mov     r15, pValue
0x18005bcd7  movzx   esi, nPropertyIndex
0x18005bcda  mov     rbx, this
0x18005bcdd  jnz     short loc_18005BCE8
0x18005bcdf  test    pValue, pValue
0x18005bce2  jz      loc_18005BECC
0x18005bce8  test    byte ptr [this+46h], 2
0x18005bcec  jnz     loc_18005C0F4
0x18005bcf2  mov     rax, [this+90h]
0x18005bcf9  mov     rdx, [rax+10h]
0x18005bcfd  mov     rax, [rdx]
0x18005bd00  mov     edi, [rax+0BCh]
0x18005bd06  call    cs:__imp_GetCurrentThreadId
0x18005bd0c  cmp     edi, eax
0x18005bd0e  jnz     loc_18005BE9E
0x18005bd14  xorps   xmm0, xmm0
0x18005bd17  movzx   ecx, si; ePropertyIndex
0x18005bd1a  movups  xmmword ptr [rbp+boxedValue.m_value], xmm0
0x18005bd1e  call    ?GetDependencyPropertyByIndex@MetadataAPI@DirectUI@@SAPEBVCDependencyProperty@@W4KnownPropertyIndex@@@Z; DirectUI::MetadataAPI::GetDependencyPropertyByIndex(KnownPropertyIndex)
0x18005bd23  cmp     cs:?m_quirkCacheSuppressions@CQuirksMode2@@0JA, 0; long CQuirksMode2::m_quirkCacheSuppressions
0x18005bd2a  mov     r14, rax
0x18005bd2d  jnz     loc_18005C051
0x18005bd33  xor     r9d, r9d; Context
0x18005bd36  lea     pValue, qword_180F72750; Parameter
0x18005bd3d  lea     rdx, ?InitOnceCallback@CQuirksMode2@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18005bd44  lea     this, InitOnce; InitOnce
0x18005bd4b  call    cs:__imp_InitOnceExecuteOnce
0x18005bd51  mov     this, cs:qword_180F72750
0x18005bd58  movzx   edx, byte ptr [this]
0x18005bd5b  shr     edx, 1
0x18005bd5d  and     edx, 1
0x18005bd60  jnz     loc_18005C063
0x18005bd66  mov     eax, [r14+8]
0x18005bd6a  mov     ecx, 288h
0x18005bd6f  and     eax, ecx
0x18005bd71  cmp     eax, ecx
0x18005bd73  jz      short loc_18005BDD0
0x18005bd75  test    dword ptr [r14+8], 1000h
0x18005bd7d  jnz     short loc_18005BDD0
0x18005bd7f  lea     this, [rbx+8]
0x18005bd83  mov     rax, [this]
0x18005bd86  mov     rax, [rax+38h]
0x18005bd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd8f  mov     this, r14; this
0x18005bd92  movzx   esi, ax
0x18005bd95  call    ?GetTargetType@CPropertyBase@@QEBAPEBVCClassInfo@@XZ; CPropertyBase::GetTargetType(void)
0x18005bd9a  movzx   edi, word ptr [rax]
0x18005bd9d  cmp     di, si
0x18005bda0  jz      short loc_18005BDD0
0x18005bda2  cmp     edi, 28h ; '('
0x18005bda5  jz      short loc_18005BDD0
0x18005bda7  mov     eax, 43Ch
0x18005bdac  cmp     di, ax
0x18005bdaf  jb      loc_18005BF0A
0x18005bdb5  movzx   ecx, si; eTypeIndex
0x18005bdb8  call    ?GetClassInfoByIndex@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::GetClassInfoByIndex(KnownTypeIndex)
0x18005bdbd  mov     this, rax; typeClass
0x18005bdc0  movzx   edx, di; targetType
0x18005bdc3  call    ?CompareCustomTypesHelper@MetadataAPI@DirectUI@@CA_NPEBVCClassInfo@@W4KnownTypeIndex@@@Z; DirectUI::MetadataAPI::CompareCustomTypesHelper(CClassInfo const *,KnownTypeIndex)
0x18005bdc8  test    al, al
0x18005bdca  jz      loc_18005C147
0x18005bdd0  test    byte ptr [rbx+46h], 2
0x18005bdd4  jnz     loc_18005C1B2
0x18005bdda  mov     this, [rbx+90h]
0x18005bde1  test    this, this
0x18005bde4  jz      loc_18005C1B2
0x18005bdea  mov     rax, [this]
0x18005bded  lea     pValue, [rbp+boxedValue]
0x18005bdf1  mov     rdx, r14
0x18005bdf4  mov     rax, [rax+20h]
0x18005bdf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdfd  mov     ebx, eax
0x18005bdff  test    eax, eax
0x18005be01  js      loc_18005C16F
0x18005be07  test    r15, r15
0x18005be0a  jz      loc_18005C1A3
0x18005be10  mov     eax, dword ptr [rbp+boxedValue.m_flags]
0x18005be13  lea     rsi, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x18005be1a  and     eax, 3Fh
0x18005be1d  mov     rbx, rsi
0x18005be20  mov     qword ptr [rbp+pstrPromoted.m_encodedStorage.___u0], rbx
0x18005be24  mov     r14d, 3FFFFFFFh
0x18005be2a  cmp     eax, 0Eh
0x18005be2d  jnz     loc_18005BF40
0x18005be33  mov     ecx, dword ptr [rbp+boxedValue.m_value]
0x18005be36  mov     eax, dword ptr [rbp+boxedValue.m_value+4]
0x18005be39  mov     dword ptr [rbp+string], ecx
0x18005be3c  mov     dword ptr [rbp+string+4], eax
0x18005be3f  test    cl, 1
0x18005be42  jnz     loc_18005C020
0x18005be48  mov     rax, [rbp+string]
0x18005be4c  mov     qword ptr [rbp+var_38.m_encodedStorage.___u0], rax
0x18005be50  test    rax, rax
0x18005be53  jz      loc_18005BF6E
0x18005be59  mov     edx, [rax+8]
0x18005be5c  mov     [rbp+length], 0
0x18005be63  mov     rax, [rax]
0x18005be66  test    edx, edx
0x18005be68  js      loc_18005C15A
0x18005be6e  and     edx, r14d; length
0x18005be71  mov     [rbp+length], edx
0x18005be74  lea     pValue, [rbp+string]; string
0x18005be78  mov     this, rax; sourceString
0x18005be7b  call    cs:__imp_WindowsCreateString
0x18005be81  mov     edi, eax
0x18005be83  test    eax, eax
0x18005be85  jns     loc_18005C181
0x18005be8b  mov     ecx, eax; failedFrameHR
0x18005be8d  call    OnFailure_2990_
0x18005be92  mov     ecx, edi; failedFrameHR
0x18005be94  call    OnFailure_2990_
0x18005be99  jmp     loc_18005BF87
0x18005be9e  mov     ebx, 8001010Eh
0x18005bea3  mov     ecx, ebx; failedFrameHR
0x18005bea5  call    OnFailure_2990_
0x18005beaa  mov     eax, ebx
0x18005beac  mov     this, [rbp+var_8]
0x18005beb0  xor     this, rsp; StackCookie
0x18005beb3  call    __security_check_cookie
0x18005beb8  mov     rbx, [rsp+70h+arg_18]
0x18005bec0  add     rsp, 70h
0x18005bec4  pop     r15
0x18005bec6  pop     r14
0x18005bec8  pop     rdi
0x18005bec9  pop     rsi
0x18005beca  pop     rbp
0x18005becb  retn
0x18005becc  lea     rax, ppInstance; "returnValue"
0x18005bed3  mov     [rbp+var_20], 4000000Bh
0x18005beda  lea     rsi, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x18005bee1  mov     [rbp+var_28], rax
0x18005bee5  lea     this, [rbp+var_30]; this
0x18005bee9  mov     qword ptr [rbp+var_30.m_encodedStorage.___u0], rsi
0x18005beed  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18005bef2  lea     rax, [rbp+var_28]
0x18005bef6  mov     ecx, 80070057h; hrEncountered
0x18005befb  lea     rdx, [rbp+var_30]; strErrorMessage
0x18005beff  mov     qword ptr [rbp+var_30.m_encodedStorage.___u0], rax
0x18005bf03  call    ?OriginateError@ErrorHelper@DirectUI@@SAJJAEBVxstring_ptr_view@@@Z; DirectUI::ErrorHelper::OriginateError(long,xstring_ptr_view const &)
0x18005bf08  jmp     short loc_18005BEAC
0x18005bf0a  cmp     si, ax
0x18005bf0d  jnb     loc_18005BDB5
0x18005bf13  mov     rax, rdi
0x18005bf16  lea     pValue, ?c_aTypeCheckData@@3QBUTypeCheckData@@B; TypeCheckData const near * const c_aTypeCheckData
0x18005bf1d  add     rax, rax
0x18005bf20  mov     rdx, [pValue+rax*8+8]
0x18005bf25  test    rdx, rdx
0x18005bf28  jz      short loc_18005BF39
0x18005bf2a  mov     this, [pValue+rax*8]
0x18005bf2e  bt      this, 2Fh ; '/'
0x18005bf33  jnb     loc_18005C007
0x18005bf39  xor     al, al
0x18005bf3b  jmp     loc_18005BDC8
0x18005bf40  lea     this, [rbp+boxedValue]; this
0x18005bf44  cmp     eax, 18h
0x18005bf47  jz      loc_18005C099
0x18005bf4d  call    ?IsNull@CValue@@QEBA_NXZ; CValue::IsNull(void)
0x18005bf52  test    al, al
0x18005bf54  jnz     short loc_18005BF98
0x18005bf56  call    OnNewFailure_2955_
0x18005bf5b  lea     this, [rbp+pstrPromoted]; this
0x18005bf5f  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18005bf64  mov     edi, 8000FFFFh
0x18005bf69  jmp     loc_18005C0DD
0x18005bf6e  xor     edi, edi
0x18005bf70  xor     eax, eax
0x18005bf72  lea     this, [rbp+pstrPromoted]; this
0x18005bf76  mov     [rbp+string], rax
0x18005bf7a  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18005bf7f  mov     rbx, [rbp+string]
0x18005bf83  mov     qword ptr [rbp+pstrPromoted.m_encodedStorage.___u0], rbx
0x18005bf87  lea     this, [rbp+var_38]; this
0x18005bf8b  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18005bf90  test    edi, edi
0x18005bf92  js      loc_18005C0C6
0x18005bf98  mov     [rbp+length], 0
0x18005bf9f  test    bl, 1
0x18005bfa2  jnz     loc_18005C080
0x18005bfa8  mov     eax, [rbx+8]
0x18005bfab  mov     this, [rbx]
0x18005bfae  test    eax, eax
0x18005bfb0  js      loc_18005C087
0x18005bfb6  and     eax, r14d
0x18005bfb9  mov     [rbp+length], eax
0x18005bfbc  test    this, this
0x18005bfbf  jz      loc_18005C076
0x18005bfc5  cmp     [rbp+length], 0
0x18005bfc9  jz      loc_18005C076
0x18005bfcf  xor     eax, eax
0x18005bfd1  cmp     ax, [this]
0x18005bfd4  jz      loc_18005C076
0x18005bfda  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18005bfde  mov     rax, rbx
0x18005bfe1  mov     [r15], rax
0x18005bfe4  test    sil, 1
0x18005bfe8  jz      short loc_18005BFF7
0x18005bfea  and     rsi, 0FFFFFFFFFFFFFFFEh
0x18005bfee  mov     this, rsi; string
0x18005bff1  call    cs:__imp_WindowsDeleteString
0x18005bff7  lea     this, [rbp+boxedValue]; this
0x18005bffb  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x18005c000  xor     eax, eax
0x18005c002  jmp     loc_18005BEAC
0x18005c007  mov     rax, rsi
0x18005c00a  add     rax, rax
0x18005c00d  mov     rax, [pValue+rax*8+8]
0x18005c012  and     rax, this
0x18005c015  cmp     rax, rdx
0x18005c018  setz    al
0x18005c01b  jmp     loc_18005BDC8
0x18005c020  mov     this, [rbp+string]
0x18005c024  lea     rdx, [rbp+string]; newString
0x18005c028  and     this, 0FFFFFFFFFFFFFFFEh; string
0x18005c02c  call    cs:__imp_WindowsDuplicateString
0x18005c032  test    eax, eax
0x18005c034  js      loc_18005C0FF
0x18005c03a  or      [rbp+string], 1
0x18005c03f  lea     this, [rbp+pstrPromoted]; this
0x18005c043  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18005c048  mov     rbx, [rbp+string]
0x18005c04c  jmp     loc_18005BF98
0x18005c051  mov     ecx, 2004Bh; quirk
0x18005c056  call    ?XamlQuirkIsEnabled@CQuirksMode2@@SA_NK@Z; CQuirksMode2::XamlQuirkIsEnabled(ulong)
0x18005c05b  test    al, al
0x18005c05d  jz      loc_18005BD66
0x18005c063  test    dword ptr [r14+8], 20000h
0x18005c06b  jz      loc_18005BDD0
0x18005c071  jmp     loc_18005BD66
0x18005c076  xor     eax, eax
0x18005c078  mov     rsi, rbx
0x18005c07b  jmp     loc_18005BFE1
0x18005c080  mov     this, rbx
0x18005c083  and     this, 0FFFFFFFFFFFFFFFEh; string
0x18005c087  lea     rdx, [rbp+length]; length
0x18005c08b  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c091  mov     this, rax
0x18005c094  jmp     loc_18005BFBC
0x18005c099  call    ??$As@$0BI@@CValue@@QEAAPEAVCDependencyObject@@XZ; CValue::As<24>(void)
0x18005c09e  mov     this, rax; pDO
0x18005c0a1  call    ??$do_pointer_cast@VCString@@@@YAPEAVCString@@PEAVCDependencyObject@@@Z; do_pointer_cast<CString>(CDependencyObject *)
0x18005c0a6  lea     rdx, [rbp+pstrPromoted]; pstrPromoted
0x18005c0aa  lea     this, [rax+60h]; this
0x18005c0ae  call    ?Promote@xstring_ptr_view@@QEBAJPEAVxruntime_string_ptr@@@Z; xstring_ptr_view::Promote(xruntime_string_ptr *)
0x18005c0b3  mov     edi, eax
0x18005c0b5  test    eax, eax
0x18005c0b7  js      loc_18005C18E
0x18005c0bd  mov     rbx, qword ptr [rbp+pstrPromoted.m_encodedStorage.___u0]
0x18005c0c1  jmp     loc_18005BF98
0x18005c0c6  mov     ecx, edi; failedFrameHR
0x18005c0c8  call    OnFailure_2990_
0x18005c0cd  mov     ecx, edi; failedFrameHR
0x18005c0cf  call    OnFailure_2990_
0x18005c0d4  lea     this, [rbp+pstrPromoted]; this
0x18005c0d8  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18005c0dd  mov     ecx, edi; failedFrameHR
0x18005c0df  call    OnFailure_2990_
0x18005c0e4  lea     this, [rbp+boxedValue]; this
0x18005c0e8  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x18005c0ed  mov     eax, edi
0x18005c0ef  jmp     loc_18005BEAC
0x18005c0f4  mov     edi, [this+90h]
0x18005c0fa  jmp     loc_18005BD06
0x18005c0ff  mov     edi, 8000FFFFh
0x18005c104  mov     qword ptr [rbp+var_38.m_encodedStorage.___u0], 0
0x18005c10c  mov     ecx, edi; errorCode
0x18005c10e  mov     [rbp+length], 0
0x18005c115  call    TraceForFailFast
0x18005c11a  xor     r8d, r8d; contextRecord
0x18005c11d  xor     edx, edx; directCallerReturnAddress
0x18005c11f  mov     ecx, edi; failedFrameHR
0x18005c121  call    OnNewFailureEncountered
0x18005c126  lea     rdx, [rbp+length]; pcStowedExceptions
0x18005c12a  lea     this, [rbp+var_38]; pppStowedExceptions
0x18005c12e  call    GetStowedExceptionsForFailFast
0x18005c133  mov     pValue, qword ptr [rbp+var_38.m_encodedStorage.___u0]
0x18005c137  mov     ecx, edi
0x18005c139  mov     edx, [rbp+length]
0x18005c13c  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x18005c142  jmp     loc_18005C03A
0x18005c147  mov     edi, 8000FFFFh
0x18005c14c  call    OnNewFailure_2955_
0x18005c151  mov     ecx, edi; failedFrameHR
0x18005c153  call    OnFailure_2990_
0x18005c158  jmp     short loc_18005C0E4
0x18005c15a  lea     rdx, [rbp+length]; length
0x18005c15e  mov     this, rax; string
0x18005c161  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c167  mov     edx, [rbp+length]
  ... truncated ...
```
