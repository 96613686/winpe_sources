# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x18000cc28`
- end: `0x18000cce2`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `186`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800200e0`

## callees

- `0x18000396c`
- `0x180008320`
- `0x180008408`
- `0x18000cc28`
- `0x180020b20`
- `0x180031010`

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
  Microsoft::WRL::Details::MakeAllocator<CdsToInputTaskHandler>::~MakeAllocator<CdsToInputTaskHandler>(&v8);
  return a1;
}

```

## disassembly

```asm
0x18000cc28  mov     [rsp+arg_8], rbx
0x18000cc2d  mov     [rsp+arg_10], rsi
0x18000cc32  push    rdi
0x18000cc33  sub     rsp, 20h
0x18000cc37  mov     rsi, rdx
0x18000cc3a  mov     rdi, rcx
0x18000cc3d  mov     qword ptr [rcx], 0
0x18000cc44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cc4b  mov     ecx, 20h ; ' '; unsigned __int64
0x18000cc50  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cc55  mov     rbx, rax
0x18000cc58  mov     [rsp+28h+arg_0], rax
0x18000cc5d  test    rax, rax
0x18000cc60  jz      short loc_18000CCC5
0x18000cc62  mov     rsi, [rsi]
0x18000cc65  mov     rcx, rax
0x18000cc68  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x18000cc6d  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x18000cc74  mov     [rbx], rcx
0x18000cc77  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000cc7e  test    rcx, rcx
0x18000cc81  jz      short loc_18000CC90
0x18000cc83  mov     rax, [rcx]
0x18000cc86  mov     rax, [rax+8]
0x18000cc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc8f  nop
0x18000cc90  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x18000cc97  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18000cc9e  mov     [rbx], rax
0x18000cca1  mov     [rbx+18h], rsi
0x18000cca5  mov     dword ptr [rbx+0Ch], 2
0x18000ccac  mov     rcx, [rdi]
0x18000ccaf  test    rcx, rcx
0x18000ccb2  jz      short loc_18000CCB9
0x18000ccb4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18000ccb9  mov     [rdi], rbx
0x18000ccbc  mov     [rsp+28h+arg_0], 0
0x18000ccc5  lea     rcx, [rsp+28h+arg_0]
0x18000ccca  call    ??1?$MakeAllocator@VCdsToInputTaskHandler@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CdsToInputTaskHandler>::~MakeAllocator<CdsToInputTaskHandler>(void)
0x18000cccf  mov     rax, rdi
0x18000ccd2  mov     rbx, [rsp+28h+arg_8]
0x18000ccd7  mov     rsi, [rsp+28h+arg_10]
0x18000ccdc  add     rsp, 20h
0x18000cce0  pop     rdi
0x18000cce1  retn
```
