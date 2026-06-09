# FSMDeviceWatcher::InternalUpdateSensorGroups(bool *)

- ea: `0x1800127f0`
- end: `0x180012ebb`
- name: `?InternalUpdateSensorGroups@FSMDeviceWatcher@@IEAAJPEA_N@Z`
- size: `1739`
- prototype: `__int64 __fastcall(FSMDeviceWatcher *__hidden this, bool *)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800144a0`
- `0x180014e40`
- `0x180015180`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180005f98`
- `0x180006a98`
- `0x180006f3c`
- `0x18000d154`
- `0x1800124f4`
- `0x1800127f0`
- `0x18001376c`
- `0x180015e38`
- `0x180016704`
- `0x1800179c8`
- `0x180017bec`
- `0x180017c44`
- `0x18002ed6c`
- `0x18004bf44`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorGroupById` at `0x180012a4b`
- `MFSENSORGROUP!MFCreateSensorGroupById` at `0x180012c10`
- `MFSENSORGROUP!MFCreateSensorGroupById` at `0x180012a4b`
- `MFSENSORGROUP!MFCreateSensorGroupById` at `0x180012c10`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::InternalUpdateSensorGroups(void ***this, bool *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // r8
  int updated; // eax
  __int64 v8; // rdx
  unsigned int v9; // r12d
  int v10; // eax
  __int64 v11; // rcx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v13)(_QWORD, GUID *, __int64 *); // rax
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // r13
  int v15; // eax
  __int64 v16; // rcx
  struct IMFSensorGroup *v17; // rbx
  __int64 (__fastcall **v18)(struct IMFSensorGroup *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v19)(struct IMFSensorGroup *, GUID *, __int64 *); // r14
  __int64 *v20; // rcx
  int v21; // eax
  struct IMFSensorGroup *v22; // rcx
  __int64 v23; // rbx
  __int64 (__fastcall **v24)(__int64, GUID *, struct IMFSensorGroup **); // rax
  __int64 (__fastcall *v25)(__int64, GUID *, struct IMFSensorGroup **); // r14
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v29; // rdx
  __int64 *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rdx
  _BYTE v33[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct IMFSensorGroup *v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v36)(__int64, GUID *, struct IMFSensorGroup **); // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v39; // [rsp+70h] [rbp-90h]
  __int64 v40; // [rsp+74h] [rbp-8Ch]
  __int64 v41; // [rsp+80h] [rbp-80h] BYREF
  int v42; // [rsp+88h] [rbp-78h]
  __int64 v43; // [rsp+8Ch] [rbp-74h]
  _BYTE v44[40]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE Buf2[56]; // [rsp+C8h] [rbp-38h] BYREF
  GUID Buf1; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v47[2]; // [rsp+110h] [rbp+10h] BYREF

  v38 = 0;
  v40 = 0;
  v39 = 0;
  v41 = 0;
  v43 = 0;
  v42 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        164,
        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        this,
        -2147467261);
    goto LABEL_50;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2602>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CameraQI2602>::GetImpl'::`2'::impl)
    && (Microsoft_Windows_MF_FrameServerEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(
      v5,
      MF_FrameServer_FsmDeviceWatcherInternalUpdateSensorGroups_Start,
      v6,
      1,
      &Buf1);
  }
  updated = FSMDeviceWatcher::InternalUpdateSensorGroups(
              (_DWORD)this,
              (unsigned int)&GUID_e5323777_f976_4f5b_9b55_b94699c46e44,
              (unsigned int)&v38,
              (unsigned int)&v41,
              (bool)a2);
  v4 = updated;
  if ( updated < 0 )
  {
    if ( g_wppLevels )
    {
      v8 = 165;
      goto LABEL_11;
    }
    goto LABEL_50;
  }
  updated = FSMDeviceWatcher::InternalUpdateSensorGroups(
              (_DWORD)this,
              (unsigned int)&GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca,
              (unsigned int)&v38,
              (unsigned int)&v41,
              (bool)a2);
  v4 = updated;
  if ( updated < 0 )
  {
    if ( g_wppLevels )
    {
      v8 = 166;
      goto LABEL_11;
    }
    goto LABEL_50;
  }
  v9 = 0;
  if ( !v39 )
  {
LABEL_49:
    FSMDeviceWatcher::InternalUpdateSensorGroupsForNetworkCameras((__int64 **)this, a2);
    utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(this + 15);
    goto LABEL_50;
  }
  while ( 1 )
  {
    v37 = 0;
    updated = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(v38 + 8LL * v9) + 80LL))(
                *(_QWORD *)(v38 + 8LL * v9),
                &v37);
    v4 = updated;
    if ( updated < 0 )
      break;
    if ( v37 > 1 )
    {
      v35 = 0;
      Buf1 = GUID_00000000_0000_0000_0000_000000000000;
      v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v38 + 8LL * v9) + 72LL))(
              *(_QWORD *)(v38 + 8LL * v9),
              0);
      v4 = v10;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v32 = 168;
LABEL_86:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v32,
            &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
            this,
            v10);
        }
LABEL_87:
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v35);
        goto LABEL_50;
      }
      v11 = v35;
      v12 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v38 + 8LL * v9);
      v13 = *v12;
      v35 = 0;
      v14 = *v13;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v10 = v14(v12, &GUID_006e0e79_a511_436e_83be_fce6990f258d, &v35);
      v4 = v10;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v32 = 169;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)(v38 + 8LL * v9) + 160LL))(
              *(_QWORD *)(v38 + 8LL * v9),
              &Buf1);
      v4 = v10;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v32 = 170;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
      {
        v36 = 0;
        v34 = 0;
        v15 = MFCreateSensorGroupById(v35, 0, &v34);
        v4 = v15;
        if ( v15 < 0 )
        {
          if ( g_wppLevels )
          {
            v29 = 171;
LABEL_65:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v29,
              &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
              this,
              v15);
          }
LABEL_66:
          wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v36);
          v30 = (__int64 *)&v34;
LABEL_67:
          wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(v30);
          goto LABEL_87;
        }
        v16 = (__int64)v36;
        v17 = v34;
        v18 = *(__int64 (__fastcall ***)(struct IMFSensorGroup *, GUID *, __int64 *))v34;
        v36 = 0;
        v19 = *v18;
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v15 = v19(v17, &GUID_8e3196f0_ce22_4599_a16a_886bb13a7966, (__int64 *)&v36);
        v4 = v15;
        if ( v15 < 0 )
        {
          if ( g_wppLevels )
          {
            v29 = 172;
            goto LABEL_65;
          }
          goto LABEL_66;
        }
        if ( (int)FSMDeviceWatcher::UpdateSensorGroupWithSensorTransformFactory((FSMDeviceWatcher *)this, v34, &Buf1) >= 0 )
        {
          if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
          {
            v15 = FSAddSensorTransformsToSensorGroup(&Buf1, v34);
            v4 = v15;
            if ( v15 < 0 )
            {
              if ( g_wppLevels )
              {
                v29 = 173;
                goto LABEL_65;
              }
              goto LABEL_66;
            }
          }
        }
        v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IMFSensorGroup **), __int64))(*v36)[9])(
                v36,
                1);
        v4 = v15;
        if ( v15 < 0 )
        {
          if ( g_wppLevels )
          {
            v29 = 174;
            goto LABEL_65;
          }
          goto LABEL_66;
        }
        v15 = (*v36)[5]((__int64)v36, 0, 0);
        v4 = v15;
        if ( v15 < 0 )
        {
          if ( g_wppLevels )
          {
            v29 = 175;
            goto LABEL_65;
          }
          goto LABEL_66;
        }
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v36);
        v20 = (__int64 *)&v34;
        goto LABEL_46;
      }
      v33[0] = 0;
      v10 = FSMDeviceWatcher::SensorDevicesInCollection(*(_QWORD *)(v38 + 8LL * v9), &v41, v33);
      v4 = v10;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v32 = 176;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      if ( !v33[0]
        || (memset_0(v44, 0, 0x60u),
            memset(v47, 0, sizeof(v47)),
            (*(int (__fastcall **)(_QWORD, _OWORD *, __int64))(**(_QWORD **)(v38 + 8LL * v9) + 136LL))(
              *(_QWORD *)(v38 + 8LL * v9),
              v47,
              32) < 0)
        || (*(int (__fastcall **)(_QWORD, _QWORD, __int64, _BYTE *, int, _QWORD))(**(_QWORD **)(v38 + 8LL * v9) + 200LL))(
             *(_QWORD *)(v38 + 8LL * v9),
             0,
             3,
             v44,
             96,
             0) < 0
        || memcmp_0(v47, Buf2, 0x20u) )
      {
        v34 = 0;
        v36 = 0;
        v21 = MFCreateSensorGroupById(v35, 0, &v36);
        v4 = v21;
        if ( v21 < 0 )
        {
          if ( g_wppLevels )
          {
            v31 = 177;
LABEL_76:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v31,
              &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
              this,
              v21);
          }
LABEL_77:
          wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v34);
          v30 = (__int64 *)&v36;
          goto LABEL_67;
        }
        v22 = v34;
        v23 = (__int64)v36;
        v24 = *v36;
        v34 = 0;
        v25 = *v24;
        if ( v22 )
          (*(void (__fastcall **)(struct IMFSensorGroup *))(*(_QWORD *)v22 + 16LL))(v22);
        v21 = v25(v23, &GUID_8e3196f0_ce22_4599_a16a_886bb13a7966, &v34);
        v4 = v21;
        if ( v21 < 0 )
        {
          if ( g_wppLevels )
          {
            v31 = 178;
            goto LABEL_76;
          }
          goto LABEL_77;
        }
        v21 = (*(__int64 (__fastcall **)(struct IMFSensorGroup *, __int64))(*(_QWORD *)v34 + 72LL))(v34, 1);
        v4 = v21;
        if ( v21 < 0 )
        {
          if ( g_wppLevels )
          {
            v31 = 179;
            goto LABEL_76;
          }
          goto LABEL_77;
        }
        v21 = (*(__int64 (__fastcall **)(struct IMFSensorGroup *, _QWORD, _QWORD))(*(_QWORD *)v34 + 40LL))(v34, 0, 0);
        v4 = v21;
        if ( v21 < 0 )
        {
          if ( g_wppLevels )
          {
            v31 = 180;
            goto LABEL_76;
          }
          goto LABEL_77;
        }
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v34);
        v20 = (__int64 *)&v36;
LABEL_46:
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(v20);
      }
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v35);
    }
    if ( ++v9 >= v39 )
      goto LABEL_49;
  }
  if ( g_wppLevels )
  {
    v8 = 167;
LABEL_11:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, updated);
  }
LABEL_50:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2602>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CameraQI2602>::GetImpl'::`2'::impl)
    && a2
    && (Microsoft_Windows_MF_FrameServerEnableBits & 1) != 0 )
  {
    McTemplateU0t_EventWriteTransfer(v27, v26, *a2);
  }
  CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(&v41);
  CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(&v38);
  return v4;
}

```

## disassembly

```asm
0x1800127f0  mov     [rsp-8+arg_10], rbx
0x1800127f5  push    rbp
0x1800127f6  push    rsi
0x1800127f7  push    rdi
0x1800127f8  push    r12
0x1800127fa  push    r13
0x1800127fc  push    r14
0x1800127fe  push    r15
0x180012800  lea     rbp, [rsp-40h]
0x180012805  sub     rsp, 140h
0x18001280c  mov     rax, cs:__security_cookie
0x180012813  xor     rax, rsp
0x180012816  mov     [rbp+70h+var_40], rax
0x18001281a  xor     r13d, r13d
0x18001281d  mov     r15, rdx
0x180012820  mov     [rsp+170h+var_108], r13
0x180012825  mov     rsi, rcx
0x180012828  mov     [rsp+170h+var_FC], r13
0x18001282d  mov     [rsp+170h+var_100], r13d
0x180012832  mov     [rbp+70h+var_F0], r13
0x180012836  mov     [rbp+70h+var_E4], r13
0x18001283a  mov     [rbp+70h+var_E8], r13d
0x18001283e  test    rdx, rdx
0x180012841  jnz     short loc_180012880
0x180012843  mov     ebx, 80004003h
0x180012848  lea     edi, [rdx+1]
0x18001284b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180012852  jb      loc_180012CE4
0x180012858  mov     edx, 0A4h
0x18001285d  mov     dword ptr [rsp+170h+var_150], ebx
0x180012861  mov     rcx, cs:WPP_GLOBAL_Control
0x180012868  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x18001286f  mov     r9, rsi
0x180012872  mov     rcx, [rcx+10h]
0x180012876  call    WPP_SF_qD
0x18001287b  jmp     loc_180012CE4
0x180012880  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraQI2602@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2602@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2602> `wil::Feature<__WilFeatureTraits_Feature_CameraQI2602>::GetImpl(void)'::`2'::impl
0x180012887  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2602@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2602>::__private_IsEnabled(void)
0x18001288c  mov     edi, 1
0x180012891  test    al, al
0x180012893  jz      short loc_1800128B6
0x180012895  test    cs:Microsoft_Windows_MF_FrameServerEnableBits, dil
0x18001289c  jz      short loc_1800128B6
0x18001289e  lea     rax, [rbp+70h+Buf1]
0x1800128a2  mov     r9d, edi
0x1800128a5  lea     rdx, MF_FrameServer_FsmDeviceWatcherInternalUpdateSensorGroups_Start
0x1800128ac  mov     [rsp+170h+var_150], rax
0x1800128b1  call    McGenEventWrite_EventWriteTransfer
0x1800128b6  lea     r9, [rbp+70h+var_F0]
0x1800128ba  mov     [rsp+170h+var_150], r15
0x1800128bf  lea     r8, [rsp+170h+var_108]
0x1800128c4  mov     rcx, rsi
0x1800128c7  lea     rdx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x1800128ce  call    ?InternalUpdateSensorGroups@FSMDeviceWatcher@@IEAAJAEBU_GUID@@AEAV?$CTUnkArray@UIMFSensorGroupIdInternal@@@@AEAV?$CTUnkArray@UIMFSensorGroupId@@@@PEA_N@Z; FSMDeviceWatcher::InternalUpdateSensorGroups(_GUID const &,CTUnkArray<IMFSensorGroupIdInternal> &,CTUnkArray<IMFSensorGroupId> &,bool *)
0x1800128d3  mov     ebx, eax
0x1800128d5  test    eax, eax
0x1800128d7  jns     short loc_1800128F4
0x1800128d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800128e0  jb      loc_180012CE4
0x1800128e6  mov     edx, 0A5h
0x1800128eb  mov     dword ptr [rsp+170h+var_150], eax
0x1800128ef  jmp     loc_180012861
0x1800128f4  lea     r9, [rbp+70h+var_F0]
0x1800128f8  mov     [rsp+170h+var_150], r15
0x1800128fd  lea     r8, [rsp+170h+var_108]
0x180012902  mov     rcx, rsi
0x180012905  lea     rdx, _GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca
0x18001290c  call    ?InternalUpdateSensorGroups@FSMDeviceWatcher@@IEAAJAEBU_GUID@@AEAV?$CTUnkArray@UIMFSensorGroupIdInternal@@@@AEAV?$CTUnkArray@UIMFSensorGroupId@@@@PEA_N@Z; FSMDeviceWatcher::InternalUpdateSensorGroups(_GUID const &,CTUnkArray<IMFSensorGroupIdInternal> &,CTUnkArray<IMFSensorGroupId> &,bool *)
0x180012911  mov     ebx, eax
0x180012913  test    eax, eax
0x180012915  jns     short loc_18001292B
0x180012917  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18001291e  jb      loc_180012CE4
0x180012924  mov     edx, 0A6h
0x180012929  jmp     short loc_1800128EB
0x18001292b  mov     r12d, r13d
0x18001292e  cmp     [rsp+170h+var_100], r13d
0x180012933  jbe     loc_180012CD0
0x180012939  mov     rax, [rsp+170h+var_108]
0x18001293e  lea     rdx, [rsp+170h+var_110]
0x180012943  mov     [rsp+170h+var_110], r13d
0x180012948  mov     r14d, r12d
0x18001294b  mov     rcx, [rax+r14*8]
0x18001294f  mov     rax, [rcx]
0x180012952  mov     rax, [rax+50h]
0x180012956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001295b  mov     ebx, eax
0x18001295d  test    eax, eax
0x18001295f  js      loc_180012EA4
0x180012965  cmp     [rsp+170h+var_110], edi
0x180012969  jbe     loc_180012CC2
0x18001296f  mov     rax, [rsp+170h+var_108]
0x180012974  xor     edx, edx
0x180012976  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001297d  mov     [rsp+170h+var_120], r13
0x180012982  movdqu  [rbp+70h+Buf1], xmm0
0x180012987  mov     rcx, [rax+r14*8]
0x18001298b  mov     rax, [rcx]
0x18001298e  mov     rax, [rax+48h]
0x180012992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012997  mov     ebx, eax
0x180012999  test    eax, eax
0x18001299b  js      loc_180012E69
0x1800129a1  mov     rax, [rsp+170h+var_108]
0x1800129a6  mov     rcx, [rsp+170h+var_120]
0x1800129ab  mov     rbx, [rax+r14*8]
0x1800129af  mov     rax, [rbx]
0x1800129b2  mov     [rsp+170h+var_120], 0
0x1800129bb  mov     r13, [rax]
0x1800129be  test    rcx, rcx
0x1800129c1  jz      short loc_1800129CF
0x1800129c3  mov     rdx, [rcx]
0x1800129c6  mov     rax, [rdx+10h]
0x1800129ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129cf  lea     r8, [rsp+170h+var_120]
0x1800129d4  mov     rcx, rbx
0x1800129d7  lea     rdx, _GUID_006e0e79_a511_436e_83be_fce6990f258d
0x1800129de  mov     rax, r13
0x1800129e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129e6  xor     r13d, r13d
0x1800129e9  mov     ebx, eax
0x1800129eb  test    eax, eax
0x1800129ed  js      loc_180012E59
0x1800129f3  mov     rax, [rsp+170h+var_108]
0x1800129f8  lea     rdx, [rbp+70h+Buf1]
0x1800129fc  mov     rcx, [rax+r14*8]
0x180012a00  mov     rax, [rcx]
0x180012a03  mov     rax, [rax+0A0h]
0x180012a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a0f  mov     ebx, eax
0x180012a11  test    eax, eax
0x180012a13  js      loc_180012E49
0x180012a19  lea     r8d, [r13+10h]; Size
0x180012a1d  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180012a24  lea     rcx, [rbp+70h+Buf1]; Buf1
0x180012a28  call    memcmp_0
0x180012a2d  test    eax, eax
0x180012a2f  jz      loc_180012B3A
0x180012a35  mov     rcx, [rsp+170h+var_120]
0x180012a3a  lea     r8, [rsp+170h+var_128]
0x180012a3f  xor     edx, edx
0x180012a41  mov     [rsp+170h+var_118], r13
0x180012a46  mov     [rsp+170h+var_128], r13
0x180012a4b  call    cs:__imp_MFCreateSensorGroupById
0x180012a51  mov     ebx, eax
0x180012a53  test    eax, eax
0x180012a55  js      loc_180012D87
0x180012a5b  mov     rcx, [rsp+170h+var_118]
0x180012a60  mov     rbx, [rsp+170h+var_128]
0x180012a65  mov     rax, [rbx]
0x180012a68  mov     [rsp+170h+var_118], r13
0x180012a6d  mov     r14, [rax]
0x180012a70  test    rcx, rcx
0x180012a73  jz      short loc_180012A81
0x180012a75  mov     rdx, [rcx]
0x180012a78  mov     rax, [rdx+10h]
0x180012a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a81  lea     r8, [rsp+170h+var_118]
0x180012a86  mov     rcx, rbx
0x180012a89  lea     rdx, _GUID_8e3196f0_ce22_4599_a16a_886bb13a7966
0x180012a90  mov     rax, r14
0x180012a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a98  mov     ebx, eax
0x180012a9a  test    eax, eax
0x180012a9c  js      loc_180012D77
0x180012aa2  mov     rdx, [rsp+170h+var_128]; struct IMFSensorGroup *
0x180012aa7  lea     r8, [rbp+70h+Buf1]; struct _GUID *
0x180012aab  mov     rcx, rsi; this
0x180012aae  call    ?UpdateSensorGroupWithSensorTransformFactory@FSMDeviceWatcher@@IEAAJPEAUIMFSensorGroup@@PEAU_GUID@@@Z; FSMDeviceWatcher::UpdateSensorGroupWithSensorTransformFactory(IMFSensorGroup *,_GUID *)
0x180012ab3  test    eax, eax
0x180012ab5  js      short loc_180012AE9
0x180012ab7  mov     r8d, 10h; Size
0x180012abd  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180012ac4  lea     rcx, [rbp+70h+Buf1]; Buf1
0x180012ac8  call    memcmp_0
0x180012acd  test    eax, eax
0x180012acf  jz      short loc_180012AE9
0x180012ad1  mov     rdx, [rsp+170h+var_128]
0x180012ad6  lea     rcx, [rbp+70h+Buf1]
0x180012ada  call    FSAddSensorTransformsToSensorGroup
0x180012adf  mov     ebx, eax
0x180012ae1  test    eax, eax
0x180012ae3  js      loc_180012D47
0x180012ae9  mov     rcx, [rsp+170h+var_118]
0x180012aee  mov     edx, edi
0x180012af0  mov     rax, [rcx]
0x180012af3  mov     rax, [rax+48h]
0x180012af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012afc  mov     ebx, eax
0x180012afe  test    eax, eax
0x180012b00  js      loc_180012D67
0x180012b06  mov     rcx, [rsp+170h+var_118]
0x180012b0b  xor     r8d, r8d
0x180012b0e  xor     edx, edx
0x180012b10  mov     rax, [rcx]
0x180012b13  mov     rax, [rax+28h]
0x180012b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b1c  mov     ebx, eax
0x180012b1e  test    eax, eax
0x180012b20  js      loc_180012D57
0x180012b26  lea     rcx, [rsp+170h+var_118]
0x180012b2b  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180012b30  lea     rcx, [rsp+170h+var_128]
0x180012b35  jmp     loc_180012CB3
0x180012b3a  mov     rcx, [rsp+170h+var_108]
0x180012b3f  lea     r8, [rsp+170h+var_130]
0x180012b44  lea     rdx, [rbp+70h+var_F0]
0x180012b48  mov     [rsp+170h+var_130], r13b
0x180012b4d  mov     rcx, [rcx+r14*8]
0x180012b51  call    ?SensorDevicesInCollection@FSMDeviceWatcher@@SAJPEAUIMFSensorGroupIdInternal@@AEAV?$CTUnkArray@UIMFSensorGroupId@@@@PEA_N@Z; FSMDeviceWatcher::SensorDevicesInCollection(IMFSensorGroupIdInternal *,CTUnkArray<IMFSensorGroupId> &,bool *)
0x180012b56  mov     ebx, eax
0x180012b58  test    eax, eax
0x180012b5a  js      loc_180012E39
0x180012b60  cmp     [rsp+170h+var_130], r13b
0x180012b65  jz      loc_180012BFA
0x180012b6b  xor     edx, edx; Val
0x180012b6d  lea     rcx, [rbp+70h+var_D0]; void *
0x180012b71  lea     r8d, [rdx+60h]; Size
0x180012b75  call    memset_0
0x180012b7a  mov     rax, [rsp+170h+var_108]
0x180012b7f  lea     rdx, [rbp+70h+var_60]
0x180012b83  xorps   xmm0, xmm0
0x180012b86  xor     r9d, r9d
0x180012b89  movups  [rbp+70h+var_60], xmm0
0x180012b8d  movups  [rbp+70h+var_50], xmm0
0x180012b91  mov     rcx, [rax+r14*8]
0x180012b95  lea     r8d, [r9+20h]
0x180012b99  mov     rax, [rcx]
0x180012b9c  mov     rax, [rax+88h]
0x180012ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ba8  test    eax, eax
0x180012baa  js      short loc_180012BFA
0x180012bac  mov     rax, [rsp+170h+var_108]
0x180012bb1  lea     r9, [rbp+70h+var_D0]
0x180012bb5  xor     edx, edx
0x180012bb7  mov     [rsp+170h+var_148], r13
0x180012bbc  mov     dword ptr [rsp+170h+var_150], 60h ; '`'
0x180012bc4  mov     rcx, [rax+r14*8]
0x180012bc8  lea     r8d, [rdx+3]
0x180012bcc  mov     rax, [rcx]
0x180012bcf  mov     rax, [rax+0C8h]
0x180012bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bdb  test    eax, eax
0x180012bdd  js      short loc_180012BFA
0x180012bdf  mov     r8d, 20h ; ' '; Size
0x180012be5  lea     rdx, [rbp+70h+Buf2]; Buf2
0x180012be9  lea     rcx, [rbp+70h+var_60]; Buf1
0x180012bed  call    memcmp_0
0x180012bf2  test    eax, eax
0x180012bf4  jz      loc_180012CB8
0x180012bfa  mov     rcx, [rsp+170h+var_120]
0x180012bff  lea     r8, [rsp+170h+var_118]
0x180012c04  xor     edx, edx
0x180012c06  mov     [rsp+170h+var_128], r13
0x180012c0b  mov     [rsp+170h+var_118], r13
0x180012c10  call    cs:__imp_MFCreateSensorGroupById
0x180012c16  mov     ebx, eax
0x180012c18  test    eax, eax
0x180012c1a  js      loc_180012DFC
0x180012c20  mov     rcx, [rsp+170h+var_128]
0x180012c25  mov     rbx, [rsp+170h+var_118]
0x180012c2a  mov     rax, [rbx]
0x180012c2d  mov     [rsp+170h+var_128], r13
0x180012c32  mov     r14, [rax]
0x180012c35  test    rcx, rcx
0x180012c38  jz      short loc_180012C46
0x180012c3a  mov     rdx, [rcx]
0x180012c3d  mov     rax, [rdx+10h]
0x180012c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c46  lea     r8, [rsp+170h+var_128]
0x180012c4b  mov     rcx, rbx
0x180012c4e  lea     rdx, _GUID_8e3196f0_ce22_4599_a16a_886bb13a7966
0x180012c55  mov     rax, r14
0x180012c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c5d  mov     ebx, eax
0x180012c5f  test    eax, eax
0x180012c61  js      loc_180012DEC
0x180012c67  mov     rcx, [rsp+170h+var_128]
0x180012c6c  mov     edx, edi
0x180012c6e  mov     rax, [rcx]
0x180012c71  mov     rax, [rax+48h]
0x180012c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c7a  mov     ebx, eax
0x180012c7c  test    eax, eax
0x180012c7e  js      loc_180012DDC
0x180012c84  mov     rcx, [rsp+170h+var_128]
0x180012c89  xor     r8d, r8d
0x180012c8c  xor     edx, edx
0x180012c8e  mov     rax, [rcx]
0x180012c91  mov     rax, [rax+28h]
0x180012c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c9a  mov     ebx, eax
0x180012c9c  test    eax, eax
0x180012c9e  js      loc_180012DCC
0x180012ca4  lea     rcx, [rsp+170h+var_128]
0x180012ca9  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180012cae  lea     rcx, [rsp+170h+var_118]
0x180012cb3  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180012cb8  lea     rcx, [rsp+170h+var_120]
0x180012cbd  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
  ... truncated ...
```
