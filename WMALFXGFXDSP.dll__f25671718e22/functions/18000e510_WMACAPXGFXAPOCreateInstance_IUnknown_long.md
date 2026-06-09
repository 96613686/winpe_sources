# WMACAPXGFXAPOCreateInstance(IUnknown *,long *)

- ea: `0x18000e510`
- end: `0x18000e55d`
- name: `?WMACAPXGFXAPOCreateInstance@@YAPEAVCWMDSPComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `77`
- prototype: `struct CWMDSPComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e510`
- `0x18000e620`
- `0x1800150c4`

## pseudocode

```c
struct CWMDSPComBase *__fastcall WMACAPXGFXAPOCreateInstance(struct IUnknown *a1, int *a2)
{
  CCorrAPO_CapX *v4; // rax

  v4 = (CCorrAPO_CapX *)operator new(0x1D8u);
  if ( v4 )
    v4 = CCorrAPO_CapX::CCorrAPO_CapX(v4, a1, a2, 1);
  return (struct CWMDSPComBase *)(((unsigned __int64)v4 + 88) & -(__int64)(v4 != 0));
}

```

## disassembly

```asm
0x18000e510  mov     [rsp+arg_0], rbx
0x18000e515  push    rdi
0x18000e516  sub     rsp, 20h
0x18000e51a  mov     rdi, rcx
0x18000e51d  mov     rbx, rdx
0x18000e520  mov     ecx, 1D8h; Size
0x18000e525  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e52a  test    rax, rax
0x18000e52d  jz      short loc_18000E55B
0x18000e52f  mov     r9d, 1; int
0x18000e535  mov     r8, rbx; int *
0x18000e538  mov     rdx, rdi; struct IUnknown *
0x18000e53b  mov     rcx, rax; this
0x18000e53e  call    ??0CCorrAPO_CapX@@QEAA@PEAUIUnknown@@PEAJH@Z; CCorrAPO_CapX::CCorrAPO_CapX(IUnknown *,long *,int)
0x18000e543  mov     rbx, [rsp+28h+arg_0]
0x18000e548  lea     rcx, [rax+58h]
0x18000e54c  neg     rax
0x18000e54f  sbb     rax, rax
0x18000e552  and     rax, rcx
0x18000e555  add     rsp, 20h
0x18000e559  pop     rdi
0x18000e55a  retn
0x18000e55b  jmp     short loc_18000E543
```
