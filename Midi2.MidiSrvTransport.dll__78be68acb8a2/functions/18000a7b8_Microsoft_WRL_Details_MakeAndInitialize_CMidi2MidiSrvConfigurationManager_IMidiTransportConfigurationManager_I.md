# Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvConfigurationManager,IMidiTransportConfigurationManager,>(IMidiTransportConfigurationManager * *)

- ea: `0x18000a7b8`
- end: `0x18000a87d`
- name: `??$MakeAndInitialize@VCMidi2MidiSrvConfigurationManager@@UIMidiTransportConfigurationManager@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIMidiTransportConfigurationManager@@@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000aa80`

## callees

- `0x1800028ec`
- `0x18000a7b8`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvConfigurationManager,IMidiTransportConfigurationManager,>(
        _QWORD *a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rdi
  unsigned int v5; // ebx

  *a1 = 0;
  v2 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v2[5] = 1;
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::`vftable'{for `IMidiTransportConfigurationManager'};
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiServicePluginMetadataReporter>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v3 = &CMidi2MidiSrvConfigurationManager::`vftable'{for `IMidiTransportConfigurationManager'};
  *((_QWORD *)v3 + 1) = &CMidi2MidiSrvConfigurationManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiServicePluginMetadataReporter>'};
  *((_QWORD *)v3 + 3) = 0;
  *((_BYTE *)v3 + 48) = 0;
  v5 = ((__int64 (__fastcall *)(_DWORD *, GUID *, _QWORD *))CMidi2MidiSrvConfigurationManager::`vftable'{for `IMidiTransportConfigurationManager'})(
         v3,
         &GUID_f19dd642_1809_4497_9eee_f230b11bd6fb,
         a1);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 16LL))(v3);
  return v5;
}

```

## disassembly

```asm
0x18000a7b8  mov     [rsp+arg_0], rbx
0x18000a7bd  push    rdi
0x18000a7be  sub     rsp, 20h
0x18000a7c2  mov     rbx, rcx
0x18000a7c5  mov     qword ptr [rcx], 0
0x18000a7cc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a7d3  mov     ecx, 38h ; '8'; unsigned __int64
0x18000a7d8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a7dd  mov     rdi, rax
0x18000a7e0  test    rax, rax
0x18000a7e3  jnz     short loc_18000A7EF
0x18000a7e5  mov     eax, 8007000Eh
0x18000a7ea  jmp     loc_18000A872
0x18000a7ef  mov     dword ptr [rax+14h], 1
0x18000a7f6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiTransportConfigurationManager@@UIMidiServicePluginMetadataReporter@@@WRL@Microsoft@@6BIMidiTransportConfigurationManager@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::`vftable'{for `IMidiTransportConfigurationManager'}
0x18000a7fd  mov     [rdi], rax
0x18000a800  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiTransportConfigurationManager@@UIMidiServicePluginMetadataReporter@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMidiServicePluginMetadataReporter@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiServicePluginMetadataReporter>'}
0x18000a807  mov     [rdi+8], rax
0x18000a80b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a812  test    rcx, rcx
0x18000a815  jz      short loc_18000A824
0x18000a817  mov     rax, [rcx]
0x18000a81a  mov     rax, [rax+8]
0x18000a81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a823  nop
0x18000a824  lea     rax, ??_7CMidi2MidiSrvConfigurationManager@@6BIMidiTransportConfigurationManager@@@; const CMidi2MidiSrvConfigurationManager::`vftable'{for `IMidiTransportConfigurationManager'}
0x18000a82b  mov     [rdi], rax
0x18000a82e  lea     rax, ??_7CMidi2MidiSrvConfigurationManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMidiServicePluginMetadataReporter@@@Details@WRL@Microsoft@@@; const CMidi2MidiSrvConfigurationManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiServicePluginMetadataReporter>'}
0x18000a835  mov     [rdi+8], rax
0x18000a839  mov     qword ptr [rdi+18h], 0
0x18000a841  mov     byte ptr [rdi+30h], 0
0x18000a845  mov     r8, rbx
0x18000a848  lea     rdx, _GUID_f19dd642_1809_4497_9eee_f230b11bd6fb
0x18000a84f  mov     rcx, rdi
0x18000a852  mov     rax, cs:??_7CMidi2MidiSrvConfigurationManager@@6BIMidiTransportConfigurationManager@@@; const CMidi2MidiSrvConfigurationManager::`vftable'{for `IMidiTransportConfigurationManager'}
0x18000a859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a85e  mov     ebx, eax
0x18000a860  mov     rcx, [rdi]
0x18000a863  mov     rax, [rcx+10h]
0x18000a867  mov     rcx, rdi
0x18000a86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a86f  nop
0x18000a870  mov     eax, ebx
0x18000a872  mov     rbx, [rsp+28h+arg_0]
0x18000a877  add     rsp, 20h
0x18000a87b  pop     rdi
0x18000a87c  retn
```
