# Microsoft::WRL::Details::CreateWeakReference(IUnknown *)

- ea: `0x1800090d8`
- end: `0x180009155`
- name: `?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z`
- size: `125`
- prototype: `struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall(Microsoft::WRL::Details *__hidden this, struct IUnknown *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bd40`
- `0x18000be50`
- `0x18000bf50`
- `0x18000c050`
- `0x180011ba0`

## callees

- `0x180001de4`
- `0x1800090d8`
- `0x180019010`

## pseudocode

```c
struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall Microsoft::WRL::Details::CreateWeakReference(
        Microsoft::WRL::Details *this,
        struct IUnknown *a2)
{
  _DWORD *v3; // rax
  _DWORD *v4; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v5; // rcx

  v3 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v4 = v3;
  if ( !v3 )
    return 0;
  v5 = Microsoft::WRL::Details::ModuleBase::module_;
  v3[3] = 1;
  *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable';
  if ( v5 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
  v4[4] = 0x3FFFFFFF;
  *(_QWORD *)v4 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
  *((_QWORD *)v4 + 3) = this;
  v4[3] = 2;
  return (struct Microsoft::WRL::Details::WeakReferenceImpl *)v4;
}

```

## disassembly

```asm
0x1800090d8  mov     [rsp+arg_0], rbx
0x1800090dd  push    rdi
0x1800090de  sub     rsp, 20h
0x1800090e2  mov     rdi, rcx
0x1800090e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800090ec  mov     ecx, 20h ; ' '; unsigned __int64
0x1800090f1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800090f6  mov     rbx, rax
0x1800090f9  test    rax, rax
0x1800090fc  jz      short loc_180009145
0x1800090fe  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180009105  mov     dword ptr [rax+0Ch], 1
0x18000910c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x180009113  mov     [rbx], rax
0x180009116  test    rcx, rcx
0x180009119  jz      short loc_180009127
0x18000911b  mov     rax, [rcx]
0x18000911e  mov     rax, [rax+8]
0x180009122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009127  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18000912e  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x180009135  mov     [rbx], rax
0x180009138  mov     [rbx+18h], rdi
0x18000913c  mov     dword ptr [rbx+0Ch], 2
0x180009143  jmp     short loc_180009147
0x180009145  xor     ebx, ebx
0x180009147  mov     rax, rbx
0x18000914a  mov     rbx, [rsp+28h+arg_0]
0x18000914f  add     rsp, 20h
0x180009153  pop     rdi
0x180009154  retn
```
