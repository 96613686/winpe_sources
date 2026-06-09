# A2DP_Device::BeginAVDTPShutdown(void)

- ea: `0x140030740`
- end: `0x140030912`
- name: `?BeginAVDTPShutdown@A2DP_Device@@AEAAJXZ`
- size: `466`
- prototype: `__int64 __fastcall(A2DP_Device *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140033e10`

## callees

- `0x140003530`
- `0x140012a5c`
- `0x14001ea8c`
- `0x14001ed2c`
- `0x14002d890`
- `0x140030740`
- `0x140032d7c`
- `0x1400355fc`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140030891`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400308c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030891`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400308c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003085d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400308a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003085d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400308a8`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x140030878`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x140030878`

## pseudocode

```c
__int64 __fastcall A2DP_Device::BeginAVDTPShutdown(A2DP_Device *this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // ebp
  int v6; // edx
  int v7; // r8d
  KIRQL v8; // si
  KIRQL v9; // al
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64); // rax

  v5 = 0;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
  {
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qi(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        51,
        (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
        *((_QWORD *)this + 50),
        (char)this);
    }
  }
  else
  {
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        52,
        (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
        (char)this);
    }
  }
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 87);
  if ( *((_QWORD *)this + 410) )
  {
    SleepstudyHelper_UnregisterComponent();
    *((_QWORD *)this + 410) = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)this + 87, v8);
  A2DP_Device::RequestStreamClose(this);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 87);
  v10 = *((_QWORD *)this + 50);
  *((_QWORD *)this + 50) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)this + 87, v9);
  if ( v10 )
  {
    v11 = (__int64 (__fastcall *)(__int64))*((_QWORD *)this + 58);
    if ( v11 )
      v5 = v11(v10);
  }
  A2DP_Device::UnregisterMpm(this);
  A2DP_Device::SetCloseCompleteEvent(this);
  A2DP_Device::SetDisconnectCompleteEvent(this);
  return v5;
}

```

## disassembly

```asm
0x140030740  push    rbx
0x140030742  push    rbp
0x140030743  push    rsi
0x140030744  push    rdi
0x140030745  sub     rsp, 58h
0x140030749  mov     rbx, rcx
0x14003074c  xor     ebp, ebp
0x14003074e  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140030753  test    eax, eax
0x140030755  jz      loc_1400307E0
0x14003075b  mov     rcx, cs:WPP_GLOBAL_Control
0x140030762  lea     rax, WPP_GLOBAL_Control
0x140030769  cmp     rcx, rax
0x14003076c  jz      short loc_14003077F
0x14003076e  mov     eax, [rcx+2Ch]
0x140030771  test    al, 10h
0x140030773  jz      short loc_14003077F
0x140030775  cmp     byte ptr [rcx+29h], 4
0x140030779  jb      short loc_14003077F
0x14003077b  mov     dl, 1
0x14003077d  jmp     short loc_140030781
0x14003077f  xor     dl, dl
0x140030781  lea     rax, WPP_RECORDER_INITIALIZED
0x140030788  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003078f  setnz   r8b
0x140030793  test    dl, dl
0x140030795  jnz     short loc_1400307A0
0x140030797  test    r8b, r8b
0x14003079a  jz      loc_140030853
0x1400307a0  mov     rax, [rbx+190h]
0x1400307a7  mov     r9, [rcx+40h]
0x1400307ab  mov     rcx, [rcx+18h]
0x1400307af  mov     [rsp+78h+var_30], rbx
0x1400307b4  mov     [rsp+78h+var_38], rax
0x1400307b9  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x1400307c0  mov     [rsp+78h+var_40], rax
0x1400307c5  mov     [rsp+78h+var_48], 33h ; '3'
0x1400307cc  mov     [rsp+78h+var_50], 5
0x1400307d4  mov     [rsp+78h+var_58], 4
0x1400307d9  call    WPP_RECORDER_AND_TRACE_SF_qi
0x1400307de  jmp     short loc_140030853
0x1400307e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307e7  lea     rax, WPP_GLOBAL_Control
0x1400307ee  cmp     rcx, rax
0x1400307f1  jz      short loc_140030804
0x1400307f3  mov     eax, [rcx+2Ch]
0x1400307f6  test    al, 10h
0x1400307f8  jz      short loc_140030804
0x1400307fa  cmp     byte ptr [rcx+29h], 4
0x1400307fe  jb      short loc_140030804
0x140030800  mov     dl, 1
0x140030802  jmp     short loc_140030806
0x140030804  xor     dl, dl
0x140030806  lea     rax, WPP_RECORDER_INITIALIZED
0x14003080d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140030814  setnz   r8b
0x140030818  test    dl, dl
0x14003081a  jnz     short loc_140030821
0x14003081c  test    r8b, r8b
0x14003081f  jz      short loc_140030853
0x140030821  mov     r9, [rcx+40h]
0x140030825  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14003082c  mov     rcx, [rcx+18h]
0x140030830  mov     [rsp+78h+var_38], rbx
0x140030835  mov     [rsp+78h+var_40], rax
0x14003083a  mov     [rsp+78h+var_48], 34h ; '4'
0x140030841  mov     [rsp+78h+var_50], 5
0x140030849  mov     [rsp+78h+var_58], 4
0x14003084e  call    WPP_RECORDER_AND_TRACE_SF_q
0x140030853  lea     rdi, [rbx+2B8h]
0x14003085a  mov     rcx, rdi; SpinLock
0x14003085d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030864  nop     dword ptr [rax+rax+00h]
0x140030869  mov     rcx, [rbx+0CD0h]
0x140030870  mov     sil, al
0x140030873  test    rcx, rcx
0x140030876  jz      short loc_14003088B
0x140030878  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x14003087f  nop     dword ptr [rax+rax+00h]
0x140030884  mov     [rbx+0CD0h], rbp
0x14003088b  mov     dl, sil; NewIrql
0x14003088e  mov     rcx, rdi; SpinLock
0x140030891  call    cs:__imp_KeReleaseSpinLock
0x140030898  nop     dword ptr [rax+rax+00h]
0x14003089d  mov     rcx, rbx; this
0x1400308a0  call    ?RequestStreamClose@A2DP_Device@@QEAAXXZ; A2DP_Device::RequestStreamClose(void)
0x1400308a5  mov     rcx, rdi; SpinLock
0x1400308a8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400308af  nop     dword ptr [rax+rax+00h]
0x1400308b4  mov     rsi, [rbx+190h]
0x1400308bb  mov     rcx, rdi; SpinLock
0x1400308be  mov     dl, al; NewIrql
0x1400308c0  mov     [rbx+190h], rbp
0x1400308c7  call    cs:__imp_KeReleaseSpinLock
0x1400308ce  nop     dword ptr [rax+rax+00h]
0x1400308d3  test    rsi, rsi
0x1400308d6  jz      short loc_1400308EE
0x1400308d8  mov     rax, [rbx+1D0h]
0x1400308df  test    rax, rax
0x1400308e2  jz      short loc_1400308EE
0x1400308e4  mov     rcx, rsi
0x1400308e7  call    _guard_dispatch_icall
0x1400308ec  mov     ebp, eax
0x1400308ee  mov     rcx, rbx; this
0x1400308f1  call    ?UnregisterMpm@A2DP_Device@@QEAAXXZ; A2DP_Device::UnregisterMpm(void)
0x1400308f6  mov     rcx, rbx; this
0x1400308f9  call    ?SetCloseCompleteEvent@A2DP_Device@@AEAAXXZ; A2DP_Device::SetCloseCompleteEvent(void)
0x1400308fe  mov     rcx, rbx; this
0x140030901  call    ?SetDisconnectCompleteEvent@A2DP_Device@@AEAAXXZ; A2DP_Device::SetDisconnectCompleteEvent(void)
0x140030906  mov     eax, ebp
0x140030908  add     rsp, 58h
0x14003090c  pop     rdi
0x14003090d  pop     rsi
0x14003090e  pop     rbp
0x14003090f  pop     rbx
0x140030910  retn
```
