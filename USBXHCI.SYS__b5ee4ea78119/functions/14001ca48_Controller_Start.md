# Controller_Start

- ea: `0x14001ca48`
- end: `0x14001cf41`
- name: `Controller_Start`
- size: `1273`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400416f8`
- `0x140044260`

## callees

- `0x14001ac48`
- `0x14001bb78`
- `0x14001c5ec`
- `0x14001ca20`
- `0x14001ca48`
- `0x14001d118`
- `0x14001f830`
- `0x14001fb30`
- `0x1400218a0`
- `0x1400219b0`
- `0x1400326e0`
- `0x140040c6c`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001cb9f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001cbfe`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001ce42`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001ce5a`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001cb9f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001cbfe`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001ce42`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001ce5a`
- `ntoskrnl!ExAllocateTimer` at `0x14001ccff`
- `ntoskrnl!ExAllocateTimer` at `0x14001ccff`
- `ntoskrnl!ExSetTimer` at `0x14001cdfd`
- `ntoskrnl!ExSetTimer` at `0x14001cdfd`
- `ntoskrnl!ExDeleteTimer` at `0x14001ccb2`
- `ntoskrnl!ExDeleteTimer` at `0x14001ccb2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001cd21`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001cd21`
- `ntoskrnl!KeInitializeEvent` at `0x14001cdda`
- `ntoskrnl!KeInitializeEvent` at `0x14001cdda`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ce1f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ce1f`
- `HAL!KeStallExecutionProcessor` at `0x14001cbdc`
- `HAL!KeStallExecutionProcessor` at `0x14001cbdc`

## string_xrefs

- `0x14001cd44`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall Controller_Start(__int64 a1)
{
  unsigned int v2; // ebx
  _QWORD *v4; // r14
  __int64 v5; // rcx
  __int64 v6; // r13
  int Ulong; // eax
  char v8; // bl
  __int64 v9; // r15
  unsigned int v10; // eax
  __int64 v11; // rdx
  char ExtendedTBCEnable; // cl
  int v13; // r9d
  int v14; // r10d
  __int64 v15; // r11
  int v16; // ebp
  int v17; // r8d
  unsigned int v18; // ebp
  __int64 v19; // rcx
  __int64 v20; // r11
  _QWORD *v21; // r12
  int v22; // eax
  unsigned int v23; // ebp
  ULONGLONG v24; // rsi
  int v25; // r8d
  unsigned int i; // ebp
  int v27; // ebp
  unsigned int j; // ebp
  ULONGLONG v29; // rcx
  int v30; // r8d
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // rdx
  __int64 v33; // rbx
  int v34; // eax
  int Timeout; // [rsp+20h] [rbp-68h]
  struct _KEVENT Event; // [rsp+30h] [rbp-58h] BYREF
  ULONGLONG UnbiasedInterruptTime; // [rsp+90h] [rbp+8h]
  __int64 v38; // [rsp+98h] [rbp+10h]

  memset(&Event, 0, sizeof(Event));
  if ( *(_BYTE *)(a1 + 1041) && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\controller.c",
      4503);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 4, 4, 121, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
  if ( !(unsigned __int8)Controller_IsControllerAccessible(a1) )
    return 0;
  v4 = (_QWORD *)(a1 + 88);
  v5 = *(_QWORD *)(a1 + 88);
  v6 = *(_QWORD *)(v5 + 32);
  v38 = v6 + 4;
  Ulong = XilRegister_ReadUlong(v5, v6 + 4);
  v8 = Ulong;
  if ( Ulong == -1 )
    return 0;
  if ( (Ulong & 1) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 2, 4, 122, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
    return (unsigned int)-1073741630;
  }
  v9 = 0;
  XilRegister_WriteUlong(*v4, *(_QWORD *)(*v4 + 32LL) + 20LL, 2);
  v10 = XilRegister_ReadUlong(*v4, v6);
  ExtendedTBCEnable = Register_GetExtendedTBCEnable(*v4, v11, *(unsigned int *)(*v4 + 80LL), v10);
  v16 = v13 | 0x10000;
  *(_BYTE *)(a1 + 1050) = ExtendedTBCEnable;
  if ( v17 != 3 )
    v16 = v13;
  v18 = (v14 != 0 ? 8197 : 5) | ((ExtendedTBCEnable & 1) << 14) | v16 & 0xFFFF9FFF;
  *(_BYTE *)(a1 + 1051) = Register_GetExtendedTBCTRBStatusSupported(v15);
  if ( (unsigned __int8)Register_GetExtendedTBCTRBStatusSupported(v19) )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v20 + 8) + 744LL) & 0x1000LL) == 0 )
    {
      v21 = (_QWORD *)(a1 + 88);
      v22 = 1;
      goto LABEL_14;
    }
    v21 = (_QWORD *)(a1 + 88);
  }
  else
  {
    v21 = (_QWORD *)(a1 + 88);
  }
  v22 = 0;
LABEL_14:
  v23 = (v22 << 15) | v18 & 0xFFFF7FFF;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 4, 4, 123, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  v24 = 0;
  XilRegister_WriteUlong(*v21, v6, v23);
  for ( i = 0; i < 0x32; ++i )
  {
    KeStallExecutionProcessor(0x64u);
    v8 = XilRegister_ReadUlong(*v4, v38);
    if ( (v8 & 1) == 0 )
    {
      v24 = KeQueryUnbiasedInterruptTime();
      break;
    }
  }
  if ( (v8 & 1) == 0 )
    goto LABEL_21;
  v9 = ExAllocateTimer(&Controller_HighResTimerCompletion, &Event, 4);
  if ( !v9 )
    return (unsigned int)-1073741670;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  for ( j = 0; j < 7; ++j )
  {
    ExSetTimer(v9, -50000, 0, 0);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    v8 = XilRegister_ReadUlong(*v4, v38);
    if ( (v8 & 1) == 0 )
    {
      v24 = KeQueryUnbiasedInterruptTime();
      break;
    }
  }
  if ( (v8 & 1) != 0 )
  {
    v29 = KeQueryUnbiasedInterruptTime();
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v31 = (v29 - UnbiasedInterruptTime) / 0x2710;
      LOBYTE(v31) = 2;
      WPP_RECORDER_SF_I(*(_QWORD *)(a1 + 72), v31, v30, 124, Timeout, (v29 - UnbiasedInterruptTime) / 0x2710);
    }
  }
  else
  {
LABEL_21:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v32 = (v24 - UnbiasedInterruptTime) / 0xA;
      LOBYTE(v32) = 4;
      WPP_RECORDER_SF_I(*(_QWORD *)(a1 + 72), v32, v25, 125, Timeout, (v24 - UnbiasedInterruptTime) / 0xA);
    }
  }
  DynamicLock_Acquire(*(_QWORD *)(a1 + 1120));
  ++*(_DWORD *)(a1 + 1128);
  v27 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 112))(
          WdfDriverGlobals,
          *(_QWORD *)(a1 + 1136));
  if ( v27 )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 (__fastcall *)(), __int64))(WdfFunctions_01033 + 1144))(
      WdfDriverGlobals,
      **(_QWORD **)(*(_QWORD *)(a1 + 128) + 40LL),
      Interrupter_ClearBusEdgeInformationRoutineWithIsrSync,
      a1 + 1112);
    v33 = *(_QWORD *)(*v4 + 32LL);
    v34 = XilRegister_ReadUlong(*v4, v33);
    XilRegister_WriteUlong(*v4, v33, v34 | 0x400u);
    *(_BYTE *)(a1 + 1112) = 1;
  }
  DynamicLock_Release(*(_QWORD *)(a1 + 1120));
  if ( v27 )
    Controller_DetectFrameMicroframeBoundary(a1);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01033 + 2552))(
    WdfDriverGlobals,
    *(_QWORD *)(a1 + 760),
    -50000000);
  v2 = 0;
  if ( v9 )
    ExDeleteTimer(v9, 0, 0, 0);
  return v2;
}

```

## disassembly

```asm
0x14001ca48  mov     [rsp+arg_10], rbx
0x14001ca4d  push    rbp
0x14001ca4e  push    rsi
0x14001ca4f  push    rdi
0x14001ca50  push    r12
0x14001ca52  push    r13
0x14001ca54  push    r14
0x14001ca56  push    r15
0x14001ca58  sub     rsp, 50h
0x14001ca5c  xor     eax, eax
0x14001ca5e  xorps   xmm0, xmm0
0x14001ca61  mov     rdi, rcx
0x14001ca64  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14001ca69  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x14001ca6e  cmp     [rcx+411h], al
0x14001ca74  jnz     loc_14001CD21
0x14001ca7a  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001ca81  mov     esi, 4
0x14001ca86  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001ca8d  lea     r15, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14001ca94  jnz     loc_14001CD55
0x14001ca9a  mov     rcx, rdi
0x14001ca9d  call    Controller_IsControllerAccessible
0x14001caa2  test    al, al
0x14001caa4  jnz     short loc_14001CAC3
0x14001caa6  xor     ebx, ebx
0x14001caa8  mov     eax, ebx
0x14001caaa  mov     rbx, [rsp+88h+arg_10]
0x14001cab2  add     rsp, 50h
0x14001cab6  pop     r15
0x14001cab8  pop     r14
0x14001caba  pop     r13
0x14001cabc  pop     r12
0x14001cabe  pop     rdi
0x14001cabf  pop     rsi
0x14001cac0  pop     rbp
0x14001cac1  retn
0x14001cac3  lea     r14, [rdi+58h]
0x14001cac7  mov     rcx, [r14]
0x14001caca  mov     r13, [rcx+20h]
0x14001cace  lea     rax, [r13+4]
0x14001cad2  mov     rdx, rax
0x14001cad5  mov     [rsp+88h+arg_8], rax
0x14001cadd  call    XilRegister_ReadUlong
0x14001cae2  mov     ebx, eax
0x14001cae4  cmp     eax, 0FFFFFFFFh
0x14001cae7  jz      short loc_14001CAA6
0x14001cae9  test    al, 1
0x14001caeb  jz      loc_14001CD74
0x14001caf1  mov     rcx, [r14]
0x14001caf4  xor     r15d, r15d
0x14001caf7  mov     rdx, [rcx+20h]
0x14001cafb  lea     r8d, [r15+2]
0x14001caff  add     rdx, 14h
0x14001cb03  call    XilRegister_WriteUlong
0x14001cb08  mov     rcx, [r14]
0x14001cb0b  mov     rdx, r13
0x14001cb0e  call    XilRegister_ReadUlong
0x14001cb13  mov     r11, [r14]
0x14001cb16  mov     r9d, eax
0x14001cb19  mov     rcx, r11
0x14001cb1c  mov     r10d, [r11+6Ch]
0x14001cb20  mov     r8d, [r11+50h]
0x14001cb24  and     r10d, 2
0x14001cb28  call    Register_GetExtendedTBCEnable
0x14001cb2d  movzx   ecx, al
0x14001cb30  mov     ebp, r9d
0x14001cb33  bts     ebp, 10h
0x14001cb37  mov     [rdi+41Ah], cl
0x14001cb3d  cmp     r8d, 3
0x14001cb41  cmovnz  ebp, r9d
0x14001cb45  and     ecx, 1
0x14001cb48  shl     ecx, 0Eh
0x14001cb4b  and     ebp, 0FFFF9FFFh
0x14001cb51  or      ebp, ecx
0x14001cb53  mov     rcx, r11
0x14001cb56  neg     r10d
0x14001cb59  sbb     eax, eax
0x14001cb5b  and     eax, 2000h
0x14001cb60  add     eax, 5
0x14001cb63  or      ebp, eax
0x14001cb65  call    Register_GetExtendedTBCTRBStatusSupported
0x14001cb6a  mov     [rdi+41Bh], al
0x14001cb70  call    Register_GetExtendedTBCTRBStatusSupported
0x14001cb75  test    al, al
0x14001cb77  jnz     loc_14001CCC3
0x14001cb7d  mov     r12, r14
0x14001cb80  xor     eax, eax
0x14001cb82  btr     ebp, 0Fh
0x14001cb86  shl     eax, 0Fh
0x14001cb89  or      ebp, eax
0x14001cb8b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001cb92  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cb99  jnz     loc_14001CDA9
0x14001cb9f  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14001cba6  nop     dword ptr [rax+rax+00h]
0x14001cbab  mov     rcx, [r12]
0x14001cbaf  mov     r8d, ebp
0x14001cbb2  mov     rdx, r13
0x14001cbb5  mov     [rsp+88h+arg_0], rax
0x14001cbbd  xor     esi, esi
0x14001cbbf  call    XilRegister_WriteUlong
0x14001cbc4  mov     r12, [rsp+88h+arg_8]
0x14001cbcc  lea     r13d, [rsi+1]
0x14001cbd0  xor     ebp, ebp
0x14001cbd2  cmp     ebp, 32h ; '2'
0x14001cbd5  jnb     short loc_14001CC0D
0x14001cbd7  mov     ecx, 64h ; 'd'; MicroSeconds
0x14001cbdc  call    cs:__imp_KeStallExecutionProcessor
0x14001cbe3  nop     dword ptr [rax+rax+00h]
0x14001cbe8  mov     rcx, [r14]
0x14001cbeb  mov     rdx, r12
0x14001cbee  call    XilRegister_ReadUlong
0x14001cbf3  mov     ebx, eax
0x14001cbf5  test    r13b, al
0x14001cbf8  jnz     loc_14001CCE5
0x14001cbfe  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14001cc05  nop     dword ptr [rax+rax+00h]
0x14001cc0a  mov     rsi, rax
0x14001cc0d  test    r13b, bl
0x14001cc10  jnz     loc_14001CCED
0x14001cc16  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001cc1d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cc24  jnz     loc_14001CEA5
0x14001cc2a  lea     rsi, [rdi+458h]
0x14001cc31  mov     rcx, [rsi+8]
0x14001cc35  call    DynamicLock_Acquire
0x14001cc3a  add     [rsi+10h], r13d
0x14001cc3e  mov     rax, cs:WdfFunctions_01033
0x14001cc45  mov     rdx, [rsi+18h]
0x14001cc49  mov     rcx, cs:WdfDriverGlobals
0x14001cc50  mov     rax, [rax+70h]
0x14001cc54  call    _guard_dispatch_icall
0x14001cc59  mov     ebp, eax
0x14001cc5b  test    eax, eax
0x14001cc5d  jnz     loc_14001CED9
0x14001cc63  mov     rcx, [rsi+8]
0x14001cc67  call    DynamicLock_Release
0x14001cc6c  test    ebp, ebp
0x14001cc6e  jnz     loc_14001CF34
0x14001cc74  mov     rax, cs:WdfFunctions_01033
0x14001cc7b  mov     r8, 0FFFFFFFFFD050F80h
0x14001cc82  mov     rdx, [rdi+2F8h]
0x14001cc89  mov     rcx, cs:WdfDriverGlobals
0x14001cc90  mov     rax, [rax+9F8h]
0x14001cc97  call    _guard_dispatch_icall
0x14001cc9c  xor     ebx, ebx
0x14001cc9e  test    r15, r15
0x14001cca1  jz      loc_14001CAA8
0x14001cca7  xor     r9d, r9d
0x14001ccaa  xor     r8d, r8d
0x14001ccad  xor     edx, edx
0x14001ccaf  mov     rcx, r15
0x14001ccb2  call    cs:__imp_ExDeleteTimer
0x14001ccb9  nop     dword ptr [rax+rax+00h]
0x14001ccbe  jmp     loc_14001CAA8
0x14001ccc3  mov     rax, [r11+8]
0x14001ccc7  mov     ecx, [rax+2E8h]
0x14001cccd  bt      rcx, 0Ch
0x14001ccd2  jb      loc_14001CDA0
0x14001ccd8  mov     r12, r14
0x14001ccdb  mov     eax, 1
0x14001cce0  jmp     loc_14001CB82
0x14001cce5  add     ebp, r13d
0x14001cce8  jmp     loc_14001CBD2
0x14001cced  mov     r8d, 4
0x14001ccf3  lea     rdx, [rsp+88h+Event]
0x14001ccf8  lea     rcx, Controller_HighResTimerCompletion
0x14001ccff  call    cs:__imp_ExAllocateTimer
0x14001cd06  nop     dword ptr [rax+rax+00h]
0x14001cd0b  mov     r15, rax
0x14001cd0e  test    rax, rax
0x14001cd11  jnz     loc_14001CDCF
0x14001cd17  mov     ebx, 0C000009Ah
0x14001cd1c  jmp     loc_14001CAA8
0x14001cd21  call    cs:__imp_KeGetCurrentIrql
0x14001cd28  nop     dword ptr [rax+rax+00h]
0x14001cd2d  test    al, al
0x14001cd2f  jz      loc_14001CA7A
0x14001cd35  mov     r9d, 1197h
0x14001cd3b  lea     r8, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14001cd42  xor     edx, edx
0x14001cd44  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x14001cd4b  call    Debug_FreAssertMsg
0x14001cd50  jmp     loc_14001CA7A
0x14001cd55  mov     rcx, [rdi+48h]
0x14001cd59  mov     r9d, 79h ; 'y'
0x14001cd5f  mov     r8d, esi
0x14001cd62  mov     [rsp+88h+Timeout], r15
0x14001cd67  mov     dl, sil
0x14001cd6a  call    WPP_RECORDER_SF_
0x14001cd6f  jmp     loc_14001CA9A
0x14001cd74  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001cd7b  jz      short loc_14001CD96
0x14001cd7d  mov     rcx, [rdi+48h]
0x14001cd81  mov     r9d, 7Ah ; 'z'
0x14001cd87  mov     r8d, esi
0x14001cd8a  mov     [rsp+88h+Timeout], r15
0x14001cd8f  mov     dl, 2
0x14001cd91  call    WPP_RECORDER_SF_
0x14001cd96  mov     ebx, 0C00000C2h
0x14001cd9b  jmp     loc_14001CAA8
0x14001cda0  lea     r12, [rdi+58h]
0x14001cda4  jmp     loc_14001CB80
0x14001cda9  mov     rcx, [rdi+48h]
0x14001cdad  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14001cdb4  mov     r9d, 7Bh ; '{'
0x14001cdba  mov     [rsp+88h+Timeout], rax
0x14001cdbf  mov     r8d, esi
0x14001cdc2  mov     dl, sil
0x14001cdc5  call    WPP_RECORDER_SF_
0x14001cdca  jmp     loc_14001CB9F
0x14001cdcf  xor     r8d, r8d; State
0x14001cdd2  lea     rcx, [rsp+88h+Event]; Event
0x14001cdd7  mov     edx, r13d; Type
0x14001cdda  call    cs:__imp_KeInitializeEvent
0x14001cde1  nop     dword ptr [rax+rax+00h]
0x14001cde6  xor     ebp, ebp
0x14001cde8  cmp     ebp, 7
0x14001cdeb  jnb     short loc_14001CE51
0x14001cded  xor     r9d, r9d
0x14001cdf0  xor     r8d, r8d
0x14001cdf3  mov     rdx, 0FFFFFFFFFFFF3CB0h
0x14001cdfa  mov     rcx, r15
0x14001cdfd  call    cs:__imp_ExSetTimer
0x14001ce04  nop     dword ptr [rax+rax+00h]
0x14001ce09  xor     r9d, r9d; Alertable
0x14001ce0c  mov     [rsp+88h+Timeout], 0; Timeout
0x14001ce15  xor     r8d, r8d; WaitMode
0x14001ce18  lea     rcx, [rsp+88h+Event]; Object
0x14001ce1d  xor     edx, edx; WaitReason
0x14001ce1f  call    cs:__imp_KeWaitForSingleObject
0x14001ce26  nop     dword ptr [rax+rax+00h]
0x14001ce2b  mov     rcx, [r14]
0x14001ce2e  mov     rdx, r12
0x14001ce31  call    XilRegister_ReadUlong
0x14001ce36  mov     ebx, eax
0x14001ce38  test    r13b, al
0x14001ce3b  jz      short loc_14001CE42
0x14001ce3d  add     ebp, r13d
0x14001ce40  jmp     short loc_14001CDE8
0x14001ce42  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14001ce49  nop     dword ptr [rax+rax+00h]
0x14001ce4e  mov     rsi, rax
0x14001ce51  test    r13b, bl
0x14001ce54  jz      loc_14001CC16
0x14001ce5a  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14001ce61  nop     dword ptr [rax+rax+00h]
0x14001ce66  mov     rcx, rax
0x14001ce69  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001ce70  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ce77  jz      loc_14001CC2A
0x14001ce7d  sub     rcx, [rsp+88h+arg_0]
0x14001ce85  mov     rax, 346DC5D63886594Bh
0x14001ce8f  mul     rcx
0x14001ce92  mov     r9d, 7Ch ; '|'
0x14001ce98  shr     rdx, 0Bh
0x14001ce9c  mov     [rsp+88h+var_60], rdx
0x14001cea1  mov     dl, 2
0x14001cea3  jmp     short loc_14001CECB
0x14001cea5  sub     rsi, [rsp+88h+arg_0]
0x14001cead  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14001ceb7  mul     rsi
0x14001ceba  mov     r9d, 7Dh ; '}'
0x14001cec0  shr     rdx, 3
0x14001cec4  mov     [rsp+88h+var_60], rdx
0x14001cec9  mov     dl, 4
0x14001cecb  mov     rcx, [rdi+48h]
0x14001cecf  call    WPP_RECORDER_SF_I
0x14001ced4  jmp     loc_14001CC2A
0x14001ced9  mov     rcx, [rdi+80h]
0x14001cee0  lea     r8, Interrupter_ClearBusEdgeInformationRoutineWithIsrSync
0x14001cee7  mov     r9, rsi
0x14001ceea  mov     rdx, [rcx+28h]
0x14001ceee  mov     rcx, cs:WdfFunctions_01033
0x14001cef5  mov     rdx, [rdx]
0x14001cef8  mov     rax, [rcx+478h]
0x14001ceff  mov     rcx, cs:WdfDriverGlobals
0x14001cf06  call    _guard_dispatch_icall
0x14001cf0b  mov     rcx, [r14]
0x14001cf0e  mov     rbx, [rcx+20h]
0x14001cf12  mov     rdx, rbx
0x14001cf15  call    XilRegister_ReadUlong
0x14001cf1a  mov     rcx, [r14]
0x14001cf1d  bts     eax, 0Ah
0x14001cf21  mov     r8d, eax
0x14001cf24  mov     rdx, rbx
0x14001cf27  call    XilRegister_WriteUlong
0x14001cf2c  mov     [rsi], r13b
0x14001cf2f  jmp     loc_14001CC63
0x14001cf34  mov     rcx, rdi
0x14001cf37  call    Controller_DetectFrameMicroframeBoundary
0x14001cf3c  jmp     loc_14001CC74
```
