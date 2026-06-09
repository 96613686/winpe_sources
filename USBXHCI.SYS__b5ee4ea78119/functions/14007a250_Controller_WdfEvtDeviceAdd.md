# Controller_WdfEvtDeviceAdd

- ea: `0x14007a250`
- end: `0x14007a815`
- name: `Controller_WdfEvtDeviceAdd`
- size: `1477`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140002568`
- `0x14001ad0c`
- `0x140040800`
- `0x14004278c`
- `0x14004464c`
- `0x140044cd8`
- `0x14004ff50`
- `0x140059970`
- `0x1400599b0`
- `0x140059d80`
- `0x140074588`
- `0x140075b9c`
- `0x14007626c`
- `0x1400765ec`
- `0x1400767c8`
- `0x14007a250`
- `0x14007b13c`
- `0x14007bf58`
- `0x14007d7dc`
- `0x14007d9d0`
- `0x14007e8f4`
- `0x14007fa54`
- `0x14007fcec`
- `0x140080778`
- `0x1400825d4`

## import_xrefs

- `ntoskrnl!IoGetDevicePropertyData` at `0x14007a4a4`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14007a4a4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007a78c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007a78c`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14007a309`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14007a309`

## pseudocode

```c
__int64 __fastcall Controller_WdfEvtDeviceAdd(__int64 a1, __int64 a2)
{
  int v3; // eax
  int v4; // edx
  int v5; // ebx
  int v6; // r9d
  __int64 v8; // r15
  struct _DEVICE_OBJECT *v9; // rax
  NTSTATUS DevicePropertyData; // eax
  int v11; // edx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  __int64 v17; // rcx
  int Data; // [rsp+28h] [rbp-D8h]
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  ULONG Type; // [rsp+58h] [rbp-A8h] BYREF
  ULONG RequiredSize; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v24; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v25[4]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  _WORD v28[200]; // [rsp+A0h] [rbp-60h] BYREF

  v26 = 0;
  v25[0] = 56;
  LOBYTE(v26) = 0;
  v25[2] = 0;
  v25[3] = 0x1000000000LL;
  v27 = 0x200000002LL;
  v25[1] = 0xC800000400LL;
  v21 = 0;
  v20 = 0;
  v24 = 0;
  RequiredSize = 0;
  Type = 0;
  v19 = 0;
  imp_WppRecorderLogCreate(WPP_GLOBAL_Control, v25, &v20);
  v3 = ((__int64 (__fastcall *)(__int64, __int64))qword_14006CD68)(UcxDriverGlobals, a2);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_5;
    v6 = 10;
    goto LABEL_4;
  }
  v5 = Controller_CreateWdfDevice(a2, v20, &v21, &v24);
  if ( v5 < 0 )
    goto LABEL_5;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         v21,
         off_14006C2C0);
  if ( (unsigned __int8)Device_IsSecureDevice(v8) )
  {
    if ( (unsigned int)Feature_XhciCompanionEtw__private_IsEnabledDeviceUsageNoInline() )
    {
      memset(v28, 0, sizeof(v28));
      RequiredSize = 0;
      Type = 0;
      v9 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 264))(
                                      WdfDriverGlobals,
                                      v21);
      DevicePropertyData = IoGetDevicePropertyData(
                             v9,
                             &DEVPKEY_Device_InstanceId,
                             0,
                             0,
                             0x190u,
                             v28,
                             &RequiredSize,
                             &Type);
      if ( DevicePropertyData < 0 || Type != 18 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = 2;
          WPP_RECORDER_SF_DD(
            v20,
            v11,
            4,
            11,
            (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
            DevicePropertyData,
            Type);
        }
        v28[0] = 0;
      }
    }
    v3 = SecureChannel_Create(v8, v28, v8 + 96);
    v5 = v3;
    if ( v3 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v6 = 12;
LABEL_4:
        LOBYTE(v4) = 2;
        WPP_RECORDER_SF_d(v20, v4, 4, v6, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v3);
        goto LABEL_5;
      }
      goto LABEL_5;
    }
  }
  v3 = Controller_Create(v21, v20, v24, &v19);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 13;
      goto LABEL_4;
    }
LABEL_5:
    if ( v19 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 1664))(
        WdfDriverGlobals,
        *(_QWORD *)(v19 + 8));
    return (unsigned int)v5;
  }
  v12 = v19;
  *(_OWORD *)(v19 + 180) = *(_OWORD *)(v8 + 24);
  *(_OWORD *)(v12 + 196) = *(_OWORD *)(v8 + 40);
  *(_OWORD *)(v12 + 212) = *(_OWORD *)(v8 + 56);
  *(_OWORD *)(v12 + 228) = *(_OWORD *)(v8 + 72);
  *(_QWORD *)(v8 + 8) = v19;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 (__fastcall *)(), __int64, const char *))(WdfFunctions_01033 + 1640))(
    WdfDriverGlobals,
    *(_QWORD *)(v19 + 8),
    Controller_WdfEvtDeviceAdd,
    371,
    "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\controller.c");
  v3 = IoControl_Create(v21, v19, v19 + 80);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 14;
      goto LABEL_4;
    }
    goto LABEL_5;
  }
  v3 = Register_Create(v19, v19 + 88);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 15;
      goto LABEL_4;
    }
    goto LABEL_5;
  }
  v3 = Interrupter_Create(v21, v19, v19 + 128);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 16;
      goto LABEL_4;
    }
    goto LABEL_5;
  }
  v3 = DeviceSlot_Create(v13, v19, v19 + 136);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 17;
      goto LABEL_4;
    }
    goto LABEL_5;
  }
  v3 = Command_Create(v14, v19, v19 + 144);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 18;
      goto LABEL_4;
    }
    goto LABEL_5;
  }
  v15 = (_QWORD *)(v19 + 168);
  if ( (*(_DWORD *)(v19 + 736) & 0x800000LL) != 0 )
  {
    v3 = IntelPptFilter_Create(v21, v19, v19 + 168);
    v5 = v3;
    if ( v3 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v6 = 19;
        goto LABEL_4;
      }
      goto LABEL_5;
    }
  }
  else
  {
    *v15 = 0;
  }
  v3 = RootHub_Create(v15, v19, v19 + 152);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 20;
      goto LABEL_4;
    }
    goto LABEL_5;
  }
  v3 = Wmi_Create(v21, v19, v19 + 160);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 21;
      goto LABEL_4;
    }
    goto LABEL_5;
  }
  *(_QWORD *)v8 = g_UsbXhciTriageInfo;
  Controller_ConfigureS0IdleSettings(v19);
  Controller_ConfigureSxWakeSettings(v19);
  KeInitializeSpinLock((PKSPIN_LOCK)(v19 + 40));
  v16 = (_QWORD *)(v19 + 48);
  *(_QWORD *)(v19 + 56) = v19 + 48;
  *v16 = v16;
  *(_DWORD *)(v19 + 64) = 0;
  *(_DWORD *)(v19 + 792) = 5;
  Controller_AddControllerToGlobalControllerList(v19);
  Etw_ControllerCreate(v17, v19);
  Controller_QueryControllerCapabilitiesFromACPI(v19);
  if ( (*(_BYTE *)(v19 + 744) & 1) != 0 )
  {
    LOWORD(Data) = 0;
    Controller_ExecuteDSM(v19, &GUID_DSM_ENABLE_KBL_WORKAROUNDS, 1, 1, 0, Data);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14007a250  mov     [rsp-8+arg_0], rbx
0x14007a255  mov     [rsp-8+arg_10], rsi
0x14007a25a  push    rbp
0x14007a25b  push    rdi
0x14007a25c  push    r12
0x14007a25e  push    r14
0x14007a260  push    r15
0x14007a262  lea     rbp, [rsp-140h]
0x14007a26a  sub     rsp, 240h
0x14007a271  mov     rax, cs:__security_cookie
0x14007a278  xor     rax, rsp
0x14007a27b  mov     [rbp+160h+var_30], rax
0x14007a282  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a289  lea     r8, [rsp+260h+var_218]
0x14007a28e  xor     r12d, r12d
0x14007a291  xorps   xmm0, xmm0
0x14007a294  movups  [rsp+260h+var_1F8], xmm0
0x14007a299  xor     eax, eax
0x14007a29b  mov     rdi, rdx
0x14007a29e  movups  [rsp+260h+var_1E8], xmm0
0x14007a2a3  mov     [rbp+160h+var_1C8], rax
0x14007a2a7  lea     rdx, [rsp+260h+var_1F8]
0x14007a2ac  movups  [rbp+160h+var_1D8], xmm0
0x14007a2b0  mov     qword ptr [rsp+260h+var_1F8], 38h ; '8'
0x14007a2b9  mov     byte ptr [rbp+160h+var_1D8], r12b
0x14007a2bd  mov     dword ptr [rbp+160h+var_1E8+0Ch], 10h
0x14007a2c4  mov     qword ptr [rsp+260h+var_1E8], r12
0x14007a2c9  mov     byte ptr [rbp+160h+var_1E8+8], r12b
0x14007a2cd  mov     dword ptr [rbp+160h+var_1C8], 2
0x14007a2d4  mov     dword ptr [rbp+160h+var_1C8+4], 2
0x14007a2db  mov     dword ptr [rsp+260h+var_1F8+8], 400h
0x14007a2e3  mov     dword ptr [rsp+260h+var_1F8+0Ch], 0C8h
0x14007a2eb  mov     [rsp+260h+var_210], r12
0x14007a2f0  mov     [rsp+260h+var_218], r12
0x14007a2f5  mov     [rsp+260h+var_200], r12d
0x14007a2fa  mov     [rsp+260h+var_204], r12d
0x14007a2ff  mov     [rsp+260h+var_208], r12d
0x14007a304  mov     [rsp+260h+var_220], r12
0x14007a309  call    cs:__imp_imp_WppRecorderLogCreate
0x14007a310  nop     dword ptr [rax+rax+00h]
0x14007a315  mov     rax, cs:qword_14006CD68
0x14007a31c  mov     rdx, rdi
0x14007a31f  mov     rcx, cs:UcxDriverGlobals
0x14007a326  call    _guard_dispatch_icall
0x14007a32b  mov     ebx, eax
0x14007a32d  test    eax, eax
0x14007a32f  jns     loc_14007A3C1
0x14007a335  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007a33c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14007a343  jz      short loc_14007A36B
0x14007a345  lea     r9d, [r12+0Ah]
0x14007a34a  lea     r14, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14007a351  lea     r8d, [r12+4]
0x14007a356  mov     rcx, [rsp+260h+var_218]
0x14007a35b  mov     dl, 2
0x14007a35d  mov     dword ptr [rsp+260h+Data], eax
0x14007a361  mov     qword ptr [rsp+260h+Size], r14
0x14007a366  call    WPP_RECORDER_SF_d
0x14007a36b  mov     rdx, [rsp+260h+var_220]
0x14007a370  test    rdx, rdx
0x14007a373  jz      short loc_14007A393
0x14007a375  mov     rax, cs:WdfFunctions_01033
0x14007a37c  mov     rdx, [rdx+8]
0x14007a380  mov     rcx, cs:WdfDriverGlobals
0x14007a387  mov     rax, [rax+680h]
0x14007a38e  call    _guard_dispatch_icall
0x14007a393  mov     eax, ebx
0x14007a395  mov     rcx, [rbp+160h+var_30]
0x14007a39c  xor     rcx, rsp; StackCookie
0x14007a39f  call    __security_check_cookie
0x14007a3a4  lea     r11, [rsp+260h+var_20]
0x14007a3ac  mov     rbx, [r11+30h]
0x14007a3b0  mov     rsi, [r11+40h]
0x14007a3b4  mov     rsp, r11
0x14007a3b7  pop     r15
0x14007a3b9  pop     r14
0x14007a3bb  pop     r12
0x14007a3bd  pop     rdi
0x14007a3be  pop     rbp
0x14007a3bf  retn
0x14007a3c1  mov     rdx, [rsp+260h+var_218]
0x14007a3c6  lea     r9, [rsp+260h+var_200]
0x14007a3cb  lea     r8, [rsp+260h+var_210]
0x14007a3d0  mov     rcx, rdi
0x14007a3d3  call    Controller_CreateWdfDevice
0x14007a3d8  mov     ebx, eax
0x14007a3da  test    eax, eax
0x14007a3dc  js      short loc_14007A36B
0x14007a3de  mov     rax, cs:WdfFunctions_01033
0x14007a3e5  mov     r8, cs:off_14006C2C0
0x14007a3ec  mov     rdx, [rsp+260h+var_210]
0x14007a3f1  mov     rcx, cs:WdfDriverGlobals
0x14007a3f8  mov     rax, [rax+650h]
0x14007a3ff  call    _guard_dispatch_icall
0x14007a404  mov     rcx, rax
0x14007a407  mov     r15, rax
0x14007a40a  call    Device_IsSecureDevice
0x14007a40f  lea     rdi, WPP_RECORDER_INITIALIZED
0x14007a416  mov     esi, 4
0x14007a41b  lea     r14, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14007a422  test    al, al
0x14007a424  jz      loc_14007A51E
0x14007a42a  call    Feature_XhciCompanionEtw__private_IsEnabledDeviceUsageNoInline
0x14007a42f  test    eax, eax
0x14007a431  jz      loc_14007A4ED
0x14007a437  mov     ebx, 190h
0x14007a43c  lea     rcx, [rbp+160h+var_1C0]; void *
0x14007a440  mov     r8d, ebx; Size
0x14007a443  xor     edx, edx; Val
0x14007a445  call    memset
0x14007a44a  mov     rax, cs:WdfFunctions_01033
0x14007a451  mov     rdx, [rsp+260h+var_210]
0x14007a456  mov     rcx, cs:WdfDriverGlobals
0x14007a45d  mov     [rsp+260h+var_204], r12d
0x14007a462  mov     [rsp+260h+var_208], r12d
0x14007a467  mov     rax, [rax+108h]
0x14007a46e  call    _guard_dispatch_icall
0x14007a473  lea     rcx, [rsp+260h+var_208]
0x14007a478  xor     r9d, r9d; Flags
0x14007a47b  mov     [rsp+260h+Type], rcx; Type
0x14007a480  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x14007a487  lea     rcx, [rsp+260h+var_204]
0x14007a48c  xor     r8d, r8d; Lcid
0x14007a48f  mov     [rsp+260h+RequiredSize], rcx; RequiredSize
0x14007a494  lea     rcx, [rbp+160h+var_1C0]
0x14007a498  mov     [rsp+260h+Data], rcx; Data
0x14007a49d  mov     rcx, rax; Pdo
0x14007a4a0  mov     [rsp+260h+Size], ebx; Size
0x14007a4a4  call    cs:__imp_IoGetDevicePropertyData
0x14007a4ab  nop     dword ptr [rax+rax+00h]
0x14007a4b0  mov     ecx, [rsp+260h+var_208]
0x14007a4b4  test    eax, eax
0x14007a4b6  js      short loc_14007A4BD
0x14007a4b8  cmp     ecx, 12h
0x14007a4bb  jz      short loc_14007A4ED
0x14007a4bd  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a4c4  jz      short loc_14007A4E8
0x14007a4c6  mov     dword ptr [rsp+260h+RequiredSize], ecx
0x14007a4ca  mov     r9d, 0Bh
0x14007a4d0  mov     rcx, [rsp+260h+var_218]
0x14007a4d5  mov     r8d, esi
0x14007a4d8  mov     dword ptr [rsp+260h+Data], eax
0x14007a4dc  mov     dl, 2
0x14007a4de  mov     qword ptr [rsp+260h+Size], r14
0x14007a4e3  call    WPP_RECORDER_SF_DD
0x14007a4e8  mov     [rbp+160h+var_1C0], r12w
0x14007a4ed  lea     r8, [r15+60h]
0x14007a4f1  mov     rcx, r15
0x14007a4f4  lea     rdx, [rbp+160h+var_1C0]
0x14007a4f8  call    SecureChannel_Create
0x14007a4fd  mov     ebx, eax
0x14007a4ff  test    eax, eax
0x14007a501  jns     short loc_14007A51E
0x14007a503  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a50a  jz      loc_14007A36B
0x14007a510  mov     r9d, 0Ch
0x14007a516  mov     r8d, esi
0x14007a519  jmp     loc_14007A356
0x14007a51e  mov     r8d, [rsp+260h+var_200]
0x14007a523  lea     r9, [rsp+260h+var_220]
0x14007a528  mov     rdx, [rsp+260h+var_218]
0x14007a52d  mov     rcx, [rsp+260h+var_210]
0x14007a532  call    Controller_Create
0x14007a537  mov     ebx, eax
0x14007a539  test    eax, eax
0x14007a53b  jns     short loc_14007A552
0x14007a53d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a544  jz      loc_14007A36B
0x14007a54a  mov     r9d, 0Dh
0x14007a550  jmp     short loc_14007A516
0x14007a552  mov     rax, [rsp+260h+var_220]
0x14007a557  lea     rcx, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14007a55e  movups  xmm0, xmmword ptr [r15+18h]
0x14007a563  mov     qword ptr [rsp+260h+Size], rcx
0x14007a568  lea     r8, Controller_WdfEvtDeviceAdd
0x14007a56f  mov     r9d, 173h
0x14007a575  movups  xmmword ptr [rax+0B4h], xmm0
0x14007a57c  movups  xmm1, xmmword ptr [r15+28h]
0x14007a581  movups  xmmword ptr [rax+0C4h], xmm1
0x14007a588  movups  xmm0, xmmword ptr [r15+38h]
0x14007a58d  movups  xmmword ptr [rax+0D4h], xmm0
0x14007a594  movups  xmm1, xmmword ptr [r15+48h]
0x14007a599  movups  xmmword ptr [rax+0E4h], xmm1
0x14007a5a0  mov     rax, [rsp+260h+var_220]
0x14007a5a5  mov     [r15+8], rax
0x14007a5a9  mov     rax, cs:WdfFunctions_01033
0x14007a5b0  mov     rdx, [rsp+260h+var_220]
0x14007a5b5  mov     rcx, cs:WdfDriverGlobals
0x14007a5bc  mov     rax, [rax+668h]
0x14007a5c3  mov     rdx, [rdx+8]
0x14007a5c7  call    _guard_dispatch_icall
0x14007a5cc  mov     rdx, [rsp+260h+var_220]
0x14007a5d1  mov     rcx, [rsp+260h+var_210]
0x14007a5d6  lea     r8, [rdx+50h]
0x14007a5da  call    IoControl_Create
0x14007a5df  mov     ebx, eax
0x14007a5e1  test    eax, eax
0x14007a5e3  jns     short loc_14007A5FD
0x14007a5e5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a5ec  jz      loc_14007A36B
0x14007a5f2  mov     r9d, 0Eh
0x14007a5f8  jmp     loc_14007A516
0x14007a5fd  mov     rcx, [rsp+260h+var_220]
0x14007a602  lea     rdx, [rcx+58h]
0x14007a606  call    Register_Create
0x14007a60b  mov     ebx, eax
0x14007a60d  test    eax, eax
0x14007a60f  jns     short loc_14007A629
0x14007a611  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a618  jz      loc_14007A36B
0x14007a61e  mov     r9d, 0Fh
0x14007a624  jmp     loc_14007A516
0x14007a629  mov     rdx, [rsp+260h+var_220]
0x14007a62e  mov     rcx, [rsp+260h+var_210]
0x14007a633  lea     r8, [rdx+80h]
0x14007a63a  call    Interrupter_Create
0x14007a63f  mov     ebx, eax
0x14007a641  test    eax, eax
0x14007a643  jns     short loc_14007A65D
0x14007a645  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a64c  jz      loc_14007A36B
0x14007a652  mov     r9d, 10h
0x14007a658  jmp     loc_14007A516
0x14007a65d  mov     rdx, [rsp+260h+var_220]
0x14007a662  lea     r8, [rdx+88h]
0x14007a669  call    DeviceSlot_Create
0x14007a66e  mov     ebx, eax
0x14007a670  test    eax, eax
0x14007a672  jns     short loc_14007A68C
0x14007a674  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a67b  jz      loc_14007A36B
0x14007a681  mov     r9d, 11h
0x14007a687  jmp     loc_14007A516
0x14007a68c  mov     rdx, [rsp+260h+var_220]
0x14007a691  lea     r8, [rdx+90h]
0x14007a698  call    Command_Create
0x14007a69d  mov     ebx, eax
0x14007a69f  test    eax, eax
0x14007a6a1  jns     short loc_14007A6BB
0x14007a6a3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a6aa  jz      loc_14007A36B
0x14007a6b0  mov     r9d, 12h
0x14007a6b6  jmp     loc_14007A516
0x14007a6bb  mov     rdx, [rsp+260h+var_220]
0x14007a6c0  mov     eax, [rdx+2E0h]
0x14007a6c6  lea     rcx, [rdx+0A8h]
0x14007a6cd  bt      rax, 17h
0x14007a6d2  jnb     short loc_14007A6FF
0x14007a6d4  mov     r8, rcx
0x14007a6d7  mov     rcx, [rsp+260h+var_210]
0x14007a6dc  call    IntelPptFilter_Create
0x14007a6e1  mov     ebx, eax
0x14007a6e3  test    eax, eax
0x14007a6e5  jns     short loc_14007A702
0x14007a6e7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a6ee  jz      loc_14007A36B
0x14007a6f4  mov     r9d, 13h
0x14007a6fa  jmp     loc_14007A516
0x14007a6ff  mov     [rcx], r12
0x14007a702  mov     rdx, [rsp+260h+var_220]
0x14007a707  lea     r8, [rdx+98h]
0x14007a70e  call    RootHub_Create
0x14007a713  mov     ebx, eax
0x14007a715  test    eax, eax
0x14007a717  jns     short loc_14007A731
0x14007a719  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a720  jz      loc_14007A36B
0x14007a726  mov     r9d, 14h
0x14007a72c  jmp     loc_14007A516
0x14007a731  mov     rdx, [rsp+260h+var_220]
0x14007a736  mov     rcx, [rsp+260h+var_210]
0x14007a73b  lea     r8, [rdx+0A0h]
0x14007a742  call    Wmi_Create
0x14007a747  mov     ebx, eax
0x14007a749  test    eax, eax
0x14007a74b  jns     short loc_14007A765
0x14007a74d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14007a754  jz      loc_14007A36B
0x14007a75a  mov     r9d, 15h
0x14007a760  jmp     loc_14007A516
0x14007a765  lea     rax, g_UsbXhciTriageInfo; "Ver1h"
0x14007a76c  mov     [r15], rax
0x14007a76f  mov     rcx, [rsp+260h+var_220]
0x14007a774  call    Controller_ConfigureS0IdleSettings
0x14007a779  mov     rcx, [rsp+260h+var_220]
0x14007a77e  call    Controller_ConfigureSxWakeSettings
0x14007a783  mov     rcx, [rsp+260h+var_220]
0x14007a788  add     rcx, 28h ; '('; SpinLock
0x14007a78c  call    cs:__imp_KeInitializeSpinLock
0x14007a793  nop     dword ptr [rax+rax+00h]
0x14007a798  mov     rax, [rsp+260h+var_220]
0x14007a79d  add     rax, 30h ; '0'
0x14007a7a1  mov     [rax+8], rax
0x14007a7a5  mov     [rax], rax
0x14007a7a8  mov     rax, [rsp+260h+var_220]
0x14007a7ad  mov     [rax+40h], r12d
0x14007a7b1  mov     rax, [rsp+260h+var_220]
0x14007a7b6  mov     dword ptr [rax+318h], 5
0x14007a7c0  mov     rcx, [rsp+260h+var_220]
0x14007a7c5  call    Controller_AddControllerToGlobalControllerList
  ... truncated ...
```
