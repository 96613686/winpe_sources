# ipx::mtf::LatticeFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x1800080b0`
- end: `0x1800080ed`
- name: `?_CreateIUnknownInstance@LatticeFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `61`
- prototype: `__int64 __fastcall(ipx::mtf::LatticeFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001fc4`
- `0x1800080b0`
- `0x18002533c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::LatticeFactory::_CreateIUnknownInstance(
        ipx::mtf::LatticeFactory *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  MtfLatticeImpl *v5; // rax

  if ( a2 )
    return 2147746064LL;
  v5 = (MtfLatticeImpl *)operator new(0x38u);
  if ( v5 )
    v5 = MtfLatticeImpl::MtfLatticeImpl(v5);
  *a3 = (struct IUnknown *)v5;
  return 0;
}

```

## disassembly

```asm
0x1800080b0  push    rbx
0x1800080b2  sub     rsp, 20h
0x1800080b6  mov     rbx, r8
0x1800080b9  test    rdx, rdx
0x1800080bc  jz      short loc_1800080C5
0x1800080be  mov     eax, 80040110h
0x1800080c3  jmp     short loc_1800080E7
0x1800080c5  mov     ecx, 38h ; '8'; Size
0x1800080ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800080cf  mov     [rsp+28h+arg_8], rax
0x1800080d4  test    rax, rax
0x1800080d7  jz      short loc_1800080E2
0x1800080d9  mov     rcx, rax; this
0x1800080dc  call    ??0MtfLatticeImpl@@QEAA@XZ; MtfLatticeImpl::MtfLatticeImpl(void)
0x1800080e1  nop
0x1800080e2  mov     [rbx], rax
0x1800080e5  xor     eax, eax
0x1800080e7  add     rsp, 20h
0x1800080eb  pop     rbx
0x1800080ec  retn
```
