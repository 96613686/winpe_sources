# AudioEffectsWatcher::RuntimeClassInitialize(ushort const *,ulong,int,DiscoverySettings)

- ea: `0x18002ccbc`
- end: `0x18002d076`
- name: `?RuntimeClassInitialize@AudioEffectsWatcher@@QEAAJPEBGKHW4DiscoverySettings@@@Z`
- size: `954`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800de334`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x18001e7dc`
- `0x180020f74`
- `0x18002ccbc`
- `0x18002e198`
- `0x18002e1f4`
- `0x18002e250`
- `0x18002ee3c`
- `0x180032e9c`
- `0x1800669e0`
- `0x1800aedc0`
- `0x1800aefc4`
- `0x1800b6978`
- `0x1800cf8c0`
- `0x1800dee60`
- `0x18016b010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18002cd16`
- `ntdll!EtwEventActivityIdControl` at `0x18002d019`
- `ntdll!EtwEventActivityIdControl` at `0x18002cd16`
- `ntdll!EtwEventActivityIdControl` at `0x18002d019`
- `ntdll!RtlPublishWnfStateData` at `0x18002d061`
- `ntdll!RtlPublishWnfStateData` at `0x18002d061`
- `ntdll!NtCreateWnfStateName` at `0x18002ce5b`
- `ntdll!NtCreateWnfStateName` at `0x18002ce5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cf58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cf58`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002cdff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002cdff`

## string_xrefs

- `0x18002cd6b`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002cdc3`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002ce0d`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002ce6a`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002cec0`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002cf22`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002cfd0`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AudioEffectsWatcher::RuntimeClassInitialize(__int64 a1, __int64 a2, int a3, int a4, int a5)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // ebx
  int v12; // eax
  const char *v13; // r9
  int LastError; // eax
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  _QWORD *v18; // rdi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rcx
  struct CSerialWorkQueue *SerialWorkQueue; // rax
  int v24; // eax
  int v26; // [rsp+20h] [rbp-A1h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-81h] BYREF
  __int64 v28; // [rsp+48h] [rbp-79h] BYREF
  EffectPack *v29[2]; // [rsp+50h] [rbp-71h] BYREF
  __int64 v30; // [rsp+60h] [rbp-61h]
  __int64 v31; // [rsp+68h] [rbp-59h] BYREF
  __int64 v32; // [rsp+70h] [rbp-51h] BYREF
  __int64 v33; // [rsp+78h] [rbp-49h] BYREF
  __int64 v34; // [rsp+80h] [rbp-41h] BYREF
  char v35; // [rsp+88h] [rbp-39h]
  _QWORD v36[8]; // [rsp+90h] [rbp-31h] BYREF
  __int64 v37; // [rsp+D0h] [rbp+Fh] BYREF
  __int128 v38; // [rsp+D8h] [rbp+17h]
  _QWORD v39[2]; // [rsp+E8h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v31 = a2;
  v38 = *(_OWORD *)(a1 + 40);
  v39[0] = *(_QWORD *)(a1 + 40);
  v39[1] = *(_QWORD *)(a1 + 48);
  EtwEventActivityIdControl(4, v39);
  *(_DWORD *)(a1 + 180) = a3;
  *(_DWORD *)(a1 + 184) = a4;
  *(_DWORD *)(a1 + 188) = a5;
  v33 = a1 + 56;
  v34 = 0;
  v35 = 1;
  v11 = _AllocString<CTCoAllocPolicy>(v10, v9, a2, &v34);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v33);
  if ( v11 >= 0 )
  {
    *(_OWORD *)v29 = 0;
    v30 = 0;
    v12 = (*(__int64 (__fastcall **)(PVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)g_pEndpointCharacteristicsCache + 40LL))(
            g_pEndpointCharacteristicsCache,
            *(_QWORD *)(a1 + 56),
            0,
            0);
    v11 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioeffectsdiscovery.cpp",
        (const char *)(unsigned int)v12,
        (int)v29);
LABEL_5:
      EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v29);
      goto LABEL_28;
    }
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:P(A;;GA;;;WD)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-1692970155-4054893335-185714091-3362601943-3526593181-1159"
             "816984-2199008581-497492991)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6D,
                    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioeffectsdiscovery.cpp",
                    v13);
LABEL_8:
      v11 = LastError;
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
      goto LABEL_5;
    }
    v37 = 0;
    v15 = NtCreateWnfStateName(&v37, 3, 0);
    if ( v15 < 0 )
    {
      v16 = 122;
LABEL_12:
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)v16,
                    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioeffectsdiscovery.cpp",
                    (const char *)(unsigned int)v15,
                    0);
      goto LABEL_8;
    }
    *(_QWORD *)(a1 + 92) = v37;
    *(_BYTE *)(a1 + 88) = 1;
    if ( (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes(v29[1], eHostProcessConnector) )
    {
      v18 = (_QWORD *)(a1 + 152);
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(a1 + 152, 0, v17, 0);
      v11 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x87,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioeffectsdiscovery.cpp",
          (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
          0);
        goto LABEL_9;
      }
      v32 = *v18;
      v28 = 0;
      if ( (int)Microsoft::WRL::Details::MakeAndInitialize<AudioEffectsWatcher::CMMNotificationDelegator,IMMNotificationClient,unsigned short const * &,void *>(
                  &v28,
                  &v31,
                  &v32) >= 0 )
      {
        v20 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, __int64))g_DeviceEnumerator->lpVtbl->RegisterEndpointNotificationCallback)(
                g_DeviceEnumerator,
                v28);
        v11 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8D,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioeffectsdiscovery.cpp",
            (const char *)(unsigned int)v20,
            0);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( SecurityDescriptor )
            LocalFree(SecurityDescriptor);
          goto LABEL_5;
        }
        v21 = v28;
        v28 = 0;
        v22 = *(_QWORD *)(a1 + 80);
        *(_QWORD *)(a1 + 80) = v21;
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      AudioEffectsWatcher::RebuildAndPublishFullEffectsListFromApos((AudioEffectsWatcher *)a1);
      SerialWorkQueue = GetSerialWorkQueue();
      v36[0] = off_1801724B0;
      v36[1] = a1;
      v36[7] = v36;
      v24 = CSerialWorkQueue::QueueRecurringWaitItem(SerialWorkQueue, *v18, v36, a1 + 160);
      v11 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x97,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioeffectsdiscovery.cpp",
          (const char *)(unsigned int)v24,
          0);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
        goto LABEL_9;
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
    }
    else
    {
      v15 = RtlPublishWnfStateData(*(_QWORD *)(a1 + 92), 0, &unk_18018D3C8, 16);
      if ( v15 < 0 )
      {
        v16 = 156;
        goto LABEL_12;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v29);
    v11 = 0;
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioeffectsdiscovery.cpp",
    (const char *)(unsigned int)v11,
    v26);
LABEL_28:
  EtwEventActivityIdControl(4, v39);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002ccbc  mov     [rsp-8+arg_10], rbx
0x18002ccc1  mov     [rsp-8+arg_18], rsi
0x18002ccc6  push    rbp
0x18002ccc7  push    rdi
0x18002ccc8  push    r14
0x18002ccca  lea     rbp, [rsp-3Fh]
0x18002cccf  sub     rsp, 100h
0x18002ccd6  mov     rax, cs:__security_cookie
0x18002ccdd  xor     rax, rsp
0x18002cce0  mov     [rbp+4Fh+var_18], rax
0x18002cce4  mov     edi, r9d
0x18002cce7  mov     ebx, r8d
0x18002ccea  mov     rsi, rdx
0x18002cced  mov     r14, rcx
0x18002ccf0  mov     [rbp+4Fh+var_A8], rdx
0x18002ccf4  movups  xmm0, xmmword ptr [rcx+28h]
0x18002ccf8  movdqu  [rbp+4Fh+var_38], xmm0
0x18002ccfd  mov     rax, [rcx+28h]
0x18002cd01  mov     [rbp+4Fh+var_28], rax
0x18002cd05  mov     rax, [rcx+30h]
0x18002cd09  mov     [rbp+4Fh+var_20], rax
0x18002cd0d  lea     rdx, [rbp+4Fh+var_28]
0x18002cd11  mov     ecx, 4
0x18002cd16  call    cs:__imp_EtwEventActivityIdControl
0x18002cd1c  nop
0x18002cd1d  mov     [r14+0B4h], ebx
0x18002cd24  mov     [r14+0B8h], edi
0x18002cd2b  mov     eax, [rbp+4Fh+arg_20]
0x18002cd2e  mov     [r14+0BCh], eax
0x18002cd35  lea     rdi, [r14+38h]
0x18002cd39  mov     [rbp+4Fh+var_98], rdi
0x18002cd3d  mov     [rbp+4Fh+var_90], 0
0x18002cd45  mov     [rbp+4Fh+var_88], 1
0x18002cd49  lea     r9, [rbp+4Fh+var_90]
0x18002cd4d  mov     r8, rsi
0x18002cd50  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18002cd55  mov     ebx, eax
0x18002cd57  lea     rcx, [rbp+4Fh+var_98]
0x18002cd5b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18002cd60  test    ebx, ebx
0x18002cd62  jns     short loc_18002CD81
0x18002cd64  mov     rcx, [rbp+57h]; this
0x18002cd68  mov     r9d, ebx; char *
0x18002cd6b  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002cd72  mov     edx, 5Eh ; '^'; void *
0x18002cd77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd7c  jmp     loc_18002D010
0x18002cd81  xorps   xmm0, xmm0
0x18002cd84  movdqu  xmmword ptr [rbp+4Fh+var_C0], xmm0
0x18002cd89  mov     [rbp+4Fh+var_B0], 0
0x18002cd91  mov     rcx, cs:?g_pEndpointCharacteristicsCache@@3PEAUIEndpointCharacteristicsCache@@EA; IEndpointCharacteristicsCache * g_pEndpointCharacteristicsCache
0x18002cd98  mov     rax, [rcx]
0x18002cd9b  lea     rdx, [rbp+4Fh+var_C0]
0x18002cd9f  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x18002cda4  xor     r9d, r9d
0x18002cda7  xor     r8d, r8d
0x18002cdaa  mov     rdx, [rdi]
0x18002cdad  mov     rax, [rax+28h]
0x18002cdb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdb6  mov     ebx, eax
0x18002cdb8  test    eax, eax
0x18002cdba  jns     short loc_18002CDE3
0x18002cdbc  mov     rcx, [rbp+57h]; this
0x18002cdc0  mov     r9d, eax; char *
0x18002cdc3  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002cdca  mov     edx, 61h ; 'a'; void *
0x18002cdcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cdd4  nop
0x18002cdd5  lea     rcx, [rbp+4Fh+var_C0]; this
0x18002cdd9  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x18002cdde  jmp     loc_18002D010
0x18002cde3  mov     [rsp+110h+SecurityDescriptor], 0
0x18002cdec  xor     r9d, r9d; SecurityDescriptorSize
0x18002cdef  lea     r8, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x18002cdf4  lea     edx, [r9+1]; StringSDRevision
0x18002cdf8  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;WD)(A;;GR;;;AC)(A;;GR;;;S-1"...
0x18002cdff  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002ce05  test    eax, eax
0x18002ce07  jnz     short loc_18002CE2A
0x18002ce09  mov     rcx, [rbp+57h]; this
0x18002ce0d  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002ce14  lea     edx, [rax+6Dh]; void *
0x18002ce17  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ce1c  mov     ebx, eax
0x18002ce1e  lea     rcx, [rsp+110h+SecurityDescriptor]
0x18002ce23  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ce28  jmp     short loc_18002CDD5
0x18002ce2a  mov     [rbp+4Fh+var_40], 0
0x18002ce32  mov     rax, [rsp+110h+SecurityDescriptor]
0x18002ce37  mov     [rsp+110h+var_E0], rax
0x18002ce3c  mov     [rsp+110h+var_E8], 640h
0x18002ce44  mov     qword ptr [rsp+110h+var_F0], 0; int
0x18002ce4d  xor     r9d, r9d
0x18002ce50  xor     r8d, r8d
0x18002ce53  lea     edx, [r9+3]
0x18002ce57  lea     rcx, [rbp+4Fh+var_40]
0x18002ce5b  call    cs:__imp_NtCreateWnfStateName
0x18002ce61  test    eax, eax
0x18002ce63  jns     short loc_18002CE7F
0x18002ce65  mov     edx, 7Ah ; 'z'; void *
0x18002ce6a  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002ce71  mov     r9d, eax; char *
0x18002ce74  mov     rcx, [rbp+57h]; this
0x18002ce78  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002ce7d  jmp     short loc_18002CE1C
0x18002ce7f  mov     rax, [rbp+4Fh+var_40]
0x18002ce83  mov     [r14+5Ch], rax
0x18002ce87  mov     byte ptr [r14+58h], 1
0x18002ce8c  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18002ce8e  mov     rcx, [rbp+4Fh+var_C0+8]; this
0x18002ce92  call    ?EndpointConnectorSupportsProcessingModes@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::EndpointConnectorSupportsProcessingModes(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x18002ce97  test    eax, eax
0x18002ce99  jz      loc_18002D045
0x18002ce9f  lea     rdi, [r14+98h]
0x18002cea6  xor     r9d, r9d
0x18002cea9  xor     edx, edx
0x18002ceab  mov     rcx, rdi
0x18002ceae  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002ceb3  mov     ebx, eax
0x18002ceb5  test    eax, eax
0x18002ceb7  jns     short loc_18002CED6
0x18002ceb9  mov     rcx, [rbp+57h]; this
0x18002cebd  mov     r9d, eax; char *
0x18002cec0  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002cec7  mov     edx, 87h; void *
0x18002cecc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ced1  jmp     loc_18002CE1E
0x18002ced6  mov     rax, [rdi]
0x18002ced9  mov     [rbp+4Fh+var_A0], rax
0x18002cedd  mov     [rbp+4Fh+var_C8], 0
0x18002cee5  lea     r8, [rbp+4Fh+var_A0]
0x18002cee9  lea     rdx, [rbp+4Fh+var_A8]
0x18002ceed  lea     rcx, [rbp+4Fh+var_C8]
0x18002cef1  call    ??$MakeAndInitialize@VCMMNotificationDelegator@AudioEffectsWatcher@@UIMMNotificationClient@@AEAPEBGPEAX@Details@WRL@Microsoft@@YAJPEAPEAUIMMNotificationClient@@AEAPEBG$$QEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<AudioEffectsWatcher::CMMNotificationDelegator,IMMNotificationClient,ushort const * &,void *>(IMMNotificationClient * *,ushort const * &,void * &&)
0x18002cef6  test    eax, eax
0x18002cef8  js      loc_18002CF89
0x18002cefe  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18002cf05  mov     rax, [rcx]
0x18002cf08  mov     rdx, [rbp+4Fh+var_C8]
0x18002cf0c  mov     rax, [rax+30h]
0x18002cf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf15  mov     ebx, eax
0x18002cf17  test    eax, eax
0x18002cf19  jns     short loc_18002CF63
0x18002cf1b  mov     rcx, [rbp+57h]; this
0x18002cf1f  mov     r9d, eax; char *
0x18002cf22  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002cf29  mov     edx, 8Dh; void *
0x18002cf2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cf33  nop
0x18002cf34  mov     rcx, [rbp+4Fh+var_C8]
0x18002cf38  test    rcx, rcx
0x18002cf3b  jz      short loc_18002CF4A
0x18002cf3d  mov     rax, [rcx]
0x18002cf40  mov     rax, [rax+10h]
0x18002cf44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf49  nop
0x18002cf4a  mov     rcx, [rsp+110h+SecurityDescriptor]; hMem
0x18002cf4f  test    rcx, rcx
0x18002cf52  jz      loc_18002CDD5
0x18002cf58  call    cs:__imp_LocalFree
0x18002cf5e  jmp     loc_18002CDD5
0x18002cf63  mov     rax, [rbp+4Fh+var_C8]
0x18002cf67  mov     [rbp+4Fh+var_C8], 0
0x18002cf6f  mov     rcx, [r14+50h]
0x18002cf73  mov     [r14+50h], rax
0x18002cf77  test    rcx, rcx
0x18002cf7a  jz      short loc_18002CF89
0x18002cf7c  mov     rax, [rcx]
0x18002cf7f  mov     rax, [rax+10h]
0x18002cf83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf88  nop
0x18002cf89  mov     rcx, r14; this
0x18002cf8c  call    ?RebuildAndPublishFullEffectsListFromApos@AudioEffectsWatcher@@AEAAJXZ; AudioEffectsWatcher::RebuildAndPublishFullEffectsListFromApos(void)
0x18002cf91  call    ?GetSerialWorkQueue@@YAAEAVCSerialWorkQueue@@XZ; GetSerialWorkQueue(void)
0x18002cf96  lea     rcx, off_1801724B0
0x18002cf9d  mov     [rbp+4Fh+var_80], rcx
0x18002cfa1  mov     [rbp+4Fh+var_78], r14
0x18002cfa5  lea     rcx, [rbp+4Fh+var_80]
0x18002cfa9  mov     [rbp+4Fh+var_48], rcx
0x18002cfad  lea     r9, [r14+0A0h]
0x18002cfb4  lea     r8, [rbp+4Fh+var_80]
0x18002cfb8  mov     rdx, [rdi]
0x18002cfbb  mov     rcx, rax
0x18002cfbe  call    ?QueueRecurringWaitItem@CSerialWorkQueue@@QEAAJPEAXV?$function@$$A6AXXZ@std@@AEAV?$unique_ptr@U_WaitTask@@U?$default_delete@U_WaitTask@@@std@@@3@@Z; CSerialWorkQueue::QueueRecurringWaitItem(void *,std::function<void (void)>,std::unique_ptr<_WaitTask> &)
0x18002cfc3  mov     ebx, eax
0x18002cfc5  test    eax, eax
0x18002cfc7  jns     short loc_18002CFF0
0x18002cfc9  mov     rcx, [rbp+57h]; this
0x18002cfcd  mov     r9d, eax; char *
0x18002cfd0  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002cfd7  mov     edx, 97h; void *
0x18002cfdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cfe1  nop
0x18002cfe2  lea     rcx, [rbp+4Fh+var_C8]
0x18002cfe6  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18002cfeb  jmp     loc_18002CE1E
0x18002cff0  lea     rcx, [rbp+4Fh+var_C8]
0x18002cff4  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18002cff9  nop
0x18002cffa  lea     rcx, [rsp+110h+SecurityDescriptor]
0x18002cfff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d004  nop
0x18002d005  lea     rcx, [rbp+4Fh+var_C0]; this
0x18002d009  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x18002d00e  xor     ebx, ebx
0x18002d010  lea     rdx, [rbp+4Fh+var_28]
0x18002d014  mov     ecx, 4
0x18002d019  call    cs:__imp_EtwEventActivityIdControl
0x18002d01f  mov     eax, ebx
0x18002d021  mov     rcx, [rbp+4Fh+var_18]
0x18002d025  xor     rcx, rsp; StackCookie
0x18002d028  call    __security_check_cookie
0x18002d02d  lea     r11, [rsp+110h+var_10]
0x18002d035  mov     rbx, [r11+30h]
0x18002d039  mov     rsi, [r11+38h]
0x18002d03d  mov     rsp, r11
0x18002d040  pop     r14
0x18002d042  pop     rdi
0x18002d043  pop     rbp
0x18002d044  retn
0x18002d045  mov     qword ptr [rsp+110h+var_F0], 0
0x18002d04e  mov     r9d, 10h
0x18002d054  lea     r8, unk_18018D3C8
0x18002d05b  xor     edx, edx
0x18002d05d  mov     rcx, [r14+5Ch]
0x18002d061  call    cs:__imp_RtlPublishWnfStateData
0x18002d067  test    eax, eax
0x18002d069  jns     short loc_18002CFFA
0x18002d06b  mov     edx, 9Ch
0x18002d070  jmp     loc_18002CE6A
```
