# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x180017ecc`
- end: `0x180017f85`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `185`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018230`

## callees

- `0x18000a590`
- `0x1800136a8`
- `0x180013ce8`
- `0x180017ecc`
- `0x180018c00`
- `0x18001c010`

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
  v4 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
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
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::EventTargetArray>::~MakeAllocator<Microsoft::WRL::Details::EventTargetArray>(&v8);
  return a1;
}

```

## disassembly

```asm
0x180017ecc  mov     [rsp+arg_8], rbx
0x180017ed1  mov     [rsp+arg_10], rsi
0x180017ed6  push    rdi
0x180017ed7  sub     rsp, 20h
0x180017edb  mov     rsi, rdx
0x180017ede  mov     qword ptr [rcx], 0
0x180017ee5  mov     rdi, rcx
0x180017ee8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017eef  mov     ecx, 20h ; ' '; unsigned __int64
0x180017ef4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017ef9  mov     [rsp+28h+arg_0], rax
0x180017efe  mov     rbx, rax
0x180017f01  test    rax, rax
0x180017f04  jz      short loc_180017F68
0x180017f06  mov     rsi, [rsi]
0x180017f09  mov     rcx, rax
0x180017f0c  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>(void)
0x180017f11  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x180017f18  mov     [rbx], rcx
0x180017f1b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180017f22  test    rcx, rcx
0x180017f25  jz      short loc_180017F33
0x180017f27  mov     rdx, [rcx]
0x180017f2a  mov     rax, [rdx+8]
0x180017f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f33  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x180017f3a  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x180017f41  mov     [rbx], rax
0x180017f44  mov     [rbx+18h], rsi
0x180017f48  mov     dword ptr [rbx+0Ch], 2
0x180017f4f  mov     rcx, [rdi]
0x180017f52  test    rcx, rcx
0x180017f55  jz      short loc_180017F5C
0x180017f57  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180017f5c  mov     [rdi], rbx
0x180017f5f  mov     [rsp+28h+arg_0], 0
0x180017f68  lea     rcx, [rsp+28h+arg_0]
0x180017f6d  call    ??1?$MakeAllocator@VEventTargetArray@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::EventTargetArray>::~MakeAllocator<Microsoft::WRL::Details::EventTargetArray>(void)
0x180017f72  mov     rbx, [rsp+28h+arg_8]
0x180017f77  mov     rax, rdi
0x180017f7a  mov     rsi, [rsp+28h+arg_10]
0x180017f7f  add     rsp, 20h
0x180017f83  pop     rdi
0x180017f84  retn
```
