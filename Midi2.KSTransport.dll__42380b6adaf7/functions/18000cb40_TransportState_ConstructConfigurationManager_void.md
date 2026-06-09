# TransportState::ConstructConfigurationManager(void)

- ea: `0x18000cb40`
- end: `0x18000cc87`
- name: `?ConstructConfigurationManager@TransportState@@QEAAJXZ`
- size: `327`
- prototype: `int(TransportState *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e6f0`

## callees

- `0x180004460`
- `0x180004bf0`
- `0x18000a814`
- `0x18000cb40`
- `0x180041010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall TransportState::ConstructConfigurationManager(TransportState *this)
{
  __int64 v2; // rcx
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  _DWORD *v6; // rax
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *((_QWORD *)this + 1) = 0;
  v3 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 3) = 1;
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v4 = &CMidi2KSMidiConfigurationManager::`vftable';
    v6 = operator new(0x28u);
    *(_OWORD *)v6 = 0;
    v6[2] = 1;
    v6[3] = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj2<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCache>::`vftable';
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 0;
    *((_QWORD *)v6 + 4) = 0;
    v4[2] = v6 + 4;
    v4[3] = v6;
    v4[4] = 0;
    v4[5] = 0;
    (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
    *((_QWORD *)this + 1) = v4;
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\transportstate.cpp",
      (const char *)0x8007000ELL,
      v7);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000cb40  push    rbx
0x18000cb42  push    rsi
0x18000cb43  push    rdi; int
0x18000cb44  sub     rsp, 20h
0x18000cb48  mov     rsi, rcx
0x18000cb4b  mov     rcx, [rcx+8]
0x18000cb4f  mov     qword ptr [rsi+8], 0
0x18000cb57  test    rcx, rcx
0x18000cb5a  jz      short loc_18000CB69
0x18000cb5c  mov     rax, [rcx]
0x18000cb5f  mov     rax, [rax+10h]
0x18000cb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb68  nop
0x18000cb69  mov     qword ptr [rsi+8], 0
0x18000cb71  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cb78  mov     ecx, 30h ; '0'; unsigned __int64
0x18000cb7d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cb82  mov     rdi, rax
0x18000cb85  mov     [rsp+38h+arg_0], rax
0x18000cb8a  mov     [rsp+38h+arg_8], rax
0x18000cb8f  test    rax, rax
0x18000cb92  jnz     short loc_18000CBB7
0x18000cb94  mov     rcx, [rsp+38h]; this
0x18000cb99  mov     ebx, 8007000Eh
0x18000cb9e  mov     r9d, ebx; char *
0x18000cba1  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\kstransport\\"...
0x18000cba8  lea     edx, [rax+25h]; void *
0x18000cbab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cbb0  mov     eax, ebx
0x18000cbb2  jmp     loc_18000CC7F
0x18000cbb7  mov     [rsp+38h+arg_10], rdi
0x18000cbbc  mov     dword ptr [rax+0Ch], 1
0x18000cbc3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiTransportConfigurationManager@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager>::`vftable'
0x18000cbca  mov     [rdi], rax
0x18000cbcd  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000cbd4  test    rcx, rcx
0x18000cbd7  jz      short loc_18000CBE6
0x18000cbd9  mov     rax, [rcx]
0x18000cbdc  mov     rax, [rax+8]
0x18000cbe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbe5  nop
0x18000cbe6  lea     rax, ??_7CMidi2KSMidiConfigurationManager@@6B@; const CMidi2KSMidiConfigurationManager::`vftable'
0x18000cbed  mov     [rdi], rax
0x18000cbf0  mov     ecx, 28h ; '('; Size
0x18000cbf5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cbfa  mov     [rsp+38h+arg_0], rax
0x18000cbff  xorps   xmm0, xmm0
0x18000cc02  movups  xmmword ptr [rax], xmm0
0x18000cc05  mov     dword ptr [rax+8], 1
0x18000cc0c  mov     dword ptr [rax+0Ch], 1
0x18000cc13  lea     rcx, ??_7?$_Ref_count_obj2@VMidiEndpointCustomPropertiesCache@WindowsMidiServicesPluginConfigurationLib@@@std@@6B@; const std::_Ref_count_obj2<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCache>::`vftable'
0x18000cc1a  mov     [rax], rcx
0x18000cc1d  lea     rcx, [rax+10h]
0x18000cc21  mov     qword ptr [rcx], 0
0x18000cc28  mov     qword ptr [rcx+8], 0
0x18000cc30  mov     qword ptr [rcx+10h], 0
0x18000cc38  mov     [rdi+10h], rcx
0x18000cc3c  mov     [rdi+18h], rax
0x18000cc40  mov     qword ptr [rdi+20h], 0
0x18000cc48  mov     qword ptr [rdi+28h], 0
0x18000cc50  mov     [rsp+38h+arg_0], 0
0x18000cc59  mov     rax, [rdi]
0x18000cc5c  mov     rcx, rdi
0x18000cc5f  mov     rax, [rax+8]
0x18000cc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc68  nop
0x18000cc69  mov     [rsi+8], rdi
0x18000cc6d  mov     rax, [rdi]
0x18000cc70  mov     rcx, rdi
0x18000cc73  mov     rax, [rax+10h]
0x18000cc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc7c  nop
0x18000cc7d  xor     eax, eax
0x18000cc7f  add     rsp, 20h
0x18000cc83  pop     rdi
0x18000cc84  pop     rsi
0x18000cc85  pop     rbx
0x18000cc86  retn
```
