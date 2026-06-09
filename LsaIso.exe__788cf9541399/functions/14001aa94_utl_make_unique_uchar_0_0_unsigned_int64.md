# utl::make_unique<uchar [0],0>(unsigned __int64)

- ea: `0x14001aa94`
- end: `0x14001aae7`
- name: `??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001ac5c`
- `0x14001bfa8`

## callees

- `0x140003a7c`
- `0x14001aa94`
- `0x140038cd2`

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
0x14001aa94  mov     [rsp+arg_0], rbx
0x14001aa99  mov     [rsp+arg_8], rsi
0x14001aa9e  push    rdi
0x14001aa9f  sub     rsp, 20h
0x14001aaa3  mov     rsi, rdx
0x14001aaa6  mov     rdi, rcx
0x14001aaa9  mov     rcx, rsi; unsigned __int64
0x14001aaac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001aab3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001aab8  mov     rbx, rax
0x14001aabb  test    rax, rax
0x14001aabe  jz      short loc_14001AACF
0x14001aac0  mov     r8, rsi; Size
0x14001aac3  xor     edx, edx; Val
0x14001aac5  mov     rcx, rax; void *
0x14001aac8  call    memset_0
0x14001aacd  jmp     short loc_14001AAD1
0x14001aacf  xor     ebx, ebx
0x14001aad1  mov     rsi, [rsp+28h+arg_8]
0x14001aad6  mov     rax, rdi
0x14001aad9  mov     [rdi], rbx
0x14001aadc  mov     rbx, [rsp+28h+arg_0]
0x14001aae1  add     rsp, 20h
0x14001aae5  pop     rdi
0x14001aae6  retn
```
