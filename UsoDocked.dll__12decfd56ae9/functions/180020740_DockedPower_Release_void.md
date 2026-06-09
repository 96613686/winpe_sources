# DockedPower::Release(void)

- ea: `0x180020740`
- end: `0x1800207cf`
- name: `?Release@DockedPower@@UEAAKXZ`
- size: `143`
- prototype: `unsigned int __fastcall(DockedPower *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180007944`
- `0x180007dc0`
- `0x180020740`

## import_xrefs

- `UMPDC!PdcTaskClientUnregister` at `0x1800207a1`
- `UMPDC!PdcTaskClientUnregister` at `0x1800207a1`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x180020792`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x180020792`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x180020783`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x180020783`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DockedPower::Release(DockedPower *this)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rcx

  v2 = _InterlockedDecrement64((volatile signed __int64 *)this + 1);
  if ( v2 )
  {
    if ( v2 > 0xFFFFFFFF )
      LODWORD(v2) = -1;
  }
  else if ( this )
  {
    `eh vector destructor iterator'(
      (char *)this + 40,
      0x10u,
      2u,
      std::shared_ptr<SystemInterface::Service::System>::~shared_ptr<SystemInterface::Service::System>);
    if ( *((_QWORD *)this + 4) )
      Pdcv2ActivationClientDeactivate();
    if ( *((_QWORD *)this + 3) )
      Pdcv2ActivationClientUnregister();
    v3 = *((_QWORD *)this + 2);
    if ( v3 )
      PdcTaskClientUnregister(v3);
    operator delete(this);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180020740  mov     [rsp+arg_0], rbx
0x180020745  push    rdi
0x180020746  sub     rsp, 20h
0x18002074a  mov     rbx, rcx
0x18002074d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180020751  lock xadd [rcx+8], rdi
0x180020757  sub     rdi, 1
0x18002075b  jnz     short loc_1800207B6
0x18002075d  test    rcx, rcx
0x180020760  jz      short loc_1800207C2
0x180020762  add     rcx, 28h ; '('; void *
0x180020766  lea     r9, ??1?$shared_ptr@VSystem@Service@SystemInterface@@@std@@QEAA@XZ; void (*)(void *)
0x18002076d  lea     edx, [rdi+10h]; unsigned __int64
0x180020770  lea     r8d, [rdi+2]; unsigned __int64
0x180020774  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180020779  nop
0x18002077a  mov     rcx, [rbx+20h]
0x18002077e  test    rcx, rcx
0x180020781  jz      short loc_180020789
0x180020783  call    cs:__imp_Pdcv2ActivationClientDeactivate
0x180020789  mov     rcx, [rbx+18h]
0x18002078d  test    rcx, rcx
0x180020790  jz      short loc_180020798
0x180020792  call    cs:__imp_Pdcv2ActivationClientUnregister
0x180020798  mov     rcx, [rbx+10h]
0x18002079c  test    rcx, rcx
0x18002079f  jz      short loc_1800207A7
0x1800207a1  call    cs:__imp_PdcTaskClientUnregister
0x1800207a7  mov     edx, 48h ; 'H'
0x1800207ac  mov     rcx, rbx; Block
0x1800207af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800207b4  jmp     short loc_1800207C2
0x1800207b6  mov     eax, 0FFFFFFFFh
0x1800207bb  cmp     rdi, rax
0x1800207be  jbe     short loc_1800207C2
0x1800207c0  mov     edi, eax
0x1800207c2  mov     eax, edi
0x1800207c4  mov     rbx, [rsp+28h+arg_0]
0x1800207c9  add     rsp, 20h
0x1800207cd  pop     rdi
0x1800207ce  retn
```
