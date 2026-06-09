# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x180008578`
- end: `0x180008632`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `186`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ae28`

## callees

- `0x18000446c`
- `0x180006574`
- `0x180008578`
- `0x1800096c8`
- `0x18000f850`
- `0x180027010`

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
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v8);
  return a1;
}

```

## disassembly

```asm
0x180008578  mov     [rsp+arg_8], rbx
0x18000857d  mov     [rsp+arg_10], rsi
0x180008582  push    rdi
0x180008583  sub     rsp, 20h
0x180008587  mov     rsi, rdx
0x18000858a  mov     rdi, rcx
0x18000858d  mov     qword ptr [rcx], 0
0x180008594  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000859b  mov     ecx, 20h ; ' '; unsigned __int64
0x1800085a0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800085a5  mov     rbx, rax
0x1800085a8  mov     [rsp+28h+arg_0], rax
0x1800085ad  test    rax, rax
0x1800085b0  jz      short loc_180008615
0x1800085b2  mov     rsi, [rsi]
0x1800085b5  mov     rcx, rax
0x1800085b8  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x1800085bd  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x1800085c4  mov     [rbx], rcx
0x1800085c7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800085ce  test    rcx, rcx
0x1800085d1  jz      short loc_1800085E0
0x1800085d3  mov     rax, [rcx]
0x1800085d6  mov     rax, [rax+8]
0x1800085da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085df  nop
0x1800085e0  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x1800085e7  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x1800085ee  mov     [rbx], rax
0x1800085f1  mov     [rbx+18h], rsi
0x1800085f5  mov     dword ptr [rbx+0Ch], 2
0x1800085fc  mov     rcx, [rdi]
0x1800085ff  test    rcx, rcx
0x180008602  jz      short loc_180008609
0x180008604  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180008609  mov     [rdi], rbx
0x18000860c  mov     [rsp+28h+arg_0], 0
0x180008615  lea     rcx, [rsp+28h+arg_0]
0x18000861a  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18000861f  mov     rax, rdi
0x180008622  mov     rbx, [rsp+28h+arg_8]
0x180008627  mov     rsi, [rsp+28h+arg_10]
0x18000862c  add     rsp, 20h
0x180008630  pop     rdi
0x180008631  retn
```
