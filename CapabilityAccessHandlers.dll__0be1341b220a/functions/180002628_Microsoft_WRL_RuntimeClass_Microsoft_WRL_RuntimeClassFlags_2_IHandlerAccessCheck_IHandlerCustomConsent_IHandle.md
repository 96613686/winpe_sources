# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>(void)

- ea: `0x180002628`
- end: `0x180002677`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerAccessCheck@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@WRL@Microsoft@@QEAA@XZ`
- size: `79`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800022c0`
- `0x180002410`
- `0x18000279c`

## callees

- `0x180002628`
- `0x180002680`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>(
        _QWORD *a1)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>();
  *a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::`vftable';
  a1[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::`vftable'{for `IHandlerCustomConsent'};
  a1[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerAccessChange>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x180002628  push    rbx
0x18000262a  sub     rsp, 20h
0x18000262e  mov     rbx, rcx
0x180002631  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>(void)
0x180002636  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerAccessCheck@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::`vftable'
0x18000263d  mov     [rbx], rcx
0x180002640  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerAccessCheck@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@WRL@Microsoft@@6BIHandlerCustomConsent@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::`vftable'{for `IHandlerCustomConsent'}
0x180002647  mov     [rbx+8], rax
0x18000264b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerAccessCheck@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIHandlerAccessChange@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerAccessChange>'}
0x180002652  mov     [rbx+10h], rax
0x180002656  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000265d  test    rcx, rcx
0x180002660  jz      short loc_18000266E
0x180002662  mov     rax, [rcx]
0x180002665  mov     rax, [rax+8]
0x180002669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000266e  mov     rax, rbx
0x180002671  add     rsp, 20h
0x180002675  pop     rbx
0x180002676  retn
```
