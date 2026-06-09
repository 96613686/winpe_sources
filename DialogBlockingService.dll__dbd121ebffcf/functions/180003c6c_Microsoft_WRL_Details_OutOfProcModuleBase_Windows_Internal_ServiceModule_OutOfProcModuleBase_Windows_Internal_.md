# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(void)

- ea: `0x180003c6c`
- end: `0x180003cd5`
- name: `??1?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `105`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, __int64, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800044a0`
- `0x18000459c`

## callees

- `0x180003c6c`
- `0x180007384`
- `0x18000e010`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(
        Microsoft::WRL::Details *this,
        __int64 a2,
        const unsigned __int16 *a3,
        bool a4)
{
  __int64 v5; // rcx
  bool result; // al

  *(_QWORD *)this = &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::`vftable';
  v5 = *((_QWORD *)this + 1);
  if ( v5 )
  {
    if ( *(_BYTE *)(v5 + 8) )
      (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
    *((_QWORD *)this + 1) = 0;
  }
  LOBYTE(a3) = 1;
  *(_QWORD *)this = &Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vftable';
  result = Microsoft::WRL::Details::TerminateMap(this, 0, a3, a4);
  Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized = 0;
  Microsoft::WRL::Details::ModuleBase::module_ = 0;
  return result;
}

```

## disassembly

```asm
0x180003c6c  push    rbx
0x180003c6e  sub     rsp, 20h
0x180003c72  lea     rax, ??_7?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::`vftable'
0x180003c79  mov     rbx, rcx
0x180003c7c  mov     [rcx], rax
0x180003c7f  mov     rcx, [rcx+8]
0x180003c83  test    rcx, rcx
0x180003c86  jz      short loc_180003CA6
0x180003c88  cmp     byte ptr [rcx+8], 0
0x180003c8c  jz      short loc_180003C9E
0x180003c8e  mov     rax, [rcx]
0x180003c91  mov     edx, 1
0x180003c96  mov     rax, [rax]
0x180003c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c9e  mov     qword ptr [rbx+8], 0
0x180003ca6  lea     rax, ??_7?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vftable'
0x180003cad  mov     r8b, 1; unsigned __int16 *
0x180003cb0  xor     edx, edx; struct Microsoft::WRL::Details::ModuleBase *
0x180003cb2  mov     [rbx], rax
0x180003cb5  mov     rcx, rbx; this
0x180003cb8  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180003cbd  mov     cs:?isInitialized@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@0_NA, 0; bool Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized
0x180003cc4  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, 0; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003ccf  add     rsp, 20h
0x180003cd3  pop     rbx
0x180003cd4  retn
```
