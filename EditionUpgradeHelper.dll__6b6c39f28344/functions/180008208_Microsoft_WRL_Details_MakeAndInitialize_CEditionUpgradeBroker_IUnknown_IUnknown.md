# Microsoft::WRL::Details::MakeAndInitialize<CEditionUpgradeBroker,IUnknown,>(IUnknown * *)

- ea: `0x180008208`
- end: `0x1800082f3`
- name: `??$MakeAndInitialize@VCEditionUpgradeBroker@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008c80`

## callees

- `0x180001d0c`
- `0x180008208`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CEditionUpgradeBroker,IUnknown,>(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v5; // rcx
  unsigned int v6; // ebx

  *a1 = 0;
  v2 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v5 = Microsoft::WRL::Details::ModuleBase::module_;
  *((_DWORD *)v2 + 9) = 1;
  *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::`vftable'{for `IEditionUpgradeBroker'};
  v2[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>'};
  v2[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::`vftable'{for `IClipServiceNotificationHelper'};
  v2[3] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFClipNotificationHelper>'};
  if ( v5 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
  *v3 = &CEditionUpgradeBroker::`vftable'{for `IEditionUpgradeBroker'};
  v3[6] = 0;
  v3[1] = &CEditionUpgradeBroker::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>'};
  v3[2] = &CEditionUpgradeBroker::`vftable'{for `IClipServiceNotificationHelper'};
  v3[3] = &CEditionUpgradeBroker::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFClipNotificationHelper>'};
  v6 = ((__int64 (__fastcall *)(_QWORD *, GUID *, _QWORD *))CEditionUpgradeBroker::`vftable'{for `IEditionUpgradeBroker'})(
         v3,
         &GUID_00000000_0000_0000_c000_000000000046,
         a1);
  (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
  return v6;
}

```

## disassembly

```asm
0x180008208  mov     [rsp+arg_0], rbx
0x18000820d  push    rdi
0x18000820e  sub     rsp, 20h
0x180008212  mov     rbx, rcx
0x180008215  mov     qword ptr [rcx], 0
0x18000821c  mov     ecx, 38h ; '8'; unsigned __int64
0x180008221  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008228  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000822d  mov     rdi, rax
0x180008230  test    rax, rax
0x180008233  jnz     short loc_18000823F
0x180008235  mov     eax, 8007000Eh
0x18000823a  jmp     loc_1800082E8
0x18000823f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008246  mov     dword ptr [rax+24h], 1
0x18000824d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@WRL@Microsoft@@6BIEditionUpgradeBroker@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::`vftable'{for `IEditionUpgradeBroker'}
0x180008254  mov     [rdi], rax
0x180008257  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>'}
0x18000825e  mov     [rdi+8], rax
0x180008262  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@WRL@Microsoft@@6BIClipServiceNotificationHelper@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::`vftable'{for `IClipServiceNotificationHelper'}
0x180008269  mov     [rdi+10h], rax
0x18000826d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFClipNotificationHelper@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFClipNotificationHelper>'}
0x180008274  mov     [rdi+18h], rax
0x180008278  test    rcx, rcx
0x18000827b  jz      short loc_180008289
0x18000827d  mov     rax, [rcx]
0x180008280  mov     rax, [rax+8]
0x180008284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008289  lea     rax, ??_7CEditionUpgradeBroker@@6BIEditionUpgradeBroker@@@; const CEditionUpgradeBroker::`vftable'{for `IEditionUpgradeBroker'}
0x180008290  mov     r8, rbx
0x180008293  mov     [rdi], rax
0x180008296  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000829d  lea     rax, ??_7CEditionUpgradeBroker@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@Details@WRL@Microsoft@@@; const CEditionUpgradeBroker::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>'}
0x1800082a4  mov     qword ptr [rdi+30h], 0
0x1800082ac  mov     [rdi+8], rax
0x1800082b0  mov     rcx, rdi
0x1800082b3  lea     rax, ??_7CEditionUpgradeBroker@@6BIClipServiceNotificationHelper@@@; const CEditionUpgradeBroker::`vftable'{for `IClipServiceNotificationHelper'}
0x1800082ba  mov     [rdi+10h], rax
0x1800082be  lea     rax, ??_7CEditionUpgradeBroker@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFClipNotificationHelper@@@Details@WRL@Microsoft@@@; const CEditionUpgradeBroker::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFClipNotificationHelper>'}
0x1800082c5  mov     [rdi+18h], rax
0x1800082c9  mov     rax, cs:??_7CEditionUpgradeBroker@@6BIEditionUpgradeBroker@@@; const CEditionUpgradeBroker::`vftable'{for `IEditionUpgradeBroker'}
0x1800082d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082d5  mov     rcx, [rdi]
0x1800082d8  mov     ebx, eax
0x1800082da  mov     rax, [rcx+10h]
0x1800082de  mov     rcx, rdi
0x1800082e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082e6  mov     eax, ebx
0x1800082e8  mov     rbx, [rsp+28h+arg_0]
0x1800082ed  add     rsp, 20h
0x1800082f1  pop     rdi
0x1800082f2  retn
```
