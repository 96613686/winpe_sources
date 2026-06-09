# TransportState::ConstructConfigurationManager(void)

- ea: `0x18001abd4`
- end: `0x18001acaf`
- name: `?ConstructConfigurationManager@TransportState@@QEAAJXZ`
- size: `219`
- prototype: `int(TransportState *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c140`

## callees

- `0x180003d6c`
- `0x180009784`
- `0x18001abd4`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TransportState::ConstructConfigurationManager(TransportState *this)
{
  __int64 v2; // rcx
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *((_QWORD *)this + 3) = 0;
  v3 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 3) = 1;
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v4 = &CMidi2VirtualMidiConfigurationManager::`vftable';
    v4[2] = 0;
    ((void (__fastcall *)(_QWORD *))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager>::AddRef)(v4);
    *((_QWORD *)this + 3) = v4;
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\transportstate.cpp",
      (const char *)0x8007000ELL,
      v6);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001abd4  mov     [rsp+arg_0], rbx
0x18001abd9  push    rdi; int
0x18001abda  sub     rsp, 20h
0x18001abde  mov     rdi, rcx
0x18001abe1  mov     rcx, [rcx+18h]
0x18001abe5  mov     qword ptr [rdi+18h], 0
0x18001abed  test    rcx, rcx
0x18001abf0  jz      short loc_18001ABFF
0x18001abf2  mov     rax, [rcx]
0x18001abf5  mov     rax, [rax+10h]
0x18001abf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abfe  nop
0x18001abff  mov     qword ptr [rdi+18h], 0
0x18001ac07  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ac0e  mov     ecx, 28h ; '('; unsigned __int64
0x18001ac13  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ac18  mov     rbx, rax
0x18001ac1b  test    rax, rax
0x18001ac1e  jz      short loc_18001AC84
0x18001ac20  mov     dword ptr [rax+0Ch], 1
0x18001ac27  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiTransportConfigurationManager@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager>::`vftable'
0x18001ac2e  mov     [rbx], rax
0x18001ac31  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001ac38  test    rcx, rcx
0x18001ac3b  jz      short loc_18001AC4A
0x18001ac3d  mov     rdx, [rcx]
0x18001ac40  mov     rax, [rdx+8]
0x18001ac44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac49  nop
0x18001ac4a  lea     rax, ??_7CMidi2VirtualMidiConfigurationManager@@6B@; const CMidi2VirtualMidiConfigurationManager::`vftable'
0x18001ac51  mov     [rbx], rax
0x18001ac54  mov     qword ptr [rbx+10h], 0
0x18001ac5c  mov     rcx, rbx
0x18001ac5f  mov     rax, cs:off_180022670
0x18001ac66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac6b  nop
0x18001ac6c  mov     [rdi+18h], rbx
0x18001ac70  mov     rax, [rbx]
0x18001ac73  mov     rcx, rbx
0x18001ac76  mov     rax, [rax+10h]
0x18001ac7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac7f  nop
0x18001ac80  xor     eax, eax
0x18001ac82  jmp     short loc_18001ACA4
0x18001ac84  mov     rcx, [rsp+28h]; this
0x18001ac89  mov     ebx, 8007000Eh
0x18001ac8e  mov     r9d, ebx; char *
0x18001ac91  lea     r8, aAvcoreMidi2Tra_1; "avcore\\midi2\\transport\\virtualmiditr"...
0x18001ac98  mov     edx, 26h ; '&'; void *
0x18001ac9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aca2  mov     eax, ebx
0x18001aca4  mov     rbx, [rsp+28h+arg_0]
0x18001aca9  add     rsp, 20h
0x18001acad  pop     rdi
0x18001acae  retn
```
