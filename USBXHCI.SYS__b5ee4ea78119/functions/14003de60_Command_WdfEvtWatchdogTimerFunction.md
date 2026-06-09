# Command_WdfEvtWatchdogTimerFunction

- ea: `0x14003de60`
- end: `0x14003e795`
- name: `Command_WdfEvtWatchdogTimerFunction`
- size: `2357`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `broker_com_uri`

## callees

- `0x140005d48`
- `0x14000c264`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001b9a4`
- `0x14001bb78`
- `0x14001fb30`
- `0x1400218a0`
- `0x1400219b0`
- `0x140021a74`
- `0x14002312c`
- `0x14002b2c0`
- `0x140031568`
- `0x140032a2c`
- `0x14003b7d0`
- `0x14003d3b4`
- `0x14003de60`
- `0x14003e79c`
- `0x14003e8c8`
- `0x14003e9e4`
- `0x14003f4b4`
- `0x14003f514`
- `0x14003fa38`
- `0x140057db0`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14003ded8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003df03`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003ded8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003df03`

## string_xrefs

- `0x14003deee`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\command.c`
- `0x14003def7`: `Code Path Requires Passive Level`
- `0x14003e0c1`: `Command abort timed out, command ring still running, resetting the controller`
- `0x14003e1ad`: `Command abort timed out; stopped event not received, but command ring is stopped; Assuming abort finished.`
- `0x14003e4d2`: `A command timed out, aborting command next`
- `0x14003e73a`: `Command Abort Timeout`

## pseudocode

```c
__int128 *__fastcall Command_WdfEvtWatchdogTimerFunction(__int64 a1)
{
  __int64 v1; // rax
  int v2; // esi
  __int64 v3; // rbx
  char IsControllerAccessible; // di
  unsigned __int8 v5; // r13
  unsigned __int8 v6; // r15
  __int64 v7; // rcx
  int v8; // r12d
  __int64 *v9; // rdi
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  _QWORD **v14; // r8
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  bool v19; // zf
  __int64 v20; // rdx
  int v21; // edx
  int v22; // r14d
  int v23; // edx
  int v24; // eax
  __int64 v25; // rdx
  __int64 *v26; // rcx
  __int64 **v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rcx
  int v31; // edx
  int v32; // edx
  _QWORD **v33; // r8
  _QWORD *v34; // rax
  _QWORD *v35; // rcx
  __int64 v36; // rdx
  _QWORD *v37; // rcx
  __int128 *result; // rax
  __int64 v39; // rdx
  __int64 v40; // rdi
  __int64 v41; // rax
  __int128 *v42; // rcx
  unsigned int v43; // edi
  __int64 v44; // rax
  __int64 v45; // rdx
  int v46; // [rsp+20h] [rbp-50h]
  unsigned __int8 v47; // [rsp+40h] [rbp-30h] BYREF
  char v48; // [rsp+41h] [rbp-2Fh]
  __int128 v49; // [rsp+48h] [rbp-28h] BYREF
  __int128 v50; // [rsp+58h] [rbp-18h] BYREF
  char v51; // [rsp+B8h] [rbp+48h]
  char v52; // [rsp+C0h] [rbp+50h]
  char v53; // [rsp+C8h] [rbp+58h] BYREF

  v49 = 0;
  v50 = 0;
  v1 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 2568))(WdfDriverGlobals, a1);
  v2 = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         v1,
         off_14006C0B8);
  if ( *(_BYTE *)(*(_QWORD *)(v3 + 8) + 1041LL) && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\command.c",
      1063);
  if ( !KeGetCurrentIrql() )
    Command_StartCommandWatchdogTimer(v3);
  IsControllerAccessible = Controller_IsControllerAccessible(*(_QWORD *)(v3 + 8));
  v51 = IsControllerAccessible;
  v48 = 0;
  *((_QWORD *)&v49 + 1) = &v49;
  v5 = 0;
  v52 = 0;
  *(_QWORD *)&v49 = &v49;
  v6 = 0;
  v7 = *(_QWORD *)(v3 + 112);
  v8 = 0;
  v47 = 0;
  v53 = 0;
  DynamicLock_Acquire(v7);
  if ( !IsControllerAccessible )
    goto LABEL_15;
  if ( *(_DWORD *)(v3 + 36) != 1 )
  {
LABEL_91:
    v22 = 0;
    goto LABEL_92;
  }
  v9 = *(__int64 **)(v3 + 80);
  if ( v9 == (__int64 *)(v3 + 80) )
  {
    IsControllerAccessible = v51;
    goto LABEL_91;
  }
  XilCommand_QueryIsRingRunning(v3, &v53, &v47);
  v13 = *((_DWORD *)v9 + 14);
  if ( v13 > 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF_qd(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v10,
      7,
      29,
      (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids,
      (char)v9,
      v13);
  }
  if ( v47 )
  {
    IsControllerAccessible = 0;
    v48 = 1;
LABEL_15:
    if ( *(_BYTE *)(v3 + 128) )
    {
      v14 = (_QWORD **)(v3 + 80);
      while ( 1 )
      {
        v15 = *v14;
        if ( *v14 == v14 )
          break;
        v16 = (_QWORD *)(v3 + 80);
        if ( v15[1] != v3 + 80 )
          goto LABEL_101;
        v17 = *v15;
        if ( *(_QWORD **)(*v15 + 8LL) != v15 )
          goto LABEL_101;
        *v16 = v17;
        *(_QWORD *)(v17 + 8) = v16;
        v18 = (_QWORD *)*((_QWORD *)&v49 + 1);
        if ( **((__int128 ***)&v49 + 1) != &v49 )
          goto LABEL_101;
        v15[1] = *((_QWORD *)&v49 + 1);
        *v15 = &v49;
        *v18 = v15;
        *((_QWORD *)&v49 + 1) = v15;
      }
      v33 = (_QWORD **)(v3 + 96);
      while ( 1 )
      {
        v34 = *v33;
        if ( *v33 == v33 )
          break;
        v35 = (_QWORD *)(v3 + 96);
        if ( v34[1] != v3 + 96 )
          goto LABEL_101;
        v36 = *v34;
        if ( *(_QWORD **)(*v34 + 8LL) != v34 )
          goto LABEL_101;
        *v35 = v36;
        *(_QWORD *)(v36 + 8) = v35;
        v37 = (_QWORD *)*((_QWORD *)&v49 + 1);
        if ( **((__int128 ***)&v49 + 1) != &v49 )
          goto LABEL_101;
        v34[1] = *((_QWORD *)&v49 + 1);
        *v34 = &v49;
        *v37 = v34;
        *((_QWORD *)&v49 + 1) = v34;
      }
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2560))(
      WdfDriverGlobals,
      *(_QWORD *)(v3 + 24),
      0);
    goto LABEL_91;
  }
  if ( *(_BYTE *)(v3 + 121) )
  {
    v19 = (*(_DWORD *)(v3 + 124))-- == 1;
    if ( !v19 )
      goto LABEL_65;
    if ( v53 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v10,
          7,
          30,
          (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
      }
      Controller_HwVerifierBreakIfEnabled(
        *(_QWORD *)(v3 + 8),
        0,
        0,
        4096,
        (__int64)"Command abort timed out, command ring still running, resetting the controller",
        *(_QWORD *)(v3 + 72) + 16LL * *(unsigned int *)(v3 + 44),
        0);
      v20 = *(_QWORD *)(v3 + 24);
      *(_BYTE *)(v3 + 121) = 0;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2560))(
        WdfDriverGlobals,
        v20,
        0);
      *(_DWORD *)(v3 + 36) = 2;
      v52 = 1;
      v5 = *((_BYTE *)v9 + 62) & 1;
      if ( (unsigned int)Feature_ATFUR__private_IsEnabledDeviceUsageNoInline() )
      {
        v21 = *(_DWORD *)(*(_QWORD *)(v3 + 72) + 16LL * *(unsigned int *)(v3 + 44) + 12);
        v8 = BYTE1(v21) >> 2;
        if ( v8 == 11 )
        {
          if ( (v21 & 0x200) != 0 )
          {
            v22 = 0;
            v2 = 1;
          }
          else
          {
            v22 = 1;
          }
          goto LABEL_66;
        }
      }
LABEL_65:
      v22 = 0;
LABEL_66:
      v6 = v52;
LABEL_79:
      IsControllerAccessible = v51;
      goto LABEL_92;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v10,
        7,
        31,
        (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
    }
    Controller_HwVerifierBreakIfEnabled(
      *(_QWORD *)(v3 + 8),
      0,
      0,
      0x2000,
      (__int64)"Command abort timed out; stopped event not received, but command ring is stopped; Assuming abort finished.",
      *(_QWORD *)(v3 + 72) + 16LL * *(unsigned int *)(v3 + 44),
      0);
    *(_BYTE *)(v3 + 121) = 0;
    v24 = *((_DWORD *)v9 + 14);
    switch ( v24 )
    {
      case 0:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v23) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v23,
            7,
            34,
            (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids,
            0);
        }
        v26 = (__int64 *)*v9;
        if ( *(__int64 **)(*v9 + 8) != v9 || (v27 = (__int64 **)v9[1], *v27 != v9) )
LABEL_101:
          __fastfail(3u);
        *v27 = v26;
        v26[1] = (__int64)v27;
        v28 = (unsigned int)++*(_DWORD *)(v3 + 44);
        if ( (_DWORD)v28 == *(_DWORD *)(v3 + 48) )
        {
          *(_DWORD *)(v3 + 44) = 0;
          v28 = 0;
        }
        XilCommand_AdvanceCommandRingControlDequeuePointer(v3, v28);
        goto LABEL_40;
      case 5:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v23) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v23,
            7,
            33,
            (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids,
            5);
        }
        break;
      case 10:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v23) = 4;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v23,
            7,
            32,
            (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids,
            10);
        }
        break;
      default:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v23) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
            v23,
            7,
            35,
            (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids,
            v24);
        }
        v2 = 0;
LABEL_40:
        if ( *(_QWORD *)(v3 + 80) != v3 + 80 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v23) = 4;
            WPP_RECORDER_SF_(*(_QWORD *)(v3 + 16), v23, 7, 36, (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
          }
          XilCommand_WriteDoorbell(v3);
        }
        v25 = *(_QWORD *)(v3 + 96);
        if ( v25 == v3 + 96 )
        {
          *((_QWORD *)&v50 + 1) = &v50;
          *(_QWORD *)&v50 = &v50;
        }
        else
        {
          v50 = *(_OWORD *)(v3 + 96);
          *(_QWORD *)(v25 + 8) = &v50;
          **((_QWORD **)&v50 + 1) = &v50;
          *(_QWORD *)(v3 + 104) = v3 + 96;
          *(_QWORD *)(v3 + 96) = v3 + 96;
        }
        while ( (__int128 *)v50 != &v50 )
        {
          if ( *(__int128 **)(v50 + 8) != &v50 )
            goto LABEL_101;
          v29 = *(_QWORD *)v50;
          if ( *(_QWORD *)(*(_QWORD *)v50 + 8LL) != (_QWORD)v50 )
            goto LABEL_101;
          *(_QWORD *)&v50 = *(_QWORD *)v50;
          *(_QWORD *)(v29 + 8) = &v50;
          Command_InternalSendCommand(v3);
        }
        if ( v9 )
        {
          DynamicLock_Release(*(_QWORD *)(v3 + 112));
          *((_BYTE *)v9 + 60) = 25;
          Etw_CommandCompleteError(v30, v3, v9, 2);
          Command_ProcessCrbCompletion(v9, 2);
          DynamicLock_Acquire(*(_QWORD *)(v3 + 112));
        }
        goto LABEL_65;
    }
    v2 = 0;
    v9 = 0;
    goto LABEL_40;
  }
  v31 = --*((_DWORD *)v9 + 14);
  if ( v31 != 5 && v31 )
  {
LABEL_78:
    v22 = 0;
    v2 = 0;
    goto LABEL_79;
  }
  if ( v53 == 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qLd(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v31,
        v11,
        v12,
        v46,
        (char)v9,
        (unsigned __int16)*((_DWORD *)v9 + 9) >> 10,
        *((_DWORD *)v9 + 14));
    v32 = (unsigned __int8)HIBYTE(*((_WORD *)v9 + 18)) >> 2;
    if ( v32 != 11 || ((*((_DWORD *)v9 + 9) >> 9) & 1) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v32) = 2;
        WPP_RECORDER_SF_ddL(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v32,
          7,
          38,
          (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids,
          5,
          (*((_DWORD *)v9 + 9) & 0x200) != 0,
          (unsigned __int8)HIBYTE(*((_WORD *)v9 + 18)) >> 2);
      }
      Controller_HwVerifierBreakIfEnabled(
        *(_QWORD *)(v3 + 8),
        0,
        0,
        0x4000,
        (__int64)"A command timed out, aborting command next",
        (__int64)(v9 + 3),
        0);
    }
    *(_BYTE *)(v3 + 121) = 1;
    *(_DWORD *)(v3 + 124) = 5;
    XilCommand_AbortCommandRing(v3);
    goto LABEL_78;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v31) = 2;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v31,
      7,
      39,
      (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2560))(
    WdfDriverGlobals,
    *(_QWORD *)(v3 + 24),
    0);
  v22 = 0;
  *(_DWORD *)(v3 + 36) = 2;
  v2 = 0;
  v52 = 1;
  v19 = (*((_BYTE *)v9 + 62) & 1) == 0;
  IsControllerAccessible = v51;
  if ( !v19 )
    v5 = 1;
LABEL_92:
  result = (__int128 *)DynamicLock_Release(*(_QWORD *)(v3 + 112));
  if ( !IsControllerAccessible )
  {
    if ( v48 == 1 )
    {
      LOBYTE(v39) = 1;
      Controller_SetControllerGone(*(_QWORD *)(v3 + 8), v39);
    }
    while ( 1 )
    {
      v40 = v49;
      result = &v49;
      if ( (__int128 *)v49 == &v49 )
        break;
      if ( *(__int128 **)(v49 + 8) != &v49 )
        goto LABEL_101;
      v41 = *(_QWORD *)v49;
      if ( *(_QWORD *)(*(_QWORD *)v49 + 8LL) != (_QWORD)v49 )
        goto LABEL_101;
      v42 = &v49;
      *(_QWORD *)&v49 = *(_QWORD *)v49;
      *(_QWORD *)(v41 + 8) = &v49;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v39) = 4;
        WPP_RECORDER_SF_qL(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v39,
          7,
          40,
          (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids,
          v40,
          (unsigned __int8)HIBYTE(*(_WORD *)(v40 + 36)) >> 2);
      }
      Etw_CommandCompleteError(v42, v3, v40, 3);
      Command_ProcessCrbCompletion(v40, 3);
    }
  }
  if ( v52 == 1 )
  {
    if ( (unsigned int)Feature_ATFUR__private_IsEnabledDeviceUsageNoInline() )
    {
      v43 = v6
          | (2 * (v8 | ((v22 | (2 * (v2 | (2 * (((unsigned __int8)v48 | v47) & 1 | (2 * ((2 * v5) | v53 & 1))))))) << 6)));
      v44 = *(_QWORD *)(v3 + 8);
      if ( *(_DWORD *)(v44 + 644) == 1 )
        v45 = *(unsigned __int16 *)(v44 + 652) | (*(unsigned __int16 *)(v44 + 648) << 16);
      else
        v45 = 0;
      MicrosoftTelemetryAssertTriggeredArgsMsgKM("USBXHCI.SYS", v45, v43, "Command Abort Timeout");
      return (__int128 *)Controller_ReportFatalError(*(_QWORD *)(v3 + 8), (v5 ^ 1u) + 1, 4105, v43, 0, 0, 0);
    }
    else
    {
      return (__int128 *)Controller_ReportFatalError(*(_QWORD *)(v3 + 8), (v5 ^ 1u) + 1, 4105, 0, 0, 0, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003de60  mov     [rsp-38h+arg_0], rbx
0x14003de65  push    rbp
0x14003de66  push    rsi
0x14003de67  push    rdi
0x14003de68  push    r12
0x14003de6a  push    r13
0x14003de6c  push    r14
0x14003de6e  push    r15
0x14003de70  mov     rbp, rsp
0x14003de73  sub     rsp, 70h
0x14003de77  mov     rax, cs:WdfFunctions_01033
0x14003de7e  xorps   xmm0, xmm0
0x14003de81  xorps   xmm1, xmm1
0x14003de84  mov     rdx, rcx
0x14003de87  mov     rcx, cs:WdfDriverGlobals
0x14003de8e  movups  [rbp+var_28], xmm0
0x14003de92  movups  [rbp+var_18], xmm1
0x14003de96  mov     rax, [rax+0A08h]
0x14003de9d  call    _guard_dispatch_icall
0x14003dea2  mov     rcx, cs:WdfFunctions_01033
0x14003dea9  mov     rdx, rax
0x14003deac  mov     r8, cs:off_14006C0B8
0x14003deb3  mov     rax, [rcx+650h]
0x14003deba  mov     rcx, cs:WdfDriverGlobals
0x14003dec1  call    _guard_dispatch_icall
0x14003dec6  xor     esi, esi
0x14003dec8  mov     rbx, rax
0x14003decb  mov     rcx, [rax+8]
0x14003decf  cmp     [rcx+411h], sil
0x14003ded6  jz      short loc_14003DF03
0x14003ded8  call    cs:__imp_KeGetCurrentIrql
0x14003dedf  nop     dword ptr [rax+rax+00h]
0x14003dee4  test    al, al
0x14003dee6  jz      short loc_14003DF03
0x14003dee8  mov     r9d, 427h
0x14003deee  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003def5  xor     edx, edx
0x14003def7  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x14003defe  call    Debug_FreAssertMsg
0x14003df03  call    cs:__imp_KeGetCurrentIrql
0x14003df0a  nop     dword ptr [rax+rax+00h]
0x14003df0f  test    al, al
0x14003df11  jnz     short loc_14003DF1B
0x14003df13  mov     rcx, rbx
0x14003df16  call    Command_StartCommandWatchdogTimer
0x14003df1b  mov     rcx, [rbx+8]
0x14003df1f  call    Controller_IsControllerAccessible
0x14003df24  mov     dil, al
0x14003df27  mov     [rbp+arg_8], al
0x14003df2a  lea     rax, [rbp+var_28]
0x14003df2e  mov     [rbp+var_2F], sil
0x14003df32  mov     qword ptr [rbp+var_28+8], rax
0x14003df36  mov     r13b, sil
0x14003df39  lea     rax, [rbp+var_28]
0x14003df3d  mov     [rbp+arg_10], sil
0x14003df41  mov     qword ptr [rbp+var_28], rax
0x14003df45  mov     r15b, sil
0x14003df48  mov     rcx, [rbx+70h]
0x14003df4c  mov     r12d, esi
0x14003df4f  mov     [rbp+var_30], sil
0x14003df53  mov     [rbp+arg_18], sil
0x14003df57  call    DynamicLock_Acquire
0x14003df5c  test    dil, dil
0x14003df5f  jz      loc_14003DFED
0x14003df65  cmp     dword ptr [rbx+24h], 1
0x14003df69  jnz     loc_14003E5E4
0x14003df6f  lea     r14, [rbx+50h]
0x14003df73  mov     rdi, [r14]
0x14003df76  cmp     rdi, r14
0x14003df79  jnz     short loc_14003DF84
0x14003df7b  mov     dil, [rbp+arg_8]
0x14003df7f  jmp     loc_14003E5E4
0x14003df84  lea     r8, [rbp+var_30]
0x14003df88  mov     rcx, rbx
0x14003df8b  lea     rdx, [rbp+arg_18]
0x14003df8f  call    XilCommand_QueryIsRingRunning
0x14003df94  mov     eax, [rdi+38h]
0x14003df97  test    eax, eax
0x14003df99  jle     short loc_14003DFD9
0x14003df9b  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003dfa2  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003dfa9  jz      short loc_14003DFE0
0x14003dfab  mov     rcx, [rbx+8]
0x14003dfaf  mov     r9d, 1Dh
0x14003dfb5  mov     dword ptr [rsp+70h+var_40], eax
0x14003dfb9  mov     dl, 4
0x14003dfbb  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x14003dfc2  mov     [rsp+70h+var_48], rdi
0x14003dfc7  mov     [rsp+70h+var_50], rax
0x14003dfcc  mov     rcx, [rcx+48h]
0x14003dfd0  lea     r8d, [r9-16h]
0x14003dfd4  call    WPP_RECORDER_SF_qd
0x14003dfd9  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003dfe0  cmp     [rbp+var_30], sil
0x14003dfe4  jz      short loc_14003E051
0x14003dfe6  mov     dil, sil
0x14003dfe9  mov     [rbp+var_2F], 1
0x14003dfed  cmp     [rbx+80h], sil
0x14003dff4  jz      loc_14003E5C3
0x14003dffa  lea     r8, [rbx+50h]
0x14003dffe  mov     rax, [r8]
0x14003e001  cmp     rax, r8
0x14003e004  jz      loc_14003E570
0x14003e00a  lea     rcx, [rbx+50h]
0x14003e00e  cmp     [rax+8], rcx
0x14003e012  jnz     loc_14003E6AA
0x14003e018  mov     rdx, [rax]
0x14003e01b  cmp     [rdx+8], rax
0x14003e01f  jnz     loc_14003E6AA
0x14003e025  mov     [rcx], rdx
0x14003e028  mov     [rdx+8], rcx
0x14003e02c  lea     rdx, [rbp+var_28]
0x14003e030  mov     rcx, qword ptr [rbp+var_28+8]
0x14003e034  cmp     [rcx], rdx
0x14003e037  jnz     loc_14003E6AA
0x14003e03d  mov     [rax+8], rcx
0x14003e041  lea     rdx, [rbp+var_28]
0x14003e045  mov     [rax], rdx
0x14003e048  mov     [rcx], rax
0x14003e04b  mov     qword ptr [rbp+var_28+8], rax
0x14003e04f  jmp     short loc_14003DFFE
0x14003e051  cmp     [rbx+79h], sil
0x14003e055  jz      loc_14003E40F
0x14003e05b  add     dword ptr [rbx+7Ch], 0FFFFFFFFh
0x14003e05f  jnz     loc_14003E403
0x14003e065  cmp     [rbp+arg_18], sil
0x14003e069  jz      loc_14003E158
0x14003e06f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x14003e076  jz      short loc_14003E09D
0x14003e078  mov     rcx, [rbx+8]
0x14003e07c  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x14003e083  mov     r9d, 1Eh
0x14003e089  mov     [rsp+70h+var_50], rax
0x14003e08e  mov     dl, 2
0x14003e090  mov     rcx, [rcx+48h]
0x14003e094  lea     r8d, [r9-17h]
0x14003e098  call    WPP_RECORDER_SF_
0x14003e09d  mov     eax, [rbx+2Ch]
0x14003e0a0  mov     r9d, 1000h
0x14003e0a6  mov     rcx, [rbx+8]
0x14003e0aa  xor     r8d, r8d
0x14003e0ad  shl     rax, 4
0x14003e0b1  xor     edx, edx
0x14003e0b3  add     rax, [rbx+48h]
0x14003e0b7  mov     [rsp+70h+var_40], rsi
0x14003e0bc  mov     [rsp+70h+var_48], rax
0x14003e0c1  lea     rax, aCommandAbortTi_1; "Command abort timed out, command ring s"...
0x14003e0c8  mov     [rsp+70h+var_50], rax
0x14003e0cd  call    Controller_HwVerifierBreakIfEnabled
0x14003e0d2  mov     rdx, [rbx+18h]
0x14003e0d6  xor     r8d, r8d
0x14003e0d9  mov     [rbx+79h], sil
0x14003e0dd  mov     rax, cs:WdfFunctions_01033
0x14003e0e4  mov     rcx, cs:WdfDriverGlobals
0x14003e0eb  mov     rax, [rax+0A00h]
0x14003e0f2  call    _guard_dispatch_icall
0x14003e0f7  mov     r15d, 1
0x14003e0fd  mov     dword ptr [rbx+24h], 2
0x14003e104  mov     [rbp+arg_10], r15b
0x14003e108  mov     r13b, [rdi+3Eh]
0x14003e10c  and     r13b, r15b
0x14003e10f  call    Feature_ATFUR__private_IsEnabledDeviceUsageNoInline
0x14003e114  test    eax, eax
0x14003e116  jz      loc_14003E403
0x14003e11c  mov     ecx, [rbx+2Ch]
0x14003e11f  mov     rax, [rbx+48h]
0x14003e123  add     rcx, rcx
0x14003e126  mov     edx, [rax+rcx*8+0Ch]
0x14003e12a  mov     r12d, edx
0x14003e12d  shr     r12d, 0Ah
0x14003e131  and     r12d, 3Fh
0x14003e135  cmp     r12d, 0Bh
0x14003e139  jnz     loc_14003E403
0x14003e13f  bt      edx, 9
0x14003e143  jnb     short loc_14003E150
0x14003e145  mov     r14d, esi
0x14003e148  mov     esi, r15d
0x14003e14b  jmp     loc_14003E406
0x14003e150  mov     r14d, r15d
0x14003e153  jmp     loc_14003E406
0x14003e158  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x14003e15f  mov     r15d, 7
0x14003e165  jz      short loc_14003E189
0x14003e167  mov     rcx, [rbx+8]
0x14003e16b  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x14003e172  lea     r9d, [r15+18h]
0x14003e176  mov     [rsp+70h+var_50], rax
0x14003e17b  mov     r8d, r15d
0x14003e17e  mov     dl, 2
0x14003e180  mov     rcx, [rcx+48h]
0x14003e184  call    WPP_RECORDER_SF_
0x14003e189  mov     eax, [rbx+2Ch]
0x14003e18c  mov     r9d, 2000h
0x14003e192  mov     rcx, [rbx+8]
0x14003e196  xor     r8d, r8d
0x14003e199  shl     rax, 4
0x14003e19d  xor     edx, edx
0x14003e19f  add     rax, [rbx+48h]
0x14003e1a3  mov     [rsp+70h+var_40], rsi
0x14003e1a8  mov     [rsp+70h+var_48], rax
0x14003e1ad  lea     rax, aCommandAbortTi; "Command abort timed out; stopped event "...
0x14003e1b4  mov     [rsp+70h+var_50], rax
0x14003e1b9  call    Controller_HwVerifierBreakIfEnabled
0x14003e1be  mov     [rbx+79h], sil
0x14003e1c2  mov     eax, [rdi+38h]
0x14003e1c5  test    eax, eax
0x14003e1c7  jz      loc_14003E2E7
0x14003e1cd  mov     esi, 5
0x14003e1d2  cmp     eax, esi
0x14003e1d4  jz      loc_14003E2C9
0x14003e1da  cmp     eax, 0Ah
0x14003e1dd  jz      loc_14003E27D
0x14003e1e3  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e1ea  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003e1f1  jz      short loc_14003E220
0x14003e1f3  mov     rcx, [rbx+8]
0x14003e1f7  lea     r9d, [rsi+1Eh]
0x14003e1fb  mov     dword ptr [rsp+70h+var_48], eax
0x14003e1ff  mov     r8d, r15d
0x14003e202  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x14003e209  mov     dl, 2
0x14003e20b  mov     [rsp+70h+var_50], rax
0x14003e210  mov     rcx, [rcx+48h]
0x14003e214  call    WPP_RECORDER_SF_d
0x14003e219  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003e220  xor     esi, esi
0x14003e222  cmp     [r14], r14
0x14003e225  jz      short loc_14003E258
0x14003e227  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x14003e22e  jz      short loc_14003E250
0x14003e230  mov     rcx, [rbx+10h]
0x14003e234  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x14003e23b  mov     r9d, 24h ; '$'
0x14003e241  mov     [rsp+70h+var_50], rax
0x14003e246  mov     r8d, r15d
0x14003e249  mov     dl, 4
0x14003e24b  call    WPP_RECORDER_SF_
0x14003e250  mov     rcx, rbx
0x14003e253  call    XilCommand_WriteDoorbell
0x14003e258  lea     rcx, [rbx+60h]
0x14003e25c  mov     rdx, [rcx]
0x14003e25f  cmp     rdx, rcx
0x14003e262  jnz     loc_14003E364
0x14003e268  lea     rax, [rbp+var_18]
0x14003e26c  mov     qword ptr [rbp+var_18+8], rax
0x14003e270  lea     rax, [rbp+var_18]
0x14003e274  mov     qword ptr [rbp+var_18], rax
0x14003e278  jmp     loc_14003E38A
0x14003e27d  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e284  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003e28b  jz      short loc_14003E2C0
0x14003e28d  mov     r9d, 20h ; ' '
0x14003e293  mov     dword ptr [rsp+70h+var_48], 0Ah
0x14003e29b  mov     dl, 4
0x14003e29d  mov     rcx, [rbx+8]
0x14003e2a1  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x14003e2a8  mov     r8d, r15d
0x14003e2ab  mov     [rsp+70h+var_50], rax
0x14003e2b0  mov     rcx, [rcx+48h]
0x14003e2b4  call    WPP_RECORDER_SF_d
0x14003e2b9  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003e2c0  xor     esi, esi
0x14003e2c2  mov     edi, esi
0x14003e2c4  jmp     loc_14003E222
0x14003e2c9  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e2d0  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003e2d7  jz      short loc_14003E2C0
0x14003e2d9  mov     r9d, 21h ; '!'
0x14003e2df  mov     dword ptr [rsp+70h+var_48], esi
0x14003e2e3  mov     dl, 2
0x14003e2e5  jmp     short loc_14003E29D
0x14003e2e7  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e2ee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e2f5  jz      short loc_14003E31F
0x14003e2f7  mov     rcx, [rbx+8]
0x14003e2fb  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x14003e302  mov     r9d, 22h ; '"'
0x14003e308  mov     dword ptr [rsp+70h+var_48], esi
0x14003e30c  mov     r8d, r15d
0x14003e30f  mov     [rsp+70h+var_50], rax
0x14003e314  mov     dl, 2
0x14003e316  mov     rcx, [rcx+48h]
0x14003e31a  call    WPP_RECORDER_SF_d
0x14003e31f  mov     rcx, [rdi]
0x14003e322  cmp     [rcx+8], rdi
0x14003e326  jnz     loc_14003E6AA
0x14003e32c  mov     rax, [rdi+8]
0x14003e330  cmp     [rax], rdi
0x14003e333  jnz     loc_14003E6AA
0x14003e339  mov     [rax], rcx
0x14003e33c  mov     [rcx+8], rax
0x14003e340  inc     dword ptr [rbx+2Ch]
0x14003e343  mov     edx, [rbx+2Ch]
0x14003e346  cmp     edx, [rbx+30h]
0x14003e349  jnz     short loc_14003E350
0x14003e34b  mov     [rbx+2Ch], esi
0x14003e34e  mov     edx, esi
0x14003e350  mov     rcx, rbx
0x14003e353  call    XilCommand_AdvanceCommandRingControlDequeuePointer
0x14003e358  lea     rcx, WPP_RECORDER_INITIALIZED
  ... truncated ...
```
