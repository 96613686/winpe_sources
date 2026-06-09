# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x18000a5fc`
- end: `0x18000a6b6`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `186`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015b20`

## callees

- `0x180002798`
- `0x18000a5fc`
- `0x18000f4b4`
- `0x180010b18`
- `0x180018250`
- `0x180025010`

## pseudocode

```c
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
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release();
    *a1 = v5;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(&v8);
  return a1;
}

```

## disassembly

```asm
0x18000a5fc  mov     [rsp+arg_8], rbx
0x18000a601  mov     [rsp+arg_10], rsi
0x18000a606  push    rdi
0x18000a607  sub     rsp, 20h
0x18000a60b  mov     rsi, rdx
0x18000a60e  mov     rdi, rcx
0x18000a611  mov     qword ptr [rcx], 0
0x18000a618  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a61f  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a624  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a629  mov     rbx, rax
0x18000a62c  mov     [rsp+28h+arg_0], rax
0x18000a631  test    rax, rax
0x18000a634  jz      short loc_18000A699
0x18000a636  mov     rsi, [rsi]
0x18000a639  mov     rcx, rax
0x18000a63c  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x18000a641  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x18000a648  mov     [rbx], rcx
0x18000a64b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a652  test    rcx, rcx
0x18000a655  jz      short loc_18000A664
0x18000a657  mov     rax, [rcx]
0x18000a65a  mov     rax, [rax+8]
0x18000a65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a663  nop
0x18000a664  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x18000a66b  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18000a672  mov     [rbx], rax
0x18000a675  mov     [rbx+18h], rsi
0x18000a679  mov     dword ptr [rbx+0Ch], 2
0x18000a680  mov     rcx, [rdi]
0x18000a683  test    rcx, rcx
0x18000a686  jz      short loc_18000A68D
0x18000a688  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x18000a68d  mov     [rdi], rbx
0x18000a690  mov     [rsp+28h+arg_0], 0
0x18000a699  lea     rcx, [rsp+28h+arg_0]
0x18000a69e  call    ??1?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(void)
0x18000a6a3  mov     rax, rdi
0x18000a6a6  mov     rbx, [rsp+28h+arg_8]
0x18000a6ab  mov     rsi, [rsp+28h+arg_10]
0x18000a6b0  add     rsp, 20h
0x18000a6b4  pop     rdi
0x18000a6b5  retn
```
