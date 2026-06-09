# wil::make_unique_nothrow<uchar [0]>(unsigned __int64)

- ea: `0x18000be7c`
- end: `0x18000becf`
- name: `??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c52c`
- `0x18000dd30`
- `0x18000ddc0`

## callees

- `0x180002878`
- `0x1800029b8`
- `0x18000be7c`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_nothrow<unsigned char [0]>(_QWORD *a1, unsigned __int64 a2)
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
0x18000be7c  mov     [rsp+arg_0], rbx
0x18000be81  mov     [rsp+arg_8], rsi
0x18000be86  push    rdi
0x18000be87  sub     rsp, 20h
0x18000be8b  mov     rsi, rdx
0x18000be8e  mov     rdi, rcx
0x18000be91  mov     rcx, rsi; unsigned __int64
0x18000be94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000be9b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000bea0  mov     rbx, rax
0x18000bea3  test    rax, rax
0x18000bea6  jz      short loc_18000BEB7
0x18000bea8  mov     r8, rsi; Size
0x18000beab  xor     edx, edx; Val
0x18000bead  mov     rcx, rax; void *
0x18000beb0  call    memset_0
0x18000beb5  jmp     short loc_18000BEB9
0x18000beb7  xor     ebx, ebx
0x18000beb9  mov     rsi, [rsp+28h+arg_8]
0x18000bebe  mov     rax, rdi
0x18000bec1  mov     [rdi], rbx
0x18000bec4  mov     rbx, [rsp+28h+arg_0]
0x18000bec9  add     rsp, 20h
0x18000becd  pop     rdi
0x18000bece  retn
```
