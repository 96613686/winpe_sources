# FSMDeviceWatcher::ValidateEnabledSensorGroups(IMFSensorGroupIdManager *)

- ea: `0x180016d0c`
- end: `0x1800174cd`
- name: `?ValidateEnabledSensorGroups@FSMDeviceWatcher@@IEAA_NPEAUIMFSensorGroupIdManager@@@Z`
- size: `1985`
- prototype: `bool __fastcall(FSMDeviceWatcher *__hidden this, struct IMFSensorGroupIdManager *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800144a0`
- `0x180015180`

## callees

- `0x180005f98`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a68`
- `0x180006a98`
- `0x180006f3c`
- `0x18000c8d4`
- `0x18000d4f8`
- `0x18000d594`
- `0x18000ebe4`
- `0x180016120`
- `0x180016d0c`
- `0x1800174d4`
- `0x180018174`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorGroupIdManager` at `0x180016dc1`
- `MFSENSORGROUP!MFCreateSensorGroupIdManager` at `0x180016dc1`

## pseudocode

```c
char __fastcall FSMDeviceWatcher::ValidateEnabledSensorGroups(
        FSMDeviceWatcher *this,
        struct IMFSensorGroupIdManager *a2)
{
  unsigned int v2; // r15d
  char v5; // r12
  unsigned int v6; // r13d
  int updated; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct IMFSensorGroupIdManager *v10; // rbx
  __int64 v11; // rax
  __int64 (__fastcall *v12)(struct IMFSensorGroupIdManager *, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct IMFSensorGroupIdInternal **)); // rsi
  __int64 (__fastcall **v13)(_QWORD, GUID *, struct IMFSensorGroupIdInternal **); // rax
  __int64 v14; // rcx
  struct IMFSensorGroupIdManager *v15; // rbx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(struct IMFSensorGroupIdManager *, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct IMFSensorGroupIdInternal **)); // rsi
  __int64 (__fastcall **v18)(_QWORD, GUID *, struct IMFSensorGroupIdInternal **); // rax
  unsigned int i; // esi
  __int64 v20; // rax
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rsi
  unsigned int v25; // eax
  unsigned int j; // r14d
  __int64 v27; // rsi
  __int64 v28; // rax
  unsigned __int8 Level; // al
  const char *v30; // rax
  __int64 v32; // [rsp+40h] [rbp-49h] BYREF
  struct IMFSensorGroupIdInternal *v33; // [rsp+48h] [rbp-41h] BYREF
  struct IMFSensorGroupIdInternal *v34; // [rsp+50h] [rbp-39h] BYREF
  struct IMFSensorGroupIdManager *v35; // [rsp+58h] [rbp-31h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, GUID *, struct IMFSensorGroupIdInternal **); // [rsp+60h] [rbp-29h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, struct IMFSensorGroupIdInternal **); // [rsp+68h] [rbp-21h] BYREF
  unsigned int v38; // [rsp+70h] [rbp-19h]
  __int64 v39; // [rsp+78h] [rbp-11h] BYREF
  unsigned int v40; // [rsp+80h] [rbp-9h]
  __int64 v41; // [rsp+84h] [rbp-5h]
  __int64 v42; // [rsp+90h] [rbp+7h] BYREF
  unsigned int v43; // [rsp+98h] [rbp+Fh]
  __int64 v44; // [rsp+9Ch] [rbp+13h]
  char v45; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned int v46; // [rsp+100h] [rbp+77h] BYREF
  int v47; // [rsp+108h] [rbp+7Fh] BYREF

  v2 = 0;
  v35 = a2;
  v45 = 0;
  v5 = 0;
  if ( a2 )
    (*(void (__fastcall **)(struct IMFSensorGroupIdManager *))(*(_QWORD *)a2 + 8LL))(a2);
  v37 = 0;
  v6 = 0;
  v34 = 0;
  v36 = 0;
  v33 = 0;
  v46 = 0;
  v47 = 0;
  v42 = 0;
  v44 = 0;
  v43 = 0;
  v39 = 0;
  v41 = 0;
  v40 = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 117, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
  if ( !v35 )
  {
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v35);
    updated = MFCreateSensorGroupIdManager(&v35);
    if ( updated < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_93;
      v8 = 118;
      goto LABEL_9;
    }
  }
  v9 = (__int64)v37;
  v10 = v35;
  v11 = *(_QWORD *)v35;
  v37 = 0;
  v12 = *(__int64 (__fastcall **)(struct IMFSensorGroupIdManager *, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct IMFSensorGroupIdInternal **)))(v11 + 32);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  updated = v12(v10, 0, 0, &v37);
  if ( updated >= 0 )
  {
    v13 = *v37;
    v34 = 0;
    updated = (*v13)(v37, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v34);
    if ( updated >= 0 )
    {
      v14 = (__int64)v36;
      v15 = v35;
      v16 = *(_QWORD *)v35;
      v36 = 0;
      v17 = *(__int64 (__fastcall **)(struct IMFSensorGroupIdManager *, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct IMFSensorGroupIdInternal **)))(v16 + 32);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      updated = v17(v15, 0, 0, &v36);
      if ( updated >= 0 )
      {
        v18 = *v36;
        v33 = 0;
        updated = (*v18)(v36, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v33);
        if ( updated >= 0 )
        {
          if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 123, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
          updated = FSMDeviceWatcher::CollectDevices(this, &GUID_e5323777_f976_4f5b_9b55_b94699c46e44, v33);
          if ( updated >= 0 )
          {
            if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
              WPP_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                125,
                &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
                this);
            updated = FSMDeviceWatcher::CollectDevices(this, &GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca, v33);
            if ( updated >= 0 )
            {
              updated = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, unsigned int *))(*(_QWORD *)v33 + 80LL))(
                          v33,
                          &v46);
              if ( updated >= 0 )
              {
                for ( i = 0; i < v46; ++i )
                {
                  v32 = 0;
                  updated = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, _QWORD, __int64 *))(*(_QWORD *)v33 + 88LL))(
                              v33,
                              i,
                              &v32);
                  if ( updated < 0 )
                  {
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v21 = 128;
LABEL_48:
                      WPP_SF_qD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v21,
                        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
                        this,
                        updated);
                    }
LABEL_49:
                    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v32);
                    goto LABEL_93;
                  }
                  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 24LL))(v32);
                  updated = FSMDeviceWatcher::UpdateSGPairCollection((__int64)a2, v20, (__int64)&v42);
                  if ( updated < 0 )
                  {
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v21 = 129;
                      goto LABEL_48;
                    }
                    goto LABEL_49;
                  }
                  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v32);
                }
                v22 = v43;
                v38 = v43;
                if ( v43 )
                {
                  while ( v2 < v22 )
                  {
                    v46 = 0;
                    v24 = v2;
                    updated = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(v42 + 8LL * v2) + 80LL))(
                                *(_QWORD *)(v42 + 8LL * v2),
                                &v46);
                    if ( updated < 0 )
                    {
                      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        goto LABEL_93;
                      v8 = 131;
                      goto LABEL_9;
                    }
                    v25 = v46;
                    if ( v46 > 1 )
                    {
                      for ( j = 0; j < v25; ++j )
                      {
                        v32 = 0;
                        updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(v42 + 8 * v24)
                                                                                       + 88LL))(
                                    *(_QWORD *)(v42 + 8 * v24),
                                    j,
                                    &v32);
                        if ( updated < 0 )
                        {
                          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                            goto LABEL_49;
                          v21 = 132;
                          goto LABEL_48;
                        }
                        v27 = v32;
                        if ( !(unsigned int)CTEntryArray<IFSConfigurationEntry *>::SetSize(&v39, v6 + 1) )
                        {
                          updated = -2147024882;
                          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                            WPP_SF_qD(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              133,
                              &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
                              this,
                              -2147024882);
                          wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v32);
                          goto LABEL_94;
                        }
                        *(_QWORD *)(v39 + 8LL * v6) = v27;
                        if ( v27 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
                        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
                        {
                          v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 24LL))(v32);
                          WPP_SF_qDDS(
                            *((_QWORD *)WPP_GLOBAL_Control + 27),
                            134,
                            (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
                            (_DWORD)this,
                            j + 1,
                            v46,
                            v28);
                        }
                        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v32);
                        v25 = v46;
                        v6 = v40;
                        v24 = v2;
                      }
                    }
                    v22 = v38;
                    ++v2;
                  }
                  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
                  if ( v6 )
                  {
                    if ( Level >= 8u )
                      WPP_SF_q(
                        *((_QWORD *)WPP_GLOBAL_Control + 27),
                        136,
                        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
                        this);
                    updated = FSMDeviceWatcher::CollectDevices(this, &KSCATEGORY_SENSOR_GROUP_INTERNAL, v34);
                    if ( updated < 0 )
                    {
                      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        goto LABEL_93;
                      v8 = 137;
                      goto LABEL_9;
                    }
                    updated = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, int *))(*(_QWORD *)v34 + 80LL))(
                                v34,
                                &v47);
                    if ( updated < 0 )
                    {
                      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        goto LABEL_93;
                      v8 = 138;
                      goto LABEL_9;
                    }
                    if ( !v47 )
                    {
                      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
                        WPP_SF_q(
                          *((_QWORD *)WPP_GLOBAL_Control + 27),
                          139,
                          &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
                          this);
                      goto LABEL_97;
                    }
                    updated = FSMDeviceWatcher::VerifySensorGroupsForDevices(this, &v39, v34, &v45);
                    if ( updated >= 0 )
                    {
                      v5 = v45;
                      goto LABEL_97;
                    }
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      WPP_SF_qD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        140,
                        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
                        this,
                        updated);
                    v5 = v45;
                    goto LABEL_93;
                  }
                  v5 = 1;
                  if ( Level < 8u )
                    goto LABEL_97;
                  v23 = 135;
                }
                else
                {
                  v5 = 1;
                  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() < 8u )
                    goto LABEL_97;
                  v23 = 130;
                }
                WPP_SF_q(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  v23,
                  &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
                  this);
                goto LABEL_97;
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v8 = 127;
                goto LABEL_9;
              }
            }
            else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v8 = 126;
              goto LABEL_9;
            }
          }
          else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v8 = 124;
            goto LABEL_9;
          }
        }
        else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v8 = 122;
          goto LABEL_9;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 121;
        goto LABEL_9;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = 120;
      goto LABEL_9;
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v8 = 119;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, updated);
  }
LABEL_93:
  if ( updated != -1072875818 )
  {
LABEL_94:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        141,
        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        this,
        updated);
    goto LABEL_101;
  }
LABEL_97:
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v30 = "true";
    if ( !v5 )
      v30 = "false";
    WPP_SF_qDs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      142,
      (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
      (_DWORD)this,
      updated,
      (__int64)v30);
  }
LABEL_101:
  CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(&v39);
  CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(&v42);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v33);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v36);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v34);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v37);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v35);
  return v5;
}

```

## disassembly

```asm
0x180016d0c  mov     [rsp-8+arg_0], rbx
0x180016d11  push    rbp
0x180016d12  push    rsi
0x180016d13  push    rdi
0x180016d14  push    r12
0x180016d16  push    r13
0x180016d18  push    r14
0x180016d1a  push    r15
0x180016d1c  lea     rbp, [rsp-27h]
0x180016d21  sub     rsp, 0B0h
0x180016d28  xor     r15d, r15d
0x180016d2b  mov     [rbp+57h+var_88], rdx
0x180016d2f  mov     [rbp+57h+arg_8], r15b
0x180016d33  mov     r14, rdx
0x180016d36  mov     rdi, rcx
0x180016d39  mov     r12b, r15b
0x180016d3c  test    rdx, rdx
0x180016d3f  jz      short loc_180016D50
0x180016d41  mov     rax, [rdx]
0x180016d44  mov     rcx, rdx
0x180016d47  mov     rax, [rax+8]
0x180016d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d50  mov     [rbp+57h+var_78], r15
0x180016d54  mov     r13d, r15d
0x180016d57  mov     [rbp+57h+var_90], r15
0x180016d5b  mov     [rbp+57h+var_80], r15
0x180016d5f  mov     [rbp+57h+var_98], r15
0x180016d63  mov     [rbp+57h+arg_10], r15d
0x180016d67  mov     [rbp+57h+arg_18], r15d
0x180016d6b  mov     [rbp+57h+var_50], r15
0x180016d6f  mov     [rbp+57h+var_44], r15
0x180016d73  mov     [rbp+57h+var_48], r15d
0x180016d77  mov     [rbp+57h+var_68], r15
0x180016d7b  mov     [rbp+57h+var_5C], r15
0x180016d7f  mov     [rbp+57h+var_60], r15d
0x180016d83  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180016d88  cmp     al, 8
0x180016d8a  jb      short loc_180016DAE
0x180016d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d93  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180016d9a  mov     edx, 75h ; 'u'
0x180016d9f  mov     r9, rdi
0x180016da2  mov     rcx, [rcx+0D8h]
0x180016da9  call    WPP_SF_q
0x180016dae  cmp     [rbp+57h+var_88], r15
0x180016db2  jnz     short loc_180016E02
0x180016db4  lea     rcx, [rbp+57h+var_88]
0x180016db8  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180016dbd  lea     rcx, [rbp+57h+var_88]
0x180016dc1  call    cs:__imp_MFCreateSensorGroupIdManager
0x180016dc7  mov     ebx, eax
0x180016dc9  test    eax, eax
0x180016dcb  jns     short loc_180016E02
0x180016dcd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016dd2  cmp     al, 1
0x180016dd4  jb      loc_1800173EA
0x180016dda  mov     edx, 76h ; 'v'
0x180016ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016de6  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180016ded  mov     r9, rdi
0x180016df0  mov     [rsp+0E0h+var_C0], ebx
0x180016df4  mov     rcx, [rcx+10h]
0x180016df8  call    WPP_SF_qD
0x180016dfd  jmp     loc_1800173EA
0x180016e02  mov     rcx, [rbp+57h+var_78]
0x180016e06  mov     rbx, [rbp+57h+var_88]
0x180016e0a  mov     rax, [rbx]
0x180016e0d  mov     [rbp+57h+var_78], r15
0x180016e11  mov     rsi, [rax+20h]
0x180016e15  test    rcx, rcx
0x180016e18  jz      short loc_180016E26
0x180016e1a  mov     rax, [rcx]
0x180016e1d  mov     rax, [rax+10h]
0x180016e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e26  lea     r9, [rbp+57h+var_78]
0x180016e2a  xor     r8d, r8d
0x180016e2d  xor     edx, edx
0x180016e2f  mov     rcx, rbx
0x180016e32  mov     rax, rsi
0x180016e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e3a  mov     ebx, eax
0x180016e3c  test    eax, eax
0x180016e3e  jns     short loc_180016E54
0x180016e40  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016e45  cmp     al, 1
0x180016e47  jb      loc_1800173EA
0x180016e4d  mov     edx, 77h ; 'w'
0x180016e52  jmp     short loc_180016DDF
0x180016e54  mov     rcx, [rbp+57h+var_90]
0x180016e58  mov     rbx, [rbp+57h+var_78]
0x180016e5c  mov     rax, [rbx]
0x180016e5f  mov     [rbp+57h+var_90], r15
0x180016e63  mov     rsi, [rax]
0x180016e66  test    rcx, rcx
0x180016e69  jz      short loc_180016E77
0x180016e6b  mov     rax, [rcx]
0x180016e6e  mov     rax, [rax+10h]
0x180016e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e77  lea     r8, [rbp+57h+var_90]
0x180016e7b  mov     rcx, rbx
0x180016e7e  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x180016e85  mov     rax, rsi
0x180016e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e8d  mov     ebx, eax
0x180016e8f  test    eax, eax
0x180016e91  jns     short loc_180016EAA
0x180016e93  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016e98  cmp     al, 1
0x180016e9a  jb      loc_1800173EA
0x180016ea0  mov     edx, 78h ; 'x'
0x180016ea5  jmp     loc_180016DDF
0x180016eaa  mov     rcx, [rbp+57h+var_80]
0x180016eae  mov     rbx, [rbp+57h+var_88]
0x180016eb2  mov     rax, [rbx]
0x180016eb5  mov     [rbp+57h+var_80], r15
0x180016eb9  mov     rsi, [rax+20h]
0x180016ebd  test    rcx, rcx
0x180016ec0  jz      short loc_180016ECE
0x180016ec2  mov     rax, [rcx]
0x180016ec5  mov     rax, [rax+10h]
0x180016ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ece  lea     r9, [rbp+57h+var_80]
0x180016ed2  xor     r8d, r8d
0x180016ed5  xor     edx, edx
0x180016ed7  mov     rcx, rbx
0x180016eda  mov     rax, rsi
0x180016edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ee2  mov     ebx, eax
0x180016ee4  test    eax, eax
0x180016ee6  jns     short loc_180016EFF
0x180016ee8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016eed  cmp     al, 1
0x180016eef  jb      loc_1800173EA
0x180016ef5  mov     edx, 79h ; 'y'
0x180016efa  jmp     loc_180016DDF
0x180016eff  mov     rcx, [rbp+57h+var_98]
0x180016f03  mov     rbx, [rbp+57h+var_80]
0x180016f07  mov     rax, [rbx]
0x180016f0a  mov     [rbp+57h+var_98], r15
0x180016f0e  mov     rsi, [rax]
0x180016f11  test    rcx, rcx
0x180016f14  jz      short loc_180016F22
0x180016f16  mov     rax, [rcx]
0x180016f19  mov     rax, [rax+10h]
0x180016f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f22  lea     r8, [rbp+57h+var_98]
0x180016f26  mov     rcx, rbx
0x180016f29  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x180016f30  mov     rax, rsi
0x180016f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f38  mov     ebx, eax
0x180016f3a  test    eax, eax
0x180016f3c  jns     short loc_180016F55
0x180016f3e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016f43  cmp     al, 1
0x180016f45  jb      loc_1800173EA
0x180016f4b  mov     edx, 7Ah ; 'z'
0x180016f50  jmp     loc_180016DDF
0x180016f55  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180016f5a  cmp     al, 8
0x180016f5c  jb      short loc_180016F80
0x180016f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f65  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180016f6c  mov     edx, 7Bh ; '{'
0x180016f71  mov     r9, rdi
0x180016f74  mov     rcx, [rcx+0D8h]
0x180016f7b  call    WPP_SF_q
0x180016f80  mov     r8, [rbp+57h+var_98]; struct IMFSensorGroupIdInternal *
0x180016f84  lea     rdx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44; struct _GUID *
0x180016f8b  mov     rcx, rdi; this
0x180016f8e  call    ?CollectDevices@FSMDeviceWatcher@@IEAAJAEBU_GUID@@PEAUIMFSensorGroupIdInternal@@@Z; FSMDeviceWatcher::CollectDevices(_GUID const &,IMFSensorGroupIdInternal *)
0x180016f93  mov     ebx, eax
0x180016f95  test    eax, eax
0x180016f97  jns     short loc_180016FB0
0x180016f99  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016f9e  cmp     al, 1
0x180016fa0  jb      loc_1800173EA
0x180016fa6  mov     edx, 7Ch ; '|'
0x180016fab  jmp     loc_180016DDF
0x180016fb0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180016fb5  cmp     al, 8
0x180016fb7  jb      short loc_180016FDB
0x180016fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180016fc0  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180016fc7  mov     edx, 7Dh ; '}'
0x180016fcc  mov     r9, rdi
0x180016fcf  mov     rcx, [rcx+0D8h]
0x180016fd6  call    WPP_SF_q
0x180016fdb  mov     r8, [rbp+57h+var_98]; struct IMFSensorGroupIdInternal *
0x180016fdf  lea     rdx, _GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca; struct _GUID *
0x180016fe6  mov     rcx, rdi; this
0x180016fe9  call    ?CollectDevices@FSMDeviceWatcher@@IEAAJAEBU_GUID@@PEAUIMFSensorGroupIdInternal@@@Z; FSMDeviceWatcher::CollectDevices(_GUID const &,IMFSensorGroupIdInternal *)
0x180016fee  mov     ebx, eax
0x180016ff0  test    eax, eax
0x180016ff2  jns     short loc_18001700B
0x180016ff4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016ff9  cmp     al, 1
0x180016ffb  jb      loc_1800173EA
0x180017001  mov     edx, 7Eh ; '~'
0x180017006  jmp     loc_180016DDF
0x18001700b  mov     rcx, [rbp+57h+var_98]
0x18001700f  lea     rdx, [rbp+57h+arg_10]
0x180017013  mov     rax, [rcx]
0x180017016  mov     rax, [rax+50h]
0x18001701a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001701f  mov     ebx, eax
0x180017021  test    eax, eax
0x180017023  jns     short loc_18001703C
0x180017025  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001702a  cmp     al, 1
0x18001702c  jb      loc_1800173EA
0x180017032  mov     edx, 7Fh
0x180017037  jmp     loc_180016DDF
0x18001703c  mov     esi, r15d
0x18001703f  cmp     esi, [rbp+57h+arg_10]
0x180017042  jnb     loc_1800170E4
0x180017048  mov     rcx, [rbp+57h+var_98]
0x18001704c  lea     r8, [rbp+57h+var_A0]
0x180017050  mov     [rbp+57h+var_A0], r15
0x180017054  mov     edx, esi
0x180017056  mov     rax, [rcx]
0x180017059  mov     rax, [rax+58h]
0x18001705d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017062  mov     ebx, eax
0x180017064  test    eax, eax
0x180017066  js      short loc_1800170AA
0x180017068  mov     rcx, [rbp+57h+var_A0]
0x18001706c  mov     rax, [rcx]
0x18001706f  mov     rax, [rax+18h]
0x180017073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017078  mov     rdx, rax
0x18001707b  lea     r8, [rbp+57h+var_50]
0x18001707f  mov     rcx, r14
0x180017082  call    ?UpdateSGPairCollection@FSMDeviceWatcher@@SAJPEAUIMFSensorGroupIdManager@@PEBGAEAV?$CTUnkArray@UIMFSensorGroupIdInternal@@@@@Z; FSMDeviceWatcher::UpdateSGPairCollection(IMFSensorGroupIdManager *,ushort const *,CTUnkArray<IMFSensorGroupIdInternal> &)
0x180017087  mov     ebx, eax
0x180017089  test    eax, eax
0x18001708b  js      short loc_18001709A
0x18001708d  lea     rcx, [rbp+57h+var_A0]
0x180017091  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180017096  inc     esi
0x180017098  jmp     short loc_18001703F
0x18001709a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001709f  cmp     al, 1
0x1800170a1  jb      short loc_1800170D6
0x1800170a3  mov     edx, 81h
0x1800170a8  jmp     short loc_1800170B8
0x1800170aa  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800170af  cmp     al, 1
0x1800170b1  jb      short loc_1800170D6
0x1800170b3  mov     edx, 80h
0x1800170b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170bf  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800170c6  mov     r9, rdi
0x1800170c9  mov     [rsp+0E0h+var_C0], ebx
0x1800170cd  mov     rcx, [rcx+10h]
0x1800170d1  call    WPP_SF_qD
0x1800170d6  lea     rcx, [rbp+57h+var_A0]
0x1800170da  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800170df  jmp     loc_1800173EA
0x1800170e4  mov     eax, [rbp+57h+var_48]
0x1800170e7  mov     [rbp+57h+var_70], eax
0x1800170ea  test    eax, eax
0x1800170ec  jnz     short loc_180017108
0x1800170ee  mov     r12b, 1
0x1800170f1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800170f6  cmp     al, 8
0x1800170f8  jb      loc_1800172D2
0x1800170fe  mov     edx, 82h
0x180017103  jmp     loc_1800172B5
0x180017108  cmp     r15d, eax
0x18001710b  jnb     loc_18001729C
0x180017111  mov     rax, [rbp+57h+var_50]
0x180017115  lea     rdx, [rbp+57h+arg_10]
0x180017119  mov     [rbp+57h+arg_10], 0
0x180017120  mov     esi, r15d
0x180017123  mov     rcx, [rax+rsi*8]
0x180017127  mov     rax, [rcx]
0x18001712a  mov     rax, [rax+50h]
0x18001712e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017133  mov     ebx, eax
0x180017135  test    eax, eax
0x180017137  js      loc_180017285
0x18001713d  mov     eax, [rbp+57h+arg_10]
0x180017140  cmp     eax, 1
0x180017143  jbe     loc_180017224
0x180017149  xor     r14d, r14d
0x18001714c  cmp     r14d, eax
0x18001714f  jnb     loc_180017224
0x180017155  mov     rax, [rbp+57h+var_50]
0x180017159  lea     r8, [rbp+57h+var_A0]
0x18001715d  mov     [rbp+57h+var_A0], 0
0x180017165  mov     edx, r14d
0x180017168  mov     rcx, [rax+rsi*8]
0x18001716c  mov     rax, [rcx]
0x18001716f  mov     rax, [rax+58h]
0x180017173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017178  mov     ebx, eax
0x18001717a  test    eax, eax
0x18001717c  js      loc_18001726E
0x180017182  mov     rsi, [rbp+57h+var_A0]
  ... truncated ...
```
