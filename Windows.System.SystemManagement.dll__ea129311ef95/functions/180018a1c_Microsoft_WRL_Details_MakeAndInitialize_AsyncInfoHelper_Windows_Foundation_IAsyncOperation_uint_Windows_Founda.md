# Microsoft::WRL::Details::MakeAndInitialize<AsyncInfoHelper<Windows::Foundation::IAsyncOperation<uint>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>>,AsyncInfoHelper<Windows::Foundation::IAsyncOperation<uint>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>>,>(AsyncInfoHelper<Windows::Foundation::IAsyncOperation<uint>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>> * *)

- ea: `0x180018a1c`
- end: `0x180018b26`
- name: `??$MakeAndInitialize@V?$AsyncInfoHelper@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$AsyncInfoHelper@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b1d0`

## callees

- `0x1800032ec`
- `0x180007248`
- `0x18000acb8`
- `0x18000aed0`
- `0x18000f854`
- `0x180018a1c`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<AsyncInfoHelper<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>,AsyncInfoHelper<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>,>(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // edi
  _DWORD *v5; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v6; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Storage::Streams::IBufferByteAccess::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &AsyncInfoHelper<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_QWORD *)v2 + 7) = 0;
    v5 = v2;
    v6 = 0;
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v2 + 14);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
      *a1 = v2;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v5);
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v5);
    }
  }
  else
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v6);
  return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
}

```

## disassembly

```asm
0x180018a1c  mov     [rsp+arg_10], rbx
0x180018a21  mov     [rsp+arg_18], rsi
0x180018a26  push    rdi
0x180018a27  sub     rsp, 30h
0x180018a2b  mov     rsi, rcx
0x180018a2e  mov     qword ptr [rcx], 0
0x180018a35  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018a3c  mov     ecx, 40h ; '@'; unsigned __int64
0x180018a41  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018a46  mov     rbx, rax
0x180018a49  mov     [rsp+38h+arg_8], rax
0x180018a4e  test    rax, rax
0x180018a51  jnz     short loc_180018A5D
0x180018a53  mov     edi, 8007000Eh
0x180018a58  jmp     loc_180018B0A
0x180018a5d  lea     rax, ??_7IBufferByteAccess@Streams@Storage@Windows@@6B@; const Windows::Storage::Streams::IBufferByteAccess::`vftable'
0x180018a64  mov     [rbx], rax
0x180018a67  lea     rdi, [rbx+8]
0x180018a6b  mov     rcx, rdi; this
0x180018a6e  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180018a73  mov     dword ptr [rbx+2Ch], 1
0x180018a7a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<uint>'}
0x180018a81  mov     [rbx], rax
0x180018a84  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180018a8b  mov     [rdi], rax
0x180018a8e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180018a95  test    rcx, rcx
0x180018a98  jz      short loc_180018AA7
0x180018a9a  mov     rax, [rcx]
0x180018a9d  mov     rax, [rax+8]
0x180018aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018aa6  nop
0x180018aa7  lea     rax, ??_7?$AsyncInfoHelper@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@6B?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@@; const AsyncInfoHelper<Windows::Foundation::IAsyncOperation<uint>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<uint>'}
0x180018aae  mov     [rbx], rax
0x180018ab1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180018ab8  mov     [rdi], rax
0x180018abb  lea     rcx, [rbx+38h]
0x180018abf  mov     qword ptr [rcx], 0
0x180018ac6  mov     [rsp+38h+arg_0], rbx
0x180018acb  mov     [rsp+38h+arg_8], 0
0x180018ad4  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180018ad9  mov     edi, eax
0x180018adb  test    eax, eax
0x180018add  jns     short loc_180018AEB
0x180018adf  lea     rcx, [rsp+38h+arg_0]
0x180018ae4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018ae9  jmp     short loc_180018B0A
0x180018aeb  mov     rax, [rbx]
0x180018aee  mov     rcx, rbx
0x180018af1  mov     rax, [rax+8]
0x180018af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018afa  nop
0x180018afb  mov     [rsi], rbx
0x180018afe  lea     rcx, [rsp+38h+arg_0]
0x180018b03  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018b08  xor     edi, edi
0x180018b0a  lea     rcx, [rsp+38h+arg_8]
0x180018b0f  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x180018b14  mov     eax, edi
0x180018b16  mov     rbx, [rsp+38h+arg_10]
0x180018b1b  mov     rsi, [rsp+38h+arg_18]
0x180018b20  add     rsp, 30h
0x180018b24  pop     rdi
0x180018b25  retn
```
