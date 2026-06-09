# CAudioPumpDspResourceManager::RuntimeClassInitialize(ushort *,ushort *,std::shared_ptr<CSerialWorkQueue> &,_tlgProvider_t const *,_GUID,IAudioDspProviderManager *)

- ea: `0x140090884`
- end: `0x140090d3a`
- name: `?RuntimeClassInitialize@CAudioPumpDspResourceManager@@QEAAJPEAG0AEAV?$shared_ptr@VCSerialWorkQueue@@@std@@PEBU_tlgProvider_t@@U_GUID@@PEAUIAudioDspProviderManager@@@Z`
- size: `1206`
- prototype: `__int64 __usercall@<rax>(CAudioPumpDspResourceManager *this@<rcx>, __int64, IID *rclsid, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14008d9bc`

## callees

- `0x14000c33c`
- `0x14000f36c`
- `0x140016ba8`
- `0x140016f68`
- `0x140035794`
- `0x140045a74`
- `0x1400516e8`
- `0x140054f24`
- `0x140058bd8`
- `0x14008d8b4`
- `0x14008fe60`
- `0x140090884`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140090a5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140090af4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140090a5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140090af4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140090a29`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140090a29`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x1400909d4`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x140090b04`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x1400909d4`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x140090b04`
- `api-ms-win-core-com-l1-1-3!CoRegisterDeviceCatalog` at `0x1400909a6`
- `api-ms-win-core-com-l1-1-3!CoRegisterDeviceCatalog` at `0x1400909a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAudioPumpDspResourceManager::RuntimeClassInitialize(
        CAudioPumpDspResourceManager *this,
        char *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        IID *rclsid,
        __int64 a7)
{
  __int64 v10; // rax
  __int64 v11; // rcx
  std::_Ref_count_base *v12; // rax
  __int64 v13; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // ebx
  __int64 v15; // rdx
  __int64 v17; // rax
  int v18; // eax
  __int64 **v19; // rsi
  __int64 v20; // rcx
  HRESULT Instance; // eax
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // r14
  __int64 (__fastcall *v26)(__int64 *, SID *, GUID *, char *); // r15
  _QWORD *v27; // rbx
  __int64 v28; // rdx
  int v29; // eax
  unsigned int v30; // r14d
  __int64 *v31; // r14
  __int64 (__fastcall *v32)(__int64 *, SID *, GUID *, char *); // r15
  __int64 v33; // rdx
  int v34; // eax
  unsigned int v35; // esi
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v38; // r8d
  __int64 v39; // rcx
  int ppv; // [rsp+20h] [rbp-81h]
  int ppva; // [rsp+20h] [rbp-81h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-61h] BYREF
  char *v43; // [rsp+48h] [rbp-59h] BYREF
  char *v44; // [rsp+50h] [rbp-51h] BYREF
  __int64 v45; // [rsp+58h] [rbp-49h] BYREF
  char *v46; // [rsp+60h] [rbp-41h] BYREF
  _QWORD v47[15]; // [rsp+68h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]

  *((_QWORD *)this + 11) = a5;
  v10 = *(_QWORD *)(a4 + 8);
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  v11 = *(_QWORD *)(a4 + 8);
  *((_QWORD *)this + 22) = *(_QWORD *)a4;
  v12 = (std::_Ref_count_base *)*((_QWORD *)this + 23);
  *((_QWORD *)this + 23) = v11;
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  v13 = *((_QWORD *)this + 25);
  *((_QWORD *)this + 25) = a7;
  if ( a7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a7 + 8LL))(a7);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpCriticalSection,
    a2,
    a3,
    (const char *)a4);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 128,
    &lpCriticalSection);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpCriticalSection);
  if ( !*((_QWORD *)this + 16) )
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = -2147024882;
    v15 = 734;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\audiopumpdspresourcemanager.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      ppv);
    return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 168, 0);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v15 = 737;
    goto LABEL_11;
  }
  v44 = 0;
  v17 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<CO_DEVICE_CATALOG_COOKIE__ *,long (*)(CO_DEVICE_CATALOG_COOKIE__ *),&long CoRevokeDeviceCatalog(CO_DEVICE_CATALOG_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_DEVICE_CATALOG_COOKIE__ *,CO_DEVICE_CATALOG_COOKIE__ *,0,std::nullptr_t>>>::put(&v44);
  v18 = CoRegisterDeviceCatalog(a3, v17);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E7,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\audiopumpdspresourcemanager.cpp",
      (const char *)(unsigned int)v18,
      ppv);
LABEL_17:
    if ( v44 )
      CoRevokeDeviceCatalog();
    return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
  (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(**((_QWORD **)this + 25) + 24LL))(
    *((_QWORD *)this + 25),
    &lpCriticalSection);
  v19 = (__int64 **)((char *)this + 96);
  v20 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  Instance = CoCreateInstance(rclsid, 0, 1u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, (LPVOID *)this + 12);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EC,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\audiopumpdspresourcemanager.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    goto LABEL_23;
  }
  v43 = 0;
  v22 = *v19;
  v23 = **v19;
  v43 = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(__int64 *, SID *, GUID *, char **))(v23 + 24))(v22, &SID_AudioDspServiceProviderService, &GUID_39f25818_c4a0_46b1_b7ac_01b630b00c7d, &v43);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v24 = 752;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\audiopumpdspresourcemanager.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      ppva);
    wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v43);
LABEL_23:
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    goto LABEL_17;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(char *, char *))(*(_QWORD *)v43 + 24LL))(v43, a2);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v24 = 753;
    goto LABEL_27;
  }
  wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v43);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( v44 )
    CoRevokeDeviceCatalog();
  v25 = *v19;
  v26 = *(__int64 (__fastcall **)(__int64 *, SID *, GUID *, char *))(**v19 + 24);
  v27 = (_QWORD *)((char *)this + 112);
  v28 = *((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  v29 = v26(v25, &SID_AudioPumpDspDriverService, &GUID_0ead8f8d_6c3b_4754_a435_374fe81b878e, (char *)this + 112);
  v30 = v29;
  if ( v29 >= 0 )
  {
    v31 = *v19;
    v32 = *(__int64 (__fastcall **)(__int64 *, SID *, GUID *, char *))(**v19 + 24);
    v33 = *((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = 0;
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v34 = v32(v31, &SID_DspAudioEngineService, &GUID_64741865_eaba_478d_ac58_fa9e4b81a170, (char *)this + 104);
    v35 = v34;
    if ( v34 >= 0 )
    {
      *((_DWORD *)this + 18) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 24LL))(*v27);
      lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 160);
      v36 = *((_QWORD *)this + 19);
      *((_QWORD *)this + 19) = 0;
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      v44 = (char *)this + 152;
      v43 = (char *)this + 144;
      v37 = *((_QWORD *)this + 17);
      *((_QWORD *)this + 17) = 0;
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      v46 = (char *)this + 136;
      v45 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 32LL))(*v27);
      v39 = *((_QWORD *)this + 15);
      *((_QWORD *)this + 15) = 0;
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = Microsoft::WRL::Details::MakeAndInitialize<CAudioDg_Driver,IAudioDgDriver,void *,void *,IAudioPumpDspBuffer * *,unsigned int *,IAudioPumpDspBuffer * *,unsigned int *>((int)this + 120, (unsigned int)&v45, v38, (unsigned int)&v46, (__int64)&v43, (__int64)&v44, (__int64)&lpCriticalSection);
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v15 = 766;
        goto LABEL_11;
      }
      v47[0] = off_1400BDDC0;
      v47[1] = this;
      v47[7] = v47;
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = CSerialWorkQueue::QueueWaitItem(*((_QWORD *)this + 22), *((_QWORD *)this + 21), v47, (char *)this + 192);
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v15 = 769;
        goto LABEL_11;
      }
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = CAudioPumpDspResourceManager::InitializeAudioDgController(this);
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v15 = 772;
        goto LABEL_11;
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F6,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\audiopumpdspresourcemanager.cpp",
        (const char *)(unsigned int)v34,
        ppva);
      return v35;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F5,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\audiopumpdspresourcemanager.cpp",
      (const char *)(unsigned int)v29,
      ppva);
    return v30;
  }
}

```

## disassembly

```asm
0x140090884  push    rbp
0x140090886  push    rbx
0x140090887  push    rsi
0x140090888  push    rdi
0x140090889  push    r12
0x14009088b  push    r14
0x14009088d  push    r15
0x14009088f  lea     rbp, [rsp-0Fh]
0x140090894  sub     rsp, 0B0h
0x14009089b  mov     rsi, r8
0x14009089e  mov     r14, rdx
0x1400908a1  mov     rdi, rcx
0x1400908a4  mov     r15, [rbp+3Fh+rclsid]
0x1400908a8  mov     rax, [rbp+3Fh+arg_20]
0x1400908ac  mov     [rcx+58h], rax
0x1400908b0  mov     rax, [r9+8]
0x1400908b4  test    rax, rax
0x1400908b7  jz      short loc_1400908BD
0x1400908b9  lock inc dword ptr [rax+8]
0x1400908bd  mov     rcx, [r9+8]
0x1400908c1  mov     rax, [r9]
0x1400908c4  mov     [rdi+0B0h], rax
0x1400908cb  mov     rax, [rdi+0B8h]
0x1400908d2  mov     [rdi+0B8h], rcx
0x1400908d9  test    rax, rax
0x1400908dc  jz      short loc_1400908E7
0x1400908de  mov     rcx, rax; this
0x1400908e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400908e6  nop
0x1400908e7  mov     rbx, [rdi+0C8h]
0x1400908ee  mov     rcx, [rbp+3Fh+arg_30]
0x1400908f2  mov     [rdi+0C8h], rcx
0x1400908f9  test    rcx, rcx
0x1400908fc  jz      short loc_14009090A
0x1400908fe  mov     rax, [rcx]
0x140090901  mov     rax, [rax+8]
0x140090905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009090a  test    rbx, rbx
0x14009090d  jz      short loc_14009091F
0x14009090f  mov     rax, [rbx]
0x140090912  mov     rcx, rbx
0x140090915  mov     rax, [rax+10h]
0x140090919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009091e  nop
0x14009091f  mov     rdx, r14
0x140090922  lea     rcx, [rbp+3Fh+lpCriticalSection]
0x140090926  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14009092b  lea     rbx, [rdi+80h]
0x140090932  lea     rdx, [rbp+3Fh+lpCriticalSection]
0x140090936  mov     rcx, rbx
0x140090939  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x14009093e  lea     rcx, [rbp+3Fh+lpCriticalSection]
0x140090942  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140090947  cmp     qword ptr [rbx], 0
0x14009094b  jnz     short loc_140090971
0x14009094d  mov     ebx, 8007000Eh
0x140090952  mov     edx, 2DEh; void *
0x140090957  mov     rcx, [rbp+47h]; this
0x14009095b  mov     r9d, ebx; char *
0x14009095e  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140090965  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009096a  mov     eax, ebx
0x14009096c  jmp     loc_140090D28
0x140090971  lea     r12, [rdi+0A8h]
0x140090978  xor     edx, edx
0x14009097a  mov     rcx, r12
0x14009097d  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140090982  mov     ebx, eax
0x140090984  test    eax, eax
0x140090986  jns     short loc_14009098F
0x140090988  mov     edx, 2E1h
0x14009098d  jmp     short loc_140090957
0x14009098f  mov     [rbp+3Fh+var_90], 0
0x140090997  lea     rcx, [rbp+3Fh+var_90]
0x14009099b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUCO_DEVICE_CATALOG_COOKIE__@@P6AJPEAU1@@Z$1?CoRevokeDeviceCatalog@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUCO_DEVICE_CATALOG_COOKIE__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<CO_DEVICE_CATALOG_COOKIE__ *,long (*)(CO_DEVICE_CATALOG_COOKIE__ *),&CoRevokeDeviceCatalog(CO_DEVICE_CATALOG_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_DEVICE_CATALOG_COOKIE__ *,CO_DEVICE_CATALOG_COOKIE__ *,0,std::nullptr_t>>>::put(void)
0x1400909a0  mov     rdx, rax
0x1400909a3  mov     rcx, rsi
0x1400909a6  call    cs:__imp_CoRegisterDeviceCatalog
0x1400909ac  mov     ebx, eax
0x1400909ae  test    eax, eax
0x1400909b0  jns     short loc_1400909DC
0x1400909b2  mov     rcx, [rbp+47h]; this
0x1400909b6  mov     r9d, eax; char *
0x1400909b9  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x1400909c0  mov     edx, 2E7h; void *
0x1400909c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400909ca  nop
0x1400909cb  mov     rcx, [rbp+3Fh+var_90]
0x1400909cf  test    rcx, rcx
0x1400909d2  jz      short loc_14009096A
0x1400909d4  call    cs:__imp_CoRevokeDeviceCatalog
0x1400909da  jmp     short loc_14009096A
0x1400909dc  mov     rcx, [rdi+0C8h]
0x1400909e3  mov     rax, [rcx]
0x1400909e6  lea     rdx, [rbp+3Fh+lpCriticalSection]
0x1400909ea  mov     rax, [rax+18h]
0x1400909ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400909f3  nop
0x1400909f4  lea     rsi, [rdi+60h]
0x1400909f8  mov     rcx, [rsi]
0x1400909fb  mov     qword ptr [rsi], 0
0x140090a02  test    rcx, rcx
0x140090a05  jz      short loc_140090A14
0x140090a07  mov     rax, [rcx]
0x140090a0a  mov     rax, [rax+10h]
0x140090a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090a13  nop
0x140090a14  mov     [rsp+0E0h+ppv], rsi; int
0x140090a19  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x140090a20  xor     edx, edx; pUnkOuter
0x140090a22  lea     r8d, [rdx+1]; dwClsContext
0x140090a26  mov     rcx, r15; rclsid
0x140090a29  call    cs:__imp_CoCreateInstance
0x140090a2f  mov     ebx, eax
0x140090a31  test    eax, eax
0x140090a33  jns     short loc_140090A66
0x140090a35  mov     rcx, [rbp+47h]; this
0x140090a39  mov     r9d, eax; char *
0x140090a3c  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140090a43  mov     edx, 2ECh; void *
0x140090a48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140090a4d  nop
0x140090a4e  mov     rcx, [rbp+3Fh+lpCriticalSection]; lpCriticalSection
0x140090a52  test    rcx, rcx
0x140090a55  jz      loc_1400909CB
0x140090a5b  call    cs:__imp_LeaveCriticalSection
0x140090a61  jmp     loc_1400909CB
0x140090a66  mov     [rbp+3Fh+var_98], 0
0x140090a6e  mov     rcx, [rsi]
0x140090a71  mov     rax, [rcx]
0x140090a74  mov     [rbp+3Fh+var_98], 0
0x140090a7c  lea     r9, [rbp+3Fh+var_98]
0x140090a80  lea     r8, _GUID_39f25818_c4a0_46b1_b7ac_01b630b00c7d
0x140090a87  lea     rdx, SID_AudioDspServiceProviderService
0x140090a8e  mov     rax, [rax+18h]
0x140090a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090a97  mov     ebx, eax
0x140090a99  test    eax, eax
0x140090a9b  jns     short loc_140090AC1
0x140090a9d  mov     edx, 2F0h; void *
0x140090aa2  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140090aa9  mov     r9d, ebx; char *
0x140090aac  mov     rcx, [rbp+47h]; this
0x140090ab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140090ab5  nop
0x140090ab6  lea     rcx, [rbp+3Fh+var_98]
0x140090aba  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x140090abf  jmp     short loc_140090A4E
0x140090ac1  mov     rcx, [rbp+3Fh+var_98]
0x140090ac5  mov     rax, [rcx]
0x140090ac8  mov     rdx, r14
0x140090acb  mov     rax, [rax+18h]
0x140090acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090ad4  mov     ebx, eax
0x140090ad6  test    eax, eax
0x140090ad8  jns     short loc_140090AE1
0x140090ada  mov     edx, 2F1h
0x140090adf  jmp     short loc_140090AA2
0x140090ae1  lea     rcx, [rbp+3Fh+var_98]
0x140090ae5  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x140090aea  nop
0x140090aeb  mov     rcx, [rbp+3Fh+lpCriticalSection]; lpCriticalSection
0x140090aef  test    rcx, rcx
0x140090af2  jz      short loc_140090AFB
0x140090af4  call    cs:__imp_LeaveCriticalSection
0x140090afa  nop
0x140090afb  mov     rcx, [rbp+3Fh+var_90]
0x140090aff  test    rcx, rcx
0x140090b02  jz      short loc_140090B0A
0x140090b04  call    cs:__imp_CoRevokeDeviceCatalog
0x140090b0a  mov     r14, [rsi]
0x140090b0d  mov     rax, [r14]
0x140090b10  mov     r15, [rax+18h]
0x140090b14  lea     rbx, [rdi+70h]
0x140090b18  mov     rdx, [rbx]
0x140090b1b  mov     qword ptr [rbx], 0
0x140090b22  test    rdx, rdx
0x140090b25  jz      short loc_140090B37
0x140090b27  mov     rcx, [rdx]
0x140090b2a  mov     rax, [rcx+10h]
0x140090b2e  mov     rcx, rdx
0x140090b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090b36  nop
0x140090b37  mov     r9, rbx
0x140090b3a  lea     r8, _GUID_0ead8f8d_6c3b_4754_a435_374fe81b878e
0x140090b41  lea     rdx, SID_AudioPumpDspDriverService
0x140090b48  mov     rcx, r14
0x140090b4b  mov     rax, r15
0x140090b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090b53  mov     r14d, eax
0x140090b56  test    eax, eax
0x140090b58  jns     short loc_140090B7A
0x140090b5a  mov     rcx, [rbp+47h]; this
0x140090b5e  mov     r9d, eax; char *
0x140090b61  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140090b68  mov     edx, 2F5h; void *
0x140090b6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140090b72  mov     eax, r14d
0x140090b75  jmp     loc_140090D28
0x140090b7a  mov     r14, [rsi]
0x140090b7d  mov     rax, [r14]
0x140090b80  mov     r15, [rax+18h]
0x140090b84  lea     rsi, [rdi+68h]
0x140090b88  mov     rdx, [rsi]
0x140090b8b  mov     qword ptr [rsi], 0
0x140090b92  test    rdx, rdx
0x140090b95  jz      short loc_140090BA7
0x140090b97  mov     rcx, [rdx]
0x140090b9a  mov     rax, [rcx+10h]
0x140090b9e  mov     rcx, rdx
0x140090ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090ba6  nop
0x140090ba7  mov     r9, rsi
0x140090baa  lea     r8, _GUID_64741865_eaba_478d_ac58_fa9e4b81a170
0x140090bb1  lea     rdx, SID_DspAudioEngineService
0x140090bb8  mov     rcx, r14
0x140090bbb  mov     rax, r15
0x140090bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090bc3  mov     esi, eax
0x140090bc5  test    eax, eax
0x140090bc7  jns     short loc_140090BE8
0x140090bc9  mov     rcx, [rbp+47h]; this
0x140090bcd  mov     r9d, eax; char *
0x140090bd0  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140090bd7  mov     edx, 2F6h; void *
0x140090bdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140090be1  mov     eax, esi
0x140090be3  jmp     loc_140090D28
0x140090be8  mov     rcx, [rbx]
0x140090beb  mov     rax, [rcx]
0x140090bee  mov     rax, [rax+18h]
0x140090bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090bf7  mov     [rdi+48h], eax
0x140090bfa  lea     rax, [rdi+0A0h]
0x140090c01  mov     [rbp+3Fh+lpCriticalSection], rax
0x140090c05  lea     rsi, [rdi+98h]
0x140090c0c  mov     rcx, [rsi]
0x140090c0f  mov     qword ptr [rsi], 0
0x140090c16  test    rcx, rcx
0x140090c19  jz      short loc_140090C28
0x140090c1b  mov     rax, [rcx]
0x140090c1e  mov     rax, [rax+10h]
0x140090c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090c27  nop
0x140090c28  mov     [rbp+3Fh+var_90], rsi
0x140090c2c  lea     rax, [rdi+90h]
0x140090c33  mov     [rbp+3Fh+var_98], rax
0x140090c37  lea     rsi, [rdi+88h]
0x140090c3e  mov     rcx, [rsi]
0x140090c41  mov     qword ptr [rsi], 0
0x140090c48  test    rcx, rcx
0x140090c4b  jz      short loc_140090C5A
0x140090c4d  mov     rax, [rcx]
0x140090c50  mov     rax, [rax+10h]
0x140090c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090c59  nop
0x140090c5a  mov     [rbp+3Fh+var_80], rsi
0x140090c5e  mov     rcx, [rbx]
0x140090c61  mov     rax, [rcx]
0x140090c64  mov     rax, [rax+20h]
0x140090c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090c6d  mov     [rbp+3Fh+var_88], rax
0x140090c71  lea     rbx, [rdi+78h]
0x140090c75  mov     rcx, [rbx]
0x140090c78  mov     qword ptr [rbx], 0
0x140090c7f  test    rcx, rcx
0x140090c82  jz      short loc_140090C91
0x140090c84  mov     rax, [rcx]
0x140090c87  mov     rax, [rax+10h]
0x140090c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090c90  nop
0x140090c91  lea     rax, [rbp+3Fh+lpCriticalSection]
0x140090c95  mov     [rsp+0E0h+var_B0], rax
0x140090c9a  lea     rax, [rbp+3Fh+var_90]
0x140090c9e  mov     [rsp+0E0h+var_B8], rax
0x140090ca3  lea     rax, [rbp+3Fh+var_98]
0x140090ca7  mov     [rsp+0E0h+ppv], rax
0x140090cac  lea     r9, [rbp+3Fh+var_80]
0x140090cb0  lea     rdx, [rbp+3Fh+var_88]
0x140090cb4  mov     rcx, rbx
0x140090cb7  call    ??$MakeAndInitialize@VCAudioDg_Driver@@UIAudioDgDriver@@PEAXPEAXPEAPEAUIAudioPumpDspBuffer@@PEAIPEAPEAU3@PEAI@Details@WRL@Microsoft@@YAJPEAPEAUIAudioDgDriver@@$$QEAPEAX1$$QEAPEAPEAUIAudioPumpDspBuffer@@$$QEAPEAI23@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioDg_Driver,IAudioDgDriver,void *,void *,IAudioPumpDspBuffer * *,uint *,IAudioPumpDspBuffer * *,uint *>(IAudioDgDriver * *,void * &&,void * &&,IAudioPumpDspBuffer * * &&,uint * &&,IAudioPumpDspBuffer * * &&,uint * &&)
0x140090cbc  mov     ebx, eax
0x140090cbe  test    eax, eax
0x140090cc0  jns     short loc_140090CCC
0x140090cc2  mov     edx, 2FEh
0x140090cc7  jmp     loc_140090957
0x140090ccc  lea     rax, off_1400BDDC0
0x140090cd3  mov     [rbp+3Fh+var_78], rax
0x140090cd7  mov     [rbp+3Fh+var_70], rdi
0x140090cdb  lea     rax, [rbp+3Fh+var_78]
0x140090cdf  mov     [rbp+3Fh+var_40], rax
0x140090ce3  lea     r9, [rdi+0C0h]
0x140090cea  lea     r8, [rbp+3Fh+var_78]
0x140090cee  mov     rdx, [r12]
0x140090cf2  mov     rcx, [rdi+0B0h]
0x140090cf9  call    ?QueueWaitItem@CSerialWorkQueue@@QEAAJPEAXV?$function@$$A6AXXZ@std@@AEAV?$unique_ptr@U_WaitTask@@U?$default_delete@U_WaitTask@@@std@@@3@@Z; CSerialWorkQueue::QueueWaitItem(void *,std::function<void (void)>,std::unique_ptr<_WaitTask> &)
0x140090cfe  mov     ebx, eax
0x140090d00  test    eax, eax
0x140090d02  jns     short loc_140090D0E
0x140090d04  mov     edx, 301h
  ... truncated ...
```
