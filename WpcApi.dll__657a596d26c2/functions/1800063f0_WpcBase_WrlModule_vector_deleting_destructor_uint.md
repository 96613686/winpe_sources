# WpcBase::WrlModule::`vector deleting destructor'(uint)

- ea: `0x1800063f0`
- end: `0x180006453`
- name: `??_EWrlModule@WpcBase@@UEAAPEAXI@Z`
- size: `99`
- prototype: `WpcBase::WrlModule *__fastcall(WpcBase::WrlModule *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800036e4`
- `0x1800063f0`
- `0x180009eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000640d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000640d`

## pseudocode

```c
WpcBase::WrlModule *__fastcall WpcBase::WrlModule::`vector deleting destructor'(WpcBase::WrlModule *this, char a2)
{
  const unsigned __int16 *v4; // r8
  struct Microsoft::WRL::Details::ModuleBase *v5; // rdx
  bool v6; // r9

  *(_QWORD *)this = &WpcBase::WrlModule::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  LOBYTE(v4) = 1;
  *(_QWORD *)this = &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::`vftable';
  Microsoft::WRL::Details::TerminateMap(this, v5, v4, v6);
  Microsoft::WRL::Details::ModuleBase::module_ = 0;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800063f0  mov     [rsp+arg_0], rbx
0x1800063f5  push    rdi
0x1800063f6  sub     rsp, 20h
0x1800063fa  lea     rax, ??_7WrlModule@WpcBase@@6B@; const WpcBase::WrlModule::`vftable'
0x180006401  mov     rdi, rcx
0x180006404  mov     [rcx], rax
0x180006407  mov     ebx, edx
0x180006409  add     rcx, 10h; lpCriticalSection
0x18000640d  call    cs:__imp_DeleteCriticalSection
0x180006413  lea     rax, ??_7?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::`vftable'
0x18000641a  mov     r8b, 1; unsigned __int16 *
0x18000641d  mov     rcx, rdi; this
0x180006420  mov     [rdi], rax
0x180006423  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180006428  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, 0; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006433  test    bl, 1
0x180006436  jz      short loc_180006445
0x180006438  mov     edx, 38h ; '8'
0x18000643d  mov     rcx, rdi; Block
0x180006440  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006445  mov     rbx, [rsp+28h+arg_0]
0x18000644a  mov     rax, rdi
0x18000644d  add     rsp, 20h
0x180006451  pop     rdi
0x180006452  retn
```
