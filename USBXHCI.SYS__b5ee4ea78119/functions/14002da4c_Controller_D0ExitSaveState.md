# Controller_D0ExitSaveState

- ea: `0x14002da4c`
- end: `0x14002dd3b`
- name: `Controller_D0ExitSaveState`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140018190`

## callees

- `0x14001a214`
- `0x14001ac48`
- `0x14001bb78`
- `0x14001d118`
- `0x14001f830`
- `0x14002da4c`
- `0x14002e028`
- `0x1400326e0`
- `0x140033bcc`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002db87`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002dc1f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002dc6a`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002dcb1`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002db87`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002dc1f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002dc6a`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002dcb1`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002dc0f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002dc0f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002da71`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002da71`

## string_xrefs

- `0x14002da90`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall Controller_D0ExitSaveState(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  __int64 v5; // rcx
  int *v6; // rbx
  _DWORD *v7; // rbp
  __int16 Ulong; // ax
  ULONGLONG v9; // rcx
  __int64 v10; // r8
  int v11; // r9d
  ULONGLONG UnbiasedInterruptTime; // rsi
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  int i; // ebx
  __int16 v17; // ax
  ULONGLONG v18; // rax
  unsigned __int64 v19; // rdx
  ULONGLONG v20; // rax
  unsigned __int64 v21; // rdx
  unsigned int v22; // ebx
  ULONGLONG v23; // rax
  int v24; // r8d
  unsigned __int64 v25; // rdx
  signed __int32 v27[8]; // [rsp+0h] [rbp-58h] BYREF
  __int64 v28; // [rsp+20h] [rbp-38h]
  int v29; // [rsp+60h] [rbp+8h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+68h] [rbp+10h] BYREF

  v3 = *(_BYTE *)(a1 + 1041) == 0;
  Interval.QuadPart = 0;
  if ( !v3 && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\controller.c",
      4808);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 4, 4, 129, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(a1, USBXHCI_ETW_EVENT_CONTROLLER_SAVE_STATE_START, a3, *(_QWORD *)(a1 + 8));
  v5 = *(_QWORD *)(a1 + 88);
  v6 = *(int **)(v5 + 32);
  v7 = v6 + 1;
  Ulong = XilRegister_ReadUlong(v5, v6 + 1);
  if ( (Ulong & 1) != 0 )
  {
    if ( (Ulong & 0x100) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_36;
      v11 = 131;
      goto LABEL_11;
    }
    if ( (Ulong & 0x200) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_36;
      v11 = 132;
      goto LABEL_11;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 4, 4, 133, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    v13 = XilRegister_ReadUlong(*(_QWORD *)(a1 + 88), v6);
    v14 = *(_QWORD *)(a1 + 88);
    v15 = v13 | 0x100;
    v29 = v15;
    if ( *(_BYTE *)(*(_QWORD *)(v14 + 8) + 1041LL) )
    {
      Register_WriteSecureMmio(v14, v6, 2, &v29);
    }
    else
    {
      *v6 = v15;
      _InterlockedOr(v27, 0);
    }
    for ( i = 20; ; --i )
    {
      v17 = XilRegister_ReadUlong(*(_QWORD *)(a1 + 88), v7);
      if ( (v17 & 0x400) != 0 )
        break;
      if ( (v17 & 0x100) == 0 )
      {
        v20 = KeQueryUnbiasedInterruptTime();
        v9 = v20;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v21 = (v20 - UnbiasedInterruptTime) / 0xA;
          LOBYTE(v21) = 4;
          WPP_RECORDER_SF_I(*(_QWORD *)(a1 + 72), v21, v10, 135, v28, (v20 - UnbiasedInterruptTime) / 0xA);
        }
        v22 = 0;
        goto LABEL_37;
      }
      if ( !i )
      {
        v18 = KeQueryUnbiasedInterruptTime();
        v9 = v18;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v19 = (v18 - UnbiasedInterruptTime) / 0x2710;
          LOBYTE(v19) = 2;
          WPP_RECORDER_SF_I(*(_QWORD *)(a1 + 72), v19, v10, 136, v28, (v18 - UnbiasedInterruptTime) / 0x2710);
        }
        goto LABEL_36;
      }
      Interval.QuadPart = -2000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    v23 = KeQueryUnbiasedInterruptTime();
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = (v23 - UnbiasedInterruptTime) / 0x2710;
      LOBYTE(v25) = 2;
      WPP_RECORDER_SF_I(*(_QWORD *)(a1 + 72), v25, v24, 134, v28, (v23 - UnbiasedInterruptTime) / 0x2710);
    }
    XilRegister_WriteUlong(*(_QWORD *)(a1 + 88), v7, 1024);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = 130;
LABEL_11:
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 2, 4, v11, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
  }
LABEL_36:
  v22 = -1073741630;
LABEL_37:
  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 8) != 0 )
    McTemplateK0pq_EtwWriteTransfer(v9, USBXHCI_ETW_EVENT_CONTROLLER_SAVE_STATE_COMPLETE, v10, *(_QWORD *)(a1 + 8), v22);
  return v22;
}

```

## disassembly

```asm
0x14002da4c  mov     [rsp+arg_10], rbx
0x14002da51  push    rbp
0x14002da52  push    rsi
0x14002da53  push    rdi
0x14002da54  push    r12
0x14002da56  push    r14
0x14002da58  sub     rsp, 30h
0x14002da5c  cmp     byte ptr [rcx+411h], 0
0x14002da63  mov     rdi, rcx
0x14002da66  mov     qword ptr [rsp+58h+Interval], 0
0x14002da6f  jz      short loc_14002DA9C
0x14002da71  call    cs:__imp_KeGetCurrentIrql
0x14002da78  nop     dword ptr [rax+rax+00h]
0x14002da7d  test    al, al
0x14002da7f  jz      short loc_14002DA9C
0x14002da81  mov     r9d, 12C8h
0x14002da87  lea     r8, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14002da8e  xor     edx, edx
0x14002da90  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x14002da97  call    Debug_FreAssertMsg
0x14002da9c  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002daa3  mov     r12d, 4
0x14002daa9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002dab0  lea     rsi, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14002dab7  jz      short loc_14002DAD2
0x14002dab9  mov     rcx, [rdi+48h]
0x14002dabd  lea     r9d, [r12+7Dh]
0x14002dac2  mov     r8d, r12d
0x14002dac5  mov     [rsp+58h+var_38], rsi
0x14002daca  mov     dl, r12b
0x14002dacd  call    WPP_RECORDER_SF_
0x14002dad2  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 8
0x14002dad9  jz      short loc_14002DAEB
0x14002dadb  mov     r9, [rdi+8]
0x14002dadf  lea     rdx, USBXHCI_ETW_EVENT_CONTROLLER_SAVE_STATE_START
0x14002dae6  call    McTemplateK0p_EtwWriteTransfer
0x14002daeb  mov     rcx, [rdi+58h]
0x14002daef  mov     rbx, [rcx+20h]
0x14002daf3  lea     rbp, [rbx+4]
0x14002daf7  mov     rdx, rbp
0x14002dafa  call    XilRegister_ReadUlong
0x14002daff  test    al, 1
0x14002db01  jnz     short loc_14002DB2E
0x14002db03  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002db0a  jz      loc_14002DD05
0x14002db10  mov     r9d, 82h
0x14002db16  mov     rcx, [rdi+48h]
0x14002db1a  mov     r8d, r12d
0x14002db1d  mov     dl, 2
0x14002db1f  mov     [rsp+58h+var_38], rsi
0x14002db24  call    WPP_RECORDER_SF_
0x14002db29  jmp     loc_14002DD05
0x14002db2e  bt      eax, 8
0x14002db32  jnb     short loc_14002DB49
0x14002db34  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002db3b  jz      loc_14002DD05
0x14002db41  mov     r9d, 83h
0x14002db47  jmp     short loc_14002DB16
0x14002db49  bt      eax, 9
0x14002db4d  jnb     short loc_14002DB64
0x14002db4f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002db56  jz      loc_14002DD05
0x14002db5c  mov     r9d, 84h
0x14002db62  jmp     short loc_14002DB16
0x14002db64  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002db6b  jz      short loc_14002DB87
0x14002db6d  mov     rcx, [rdi+48h]
0x14002db71  mov     r9d, 85h
0x14002db77  mov     r8d, r12d
0x14002db7a  mov     [rsp+58h+var_38], rsi
0x14002db7f  mov     dl, r12b
0x14002db82  call    WPP_RECORDER_SF_
0x14002db87  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14002db8e  nop     dword ptr [rax+rax+00h]
0x14002db93  mov     rcx, [rdi+58h]
0x14002db97  mov     rdx, rbx
0x14002db9a  mov     rsi, rax
0x14002db9d  call    XilRegister_ReadUlong
0x14002dba2  mov     rcx, [rdi+58h]
0x14002dba6  bts     eax, 8
0x14002dbaa  mov     [rsp+58h+arg_0], eax
0x14002dbae  mov     r8, [rcx+8]
0x14002dbb2  cmp     byte ptr [r8+411h], 0
0x14002dbba  jz      short loc_14002DBD1
0x14002dbbc  lea     r9, [rsp+58h+arg_0]
0x14002dbc1  mov     r8d, 2
0x14002dbc7  mov     rdx, rbx
0x14002dbca  call    Register_WriteSecureMmio
0x14002dbcf  jmp     short loc_14002DBD8
0x14002dbd1  mov     [rbx], eax
0x14002dbd3  lock or [rsp+58h+var_58], 0
0x14002dbd8  mov     ebx, 14h
0x14002dbdd  mov     rcx, [rdi+58h]
0x14002dbe1  mov     rdx, rbp
0x14002dbe4  call    XilRegister_ReadUlong
0x14002dbe9  bt      eax, 0Ah
0x14002dbed  jb      loc_14002DCB1
0x14002dbf3  bt      eax, 8
0x14002dbf7  jnb     short loc_14002DC6A
0x14002dbf9  test    ebx, ebx
0x14002dbfb  jz      short loc_14002DC1F
0x14002dbfd  lea     r8, [rsp+58h+Interval]; Interval
0x14002dc02  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFF830h
0x14002dc0b  xor     edx, edx; Alertable
0x14002dc0d  xor     ecx, ecx; WaitMode
0x14002dc0f  call    cs:__imp_KeDelayExecutionThread
0x14002dc16  nop     dword ptr [rax+rax+00h]
0x14002dc1b  dec     ebx
0x14002dc1d  jmp     short loc_14002DBDD
0x14002dc1f  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14002dc26  nop     dword ptr [rax+rax+00h]
0x14002dc2b  mov     rcx, rax
0x14002dc2e  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002dc35  jz      loc_14002DD05
0x14002dc3b  sub     rcx, rsi
0x14002dc3e  mov     rax, 346DC5D63886594Bh
0x14002dc48  mul     rcx
0x14002dc4b  mov     rcx, [rdi+48h]
0x14002dc4f  mov     r9d, 88h
0x14002dc55  shr     rdx, 0Bh
0x14002dc59  mov     [rsp+58h+var_30], rdx
0x14002dc5e  mov     dl, 2
0x14002dc60  call    WPP_RECORDER_SF_I
0x14002dc65  jmp     loc_14002DD05
0x14002dc6a  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14002dc71  nop     dword ptr [rax+rax+00h]
0x14002dc76  mov     rcx, rax
0x14002dc79  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002dc80  jz      short loc_14002DCAD
0x14002dc82  sub     rcx, rsi
0x14002dc85  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14002dc8f  mul     rcx
0x14002dc92  mov     rcx, [rdi+48h]
0x14002dc96  mov     r9d, 87h
0x14002dc9c  shr     rdx, 3
0x14002dca0  mov     [rsp+58h+var_30], rdx
0x14002dca5  mov     dl, r12b
0x14002dca8  call    WPP_RECORDER_SF_I
0x14002dcad  xor     ebx, ebx
0x14002dcaf  jmp     short loc_14002DD0A
0x14002dcb1  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14002dcb8  nop     dword ptr [rax+rax+00h]
0x14002dcbd  mov     rcx, rax
0x14002dcc0  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002dcc7  jz      short loc_14002DCF3
0x14002dcc9  sub     rcx, rsi
0x14002dccc  mov     rax, 346DC5D63886594Bh
0x14002dcd6  mul     rcx
0x14002dcd9  mov     rcx, [rdi+48h]
0x14002dcdd  mov     r9d, 86h
0x14002dce3  shr     rdx, 0Bh
0x14002dce7  mov     [rsp+58h+var_30], rdx
0x14002dcec  mov     dl, 2
0x14002dcee  call    WPP_RECORDER_SF_I
0x14002dcf3  mov     rcx, [rdi+58h]
0x14002dcf7  mov     r8d, 400h
0x14002dcfd  mov     rdx, rbp
0x14002dd00  call    XilRegister_WriteUlong
0x14002dd05  mov     ebx, 0C00000C2h
0x14002dd0a  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 8
0x14002dd11  jz      short loc_14002DD27
0x14002dd13  mov     r9, [rdi+8]
0x14002dd17  lea     rdx, USBXHCI_ETW_EVENT_CONTROLLER_SAVE_STATE_COMPLETE
0x14002dd1e  mov     dword ptr [rsp+58h+var_38], ebx
0x14002dd22  call    McTemplateK0pq_EtwWriteTransfer
0x14002dd27  mov     eax, ebx
0x14002dd29  mov     rbx, [rsp+58h+arg_10]
0x14002dd2e  add     rsp, 30h
0x14002dd32  pop     r14
0x14002dd34  pop     r12
0x14002dd36  pop     rdi
0x14002dd37  pop     rsi
0x14002dd38  pop     rbp
0x14002dd39  retn
```
