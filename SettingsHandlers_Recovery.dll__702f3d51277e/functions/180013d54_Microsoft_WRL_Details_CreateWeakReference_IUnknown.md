# Microsoft::WRL::Details::CreateWeakReference(IUnknown *)

- ea: `0x180013d54`
- end: `0x180013dd2`
- name: `?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z`
- size: `126`
- prototype: `struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall(Microsoft::WRL::Details *__hidden this, struct IUnknown *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a900`
- `0x18001aa10`
- `0x18001ab20`
- `0x18001ac30`
- `0x18001ad40`

## callees

- `0x180002380`
- `0x180013d54`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013d54  mov     [rsp+arg_0], rbx
0x180013d59  push    rdi
0x180013d5a  sub     rsp, 20h
0x180013d5e  mov     rdi, rcx
0x180013d61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013d68  mov     ecx, 20h ; ' '; unsigned __int64
0x180013d6d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013d72  mov     rbx, rax
0x180013d75  test    rax, rax
0x180013d78  jz      short loc_180013DC2
0x180013d7a  mov     dword ptr [rax+0Ch], 1
0x180013d81  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x180013d88  mov     [rbx], rax
0x180013d8b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180013d92  test    rcx, rcx
0x180013d95  jz      short loc_180013DA4
0x180013d97  mov     rax, [rcx]
0x180013d9a  mov     rax, [rax+8]
0x180013d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da3  nop
0x180013da4  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x180013dab  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x180013db2  mov     [rbx], rax
0x180013db5  mov     [rbx+18h], rdi
0x180013db9  mov     dword ptr [rbx+0Ch], 2
0x180013dc0  jmp     short loc_180013DC4
0x180013dc2  xor     ebx, ebx
0x180013dc4  mov     rax, rbx
0x180013dc7  mov     rbx, [rsp+28h+arg_0]
0x180013dcc  add     rsp, 20h
0x180013dd0  pop     rdi
0x180013dd1  retn
```
