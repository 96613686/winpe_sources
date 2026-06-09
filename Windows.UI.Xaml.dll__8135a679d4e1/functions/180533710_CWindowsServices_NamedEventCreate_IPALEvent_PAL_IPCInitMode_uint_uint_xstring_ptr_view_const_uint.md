# CWindowsServices::NamedEventCreate(IPALEvent * *,PAL_IPCInitMode,uint,uint,xstring_ptr_view const &,uint)

- ea: `0x180533710`
- end: `0x1805339d9`
- name: `?NamedEventCreate@CWindowsServices@@UEAAJPEAPEAUIPALEvent@@W4PAL_IPCInitMode@@IIAEBVxstring_ptr_view@@I@Z`
- size: `713`
- prototype: `HRESULT __fastcall(CWindowsServices *this, IPALEvent **ppEvent, PAL_IPCInitMode initMode, unsigned int bInitialState, unsigned int bManualReset, const xstring_ptr_view *strName, unsigned int bReturnFailureIfCreationFailed)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callees

- `0x180004bc0`
- `0x180131190`
- `0x180533710`
- `0x1805339e0`
- `0x180687a78`
- `0x18069f6ac`
- `0x1806c06e8`
- `0x1806c1dc0`
- `0x18076e110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180533979`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180533979`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180533833`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180533833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1805338a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18053390f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180533946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1805338a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18053390f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180533946`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1805337ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1805337ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1805337a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1805337a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805338c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805338c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1805338dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1805338f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1805338dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1805338f4`

## pseudocode

```c
__int64 __fastcall CWindowsServices::NamedEventCreate(
        CWindowsServices *this,
        IPALEvent **ppEvent,
        PAL_IPCInitMode initMode,
        BOOL bInitialState,
        BOOL bManualReset,
        const xstring_ptr_view *strName,
        unsigned int bReturnFailureIfCreationFailed)
{
  unsigned __int64 RuntimeStringHandleMarker; // rax
  int v12; // edx
  HSTRING StringRawBuffer; // rcx
  DWORD CurrentProcessId; // edi
  DWORD CurrentThreadId; // eax
  unsigned __int64 v16; // rcx
  DWORD v17; // ebp
  PCWSTR v18; // rax
  HRESULT v19; // eax
  HRESULT v20; // ecx
  unsigned int v21; // ebx
  IPALEvent_vtbl *EventW; // rdi
  IPALEvent *FailFast; // rax
  HRESULT v25; // ecx
  HSTRING v26; // rcx
  signed int v27; // eax
  signed int LastError; // eax
  unsigned int cchRemaining[4]; // [rsp+50h] [rbp-268h] BYREF
  wchar_t eventName[264]; // [rsp+60h] [rbp-258h] BYREF

  if ( !ppEvent )
  {
    v21 = -2147418113;
    OnNewFailure_2955_((HRESULT)this);
    return v21;
  }
  *ppEvent = 0;
  RuntimeStringHandleMarker = strName->m_encodedStorage.RuntimeStringHandleMarker;
  cchRemaining[0] = 0;
  if ( (RuntimeStringHandleMarker & 1) != 0 )
  {
    StringRawBuffer = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_27;
  }
  v12 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
  StringRawBuffer = *(HSTRING *)RuntimeStringHandleMarker;
  if ( v12 < 0 )
  {
LABEL_27:
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(StringRawBuffer, cchRemaining);
    goto LABEL_5;
  }
  cchRemaining[0] = v12 & 0x3FFFFFFF;
LABEL_5:
  if ( !StringRawBuffer || !cchRemaining[0] || !*(_WORD *)StringRawBuffer )
  {
    v21 = -2147418113;
    OnNewFailure_2955_((HRESULT)StringRawBuffer);
    return v21;
  }
  CurrentProcessId = GetCurrentProcessId();
  CurrentThreadId = GetCurrentThreadId();
  v16 = strName->m_encodedStorage.RuntimeStringHandleMarker;
  v17 = CurrentThreadId;
  if ( (strName->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v26 = (HSTRING)(v16 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v18 = *(PCWSTR *)v16;
    if ( *(int *)(v16 + 8) >= 0 )
      goto LABEL_10;
    v26 = *(HSTRING *)v16;
  }
  v18 = WindowsGetStringRawBuffer(v26, 0);
LABEL_10:
  v19 = CWindowsServices::PrintStringCchExW(
          (CWindowsServices *)((char *)this - 8),
          eventName,
          0x103u,
          0,
          cchRemaining,
          0,
          L"%s.%d.%d",
          v18,
          CurrentProcessId,
          v17);
  v21 = v19;
  if ( v19 < 0 )
  {
    OnFailure_2990_(v19);
    return v21;
  }
  if ( (initMode & 0xFFFFFFFD) != 0 )
  {
    if ( initMode != InitModeOpenOnly )
    {
      v21 = -2147024809;
      OnFailure_1169_(v20);
      return v21;
    }
    EventW = (IPALEvent_vtbl *)OpenEventW(0x100002u, 0, eventName);
    if ( EventW )
      goto LABEL_14;
    if ( !bReturnFailureIfCreationFailed )
      return v21;
    LastError = GetLastError();
    v21 = LastError;
    if ( LastError > 0 )
      v21 = (unsigned __int16)LastError | 0x80070000;
    if ( (v21 & 0x80000000) == 0 )
      v21 = -2147467259;
LABEL_33:
    OnNewFailure_3049_(v21);
    return v21;
  }
  EventW = (IPALEvent_vtbl *)CreateEventW(0, bManualReset, bInitialState, eventName);
  if ( !EventW )
  {
    if ( !bReturnFailureIfCreationFailed )
      return v21;
    v27 = GetLastError();
    v21 = v27;
    if ( v27 > 0 )
      v21 = (unsigned __int16)v27 | 0x80070000;
    if ( (v21 & 0x80000000) == 0 )
      v21 = -2147467259;
    goto LABEL_33;
  }
  if ( initMode || GetLastError() != 183 )
  {
LABEL_14:
    FailFast = (IPALEvent *)XcpAllocation::OSMemoryAllocateFailFast(0x10u);
    if ( FailFast )
    {
      FailFast[1].__vftable = EventW;
      FailFast->__vftable = (IPALEvent_vtbl *)CWinEvent::`vftable';
    }
    else
    {
      FailFast = 0;
    }
    *ppEvent = FailFast;
    return v21;
  }
  if ( bReturnFailureIfCreationFailed )
  {
    v21 = -2147467259;
    OnFailure_977_(v25);
  }
  CloseHandle(EventW);
  return v21;
}

```

## disassembly

```asm
0x180533710  mov     [rsp+arg_10], rbx
0x180533715  push    rbp
0x180533716  push    rsi
0x180533717  push    rdi
0x180533718  push    r12
0x18053371a  push    r13
0x18053371c  push    r14
0x18053371e  push    r15
0x180533720  sub     rsp, 280h
0x180533727  mov     rax, cs:__security_cookie
0x18053372e  xor     rax, rsp
0x180533731  mov     [rsp+2B8h+var_48], rax
0x180533739  mov     rbx, [rsp+2B8h+arg_28]
0x180533741  xor     edi, edi
0x180533743  mov     r12d, [rsp+2B8h+arg_20]
0x18053374b  mov     r15d, bInitialState
0x18053374e  mov     esi, initMode
0x180533751  mov     r14, ppEvent
0x180533754  mov     r13, this
0x180533757  test    ppEvent, ppEvent
0x18053375a  jz      loc_1805338CB
0x180533760  mov     [ppEvent], rdi
0x180533763  mov     rax, [rbx]
0x180533766  mov     [rsp+2B8h+cchRemaining], edi
0x18053376a  test    al, 1
0x18053376c  jnz     loc_1805338E8
0x180533772  mov     edx, [rax+8]
0x180533775  mov     this, [rax]; failedFrameHR
0x180533778  test    edx, edx
0x18053377a  js      loc_1805338EF
0x180533780  and     edx, 3FFFFFFFh
0x180533786  mov     [rsp+2B8h+cchRemaining], edx
0x18053378a  test    this, this
0x18053378d  jz      loc_18053389A
0x180533793  cmp     [rsp+2B8h+cchRemaining], edi
0x180533797  jz      loc_18053389A
0x18053379d  cmp     di, [this]
0x1805337a0  jz      loc_18053389A
0x1805337a6  call    cs:__imp_GetCurrentProcessId
0x1805337ac  mov     edi, eax
0x1805337ae  call    cs:__imp_GetCurrentThreadId
0x1805337b4  mov     this, [rbx]
0x1805337b7  mov     ebp, eax
0x1805337b9  test    cl, 1
0x1805337bc  jnz     loc_1805338D7
0x1805337c2  cmp     dword ptr [this+8], 0
0x1805337c6  mov     rax, [this]
0x1805337c9  jl      loc_180533941
0x1805337cf  mov     [rsp+2B8h+var_270], ebp
0x1805337d3  lea     this, [r13-8]; this
0x1805337d7  mov     [rsp+2B8h+var_278], edi
0x1805337db  lea     ppEvent, [rsp+2B8h+eventName]; pszDest
0x1805337e0  mov     [rsp+2B8h+var_280], rax
0x1805337e5  xor     ebp, ebp
0x1805337e7  lea     rax, aSDD; "%s.%d.%d"
0x1805337ee  xor     bInitialState, bInitialState; ppszDestEnd
0x1805337f1  mov     [rsp+2B8h+pszFormat], rax; pszFormat
0x1805337f6  mov     initMode, 103h; cchDest
0x1805337fc  lea     rax, [rsp+2B8h+cchRemaining]
0x180533801  mov     qword ptr [rsp+2B8h+dwFlags], rbp; dwFlags
0x180533806  mov     [rsp+2B8h+pcchRemaining], rax; pcchRemaining
0x18053380b  call    ?PrintStringCchExW@CWindowsServices@@UEAAJPEAGIPEAPEAGPEAIIPEBGZZ; CWindowsServices::PrintStringCchExW(ushort *,uint,ushort * *,uint *,uint,ushort const *,...)
0x180533810  mov     ebx, eax
0x180533812  test    eax, eax
0x180533814  js      loc_180533935
0x18053381a  test    esi, 0FFFFFFFDh
0x180533820  jnz     loc_180533968
0x180533826  lea     r9, [rsp+2B8h+eventName]; lpName
0x18053382b  mov     initMode, r15d; bInitialState
0x18053382e  mov     edx, r12d; bManualReset
0x180533831  xor     ecx, ecx; lpEventAttributes
0x180533833  call    cs:__imp_CreateEventW
0x180533839  mov     rdi, rax
0x18053383c  test    rax, rax
0x18053383f  jz      loc_180533902
0x180533845  test    esi, esi
0x180533847  jz      short loc_1805338A6
0x180533849  mov     ecx, 10h; cSize
0x18053384e  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x180533853  test    rax, rax
0x180533856  jz      loc_1805339D1
0x18053385c  lea     this, ??_7CWinEvent@@6B@; const CWinEvent::`vftable'
0x180533863  mov     [rax+8], rdi
0x180533867  mov     [rax], this
0x18053386a  mov     [r14], rax
0x18053386d  mov     eax, ebx
0x18053386f  mov     this, [rsp+2B8h+var_48]
0x180533877  xor     this, rsp; StackCookie
0x18053387a  call    __security_check_cookie
0x18053387f  mov     rbx, [rsp+2B8h+arg_10]
0x180533887  add     rsp, 280h
0x18053388e  pop     r15
0x180533890  pop     r14
0x180533892  pop     r13
0x180533894  pop     r12
0x180533896  pop     rdi
0x180533897  pop     rsi
0x180533898  pop     rbp
0x180533899  retn
0x18053389a  mov     ebx, 8000FFFFh
0x18053389f  call    OnNewFailure_2955_
0x1805338a4  jmp     short loc_18053386D
0x1805338a6  call    cs:__imp_GetLastError
0x1805338ac  cmp     eax, 0B7h
0x1805338b1  jnz     short loc_180533849
0x1805338b3  cmp     [rsp+2B8h+arg_30], ebp
0x1805338ba  jnz     loc_1805339C2
0x1805338c0  mov     this, rdi; hObject
0x1805338c3  call    cs:__imp_CloseHandle
0x1805338c9  jmp     short loc_18053386D
0x1805338cb  mov     ebx, 8000FFFFh
0x1805338d0  call    OnNewFailure_2955_
0x1805338d5  jmp     short loc_18053386D
0x1805338d7  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1805338db  xor     edx, edx; length
0x1805338dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1805338e3  jmp     loc_1805337CF
0x1805338e8  and     rax, 0FFFFFFFFFFFFFFFEh
0x1805338ec  mov     this, rax; string
0x1805338ef  lea     ppEvent, [rsp+2B8h+cchRemaining]; length
0x1805338f4  call    cs:__imp_WindowsGetStringRawBuffer
0x1805338fa  mov     this, rax
0x1805338fd  jmp     loc_18053378A
0x180533902  cmp     [rsp+2B8h+arg_30], ebp
0x180533909  jz      loc_18053386D
0x18053390f  call    cs:__imp_GetLastError
0x180533915  mov     ebx, eax
0x180533917  test    eax, eax
0x180533919  jg      loc_1805339B4
0x18053391f  test    ebx, ebx
0x180533921  mov     eax, 80004005h
0x180533926  cmovns  ebx, eax
0x180533929  mov     ecx, ebx; failedFrameHR
0x18053392b  call    OnNewFailure_3049_
0x180533930  jmp     loc_18053386D
0x180533935  mov     ecx, eax; failedFrameHR
0x180533937  call    OnFailure_2990_
0x18053393c  jmp     loc_18053386D
0x180533941  mov     this, rax
0x180533944  jmp     short loc_1805338DB
0x180533946  call    cs:__imp_GetLastError
0x18053394c  mov     ebx, eax
0x18053394e  test    eax, eax
0x180533950  jg      short loc_18053399A
0x180533952  test    ebx, ebx
0x180533954  mov     eax, 80004005h
0x180533959  cmovns  ebx, eax
0x18053395c  mov     ecx, ebx; failedFrameHR
0x18053395e  call    OnNewFailure_3049_
0x180533963  jmp     loc_18053386D
0x180533968  cmp     esi, 1
0x18053396b  jnz     short loc_1805339A5
0x18053396d  lea     r8, [rsp+2B8h+eventName]; lpName
0x180533972  xor     edx, edx; bInheritHandle
0x180533974  mov     ecx, 100002h; dwDesiredAccess
0x180533979  call    cs:__imp_OpenEventW
0x18053397f  mov     rdi, rax
0x180533982  test    rax, rax
0x180533985  jnz     loc_180533849
0x18053398b  cmp     [rsp+2B8h+arg_30], ebp
0x180533992  jz      loc_18053386D
0x180533998  jmp     short loc_180533946
0x18053399a  movzx   ebx, ax
0x18053399d  or      ebx, 80070000h
0x1805339a3  jmp     short loc_180533952
0x1805339a5  mov     ebx, 80070057h
0x1805339aa  call    OnFailure_1169_
0x1805339af  jmp     loc_18053386D
0x1805339b4  movzx   ebx, ax
0x1805339b7  or      ebx, 80070000h
0x1805339bd  jmp     loc_18053391F
0x1805339c2  mov     ebx, 80004005h
0x1805339c7  call    OnFailure_977_
0x1805339cc  jmp     loc_1805338C0
0x1805339d1  mov     rax, rbp
0x1805339d4  jmp     loc_18053386A
```
