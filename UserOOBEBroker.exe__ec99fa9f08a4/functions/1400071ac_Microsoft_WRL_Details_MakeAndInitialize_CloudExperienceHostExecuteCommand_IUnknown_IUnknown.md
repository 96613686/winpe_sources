# Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostExecuteCommand,IUnknown,>(IUnknown * *)

- ea: `0x1400071ac`
- end: `0x14000725b`
- name: `??$MakeAndInitialize@VCloudExperienceHostExecuteCommand@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140008be0`

## callees

- `0x1400025d8`
- `0x1400071ac`
- `0x14000aad0`
- `0x14000c350`
- `0x14000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostExecuteCommand,IUnknown,>(_QWORD *a1)
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
  *v3 = &CloudExperienceHostExecuteCommand::`vftable'{for `IExecuteCommand'};
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
0x1400071ac  mov     [rsp+arg_0], rbx
0x1400071b1  push    rdi
0x1400071b2  sub     rsp, 20h
0x1400071b6  mov     rbx, rcx
0x1400071b9  mov     qword ptr [rcx], 0
0x1400071c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400071c7  mov     ecx, 20h ; ' '; unsigned __int64
0x1400071cc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400071d1  mov     rdi, rax
0x1400071d4  test    rax, rax
0x1400071d7  jnz     short loc_1400071E0
0x1400071d9  mov     eax, 8007000Eh
0x1400071de  jmp     short loc_140007250
0x1400071e0  mov     dword ptr [rax+14h], 1
0x1400071e7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIExecuteCommand@@UIObjectWithSelection@@@WRL@Microsoft@@6BIExecuteCommand@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IObjectWithSelection>::`vftable'{for `IExecuteCommand'}
0x1400071ee  mov     [rdi], rax
0x1400071f1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIExecuteCommand@@UIObjectWithSelection@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectWithSelection@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IObjectWithSelection>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'}
0x1400071f8  mov     [rdi+8], rax
0x1400071fc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140007203  test    rcx, rcx
0x140007206  jz      short loc_140007215
0x140007208  mov     rax, [rcx]
0x14000720b  mov     rax, [rax+8]
0x14000720f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007214  nop
0x140007215  lea     rax, ??_7CloudExperienceHostExecuteCommand@@6BIExecuteCommand@@@; const CloudExperienceHostExecuteCommand::`vftable'{for `IExecuteCommand'}
0x14000721c  mov     [rdi], rax
0x14000721f  lea     rax, ??_7CloudExperienceHostExecuteCommand@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectWithSelection@@@Details@WRL@Microsoft@@@; const CloudExperienceHostExecuteCommand::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'}
0x140007226  mov     [rdi+8], rax
0x14000722a  mov     qword ptr [rdi+18h], 0
0x140007232  mov     r8, rbx
0x140007235  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14000723c  mov     rcx, rdi
0x14000723f  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::QueryInterface(_GUID const &,void * *)
0x140007244  mov     ebx, eax
0x140007246  mov     rcx, rdi
0x140007249  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::Release(void)
0x14000724e  mov     eax, ebx
0x140007250  mov     rbx, [rsp+28h+arg_0]
0x140007255  add     rsp, 20h
0x140007259  pop     rdi
0x14000725a  retn
```
