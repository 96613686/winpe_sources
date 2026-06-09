# DirectUI::MetadataAPI::TryGetClassInfoByName(KnownNamespaceIndex,xstring_ptr_view const &,CClassInfo const * *)

- ea: `0x180195524`
- end: `0x18019583a`
- name: `?TryGetClassInfoByName@MetadataAPI@DirectUI@@SAJW4KnownNamespaceIndex@@AEBVxstring_ptr_view@@PEAPEBVCClassInfo@@@Z`
- size: `790`
- prototype: `HRESULT __fastcall(KnownNamespaceIndex eNamespaceIndex, const xstring_ptr_view *strTypeName, const CClassInfo **ppType)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18053d4b8`

## callees

- `0x180004bc0`
- `0x1800913b4`
- `0x1800c09f8`
- `0x1800d1d80`
- `0x1800d2fdc`
- `0x1800fe130`
- `0x180194584`
- `0x180195524`
- `0x18028a104`
- `0x1804e7328`
- `0x18069f6ac`
- `0x18076e110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180195564`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180195564`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801956ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180195775`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801956ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180195775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18019560f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18019560f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1801956cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18019580c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1801956cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18019580c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1801957c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1801957d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1801957c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1801957d1`

## pseudocode

```c
__int64 __fastcall DirectUI::MetadataAPI::TryGetClassInfoByName(
        KnownNamespaceIndex eNamespaceIndex,
        const xstring_ptr_view *strTypeName,
        const CClassInfo **ppType)
{
  unsigned int m_cBuffer; // esi
  const CNamespaceInfo *NamespaceByIndex; // rax
  xstring_ptr_storage *p_m_strNameStorage; // rcx
  int v9; // ebx
  UINT32 StringLen; // ebx
  unsigned __int64 RuntimeStringHandleMarker; // rcx
  int v12; // eax
  UINT32 v13; // eax
  UINT32 v14; // ebx
  unsigned int v15; // edi
  int v16; // eax
  unsigned int v17; // ebx
  HRESULT appended; // eax
  HRESULT v19; // eax
  HRESULT ClassInfoByFullName; // eax
  const CClassInfo *BuiltinClassInfoByName; // rax
  HSTRING Buffer; // rcx
  HSTRING v24; // rcx
  xstring_ptr strFullName; // [rsp+20h] [rbp-E0h] BYREF
  xstring_ptr strNamespaceName; // [rsp+28h] [rbp-D8h] BYREF
  TStringBuilder<96> strFullNameBuilder; // [rsp+30h] [rbp-D0h] BYREF

  if ( (unsigned __int16)eNamespaceIndex < (Windows_ApplicationModel_DataTransfer|Windows_UI) )
  {
    BuiltinClassInfoByName = (const CClassInfo *)DirectUI::MetadataAPI::GetBuiltinClassInfoByName(strTypeName);
    *ppType = BuiltinClassInfoByName;
    if ( BuiltinClassInfoByName )
      return 0;
  }
  EnterCriticalSection(&g_csStatic);
  strFullNameBuilder.m_hPreallocatedBuffer = 0;
  m_cBuffer = 96;
  strFullNameBuilder.m_pBuffer = strFullNameBuilder.m_inlineBuffer;
  *(_QWORD *)&strFullNameBuilder.m_cBuffer = 96;
  NamespaceByIndex = DirectUI::MetadataAPI::GetNamespaceByIndex(eNamespaceIndex);
  p_m_strNameStorage = &NamespaceByIndex->m_strNameStorage;
  strFullName.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
  strNamespaceName.m_encodedStorage.Storage = &NamespaceByIndex->m_strNameStorage;
  if ( (((_BYTE)NamespaceByIndex + 4) & 1) != 0 )
  {
    Buffer = (HSTRING)((unsigned __int64)p_m_strNameStorage & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v9 = *((_DWORD *)&NamespaceByIndex->m_strNameStorage + 2);
    if ( v9 >= 0 )
    {
      StringLen = v9 & 0x3FFFFFFF;
      goto LABEL_5;
    }
    Buffer = (HSTRING)p_m_strNameStorage->Buffer;
  }
  StringLen = WindowsGetStringLen(Buffer);
LABEL_5:
  RuntimeStringHandleMarker = strTypeName->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (strTypeName->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v24 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v12 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
    if ( v12 >= 0 )
    {
      v13 = v12 & 0x3FFFFFFF;
      goto LABEL_8;
    }
    v24 = *(HSTRING *)RuntimeStringHandleMarker;
  }
  v13 = WindowsGetStringLen(v24);
LABEL_8:
  v14 = v13 + StringLen + 1;
  if ( v14 >= 0x7FFFFF9F )
  {
    v17 = -2147418113;
    OnNewFailure_2955_(RuntimeStringHandleMarker);
  }
  else
  {
    v15 = v14 + 1;
    if ( strFullNameBuilder.m_pBuffer == strFullNameBuilder.m_inlineBuffer )
    {
      m_cBuffer = strFullNameBuilder.m_cBuffer;
    }
    else
    {
      WindowsDeleteStringBuffer(strFullNameBuilder.m_hPreallocatedBuffer);
      strFullNameBuilder.m_hPreallocatedBuffer = 0;
      strFullNameBuilder.m_pBuffer = strFullNameBuilder.m_inlineBuffer;
      strFullNameBuilder.m_cBuffer = 96;
    }
    if ( v15 <= m_cBuffer )
    {
LABEL_14:
      strFullNameBuilder.m_cActual = 0;
      appended = TStringBuilder<96>::Append(&strFullNameBuilder, &strNamespaceName);
      v17 = appended;
      if ( appended < 0
        || (appended = TStringBuilder<96>::AppendChar(&strFullNameBuilder, 0x2Eu), v17 = appended, appended < 0)
        || (appended = TStringBuilder<96>::Append(&strFullNameBuilder, strTypeName), v17 = appended, appended < 0) )
      {
        OnFailure_2990_(appended);
      }
      else
      {
        v19 = TStringBuilder<96>::DetachString(&strFullNameBuilder, &strFullName);
        v17 = v19;
        if ( v19 >= 0 )
        {
          ClassInfoByFullName = DirectUI::MetadataAPI::TryGetClassInfoByFullName(&strFullName, 1, ppType);
          v17 = ClassInfoByFullName;
          if ( ClassInfoByFullName >= 0 )
          {
            xstring_ptr::~xstring_ptr(&strFullName);
            xstring_ptr::~xstring_ptr(&strNamespaceName);
            if ( strFullNameBuilder.m_pBuffer != strFullNameBuilder.m_inlineBuffer )
            {
              WindowsDeleteStringBuffer(strFullNameBuilder.m_hPreallocatedBuffer);
              strFullNameBuilder.m_hPreallocatedBuffer = 0;
            }
            strFullNameBuilder.m_pBuffer = 0;
            LeaveCriticalSection(&g_csStatic);
            return 0;
          }
          OnFailure_2990_(ClassInfoByFullName);
          goto LABEL_33;
        }
        OnFailure_2990_(v19);
      }
      xstring_ptr::~xstring_ptr(&strFullName);
      xstring_ptr::~xstring_ptr(&strNamespaceName);
      if ( strFullNameBuilder.m_pBuffer != strFullNameBuilder.m_inlineBuffer )
      {
        WindowsDeleteStringBuffer(strFullNameBuilder.m_hPreallocatedBuffer);
        strFullNameBuilder.m_hPreallocatedBuffer = 0;
      }
      strFullNameBuilder.m_pBuffer = 0;
      goto LABEL_29;
    }
    v16 = WindowsPreallocateStringBuffer(v14, &strFullNameBuilder.m_pBuffer, &strFullNameBuilder.m_hPreallocatedBuffer);
    v17 = v16;
    if ( v16 >= 0 )
    {
      strFullNameBuilder.m_cBuffer = v15;
      goto LABEL_14;
    }
    OnFailure_2990_(v16);
  }
  OnFailure_2990_(v17);
LABEL_33:
  xstring_ptr::~xstring_ptr(&strFullName);
  xstring_ptr::~xstring_ptr(&strNamespaceName);
  TStringBuilder<16>::~TStringBuilder<16>(&strFullNameBuilder);
LABEL_29:
  LeaveCriticalSection(&g_csStatic);
  return v17;
}

```

## disassembly

```asm
0x180195524  mov     [rsp-8+arg_18], rbx
0x180195529  push    rbp
0x18019552a  push    rsi
0x18019552b  push    rdi
0x18019552c  push    r14
0x18019552e  push    r15
0x180195530  lea     rbp, [rsp-20h]
0x180195535  sub     rsp, 120h
0x18019553c  mov     rax, cs:__security_cookie
0x180195543  xor     rax, rsp
0x180195546  mov     [rbp+40h+var_30], rax
0x18019554a  mov     r15, ppType
0x18019554d  mov     r14, strTypeName
0x180195550  movzx   ebx, eNamespaceIndex
0x180195553  cmp     eNamespaceIndex, 31h ; '1'
0x180195557  jb      loc_180195715
0x18019555d  lea     rcx, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180195564  call    cs:__imp_EnterCriticalSection
0x18019556a  lea     rax, [rsp+140h+strFullNameBuilder.m_inlineBuffer]
0x18019556f  mov     [rsp+140h+strFullNameBuilder.m_hPreallocatedBuffer], 0
0x180195578  mov     esi, 60h ; '`'
0x18019557d  mov     [rsp+140h+strFullNameBuilder.m_pBuffer], rax
0x180195582  movzx   ecx, bx; eNamespaceIndex
0x180195585  mov     qword ptr [rsp+140h+strFullNameBuilder.m_cBuffer], rsi
0x18019558a  call    ?GetNamespaceByIndex@MetadataAPI@DirectUI@@SAPEBVCNamespaceInfo@@W4KnownNamespaceIndex@@@Z; DirectUI::MetadataAPI::GetNamespaceByIndex(KnownNamespaceIndex)
0x18019558f  mov     edi, 3FFFFFFFh
0x180195594  lea     rcx, [rax+4]
0x180195598  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x18019559f  mov     qword ptr [rsp+140h+strFullName.m_encodedStorage.___u0], rax
0x1801955a4  mov     qword ptr [rsp+140h+strNamespaceName.m_encodedStorage.___u0], rcx
0x1801955a9  test    cl, 1
0x1801955ac  jnz     loc_1801957BC
0x1801955b2  mov     ebx, [rcx+8]
0x1801955b5  test    ebx, ebx
0x1801955b7  js      loc_1801957FD
0x1801955bd  and     ebx, edi
0x1801955bf  mov     rcx, [r14]; failedFrameHR
0x1801955c2  test    cl, 1
0x1801955c5  jnz     loc_1801957CD
0x1801955cb  mov     eax, [rcx+8]
0x1801955ce  test    eax, eax
0x1801955d0  js      loc_180195802
0x1801955d6  and     eax, edi
0x1801955d8  inc     ebx
0x1801955da  add     ebx, eax
0x1801955dc  cmp     ebx, 7FFFFF9Fh
0x1801955e2  jnb     loc_18019578B
0x1801955e8  lea     rax, [rsp+140h+strFullNameBuilder.m_inlineBuffer]
0x1801955ed  lea     edi, [rbx+1]
0x1801955f0  cmp     [rsp+140h+strFullNameBuilder.m_pBuffer], rax
0x1801955f5  jnz     loc_180195807
0x1801955fb  mov     esi, [rsp+140h+strFullNameBuilder.m_cBuffer]
0x1801955ff  cmp     edi, esi
0x180195601  jbe     short loc_180195623
0x180195603  lea     ppType, [rsp+140h+strFullNameBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180195608  mov     ecx, ebx; length
0x18019560a  lea     strTypeName, [rsp+140h+strFullNameBuilder]; charBuffer
0x18019560f  call    cs:__imp_WindowsPreallocateStringBuffer
0x180195615  mov     ebx, eax
0x180195617  test    eax, eax
0x180195619  js      loc_1801957F4
0x18019561f  mov     [rsp+140h+strFullNameBuilder.m_cBuffer], edi
0x180195623  lea     strTypeName, [rsp+140h+strNamespaceName]; strToAppend
0x180195628  mov     [rsp+140h+strFullNameBuilder.m_cActual], 0
0x180195630  lea     rcx, [rsp+140h+strFullNameBuilder]; this
0x180195635  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x18019563a  mov     ebx, eax
0x18019563c  test    eax, eax
0x18019563e  js      loc_1801957DC
0x180195644  mov     edx, 2Eh ; '.'; ch
0x180195649  lea     rcx, [rsp+140h+strFullNameBuilder]; this
0x18019564e  call    ?AppendChar@?$TStringBuilder@$0GA@@@QEAAJG@Z; TStringBuilder<96>::AppendChar(ushort)
0x180195653  mov     ebx, eax
0x180195655  test    eax, eax
0x180195657  js      loc_1801957E8
0x18019565d  mov     strTypeName, r14; strToAppend
0x180195660  lea     rcx, [rsp+140h+strFullNameBuilder]; this
0x180195665  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x18019566a  mov     ebx, eax
0x18019566c  test    eax, eax
0x18019566e  js      loc_180195782
0x180195674  lea     strTypeName, [rsp+140h+strFullName]; pstrDetachedString
0x180195679  lea     rcx, [rsp+140h+strFullNameBuilder]; this
0x18019567e  call    ?DetachString@?$TStringBuilder@$0GA@@@QEAAJPEAVxstring_ptr@@@Z; TStringBuilder<96>::DetachString(xstring_ptr *)
0x180195683  mov     ebx, eax
0x180195685  test    eax, eax
0x180195687  js      loc_18019572A
0x18019568d  mov     ppType, r15; ppType
0x180195690  lea     rcx, [rsp+140h+strFullName]; strTypeFullName
0x180195695  mov     dl, 1; bSearchCustomTypesOnly
0x180195697  call    ?TryGetClassInfoByFullName@MetadataAPI@DirectUI@@CAJAEBVxstring_ptr_view@@_NPEAPEBVCClassInfo@@@Z; DirectUI::MetadataAPI::TryGetClassInfoByFullName(xstring_ptr_view const &,bool,CClassInfo const * *)
0x18019569c  mov     ebx, eax
0x18019569e  test    eax, eax
0x1801956a0  js      loc_18019582E
0x1801956a6  lea     rcx, [rsp+140h+strFullName]; this
0x1801956ab  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801956b0  lea     rcx, [rsp+140h+strNamespaceName]; this
0x1801956b5  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801956ba  lea     rax, [rsp+140h+strFullNameBuilder.m_inlineBuffer]
0x1801956bf  cmp     [rsp+140h+strFullNameBuilder.m_pBuffer], rax
0x1801956c4  jz      short loc_1801956DA
0x1801956c6  mov     rcx, [rsp+140h+strFullNameBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1801956cb  call    cs:__imp_WindowsDeleteStringBuffer
0x1801956d1  mov     [rsp+140h+strFullNameBuilder.m_hPreallocatedBuffer], 0
0x1801956da  lea     rcx, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801956e1  mov     [rsp+140h+strFullNameBuilder.m_pBuffer], 0
0x1801956ea  call    cs:__imp_LeaveCriticalSection
0x1801956f0  xor     eax, eax
0x1801956f2  mov     rcx, [rbp+40h+var_30]
0x1801956f6  xor     rcx, rsp; StackCookie
0x1801956f9  call    __security_check_cookie
0x1801956fe  mov     rbx, [rsp+140h+arg_18]
0x180195706  add     rsp, 120h
0x18019570d  pop     r15
0x18019570f  pop     r14
0x180195711  pop     rdi
0x180195712  pop     rsi
0x180195713  pop     rbp
0x180195714  retn
0x180195715  mov     rcx, r14; strTypeName
0x180195718  call    ?GetBuiltinClassInfoByName@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@AEBVxstring_ptr_view@@@Z; DirectUI::MetadataAPI::GetBuiltinClassInfoByName(xstring_ptr_view const &)
0x18019571d  mov     [r15], rax
0x180195720  test    rax, rax
0x180195723  jnz     short loc_1801956F0
0x180195725  jmp     loc_18019555D
0x18019572a  mov     ecx, eax; failedFrameHR
0x18019572c  call    OnFailure_2990_
0x180195731  lea     rcx, [rsp+140h+strFullName]; this
0x180195736  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18019573b  lea     rcx, [rsp+140h+strNamespaceName]; this
0x180195740  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180195745  lea     rax, [rsp+140h+strFullNameBuilder.m_inlineBuffer]
0x18019574a  cmp     [rsp+140h+strFullNameBuilder.m_pBuffer], rax
0x18019574f  jz      short loc_180195765
0x180195751  mov     rcx, [rsp+140h+strFullNameBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180195756  call    cs:__imp_WindowsDeleteStringBuffer
0x18019575c  mov     [rsp+140h+strFullNameBuilder.m_hPreallocatedBuffer], 0
0x180195765  mov     [rsp+140h+strFullNameBuilder.m_pBuffer], 0
0x18019576e  lea     rcx, ?g_csStatic@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180195775  call    cs:__imp_LeaveCriticalSection
0x18019577b  mov     eax, ebx
0x18019577d  jmp     loc_1801956F2
0x180195782  mov     ecx, eax; failedFrameHR
0x180195784  call    OnFailure_2990_
0x180195789  jmp     short loc_180195731
0x18019578b  mov     ebx, 8000FFFFh
0x180195790  call    OnNewFailure_2955_
0x180195795  mov     ecx, ebx; failedFrameHR
0x180195797  call    OnFailure_2990_
0x18019579c  lea     rcx, [rsp+140h+strFullName]; this
0x1801957a1  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801957a6  lea     rcx, [rsp+140h+strNamespaceName]; this
0x1801957ab  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1801957b0  lea     rcx, [rsp+140h+strFullNameBuilder]; this
0x1801957b5  call    ??1?$TStringBuilder@$0BA@@@QEAA@XZ; TStringBuilder<16>::~TStringBuilder<16>(void)
0x1801957ba  jmp     short loc_18019576E
0x1801957bc  and     rcx, 0FFFFFFFFFFFFFFFEh; string
0x1801957c0  call    cs:__imp_WindowsGetStringLen
0x1801957c6  mov     ebx, eax
0x1801957c8  jmp     loc_1801955BF
0x1801957cd  and     rcx, 0FFFFFFFFFFFFFFFEh; string
0x1801957d1  call    cs:__imp_WindowsGetStringLen
0x1801957d7  jmp     loc_1801955D8
0x1801957dc  mov     ecx, eax; failedFrameHR
0x1801957de  call    OnFailure_2990_
0x1801957e3  jmp     loc_180195731
0x1801957e8  mov     ecx, eax; failedFrameHR
0x1801957ea  call    OnFailure_2990_
0x1801957ef  jmp     loc_180195731
0x1801957f4  mov     ecx, eax; failedFrameHR
0x1801957f6  call    OnFailure_2990_
0x1801957fb  jmp     short loc_180195795
0x1801957fd  mov     rcx, [rcx]
0x180195800  jmp     short loc_1801957C0
0x180195802  mov     rcx, [rcx]
0x180195805  jmp     short loc_1801957D1
0x180195807  mov     rcx, [rsp+140h+strFullNameBuilder.m_hPreallocatedBuffer]; bufferHandle
0x18019580c  call    cs:__imp_WindowsDeleteStringBuffer
0x180195812  lea     rax, [rsp+140h+strFullNameBuilder.m_inlineBuffer]
0x180195817  mov     [rsp+140h+strFullNameBuilder.m_hPreallocatedBuffer], 0
0x180195820  mov     [rsp+140h+strFullNameBuilder.m_pBuffer], rax
0x180195825  mov     [rsp+140h+strFullNameBuilder.m_cBuffer], esi
0x180195829  jmp     loc_1801955FF
0x18019582e  mov     ecx, eax; failedFrameHR
0x180195830  call    OnFailure_2990_
0x180195835  jmp     loc_18019579C
```
