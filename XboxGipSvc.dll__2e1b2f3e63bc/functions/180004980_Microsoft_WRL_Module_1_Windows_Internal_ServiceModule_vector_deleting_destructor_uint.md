# Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vector deleting destructor'(uint)

- ea: `0x180004980`
- end: `0x1800049d5`
- name: `??_E?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `85`
- prototype: `Microsoft::WRL::Details *__fastcall(Microsoft::WRL::Details *, char, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001b6c`
- `0x1800026b4`
- `0x180004980`

## pseudocode

```c
Microsoft::WRL::Details *__fastcall Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vector deleting destructor'(
        Microsoft::WRL::Details *a1,
        char a2,
        const unsigned __int16 *a3,
        bool a4)
{
  *(_QWORD *)a1 = &Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vftable';
  LOBYTE(a3) = 1;
  Microsoft::WRL::Details::TerminateMap(a1, 0, a3, a4);
  Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized = 0;
  Microsoft::WRL::Details::ModuleBase::module_ = 0;
  if ( (a2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)8);
  return a1;
}

```

## disassembly

```asm
0x180004980  mov     [rsp+arg_0], rbx
0x180004985  push    rdi
0x180004986  sub     rsp, 20h
0x18000498a  mov     ebx, edx
0x18000498c  lea     rax, ??_7?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vftable'
0x180004993  xor     edx, edx; struct Microsoft::WRL::Details::ModuleBase *
0x180004995  mov     [rcx], rax
0x180004998  mov     r8b, 1; unsigned __int16 *
0x18000499b  mov     rdi, rcx
0x18000499e  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x1800049a3  mov     cs:?isInitialized@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@0_NA, 0; bool Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized
0x1800049aa  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, 0; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800049b5  test    bl, 1
0x1800049b8  jz      short loc_1800049C7
0x1800049ba  mov     edx, 8; struct std::nothrow_t *
0x1800049bf  mov     rcx, rdi; void *
0x1800049c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800049c7  mov     rbx, [rsp+28h+arg_0]
0x1800049cc  mov     rax, rdi
0x1800049cf  add     rsp, 20h
0x1800049d3  pop     rdi
0x1800049d4  retn
```
