# Microsoft::WRL::Details::CreateWeakReference(IUnknown *)

- ea: `0x18000a4f8`
- end: `0x18000a576`
- name: `?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z`
- size: `126`
- prototype: `struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall(Microsoft::WRL::Details *__hidden this, struct IUnknown *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c540`
- `0x18000c650`
- `0x18000f0e0`

## callees

- `0x1800022fc`
- `0x18000a4f8`
- `0x180011010`

## pseudocode

```c
struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall Microsoft::WRL::Details::CreateWeakReference(
        Microsoft::WRL::Details *this,
        struct IUnknown *a2)
{
  _DWORD *v3; // rax
  _DWORD *v4; // rbx

  v3 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( !v3 )
    return 0;
  v3[3] = 1;
  *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  v4[4] = 0x3FFFFFFF;
  *(_QWORD *)v4 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
  *((_QWORD *)v4 + 3) = this;
  v4[3] = 2;
  return (struct Microsoft::WRL::Details::WeakReferenceImpl *)v4;
}

```

## disassembly

```asm
0x18000a4f8  mov     [rsp+arg_0], rbx
0x18000a4fd  push    rdi
0x18000a4fe  sub     rsp, 20h
0x18000a502  mov     rdi, rcx
0x18000a505  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a50c  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a511  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a516  mov     rbx, rax
0x18000a519  test    rax, rax
0x18000a51c  jz      short loc_18000A566
0x18000a51e  mov     dword ptr [rax+0Ch], 1
0x18000a525  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x18000a52c  mov     [rbx], rax
0x18000a52f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a536  test    rcx, rcx
0x18000a539  jz      short loc_18000A548
0x18000a53b  mov     rax, [rcx]
0x18000a53e  mov     rax, [rax+8]
0x18000a542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a547  nop
0x18000a548  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x18000a54f  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18000a556  mov     [rbx], rax
0x18000a559  mov     [rbx+18h], rdi
0x18000a55d  mov     dword ptr [rbx+0Ch], 2
0x18000a564  jmp     short loc_18000A568
0x18000a566  xor     ebx, ebx
0x18000a568  mov     rax, rbx
0x18000a56b  mov     rbx, [rsp+28h+arg_0]
0x18000a570  add     rsp, 20h
0x18000a574  pop     rdi
0x18000a575  retn
```
