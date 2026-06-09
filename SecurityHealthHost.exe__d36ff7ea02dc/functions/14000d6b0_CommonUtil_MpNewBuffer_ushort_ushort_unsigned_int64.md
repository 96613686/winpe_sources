# CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)

- ea: `0x14000d6b0`
- end: `0x14000d6f0`
- name: `??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d778`

## callees

- `0x140002310`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpNewBuffer<unsigned short>(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v3; // rax
  void *v4; // rax

  v3 = 2 * a2;
  if ( !is_mul_ok(a2, 2u) )
    v3 = -1;
  v4 = operator new[](v3, (const struct std::nothrow_t *)std::nothrow);
  *a1 = v4;
  return v4 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x14000d6b0  push    rbx
0x14000d6b2  sub     rsp, 20h
0x14000d6b6  mov     rbx, rcx
0x14000d6b9  mov     eax, 2
0x14000d6be  mul     rdx
0x14000d6c1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d6c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d6cf  cmovb   rax, rcx
0x14000d6d3  mov     rcx, rax; unsigned __int64
0x14000d6d6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000d6db  mov     [rbx], rax
0x14000d6de  neg     rax
0x14000d6e1  sbb     eax, eax
0x14000d6e3  not     eax
0x14000d6e5  and     eax, 8007000Eh
0x14000d6ea  add     rsp, 20h
0x14000d6ee  pop     rbx
0x14000d6ef  retn
```
