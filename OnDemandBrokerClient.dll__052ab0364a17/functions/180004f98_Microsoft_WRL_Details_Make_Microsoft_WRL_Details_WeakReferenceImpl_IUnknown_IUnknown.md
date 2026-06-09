# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x180004f98`
- end: `0x180005051`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `185`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005820`

## callees

- `0x180004d50`
- `0x180004f98`
- `0x180005058`
- `0x180005090`
- `0x180006010`
- `0x180007010`

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
0x180004f98  mov     [rsp+arg_8], rbx
0x180004f9d  mov     [rsp+arg_10], rsi
0x180004fa2  push    rdi
0x180004fa3  sub     rsp, 20h
0x180004fa7  mov     rsi, rdx
0x180004faa  mov     qword ptr [rcx], 0
0x180004fb1  mov     rdi, rcx
0x180004fb4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004fbb  mov     ecx, 20h ; ' '; unsigned __int64
0x180004fc0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004fc5  mov     [rsp+28h+arg_0], rax
0x180004fca  mov     rbx, rax
0x180004fcd  test    rax, rax
0x180004fd0  jz      short loc_180005034
0x180004fd2  mov     rsi, [rsi]
0x180004fd5  mov     rcx, rax
0x180004fd8  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x180004fdd  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x180004fe4  mov     [rbx], rcx
0x180004fe7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004fee  test    rcx, rcx
0x180004ff1  jz      short loc_180004FFF
0x180004ff3  mov     rdx, [rcx]
0x180004ff6  mov     rax, [rdx+8]
0x180004ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fff  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x180005006  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18000500d  mov     [rbx], rax
0x180005010  mov     [rbx+18h], rsi
0x180005014  mov     dword ptr [rbx+0Ch], 2
0x18000501b  mov     rcx, [rdi]
0x18000501e  test    rcx, rcx
0x180005021  jz      short loc_180005028
0x180005023  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180005028  mov     [rdi], rbx
0x18000502b  mov     [rsp+28h+arg_0], 0
0x180005034  lea     rcx, [rsp+28h+arg_0]
0x180005039  call    ??1?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(void)
0x18000503e  mov     rbx, [rsp+28h+arg_8]
0x180005043  mov     rax, rdi
0x180005046  mov     rsi, [rsp+28h+arg_10]
0x18000504b  add     rsp, 20h
0x18000504f  pop     rdi
0x180005050  retn
```
