# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(void)

- ea: `0x1800043a0`
- end: `0x180004409`
- name: `??1?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `105`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, __int64, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004a40`
- `0x180004b74`

## callees

- `0x1800026b4`
- `0x1800043a0`
- `0x180012010`

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
0x1800043a0  push    rbx
0x1800043a2  sub     rsp, 20h
0x1800043a6  lea     rax, ??_7?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::`vftable'
0x1800043ad  mov     rbx, rcx
0x1800043b0  mov     [rcx], rax
0x1800043b3  mov     rcx, [rcx+8]
0x1800043b7  test    rcx, rcx
0x1800043ba  jz      short loc_1800043DA
0x1800043bc  cmp     byte ptr [rcx+8], 0
0x1800043c0  jz      short loc_1800043D2
0x1800043c2  mov     rax, [rcx]
0x1800043c5  mov     edx, 1
0x1800043ca  mov     rax, [rax]
0x1800043cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043d2  mov     qword ptr [rbx+8], 0
0x1800043da  lea     rax, ??_7?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vftable'
0x1800043e1  mov     r8b, 1; unsigned __int16 *
0x1800043e4  xor     edx, edx; struct Microsoft::WRL::Details::ModuleBase *
0x1800043e6  mov     [rbx], rax
0x1800043e9  mov     rcx, rbx; this
0x1800043ec  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x1800043f1  mov     cs:?isInitialized@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@0_NA, 0; bool Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized
0x1800043f8  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, 0; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004403  add     rsp, 20h
0x180004407  pop     rbx
0x180004408  retn
```
