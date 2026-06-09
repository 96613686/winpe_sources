# DynamicAudioEndpointManager::GetDefaultAudioEndpoint(void *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,bool *,ushort * *)

- ea: `0x180066d3c`
- end: `0x180067013`
- name: `?GetDefaultAudioEndpoint@DynamicAudioEndpointManager@@QEAAJPEAXW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEA_NPEAPEAG@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007f680`

## callees

- `0x18000accc`
- `0x18000ca50`
- `0x18000d2b0`
- `0x18000e134`
- `0x1800126bc`
- `0x1800526e8`
- `0x180066d3c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180066e16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180066ffe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180066e16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180066ffe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180066d67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180066d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066df1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ee1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066fc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066df1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ee1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066fc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DynamicAudioEndpointManager::GetDefaultAudioEndpoint(
        void *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        _QWORD *a6)
{
  DynamicAudioEndpointManager *v9; // rdi
  RTL_SRWLOCK *v10; // r14
  __int64 v11; // rax
  int v12; // eax
  int DefaultAudioEndpoint; // ebx
  unsigned int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, _QWORD *); // rsi
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, LPVOID *); // rbx
  int v20; // eax
  LPVOID v21; // rdx
  void *v22; // rcx
  int v23; // [rsp+20h] [rbp-38h]
  int v24; // [rsp+20h] [rbp-38h]
  __int64 v25; // [rsp+30h] [rbp-28h] BYREF
  __int64 v26; // [rsp+38h] [rbp-20h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-18h] BYREF
  RTL_SRWLOCK *v28; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  LPVOID pv; // [rsp+90h] [rbp+38h] BYREF

  pv = a1;
  v9 = g_DynamicAudioEndpointManager;
  v10 = (RTL_SRWLOCK *)((char *)g_DynamicAudioEndpointManager + 16);
  AcquireSRWLockShared((PSRWLOCK)g_DynamicAudioEndpointManager + 2);
  v28 = v10;
  v27 = 0;
  v25 = 0;
  pv = 0;
  v26 = 0;
  v11 = *(_QWORD *)g_PolicyManager;
  v26 = 0;
  v12 = (*(__int64 (__fastcall **)(struct IAudioPolicyManager *, __int64, __int64 *))(v11 + 32))(
          g_PolicyManager,
          a2,
          &v26);
  DefaultAudioEndpoint = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\defaultdevice\\dynamicrouting.cpp",
      (const char *)(unsigned int)v12,
      v23);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( pv )
      CoTaskMemFree(pv);
LABEL_6:
    if ( v10 )
      ReleaseSRWLockShared(v10);
    return (unsigned int)DefaultAudioEndpoint;
  }
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 40LL))(v26);
  v27 = 0;
  v24 = a5;
  DefaultAudioEndpoint = DynamicAudioEndpointManager::GetDefaultAudioEndpoint(v9, v15, a3, a4);
  if ( DefaultAudioEndpoint < 0 )
  {
LABEL_22:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v26);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v25);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v27);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v28);
    return (unsigned int)DefaultAudioEndpoint;
  }
  v25 = 0;
  v16 = v27;
  v17 = (**v27)(v27, &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21, &v25);
  DefaultAudioEndpoint = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\defaultdevice\\dynamicrouting.cpp",
      (const char *)(unsigned int)v17,
      v24);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v16 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[2])(v16);
    goto LABEL_6;
  }
  v18 = v25;
  v19 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v25 + 56LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v20 = v19(v18, &pv);
  DefaultAudioEndpoint = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF0,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\defaultdevice\\dynamicrouting.cpp",
      (const char *)(unsigned int)v20,
      v24);
    goto LABEL_22;
  }
  v21 = pv;
  v22 = 0;
  pv = 0;
  *a6 = v21;
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v22 = pv;
  }
  if ( v22 )
    CoTaskMemFree(v22);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v16 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[2])(v16);
  if ( v10 )
    ReleaseSRWLockShared(v10);
  return 0;
}

```

## disassembly

```asm
0x180066d3c  mov     [rsp-30h+pv], rcx
0x180066d41  push    rbp
0x180066d42  push    rbx
0x180066d43  push    rsi
0x180066d44  push    rdi
0x180066d45  push    r14
0x180066d47  push    r15
0x180066d49  mov     rbp, rsp
0x180066d4c  sub     rsp, 58h
0x180066d50  mov     esi, r9d
0x180066d53  mov     r15d, r8d
0x180066d56  mov     rbx, rdx
0x180066d59  mov     rdi, cs:?g_DynamicAudioEndpointManager@@3PEAVDynamicAudioEndpointManager@@EA; DynamicAudioEndpointManager * g_DynamicAudioEndpointManager
0x180066d60  lea     r14, [rdi+10h]
0x180066d64  mov     rcx, r14; SRWLock
0x180066d67  call    cs:__imp_AcquireSRWLockShared
0x180066d6d  mov     [rbp+var_10], r14
0x180066d71  mov     [rbp+var_18], 0
0x180066d79  mov     [rbp+var_28], 0
0x180066d81  mov     [rbp+pv], 0
0x180066d89  mov     [rbp+var_20], 0
0x180066d91  mov     rcx, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA; IAudioPolicyManager * g_PolicyManager
0x180066d98  mov     rax, [rcx]
0x180066d9b  mov     [rbp+var_20], 0
0x180066da3  lea     r8, [rbp+var_20]
0x180066da7  mov     rdx, rbx
0x180066daa  mov     rax, [rax+20h]
0x180066dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066db3  mov     ebx, eax
0x180066db5  test    eax, eax
0x180066db7  jns     short loc_180066E23
0x180066db9  mov     rcx, [rbp+30h]; this
0x180066dbd  mov     r9d, eax; char *
0x180066dc0  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiosrv\\de"...
0x180066dc7  mov     edx, 0EAh; void *
0x180066dcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066dd1  nop
0x180066dd2  mov     rcx, [rbp+var_20]
0x180066dd6  test    rcx, rcx
0x180066dd9  jz      short loc_180066DE8
0x180066ddb  mov     rax, [rcx]
0x180066dde  mov     rax, [rax+10h]
0x180066de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066de7  nop
0x180066de8  mov     rcx, [rbp+pv]; pv
0x180066dec  test    rcx, rcx
0x180066def  jz      short loc_180066DF8
0x180066df1  call    cs:__imp_CoTaskMemFree
0x180066df7  nop
0x180066df8  mov     rcx, [rbp+var_28]
0x180066dfc  test    rcx, rcx
0x180066dff  jz      short loc_180066E0E
0x180066e01  mov     rax, [rcx]
0x180066e04  mov     rax, [rax+10h]
0x180066e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e0d  nop
0x180066e0e  test    r14, r14
0x180066e11  jz      short loc_180066E1C
0x180066e13  mov     rcx, r14; SRWLock
0x180066e16  call    cs:__imp_ReleaseSRWLockShared
0x180066e1c  mov     eax, ebx
0x180066e1e  jmp     loc_180067006
0x180066e23  mov     rcx, [rbp+var_20]
0x180066e27  mov     rax, [rcx]
0x180066e2a  mov     rax, [rax+28h]
0x180066e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e33  nop
0x180066e34  mov     [rbp+var_18], 0
0x180066e3c  lea     rcx, [rbp+var_18]
0x180066e40  mov     [rsp+58h+var_30], rcx
0x180066e45  mov     rdx, qword ptr [rbp+arg_20]
0x180066e49  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180066e4e  mov     r9d, esi
0x180066e51  mov     r8d, r15d
0x180066e54  mov     edx, eax
0x180066e56  mov     rcx, rdi
0x180066e59  call    ?GetDefaultAudioEndpoint@DynamicAudioEndpointManager@@QEAAJKW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEA_NPEAPEAUIMMDevice@@@Z; DynamicAudioEndpointManager::GetDefaultAudioEndpoint(ulong,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,bool *,IMMDevice * *)
0x180066e5e  mov     ebx, eax
0x180066e60  test    eax, eax
0x180066e62  js      loc_180066F5C
0x180066e68  mov     rcx, [rbp+var_28]
0x180066e6c  mov     [rbp+var_28], 0
0x180066e74  test    rcx, rcx
0x180066e77  jz      short loc_180066E86
0x180066e79  mov     rax, [rcx]
0x180066e7c  mov     rax, [rax+10h]
0x180066e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e85  nop
0x180066e86  mov     rsi, [rbp+var_18]
0x180066e8a  mov     rax, [rsi]
0x180066e8d  lea     r8, [rbp+var_28]
0x180066e91  lea     rdx, _GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21
0x180066e98  mov     rcx, rsi
0x180066e9b  mov     rax, [rax]
0x180066e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ea3  mov     ebx, eax
0x180066ea5  test    eax, eax
0x180066ea7  jns     short loc_180066F18
0x180066ea9  mov     rcx, [rbp+30h]; this
0x180066ead  mov     r9d, eax; char *
0x180066eb0  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiosrv\\de"...
0x180066eb7  mov     edx, 0EFh; void *
0x180066ebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066ec1  nop
0x180066ec2  mov     rcx, [rbp+var_20]
0x180066ec6  test    rcx, rcx
0x180066ec9  jz      short loc_180066ED8
0x180066ecb  mov     rax, [rcx]
0x180066ece  mov     rax, [rax+10h]
0x180066ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ed7  nop
0x180066ed8  mov     rcx, [rbp+pv]; pv
0x180066edc  test    rcx, rcx
0x180066edf  jz      short loc_180066EE8
0x180066ee1  call    cs:__imp_CoTaskMemFree
0x180066ee7  nop
0x180066ee8  mov     rcx, [rbp+var_28]
0x180066eec  test    rcx, rcx
0x180066eef  jz      short loc_180066EFE
0x180066ef1  mov     rax, [rcx]
0x180066ef4  mov     rax, [rax+10h]
0x180066ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066efd  nop
0x180066efe  test    rsi, rsi
0x180066f01  jz      short loc_180066F13
0x180066f03  mov     rax, [rsi]
0x180066f06  mov     rcx, rsi
0x180066f09  mov     rax, [rax+10h]
0x180066f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f12  nop
0x180066f13  jmp     loc_180066E0E
0x180066f18  mov     rdi, [rbp+var_28]
0x180066f1c  mov     rax, [rdi]
0x180066f1f  mov     rbx, [rax+38h]
0x180066f23  xor     edx, edx
0x180066f25  lea     rcx, [rbp+pv]
0x180066f29  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180066f2e  lea     rdx, [rbp+pv]
0x180066f32  mov     rcx, rdi
0x180066f35  mov     rax, rbx
0x180066f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f3d  mov     ebx, eax
0x180066f3f  test    eax, eax
0x180066f41  jns     short loc_180066F92
0x180066f43  mov     rcx, [rbp+30h]; this
0x180066f47  mov     r9d, eax; char *
0x180066f4a  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiosrv\\de"...
0x180066f51  mov     edx, 0F0h; void *
0x180066f56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066f5b  nop
0x180066f5c  lea     rcx, [rbp+var_20]
0x180066f60  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180066f65  nop
0x180066f66  lea     rcx, [rbp+pv]
0x180066f6a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180066f6f  nop
0x180066f70  lea     rcx, [rbp+var_28]
0x180066f74  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180066f79  nop
0x180066f7a  lea     rcx, [rbp+var_18]
0x180066f7e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180066f83  nop
0x180066f84  lea     rcx, [rbp+var_10]
0x180066f88  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180066f8d  jmp     loc_180066E1C
0x180066f92  mov     rdx, [rbp+pv]
0x180066f96  xor     ecx, ecx
0x180066f98  mov     [rbp+pv], rcx
0x180066f9c  mov     rax, [rbp+arg_28]
0x180066fa0  mov     [rax], rdx
0x180066fa3  mov     rdx, [rbp+var_20]
0x180066fa7  test    rdx, rdx
0x180066faa  jz      short loc_180066FBF
0x180066fac  mov     rax, [rdx]
0x180066faf  mov     rcx, rdx
0x180066fb2  mov     rax, [rax+10h]
0x180066fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fbb  mov     rcx, [rbp+pv]; pv
0x180066fbf  test    rcx, rcx
0x180066fc2  jz      short loc_180066FCB
0x180066fc4  call    cs:__imp_CoTaskMemFree
0x180066fca  nop
0x180066fcb  mov     rcx, [rbp+var_28]
0x180066fcf  test    rcx, rcx
0x180066fd2  jz      short loc_180066FE1
0x180066fd4  mov     rax, [rcx]
0x180066fd7  mov     rax, [rax+10h]
0x180066fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fe0  nop
0x180066fe1  test    rsi, rsi
0x180066fe4  jz      short loc_180066FF6
0x180066fe6  mov     rax, [rsi]
0x180066fe9  mov     rcx, rsi
0x180066fec  mov     rax, [rax+10h]
0x180066ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ff5  nop
0x180066ff6  test    r14, r14
0x180066ff9  jz      short loc_180067004
0x180066ffb  mov     rcx, r14; SRWLock
0x180066ffe  call    cs:__imp_ReleaseSRWLockShared
0x180067004  xor     eax, eax
0x180067006  add     rsp, 58h
0x18006700a  pop     r15
0x18006700c  pop     r14
0x18006700e  pop     rdi
0x18006700f  pop     rsi
0x180067010  pop     rbx
0x180067011  pop     rbp
0x180067012  retn
```
