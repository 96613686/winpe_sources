# A2DP_Device::RequestStreamOpen(void)

- ea: `0x140032f78`
- end: `0x140033260`
- name: `?RequestStreamOpen@A2DP_Device@@QEAAXXZ`
- size: `744`
- prototype: `void __fastcall(A2DP_Device *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140083af4`

## callees

- `0x140003530`
- `0x1400077e0`
- `0x140010628`
- `0x140030be0`
- `0x140032f78`
- `0x140035678`
- `0x140035868`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14003310a`
- `ntoskrnl!KeResetEvent` at `0x14003310a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003304d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003311c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003315b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003304d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003311c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003315b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003302c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003312b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003302c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003312b`
- `ntoskrnl!KeCancelTimer` at `0x1400330f7`
- `ntoskrnl!KeCancelTimer` at `0x1400330f7`
- `HAL!KeQueryPerformanceCounter` at `0x140033013`
- `HAL!KeQueryPerformanceCounter` at `0x140033069`
- `HAL!KeQueryPerformanceCounter` at `0x1400331b7`
- `HAL!KeQueryPerformanceCounter` at `0x140033013`
- `HAL!KeQueryPerformanceCounter` at `0x140033069`
- `HAL!KeQueryPerformanceCounter` at `0x1400331b7`

## pseudocode

```c
void __fastcall A2DP_Device::RequestStreamOpen(A2DP_Device *this)
{
  char v2; // bp
  bool v3; // dl
  LARGE_INTEGER PerformanceCounter; // rbx
  KIRQL v5; // al
  KIRQL v6; // r14
  LARGE_INTEGER v7; // rax
  int v8; // r8d
  PDEVICE_OBJECT v9; // r10
  LONGLONG v10; // rdx
  KIRQL v11; // al
  __int64 v12; // r14
  KIRQL v13; // r15
  __int64 v14; // r8
  int v15; // edi
  LARGE_INTEGER v16; // rax
  __int16 v17; // [rsp+30h] [rbp-58h]
  int v18; // [rsp+40h] [rbp-48h]
  char v19; // [rsp+48h] [rbp-40h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+90h] [rbp+8h] BYREF

  PerformanceFrequency.QuadPart = 0;
  v2 = 1;
  v3 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      83,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)this);
  A2DP_Device::EnterActiveACLMode(this);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 87);
  v6 = v5;
  if ( *((_BYTE *)this + 817) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)this + 87, v5);
    A2DP_Device::WaitForOpenComplete((KSPIN_LOCK *)this);
    v7 = KeQueryPerformanceCounter(&PerformanceFrequency);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v2 = 0;
    }
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = (char)this;
      v10 = 1000 * (v7.QuadPart - PerformanceCounter.QuadPart) % PerformanceFrequency.QuadPart;
      v18 = 1000 * (v7.QuadPart - PerformanceCounter.QuadPart) / PerformanceFrequency.QuadPart;
      v17 = 84;
LABEL_30:
      LOBYTE(v10) = v2;
      WPP_RECORDER_AND_TRACE_SF_dq(
        v9->AttachedDevice,
        v10,
        v8,
        v9->DeviceExtension,
        4,
        5,
        v17,
        (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
        v18,
        v19);
    }
  }
  else
  {
    *((_BYTE *)this + 817) = 1;
    KeCancelTimer((PKTIMER)((char *)this + 3016));
    KeResetEvent((PRKEVENT)this + 32);
    KeReleaseSpinLock((PKSPIN_LOCK)this + 87, v6);
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 87);
    v12 = *((_QWORD *)this + 50);
    v13 = v11;
    if ( v12 )
      (*((void (__fastcall **)(_QWORD))this + 53))(*((_QWORD *)this + 50));
    KeReleaseSpinLock((PKSPIN_LOCK)this + 87, v13);
    if ( v12
      && (A2DP_Device::SetLastAvdtpActivity(this, 9, v14),
          v15 = (*((__int64 (__fastcall **)(__int64))this + 62))(v12),
          (*((void (__fastcall **)(__int64))this + 54))(v12),
          v15 >= 0) )
    {
      A2DP_Device::WaitForOpenComplete((KSPIN_LOCK *)this);
    }
    else
    {
      A2DP_Device::SetOpenCompleteEvent(this);
    }
    v16 = KeQueryPerformanceCounter(&PerformanceFrequency);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v2 = 0;
    }
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = (char)this;
      v10 = 1000 * (v16.QuadPart - PerformanceCounter.QuadPart) % PerformanceFrequency.QuadPart;
      v18 = 1000 * (v16.QuadPart - PerformanceCounter.QuadPart) / PerformanceFrequency.QuadPart;
      v17 = 85;
      goto LABEL_30;
    }
  }
}

```

## disassembly

```asm
0x140032f78  mov     rax, rsp
0x140032f7b  push    rbx
0x140032f7c  push    rbp
0x140032f7d  push    rsi
0x140032f7e  push    rdi
0x140032f7f  push    r14
0x140032f81  push    r15
0x140032f83  sub     rsp, 58h
0x140032f87  mov     rsi, rcx
0x140032f8a  mov     qword ptr [rax+8], 0
0x140032f92  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f99  lea     r15, WPP_GLOBAL_Control
0x140032fa0  mov     bpl, 1
0x140032fa3  cmp     rcx, r15
0x140032fa6  jz      short loc_140032FBA
0x140032fa8  mov     eax, [rcx+2Ch]
0x140032fab  test    al, 10h
0x140032fad  jz      short loc_140032FBA
0x140032faf  cmp     byte ptr [rcx+29h], 4
0x140032fb3  jb      short loc_140032FBA
0x140032fb5  mov     dl, bpl
0x140032fb8  jmp     short loc_140032FBC
0x140032fba  xor     dl, dl
0x140032fbc  lea     rax, WPP_RECORDER_INITIALIZED
0x140032fc3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032fca  lea     r9, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x140032fd1  setnz   r8b
0x140032fd5  test    dl, dl
0x140032fd7  jnz     short loc_140032FDE
0x140032fd9  test    r8b, r8b
0x140032fdc  jz      short loc_140033009
0x140032fde  mov     [rsp+88h+var_48], rsi
0x140032fe3  mov     [rsp+88h+var_50], r9
0x140032fe8  mov     r9, [rcx+40h]
0x140032fec  mov     rcx, [rcx+18h]
0x140032ff0  mov     [rsp+88h+var_58], 53h ; 'S'
0x140032ff7  mov     [rsp+88h+var_60], 5
0x140032fff  mov     [rsp+88h+var_68], 4
0x140033004  call    WPP_RECORDER_AND_TRACE_SF_q
0x140033009  mov     rcx, rsi; this
0x14003300c  call    ?EnterActiveACLMode@A2DP_Device@@AEAAXXZ; A2DP_Device::EnterActiveACLMode(void)
0x140033011  xor     ecx, ecx; PerformanceFrequency
0x140033013  call    cs:__imp_KeQueryPerformanceCounter
0x14003301a  nop     dword ptr [rax+rax+00h]
0x14003301f  lea     rdi, [rsi+2B8h]
0x140033026  mov     rbx, rax
0x140033029  mov     rcx, rdi; SpinLock
0x14003302c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140033033  nop     dword ptr [rax+rax+00h]
0x140033038  cmp     byte ptr [rsi+331h], 0
0x14003303f  mov     r14b, al
0x140033042  jz      loc_1400330E9
0x140033048  mov     dl, al; NewIrql
0x14003304a  mov     rcx, rdi; SpinLock
0x14003304d  call    cs:__imp_KeReleaseSpinLock
0x140033054  nop     dword ptr [rax+rax+00h]
0x140033059  mov     rcx, rsi; this
0x14003305c  call    ?WaitForOpenComplete@A2DP_Device@@AEAAJXZ; A2DP_Device::WaitForOpenComplete(void)
0x140033061  lea     rcx, [rsp+88h+PerformanceFrequency]; PerformanceFrequency
0x140033069  call    cs:__imp_KeQueryPerformanceCounter
0x140033070  nop     dword ptr [rax+rax+00h]
0x140033075  mov     r10, cs:WPP_GLOBAL_Control
0x14003307c  cmp     r10, r15
0x14003307f  jz      short loc_140033091
0x140033081  mov     ecx, [r10+2Ch]
0x140033085  test    cl, 10h
0x140033088  jz      short loc_140033091
0x14003308a  cmp     byte ptr [r10+29h], 4
0x14003308f  jnb     short loc_140033094
0x140033091  xor     bpl, bpl
0x140033094  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003309b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400330a2  setnz   r8b
0x1400330a6  test    bpl, bpl
0x1400330a9  jnz     short loc_1400330B4
0x1400330ab  test    r8b, r8b
0x1400330ae  jz      loc_140033252
0x1400330b4  sub     rax, rbx
0x1400330b7  mov     qword ptr [rsp+88h+var_40], rsi
0x1400330bc  imul    rax, 3E8h
0x1400330c3  cqo
0x1400330c5  idiv    qword ptr [rsp+88h+PerformanceFrequency]
0x1400330cd  mov     dword ptr [rsp+88h+var_48], eax
0x1400330d1  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x1400330d8  mov     [rsp+88h+var_50], rax
0x1400330dd  mov     [rsp+88h+var_58], 54h ; 'T'
0x1400330e4  jmp     loc_140033235
0x1400330e9  lea     rcx, [rsi+0BC8h]; PKTIMER
0x1400330f0  mov     [rsi+331h], bpl
0x1400330f7  call    cs:__imp_KeCancelTimer
0x1400330fe  nop     dword ptr [rax+rax+00h]
0x140033103  lea     rcx, [rsi+300h]; Event
0x14003310a  call    cs:__imp_KeResetEvent
0x140033111  nop     dword ptr [rax+rax+00h]
0x140033116  mov     dl, r14b; NewIrql
0x140033119  mov     rcx, rdi; SpinLock
0x14003311c  call    cs:__imp_KeReleaseSpinLock
0x140033123  nop     dword ptr [rax+rax+00h]
0x140033128  mov     rcx, rdi; SpinLock
0x14003312b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140033132  nop     dword ptr [rax+rax+00h]
0x140033137  mov     r14, [rsi+190h]
0x14003313e  mov     r15b, al
0x140033141  test    r14, r14
0x140033144  jz      short loc_140033155
0x140033146  mov     rax, [rsi+1A8h]
0x14003314d  mov     rcx, r14
0x140033150  call    _guard_dispatch_icall
0x140033155  mov     dl, r15b; NewIrql
0x140033158  mov     rcx, rdi; SpinLock
0x14003315b  call    cs:__imp_KeReleaseSpinLock
0x140033162  nop     dword ptr [rax+rax+00h]
0x140033167  test    r14, r14
0x14003316a  jz      short loc_1400331A7
0x14003316c  mov     edx, 9
0x140033171  mov     rcx, rsi
0x140033174  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x140033179  mov     rax, [rsi+1F0h]
0x140033180  mov     rcx, r14
0x140033183  call    _guard_dispatch_icall
0x140033188  mov     edi, eax
0x14003318a  mov     rcx, r14
0x14003318d  mov     rax, [rsi+1B0h]
0x140033194  call    _guard_dispatch_icall
0x140033199  test    edi, edi
0x14003319b  js      short loc_1400331A7
0x14003319d  mov     rcx, rsi; this
0x1400331a0  call    ?WaitForOpenComplete@A2DP_Device@@AEAAJXZ; A2DP_Device::WaitForOpenComplete(void)
0x1400331a5  jmp     short loc_1400331AF
0x1400331a7  mov     rcx, rsi; this
0x1400331aa  call    ?SetOpenCompleteEvent@A2DP_Device@@AEAAXXZ; A2DP_Device::SetOpenCompleteEvent(void)
0x1400331af  lea     rcx, [rsp+88h+PerformanceFrequency]; PerformanceFrequency
0x1400331b7  call    cs:__imp_KeQueryPerformanceCounter
0x1400331be  nop     dword ptr [rax+rax+00h]
0x1400331c3  mov     r10, cs:WPP_GLOBAL_Control
0x1400331ca  lea     rcx, WPP_GLOBAL_Control
0x1400331d1  cmp     r10, rcx
0x1400331d4  jz      short loc_1400331E6
0x1400331d6  mov     ecx, [r10+2Ch]
0x1400331da  test    cl, 10h
0x1400331dd  jz      short loc_1400331E6
0x1400331df  cmp     byte ptr [r10+29h], 4
0x1400331e4  jnb     short loc_1400331E9
0x1400331e6  xor     bpl, bpl
0x1400331e9  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400331f0  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400331f7  setnz   r8b
0x1400331fb  test    bpl, bpl
0x1400331fe  jnz     short loc_140033205
0x140033200  test    r8b, r8b
0x140033203  jz      short loc_140033252
0x140033205  sub     rax, rbx
0x140033208  mov     qword ptr [rsp+88h+var_40], rsi
0x14003320d  imul    rax, 3E8h
0x140033214  cqo
0x140033216  idiv    qword ptr [rsp+88h+PerformanceFrequency]
0x14003321e  mov     dword ptr [rsp+88h+var_48], eax
0x140033222  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x140033229  mov     [rsp+88h+var_50], rax
0x14003322e  mov     [rsp+88h+var_58], 55h ; 'U'
0x140033235  mov     r9, [r10+40h]
0x140033239  mov     dl, bpl
0x14003323c  mov     rcx, [r10+18h]
0x140033240  mov     [rsp+88h+var_60], 5
0x140033248  mov     [rsp+88h+var_68], 4
0x14003324d  call    WPP_RECORDER_AND_TRACE_SF_dq
0x140033252  add     rsp, 58h
0x140033256  pop     r15
0x140033258  pop     r14
0x14003325a  pop     rdi
0x14003325b  pop     rsi
0x14003325c  pop     rbp
0x14003325d  pop     rbx
0x14003325e  retn
```
