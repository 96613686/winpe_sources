# Windows::Compat::Inventory::InventoryWatchdog::ThreadProc(void *)

- ea: `0x1800252a0`
- end: `0x180025434`
- name: `?ThreadProc@InventoryWatchdog@Inventory@Compat@Windows@@CAKPEAX@Z`
- size: `404`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800252a0`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025332`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025370`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025332`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025370`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025342`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025391`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800253b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025342`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025391`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800253b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800252d5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800252d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252df`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002537b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002537b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180025357`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180025357`

## string_xrefs

- `0x1800253de`: `m_threadRunningEvent not initialized [%#x]`
- `0x18002531a`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800253cb`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x180025411`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::InventoryWatchdog::ThreadProc(RTL_SRWLOCK *Parameter)
{
  PVOID Ptr; // rcx
  DWORD v3; // esi
  DWORD v4; // eax
  void (*v5)(void); // rax
  const char *v6; // r9
  __int64 v7; // r8
  DWORD LastError; // [rsp+20h] [rbp-28h]
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( !Parameter[5].Ptr )
  {
    v6 = "m_stillAliveEvent not initialized [%#x]";
    v7 = 256;
    goto LABEL_23;
  }
  if ( !Parameter[6].Ptr )
  {
    v6 = "m_shutdownEvent not initialized [%#x]";
    v7 = 262;
    goto LABEL_23;
  }
  Ptr = Parameter[7].Ptr;
  if ( !Ptr )
  {
    v6 = "m_threadRunningEvent not initialized [%#x]";
    v7 = 268;
LABEL_23:
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Watch", v7, v6, -2147418113);
    return 0;
  }
  if ( SetEvent(Ptr) )
  {
    Handles[0] = Parameter[5].Ptr;
    Handles[1] = Parameter[6].Ptr;
    AslLogCallPrintf(3, "Windows::Compat::Inventory::InventoryWatchdog::Watch", 283, "Starting InventoryWatchdog...");
    while ( 1 )
    {
      do
      {
        AcquireSRWLockExclusive(Parameter + 3);
        v3 = (DWORD)Parameter->Ptr;
        if ( Parameter != (RTL_SRWLOCK *)-24LL )
          ReleaseSRWLockExclusive(Parameter + 3);
        v4 = WaitForMultipleObjects(2u, Handles, 0, v3);
      }
      while ( !v4 );
      if ( v4 != 258 )
        break;
      AcquireSRWLockExclusive(Parameter + 3);
      if ( !IsDebuggerPresent() && v3 >= LODWORD(Parameter->Ptr) )
      {
        v5 = Windows::Compat::Inventory::InventoryWatchdog::DefaultTimeoutAction;
        if ( Parameter[1].Ptr )
          v5 = (void (*)(void))Parameter[1].Ptr;
        v5();
        if ( Parameter != (RTL_SRWLOCK *)-24LL )
          ReleaseSRWLockExclusive(Parameter + 3);
        break;
      }
      if ( Parameter != (RTL_SRWLOCK *)-24LL )
        ReleaseSRWLockExclusive(Parameter + 3);
    }
    AslLogCallPrintf(3, "Windows::Compat::Inventory::InventoryWatchdog::Watch", 343, "Stopping InventoryWatchdog.");
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Watch", 274, "SetEvent failed [%d]", LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x1800252a0  mov     [rsp+arg_8], rbx
0x1800252a5  mov     [rsp+arg_10], rsi
0x1800252aa  push    rdi
0x1800252ab  sub     rsp, 40h
0x1800252af  mov     rdi, rcx
0x1800252b2  cmp     qword ptr [rcx+28h], 0
0x1800252b7  jz      loc_1800253FC
0x1800252bd  cmp     qword ptr [rcx+30h], 0
0x1800252c2  jz      loc_1800253ED
0x1800252c8  mov     rcx, [rcx+38h]; hEvent
0x1800252cc  test    rcx, rcx
0x1800252cf  jz      loc_1800253DE
0x1800252d5  call    cs:__imp_SetEvent
0x1800252db  test    eax, eax
0x1800252dd  jnz     short loc_1800252FB
0x1800252df  call    cs:__imp_GetLastError
0x1800252e5  mov     [rsp+48h+var_28], eax
0x1800252e9  lea     r9, aSeteventFailed; "SetEvent failed [%d]"
0x1800252f0  mov     r8d, 112h
0x1800252f6  jmp     loc_180025411
0x1800252fb  mov     rax, [rdi+28h]
0x1800252ff  mov     [rsp+48h+Handles], rax
0x180025304  mov     rax, [rdi+30h]
0x180025308  mov     [rsp+48h+var_10], rax
0x18002530d  lea     r9, aStartingInvent; "Starting InventoryWatchdog..."
0x180025314  mov     r8d, 11Bh
0x18002531a  lea     rdx, aWindowsCompatI_20; "Windows::Compat::Inventory::InventoryWa"...
0x180025321  mov     ecx, 3
0x180025326  call    AslLogCallPrintf
0x18002532b  lea     rbx, [rdi+18h]
0x18002532f  mov     rcx, rbx; SRWLock
0x180025332  call    cs:__imp_AcquireSRWLockExclusive
0x180025338  mov     esi, [rdi]
0x18002533a  test    rbx, rbx
0x18002533d  jz      short loc_180025348
0x18002533f  mov     rcx, rbx; SRWLock
0x180025342  call    cs:__imp_ReleaseSRWLockExclusive
0x180025348  mov     r9d, esi; dwMilliseconds
0x18002534b  xor     r8d, r8d; bWaitAll
0x18002534e  lea     rdx, [rsp+48h+Handles]; lpHandles
0x180025353  lea     ecx, [r8+2]; nCount
0x180025357  call    cs:__imp_WaitForMultipleObjects
0x18002535d  test    eax, eax
0x18002535f  jz      short loc_18002532F
0x180025361  sub     eax, 1
0x180025364  jz      short loc_1800253BE
0x180025366  cmp     eax, 101h
0x18002536b  jnz     short loc_1800253BE
0x18002536d  mov     rcx, rbx; SRWLock
0x180025370  call    cs:__imp_AcquireSRWLockExclusive
0x180025376  mov     [rsp+48h+arg_0], rbx
0x18002537b  call    cs:__imp_IsDebuggerPresent
0x180025381  test    eax, eax
0x180025383  jnz     short loc_180025389
0x180025385  cmp     esi, [rdi]
0x180025387  jnb     short loc_180025399
0x180025389  test    rbx, rbx
0x18002538c  jz      short loc_18002532F
0x18002538e  mov     rcx, rbx; SRWLock
0x180025391  call    cs:__imp_ReleaseSRWLockExclusive
0x180025397  jmp     short loc_18002532F
0x180025399  lea     rax, ?DefaultTimeoutAction@InventoryWatchdog@Inventory@Compat@Windows@@CAXXZ; Windows::Compat::Inventory::InventoryWatchdog::DefaultTimeoutAction(void)
0x1800253a0  cmp     qword ptr [rdi+8], 0
0x1800253a5  cmovnz  rax, [rdi+8]
0x1800253aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253af  nop
0x1800253b0  test    rbx, rbx
0x1800253b3  jz      short loc_1800253BE
0x1800253b5  mov     rcx, rbx; SRWLock
0x1800253b8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800253be  lea     r9, aStoppingInvent; "Stopping InventoryWatchdog."
0x1800253c5  mov     r8d, 157h
0x1800253cb  lea     rdx, aWindowsCompatI_20; "Windows::Compat::Inventory::InventoryWa"...
0x1800253d2  mov     ecx, 3
0x1800253d7  call    AslLogCallPrintf
0x1800253dc  jmp     short loc_180025422
0x1800253de  lea     r9, aMThreadrunning; "m_threadRunningEvent not initialized [%"...
0x1800253e5  mov     r8d, 10Ch
0x1800253eb  jmp     short loc_180025409
0x1800253ed  lea     r9, aMShutdownevent; "m_shutdownEvent not initialized [%#x]"
0x1800253f4  mov     r8d, 106h
0x1800253fa  jmp     short loc_180025409
0x1800253fc  lea     r9, aMStillaliveeve; "m_stillAliveEvent not initialized [%#x]"
0x180025403  mov     r8d, 100h
0x180025409  mov     [rsp+48h+var_28], 8000FFFFh
0x180025411  lea     rdx, aWindowsCompatI_20; "Windows::Compat::Inventory::InventoryWa"...
0x180025418  mov     ecx, 1
0x18002541d  call    AslLogCallPrintf
0x180025422  xor     eax, eax
0x180025424  mov     rbx, [rsp+48h+arg_8]
0x180025429  mov     rsi, [rsp+48h+arg_10]
0x18002542e  add     rsp, 40h
0x180025432  pop     rdi
0x180025433  retn
```
