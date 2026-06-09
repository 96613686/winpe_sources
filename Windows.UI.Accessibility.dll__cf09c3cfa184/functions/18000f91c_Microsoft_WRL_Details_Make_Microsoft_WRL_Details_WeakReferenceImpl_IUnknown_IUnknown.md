# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x18000f91c`
- end: `0x18000f9d6`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014d20`

## callees

- `0x180004cd0`
- `0x18000f91c`
- `0x1800125e0`
- `0x1800132c0`
- `0x1800156d0`
- `0x180035010`

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
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    *a1 = v5;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(&v8);
  return a1;
}

```

## disassembly

```asm
0x18000f91c  mov     [rsp+arg_8], rbx
0x18000f921  mov     [rsp+arg_10], rsi
0x18000f926  push    rdi
0x18000f927  sub     rsp, 20h
0x18000f92b  mov     rsi, rdx
0x18000f92e  mov     rdi, rcx
0x18000f931  mov     qword ptr [rcx], 0
0x18000f938  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f93f  mov     ecx, 20h ; ' '; unsigned __int64
0x18000f944  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f949  mov     rbx, rax
0x18000f94c  mov     [rsp+28h+arg_0], rax
0x18000f951  test    rax, rax
0x18000f954  jz      short loc_18000F9B9
0x18000f956  mov     rsi, [rsi]
0x18000f959  mov     rcx, rax
0x18000f95c  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x18000f961  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x18000f968  mov     [rbx], rcx
0x18000f96b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000f972  test    rcx, rcx
0x18000f975  jz      short loc_18000F984
0x18000f977  mov     rax, [rcx]
0x18000f97a  mov     rax, [rax+8]
0x18000f97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f983  nop
0x18000f984  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x18000f98b  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18000f992  mov     [rbx], rax
0x18000f995  mov     [rbx+18h], rsi
0x18000f999  mov     dword ptr [rbx+0Ch], 2
0x18000f9a0  mov     rcx, [rdi]
0x18000f9a3  test    rcx, rcx
0x18000f9a6  jz      short loc_18000F9AD
0x18000f9a8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18000f9ad  mov     [rdi], rbx
0x18000f9b0  mov     [rsp+28h+arg_0], 0
0x18000f9b9  lea     rcx, [rsp+28h+arg_0]
0x18000f9be  call    ??1?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(void)
0x18000f9c3  mov     rax, rdi
0x18000f9c6  mov     rbx, [rsp+28h+arg_8]
0x18000f9cb  mov     rsi, [rsp+28h+arg_10]
0x18000f9d0  add     rsp, 20h
0x18000f9d4  pop     rdi
0x18000f9d5  retn
```
