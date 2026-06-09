# Microsoft::WRL::SimpleClassFactory<LocationCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001460`
- end: `0x1800015d0`
- name: `?CreateInstance@?$SimpleClassFactory@VLocationCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `368`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001460`
- `0x1800015e0`
- `0x180004c94`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000158c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000158c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<LocationCapabilityHandler,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  void *v6; // rax
  __int64 v7; // rbx
  signed __int32 i; // edx
  unsigned int v9; // edi

  *a4 = 0;
  if ( a2 )
  {
    RoOriginateError(2147746064LL, 0);
    return 2147746064LL;
  }
  else
  {
    v6 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = (__int64)v6;
    if ( v6 )
    {
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>((__int64)v6);
      *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessChange,IHandlerPolicy>::`vftable'{for `IHandlerAccessChange'};
      *(_QWORD *)(v7 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessChange,IHandlerPolicy>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerPolicy>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v7 = &LocationCapabilityHandler::`vftable'{for `IHandlerAccessChange'};
      *(_QWORD *)(v7 + 8) = &LocationCapabilityHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerPolicy>'};
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::AddRef(v7);
      for ( i = *(_DWORD *)(v7 + 20); i != 0x7FFFFFFF; i = *(_DWORD *)(v7 + 20) )
      {
        if ( i == _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 20), i - 1, i) )
          break;
      }
      if ( i == 1 )
      {
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 32LL))(v7, 1);
        if ( Microsoft::WRL::Details::ModuleBase::module_ )
          (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                               + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
      }
      v9 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v7)(v7, a3, a4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      return v9;
    }
    else
    {
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x180001460  mov     [rsp+arg_0], rbx
0x180001465  mov     [rsp+arg_8], rsi
0x18000146a  push    rdi
0x18000146b  sub     rsp, 20h
0x18000146f  mov     rdi, r9
0x180001472  mov     rsi, r8
0x180001475  mov     qword ptr [r9], 0
0x18000147c  test    rdx, rdx
0x18000147f  jnz     loc_180001585
0x180001485  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000148c  mov     ecx, 18h; unsigned __int64
0x180001491  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001496  mov     rbx, rax
0x180001499  test    rax, rax
0x18000149c  jz      loc_1800015BB
0x1800014a2  mov     rcx, rax
0x1800014a5  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessChange@@UIHandlerPolicy@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>(void)
0x1800014aa  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerAccessChange@@UIHandlerPolicy@@@WRL@Microsoft@@6BIHandlerAccessChange@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessChange,IHandlerPolicy>::`vftable'{for `IHandlerAccessChange'}
0x1800014b1  mov     [rbx], rcx
0x1800014b4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerAccessChange@@UIHandlerPolicy@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIHandlerPolicy@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessChange,IHandlerPolicy>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerPolicy>'}
0x1800014bb  mov     [rbx+8], rax
0x1800014bf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800014c6  test    rcx, rcx
0x1800014c9  jz      short loc_1800014D8
0x1800014cb  mov     rax, [rcx]
0x1800014ce  mov     rax, [rax+8]
0x1800014d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014d7  nop
0x1800014d8  lea     rax, ??_7LocationCapabilityHandler@@6BIHandlerAccessChange@@@; const LocationCapabilityHandler::`vftable'{for `IHandlerAccessChange'}
0x1800014df  mov     [rbx], rax
0x1800014e2  lea     rax, ??_7LocationCapabilityHandler@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIHandlerPolicy@@@Details@WRL@Microsoft@@@; const LocationCapabilityHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerPolicy>'}
0x1800014e9  mov     [rbx+8], rax
0x1800014ed  mov     rcx, rbx
0x1800014f0  mov     rax, cs:off_180015040
0x1800014f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014fc  nop
0x1800014fd  mov     edx, [rbx+14h]
0x180001500  cmp     edx, 7FFFFFFFh
0x180001506  jz      short loc_180001518
0x180001508  lea     ecx, [rdx-1]
0x18000150b  mov     eax, edx
0x18000150d  lock cmpxchg [rbx+14h], ecx
0x180001512  jnz     loc_1800015A7
0x180001518  lea     eax, [rdx-1]
0x18000151b  test    eax, eax
0x18000151d  jz      short loc_180001557
0x18000151f  mov     rax, [rbx]
0x180001522  mov     r8, rdi
0x180001525  mov     rdx, rsi
0x180001528  mov     rcx, rbx
0x18000152b  mov     rax, [rax]
0x18000152e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001533  mov     edi, eax
0x180001535  mov     rcx, [rbx]
0x180001538  mov     rax, [rcx+10h]
0x18000153c  mov     rcx, rbx
0x18000153f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001544  nop
0x180001545  mov     eax, edi
0x180001547  mov     rbx, [rsp+28h+arg_0]
0x18000154c  mov     rsi, [rsp+28h+arg_8]
0x180001551  add     rsp, 20h
0x180001555  pop     rdi
0x180001556  retn
0x180001557  mov     rax, [rbx]
0x18000155a  mov     edx, 1
0x18000155f  mov     rcx, rbx
0x180001562  mov     rax, [rax+20h]
0x180001566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000156b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180001572  test    rcx, rcx
0x180001575  jz      short loc_18000151F
0x180001577  mov     rax, [rcx]
0x18000157a  mov     rax, [rax+10h]
0x18000157e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001583  jmp     short loc_18000151F
0x180001585  xor     edx, edx
0x180001587  mov     ecx, 80040110h
0x18000158c  call    cs:__imp_RoOriginateError
0x180001592  mov     eax, 80040110h
0x180001597  mov     rbx, [rsp+28h+arg_0]
0x18000159c  mov     rsi, [rsp+28h+arg_8]
0x1800015a1  add     rsp, 20h
0x1800015a5  pop     rdi
0x1800015a6  retn
0x1800015a7  mov     edx, [rbx+14h]
0x1800015aa  cmp     edx, 7FFFFFFFh
0x1800015b0  jnz     loc_180001508
0x1800015b6  jmp     loc_180001518
0x1800015bb  mov     eax, 8007000Eh
0x1800015c0  mov     rbx, [rsp+28h+arg_0]
0x1800015c5  mov     rsi, [rsp+28h+arg_8]
0x1800015ca  add     rsp, 20h
0x1800015ce  pop     rdi
0x1800015cf  retn
```
