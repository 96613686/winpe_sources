# CPcmPin::Pump(bool)

- ea: `0x140003cc0`
- end: `0x140004396`
- name: `?Pump@CPcmPin@@AEAAX_N@Z`
- size: `1750`
- prototype: `void __fastcall(CPcmPin *this, char)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400030d0`
- `0x140003a20`

## callees

- `0x140002ea0`
- `0x140003cc0`
- `0x1400043a0`
- `0x140004720`
- `0x140004ac0`
- `0x140005060`
- `0x140005800`
- `0x140006380`
- `0x140006410`
- `0x14001bed0`
- `0x14001bf6c`
- `0x140034c2c`
- `0x14003abdc`
- `0x14003b29c`
- `0x14003b3dc`
- `0x14003b444`
- `0x14003b5ec`
- `0x14005c7d0`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExSetTimer` at `0x140004021`
- `ntoskrnl!ExSetTimer` at `0x140004021`
- `ntoskrnl!KeClearEvent` at `0x14000431f`
- `ntoskrnl!KeClearEvent` at `0x14000431f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004056`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004056`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d59`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003f69`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d59`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003f69`
- `ntoskrnl!KeSetEvent` at `0x140003f0a`
- `ntoskrnl!KeSetEvent` at `0x1400042b8`
- `ntoskrnl!KeSetEvent` at `0x140003f0a`
- `ntoskrnl!KeSetEvent` at `0x1400042b8`
- `HAL!KeQueryPerformanceCounter` at `0x140003d20`
- `HAL!KeQueryPerformanceCounter` at `0x140003d20`
- `ks!KsPinReleaseProcessingMutex` at `0x140003ec6`
- `ks!KsPinReleaseProcessingMutex` at `0x140003ec6`
- `ks!KsPinAcquireProcessingMutex` at `0x140003d00`
- `ks!KsPinAcquireProcessingMutex` at `0x140003d00`
- `ks!KsPinAttemptProcessing` at `0x140003ed8`
- `ks!KsPinAttemptProcessing` at `0x140003ed8`

## pseudocode

```c
void __fastcall CPcmPin::Pump(CPcmPin *this, char a2)
{
  _QWORD **v4; // rdi
  KSPIN_LOCK *v5; // rbp
  KIRQL v6; // al
  __int64 v7; // r8
  KIRQL v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int128 v11; // rtt
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  bool v15; // di
  unsigned __int64 v16; // rdi
  utl::_RefCountBase *v17; // rcx
  unsigned __int64 updated; // rbp
  int v19; // r8d
  __int64 v20; // rax
  bool v21; // r10
  __int64 v22; // rcx
  __int64 v23; // r8
  KIRQL v24; // r15
  unsigned __int32 v25; // esi
  __int64 v26; // rcx
  char v27; // dl
  char v28; // bp
  bool v29; // al
  __int64 v30; // rcx
  unsigned __int8 v31; // al
  __int64 v32; // rcx
  __int64 v33; // r8
  int v34; // edi
  unsigned __int64 v35; // rax
  __int64 v36; // r9
  __int64 v37; // rcx
  int v38; // [rsp+20h] [rbp-C8h]
  int v39; // [rsp+28h] [rbp-C0h]
  int v40; // [rsp+30h] [rbp-B8h]
  __int64 v41; // [rsp+30h] [rbp-B8h]
  int v42; // [rsp+38h] [rbp-B0h]
  __int64 QuadPart; // [rsp+80h] [rbp-68h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+88h] [rbp-60h] BYREF
  _BYTE v45[16]; // [rsp+90h] [rbp-58h] BYREF
  KSPIN_LOCK *v46; // [rsp+A0h] [rbp-48h] BYREF
  utl::_RefCountBase *v47; // [rsp+A8h] [rbp-40h]

  KsPinAcquireProcessingMutex(*((PKSPIN *)this + 2));
  PerformanceFrequency.QuadPart = 0;
  QuadPart = KeQueryPerformanceCounter(&PerformanceFrequency).QuadPart;
  v4 = (_QWORD **)lambda_84b293e5b2e8a59c6b3d0ec58252e409_::_lambda_84b293e5b2e8a59c6b3d0ec58252e409_(
                    v45,
                    this,
                    &QuadPart);
  v5 = *v4 + 10;
  v6 = KeAcquireSpinLockRaiseToDpc(v5);
  v7 = (__int64)*v4;
  v8 = v6;
  v9 = (*v4)[13];
  v10 = (*v4)[18];
  if ( v9 )
  {
    v11 = *(int *)(v7 + 52) * (*v4[1] - v9);
    v9 = *(int *)(v7 + 52) * (*v4[1] - v9) % *(_QWORD *)(v7 + 112);
    v12 = *(_QWORD *)(v7 + 96) + v11 / *(__int64 *)(v7 + 112);
  }
  else
  {
    v12 = (*v4)[18];
  }
  v13 = 0;
  if ( v12 > 0 )
    v13 = v12;
  v14 = *(_QWORD *)(v7 + 56);
  if ( v13 < v14 )
    v14 = v13;
  if ( v14 > v10 )
    v10 = v14;
  *(_QWORD *)(v7 + 144) = v10;
  if ( v5 )
  {
    v46 = v5;
    LOBYTE(v47) = v8;
    wil::details::kspin_lock_saved_irql::Release((const struct wil::details::kspin_lock_saved_irql *)&v46);
  }
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
  {
    McTemplateK0xxxx_EtwWriteTransfer(
      v14,
      v9,
      v7,
      *((_QWORD *)this + 7),
      *((_QWORD *)this + 8),
      *((_QWORD *)this + 9),
      v10);
    if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
    {
      v36 = *((int *)this + 13);
      v37 = *((_QWORD *)this + 7) - *((_QWORD *)this + 8);
      v41 = 1000000LL * (*((_QWORD *)this + 8) - *((_QWORD *)this + 9)) / v36;
      McTemplateK0xxiii_EtwWriteTransfer(
        v37,
        1000000 * v37 % v36,
        v41,
        v36,
        *((_QWORD *)this + 7),
        1000000 * v37 / v36,
        v41,
        1000000 * (*((_QWORD *)this + 9) - v10) / v36);
    }
  }
  v15 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
     && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_liiiiidi(
      WPP_GLOBAL_Control->AttachedDevice,
      v15,
      v7,
      WPP_GLOBAL_Control->DeviceExtension,
      v38,
      v39,
      v40,
      v42,
      a2,
      1000 * QuadPart / PerformanceFrequency.QuadPart,
      v10,
      *((_QWORD *)this + 9),
      *((_QWORD *)this + 8),
      *((_QWORD *)this + 7),
      *((_DWORD *)this + 12),
      *((_QWORD *)this + 15));
  }
  v16 = CPcmPin::ProcessCloneStreamPointersToComplete(this, v10, QuadPart);
  updated = CPcmPin::UpdateL2capOverflowedCondition(this);
  if ( updated )
  {
    A2dpRole::GetCurrentSelectedCodec(*(_QWORD *)(*((_QWORD *)this + 4) + 8LL), &v46);
    if ( v46 )
      (*(void (__fastcall **)(KSPIN_LOCK *, unsigned __int64))(*v46 + 168))(v46, updated);
    v17 = v47;
    if ( v47 )
      utl::_RefCountBase::_DecStrong(v47);
  }
  if ( a2 )
    CPcmPin::ProcessCloneStreamPointersToSubmit(this);
  v20 = *((_QWORD *)this + 7);
  if ( v20 > v10 )
  {
    v17 = (utl::_RefCountBase *)*((int *)this + 13);
    v35 = 10000000 * (v20 - v10) / (__int64)v17;
    if ( v16 >= v35 )
      v16 = v35;
  }
  if ( *((_QWORD *)this + 9) == *((_QWORD *)this + 8) )
    KeSetEvent((PRKEVENT)this + 12, 0, 0);
  if ( v10 == *((_QWORD *)this + 7) )
    KeSetEvent((PRKEVENT)this + 13, 0, 0);
  if ( v16 != -1 )
  {
    v21 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
               && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( v21 || (_BYTE)v19 )
      WPP_RECORDER_AND_TRACE_SF_i(
        WPP_GLOBAL_Control->AttachedDevice,
        v21,
        v19,
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        v39,
        56,
        v42,
        v16 / 0x2710);
    v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 31);
    if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 2) != 0 )
      McTemplateK0i_EtwWriteTransfer(
        v22,
        (__int64)((unsigned __int128)((__int64)v16 * (__int128)0x346DC5D63886594BLL) >> 64) >> 11,
        v23,
        (__int64)v16 / 10000);
    v25 = _InterlockedIncrement((volatile signed __int32 *)this + 84);
    if ( v25 == 1 )
      KeClearEvent((PRKEVENT)this + 11);
    v26 = *((_QWORD *)this + 4);
    if ( v26 )
    {
      v27 = _InterlockedIncrement((volatile signed __int32 *)(v26 + 2760));
      v28 = _InterlockedIncrement((volatile signed __int32 *)(v26 + 3448));
      v29 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                 && LOWORD(WPP_GLOBAL_Control->DeviceType);
      if ( v29 || (_BYTE)v23 )
        WPP_RECORDER_AND_TRACE_SF_dsddq(
          WPP_GLOBAL_Control->AttachedDevice,
          v29,
          v23,
          WPP_GLOBAL_Control->DeviceExtension,
          v38,
          v39,
          46,
          v42,
          v27,
          (__int64)"LockTimerDpc",
          9,
          v28,
          v26);
    }
    v30 = *((_QWORD *)this + 32);
    v46 = 0;
    v47 = (utl::_RefCountBase *)20000;
    v31 = ExSetTimer(v30, -(__int64)v16, 0, &v46);
    v34 = v31;
    if ( v31 )
      v25 = CPcmPin::UnlockTimerDpc(this);
    if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 2) != 0 )
      McTemplateK0qq_EtwWriteTransfer(v32, SetTimerStop, v33, v25, v34);
    KeReleaseSpinLock((PKSPIN_LOCK)this + 31, v24);
  }
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v17, PumpStop);
  KsPinReleaseProcessingMutex(*((PKSPIN *)this + 2));
  KsPinAttemptProcessing(*((PKSPIN *)this + 2), 1u);
}

```

## disassembly

```asm
0x140003cc0  mov     r11, rsp
0x140003cc3  push    rbx
0x140003cc4  sub     rsp, 0E0h
0x140003ccb  mov     rax, cs:__security_cookie
0x140003cd2  xor     rax, rsp
0x140003cd5  mov     [rsp+0E8h+var_38], rax
0x140003cdd  mov     [r11+10h], rbp
0x140003ce1  mov     rbx, rcx
0x140003ce4  mov     rcx, [rcx+10h]; Pin
0x140003ce8  mov     [r11+18h], rsi
0x140003cec  mov     [r11+20h], rdi
0x140003cf0  mov     [r11-10h], r12
0x140003cf4  mov     [r11-18h], r13
0x140003cf8  mov     [r11-20h], r14
0x140003cfc  movzx   r14d, dl
0x140003d00  call    cs:__imp_KsPinAcquireProcessingMutex
0x140003d07  nop     dword ptr [rax+rax+00h]
0x140003d0c  lea     rcx, [rsp+0E8h+PerformanceFrequency]; PerformanceFrequency
0x140003d14  mov     qword ptr [rsp+0E8h+PerformanceFrequency], 0
0x140003d20  call    cs:__imp_KeQueryPerformanceCounter
0x140003d27  nop     dword ptr [rax+rax+00h]
0x140003d2c  lea     r8, [rsp+0E8h+var_68]
0x140003d34  mov     rdx, rbx
0x140003d37  lea     rcx, [rsp+0E8h+var_58]
0x140003d3f  mov     [rsp+0E8h+var_68], rax
0x140003d47  call    _lambda_84b293e5b2e8a59c6b3d0ec58252e409____lambda_84b293e5b2e8a59c6b3d0ec58252e409_
0x140003d4c  mov     rdi, rax
0x140003d4f  mov     rbp, [rax]
0x140003d52  add     rbp, 50h ; 'P'
0x140003d56  mov     rcx, rbp; SpinLock
0x140003d59  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003d60  nop     dword ptr [rax+rax+00h]
0x140003d65  mov     r8, [rdi]
0x140003d68  movzx   r9d, al
0x140003d6c  mov     rdx, [r8+68h]
0x140003d70  mov     rsi, [r8+90h]
0x140003d77  test    rdx, rdx
0x140003d7a  jz      loc_14000427D
0x140003d80  mov     rcx, [rdi+8]
0x140003d84  mov     rax, [rcx]
0x140003d87  movsxd  rcx, dword ptr [r8+34h]
0x140003d8b  sub     rax, rdx
0x140003d8e  imul    rax, rcx
0x140003d92  cqo
0x140003d94  idiv    qword ptr [r8+70h]
0x140003d98  mov     rcx, rax
0x140003d9b  add     rcx, [r8+60h]
0x140003d9f  xor     eax, eax
0x140003da1  test    rcx, rcx
0x140003da4  cmovg   rax, rcx
0x140003da8  mov     rcx, [r8+38h]
0x140003dac  cmp     rax, rcx
0x140003daf  cmovl   rcx, rax
0x140003db3  cmp     rcx, rsi
0x140003db6  cmovg   rsi, rcx
0x140003dba  mov     [r8+90h], rsi
0x140003dc1  test    rbp, rbp
0x140003dc4  jnz     loc_14000406F
0x140003dca  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 1
0x140003dd1  jnz     loc_1400041A9
0x140003dd7  mov     r11, cs:WPP_GLOBAL_Control
0x140003dde  lea     r12, WPP_GLOBAL_Control
0x140003de5  cmp     r11, r12
0x140003de8  jz      short loc_140003DF8
0x140003dea  test    dword ptr [r11+2Ch], 2000h
0x140003df2  jnz     loc_140004285
0x140003df8  xor     dil, dil
0x140003dfb  lea     r13, WPP_RECORDER_INITIALIZED
0x140003e02  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140003e09  setnz   r8b
0x140003e0d  test    dil, dil
0x140003e10  jnz     loc_1400040FC
0x140003e16  test    r8b, r8b
0x140003e19  jnz     loc_1400040FC
0x140003e1f  mov     r8, [rsp+0E8h+var_68]; __int64
0x140003e27  mov     rdx, rsi; __int64
0x140003e2a  mov     rcx, rbx; this
0x140003e2d  call    ?ProcessCloneStreamPointersToComplete@CPcmPin@@AEAA_K_J0@Z; CPcmPin::ProcessCloneStreamPointersToComplete(__int64,__int64)
0x140003e32  mov     rcx, rbx; this
0x140003e35  mov     rdi, rax
0x140003e38  call    ?UpdateL2capOverflowedCondition@CPcmPin@@AEAA_KXZ; CPcmPin::UpdateL2capOverflowedCondition(void)
0x140003e3d  mov     rbp, rax
0x140003e40  test    rax, rax
0x140003e43  jnz     loc_140004240
0x140003e49  test    r14b, r14b
0x140003e4c  jz      short loc_140003E56
0x140003e4e  mov     rcx, rbx; this
0x140003e51  call    ?ProcessCloneStreamPointersToSubmit@CPcmPin@@AEAAXXZ; CPcmPin::ProcessCloneStreamPointersToSubmit(void)
0x140003e56  mov     rax, [rbx+38h]
0x140003e5a  cmp     rax, rsi
0x140003e5d  jg      loc_1400040BE
0x140003e63  mov     rax, [rbx+40h]
0x140003e67  cmp     [rbx+48h], rax
0x140003e6b  jz      loc_140003EFE
0x140003e71  cmp     rsi, [rbx+38h]
0x140003e75  jz      loc_1400042AC
0x140003e7b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140003e7f  jb      loc_140003F1B
0x140003e85  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 1
0x140003e8c  mov     r14, [rsp+0E8h+var_20]
0x140003e94  mov     r13, [rsp+0E8h+var_18]
0x140003e9c  mov     r12, [rsp+0E8h+var_10]
0x140003ea4  mov     rdi, [rsp+0E8h+arg_18]
0x140003eac  mov     rsi, [rsp+0E8h+arg_10]
0x140003eb4  mov     rbp, [rsp+0E8h+arg_8]
0x140003ebc  jnz     loc_140004385
0x140003ec2  mov     rcx, [rbx+10h]; Pin
0x140003ec6  call    cs:__imp_KsPinReleaseProcessingMutex
0x140003ecd  nop     dword ptr [rax+rax+00h]
0x140003ed2  mov     rcx, [rbx+10h]; Pin
0x140003ed6  mov     dl, 1; Asynchronous
0x140003ed8  call    cs:__imp_KsPinAttemptProcessing
0x140003edf  nop     dword ptr [rax+rax+00h]
0x140003ee4  mov     rcx, [rsp+0E8h+var_38]
0x140003eec  xor     rcx, rsp; StackCookie
0x140003eef  call    __security_check_cookie
0x140003ef4  add     rsp, 0E0h
0x140003efb  pop     rbx
0x140003efc  retn
0x140003efe  lea     rcx, [rbx+120h]; Event
0x140003f05  xor     r8d, r8d; Wait
0x140003f08  xor     edx, edx; Increment
0x140003f0a  call    cs:__imp_KeSetEvent
0x140003f11  nop     dword ptr [rax+rax+00h]
0x140003f16  jmp     loc_140003E71
0x140003f1b  mov     [rsp+0E8h+var_28], r15
0x140003f23  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f2a  cmp     rcx, r12
0x140003f2d  jnz     loc_1400040DD
0x140003f33  xor     r10b, r10b
0x140003f36  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140003f3d  jnz     loc_140004164
0x140003f43  xor     r8b, r8b
0x140003f46  mov     rsi, 346DC5D63886594Bh
0x140003f50  test    r10b, r10b
0x140003f53  jnz     loc_1400042C9
0x140003f59  test    r8b, r8b
0x140003f5c  jnz     loc_1400042C9
0x140003f62  lea     rcx, [rbx+0F8h]; SpinLock
0x140003f69  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003f70  nop     dword ptr [rax+rax+00h]
0x140003f75  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 2
0x140003f7c  movzx   r15d, al
0x140003f80  jnz     loc_1400042FA
0x140003f86  mov     ebp, 1
0x140003f8b  mov     esi, ebp
0x140003f8d  lock xadd [rbx+150h], esi
0x140003f95  inc     esi
0x140003f97  cmp     esi, ebp
0x140003f99  jz      loc_140004318
0x140003f9f  mov     rcx, [rbx+20h]
0x140003fa3  test    rcx, rcx
0x140003fa6  jz      short loc_140003FF1
0x140003fa8  mov     edx, ebp
0x140003faa  lock xadd [rcx+0AC8h], edx
0x140003fb2  inc     edx
0x140003fb4  lock xadd [rcx+0D78h], ebp
0x140003fbc  inc     ebp
0x140003fbe  mov     r10, cs:WPP_GLOBAL_Control
0x140003fc5  cmp     r10, r12
0x140003fc8  jnz     loc_14000418B
0x140003fce  xor     al, al
0x140003fd0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140003fd7  jnz     loc_140004177
0x140003fdd  xor     r8b, r8b
0x140003fe0  test    al, al
0x140003fe2  jnz     loc_140004330
0x140003fe8  test    r8b, r8b
0x140003feb  jnz     loc_140004330
0x140003ff1  mov     rcx, [rbx+100h]
0x140003ff8  lea     r9, [rsp+0E8h+var_48]
0x140004000  neg     rdi
0x140004003  mov     [rsp+0E8h+var_48], 0
0x14000400f  mov     rdx, rdi
0x140004012  mov     [rsp+0E8h+var_40], 4E20h
0x14000401e  xor     r8d, r8d
0x140004021  call    cs:__imp_ExSetTimer
0x140004028  nop     dword ptr [rax+rax+00h]
0x14000402d  movzx   edi, al
0x140004030  test    al, al
0x140004032  jz      short loc_14000403E
0x140004034  mov     rcx, rbx; this
0x140004037  call    ?UnlockTimerDpc@CPcmPin@@AEAAJXZ; CPcmPin::UnlockTimerDpc(void)
0x14000403c  mov     esi, eax
0x14000403e  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 2
0x140004045  jnz     loc_14000436D
0x14000404b  movzx   edx, r15b; NewIrql
0x14000404f  lea     rcx, [rbx+0F8h]; SpinLock
0x140004056  call    cs:__imp_KeReleaseSpinLock
0x14000405d  nop     dword ptr [rax+rax+00h]
0x140004062  mov     r15, [rsp+0E8h+var_28]
0x14000406a  jmp     loc_140003E85
0x14000406f  mov     eax, dword ptr [rsp+0E8h+var_40+1]
0x140004076  lea     rcx, [rsp+0E8h+var_48]; struct wil::details::kspin_lock_saved_irql *
0x14000407e  mov     dword ptr [rsp+0E8h+var_40+1], eax
0x140004085  movzx   eax, word ptr [rsp+0E8h+var_40+5]
0x14000408d  mov     word ptr [rsp+0E8h+var_40+5], ax
0x140004095  movzx   eax, byte ptr [rsp+0E8h+var_40+7]
0x14000409d  mov     byte ptr [rsp+0E8h+var_40+7], al
0x1400040a4  mov     [rsp+0E8h+var_48], rbp
0x1400040ac  mov     byte ptr [rsp+0E8h+var_40], r9b
0x1400040b4  call    ?Release@kspin_lock_saved_irql@details@wil@@SAXAEBU123@@Z; wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &)
0x1400040b9  jmp     loc_140003DCA
0x1400040be  movsxd  rcx, dword ptr [rbx+34h]
0x1400040c2  sub     rax, rsi
0x1400040c5  imul    rax, 989680h
0x1400040cc  cqo
0x1400040ce  idiv    rcx
0x1400040d1  cmp     rdi, rax
0x1400040d4  cmovnb  rdi, rax
0x1400040d8  jmp     loc_140003E63
0x1400040dd  test    dword ptr [rcx+2Ch], 2000h
0x1400040e4  jz      loc_140003F33
0x1400040ea  cmp     byte ptr [rcx+29h], 5
0x1400040ee  jb      loc_140003F33
0x1400040f4  mov     r10b, 1
0x1400040f7  jmp     loc_140003F36
0x1400040fc  imul    rax, [rsp+0E8h+var_68], 3E8h
0x140004108  mov     rcx, [rbx+78h]
0x14000410c  mov     r9d, [rbx+30h]
0x140004110  cqo
0x140004112  idiv    qword ptr [rsp+0E8h+PerformanceFrequency]
0x14000411a  mov     [rsp+0E8h+var_70], rcx
0x14000411f  movzx   edx, dil
0x140004123  mov     rcx, [r11+18h]
0x140004127  mov     [rsp+0E8h+var_78], r9d
0x14000412c  mov     r9, [rbx+38h]
0x140004130  mov     [rsp+0E8h+var_80], r9
0x140004135  mov     r9, [rbx+40h]
0x140004139  mov     [rsp+0E8h+var_88], r9
0x14000413e  mov     r9, [rbx+48h]
0x140004142  mov     [rsp+0E8h+var_90], r9
0x140004147  mov     r9, [r11+40h]
0x14000414b  mov     [rsp+0E8h+var_98], rsi
0x140004150  mov     [rsp+0E8h+var_A0], rax
0x140004155  mov     dword ptr [rsp+0E8h+var_A8], r14d
0x14000415a  call    WPP_RECORDER_AND_TRACE_SF_liiiiidi
0x14000415f  jmp     loc_140003E1F
0x140004164  cmp     word ptr [rcx+48h], 0
0x140004169  jz      loc_140003F43
0x14000416f  mov     r8b, 1
0x140004172  jmp     loc_140003F46
0x140004177  cmp     word ptr [r10+48h], 0
0x14000417d  jz      loc_140003FDD
0x140004183  mov     r8b, 1
0x140004186  jmp     loc_140003FE0
0x14000418b  mov     eax, [r10+2Ch]
0x14000418f  test    al, 10h
0x140004191  jz      loc_140003FCE
0x140004197  cmp     byte ptr [r10+29h], 5
0x14000419c  jb      loc_140003FCE
0x1400041a2  mov     al, 1
0x1400041a4  jmp     loc_140003FD0
0x1400041a9  mov     rax, [rbx+48h]
0x1400041ad  mov     r9, [rbx+38h]
0x1400041b1  mov     [rsp+0E8h+var_B8], rsi
0x1400041b6  mov     [rsp+0E8h+var_C0], rax
0x1400041bb  mov     rax, [rbx+40h]
0x1400041bf  mov     [rsp+0E8h+var_C8], rax
0x1400041c4  call    McTemplateK0xxxx_EtwWriteTransfer
0x1400041c9  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 1
0x1400041d0  jz      loc_140003DD7
0x1400041d6  mov     r8, [rbx+48h]
0x1400041da  movsxd  r9, dword ptr [rbx+34h]
0x1400041de  mov     rax, r8
0x1400041e1  mov     r11, [rbx+40h]
0x1400041e5  sub     rax, rsi
0x1400041e8  mov     rdi, [rbx+38h]
0x1400041ec  mov     rcx, r11
0x1400041ef  imul    rax, 0F4240h
0x1400041f6  sub     rcx, r8
0x1400041f9  cqo
0x1400041fb  idiv    r9
0x1400041fe  mov     r10, rax
0x140004201  imul    rax, rcx, 0F4240h
0x140004208  mov     rcx, rdi
0x14000420b  mov     [rsp+0E8h+var_B0], r10
0x140004210  cqo
0x140004212  sub     rcx, r11
0x140004215  idiv    r9
0x140004218  mov     r8, rax
0x14000421b  imul    rax, rcx, 0F4240h
0x140004222  mov     [rsp+0E8h+var_B8], r8
0x140004227  cqo
0x140004229  idiv    r9
0x14000422c  mov     [rsp+0E8h+var_C0], rax
0x140004231  mov     [rsp+0E8h+var_C8], rdi
0x140004236  call    McTemplateK0xxiii_EtwWriteTransfer
0x14000423b  jmp     loc_140003DD7
0x140004240  mov     rcx, [rbx+20h]
0x140004244  lea     rdx, [rsp+0E8h+var_48]
0x14000424c  mov     rcx, [rcx+8]
0x140004250  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x140004255  mov     rcx, [rsp+0E8h+var_48]
0x14000425d  test    rcx, rcx
0x140004260  jnz     short loc_140004298
0x140004262  mov     rcx, [rsp+0E8h+var_40]; this
0x14000426a  test    rcx, rcx
0x14000426d  jz      loc_140003E49
0x140004273  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
  ... truncated ...
```
