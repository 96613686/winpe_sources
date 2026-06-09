# CPimcManager::InitializeHookThread(CHookThreadItem *)

- ea: `0x18000aa8c`
- end: `0x18000ac92`
- name: `?InitializeHookThread@CPimcManager@@SAJPEAUCHookThreadItem@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(struct CHookThreadItem *lpParameter)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18000ada8`

## callees

- `0x180001360`
- `0x18000aa8c`
- `0x18000ce0c`
- `0x18000d44c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000abfb`
- `KERNEL32!CloseHandle` at `0x18000ac34`
- `KERNEL32!CloseHandle` at `0x18000abfb`
- `KERNEL32!CloseHandle` at `0x18000ac34`
- `KERNEL32!WaitForSingleObject` at `0x18000ab74`
- `KERNEL32!WaitForSingleObject` at `0x18000ac1e`
- `KERNEL32!WaitForSingleObject` at `0x18000ab74`
- `KERNEL32!WaitForSingleObject` at `0x18000ac1e`
- `KERNEL32!CreateEventW` at `0x18000aab1`
- `KERNEL32!CreateEventW` at `0x18000aac9`
- `KERNEL32!CreateEventW` at `0x18000aae0`
- `KERNEL32!CreateEventW` at `0x18000abb1`
- `KERNEL32!CreateEventW` at `0x18000aab1`
- `KERNEL32!CreateEventW` at `0x18000aac9`
- `KERNEL32!CreateEventW` at `0x18000aae0`
- `KERNEL32!CreateEventW` at `0x18000abb1`
- `KERNEL32!SignalObjectAndWait` at `0x18000abed`
- `KERNEL32!SignalObjectAndWait` at `0x18000abed`
- `KERNEL32!CreateWaitableTimerW` at `0x18000aaf3`
- `KERNEL32!CreateWaitableTimerW` at `0x18000aaf3`
- `KERNEL32!CreateThread` at `0x18000ab43`
- `KERNEL32!CreateThread` at `0x18000ab43`
- `KERNEL32!QueueUserAPC` at `0x18000abc7`
- `KERNEL32!QueueUserAPC` at `0x18000abc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPimcManager::InitializeHookThread(struct CHookThreadItem *lpParameter)
{
  void **v2; // r12
  HANDLE *v3; // r15
  HANDLE *v4; // rbp
  HANDLE WaitableTimerW; // rax
  HANDLE v6; // rax
  unsigned int v7; // ebx
  void **v8; // rcx
  DWORD v9; // eax
  HANDLE *v10; // rdi
  DWORD v11; // eax
  DWORD ThreadId; // [rsp+70h] [rbp+8h] BYREF
  HANDLE *v14; // [rsp+78h] [rbp+10h]

  v2 = (void **)((char *)lpParameter + 64);
  *((_QWORD *)lpParameter + 8) = CreateEventW(0, 0, 0, 0);
  v3 = (HANDLE *)((char *)lpParameter + 72);
  *((_QWORD *)lpParameter + 9) = CreateEventW(0, 0, 0, 0);
  v4 = (HANDLE *)((char *)lpParameter + 80);
  *((_QWORD *)lpParameter + 10) = CreateEventW(0, 0, 0, 0);
  WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
  *((_QWORD *)lpParameter + 11) = WaitableTimerW;
  if ( !*v2 || !*v3 || !*v4 || !WaitableTimerW )
  {
    v7 = -2147467259;
    v8 = (void **)((char *)lpParameter + 56);
LABEL_17:
    SafeCloseHandle(v8);
    SafeCloseHandle(v2);
    SafeCloseHandle((void **)lpParameter + 9);
    SafeCloseHandle((void **)lpParameter + 10);
    SafeCloseHandle((void **)lpParameter + 11);
    return v7;
  }
  ThreadId = 0;
  v6 = CreateThread(0, 0, CPimcManager::HookThreadProc, lpParameter, 0, &ThreadId);
  *((_QWORD *)lpParameter + 7) = v6;
  v7 = v6 == 0 ? 0x80004005 : 0;
  v8 = (void **)((char *)lpParameter + 56);
  if ( !v6 )
    goto LABEL_17;
  v9 = WaitForSingleObject(*v2, 0xFFFFFFFF);
  v7 = v9 != 0 ? 0x80004005 : 0;
  v8 = (void **)((char *)lpParameter + 56);
  if ( v9 )
    goto LABEL_17;
  v10 = (HANDLE *)operator new(0x20u);
  v14 = v10;
  v10[1] = (HANDLE)*(unsigned int *)lpParameter;
  *((_DWORD *)v10 + 4) = 0;
  *v10 = CreateEventW(0, 0, 0, 0);
  v11 = QueueUserAPC(CPimcManager::InstallWindowHookApcCore, *((HANDLE *)lpParameter + 7), (ULONG_PTR)v10);
  v7 = v11 == 0 ? 0x80000303 : 0;
  if ( !v11 )
  {
    SignalObjectAndWait(*v3, *v4, 0xFFFFFFFF, 0);
    if ( *v10 )
      CloseHandle(*v10);
    operator delete(v10);
    v8 = (void **)((char *)lpParameter + 56);
    goto LABEL_17;
  }
  if ( *v10 )
    WaitForSingleObject(*v10, 0xFFFFFFFF);
  *((_QWORD *)lpParameter + 1) = v10[3];
  if ( *v10 )
    CloseHandle(*v10);
  operator delete(v10);
  return v7;
}

```

## disassembly

```asm
0x18000aa8c  mov     [rsp+arg_10], rbx
0x18000aa91  push    rbp
0x18000aa92  push    rsi
0x18000aa93  push    rdi
0x18000aa94  push    r12
0x18000aa96  push    r13
0x18000aa98  push    r14
0x18000aa9a  push    r15
0x18000aa9c  sub     rsp, 30h
0x18000aaa0  mov     rsi, rcx
0x18000aaa3  lea     r12, [rcx+40h]
0x18000aaa7  xor     r9d, r9d; lpName
0x18000aaaa  xor     r8d, r8d; bInitialState
0x18000aaad  xor     edx, edx; bManualReset
0x18000aaaf  xor     ecx, ecx; lpEventAttributes
0x18000aab1  call    cs:__imp_CreateEventW
0x18000aab7  mov     [r12], rax
0x18000aabb  lea     r15, [rsi+48h]
0x18000aabf  xor     r9d, r9d; lpName
0x18000aac2  xor     r8d, r8d; bInitialState
0x18000aac5  xor     edx, edx; bManualReset
0x18000aac7  xor     ecx, ecx; lpEventAttributes
0x18000aac9  call    cs:__imp_CreateEventW
0x18000aacf  mov     [r15], rax
0x18000aad2  lea     rbp, [rsi+50h]
0x18000aad6  xor     r9d, r9d; lpName
0x18000aad9  xor     r8d, r8d; bInitialState
0x18000aadc  xor     edx, edx; bManualReset
0x18000aade  xor     ecx, ecx; lpEventAttributes
0x18000aae0  call    cs:__imp_CreateEventW
0x18000aae6  mov     [rbp+0], rax
0x18000aaea  xor     r8d, r8d; lpTimerName
0x18000aaed  lea     edx, [r8+1]; bManualReset
0x18000aaf1  xor     ecx, ecx; lpTimerAttributes
0x18000aaf3  call    cs:__imp_CreateWaitableTimerW
0x18000aaf9  mov     [rsi+58h], rax
0x18000aafd  xor     ecx, ecx; lpThreadAttributes
0x18000aaff  cmp     [r12], rcx
0x18000ab03  jz      loc_18000AC49
0x18000ab09  cmp     [r15], rcx
0x18000ab0c  jz      loc_18000AC49
0x18000ab12  cmp     [rbp+0], rcx
0x18000ab16  jz      loc_18000AC49
0x18000ab1c  test    rax, rax
0x18000ab1f  jz      loc_18000AC49
0x18000ab25  mov     [rsp+68h+ThreadId], ecx
0x18000ab29  lea     rax, [rsp+68h+ThreadId]
0x18000ab2e  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18000ab33  mov     [rsp+68h+dwCreationFlags], ecx; dwCreationFlags
0x18000ab37  mov     r9, rsi; lpParameter
0x18000ab3a  lea     r8, ?HookThreadProc@CPimcManager@@SAKPEAX@Z; lpStartAddress
0x18000ab41  xor     edx, edx; dwStackSize
0x18000ab43  call    cs:__imp_CreateThread
0x18000ab49  lea     r14, [rsi+38h]
0x18000ab4d  mov     [r14], rax
0x18000ab50  mov     rcx, rax
0x18000ab53  neg     rcx
0x18000ab56  sbb     ebx, ebx
0x18000ab58  not     ebx
0x18000ab5a  mov     edi, 80004005h
0x18000ab5f  and     ebx, edi
0x18000ab61  mov     rcx, r14
0x18000ab64  test    rax, rax
0x18000ab67  jz      loc_18000AC52
0x18000ab6d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ab70  mov     rcx, [r12]; hHandle
0x18000ab74  call    cs:__imp_WaitForSingleObject
0x18000ab7a  mov     ecx, eax
0x18000ab7c  neg     ecx
0x18000ab7e  sbb     ebx, ebx
0x18000ab80  and     ebx, edi
0x18000ab82  mov     rcx, r14
0x18000ab85  test    eax, eax
0x18000ab87  jnz     loc_18000AC52
0x18000ab8d  lea     ecx, [rax+20h]; Size
0x18000ab90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab95  mov     rdi, rax
0x18000ab98  mov     [rsp+68h+arg_8], rax
0x18000ab9d  mov     ecx, [rsi]
0x18000ab9f  mov     [rax+8], rcx
0x18000aba3  and     dword ptr [rax+10h], 0
0x18000aba7  xor     r9d, r9d; lpName
0x18000abaa  xor     r8d, r8d; bInitialState
0x18000abad  xor     edx, edx; bManualReset
0x18000abaf  xor     ecx, ecx; lpEventAttributes
0x18000abb1  call    cs:__imp_CreateEventW
0x18000abb7  mov     [rdi], rax
0x18000abba  mov     r8, rdi; dwData
0x18000abbd  mov     rdx, [r14]; hThread
0x18000abc0  lea     rcx, ?InstallWindowHookApcCore@CPimcManager@@SAX_K@Z; pfnAPC
0x18000abc7  call    cs:__imp_QueueUserAPC
0x18000abcd  mov     ecx, eax
0x18000abcf  neg     ecx
0x18000abd1  sbb     ebx, ebx
0x18000abd3  not     ebx
0x18000abd5  and     ebx, 80000303h
0x18000abdb  test    eax, eax
0x18000abdd  jnz     short loc_18000AC13
0x18000abdf  xor     r9d, r9d; bAlertable
0x18000abe2  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18000abe6  mov     rdx, [rbp+0]; hObjectToWaitOn
0x18000abea  mov     rcx, [r15]; hObjectToSignal
0x18000abed  call    cs:__imp_SignalObjectAndWait
0x18000abf3  mov     rcx, [rdi]; hObject
0x18000abf6  test    rcx, rcx
0x18000abf9  jz      short loc_18000AC01
0x18000abfb  call    cs:__imp_CloseHandle
0x18000ac01  mov     edx, 20h ; ' '
0x18000ac06  mov     rcx, rdi; Block
0x18000ac09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ac0e  mov     rcx, r14
0x18000ac11  jmp     short loc_18000AC52
0x18000ac13  mov     rcx, [rdi]; hHandle
0x18000ac16  test    rcx, rcx
0x18000ac19  jz      short loc_18000AC24
0x18000ac1b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ac1e  call    cs:__imp_WaitForSingleObject
0x18000ac24  mov     rcx, [rdi+18h]
0x18000ac28  mov     [rsi+8], rcx
0x18000ac2c  mov     rcx, [rdi]; hObject
0x18000ac2f  test    rcx, rcx
0x18000ac32  jz      short loc_18000AC3A
0x18000ac34  call    cs:__imp_CloseHandle
0x18000ac3a  mov     edx, 20h ; ' '
0x18000ac3f  mov     rcx, rdi; Block
0x18000ac42  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ac47  jmp     short loc_18000AC78
0x18000ac49  mov     ebx, 80004005h
0x18000ac4e  lea     rcx, [rsi+38h]; void **
0x18000ac52  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000ac57  mov     rcx, r12; void **
0x18000ac5a  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000ac5f  mov     rcx, r15; void **
0x18000ac62  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000ac67  mov     rcx, rbp; void **
0x18000ac6a  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000ac6f  lea     rcx, [rsi+58h]; void **
0x18000ac73  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000ac78  mov     eax, ebx
0x18000ac7a  mov     rbx, [rsp+68h+arg_10]
0x18000ac82  add     rsp, 30h
0x18000ac86  pop     r15
0x18000ac88  pop     r14
0x18000ac8a  pop     r13
0x18000ac8c  pop     r12
0x18000ac8e  pop     rdi
0x18000ac8f  pop     rsi
0x18000ac90  pop     rbp
0x18000ac91  retn
```
