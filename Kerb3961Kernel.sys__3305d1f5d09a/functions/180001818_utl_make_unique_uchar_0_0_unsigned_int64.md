# utl::make_unique<uchar [0],0>(unsigned __int64)

- ea: `0x180001818`
- end: `0x180001865`
- name: `??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z`
- size: `77`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180001464`
- `0x1800037e0`
- `0x180003910`
- `0x180003a54`
- `0x180005950`
- `0x180005b1c`
- `0x180005e34`
- `0x180006cc8`
- `0x18000fd70`

## callees

- `0x180001818`
- `0x180011ab8`
- `0x180012600`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<unsigned char [0],0>(_QWORD *a1, const struct std::nothrow_t *a2)
{
  void *v4; // rax
  void *v5; // rbx
  _QWORD *result; // rax

  v4 = operator new[]((unsigned __int64)a2, a2);
  v5 = v4;
  if ( v4 )
    memset(v4, 0, (size_t)a2);
  else
    v5 = 0;
  result = a1;
  *a1 = v5;
  return result;
}

```

## disassembly

```asm
0x180001818  mov     [rsp+arg_0], rbx
0x18000181d  mov     [rsp+arg_8], rsi
0x180001822  push    rdi
0x180001823  sub     rsp, 20h
0x180001827  mov     rdi, rcx
0x18000182a  mov     rsi, rdx
0x18000182d  mov     rcx, rdx; unsigned __int64
0x180001830  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180001835  mov     rbx, rax
0x180001838  test    rax, rax
0x18000183b  jz      short loc_18000184C
0x18000183d  mov     r8, rsi; Size
0x180001840  xor     edx, edx; Val
0x180001842  mov     rcx, rax; void *
0x180001845  call    memset
0x18000184a  jmp     short loc_18000184E
0x18000184c  xor     ebx, ebx
0x18000184e  mov     rsi, [rsp+28h+arg_8]
0x180001853  mov     rax, rdi
0x180001856  mov     [rdi], rbx
0x180001859  mov     rbx, [rsp+28h+arg_0]
0x18000185e  add     rsp, 20h
0x180001862  pop     rdi
0x180001863  retn
```
