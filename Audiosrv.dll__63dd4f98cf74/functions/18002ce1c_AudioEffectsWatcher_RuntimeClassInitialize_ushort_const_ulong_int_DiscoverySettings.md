# AudioEffectsWatcher::RuntimeClassInitialize(ushort const *,ulong,int,DiscoverySettings)

- ea: `0x18002ce1c`
- end: `0x18002d1d6`
- name: `?RuntimeClassInitialize@AudioEffectsWatcher@@QEAAJPEBGKHW4DiscoverySettings@@@Z`
- size: `954`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800dc344`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x18001e92c`
- `0x1800210c4`
- `0x18002ce1c`
- `0x18002e2f8`
- `0x18002e354`
- `0x18002e3b0`
- `0x18002ef9c`
- `0x180032ffc`
- `0x180066550`
- `0x1800ad0c0`
- `0x1800ad2c4`
- `0x1800b4c88`
- `0x1800cd8d0`
- `0x1800dce70`
- `0x18016c010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18002ce76`
- `ntdll!EtwEventActivityIdControl` at `0x18002d179`
- `ntdll!EtwEventActivityIdControl` at `0x18002ce76`
- `ntdll!EtwEventActivityIdControl` at `0x18002d179`
- `ntdll!RtlPublishWnfStateData` at `0x18002d1c1`
- `ntdll!RtlPublishWnfStateData` at `0x18002d1c1`
- `ntdll!NtCreateWnfStateName` at `0x18002cfbb`
- `ntdll!NtCreateWnfStateName` at `0x18002cfbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d0b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d0b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002cf5f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002cf5f`

## string_xrefs

- `0x18002cecb`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002cf23`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002cf6d`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002cfca`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002d020`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002d082`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`
- `0x18002d130`: `avcore\audiocore\server\audiosrv\dll\audioeffectsdiscovery.cpp`

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
  _QWORD *v17; // rdi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  struct CSerialWorkQueue *SerialWorkQueue; // rax
  int v23; // eax
  int v25; // [rsp+20h] [rbp-A1h]
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
    v26 = 0;
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
                    v26);
      goto LABEL_8;
    }
    *(_QWORD *)(a1 + 92) = v37;
    *(_BYTE *)(a1 + 88) = 1;
    if ( (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes(v29[1], eHostProcessConnector) )
    {
      v17 = (_QWORD *)(a1 + 152);
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(a1 + 152, 0);
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
      v32 = *v17;
      v28 = 0;
      if ( (int)Microsoft::WRL::Details::MakeAndInitialize<AudioEffectsWatcher::CMMNotificationDelegator,IMMNotificationClient,unsigned short const * &,void *>(
                  &v28,
                  &v31,
                  &v32) >= 0 )
      {
        v19 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, __int64))g_DeviceEnumerator->lpVtbl->RegisterEndpointNotificationCallback)(
                g_DeviceEnumerator,
                v28);
        v11 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8D,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioeffectsdiscovery.cpp",
            (const char *)(unsigned int)v19,
            0);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( SecurityDescriptor )
            LocalFree(SecurityDescriptor);
          goto LABEL_5;
        }
        v20 = v28;
        v28 = 0;
        v21 = *(_QWORD *)(a1 + 80);
        *(_QWORD *)(a1 + 80) = v20;
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      AudioEffectsWatcher::RebuildAndPublishFullEffectsListFromApos((AudioEffectsWatcher *)a1);
      SerialWorkQueue = GetSerialWorkQueue();
      v36[0] = off_180173490;
      v36[1] = a1;
      v36[7] = v36;
      v23 = CSerialWorkQueue::QueueRecurringWaitItem(SerialWorkQueue, *v17, v36, a1 + 160);
      v11 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x97,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioeffectsdiscovery.cpp",
          (const char *)(unsigned int)v23,
          0);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
        goto LABEL_9;
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
    }
    else
    {
      v15 = RtlPublishWnfStateData(*(_QWORD *)(a1 + 92), 0, qword_18018E418, 16, 0);
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
    v25);
LABEL_28:
  EtwEventActivityIdControl(4, v39);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002ce1c  mov     [rsp-8+arg_10], rbx
0x18002ce21  mov     [rsp-8+arg_18], rsi
0x18002ce26  push    rbp
0x18002ce27  push    rdi
0x18002ce28  push    r14
0x18002ce2a  lea     rbp, [rsp-3Fh]
0x18002ce2f  sub     rsp, 100h
0x18002ce36  mov     rax, cs:__security_cookie
0x18002ce3d  xor     rax, rsp
0x18002ce40  mov     [rbp+4Fh+var_18], rax
0x18002ce44  mov     edi, r9d
0x18002ce47  mov     ebx, r8d
0x18002ce4a  mov     rsi, rdx
0x18002ce4d  mov     r14, rcx
0x18002ce50  mov     [rbp+4Fh+var_A8], rdx
0x18002ce54  movups  xmm0, xmmword ptr [rcx+28h]
0x18002ce58  movdqu  [rbp+4Fh+var_38], xmm0
0x18002ce5d  mov     rax, [rcx+28h]
0x18002ce61  mov     [rbp+4Fh+var_28], rax
0x18002ce65  mov     rax, [rcx+30h]
0x18002ce69  mov     [rbp+4Fh+var_20], rax
0x18002ce6d  lea     rdx, [rbp+4Fh+var_28]
0x18002ce71  mov     ecx, 4
0x18002ce76  call    cs:__imp_EtwEventActivityIdControl
0x18002ce7c  nop
0x18002ce7d  mov     [r14+0B4h], ebx
0x18002ce84  mov     [r14+0B8h], edi
0x18002ce8b  mov     eax, [rbp+4Fh+arg_20]
0x18002ce8e  mov     [r14+0BCh], eax
0x18002ce95  lea     rdi, [r14+38h]
0x18002ce99  mov     [rbp+4Fh+var_98], rdi
0x18002ce9d  mov     [rbp+4Fh+var_90], 0
0x18002cea5  mov     [rbp+4Fh+var_88], 1
0x18002cea9  lea     r9, [rbp+4Fh+var_90]
0x18002cead  mov     r8, rsi
0x18002ceb0  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18002ceb5  mov     ebx, eax
0x18002ceb7  lea     rcx, [rbp+4Fh+var_98]
0x18002cebb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18002cec0  test    ebx, ebx
0x18002cec2  jns     short loc_18002CEE1
0x18002cec4  mov     rcx, [rbp+57h]; this
0x18002cec8  mov     r9d, ebx; char *
0x18002cecb  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002ced2  mov     edx, 5Eh ; '^'; void *
0x18002ced7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cedc  jmp     loc_18002D170
0x18002cee1  xorps   xmm0, xmm0
0x18002cee4  movdqu  xmmword ptr [rbp+4Fh+var_C0], xmm0
0x18002cee9  mov     [rbp+4Fh+var_B0], 0
0x18002cef1  mov     rcx, cs:?g_pEndpointCharacteristicsCache@@3PEAUIEndpointCharacteristicsCache@@EA; IEndpointCharacteristicsCache * g_pEndpointCharacteristicsCache
0x18002cef8  mov     rax, [rcx]
0x18002cefb  lea     rdx, [rbp+4Fh+var_C0]
0x18002ceff  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x18002cf04  xor     r9d, r9d
0x18002cf07  xor     r8d, r8d
0x18002cf0a  mov     rdx, [rdi]
0x18002cf0d  mov     rax, [rax+28h]
0x18002cf11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf16  mov     ebx, eax
0x18002cf18  test    eax, eax
0x18002cf1a  jns     short loc_18002CF43
0x18002cf1c  mov     rcx, [rbp+57h]; this
0x18002cf20  mov     r9d, eax; char *
0x18002cf23  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002cf2a  mov     edx, 61h ; 'a'; void *
0x18002cf2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cf34  nop
0x18002cf35  lea     rcx, [rbp+4Fh+var_C0]; this
0x18002cf39  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x18002cf3e  jmp     loc_18002D170
0x18002cf43  mov     [rsp+110h+SecurityDescriptor], 0
0x18002cf4c  xor     r9d, r9d; SecurityDescriptorSize
0x18002cf4f  lea     r8, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x18002cf54  lea     edx, [r9+1]; StringSDRevision
0x18002cf58  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;WD)(A;;GR;;;AC)(A;;GR;;;S-1"...
0x18002cf5f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002cf65  test    eax, eax
0x18002cf67  jnz     short loc_18002CF8A
0x18002cf69  mov     rcx, [rbp+57h]; this
0x18002cf6d  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002cf74  lea     edx, [rax+6Dh]; void *
0x18002cf77  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cf7c  mov     ebx, eax
0x18002cf7e  lea     rcx, [rsp+110h+SecurityDescriptor]
0x18002cf83  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cf88  jmp     short loc_18002CF35
0x18002cf8a  mov     [rbp+4Fh+var_40], 0
0x18002cf92  mov     rax, [rsp+110h+SecurityDescriptor]
0x18002cf97  mov     [rsp+110h+var_E0], rax
0x18002cf9c  mov     [rsp+110h+var_E8], 640h
0x18002cfa4  mov     qword ptr [rsp+110h+var_F0], 0; int
0x18002cfad  xor     r9d, r9d
0x18002cfb0  xor     r8d, r8d
0x18002cfb3  lea     edx, [r9+3]
0x18002cfb7  lea     rcx, [rbp+4Fh+var_40]
0x18002cfbb  call    cs:__imp_NtCreateWnfStateName
0x18002cfc1  test    eax, eax
0x18002cfc3  jns     short loc_18002CFDF
0x18002cfc5  mov     edx, 7Ah ; 'z'; void *
0x18002cfca  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002cfd1  mov     r9d, eax; char *
0x18002cfd4  mov     rcx, [rbp+57h]; this
0x18002cfd8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002cfdd  jmp     short loc_18002CF7C
0x18002cfdf  mov     rax, [rbp+4Fh+var_40]
0x18002cfe3  mov     [r14+5Ch], rax
0x18002cfe7  mov     byte ptr [r14+58h], 1
0x18002cfec  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18002cfee  mov     rcx, [rbp+4Fh+var_C0+8]; this
0x18002cff2  call    ?EndpointConnectorSupportsProcessingModes@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::EndpointConnectorSupportsProcessingModes(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x18002cff7  test    eax, eax
0x18002cff9  jz      loc_18002D1A5
0x18002cfff  lea     rdi, [r14+98h]
0x18002d006  xor     r9d, r9d
0x18002d009  xor     edx, edx
0x18002d00b  mov     rcx, rdi
0x18002d00e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002d013  mov     ebx, eax
0x18002d015  test    eax, eax
0x18002d017  jns     short loc_18002D036
0x18002d019  mov     rcx, [rbp+57h]; this
0x18002d01d  mov     r9d, eax; char *
0x18002d020  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002d027  mov     edx, 87h; void *
0x18002d02c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d031  jmp     loc_18002CF7E
0x18002d036  mov     rax, [rdi]
0x18002d039  mov     [rbp+4Fh+var_A0], rax
0x18002d03d  mov     [rbp+4Fh+var_C8], 0
0x18002d045  lea     r8, [rbp+4Fh+var_A0]
0x18002d049  lea     rdx, [rbp+4Fh+var_A8]
0x18002d04d  lea     rcx, [rbp+4Fh+var_C8]
0x18002d051  call    ??$MakeAndInitialize@VCMMNotificationDelegator@AudioEffectsWatcher@@UIMMNotificationClient@@AEAPEBGPEAX@Details@WRL@Microsoft@@YAJPEAPEAUIMMNotificationClient@@AEAPEBG$$QEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<AudioEffectsWatcher::CMMNotificationDelegator,IMMNotificationClient,ushort const * &,void *>(IMMNotificationClient * *,ushort const * &,void * &&)
0x18002d056  test    eax, eax
0x18002d058  js      loc_18002D0E9
0x18002d05e  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18002d065  mov     rax, [rcx]
0x18002d068  mov     rdx, [rbp+4Fh+var_C8]
0x18002d06c  mov     rax, [rax+30h]
0x18002d070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d075  mov     ebx, eax
0x18002d077  test    eax, eax
0x18002d079  jns     short loc_18002D0C3
0x18002d07b  mov     rcx, [rbp+57h]; this
0x18002d07f  mov     r9d, eax; char *
0x18002d082  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002d089  mov     edx, 8Dh; void *
0x18002d08e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d093  nop
0x18002d094  mov     rcx, [rbp+4Fh+var_C8]
0x18002d098  test    rcx, rcx
0x18002d09b  jz      short loc_18002D0AA
0x18002d09d  mov     rax, [rcx]
0x18002d0a0  mov     rax, [rax+10h]
0x18002d0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0a9  nop
0x18002d0aa  mov     rcx, [rsp+110h+SecurityDescriptor]; hMem
0x18002d0af  test    rcx, rcx
0x18002d0b2  jz      loc_18002CF35
0x18002d0b8  call    cs:__imp_LocalFree
0x18002d0be  jmp     loc_18002CF35
0x18002d0c3  mov     rax, [rbp+4Fh+var_C8]
0x18002d0c7  mov     [rbp+4Fh+var_C8], 0
0x18002d0cf  mov     rcx, [r14+50h]
0x18002d0d3  mov     [r14+50h], rax
0x18002d0d7  test    rcx, rcx
0x18002d0da  jz      short loc_18002D0E9
0x18002d0dc  mov     rax, [rcx]
0x18002d0df  mov     rax, [rax+10h]
0x18002d0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0e8  nop
0x18002d0e9  mov     rcx, r14; this
0x18002d0ec  call    ?RebuildAndPublishFullEffectsListFromApos@AudioEffectsWatcher@@AEAAJXZ; AudioEffectsWatcher::RebuildAndPublishFullEffectsListFromApos(void)
0x18002d0f1  call    ?GetSerialWorkQueue@@YAAEAVCSerialWorkQueue@@XZ; GetSerialWorkQueue(void)
0x18002d0f6  lea     rcx, off_180173490
0x18002d0fd  mov     [rbp+4Fh+var_80], rcx
0x18002d101  mov     [rbp+4Fh+var_78], r14
0x18002d105  lea     rcx, [rbp+4Fh+var_80]
0x18002d109  mov     [rbp+4Fh+var_48], rcx
0x18002d10d  lea     r9, [r14+0A0h]
0x18002d114  lea     r8, [rbp+4Fh+var_80]
0x18002d118  mov     rdx, [rdi]
0x18002d11b  mov     rcx, rax
0x18002d11e  call    ?QueueRecurringWaitItem@CSerialWorkQueue@@QEAAJPEAXV?$function@$$A6AXXZ@std@@AEAV?$unique_ptr@U_WaitTask@@U?$default_delete@U_WaitTask@@@std@@@3@@Z; CSerialWorkQueue::QueueRecurringWaitItem(void *,std::function<void (void)>,std::unique_ptr<_WaitTask> &)
0x18002d123  mov     ebx, eax
0x18002d125  test    eax, eax
0x18002d127  jns     short loc_18002D150
0x18002d129  mov     rcx, [rbp+57h]; this
0x18002d12d  mov     r9d, eax; char *
0x18002d130  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002d137  mov     edx, 97h; void *
0x18002d13c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d141  nop
0x18002d142  lea     rcx, [rbp+4Fh+var_C8]
0x18002d146  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18002d14b  jmp     loc_18002CF7E
0x18002d150  lea     rcx, [rbp+4Fh+var_C8]
0x18002d154  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18002d159  nop
0x18002d15a  lea     rcx, [rsp+110h+SecurityDescriptor]
0x18002d15f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d164  nop
0x18002d165  lea     rcx, [rbp+4Fh+var_C0]; this
0x18002d169  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x18002d16e  xor     ebx, ebx
0x18002d170  lea     rdx, [rbp+4Fh+var_28]
0x18002d174  mov     ecx, 4
0x18002d179  call    cs:__imp_EtwEventActivityIdControl
0x18002d17f  mov     eax, ebx
0x18002d181  mov     rcx, [rbp+4Fh+var_18]
0x18002d185  xor     rcx, rsp; StackCookie
0x18002d188  call    __security_check_cookie
0x18002d18d  lea     r11, [rsp+110h+var_10]
0x18002d195  mov     rbx, [r11+30h]
0x18002d199  mov     rsi, [r11+38h]
0x18002d19d  mov     rsp, r11
0x18002d1a0  pop     r14
0x18002d1a2  pop     rdi
0x18002d1a3  pop     rbp
0x18002d1a4  retn
0x18002d1a5  mov     qword ptr [rsp+110h+var_F0], 0
0x18002d1ae  mov     r9d, 10h
0x18002d1b4  lea     r8, qword_18018E418
0x18002d1bb  xor     edx, edx
0x18002d1bd  mov     rcx, [r14+5Ch]
0x18002d1c1  call    cs:__imp_RtlPublishWnfStateData
0x18002d1c7  test    eax, eax
0x18002d1c9  jns     short loc_18002D15A
0x18002d1cb  mov     edx, 9Ch
0x18002d1d0  jmp     loc_18002CFCA
```
