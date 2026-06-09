# Register_ControllerStop

- ea: `0x140017adc`
- end: `0x140017eec`
- name: `Register_ControllerStop`
- size: `1040`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140017a10`
- `0x140018d90`
- `0x14001a928`
- `0x14004132c`
- `0x1400416f8`

## callees

- `0x140002568`
- `0x1400038c0`
- `0x140017adc`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001d118`
- `0x14001f830`
- `0x14001fb30`
- `0x140049d88`
- `0x140050ba8`
- `0x140050ca8`
- `0x140057db0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140017b93`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140017d44`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140017df8`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140017b93`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140017d44`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140017df8`
- `ntoskrnl!KeDelayExecutionThread` at `0x140017be8`
- `ntoskrnl!KeDelayExecutionThread` at `0x140017be8`
- `ntoskrnl!ExAllocateTimer` at `0x140017c0e`
- `ntoskrnl!ExAllocateTimer` at `0x140017c0e`
- `ntoskrnl!ExSetTimer` at `0x140017c4f`
- `ntoskrnl!ExSetTimer` at `0x140017c4f`
- `ntoskrnl!ExDeleteTimer` at `0x140017ecc`
- `ntoskrnl!ExDeleteTimer` at `0x140017ecc`
- `ntoskrnl!KeInitializeEvent` at `0x140017c32`
- `ntoskrnl!KeInitializeEvent` at `0x140017c32`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017c71`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017c71`

## pseudocode

```c
__int64 __fastcall Register_ControllerStop(__int64 a1)
{
  __int64 v2; // r15
  _QWORD *v3; // rbx
  __int64 *v4; // rdx
  __int64 v5; // r14
  int Ulong; // eax
  ULONGLONG UnbiasedInterruptTime; // r13
  int v8; // esi
  int v9; // edx
  unsigned int v10; // ebx
  int v11; // edx
  ULONGLONG v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // edx
  __int64 v16; // rcx
  unsigned __int128 v17; // rax
  __int64 v18; // r14
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  struct _KEVENT Event; // [rsp+40h] [rbp-68h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+B0h] [rbp+8h] BYREF

  Interval.QuadPart = 0;
  memset(&Event, 0, sizeof(Event));
  v2 = 0;
  v3 = (_QWORD *)(a1 + 8);
  v4 = WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 4;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*v3 + 72LL),
      (_DWORD)v4,
      6,
      58,
      (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids);
  }
  if ( !(unsigned __int8)Controller_IsControllerAccessible(*v3) )
    goto LABEL_39;
  v5 = *(_QWORD *)(a1 + 32);
  Ulong = XilRegister_ReadUlong(a1, v5);
  XilRegister_WriteUlong(a1, v5, Ulong & 0xFFFFFFFE);
  if ( (unsigned int)Feature_RTOFRS__private_IsEnabledDeviceUsageNoInline() )
  {
    v8 = 1000;
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  }
  else
  {
    UnbiasedInterruptTime = 0;
    v3 = (_QWORD *)(a1 + 8);
    v8 = 16;
  }
  if ( (XilRegister_ReadUlong(a1, v5 + 4) & 1) != 0 )
  {
LABEL_18:
    if ( (unsigned int)Feature_RTOFRS__private_IsEnabledDeviceUsageNoInline() )
    {
      v17 = (KeQueryUnbiasedInterruptTime() - UnbiasedInterruptTime) * (unsigned __int128)0x346DC5D63886594BuLL;
      v18 = *((_QWORD *)&v17 + 1) >> 11;
      if ( (unsigned int)(1000 - v8) > 0x10 )
      {
        v19 = *(_QWORD *)(a1 + 8);
        if ( *(_DWORD *)(v19 + 644) == 1 )
          v20 = *(unsigned __int16 *)(v19 + 652) | (*(unsigned __int16 *)(v19 + 648) << 16);
        else
          v20 = 0;
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          "USBXHCI.SYS",
          v20,
          (unsigned int)v18,
          "Controller took longer than expected to Stop. Parameter2 is delay in milliseconds");
        Etw_ReportDelayedControllerStop(v21, *v3, (unsigned int)v18);
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        BYTE8(v17) = 4;
        WPP_RECORDER_SF_ddd(
          *(_QWORD *)(*v3 + 72LL),
          DWORD2(v17),
          6,
          59,
          (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
          -24 - v8,
          1,
          v18);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_DD(
        *(_QWORD *)(*v3 + 72LL),
        v9,
        6,
        60,
        (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
        16 - v8,
        1);
    }
LABEL_39:
    v10 = 0;
    goto LABEL_40;
  }
  while ( v8 )
  {
    Interval.QuadPart = -10000;
    if ( (unsigned int)Feature_RTOFRS__private_IsEnabledDeviceUsageNoInline() && (unsigned int)(1000 - v8) >= 0x10 )
    {
      if ( !v2 )
      {
        v2 = ExAllocateTimer(&Controller_HighResTimerCompletion, &Event, 4);
        if ( !v2 )
        {
          v10 = -1073741670;
          goto LABEL_40;
        }
        KeInitializeEvent(&Event, SynchronizationEvent, 0);
      }
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ExSetTimer)(
        v2,
        (union _LARGE_INTEGER)Interval.QuadPart,
        0,
        0);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    }
    else
    {
      KeDelayExecutionThread(0, 0, &Interval);
    }
    --v8;
    if ( (XilRegister_ReadUlong(a1, v5 + 4) & 1) != 0 )
    {
      v3 = (_QWORD *)(a1 + 8);
      goto LABEL_18;
    }
  }
  if ( (unsigned int)Feature_RTOFRS__private_IsEnabledDeviceUsageNoInline() )
  {
    v12 = (KeQueryUnbiasedInterruptTime() - UnbiasedInterruptTime) / 0x2710;
    v13 = *(_QWORD *)(a1 + 8);
    if ( *(_DWORD *)(v13 + 644) == 1 )
      v14 = *(unsigned __int16 *)(v13 + 652) | (*(unsigned __int16 *)(v13 + 648) << 16);
    else
      v14 = 0;
    MicrosoftTelemetryAssertTriggeredArgsMsgKM(
      "USBXHCI.SYS",
      v14,
      (unsigned int)v12,
      "Controller failed to Stop. Parameter2 is delay in milliseconds");
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_DD(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
        v15,
        6,
        61,
        (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
        232,
        v12);
    }
    Etw_ReportFailedControllerStop(v16, *(_QWORD *)(a1 + 8), (unsigned int)v12);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
      v11,
      6,
      62,
      (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
      16);
  }
  v10 = -1073741823;
LABEL_40:
  if ( (unsigned int)Feature_RTOFRS__private_IsEnabledDeviceUsageNoInline() && v2 )
    ExDeleteTimer(v2, 0, 0, 0);
  return v10;
}

```

## disassembly

```asm
0x140017adc  mov     r11, rsp
0x140017adf  push    rbx
0x140017ae0  push    rbp
0x140017ae1  push    rsi
0x140017ae2  push    rdi
0x140017ae3  push    r12
0x140017ae5  push    r13
0x140017ae7  push    r14
0x140017ae9  push    r15
0x140017aeb  sub     rsp, 68h
0x140017aef  xor     eax, eax
0x140017af1  mov     qword ptr [r11+8], 0
0x140017af9  xorps   xmm0, xmm0
0x140017afc  mov     rdi, rcx
0x140017aff  movups  xmmword ptr [rsp+0A8h+Event.Header.___u0], xmm0
0x140017b04  mov     [r11-58h], rax
0x140017b08  xor     r15d, r15d
0x140017b0b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140017b12  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017b19  lea     rbx, [rcx+8]
0x140017b1d  lea     rdx, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x140017b24  jz      short loc_140017B41
0x140017b26  mov     rcx, [rbx]
0x140017b29  lea     r9d, [r15+3Ah]
0x140017b2d  mov     [rsp+0A8h+Timeout], rdx
0x140017b32  lea     r8d, [r15+6]
0x140017b36  mov     dl, 4
0x140017b38  mov     rcx, [rcx+48h]
0x140017b3c  call    WPP_RECORDER_SF_
0x140017b41  mov     rcx, [rbx]
0x140017b44  call    Controller_IsControllerAccessible
0x140017b49  test    al, al
0x140017b4b  jz      loc_140017EB1
0x140017b51  mov     r14, [rdi+20h]
0x140017b55  mov     rcx, rdi
0x140017b58  mov     rdx, r14
0x140017b5b  call    XilRegister_ReadUlong
0x140017b60  and     eax, 0FFFFFFFEh
0x140017b63  mov     rdx, r14
0x140017b66  mov     r8d, eax
0x140017b69  mov     rcx, rdi
0x140017b6c  call    XilRegister_WriteUlong
0x140017b71  call    Feature_RTOFRS__private_IsEnabledDeviceUsageNoInline
0x140017b76  mov     ebp, 10h
0x140017b7b  mov     r12d, 3E8h
0x140017b81  test    eax, eax
0x140017b83  jnz     short loc_140017B90
0x140017b85  xor     r13d, r13d
0x140017b88  lea     rbx, [rdi+8]
0x140017b8c  mov     esi, ebp
0x140017b8e  jmp     short loc_140017BA2
0x140017b90  mov     esi, r12d
0x140017b93  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140017b9a  nop     dword ptr [rax+rax+00h]
0x140017b9f  mov     r13, rax
0x140017ba2  lea     rdx, [r14+4]
0x140017ba6  mov     rcx, rdi
0x140017ba9  call    XilRegister_ReadUlong
0x140017bae  test    al, 1
0x140017bb0  jnz     loc_140017C97
0x140017bb6  test    esi, esi
0x140017bb8  jz      loc_140017CF9
0x140017bbe  mov     qword ptr [rsp+0A8h+Interval], 0FFFFFFFFFFFFD8F0h
0x140017bca  call    Feature_RTOFRS__private_IsEnabledDeviceUsageNoInline
0x140017bcf  test    eax, eax
0x140017bd1  jz      short loc_140017BDC
0x140017bd3  mov     eax, r12d
0x140017bd6  sub     eax, esi
0x140017bd8  cmp     eax, ebp
0x140017bda  jnb     short loc_140017BF9
0x140017bdc  lea     r8, [rsp+0A8h+Interval]; Interval
0x140017be4  xor     edx, edx; Alertable
0x140017be6  xor     ecx, ecx; WaitMode
0x140017be8  call    cs:__imp_KeDelayExecutionThread
0x140017bef  nop     dword ptr [rax+rax+00h]
0x140017bf4  jmp     loc_140017C7D
0x140017bf9  test    r15, r15
0x140017bfc  jnz     short loc_140017C3E
0x140017bfe  lea     r8d, [r15+4]
0x140017c02  lea     rdx, [rsp+0A8h+Event]
0x140017c07  lea     rcx, Controller_HighResTimerCompletion
0x140017c0e  call    cs:__imp_ExAllocateTimer
0x140017c15  nop     dword ptr [rax+rax+00h]
0x140017c1a  mov     r15, rax
0x140017c1d  test    rax, rax
0x140017c20  jz      loc_140017CEF
0x140017c26  xor     r8d, r8d; State
0x140017c29  lea     rcx, [rsp+0A8h+Event]; Event
0x140017c2e  lea     edx, [r8+1]; Type
0x140017c32  call    cs:__imp_KeInitializeEvent
0x140017c39  nop     dword ptr [rax+rax+00h]
0x140017c3e  mov     rdx, qword ptr [rsp+0A8h+Interval]
0x140017c46  xor     r9d, r9d
0x140017c49  xor     r8d, r8d
0x140017c4c  mov     rcx, r15
0x140017c4f  call    cs:__imp_ExSetTimer
0x140017c56  nop     dword ptr [rax+rax+00h]
0x140017c5b  xor     r9d, r9d; Alertable
0x140017c5e  mov     [rsp+0A8h+Timeout], 0; Timeout
0x140017c67  xor     r8d, r8d; WaitMode
0x140017c6a  lea     rcx, [rsp+0A8h+Event]; Object
0x140017c6f  xor     edx, edx; WaitReason
0x140017c71  call    cs:__imp_KeWaitForSingleObject
0x140017c78  nop     dword ptr [rax+rax+00h]
0x140017c7d  lea     rdx, [r14+4]
0x140017c81  mov     rcx, rdi
0x140017c84  dec     esi
0x140017c86  call    XilRegister_ReadUlong
0x140017c8b  test    al, 1
0x140017c8d  jz      loc_140017BB6
0x140017c93  lea     rbx, [rdi+8]
0x140017c97  call    Feature_RTOFRS__private_IsEnabledDeviceUsageNoInline
0x140017c9c  test    eax, eax
0x140017c9e  jnz     loc_140017DF8
0x140017ca4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140017cab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017cb2  jz      loc_140017EB1
0x140017cb8  mov     rcx, [rbx]
0x140017cbb  lea     rax, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x140017cc2  mov     r9d, 3Ch ; '<'
0x140017cc8  mov     [rsp+0A8h+var_78], 1
0x140017cd0  sub     ebp, esi
0x140017cd2  mov     dl, 4
0x140017cd4  mov     [rsp+0A8h+var_80], ebp
0x140017cd8  mov     rcx, [rcx+48h]
0x140017cdc  lea     r8d, [r9-36h]
0x140017ce0  mov     [rsp+0A8h+Timeout], rax
0x140017ce5  call    WPP_RECORDER_SF_DD
0x140017cea  jmp     loc_140017EB1
0x140017cef  mov     ebx, 0C000009Ah
0x140017cf4  jmp     loc_140017EB3
0x140017cf9  call    Feature_RTOFRS__private_IsEnabledDeviceUsageNoInline
0x140017cfe  test    eax, eax
0x140017d00  jnz     short loc_140017D44
0x140017d02  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140017d09  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017d10  jz      loc_140017DEE
0x140017d16  mov     rcx, [rdi+8]
0x140017d1a  lea     rax, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x140017d21  mov     r9d, 3Eh ; '>'
0x140017d27  mov     [rsp+0A8h+var_80], ebp
0x140017d2b  mov     dl, 2
0x140017d2d  mov     [rsp+0A8h+Timeout], rax
0x140017d32  mov     rcx, [rcx+48h]
0x140017d36  lea     r8d, [r9-38h]
0x140017d3a  call    WPP_RECORDER_SF_d
0x140017d3f  jmp     loc_140017DEE
0x140017d44  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140017d4b  nop     dword ptr [rax+rax+00h]
0x140017d50  mov     rcx, rax
0x140017d53  mov     rax, 346DC5D63886594Bh
0x140017d5d  sub     rcx, r13
0x140017d60  mul     rcx
0x140017d63  mov     rbx, rdx
0x140017d66  shr     rbx, 0Bh
0x140017d6a  mov     rax, [rdi+8]; __annotation("Debug", "TelemetryAssert", "FALSE", "Controller failed to Stop. Parameter2 is delay in milliseconds")
0x140017d6e  cmp     dword ptr [rax+284h], 1
0x140017d75  jnz     short loc_140017D8C
0x140017d77  movzx   edx, word ptr [rax+288h]
0x140017d7e  movzx   eax, word ptr [rax+28Ch]
0x140017d85  shl     edx, 10h
0x140017d88  or      edx, eax
0x140017d8a  jmp     short loc_140017D8E
0x140017d8c  xor     edx, edx
0x140017d8e  lea     r9, aControllerFail; "Controller failed to Stop. Parameter2 i"...
0x140017d95  mov     r8d, ebx
0x140017d98  lea     rcx, aUsbxhciSys_0; "USBXHCI.SYS"
0x140017d9f  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140017da4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140017dab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017db2  jz      short loc_140017DE2
0x140017db4  mov     rcx, [rdi+8]
0x140017db8  lea     rax, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x140017dbf  mov     r9d, 3Dh ; '='
0x140017dc5  mov     [rsp+0A8h+var_78], ebx
0x140017dc9  mov     [rsp+0A8h+var_80], r12d
0x140017dce  mov     dl, 2
0x140017dd0  mov     [rsp+0A8h+Timeout], rax
0x140017dd5  mov     rcx, [rcx+48h]
0x140017dd9  lea     r8d, [r9-37h]
0x140017ddd  call    WPP_RECORDER_SF_DD
0x140017de2  mov     rdx, [rdi+8]
0x140017de6  mov     r8d, ebx
0x140017de9  call    Etw_ReportFailedControllerStop
0x140017dee  mov     ebx, 0C0000001h
0x140017df3  jmp     loc_140017EB3
0x140017df8  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140017dff  nop     dword ptr [rax+rax+00h]
0x140017e04  mov     rcx, rax
0x140017e07  sub     r12d, esi
0x140017e0a  sub     rcx, r13
0x140017e0d  mov     rax, 346DC5D63886594Bh
0x140017e17  mul     rcx
0x140017e1a  mov     r14, rdx
0x140017e1d  shr     r14, 0Bh
0x140017e21  cmp     r12d, ebp
0x140017e24  jbe     short loc_140017E6B
0x140017e26  mov     rax, [rdi+8]; __annotation("Debug", "TelemetryAssert", "FALSE", "Controller took longer than expected to Stop. Parameter2 is delay in milliseconds")
0x140017e2a  cmp     dword ptr [rax+284h], 1
0x140017e31  jnz     short loc_140017E48
0x140017e33  movzx   edx, word ptr [rax+288h]
0x140017e3a  movzx   eax, word ptr [rax+28Ch]
0x140017e41  shl     edx, 10h
0x140017e44  or      edx, eax
0x140017e46  jmp     short loc_140017E4A
0x140017e48  xor     edx, edx
0x140017e4a  lea     r9, aControllerTook; "Controller took longer than expected to"...
0x140017e51  mov     r8d, r14d
0x140017e54  lea     rcx, aUsbxhciSys_0; "USBXHCI.SYS"
0x140017e5b  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140017e60  mov     rdx, [rbx]
0x140017e63  mov     r8d, r14d
0x140017e66  call    Etw_ReportDelayedControllerStop
0x140017e6b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140017e72  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017e79  jz      short loc_140017EB1
0x140017e7b  mov     rcx, [rbx]
0x140017e7e  lea     rax, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x140017e85  mov     [rsp+0A8h+var_70], r14d
0x140017e8a  mov     r9d, 3Bh ; ';'
0x140017e90  mov     [rsp+0A8h+var_78], 1
0x140017e98  mov     dl, 4
0x140017e9a  mov     [rsp+0A8h+var_80], r12d
0x140017e9f  mov     rcx, [rcx+48h]
0x140017ea3  lea     r8d, [r9-35h]
0x140017ea7  mov     [rsp+0A8h+Timeout], rax
0x140017eac  call    WPP_RECORDER_SF_ddd
0x140017eb1  xor     ebx, ebx
0x140017eb3  call    Feature_RTOFRS__private_IsEnabledDeviceUsageNoInline
0x140017eb8  test    eax, eax
0x140017eba  jz      short loc_140017ED8
0x140017ebc  test    r15, r15
0x140017ebf  jz      short loc_140017ED8
0x140017ec1  xor     r9d, r9d
0x140017ec4  xor     r8d, r8d
0x140017ec7  xor     edx, edx
0x140017ec9  mov     rcx, r15
0x140017ecc  call    cs:__imp_ExDeleteTimer
0x140017ed3  nop     dword ptr [rax+rax+00h]
0x140017ed8  mov     eax, ebx
0x140017eda  add     rsp, 68h
0x140017ede  pop     r15
0x140017ee0  pop     r14
0x140017ee2  pop     r13
0x140017ee4  pop     r12
0x140017ee6  pop     rdi
0x140017ee7  pop     rsi
0x140017ee8  pop     rbp
0x140017ee9  pop     rbx
0x140017eea  retn
```
