# Microsoft::WRL::SimpleClassFactory<CameraCapabilityHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001f10`
- end: `0x180002001`
- name: `?CreateInstance@?$SimpleClassFactory@VCameraCapabilityHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001f10`
- `0x180002010`
- `0x180002080`
- `0x180004c94`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180001fe6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180001fe6`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CameraCapabilityHandler,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  void *v6; // rax
  void *v7; // rdi
  unsigned int v8; // ebx

  *a4 = 0;
  if ( a2 )
  {
    RoOriginateError(2147746064LL, 0);
    return 2147746064LL;
  }
  else
  {
    v6 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck>((__int64)v6);
      *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerPolicy>::`vftable';
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v7 = &CameraCapabilityHandler::`vftable';
      ((void (__fastcall *)(void *))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerCustomConsent>::AddRef)(v7);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerPolicy>::Release(v7);
      v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, a3, a4);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
      return v8;
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
0x180001f10  mov     [rsp+arg_0], rbx
0x180001f15  mov     [rsp+arg_8], rsi
0x180001f1a  push    rdi
0x180001f1b  sub     rsp, 20h
0x180001f1f  mov     rbx, r9
0x180001f22  mov     rsi, r8
0x180001f25  mov     qword ptr [r9], 0
0x180001f2c  test    rdx, rdx
0x180001f2f  jnz     loc_180001FDF
0x180001f35  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001f3c  mov     ecx, 10h; unsigned __int64
0x180001f41  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001f46  mov     rdi, rax
0x180001f49  test    rax, rax
0x180001f4c  jz      loc_180001FD8
0x180001f52  mov     rcx, rax
0x180001f55  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck>(void)
0x180001f5a  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerPolicy@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerPolicy>::`vftable'
0x180001f61  mov     [rdi], rcx
0x180001f64  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180001f6b  test    rcx, rcx
0x180001f6e  jz      short loc_180001F7D
0x180001f70  mov     rdx, [rcx]
0x180001f73  mov     rax, [rdx+8]
0x180001f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f7c  nop
0x180001f7d  lea     rax, ??_7CameraCapabilityHandler@@6B@; const CameraCapabilityHandler::`vftable'
0x180001f84  mov     [rdi], rax
0x180001f87  mov     rcx, rdi
0x180001f8a  mov     rax, cs:off_180015100
0x180001f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f96  nop
0x180001f97  mov     rcx, rdi
0x180001f9a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerPolicy@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerPolicy>::Release(void)
0x180001f9f  nop
0x180001fa0  mov     rax, [rdi]
0x180001fa3  mov     r8, rbx
0x180001fa6  mov     rdx, rsi
0x180001fa9  mov     rcx, rdi
0x180001fac  mov     rax, [rax]
0x180001faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fb4  mov     ebx, eax
0x180001fb6  mov     rcx, [rdi]
0x180001fb9  mov     rax, [rcx+10h]
0x180001fbd  mov     rcx, rdi
0x180001fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc5  nop
0x180001fc6  mov     eax, ebx
0x180001fc8  mov     rbx, [rsp+28h+arg_0]
0x180001fcd  mov     rsi, [rsp+28h+arg_8]
0x180001fd2  add     rsp, 20h
0x180001fd6  pop     rdi
0x180001fd7  retn
0x180001fd8  mov     eax, 8007000Eh
0x180001fdd  jmp     short loc_180001FC8
0x180001fdf  xor     edx, edx
0x180001fe1  mov     ecx, 80040110h
0x180001fe6  call    cs:__imp_RoOriginateError
0x180001fec  mov     eax, 80040110h
0x180001ff1  mov     rbx, [rsp+28h+arg_0]
0x180001ff6  mov     rsi, [rsp+28h+arg_8]
0x180001ffb  add     rsp, 20h
0x180001fff  pop     rdi
0x180002000  retn
```
