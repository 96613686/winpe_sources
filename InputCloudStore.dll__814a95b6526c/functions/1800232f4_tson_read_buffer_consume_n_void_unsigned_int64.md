# tson::read_buffer::consume_n(void *,unsigned __int64)

- ea: `0x1800232f4`
- end: `0x180023336`
- name: `?consume_n@read_buffer@tson@@QEAA_NPEAX_K@Z`
- size: `66`
- prototype: `bool(tson::read_buffer *__hidden this, void *, unsigned __int64)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180009464`
- `0x1800097a0`
- `0x180009808`
- `0x1800098c4`
- `0x180009980`
- `0x180009b08`
- `0x180009b70`
- `0x1800168d0`
- `0x18001698c`
- `0x180016a48`
- `0x180016fa4`
- `0x180017068`
- `0x18001714c`
- `0x1800171f0`

## callees

- `0x180004341`
- `0x1800232f4`

## pseudocode

```c
char __fastcall tson::read_buffer::consume_n(tson::read_buffer *this, void *a2, size_t a3)
{
  const void *v5; // rdx

  v5 = (const void *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)v5 + a3 > *((_QWORD *)this + 2) )
  {
    *((_BYTE *)this + 24) = 1;
    return 0;
  }
  else
  {
    memcpy_0(a2, v5, a3);
    *((_QWORD *)this + 1) += a3;
    return 1;
  }
}

```

## disassembly

```asm
0x1800232f4  mov     [rsp+arg_0], rbx
0x1800232f9  push    rdi
0x1800232fa  sub     rsp, 20h
0x1800232fe  mov     r9, rdx
0x180023301  mov     rdi, r8
0x180023304  mov     rdx, [rcx+8]; Src
0x180023308  mov     rbx, rcx
0x18002330b  lea     rax, [rdx+r8]
0x18002330f  cmp     rax, [rcx+10h]
0x180023313  ja      short loc_180023325
0x180023315  mov     rcx, r9; void *
0x180023318  call    memcpy_0
0x18002331d  add     [rbx+8], rdi
0x180023321  mov     al, 1
0x180023323  jmp     short loc_18002332B
0x180023325  mov     byte ptr [rcx+18h], 1
0x180023329  xor     al, al
0x18002332b  mov     rbx, [rsp+28h+arg_0]
0x180023330  add     rsp, 20h
0x180023334  pop     rdi
0x180023335  retn
```
