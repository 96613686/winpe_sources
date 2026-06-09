# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(unsigned __int64)

- ea: `0x140007350`
- end: `0x1400073f4`
- name: `?_GrowTo@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z`
- size: `164`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140006c10`
- `0x14000ddf0`
- `0x14000de94`
- `0x14000e1e8`

## callees

- `0x1400023f4`
- `0x140002440`
- `0x140007350`
- `0x14001130c`

## pseudocode

```c
char __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(
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
    operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)a1 = v6;
  *(_QWORD *)(a1 + 8) = &v6[2 * v8];
  *(_QWORD *)(a1 + 16) = &v6[v4 - 2];
  return v7;
}

```

## disassembly

```asm
0x140007350  push    rbx
0x140007352  push    rbp
0x140007353  push    rsi
0x140007354  push    rdi
0x140007355  push    r14
0x140007357  push    r15
0x140007359  sub     rsp, 28h
0x14000735d  add     rdx, 8
0x140007361  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000736b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14000736f  mov     rdi, rcx
0x140007372  cmp     rdx, rax
0x140007375  ja      short loc_1400073E1
0x140007377  lea     r14, [rdx+rdx]
0x14000737b  mov     rcx, r14; unsigned __int64
0x14000737e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140007385  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000738a  mov     rbx, rax
0x14000738d  test    rax, rax
0x140007390  jz      short loc_1400073E1
0x140007392  mov     rbp, [rdi+8]
0x140007396  mov     rcx, rax; void *
0x140007399  sub     rbp, [rdi]
0x14000739c  mov     sil, 1
0x14000739f  mov     rdx, [rdi]; Src
0x1400073a2  sar     rbp, 1
0x1400073a5  lea     r8, ds:2[rbp*2]; Size
0x1400073ad  call    memcpy_0
0x1400073b2  lea     r15, [rdi+10h]
0x1400073b6  cmp     [rdi], r15
0x1400073b9  jz      short loc_1400073CA
0x1400073bb  mov     rcx, [rdi]; void *
0x1400073be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400073c5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400073ca  lea     rax, [rbx+rbp*2]
0x1400073ce  mov     [rdi], rbx
0x1400073d1  mov     [rdi+8], rax
0x1400073d5  lea     rax, [r14-2]
0x1400073d9  add     rax, rbx
0x1400073dc  mov     [r15], rax
0x1400073df  jmp     short loc_1400073E4
0x1400073e1  xor     sil, sil
0x1400073e4  mov     al, sil
0x1400073e7  add     rsp, 28h
0x1400073eb  pop     r15
0x1400073ed  pop     r14
0x1400073ef  pop     rdi
0x1400073f0  pop     rsi
0x1400073f1  pop     rbp
0x1400073f2  pop     rbx
0x1400073f3  retn
```
