# Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvConfigurationManager,IMidiServicePluginMetadataReporter,>(IMidiServicePluginMetadataReporter * *)

- ea: `0x18000a6ec`
- end: `0x18000a7b1`
- name: `??$MakeAndInitialize@VCMidi2MidiSrvConfigurationManager@@UIMidiServicePluginMetadataReporter@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIMidiServicePluginMetadataReporter@@@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000aa80`

## callees

- `0x1800028ec`
- `0x18000a6ec`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvConfigurationManager,IMidiServicePluginMetadataReporter,>(
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
         &GUID_469c7722_f779_40c3_b648_52620f75dcee,
         a1);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 16LL))(v3);
  return v5;
}

```

## disassembly

```asm
0x18000a6ec  mov     [rsp+arg_0], rbx
0x18000a6f1  push    rdi
0x18000a6f2  sub     rsp, 20h
0x18000a6f6  mov     rbx, rcx
0x18000a6f9  mov     qword ptr [rcx], 0
0x18000a700  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a707  mov     ecx, 38h ; '8'; unsigned __int64
0x18000a70c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a711  mov     rdi, rax
0x18000a714  test    rax, rax
0x18000a717  jnz     short loc_18000A723
0x18000a719  mov     eax, 8007000Eh
0x18000a71e  jmp     loc_18000A7A6
0x18000a723  mov     dword ptr [rax+14h], 1
0x18000a72a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiTransportConfigurationManager@@UIMidiServicePluginMetadataReporter@@@WRL@Microsoft@@6BIMidiTransportConfigurationManager@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::`vftable'{for `IMidiTransportConfigurationManager'}
0x18000a731  mov     [rdi], rax
0x18000a734  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiTransportConfigurationManager@@UIMidiServicePluginMetadataReporter@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMidiServicePluginMetadataReporter@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiServicePluginMetadataReporter>'}
0x18000a73b  mov     [rdi+8], rax
0x18000a73f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a746  test    rcx, rcx
0x18000a749  jz      short loc_18000A758
0x18000a74b  mov     rax, [rcx]
0x18000a74e  mov     rax, [rax+8]
0x18000a752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a757  nop
0x18000a758  lea     rax, ??_7CMidi2MidiSrvConfigurationManager@@6BIMidiTransportConfigurationManager@@@; const CMidi2MidiSrvConfigurationManager::`vftable'{for `IMidiTransportConfigurationManager'}
0x18000a75f  mov     [rdi], rax
0x18000a762  lea     rax, ??_7CMidi2MidiSrvConfigurationManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMidiServicePluginMetadataReporter@@@Details@WRL@Microsoft@@@; const CMidi2MidiSrvConfigurationManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiServicePluginMetadataReporter>'}
0x18000a769  mov     [rdi+8], rax
0x18000a76d  mov     qword ptr [rdi+18h], 0
0x18000a775  mov     byte ptr [rdi+30h], 0
0x18000a779  mov     r8, rbx
0x18000a77c  lea     rdx, _GUID_469c7722_f779_40c3_b648_52620f75dcee
0x18000a783  mov     rcx, rdi
0x18000a786  mov     rax, cs:??_7CMidi2MidiSrvConfigurationManager@@6BIMidiTransportConfigurationManager@@@; const CMidi2MidiSrvConfigurationManager::`vftable'{for `IMidiTransportConfigurationManager'}
0x18000a78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a792  mov     ebx, eax
0x18000a794  mov     rcx, [rdi]
0x18000a797  mov     rax, [rcx+10h]
0x18000a79b  mov     rcx, rdi
0x18000a79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a3  nop
0x18000a7a4  mov     eax, ebx
0x18000a7a6  mov     rbx, [rsp+28h+arg_0]
0x18000a7ab  add     rsp, 20h
0x18000a7af  pop     rdi
0x18000a7b0  retn
```
