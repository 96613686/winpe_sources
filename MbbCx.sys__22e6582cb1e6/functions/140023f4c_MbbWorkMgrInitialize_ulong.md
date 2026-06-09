# MbbWorkMgrInitialize(ulong)

- ea: `0x140023f4c`
- end: `0x1400240e4`
- name: `?MbbWorkMgrInitialize@@YAPEAXK@Z`
- size: `408`
- prototype: `void *__fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140006b60`
- `0x14001a2a4`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x14001deb0`
- `0x140023db0`
- `0x140023f4c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140023fdd`
- `ntoskrnl!KeInitializeEvent` at `0x140023ff2`
- `ntoskrnl!KeInitializeEvent` at `0x140023fdd`
- `ntoskrnl!KeInitializeEvent` at `0x140023ff2`
- `ntoskrnl!PsCreateSystemThread` at `0x14002407f`
- `ntoskrnl!PsCreateSystemThread` at `0x14002407f`
- `ntoskrnl!ExAllocatePool2` at `0x140023f65`
- `ntoskrnl!ExAllocatePool2` at `0x140023f65`
- `ntoskrnl!KeInitializeSpinLock` at `0x140023fc8`
- `ntoskrnl!KeInitializeSpinLock` at `0x140023fc8`

## pseudocode

```c
__int64 __fastcall MbbWorkMgrInitialize(unsigned int a1)
{
  __int64 Pool2; // rax
  int v3; // edx
  __int64 StartContext; // rdi
  _QWORD *v5; // rax
  __int64 v6; // rax
  int v7; // edx
  NTSTATUS SystemThread; // eax
  int v9; // edx

  Pool2 = ExAllocatePool2(64, 96, 1683505741);
  StartContext = Pool2;
  if ( Pool2 )
  {
    v5 = (_QWORD *)(Pool2 + 72);
    v5[1] = v5;
    *v5 = v5;
    KeInitializeSpinLock((PKSPIN_LOCK)StartContext);
    KeInitializeEvent((PRKEVENT)(StartContext + 48), NotificationEvent, 0);
    KeInitializeEvent((PRKEVENT)(StartContext + 24), NotificationEvent, 0);
    *(_QWORD *)(StartContext + 88) = 0;
    v6 = MbbAllocMgrInitialize(0x38u, a1, 0x6458424Du, 0);
    *(_QWORD *)(StartContext + 16) = v6;
    if ( v6 )
    {
      SystemThread = PsCreateSystemThread(
                       (PHANDLE)(StartContext + 88),
                       0xF0000u,
                       0,
                       0,
                       0,
                       MbbWorkMgrProcessWorkItem,
                       (PVOID)StartContext);
      if ( SystemThread >= 0 )
        return StartContext;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          9,
          13,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          SystemThread);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        9,
        12,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
    }
    MbbWorkMgrCleanup((PVOID)StartContext);
    return 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      9,
      11,
      (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
  }
  return StartContext;
}

```

## disassembly

```asm
0x140023f4c  push    rbx
0x140023f4e  push    rbp
0x140023f4f  push    rsi
0x140023f50  push    rdi
0x140023f51  sub     rsp, 48h
0x140023f55  mov     edx, 60h ; '`'
0x140023f5a  mov     ebp, ecx
0x140023f5c  mov     r8d, 6458424Dh
0x140023f62  lea     ecx, [rdx-20h]
0x140023f65  call    cs:__imp_ExAllocatePool2
0x140023f6c  nop     dword ptr [rax+rax+00h]
0x140023f71  mov     rdi, rax
0x140023f74  test    rax, rax
0x140023f77  jnz     short loc_140023FB8
0x140023f79  lea     rax, WPP_RECORDER_INITIALIZED
0x140023f80  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023f87  jz      loc_1400240D7
0x140023f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f94  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140023f9b  lea     r9d, [rdi+0Bh]
0x140023f9f  mov     [rsp+68h+ClientId], rax
0x140023fa4  lea     r8d, [rdi+9]
0x140023fa8  mov     dl, 2
0x140023faa  mov     rcx, [rcx+40h]
0x140023fae  call    WPP_RECORDER_SF_
0x140023fb3  jmp     loc_1400240D7
0x140023fb8  add     rax, 48h ; 'H'
0x140023fbc  mov     rcx, rdi; SpinLock
0x140023fbf  xor     ebx, ebx
0x140023fc1  mov     [rax+8], rax
0x140023fc5  mov     [rax], rax
0x140023fc8  call    cs:__imp_KeInitializeSpinLock
0x140023fcf  nop     dword ptr [rax+rax+00h]
0x140023fd4  lea     rcx, [rdi+30h]; Event
0x140023fd8  xor     r8d, r8d; State
0x140023fdb  xor     edx, edx; Type
0x140023fdd  call    cs:__imp_KeInitializeEvent
0x140023fe4  nop     dword ptr [rax+rax+00h]
0x140023fe9  lea     rcx, [rdi+18h]; Event
0x140023fed  xor     r8d, r8d; State
0x140023ff0  xor     edx, edx; Type
0x140023ff2  call    cs:__imp_KeInitializeEvent
0x140023ff9  nop     dword ptr [rax+rax+00h]
0x140023ffe  mov     r9d, ebx
0x140024001  mov     [rdi+58h], rbx
0x140024005  mov     r8d, 6458424Dh
0x14002400b  lea     ecx, [rbx+38h]
0x14002400e  mov     edx, ebp
0x140024010  call    ?MbbAllocMgrInitialize@@YAPEAXKKKTMBB_ALLOC_FLAGS@@@Z; MbbAllocMgrInitialize(ulong,ulong,ulong,MBB_ALLOC_FLAGS)
0x140024015  mov     [rdi+10h], rax
0x140024019  test    rax, rax
0x14002401c  jnz     short loc_14002405A
0x14002401e  lea     rax, WPP_RECORDER_INITIALIZED
0x140024025  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002402c  jz      loc_1400240CD
0x140024032  mov     rcx, cs:WPP_GLOBAL_Control
0x140024039  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140024040  lea     r9d, [rbx+0Ch]
0x140024044  mov     [rsp+68h+ClientId], rax
0x140024049  lea     r8d, [rbx+9]
0x14002404d  mov     dl, 2
0x14002404f  mov     rcx, [rcx+40h]
0x140024053  call    WPP_RECORDER_SF_
0x140024058  jmp     short loc_1400240CD
0x14002405a  lea     rax, ?MbbWorkMgrProcessWorkItem@@YAXPEAX@Z; MbbWorkMgrProcessWorkItem(void *)
0x140024061  mov     [rsp+68h+StartContext], rdi; StartContext
0x140024066  mov     [rsp+68h+StartRoutine], rax; StartRoutine
0x14002406b  lea     rcx, [rdi+58h]; ThreadHandle
0x14002406f  xor     r9d, r9d; ProcessHandle
0x140024072  mov     [rsp+68h+ClientId], rbx; ClientId
0x140024077  xor     r8d, r8d; ObjectAttributes
0x14002407a  mov     edx, 0F0000h; DesiredAccess
0x14002407f  call    cs:__imp_PsCreateSystemThread
0x140024086  nop     dword ptr [rax+rax+00h]
0x14002408b  mov     ecx, eax
0x14002408d  test    eax, eax
0x14002408f  jns     short loc_1400240D7
0x140024091  lea     rax, WPP_RECORDER_INITIALIZED
0x140024098  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002409f  jz      short loc_1400240CD
0x1400240a1  mov     dword ptr [rsp+68h+StartRoutine], ecx
0x1400240a5  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x1400240ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400240b3  mov     r9d, 0Dh
0x1400240b9  mov     dl, 2
0x1400240bb  mov     [rsp+68h+ClientId], rax
0x1400240c0  mov     rcx, [rcx+40h]
0x1400240c4  lea     r8d, [r9-4]
0x1400240c8  call    WPP_RECORDER_SF_d
0x1400240cd  mov     rcx, rdi; P
0x1400240d0  call    ?MbbWorkMgrCleanup@@YAXPEAX@Z; MbbWorkMgrCleanup(void *)
0x1400240d5  xor     edi, edi
0x1400240d7  mov     rax, rdi
0x1400240da  add     rsp, 48h
0x1400240de  pop     rdi
0x1400240df  pop     rsi
0x1400240e0  pop     rbp
0x1400240e1  pop     rbx
0x1400240e2  retn
```
