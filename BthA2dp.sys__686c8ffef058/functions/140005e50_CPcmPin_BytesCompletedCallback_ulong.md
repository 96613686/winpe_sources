# CPcmPin::BytesCompletedCallback(ulong)

- ea: `0x140005e50`
- end: `0x140006376`
- name: `?BytesCompletedCallback@CPcmPin@@QEAAJK@Z`
- size: `1318`
- prototype: `__int64 __fastcall(CPcmPin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400064a0`
- `0x14000e310`

## callees

- `0x140005800`
- `0x140005e50`
- `0x14001bed0`
- `0x14001bf14`
- `0x140034c2c`
- `0x14003b29c`
- `0x14003b3dc`
- `0x14003b5ec`
- `0x14003b6a4`
- `0x14003b7fc`
- `0x14005c7d0`

## import_xrefs

- `ntoskrnl!ExSetTimer` at `0x140006009`
- `ntoskrnl!ExSetTimer` at `0x140006009`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400062e1`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400062e1`
- `ntoskrnl!KeClearEvent` at `0x14000630a`
- `ntoskrnl!KeClearEvent` at `0x14000630a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f45`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000603e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f45`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000603e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005ea1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005f58`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005ea1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005f58`
- `HAL!KeQueryPerformanceCounter` at `0x140005e8e`
- `HAL!KeQueryPerformanceCounter` at `0x140005e8e`

## pseudocode

```c
__int64 __fastcall CPcmPin::BytesCompletedCallback(CPcmPin *this, unsigned int a2)
{
  signed __int64 v3; // rdi
  LARGE_INTEGER v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // r8
  KIRQL v7; // r14
  bool v8; // r11
  signed __int64 v9; // rax
  signed __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  KIRQL v14; // r14
  unsigned __int32 v15; // edi
  __int64 v16; // rdx
  bool v17; // r10
  bool v18; // al
  __int64 v19; // rcx
  unsigned __int8 v20; // al
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // esi
  __int64 v24; // rcx
  __int64 v26; // r9
  __int64 v27; // r8
  bool v28; // r10
  __int64 v29; // r9
  bool v30; // r11
  int v31; // [rsp+20h] [rbp-98h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+70h] [rbp-48h] BYREF
  _QWORD v33[2]; // [rsp+78h] [rbp-40h] BYREF

  v3 = a2;
  PerformanceFrequency.QuadPart = 0;
  v4 = KeQueryPerformanceCounter(&PerformanceFrequency);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 10);
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
    McTemplateK0q_EtwWriteTransfer(v5, BytesCompletedCallbackStart, v6, (unsigned int)v3);
  v8 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
  LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType);
  if ( v8 || (_BYTE)v6 )
    WPP_RECORDER_AND_TRACE_SF_idiiii(WPP_GLOBAL_Control->AttachedDevice, v8, v6, WPP_GLOBAL_Control->DeviceExtension);
  if ( *((_BYTE *)this + 88) )
  {
    v29 = *((_QWORD *)this + 9);
    *((union _LARGE_INTEGER *)this + 14) = PerformanceFrequency;
    *((_QWORD *)this + 12) = v29;
    *((LARGE_INTEGER *)this + 13) = v4;
    *((_BYTE *)this + 88) = 0;
    v30 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( v30 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_ii(WPP_GLOBAL_Control->AttachedDevice, v30, v6, WPP_GLOBAL_Control->DeviceExtension, 4);
    }
  }
  v9 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, v3, 0);
  if ( v9 )
  {
    do
    {
      v10 = v9;
      v9 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, v9 + v3, v9);
    }
    while ( v9 != v10 );
  }
  if ( !*((_QWORD *)this + 15) )
  {
    v26 = *((_QWORD *)this + 13);
    if ( v26 )
    {
      v27 = *((_QWORD *)this + 14);
      if ( v4.QuadPart > v27 * (*((_QWORD *)this + 9) - *((_QWORD *)this + 12)) / *((int *)this + 13)
                       + v26
                       + 120 * v27 / 1000 )
      {
        if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 4) != 0 )
          McTemplateK0_EtwWriteTransfer(120 * v27, L2capOverflowStart);
        v28 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        if ( v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_i(
            WPP_GLOBAL_Control->AttachedDevice,
            v28,
            v27,
            WPP_GLOBAL_Control->DeviceExtension,
            3);
        }
        *((_QWORD *)this + 15) = KeQueryUnbiasedInterruptTime();
      }
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)this + 10, v7);
  v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 31);
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 2) != 0 )
    McTemplateK0i_EtwWriteTransfer(v12, v11, v13, 0);
  v15 = _InterlockedIncrement((volatile signed __int32 *)this + 84);
  if ( v15 == 1 )
    KeClearEvent((PRKEVENT)this + 11);
  v16 = *((_QWORD *)this + 4);
  if ( v16 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 2760));
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 3448));
    v17 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    v18 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( v17 || v18 )
      WPP_RECORDER_AND_TRACE_SF_dsddq(
        WPP_GLOBAL_Control->AttachedDevice,
        v17,
        v18,
        WPP_GLOBAL_Control->DeviceExtension,
        v31);
  }
  v19 = *((_QWORD *)this + 32);
  v33[0] = 0;
  v33[1] = 20000;
  v20 = ExSetTimer(v19, 0, 0, v33);
  v23 = v20;
  if ( v20 )
    v15 = CPcmPin::UnlockTimerDpc(this);
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 2) != 0 )
    McTemplateK0qq_EtwWriteTransfer(v21, SetTimerStop, v22, v15, v23);
  KeReleaseSpinLock((PKSPIN_LOCK)this + 31, v14);
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v24, "\n");
  return 0;
}

```

## disassembly

```asm
0x140005e50  mov     [rsp+arg_10], rbx
0x140005e55  mov     [rsp+arg_18], rbp
0x140005e5a  push    rsi
0x140005e5b  push    rdi
0x140005e5c  push    r12
0x140005e5e  push    r14
0x140005e60  push    r15
0x140005e62  sub     rsp, 90h
0x140005e69  mov     rax, cs:__security_cookie
0x140005e70  xor     rax, rsp
0x140005e73  mov     [rsp+0B8h+var_30], rax
0x140005e7b  mov     rbx, rcx
0x140005e7e  mov     edi, edx
0x140005e80  lea     rcx, [rsp+0B8h+PerformanceFrequency]; PerformanceFrequency
0x140005e85  mov     qword ptr [rsp+0B8h+PerformanceFrequency], 0
0x140005e8e  call    cs:__imp_KeQueryPerformanceCounter
0x140005e95  nop     dword ptr [rax+rax+00h]
0x140005e9a  lea     rcx, [rbx+50h]; SpinLock
0x140005e9e  mov     rsi, rax
0x140005ea1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005ea8  nop     dword ptr [rax+rax+00h]
0x140005ead  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 1
0x140005eb4  movzx   r14d, al
0x140005eb8  jnz     loc_140006200
0x140005ebe  mov     r10, cs:WPP_GLOBAL_Control
0x140005ec5  lea     r15, WPP_GLOBAL_Control
0x140005ecc  cmp     r10, r15
0x140005ecf  jnz     loc_140006086
0x140005ed5  xor     r11b, r11b
0x140005ed8  lea     r12, WPP_RECORDER_INITIALIZED
0x140005edf  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140005ee6  jnz     loc_140006140
0x140005eec  xor     r8b, r8b
0x140005eef  test    r11b, r11b
0x140005ef2  jnz     loc_140006225
0x140005ef8  test    r8b, r8b
0x140005efb  jnz     loc_140006225
0x140005f01  cmp     byte ptr [rbx+58h], 0
0x140005f05  jnz     loc_140006183
0x140005f0b  mov     r8, rdi
0x140005f0e  xor     eax, eax
0x140005f10  lock cmpxchg [rbx+48h], r8
0x140005f16  jz      short loc_140005F32
0x140005f18  nop     dword ptr [rax+rax+00000000h]
0x140005f20  mov     rdx, rax
0x140005f23  lea     rcx, [rax+rdi]
0x140005f27  lock cmpxchg [rbx+48h], rcx
0x140005f2d  cmp     rax, rdx
0x140005f30  jnz     short loc_140005F20
0x140005f32  cmp     qword ptr [rbx+78h], 0
0x140005f37  jz      loc_1400060A7
0x140005f3d  movzx   edx, r14b; NewIrql
0x140005f41  lea     rcx, [rbx+50h]; SpinLock
0x140005f45  call    cs:__imp_KeReleaseSpinLock
0x140005f4c  nop     dword ptr [rax+rax+00h]
0x140005f51  lea     rcx, [rbx+0F8h]; SpinLock
0x140005f58  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005f5f  nop     dword ptr [rax+rax+00h]
0x140005f64  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 2
0x140005f6b  movzx   r14d, al
0x140005f6f  jnz     loc_1400062F6
0x140005f75  mov     esi, 1
0x140005f7a  mov     edi, esi
0x140005f7c  lock xadd [rbx+150h], edi
0x140005f84  inc     edi
0x140005f86  cmp     edi, esi
0x140005f88  jz      loc_140006303
0x140005f8e  mov     rdx, [rbx+20h]
0x140005f92  test    rdx, rdx
0x140005f95  jz      short loc_140005FE3
0x140005f97  mov     r8d, esi
0x140005f9a  lock xadd [rdx+0AC8h], r8d
0x140005fa3  inc     r8d
0x140005fa6  lock xadd [rdx+0D78h], esi
0x140005fae  inc     esi
0x140005fb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fb7  cmp     rcx, r15
0x140005fba  jnz     loc_140006166
0x140005fc0  xor     r10b, r10b
0x140005fc3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140005fca  jnz     loc_140006154
0x140005fd0  xor     al, al
0x140005fd2  test    r10b, r10b
0x140005fd5  jnz     loc_14000631B
0x140005fdb  test    al, al
0x140005fdd  jnz     loc_14000631B
0x140005fe3  mov     rcx, [rbx+100h]
0x140005fea  lea     r9, [rsp+0B8h+var_40]
0x140005fef  xor     r8d, r8d
0x140005ff2  mov     [rsp+0B8h+var_40], 0
0x140005ffb  xor     edx, edx
0x140005ffd  mov     [rsp+0B8h+var_38], 4E20h
0x140006009  call    cs:__imp_ExSetTimer
0x140006010  nop     dword ptr [rax+rax+00h]
0x140006015  movzx   esi, al
0x140006018  test    al, al
0x14000601a  jz      short loc_140006026
0x14000601c  mov     rcx, rbx; this
0x14000601f  call    ?UnlockTimerDpc@CPcmPin@@AEAAJXZ; CPcmPin::UnlockTimerDpc(void)
0x140006024  mov     edi, eax
0x140006026  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 2
0x14000602d  jnz     loc_14000635E
0x140006033  movzx   edx, r14b; NewIrql
0x140006037  lea     rcx, [rbx+0F8h]; SpinLock
0x14000603e  call    cs:__imp_KeReleaseSpinLock
0x140006045  nop     dword ptr [rax+rax+00h]
0x14000604a  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 1
0x140006051  jnz     loc_140006214
0x140006057  xor     eax, eax
0x140006059  mov     rcx, [rsp+0B8h+var_30]
0x140006061  xor     rcx, rsp; StackCookie
0x140006064  call    __security_check_cookie
0x140006069  lea     r11, [rsp+0B8h+var_28]
0x140006071  mov     rbx, [r11+40h]
0x140006075  mov     rbp, [r11+48h]
0x140006079  mov     rsp, r11
0x14000607c  pop     r15
0x14000607e  pop     r14
0x140006080  pop     r12
0x140006082  pop     rdi
0x140006083  pop     rsi
0x140006084  retn
0x140006086  test    dword ptr [r10+2Ch], 2000h
0x14000608e  jz      loc_140005ED5
0x140006094  cmp     byte ptr [r10+29h], 5
0x140006099  jb      loc_140005ED5
0x14000609f  mov     r11b, 1
0x1400060a2  jmp     loc_140005ED8
0x1400060a7  mov     r9, [rbx+68h]
0x1400060ab  test    r9, r9
0x1400060ae  jz      loc_140005F3D
0x1400060b4  mov     r8, [rbx+70h]
0x1400060b8  movsxd  rcx, dword ptr [rbx+34h]
0x1400060bc  mov     rax, [rbx+48h]
0x1400060c0  sub     rax, [rbx+60h]
0x1400060c4  imul    rax, r8
0x1400060c8  cqo
0x1400060ca  idiv    rcx
0x1400060cd  imul    rcx, r8, 78h ; 'x'
0x1400060d1  lea     rdi, [rax+r9]
0x1400060d5  mov     rax, 20C49BA5E353F7CFh
0x1400060df  imul    rcx
0x1400060e2  sar     rdx, 7
0x1400060e6  mov     rax, rdx
0x1400060e9  shr     rax, 3Fh
0x1400060ed  add     rdx, rax
0x1400060f0  add     rdx, rdi
0x1400060f3  cmp     rsi, rdx
0x1400060f6  jle     loc_140005F3D
0x1400060fc  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 4
0x140006103  jz      short loc_140006111
0x140006105  lea     rdx, _L2capOverflowStart
0x14000610c  call    McTemplateK0_EtwWriteTransfer
0x140006111  mov     rcx, cs:WPP_GLOBAL_Control
0x140006118  cmp     rcx, r15
0x14000611b  jz      loc_140006297
0x140006121  test    dword ptr [rcx+2Ch], 2000h
0x140006128  jz      loc_140006297
0x14000612e  cmp     byte ptr [rcx+29h], 3
0x140006132  jb      loc_140006297
0x140006138  mov     r10b, 1
0x14000613b  jmp     loc_14000629A
0x140006140  cmp     word ptr [r10+48h], 0
0x140006146  jz      loc_140005EEC
0x14000614c  mov     r8b, 1
0x14000614f  jmp     loc_140005EEF
0x140006154  cmp     word ptr [rcx+48h], 0
0x140006159  jz      loc_140005FD0
0x14000615f  mov     al, 1
0x140006161  jmp     loc_140005FD2
0x140006166  mov     eax, [rcx+2Ch]
0x140006169  test    al, 10h
0x14000616b  jz      loc_140005FC0
0x140006171  cmp     byte ptr [rcx+29h], 5
0x140006175  jb      loc_140005FC0
0x14000617b  mov     r10b, 1
0x14000617e  jmp     loc_140005FC3
0x140006183  mov     rcx, qword ptr [rsp+0B8h+PerformanceFrequency]
0x140006188  mov     r9, [rbx+48h]
0x14000618c  mov     [rbx+70h], rcx
0x140006190  mov     [rbx+60h], r9
0x140006194  mov     [rbx+68h], rsi
0x140006198  mov     byte ptr [rbx+58h], 0
0x14000619c  mov     r10, cs:WPP_GLOBAL_Control
0x1400061a3  cmp     r10, r15
0x1400061a6  jnz     loc_140006276
0x1400061ac  xor     r11b, r11b
0x1400061af  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400061b6  setnz   r8b
0x1400061ba  test    r11b, r11b
0x1400061bd  jnz     short loc_1400061C8
0x1400061bf  test    r8b, r8b
0x1400061c2  jz      loc_140005F0B
0x1400061c8  imul    rax, rsi, 3E8h
0x1400061cf  cqo
0x1400061d1  idiv    rcx
0x1400061d4  mov     rcx, [r10+18h]
0x1400061d8  movzx   edx, r11b
0x1400061dc  mov     [rsp+0B8h+var_70], rax
0x1400061e1  mov     [rsp+0B8h+var_78], r9
0x1400061e6  mov     r9, [r10+40h]
0x1400061ea  mov     [rsp+0B8h+var_88], 1Eh
0x1400061f1  mov     byte ptr [rsp+0B8h+var_98], 4
0x1400061f6  call    WPP_RECORDER_AND_TRACE_SF_ii
0x1400061fb  jmp     loc_140005F0B
0x140006200  mov     r9d, edi
0x140006203  lea     rdx, _BytesCompletedCallbackStart
0x14000620a  call    McTemplateK0q_EtwWriteTransfer
0x14000620f  jmp     loc_140005EBE
0x140006214  lea     rdx, _BytesCompletedCallbackStop; "\n"
0x14000621b  call    McTemplateK0_EtwWriteTransfer
0x140006220  jmp     loc_140006057
0x140006225  mov     rcx, [rbx+78h]
0x140006229  mov     r9, [r10+40h]
0x14000622d  mov     [rsp+0B8h+var_50], rcx
0x140006232  mov     rcx, [rbx+38h]
0x140006236  imul    rax, rsi, 3E8h
0x14000623d  mov     [rsp+0B8h+var_58], rcx
0x140006242  mov     rcx, [rbx+40h]
0x140006246  cqo
0x140006248  idiv    qword ptr [rsp+0B8h+PerformanceFrequency]
0x14000624d  mov     [rsp+0B8h+var_60], rcx
0x140006252  movzx   edx, r11b
0x140006256  mov     rcx, [rbx+48h]
0x14000625a  mov     [rsp+0B8h+var_68], rcx
0x14000625f  mov     rcx, [r10+18h]
0x140006263  mov     dword ptr [rsp+0B8h+var_70], edi
0x140006267  mov     [rsp+0B8h+var_78], rax
0x14000626c  call    WPP_RECORDER_AND_TRACE_SF_idiiii
0x140006271  jmp     loc_140005F01
0x140006276  test    dword ptr [r10+2Ch], 2000h
0x14000627e  jz      loc_1400061AC
0x140006284  cmp     byte ptr [r10+29h], 4
0x140006289  jb      loc_1400061AC
0x14000628f  mov     r11b, 1
0x140006292  jmp     loc_1400061AF
0x140006297  xor     r10b, r10b
0x14000629a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400062a1  setnz   r8b
0x1400062a5  test    r10b, r10b
0x1400062a8  jnz     short loc_1400062AF
0x1400062aa  test    r8b, r8b
0x1400062ad  jz      short loc_1400062E1
0x1400062af  mov     r9, [rcx+40h]
0x1400062b3  sub     rsi, rdi
0x1400062b6  mov     rcx, [rcx+18h]
0x1400062ba  imul    rax, rsi, 3E8h
0x1400062c1  cqo
0x1400062c3  idiv    qword ptr [rbx+70h]
0x1400062c7  movzx   edx, r10b
0x1400062cb  mov     [rsp+0B8h+var_78], rax
0x1400062d0  mov     [rsp+0B8h+var_88], 1Fh
0x1400062d7  mov     byte ptr [rsp+0B8h+var_98], 3
0x1400062dc  call    WPP_RECORDER_AND_TRACE_SF_i
0x1400062e1  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400062e8  nop     dword ptr [rax+rax+00h]
0x1400062ed  mov     [rbx+78h], rax
0x1400062f1  jmp     loc_140005F3D
0x1400062f6  xor     r9d, r9d
0x1400062f9  call    McTemplateK0i_EtwWriteTransfer
0x1400062fe  jmp     loc_140005F75
0x140006303  lea     rcx, [rbx+108h]; Event
0x14000630a  call    cs:__imp_KeClearEvent
0x140006311  nop     dword ptr [rax+rax+00h]
0x140006316  jmp     loc_140005F8E
0x14000631b  mov     r9, [rcx+40h]
0x14000631f  mov     rcx, [rcx+18h]
0x140006323  mov     [rsp+0B8h+var_58], rdx
0x140006328  lea     rdx, aLocktimerdpc; "LockTimerDpc"
0x14000632f  mov     dword ptr [rsp+0B8h+var_60], esi
0x140006333  mov     dword ptr [rsp+0B8h+var_68], 9
0x14000633b  mov     [rsp+0B8h+var_70], rdx
0x140006340  movzx   edx, r10b
0x140006344  mov     dword ptr [rsp+0B8h+var_78], r8d
0x140006349  movzx   r8d, al
0x14000634d  mov     [rsp+0B8h+var_88], 2Eh ; '.'
0x140006354  call    WPP_RECORDER_AND_TRACE_SF_dsddq
0x140006359  jmp     loc_140005FE3
0x14000635e  mov     r9d, edi
0x140006361  mov     [rsp+0B8h+var_98], esi
0x140006365  lea     rdx, _SetTimerStop
0x14000636c  call    McTemplateK0qq_EtwWriteTransfer
0x140006371  jmp     loc_140006033
```
