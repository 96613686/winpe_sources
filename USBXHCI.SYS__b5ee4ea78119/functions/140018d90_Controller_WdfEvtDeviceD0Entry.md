# Controller_WdfEvtDeviceD0Entry

- ea: `0x140018d90`
- end: `0x14001940a`
- name: `Controller_WdfEvtDeviceD0Entry`
- size: `1658`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000c264`
- `0x140017adc`
- `0x140018d90`
- `0x140019410`
- `0x140019828`
- `0x14001a928`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001adfc`
- `0x14001afa8`
- `0x14001b3b8`
- `0x14001b8ac`
- `0x14001b908`
- `0x14001bb78`
- `0x14001c858`
- `0x14001f830`
- `0x14002b300`
- `0x14002e8b4`
- `0x14002e958`
- `0x1400327a4`
- `0x140036d6c`
- `0x14003b694`
- `0x14003b7d0`
- `0x14003c1d4`
- `0x14003c59c`
- `0x140059970`
- `0x1400599b0`
- `0x140074504`
- `0x140077520`
- `0x14008252c`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x140018fc9`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140018fc9`
- `ntoskrnl!KeGetCurrentIrql` at `0x140018df1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140018df1`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x140018ec4`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x140018ec4`

## string_xrefs

- `0x140018e10`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall Controller_WdfEvtDeviceD0Entry(__int64 a1, unsigned int a2)
{
  unsigned int v4; // esi
  __int64 v5; // r12
  __int64 v6; // rbx
  int PreProcessedSystemPowerAction; // edi
  __int64 v8; // rdx
  char v9; // bp
  int v10; // edi
  __int64 v11; // rax
  int v12; // eax
  int v13; // edx
  int v14; // eax
  int v15; // r9d
  unsigned __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int i; // r12d
  int v20; // eax
  int v21; // edx
  int v22; // eax
  int v23; // edx
  int v24; // r9d
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // r8d
  __int64 v28; // rdx
  char v30; // [rsp+41h] [rbp-77h]
  int v31; // [rsp+44h] [rbp-74h]
  char v32; // [rsp+48h] [rbp-70h]
  _BYTE v33[12]; // [rsp+50h] [rbp-68h] BYREF

  v4 = 0;
  *(_QWORD *)v33 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_14006C2C0);
  v5 = *(_QWORD *)v33;
  v6 = *(_QWORD *)(*(_QWORD *)v33 + 8LL);
  if ( *(_BYTE *)(v6 + 1041) && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\controller.c",
      2235);
  Controller_LogDiagnosticsOnD0Entry(a1, a2);
  v32 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 3104))(WdfDriverGlobals, a1);
  PreProcessedSystemPowerAction = Controller_GetPreProcessedSystemPowerAction(v6);
  v31 = PreProcessedSystemPowerAction;
  if ( (unsigned int)XilRegister_ReadUlong(*(_QWORD *)(v6 + 88), *(_QWORD *)(*(_QWORD *)(v6 + 88) + 24LL)) == -1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(v6 + 72), v8, 4, 64, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
    }
    v9 = 1;
    v10 = -1073741823;
    goto LABEL_64;
  }
  v30 = 0;
  if ( *(_DWORD *)(v6 + 864) && *(_QWORD *)(v6 + 1296) )
    SleepstudyHelper_ComponentActive();
  if ( PreProcessedSystemPowerAction == 2 )
  {
    v11 = *(_QWORD *)(v6 + 824);
    if ( v11 && *(_DWORD *)(v11 + 584) == 4 )
    {
      v12 = Register_ControllerStop(*(_QWORD *)(v6 + 88));
      if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v6 + 72),
          v13,
          4,
          65,
          (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
          v12);
      }
    }
    else
    {
      v14 = Register_BiosHandoff(*(_QWORD *)(v6 + 88));
      v10 = v14;
      if ( v14 < 0 )
      {
        v4 = 10;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v15 = 66;
          goto LABEL_23;
        }
LABEL_63:
        v9 = 0;
LABEL_64:
        DeviceSlot_DisableAllDeviceSlots(*(_QWORD *)(v6 + 136));
        if ( v9 )
        {
          if ( (*(_DWORD *)(v5 + 28) & 0x10) == 0 )
            Etw_ReportFatalError(v4, v6, 0, 4150, v4, v10);
          LOBYTE(v25) = 1;
        }
        else
        {
          Controller_ReportFatalErrorEx(v6, 0, 4124, v4, v10, 0, 0, 0);
          v25 = 0;
        }
        Controller_SetControllerGone(v6, v25);
        goto LABEL_85;
      }
    }
    DeviceSlot_D0EntryCleanupState(*(_QWORD *)(v6 + 136), a2);
    v14 = Register_ControllerReset(*(_QWORD *)(v6 + 88), 0);
    v10 = v14;
    if ( v14 < 0 )
    {
      v4 = 11;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v15 = 67;
LABEL_23:
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v6 + 72),
          v8,
          4,
          v15,
          (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
          v14);
        goto LABEL_63;
      }
      goto LABEL_63;
    }
    v30 = 1;
  }
  if ( !*(_BYTE *)(v6 + 840) )
  {
    *(_DWORD *)(v6 + 844) = KeQueryTimeIncrement();
    v16 = ((unsigned int)(**(_DWORD **)(*(_QWORD *)(v6 + 88) + 40LL) + 1) >> 3) & 0x7FF;
    v8 = _InterlockedExchange64(
           (volatile __int64 *)(v6 + 832),
           (v16 >> 11) | ((MEMORY[0xFFFFF78000000320] * *(unsigned int *)(v6 + 844) / 10000LL - v16) << 21));
    *(_BYTE *)(v6 + 840) = 1;
  }
  LOBYTE(v8) = 1;
  Controller_ExecuteHSICDisconnectInU3Workaround(v6, v8);
  if ( (*(_BYTE *)(v6 + 744) & 1) != 0 )
  {
    LOBYTE(v17) = 1;
    Controller_ExecuteKBLPowerTransitionWorkaround(v6, v17);
  }
  v4 = 5;
  for ( i = 1; i <= 2; ++i )
  {
    if ( i == 2
      || (*(_BYTE *)(v6 + 736) & 2) != 0
      || *(_BYTE *)(v6 + 796)
      || a2 == 5
      || (unsigned int)Controller_GetPreProcessedSystemPowerAction(v6) == 2
      || (*(_BYTE *)(v6 + 744) & 8) != 0 && (unsigned __int8)Controller_InUseByDebugger(v6) )
    {
      LOBYTE(v18) = 0;
    }
    else
    {
      Register_D0EntryPreRestoreState(*(_QWORD *)(v6 + 88));
      LOBYTE(v18) = 1;
    }
    v20 = Interrupter_D0Entry(*(_QWORD *)(v6 + 128), a2, v18);
    v10 = v20;
    if ( v20 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      v24 = 68;
      goto LABEL_61;
    }
    v20 = DeviceSlot_D0Entry(*(_QWORD *)(v6 + 136), a2);
    v10 = v20;
    if ( v20 < 0 )
    {
      v4 = 6;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      v24 = 69;
      goto LABEL_61;
    }
    v20 = Command_D0Entry(*(_QWORD *)(v6 + 144), a2);
    v10 = v20;
    if ( v20 < 0 )
    {
      v4 = 7;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      v24 = 70;
      goto LABEL_61;
    }
    if ( i == 2 || a2 == 5 || v31 == 2 )
      break;
    if ( (*(_BYTE *)(v6 + 736) & 2) != 0
      || *(_BYTE *)(v6 + 796)
      || (unsigned int)Controller_GetPreProcessedSystemPowerAction(v6) == 2
      || (*(_BYTE *)(v6 + 744) & 8) != 0 && (unsigned __int8)Controller_InUseByDebugger(v6) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = 4;
        WPP_RECORDER_SF_(*(_QWORD *)(v6 + 72), v21, 4, 72, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
      }
    }
    else
    {
      v22 = Controller_D0EntryRestoreState(v6);
      if ( v22 >= 0 )
        break;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v23) = 4;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v6 + 72),
          v23,
          4,
          71,
          (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
          v22);
      }
      Controller_HwVerifierBreakIfEnabled(
        v6,
        0,
        0,
        0x400000,
        (__int64)"Controller restore state operation failed",
        0,
        0);
    }
    DeviceSlot_D0EntryCleanupState(*(_QWORD *)(v6 + 136), a2);
    v20 = Register_ControllerReset(*(_QWORD *)(v6 + 88), 0);
    v10 = v20;
    if ( v20 < 0 )
    {
      v4 = 11;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v24 = 73;
        goto LABEL_61;
      }
LABEL_62:
      v5 = *(_QWORD *)v33;
      goto LABEL_63;
    }
    v30 = 1;
  }
  v20 = Register_D0Entry(*(_QWORD *)(v6 + 88));
  v10 = v20;
  if ( v20 < 0 )
  {
    v4 = 1;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_62;
    v24 = 74;
    goto LABEL_61;
  }
  v20 = RootHub_D0Entry(*(_QWORD *)(v6 + 152));
  v10 = v20;
  if ( v20 < 0 )
  {
    v4 = 13;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_62;
    v24 = 75;
LABEL_61:
    LOBYTE(v21) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v6 + 72), v21, 4, v24, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v20);
    goto LABEL_62;
  }
  *(_DWORD *)(v6 + 792) = 1;
  if ( v30 == 1 )
  {
    v28 = *(_QWORD *)(v6 + 8);
    *(_QWORD *)&v33[4] = 0;
    *(_DWORD *)v33 = 12;
    ((void (__fastcall *)(__int64, __int64, _BYTE *))qword_14006CCD8)(UcxDriverGlobals, v28, v33);
  }
  Controller_UpdateIdleTimeoutOnControllerFDOD0Entry(v6);
  *(_DWORD *)(v6 + 820) = 7;
LABEL_85:
  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 8) != 0 )
    McTemplateK0pqqq_EtwWriteTransfer(
      v26,
      (unsigned int)USBXHCI_ETW_EVENT_CONTROLLER_D0_ENTRY_COMPLETE,
      v27,
      *(_QWORD *)(v6 + 8),
      a2,
      v32,
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140018d90  push    rbx
0x140018d92  push    rbp
0x140018d93  push    rsi
0x140018d94  push    rdi
0x140018d95  push    r12
0x140018d97  push    r13
0x140018d99  push    r14
0x140018d9b  push    r15
0x140018d9d  sub     rsp, 78h
0x140018da1  mov     rax, cs:__security_cookie
0x140018da8  xor     rax, rsp
0x140018dab  mov     [rsp+0B8h+var_58], rax
0x140018db0  mov     rax, cs:WdfFunctions_01033
0x140018db7  mov     r13d, edx
0x140018dba  mov     r8, cs:off_14006C2C0
0x140018dc1  mov     rdi, rcx
0x140018dc4  mov     rdx, rcx
0x140018dc7  mov     rcx, cs:WdfDriverGlobals
0x140018dce  mov     rax, [rax+650h]
0x140018dd5  call    _guard_dispatch_icall
0x140018dda  xor     esi, esi
0x140018ddc  mov     [rsp+0B8h+var_68], rax
0x140018de1  mov     r12, rax
0x140018de4  mov     rbx, [rax+8]
0x140018de8  cmp     [rbx+411h], sil
0x140018def  jz      short loc_140018E1C
0x140018df1  call    cs:__imp_KeGetCurrentIrql
0x140018df8  nop     dword ptr [rax+rax+00h]
0x140018dfd  test    al, al
0x140018dff  jz      short loc_140018E1C
0x140018e01  mov     r9d, 8BBh
0x140018e07  lea     r8, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140018e0e  xor     edx, edx
0x140018e10  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x140018e17  call    Debug_FreAssertMsg
0x140018e1c  mov     edx, r13d
0x140018e1f  mov     rcx, rdi
0x140018e22  call    Controller_LogDiagnosticsOnD0Entry
0x140018e27  mov     rax, cs:WdfFunctions_01033
0x140018e2e  mov     rdx, rdi
0x140018e31  mov     rcx, cs:WdfDriverGlobals
0x140018e38  mov     rax, [rax+0C20h]
0x140018e3f  call    _guard_dispatch_icall
0x140018e44  mov     rcx, rbx
0x140018e47  mov     dword ptr [rsp+0B8h+var_70], eax
0x140018e4b  call    Controller_GetPreProcessedSystemPowerAction
0x140018e50  mov     rcx, [rbx+58h]
0x140018e54  mov     edi, eax
0x140018e56  mov     [rsp+0B8h+var_74], eax
0x140018e5a  mov     rdx, [rcx+18h]
0x140018e5e  call    XilRegister_ReadUlong
0x140018e63  cmp     eax, 0FFFFFFFFh
0x140018e66  jnz     short loc_140018EA6
0x140018e68  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140018e6f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140018e76  jz      short loc_140018E99
0x140018e78  mov     rcx, [rbx+48h]
0x140018e7c  lea     r15, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140018e83  mov     r9d, 40h ; '@'
0x140018e89  mov     [rsp+0B8h+var_98], r15
0x140018e8e  mov     dl, 2
0x140018e90  lea     r8d, [r9-3Ch]
0x140018e94  call    WPP_RECORDER_SF_
0x140018e99  mov     bpl, 1
0x140018e9c  mov     edi, 0C0000001h
0x140018ea1  jmp     loc_14001924B
0x140018ea6  mov     [rsp+0B8h+var_77], sil
0x140018eab  mov     [rsp+0B8h+var_78], sil
0x140018eb0  cmp     [rbx+360h], esi
0x140018eb6  jz      short loc_140018ED0
0x140018eb8  mov     rcx, [rbx+510h]
0x140018ebf  test    rcx, rcx
0x140018ec2  jz      short loc_140018ED0
0x140018ec4  call    cs:__imp_SleepstudyHelper_ComponentActive
0x140018ecb  nop     dword ptr [rax+rax+00h]
0x140018ed0  lea     rbp, WPP_RECORDER_INITIALIZED
0x140018ed7  mov     r14d, 4
0x140018edd  lea     r15, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140018ee4  cmp     edi, 2
0x140018ee7  jnz     loc_140018FC0
0x140018eed  mov     rax, [rbx+338h]
0x140018ef4  test    rax, rax
0x140018ef7  jz      short loc_140018F6C
0x140018ef9  cmp     [rax+248h], r14d
0x140018f00  jnz     short loc_140018F6C
0x140018f02  mov     rcx, [rbx+58h]
0x140018f06  call    Register_ControllerStop
0x140018f0b  test    eax, eax
0x140018f0d  jns     short loc_140018F34
0x140018f0f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140018f16  jz      short loc_140018F34
0x140018f18  mov     rcx, [rbx+48h]
0x140018f1c  lea     r9d, [r14+3Dh]
0x140018f20  mov     dword ptr [rsp+0B8h+var_90], eax
0x140018f24  mov     r8d, r14d
0x140018f27  mov     dl, dil
0x140018f2a  mov     [rsp+0B8h+var_98], r15
0x140018f2f  call    WPP_RECORDER_SF_d
0x140018f34  mov     rcx, [rbx+88h]
0x140018f3b  mov     edx, r13d
0x140018f3e  call    DeviceSlot_D0EntryCleanupState
0x140018f43  mov     rcx, [rbx+58h]
0x140018f47  xor     edx, edx
0x140018f49  call    Register_ControllerReset
0x140018f4e  mov     edi, eax
0x140018f50  test    eax, eax
0x140018f52  jns     short loc_140018FBB
0x140018f54  mov     esi, 0Bh
0x140018f59  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140018f60  jz      loc_140019246
0x140018f66  lea     r9d, [rsi+38h]
0x140018f6a  jmp     short loc_140018F9F
0x140018f6c  mov     rcx, [rbx+58h]
0x140018f70  call    Register_BiosHandoff
0x140018f75  mov     edi, eax
0x140018f77  test    eax, eax
0x140018f79  jns     short loc_140018F34
0x140018f7b  mov     esi, 0Ah
0x140018f80  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140018f87  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140018f8e  jz      loc_140019246
0x140018f94  lea     r9d, [rsi+38h]
0x140018f98  lea     r15, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140018f9f  mov     rcx, [rbx+48h]
0x140018fa3  mov     r8d, r14d
0x140018fa6  mov     dword ptr [rsp+0B8h+var_90], eax
0x140018faa  mov     dl, 2
0x140018fac  mov     [rsp+0B8h+var_98], r15
0x140018fb1  call    WPP_RECORDER_SF_d
0x140018fb6  jmp     loc_140019246
0x140018fbb  mov     [rsp+0B8h+var_77], 1
0x140018fc0  cmp     [rbx+348h], sil
0x140018fc7  jnz     short loc_140019043
0x140018fc9  call    cs:__imp_KeQueryTimeIncrement
0x140018fd0  nop     dword ptr [rax+rax+00h]
0x140018fd5  mov     [rbx+34Ch], eax
0x140018fdb  mov     rax, [rbx+58h]
0x140018fdf  mov     rcx, [rax+28h]
0x140018fe3  nop
0x140018fe4  mov     rax, 0FFFFF78000000320h
0x140018fee  mov     r8d, [rcx]
0x140018ff1  mov     rax, [rax]
0x140018ff4  inc     r8d
0x140018ff7  mov     ecx, [rbx+34Ch]
0x140018ffd  imul    rcx, rax
0x140019001  shr     r8, 3
0x140019005  mov     rax, 346DC5D63886594Bh
0x14001900f  imul    rcx
0x140019012  and     r8d, 7FFh
0x140019019  sar     rdx, 0Bh
0x14001901d  mov     rax, rdx
0x140019020  shr     rax, 3Fh
0x140019024  add     rdx, rax
0x140019027  sub     rdx, r8
0x14001902a  shr     r8, 0Bh
0x14001902e  shl     rdx, 15h
0x140019032  or      rdx, r8
0x140019035  xchg    rdx, [rbx+340h]
0x14001903c  mov     byte ptr [rbx+348h], 1
0x140019043  mov     dl, 1
0x140019045  mov     rcx, rbx
0x140019048  call    Controller_ExecuteHSICDisconnectInU3Workaround
0x14001904d  test    byte ptr [rbx+2E8h], 1
0x140019054  jz      short loc_140019060
0x140019056  mov     dl, 1
0x140019058  mov     rcx, rbx
0x14001905b  call    Controller_ExecuteKBLPowerTransitionWorkaround
0x140019060  mov     esi, 5
0x140019065  lea     r12d, [rsi-4]
0x140019069  cmp     r12d, 2
0x14001906d  ja      loc_1400192E0
0x140019073  jz      short loc_1400190BC
0x140019075  test    byte ptr [rbx+2E0h], 2
0x14001907c  jnz     short loc_1400190BC
0x14001907e  cmp     byte ptr [rbx+31Ch], 0
0x140019085  jnz     short loc_1400190BC
0x140019087  cmp     r13d, esi
0x14001908a  jz      short loc_1400190BC
0x14001908c  mov     rcx, rbx
0x14001908f  call    Controller_GetPreProcessedSystemPowerAction
0x140019094  cmp     eax, 2
0x140019097  jz      short loc_1400190BC
0x140019099  test    byte ptr [rbx+2E8h], 8
0x1400190a0  jz      short loc_1400190AE
0x1400190a2  mov     rcx, rbx
0x1400190a5  call    Controller_InUseByDebugger
0x1400190aa  test    al, al
0x1400190ac  jnz     short loc_1400190BC
0x1400190ae  mov     rcx, [rbx+58h]
0x1400190b2  call    Register_D0EntryPreRestoreState
0x1400190b7  mov     r8b, 1
0x1400190ba  jmp     short loc_1400190BF
0x1400190bc  xor     r8b, r8b
0x1400190bf  mov     rcx, [rbx+80h]
0x1400190c6  mov     edx, r13d
0x1400190c9  call    Interrupter_D0Entry
0x1400190ce  mov     edi, eax
0x1400190d0  test    eax, eax
0x1400190d2  js      loc_1400192C8
0x1400190d8  mov     rcx, [rbx+88h]
0x1400190df  mov     edx, r13d
0x1400190e2  call    DeviceSlot_D0Entry
0x1400190e7  mov     edi, eax
0x1400190e9  test    eax, eax
0x1400190eb  js      loc_1400192B1
0x1400190f1  mov     rcx, [rbx+90h]
0x1400190f8  mov     edx, r13d
0x1400190fb  call    Command_D0Entry
0x140019100  mov     edi, eax
0x140019102  test    eax, eax
0x140019104  js      loc_14001929A
0x14001910a  cmp     r12d, 2
0x14001910e  jz      loc_1400192E0
0x140019114  cmp     r13d, esi
0x140019117  jz      loc_1400192E0
0x14001911d  cmp     [rsp+0B8h+var_74], 2
0x140019122  jz      loc_1400192E0
0x140019128  test    byte ptr [rbx+2E0h], 2
0x14001912f  jnz     loc_1400191C8
0x140019135  xor     edi, edi
0x140019137  cmp     [rbx+31Ch], dil
0x14001913e  jnz     loc_1400191C8
0x140019144  mov     rcx, rbx
0x140019147  call    Controller_GetPreProcessedSystemPowerAction
0x14001914c  cmp     eax, 2
0x14001914f  jz      short loc_1400191C8
0x140019151  test    byte ptr [rbx+2E8h], 8
0x140019158  jz      short loc_140019166
0x14001915a  mov     rcx, rbx
0x14001915d  call    Controller_InUseByDebugger
0x140019162  test    al, al
0x140019164  jnz     short loc_1400191C8
0x140019166  mov     rcx, rbx
0x140019169  call    Controller_D0EntryRestoreState
0x14001916e  test    eax, eax
0x140019170  jns     loc_1400192E0
0x140019176  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001917d  jz      short loc_14001919D
0x14001917f  mov     rcx, [rbx+48h]
0x140019183  mov     r9d, 47h ; 'G'
0x140019189  mov     dword ptr [rsp+0B8h+var_90], eax
0x14001918d  mov     r8d, r14d
0x140019190  mov     dl, r14b
0x140019193  mov     [rsp+0B8h+var_98], r15
0x140019198  call    WPP_RECORDER_SF_d
0x14001919d  mov     [rsp+0B8h+var_88], rdi
0x1400191a2  lea     rax, aControllerRest; "Controller restore state operation fail"...
0x1400191a9  mov     [rsp+0B8h+var_90], rdi
0x1400191ae  mov     r9d, 400000h
0x1400191b4  xor     r8d, r8d
0x1400191b7  mov     [rsp+0B8h+var_98], rax
0x1400191bc  xor     edx, edx
0x1400191be  mov     rcx, rbx
0x1400191c1  call    Controller_HwVerifierBreakIfEnabled
0x1400191c6  jmp     short loc_1400191EB
0x1400191c8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x1400191cf  jz      short loc_1400191EB
0x1400191d1  mov     rcx, [rbx+48h]
0x1400191d5  mov     r9d, 48h ; 'H'
0x1400191db  mov     r8d, r14d
0x1400191de  mov     [rsp+0B8h+var_98], r15
0x1400191e3  mov     dl, r14b
0x1400191e6  call    WPP_RECORDER_SF_
0x1400191eb  mov     rcx, [rbx+88h]
0x1400191f2  mov     edx, r13d
0x1400191f5  call    DeviceSlot_D0EntryCleanupState
0x1400191fa  mov     rcx, [rbx+58h]
0x1400191fe  xor     edx, edx
0x140019200  call    Register_ControllerReset
0x140019205  mov     edi, eax
0x140019207  test    eax, eax
0x140019209  js      short loc_140019218
0x14001920b  mov     [rsp+0B8h+var_77], 1
0x140019210  inc     r12d
0x140019213  jmp     loc_140019069
0x140019218  mov     esi, 0Bh
0x14001921d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140019224  jz      short loc_140019241
0x140019226  lea     r9d, [rsi+3Eh]
0x14001922a  mov     rcx, [rbx+48h]
0x14001922e  mov     r8d, r14d
0x140019231  mov     dword ptr [rsp+0B8h+var_90], eax
0x140019235  mov     dl, 2
0x140019237  mov     [rsp+0B8h+var_98], r15
0x14001923c  call    WPP_RECORDER_SF_d
0x140019241  mov     r12, [rsp+0B8h+var_68]
0x140019246  mov     bpl, [rsp+0B8h+var_78]
0x14001924b  mov     rcx, [rbx+88h]
0x140019252  call    DeviceSlot_DisableAllDeviceSlots
0x140019257  xor     ecx, ecx
0x140019259  test    bpl, bpl
0x14001925c  jz      loc_140019337
0x140019262  mov     eax, [r12+1Ch]
0x140019267  test    al, 10h
0x140019269  jnz     short loc_14001928B
0x14001926b  movsxd  rax, edi
0x14001926e  mov     r9d, 1036h
0x140019274  mov     ecx, esi
0x140019276  xor     r8d, r8d
0x140019279  mov     [rsp+0B8h+var_90], rax
  ... truncated ...
```
