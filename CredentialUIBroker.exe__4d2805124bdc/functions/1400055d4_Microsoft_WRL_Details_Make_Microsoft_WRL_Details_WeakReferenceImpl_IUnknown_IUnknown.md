# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x1400055d4`
- end: `0x14000568d`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `185`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000b4c4`

## callees

- `0x140003644`
- `0x1400055d4`
- `0x140007ebc`
- `0x140008920`
- `0x140012c80`
- `0x14001f010`

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
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICredUIBroker>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICredUIBroker>(v4);
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[4] = 0x3FFFFFFF;
    *(_QWORD *)v5 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
    *((_QWORD *)v5 + 3) = v6;
    v5[3] = 2;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release();
    *a1 = v5;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(&v8);
  return a1;
}

```

## disassembly

```asm
0x1400055d4  mov     [rsp+arg_8], rbx
0x1400055d9  mov     [rsp+arg_10], rsi
0x1400055de  push    rdi
0x1400055df  sub     rsp, 20h
0x1400055e3  mov     rsi, rdx
0x1400055e6  mov     qword ptr [rcx], 0
0x1400055ed  mov     rdi, rcx
0x1400055f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400055f7  mov     ecx, 20h ; ' '; unsigned __int64
0x1400055fc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140005601  mov     [rsp+28h+arg_0], rax
0x140005606  mov     rbx, rax
0x140005609  test    rax, rax
0x14000560c  jz      short loc_140005670
0x14000560e  mov     rsi, [rsi]
0x140005611  mov     rcx, rax
0x140005614  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICredUIBroker@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICredUIBroker>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICredUIBroker>(void)
0x140005619  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x140005620  mov     [rbx], rcx
0x140005623  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000562a  test    rcx, rcx
0x14000562d  jz      short loc_14000563B
0x14000562f  mov     rdx, [rcx]
0x140005632  mov     rax, [rdx+8]
0x140005636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000563b  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x140005642  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x140005649  mov     [rbx], rax
0x14000564c  mov     [rbx+18h], rsi
0x140005650  mov     dword ptr [rbx+0Ch], 2
0x140005657  mov     rcx, [rdi]
0x14000565a  test    rcx, rcx
0x14000565d  jz      short loc_140005664
0x14000565f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x140005664  mov     [rdi], rbx
0x140005667  mov     [rsp+28h+arg_0], 0
0x140005670  lea     rcx, [rsp+28h+arg_0]
0x140005675  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x14000567a  mov     rbx, [rsp+28h+arg_8]
0x14000567f  mov     rax, rdi
0x140005682  mov     rsi, [rsp+28h+arg_10]
0x140005687  add     rsp, 20h
0x14000568b  pop     rdi
0x14000568c  retn
```
