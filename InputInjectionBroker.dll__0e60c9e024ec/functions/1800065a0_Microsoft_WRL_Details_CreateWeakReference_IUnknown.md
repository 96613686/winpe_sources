# Microsoft::WRL::Details::CreateWeakReference(IUnknown *)

- ea: `0x1800065a0`
- end: `0x18000661e`
- name: `?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z`
- size: `126`
- prototype: `struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall(Microsoft::WRL::Details *__hidden this, struct IUnknown *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800068d0`
- `0x18000aad0`

## callees

- `0x180001e68`
- `0x1800065a0`
- `0x180012010`

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
0x1800065a0  mov     [rsp+arg_0], rbx
0x1800065a5  push    rdi
0x1800065a6  sub     rsp, 20h
0x1800065aa  mov     rdi, rcx
0x1800065ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800065b4  mov     ecx, 20h ; ' '; unsigned __int64
0x1800065b9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800065be  mov     rbx, rax
0x1800065c1  test    rax, rax
0x1800065c4  jz      short loc_18000660E
0x1800065c6  mov     dword ptr [rax+0Ch], 1
0x1800065cd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x1800065d4  mov     [rbx], rax
0x1800065d7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800065de  test    rcx, rcx
0x1800065e1  jz      short loc_1800065F0
0x1800065e3  mov     rax, [rcx]
0x1800065e6  mov     rax, [rax+8]
0x1800065ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ef  nop
0x1800065f0  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x1800065f7  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x1800065fe  mov     [rbx], rax
0x180006601  mov     [rbx+18h], rdi
0x180006605  mov     dword ptr [rbx+0Ch], 2
0x18000660c  jmp     short loc_180006610
0x18000660e  xor     ebx, ebx
0x180006610  mov     rax, rbx
0x180006613  mov     rbx, [rsp+28h+arg_0]
0x180006618  add     rsp, 20h
0x18000661c  pop     rdi
0x18000661d  retn
```
