# CPcmPin::AVStrMiniPinReset(_KSPIN *)

- ea: `0x14003ae10`
- end: `0x14003affc`
- name: `?AVStrMiniPinReset@CPcmPin@@SAXPEAU_KSPIN@@@Z`
- size: `492`
- prototype: `void __fastcall(PVOID Object)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005800`
- `0x14000f570`
- `0x14001be60`
- `0x14003ae10`
- `0x14003b160`

## import_xrefs

- `ntoskrnl!ExCancelTimer` at `0x14003aec5`
- `ntoskrnl!ExCancelTimer` at `0x14003aec5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003aef5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003aef5`
- `HAL!KeQueryPerformanceCounter` at `0x14003af5d`
- `HAL!KeQueryPerformanceCounter` at `0x14003af5d`
- `ks!KsReleaseControl` at `0x14003afdc`
- `ks!KsReleaseControl` at `0x14003afdc`
- `ks!KsStreamPointerDelete` at `0x14003afb2`
- `ks!KsStreamPointerDelete` at `0x14003afb2`
- `ks!KsStreamPointerGetNextClone` at `0x14003af74`
- `ks!KsStreamPointerGetNextClone` at `0x14003af74`
- `ks!KsPinGetFirstCloneStreamPointer` at `0x14003af40`
- `ks!KsPinGetFirstCloneStreamPointer` at `0x14003af40`
- `ks!KsAcquireControl` at `0x14003ae9a`
- `ks!KsAcquireControl` at `0x14003ae9a`

## pseudocode

```c
void __fastcall CPcmPin::AVStrMiniPinReset(_QWORD *Object)
{
  bool v2; // dl
  __int64 v3; // rdi
  int v4; // eax
  struct _KSPIN *v5; // rcx
  PKSSTREAM_POINTER FirstCloneStreamPointer; // rax
  struct _KSSTREAM_POINTER *v7; // rbp
  LARGE_INTEGER v8; // rbx
  PKSSTREAM_POINTER NextClone; // rax
  struct _KSSTREAM_POINTER *v10; // r14
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+60h] [rbp+8h] BYREF

  v2 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      27,
      (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids);
  v3 = Object[2];
  KsAcquireControl(Object);
  v4 = *((_DWORD *)Object + 31);
  if ( !v4 )
  {
    _InterlockedExchange((volatile __int32 *)(v3 + 244), 1);
    if ( (unsigned __int8)ExCancelTimer(*(_QWORD *)(v3 + 256), 0) )
      CPcmPin::UnlockTimerDpc((CPcmPin *)v3);
    KeWaitForSingleObject((PVOID)(v3 + 264), Executive, 0, 0, 0);
    *(_QWORD *)(v3 + 56) = 0;
    *(_QWORD *)(v3 + 64) = 0;
    *(_QWORD *)(v3 + 72) = 0;
    *(_QWORD *)(v3 + 40) = 0;
    CPcmPin::ResetCorrelatedPosition((CPcmPin *)v3);
    v5 = *(struct _KSPIN **)(v3 + 16);
    *(_QWORD *)(v3 + 144) = 0;
    *(_QWORD *)(v3 + 120) = 0;
    FirstCloneStreamPointer = KsPinGetFirstCloneStreamPointer(v5);
    PerformanceFrequency.QuadPart = 0;
    v7 = FirstCloneStreamPointer;
    v8 = KeQueryPerformanceCounter(&PerformanceFrequency);
    if ( v7 )
    {
      do
      {
        NextClone = KsStreamPointerGetNextClone(v7);
        v10 = NextClone;
        if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
          McTemplateK0px_EtwWriteTransfer(
            v8.QuadPart - *(_QWORD *)NextClone->Context,
            1000 * (v8.QuadPart - *(_QWORD *)NextClone->Context) % *((_QWORD *)NextClone->Context + 1),
            NextClone->Context,
            v7);
        KsStreamPointerDelete(v7);
        _InterlockedDecrement((volatile signed __int32 *)(v3 + 48));
        v7 = v10;
      }
      while ( v10 );
    }
    goto LABEL_18;
  }
  if ( v4 == 1 )
LABEL_18:
    _InterlockedExchange((volatile __int32 *)(v3 + 244), 0);
  KsReleaseControl(Object);
}

```

## disassembly

```asm
0x14003ae10  mov     [rsp+arg_8], rbx
0x14003ae15  mov     [rsp+arg_10], rbp
0x14003ae1a  push    rsi
0x14003ae1b  push    rdi
0x14003ae1c  push    r14
0x14003ae1e  sub     rsp, 40h
0x14003ae22  mov     rsi, rcx
0x14003ae25  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ae2c  lea     rax, WPP_GLOBAL_Control
0x14003ae33  cmp     rcx, rax
0x14003ae36  jz      short loc_14003AE49
0x14003ae38  mov     eax, [rcx+2Ch]
0x14003ae3b  test    al, 10h
0x14003ae3d  jz      short loc_14003AE49
0x14003ae3f  cmp     byte ptr [rcx+29h], 4
0x14003ae43  jb      short loc_14003AE49
0x14003ae45  mov     dl, 1
0x14003ae47  jmp     short loc_14003AE4B
0x14003ae49  xor     dl, dl
0x14003ae4b  lea     rax, WPP_RECORDER_INITIALIZED
0x14003ae52  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003ae59  setnz   r8b
0x14003ae5d  test    dl, dl
0x14003ae5f  jnz     short loc_14003AE66
0x14003ae61  test    r8b, r8b
0x14003ae64  jz      short loc_14003AE93
0x14003ae66  mov     r9, [rcx+40h]
0x14003ae6a  lea     rax, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x14003ae71  mov     rcx, [rcx+18h]
0x14003ae75  mov     [rsp+58h+var_20], rax
0x14003ae7a  mov     [rsp+58h+var_28], 1Bh
0x14003ae81  mov     [rsp+58h+var_30], 5
0x14003ae89  mov     byte ptr [rsp+58h+Timeout], 4
0x14003ae8e  call    WPP_RECORDER_AND_TRACE_SF_
0x14003ae93  mov     rdi, [rsi+10h]
0x14003ae97  mov     rcx, rsi; Object
0x14003ae9a  call    cs:__imp_KsAcquireControl
0x14003aea1  nop     dword ptr [rax+rax+00h]
0x14003aea6  mov     eax, [rsi+7Ch]
0x14003aea9  test    eax, eax
0x14003aeab  jnz     loc_14003AFCC
0x14003aeb1  mov     eax, 1
0x14003aeb6  xor     edx, edx
0x14003aeb8  xchg    eax, [rdi+0F4h]
0x14003aebe  mov     rcx, [rdi+100h]
0x14003aec5  call    cs:__imp_ExCancelTimer
0x14003aecc  nop     dword ptr [rax+rax+00h]
0x14003aed1  test    al, al
0x14003aed3  jz      short loc_14003AEDD
0x14003aed5  mov     rcx, rdi; this
0x14003aed8  call    ?UnlockTimerDpc@CPcmPin@@AEAAJXZ; CPcmPin::UnlockTimerDpc(void)
0x14003aedd  lea     rcx, [rdi+108h]; Object
0x14003aee4  mov     [rsp+58h+Timeout], 0; Timeout
0x14003aeed  xor     r9d, r9d; Alertable
0x14003aef0  xor     r8d, r8d; WaitMode
0x14003aef3  xor     edx, edx; WaitReason
0x14003aef5  call    cs:__imp_KeWaitForSingleObject
0x14003aefc  nop     dword ptr [rax+rax+00h]
0x14003af01  mov     rcx, rdi; this
0x14003af04  mov     qword ptr [rdi+38h], 0
0x14003af0c  mov     qword ptr [rdi+40h], 0
0x14003af14  mov     qword ptr [rdi+48h], 0
0x14003af1c  mov     qword ptr [rdi+28h], 0
0x14003af24  call    ?ResetCorrelatedPosition@CPcmPin@@AEAAXXZ; CPcmPin::ResetCorrelatedPosition(void)
0x14003af29  mov     rcx, [rdi+10h]; Pin
0x14003af2d  mov     qword ptr [rdi+90h], 0
0x14003af38  mov     qword ptr [rdi+78h], 0
0x14003af40  call    cs:__imp_KsPinGetFirstCloneStreamPointer
0x14003af47  nop     dword ptr [rax+rax+00h]
0x14003af4c  lea     rcx, [rsp+58h+PerformanceFrequency]; PerformanceFrequency
0x14003af51  mov     qword ptr [rsp+58h+PerformanceFrequency], 0
0x14003af5a  mov     rbp, rax
0x14003af5d  call    cs:__imp_KeQueryPerformanceCounter
0x14003af64  nop     dword ptr [rax+rax+00h]
0x14003af69  mov     rbx, rax
0x14003af6c  test    rbp, rbp
0x14003af6f  jz      short loc_14003AFD1
0x14003af71  mov     rcx, rbp; StreamPointer
0x14003af74  call    cs:__imp_KsStreamPointerGetNextClone
0x14003af7b  nop     dword ptr [rax+rax+00h]
0x14003af80  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 1
0x14003af87  mov     r14, rax
0x14003af8a  jz      short loc_14003AFAF
0x14003af8c  mov     r8, [rax]
0x14003af8f  mov     rcx, rbx
0x14003af92  mov     r9, rbp
0x14003af95  sub     rcx, [r8]
0x14003af98  imul    rax, rcx, 3E8h
0x14003af9f  cqo
0x14003afa1  idiv    qword ptr [r8+8]
0x14003afa5  mov     [rsp+58h+Timeout], rax
0x14003afaa  call    McTemplateK0px_EtwWriteTransfer
0x14003afaf  mov     rcx, rbp; StreamPointer
0x14003afb2  call    cs:__imp_KsStreamPointerDelete
0x14003afb9  nop     dword ptr [rax+rax+00h]
0x14003afbe  lock dec dword ptr [rdi+30h]
0x14003afc2  mov     rbp, r14
0x14003afc5  test    r14, r14
0x14003afc8  jnz     short loc_14003AF71
0x14003afca  jmp     short loc_14003AFD1
0x14003afcc  cmp     eax, 1
0x14003afcf  jnz     short loc_14003AFD9
0x14003afd1  xor     eax, eax
0x14003afd3  xchg    eax, [rdi+0F4h]
0x14003afd9  mov     rcx, rsi; Object
0x14003afdc  call    cs:__imp_KsReleaseControl
0x14003afe3  nop     dword ptr [rax+rax+00h]
0x14003afe8  mov     rbx, [rsp+58h+arg_8]
0x14003afed  mov     rbp, [rsp+58h+arg_10]
0x14003aff2  add     rsp, 40h
0x14003aff6  pop     r14
0x14003aff8  pop     rdi
0x14003aff9  pop     rsi
0x14003affa  retn
```
