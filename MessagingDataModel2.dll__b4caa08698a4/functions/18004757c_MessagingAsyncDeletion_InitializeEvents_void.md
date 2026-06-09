# MessagingAsyncDeletion::_InitializeEvents(void)

- ea: `0x18004757c`
- end: `0x180047654`
- name: `?_InitializeEvents@MessagingAsyncDeletion@@AEAAJXZ`
- size: `216`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180046ef0`

## callees

- `0x18002416c`
- `0x180046fbc`
- `0x1800472b4`
- `0x18004757c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047598`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047616`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004763c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004763c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800475f3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800475f3`

## pseudocode

```c
__int64 __fastcall MessagingAsyncDeletion::_InitializeEvents(_QWORD *pv)
{
  HANDLE EventW; // rax
  HANDLE *v3; // rsi
  signed int LastError; // eax
  unsigned int v5; // ebx
  struct _TP_WAIT **v7; // rdi
  struct _TP_WAIT *ThreadpoolWait; // rbx
  signed int v9; // eax

  EventW = CreateEventW(0, 0, 0, 0);
  v3 = (HANDLE *)(pv + 6);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::reset(pv + 6, EventW);
  if ( !pv[6] )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_4:
    Log_HREvent_21(v5);
    return v5;
  }
  v7 = (struct _TP_WAIT **)(pv + 7);
  ThreadpoolWait = CreateThreadpoolWait((PTP_WAIT_CALLBACK)MessagingAsyncDeletion::_HandleAsyncDeletionRequest, pv, 0);
  if ( ThreadpoolWait == *v7 )
  {
    ThreadpoolWait = *v7;
  }
  else
  {
    tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>::_Delete(v7);
    *v7 = ThreadpoolWait;
  }
  if ( !ThreadpoolWait )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_4;
  }
  SetThreadpoolWait(ThreadpoolWait, *v3, 0);
  return 0;
}

```

## disassembly

```asm
0x18004757c  mov     [rsp+arg_0], rbx
0x180047581  mov     [rsp+arg_8], rsi
0x180047586  push    rdi
0x180047587  sub     rsp, 30h
0x18004758b  mov     rbx, rcx
0x18004758e  xor     r9d, r9d; lpName
0x180047591  xor     ecx, ecx; lpEventAttributes
0x180047593  xor     r8d, r8d; bInitialState
0x180047596  xor     edx, edx; bManualReset
0x180047598  call    cs:__imp_CreateEventW
0x18004759e  lea     rsi, [rbx+30h]
0x1800475a2  mov     rdx, rax
0x1800475a5  mov     rcx, rsi
0x1800475a8  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::reset(void *)
0x1800475ad  cmp     qword ptr [rsi], 0
0x1800475b1  jnz     short loc_1800475E2
0x1800475b3  call    cs:__imp_GetLastError
0x1800475b9  mov     ebx, eax
0x1800475bb  test    eax, eax
0x1800475bd  jle     short loc_1800475C8
0x1800475bf  movzx   ebx, ax
0x1800475c2  or      ebx, 80070000h
0x1800475c8  mov     r9d, 5Ah ; 'Z'
0x1800475ce  lea     r8, aOnecoreuapBase_68; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800475d5  xor     edx, edx
0x1800475d7  mov     ecx, ebx; int
0x1800475d9  call    Log_HREvent_21
0x1800475de  mov     eax, ebx
0x1800475e0  jmp     short loc_180047644
0x1800475e2  xor     r8d, r8d; pcbe
0x1800475e5  lea     rcx, ?_HandleAsyncDeletionRequest@MessagingAsyncDeletion@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800475ec  mov     rdx, rbx; pv
0x1800475ef  lea     rdi, [rbx+38h]
0x1800475f3  call    cs:__imp_CreateThreadpoolWait
0x1800475f9  mov     rbx, rax
0x1800475fc  cmp     rax, [rdi]
0x1800475ff  jz      short loc_18004760E
0x180047601  mov     rcx, rdi
0x180047604  call    ?_Delete@?$auto_xxx@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>::_Delete(void)
0x180047609  mov     [rdi], rbx
0x18004760c  jmp     short loc_180047611
0x18004760e  mov     rbx, [rdi]
0x180047611  test    rbx, rbx
0x180047614  jnz     short loc_180047633
0x180047616  call    cs:__imp_GetLastError
0x18004761c  mov     ebx, eax
0x18004761e  test    eax, eax
0x180047620  jle     short loc_18004762B
0x180047622  movzx   ebx, ax
0x180047625  or      ebx, 80070000h
0x18004762b  mov     r9d, 5Ch ; '\'
0x180047631  jmp     short loc_1800475CE
0x180047633  mov     rdx, [rsi]; h
0x180047636  xor     r8d, r8d; pftTimeout
0x180047639  mov     rcx, rbx; pwa
0x18004763c  call    cs:__imp_SetThreadpoolWait
0x180047642  xor     eax, eax
0x180047644  mov     rbx, [rsp+38h+arg_0]
0x180047649  mov     rsi, [rsp+38h+arg_8]
0x18004764e  add     rsp, 30h
0x180047652  pop     rdi
0x180047653  retn
```
