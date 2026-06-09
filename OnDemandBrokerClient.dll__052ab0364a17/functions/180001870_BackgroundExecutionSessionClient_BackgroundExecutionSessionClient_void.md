# BackgroundExecutionSessionClient::BackgroundExecutionSessionClient(void)

- ea: `0x180001870`
- end: `0x180001916`
- name: `??0BackgroundExecutionSessionClient@@QEAA@XZ`
- size: `166`
- prototype: `BackgroundExecutionSessionClient *__fastcall(BackgroundExecutionSessionClient *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800015a0`

## callees

- `0x180001870`
- `0x180001920`
- `0x180007010`

## pseudocode

```c
BackgroundExecutionSessionClient *__fastcall BackgroundExecutionSessionClient::BackgroundExecutionSessionClient(
        BackgroundExecutionSessionClient *this)
{
  struct Microsoft::WRL::Details::ModuleBase *v2; // rcx

  Microsoft::WRL::FtmBase::FtmBase((BackgroundExecutionSessionClient *)((char *)this + 8));
  v2 = Microsoft::WRL::Details::ModuleBase::module_;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>'};
  *((_QWORD *)this + 5) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 6) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'};
  *((_QWORD *)this + 8) = 1;
  if ( v2 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v2 + 8LL))(v2);
  *(_QWORD *)this = &BackgroundExecutionSessionClient::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>'};
  *((_QWORD *)this + 5) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 6) = &BackgroundExecutionSessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'};
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  return this;
}

```

## disassembly

```asm
0x180001870  mov     [rsp+arg_0], rbx
0x180001875  push    rdi
0x180001876  sub     rsp, 20h
0x18000187a  mov     rbx, rcx
0x18000187d  add     rcx, 8; this
0x180001881  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180001886  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000188d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6BIInspectable@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IInspectable'}
0x180001894  mov     [rbx], rax
0x180001897  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>'}
0x18000189e  mov     [rbx+8], rax
0x1800018a2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IWeakReferenceSource'}
0x1800018a9  mov     [rbx+28h], rax
0x1800018ad  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'}
0x1800018b4  mov     [rbx+30h], rax
0x1800018b8  mov     qword ptr [rbx+40h], 1
0x1800018c0  test    rcx, rcx
0x1800018c3  jnz     short loc_180001908
0x1800018c5  lea     rax, ??_7BackgroundExecutionSessionClient@@6BIInspectable@@@; const BackgroundExecutionSessionClient::`vftable'{for `IInspectable'}
0x1800018cc  mov     [rbx], rax
0x1800018cf  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>'}
0x1800018d6  mov     [rbx+8], rax
0x1800018da  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IWeakReferenceSource'}
0x1800018e1  mov     [rbx+28h], rax
0x1800018e5  lea     rax, ??_7BackgroundExecutionSessionClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIInspectable@@@Details@WRL@Microsoft@@@; const BackgroundExecutionSessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'}
0x1800018ec  mov     [rbx+30h], rax
0x1800018f0  xor     eax, eax
0x1800018f2  mov     [rbx+68h], rax
0x1800018f6  mov     [rbx+70h], rax
0x1800018fa  mov     rax, rbx
0x1800018fd  mov     rbx, [rsp+28h+arg_0]
0x180001902  add     rsp, 20h
0x180001906  pop     rdi
0x180001907  retn
0x180001908  mov     rax, [rcx]
0x18000190b  mov     rax, [rax+8]
0x18000190f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001914  jmp     short loc_1800018C5
```
