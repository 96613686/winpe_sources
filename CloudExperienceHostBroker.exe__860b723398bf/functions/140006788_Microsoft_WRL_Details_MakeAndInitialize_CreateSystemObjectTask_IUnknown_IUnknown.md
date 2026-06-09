# Microsoft::WRL::Details::MakeAndInitialize<CreateSystemObjectTask,IUnknown,>(IUnknown * *)

- ea: `0x140006788`
- end: `0x1400068bc`
- name: `??$MakeAndInitialize@VCreateSystemObjectTask@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140007a30`

## callees

- `0x1400021a8`
- `0x140004d74`
- `0x1400062e8`
- `0x140006788`
- `0x14000722c`
- `0x140007360`
- `0x140008550`
- `0x14000925c`
- `0x14000a010`

## string_xrefs

- `0x140006846`: `Global\CloudExperienceHostCreateObjectTaskReadyEvent`
- `0x14000686a`: `onecoreuap\internal\shell\inc\private\createobjectservertaskbase.h`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CreateSystemObjectTask,IUnknown,>(_QWORD *a1)
{
  CreateObjectServerTaskBase *v2; // rax
  CreateObjectServerTaskBase *v3; // rbx
  unsigned int ObjectServerTask; // edi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  CreateObjectServerTaskBase *v9; // [rsp+40h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = (CreateObjectServerTaskBase *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v9 = v2;
  if ( v2 )
  {
    CreateObjectServerTaskBase::CreateObjectServerTaskBase(v2);
    *((_DWORD *)v3 + 27) = 1;
    *(_QWORD *)v3 = &CreateSystemObjectTask::`vftable';
    *((_QWORD *)v3 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CreateObjectServerTaskBase>::`vftable'{for `IClassFactory'};
    *((_QWORD *)v3 + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CreateObjectServerTaskBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = &CreateSystemObjectTask::`vftable';
    *((_QWORD *)v3 + 1) = &CreateSystemObjectTask::`vftable'{for `IClassFactory'};
    *((_QWORD *)v3 + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CreateObjectServerTaskBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v9 = 0;
    *(GUID *)((char *)v3 + 56) = GUID_f7fa3149_91e7_43b7_8040_b707688ced1a;
    *((_QWORD *)v3 + 9) = L"Global\\CloudExperienceHostCreateObjectTaskReadyEvent";
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)v3 + 88, 0);
    ObjectServerTask = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      *((_DWORD *)v3 + 24) = 3600000;
      ObjectServerTask = Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>>(
                           v3,
                           &GUID_00000000_0000_0000_c000_000000000046,
                           a1);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\createobjectservertaskbase.h",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        v7);
    }
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>::Release(v3);
  }
  else
  {
    ObjectServerTask = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>(&v9);
  return ObjectServerTask;
}

```

## disassembly

```asm
0x140006788  mov     [rsp+arg_8], rbx
0x14000678d  mov     [rsp+arg_10], rsi
0x140006792  push    rdi
0x140006793  sub     rsp, 30h
0x140006797  mov     rsi, rcx
0x14000679a  mov     qword ptr [rcx], 0
0x1400067a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400067a8  mov     ecx, 70h ; 'p'; unsigned __int64
0x1400067ad  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400067b2  mov     rbx, rax
0x1400067b5  mov     [rsp+38h+arg_0], rax
0x1400067ba  test    rax, rax
0x1400067bd  jnz     short loc_1400067C9
0x1400067bf  mov     edi, 8007000Eh
0x1400067c4  jmp     loc_1400068A0
0x1400067c9  mov     rcx, rbx; this
0x1400067cc  call    ??0CreateObjectServerTaskBase@@QEAA@XZ; CreateObjectServerTaskBase::CreateObjectServerTaskBase(void)
0x1400067d1  mov     dword ptr [rbx+6Ch], 1
0x1400067d8  lea     rax, ??_7CreateSystemObjectTask@@6B@; const CreateSystemObjectTask::`vftable'
0x1400067df  mov     [rbx], rax
0x1400067e2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCreateObjectServerTaskBase@@@WRL@Microsoft@@6BIClassFactory@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CreateObjectServerTaskBase>::`vftable'{for `IClassFactory'}
0x1400067e9  mov     [rbx+8], rax
0x1400067ed  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCreateObjectServerTaskBase@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CreateObjectServerTaskBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400067f4  mov     [rbx+10h], rax
0x1400067f8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400067ff  test    rcx, rcx
0x140006802  jz      short loc_140006811
0x140006804  mov     rax, [rcx]
0x140006807  mov     rax, [rax+8]
0x14000680b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006810  nop
0x140006811  lea     rax, ??_7CreateSystemObjectTask@@6B@; const CreateSystemObjectTask::`vftable'
0x140006818  mov     [rbx], rax
0x14000681b  lea     rax, ??_7CreateSystemObjectTask@@6BIClassFactory@@@; const CreateSystemObjectTask::`vftable'{for `IClassFactory'}
0x140006822  mov     [rbx+8], rax
0x140006826  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCreateObjectServerTaskBase@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CreateObjectServerTaskBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14000682d  mov     [rbx+10h], rax
0x140006831  mov     [rsp+38h+arg_0], 0
0x14000683a  movups  xmm0, xmmword ptr cs:_GUID_f7fa3149_91e7_43b7_8040_b707688ced1a.Data1
0x140006841  movdqu  xmmword ptr [rbx+38h], xmm0
0x140006846  lea     rax, aGlobalCloudexp; "Global\\CloudExperienceHostCreateObject"...
0x14000684d  mov     [rbx+48h], rax
0x140006851  lea     rcx, [rbx+58h]
0x140006855  xor     edx, edx
0x140006857  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000685c  mov     edi, eax
0x14000685e  test    eax, eax
0x140006860  jns     short loc_14000687D
0x140006862  mov     rcx, [rsp+38h]; this
0x140006867  mov     r9d, eax; char *
0x14000686a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x140006871  mov     edx, 12h; void *
0x140006876  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000687b  jmp     short loc_140006898
0x14000687d  mov     dword ptr [rbx+60h], 36EE80h
0x140006884  mov     r8, rsi
0x140006887  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14000688e  mov     rcx, rbx
0x140006891  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCreateObjectServerTaskBase@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCreateObjectServerTaskBase@@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase> *,_GUID const &,void * *)
0x140006896  mov     edi, eax
0x140006898  mov     rcx, rbx
0x14000689b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCreateObjectServerTaskBase@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>::Release(void)
0x1400068a0  lea     rcx, [rsp+38h+arg_0]
0x1400068a5  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>>(void)
0x1400068aa  mov     eax, edi
0x1400068ac  mov     rbx, [rsp+38h+arg_8]
0x1400068b1  mov     rsi, [rsp+38h+arg_10]
0x1400068b6  add     rsp, 30h
0x1400068ba  pop     rdi
0x1400068bb  retn
```
