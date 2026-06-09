# StartRoutine

- ea: `0x140007480`
- end: `0x14000773d`
- name: `StartRoutine`
- size: `701`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x140001010`
- `0x140007480`
- `0x140008098`
- `0x140015890`
- `0x140015c80`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x140007709`
- `ntoskrnl!PsTerminateSystemThread` at `0x140007709`
- `ntoskrnl!KeSetPriorityThread` at `0x140007503`
- `ntoskrnl!KeSetPriorityThread` at `0x140007503`
- `ntoskrnl!ZwSetInformationThread` at `0x140007555`
- `ntoskrnl!ZwSetInformationThread` at `0x140007555`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400075bd`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400075bd`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140007516`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140007516`
- `ntoskrnl!KeSetEvent` at `0x1400076ca`
- `ntoskrnl!KeSetEvent` at `0x1400076ca`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x140007662`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x140007662`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14000761b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14000761b`
- `NDIS!NdisReleaseReadWriteLock` at `0x140007697`
- `NDIS!NdisReleaseReadWriteLock` at `0x140007697`
- `NDIS!NdisAcquireReadWriteLock` at `0x140007641`
- `NDIS!NdisAcquireReadWriteLock` at `0x140007641`

## string_xrefs

- `0x1400074ed`: `Spinning up a thread on processor %i\n`
- `0x1400076fb`: `Exiting queue servicing thread on processor %i\n`

## pseudocode

```c
void __fastcall StartRoutine(PVOID StartContext)
{
  ULONG v1; // esi
  struct _KTHREAD *CurrentThread; // rbx
  NTSTATUS v3; // eax
  ULONG v4; // ebx
  NTSTATUS v5; // eax
  unsigned int i; // edi
  PEX_RUNDOWN_REF_CACHE_AWARE j; // rdi
  __int64 v8; // rax
  struct _KEVENT *v9; // rdi
  _PROCESSOR_NUMBER ProcNumber; // [rsp+40h] [rbp-C0h] BYREF
  struct _LOCK_STATE LockState; // [rsp+44h] [rbp-BCh] BYREF
  __int128 ThreadInformation; // [rsp+48h] [rbp-B8h] BYREF
  PVOID Object[64]; // [rsp+60h] [rbp-A0h] BYREF
  struct _KWAIT_BLOCK WaitBlockArray; // [rsp+260h] [rbp+160h] BYREF

  v1 = (unsigned int)StartContext;
  sub_140015C80(Object, 0, 512);
  CurrentThread = KeGetCurrentThread();
  ThreadInformation = 0;
  ProcNumber = 0;
  if ( (byte_14001E7B4 & 1) != 0 )
    sub_140001010("Spinning up a thread on processor %i\n", v1);
  KeSetPriorityThread(CurrentThread, 16);
  KeGetProcessorNumberFromIndex(v1, &ProcNumber);
  *((_QWORD *)&ThreadInformation + 1) = ProcNumber.Group;
  *(_QWORD *)&ThreadInformation = 1LL << ProcNumber.Number;
  v3 = ZwSetInformationThread(
         (HANDLE)0xFFFFFFFFFFFFFFFELL,
         MaxThreadInfoClass|ThreadPriority,
         &ThreadInformation,
         0x10u);
  Object[0] = &Event;
  v4 = 2;
  Object[1] = (char *)qword_14001D298 + 24 * v1;
  if ( v3 >= 0 )
  {
    while ( 1 )
    {
      v5 = KeWaitForMultipleObjects(v4, Object, WaitAny, Executive, 0, 0, 0, &WaitBlockArray);
      if ( v5 < 0 )
        break;
      if ( !v5 )
        goto LABEL_22;
      if ( v5 == 1 )
      {
        LockState = 0;
        if ( (byte_14001E7B4 & 1) != 0 )
          sub_140001010("Re-enumerating adapters on processor %i\n", v1);
        for ( i = 2; i < v4; ++i )
          ExReleaseRundownProtectionCacheAwareEx(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Object[i] - 156), 1u);
        v4 = 2;
        NdisAcquireReadWriteLock(&Lock, 0, &LockState);
        for ( j = (PEX_RUNDOWN_REF_CACHE_AWARE)WorkItemContext; j; j = *(PEX_RUNDOWN_REF_CACHE_AWARE *)j )
        {
          if ( v4 < 0x40 )
          {
            if ( ExAcquireRundownProtectionCacheAwareEx(*((PEX_RUNDOWN_REF_CACHE_AWARE *)j + 3), 1u) )
            {
              v8 = v4++;
              Object[v8] = (char *)j + 1272;
            }
          }
        }
        NdisReleaseReadWriteLock(&Lock, &LockState);
      }
      else
      {
        v9 = (struct _KEVENT *)Object[v5];
        if ( !(unsigned __int8)sub_140008098(&v9[-53]) )
          KeSetEvent(v9, 1, 0);
      }
    }
    if ( (byte_14001E7B4 & 1) == 0 )
      goto LABEL_24;
    sub_140001010("KeWaitForMultipleObjects failed! %08x\n", v5);
LABEL_22:
    if ( (byte_14001E7B4 & 1) != 0 )
      sub_140001010("Exiting queue servicing thread on processor %i\n", v1);
  }
LABEL_24:
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140007480  mov     [rsp-8+arg_8], rbx
0x140007485  mov     [rsp-8+arg_10], rsi
0x14000748a  push    rbp
0x14000748b  push    rdi
0x14000748c  push    r14
0x14000748e  lea     rbp, [rsp-0D70h]
0x140007496  sub     rsp, 0E70h
0x14000749d  mov     rax, cs:__security_cookie
0x1400074a4  xor     rax, rsp
0x1400074a7  mov     [rbp+0D80h+var_20], rax
0x1400074ae  mov     rsi, rcx
0x1400074b1  xor     edx, edx
0x1400074b3  lea     rcx, [rsp+0E80h+Object]
0x1400074b8  mov     r8d, 200h
0x1400074be  call    sub_140015C80
0x1400074c3  mov     rbx, gs:188h
0x1400074cc  mov     r14d, 1
0x1400074d2  test    cs:byte_14001E7B4, r14b
0x1400074d9  xorps   xmm0, xmm0
0x1400074dc  movups  [rsp+0E80h+ThreadInformation], xmm0
0x1400074e1  mov     dword ptr [rsp+0E80h+ProcNumber.Group], 0
0x1400074e9  jz      short loc_1400074F9
0x1400074eb  mov     edx, esi
0x1400074ed  lea     rcx, aSpinningUpAThr; "Spinning up a thread on processor %i\n"
0x1400074f4  call    sub_140001010
0x1400074f9  mov     edi, 10h
0x1400074fe  mov     rcx, rbx; Thread
0x140007501  mov     edx, edi; Priority
0x140007503  call    cs:KeSetPriorityThread
0x14000750a  nop     dword ptr [rax+rax+00h]
0x14000750f  lea     rdx, [rsp+0E80h+ProcNumber]; ProcNumber
0x140007514  mov     ecx, esi; ProcIndex
0x140007516  call    cs:KeGetProcessorNumberFromIndex
0x14000751d  nop     dword ptr [rax+rax+00h]
0x140007522  movzx   eax, [rsp+0E80h+ProcNumber.Group]
0x140007527  lea     r8, [rsp+0E80h+ThreadInformation]; ThreadInformation
0x14000752c  mov     cl, [rsp+0E80h+ProcNumber.Number]
0x140007530  lea     edx, [rdi+0Eh]; ThreadInformationClass
0x140007533  xorps   xmm0, xmm0
0x140007536  mov     r9d, edi; ThreadInformationLength
0x140007539  movups  [rsp+0E80h+ThreadInformation], xmm0
0x14000753e  mov     word ptr [rsp+0E80h+ThreadInformation+8], ax
0x140007543  mov     rax, r14
0x140007546  shl     rax, cl
0x140007549  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140007550  mov     qword ptr [rsp+0E80h+ThreadInformation], rax
0x140007555  call    cs:ZwSetInformationThread
0x14000755c  nop     dword ptr [rax+rax+00h]
0x140007561  lea     rcx, Event
0x140007568  shr     eax, 1Fh
0x14000756b  mov     [rsp+0E80h+Object], rcx
0x140007570  lea     ebx, [rdi-0Eh]
0x140007573  mov     ecx, esi
0x140007575  lea     rdx, [rcx+rcx*2]
0x140007579  mov     rcx, cs:qword_14001D298
0x140007580  lea     rdx, [rcx+rdx*8]
0x140007584  mov     [rsp+0E80h+var_E18], rdx
0x140007589  test    al, al
0x14000758b  jnz     loc_140007707
0x140007591  lea     rax, [rbp+0D80h+var_C20]
0x140007598  xor     r9d, r9d; WaitReason
0x14000759b  mov     [rsp+0E80h+WaitBlockArray], rax; WaitBlockArray
0x1400075a0  lea     rdx, [rsp+0E80h+Object]; Object
0x1400075a5  mov     [rsp+0E80h+Timeout], 0; Timeout
0x1400075ae  mov     r8d, r14d; WaitType
0x1400075b1  mov     [rsp+0E80h+Alertable], 0; Alertable
0x1400075b6  mov     ecx, ebx; Count
0x1400075b8  mov     [rsp+0E80h+WaitMode], 0; WaitMode
0x1400075bd  call    cs:KeWaitForMultipleObjects
0x1400075c4  nop     dword ptr [rax+rax+00h]
0x1400075c9  mov     edx, eax
0x1400075cb  test    eax, eax
0x1400075cd  js      loc_1400076DB
0x1400075d3  jz      loc_1400076F0
0x1400075d9  cmp     edx, r14d
0x1400075dc  jnz     loc_1400076A8
0x1400075e2  test    cs:byte_14001E7B4, r14b
0x1400075e9  mov     dword ptr [rsp+0E80h+LockState.LockState], 0
0x1400075f1  jz      short loc_140007601
0x1400075f3  mov     edx, esi
0x1400075f5  lea     rcx, aReEnumeratingA; "Re-enumerating adapters on processor %i"...
0x1400075fc  call    sub_140001010
0x140007601  mov     edi, 2
0x140007606  cmp     ebx, edi
0x140007608  jbe     short loc_14000762E
0x14000760a  mov     eax, edi
0x14000760c  mov     edx, r14d; Count
0x14000760f  mov     rcx, [rsp+rax*8+0E80h+Object]
0x140007614  mov     rcx, [rcx-4E0h]; RunRef
0x14000761b  call    cs:ExReleaseRundownProtectionCacheAwareEx
0x140007622  nop     dword ptr [rax+rax+00h]
0x140007627  add     edi, r14d
0x14000762a  cmp     edi, ebx
0x14000762c  jb      short loc_14000760A
0x14000762e  lea     r8, [rsp+0E80h+LockState]; LockState
0x140007633  xor     edx, edx; fWrite
0x140007635  lea     rcx, Lock; Lock
0x14000763c  mov     ebx, 2
0x140007641  call    cs:NdisAcquireReadWriteLock
0x140007648  nop     dword ptr [rax+rax+00h]
0x14000764d  mov     rdi, cs:WorkItemContext
0x140007654  jmp     short loc_140007686
0x140007656  cmp     ebx, 40h ; '@'
0x140007659  jnb     short loc_140007683
0x14000765b  mov     rcx, [rdi+18h]; RunRefCacheAware
0x14000765f  mov     edx, r14d; Count
0x140007662  call    cs:ExAcquireRundownProtectionCacheAwareEx
0x140007669  nop     dword ptr [rax+rax+00h]
0x14000766e  test    al, al
0x140007670  jz      short loc_140007683
0x140007672  mov     eax, ebx
0x140007674  lea     rcx, [rdi+4F8h]
0x14000767b  add     ebx, r14d
0x14000767e  mov     [rsp+rax*8+0E80h+Object], rcx
0x140007683  mov     rdi, [rdi]
0x140007686  test    rdi, rdi
0x140007689  jnz     short loc_140007656
0x14000768b  lea     rdx, [rsp+0E80h+LockState]; LockState
0x140007690  lea     rcx, Lock; Lock
0x140007697  call    cs:NdisReleaseReadWriteLock
0x14000769e  nop     dword ptr [rax+rax+00h]
0x1400076a3  jmp     loc_140007591
0x1400076a8  mov     rdi, [rsp+rdx*8+0E80h+Object]
0x1400076ad  lea     rcx, [rdi-4F8h]
0x1400076b4  call    sub_140008098
0x1400076b9  test    al, al
0x1400076bb  jnz     loc_140007591
0x1400076c1  xor     r8d, r8d; Wait
0x1400076c4  mov     edx, r14d; Increment
0x1400076c7  mov     rcx, rdi; Event
0x1400076ca  call    cs:KeSetEvent
0x1400076d1  nop     dword ptr [rax+rax+00h]
0x1400076d6  jmp     loc_140007591
0x1400076db  test    cs:byte_14001E7B4, r14b
0x1400076e2  jz      short loc_140007707
0x1400076e4  lea     rcx, aKewaitformulti_0; "KeWaitForMultipleObjects failed! %08x\n"
0x1400076eb  call    sub_140001010
0x1400076f0  test    cs:byte_14001E7B4, r14b
0x1400076f7  jz      short loc_140007707
0x1400076f9  mov     edx, esi
0x1400076fb  lea     rcx, aExitingQueueSe; "Exiting queue servicing thread on proce"...
0x140007702  call    sub_140001010
0x140007707  xor     ecx, ecx; ExitStatus
0x140007709  call    cs:PsTerminateSystemThread
0x140007710  nop     dword ptr [rax+rax+00h]
0x140007715  mov     rcx, [rbp+0D80h+var_20]
0x14000771c  xor     rcx, rsp; StackCookie
0x14000771f  call    __security_check_cookie
0x140007724  lea     r11, [rsp+0E80h+var_10]
0x14000772c  mov     rbx, [r11+28h]
0x140007730  mov     rsi, [r11+30h]
0x140007734  mov     rsp, r11
0x140007737  pop     r14
0x140007739  pop     rdi
0x14000773a  pop     rbp
0x14000773b  retn
```
