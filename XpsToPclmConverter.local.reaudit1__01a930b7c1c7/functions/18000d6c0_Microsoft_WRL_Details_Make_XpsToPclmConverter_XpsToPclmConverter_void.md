# Microsoft::WRL::Details::Make<XpsToPclmConverter::XpsToPclmConverter,>(void)

- ea: `0x18000d6c0`
- end: `0x18000d788`
- name: `??$Make@VXpsToPclmConverter@1@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VXpsToPclmConverter@1@@12@XZ`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000dbf8`

## callees

- `0x180001acc`
- `0x180002148`
- `0x18000d6c0`
- `0x18000d9ac`
- `0x18000d9fc`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<XpsToPclmConverter::XpsToPclmConverter,>(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  _QWORD *v5; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v5 = v2;
  if ( v2 )
  {
    memset_0(v2, 0, 0x90u);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPCLmWriter>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPCLmWriter>(v3);
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPDLConverter>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v3 = &XpsToPclmConverter::XpsToPclmConverter::`vftable';
    v3[3] = 0;
    v3[4] = 0;
    v3[5] = 0;
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
    v5 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<XpsToPclmConverter::XpsToPclmConverter>::~MakeAllocator<XpsToPclmConverter::XpsToPclmConverter>(&v5);
  return a1;
}

```

## disassembly

```asm
0x18000d6c0  mov     [rsp+arg_8], rbx
0x18000d6c5  push    rdi
0x18000d6c6  sub     rsp, 20h
0x18000d6ca  mov     rdi, rcx
0x18000d6cd  mov     qword ptr [rcx], 0
0x18000d6d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d6db  mov     ecx, 90h; unsigned __int64
0x18000d6e0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d6e5  mov     rbx, rax
0x18000d6e8  mov     [rsp+28h+arg_0], rax
0x18000d6ed  test    rax, rax
0x18000d6f0  jz      short loc_18000D770
0x18000d6f2  xor     edx, edx; Val
0x18000d6f4  mov     r8d, 90h; Size
0x18000d6fa  mov     rcx, rax; void *
0x18000d6fd  call    memset_0
0x18000d702  nop
0x18000d703  mov     rcx, rbx
0x18000d706  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPCLmWriter@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPCLmWriter>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPCLmWriter>(void)
0x18000d70b  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPDLConverter@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPDLConverter>::`vftable'
0x18000d712  mov     [rbx], rcx
0x18000d715  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d71c  test    rcx, rcx
0x18000d71f  jz      short loc_18000D72E
0x18000d721  mov     rax, [rcx]
0x18000d724  mov     rax, [rax+8]
0x18000d728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d72d  nop
0x18000d72e  lea     rax, ??_7XpsToPclmConverter@0@6B@; const XpsToPclmConverter::XpsToPclmConverter::`vftable'
0x18000d735  mov     [rbx], rax
0x18000d738  mov     qword ptr [rbx+18h], 0
0x18000d740  mov     qword ptr [rbx+20h], 0
0x18000d748  mov     qword ptr [rbx+28h], 0
0x18000d750  mov     rcx, [rdi]
0x18000d753  test    rcx, rcx
0x18000d756  jz      short loc_18000D764
0x18000d758  mov     rax, [rcx]
0x18000d75b  mov     rax, [rax+10h]
0x18000d75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d764  mov     [rdi], rbx
0x18000d767  mov     [rsp+28h+arg_0], 0
0x18000d770  lea     rcx, [rsp+28h+arg_0]
0x18000d775  call    ??1?$MakeAllocator@VXpsToPclmConverter@1@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<XpsToPclmConverter::XpsToPclmConverter>::~MakeAllocator<XpsToPclmConverter::XpsToPclmConverter>(void)
0x18000d77a  mov     rax, rdi
0x18000d77d  mov     rbx, [rsp+28h+arg_8]
0x18000d782  add     rsp, 20h
0x18000d786  pop     rdi
0x18000d787  retn
```
