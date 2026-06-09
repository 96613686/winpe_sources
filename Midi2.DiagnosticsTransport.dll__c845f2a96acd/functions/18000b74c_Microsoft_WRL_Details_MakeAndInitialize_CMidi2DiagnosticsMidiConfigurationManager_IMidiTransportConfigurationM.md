# Microsoft::WRL::Details::MakeAndInitialize<CMidi2DiagnosticsMidiConfigurationManager,IMidiTransportConfigurationManager,>(IMidiTransportConfigurationManager * *)

- ea: `0x18000b74c`
- end: `0x18000b7f4`
- name: `??$MakeAndInitialize@VCMidi2DiagnosticsMidiConfigurationManager@@UIMidiTransportConfigurationManager@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIMidiTransportConfigurationManager@@@Z`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b9f0`

## callees

- `0x18000384c`
- `0x18000b74c`
- `0x180013010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CMidi2DiagnosticsMidiConfigurationManager,IMidiTransportConfigurationManager,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  unsigned int v5; // ebx

  *a1 = 0;
  v2 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  *((_DWORD *)v2 + 3) = 1;
  *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v3 = &CMidi2DiagnosticsMidiConfigurationManager::`vftable';
  v3[2] = 0;
  v5 = ((__int64 (__fastcall *)(_QWORD *, GUID *, _QWORD *))CMidi2DiagnosticsMidiConfigurationManager::`vftable')(
         v3,
         &GUID_f19dd642_1809_4497_9eee_f230b11bd6fb,
         a1);
  (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
  return v5;
}

```

## disassembly

```asm
0x18000b74c  mov     [rsp+arg_0], rbx
0x18000b751  push    rdi
0x18000b752  sub     rsp, 20h
0x18000b756  mov     rbx, rcx
0x18000b759  mov     qword ptr [rcx], 0
0x18000b760  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b767  mov     ecx, 18h; unsigned __int64
0x18000b76c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b771  mov     rdi, rax
0x18000b774  test    rax, rax
0x18000b777  jnz     short loc_18000B780
0x18000b779  mov     eax, 8007000Eh
0x18000b77e  jmp     short loc_18000B7E9
0x18000b780  mov     dword ptr [rax+0Ch], 1
0x18000b787  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiTransportConfigurationManager@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager>::`vftable'
0x18000b78e  mov     [rdi], rax
0x18000b791  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b798  test    rcx, rcx
0x18000b79b  jz      short loc_18000B7AA
0x18000b79d  mov     rax, [rcx]
0x18000b7a0  mov     rax, [rax+8]
0x18000b7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7a9  nop
0x18000b7aa  lea     rax, ??_7CMidi2DiagnosticsMidiConfigurationManager@@6B@; const CMidi2DiagnosticsMidiConfigurationManager::`vftable'
0x18000b7b1  mov     [rdi], rax
0x18000b7b4  mov     qword ptr [rdi+10h], 0
0x18000b7bc  mov     r8, rbx
0x18000b7bf  lea     rdx, _GUID_f19dd642_1809_4497_9eee_f230b11bd6fb
0x18000b7c6  mov     rcx, rdi
0x18000b7c9  mov     rax, cs:??_7CMidi2DiagnosticsMidiConfigurationManager@@6B@; const CMidi2DiagnosticsMidiConfigurationManager::`vftable'
0x18000b7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7d5  mov     ebx, eax
0x18000b7d7  mov     rcx, [rdi]
0x18000b7da  mov     rax, [rcx+10h]
0x18000b7de  mov     rcx, rdi
0x18000b7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7e6  nop
0x18000b7e7  mov     eax, ebx
0x18000b7e9  mov     rbx, [rsp+28h+arg_0]
0x18000b7ee  add     rsp, 20h
0x18000b7f2  pop     rdi
0x18000b7f3  retn
```
