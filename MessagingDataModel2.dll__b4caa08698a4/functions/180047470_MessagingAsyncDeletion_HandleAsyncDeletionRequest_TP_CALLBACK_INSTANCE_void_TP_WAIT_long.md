# MessagingAsyncDeletion::_HandleAsyncDeletionRequest(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180047470`
- end: `0x180047575`
- name: `?_HandleAsyncDeletionRequest@MessagingAsyncDeletion@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `261`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180046b98`
- `0x180046c98`
- `0x180046fbc`
- `0x1800472d4`
- `0x180047470`
- `0x18004765c`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004748c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004748c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800474aa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800474aa`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180047498`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180047498`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004751d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004751d`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x180047533`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x180047533`

## pseudocode

```c
void __fastcall MessagingAsyncDeletion::_HandleAsyncDeletionRequest(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  HANDLE CurrentThread; // rbx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  _DWORD v9[2]; // [rsp+30h] [rbp-28h] BYREF
  enum _PRIORITY_HINT v10; // [rsp+38h] [rbp-20h] BYREF
  int v11; // [rsp+3Ch] [rbp-1Ch]

  CurrentThread = GetCurrentThread();
  v9[1] = GetThreadPriority(CurrentThread);
  v9[0] = SetThreadPriority(CurrentThread, -2);
  v11 = 0;
  auto_iopriority::ChangePriority((auto_iopriority *)&v10, IoPriorityHintLow);
  if ( !*((_DWORD *)Context + 6) )
  {
    v6 = MessagingAsyncDeletion::_OnAsyncDeletionNotification((MessagingAsyncDeletion *)Context);
    if ( v6 < 0 )
      Log_HREvent_21(v6);
    v7 = MessagingAsyncDeletion::_DeleteProviderMessages((MessagingAsyncDeletion *)Context);
    if ( v7 < 0 )
      Log_HREvent_21(v7);
    SetThreadpoolWait(*((PTP_WAIT *)Context + 7), *((HANDLE *)Context + 6), 0);
  }
  if ( v11 )
  {
    v11 = 0;
    v8 = SetThreadIOPriority(v10, 0);
    if ( v8 < 0 )
      Log_HREvent_21(v8);
  }
  AutoResetThreadPriority::~AutoResetThreadPriority((AutoResetThreadPriority *)v9);
}

```

## disassembly

```asm
0x180047470  mov     [rsp+arg_0], rbx
0x180047475  push    rdi
0x180047476  sub     rsp, 50h
0x18004747a  mov     rax, cs:__security_cookie
0x180047481  xor     rax, rsp
0x180047484  mov     [rsp+58h+var_18], rax
0x180047489  mov     rdi, rdx
0x18004748c  call    cs:__imp_GetCurrentThread
0x180047492  mov     rcx, rax; hThread
0x180047495  mov     rbx, rax
0x180047498  call    cs:__imp_GetThreadPriority
0x18004749e  mov     edx, 0FFFFFFFEh; nPriority
0x1800474a3  mov     rcx, rbx; hThread
0x1800474a6  mov     [rsp+58h+var_24], eax
0x1800474aa  call    cs:__imp_SetThreadPriority
0x1800474b0  xor     ebx, ebx
0x1800474b2  lea     rcx, [rsp+58h+var_20]; this
0x1800474b7  mov     [rsp+58h+var_28], eax
0x1800474bb  mov     [rsp+58h+var_1C], ebx
0x1800474bf  lea     edx, [rbx+1]; enum _PRIORITY_HINT
0x1800474c2  call    ?ChangePriority@auto_iopriority@@QEAAJW4_PRIORITY_HINT@@@Z; auto_iopriority::ChangePriority(_PRIORITY_HINT)
0x1800474c7  mov     eax, [rdi+18h]
0x1800474ca  test    eax, eax
0x1800474cc  jnz     short loc_180047523
0x1800474ce  mov     rcx, rdi; this
0x1800474d1  call    ?_OnAsyncDeletionNotification@MessagingAsyncDeletion@@AEAAJXZ; MessagingAsyncDeletion::_OnAsyncDeletionNotification(void)
0x1800474d6  test    eax, eax
0x1800474d8  jns     short loc_1800474F0
0x1800474da  mov     r9d, 0B5h
0x1800474e0  lea     r8, aOnecoreuapBase_68; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800474e7  xor     edx, edx
0x1800474e9  mov     ecx, eax; int
0x1800474eb  call    Log_HREvent_21
0x1800474f0  mov     rcx, rdi; this
0x1800474f3  call    ?_DeleteProviderMessages@MessagingAsyncDeletion@@AEAAJXZ; MessagingAsyncDeletion::_DeleteProviderMessages(void)
0x1800474f8  test    eax, eax
0x1800474fa  jns     short loc_180047512
0x1800474fc  mov     r9d, 0B7h
0x180047502  lea     r8, aOnecoreuapBase_68; "onecoreuap\\base\\appmodel\\messagingom"...
0x180047509  xor     edx, edx
0x18004750b  mov     ecx, eax; int
0x18004750d  call    Log_HREvent_21
0x180047512  mov     rdx, [rdi+30h]; h
0x180047516  xor     r8d, r8d; pftTimeout
0x180047519  mov     rcx, [rdi+38h]; pwa
0x18004751d  call    cs:__imp_SetThreadpoolWait
0x180047523  cmp     [rsp+58h+var_1C], ebx
0x180047527  jz      short loc_180047553
0x180047529  mov     ecx, [rsp+58h+var_20]
0x18004752d  xor     edx, edx
0x18004752f  mov     [rsp+58h+var_1C], ebx
0x180047533  call    cs:__imp_?SetThreadIOPriority@@YAJW4_PRIORITY_HINT@@PEAX@Z; SetThreadIOPriority(_PRIORITY_HINT,void *)
0x180047539  test    eax, eax
0x18004753b  jns     short loc_180047553
0x18004753d  mov     r9d, 2DBh
0x180047543  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\UserDat"...
0x18004754a  xor     edx, edx
0x18004754c  mov     ecx, eax; int
0x18004754e  call    Log_HREvent_21
0x180047553  lea     rcx, [rsp+58h+var_28]; this
0x180047558  call    ??1AutoResetThreadPriority@@QEAA@XZ; AutoResetThreadPriority::~AutoResetThreadPriority(void)
0x18004755d  mov     rcx, [rsp+58h+var_18]
0x180047562  xor     rcx, rsp; StackCookie
0x180047565  call    __security_check_cookie
0x18004756a  mov     rbx, [rsp+58h+arg_0]
0x18004756f  add     rsp, 50h
0x180047573  pop     rdi
0x180047574  retn
```
