# HmgDecProcessHandleCount

- ea: `0x140020758`
- end: `0x140020a2b`
- name: `HmgDecProcessHandleCount`
- size: `723`
- prototype: ``
- caller_count: `9`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007690`
- `0x140015410`
- `0x140018d20`
- `0x140019670`
- `0x14001a0f0`
- `0x14001d890`
- `0x14001f060`
- `0x1400204f0`
- `0x140039650`

## callees

- `0x140013ff0`
- `0x14001c970`
- `0x14001cb30`
- `0x140020758`
- `0x140028974`
- `0x1400411c0`
- `0x14010f2b0`
- `0x140190650`
- `0x1401ab6b0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002079b`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002079b`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140020852`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140020852`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140020784`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140020784`
- `ntoskrnl!PsSetProcessWin32Process` at `0x140020a12`
- `ntoskrnl!PsSetProcessWin32Process` at `0x140020a12`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400208dd`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400208dd`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002091f`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002091f`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400208ce`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400208ce`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002083f`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002083f`
- `ntoskrnl!ObfReferenceObject` at `0x1400207c5`
- `ntoskrnl!ObfReferenceObject` at `0x14002095a`
- `ntoskrnl!ObfReferenceObject` at `0x1400207c5`
- `ntoskrnl!ObfReferenceObject` at `0x14002095a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400208a7`
- `ntoskrnl!ObfDereferenceObject` at `0x14002096f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400208a7`
- `ntoskrnl!ObfDereferenceObject` at `0x14002096f`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140020934`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140020934`

## pseudocode

```c
void __fastcall HmgDecProcessHandleCount(_QWORD *a1, int a2)
{
  void *v2; // rbx
  PVOID *CurrentProcessWin32Process; // rax
  volatile signed __int32 *v5; // rbx
  HSEMAPHORE v6; // rbp
  struct _GRETHREAD *v7; // rax
  unsigned __int64 i; // rcx
  __int64 v9; // r8
  struct _GRETHREAD *v10; // rdi
  struct _KTHREAD *CurrentThread; // r14
  __int64 v12; // rsi
  __int64 *ThreadWin32Thread; // rax
  __int64 v14; // rax
  __int64 v15; // rsi
  void *v17; // rdi
  bool v18; // cl
  int CurrentWin32kSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  bool v21; // cl
  PVOID *ProcessWin32Process; // rax
  int v23; // edx
  int v24; // eax
  PEPROCESS Process; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 )
    return;
  v2 = (void *)a2;
  if ( a2 == -2147483630 )
    return;
  if ( a2 == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
  {
    CurrentProcessWin32Process = (PVOID *)PsGetCurrentProcessWin32Process();
    v5 = (volatile signed __int32 *)CurrentProcessWin32Process;
    if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process || !CurrentProcessWin32Process )
      return;
    ObfReferenceObject(*CurrentProcessWin32Process);
    _InterlockedIncrement(v5 + 2);
    goto LABEL_8;
  }
  Process = 0;
  if ( PsLookupProcessByProcessId(v2, &Process) >= 0 )
  {
    ProcessWin32Process = (PVOID *)PsGetProcessWin32Process(Process);
    v5 = (volatile signed __int32 *)ProcessWin32Process;
    if ( !ProcessWin32Process || *ProcessWin32Process )
    {
      if ( ProcessWin32Process )
      {
        ObfReferenceObject(*ProcessWin32Process);
        _InterlockedIncrement(v5 + 2);
      }
    }
    else
    {
      v5 = 0;
    }
    ObfDereferenceObject(Process);
    if ( v5 )
    {
LABEL_8:
      v6 = (HSEMAPHORE)(*a1 + 1512LL);
      GreAcquireSemaphoreInternal(v6);
      v7 = GreGetCurrentThreadCrossSessionCheck();
      v10 = v7;
      if ( v7 )
      {
        v9 = *(_QWORD *)v7;
        if ( (*(_QWORD *)v7 & 0xFFFFFFDFFFF00000uLL) != 0 && (v9 & 0x100000) == 0 )
        {
          v23 = 38;
          for ( i = 0; i < 0x40; ++i )
          {
            v24 = i;
            if ( ((1LL << i) & 0xFFFFFFDFFFFFFFFFuLL & v9) == 0 )
              v24 = v23;
            v23 = v24;
          }
          if ( v24 > 20 && v24 != 38 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(i, (unsigned int)v24);
        }
        LOBYTE(i) = *((_BYTE *)v10 + 28);
        *((_BYTE *)v10 + 28) = i + 1;
        if ( !(_BYTE)i )
          *(_QWORD *)v10 |= 0x100000uLL;
      }
      --*((_DWORD *)v5 + 15);
      if ( v6 )
      {
        if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
          McTemplateK0pz_EtwWriteTransfer(i, (unsigned int)&LockRelease, v9, (_DWORD)v6, (__int64)L"Hmgr");
        CurrentThread = KeGetCurrentThread();
        v12 = 0;
        if ( !(unsigned __int8)KeIsAttachedProcess()
          || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
              CurrentThreadProcess = PsGetCurrentThreadProcess(),
              CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
        {
          ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
          if ( ThreadWin32Thread )
            v12 = *ThreadWin32Thread;
        }
        v14 = v12 + 8;
        v15 = -v12;
        if ( (v14 & -(__int64)(v15 != 0)) != 0 && (*(_BYTE *)((v14 & -(__int64)(v15 != 0)) + 0x1C))-- == 1 )
          *(_QWORD *)(v14 & -(__int64)(v15 != 0)) &= ~0x100000uLL;
        GreReleaseSemaphoreSharedInternal(v6);
      }
      v17 = *(void **)v5;
      v18 = (v5[69] & 0x200) != 0;
      if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
      {
        v21 = !v18;
        if ( v21 )
        {
          if ( v21 )
            UserDeleteW32Process((PVOID)v5);
        }
        else
        {
          PsSetProcessWin32Process(*(_QWORD *)v5, 0, v5);
          GreDeleteFastMutex((PVOID)v5);
        }
      }
      ObfDereferenceObject(v17);
    }
  }
}

```

## disassembly

```asm
0x140020758  test    edx, edx
0x14002075a  jz      locret_1400208C5
0x140020760  mov     [rsp+arg_0], rbx
0x140020765  mov     [rsp+arg_18], rbp
0x14002076a  push    rsi
0x14002076b  push    rdi
0x14002076c  push    r14
0x14002076e  sub     rsp, 30h
0x140020772  movsxd  rbx, edx
0x140020775  mov     rdi, rcx
0x140020778  cmp     ebx, 80000012h
0x14002077e  jz      loc_1400208B3
0x140020784  call    cs:__imp_PsGetCurrentProcessId
0x14002078b  nop     dword ptr [rax+rax+00h]
0x140020790  and     eax, 0FFFFFFFCh
0x140020793  cmp     ebx, eax
0x140020795  jnz     loc_14002090E
0x14002079b  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400207a2  nop     dword ptr [rax+rax+00h]
0x1400207a7  mov     rbx, rax
0x1400207aa  test    rax, rax
0x1400207ad  jz      short loc_1400207B9
0x1400207af  cmp     qword ptr [rax], 0
0x1400207b3  jz      loc_1400208B3
0x1400207b9  test    rbx, rbx
0x1400207bc  jz      loc_1400208B3
0x1400207c2  mov     rcx, [rax]; Object
0x1400207c5  call    cs:__imp_ObfReferenceObject
0x1400207cc  nop     dword ptr [rax+rax+00h]
0x1400207d1  lock inc dword ptr [rbx+8]
0x1400207d5  mov     rbp, [rdi]
0x1400207d8  add     rbp, 5E8h
0x1400207df  mov     rcx, rbp; Resource
0x1400207e2  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x1400207e7  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x1400207ec  mov     rdi, rax
0x1400207ef  test    rax, rax
0x1400207f2  jz      short loc_14002081F
0x1400207f4  mov     r8, [rax]
0x1400207f7  mov     esi, 100000h
0x1400207fc  mov     rax, 0FFFFFFDFFFF00000h
0x140020806  test    rax, r8
0x140020809  jnz     loc_140020989
0x14002080f  mov     cl, [rdi+1Ch]
0x140020812  lea     eax, [rcx+1]
0x140020815  mov     [rdi+1Ch], al
0x140020818  test    cl, cl
0x14002081a  jnz     short loc_14002081F
0x14002081c  or      [rdi], rsi
0x14002081f  dec     dword ptr [rbx+3Ch]
0x140020822  test    rbp, rbp
0x140020825  jz      short loc_140020888
0x140020827  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14002082e  jnz     loc_1400209DD
0x140020834  mov     r14, gs:188h
0x14002083d  xor     esi, esi
0x14002083f  call    cs:__imp_KeIsAttachedProcess
0x140020846  nop     dword ptr [rax+rax+00h]
0x14002084b  test    al, al
0x14002084d  jnz     short loc_1400208C7
0x14002084f  mov     rcx, r14
0x140020852  call    cs:__imp_PsGetThreadWin32Thread
0x140020859  nop     dword ptr [rax+rax+00h]
0x14002085e  test    rax, rax
0x140020861  jz      short loc_140020866
0x140020863  mov     rsi, [rax]
0x140020866  lea     rax, [rsi+8]
0x14002086a  neg     rsi
0x14002086d  sbb     rdx, rdx
0x140020870  and     rdx, rax
0x140020873  jz      short loc_140020880
0x140020875  add     byte ptr [rdx+1Ch], 0FFh
0x140020879  jnz     short loc_140020880
0x14002087b  btr     qword ptr [rdx], 14h
0x140020880  mov     rcx, rbp; HSEMAPHORE
0x140020883  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140020888  mov     ecx, [rbx+114h]
0x14002088e  mov     rdi, [rbx]
0x140020891  shr     ecx, 9
0x140020894  and     cl, 1
0x140020897  or      eax, 0FFFFFFFFh
0x14002089a  lock xadd [rbx+8], eax
0x14002089f  cmp     eax, 1
0x1400208a2  jz      short loc_1400208F6
0x1400208a4  mov     rcx, rdi; Object
0x1400208a7  call    cs:__imp_ObfDereferenceObject
0x1400208ae  nop     dword ptr [rax+rax+00h]
0x1400208b3  mov     rbx, [rsp+48h+arg_0]
0x1400208b8  mov     rbp, [rsp+48h+arg_18]
0x1400208bd  add     rsp, 30h
0x1400208c1  pop     r14
0x1400208c3  pop     rdi
0x1400208c4  pop     rsi
0x1400208c5  retn
0x1400208c7  call    W32GetCurrentWin32kSessionId
0x1400208cc  mov     edi, eax
0x1400208ce  call    cs:__imp_PsGetCurrentThreadProcess
0x1400208d5  nop     dword ptr [rax+rax+00h]
0x1400208da  mov     rcx, rax
0x1400208dd  call    cs:__imp_PsGetProcessSessionIdEx
0x1400208e4  nop     dword ptr [rax+rax+00h]
0x1400208e9  cmp     edi, eax
0x1400208eb  jz      loc_14002084F
0x1400208f1  jmp     loc_140020866
0x1400208f6  xor     cl, 1
0x1400208f9  jz      loc_140020A0A
0x1400208ff  cmp     cl, 1
0x140020902  jnz     short loc_1400208A4
0x140020904  mov     rcx, rbx; Buffer
0x140020907  call    UserDeleteW32Process
0x14002090c  jmp     short loc_1400208A4
0x14002090e  mov     rcx, rbx; ProcessId
0x140020911  mov     [rsp+48h+Process], 0
0x14002091a  lea     rdx, [rsp+48h+Process]; Process
0x14002091f  call    cs:__imp_PsLookupProcessByProcessId
0x140020926  nop     dword ptr [rax+rax+00h]
0x14002092b  test    eax, eax
0x14002092d  js      short loc_1400208B3
0x14002092f  mov     rcx, [rsp+48h+Process]
0x140020934  call    cs:__imp_PsGetProcessWin32Process
0x14002093b  nop     dword ptr [rax+rax+00h]
0x140020940  mov     rbx, rax
0x140020943  test    rax, rax
0x140020946  jz      short loc_140020952
0x140020948  cmp     qword ptr [rax], 0
0x14002094c  jnz     short loc_140020952
0x14002094e  xor     ebx, ebx
0x140020950  jmp     short loc_14002096A
0x140020952  test    rbx, rbx
0x140020955  jz      short loc_14002096A
0x140020957  mov     rcx, [rax]; Object
0x14002095a  call    cs:__imp_ObfReferenceObject
0x140020961  nop     dword ptr [rax+rax+00h]
0x140020966  lock inc dword ptr [rbx+8]
0x14002096a  mov     rcx, [rsp+48h+Process]; Object
0x14002096f  call    cs:__imp_ObfDereferenceObject
0x140020976  nop     dword ptr [rax+rax+00h]
0x14002097b  test    rbx, rbx
0x14002097e  jnz     loc_1400207D5
0x140020984  jmp     loc_1400208B3
0x140020989  test    rsi, r8
0x14002098c  jnz     loc_14002080F
0x140020992  mov     edx, 26h ; '&'
0x140020997  xor     ecx, ecx
0x140020999  mov     eax, 1
0x14002099e  mov     r9, 0FFFFFFDFFFFFFFFFh
0x1400209a8  shl     rax, cl
0x1400209ab  and     rax, r9
0x1400209ae  test    r8, rax
0x1400209b1  mov     eax, ecx
0x1400209b3  cmovz   eax, edx
0x1400209b6  inc     rcx
0x1400209b9  mov     edx, eax
0x1400209bb  cmp     rcx, 40h ; '@'
0x1400209bf  jb      short loc_140020999
0x1400209c1  cmp     eax, 14h
0x1400209c4  jle     loc_14002080F
0x1400209ca  cmp     eax, 26h ; '&'
0x1400209cd  jz      loc_14002080F
0x1400209d3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400209d8  jmp     loc_14002080F
0x1400209dd  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x1400209e4  jz      loc_140020834
0x1400209ea  lea     rax, aHmgr; "Hmgr"
0x1400209f1  mov     r9, rbp
0x1400209f4  lea     rdx, LockRelease
0x1400209fb  mov     [rsp+48h+var_28], rax
0x140020a00  call    McTemplateK0pz_EtwWriteTransfer
0x140020a05  jmp     loc_140020834
0x140020a0a  mov     rcx, [rbx]
0x140020a0d  mov     r8, rbx
0x140020a10  xor     edx, edx
0x140020a12  call    cs:__imp_PsSetProcessWin32Process
0x140020a19  nop     dword ptr [rax+rax+00h]
0x140020a1e  mov     rcx, rbx; Buffer
0x140020a21  call    GreDeleteFastMutex
0x140020a26  jmp     loc_1400208A4
```
