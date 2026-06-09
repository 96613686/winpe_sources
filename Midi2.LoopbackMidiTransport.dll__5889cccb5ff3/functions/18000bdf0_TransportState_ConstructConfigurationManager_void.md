# TransportState::ConstructConfigurationManager(void)

- ea: `0x18000bdf0`
- end: `0x18000becb`
- name: `?ConstructConfigurationManager@TransportState@@QEAAJXZ`
- size: `219`
- prototype: `int(TransportState *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d720`

## callees

- `0x18000499c`
- `0x18000a024`
- `0x18000bdf0`
- `0x180032010`

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

  v2 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *((_QWORD *)this + 1) = 0;
  v3 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 3) = 1;
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v4 = &CMidi2LoopbackMidiConfigurationManager::`vftable';
    v4[2] = 0;
    ((void (__fastcall *)(_QWORD *))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager>::AddRef)(v4);
    *((_QWORD *)this + 1) = v4;
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\transportstate.cpp",
      (const char *)0x8007000ELL,
      v6);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000bdf0  mov     [rsp+arg_0], rbx
0x18000bdf5  push    rdi; int
0x18000bdf6  sub     rsp, 20h
0x18000bdfa  mov     rdi, rcx
0x18000bdfd  mov     rcx, [rcx+8]
0x18000be01  mov     qword ptr [rdi+8], 0
0x18000be09  test    rcx, rcx
0x18000be0c  jz      short loc_18000BE1B
0x18000be0e  mov     rax, [rcx]
0x18000be11  mov     rax, [rax+10h]
0x18000be15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be1a  nop
0x18000be1b  mov     qword ptr [rdi+8], 0
0x18000be23  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000be2a  mov     ecx, 28h ; '('; unsigned __int64
0x18000be2f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000be34  mov     rbx, rax
0x18000be37  test    rax, rax
0x18000be3a  jz      short loc_18000BEA0
0x18000be3c  mov     dword ptr [rax+0Ch], 1
0x18000be43  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiTransportConfigurationManager@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager>::`vftable'
0x18000be4a  mov     [rbx], rax
0x18000be4d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000be54  test    rcx, rcx
0x18000be57  jz      short loc_18000BE66
0x18000be59  mov     rdx, [rcx]
0x18000be5c  mov     rax, [rdx+8]
0x18000be60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be65  nop
0x18000be66  lea     rax, ??_7CMidi2LoopbackMidiConfigurationManager@@6B@; const CMidi2LoopbackMidiConfigurationManager::`vftable'
0x18000be6d  mov     [rbx], rax
0x18000be70  mov     qword ptr [rbx+10h], 0
0x18000be78  mov     rcx, rbx
0x18000be7b  mov     rax, cs:off_180033200
0x18000be82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be87  nop
0x18000be88  mov     [rdi+8], rbx
0x18000be8c  mov     rax, [rbx]
0x18000be8f  mov     rcx, rbx
0x18000be92  mov     rax, [rax+10h]
0x18000be96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be9b  nop
0x18000be9c  xor     eax, eax
0x18000be9e  jmp     short loc_18000BEC0
0x18000bea0  mov     rcx, [rsp+28h]; this
0x18000bea5  mov     ebx, 8007000Eh
0x18000beaa  mov     r9d, ebx; char *
0x18000bead  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\loopbackmidit"...
0x18000beb4  mov     edx, 26h ; '&'; void *
0x18000beb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bebe  mov     eax, ebx
0x18000bec0  mov     rbx, [rsp+28h+arg_0]
0x18000bec5  add     rsp, 20h
0x18000bec9  pop     rdi
0x18000beca  retn
```
