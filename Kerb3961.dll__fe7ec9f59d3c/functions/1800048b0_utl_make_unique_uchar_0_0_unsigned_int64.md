# utl::make_unique<uchar [0],0>(unsigned __int64)

- ea: `0x1800048b0`
- end: `0x180004903`
- name: `??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z`
- size: `83`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180004118`
- `0x180006ee0`
- `0x18000700c`
- `0x18000712c`
- `0x180008500`
- `0x18000901c`
- `0x1800092a4`
- `0x18000fc10`
- `0x18001b6e0`

## callees

- `0x18000211c`
- `0x180002928`
- `0x1800048b0`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<unsigned char [0],0>(_QWORD *a1, unsigned __int64 a2)
{
  void *v4; // rax
  void *v5; // rbx
  _QWORD *result; // rax

  v4 = operator new[](a2, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
    memset_0(v4, 0, a2);
  else
    v5 = 0;
  result = a1;
  *a1 = v5;
  return result;
}

```

## disassembly

```asm
0x1800048b0  mov     [rsp+arg_0], rbx
0x1800048b5  mov     [rsp+arg_8], rsi
0x1800048ba  push    rdi
0x1800048bb  sub     rsp, 20h
0x1800048bf  mov     rsi, rdx
0x1800048c2  mov     rdi, rcx
0x1800048c5  mov     rcx, rsi; unsigned __int64
0x1800048c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800048cf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800048d4  mov     rbx, rax
0x1800048d7  test    rax, rax
0x1800048da  jz      short loc_1800048EB
0x1800048dc  mov     r8, rsi; Size
0x1800048df  xor     edx, edx; Val
0x1800048e1  mov     rcx, rax; void *
0x1800048e4  call    memset_0
0x1800048e9  jmp     short loc_1800048ED
0x1800048eb  xor     ebx, ebx
0x1800048ed  mov     rsi, [rsp+28h+arg_8]
0x1800048f2  mov     rax, rdi
0x1800048f5  mov     [rdi], rbx
0x1800048f8  mov     rbx, [rsp+28h+arg_0]
0x1800048fd  add     rsp, 20h
0x180004901  pop     rdi
0x180004902  retn
```
