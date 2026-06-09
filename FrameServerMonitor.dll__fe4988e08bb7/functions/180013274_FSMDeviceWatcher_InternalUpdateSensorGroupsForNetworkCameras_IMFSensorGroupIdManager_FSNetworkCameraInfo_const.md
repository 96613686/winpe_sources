# FSMDeviceWatcher::InternalUpdateSensorGroupsForNetworkCameras(IMFSensorGroupIdManager *,FSNetworkCameraInfo const &)

- ea: `0x180013274`
- end: `0x180013764`
- name: `?InternalUpdateSensorGroupsForNetworkCameras@FSMDeviceWatcher@@IEAAJPEAUIMFSensorGroupIdManager@@AEBUFSNetworkCameraInfo@@@Z`
- size: `1264`
- prototype: `__int64 __fastcall(FSMDeviceWatcher *__hidden this, struct IMFSensorGroupIdManager *, const struct FSNetworkCameraInfo *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001376c`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180005f98`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000d62c`
- `0x18000e66c`
- `0x180013274`
- `0x180026b78`
- `0x180041b60`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorDeviceBlobByObject` at `0x180013559`
- `MFSENSORGROUP!MFCreateSensorDeviceBlobByObject` at `0x180013559`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001370b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001371e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001370b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001371e`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18001334e`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18001334e`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x180013602`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x180013602`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::InternalUpdateSensorGroupsForNetworkCameras(
        FSMDeviceWatcher *this,
        struct IMFSensorGroupIdManager *a2,
        const struct FSNetworkCameraInfo *a3)
{
  int v6; // ecx
  __int64 *v7; // r8
  int v8; // ebx
  __int64 v9; // rdx
  unsigned __int8 Level; // al
  __int64 v11; // rax
  __int64 (__fastcall **v12)(__int64, GUID *, __int64 *); // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  int i; // esi
  const WCHAR *v18; // rcx
  void *v19; // rcx
  unsigned __int8 *v20; // rcx
  __int64 v22; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v23)(__int64, GUID *, __int64 *); // [rsp+78h] [rbp-88h] BYREF
  unsigned int v24; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v25; // [rsp+84h] [rbp-7Ch] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v27; // [rsp+90h] [rbp-70h] BYREF
  ULONG pulLength; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME v29; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 **v30; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-50h] BYREF
  char v32; // [rsp+B8h] [rbp-48h]
  LPVOID *p_pv; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v34; // [rsp+C8h] [rbp-38h] BYREF
  char v35; // [rsp+D0h] [rbp-30h]
  _OWORD v36[4]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int8 v37[16]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v38; // [rsp+130h] [rbp+30h]
  unsigned __int8 v39[16]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v40; // [rsp+150h] [rbp+50h]
  WCHAR pszAliasDeviceInterface[264]; // [rsp+160h] [rbp+60h] BYREF

  v29 = 0;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v23 = 0;
  v22 = 0;
  *(_OWORD *)v37 = 0;
  v27 = 0;
  v38 = 0;
  v25 = 0;
  pv = 0;
  v36[0] = GUID_b8238652_b500_41eb_b4f3_4234f7f5ae99;
  v24 = 0;
  v36[1] = GUID_e5323777_f976_4f5b_9b55_b94699c46e44;
  v36[2] = GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196;
  v36[3] = GUID_6994ad05_93ef_11d0_a3cc_00a0c9223196;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      211,
      (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
      v6,
      *v7);
  GetSystemTimePreciseAsFileTime(&v29);
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
LABEL_7:
      Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
LABEL_30:
      if ( !Level )
        goto LABEL_45;
      v16 = 222;
      goto LABEL_44;
    }
    v9 = 212;
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v8);
    goto LABEL_7;
  }
  v11 = *(_QWORD *)a2;
  v23 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdManager *, _QWORD, _QWORD, __int64 (__fastcall ****)(__int64, GUID *, __int64 *)))(v11 + 32))(
         a2,
         0,
         0,
         &v23);
  if ( v8 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v9 = 213;
    goto LABEL_6;
  }
  v12 = *v23;
  v22 = 0;
  v8 = (*v12)((__int64)v23, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v22);
  if ( v8 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v9 = 214;
    goto LABEL_6;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 64LL))(v22, *(_QWORD *)a3);
  if ( v8 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v9 = 215;
    goto LABEL_6;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 72LL))(v22, 0);
  if ( v8 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v9 = 216;
    goto LABEL_6;
  }
  v8 = (*v23)[4]((__int64)v23, (GUID *)v39, (__int64 *)32);
  if ( v8 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v9 = 217;
    goto LABEL_6;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, __int64, _QWORD))(*(_QWORD *)v22 + 136LL))(
         v22,
         v37,
         32,
         0);
  if ( v8 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v9 = 218;
    goto LABEL_6;
  }
  v13 = *((_QWORD *)a3 + 5);
  v14 = *(_QWORD *)a3;
  v15 = *((_QWORD *)a3 + 4);
  p_pv = &pv;
  v30 = &v27;
  v34 = 0;
  v35 = 1;
  v31 = 0;
  v32 = 1;
  v8 = MFCreateSensorDeviceBlobByObject(v15, v14, v13, &v31, &v25, &v34, &v24);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&v30);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
  if ( v8 >= 0 )
  {
    for ( i = 0; (unsigned __int64)i < 4; ++i )
    {
      memset_0(pszAliasDeviceInterface, 0, 0x208u);
      v18 = *(const WCHAR **)a3;
      pulLength = 260;
      if ( !CM_Get_Device_Interface_AliasW(v18, (LPGUID)&v36[i], pszAliasDeviceInterface, &pulLength, 0)
        && FSIsDeviceInterfaceEnabled(pszAliasDeviceInterface) )
      {
        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            220,
            (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
            (_DWORD)this,
            (__int64)pszAliasDeviceInterface);
        v8 = FSUpdateSensorGroupDataToDevice(
               1,
               pszAliasDeviceInterface,
               *((struct IMFAttributes **)a3 + 5),
               v39,
               0x20u,
               v37,
               0x20u,
               v27,
               v25,
               (unsigned __int8 *)pv,
               v24,
               1u,
               (const struct FSMFileTime *)&v29,
               &v29);
        if ( v8 < 0 )
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            break;
          v9 = 221;
          goto LABEL_6;
        }
      }
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v8);
  }
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  if ( v8 < 0 )
    goto LABEL_30;
  if ( Level < 8u )
    goto LABEL_45;
  v16 = 223;
LABEL_44:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v16, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v8);
LABEL_45:
  v19 = pv;
  pv = 0;
  if ( v19 )
    CoTaskMemFree(v19);
  v20 = v27;
  v27 = 0;
  if ( v20 )
    CoTaskMemFree(v20);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v22);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v23);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180013274  mov     [rsp-8+arg_18], rbx
0x180013279  push    rbp
0x18001327a  push    rsi
0x18001327b  push    rdi
0x18001327c  push    r12
0x18001327e  push    r13
0x180013280  push    r14
0x180013282  push    r15
0x180013284  lea     rbp, [rsp-280h]
0x18001328c  sub     rsp, 380h
0x180013293  mov     rax, cs:__security_cookie
0x18001329a  xor     rax, rsp
0x18001329d  mov     [rbp+2B0h+var_40], rax
0x1800132a4  xor     r12d, r12d
0x1800132a7  xorps   xmm0, xmm0
0x1800132aa  xorps   xmm1, xmm1
0x1800132ad  mov     [rbp+2B0h+var_310], r12
0x1800132b1  movups  xmmword ptr [rbp+2B0h+var_270], xmm0
0x1800132b5  mov     r15, r8
0x1800132b8  mov     rbx, rdx
0x1800132bb  movups  [rbp+2B0h+var_260], xmm0
0x1800132bf  mov     rdi, rcx
0x1800132c2  mov     [rsp+3B0h+var_338], r12
0x1800132c7  movups  xmm0, xmmword ptr cs:_GUID_b8238652_b500_41eb_b4f3_4234f7f5ae99.Data1
0x1800132ce  mov     [rsp+3B0h+var_340], r12
0x1800132d3  movups  xmmword ptr [rbp+2B0h+var_290], xmm1
0x1800132d7  mov     [rbp+2B0h+var_320], r12
0x1800132db  movups  [rbp+2B0h+var_280], xmm1
0x1800132df  mov     [rbp+2B0h+var_32C], r12d
0x1800132e3  movups  xmm1, xmmword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data1
0x1800132ea  mov     [rbp+2B0h+pv], r12
0x1800132ee  movdqu  [rbp+2B0h+var_2D0], xmm0
0x1800132f3  mov     [rbp+2B0h+var_330], r12d
0x1800132f7  movups  xmm0, xmmword ptr cs:_GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196.Data1
0x1800132fe  movdqu  [rbp+2B0h+var_2C0], xmm1
0x180013303  movups  xmm1, xmmword ptr cs:_GUID_6994ad05_93ef_11d0_a3cc_00a0c9223196.Data1
0x18001330a  movdqu  [rbp+2B0h+var_2B0], xmm0
0x18001330f  movdqu  [rbp+2B0h+var_2A0], xmm1
0x180013314  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180013319  lea     r13, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180013320  cmp     al, 8
0x180013322  jb      short loc_18001334A
0x180013324  mov     rax, [r8]
0x180013327  mov     r9, rcx
0x18001332a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013331  mov     edx, 0D3h
0x180013336  mov     r8, r13
0x180013339  mov     qword ptr [rsp+3B0h+ulFlags], rax
0x18001333e  mov     rcx, [rcx+0D8h]
0x180013345  call    WPP_SF_qS
0x18001334a  lea     rcx, [rbp+2B0h+var_310]
0x18001334e  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180013354  test    rbx, rbx
0x180013357  jnz     short loc_180013390
0x180013359  mov     ebx, 80070057h
0x18001335e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013363  cmp     al, 1
0x180013365  jb      short loc_180013386
0x180013367  mov     edx, 0D4h
0x18001336c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013373  mov     r9, rdi
0x180013376  mov     r8, r13
0x180013379  mov     [rsp+3B0h+ulFlags], ebx
0x18001337d  mov     rcx, [rcx+10h]
0x180013381  call    WPP_SF_qD
0x180013386  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001338b  jmp     loc_1800135B1
0x180013390  mov     rcx, [rsp+3B0h+var_338]
0x180013395  mov     rax, [rbx]
0x180013398  mov     [rsp+3B0h+var_338], r12
0x18001339d  mov     rsi, [rax+20h]
0x1800133a1  test    rcx, rcx
0x1800133a4  jz      short loc_1800133B2
0x1800133a6  mov     rdx, [rcx]
0x1800133a9  mov     rax, [rdx+10h]
0x1800133ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133b2  lea     r9, [rsp+3B0h+var_338]
0x1800133b7  xor     r8d, r8d
0x1800133ba  xor     edx, edx
0x1800133bc  mov     rcx, rbx
0x1800133bf  mov     rax, rsi
0x1800133c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c7  mov     ebx, eax
0x1800133c9  test    eax, eax
0x1800133cb  jns     short loc_1800133DD
0x1800133cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800133d2  cmp     al, 1
0x1800133d4  jb      short loc_180013386
0x1800133d6  mov     edx, 0D5h
0x1800133db  jmp     short loc_18001336C
0x1800133dd  mov     rcx, [rsp+3B0h+var_340]
0x1800133e2  mov     rbx, [rsp+3B0h+var_338]
0x1800133e7  mov     rax, [rbx]
0x1800133ea  mov     [rsp+3B0h+var_340], r12
0x1800133ef  mov     rsi, [rax]
0x1800133f2  test    rcx, rcx
0x1800133f5  jz      short loc_180013403
0x1800133f7  mov     rdx, [rcx]
0x1800133fa  mov     rax, [rdx+10h]
0x1800133fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013403  lea     r8, [rsp+3B0h+var_340]
0x180013408  mov     rcx, rbx
0x18001340b  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x180013412  mov     rax, rsi
0x180013415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001341a  mov     ebx, eax
0x18001341c  test    eax, eax
0x18001341e  jns     short loc_180013437
0x180013420  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013425  cmp     al, 1
0x180013427  jb      loc_180013386
0x18001342d  mov     edx, 0D6h
0x180013432  jmp     loc_18001336C
0x180013437  mov     rcx, [rsp+3B0h+var_340]
0x18001343c  mov     rdx, [r15]
0x18001343f  mov     rax, [rcx]
0x180013442  mov     rax, [rax+40h]
0x180013446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001344b  mov     ebx, eax
0x18001344d  test    eax, eax
0x18001344f  jns     short loc_180013468
0x180013451  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013456  cmp     al, 1
0x180013458  jb      loc_180013386
0x18001345e  mov     edx, 0D7h
0x180013463  jmp     loc_18001336C
0x180013468  mov     rcx, [rsp+3B0h+var_340]
0x18001346d  xor     edx, edx
0x18001346f  mov     rax, [rcx]
0x180013472  mov     rax, [rax+48h]
0x180013476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001347b  mov     ebx, eax
0x18001347d  test    eax, eax
0x18001347f  jns     short loc_180013498
0x180013481  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013486  cmp     al, 1
0x180013488  jb      loc_180013386
0x18001348e  mov     edx, 0D8h
0x180013493  jmp     loc_18001336C
0x180013498  mov     rcx, [rsp+3B0h+var_338]
0x18001349d  lea     rdx, [rbp+2B0h+var_270]
0x1800134a1  xor     r9d, r9d
0x1800134a4  mov     rax, [rcx]
0x1800134a7  lea     esi, [r9+20h]
0x1800134ab  mov     r8d, esi
0x1800134ae  mov     rax, [rax+20h]
0x1800134b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134b7  mov     ebx, eax
0x1800134b9  test    eax, eax
0x1800134bb  jns     short loc_1800134D4
0x1800134bd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800134c2  cmp     al, 1
0x1800134c4  jb      loc_180013386
0x1800134ca  mov     edx, 0D9h
0x1800134cf  jmp     loc_18001336C
0x1800134d4  mov     rcx, [rsp+3B0h+var_340]
0x1800134d9  lea     rdx, [rbp+2B0h+var_290]
0x1800134dd  xor     r9d, r9d
0x1800134e0  mov     r8d, esi
0x1800134e3  mov     rax, [rcx]
0x1800134e6  mov     rax, [rax+88h]
0x1800134ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134f2  mov     ebx, eax
0x1800134f4  test    eax, eax
0x1800134f6  jns     short loc_18001350F
0x1800134f8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800134fd  cmp     al, 1
0x1800134ff  jb      loc_180013386
0x180013505  mov     edx, 0DAh
0x18001350a  jmp     loc_18001336C
0x18001350f  mov     r8, [r15+28h]
0x180013513  lea     rax, [rbp+2B0h+pv]
0x180013517  mov     rdx, [r15]
0x18001351a  lea     r9, [rbp+2B0h+var_300]
0x18001351e  mov     rcx, [r15+20h]
0x180013522  mov     [rbp+2B0h+var_2F0], rax
0x180013526  lea     rax, [rbp+2B0h+var_320]
0x18001352a  mov     [rbp+2B0h+var_308], rax
0x18001352e  lea     rax, [rbp+2B0h+var_330]
0x180013532  mov     qword ptr [rsp+3B0h+var_380], rax
0x180013537  lea     rax, [rbp+2B0h+var_2E8]
0x18001353b  mov     [rsp+3B0h+var_388], rax
0x180013540  lea     rax, [rbp+2B0h+var_32C]
0x180013544  mov     qword ptr [rsp+3B0h+ulFlags], rax
0x180013549  mov     [rbp+2B0h+var_2E8], r12
0x18001354d  mov     [rbp+2B0h+var_2E0], 1
0x180013551  mov     [rbp+2B0h+var_300], r12
0x180013555  mov     [rbp+2B0h+var_2F8], 1
0x180013559  call    cs:__imp_MFCreateSensorDeviceBlobByObject
0x18001355f  lea     rcx, [rbp+2B0h+var_308]
0x180013563  mov     ebx, eax
0x180013565  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001356a  lea     rcx, [rbp+2B0h+var_2F0]
0x18001356e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180013573  mov     eax, ebx
0x180013575  shr     eax, 1Fh
0x180013578  test    al, al
0x18001357a  jz      short loc_1800135C3
0x18001357c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013581  cmp     al, 1
0x180013583  jb      short loc_1800135A4
0x180013585  mov     rcx, cs:WPP_GLOBAL_Control
0x18001358c  mov     edx, 0DBh
0x180013591  mov     r9, rdi
0x180013594  mov     [rsp+3B0h+ulFlags], ebx
0x180013598  mov     r8, r13
0x18001359b  mov     rcx, [rcx+10h]
0x18001359f  call    WPP_SF_qD
0x1800135a4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800135a9  test    ebx, ebx
0x1800135ab  jns     loc_1800136D8
0x1800135b1  cmp     al, 1
0x1800135b3  jb      loc_1800136FE
0x1800135b9  mov     edx, 0DEh
0x1800135be  jmp     loc_1800136E1
0x1800135c3  mov     esi, r12d
0x1800135c6  movsxd  r14, esi
0x1800135c9  cmp     r14, 4
0x1800135cd  jnb     short loc_1800135A4
0x1800135cf  xor     edx, edx; Val
0x1800135d1  lea     rcx, [rbp+2B0h+pszAliasDeviceInterface]; void *
0x1800135d5  mov     r8d, 208h; Size
0x1800135db  call    memset_0
0x1800135e0  mov     rcx, [r15]; pszDeviceInterface
0x1800135e3  lea     rdx, [rbp+2B0h+var_2D0]
0x1800135e7  shl     r14, 4
0x1800135eb  lea     r9, [rbp+2B0h+pulLength]; pulLength
0x1800135ef  add     rdx, r14; AliasInterfaceGuid
0x1800135f2  mov     [rbp+2B0h+pulLength], 104h
0x1800135f9  lea     r8, [rbp+2B0h+pszAliasDeviceInterface]; pszAliasDeviceInterface
0x1800135fd  mov     [rsp+3B0h+ulFlags], r12d; ulFlags
0x180013602  call    cs:__imp_CM_Get_Device_Interface_AliasW
0x180013608  test    eax, eax
0x18001360a  jnz     loc_1800136BA
0x180013610  lea     rcx, [rbp+2B0h+pszAliasDeviceInterface]; unsigned __int16 *
0x180013614  call    ?FSIsDeviceInterfaceEnabled@@YA_NPEBG@Z; FSIsDeviceInterfaceEnabled(ushort const *)
0x180013619  test    al, al
0x18001361b  jz      loc_1800136BA
0x180013621  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180013626  cmp     al, 8
0x180013628  jb      short loc_180013651
0x18001362a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013631  lea     rax, [rbp+2B0h+pszAliasDeviceInterface]
0x180013635  mov     edx, 0DCh
0x18001363a  mov     qword ptr [rsp+3B0h+ulFlags], rax
0x18001363f  mov     r9, rdi
0x180013642  mov     r8, r13
0x180013645  mov     rcx, [rcx+0D8h]
0x18001364c  call    WPP_SF_qS
0x180013651  mov     eax, [rbp+2B0h+var_330]
0x180013654  lea     r9, [rbp+2B0h+var_310]
0x180013658  mov     rcx, [rbp+2B0h+pv]
0x18001365c  mov     edx, [rbp+2B0h+var_32C]
0x18001365f  mov     r8, [rbp+2B0h+var_320]
0x180013663  mov     [rsp+3B0h+var_348], r9; struct FSMFileTime *
0x180013668  lea     r9, [rbp+2B0h+var_310]
0x18001366c  mov     [rsp+3B0h+var_350], r9; struct FSMFileTime *
0x180013671  lea     r9, [rbp+2B0h+var_270]; unsigned __int8 *
0x180013675  mov     [rsp+3B0h+var_358], 1; unsigned int
0x18001367d  mov     [rsp+3B0h+var_360], eax; unsigned int
0x180013681  lea     rax, [rbp+2B0h+var_290]
0x180013685  mov     [rsp+3B0h+var_368], rcx; unsigned __int8 *
0x18001368a  mov     ecx, 20h ; ' '
0x18001368f  mov     [rsp+3B0h+var_370], edx; unsigned int
0x180013693  lea     rdx, [rbp+2B0h+pszAliasDeviceInterface]; unsigned __int16 *
0x180013697  mov     [rsp+3B0h+var_378], r8; unsigned __int8 *
0x18001369c  mov     r8, [r15+28h]; struct IMFAttributes *
0x1800136a0  mov     [rsp+3B0h+var_380], ecx; unsigned int
0x1800136a4  mov     [rsp+3B0h+var_388], rax; unsigned __int8 *
0x1800136a9  mov     [rsp+3B0h+ulFlags], ecx; unsigned int
0x1800136ad  mov     cl, 1; bool
0x1800136af  call    ?FSUpdateSensorGroupDataToDevice@@YAJ_NPEBGPEAUIMFAttributes@@PEAEK3K3K3KKAEBUFSMFileTime@@4@Z; FSUpdateSensorGroupDataToDevice(bool,ushort const *,IMFAttributes *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong,FSMFileTime const &,FSMFileTime const &)
0x1800136b4  mov     ebx, eax
0x1800136b6  test    eax, eax
0x1800136b8  js      short loc_1800136C1
0x1800136ba  inc     esi
0x1800136bc  jmp     loc_1800135C6
0x1800136c1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800136c6  cmp     al, 1
0x1800136c8  jb      loc_1800135A4
0x1800136ce  mov     edx, 0DDh
0x1800136d3  jmp     loc_18001336C
0x1800136d8  cmp     al, 8
0x1800136da  jb      short loc_1800136FE
0x1800136dc  mov     edx, 0DFh
0x1800136e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136e8  mov     r9, rdi
0x1800136eb  mov     r8, r13
0x1800136ee  mov     [rsp+3B0h+ulFlags], ebx
0x1800136f2  mov     rcx, [rcx+0D8h]
0x1800136f9  call    WPP_SF_qD
0x1800136fe  mov     rcx, [rbp+2B0h+pv]; pv
0x180013702  mov     [rbp+2B0h+pv], r12
0x180013706  test    rcx, rcx
0x180013709  jz      short loc_180013711
0x18001370b  call    cs:__imp_CoTaskMemFree
0x180013711  mov     rcx, [rbp+2B0h+var_320]; pv
0x180013715  mov     [rbp+2B0h+var_320], r12
0x180013719  test    rcx, rcx
0x18001371c  jz      short loc_180013724
  ... truncated ...
```
