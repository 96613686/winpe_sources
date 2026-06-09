# CommonUtil::MpNewBuffer<wchar_t>(wchar_t * *,unsigned __int64)

- ea: `0x140024bcc`
- end: `0x140024c0c`
- name: `??$MpNewBuffer@_W@CommonUtil@@YAJPEAPEA_W_K@Z`
- size: `64`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003008`
- `0x140003814`
- `0x140003a24`

## callees

- `0x140006170`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpNewBuffer<wchar_t>(_QWORD *a1, unsigned __int64 a2)
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
0x140024bcc  push    rbx
0x140024bce  sub     rsp, 20h
0x140024bd2  mov     rbx, rcx
0x140024bd5  mov     eax, 2
0x140024bda  mul     rdx
0x140024bdd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140024be4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140024beb  cmovb   rax, rcx
0x140024bef  mov     rcx, rax; unsigned __int64
0x140024bf2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140024bf7  mov     [rbx], rax
0x140024bfa  neg     rax
0x140024bfd  sbb     eax, eax
0x140024bff  not     eax
0x140024c01  and     eax, 8007000Eh
0x140024c06  add     rsp, 20h
0x140024c0a  pop     rbx
0x140024c0b  retn
```
