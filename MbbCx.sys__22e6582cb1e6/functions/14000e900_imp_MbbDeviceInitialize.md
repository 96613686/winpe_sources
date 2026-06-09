# imp_MbbDeviceInitialize

- ea: `0x14000e900`
- end: `0x14000eab6`
- name: `imp_MbbDeviceInitialize`
- size: `438`
- prototype: `NTSTATUS __stdcall(WDFDEVICE Device, PMBB_DEVICE_CONFIG Config)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x140001db8`
- `0x140009104`
- `0x140009568`
- `0x14000b3fc`
- `0x14000e900`
- `0x140047e90`

## pseudocode

```c
NTSTATUS __stdcall imp_MbbDeviceInitialize(WDFDEVICE Device, PMBB_DEVICE_CONFIG Config)
{
  const struct _MBB_DEVICE_CONFIG *v2; // r8
  const struct _MBB_DEVICE_CONFIG *v3; // rbx
  int v6; // eax
  int v7; // edx
  NTSTATUS v8; // edi
  int v9; // edx
  int v10; // r9d
  MbxDevice *v12; // rax
  __int64 v13; // [rsp+28h] [rbp-58h]
  __int128 v14; // [rsp+40h] [rbp-40h] BYREF
  __int128 v15; // [rsp+50h] [rbp-30h]
  __int128 v16; // [rsp+60h] [rbp-20h]
  __int64 *v17; // [rsp+70h] [rbp-10h]
  MbxDevice *v18; // [rsp+A0h] [rbp+20h] BYREF

  v3 = v2;
  v17 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v14) = -1;
    else
      LODWORD(v14) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v14) = 56;
  }
  v18 = 0;
  *((_QWORD *)&v15 + 1) = 0x100000001LL;
  v17 = off_14005DF70;
  *(_QWORD *)&v15 = CFxObject<WDFDEVICE__ *,MbxDevice,&MbxDevice * GetMbxDeviceFromHandle(WDFDEVICE__ *),0>::_OnDestroy;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, PMBB_DEVICE_CONFIG, __int128 *, MbxDevice **))(WdfFunctions_01031 + 1624))(
         WdfDriverGlobals,
         Config,
         &v14,
         &v18);
  v8 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      11,
      51,
      (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids,
      (char)Config,
      v6);
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v10 = 12;
    goto LABEL_10;
  }
  if ( v18 )
    MbxDevice::MbxDevice(v18, (struct WDFDEVICE__ *)Config, v3, (struct _MBX_PRIVATE_GLOBALS *)(Device - 1));
  v12 = (MbxDevice *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, PMBB_DEVICE_CONFIG, __int64 *))(WdfFunctions_01031 + 1616))(
                       WdfDriverGlobals,
                       Config,
                       off_14005DF70);
  v8 = MbxDevice::Initialize(v12);
  if ( v8 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v10 = 13;
LABEL_10:
    LODWORD(v13) = v8;
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      11,
      v10,
      (__int64)WPP_c2cb746ee0e53b6729cbe0619734295d_Traceguids,
      v13);
    return v8;
  }
  return 0;
}

```

## disassembly

```asm
0x14000e900  mov     [rsp-18h+arg_8], rbx
0x14000e905  mov     [rsp-18h+arg_10], rsi
0x14000e90a  push    rbp
0x14000e90b  push    rdi
0x14000e90c  push    r14
0x14000e90e  mov     rbp, rsp
0x14000e911  sub     rsp, 80h
0x14000e918  xorps   xmm0, xmm0
0x14000e91b  xor     eax, eax
0x14000e91d  cmp     cs:WdfClientVersionHigherThanFramework, al
0x14000e923  mov     rbx, r8
0x14000e926  mov     rsi, rdx
0x14000e929  mov     [rbp+var_10], rax
0x14000e92d  mov     r14, rcx
0x14000e930  movups  [rbp+var_40], xmm0
0x14000e934  movups  [rbp+var_30], xmm0
0x14000e938  movups  [rbp+var_20], xmm0
0x14000e93c  jz      short loc_14000E962
0x14000e93e  cmp     cs:WdfStructureCount, 26h ; '&'
0x14000e945  jbe     short loc_14000E959
0x14000e947  mov     rax, cs:WdfStructures
0x14000e94e  mov     ecx, [rax+130h]
0x14000e954  mov     dword ptr [rbp+var_40], ecx
0x14000e957  jmp     short loc_14000E969
0x14000e959  mov     dword ptr [rbp+var_40], 0FFFFFFFFh
0x14000e960  jmp     short loc_14000E969
0x14000e962  mov     dword ptr [rbp+var_40], 38h ; '8'
0x14000e969  mov     rcx, cs:WdfDriverGlobals
0x14000e970  lea     r9, [rbp+arg_0]
0x14000e974  mov     eax, 1
0x14000e979  mov     [rbp+arg_0], 0
0x14000e981  mov     dword ptr [rbp+var_30+8], eax
0x14000e984  lea     r8, [rbp+var_40]
0x14000e988  mov     dword ptr [rbp+var_30+0Ch], eax
0x14000e98b  mov     rax, cs:off_14005DF70
0x14000e992  mov     [rbp+var_10], rax
0x14000e996  lea     rax, ?_OnDestroy@?$CFxObject@PEAUWDFDEVICE__@@VMbxDevice@@$1?GetMbxDeviceFromHandle@@YAPEAV2@PEAU1@@Z$0A@@@KAXPEAX@Z; CFxObject<WDFDEVICE__ *,MbxDevice,&GetMbxDeviceFromHandle(WDFDEVICE__ *),0>::_OnDestroy(void *)
0x14000e99d  mov     qword ptr [rbp+var_30], rax
0x14000e9a1  mov     rax, cs:WdfFunctions_01031
0x14000e9a8  mov     rax, [rax+658h]
0x14000e9af  call    _guard_dispatch_icall
0x14000e9b4  mov     edi, eax
0x14000e9b6  test    eax, eax
0x14000e9b8  jns     short loc_14000EA36
0x14000e9ba  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000e9c1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000e9c8  jz      short loc_14000EA32
0x14000e9ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9d1  mov     r9d, 33h ; '3'
0x14000e9d7  mov     [rsp+80h+var_50], eax
0x14000e9db  mov     dl, 2
0x14000e9dd  lea     rax, WPP_87eee639879b3392f87380bbab0baecf_Traceguids
0x14000e9e4  mov     [rsp+80h+var_58], rsi
0x14000e9e9  mov     [rsp+80h+var_60], rax
0x14000e9ee  mov     rcx, [rcx+40h]
0x14000e9f2  lea     r8d, [r9-28h]
0x14000e9f6  call    WPP_RECORDER_SF_qd
0x14000e9fb  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000ea02  jz      short loc_14000EA32
0x14000ea04  mov     r9d, 0Ch
0x14000ea0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea11  lea     rax, WPP_c2cb746ee0e53b6729cbe0619734295d_Traceguids
0x14000ea18  mov     dword ptr [rsp+80h+var_58], edi
0x14000ea1c  mov     r8d, 0Bh
0x14000ea22  mov     dl, 2
0x14000ea24  mov     [rsp+80h+var_60], rax
0x14000ea29  mov     rcx, [rcx+40h]
0x14000ea2d  call    WPP_RECORDER_SF_d
0x14000ea32  mov     eax, edi
0x14000ea34  jmp     short loc_14000EA9D
0x14000ea36  mov     rcx, [rbp+arg_0]; this
0x14000ea3a  test    rcx, rcx
0x14000ea3d  jz      short loc_14000EA4E
0x14000ea3f  lea     r9, [r14-4]; struct _MBX_PRIVATE_GLOBALS *
0x14000ea43  mov     r8, rbx; struct _MBB_DEVICE_CONFIG *
0x14000ea46  mov     rdx, rsi; struct WDFDEVICE__ *
0x14000ea49  call    ??0MbxDevice@@AEAA@PEAUWDFDEVICE__@@AEBU_MBB_DEVICE_CONFIG@@PEAU_MBX_PRIVATE_GLOBALS@@@Z; MbxDevice::MbxDevice(WDFDEVICE__ *,_MBB_DEVICE_CONFIG const &,_MBX_PRIVATE_GLOBALS *)
0x14000ea4e  mov     rax, cs:WdfFunctions_01031
0x14000ea55  mov     rdx, rsi
0x14000ea58  mov     r8, cs:off_14005DF70
0x14000ea5f  mov     rcx, cs:WdfDriverGlobals
0x14000ea66  mov     rax, [rax+650h]
0x14000ea6d  call    _guard_dispatch_icall
0x14000ea72  mov     rcx, rax; this
0x14000ea75  call    ?Initialize@MbxDevice@@QEAAJXZ; MbxDevice::Initialize(void)
0x14000ea7a  mov     edi, eax
0x14000ea7c  test    eax, eax
0x14000ea7e  jns     short loc_14000EA9B
0x14000ea80  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000ea87  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000ea8e  jz      short loc_14000EA32
0x14000ea90  mov     r9d, 0Dh
0x14000ea96  jmp     loc_14000EA0A
0x14000ea9b  xor     eax, eax
0x14000ea9d  lea     r11, [rsp+80h+var_s0]
0x14000eaa5  mov     rbx, [r11+28h]
0x14000eaa9  mov     rsi, [r11+30h]
0x14000eaad  mov     rsp, r11
0x14000eab0  pop     r14
0x14000eab2  pop     rdi
0x14000eab3  pop     rbp
0x14000eab4  retn
```
