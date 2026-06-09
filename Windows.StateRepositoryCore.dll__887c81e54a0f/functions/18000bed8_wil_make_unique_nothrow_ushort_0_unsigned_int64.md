# wil::make_unique_nothrow<ushort [0]>(unsigned __int64)

- ea: `0x18000bed8`
- end: `0x18000bf3e`
- name: `??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z`
- size: `102`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c698`
- `0x18000dc7c`
- `0x18000dd80`

## callees

- `0x180002878`
- `0x1800029b8`
- `0x18000bed8`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_nothrow<unsigned short [0]>(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v3; // rsi
  void *v4; // rax
  void *v5; // rbx
  _QWORD *result; // rax

  v3 = 2 * a2;
  if ( !is_mul_ok(a2, 2u) )
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
0x18000bed8  mov     [rsp+arg_0], rbx
0x18000bedd  mov     [rsp+arg_8], rsi
0x18000bee2  push    rdi
0x18000bee3  sub     rsp, 20h
0x18000bee7  mov     rdi, rcx
0x18000beea  mov     eax, 2
0x18000beef  mul     rdx
0x18000bef2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bef9  mov     rsi, rax
0x18000befc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000bf03  cmovb   rsi, rax
0x18000bf07  mov     rcx, rsi; unsigned __int64
0x18000bf0a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000bf0f  mov     rbx, rax
0x18000bf12  test    rax, rax
0x18000bf15  jz      short loc_18000BF26
0x18000bf17  mov     r8, rsi; Size
0x18000bf1a  xor     edx, edx; Val
0x18000bf1c  mov     rcx, rax; void *
0x18000bf1f  call    memset_0
0x18000bf24  jmp     short loc_18000BF28
0x18000bf26  xor     ebx, ebx
0x18000bf28  mov     rsi, [rsp+28h+arg_8]
0x18000bf2d  mov     rax, rdi
0x18000bf30  mov     [rdi], rbx
0x18000bf33  mov     rbx, [rsp+28h+arg_0]
0x18000bf38  add     rsp, 20h
0x18000bf3c  pop     rdi
0x18000bf3d  retn
```
