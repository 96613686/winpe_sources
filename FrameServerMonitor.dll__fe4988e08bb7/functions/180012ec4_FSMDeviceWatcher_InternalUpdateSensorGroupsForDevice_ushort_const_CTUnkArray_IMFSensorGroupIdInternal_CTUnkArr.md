# FSMDeviceWatcher::InternalUpdateSensorGroupsForDevice(ushort const *,CTUnkArray<IMFSensorGroupIdInternal> &,CTUnkArray<IMFSensorGroupId> &)

- ea: `0x180012ec4`
- end: `0x18001326d`
- name: `?InternalUpdateSensorGroupsForDevice@FSMDeviceWatcher@@IEAAJPEBGAEAV?$CTUnkArray@UIMFSensorGroupIdInternal@@@@AEAV?$CTUnkArray@UIMFSensorGroupId@@@@@Z`
- size: `937`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800124f4`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180005f98`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180007348`
- `0x18000cadc`
- `0x18000d62c`
- `0x180010d58`
- `0x180012ec4`
- `0x180016120`
- `0x180018224`
- `0x180040914`
- `0x180040a10`
- `0x1800426d8`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorGroupById` at `0x180012f9b`
- `MFSENSORGROUP!MFCreateSensorGroupById` at `0x180012f9b`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::InternalUpdateSensorGroupsForDevice(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int DeviceProcessedState; // ebx
  __int64 v9; // rdx
  unsigned __int8 Level; // al
  int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD **v15; // rbx
  _QWORD *v16; // rax
  __int64 (__fastcall *v17)(_QWORD **, GUID *, __int64 *); // r15
  int v18; // edx
  unsigned int *v20; // [rsp+28h] [rbp-D8h]
  bool v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD **v23; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v24[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct IMFSensorGroupId *v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[2]; // [rsp+70h] [rbp-90h] BYREF

  v25[0] = 0;
  v21 = 0;
  if ( !a2 )
  {
    DeviceProcessedState = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
LABEL_5:
      Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
      goto LABEL_41;
    }
    v9 = 232;
LABEL_4:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
      a1,
      DeviceProcessedState);
    goto LABEL_5;
  }
  DeviceProcessedState = FSMDeviceWatcher::GetDeviceProcessedState(
                           (FSMDeviceWatcher *)a1,
                           (const unsigned __int16 *)a2,
                           &v21,
                           v25);
  if ( DeviceProcessedState < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_5;
    v9 = 233;
    goto LABEL_4;
  }
  if ( v21 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        239,
        (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        (_DWORD)a1,
        a2);
    if ( !(unsigned int)CTUnkArray<IFSCameraControlState>::Add((__int64 *)a4, (__int64)v25[0]) )
    {
      DeviceProcessedState = -2147024882;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_5;
      v9 = 240;
      goto LABEL_4;
    }
  }
  else
  {
    v12 = a1[22];
    v22 = 0;
    v24[0] = 0;
    v23 = 0;
    DeviceProcessedState = MFCreateSensorGroupById(v25[0], v12, &v23);
    if ( DeviceProcessedState < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
LABEL_14:
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v22);
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v23);
        goto LABEL_5;
      }
      v13 = 234;
LABEL_13:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        a1,
        DeviceProcessedState);
      goto LABEL_14;
    }
    v14 = v22;
    v15 = v23;
    v16 = *v23;
    v22 = 0;
    v17 = (__int64 (__fastcall *)(_QWORD **, GUID *, __int64 *))*v16;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    DeviceProcessedState = v17(v15, &GUID_8e3196f0_ce22_4599_a16a_886bb13a7966, &v22);
    if ( DeviceProcessedState < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_14;
      v13 = 235;
      goto LABEL_13;
    }
    DeviceProcessedState = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _QWORD))(*(_QWORD *)v22 + 48LL))(
                             v22,
                             0,
                             0,
                             1,
                             0);
    if ( DeviceProcessedState < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_14;
      v13 = 236;
      goto LABEL_13;
    }
    if ( FSGetDeviceInterfaceProperty(
           (LPCWSTR)a2,
           (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_ConfigAppPfn,
           0,
           0,
           v24) < 0 )
    {
      memset_0(Data, 0, 0x82u);
      if ( (int)FSGetDeviceInterfaceRegistryEntry2((LPCWSTR)a2, L"SCSVCamPfn", Data, 0x80u, v24, v20) >= 0 )
      {
        *(_QWORD *)v24 = 0;
        DeviceProcessedState = StringCchLengthW((const unsigned __int16 *)Data, 0x41u, (unsigned __int64 *)v24);
        if ( DeviceProcessedState < 0 )
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_14;
          v13 = 237;
          goto LABEL_13;
        }
        DeviceProcessedState = FSSetDeviceInterfaceProperty(
                                 (const unsigned __int16 *)a2,
                                 &DEVPKEY_DeviceInterface_FSM_VirtualCamera_ConfigAppPfn,
                                 0x12u,
                                 Data,
                                 2 * (v24[0] + 1));
        if ( DeviceProcessedState < 0 )
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_14;
          v13 = 238;
          goto LABEL_13;
        }
      }
    }
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v22);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v23);
  }
  DeviceProcessedState = FSMDeviceWatcher::UpdateSGPairCollection(a1[11], a2, a3);
  if ( DeviceProcessedState < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v9 = 241;
    goto LABEL_4;
  }
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  if ( DeviceProcessedState < 0 )
  {
LABEL_41:
    if ( Level )
    {
      v18 = 242;
LABEL_45:
      WPP_SF_qDSDD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v18,
        v11,
        (_DWORD)a1,
        DeviceProcessedState,
        a2,
        *(_DWORD *)(a3 + 8),
        *(_DWORD *)(a4 + 8));
      goto LABEL_46;
    }
    goto LABEL_46;
  }
  if ( Level >= 8u )
  {
    v18 = 243;
    goto LABEL_45;
  }
LABEL_46:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)v25);
  return (unsigned int)DeviceProcessedState;
}

```

## disassembly

```asm
0x180012ec4  push    rbp
0x180012ec6  push    rbx
0x180012ec7  push    rsi
0x180012ec8  push    rdi
0x180012ec9  push    r12
0x180012ecb  push    r13
0x180012ecd  push    r14
0x180012ecf  push    r15
0x180012ed1  lea     rbp, [rsp-18h]
0x180012ed6  sub     rsp, 118h
0x180012edd  mov     rax, cs:__security_cookie
0x180012ee4  xor     rax, rsp
0x180012ee7  mov     [rbp+50h+var_50], rax
0x180012eeb  xor     r15d, r15d
0x180012eee  mov     r13, r9
0x180012ef1  mov     [rsp+150h+var_F0], r15
0x180012ef6  mov     r12, r8
0x180012ef9  mov     [rsp+150h+var_110], r15b
0x180012efe  mov     r14, rdx
0x180012f01  mov     rdi, rcx
0x180012f04  test    rdx, rdx
0x180012f07  jnz     short loc_180012F44
0x180012f09  mov     ebx, 80070057h
0x180012f0e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180012f13  cmp     al, 1
0x180012f15  jb      short loc_180012F3A
0x180012f17  mov     edx, 0E8h
0x180012f1c  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180012f23  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f2a  mov     r9, rdi
0x180012f2d  mov     [rsp+150h+var_130], ebx
0x180012f31  mov     rcx, [rcx+10h]
0x180012f35  call    WPP_SF_qD
0x180012f3a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180012f3f  jmp     loc_1800131FD
0x180012f44  lea     r9, [rsp+150h+var_F0]; struct IMFSensorGroupId **
0x180012f49  lea     r8, [rsp+150h+var_110]; bool *
0x180012f4e  call    ?GetDeviceProcessedState@FSMDeviceWatcher@@IEAAJPEBGPEA_NPEAPEAUIMFSensorGroupId@@@Z; FSMDeviceWatcher::GetDeviceProcessedState(ushort const *,bool *,IMFSensorGroupId * *)
0x180012f53  mov     ebx, eax
0x180012f55  test    eax, eax
0x180012f57  jns     short loc_180012F69
0x180012f59  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180012f5e  cmp     al, 1
0x180012f60  jb      short loc_180012F3A
0x180012f62  mov     edx, 0E9h
0x180012f67  jmp     short loc_180012F1C
0x180012f69  lea     rsi, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180012f70  cmp     [rsp+150h+var_110], r15b
0x180012f75  jnz     loc_180013198
0x180012f7b  mov     rdx, [rdi+0B0h]
0x180012f82  lea     r8, [rsp+150h+var_100]
0x180012f87  mov     rcx, [rsp+150h+var_F0]
0x180012f8c  mov     [rsp+150h+var_108], r15
0x180012f91  mov     [rsp+150h+var_F8], r15d
0x180012f96  mov     [rsp+150h+var_100], r15
0x180012f9b  call    cs:__imp_MFCreateSensorGroupById
0x180012fa1  mov     ebx, eax
0x180012fa3  test    eax, eax
0x180012fa5  jns     short loc_180012FE8
0x180012fa7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180012fac  cmp     al, 1
0x180012fae  jb      short loc_180012FCF
0x180012fb0  mov     edx, 0EAh
0x180012fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fbc  mov     r9, rdi
0x180012fbf  mov     r8, rsi
0x180012fc2  mov     [rsp+150h+var_130], ebx
0x180012fc6  mov     rcx, [rcx+10h]
0x180012fca  call    WPP_SF_qD
0x180012fcf  lea     rcx, [rsp+150h+var_108]
0x180012fd4  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180012fd9  lea     rcx, [rsp+150h+var_100]
0x180012fde  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180012fe3  jmp     loc_180012F3A
0x180012fe8  mov     rcx, [rsp+150h+var_108]
0x180012fed  mov     rbx, [rsp+150h+var_100]
0x180012ff2  mov     rax, [rbx]
0x180012ff5  mov     [rsp+150h+var_108], 0
0x180012ffe  mov     r15, [rax]
0x180013001  test    rcx, rcx
0x180013004  jz      short loc_180013012
0x180013006  mov     rdx, [rcx]
0x180013009  mov     rax, [rdx+10h]
0x18001300d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013012  lea     r8, [rsp+150h+var_108]
0x180013017  mov     rcx, rbx
0x18001301a  lea     rdx, _GUID_8e3196f0_ce22_4599_a16a_886bb13a7966
0x180013021  mov     rax, r15
0x180013024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013029  xor     r15d, r15d
0x18001302c  mov     ebx, eax
0x18001302e  test    eax, eax
0x180013030  jns     short loc_180013045
0x180013032  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013037  cmp     al, 1
0x180013039  jb      short loc_180012FCF
0x18001303b  mov     edx, 0EBh
0x180013040  jmp     loc_180012FB5
0x180013045  mov     rcx, [rsp+150h+var_108]
0x18001304a  mov     r9d, 1
0x180013050  xor     r8d, r8d
0x180013053  mov     qword ptr [rsp+150h+var_130], r15
0x180013058  xor     edx, edx
0x18001305a  mov     rax, [rcx]
0x18001305d  mov     rax, [rax+30h]
0x180013061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013066  mov     ebx, eax
0x180013068  test    eax, eax
0x18001306a  jns     short loc_180013083
0x18001306c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013071  cmp     al, 1
0x180013073  jb      loc_180012FCF
0x180013079  mov     edx, 0ECh
0x18001307e  jmp     loc_180012FB5
0x180013083  lea     rax, [rsp+150h+var_F8]
0x180013088  xor     r9d, r9d; unsigned int
0x18001308b  xor     r8d, r8d; PropertyBuffer
0x18001308e  mov     qword ptr [rsp+150h+var_130], rax; unsigned int *
0x180013093  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_ConfigAppPfn; PropertyKey
0x18001309a  mov     rcx, r14; pszDeviceInterface
0x18001309d  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x1800130a2  test    eax, eax
0x1800130a4  jns     loc_18001315F
0x1800130aa  xor     edx, edx; Val
0x1800130ac  lea     rcx, [rsp+150h+Data]; void *
0x1800130b1  mov     r8d, 82h; Size
0x1800130b7  call    memset_0
0x1800130bc  lea     rax, [rsp+150h+var_F8]
0x1800130c1  mov     r9d, 80h; unsigned int
0x1800130c7  lea     r8, [rsp+150h+Data]; lpData
0x1800130cc  mov     qword ptr [rsp+150h+var_130], rax; unsigned int *
0x1800130d1  lea     rdx, aScsvcampfn; "SCSVCamPfn"
0x1800130d8  mov     rcx, r14; pszDeviceInterface
0x1800130db  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x1800130e0  test    eax, eax
0x1800130e2  js      short loc_18001315F
0x1800130e4  lea     r8, [rsp+150h+var_F8]; unsigned __int64 *
0x1800130e9  mov     qword ptr [rsp+150h+var_F8], r15
0x1800130ee  mov     edx, 41h ; 'A'; unsigned __int64
0x1800130f3  lea     rcx, [rsp+150h+Data]; unsigned __int16 *
0x1800130f8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800130fd  mov     ebx, eax
0x1800130ff  test    eax, eax
0x180013101  jns     short loc_18001311A
0x180013103  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013108  cmp     al, 1
0x18001310a  jb      loc_180012FCF
0x180013110  mov     edx, 0EDh
0x180013115  jmp     loc_180012FB5
0x18001311a  mov     rax, qword ptr [rsp+150h+var_F8]
0x18001311f  lea     r9, [rsp+150h+Data]; unsigned __int8 *
0x180013124  inc     rax
0x180013127  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_ConfigAppPfn; struct _DEVPROPKEY *
0x18001312e  add     eax, eax
0x180013130  mov     r8d, 12h; unsigned int
0x180013136  mov     rcx, r14; unsigned __int16 *
0x180013139  mov     [rsp+150h+var_130], eax; ULONG
0x18001313d  call    ?FSSetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@KQEAEK@Z; FSSetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,ulong,uchar * const,ulong)
0x180013142  mov     ebx, eax
0x180013144  test    eax, eax
0x180013146  jns     short loc_18001315F
0x180013148  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001314d  cmp     al, 1
0x18001314f  jb      loc_180012FCF
0x180013155  mov     edx, 0EEh
0x18001315a  jmp     loc_180012FB5
0x18001315f  lea     rcx, [rsp+150h+var_108]
0x180013164  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180013169  lea     rcx, [rsp+150h+var_100]
0x18001316e  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180013173  mov     rcx, [rdi+58h]
0x180013177  mov     r8, r12
0x18001317a  mov     rdx, r14
0x18001317d  call    ?UpdateSGPairCollection@FSMDeviceWatcher@@SAJPEAUIMFSensorGroupIdManager@@PEBGAEAV?$CTUnkArray@UIMFSensorGroupIdInternal@@@@@Z; FSMDeviceWatcher::UpdateSGPairCollection(IMFSensorGroupIdManager *,ushort const *,CTUnkArray<IMFSensorGroupIdInternal> &)
0x180013182  mov     ebx, eax
0x180013184  test    eax, eax
0x180013186  jns     short loc_1800131F4
0x180013188  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001318d  cmp     al, 1
0x18001318f  jb      short loc_1800131F4
0x180013191  mov     edx, 0F1h
0x180013196  jmp     short loc_1800131EC
0x180013198  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001319d  cmp     al, 8
0x18001319f  jb      short loc_1800131C4
0x1800131a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131a8  mov     edx, 0EFh
0x1800131ad  mov     r9, rdi
0x1800131b0  mov     qword ptr [rsp+150h+var_130], r14
0x1800131b5  mov     r8, rsi
0x1800131b8  mov     rcx, [rcx+0D8h]
0x1800131bf  call    WPP_SF_qS
0x1800131c4  mov     rdx, [rsp+150h+var_F0]
0x1800131c9  mov     rcx, r13
0x1800131cc  call    ?Add@?$CTUnkArray@UIFSCameraControlState@@@@QEAAHPEAUIFSCameraControlState@@@Z; CTUnkArray<IFSCameraControlState>::Add(IFSCameraControlState *)
0x1800131d1  test    eax, eax
0x1800131d3  jnz     short loc_180013173
0x1800131d5  mov     ebx, 8007000Eh
0x1800131da  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800131df  cmp     al, 1
0x1800131e1  jb      loc_180012F3A
0x1800131e7  mov     edx, 0F0h
0x1800131ec  mov     r8, rsi
0x1800131ef  jmp     loc_180012F23
0x1800131f4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800131f9  test    ebx, ebx
0x1800131fb  jns     short loc_180013208
0x1800131fd  cmp     al, 1
0x1800131ff  jb      short loc_180013241
0x180013201  mov     edx, 0F2h
0x180013206  jmp     short loc_180013211
0x180013208  cmp     al, 8
0x18001320a  jb      short loc_180013241
0x18001320c  mov     edx, 0F3h
0x180013211  mov     eax, [r13+8]
0x180013215  mov     r9, rdi
0x180013218  mov     rcx, cs:WPP_GLOBAL_Control
0x18001321f  mov     [rsp+150h+var_118], eax
0x180013223  mov     eax, [r12+8]
0x180013228  mov     [rsp+150h+var_120], eax
0x18001322c  mov     rcx, [rcx+0D8h]
0x180013233  mov     [rsp+150h+var_128], r14
0x180013238  mov     [rsp+150h+var_130], ebx
0x18001323c  call    WPP_SF_qDSDD
0x180013241  lea     rcx, [rsp+150h+var_F0]
0x180013246  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18001324b  mov     eax, ebx
0x18001324d  mov     rcx, [rbp+50h+var_50]
0x180013251  xor     rcx, rsp; StackCookie
0x180013254  call    __security_check_cookie
0x180013259  add     rsp, 118h
0x180013260  pop     r15
0x180013262  pop     r14
0x180013264  pop     r13
0x180013266  pop     r12
0x180013268  pop     rdi
0x180013269  pop     rsi
0x18001326a  pop     rbx
0x18001326b  pop     rbp
0x18001326c  retn
```
