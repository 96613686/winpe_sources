# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x180003184`
- end: `0x18000323e`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004658`

## callees

- `0x180001d84`
- `0x180003184`
- `0x180003bcc`
- `0x180003ee4`
- `0x180005d70`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(
        _QWORD *a1,
        __int64 *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  __int64 v6; // rsi
  void *v8; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v8 = v4;
  if ( v4 )
  {
    v6 = *a2;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(v4);
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[4] = 0x3FFFFFFF;
    *(_QWORD *)v5 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
    *((_QWORD *)v5 + 3) = v6;
    v5[3] = 2;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release();
    *a1 = v5;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(&v8);
  return a1;
}

```

## disassembly

```asm
0x180003184  mov     [rsp+arg_8], rbx
0x180003189  mov     [rsp+arg_10], rsi
0x18000318e  push    rdi
0x18000318f  sub     rsp, 20h
0x180003193  mov     rsi, rdx
0x180003196  mov     rdi, rcx
0x180003199  mov     qword ptr [rcx], 0
0x1800031a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800031a7  mov     ecx, 20h ; ' '; unsigned __int64
0x1800031ac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800031b1  mov     rbx, rax
0x1800031b4  mov     [rsp+28h+arg_0], rax
0x1800031b9  test    rax, rax
0x1800031bc  jz      short loc_180003221
0x1800031be  mov     rsi, [rsi]
0x1800031c1  mov     rcx, rax
0x1800031c4  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x1800031c9  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x1800031d0  mov     [rbx], rcx
0x1800031d3  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800031da  test    rcx, rcx
0x1800031dd  jz      short loc_1800031EC
0x1800031df  mov     rax, [rcx]
0x1800031e2  mov     rax, [rax+8]
0x1800031e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031eb  nop
0x1800031ec  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x1800031f3  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x1800031fa  mov     [rbx], rax
0x1800031fd  mov     [rbx+18h], rsi
0x180003201  mov     dword ptr [rbx+0Ch], 2
0x180003208  mov     rcx, [rdi]
0x18000320b  test    rcx, rcx
0x18000320e  jz      short loc_180003215
0x180003210  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180003215  mov     [rdi], rbx
0x180003218  mov     [rsp+28h+arg_0], 0
0x180003221  lea     rcx, [rsp+28h+arg_0]
0x180003226  call    ??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(void)
0x18000322b  mov     rax, rdi
0x18000322e  mov     rbx, [rsp+28h+arg_8]
0x180003233  mov     rsi, [rsp+28h+arg_10]
0x180003238  add     rsp, 20h
0x18000323c  pop     rdi
0x18000323d  retn
```
