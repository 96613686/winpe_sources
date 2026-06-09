# Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vector deleting destructor'(uint)

- ea: `0x1800043e0`
- end: `0x180004435`
- name: `??_E?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `85`
- prototype: `Microsoft::WRL::Details *__fastcall(Microsoft::WRL::Details *, char, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001644`
- `0x1800043e0`
- `0x180007384`

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
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800043e0  mov     [rsp+arg_0], rbx
0x1800043e5  push    rdi
0x1800043e6  sub     rsp, 20h
0x1800043ea  mov     ebx, edx
0x1800043ec  lea     rax, ??_7?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vftable'
0x1800043f3  xor     edx, edx; struct Microsoft::WRL::Details::ModuleBase *
0x1800043f5  mov     [rcx], rax
0x1800043f8  mov     r8b, 1; unsigned __int16 *
0x1800043fb  mov     rdi, rcx
0x1800043fe  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180004403  mov     cs:?isInitialized@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@0_NA, 0; bool Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized
0x18000440a  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, 0; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004415  test    bl, 1
0x180004418  jz      short loc_180004427
0x18000441a  mov     edx, 8; unsigned __int64
0x18000441f  mov     rcx, rdi; void *
0x180004422  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004427  mov     rbx, [rsp+28h+arg_0]
0x18000442c  mov     rax, rdi
0x18000442f  add     rsp, 20h
0x180004433  pop     rdi
0x180004434  retn
```
