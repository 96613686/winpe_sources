# Controller_WdfEvtDevicePrepareHardware

- ea: `0x14007a8f0`
- end: `0x14007ad94`
- name: `Controller_WdfEvtDevicePrepareHardware`
- size: `1188`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x14001ad0c`
- `0x14001bb78`
- `0x14002b300`
- `0x140031928`
- `0x140035738`
- `0x1400408a8`
- `0x140040ac0`
- `0x140040b48`
- `0x1400451e8`
- `0x140046928`
- `0x140059970`
- `0x1400599b0`
- `0x140074008`
- `0x140075f20`
- `0x14007a8f0`
- `0x14007cbe0`
- `0x14007e5c8`
- `0x14007eb90`
- `0x1400801d8`
- `0x140080478`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14007a9c1`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14007a9c1`
- `ntoskrnl!DbgPrint` at `0x14007ad07`
- `ntoskrnl!DbgPrint` at `0x14007ad07`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterComponentEx` at `0x14007ac85`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterComponentEx` at `0x14007ac85`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x14007abc3`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x14007abe0`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x14007abc3`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x14007abe0`

## pseudocode

```c
__int64 __fastcall Controller_WdfEvtDevicePrepareHardware(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdi
  int v6; // edx
  char IsSecureDevice; // r12
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // esi
  int v14; // ecx
  int v15; // ecx
  __int64 v16; // rbx
  NTSTATUS v17; // eax
  int v18; // edx
  __int64 v19; // rcx
  int v20; // eax
  int v21; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v26; // [rsp+70h] [rbp-90h] BYREF
  __int128 v27; // [rsp+80h] [rbp-80h] BYREF
  char v28; // [rsp+90h] [rbp-70h] BYREF

  *(_QWORD *)&v24 = a2;
  DestinationString.Buffer = (wchar_t *)&v28;
  *(_QWORD *)&DestinationString.Length = 0x2000000;
  v27 = 0;
  v26 = 0;
  v5 = *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_14006C2C0)
                 + 8);
  IsSecureDevice = Controller_IsSecureDevice(v5);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_q(*(_QWORD *)(v5 + 72), v6, 4, 48, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, a1);
  }
  v8 = *(_DWORD *)(v5 + 1320);
  if ( v8 != KeQueryActiveProcessorCountEx(0xFFFFu) )
  {
    Controller_DeallocateIrqlTrackingArray(v5);
    Controller_AllocateIrqlTrackingArray(v5);
  }
  v9 = *(_QWORD *)(v5 + 88);
  *(_DWORD *)(v5 + 820) = 0;
  v10 = Register_PrepareHardware(v9, a3);
  v12 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(*(_QWORD *)(v5 + 72), 2, 4, 49, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v10);
    v13 = 1;
    goto LABEL_49;
  }
  v13 = 2;
  if ( !IsSecureDevice )
    goto LABEL_55;
  v11 = v5 + 104;
  if ( !*(_QWORD *)(v5 + 104) )
  {
    v12 = SecureDmaEnabler_Create(v5);
    if ( v12 < 0 )
      goto LABEL_49;
  }
  if ( *(_DWORD *)(v5 + 1052) == 2 )
  {
LABEL_55:
    if ( !*(_QWORD *)(v5 + 96) )
    {
      v12 = DmaEnabler_Create(a1, v5);
      if ( v12 < 0 )
      {
        v13 = 3;
LABEL_49:
        DbgPrint("USBXHCI: Controller enumeration failure in WdfEvtDevicePrepareHardware\n");
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = 1;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(v5 + 72),
            v21,
            4,
            52,
            (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
            v12);
        }
        Controller_ReportFatalErrorEx(v5, 32, 4137, v13, v12, 0, 0, 0);
        return (unsigned int)v12;
      }
    }
  }
  v14 = *(_DWORD *)(v5 + 1052);
  if ( v14 )
  {
    v15 = v14 - 1;
    if ( !v15 )
    {
      if ( *(_QWORD *)(v5 + 120) )
        goto LABEL_28;
      LOBYTE(v11) = 1;
      goto LABEL_26;
    }
    if ( v15 != 1 )
    {
      Debug_FreAssertMsg("Unexpected DMA mode", 0, "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\controller.c", 1567);
      v12 = -1073741630;
      v13 = 0;
      goto LABEL_49;
    }
  }
  if ( *(_QWORD *)(v5 + 120) )
    goto LABEL_28;
  v11 = 0;
LABEL_26:
  v12 = CommonBuffer_Create(v5, v11);
  if ( v12 < 0 )
  {
    v13 = 4;
    goto LABEL_49;
  }
LABEL_28:
  v12 = Interrupter_PrepareHardware(*(_QWORD *)(v5 + 128), v24, a3);
  if ( v12 < 0 )
  {
    v13 = 5;
    goto LABEL_49;
  }
  v12 = XilDeviceSlot_PrepareHardware(*(_QWORD *)(v5 + 136));
  if ( v12 < 0 )
  {
    v13 = 6;
    goto LABEL_49;
  }
  v12 = Command_PrepareHardware(*(_QWORD *)(v5 + 144));
  if ( v12 < 0 )
  {
    v13 = 7;
    goto LABEL_49;
  }
  v12 = RootHub_PrepareHardware(*(_QWORD *)(v5 + 152));
  if ( v12 < 0 )
  {
    v13 = 13;
    goto LABEL_49;
  }
  if ( *(_DWORD *)(v5 + 864) && *(_QWORD *)(g_WdfDriverUsbXhciContext + 32) )
  {
    v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 264))(WdfDriverGlobals, a1);
    SleepstudyHelper_GenerateGuid(0, v16, &v27);
    SleepstudyHelper_GenerateGuid(7, v16 + 336, &v26);
    v17 = RtlUnicodeStringPrintf(
            &DestinationString,
            L"USBXHCI Selective Suspend Disabled/ Unsupported: Reason code: %d",
            *(unsigned int *)(v5 + 864));
    v12 = v17;
    if ( v17 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v5 + 72),
          v18,
          4,
          50,
          (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
          v17);
      }
      v13 = 12;
      goto LABEL_49;
    }
    v24 = v26;
    v19 = *(_QWORD *)(g_WdfDriverUsbXhciContext + 32);
    v25 = v27;
    v20 = SleepstudyHelper_RegisterComponentEx(v19, &v25, &v24, &DestinationString, v5 + 1296);
    v12 = v20;
    if ( v20 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(*(_QWORD *)(v5 + 72), 3, 4, 51, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v20);
      *(_QWORD *)(v5 + 1296) = 0;
      v12 = 0;
    }
  }
  v13 = 0;
  if ( (*(_DWORD *)(v5 + 744) & 0x100000LL) != 0 )
    Controller_ClearHSIIWorkaround(v5);
  if ( v12 < 0 )
    goto LABEL_49;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14007a8f0  mov     [rsp-8+arg_18], rbx
0x14007a8f5  push    rbp
0x14007a8f6  push    rsi
0x14007a8f7  push    rdi
0x14007a8f8  push    r12
0x14007a8fa  push    r13
0x14007a8fc  push    r14
0x14007a8fe  push    r15
0x14007a900  lea     rbp, [rsp-1A0h]
0x14007a908  sub     rsp, 2A0h
0x14007a90f  mov     rax, cs:__security_cookie
0x14007a916  xor     rax, rsp
0x14007a919  mov     [rbp+1D0h+var_40], rax
0x14007a920  lea     rax, [rbp+1D0h+var_240]
0x14007a924  mov     qword ptr [rsp+2D0h+var_280], rdx
0x14007a929  mov     [rsp+2D0h+DestinationString.Buffer], rax
0x14007a92e  xorps   xmm0, xmm0
0x14007a931  mov     rax, cs:WdfFunctions_01033
0x14007a938  xorps   xmm1, xmm1
0x14007a93b  mov     r13, r8
0x14007a93e  mov     qword ptr [rsp+2D0h+DestinationString.Length], 2000000h
0x14007a947  mov     r8, cs:off_14006C2C0
0x14007a94e  mov     r15, rcx
0x14007a951  movups  [rbp+1D0h+var_250], xmm0
0x14007a955  mov     rdx, rcx
0x14007a958  mov     rcx, cs:WdfDriverGlobals
0x14007a95f  movups  [rsp+2D0h+var_260], xmm1
0x14007a964  mov     rax, [rax+650h]
0x14007a96b  call    _guard_dispatch_icall
0x14007a970  mov     rdi, [rax+8]
0x14007a974  mov     rcx, rdi
0x14007a977  call    Controller_IsSecureDevice
0x14007a97c  mov     r12b, al
0x14007a97f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007a986  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007a98d  lea     rsi, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14007a994  jz      short loc_14007A9B6
0x14007a996  mov     rcx, [rdi+48h]
0x14007a99a  mov     r9d, 30h ; '0'
0x14007a9a0  mov     [rsp+2D0h+var_2A8], r15
0x14007a9a5  mov     [rsp+2D0h+var_2B0], rsi
0x14007a9aa  lea     r8d, [r9-2Ch]
0x14007a9ae  mov     dl, r8b
0x14007a9b1  call    WPP_RECORDER_SF_q
0x14007a9b6  mov     ebx, [rdi+528h]
0x14007a9bc  mov     ecx, 0FFFFh; GroupNumber
0x14007a9c1  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14007a9c8  nop     dword ptr [rax+rax+00h]
0x14007a9cd  cmp     ebx, eax
0x14007a9cf  jz      short loc_14007A9E1
0x14007a9d1  mov     rcx, rdi
0x14007a9d4  call    Controller_DeallocateIrqlTrackingArray
0x14007a9d9  mov     rcx, rdi
0x14007a9dc  call    Controller_AllocateIrqlTrackingArray
0x14007a9e1  mov     rcx, [rdi+58h]
0x14007a9e5  mov     rdx, r13
0x14007a9e8  mov     dword ptr [rdi+334h], 0
0x14007a9f2  call    Register_PrepareHardware
0x14007a9f7  mov     ebx, eax
0x14007a9f9  test    eax, eax
0x14007a9fb  jns     short loc_14007AA41
0x14007a9fd  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007aa04  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14007aa0b  jz      short loc_14007AA2D
0x14007aa0d  mov     rcx, [rdi+48h]
0x14007aa11  mov     r9d, 31h ; '1'
0x14007aa17  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x14007aa1b  mov     [rsp+2D0h+var_2B0], rsi
0x14007aa20  lea     edx, [r9-2Fh]
0x14007aa24  lea     r8d, [r9-2Dh]
0x14007aa28  call    WPP_RECORDER_SF_d
0x14007aa2d  mov     esi, 1
0x14007aa32  lea     r15, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14007aa39  xor     r12d, r12d
0x14007aa3c  jmp     loc_14007AD00
0x14007aa41  mov     esi, 2
0x14007aa46  test    r12b, r12b
0x14007aa49  jz      short loc_14007AA8E
0x14007aa4b  lea     rdx, [rdi+68h]
0x14007aa4f  xor     r12d, r12d
0x14007aa52  cmp     [rdx], r12
0x14007aa55  jnz     short loc_14007AA65
0x14007aa57  mov     rcx, rdi
0x14007aa5a  call    SecureDmaEnabler_Create
0x14007aa5f  mov     ebx, eax
0x14007aa61  test    eax, eax
0x14007aa63  js      short loc_14007AACA
0x14007aa65  cmp     [rdi+41Ch], esi
0x14007aa6b  jnz     short loc_14007AA93
0x14007aa6d  lea     r8, [rdi+60h]
0x14007aa71  cmp     [r8], r12
0x14007aa74  jnz     short loc_14007AA93
0x14007aa76  mov     rdx, rdi
0x14007aa79  mov     rcx, r15
0x14007aa7c  call    DmaEnabler_Create
0x14007aa81  mov     ebx, eax
0x14007aa83  test    eax, eax
0x14007aa85  jns     short loc_14007AA93
0x14007aa87  mov     esi, 3
0x14007aa8c  jmp     short loc_14007AACA
0x14007aa8e  xor     r12d, r12d
0x14007aa91  jmp     short loc_14007AA6D
0x14007aa93  mov     ecx, [rdi+41Ch]
0x14007aa99  test    ecx, ecx
0x14007aa9b  jz      short loc_14007AAEA
0x14007aa9d  sub     ecx, 1
0x14007aaa0  jz      short loc_14007AADD
0x14007aaa2  cmp     ecx, 1
0x14007aaa5  jz      short loc_14007AAEA
0x14007aaa7  mov     r9d, 61Fh
0x14007aaad  lea     r8, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14007aab4  xor     edx, edx
0x14007aab6  lea     rcx, aUnexpectedDmaM; "Unexpected DMA mode"
0x14007aabd  call    Debug_FreAssertMsg
0x14007aac2  mov     ebx, 0C00000C2h
0x14007aac7  mov     rsi, r12
0x14007aaca  lea     r15, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14007aad1  lea     r13, WPP_RECORDER_INITIALIZED
0x14007aad8  jmp     loc_14007AD00
0x14007aadd  lea     r8, [rdi+78h]
0x14007aae1  cmp     [r8], r12
0x14007aae4  jnz     short loc_14007AB0A
0x14007aae6  mov     dl, 1
0x14007aae8  jmp     short loc_14007AAF5
0x14007aaea  lea     r8, [rdi+78h]
0x14007aaee  cmp     [r8], r12
0x14007aaf1  jnz     short loc_14007AB0A
0x14007aaf3  xor     edx, edx
0x14007aaf5  mov     rcx, rdi
0x14007aaf8  call    CommonBuffer_Create
0x14007aafd  mov     ebx, eax
0x14007aaff  test    eax, eax
0x14007ab01  jns     short loc_14007AB0A
0x14007ab03  mov     esi, 4
0x14007ab08  jmp     short loc_14007AACA
0x14007ab0a  mov     rdx, qword ptr [rsp+2D0h+var_280]
0x14007ab0f  mov     r8, r13
0x14007ab12  mov     rcx, [rdi+80h]
0x14007ab19  call    Interrupter_PrepareHardware
0x14007ab1e  mov     ebx, eax
0x14007ab20  test    eax, eax
0x14007ab22  jns     short loc_14007AB2B
0x14007ab24  mov     esi, 5
0x14007ab29  jmp     short loc_14007AACA
0x14007ab2b  mov     rcx, [rdi+88h]
0x14007ab32  call    XilDeviceSlot_PrepareHardware
0x14007ab37  mov     ebx, eax
0x14007ab39  test    eax, eax
0x14007ab3b  jns     short loc_14007AB44
0x14007ab3d  mov     esi, 6
0x14007ab42  jmp     short loc_14007AACA
0x14007ab44  mov     rcx, [rdi+90h]
0x14007ab4b  call    Command_PrepareHardware
0x14007ab50  mov     ebx, eax
0x14007ab52  test    eax, eax
0x14007ab54  jns     short loc_14007AB60
0x14007ab56  mov     esi, 7
0x14007ab5b  jmp     loc_14007AACA
0x14007ab60  mov     rcx, [rdi+98h]
0x14007ab67  call    RootHub_PrepareHardware
0x14007ab6c  mov     ebx, eax
0x14007ab6e  test    eax, eax
0x14007ab70  jns     short loc_14007AB7C
0x14007ab72  mov     esi, 0Dh
0x14007ab77  jmp     loc_14007AACA
0x14007ab7c  cmp     [rdi+360h], r12d
0x14007ab83  jz      loc_14007ACD6
0x14007ab89  mov     rax, cs:g_WdfDriverUsbXhciContext
0x14007ab90  cmp     [rax+20h], r12
0x14007ab94  jz      loc_14007ACD6
0x14007ab9a  mov     rax, cs:WdfFunctions_01033
0x14007aba1  mov     rdx, r15
0x14007aba4  mov     rcx, cs:WdfDriverGlobals
0x14007abab  mov     rax, [rax+108h]
0x14007abb2  call    _guard_dispatch_icall
0x14007abb7  lea     r8, [rbp+1D0h+var_250]
0x14007abbb  mov     rdx, rax
0x14007abbe  xor     ecx, ecx
0x14007abc0  mov     rbx, rax
0x14007abc3  call    cs:__imp_SleepstudyHelper_GenerateGuid
0x14007abca  nop     dword ptr [rax+rax+00h]
0x14007abcf  lea     rdx, [rbx+150h]
0x14007abd6  mov     ecx, 7
0x14007abdb  lea     r8, [rsp+2D0h+var_260]
0x14007abe0  call    cs:__imp_SleepstudyHelper_GenerateGuid
0x14007abe7  nop     dword ptr [rax+rax+00h]
0x14007abec  mov     r8d, [rdi+360h]
0x14007abf3  lea     rdx, aUsbxhciSelecti; "USBXHCI Selective Suspend Disabled/ Uns"...
0x14007abfa  lea     rcx, [rsp+2D0h+DestinationString]; DestinationString
0x14007abff  call    RtlUnicodeStringPrintf
0x14007ac04  mov     ebx, eax
0x14007ac06  test    eax, eax
0x14007ac08  jns     short loc_14007AC4A
0x14007ac0a  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007ac11  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14007ac18  lea     r15, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14007ac1f  jz      short loc_14007AC40
0x14007ac21  mov     rcx, [rdi+48h]
0x14007ac25  mov     r9d, 32h ; '2'
0x14007ac2b  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x14007ac2f  mov     dl, sil
0x14007ac32  mov     [rsp+2D0h+var_2B0], r15
0x14007ac37  lea     r8d, [r9-2Eh]
0x14007ac3b  call    WPP_RECORDER_SF_d
0x14007ac40  mov     esi, 0Ch
0x14007ac45  jmp     loc_14007AD00
0x14007ac4a  mov     rcx, cs:g_WdfDriverUsbXhciContext
0x14007ac51  lea     r14, [rdi+510h]
0x14007ac58  movaps  xmm0, [rsp+2D0h+var_260]
0x14007ac5d  lea     r9, [rsp+2D0h+DestinationString]
0x14007ac62  movaps  xmm1, [rbp+1D0h+var_250]
0x14007ac66  lea     r8, [rsp+2D0h+var_280]
0x14007ac6b  lea     rdx, [rsp+2D0h+var_270]
0x14007ac70  movdqa  [rsp+2D0h+var_280], xmm0
0x14007ac76  mov     rcx, [rcx+20h]
0x14007ac7a  movdqa  [rsp+2D0h+var_270], xmm1
0x14007ac80  mov     [rsp+2D0h+var_2B0], r14
0x14007ac85  call    cs:__imp_SleepstudyHelper_RegisterComponentEx
0x14007ac8c  nop     dword ptr [rax+rax+00h]
0x14007ac91  mov     ebx, eax
0x14007ac93  test    eax, eax
0x14007ac95  jns     short loc_14007ACD6
0x14007ac97  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007ac9e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14007aca5  lea     r15, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14007acac  jz      short loc_14007ACCE
0x14007acae  mov     rcx, [rdi+48h]
0x14007acb2  mov     r9d, 33h ; '3'
0x14007acb8  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x14007acbc  mov     [rsp+2D0h+var_2B0], r15
0x14007acc1  lea     edx, [r9-30h]
0x14007acc5  lea     r8d, [r9-2Fh]
0x14007acc9  call    WPP_RECORDER_SF_d
0x14007acce  mov     [r14], r12
0x14007acd1  mov     ebx, r12d
0x14007acd4  jmp     short loc_14007ACE4
0x14007acd6  lea     r15, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14007acdd  lea     r13, WPP_RECORDER_INITIALIZED
0x14007ace4  mov     eax, [rdi+2E8h]
0x14007acea  mov     rsi, r12
0x14007aced  bt      rax, 14h
0x14007acf2  jnb     short loc_14007ACFC
0x14007acf4  mov     rcx, rdi
0x14007acf7  call    Controller_ClearHSIIWorkaround
0x14007acfc  test    ebx, ebx
0x14007acfe  jns     short loc_14007AD67
0x14007ad00  lea     rcx, aUsbxhciControl; "USBXHCI: Controller enumeration failure"...
0x14007ad07  call    cs:__imp_DbgPrint
0x14007ad0e  nop     dword ptr [rax+rax+00h]
0x14007ad13  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007ad1a  jz      short loc_14007AD3A
0x14007ad1c  mov     rcx, [rdi+48h]
0x14007ad20  mov     r9d, 34h ; '4'
0x14007ad26  mov     dword ptr [rsp+2D0h+var_2A8], ebx
0x14007ad2a  mov     dl, 1
0x14007ad2c  mov     [rsp+2D0h+var_2B0], r15
0x14007ad31  lea     r8d, [r9-30h]
0x14007ad35  call    WPP_RECORDER_SF_d
0x14007ad3a  mov     [rsp+2D0h+var_298], r12
0x14007ad3f  mov     r9, rsi
0x14007ad42  mov     [rsp+2D0h+var_2A0], r12
0x14007ad47  mov     edx, 20h ; ' '
0x14007ad4c  movsxd  rax, ebx
0x14007ad4f  mov     r8d, 1029h
0x14007ad55  mov     [rsp+2D0h+var_2A8], r12
0x14007ad5a  mov     rcx, rdi
0x14007ad5d  mov     [rsp+2D0h+var_2B0], rax
0x14007ad62  call    Controller_ReportFatalErrorEx
0x14007ad67  mov     eax, ebx
0x14007ad69  mov     rcx, [rbp+1D0h+var_40]
0x14007ad70  xor     rcx, rsp; StackCookie
0x14007ad73  call    __security_check_cookie
0x14007ad78  mov     rbx, [rsp+2D0h+arg_18]
0x14007ad80  add     rsp, 2A0h
0x14007ad87  pop     r15
0x14007ad89  pop     r14
0x14007ad8b  pop     r13
0x14007ad8d  pop     r12
0x14007ad8f  pop     rdi
0x14007ad90  pop     rsi
0x14007ad91  pop     rbp
0x14007ad92  retn
```
