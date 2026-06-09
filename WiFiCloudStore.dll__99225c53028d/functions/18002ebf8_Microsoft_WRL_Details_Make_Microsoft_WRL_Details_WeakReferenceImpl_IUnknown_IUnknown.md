# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x18002ebf8`
- end: `0x18002ecb2`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `186`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800306d0`

## callees

- `0x18001b2d0`
- `0x18001cd7c`
- `0x18001f5f4`
- `0x18002a448`
- `0x18002ebf8`
- `0x180041010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(
        _QWORD *a1,
        __int64 *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  __int64 v6; // rsi
  void *v8; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
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
0x18002ebf8  mov     [rsp+arg_8], rbx
0x18002ebfd  mov     [rsp+arg_10], rsi
0x18002ec02  push    rdi
0x18002ec03  sub     rsp, 20h
0x18002ec07  mov     rsi, rdx
0x18002ec0a  mov     rdi, rcx
0x18002ec0d  mov     qword ptr [rcx], 0
0x18002ec14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ec1b  mov     ecx, 20h ; ' '; unsigned __int64
0x18002ec20  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ec25  mov     rbx, rax
0x18002ec28  mov     [rsp+28h+arg_0], rax
0x18002ec2d  test    rax, rax
0x18002ec30  jz      short loc_18002EC95
0x18002ec32  mov     rsi, [rsi]
0x18002ec35  mov     rcx, rax
0x18002ec38  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x18002ec3d  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x18002ec44  mov     [rbx], rcx
0x18002ec47  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002ec4e  test    rcx, rcx
0x18002ec51  jz      short loc_18002EC60
0x18002ec53  mov     rax, [rcx]
0x18002ec56  mov     rax, [rax+8]
0x18002ec5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec5f  nop
0x18002ec60  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x18002ec67  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18002ec6e  mov     [rbx], rax
0x18002ec71  mov     [rbx+18h], rsi
0x18002ec75  mov     dword ptr [rbx+0Ch], 2
0x18002ec7c  mov     rcx, [rdi]
0x18002ec7f  test    rcx, rcx
0x18002ec82  jz      short loc_18002EC89
0x18002ec84  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18002ec89  mov     [rdi], rbx
0x18002ec8c  mov     [rsp+28h+arg_0], 0
0x18002ec95  lea     rcx, [rsp+28h+arg_0]
0x18002ec9a  call    ??1?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(void)
0x18002ec9f  mov     rax, rdi
0x18002eca2  mov     rbx, [rsp+28h+arg_8]
0x18002eca7  mov     rsi, [rsp+28h+arg_10]
0x18002ecac  add     rsp, 20h
0x18002ecb0  pop     rdi
0x18002ecb1  retn
```
