# RdpIdCreateDevice(WDFDEVICE_INIT *)

- ea: `0x18000f31c`
- end: `0x18000f789`
- name: `?RdpIdCreateDevice@@YAXPEAUWDFDEVICE_INIT@@@Z`
- size: `1133`
- prototype: `void __fastcall(struct WDFDEVICE_INIT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cc30`

## callees

- `0x180006f60`
- `0x180006f84`
- `0x180007b38`
- `0x18000dbd8`
- `0x18000e6d0`
- `0x18000e9b8`
- `0x18000ebdc`
- `0x18000ed58`
- `0x18000ed9c`
- `0x18000f31c`
- `0x1800106b8`
- `0x18001072c`
- `0x180010830`
- `0x180011e08`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f3a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f728`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f3a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f728`

## string_xrefs

- `0x18000f52a`: `IddCxDeviceInitConfig failed`
- `0x18000f601`: `Failed to create device`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RdpIdCreateDevice(struct WDFDEVICE_INIT *a1)
{
  char v1; // bl
  bool v2; // di
  bool v3; // si
  char CurrentThreadId; // al
  int v5; // r8d
  int v6; // edx
  char IsEnabled; // al
  int v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // eax
  bool v16; // di
  char v17; // al
  int v18; // r8d
  int v19; // edx
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  const char *v22; // [rsp+28h] [rbp-D8h]
  const char *v23; // [rsp+28h] [rbp-D8h]
  const char *v24; // [rsp+28h] [rbp-D8h]
  int v25; // [rsp+28h] [rbp-D8h]
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  struct WDFDEVICE_INIT *v27; // [rsp+58h] [rbp-A8h] BYREF
  Rdp::Utils::Synchronization::rundown_mutex *v28; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v29; // [rsp+68h] [rbp-98h]
  _QWORD v30[3]; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+8Ch] [rbp-74h]
  __int128 v33; // [rsp+90h] [rbp-70h]
  __int64 *v34; // [rsp+A0h] [rbp-60h]
  int v35; // [rsp+B0h] [rbp-50h] BYREF
  __int64 (__fastcall *v36)(int, int, int, int, char *); // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v37)(struct IDDCX_ADAPTER__ *, const struct IDARG_IN_ADAPTER_INIT_FINISHED *); // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v38)(struct IDDCX_MONITOR__ *, const struct IDARG_IN_GETDEFAULTDESCRIPTIONMODES *, struct IDARG_OUT_GETDEFAULTDESCRIPTIONMODES *); // [rsp+D8h] [rbp-28h]
  int (*v39)(struct IDDCX_MONITOR__ *, const struct IDARG_IN_SETSWAPCHAIN *); // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v40)(struct IDDCX_MONITOR__ *); // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall *v41)(struct IDDCX_MONITOR__ *, const struct IDARG_IN_SET_GAMMARAMP *); // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v42)(struct IDDCX_ADAPTER__ *, const struct IDARG_IN_OPM_GET_CERTIFICATE_SIZE *, struct IDARG_OUT_OPM_GET_CERTIFICATE_SIZE *); // [rsp+110h] [rbp+10h]
  __int64 (__fastcall *v43)(struct IDDCX_ADAPTER__ *, const struct IDARG_IN_OPM_GET_CERTIFICATE *); // [rsp+118h] [rbp+18h]
  __int64 (__fastcall *v44)(struct IDDCX_MONITOR__ *, struct IDDCX_OPMCTX__ *, const struct IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT *); // [rsp+120h] [rbp+20h]
  __int64 (__fastcall *v45)(struct IDDCX_OPMCTX__ *, struct IDARG_OUT_OPM_GET_RANDOM_NUMBER *); // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v46)(struct IDDCX_OPMCTX__ *, const struct IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS *); // [rsp+130h] [rbp+30h]
  __int64 (__fastcall *v47)(struct IDDCX_OPMCTX__ *, const struct IDARG_IN_OPM_GET_INFOMATION *, struct IDARG_OUT_OPM_GET_INFOMATION *); // [rsp+138h] [rbp+38h]
  __int64 (__fastcall *v48)(struct IDDCX_OPMCTX__ *, const struct IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT *); // [rsp+140h] [rbp+40h]
  __int64 (__fastcall *v49)(struct IDDCX_OPMCTX__ *); // [rsp+148h] [rbp+48h]
  __int64 (__fastcall *v50)(const struct IDARG_IN_PARSEMONITORDESCRIPTION2 *, struct IDARG_OUT_PARSEMONITORDESCRIPTION *); // [rsp+158h] [rbp+58h]
  __int64 (__fastcall *v51)(struct IDDCX_ADAPTER__ *, struct IDARG_IN_QUERYTARGET_INFO *, struct IDARG_OUT_QUERYTARGET_INFO *); // [rsp+160h] [rbp+60h]
  __int64 (__fastcall *v52)(struct IDDCX_ADAPTER__ *, const struct IDARG_IN_COMMITMODES2 *); // [rsp+168h] [rbp+68h]
  __int64 (__fastcall *v53)(struct IDDCX_MONITOR__ *, const struct IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA *); // [rsp+170h] [rbp+70h]
  __int64 (__fastcall *v54)(struct IDDCX_MONITOR__ *, const struct IDARG_IN_QUERYTARGETMODES2 *, struct IDARG_OUT_QUERYTARGETMODES *); // [rsp+178h] [rbp+78h]
  _DWORD v55[2]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v56; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v27 = a1;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v3 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v5) = v3;
    LOBYTE(v6) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      v5,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v20,
      (int)v22,
      10,
      &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
      CurrentThreadId);
  }
  memset_0(&v35, 0, 0xD8u);
  if ( IddClientVersionHigherThanFramework )
  {
    if ( (unsigned int)IddStructureCount <= 0x2E )
      v35 = -1;
    else
      v35 = *(_DWORD *)(IddStructures + 368);
  }
  else
  {
    v35 = 216;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableIddCx111>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableIddCx111>::GetImpl'::`2'::impl);
  v8 = v35;
  if ( !IsEnabled )
    v8 = 208;
  v35 = v8;
  v36 = RdpIdEvtIddCxIoDeviceControl;
  v37 = RdpIdEvtIddCxAdapterInitFinished;
  v52 = RdpIdEvtIddCxAdapterCommitModes2;
  v51 = RdpIdEvtIddCxAdapterQueryTargetInfo;
  v50 = RdpIdEvtIddCxParseMonitorDescription2;
  v39 = RdpIdEvtIddCxMonitorAssignSwapChain;
  v40 = RdpIdEvtIddCxMonitorUnassignSwapChain;
  v38 = RdpIdEvtIddCxMonitorGetDefaultModes;
  v54 = RdpIdEvtIddCxMonitorQueryTargetModes2;
  v41 = RdpIdEvtIddCxMonitorSetGammaRamp;
  v53 = RdpIdEvtIddCxMonitorSetDefaultHdrMetaData;
  v42 = RdpIdEvtIddCxMonitorOpmGetCertificateSize;
  v43 = RdpIdEvtIddCxMonitorOpmGetCertificate;
  v44 = RdpIdEvtIddCxMonitorOpmCreateProtectedOutput;
  v45 = RdpIdEvtIddCxMonitorOpmGetRandomNumber;
  v46 = RdpIdEvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers;
  v47 = RdpIdEvtIddCxMonitorOPMGetInformation;
  v48 = RdpIdEvtIddCxMonitorOPMConfigureProtectedOutput;
  v49 = RdpIdEvtIddCxMonitorOPMDestroyProtectedOutput;
  v9 = ((__int64 (__fastcall *)(__int64, struct WDFDEVICE_INIT *, int *))IddFunctions)(IddDriverGlobals, v27, &v35);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\device.cpp",
    (const char *)v9,
    (int)"IddCxDeviceInitConfig failed",
    v22);
  v56 = 2;
  v55[0] = 16;
  v55[1] = 3;
  (*(void (__fastcall **)(__int64, struct WDFDEVICE_INIT *, _DWORD *))(WdfFunctions_02025 + 344))(
    WdfDriverGlobals,
    v27,
    v55);
  v26 = 0;
  v30[0] = 56;
  v30[2] = 0;
  v33 = 0;
  v31 = 1;
  v32 = 1;
  v34 = off_180057078;
  v30[1] = RdpIdEvtDeviceCleanup;
  v10 = (*(__int64 (__fastcall **)(__int64, struct WDFDEVICE_INIT **, _QWORD *, __int64 *))(WdfFunctions_02025 + 200))(
          WdfDriverGlobals,
          &v27,
          v30,
          &v26);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x6F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\device.cpp",
    (const char *)v10,
    (int)"Failed to create device",
    v23);
  v11 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(WdfFunctions_02025 + 984))(
                     WdfDriverGlobals,
                     v26,
                     off_180057078);
  v12 = std::make_shared<CRdpIdAdapter,WDFDEVICE__ * &>(&v28, &v26);
  std::shared_ptr<CRdpIdAdapter>::operator=(v11, v12);
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
  v28 = (Rdp::Utils::Synchronization::rundown_mutex *)operator new(0x60u);
  v13 = Rdp::Utils::Synchronization::rundown_mutex::rundown_mutex(v28);
  v28 = 0;
  v14 = v11[3];
  v11[3] = v13;
  if ( v14 )
    std::default_delete<Rdp::Utils::Synchronization::rundown_mutex>::operator()();
  std::unique_ptr<Rdp::Utils::Synchronization::rundown_mutex>::~unique_ptr<Rdp::Utils::Synchronization::rundown_mutex>(&v28);
  qword_180057F60 = *v11;
  RdpIdQueueInitialize(v26);
  v15 = ((__int64 (__fastcall *)(__int64, __int64))qword_180057B18)(IddDriverGlobals, v26);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x8B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\device.cpp",
    (const char *)v15,
    (int)"IddCxDeviceInitialize failed",
    v24);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v1 = 0;
  }
  v16 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v17 = GetCurrentThreadId();
    LOBYTE(v18) = v16;
    LOBYTE(v19) = v1;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      v18,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v21,
      v25,
      11,
      &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
      v17);
  }
}

```

## disassembly

```asm
0x18000f31c  mov     [rsp-8+arg_8], rbx
0x18000f321  mov     [rsp-8+arg_10], rsi
0x18000f326  push    rbp
0x18000f327  push    rdi
0x18000f328  push    r12
0x18000f32a  push    r13
0x18000f32c  push    r15
0x18000f32e  lea     rbp, [rsp-0B0h]
0x18000f336  sub     rsp, 1B0h
0x18000f33d  mov     rax, cs:__security_cookie
0x18000f344  xor     rax, rsp
0x18000f347  mov     [rbp+0D0h+var_30], rax
0x18000f34e  mov     [rsp+1D0h+var_178], rcx
0x18000f353  lea     r13, WPP_GLOBAL_Control
0x18000f35a  mov     ebx, 1
0x18000f35f  mov     rax, cs:WPP_GLOBAL_Control
0x18000f366  cmp     rax, r13
0x18000f369  jz      short loc_18000F37B
0x18000f36b  test    [rax+1Ch], bl
0x18000f36e  jz      short loc_18000F37B
0x18000f370  cmp     byte ptr [rax+19h], 4
0x18000f374  jb      short loc_18000F37B
0x18000f376  mov     dil, bl
0x18000f379  jmp     short loc_18000F37E
0x18000f37b  xor     dil, dil
0x18000f37e  lea     r15, WPP_RECORDER_INITIALIZED
0x18000f385  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f38c  setnz   sil
0x18000f390  lea     r12, WPP_bf700344ce113c4bc67df149a6a70839_Traceguids
0x18000f397  test    dil, dil
0x18000f39a  jnz     short loc_18000F3A1
0x18000f39c  test    sil, sil
0x18000f39f  jz      short loc_18000F3D7
0x18000f3a1  call    cs:__imp_GetCurrentThreadId
0x18000f3a8  nop     dword ptr [rax+rax+00h]
0x18000f3ad  mov     dword ptr [rsp+1D0h+var_190], eax; char
0x18000f3b1  mov     [rsp+1D0h+MessageGuid], r12; MessageGuid
0x18000f3b6  mov     [rsp+1D0h+var_1A0], 0Ah; __int16
0x18000f3bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3c4  mov     r9, [rcx+28h]; int
0x18000f3c8  mov     r8b, sil; int
0x18000f3cb  mov     dl, dil; int
0x18000f3ce  mov     rcx, [rcx+10h]; int
0x18000f3d2  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000f3d7  mov     edi, 0D8h
0x18000f3dc  mov     r8d, edi; Size
0x18000f3df  xor     edx, edx; Val
0x18000f3e1  lea     rcx, [rbp+0D0h+var_120]; void *
0x18000f3e5  call    memset_0
0x18000f3ea  cmp     cs:IddClientVersionHigherThanFramework, 0
0x18000f3f1  jz      short loc_18000F417
0x18000f3f3  cmp     cs:IddStructureCount, 2Eh ; '.'
0x18000f3fa  jbe     short loc_18000F40E
0x18000f3fc  mov     rax, cs:IddStructures
0x18000f403  mov     ecx, [rax+170h]
0x18000f409  mov     [rbp+0D0h+var_120], ecx
0x18000f40c  jmp     short loc_18000F41A
0x18000f40e  mov     [rbp+0D0h+var_120], 0FFFFFFFFh
0x18000f415  jmp     short loc_18000F41A
0x18000f417  mov     [rbp+0D0h+var_120], edi
0x18000f41a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableIddCx111@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableIddCx111@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableIddCx111> `wil::Feature<__WilFeatureTraits_Feature_EnableIddCx111>::GetImpl(void)'::`2'::impl
0x18000f421  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableIddCx111@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableIddCx111>::__private_IsEnabled(void)
0x18000f426  mov     ecx, [rbp+0D0h+var_120]
0x18000f429  mov     edx, 0D0h
0x18000f42e  test    al, al
0x18000f430  cmovz   ecx, edx
0x18000f433  mov     [rbp+0D0h+var_120], ecx
0x18000f436  lea     rax, RdpIdEvtIddCxIoDeviceControl
0x18000f43d  mov     [rbp+0D0h+var_118], rax
0x18000f441  lea     rax, ?RdpIdEvtIddCxAdapterInitFinished@@YAJPEAUIDDCX_ADAPTER__@@PEBUIDARG_IN_ADAPTER_INIT_FINISHED@@@Z; RdpIdEvtIddCxAdapterInitFinished(IDDCX_ADAPTER__ *,IDARG_IN_ADAPTER_INIT_FINISHED const *)
0x18000f448  mov     [rbp+0D0h+var_108], rax
0x18000f44c  lea     rax, ?RdpIdEvtIddCxAdapterCommitModes2@@YAJPEAUIDDCX_ADAPTER__@@PEBUIDARG_IN_COMMITMODES2@@@Z; RdpIdEvtIddCxAdapterCommitModes2(IDDCX_ADAPTER__ *,IDARG_IN_COMMITMODES2 const *)
0x18000f453  mov     [rbp+0D0h+var_68], rax
0x18000f457  lea     rax, ?RdpIdEvtIddCxAdapterQueryTargetInfo@@YAJPEAUIDDCX_ADAPTER__@@PEAUIDARG_IN_QUERYTARGET_INFO@@PEAUIDARG_OUT_QUERYTARGET_INFO@@@Z; RdpIdEvtIddCxAdapterQueryTargetInfo(IDDCX_ADAPTER__ *,IDARG_IN_QUERYTARGET_INFO *,IDARG_OUT_QUERYTARGET_INFO *)
0x18000f45e  mov     [rbp+0D0h+var_70], rax
0x18000f462  lea     rax, ?RdpIdEvtIddCxParseMonitorDescription2@@YAJPEBUIDARG_IN_PARSEMONITORDESCRIPTION2@@PEAUIDARG_OUT_PARSEMONITORDESCRIPTION@@@Z; RdpIdEvtIddCxParseMonitorDescription2(IDARG_IN_PARSEMONITORDESCRIPTION2 const *,IDARG_OUT_PARSEMONITORDESCRIPTION *)
0x18000f469  mov     [rbp+0D0h+var_78], rax
0x18000f46d  lea     rax, ?RdpIdEvtIddCxMonitorAssignSwapChain@@YAJPEAUIDDCX_MONITOR__@@PEBUIDARG_IN_SETSWAPCHAIN@@@Z; RdpIdEvtIddCxMonitorAssignSwapChain(IDDCX_MONITOR__ *,IDARG_IN_SETSWAPCHAIN const *)
0x18000f474  mov     [rbp+0D0h+var_E8], rax
0x18000f478  lea     rax, ?RdpIdEvtIddCxMonitorUnassignSwapChain@@YAJPEAUIDDCX_MONITOR__@@@Z; RdpIdEvtIddCxMonitorUnassignSwapChain(IDDCX_MONITOR__ *)
0x18000f47f  mov     [rbp+0D0h+var_E0], rax
0x18000f483  lea     rax, ?RdpIdEvtIddCxMonitorGetDefaultModes@@YAJPEAUIDDCX_MONITOR__@@PEBUIDARG_IN_GETDEFAULTDESCRIPTIONMODES@@PEAUIDARG_OUT_GETDEFAULTDESCRIPTIONMODES@@@Z; RdpIdEvtIddCxMonitorGetDefaultModes(IDDCX_MONITOR__ *,IDARG_IN_GETDEFAULTDESCRIPTIONMODES const *,IDARG_OUT_GETDEFAULTDESCRIPTIONMODES *)
0x18000f48a  mov     [rbp+0D0h+var_F8], rax
0x18000f48e  lea     rax, ?RdpIdEvtIddCxMonitorQueryTargetModes2@@YAJPEAUIDDCX_MONITOR__@@PEBUIDARG_IN_QUERYTARGETMODES2@@PEAUIDARG_OUT_QUERYTARGETMODES@@@Z; RdpIdEvtIddCxMonitorQueryTargetModes2(IDDCX_MONITOR__ *,IDARG_IN_QUERYTARGETMODES2 const *,IDARG_OUT_QUERYTARGETMODES *)
0x18000f495  mov     [rbp+0D0h+var_58], rax
0x18000f499  lea     rax, ?RdpIdEvtIddCxMonitorSetGammaRamp@@YAJPEAUIDDCX_MONITOR__@@PEBUIDARG_IN_SET_GAMMARAMP@@@Z; RdpIdEvtIddCxMonitorSetGammaRamp(IDDCX_MONITOR__ *,IDARG_IN_SET_GAMMARAMP const *)
0x18000f4a0  mov     [rbp+0D0h+var_C8], rax
0x18000f4a4  lea     rax, ?RdpIdEvtIddCxMonitorSetDefaultHdrMetaData@@YAJPEAUIDDCX_MONITOR__@@PEBUIDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA@@@Z; RdpIdEvtIddCxMonitorSetDefaultHdrMetaData(IDDCX_MONITOR__ *,IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA const *)
0x18000f4ab  mov     [rbp+0D0h+var_60], rax
0x18000f4af  lea     rax, ?RdpIdEvtIddCxMonitorOpmGetCertificateSize@@YAJPEAUIDDCX_ADAPTER__@@PEBUIDARG_IN_OPM_GET_CERTIFICATE_SIZE@@PEAUIDARG_OUT_OPM_GET_CERTIFICATE_SIZE@@@Z; RdpIdEvtIddCxMonitorOpmGetCertificateSize(IDDCX_ADAPTER__ *,IDARG_IN_OPM_GET_CERTIFICATE_SIZE const *,IDARG_OUT_OPM_GET_CERTIFICATE_SIZE *)
0x18000f4b6  mov     [rbp+0D0h+var_C0], rax
0x18000f4ba  lea     rax, ?RdpIdEvtIddCxMonitorOpmGetCertificate@@YAJPEAUIDDCX_ADAPTER__@@PEBUIDARG_IN_OPM_GET_CERTIFICATE@@@Z; RdpIdEvtIddCxMonitorOpmGetCertificate(IDDCX_ADAPTER__ *,IDARG_IN_OPM_GET_CERTIFICATE const *)
0x18000f4c1  mov     [rbp+0D0h+var_B8], rax
0x18000f4c5  lea     rax, ?RdpIdEvtIddCxMonitorOpmCreateProtectedOutput@@YAJPEAUIDDCX_MONITOR__@@PEAUIDDCX_OPMCTX__@@PEBUIDARG_IN_OPM_CREATE_PROTECTED_OUTPUT@@@Z; RdpIdEvtIddCxMonitorOpmCreateProtectedOutput(IDDCX_MONITOR__ *,IDDCX_OPMCTX__ *,IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT const *)
0x18000f4cc  mov     [rbp+0D0h+var_B0], rax
0x18000f4d0  lea     rax, ?RdpIdEvtIddCxMonitorOpmGetRandomNumber@@YAJPEAUIDDCX_OPMCTX__@@PEAUIDARG_OUT_OPM_GET_RANDOM_NUMBER@@@Z; RdpIdEvtIddCxMonitorOpmGetRandomNumber(IDDCX_OPMCTX__ *,IDARG_OUT_OPM_GET_RANDOM_NUMBER *)
0x18000f4d7  mov     [rbp+0D0h+var_A8], rax
0x18000f4db  lea     rax, ?RdpIdEvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers@@YAJPEAUIDDCX_OPMCTX__@@PEBUIDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS@@@Z; RdpIdEvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers(IDDCX_OPMCTX__ *,IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS const *)
0x18000f4e2  mov     [rbp+0D0h+var_A0], rax
0x18000f4e6  lea     rax, ?RdpIdEvtIddCxMonitorOPMGetInformation@@YAJPEAUIDDCX_OPMCTX__@@PEBUIDARG_IN_OPM_GET_INFOMATION@@PEAUIDARG_OUT_OPM_GET_INFOMATION@@@Z; RdpIdEvtIddCxMonitorOPMGetInformation(IDDCX_OPMCTX__ *,IDARG_IN_OPM_GET_INFOMATION const *,IDARG_OUT_OPM_GET_INFOMATION *)
0x18000f4ed  mov     [rbp+0D0h+var_98], rax
0x18000f4f1  lea     rax, ?RdpIdEvtIddCxMonitorOPMConfigureProtectedOutput@@YAJPEAUIDDCX_OPMCTX__@@PEBUIDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT@@@Z; RdpIdEvtIddCxMonitorOPMConfigureProtectedOutput(IDDCX_OPMCTX__ *,IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT const *)
0x18000f4f8  mov     [rbp+0D0h+var_90], rax
0x18000f4fc  lea     rax, ?RdpIdEvtIddCxMonitorOPMDestroyProtectedOutput@@YAJPEAUIDDCX_OPMCTX__@@@Z; RdpIdEvtIddCxMonitorOPMDestroyProtectedOutput(IDDCX_OPMCTX__ *)
0x18000f503  mov     [rbp+0D0h+var_88], rax
0x18000f507  lea     r8, [rbp+0D0h+var_120]
0x18000f50b  mov     rdx, [rsp+1D0h+var_178]
0x18000f510  mov     rcx, cs:IddDriverGlobals
0x18000f517  mov     rax, cs:IddFunctions
0x18000f51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f523  mov     rcx, [rbp+0D8h]; this
0x18000f52a  lea     rdx, aIddcxdeviceini_0; "IddCxDeviceInitConfig failed"
0x18000f531  mov     qword ptr [rsp+1D0h+var_1B0], rdx; int
0x18000f536  mov     r9d, eax; char *
0x18000f539  lea     rsi, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18000f540  mov     r8, rsi; unsigned int
0x18000f543  mov     edx, 5Eh ; '^'; void *
0x18000f548  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000f54d  mov     [rbp+0D0h+var_38], 2
0x18000f558  mov     [rbp+0D0h+var_40], 10h
0x18000f562  mov     [rbp+0D0h+var_3C], 3
0x18000f56c  mov     rax, cs:WdfFunctions_02025
0x18000f573  lea     r8, [rbp+0D0h+var_40]
0x18000f57a  mov     rdx, [rsp+1D0h+var_178]
0x18000f57f  mov     rcx, cs:WdfDriverGlobals
0x18000f586  mov     rax, [rax+158h]
0x18000f58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f592  mov     [rsp+1D0h+var_180], 0
0x18000f59b  mov     [rsp+1D0h+var_160], 38h ; '8'
0x18000f5a4  mov     [rbp+0D0h+var_150], 0
0x18000f5ac  xorps   xmm0, xmm0
0x18000f5af  movdqu  [rbp+0D0h+var_140], xmm0
0x18000f5b4  mov     [rbp+0D0h+var_148], ebx
0x18000f5b7  mov     [rbp+0D0h+var_144], ebx
0x18000f5ba  mov     rax, cs:off_180057078
0x18000f5c1  mov     [rbp+0D0h+var_130], rax
0x18000f5c5  lea     rax, ?RdpIdEvtDeviceCleanup@@YAXPEAX@Z; RdpIdEvtDeviceCleanup(void *)
0x18000f5cc  mov     [rsp+1D0h+var_158], rax
0x18000f5d1  mov     rax, cs:WdfFunctions_02025
0x18000f5d8  lea     r9, [rsp+1D0h+var_180]
0x18000f5dd  lea     r8, [rsp+1D0h+var_160]
0x18000f5e2  lea     rdx, [rsp+1D0h+var_178]
0x18000f5e7  mov     rcx, cs:WdfDriverGlobals
0x18000f5ee  mov     rax, [rax+0C8h]
0x18000f5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5fa  mov     rcx, [rbp+0D8h]; this
0x18000f601  lea     rdx, aFailedToCreate_6; "Failed to create device"
0x18000f608  mov     qword ptr [rsp+1D0h+var_1B0], rdx; int
0x18000f60d  mov     r9d, eax; char *
0x18000f610  mov     r8, rsi; unsigned int
0x18000f613  mov     edx, 6Fh ; 'o'; void *
0x18000f618  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000f61d  mov     rax, cs:WdfFunctions_02025
0x18000f624  mov     r8, cs:off_180057078
0x18000f62b  mov     rdx, [rsp+1D0h+var_180]
0x18000f630  mov     rcx, cs:WdfDriverGlobals
0x18000f637  mov     rax, [rax+3D8h]
0x18000f63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f643  mov     rdi, rax
0x18000f646  lea     rdx, [rsp+1D0h+var_180]
0x18000f64b  lea     rcx, [rsp+1D0h+var_170]
0x18000f650  call    ??$make_shared@VCRdpIdAdapter@@AEAPEAUWDFDEVICE__@@@std@@YA?AV?$shared_ptr@VCRdpIdAdapter@@@0@AEAPEAUWDFDEVICE__@@@Z; std::make_shared<CRdpIdAdapter,WDFDEVICE__ * &>(WDFDEVICE__ * &)
0x18000f655  mov     rdx, rax
0x18000f658  mov     rcx, rdi
0x18000f65b  call    ??4?$shared_ptr@VCRdpIdAdapter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CRdpIdAdapter>::operator=(std::shared_ptr<CRdpIdAdapter> &&)
0x18000f660  mov     rcx, [rsp+1D0h+var_168]; this
0x18000f665  test    rcx, rcx
0x18000f668  jz      short loc_18000F66F
0x18000f66a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f66f  mov     ecx, 60h ; '`'; Size
0x18000f674  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f679  mov     [rsp+1D0h+var_170], rax
0x18000f67e  mov     rcx, rax; this
0x18000f681  call    ??0rundown_mutex@Synchronization@Utils@Rdp@@QEAA@XZ; Rdp::Utils::Synchronization::rundown_mutex::rundown_mutex(void)
0x18000f686  nop
0x18000f687  mov     [rsp+1D0h+var_170], 0
0x18000f690  mov     rdx, [rdi+18h]
0x18000f694  mov     [rdi+18h], rax
0x18000f698  test    rdx, rdx
0x18000f69b  jz      short loc_18000F6A2
0x18000f69d  call    ??R?$default_delete@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEBAXPEAVrundown_mutex@Synchronization@Utils@Rdp@@@Z; std::default_delete<Rdp::Utils::Synchronization::rundown_mutex>::operator()(Rdp::Utils::Synchronization::rundown_mutex *)
0x18000f6a2  lea     rcx, [rsp+1D0h+var_170]
0x18000f6a7  call    ??1?$unique_ptr@Vrundown_mutex@Synchronization@Utils@Rdp@@U?$default_delete@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Utils::Synchronization::rundown_mutex>::~unique_ptr<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18000f6ac  mov     rax, [rdi]
0x18000f6af  mov     cs:qword_180057F60, rax
0x18000f6b6  mov     rcx, [rsp+1D0h+var_180]
0x18000f6bb  call    RdpIdQueueInitialize
0x18000f6c0  mov     rdx, [rsp+1D0h+var_180]
0x18000f6c5  mov     rcx, cs:IddDriverGlobals
0x18000f6cc  mov     rax, cs:qword_180057B18
0x18000f6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d8  mov     rcx, [rbp+0D8h]; this
0x18000f6df  lea     rdx, aIddcxdeviceini; "IddCxDeviceInitialize failed"
0x18000f6e6  mov     qword ptr [rsp+1D0h+var_1B0], rdx; int
0x18000f6eb  mov     r9d, eax; char *
0x18000f6ee  mov     r8, rsi; unsigned int
0x18000f6f1  mov     edx, 8Bh; void *
0x18000f6f6  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000f6fb  mov     rax, cs:WPP_GLOBAL_Control
0x18000f702  cmp     rax, r13
0x18000f705  jz      short loc_18000F712
0x18000f707  test    [rax+1Ch], bl
0x18000f70a  jz      short loc_18000F712
0x18000f70c  cmp     byte ptr [rax+19h], 4
0x18000f710  jnb     short loc_18000F714
0x18000f712  xor     bl, bl
0x18000f714  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f71b  setnz   dil
0x18000f71f  test    bl, bl
0x18000f721  jnz     short loc_18000F728
0x18000f723  test    dil, dil
0x18000f726  jz      short loc_18000F75D
0x18000f728  call    cs:__imp_GetCurrentThreadId
0x18000f72f  nop     dword ptr [rax+rax+00h]
0x18000f734  mov     dword ptr [rsp+1D0h+var_190], eax; char
0x18000f738  mov     [rsp+1D0h+MessageGuid], r12; MessageGuid
0x18000f73d  mov     [rsp+1D0h+var_1A0], 0Bh; __int16
0x18000f744  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f74b  mov     r9, [rcx+28h]; int
0x18000f74f  mov     r8b, dil; int
0x18000f752  mov     dl, bl; int
0x18000f754  mov     rcx, [rcx+10h]; int
0x18000f758  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000f75d  mov     rcx, [rbp+0D0h+var_30]
0x18000f764  xor     rcx, rsp; StackCookie
0x18000f767  call    __security_check_cookie
0x18000f76c  lea     r11, [rsp+1D0h+var_20]
0x18000f774  mov     rbx, [r11+38h]
0x18000f778  mov     rsi, [r11+40h]
0x18000f77c  mov     rsp, r11
0x18000f77f  pop     r15
0x18000f781  pop     r13
0x18000f783  pop     r12
0x18000f785  pop     rdi
0x18000f786  pop     rbp
0x18000f787  retn
```
