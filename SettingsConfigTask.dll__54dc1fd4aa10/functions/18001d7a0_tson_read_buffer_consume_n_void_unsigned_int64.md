# tson::read_buffer::consume_n(void *,unsigned __int64)

- ea: `0x18001d7a0`
- end: `0x18001d7e2`
- name: `?consume_n@read_buffer@tson@@QEAA_NPEAX_K@Z`
- size: `66`
- prototype: `bool(tson::read_buffer *__hidden this, void *, unsigned __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c418`
- `0x18000c714`
- `0x18000c77c`
- `0x18000c7e0`
- `0x18000c9d0`
- `0x18000ca38`
- `0x180010510`
- `0x1800105cc`
- `0x180010688`
- `0x18001099c`
- `0x180010d0c`
- `0x180010dd0`
- `0x180010eb4`
- `0x180010f58`
- `0x18001dbe0`

## callees

- `0x180003369`
- `0x18001d7a0`

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
0x18001d7a0  mov     [rsp+arg_0], rbx
0x18001d7a5  push    rdi
0x18001d7a6  sub     rsp, 20h
0x18001d7aa  mov     r9, rdx
0x18001d7ad  mov     rdi, r8
0x18001d7b0  mov     rdx, [rcx+8]; Src
0x18001d7b4  mov     rbx, rcx
0x18001d7b7  lea     rax, [rdx+r8]
0x18001d7bb  cmp     rax, [rcx+10h]
0x18001d7bf  ja      short loc_18001D7D1
0x18001d7c1  mov     rcx, r9; void *
0x18001d7c4  call    memcpy_0
0x18001d7c9  add     [rbx+8], rdi
0x18001d7cd  mov     al, 1
0x18001d7cf  jmp     short loc_18001D7D7
0x18001d7d1  mov     byte ptr [rcx+18h], 1
0x18001d7d5  xor     al, al
0x18001d7d7  mov     rbx, [rsp+28h+arg_0]
0x18001d7dc  add     rsp, 20h
0x18001d7e0  pop     rdi
0x18001d7e1  retn
```
