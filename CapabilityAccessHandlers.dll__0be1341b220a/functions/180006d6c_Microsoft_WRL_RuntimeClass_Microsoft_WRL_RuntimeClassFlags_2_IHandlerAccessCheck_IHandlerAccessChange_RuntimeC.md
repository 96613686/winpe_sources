# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerAccessChange>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerAccessChange>(void)

- ea: `0x180006d6c`
- end: `0x180006db0`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerAccessCheck@@UIHandlerAccessChange@@@WRL@Microsoft@@QEAA@XZ`
- size: `68`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006150`
- `0x18000624c`

## callees

- `0x1800015e0`
- `0x180006d6c`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerAccessChange>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerAccessChange>(
        _QWORD *a1)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>();
  *a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerAccessChange>::`vftable'{for `IHandlerAccessCheck'};
  a1[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerAccessChange>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerAccessChange>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x180006d6c  push    rbx
0x180006d6e  sub     rsp, 20h
0x180006d72  mov     rbx, rcx
0x180006d75  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessChange@@UIHandlerPolicy@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>(void)
0x180006d7a  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerAccessCheck@@UIHandlerAccessChange@@@WRL@Microsoft@@6BIHandlerAccessCheck@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerAccessChange>::`vftable'{for `IHandlerAccessCheck'}
0x180006d81  mov     [rbx], rcx
0x180006d84  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerAccessCheck@@UIHandlerAccessChange@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIHandlerAccessChange@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerAccessChange>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerAccessChange>'}
0x180006d8b  mov     [rbx+8], rax
0x180006d8f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006d96  test    rcx, rcx
0x180006d99  jz      short loc_180006DA7
0x180006d9b  mov     rax, [rcx]
0x180006d9e  mov     rax, [rax+8]
0x180006da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da7  mov     rax, rbx
0x180006daa  add     rsp, 20h
0x180006dae  pop     rbx
0x180006daf  retn
```
