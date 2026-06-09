# CsQueue::StopAndFlush(void)

- ea: `0x14005bb10`
- end: `0x14005bc63`
- name: `?StopAndFlush@CsQueue@@QEAAXXZ`
- size: `339`
- prototype: `void __fastcall(CsQueue *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140089620`

## callees

- `0x140003530`
- `0x140012a5c`
- `0x14002d890`
- `0x14005b0a0`
- `0x14005bb10`

## import_xrefs

- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14005bc3c`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14005bc3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005bbae`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005bbae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005bb98`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005bb98`

## pseudocode

```c
void __fastcall CsQueue::StopAndFlush(CsQueue *this)
{
  bool v2; // dl
  KIRQL v3; // al
  int v4; // edx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rcx
  IRP *v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r9

  v2 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      15,
      (__int64)WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids,
      (char)this);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 1);
  *((_BYTE *)this + 32) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)this + 1, v3);
  while ( 1 )
  {
    v9 = IoCsqRemoveNextIrp((PIO_CSQ)((char *)this + 40), 0);
    if ( !v9 )
      break;
    if ( !(unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v8, v7, v10, v11) )
    {
      LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qi(
          WPP_GLOBAL_Control->AttachedDevice,
          v4,
          v5,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          1,
          16,
          (__int64)WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids,
          (char)v9,
          (char)this);
    }
    CsQueue::CompleteCanceledIrpCallback((PIO_CSQ)((char *)this + 40), v9, v5, v6);
  }
}

```

## disassembly

```asm
0x14005bb10  push    rbx
0x14005bb12  push    rsi
0x14005bb13  push    rdi
0x14005bb14  push    r12
0x14005bb16  push    r14
0x14005bb18  push    r15
0x14005bb1a  sub     rsp, 58h
0x14005bb1e  mov     rdi, rcx
0x14005bb21  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bb28  lea     r14, WPP_GLOBAL_Control
0x14005bb2f  cmp     rcx, r14
0x14005bb32  jz      short loc_14005BB45
0x14005bb34  mov     eax, [rcx+2Ch]
0x14005bb37  test    al, 1
0x14005bb39  jz      short loc_14005BB45
0x14005bb3b  cmp     byte ptr [rcx+29h], 4
0x14005bb3f  jb      short loc_14005BB45
0x14005bb41  mov     dl, 1
0x14005bb43  jmp     short loc_14005BB47
0x14005bb45  xor     dl, dl
0x14005bb47  lea     r15, WPP_RECORDER_INITIALIZED
0x14005bb4e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14005bb55  lea     r12, WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids
0x14005bb5c  setnz   r8b
0x14005bb60  test    dl, dl
0x14005bb62  jnz     short loc_14005BB69
0x14005bb64  test    r8b, r8b
0x14005bb67  jz      short loc_14005BB94
0x14005bb69  mov     r9, [rcx+40h]
0x14005bb6d  mov     rcx, [rcx+18h]
0x14005bb71  mov     [rsp+88h+var_48], rdi
0x14005bb76  mov     [rsp+88h+var_50], r12
0x14005bb7b  mov     [rsp+88h+var_58], 0Fh
0x14005bb82  mov     [rsp+88h+var_60], 1
0x14005bb8a  mov     [rsp+88h+var_68], 4
0x14005bb8f  call    WPP_RECORDER_AND_TRACE_SF_q
0x14005bb94  lea     rcx, [rdi+8]; SpinLock
0x14005bb98  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005bb9f  nop     dword ptr [rax+rax+00h]
0x14005bba4  lea     rcx, [rdi+8]; SpinLock
0x14005bba8  mov     byte ptr [rdi+20h], 0
0x14005bbac  mov     dl, al; NewIrql
0x14005bbae  call    cs:__imp_KeReleaseSpinLock
0x14005bbb5  nop     dword ptr [rax+rax+00h]
0x14005bbba  lea     rsi, [rdi+28h]
0x14005bbbe  jmp     short loc_14005BC37
0x14005bbc0  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14005bbc5  test    eax, eax
0x14005bbc7  jnz     short loc_14005BC2C
0x14005bbc9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bbd0  cmp     rcx, r14
0x14005bbd3  jz      short loc_14005BBE6
0x14005bbd5  mov     eax, [rcx+2Ch]
0x14005bbd8  test    al, 1
0x14005bbda  jz      short loc_14005BBE6
0x14005bbdc  cmp     byte ptr [rcx+29h], 4
0x14005bbe0  jb      short loc_14005BBE6
0x14005bbe2  mov     dl, 1
0x14005bbe4  jmp     short loc_14005BBE8
0x14005bbe6  xor     dl, dl
0x14005bbe8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14005bbef  setnz   r8b
0x14005bbf3  test    dl, dl
0x14005bbf5  jnz     short loc_14005BBFC
0x14005bbf7  test    r8b, r8b
0x14005bbfa  jz      short loc_14005BC2C
0x14005bbfc  mov     r9, [rcx+40h]
0x14005bc00  mov     rcx, [rcx+18h]
0x14005bc04  mov     [rsp+88h+var_40], rdi
0x14005bc09  mov     [rsp+88h+var_48], rbx
0x14005bc0e  mov     [rsp+88h+var_50], r12
0x14005bc13  mov     [rsp+88h+var_58], 10h
0x14005bc1a  mov     [rsp+88h+var_60], 1
0x14005bc22  mov     [rsp+88h+var_68], 4
0x14005bc27  call    WPP_RECORDER_AND_TRACE_SF_qi
0x14005bc2c  mov     rdx, rbx; Irp
0x14005bc2f  mov     rcx, rsi; Csq
0x14005bc32  call    ?CompleteCanceledIrpCallback@CsQueue@@CAXPEAU_IO_CSQ@@PEAU_IRP@@@Z; CsQueue::CompleteCanceledIrpCallback(_IO_CSQ *,_IRP *)
0x14005bc37  xor     edx, edx; PeekContext
0x14005bc39  mov     rcx, rsi; Csq
0x14005bc3c  call    cs:__imp_IoCsqRemoveNextIrp
0x14005bc43  nop     dword ptr [rax+rax+00h]
0x14005bc48  mov     rbx, rax
0x14005bc4b  test    rax, rax
0x14005bc4e  jnz     loc_14005BBC0
0x14005bc54  add     rsp, 58h
0x14005bc58  pop     r15
0x14005bc5a  pop     r14
0x14005bc5c  pop     r12
0x14005bc5e  pop     rdi
0x14005bc5f  pop     rsi
0x14005bc60  pop     rbx
0x14005bc61  retn
```
