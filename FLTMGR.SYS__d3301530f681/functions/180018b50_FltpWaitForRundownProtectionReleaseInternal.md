# FltpWaitForRundownProtectionReleaseInternal

- ea: `0x180018b50`
- end: `0x180018cac`
- name: `FltpWaitForRundownProtectionReleaseInternal`
- size: `348`
- prototype: `__int64 __fastcall(PEX_RUNDOWN_REF RunRef)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18004c7a4`
- `0x180063b40`
- `0x1800648b0`
- `0x18006c900`

## callees

- `0x180018b50`
- `0x180024c40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180018c93`
- `ntoskrnl!ExFreePoolWithTag` at `0x180018c93`
- `ntoskrnl!KeInitializeEvent` at `0x180018bd1`
- `ntoskrnl!KeInitializeEvent` at `0x180018bd1`
- `ntoskrnl!KeWaitForSingleObject` at `0x180018c83`
- `ntoskrnl!KeWaitForSingleObject` at `0x180018c83`
- `ntoskrnl!KeInitializeDpc` at `0x180018bed`
- `ntoskrnl!KeInitializeDpc` at `0x180018bed`
- `ntoskrnl!KeCancelTimer` at `0x180018c3c`
- `ntoskrnl!KeCancelTimer` at `0x180018c3c`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x180018c63`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x180018c63`
- `ntoskrnl!KeInitializeTimer` at `0x180018bfd`
- `ntoskrnl!KeInitializeTimer` at `0x180018bfd`
- `ntoskrnl!KeSetTimer` at `0x180018c18`
- `ntoskrnl!KeSetTimer` at `0x180018c18`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x180018c2c`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x180018c2c`

## pseudocode

```c
void __fastcall FltpWaitForRundownProtectionReleaseInternal(struct _EX_RUNDOWN_REF_CACHE_AWARE *RunRef, char a2)
{
  _QWORD DeferredContext[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct _KEVENT Event; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+68h] [rbp-98h]
  __int64 v7; // [rsp+70h] [rbp-90h]
  struct _KDPC Dpc; // [rsp+80h] [rbp-80h] BYREF
  struct _KTIMER Timer; // [rsp+C0h] [rbp-40h] BYREF

  memset(&Dpc, 0, 60);
  memset(&Timer, 0, sizeof(Timer));
  DeferredContext[2] = FltpSendModernAppTerminationWorker;
  DeferredContext[1] = 0;
  DeferredContext[3] = DeferredContext;
  memset(&Event, 0, sizeof(Event));
  v7 = 0;
  P = 0;
  DeferredContext[0] = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  KeInitializeDpc(&Dpc, FltpSendModernAppTermination, DeferredContext);
  KeInitializeTimer(&Timer);
  KeSetTimer(&Timer, (LARGE_INTEGER)-100000000LL, &Dpc);
  if ( a2 )
    ExWaitForRundownProtectionReleaseCacheAware(RunRef);
  else
    ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)RunRef);
  if ( KeCancelTimer(&Timer) )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
  }
  else
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x180018b50  push    rbp
0x180018b52  push    rbx
0x180018b53  push    rsi
0x180018b54  push    rdi
0x180018b55  lea     rbp, [rsp-8]
0x180018b5a  sub     rsp, 108h
0x180018b61  xorps   xmm0, xmm0
0x180018b64  movzx   edi, dl
0x180018b67  mov     rbx, rcx
0x180018b6a  xor     eax, eax
0x180018b6c  movups  xmmword ptr [rbp+20h+Dpc.DeferredContext], xmm0
0x180018b70  xor     edx, edx; Val
0x180018b72  lea     rcx, [rbp+20h+Timer]; void *
0x180018b76  mov     r8d, 40h ; '@'; Size
0x180018b7c  movups  xmmword ptr [rbp+20h+Dpc.SystemArgument1+4], xmm0
0x180018b80  movups  xmmword ptr [rbp+20h+Dpc], xmm0
0x180018b84  movups  xmmword ptr [rbp+20h+Dpc.ProcessorHistory], xmm0
0x180018b88  call    memset
0x180018b8d  xor     esi, esi
0x180018b8f  lea     rax, FltpSendModernAppTerminationWorker
0x180018b96  mov     [rsp+120h+var_E0], rax
0x180018b9b  lea     rcx, [rsp+120h+Event]; Event
0x180018ba0  lea     rax, [rsp+120h+DeferredContext]
0x180018ba5  mov     [rsp+120h+var_E8], rsi
0x180018baa  xorps   xmm0, xmm0
0x180018bad  mov     [rsp+120h+var_D8], rax
0x180018bb2  xor     r8d, r8d; State
0x180018bb5  movdqa  xmmword ptr [rsp+120h+Event.Header], xmm0
0x180018bbb  xor     edx, edx; Type
0x180018bbd  mov     [rsp+120h+Event.Header.WaitListHead.Blink], rsi
0x180018bc2  mov     [rsp+120h+var_B0], rsi
0x180018bc7  mov     [rsp+120h+P], rsi
0x180018bcc  mov     [rsp+120h+DeferredContext], rsi
0x180018bd1  call    cs:__imp_KeInitializeEvent
0x180018bd8  nop     dword ptr [rax+rax+00h]
0x180018bdd  lea     r8, [rsp+120h+DeferredContext]; DeferredContext
0x180018be2  lea     rdx, FltpSendModernAppTermination; DeferredRoutine
0x180018be9  lea     rcx, [rbp+20h+Dpc]; Dpc
0x180018bed  call    cs:__imp_KeInitializeDpc
0x180018bf4  nop     dword ptr [rax+rax+00h]
0x180018bf9  lea     rcx, [rbp+20h+Timer]; Timer
0x180018bfd  call    cs:__imp_KeInitializeTimer
0x180018c04  nop     dword ptr [rax+rax+00h]
0x180018c09  lea     r8, [rbp+20h+Dpc]; Dpc
0x180018c0d  mov     rdx, 0FFFFFFFFFA0A1F00h; DueTime
0x180018c14  lea     rcx, [rbp+20h+Timer]; Timer
0x180018c18  call    cs:__imp_KeSetTimer
0x180018c1f  nop     dword ptr [rax+rax+00h]
0x180018c24  mov     rcx, rbx; RunRef
0x180018c27  test    dil, dil
0x180018c2a  jz      short loc_180018C63
0x180018c2c  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x180018c33  nop     dword ptr [rax+rax+00h]
0x180018c38  lea     rcx, [rbp+20h+Timer]; PKTIMER
0x180018c3c  call    cs:__imp_KeCancelTimer
0x180018c43  nop     dword ptr [rax+rax+00h]
0x180018c48  test    al, al
0x180018c4a  jz      short loc_180018C71
0x180018c4c  mov     rcx, [rsp+120h+P]; P
0x180018c51  test    rcx, rcx
0x180018c54  jnz     short loc_180018C91
0x180018c56  add     rsp, 108h
0x180018c5d  pop     rdi
0x180018c5e  pop     rsi
0x180018c5f  pop     rbx
0x180018c60  pop     rbp
0x180018c61  retn
0x180018c63  call    cs:__imp_ExWaitForRundownProtectionRelease
0x180018c6a  nop     dword ptr [rax+rax+00h]
0x180018c6f  jmp     short loc_180018C38
0x180018c71  xor     r9d, r9d; Alertable
0x180018c74  mov     [rsp+120h+Timeout], rsi; Timeout
0x180018c79  xor     r8d, r8d; WaitMode
0x180018c7c  lea     rcx, [rsp+120h+Event]; Object
0x180018c81  xor     edx, edx; WaitReason
0x180018c83  call    cs:__imp_KeWaitForSingleObject
0x180018c8a  nop     dword ptr [rax+rax+00h]
0x180018c8f  jmp     short loc_180018C56
0x180018c91  xor     edx, edx; Tag
0x180018c93  call    cs:__imp_ExFreePoolWithTag
0x180018c9a  nop     dword ptr [rax+rax+00h]
0x180018c9f  add     rsp, 108h
0x180018ca6  pop     rdi
0x180018ca7  pop     rsi
0x180018ca8  pop     rbx
0x180018ca9  pop     rbp
0x180018caa  retn
```
