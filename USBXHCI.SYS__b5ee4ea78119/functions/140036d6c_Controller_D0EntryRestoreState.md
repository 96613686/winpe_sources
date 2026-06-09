# Controller_D0EntryRestoreState

- ea: `0x140036d6c`
- end: `0x1400370b7`
- name: `Controller_D0EntryRestoreState`
- size: `843`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140018d90`

## callees

- `0x14001ac48`
- `0x14001ad0c`
- `0x14001bb78`
- `0x14001d118`
- `0x14001f830`
- `0x14002e028`
- `0x1400326e0`
- `0x140033bcc`
- `0x140036d6c`
- `0x140041f48`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140036ec0`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140036f5f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140036fa2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140036fd2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140037019`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140036ec0`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140036f5f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140036fa2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140036fd2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140037019`
- `ntoskrnl!KeDelayExecutionThread` at `0x140036f92`
- `ntoskrnl!KeDelayExecutionThread` at `0x140036f92`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036d93`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036d93`

## string_xrefs

- `0x140036db2`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall Controller_D0EntryRestoreState(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  __int64 v5; // rcx
  __int64 v6; // rbp
  __int64 v7; // r14
  __int16 Ulong; // ax
  ULONGLONG v9; // rcx
  __int64 v10; // r8
  int v11; // r9d
  int v12; // ebx
  ULONGLONG UnbiasedInterruptTime; // rsi
  int v14; // eax
  int v15; // edx
  __int16 v16; // ax
  unsigned __int64 v17; // rcx
  ULONGLONG v18; // rax
  unsigned __int64 v19; // rdx
  int v20; // ebx
  ULONGLONG v21; // rax
  int v22; // r8d
  unsigned __int64 v23; // rdx
  int v25; // [rsp+20h] [rbp-58h]
  union _LARGE_INTEGER Interval; // [rsp+80h] [rbp+8h] BYREF

  v3 = *(_BYTE *)(a1 + 1041) == 0;
  Interval.QuadPart = 0;
  if ( !v3 && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\controller.c",
      4286);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 4, 4, 113, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(a1, USBXHCI_ETW_EVENT_CONTROLLER_RESTORE_STATE_START, a3, *(_QWORD *)(a1 + 8));
  v5 = *(_QWORD *)(a1 + 88);
  v6 = *(_QWORD *)(v5 + 32);
  v7 = v6 + 4;
  Ulong = XilRegister_ReadUlong(v5, v6 + 4);
  if ( (Ulong & 1) != 0 )
  {
    if ( (Ulong & 0x100) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v11 = 115;
      goto LABEL_11;
    }
    if ( (Ulong & 0x200) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v11 = 116;
      goto LABEL_11;
    }
    v12 = 20;
    XilRegister_WriteUlong(*(_QWORD *)(a1 + 88), *(_QWORD *)(*(_QWORD *)(a1 + 88) + 32LL) + 20LL, 2);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 4, 4, 117, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    v14 = XilRegister_ReadUlong(*(_QWORD *)(a1 + 88), v6);
    XilRegister_WriteUlong(*(_QWORD *)(a1 + 88), v6, v14 | 0x200u);
    if ( (*(_DWORD *)(a1 + 744) & 0x40000000) != 0 )
    {
      v12 = 500;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 4;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 72),
          v15,
          4,
          118,
          (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
          100);
      }
    }
    while ( 1 )
    {
      v16 = XilRegister_ReadUlong(*(_QWORD *)(a1 + 88), v7);
      if ( (v16 & 0x400) != 0 )
        break;
      if ( (v16 & 0x200) == 0 )
      {
        v18 = KeQueryUnbiasedInterruptTime();
        v9 = v18;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v19 = (v18 - UnbiasedInterruptTime) / 0xA;
          LOBYTE(v19) = 4;
          WPP_RECORDER_SF_I(*(_QWORD *)(a1 + 72), v19, v10, 120, v25, (v18 - UnbiasedInterruptTime) / 0xA);
        }
        v20 = 0;
        goto LABEL_38;
      }
      if ( !v12 )
      {
        v17 = KeQueryUnbiasedInterruptTime() - UnbiasedInterruptTime;
LABEL_30:
        Controller_LogRestoreTimeout(a1, v17 / 0x2710);
        goto LABEL_37;
      }
      if ( (*(_DWORD *)(a1 + 744) & 0x40000000) != 0 )
      {
        v17 = KeQueryUnbiasedInterruptTime() - UnbiasedInterruptTime;
        if ( v17 >= 0xF4240 )
          goto LABEL_30;
      }
      Interval.QuadPart = -2000;
      KeDelayExecutionThread(0, 0, &Interval);
      --v12;
    }
    v21 = KeQueryUnbiasedInterruptTime();
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = (v21 - UnbiasedInterruptTime) / 0x2710;
      LOBYTE(v23) = 2;
      WPP_RECORDER_SF_I(*(_QWORD *)(a1 + 72), v23, v22, 119, v25, (v21 - UnbiasedInterruptTime) / 0x2710);
    }
    XilRegister_WriteUlong(*(_QWORD *)(a1 + 88), v7, 1024);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = 114;
LABEL_11:
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 2, 4, v11, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
  }
LABEL_37:
  v20 = -1073741630;
LABEL_38:
  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 8) != 0 )
    McTemplateK0pq_EtwWriteTransfer(
      v9,
      USBXHCI_ETW_EVENT_CONTROLLER_RESTORE_STATE_COMPLETE,
      v10,
      *(_QWORD *)(a1 + 8),
      v20);
  if ( v20 < 0 )
  {
    ++*(_DWORD *)(a1 + 880);
    ++*(_DWORD *)(a1 + 948);
    *(_BYTE *)(a1 + 872) = 1;
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x140036d6c  mov     rax, rsp
0x140036d6f  push    rbx
0x140036d70  push    rbp
0x140036d71  push    rsi
0x140036d72  push    rdi
0x140036d73  push    r12
0x140036d75  push    r13
0x140036d77  push    r14
0x140036d79  push    r15
0x140036d7b  sub     rsp, 38h
0x140036d7f  cmp     byte ptr [rcx+411h], 0
0x140036d86  mov     rdi, rcx
0x140036d89  mov     qword ptr [rax+8], 0
0x140036d91  jz      short loc_140036DBE
0x140036d93  call    cs:__imp_KeGetCurrentIrql
0x140036d9a  nop     dword ptr [rax+rax+00h]
0x140036d9f  test    al, al
0x140036da1  jz      short loc_140036DBE
0x140036da3  mov     r9d, 10BEh
0x140036da9  lea     r8, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140036db0  xor     edx, edx
0x140036db2  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x140036db9  call    Debug_FreAssertMsg
0x140036dbe  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036dc5  mov     r12d, 4
0x140036dcb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140036dd2  lea     r13, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140036dd9  jz      short loc_140036DF4
0x140036ddb  mov     rcx, [rdi+48h]
0x140036ddf  lea     r9d, [r12+6Dh]
0x140036de4  mov     r8d, r12d
0x140036de7  mov     [rsp+78h+var_58], r13
0x140036dec  mov     dl, r12b
0x140036def  call    WPP_RECORDER_SF_
0x140036df4  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 8
0x140036dfb  jz      short loc_140036E0D
0x140036dfd  mov     r9, [rdi+8]
0x140036e01  lea     rdx, USBXHCI_ETW_EVENT_CONTROLLER_RESTORE_STATE_START
0x140036e08  call    McTemplateK0p_EtwWriteTransfer
0x140036e0d  mov     rcx, [rdi+58h]
0x140036e11  mov     rbp, [rcx+20h]
0x140036e15  lea     r14, [rbp+4]
0x140036e19  mov     rdx, r14
0x140036e1c  call    XilRegister_ReadUlong
0x140036e21  test    al, 1
0x140036e23  jnz     short loc_140036E50
0x140036e25  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036e2c  jz      loc_14003706A
0x140036e32  mov     r9d, 72h ; 'r'
0x140036e38  mov     rcx, [rdi+48h]
0x140036e3c  mov     r8d, r12d
0x140036e3f  mov     dl, 2
0x140036e41  mov     [rsp+78h+var_58], r13
0x140036e46  call    WPP_RECORDER_SF_
0x140036e4b  jmp     loc_14003706A
0x140036e50  bt      eax, 8
0x140036e54  jnb     short loc_140036E6B
0x140036e56  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036e5d  jz      loc_14003706A
0x140036e63  mov     r9d, 73h ; 's'
0x140036e69  jmp     short loc_140036E38
0x140036e6b  bt      eax, 9
0x140036e6f  jnb     short loc_140036E86
0x140036e71  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036e78  jz      loc_14003706A
0x140036e7e  mov     r9d, 74h ; 't'
0x140036e84  jmp     short loc_140036E38
0x140036e86  mov     rcx, [rdi+58h]
0x140036e8a  mov     ebx, 14h
0x140036e8f  mov     rdx, [rcx+20h]
0x140036e93  lea     r8d, [rbx-12h]
0x140036e97  add     rdx, rbx
0x140036e9a  call    XilRegister_WriteUlong
0x140036e9f  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036ea6  jz      short loc_140036EC0
0x140036ea8  mov     rcx, [rdi+48h]
0x140036eac  lea     r9d, [rbx+61h]
0x140036eb0  mov     r8d, r12d
0x140036eb3  mov     [rsp+78h+var_58], r13
0x140036eb8  mov     dl, r12b
0x140036ebb  call    WPP_RECORDER_SF_
0x140036ec0  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140036ec7  nop     dword ptr [rax+rax+00h]
0x140036ecc  mov     rcx, [rdi+58h]
0x140036ed0  mov     rdx, rbp
0x140036ed3  mov     rsi, rax
0x140036ed6  call    XilRegister_ReadUlong
0x140036edb  mov     rcx, [rdi+58h]
0x140036edf  bts     eax, 9
0x140036ee3  mov     r8d, eax
0x140036ee6  mov     rdx, rbp
0x140036ee9  call    XilRegister_WriteUlong
0x140036eee  mov     ecx, [rdi+2E8h]
0x140036ef4  bt      rcx, 1Eh
0x140036ef9  jnb     short loc_140036F2B
0x140036efb  mov     ebx, 1F4h
0x140036f00  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036f07  jz      short loc_140036F2B
0x140036f09  mov     rcx, [rdi+48h]
0x140036f0d  mov     r9d, 76h ; 'v'
0x140036f13  mov     dword ptr [rsp+78h+var_50], 64h ; 'd'
0x140036f1b  mov     r8d, r12d
0x140036f1e  mov     dl, r12b
0x140036f21  mov     [rsp+78h+var_58], r13
0x140036f26  call    WPP_RECORDER_SF_d
0x140036f2b  mov     ebp, 400h
0x140036f30  mov     rcx, [rdi+58h]
0x140036f34  mov     rdx, r14
0x140036f37  call    XilRegister_ReadUlong
0x140036f3c  test    ebp, eax
0x140036f3e  jnz     loc_140037019
0x140036f44  bt      eax, 9
0x140036f48  jnb     loc_140036FD2
0x140036f4e  test    ebx, ebx
0x140036f50  jz      short loc_140036FA2
0x140036f52  mov     eax, [rdi+2E8h]
0x140036f58  bt      rax, 1Eh
0x140036f5d  jnb     short loc_140036F7A
0x140036f5f  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140036f66  nop     dword ptr [rax+rax+00h]
0x140036f6b  mov     rcx, rax
0x140036f6e  sub     rcx, rsi
0x140036f71  cmp     rcx, 0F4240h
0x140036f78  jnb     short loc_140036FB4
0x140036f7a  lea     r8, [rsp+78h+Interval]; Interval
0x140036f82  mov     qword ptr [rsp+78h+Interval], 0FFFFFFFFFFFFF830h
0x140036f8e  xor     edx, edx; Alertable
0x140036f90  xor     ecx, ecx; WaitMode
0x140036f92  call    cs:__imp_KeDelayExecutionThread
0x140036f99  nop     dword ptr [rax+rax+00h]
0x140036f9e  dec     ebx
0x140036fa0  jmp     short loc_140036F30
0x140036fa2  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140036fa9  nop     dword ptr [rax+rax+00h]
0x140036fae  mov     rcx, rax
0x140036fb1  sub     rcx, rsi
0x140036fb4  mov     rax, 346DC5D63886594Bh
0x140036fbe  mul     rcx
0x140036fc1  mov     rcx, rdi
0x140036fc4  shr     rdx, 0Bh
0x140036fc8  call    Controller_LogRestoreTimeout
0x140036fcd  jmp     loc_14003706A
0x140036fd2  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140036fd9  nop     dword ptr [rax+rax+00h]
0x140036fde  mov     rcx, rax
0x140036fe1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140036fe8  jz      short loc_140037015
0x140036fea  sub     rcx, rsi
0x140036fed  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140036ff7  mul     rcx
0x140036ffa  mov     rcx, [rdi+48h]
0x140036ffe  mov     r9d, 78h ; 'x'
0x140037004  shr     rdx, 3
0x140037008  mov     [rsp+78h+var_50], rdx
0x14003700d  mov     dl, r12b
0x140037010  call    WPP_RECORDER_SF_I
0x140037015  xor     ebx, ebx
0x140037017  jmp     short loc_14003706F
0x140037019  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140037020  nop     dword ptr [rax+rax+00h]
0x140037025  mov     rcx, rax
0x140037028  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14003702f  jz      short loc_14003705B
0x140037031  sub     rcx, rsi
0x140037034  mov     rax, 346DC5D63886594Bh
0x14003703e  mul     rcx
0x140037041  mov     rcx, [rdi+48h]
0x140037045  mov     r9d, 77h ; 'w'
0x14003704b  shr     rdx, 0Bh
0x14003704f  mov     [rsp+78h+var_50], rdx
0x140037054  mov     dl, 2
0x140037056  call    WPP_RECORDER_SF_I
0x14003705b  mov     rcx, [rdi+58h]
0x14003705f  mov     r8d, ebp
0x140037062  mov     rdx, r14
0x140037065  call    XilRegister_WriteUlong
0x14003706a  mov     ebx, 0C00000C2h
0x14003706f  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 8
0x140037076  jz      short loc_14003708C
0x140037078  mov     r9, [rdi+8]
0x14003707c  lea     rdx, USBXHCI_ETW_EVENT_CONTROLLER_RESTORE_STATE_COMPLETE
0x140037083  mov     dword ptr [rsp+78h+var_58], ebx
0x140037087  call    McTemplateK0pq_EtwWriteTransfer
0x14003708c  test    ebx, ebx
0x14003708e  jns     short loc_1400370A3
0x140037090  inc     dword ptr [rdi+370h]
0x140037096  inc     dword ptr [rdi+3B4h]
0x14003709c  mov     byte ptr [rdi+368h], 1
0x1400370a3  mov     eax, ebx
0x1400370a5  add     rsp, 38h
0x1400370a9  pop     r15
0x1400370ab  pop     r14
0x1400370ad  pop     r13
0x1400370af  pop     r12
0x1400370b1  pop     rdi
0x1400370b2  pop     rsi
0x1400370b3  pop     rbp
0x1400370b4  pop     rbx
0x1400370b5  retn
```
