# Windows::System::DispatcherQueueController::CreateOnNewThread(DISPATCHERQUEUE_THREAD_APARTMENTTYPE,Windows::System::IDispatcherQueueController * *)

- ea: `0x180068e70`
- end: `0x180069033`
- name: `?CreateOnNewThread@DispatcherQueueController@System@Windows@@SAJW4DISPATCHERQUEUE_THREAD_APARTMENTTYPE@@PEAPEAUIDispatcherQueueController@23@@Z`
- size: `451`
- prototype: `__int64 __fastcall(enum DISPATCHERQUEUE_THREAD_APARTMENTTYPE, struct Windows::System::IDispatcherQueueController **)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800683e0`
- `0x180068d50`

## callees

- `0x180068e70`
- `0x1800a1ae8`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180068ea3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180068ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068fe4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180068eda`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180068eda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068f2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068f46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068f2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068f46`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180068f0b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180068f0b`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180068f23`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180068fd9`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180068ff0`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180068f23`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180068fd9`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180068ff0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::System::DispatcherQueueController::CreateOnNewThread(
        enum DISPATCHERQUEUE_THREAD_APARTMENTTYPE a1,
        struct Windows::System::IDispatcherQueueController **a2)
{
  const char *v3; // r9
  HANDLE v4; // rdi
  const char *v5; // r9
  DWORD v6; // eax
  __int64 v7; // rcx
  struct Windows::System::IDispatcherQueueController *v8; // rcx
  struct Windows::System::IDispatcherQueueController *v10; // rbx
  signed int LastError; // eax
  bool v12; // sf
  signed int v13; // eax
  signed int v14; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Parameter; // [rsp+40h] [rbp-28h] BYREF
  enum DISPATCHERQUEUE_THREAD_APARTMENTTYPE v17; // [rsp+48h] [rbp-20h]
  struct Windows::System::IDispatcherQueueController *v18; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  v18 = 0;
  if ( a1 != DQTAT_COM_ASTA && a1 != DQTAT_COM_STA )
    return 2147942487LL;
  v17 = a1;
  Parameter = CreateEventW(0, 1, 0, 0);
  if ( !Parameter )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x14B,
      (unsigned int)"mincore\\coreui\\dev\\dispatcherqueue\\wrtdispatcherqueuecontroller.cpp",
      v3);
  v4 = CreateThread(0, 0, Windows::System::DispatcherQueueController::DispatcherQueueThreadProc, &Parameter, 0, 0);
  if ( !v4 )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x155,
      (unsigned int)"mincore\\coreui\\dev\\dispatcherqueue\\wrtdispatcherqueuecontroller.cpp",
      v5);
  Handles[0] = Parameter;
  Handles[1] = v4;
  v6 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( !v6 )
  {
    v10 = v18;
    if ( v18 )
      (*(void (__fastcall **)(struct Windows::System::IDispatcherQueueController *))(*(_QWORD *)v18 + 8LL))(v18);
    *a2 = v10;
    goto LABEL_8;
  }
  if ( v6 == 1 )
  {
    v7 = 2147549183LL;
  }
  else
  {
    LastError = GetLastError();
    v12 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v12 = LastError < 0;
    }
    if ( !v12 )
      goto LABEL_8;
    v7 = (unsigned int)LastError;
  }
  RoFailFastWithErrorContext(v7);
LABEL_8:
  if ( !CloseHandle(Parameter) )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    RoFailFastWithErrorContext((unsigned int)v13);
  }
  Parameter = 0;
  if ( !CloseHandle(v4) )
  {
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    RoFailFastWithErrorContext((unsigned int)v14);
  }
  v8 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(struct Windows::System::IDispatcherQueueController *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180068e70  push    rbp
0x180068e72  push    rbx
0x180068e73  push    rsi
0x180068e74  push    rdi
0x180068e75  mov     rbp, rsp
0x180068e78  sub     rsp, 68h
0x180068e7c  mov     rsi, rdx
0x180068e7f  mov     [rbp+var_18], 0
0x180068e87  mov     r8d, ecx
0x180068e8a  sub     r8d, 1
0x180068e8e  jnz     loc_180068F9B
0x180068e94  mov     [rbp+var_20], ecx
0x180068e97  xor     r9d, r9d; lpName
0x180068e9a  xor     r8d, r8d; bInitialState
0x180068e9d  lea     edx, [r9+1]; bManualReset
0x180068ea1  xor     ecx, ecx; lpEventAttributes
0x180068ea3  call    cs:__imp_CreateEventW
0x180068ea9  mov     [rbp+Parameter], rax
0x180068ead  mov     rcx, [rbp+20h]; this
0x180068eb1  test    rax, rax
0x180068eb4  jz      loc_180068FFB
0x180068eba  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x180068ec3  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x180068ecb  lea     r9, [rbp+Parameter]; lpParameter
0x180068ecf  lea     r8, ?DispatcherQueueThreadProc@DispatcherQueueController@System@Windows@@CAKPEAX@Z; lpStartAddress
0x180068ed6  xor     edx, edx; dwStackSize
0x180068ed8  xor     ecx, ecx; lpThreadAttributes
0x180068eda  call    cs:__imp_CreateThread
0x180068ee0  mov     rdi, rax
0x180068ee3  mov     rcx, [rbp+20h]; this
0x180068ee7  test    rax, rax
0x180068eea  jz      loc_18006900D
0x180068ef0  mov     rax, [rbp+Parameter]
0x180068ef4  mov     [rbp+Handles], rax
0x180068ef8  mov     [rbp+var_30], rdi
0x180068efc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180068f00  xor     r8d, r8d; bWaitAll
0x180068f03  lea     rdx, [rbp+Handles]; lpHandles
0x180068f07  lea     ecx, [r8+2]; nCount
0x180068f0b  call    cs:__imp_WaitForMultipleObjects
0x180068f11  test    eax, eax
0x180068f13  jz      short loc_180068F7D
0x180068f15  cmp     eax, 1
0x180068f18  jnz     loc_180068FAC
0x180068f1e  mov     ecx, 8000FFFFh
0x180068f23  call    cs:__imp_RoFailFastWithErrorContext
0x180068f29  mov     rcx, [rbp+Parameter]; hObject
0x180068f2d  call    cs:__imp_CloseHandle
0x180068f33  test    eax, eax
0x180068f35  jz      loc_180068FCD
0x180068f3b  mov     [rbp+Parameter], 0
0x180068f43  mov     rcx, rdi; hObject
0x180068f46  call    cs:__imp_CloseHandle
0x180068f4c  test    eax, eax
0x180068f4e  jz      loc_180068FE4
0x180068f54  mov     rcx, [rbp+var_18]
0x180068f58  test    rcx, rcx
0x180068f5b  jz      short loc_180068F72
0x180068f5d  mov     [rbp+var_18], 0
0x180068f65  mov     rax, [rcx]
0x180068f68  mov     rax, [rax+10h]
0x180068f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f71  nop
0x180068f72  xor     eax, eax
0x180068f74  add     rsp, 68h
0x180068f78  pop     rdi
0x180068f79  pop     rsi
0x180068f7a  pop     rbx
0x180068f7b  pop     rbp
0x180068f7c  retn
0x180068f7d  mov     rbx, [rbp+var_18]
0x180068f81  test    rbx, rbx
0x180068f84  jz      short loc_180068F96
0x180068f86  mov     rax, [rbx]
0x180068f89  mov     rcx, rbx
0x180068f8c  mov     rax, [rax+8]
0x180068f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f95  nop
0x180068f96  mov     [rsi], rbx
0x180068f99  jmp     short loc_180068F29
0x180068f9b  cmp     r8d, 1
0x180068f9f  jz      loc_180068E94
0x180068fa5  mov     eax, 80070057h
0x180068faa  jmp     short loc_180068F74
0x180068fac  call    cs:__imp_GetLastError
0x180068fb2  test    eax, eax
0x180068fb4  jle     short loc_180068FC0
0x180068fb6  movzx   eax, ax
0x180068fb9  or      eax, 80070000h
0x180068fbe  test    eax, eax
0x180068fc0  jns     loc_180068F29
0x180068fc6  mov     ecx, eax
0x180068fc8  jmp     loc_180068F23
0x180068fcd  call    cs:__imp_GetLastError
0x180068fd3  test    eax, eax
0x180068fd5  jg      short loc_18006901F
0x180068fd7  mov     ecx, eax
0x180068fd9  call    cs:__imp_RoFailFastWithErrorContext
0x180068fdf  jmp     loc_180068F3B
0x180068fe4  call    cs:__imp_GetLastError
0x180068fea  test    eax, eax
0x180068fec  jg      short loc_180069029
0x180068fee  mov     ecx, eax
0x180068ff0  call    cs:__imp_RoFailFastWithErrorContext
0x180068ff6  jmp     loc_180068F54
0x180068ffb  lea     r8, aMincoreCoreuiD_1; "mincore\\coreui\\dev\\dispatcherqueue\\"...
0x180069002  mov     edx, 14Bh; void *
0x180069007  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006900d  lea     r8, aMincoreCoreuiD_1; "mincore\\coreui\\dev\\dispatcherqueue\\"...
0x180069014  mov     edx, 155h; void *
0x180069019  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006901f  movzx   eax, ax
0x180069022  or      eax, 80070000h
0x180069027  jmp     short loc_180068FD7
0x180069029  movzx   eax, ax
0x18006902c  or      eax, 80070000h
0x180069031  jmp     short loc_180068FEE
```
