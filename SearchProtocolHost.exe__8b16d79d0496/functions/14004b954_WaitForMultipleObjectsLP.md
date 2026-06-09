# WaitForMultipleObjectsLP

- ea: `0x14004b954`
- end: `0x14004bb5d`
- name: `WaitForMultipleObjectsLP`
- size: `521`
- prototype: `__int64 __fastcall(DWORD nCount, HANDLE *pHandles, DWORD dwMilliseconds)`
- caller_count: `9`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x14004a71c`
- `0x14004a7bc`
- `0x14004a928`
- `0x14004b6cc`
- `0x14004b780`
- `0x14004b880`
- `0x14004b914`
- `0x14004bb64`
- `0x14004bd34`

## callees

- `0x140005240`
- `0x1400061f8`
- `0x140006210`
- `0x14000f208`
- `0x140037ca8`
- `0x14004b954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimerEx` at `0x14004bac6`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimerEx` at `0x14004bac6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14004bb13`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14004bb13`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x14004b9d8`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x14004b9d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ba2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ba2e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x14004ba62`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x14004ba62`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x14004ba7d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x14004ba7d`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x14004badf`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x14004badf`

## pseudocode

```c
__int64 __fastcall WaitForMultipleObjectsLP(DWORD nCount, HANDLE *pHandles, DWORD dwMilliseconds, char a4)
{
  __int64 v4; // r14
  __int64 v6; // rsi
  DWORD LastError; // ebx
  char *v9; // rdi
  DWORD v10; // r12d
  HANDLE WaitableTimer; // rax
  __int64 v12; // rbx
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp-C0h] BYREF
  char *v15; // [rsp+48h] [rbp-B8h] BYREF
  MSG Msg; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v17[64]; // [rsp+80h] [rbp-80h] BYREF

  v4 = dwMilliseconds;
  v6 = nCount;
  LastError = 87;
  memset_0(v17, 0, sizeof(v17));
  if ( (unsigned int)v6 < 0x40 )
  {
    v9 = 0;
    v15 = 0;
    v10 = v4;
    DueTime.QuadPart = 0;
    if ( (unsigned int)(v4 - 500) <= 0xFFFFFE0A )
    {
      WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v15,
        WaitableTimer);
      v9 = v15;
      if ( (unsigned __int64)(v15 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        if ( LastError )
        {
LABEL_22:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
          return LastError;
        }
      }
      else
      {
        v12 = v6;
        DueTime.QuadPart = -12500 * v4;
        v10 = -1;
        memcpy_0(v17, pHandles, 8 * v6);
        LODWORD(v6) = v6 + 1;
        v17[v12] = v9;
        pHandles = (HANDLE *)v17;
      }
    }
    do
    {
      memset(&Msg, 0, sizeof(Msg));
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        if ( Msg.message == 18 )
          goto LABEL_21;
        DispatchMessageW(&Msg);
      }
      if ( Msg.message == 18 )
      {
LABEL_21:
        LastError = 1;
        goto LABEL_22;
      }
      if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        SetWaitableTimerEx(v9, &DueTime, 0, 0, 0, 0, (unsigned int)v4 >> 2);
      LastError = MsgWaitForMultipleObjects(v6, pHandles, 0, v10, 0x1CFFu);
    }
    while ( LastError == (_DWORD)v6 );
    if ( LastError == (_DWORD)v6 - 1 && (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = 258;
    }
    else if ( a4 && !LastError && !ResetEvent(*pHandles) )
    {
      LastError = -1;
    }
    goto LABEL_22;
  }
  return LastError;
}

```

## disassembly

```asm
0x14004b954  mov     [rsp-8+arg_18], rbx
0x14004b959  push    rbp
0x14004b95a  push    rsi
0x14004b95b  push    rdi
0x14004b95c  push    r12
0x14004b95e  push    r13
0x14004b960  push    r14
0x14004b962  push    r15
0x14004b964  lea     rbp, [rsp-190h]
0x14004b96c  sub     rsp, 290h
0x14004b973  mov     rax, cs:__security_cookie
0x14004b97a  xor     rax, rsp
0x14004b97d  mov     [rbp+1C0h+var_40], rax
0x14004b984  mov     r14d, r8d
0x14004b987  mov     r15, rdx
0x14004b98a  mov     esi, ecx
0x14004b98c  xor     edx, edx; Val
0x14004b98e  mov     r8d, 200h; Size
0x14004b994  lea     rcx, [rbp+1C0h+var_240]; void *
0x14004b998  mov     r13b, r9b
0x14004b99b  mov     ebx, 57h ; 'W'
0x14004b9a0  call    memset_0
0x14004b9a5  cmp     esi, 40h ; '@'
0x14004b9a8  jnb     loc_14004BB31
0x14004b9ae  xor     edi, edi
0x14004b9b0  lea     eax, [r14-1F4h]
0x14004b9b7  mov     [rsp+2C0h+var_278], rdi
0x14004b9bc  mov     r12d, r14d
0x14004b9bf  mov     qword ptr [rsp+2C0h+DueTime], rdi
0x14004b9c4  cmp     eax, 0FFFFFE0Ah
0x14004b9c9  ja      short loc_14004BA3E
0x14004b9cb  mov     r9d, 1F0003h; dwDesiredAccess
0x14004b9d1  xor     r8d, r8d; dwFlags
0x14004b9d4  xor     edx, edx; lpTimerName
0x14004b9d6  xor     ecx, ecx; lpTimerAttributes
0x14004b9d8  call    cs:__imp_CreateWaitableTimerExW
0x14004b9de  mov     rdx, rax
0x14004b9e1  lea     rcx, [rsp+2C0h+var_278]
0x14004b9e6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004b9eb  mov     rdi, [rsp+2C0h+var_278]
0x14004b9f0  lea     rax, [rdi-1]
0x14004b9f4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004b9f8  ja      short loc_14004BA2E
0x14004b9fa  imul    rcx, r14, 0FFFFFFFFFFFFCF2Ch
0x14004ba01  lea     rbx, ds:0[rsi*8]
0x14004ba09  mov     rdx, r15; Src
0x14004ba0c  mov     qword ptr [rsp+2C0h+DueTime], rcx
0x14004ba11  mov     r8, rbx; Size
0x14004ba14  lea     rcx, [rbp+1C0h+var_240]; void *
0x14004ba18  or      r12d, 0FFFFFFFFh
0x14004ba1c  call    memcpy_0
0x14004ba21  inc     esi
0x14004ba23  mov     [rbp+rbx+1C0h+var_240], rdi
0x14004ba28  lea     r15, [rbp+1C0h+var_240]
0x14004ba2c  jmp     short loc_14004BA3E
0x14004ba2e  call    cs:__imp_GetLastError
0x14004ba34  mov     ebx, eax
0x14004ba36  test    eax, eax
0x14004ba38  jnz     loc_14004BB27
0x14004ba3e  xorps   xmm0, xmm0
0x14004ba41  movups  xmmword ptr [rsp+2C0h+Msg.hwnd], xmm0
0x14004ba46  movups  xmmword ptr [rsp+2C0h+Msg.wParam], xmm0
0x14004ba4b  movups  xmmword ptr [rsp+2C0h+Msg.time], xmm0
0x14004ba50  jmp     short loc_14004BA68
0x14004ba52  cmp     [rsp+2C0h+Msg.message], 12h
0x14004ba57  jz      loc_14004BB22
0x14004ba5d  lea     rcx, [rsp+2C0h+Msg]; lpMsg
0x14004ba62  call    cs:__imp_DispatchMessageW
0x14004ba68  xor     r9d, r9d; wMsgFilterMax
0x14004ba6b  mov     [rsp+2C0h+wRemoveMsg], 1; wRemoveMsg
0x14004ba73  xor     r8d, r8d; wMsgFilterMin
0x14004ba76  lea     rcx, [rsp+2C0h+Msg]; lpMsg
0x14004ba7b  xor     edx, edx; hWnd
0x14004ba7d  call    cs:__imp_PeekMessageW
0x14004ba83  test    eax, eax
0x14004ba85  jnz     short loc_14004BA52
0x14004ba87  cmp     [rsp+2C0h+Msg.message], 12h
0x14004ba8c  jz      loc_14004BB22
0x14004ba92  lea     rax, [rdi-1]
0x14004ba96  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004ba9a  ja      short loc_14004BACC
0x14004ba9c  mov     eax, r14d
0x14004ba9f  lea     rdx, [rsp+2C0h+DueTime]; lpDueTime
0x14004baa4  shr     eax, 2
0x14004baa7  xor     r9d, r9d; pfnCompletionRoutine
0x14004baaa  mov     [rsp+2C0h+TolerableDelay], eax; TolerableDelay
0x14004baae  xor     r8d, r8d; lPeriod
0x14004bab1  mov     [rsp+2C0h+WakeContext], 0; WakeContext
0x14004baba  mov     rcx, rdi; hTimer
0x14004babd  mov     qword ptr [rsp+2C0h+wRemoveMsg], 0; lpArgToCompletionRoutine
0x14004bac6  call    cs:__imp_SetWaitableTimerEx
0x14004bacc  mov     r9d, r12d; dwMilliseconds
0x14004bacf  mov     [rsp+2C0h+wRemoveMsg], 1CFFh; dwWakeMask
0x14004bad7  xor     r8d, r8d; fWaitAll
0x14004bada  mov     rdx, r15; pHandles
0x14004badd  mov     ecx, esi; nCount
0x14004badf  call    cs:__imp_MsgWaitForMultipleObjects
0x14004bae5  mov     ebx, eax
0x14004bae7  cmp     eax, esi
0x14004bae9  jz      loc_14004BA3E
0x14004baef  lea     eax, [rsi-1]
0x14004baf2  cmp     ebx, eax
0x14004baf4  jnz     short loc_14004BB07
0x14004baf6  lea     rax, [rdi-1]
0x14004bafa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004bafe  ja      short loc_14004BB07
0x14004bb00  mov     ebx, 102h
0x14004bb05  jmp     short loc_14004BB27
0x14004bb07  test    r13b, r13b
0x14004bb0a  jz      short loc_14004BB27
0x14004bb0c  test    ebx, ebx
0x14004bb0e  jnz     short loc_14004BB27
0x14004bb10  mov     rcx, [r15]; hEvent
0x14004bb13  call    cs:__imp_ResetEvent
0x14004bb19  test    eax, eax
0x14004bb1b  jnz     short loc_14004BB27
0x14004bb1d  or      ebx, 0FFFFFFFFh
0x14004bb20  jmp     short loc_14004BB27
0x14004bb22  mov     ebx, 1
0x14004bb27  lea     rcx, [rsp+2C0h+var_278]
0x14004bb2c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14004bb31  mov     eax, ebx
0x14004bb33  mov     rcx, [rbp+1C0h+var_40]
0x14004bb3a  xor     rcx, rsp; StackCookie
0x14004bb3d  call    __security_check_cookie
0x14004bb42  mov     rbx, [rsp+2C0h+arg_18]
0x14004bb4a  add     rsp, 290h
0x14004bb51  pop     r15
0x14004bb53  pop     r14
0x14004bb55  pop     r13
0x14004bb57  pop     r12
0x14004bb59  pop     rdi
0x14004bb5a  pop     rsi
0x14004bb5b  pop     rbp
0x14004bb5c  retn
```
