# utl::make_unique<uint [0],0>(unsigned __int64)

- ea: `0x18000a1a4`
- end: `0x18000a20a`
- name: `??$make_unique@$$BY0A@I$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@IU?$default_delete@$$BY0A@I@utl@@@0@_K@Z`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b3d0`
- `0x18000ba20`

## callees

- `0x18000211c`
- `0x180002928`
- `0x18000a1a4`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<unsigned int [0],0>(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v3; // rsi
  void *v4; // rax
  void *v5; // rbx
  _QWORD *result; // rax

  v3 = 4 * a2;
  if ( !is_mul_ok(a2, 4u) )
    v3 = -1;
  v4 = operator new[](v3, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
    memset_0(v4, 0, v3);
  else
    v5 = 0;
  result = a1;
  *a1 = v5;
  return result;
}

```

## disassembly

```asm
0x18000a1a4  mov     [rsp+arg_0], rbx
0x18000a1a9  mov     [rsp+arg_8], rsi
0x18000a1ae  push    rdi
0x18000a1af  sub     rsp, 20h
0x18000a1b3  mov     rdi, rcx
0x18000a1b6  mov     eax, 4
0x18000a1bb  mul     rdx
0x18000a1be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a1c5  mov     rsi, rax
0x18000a1c8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a1cf  cmovb   rsi, rax
0x18000a1d3  mov     rcx, rsi; unsigned __int64
0x18000a1d6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a1db  mov     rbx, rax
0x18000a1de  test    rax, rax
0x18000a1e1  jz      short loc_18000A1F2
0x18000a1e3  mov     r8, rsi; Size
0x18000a1e6  xor     edx, edx; Val
0x18000a1e8  mov     rcx, rax; void *
0x18000a1eb  call    memset_0
0x18000a1f0  jmp     short loc_18000A1F4
0x18000a1f2  xor     ebx, ebx
0x18000a1f4  mov     rsi, [rsp+28h+arg_8]
0x18000a1f9  mov     rax, rdi
0x18000a1fc  mov     [rdi], rbx
0x18000a1ff  mov     rbx, [rsp+28h+arg_0]
0x18000a204  add     rsp, 20h
0x18000a208  pop     rdi
0x18000a209  retn
```
