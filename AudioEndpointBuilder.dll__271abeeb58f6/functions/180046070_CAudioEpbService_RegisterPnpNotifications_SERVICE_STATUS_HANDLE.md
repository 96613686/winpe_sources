# CAudioEpbService::RegisterPnpNotifications(SERVICE_STATUS_HANDLE__ *)

- ea: `0x180046070`
- end: `0x1800469f1`
- name: `?RegisterPnpNotifications@CAudioEpbService@@UEAAJPEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `2433`
- prototype: `int(CAudioEpbService *__hidden this, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18002658c`
- `0x18003512c`
- `0x18003514c`
- `0x18003e920`
- `0x18003f7a4`
- `0x180046070`
- `0x1800475f8`
- `0x180047784`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18004645c`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180046721`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x1800469bd`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18004645c`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180046721`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x1800469bd`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800462ed`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180046412`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800466d1`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180046970`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800462ed`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180046412`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800466d1`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180046970`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1800460f6`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18004612f`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180046761`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1800460f6`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18004612f`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180046761`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18004679d`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18004679d`

## string_xrefs

- `0x180046783`: `Endpoint Plugin Register Notification`

## pseudocode

```c
__int64 __fastcall CAudioEpbService::RegisterPnpNotifications(
        CAudioEpbService *this,
        struct SERVICE_STATUS_HANDLE__ *a2)
{
  signed int ObjectQuery; // ebx
  _QWORD *v5; // rbx
  __int64 v6; // rsi
  _BYTE *v7; // r9
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // r9
  const wchar_t *v13; // r8
  __int64 *v14; // rdi
  __int64 v15; // rbx
  int v17; // [rsp+20h] [rbp-E0h]
  _BYTE *v18; // [rsp+28h] [rbp-D8h]
  char *v19; // [rsp+40h] [rbp-C0h]
  char v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[7]; // [rsp+51h] [rbp-AFh] BYREF
  _BYTE v22[8]; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+68h] [rbp-98h]
  GUID v25; // [rsp+70h] [rbp-90h]
  _DWORD v26[4]; // [rsp+200h] [rbp+100h] BYREF
  GUID v27; // [rsp+210h] [rbp+110h]
  _BYTE v28[24]; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 pid; // [rsp+3B8h] [rbp+2B8h]
  DEVPROPGUID v30; // [rsp+3C0h] [rbp+2C0h]
  GUID *v31; // [rsp+3D0h] [rbp+2D0h]
  __int64 v32; // [rsp+3D8h] [rbp+2D8h]
  DEVPROPKEY v33; // [rsp+3E0h] [rbp+2E0h]
  int v34; // [rsp+3F4h] [rbp+2F4h]
  __int64 v35; // [rsp+3F8h] [rbp+2F8h]
  DEVPROPKEY v36; // [rsp+400h] [rbp+300h]
  int v37; // [rsp+414h] [rbp+314h]
  _BYTE v38[24]; // [rsp+418h] [rbp+318h]
  __int64 v39; // [rsp+430h] [rbp+330h]
  __int64 v40; // [rsp+438h] [rbp+338h]
  DEVPROPKEY v41; // [rsp+440h] [rbp+340h]
  int v42; // [rsp+454h] [rbp+354h]
  __int64 v43; // [rsp+458h] [rbp+358h]
  _BYTE v44[24]; // [rsp+460h] [rbp+360h] BYREF
  __int64 v45; // [rsp+478h] [rbp+378h]
  DEVPROPGUID fmtid; // [rsp+480h] [rbp+380h]
  GUID *v47; // [rsp+490h] [rbp+390h]
  __int64 v48; // [rsp+498h] [rbp+398h]
  DEVPROPKEY v49; // [rsp+4A0h] [rbp+3A0h]
  int v50; // [rsp+4B4h] [rbp+3B4h]
  __int64 v51; // [rsp+4B8h] [rbp+3B8h]
  int v52; // [rsp+4C0h] [rbp+3C0h] BYREF
  DEVPROPKEY v53; // [rsp+4C8h] [rbp+3C8h]
  int v54; // [rsp+4DCh] [rbp+3DCh]
  __int64 v55; // [rsp+4E0h] [rbp+3E0h]
  int v56; // [rsp+4E8h] [rbp+3E8h]
  int v57; // [rsp+4ECh] [rbp+3ECh]
  GUID *v58; // [rsp+4F0h] [rbp+3F0h]
  int v59; // [rsp+4F8h] [rbp+3F8h]
  DEVPROPKEY v60; // [rsp+500h] [rbp+400h]
  int v61; // [rsp+514h] [rbp+414h]
  __int64 v62; // [rsp+518h] [rbp+418h]
  int v63; // [rsp+520h] [rbp+420h]
  int v64; // [rsp+524h] [rbp+424h]
  const wchar_t *v65; // [rsp+528h] [rbp+428h]
  int v66; // [rsp+530h] [rbp+430h]
  DEVPROPKEY v67; // [rsp+538h] [rbp+438h]
  int v68; // [rsp+54Ch] [rbp+44Ch]
  __int64 v69; // [rsp+550h] [rbp+450h]
  int v70; // [rsp+558h] [rbp+458h]
  int v71; // [rsp+55Ch] [rbp+45Ch]
  char *v72; // [rsp+560h] [rbp+460h]
  int v73; // [rsp+568h] [rbp+468h]
  DEVPROPKEY v74; // [rsp+570h] [rbp+470h]
  int v75; // [rsp+584h] [rbp+484h]
  __int64 v76; // [rsp+588h] [rbp+488h]
  int v77; // [rsp+590h] [rbp+490h]
  int v78; // [rsp+594h] [rbp+494h]
  char *v79; // [rsp+598h] [rbp+498h]
  int v80; // [rsp+5A0h] [rbp+4A0h]
  DEVPROPKEY v81; // [rsp+5A8h] [rbp+4A8h]
  int v82; // [rsp+5BCh] [rbp+4BCh]
  __int64 v83; // [rsp+5C0h] [rbp+4C0h]
  __int64 v84; // [rsp+5C8h] [rbp+4C8h]
  __int64 v85; // [rsp+5D0h] [rbp+4D0h]

  memset_0(&v23, 0, 0x1A0u);
  memset_0(v26, 0, 0x1A0u);
  v23 = 416;
  v24 = 0;
  v25 = GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196;
  if ( (unsigned int)CM_Register_Notification(&v23, 0, ServiceDeviceEventCallback, (char *)this + 8) )
  {
    ObjectQuery = -2147467259;
  }
  else
  {
    v23 = 416;
    v24 = 0;
    v25 = GUID_03b80e5a_ede8_4b33_a751_6ce34ec4c700;
    ObjectQuery = (unsigned int)CM_Register_Notification(&v23, 0, ServiceDeviceEventCallback, (char *)this + 24) != 0
                ? 0x80004005
                : 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AudioEndpointBuilderAPOInstallInProgress>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_AudioEndpointBuilderAPOInstallInProgress>::GetImpl'::`2'::impl) )
  {
    if ( ObjectQuery >= 0 )
    {
      v5 = (_QWORD *)((char *)this + 72);
      pid = DEVPKEY_Device_ClassGuid.pid;
      v31 = &GUID_5989fce8_9cd0_467d_8a6a_5419e31529d4;
      v33 = DEVPKEY_Device_IsRebootRequired;
      *(DEVPROPGUID *)&v28[8] = DEVPKEY_Device_ClassGuid.fmtid;
      *(_QWORD *)v36.fmtid.Data4 = &v20;
      *(_DWORD *)&v38[16] = 9;
      *(_QWORD *)&v41.fmtid.Data1 = v21;
      *(_OWORD *)v38 = DEVPKEY_Device_InstallInProgress;
      *(_DWORD *)&v44[16] = 10;
      *(_DWORD *)v28 = 2;
      *(_OWORD *)v44 = DEVPKEY_Device_LastKnownParent;
      LODWORD(v32) = 2;
      v6 = *((_QWORD *)this + 9);
      fmtid = DEVPKEY_Device_DevNodeStatus.fmtid;
      v47 = (GUID *)DEVPKEY_Device_DevNodeStatus.pid;
      v20 = 0;
      v21[0] = -1;
      *(_QWORD *)&v30.Data1 = 0;
      *(_QWORD *)v30.Data4 = 0x100000000DLL;
      v34 = 0;
      v35 = 0;
      *(_QWORD *)&v36.fmtid.Data1 = 0x100000011LL;
      v36.pid = 65538;
      *(_DWORD *)&v38[20] = 0;
      v39 = 0;
      v40 = 0x100000011LL;
      *(_DWORD *)&v44[20] = 0;
      v45 = 0;
      v48 = 0;
      v49 = DEVPKEY_Device_InstallDate;
      v50 = 0;
      v51 = 0;
      if ( v6 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v22);
        DevCloseObjectQuery(v6);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
      }
      v19 = (char *)this + 72;
      v7 = v44;
      v18 = v28;
      v17 = 3;
LABEL_13:
      *v5 = 0;
      ObjectQuery = DevCreateObjectQuery(3, 1, 3, v7, v17, v18, DevQueryCallback, 0, v19);
    }
  }
  else if ( ObjectQuery >= 0 )
  {
    v5 = (_QWORD *)((char *)this + 72);
    v45 = DEVPKEY_Device_ClassGuid.pid;
    *(DEVPROPGUID *)&v44[8] = DEVPKEY_Device_ClassGuid.fmtid;
    v47 = &GUID_5989fce8_9cd0_467d_8a6a_5419e31529d4;
    *(_DWORD *)&v28[16] = 10;
    *(_OWORD *)v28 = DEVPKEY_Device_LastKnownParent;
    *(_DWORD *)v44 = 2;
    v8 = *((_QWORD *)this + 9);
    v30 = DEVPKEY_Device_DevNodeStatus.fmtid;
    v31 = (GUID *)DEVPKEY_Device_DevNodeStatus.pid;
    *(_QWORD *)&fmtid.Data1 = 0;
    *(_QWORD *)fmtid.Data4 = 0x100000000DLL;
    *(_DWORD *)&v28[20] = 0;
    pid = 0;
    v32 = 0;
    v33 = DEVPKEY_Device_InstallDate;
    v34 = 0;
    v35 = 0;
    if ( v8 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v22);
      DevCloseObjectQuery(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
    }
    v19 = (char *)this + 72;
    v7 = v28;
    v18 = v44;
    v17 = 1;
    goto LABEL_13;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl'::`2'::impl)
    || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl'::`2'::impl) )
  {
    v53 = DEVPKEY_Device_ClassGuid;
    v58 = &GUID_DEVCLASS_MEDIA;
    v65 = L"USB\\Class_01";
    v67 = DEVPKEY_Device_IsPresent;
    v72 = v21;
    v74 = DEVPKEY_Device_IsRebootRequired;
    v79 = &v20;
    *(DEVPROPKEY *)v28 = DEVPKEY_Device_DevNodeStatus;
    v31 = (GUID *)DEVPKEY_Device_InstallDate.pid;
    v30 = DEVPKEY_Device_InstallDate.fmtid;
    v36 = DEVPKEY_Device_DriverInfPath;
    v39 = DEVPKEY_Device_InstanceId.pid;
    *(DEVPROPGUID *)&v38[8] = DEVPKEY_Device_InstanceId.fmtid;
    v20 = 0;
    v21[0] = -1;
    v41 = PKEY_DriverSwitchedByAEB;
    v52 = 2;
    v54 = 0;
    v55 = 0;
    v56 = 13;
    v57 = 16;
    v59 = 135168;
    v60 = DEVPKEY_Device_CompatibleIds;
    v61 = 0;
    v62 = 0;
    v63 = 18;
    v64 = 26;
    v66 = 2;
    v68 = 0;
    v69 = 0;
    v70 = 17;
    v71 = 1;
    v73 = 2;
    v75 = 0;
    v76 = 0;
    v77 = 17;
    v78 = 1;
    *(_DWORD *)&v28[20] = 0;
    pid = 0;
    v32 = 0;
    v33 = DEVPKEY_Device_CompatibleIds;
    v34 = 0;
    v35 = 0;
    v37 = 0;
    *(_QWORD *)v38 = 0;
    v40 = 0;
    v42 = 0;
    v43 = 0;
    v11 = *((_QWORD *)this + 13);
    if ( v11 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v22);
      DevCloseObjectQuery(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
    }
    *((_QWORD *)this + 13) = 0;
    ObjectQuery = DevCreateObjectQuery(3, 1, 6, v28, 4, &v52, MidiDriverDevQueryCallback, 0, (char *)this + 104);
  }
  if ( ObjectQuery < 0 )
  {
    if ( (Microsoft_Windows_AudioEnableBits & 4) == 0 )
      goto LABEL_27;
    v12 = (unsigned int)ObjectQuery;
    v13 = L"KS Endpoint Register Notification";
  }
  else
  {
    v26[0] = 416;
    v26[2] = 0;
    v27 = GUID_9f2f7b66_65ac_4fa6_8ae4_123c78b89313;
    if ( !(unsigned int)CM_Register_Notification(v26, 0, ServiceDeviceEventCallback, (char *)this + 16) )
    {
      ObjectQuery = PowerSettingRegisterNotification(&GUID_SYSTEM_AWAYMODE, 1u, a2, (PHPOWERNOTIFY)this + 5);
      goto LABEL_27;
    }
    ObjectQuery = -2147467259;
    if ( (Microsoft_Windows_AudioEnableBits & 4) == 0 )
      return (unsigned int)ObjectQuery;
    v12 = 2147500037LL;
    v13 = L"Endpoint Plugin Register Notification";
  }
  McTemplateU0zq_EtwEventWriteTransfer(v10, v9, v13, v12);
LABEL_27:
  if ( ObjectQuery >= 0 )
  {
    v53 = DEVPKEY_Device_ClassGuid;
    v14 = (__int64 *)((char *)this + 80);
    v21[0] = -1;
    v15 = *v14;
    v58 = &GUID_DEVCLASS_MEDIA;
    v60 = DEVPKEY_Device_IsPresent;
    v65 = (const wchar_t *)v21;
    v67 = DEVPKEY_Device_IsRebootRequired;
    v72 = &v20;
    v74.pid = 9;
    v79 = &v20;
    v20 = 0;
    v52 = 2;
    v54 = 0;
    v55 = 0;
    v56 = 13;
    v57 = 16;
    v59 = 2;
    v61 = 0;
    v62 = 0;
    v63 = 17;
    v64 = 1;
    v66 = 2;
    v68 = 0;
    v69 = 0;
    v70 = 17;
    v71 = 1;
    v73 = 2;
    v75 = 0;
    v76 = 0;
    v77 = 17;
    v78 = 1;
    v80 = 1;
    v81 = DEVPKEY_Device_InstallDate;
    v82 = 0;
    v83 = 0;
    v84 = 16;
    v85 = 0;
    *(DEVPROPKEY *)v44 = DEVPKEY_Device_InstallDate;
    *(_DWORD *)&v44[20] = 0;
    v45 = 0;
    v74.fmtid = (DEVPROPGUID)DEVPKEY_Device_InstallInProgress;
    if ( v15 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v22);
      DevCloseObjectQuery(v15);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
    }
    *v14 = 0;
    return (unsigned int)DevCreateObjectQuery(3, 1, 1, v44, 5, &v52, DevQueryInstallDateCallback, 0, v14);
  }
  return (unsigned int)ObjectQuery;
}

```

## disassembly

```asm
0x180046070  mov     [rsp-8+arg_10], rbx
0x180046075  push    rbp
0x180046076  push    rsi
0x180046077  push    rdi
0x180046078  push    r12
0x18004607a  push    r13
0x18004607c  push    r14
0x18004607e  push    r15
0x180046080  lea     rbp, [rsp-4F0h]
0x180046088  sub     rsp, 5F0h
0x18004608f  mov     rax, cs:__security_cookie
0x180046096  xor     rax, rsp
0x180046099  mov     [rbp+520h+var_40], rax
0x1800460a0  mov     r14, rdx
0x1800460a3  mov     rdi, rcx
0x1800460a6  mov     ebx, 1A0h
0x1800460ab  lea     rcx, [rsp+620h+var_5C0]; void *
0x1800460b0  mov     r8d, ebx; Size
0x1800460b3  xor     edx, edx; Val
0x1800460b5  call    memset_0
0x1800460ba  mov     r8d, ebx; Size
0x1800460bd  lea     rcx, [rbp+520h+var_420]; void *
0x1800460c4  xor     edx, edx; Val
0x1800460c6  call    memset_0
0x1800460cb  movups  xmm0, xmmword ptr cs:_GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196.Data1
0x1800460d2  xor     r15d, r15d
0x1800460d5  mov     [rsp+620h+var_5C0], ebx
0x1800460d9  lea     r9, [rdi+8]
0x1800460dd  mov     [rsp+620h+var_5B8], r15d
0x1800460e2  lea     r8, ServiceDeviceEventCallback
0x1800460e9  xor     edx, edx
0x1800460eb  lea     rcx, [rsp+620h+var_5C0]
0x1800460f0  movdqu  [rsp+620h+var_5B0], xmm0
0x1800460f6  call    cs:__imp_CM_Register_Notification
0x1800460fc  test    eax, eax
0x1800460fe  jz      short loc_180046107
0x180046100  mov     ebx, 80004005h
0x180046105  jmp     short loc_180046144
0x180046107  movups  xmm0, xmmword ptr cs:_GUID_03b80e5a_ede8_4b33_a751_6ce34ec4c700.Data1
0x18004610e  lea     r9, [rdi+18h]
0x180046112  mov     [rsp+620h+var_5C0], ebx
0x180046116  lea     r8, ServiceDeviceEventCallback
0x18004611d  mov     [rsp+620h+var_5B8], r15d
0x180046122  xor     edx, edx
0x180046124  lea     rcx, [rsp+620h+var_5C0]
0x180046129  movdqu  [rsp+620h+var_5B0], xmm0
0x18004612f  call    cs:__imp_CM_Register_Notification
0x180046135  mov     ecx, r15d
0x180046138  sub     ecx, eax
0x18004613a  neg     ecx
0x18004613c  sbb     ebx, ebx
0x18004613e  and     ebx, 80004005h
0x180046144  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AudioEndpointBuilderAPOInstallInProgress@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AudioEndpointBuilderAPOInstallInProgress@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AudioEndpointBuilderAPOInstallInProgress> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AudioEndpointBuilderAPOInstallInProgress>::GetImpl(void)'::`2'::impl
0x18004614b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AudioEndpointBuilderAPOInstallInProgress@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AudioEndpointBuilderAPOInstallInProgress>::__private_IsEnabled(void)
0x180046150  mov     esi, 2
0x180046155  lea     edx, [rsi+0Eh]
0x180046158  lea     ecx, [rsi+0Fh]
0x18004615b  lea     r8d, [rsi+0Bh]
0x18004615f  lea     r12d, [rsi-1]
0x180046163  lea     r13d, [rsi+1]
0x180046167  test    al, al
0x180046169  jz      loc_180046330
0x18004616f  test    ebx, ebx
0x180046171  js      loc_180046469
0x180046177  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ClassGuid.fmtid.Data1
0x18004617e  mov     eax, cs:DEVPKEY_Device_ClassGuid.pid
0x180046184  lea     rbx, [rdi+48h]
0x180046188  mov     dword ptr [rbp+520h+var_268], eax
0x18004618e  lea     rax, _GUID_5989fce8_9cd0_467d_8a6a_5419e31529d4
0x180046195  mov     [rbp+520h+var_250], rax
0x18004619c  mov     eax, cs:DEVPKEY_Device_IsRebootRequired.pid
0x1800461a2  mov     [rbp+520h+var_230], eax
0x1800461a8  lea     rax, [rsp+620h+var_5D0]
0x1800461ad  movups  [rbp+520h+var_280+8], xmm0
0x1800461b4  mov     qword ptr [rbp+520h+var_220+8], rax
0x1800461bb  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_IsRebootRequired.fmtid.Data1
0x1800461c2  mov     eax, cs:dword_18006FC80
0x1800461c8  mov     [rbp+520h+var_1F8], eax
0x1800461ce  lea     rax, [rsp+620h+var_5CF]
0x1800461d3  movaps  [rbp+520h+var_240], xmm0
0x1800461da  movups  xmm0, cs:DEVPKEY_Device_InstallInProgress
0x1800461e1  mov     qword ptr [rbp+520h+var_1E0], rax
0x1800461e8  mov     eax, cs:dword_18006FC68
0x1800461ee  movups  [rbp+520h+var_208], xmm0
0x1800461f5  mov     [rbp+520h+var_1B0], eax
0x1800461fb  movups  xmm0, cs:DEVPKEY_Device_LastKnownParent
0x180046202  mov     eax, cs:DEVPKEY_Device_DevNodeStatus.pid
0x180046208  mov     dword ptr [rbp+520h+var_280], esi
0x18004620e  movaps  [rbp+520h+var_1C0], xmm0
0x180046215  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DevNodeStatus.fmtid.Data1
0x18004621c  mov     dword ptr [rbp+520h+var_248], esi
0x180046222  mov     rsi, [rbx]
0x180046225  movaps  [rbp+520h+var_1A0], xmm0
0x18004622c  mov     dword ptr [rbp+520h+var_190], eax
0x180046232  mov     eax, cs:DEVPKEY_Device_InstallDate.pid
0x180046238  mov     [rsp+620h+var_5D0], r15b
0x18004623d  mov     [rsp+620h+var_5CF], 0FFh
0x180046242  mov     dword ptr [rbp+520h+var_268+4], r15d
0x180046249  mov     qword ptr [rbp+520h+var_260], r15
0x180046250  mov     dword ptr [rbp+520h+var_260+8], r8d
0x180046257  mov     dword ptr [rbp+520h+var_260+0Ch], edx
0x18004625d  mov     [rbp+520h+var_22C], r15d
0x180046264  mov     [rbp+520h+var_228], r15
0x18004626b  mov     dword ptr [rbp+520h+var_220], ecx
0x180046271  mov     dword ptr [rbp+520h+var_220+4], r12d
0x180046278  mov     [rbp+520h+var_210], 10002h
0x180046282  mov     [rbp+520h+var_1F4], r15d
0x180046289  mov     [rbp+520h+var_1F0], r15
0x180046290  mov     dword ptr [rbp+520h+var_1E8], ecx
0x180046296  mov     dword ptr [rbp+520h+var_1E8+4], r12d
0x18004629d  mov     [rbp+520h+var_1AC], r15d
0x1800462a4  mov     [rbp+520h+var_1A8], r15
0x1800462ab  mov     dword ptr [rbp+520h+var_190+4], r15d
0x1800462b2  mov     [rbp+520h+var_188], r15
0x1800462b9  mov     [rbp+520h+var_170], eax
0x1800462bf  mov     [rbp+520h+var_16C], r15d
0x1800462c6  mov     [rbp+520h+var_168], r15
0x1800462cd  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstallDate.fmtid.Data1
0x1800462d4  movaps  [rbp+520h+var_180], xmm0
0x1800462db  test    rsi, rsi
0x1800462de  jz      short loc_1800462FD
0x1800462e0  lea     rcx, [rsp+620h+var_5C8]; this
0x1800462e5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800462ea  mov     rcx, rsi
0x1800462ed  call    cs:__imp_DevCloseObjectQuery
0x1800462f3  lea     rcx, [rsp+620h+var_5C8]; this
0x1800462f8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800462fd  mov     [rsp+620h+var_5E0], rbx
0x180046302  lea     rax, ?DevQueryCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DevQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180046309  mov     [rsp+620h+var_5E8], r15
0x18004630e  lea     r9, [rbp+520h+var_1C0]
0x180046315  mov     [rsp+620h+var_5F0], rax
0x18004631a  lea     rax, [rbp+520h+var_280]
0x180046321  mov     [rsp+620h+var_5F8], rax
0x180046326  mov     [rsp+620h+var_600], r13d
0x18004632b  jmp     loc_180046450
0x180046330  test    ebx, ebx
0x180046332  js      loc_180046469
0x180046338  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ClassGuid.fmtid.Data1
0x18004633f  mov     eax, cs:DEVPKEY_Device_ClassGuid.pid
0x180046345  lea     rbx, [rdi+48h]
0x180046349  mov     dword ptr [rbp+520h+var_1A8], eax
0x18004634f  lea     rax, _GUID_5989fce8_9cd0_467d_8a6a_5419e31529d4
0x180046356  movups  [rbp+520h+var_1C0+8], xmm0
0x18004635d  mov     [rbp+520h+var_190], rax
0x180046364  movups  xmm0, cs:DEVPKEY_Device_LastKnownParent
0x18004636b  mov     eax, cs:dword_18006FC68
0x180046371  mov     [rbp+520h+var_270], eax
0x180046377  mov     eax, cs:DEVPKEY_Device_DevNodeStatus.pid
0x18004637d  movaps  [rbp+520h+var_280], xmm0
0x180046384  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DevNodeStatus.fmtid.Data1
0x18004638b  mov     dword ptr [rbp+520h+var_1C0], esi
0x180046391  mov     rsi, [rbx]
0x180046394  movaps  [rbp+520h+var_260], xmm0
0x18004639b  mov     dword ptr [rbp+520h+var_250], eax
0x1800463a1  mov     eax, cs:DEVPKEY_Device_InstallDate.pid
0x1800463a7  mov     dword ptr [rbp+520h+var_1A8+4], r15d
0x1800463ae  mov     qword ptr [rbp+520h+var_1A0], r15
0x1800463b5  mov     dword ptr [rbp+520h+var_1A0+8], r8d
0x1800463bc  mov     dword ptr [rbp+520h+var_1A0+0Ch], edx
0x1800463c2  mov     [rbp+520h+var_26C], r15d
0x1800463c9  mov     [rbp+520h+var_268], r15
0x1800463d0  mov     dword ptr [rbp+520h+var_250+4], r15d
0x1800463d7  mov     [rbp+520h+var_248], r15
0x1800463de  mov     [rbp+520h+var_230], eax
0x1800463e4  mov     [rbp+520h+var_22C], r15d
0x1800463eb  mov     [rbp+520h+var_228], r15
0x1800463f2  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstallDate.fmtid.Data1
0x1800463f9  movaps  [rbp+520h+var_240], xmm0
0x180046400  test    rsi, rsi
0x180046403  jz      short loc_180046422
0x180046405  lea     rcx, [rsp+620h+var_5C8]; this
0x18004640a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004640f  mov     rcx, rsi
0x180046412  call    cs:__imp_DevCloseObjectQuery
0x180046418  lea     rcx, [rsp+620h+var_5C8]; this
0x18004641d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180046422  mov     [rsp+620h+var_5E0], rbx
0x180046427  lea     rax, ?DevQueryCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DevQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18004642e  mov     [rsp+620h+var_5E8], r15
0x180046433  lea     r9, [rbp+520h+var_280]
0x18004643a  mov     [rsp+620h+var_5F0], rax
0x18004643f  lea     rax, [rbp+520h+var_1C0]
0x180046446  mov     [rsp+620h+var_5F8], rax
0x18004644b  mov     [rsp+620h+var_600], r12d
0x180046450  mov     r8d, r13d
0x180046453  mov     [rbx], r15
0x180046456  mov     edx, r12d
0x180046459  mov     ecx, r13d
0x18004645c  call    cs:__imp_DevCreateObjectQuery
0x180046462  mov     ebx, eax
0x180046464  mov     esi, 2
0x180046469  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MIDI2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2> `wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl(void)'::`2'::impl
0x180046470  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled(void)
0x180046475  lea     rcx, GUID_DEVCLASS_MEDIA
0x18004647c  test    al, al
0x18004647e  jnz     short loc_18004649B
0x180046480  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MIDI2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2> `wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl(void)'::`2'::impl
0x180046487  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled(void)
0x18004648c  test    al, al
0x18004648e  jnz     loc_180046729
0x180046494  lea     rcx, GUID_DEVCLASS_MEDIA
0x18004649b  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ClassGuid.fmtid.Data1
0x1800464a2  mov     eax, cs:DEVPKEY_Device_ClassGuid.pid
0x1800464a8  lea     rbx, [rdi+68h]
0x1800464ac  movups  xmm1, xmmword ptr cs:DEVPKEY_Device_CompatibleIds.fmtid.Data1
0x1800464b3  mov     [rbp+520h+var_148], eax
0x1800464b9  mov     edx, 11h
0x1800464be  movups  [rbp+520h+var_158], xmm0
0x1800464c5  lea     rax, aUsbClass01; "USB\\Class_01"
0x1800464cc  mov     [rbp+520h+var_130], rcx
0x1800464d3  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_IsPresent.fmtid.Data1
0x1800464da  mov     ecx, cs:DEVPKEY_Device_CompatibleIds.pid
0x1800464e0  mov     [rbp+520h+var_F8], rax
0x1800464e7  mov     eax, cs:DEVPKEY_Device_IsPresent.pid
0x1800464ed  mov     [rbp+520h+var_D8], eax
0x1800464f3  lea     rax, [rsp+620h+var_5CF]
0x1800464f8  mov     [rbp+520h+var_C0], rax
0x1800464ff  mov     eax, cs:DEVPKEY_Device_IsRebootRequired.pid
0x180046505  movups  [rbp+520h+var_E8], xmm0
0x18004650c  mov     [rbp+520h+var_A0], eax
0x180046512  lea     rax, [rsp+620h+var_5D0]
0x180046517  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_IsRebootRequired.fmtid.Data1
0x18004651e  mov     [rbp+520h+var_88], rax
0x180046525  mov     eax, cs:DEVPKEY_Device_DevNodeStatus.pid
0x18004652b  movaps  [rbp+520h+var_B0], xmm0
0x180046532  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DevNodeStatus.fmtid.Data1
0x180046539  mov     [rbp+520h+var_270], eax
0x18004653f  mov     eax, cs:DEVPKEY_Device_InstallDate.pid
0x180046545  movaps  [rbp+520h+var_280], xmm0
0x18004654c  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstallDate.fmtid.Data1
0x180046553  mov     dword ptr [rbp+520h+var_250], eax
0x180046559  mov     eax, cs:DEVPKEY_Device_DriverInfPath.pid
0x18004655f  movaps  [rbp+520h+var_260], xmm0
0x180046566  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverInfPath.fmtid.Data1
0x18004656d  mov     [rbp+520h+var_210], eax
0x180046573  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x180046579  movaps  [rbp+520h+var_220], xmm0
0x180046580  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x180046587  mov     dword ptr [rbp+520h+var_1F0], eax
0x18004658d  mov     eax, cs:?PKEY_DriverSwitchedByAEB@@3U_tagpropertykey@@A.pid; _tagpropertykey PKEY_DriverSwitchedByAEB ...
0x180046593  movaps  [rbp+520h+var_208+8], xmm0
0x18004659a  movups  xmm0, xmmword ptr cs:?PKEY_DriverSwitchedByAEB@@3U_tagpropertykey@@A.fmtid.Data1; _tagpropertykey PKEY_DriverSwitchedByAEB ...
0x1800465a1  mov     [rsp+620h+var_5D0], r15b
0x1800465a6  mov     [rsp+620h+var_5CF], 0FFh
0x1800465ab  movaps  [rbp+520h+var_1E0], xmm0
0x1800465b2  mov     [rbp+520h+var_160], esi
0x1800465b8  mov     [rbp+520h+var_144], r15d
0x1800465bf  mov     [rbp+520h+var_140], r15
0x1800465c6  mov     [rbp+520h+var_138], 0Dh
0x1800465d0  mov     [rbp+520h+var_134], 10h
0x1800465da  mov     [rbp+520h+var_128], 21000h
0x1800465e4  movaps  [rbp+520h+var_120], xmm1
0x1800465eb  mov     [rbp+520h+var_110], ecx
0x1800465f1  mov     [rbp+520h+var_10C], r15d
0x1800465f8  mov     [rbp+520h+var_108], r15
0x1800465ff  mov     [rbp+520h+var_100], 12h
0x180046609  mov     [rbp+520h+var_FC], 1Ah
0x180046613  mov     [rbp+520h+var_F0], esi
0x180046619  mov     [rbp+520h+var_D4], r15d
0x180046620  mov     [rbp+520h+var_D0], r15
0x180046627  mov     [rbp+520h+var_C8], edx
0x18004662d  mov     [rbp+520h+var_C4], r12d
0x180046634  mov     [rbp+520h+var_B8], esi
0x18004663a  mov     [rbp+520h+var_9C], r15d
0x180046641  mov     [rbp+520h+var_98], r15
0x180046648  mov     [rbp+520h+var_90], edx
0x18004664e  mov     [rbp+520h+var_8C], r12d
0x180046655  mov     [rbp+520h+var_26C], r15d
0x18004665c  mov     [rbp+520h+var_268], r15
0x180046663  mov     dword ptr [rbp+520h+var_250+4], r15d
0x18004666a  mov     [rbp+520h+var_248], r15
0x180046671  movaps  [rbp+520h+var_240], xmm1
0x180046678  mov     [rbp+520h+var_230], ecx
0x18004667e  mov     [rbp+520h+var_22C], r15d
0x180046685  mov     [rbp+520h+var_228], r15
0x18004668c  mov     [rbp+520h+var_20C], r15d
0x180046693  mov     qword ptr [rbp+520h+var_208], r15
0x18004669a  mov     dword ptr [rbp+520h+var_1F0+4], r15d
0x1800466a1  mov     [rbp+520h+var_1E8], r15
0x1800466a8  mov     [rbp+520h+var_1D0], eax
0x1800466ae  mov     [rbp+520h+var_1CC], r15d
0x1800466b5  mov     [rbp+520h+var_1C8], r15
0x1800466bc  mov     rsi, [rbx]
0x1800466bf  test    rsi, rsi
0x1800466c2  jz      short loc_1800466E1
0x1800466c4  lea     rcx, [rsp+620h+var_5C8]; this
0x1800466c9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800466ce  mov     rcx, rsi
0x1800466d1  call    cs:__imp_DevCloseObjectQuery
0x1800466d7  lea     rcx, [rsp+620h+var_5C8]; this
0x1800466dc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800466e1  mov     [rsp+620h+var_5E0], rbx
0x1800466e6  lea     rax, ?MidiDriverDevQueryCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; MidiDriverDevQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x1800466ed  mov     [rsp+620h+var_5E8], r15
0x1800466f2  lea     r9, [rbp+520h+var_280]
0x1800466f9  mov     [rsp+620h+var_5F0], rax
0x1800466fe  mov     r8d, 6
0x180046704  lea     rax, [rbp+520h+var_160]
0x18004670b  mov     [rbx], r15
  ... truncated ...
```
