# DynamicAudioEndpointManager::GetDefaultAudioEndpoint(void *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,bool *,ushort * *)

- ea: `0x1800668ac`
- end: `0x180066b83`
- name: `?GetDefaultAudioEndpoint@DynamicAudioEndpointManager@@QEAAJPEAXW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEA_NPEAPEAG@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007f180`

## callees

- `0x18000ae1c`
- `0x18000cba0`
- `0x18000d400`
- `0x18000e284`
- `0x18001280c`
- `0x180052258`
- `0x1800668ac`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180066986`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180066b6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180066986`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180066b6e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800668d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800668d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066a51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066a51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b34`

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
0x1800668ac  mov     [rsp-30h+pv], rcx
0x1800668b1  push    rbp
0x1800668b2  push    rbx
0x1800668b3  push    rsi
0x1800668b4  push    rdi
0x1800668b5  push    r14
0x1800668b7  push    r15
0x1800668b9  mov     rbp, rsp
0x1800668bc  sub     rsp, 58h
0x1800668c0  mov     esi, r9d
0x1800668c3  mov     r15d, r8d
0x1800668c6  mov     rbx, rdx
0x1800668c9  mov     rdi, cs:?g_DynamicAudioEndpointManager@@3PEAVDynamicAudioEndpointManager@@EA; DynamicAudioEndpointManager * g_DynamicAudioEndpointManager
0x1800668d0  lea     r14, [rdi+10h]
0x1800668d4  mov     rcx, r14; SRWLock
0x1800668d7  call    cs:__imp_AcquireSRWLockShared
0x1800668dd  mov     [rbp+var_10], r14
0x1800668e1  mov     [rbp+var_18], 0
0x1800668e9  mov     [rbp+var_28], 0
0x1800668f1  mov     [rbp+pv], 0
0x1800668f9  mov     [rbp+var_20], 0
0x180066901  mov     rcx, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA; IAudioPolicyManager * g_PolicyManager
0x180066908  mov     rax, [rcx]
0x18006690b  mov     [rbp+var_20], 0
0x180066913  lea     r8, [rbp+var_20]
0x180066917  mov     rdx, rbx
0x18006691a  mov     rax, [rax+20h]
0x18006691e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066923  mov     ebx, eax
0x180066925  test    eax, eax
0x180066927  jns     short loc_180066993
0x180066929  mov     rcx, [rbp+30h]; this
0x18006692d  mov     r9d, eax; char *
0x180066930  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiosrv\\de"...
0x180066937  mov     edx, 0EAh; void *
0x18006693c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066941  nop
0x180066942  mov     rcx, [rbp+var_20]
0x180066946  test    rcx, rcx
0x180066949  jz      short loc_180066958
0x18006694b  mov     rax, [rcx]
0x18006694e  mov     rax, [rax+10h]
0x180066952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066957  nop
0x180066958  mov     rcx, [rbp+pv]; pv
0x18006695c  test    rcx, rcx
0x18006695f  jz      short loc_180066968
0x180066961  call    cs:__imp_CoTaskMemFree
0x180066967  nop
0x180066968  mov     rcx, [rbp+var_28]
0x18006696c  test    rcx, rcx
0x18006696f  jz      short loc_18006697E
0x180066971  mov     rax, [rcx]
0x180066974  mov     rax, [rax+10h]
0x180066978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006697d  nop
0x18006697e  test    r14, r14
0x180066981  jz      short loc_18006698C
0x180066983  mov     rcx, r14; SRWLock
0x180066986  call    cs:__imp_ReleaseSRWLockShared
0x18006698c  mov     eax, ebx
0x18006698e  jmp     loc_180066B76
0x180066993  mov     rcx, [rbp+var_20]
0x180066997  mov     rax, [rcx]
0x18006699a  mov     rax, [rax+28h]
0x18006699e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669a3  nop
0x1800669a4  mov     [rbp+var_18], 0
0x1800669ac  lea     rcx, [rbp+var_18]
0x1800669b0  mov     [rsp+58h+var_30], rcx
0x1800669b5  mov     rdx, qword ptr [rbp+arg_20]
0x1800669b9  mov     qword ptr [rsp+58h+var_38], rdx; int
0x1800669be  mov     r9d, esi
0x1800669c1  mov     r8d, r15d
0x1800669c4  mov     edx, eax
0x1800669c6  mov     rcx, rdi
0x1800669c9  call    ?GetDefaultAudioEndpoint@DynamicAudioEndpointManager@@QEAAJKW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEA_NPEAPEAUIMMDevice@@@Z; DynamicAudioEndpointManager::GetDefaultAudioEndpoint(ulong,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,bool *,IMMDevice * *)
0x1800669ce  mov     ebx, eax
0x1800669d0  test    eax, eax
0x1800669d2  js      loc_180066ACC
0x1800669d8  mov     rcx, [rbp+var_28]
0x1800669dc  mov     [rbp+var_28], 0
0x1800669e4  test    rcx, rcx
0x1800669e7  jz      short loc_1800669F6
0x1800669e9  mov     rax, [rcx]
0x1800669ec  mov     rax, [rax+10h]
0x1800669f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669f5  nop
0x1800669f6  mov     rsi, [rbp+var_18]
0x1800669fa  mov     rax, [rsi]
0x1800669fd  lea     r8, [rbp+var_28]
0x180066a01  lea     rdx, _GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21
0x180066a08  mov     rcx, rsi
0x180066a0b  mov     rax, [rax]
0x180066a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a13  mov     ebx, eax
0x180066a15  test    eax, eax
0x180066a17  jns     short loc_180066A88
0x180066a19  mov     rcx, [rbp+30h]; this
0x180066a1d  mov     r9d, eax; char *
0x180066a20  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiosrv\\de"...
0x180066a27  mov     edx, 0EFh; void *
0x180066a2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066a31  nop
0x180066a32  mov     rcx, [rbp+var_20]
0x180066a36  test    rcx, rcx
0x180066a39  jz      short loc_180066A48
0x180066a3b  mov     rax, [rcx]
0x180066a3e  mov     rax, [rax+10h]
0x180066a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a47  nop
0x180066a48  mov     rcx, [rbp+pv]; pv
0x180066a4c  test    rcx, rcx
0x180066a4f  jz      short loc_180066A58
0x180066a51  call    cs:__imp_CoTaskMemFree
0x180066a57  nop
0x180066a58  mov     rcx, [rbp+var_28]
0x180066a5c  test    rcx, rcx
0x180066a5f  jz      short loc_180066A6E
0x180066a61  mov     rax, [rcx]
0x180066a64  mov     rax, [rax+10h]
0x180066a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a6d  nop
0x180066a6e  test    rsi, rsi
0x180066a71  jz      short loc_180066A83
0x180066a73  mov     rax, [rsi]
0x180066a76  mov     rcx, rsi
0x180066a79  mov     rax, [rax+10h]
0x180066a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a82  nop
0x180066a83  jmp     loc_18006697E
0x180066a88  mov     rdi, [rbp+var_28]
0x180066a8c  mov     rax, [rdi]
0x180066a8f  mov     rbx, [rax+38h]
0x180066a93  xor     edx, edx
0x180066a95  lea     rcx, [rbp+pv]
0x180066a99  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180066a9e  lea     rdx, [rbp+pv]
0x180066aa2  mov     rcx, rdi
0x180066aa5  mov     rax, rbx
0x180066aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066aad  mov     ebx, eax
0x180066aaf  test    eax, eax
0x180066ab1  jns     short loc_180066B02
0x180066ab3  mov     rcx, [rbp+30h]; this
0x180066ab7  mov     r9d, eax; char *
0x180066aba  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiosrv\\de"...
0x180066ac1  mov     edx, 0F0h; void *
0x180066ac6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066acb  nop
0x180066acc  lea     rcx, [rbp+var_20]
0x180066ad0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180066ad5  nop
0x180066ad6  lea     rcx, [rbp+pv]
0x180066ada  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180066adf  nop
0x180066ae0  lea     rcx, [rbp+var_28]
0x180066ae4  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180066ae9  nop
0x180066aea  lea     rcx, [rbp+var_18]
0x180066aee  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180066af3  nop
0x180066af4  lea     rcx, [rbp+var_10]
0x180066af8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180066afd  jmp     loc_18006698C
0x180066b02  mov     rdx, [rbp+pv]
0x180066b06  xor     ecx, ecx
0x180066b08  mov     [rbp+pv], rcx
0x180066b0c  mov     rax, [rbp+arg_28]
0x180066b10  mov     [rax], rdx
0x180066b13  mov     rdx, [rbp+var_20]
0x180066b17  test    rdx, rdx
0x180066b1a  jz      short loc_180066B2F
0x180066b1c  mov     rax, [rdx]
0x180066b1f  mov     rcx, rdx
0x180066b22  mov     rax, [rax+10h]
0x180066b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b2b  mov     rcx, [rbp+pv]; pv
0x180066b2f  test    rcx, rcx
0x180066b32  jz      short loc_180066B3B
0x180066b34  call    cs:__imp_CoTaskMemFree
0x180066b3a  nop
0x180066b3b  mov     rcx, [rbp+var_28]
0x180066b3f  test    rcx, rcx
0x180066b42  jz      short loc_180066B51
0x180066b44  mov     rax, [rcx]
0x180066b47  mov     rax, [rax+10h]
0x180066b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b50  nop
0x180066b51  test    rsi, rsi
0x180066b54  jz      short loc_180066B66
0x180066b56  mov     rax, [rsi]
0x180066b59  mov     rcx, rsi
0x180066b5c  mov     rax, [rax+10h]
0x180066b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b65  nop
0x180066b66  test    r14, r14
0x180066b69  jz      short loc_180066B74
0x180066b6b  mov     rcx, r14; SRWLock
0x180066b6e  call    cs:__imp_ReleaseSRWLockShared
0x180066b74  xor     eax, eax
0x180066b76  add     rsp, 58h
0x180066b7a  pop     r15
0x180066b7c  pop     r14
0x180066b7e  pop     rdi
0x180066b7f  pop     rsi
0x180066b80  pop     rbx
0x180066b81  pop     rbp
0x180066b82  retn
```
