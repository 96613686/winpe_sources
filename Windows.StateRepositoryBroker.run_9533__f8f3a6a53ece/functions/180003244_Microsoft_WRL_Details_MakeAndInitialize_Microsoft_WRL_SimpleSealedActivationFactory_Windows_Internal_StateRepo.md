# Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>,Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>,>(Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0> * *)

- ea: `0x180003244`
- end: `0x1800032f6`
- name: `??$MakeAndInitialize@V?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@12@@Z`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002d60`

## callees

- `0x180001d84`
- `0x180003244`
- `0x180003ba8`
- `0x180003ee4`
- `0x180004390`
- `0x180005c50`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>,Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  unsigned int v4; // ebx
  void *v6; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v6 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::RuntimeClassFlags<13>,0,1,0>::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::RuntimeClassFlags<13>,0,1,0>(v2);
    *v3 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
    v3[3] = 0;
    *((_DWORD *)v3 + 8) = 4;
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v3 = &Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>::`vftable';
    v6 = 0;
    Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(v3);
    *a1 = v3;
    Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(v3);
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(&v6);
  return v4;
}

```

## disassembly

```asm
0x180003244  mov     [rsp+arg_8], rbx
0x180003249  push    rdi
0x18000324a  sub     rsp, 20h
0x18000324e  mov     rdi, rcx
0x180003251  mov     qword ptr [rcx], 0
0x180003258  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000325f  mov     ecx, 28h ; '('; unsigned __int64
0x180003264  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003269  mov     rbx, rax
0x18000326c  mov     [rsp+28h+arg_0], rax
0x180003271  test    rax, rax
0x180003274  jnz     short loc_18000327D
0x180003276  mov     ebx, 8007000Eh
0x18000327b  jmp     short loc_1800032DF
0x18000327d  mov     rcx, rbx
0x180003280  call    ??0?$RuntimeClass@U?$InterfaceListHelper@UIActivationFactory@@VNil@Details@WRL@Microsoft@@V2345@V2345@V2345@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0N@@34@$0A@$00$0A@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::RuntimeClassFlags<13>,0,1,0>::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::RuntimeClassFlags<13>,0,1,0>(void)
0x180003285  lea     rcx, ??_7?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x18000328c  mov     [rbx], rcx
0x18000328f  mov     qword ptr [rbx+18h], 0
0x180003297  mov     dword ptr [rbx+20h], 4
0x18000329e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800032a5  test    rcx, rcx
0x1800032a8  jz      short loc_1800032B7
0x1800032aa  mov     rax, [rcx]
0x1800032ad  mov     rax, [rax+8]
0x1800032b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b6  nop
0x1800032b7  lea     rax, ??_7?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>::`vftable'
0x1800032be  mov     [rbx], rax
0x1800032c1  mov     [rsp+28h+arg_0], 0
0x1800032ca  mov     rcx, rbx
0x1800032cd  call    ?AddRef@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)
0x1800032d2  mov     [rdi], rbx
0x1800032d5  mov     rcx, rbx
0x1800032d8  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x1800032dd  xor     ebx, ebx
0x1800032df  lea     rcx, [rsp+28h+arg_0]
0x1800032e4  call    ??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(void)
0x1800032e9  mov     eax, ebx
0x1800032eb  mov     rbx, [rsp+28h+arg_8]
0x1800032f0  add     rsp, 20h
0x1800032f4  pop     rdi
0x1800032f5  retn
```
