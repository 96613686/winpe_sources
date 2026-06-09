# WMALFXAPOCreateInstance(IUnknown *,long *)

- ea: `0x18000e6d0`
- end: `0x18000e71a`
- name: `?WMALFXAPOCreateInstance@@YAPEAVCWMDSPComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `74`
- prototype: `struct CWMDSPComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e6d0`
- `0x18000e720`
- `0x1800150c4`

## pseudocode

```c
struct CWMDSPComBase *__fastcall WMALFXAPOCreateInstance(struct IUnknown *a1, int *a2)
{
  CCorrAPO *v4; // rax

  v4 = (CCorrAPO *)operator new(0x1D8u);
  if ( v4 )
    v4 = CCorrAPO::CCorrAPO(v4, a1, a2, 0);
  return (struct CWMDSPComBase *)(((unsigned __int64)v4 + 88) & -(__int64)(v4 != 0));
}

```

## disassembly

```asm
0x18000e6d0  mov     [rsp+arg_0], rbx
0x18000e6d5  push    rdi
0x18000e6d6  sub     rsp, 20h
0x18000e6da  mov     rdi, rcx
0x18000e6dd  mov     rbx, rdx
0x18000e6e0  mov     ecx, 1D8h; Size
0x18000e6e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e6ea  test    rax, rax
0x18000e6ed  jz      short loc_18000E718
0x18000e6ef  xor     r9d, r9d; int
0x18000e6f2  mov     r8, rbx; int *
0x18000e6f5  mov     rdx, rdi; struct IUnknown *
0x18000e6f8  mov     rcx, rax; this
0x18000e6fb  call    ??0CCorrAPO@@QEAA@PEAUIUnknown@@PEAJH@Z; CCorrAPO::CCorrAPO(IUnknown *,long *,int)
0x18000e700  mov     rbx, [rsp+28h+arg_0]
0x18000e705  lea     rcx, [rax+58h]
0x18000e709  neg     rax
0x18000e70c  sbb     rax, rax
0x18000e70f  and     rax, rcx
0x18000e712  add     rsp, 20h
0x18000e716  pop     rdi
0x18000e717  retn
0x18000e718  jmp     short loc_18000E700
```
