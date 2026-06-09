# CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)

- ea: `0x180006ce4`
- end: `0x180006d24`
- name: `??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z`
- size: `64`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006eb0`
- `0x180006f68`
- `0x180007d9c`

## callees

- `0x1800021b0`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpNewBuffer<unsigned short>(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v3; // rax
  void *v4; // rax

  v3 = 2 * a2;
  if ( !is_mul_ok(a2, 2u) )
    v3 = -1;
  v4 = operator new[](v3, (const struct std::nothrow_t *)&std::nothrow);
  *a1 = v4;
  return v4 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180006ce4  push    rbx
0x180006ce6  sub     rsp, 20h
0x180006cea  mov     rbx, rcx
0x180006ced  mov     eax, 2
0x180006cf2  mul     rdx
0x180006cf5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006cfc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006d03  cmovb   rax, rcx
0x180006d07  mov     rcx, rax; unsigned __int64
0x180006d0a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006d0f  mov     [rbx], rax
0x180006d12  neg     rax
0x180006d15  sbb     eax, eax
0x180006d17  not     eax
0x180006d19  and     eax, 8007000Eh
0x180006d1e  add     rsp, 20h
0x180006d22  pop     rbx
0x180006d23  retn
```
