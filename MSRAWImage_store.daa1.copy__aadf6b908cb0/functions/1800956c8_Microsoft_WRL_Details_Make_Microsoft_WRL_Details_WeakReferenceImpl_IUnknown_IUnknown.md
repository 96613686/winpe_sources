# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x1800956c8`
- end: `0x180095782`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800966a0`

## callees

- `0x180002a24`
- `0x1800956c8`
- `0x1800959a8`
- `0x180095b58`
- `0x180096a60`
- `0x1800b4010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(
        _QWORD *a1,
        __int64 *a2)
{
  void *v4; // rax
  _DWORD *v5; // rbx
  __int64 v6; // rsi
  void *v8; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v4;
  v5 = v4;
  if ( v4 )
  {
    v6 = *a2;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>(v4);
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
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(&v8);
  return a1;
}

```

## disassembly

```asm
0x1800956c8  mov     [rsp+arg_8], rbx
0x1800956cd  mov     [rsp+arg_10], rsi
0x1800956d2  push    rdi
0x1800956d3  sub     rsp, 20h
0x1800956d7  mov     rsi, rdx
0x1800956da  mov     qword ptr [rcx], 0
0x1800956e1  mov     rdi, rcx
0x1800956e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800956eb  mov     ecx, 20h ; ' '; unsigned __int64
0x1800956f0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800956f5  mov     [rsp+28h+arg_0], rax
0x1800956fa  mov     rbx, rax
0x1800956fd  test    rax, rax
0x180095700  jz      short loc_180095764
0x180095702  mov     rsi, [rsi]
0x180095705  mov     rcx, rax
0x180095708  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>(void)
0x18009570d  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x180095714  mov     [rbx], rcx
0x180095717  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18009571e  test    rcx, rcx
0x180095721  jz      short loc_18009572F
0x180095723  mov     rax, [rcx]
0x180095726  mov     rax, [rax+8]
0x18009572a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009572f  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x180095736  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18009573d  mov     [rbx], rax
0x180095740  mov     [rbx+18h], rsi
0x180095744  mov     dword ptr [rbx+0Ch], 2
0x18009574b  mov     rcx, [rdi]
0x18009574e  test    rcx, rcx
0x180095751  jz      short loc_180095758
0x180095753  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180095758  mov     [rdi], rbx
0x18009575b  mov     [rsp+28h+arg_0], 0
0x180095764  lea     rcx, [rsp+28h+arg_0]
0x180095769  call    ??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VCRAWWICDecoder@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(void)
0x18009576e  mov     rbx, [rsp+28h+arg_8]
0x180095773  mov     rax, rdi
0x180095776  mov     rsi, [rsp+28h+arg_10]
0x18009577b  add     rsp, 20h
0x18009577f  pop     rdi
0x180095780  retn
```
