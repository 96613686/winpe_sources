# CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)

- ea: `0x140005578`
- end: `0x1400055b8`
- name: `??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005e1c`
- `0x14000e800`
- `0x14000ea5c`
- `0x1400100bc`

## callees

- `0x140002450`

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
0x140005578  push    rbx
0x14000557a  sub     rsp, 20h
0x14000557e  mov     rbx, rcx
0x140005581  mov     eax, 2
0x140005586  mul     rdx
0x140005589  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140005590  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005597  cmovb   rax, rcx
0x14000559b  mov     rcx, rax; unsigned __int64
0x14000559e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400055a3  mov     [rbx], rax
0x1400055a6  neg     rax
0x1400055a9  sbb     eax, eax
0x1400055ab  not     eax
0x1400055ad  and     eax, 8007000Eh
0x1400055b2  add     rsp, 20h
0x1400055b6  pop     rbx
0x1400055b7  retn
```
