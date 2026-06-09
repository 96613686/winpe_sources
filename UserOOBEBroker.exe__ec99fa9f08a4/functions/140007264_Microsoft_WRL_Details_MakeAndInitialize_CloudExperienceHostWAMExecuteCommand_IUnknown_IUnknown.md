# Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostWAMExecuteCommand,IUnknown,>(IUnknown * *)

- ea: `0x140007264`
- end: `0x140007313`
- name: `??$MakeAndInitialize@VCloudExperienceHostWAMExecuteCommand@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140008c90`

## callees

- `0x1400025d8`
- `0x140007264`
- `0x14000aad0`
- `0x14000c350`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostWAMExecuteCommand,IUnknown,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  unsigned int Interface; // ebx

  *a1 = 0;
  v2 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  *((_DWORD *)v2 + 5) = 1;
  *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IObjectWithSelection>::`vftable'{for `IExecuteCommand'};
  v2[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IObjectWithSelection>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v3 = &CloudExperienceHostWAMExecuteCommand::`vftable'{for `IExecuteCommand'};
  v3[1] = &CloudExperienceHostExecuteCommand::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'};
  v3[3] = 0;
  Interface = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::QueryInterface(
                v3,
                &GUID_00000000_0000_0000_c000_000000000046,
                a1);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::Release(v3);
  return Interface;
}

```

## disassembly

```asm
0x140007264  mov     [rsp+arg_0], rbx
0x140007269  push    rdi
0x14000726a  sub     rsp, 20h
0x14000726e  mov     rbx, rcx
0x140007271  mov     qword ptr [rcx], 0
0x140007278  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000727f  mov     ecx, 20h ; ' '; unsigned __int64
0x140007284  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140007289  mov     rdi, rax
0x14000728c  test    rax, rax
0x14000728f  jnz     short loc_140007298
0x140007291  mov     eax, 8007000Eh
0x140007296  jmp     short loc_140007308
0x140007298  mov     dword ptr [rax+14h], 1
0x14000729f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIExecuteCommand@@UIObjectWithSelection@@@WRL@Microsoft@@6BIExecuteCommand@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IObjectWithSelection>::`vftable'{for `IExecuteCommand'}
0x1400072a6  mov     [rdi], rax
0x1400072a9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIExecuteCommand@@UIObjectWithSelection@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectWithSelection@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IObjectWithSelection>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'}
0x1400072b0  mov     [rdi+8], rax
0x1400072b4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400072bb  test    rcx, rcx
0x1400072be  jz      short loc_1400072CD
0x1400072c0  mov     rax, [rcx]
0x1400072c3  mov     rax, [rax+8]
0x1400072c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400072cc  nop
0x1400072cd  lea     rax, ??_7CloudExperienceHostWAMExecuteCommand@@6BIExecuteCommand@@@; const CloudExperienceHostWAMExecuteCommand::`vftable'{for `IExecuteCommand'}
0x1400072d4  mov     [rdi], rax
0x1400072d7  lea     rax, ??_7CloudExperienceHostExecuteCommand@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectWithSelection@@@Details@WRL@Microsoft@@@; const CloudExperienceHostExecuteCommand::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'}
0x1400072de  mov     [rdi+8], rax
0x1400072e2  mov     qword ptr [rdi+18h], 0
0x1400072ea  mov     r8, rbx
0x1400072ed  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1400072f4  mov     rcx, rdi
0x1400072f7  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::QueryInterface(_GUID const &,void * *)
0x1400072fc  mov     ebx, eax
0x1400072fe  mov     rcx, rdi
0x140007301  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::Release(void)
0x140007306  mov     eax, ebx
0x140007308  mov     rbx, [rsp+28h+arg_0]
0x14000730d  add     rsp, 20h
0x140007311  pop     rdi
0x140007312  retn
```
