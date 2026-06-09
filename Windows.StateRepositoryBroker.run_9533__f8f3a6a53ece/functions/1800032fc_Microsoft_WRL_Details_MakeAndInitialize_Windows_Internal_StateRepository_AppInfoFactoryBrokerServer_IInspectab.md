# Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,IInspectable,>(IInspectable * *)

- ea: `0x1800032fc`
- end: `0x1800033f8`
- name: `??$MakeAndInitialize@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UIInspectable@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIInspectable@@@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004310`

## callees

- `0x180001d84`
- `0x1800032fc`
- `0x180003b84`
- `0x180003ee4`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,IInspectable,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  unsigned int v4; // edi
  _QWORD *v5; // rdi
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v7 = v2;
  if ( v2 )
  {
    v5 = v2 + 1;
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>(v2 + 1);
    v3[7] = 1;
    *v3 = &Microsoft::WRL::RuntimeClass<Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::`vftable';
    *v5 = &Microsoft::WRL::RuntimeClass<Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
    v3[2] = &Microsoft::WRL::RuntimeClass<Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v3 = &Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::`vftable';
    *v5 = &Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::`vftable'{for `IWeakReferenceSource'};
    v3[2] = &Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v7 = 0;
    v4 = ((__int64 (__fastcall *)(_QWORD *, GUID *, _QWORD *))Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::`vftable')(
           v3,
           &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
           a1);
    (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(&v7);
  return v4;
}

```

## disassembly

```asm
0x1800032fc  mov     [rsp+arg_8], rbx
0x180003301  mov     [rsp+arg_10], rsi
0x180003306  push    rdi
0x180003307  sub     rsp, 20h
0x18000330b  mov     rsi, rcx
0x18000330e  mov     qword ptr [rcx], 0
0x180003315  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000331c  mov     ecx, 40h ; '@'; unsigned __int64
0x180003321  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003326  mov     rbx, rax
0x180003329  mov     [rsp+28h+arg_0], rax
0x18000332e  test    rax, rax
0x180003331  jnz     short loc_18000333D
0x180003333  mov     edi, 8007000Eh
0x180003338  jmp     loc_1800033DC
0x18000333d  lea     rdi, [rax+8]
0x180003341  mov     rcx, rdi
0x180003344  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>(void)
0x180003349  mov     qword ptr [rbx+38h], 1
0x180003351  lea     rax, ??_7?$RuntimeClass@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::`vftable'
0x180003358  mov     [rbx], rax
0x18000335b  lea     rax, ??_7?$RuntimeClass@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x180003362  mov     [rdi], rax
0x180003365  lea     rax, ??_7?$RuntimeClass@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000336c  mov     [rbx+10h], rax
0x180003370  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003377  test    rcx, rcx
0x18000337a  jz      short loc_180003389
0x18000337c  mov     rax, [rcx]
0x18000337f  mov     rax, [rax+8]
0x180003383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003388  nop
0x180003389  lea     rax, ??_7AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@6B@; const Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::`vftable'
0x180003390  mov     [rbx], rax
0x180003393  lea     rax, ??_7AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::`vftable'{for `IWeakReferenceSource'}
0x18000339a  mov     [rdi], rax
0x18000339d  lea     rax, ??_7AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800033a4  mov     [rbx+10h], rax
0x1800033a8  mov     [rsp+28h+arg_0], 0
0x1800033b1  mov     r8, rsi
0x1800033b4  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1800033bb  mov     rcx, rbx
0x1800033be  mov     rax, cs:??_7AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@6B@; const Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::`vftable'
0x1800033c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ca  mov     edi, eax
0x1800033cc  mov     rcx, [rbx]
0x1800033cf  mov     rax, [rcx+10h]
0x1800033d3  mov     rcx, rbx
0x1800033d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033db  nop
0x1800033dc  lea     rcx, [rsp+28h+arg_0]
0x1800033e1  call    ??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(void)
0x1800033e6  mov     eax, edi
0x1800033e8  mov     rbx, [rsp+28h+arg_8]
0x1800033ed  mov     rsi, [rsp+28h+arg_10]
0x1800033f2  add     rsp, 20h
0x1800033f6  pop     rdi
0x1800033f7  retn
```
