# FSMDeviceWatcher::RegisterWatcher(void)

- ea: `0x180015180`
- end: `0x18001578d`
- name: `?RegisterWatcher@FSMDeviceWatcher@@UEAAJXZ`
- size: `1549`
- prototype: `__int64 __fastcall(FSMDeviceWatcher *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180002f90`
- `0x180003274`
- `0x1800056a8`
- `0x180005f98`
- `0x180006a14`
- `0x180006a68`
- `0x180006a98`
- `0x18000d024`
- `0x18000d154`
- `0x18000d4f8`
- `0x18000d594`
- `0x18000e100`
- `0x18000e2c8`
- `0x18000eedc`
- `0x1800127f0`
- `0x18001376c`
- `0x180015180`
- `0x180016d0c`
- `0x1800285c0`
- `0x1800452c4`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFCleanupVirtualCameraEntries` at `0x180015536`
- `MFSENSORGROUP!MFCleanupVirtualCameraEntries` at `0x180015536`
- `MFSENSORGROUP!MFCreateSensorGroupIdManager` at `0x180015243`
- `MFSENSORGROUP!MFCreateSensorGroupIdManager` at `0x180015243`
- `MFSENSORGROUP!MFInitializeSensorGroupStore` at `0x180015432`
- `MFSENSORGROUP!MFInitializeSensorGroupStore` at `0x180015432`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015754`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015754`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180015334`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180015334`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180015341`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180015341`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18001530a`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18001530a`
- `MFPlat!MFPutWorkItem` at `0x1800155fd`
- `MFPlat!MFPutWorkItem` at `0x18001567d`
- `MFPlat!MFPutWorkItem` at `0x1800155fd`
- `MFPlat!MFPutWorkItem` at `0x18001567d`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::RegisterWatcher(FSMDeviceWatcher *this)
{
  char *v2; // rdi
  signed int v3; // r14d
  __int64 v4; // rdx
  struct IMFSensorGroupIdManager **v5; // r13
  int Instance; // eax
  __int64 v7; // rdx
  char **unique; // rax
  __int64 v9; // rcx
  char *v10; // rdx
  signed int i; // ebx
  char *v12; // r12
  __int64 v13; // r14
  CONFIGRET v14; // eax
  signed int v15; // eax
  __int64 v16; // r14
  __int64 v17; // rcx
  struct IMFSensorGroupId *v18; // rbx
  __int64 v19; // r8
  __int64 v20; // rdx
  int updated; // eax
  const char *v22; // r8
  signed int v23; // eax
  __int64 v24; // rdx
  char *v25; // rax
  __int64 v26; // rcx
  bool v28[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+34h] [rbp-CCh] BYREF
  char *v30; // [rsp+38h] [rbp-C8h] BYREF
  struct IMFSensorGroupId *v31[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v33[25]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v31[0] = 0;
  v29 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
  v3 = *((_DWORD *)this + 26);
  if ( v3 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v4 = 18;
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v3);
    goto LABEL_79;
  }
  v5 = (struct IMFSensorGroupIdManager **)((char *)this + 88);
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((char *)this + 88);
  Instance = MFCreateSensorGroupIdManager((char *)this + 88);
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v7 = 19;
    goto LABEL_11;
  }
  unique = (char **)wil::make_unique_nothrow<FSMDeviceWatcherCMRegisterInfo [0]>(&v30);
  v2 = *unique;
  *unique = 0;
  v10 = v30;
  v30 = 0;
  if ( v10 )
    wistd::default_delete<FSMDeviceWatcherCMRegisterInfo [0]>::operator()<FSMDeviceWatcherCMRegisterInfo>(v9, v10);
  if ( *((_QWORD *)this + 21) )
  {
    v3 = -1072871856;
    if ( !g_wppLevels )
      goto LABEL_79;
    v4 = 20;
    goto LABEL_6;
  }
  for ( i = 0; (unsigned int)i < 4; ++i )
  {
    memset_0(v33, 0, sizeof(v33));
    v32[0] = 416;
    v32[1] = 0;
    v12 = &v2[16 * i];
    v33[0] = *(_OWORD *)&qword_180052950[2 * i];
    v13 = *(_QWORD *)v12;
    if ( *(_QWORD *)v12 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v30);
      CM_Unregister_Notification(v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v30);
    }
    *(_QWORD *)v12 = 0;
    v14 = CM_Register_Notification(v32, this, &FSMDeviceWatcher::PcmNotifyCallback, &v2[16 * i]);
    v15 = CM_MapCrToWin32Err(v14, 0xDu);
    v3 = v15;
    if ( v15 > 0 )
      v3 = (unsigned __int16)v15 | 0x80070000;
    if ( v3 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v3);
      goto LABEL_79;
    }
    v16 = *((_QWORD *)v12 + 1);
    *((_QWORD *)v12 + 1) = this;
    (*(void (__fastcall **)(FSMDeviceWatcher *))(*(_QWORD *)this + 8LL))(this);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    v17 = *((_QWORD *)this + 25);
    *((_QWORD *)this + 25) = 0;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    Instance = FSMConfigurationsManager::CreateInstance((struct FSMConfigurationsManager **)this + 25);
    v3 = Instance;
    if ( Instance < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_79;
      v7 = 22;
LABEL_11:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        this,
        Instance);
      goto LABEL_79;
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 25) + 24LL))(*((_QWORD *)this + 25), 1);
  }
  Instance = (*(__int64 (__fastcall **)(FSMDeviceWatcher *))(*(_QWORD *)this + 112LL))(this);
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v7 = 23;
    goto LABEL_11;
  }
  Instance = MFInitializeSensorGroupStore();
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v7 = 24;
    goto LABEL_11;
  }
  Instance = FSMDeviceWatcher::CreateSensorGroupCollectionHash((__int64 **)this, v31);
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v7 = 25;
    goto LABEL_11;
  }
  v18 = v31[0];
  Instance = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdManager *, struct IMFSensorGroupId *, int *))(*(_QWORD *)*v5 + 40LL))(
               *v5,
               v31[0],
               &v29);
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v7 = 26;
    goto LABEL_11;
  }
  if ( v29 )
  {
    if ( FSMDeviceWatcher::ValidateEnabledSensorGroups(this, *v5) )
    {
      v29 = 1;
      goto LABEL_55;
    }
    v29 = 0;
  }
  v28[0] = 0;
  Instance = FSMDeviceWatcher::InternalUpdateSensorGroups((void ***)this, v28);
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v7 = 27;
    goto LABEL_11;
  }
  if ( v28[0] )
    v18 = 0;
  (*(void (__fastcall **)(struct IMFSensorGroupIdManager *, struct IMFSensorGroupId *))(*(_QWORD *)*v5 + 48LL))(
    *v5,
    v18);
  *((_BYTE *)this + 144) = 1;
LABEL_55:
  MFCleanupVirtualCameraEntries();
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear((void ***)this + 15);
  LOBYTE(v19) = 1;
  LOBYTE(v20) = 1;
  Instance = FSMEnumDevicesByCategory(&GUID_b8238652_b500_41eb_b4f3_4234f7f5ae99, v20, v19, (char *)this + 120);
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v7 = 28;
    goto LABEL_11;
  }
  if ( *((_QWORD *)this + 17) )
  {
    v28[0] = 0;
    updated = FSMDeviceWatcher::InternalUpdateSensorGroupsForNetworkCameras((__int64 **)this, v28);
    if ( (updated < 0 || v28[0]) && byte_18005E5A5 )
    {
      v22 = "true";
      if ( !v28[0] )
        v22 = "false";
      WPP_SF_qDs(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        29,
        (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        (_DWORD)this,
        updated,
        (__int64)v22);
    }
    utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear((void ***)this + 15);
  }
  Instance = MFPutWorkItem(5u, (IMFAsyncCallback *)this + 3, 0);
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v7 = 30;
    goto LABEL_11;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 31, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
  Instance = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 184);
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v7 = 32;
    goto LABEL_11;
  }
  Instance = MFPutWorkItem(*((_DWORD *)this + 20), (IMFAsyncCallback *)this + 2, 0);
  v3 = Instance;
  if ( Instance < 0 && g_wppLevels )
  {
    v7 = 33;
    goto LABEL_11;
  }
LABEL_79:
  v23 = v3;
  if ( *((_DWORD *)this + 26) )
    v23 = *((_DWORD *)this + 26);
  *((_DWORD *)this + 26) = v23;
  if ( v3 >= 0 )
  {
    v25 = (char *)*((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = v2;
    v2 = v25;
    if ( (unsigned __int8)byte_18005E5A5 < 8u )
      goto LABEL_89;
    v24 = 35;
    goto LABEL_88;
  }
  if ( *((_QWORD *)this + 23) )
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 184,
      0);
  if ( byte_18005E5A5 )
  {
    v24 = 34;
LABEL_88:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v24, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v3);
  }
LABEL_89:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)v31);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( v2 )
    wistd::default_delete<FSMDeviceWatcherCMRegisterInfo [0]>::operator()<FSMDeviceWatcherCMRegisterInfo>(v26, v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180015180  push    rbp
0x180015182  push    rbx
0x180015183  push    rsi
0x180015184  push    rdi
0x180015185  push    r12
0x180015187  push    r13
0x180015189  push    r14
0x18001518b  push    r15
0x18001518d  lea     rbp, [rsp-108h]
0x180015195  sub     rsp, 208h
0x18001519c  mov     rax, cs:__security_cookie
0x1800151a3  xor     rax, rsp
0x1800151a6  mov     [rbp+140h+var_50], rax
0x1800151ad  mov     r15, rcx
0x1800151b0  xor     r12d, r12d
0x1800151b3  add     rcx, 28h ; '('; lpCriticalSection
0x1800151b7  mov     edi, r12d
0x1800151ba  call    cs:__imp_EnterCriticalSection
0x1800151c0  mov     [rsp+240h+var_200], r12
0x1800151c5  mov     [rsp+240h+var_20C], r12d
0x1800151ca  cmp     cs:byte_18005E5A5, 8
0x1800151d1  jb      short loc_1800151F5
0x1800151d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151da  lea     edx, [r12+11h]
0x1800151df  mov     r9, r15
0x1800151e2  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800151e9  mov     rcx, [rcx+0D8h]
0x1800151f0  call    WPP_SF_q
0x1800151f5  mov     r14d, [r15+68h]
0x1800151f9  test    r14d, r14d
0x1800151fc  jns     short loc_180015234
0x1800151fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015205  jb      loc_1800156CD
0x18001520b  mov     edx, 12h
0x180015210  mov     [rsp+240h+var_220], r14d
0x180015215  mov     rcx, cs:WPP_GLOBAL_Control
0x18001521c  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180015223  mov     r9, r15
0x180015226  mov     rcx, [rcx+10h]
0x18001522a  call    WPP_SF_qD
0x18001522f  jmp     loc_1800156CD
0x180015234  lea     r13, [r15+58h]
0x180015238  mov     rcx, r13
0x18001523b  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180015240  mov     rcx, r13
0x180015243  call    cs:__imp_MFCreateSensorGroupIdManager
0x180015249  mov     r14d, eax
0x18001524c  test    eax, eax
0x18001524e  jns     short loc_180015268
0x180015250  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015257  jb      loc_1800156CD
0x18001525d  mov     edx, 13h
0x180015262  mov     [rsp+240h+var_220], eax
0x180015266  jmp     short loc_180015215
0x180015268  lea     rcx, [rsp+240h+var_208]
0x18001526d  call    ??$make_unique_nothrow@$$BY0A@UFSMDeviceWatcherCMRegisterInfo@@@wil@@YA?AV?$unique_ptr@$$BY0A@UFSMDeviceWatcherCMRegisterInfo@@U?$default_delete@$$BY0A@UFSMDeviceWatcherCMRegisterInfo@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<FSMDeviceWatcherCMRegisterInfo [0]>(unsigned __int64)
0x180015272  mov     rdi, [rax]
0x180015275  mov     [rax], r12
0x180015278  mov     rdx, [rsp+240h+var_208]
0x18001527d  mov     [rsp+240h+var_208], r12
0x180015282  test    rdx, rdx
0x180015285  jz      short loc_18001528C
0x180015287  call    ??$?RUFSMDeviceWatcherCMRegisterInfo@@@?$default_delete@$$BY0A@UFSMDeviceWatcherCMRegisterInfo@@@wistd@@QEBAXPEAUFSMDeviceWatcherCMRegisterInfo@@@Z; wistd::default_delete<FSMDeviceWatcherCMRegisterInfo [0]>::operator()<FSMDeviceWatcherCMRegisterInfo>(FSMDeviceWatcherCMRegisterInfo *)
0x18001528c  cmp     [r15+0A8h], r12
0x180015293  jz      short loc_1800152B2
0x180015295  mov     r14d, 0C00D4650h
0x18001529b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800152a2  jb      loc_1800156CD
0x1800152a8  mov     edx, 14h
0x1800152ad  jmp     loc_180015210
0x1800152b2  mov     ebx, r12d
0x1800152b5  xor     edx, edx; Val
0x1800152b7  lea     rcx, [rsp+240h+var_1E0]; void *
0x1800152bc  mov     r8d, 190h; Size
0x1800152c2  call    memset_0
0x1800152c7  movsxd  rax, ebx
0x1800152ca  lea     rcx, qword_180052950
0x1800152d1  add     rax, rax
0x1800152d4  mov     [rsp+240h+var_1F0], 1A0h
0x1800152dd  mov     [rsp+240h+var_1E8], 0
0x1800152e6  movups  xmm0, xmmword ptr [rcx+rax*8]
0x1800152ea  lea     r12, [rdi+rax*8]
0x1800152ee  movdqu  [rsp+240h+var_1E0], xmm0
0x1800152f4  mov     r14, [r12]
0x1800152f8  test    r14, r14
0x1800152fb  jz      short loc_18001531A
0x1800152fd  lea     rcx, [rsp+240h+var_208]; this
0x180015302  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015307  mov     rcx, r14
0x18001530a  call    cs:__imp_CM_Unregister_Notification
0x180015310  lea     rcx, [rsp+240h+var_208]; this
0x180015315  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001531a  mov     r9, r12
0x18001531d  mov     qword ptr [r12], 0
0x180015325  lea     r8, ?PcmNotifyCallback@FSMDeviceWatcher@@KAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; FSMDeviceWatcher::PcmNotifyCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18001532c  mov     rdx, r15
0x18001532f  lea     rcx, [rsp+240h+var_1F0]
0x180015334  call    cs:__imp_CM_Register_Notification
0x18001533a  mov     ecx, eax; CmReturnCode
0x18001533c  mov     edx, 0Dh; DefaultErr
0x180015341  call    cs:__imp_CM_MapCrToWin32Err
0x180015347  mov     r14d, eax
0x18001534a  test    eax, eax
0x18001534c  jle     short loc_180015359
0x18001534e  movzx   r14d, ax
0x180015352  or      r14d, 80070000h
0x180015359  test    r14d, r14d
0x18001535c  js      loc_18001569D
0x180015362  mov     r14, [r12+8]
0x180015367  mov     rcx, r15
0x18001536a  mov     [r12+8], r15
0x18001536f  mov     rax, [r15]
0x180015372  mov     rax, [rax+8]
0x180015376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001537b  xor     r12d, r12d
0x18001537e  test    r14, r14
0x180015381  jz      short loc_180015392
0x180015383  mov     rax, [r14]
0x180015386  mov     rcx, r14
0x180015389  mov     rax, [rax+10h]
0x18001538d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015392  inc     ebx
0x180015394  cmp     ebx, 4
0x180015397  jb      loc_1800152B5
0x18001539d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x1800153a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x1800153a9  test    al, al
0x1800153ab  jz      short loc_180015405
0x1800153ad  lea     rbx, [r15+0C8h]
0x1800153b4  mov     rcx, [rbx]
0x1800153b7  mov     [rbx], r12
0x1800153ba  test    rcx, rcx
0x1800153bd  jz      short loc_1800153CB
0x1800153bf  mov     rax, [rcx]
0x1800153c2  mov     rax, [rax+10h]
0x1800153c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153cb  mov     rcx, rbx; struct FSMConfigurationsManager **
0x1800153ce  call    ?CreateInstance@FSMConfigurationsManager@@SAJPEAPEAV1@@Z; FSMConfigurationsManager::CreateInstance(FSMConfigurationsManager * *)
0x1800153d3  mov     r14d, eax
0x1800153d6  test    eax, eax
0x1800153d8  jns     short loc_1800153F1
0x1800153da  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800153e1  jb      loc_1800156CD
0x1800153e7  mov     edx, 16h
0x1800153ec  jmp     loc_180015262
0x1800153f1  mov     rcx, [rbx]
0x1800153f4  mov     edx, 1
0x1800153f9  mov     rax, [rcx]
0x1800153fc  mov     rax, [rax+18h]
0x180015400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015405  mov     rax, [r15]
0x180015408  mov     rcx, r15
0x18001540b  mov     rax, [rax+70h]
0x18001540f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015414  mov     r14d, eax
0x180015417  test    eax, eax
0x180015419  jns     short loc_180015432
0x18001541b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015422  jb      loc_1800156CD
0x180015428  mov     edx, 17h
0x18001542d  jmp     loc_180015262
0x180015432  call    cs:__imp_MFInitializeSensorGroupStore
0x180015438  mov     r14d, eax
0x18001543b  test    eax, eax
0x18001543d  jns     short loc_180015456
0x18001543f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015446  jb      loc_1800156CD
0x18001544c  mov     edx, 18h
0x180015451  jmp     loc_180015262
0x180015456  lea     rdx, [rsp+240h+var_200]; struct IMFSensorGroupId **
0x18001545b  mov     rcx, r15; this
0x18001545e  call    ?CreateSensorGroupCollectionHash@FSMDeviceWatcher@@IEAAJPEAPEAUIMFSensorGroupId@@@Z; FSMDeviceWatcher::CreateSensorGroupCollectionHash(IMFSensorGroupId * *)
0x180015463  mov     r14d, eax
0x180015466  test    eax, eax
0x180015468  jns     short loc_180015481
0x18001546a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015471  jb      loc_1800156CD
0x180015477  mov     edx, 19h
0x18001547c  jmp     loc_180015262
0x180015481  mov     rcx, [r13+0]
0x180015485  lea     r8, [rsp+240h+var_20C]
0x18001548a  mov     rbx, [rsp+240h+var_200]
0x18001548f  mov     rdx, rbx
0x180015492  mov     rax, [rcx]
0x180015495  mov     rax, [rax+28h]
0x180015499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001549e  mov     r14d, eax
0x1800154a1  test    eax, eax
0x1800154a3  jns     short loc_1800154BC
0x1800154a5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800154ac  jb      loc_1800156CD
0x1800154b2  mov     edx, 1Ah
0x1800154b7  jmp     loc_180015262
0x1800154bc  cmp     [rsp+240h+var_20C], r12d
0x1800154c1  jz      short loc_1800154E2
0x1800154c3  mov     rdx, [r13+0]; struct IMFSensorGroupIdManager *
0x1800154c7  mov     rcx, r15; this
0x1800154ca  call    ?ValidateEnabledSensorGroups@FSMDeviceWatcher@@IEAA_NPEAUIMFSensorGroupIdManager@@@Z; FSMDeviceWatcher::ValidateEnabledSensorGroups(IMFSensorGroupIdManager *)
0x1800154cf  test    al, al
0x1800154d1  jz      short loc_1800154DD
0x1800154d3  mov     [rsp+240h+var_20C], 1
0x1800154db  jmp     short loc_180015536
0x1800154dd  mov     [rsp+240h+var_20C], r12d
0x1800154e2  lea     rdx, [rsp+240h+var_210]; bool *
0x1800154e7  mov     [rsp+240h+var_210], r12b
0x1800154ec  mov     rcx, r15; this
0x1800154ef  call    ?InternalUpdateSensorGroups@FSMDeviceWatcher@@IEAAJPEA_N@Z; FSMDeviceWatcher::InternalUpdateSensorGroups(bool *)
0x1800154f4  mov     r14d, eax
0x1800154f7  test    eax, eax
0x1800154f9  jns     short loc_180015512
0x1800154fb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015502  jb      loc_1800156CD
0x180015508  mov     edx, 1Bh
0x18001550d  jmp     loc_180015262
0x180015512  mov     rcx, [r13+0]
0x180015516  cmp     [rsp+240h+var_210], r12b
0x18001551b  cmovnz  rbx, r12
0x18001551f  mov     rax, [rcx]
0x180015522  mov     rdx, rbx
0x180015525  mov     rax, [rax+30h]
0x180015529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001552e  mov     byte ptr [r15+90h], 1
0x180015536  call    cs:__imp_MFCleanupVirtualCameraEntries
0x18001553c  lea     rbx, [r15+78h]
0x180015540  mov     rcx, rbx
0x180015543  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x180015548  mov     r8b, 1
0x18001554b  lea     rcx, _GUID_b8238652_b500_41eb_b4f3_4234f7f5ae99
0x180015552  mov     dl, r8b
0x180015555  mov     r9, rbx
0x180015558  call    FSMEnumDevicesByCategory
0x18001555d  mov     r14d, eax
0x180015560  test    eax, eax
0x180015562  jns     short loc_18001557B
0x180015564  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001556b  jb      loc_1800156CD
0x180015571  mov     edx, 1Ch
0x180015576  jmp     loc_180015262
0x18001557b  cmp     [r15+88h], r12
0x180015582  jbe     short loc_1800155F2
0x180015584  lea     rdx, [rsp+240h+var_210]; bool *
0x180015589  mov     [rsp+240h+var_210], r12b
0x18001558e  mov     rcx, r15; this
0x180015591  call    ?InternalUpdateSensorGroupsForNetworkCameras@FSMDeviceWatcher@@IEAAJPEA_N@Z; FSMDeviceWatcher::InternalUpdateSensorGroupsForNetworkCameras(bool *)
0x180015596  mov     cl, [rsp+240h+var_210]
0x18001559a  test    eax, eax
0x18001559c  js      short loc_1800155A2
0x18001559e  test    cl, cl
0x1800155a0  jz      short loc_1800155EA
0x1800155a2  cmp     cs:byte_18005E5A5, 1
0x1800155a9  jb      short loc_1800155EA
0x1800155ab  test    cl, cl
0x1800155ad  lea     rdx, aFalse; "false"
0x1800155b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155bb  lea     r8, aTrue_0; "true"
0x1800155c2  cmovz   r8, rdx
0x1800155c6  mov     r9, r15
0x1800155c9  mov     [rsp+240h+var_218], r8
0x1800155ce  mov     edx, 1Dh
0x1800155d3  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800155da  mov     [rsp+240h+var_220], eax
0x1800155de  mov     rcx, [rcx+0D8h]
0x1800155e5  call    WPP_SF_qDs
0x1800155ea  mov     rcx, rbx
0x1800155ed  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x1800155f2  xor     r8d, r8d; pState
0x1800155f5  lea     rdx, [r15+18h]; pCallback
0x1800155f9  lea     ecx, [r8+5]; dwQueue
0x1800155fd  call    cs:__imp_MFPutWorkItem
0x180015603  mov     r14d, eax
0x180015606  test    eax, eax
0x180015608  jns     short loc_180015621
0x18001560a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015611  jb      loc_1800156CD
0x180015617  mov     edx, 1Eh
0x18001561c  jmp     loc_180015262
0x180015621  cmp     cs:byte_18005E5A5, 8
0x180015628  jb      short loc_18001564C
0x18001562a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015631  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180015638  mov     edx, 1Fh
0x18001563d  mov     r9, r15
0x180015640  mov     rcx, [rcx+0D8h]
0x180015647  call    WPP_SF_q
0x18001564c  lea     rcx, [r15+0B8h]
0x180015653  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180015658  mov     r14d, eax
0x18001565b  test    eax, eax
0x18001565d  jns     short loc_180015672
0x18001565f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015666  jb      short loc_1800156CD
0x180015668  mov     edx, 20h ; ' '
0x18001566d  jmp     loc_180015262
0x180015672  mov     ecx, [r15+50h]; dwQueue
0x180015676  lea     rdx, [r15+10h]; pCallback
0x18001567a  xor     r8d, r8d; pState
0x18001567d  call    cs:__imp_MFPutWorkItem
0x180015683  mov     r14d, eax
0x180015686  test    eax, eax
0x180015688  jns     short loc_1800156CD
  ... truncated ...
```
