# CancelReadyIrp

- ea: `0x140009a88`
- end: `0x140009b70`
- name: `CancelReadyIrp`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140008720`
- `0x140009c10`

## callees

- `0x140004adc`
- `0x140009a88`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009ae1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009ae1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009ab9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009ab9`
- `ntoskrnl!IoCancelIrp` at `0x140009af5`
- `ntoskrnl!IoCancelIrp` at `0x140009af5`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140009b2c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140009b2c`

## pseudocode

```c
void __fastcall CancelReadyIrp(__int64 a1)
{
  KSPIN_LOCK *v2; // rcx
  IRP *v3; // rdi
  IRP **v4; // rbx
  char v5; // bl
  int Default; // eax
  int v7; // edx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-28h] BYREF

  v2 = (KSPIN_LOCK *)(*(_QWORD *)a1 + 1136LL);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v3 = 0;
  KeAcquireInStackQueuedSpinLock(v2, &LockHandle);
  v4 = (IRP **)(a1 + 136);
  if ( *(_DWORD *)(a1 + 20) == 2 )
  {
    v3 = *v4;
    *(_BYTE *)(a1 + 203) = 1;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v3 == *v4 )
  {
    IoCancelIrp(v3);
    if ( gTracingEnabled )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v5 = *(_WORD *)(a1 + 40) - 1;
        Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v7) = 4;
        WPP_RECORDER_SF_iD(Default, v7, 3, 40, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, (char)v3, v5);
      }
    }
  }
}

```

## disassembly

```asm
0x140009a88  mov     r11, rsp
0x140009a8b  mov     [r11+8], rbx
0x140009a8f  mov     [r11+10h], rsi
0x140009a93  push    rdi
0x140009a94  sub     rsp, 60h
0x140009a98  mov     rsi, rcx
0x140009a9b  lea     rdx, [r11-28h]; LockHandle
0x140009a9f  mov     rcx, [rcx]
0x140009aa2  xorps   xmm0, xmm0
0x140009aa5  xor     eax, eax
0x140009aa7  add     rcx, 470h; SpinLock
0x140009aae  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x140009ab3  mov     [r11-18h], rax
0x140009ab7  xor     edi, edi
0x140009ab9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009ac0  nop     dword ptr [rax+rax+00h]
0x140009ac5  cmp     dword ptr [rsi+14h], 2
0x140009ac9  lea     rbx, [rsi+88h]
0x140009ad0  jnz     short loc_140009ADC
0x140009ad2  mov     rdi, [rbx]
0x140009ad5  mov     byte ptr [rsi+0CBh], 1
0x140009adc  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140009ae1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140009ae8  nop     dword ptr [rax+rax+00h]
0x140009aed  cmp     rdi, [rbx]
0x140009af0  jnz     short loc_140009B5F
0x140009af2  mov     rcx, rdi; Irp
0x140009af5  call    cs:__imp_IoCancelIrp
0x140009afc  nop     dword ptr [rax+rax+00h]
0x140009b01  cmp     cs:gTracingEnabled, 0
0x140009b08  jz      short loc_140009B5F
0x140009b0a  lea     rax, WPP_RECORDER_INITIALIZED
0x140009b11  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009b18  jz      short loc_140009B5F
0x140009b1a  movzx   ebx, word ptr [rsi+28h]
0x140009b1e  mov     esi, 28h ; '('
0x140009b23  mov     rcx, cs:WPP_GLOBAL_Control
0x140009b2a  dec     ebx
0x140009b2c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140009b33  nop     dword ptr [rax+rax+00h]
0x140009b38  mov     [rsp+68h+var_38], ebx
0x140009b3c  lea     r8d, [rsi-25h]
0x140009b40  mov     rcx, rax
0x140009b43  mov     [rsp+68h+var_40], rdi
0x140009b48  lea     rax, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x140009b4f  movzx   r9d, si
0x140009b53  mov     dl, 4
0x140009b55  mov     [rsp+68h+var_48], rax
0x140009b5a  call    WPP_RECORDER_SF_iD
0x140009b5f  mov     rbx, [rsp+68h+arg_0]
0x140009b64  mov     rsi, [rsp+68h+arg_8]
0x140009b69  add     rsp, 60h
0x140009b6d  pop     rdi
0x140009b6e  retn
```
