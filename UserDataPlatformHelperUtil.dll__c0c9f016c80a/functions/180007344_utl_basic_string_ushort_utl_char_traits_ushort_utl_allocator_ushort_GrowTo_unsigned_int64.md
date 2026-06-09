# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowTo(unsigned __int64)

- ea: `0x180007344`
- end: `0x1800073e8`
- name: `?_GrowTo@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z`
- size: `164`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800061e0`
- `0x1800073f0`

## callees

- `0x180001178`
- `0x1800016e8`
- `0x180007344`
- `0x18000a142`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowTo(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v2; // rdx
  __int64 v4; // r14
  char *v5; // rax
  char *v6; // rbx
  char v7; // si
  __int64 v8; // rbp

  v2 = (a2 + 8) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( v2 > 0x7FFFFFFFFFFFFFFFLL )
    return 0;
  v4 = 2 * v2;
  v5 = (char *)operator new(2 * v2, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
    return 0;
  v7 = 1;
  v8 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1;
  memcpy_0(v5, *(const void **)a1, 2 * v8 + 2);
  if ( *(_QWORD *)a1 != a1 + 16 )
    operator delete(*(void **)a1);
  *(_QWORD *)a1 = v6;
  *(_QWORD *)(a1 + 8) = &v6[2 * v8];
  *(_QWORD *)(a1 + 16) = &v6[v4 - 2];
  return v7;
}

```

## disassembly

```asm
0x180007344  push    rbx
0x180007346  push    rbp
0x180007347  push    rsi
0x180007348  push    rdi
0x180007349  push    r14
0x18000734b  push    r15
0x18000734d  sub     rsp, 28h
0x180007351  add     rdx, 8
0x180007355  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000735f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180007363  mov     rdi, rcx
0x180007366  cmp     rdx, rax
0x180007369  ja      short loc_1800073D5
0x18000736b  lea     r14, [rdx+rdx]
0x18000736f  mov     rcx, r14; unsigned __int64
0x180007372  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007379  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000737e  mov     rbx, rax
0x180007381  test    rax, rax
0x180007384  jz      short loc_1800073D5
0x180007386  mov     rbp, [rdi+8]
0x18000738a  mov     rcx, rax; void *
0x18000738d  sub     rbp, [rdi]
0x180007390  mov     sil, 1
0x180007393  mov     rdx, [rdi]; Src
0x180007396  sar     rbp, 1
0x180007399  lea     r8, ds:2[rbp*2]; Size
0x1800073a1  call    memcpy_0
0x1800073a6  lea     r15, [rdi+10h]
0x1800073aa  cmp     [rdi], r15
0x1800073ad  jz      short loc_1800073BE
0x1800073af  mov     rcx, [rdi]; Block
0x1800073b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800073b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800073be  lea     rax, [rbx+rbp*2]
0x1800073c2  mov     [rdi], rbx
0x1800073c5  mov     [rdi+8], rax
0x1800073c9  lea     rax, [r14-2]
0x1800073cd  add     rax, rbx
0x1800073d0  mov     [r15], rax
0x1800073d3  jmp     short loc_1800073D8
0x1800073d5  xor     sil, sil
0x1800073d8  mov     al, sil
0x1800073db  add     rsp, 28h
0x1800073df  pop     r15
0x1800073e1  pop     r14
0x1800073e3  pop     rdi
0x1800073e4  pop     rsi
0x1800073e5  pop     rbp
0x1800073e6  pop     rbx
0x1800073e7  retn
```
