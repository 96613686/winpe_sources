# DirectUI::PropertyChangedEventArgs::get_PropertyName(HSTRING__ * *)

- ea: `0x18017f4c0`
- end: `0x18017f832`
- name: `?get_PropertyName@PropertyChangedEventArgs@DirectUI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `882`
- prototype: `HRESULT __fastcall(DirectUI::PropertyChangedEventArgs *this, HSTRING__ **pValue)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180004bc0`
- `0x1800af8e0`
- `0x1800fe130`
- `0x18017f4c0`
- `0x18017ffdc`
- `0x1801800b8`
- `0x1806b2e84`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017f4e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017f4e6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18017f683`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18017f683`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017f54b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017f54b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017f76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017f782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017f79c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017f76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017f782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017f79c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18017f4fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18017f4fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18017f7f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18017f7f8`
- `api-ms-win-core-winrt-error-l1-1-0!RoGetErrorReportingFlags` at `0x18017f665`
- `api-ms-win-core-winrt-error-l1-1-0!RoGetErrorReportingFlags` at `0x18017f665`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18017f64c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18017f64c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18017f6f2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18017f6f2`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18017f691`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18017f691`

## pseudocode

```c
__int64 __fastcall DirectUI::PropertyChangedEventArgs::get_PropertyName(
        DirectUI::PropertyChangedEventArgs *this,
        HSTRING__ **pValue)
{
  int v4; // eax
  unsigned int v5; // ebx
  PCWSTR StringRawBuffer; // rcx
  int v8; // eax
  HRESULT ErrorReportingFlags; // eax
  const xstring_ptr_storage *Storage; // rcx
  int v11; // eax
  const wchar_t *Buffer; // r8
  const wchar_t *v13; // rbx
  int v14; // eax
  UINT32 StringLen; // eax
  HRESULT v16; // ecx
  int v17; // eax
  HRESULT (__fastcall *SetDescription)(ICreateErrorInfo *, wchar_t *); // rbx
  const wchar_t *v19; // rax
  HSTRING v20; // rcx
  PCWSTR v21; // rax
  HSTRING v22; // rcx
  PCWSTR v23; // rax
  HSTRING v24; // rcx
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-30h] BYREF
  IErrorInfo *perrinfo; // [rsp+28h] [rbp-28h] BYREF
  xstring_ptr_view v27; // [rsp+30h] [rbp-20h] BYREF
  const wchar_t *v28; // [rsp+38h] [rbp-18h] BYREF
  int v29; // [rsp+40h] [rbp-10h]
  UINT32 length; // [rsp+70h] [rbp+20h] BYREF
  xstring_ptr pstrPromoted; // [rsp+78h] [rbp+28h] BYREF

  if ( DirectUI::DXamlCore::s_quirkValidateRetVal || pValue )
  {
    if ( LODWORD(this[-1].m_propertyName._hstring) == GetCurrentThreadId() )
    {
      v4 = WindowsDuplicateString(*(HSTRING *)&this->m_inFinalRelease, pValue);
      v5 = v4;
      if ( v4 < 0 )
        OnFailure_2990_(v4);
    }
    else
    {
      v5 = -2147417842;
      OnFailure_2990_(-2147417842);
    }
    return v5;
  }
  v27.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  StringRawBuffer = L"returnValue";
  v28 = L"returnValue";
  v8 = 1073741835;
  v29 = 1073741835;
  if ( ((unsigned __int8)&xstring_ptr_constants::c_xstring_ptr_storage_null & 1) != 0 )
  {
    WindowsDeleteString((HSTRING)((unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null
                                & 0xFFFFFFFFFFFFFFFEuLL));
    v8 = v29;
    StringRawBuffer = v28;
  }
  pstrPromoted.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  v27.m_encodedStorage.Storage = (const xstring_ptr_storage *)&v28;
  pperrinfo = 0;
  perrinfo = 0;
  length = 0;
  if ( ((unsigned __int8)&v28 & 1) != 0 )
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)&v28, &length);
  else
    length = v8 & 0x3FFFFFFF;
  if ( StringRawBuffer && length && *StringRawBuffer )
  {
    ErrorReportingFlags = xstring_ptr_view::Promote(&v27, &pstrPromoted);
    if ( ErrorReportingFlags < 0 )
      goto LABEL_48;
  }
  else
  {
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&pstrPromoted);
  }
  Storage = pstrPromoted.m_encodedStorage.Storage;
  length = 0;
  if ( ((__int64)pstrPromoted.m_encodedStorage.Storage & 1) != 0 )
  {
    v22 = (HSTRING)(pstrPromoted.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
LABEL_47:
    v23 = WindowsGetStringRawBuffer(v22, &length);
    Storage = pstrPromoted.m_encodedStorage.Storage;
    Buffer = v23;
    goto LABEL_18;
  }
  v11 = *((_DWORD *)pstrPromoted.m_encodedStorage.Storage + 2);
  Buffer = pstrPromoted.m_encodedStorage.Storage->Buffer;
  if ( v11 < 0 )
  {
    v22 = *(HSTRING *)pstrPromoted.m_encodedStorage.Handle;
    goto LABEL_47;
  }
  length = v11 & 0x3FFFFFFF;
LABEL_18:
  if ( !Buffer || !length || !*Buffer )
    goto LABEL_37;
  if ( ((unsigned __int8)Storage & 1) != 0 )
  {
    v20 = (HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    if ( *((int *)Storage + 2) >= 0 )
    {
      v13 = Storage->Buffer;
      goto LABEL_24;
    }
    v20 = (HSTRING)Storage->Buffer;
  }
  v21 = WindowsGetStringRawBuffer(v20, 0);
  Storage = pstrPromoted.m_encodedStorage.Storage;
  v13 = v21;
LABEL_24:
  if ( ((unsigned __int8)Storage & 1) != 0 )
  {
    v24 = (HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL);
LABEL_55:
    StringLen = WindowsGetStringLen(v24);
    goto LABEL_27;
  }
  v14 = *((_DWORD *)Storage + 2);
  if ( v14 < 0 )
  {
    v24 = (HSTRING)Storage->Buffer;
    goto LABEL_55;
  }
  StringLen = v14 & 0x3FFFFFFF;
LABEL_27:
  if ( !(unsigned int)RoOriginateErrorW(2147942487LL, StringLen, v13) )
  {
    OnNewFailure_1208_(v16);
    goto LABEL_37;
  }
  length = 0;
  ErrorReportingFlags = RoGetErrorReportingFlags(&length);
  if ( ErrorReportingFlags >= 0 )
  {
    if ( (length & 8) != 0 || (length & 4) == 0 && !IsDebuggerPresent() )
    {
      v17 = CreateErrorInfo(&pperrinfo);
      if ( v17 < 0
        || (SetDescription = pperrinfo->SetDescription,
            v19 = xstring_ptr_view::GetBuffer(&v27),
            v17 = SetDescription(pperrinfo, (wchar_t *)v19),
            v17 < 0)
        || (v17 = pperrinfo->QueryInterface(pperrinfo, &IID_IErrorInfo, (void **)&perrinfo), v17 < 0)
        || (v17 = SetErrorInfo(0, perrinfo), v17 < 0) )
      {
        OnFailure_2990_(v17);
      }
    }
    goto LABEL_37;
  }
LABEL_48:
  OnFailure_2990_(ErrorReportingFlags);
LABEL_37:
  if ( pperrinfo )
  {
    pperrinfo->Release(pperrinfo);
    pperrinfo = 0;
  }
  if ( perrinfo )
  {
    perrinfo->Release(perrinfo);
    perrinfo = 0;
  }
  xstring_ptr::~xstring_ptr(&pstrPromoted);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18017f4c0  mov     [rsp-8+arg_0], rbx
0x18017f4c5  mov     [rsp-8+arg_8], rdi
0x18017f4ca  push    rbp
0x18017f4cb  mov     rbp, rsp
0x18017f4ce  sub     rsp, 50h
0x18017f4d2  cmp     cs:?s_quirkValidateRetVal@DXamlCore@DirectUI@@0EA, 0; uchar DirectUI::DXamlCore::s_quirkValidateRetVal
0x18017f4d9  mov     rbx, pValue
0x18017f4dc  mov     rdi, this
0x18017f4df  jnz     short loc_18017F4E6
0x18017f4e1  test    pValue, pValue
0x18017f4e4  jz      short loc_18017F51E
0x18017f4e6  call    cs:__imp_GetCurrentThreadId
0x18017f4ec  cmp     [rdi-8], eax
0x18017f4ef  jnz     loc_18017F821
0x18017f4f5  mov     this, [rdi+8]; string
0x18017f4f9  mov     pValue, rbx; newString
0x18017f4fc  call    cs:__imp_WindowsDuplicateString
0x18017f502  mov     ebx, eax
0x18017f504  test    eax, eax
0x18017f506  js      loc_18017F815
0x18017f50c  mov     eax, ebx
0x18017f50e  mov     rbx, [rsp+50h+arg_0]
0x18017f513  mov     rdi, [rsp+50h+arg_8]
0x18017f518  add     rsp, 50h
0x18017f51c  pop     rbp
0x18017f51d  retn
0x18017f51e  lea     rbx, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x18017f525  mov     dil, 1
0x18017f528  mov     qword ptr [rbp+var_20.m_encodedStorage.___u0], rbx
0x18017f52c  lea     this, ppInstance; "returnValue"
0x18017f533  mov     [rbp+var_18], this
0x18017f537  mov     eax, 4000000Bh
0x18017f53c  mov     [rbp+var_10], eax
0x18017f53f  test    dil, bl
0x18017f542  jz      short loc_18017F558
0x18017f544  mov     this, rbx
0x18017f547  and     this, 0FFFFFFFFFFFFFFFEh; string
0x18017f54b  call    cs:__imp_WindowsDeleteString
0x18017f551  mov     eax, [rbp+var_10]
0x18017f554  mov     this, [rbp+var_18]
0x18017f558  lea     pValue, [rbp+var_18]
0x18017f55c  mov     qword ptr [rbp+pstrPromoted.m_encodedStorage.___u0], rbx
0x18017f560  mov     qword ptr [rbp+var_20.m_encodedStorage.___u0], pValue
0x18017f564  mov     [rbp+pperrinfo], 0
0x18017f56c  mov     [rbp+perrinfo], 0
0x18017f574  lea     pValue, [rbp+var_18]
0x18017f578  mov     [rbp+length], 0
0x18017f57f  test    dil, dl
0x18017f582  jnz     loc_18017F762
0x18017f588  test    eax, eax
0x18017f58a  js      loc_18017F76A
0x18017f590  and     eax, 3FFFFFFFh
0x18017f595  mov     [rbp+length], eax
0x18017f598  test    this, this
0x18017f59b  jz      loc_18017F754
0x18017f5a1  cmp     [rbp+length], 0
0x18017f5a5  jz      loc_18017F754
0x18017f5ab  xor     eax, eax
0x18017f5ad  cmp     ax, [this]
0x18017f5b0  jz      loc_18017F754
0x18017f5b6  lea     pValue, [rbp+pstrPromoted]; pstrPromoted
0x18017f5ba  lea     this, [rbp+var_20]; this
0x18017f5be  call    ?Promote@xstring_ptr_view@@QEBAJPEAVxstring_ptr@@@Z; xstring_ptr_view::Promote(xstring_ptr *)
0x18017f5c3  test    eax, eax
0x18017f5c5  js      loc_18017F7AE
0x18017f5cb  mov     this, qword ptr [rbp+pstrPromoted.m_encodedStorage.___u0]
0x18017f5cf  mov     [rbp+length], 0
0x18017f5d6  test    dil, cl
0x18017f5d9  jnz     loc_18017F794
0x18017f5df  mov     eax, [this+8]
0x18017f5e2  mov     r8, [this]
0x18017f5e5  test    eax, eax
0x18017f5e7  js      loc_18017F80B
0x18017f5ed  and     eax, 3FFFFFFFh
0x18017f5f2  mov     [rbp+length], eax
0x18017f5f5  test    r8, r8
0x18017f5f8  jz      loc_18017F703
0x18017f5fe  cmp     [rbp+length], 0
0x18017f602  jz      loc_18017F703
0x18017f608  xor     eax, eax
0x18017f60a  cmp     ax, [r8]
0x18017f60e  jz      loc_18017F703
0x18017f614  test    dil, cl
0x18017f617  jnz     loc_18017F77C
0x18017f61d  cmp     [this+8], eax
0x18017f620  jl      loc_18017F803
0x18017f626  mov     rbx, [this]
0x18017f629  test    dil, cl
0x18017f62c  jnz     loc_18017F7F4
0x18017f632  mov     eax, [this+8]
0x18017f635  test    eax, eax
0x18017f637  js      loc_18017F810
0x18017f63d  and     eax, 3FFFFFFFh
0x18017f642  mov     r8, rbx
0x18017f645  mov     edx, eax
0x18017f647  mov     ecx, 80070057h
0x18017f64c  call    cs:__imp_RoOriginateErrorW
0x18017f652  test    eax, eax
0x18017f654  jz      loc_18017F7EA
0x18017f65a  lea     this, [rbp+length]
0x18017f65e  mov     [rbp+length], 0
0x18017f665  call    cs:__imp_RoGetErrorReportingFlags
0x18017f66b  test    eax, eax
0x18017f66d  js      loc_18017F7DE
0x18017f673  test    byte ptr [rbp+length], 8
0x18017f677  jnz     short loc_18017F68D
0x18017f679  test    byte ptr [rbp+length], 4
0x18017f67d  jnz     loc_18017F703
0x18017f683  call    cs:__imp_IsDebuggerPresent
0x18017f689  test    eax, eax
0x18017f68b  jnz     short loc_18017F703
0x18017f68d  lea     this, [rbp+pperrinfo]; pperrinfo
0x18017f691  call    cs:__imp_CreateErrorInfo
0x18017f697  test    eax, eax
0x18017f699  js      loc_18017F7D2
0x18017f69f  mov     rax, [rbp+pperrinfo]
0x18017f6a3  mov     this, [rax]
0x18017f6a6  mov     rbx, [this+28h]
0x18017f6aa  lea     this, [rbp+var_20]; this
0x18017f6ae  call    ?GetBuffer@xstring_ptr_view@@QEBAPEBGXZ; xstring_ptr_view::GetBuffer(void)
0x18017f6b3  mov     this, [rbp+pperrinfo]
0x18017f6b7  mov     pValue, rax
0x18017f6ba  mov     rax, rbx
0x18017f6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017f6c2  test    eax, eax
0x18017f6c4  js      loc_18017F7C6
0x18017f6ca  mov     this, [rbp+pperrinfo]
0x18017f6ce  lea     r8, [rbp+perrinfo]
0x18017f6d2  lea     pValue, IID_IErrorInfo
0x18017f6d9  mov     rax, [this]
0x18017f6dc  mov     rax, [rax]
0x18017f6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017f6e4  test    eax, eax
0x18017f6e6  js      loc_18017F7BA
0x18017f6ec  mov     pValue, [rbp+perrinfo]; perrinfo
0x18017f6f0  xor     ecx, ecx; dwReserved
0x18017f6f2  call    cs:__imp_SetErrorInfo
0x18017f6f8  test    eax, eax
0x18017f6fa  jns     short loc_18017F703
0x18017f6fc  mov     ecx, eax; failedFrameHR
0x18017f6fe  call    OnFailure_2990_
0x18017f703  mov     this, [rbp+pperrinfo]
0x18017f707  test    this, this
0x18017f70a  jnz     short loc_18017F728
0x18017f70c  mov     this, [rbp+perrinfo]
0x18017f710  test    this, this
0x18017f713  jnz     short loc_18017F73E
0x18017f715  lea     this, [rbp+pstrPromoted]; this
0x18017f719  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18017f71e  mov     eax, 80070057h
0x18017f723  jmp     loc_18017F50E
0x18017f728  mov     rax, [this]
0x18017f72b  mov     rax, [rax+10h]
0x18017f72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017f734  mov     [rbp+pperrinfo], 0
0x18017f73c  jmp     short loc_18017F70C
0x18017f73e  mov     pValue, [this]
0x18017f741  mov     rax, [pValue+10h]
0x18017f745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017f74a  mov     [rbp+perrinfo], 0
0x18017f752  jmp     short loc_18017F715
0x18017f754  lea     this, [rbp+pstrPromoted]; this
0x18017f758  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18017f75d  jmp     loc_18017F5CB
0x18017f762  lea     this, [rbp+var_18]
0x18017f766  and     this, 0FFFFFFFFFFFFFFFEh; string
0x18017f76a  lea     pValue, [rbp+length]; length
0x18017f76e  call    cs:__imp_WindowsGetStringRawBuffer
0x18017f774  mov     this, rax
0x18017f777  jmp     loc_18017F598
0x18017f77c  and     this, 0FFFFFFFFFFFFFFFEh; string
0x18017f780  xor     edx, edx; length
0x18017f782  call    cs:__imp_WindowsGetStringRawBuffer
0x18017f788  mov     this, qword ptr [rbp+pstrPromoted.m_encodedStorage.___u0]
0x18017f78c  mov     rbx, rax
0x18017f78f  jmp     loc_18017F629
0x18017f794  and     this, 0FFFFFFFFFFFFFFFEh; string
0x18017f798  lea     pValue, [rbp+length]; length
0x18017f79c  call    cs:__imp_WindowsGetStringRawBuffer
0x18017f7a2  mov     this, qword ptr [rbp+pstrPromoted.m_encodedStorage.___u0]
0x18017f7a6  mov     r8, rax
0x18017f7a9  jmp     loc_18017F5F5
0x18017f7ae  mov     ecx, eax; failedFrameHR
0x18017f7b0  call    OnFailure_2990_
0x18017f7b5  jmp     loc_18017F703
0x18017f7ba  mov     ecx, eax; failedFrameHR
0x18017f7bc  call    OnFailure_2990_
0x18017f7c1  jmp     loc_18017F703
0x18017f7c6  mov     ecx, eax; failedFrameHR
0x18017f7c8  call    OnFailure_2990_
0x18017f7cd  jmp     loc_18017F703
0x18017f7d2  mov     ecx, eax; failedFrameHR
0x18017f7d4  call    OnFailure_2990_
0x18017f7d9  jmp     loc_18017F703
0x18017f7de  mov     ecx, eax; failedFrameHR
0x18017f7e0  call    OnFailure_2990_
0x18017f7e5  jmp     loc_18017F703
0x18017f7ea  call    OnNewFailure_1208_
0x18017f7ef  jmp     loc_18017F703
0x18017f7f4  and     this, 0FFFFFFFFFFFFFFFEh; string
0x18017f7f8  call    cs:__imp_WindowsGetStringLen
0x18017f7fe  jmp     loc_18017F642
0x18017f803  mov     this, [this]
0x18017f806  jmp     loc_18017F780
0x18017f80b  mov     this, r8
0x18017f80e  jmp     short loc_18017F798
0x18017f810  mov     this, [this]
0x18017f813  jmp     short loc_18017F7F8
0x18017f815  mov     ecx, eax; failedFrameHR
0x18017f817  call    OnFailure_2990_
0x18017f81c  jmp     $Cleanup_829
0x18017f821  mov     ebx, 8001010Eh
0x18017f826  mov     ecx, ebx; failedFrameHR
0x18017f828  call    OnFailure_2990_
0x18017f82d  jmp     $Cleanup_829
```
