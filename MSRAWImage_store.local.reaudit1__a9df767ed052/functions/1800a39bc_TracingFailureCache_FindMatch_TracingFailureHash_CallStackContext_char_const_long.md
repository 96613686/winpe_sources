# TracingFailureCache::FindMatch(TracingFailureHash &,CallStackContext &,char const *,long)

- ea: `0x1800a39bc`
- end: `0x1800a3b6f`
- name: `?FindMatch@TracingFailureCache@@IEAAPEAVTracingFailureDetails@@AEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z`
- size: `435`
- prototype: `struct TracingFailureDetails *__fastcall(TracingFailureCache *__hidden this, struct TracingFailureHash *, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a3ee0`

## callees

- `0x180002420`
- `0x180003044`
- `0x1800a39bc`

## pseudocode

```c
struct TracingFailureDetails *__fastcall TracingFailureCache::FindMatch(
        TracingFailureCache *this,
        struct TracingFailureHash *a2,
        __m128i *a3,
        const char *a4,
        int a5)
{
  __int64 v5; // rdi
  __int64 v9; // rcx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  unsigned int i; // r8d
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned __int64 v15; // r9
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rax

  v5 = 0;
  if ( a4 )
  {
    v9 = *((_QWORD *)this + 11);
    if ( v9 )
    {
      for ( i = 0; i < *((_DWORD *)this + 10); ++i )
      {
        v13 = 2328LL * i;
        if ( *(_DWORD *)(v13 + v9 + 1996) == a3[124].m128i_i32[3] )
        {
          v14 = *(_QWORD *)a2 - *(_QWORD *)(v13 + v9 + 2309);
          if ( *(_QWORD *)a2 == *(_QWORD *)(v13 + v9 + 2309) )
            v14 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v13 + v9 + 2317);
          if ( !v14 && *(_DWORD *)(v13 + v9 + 2288) == a5 )
          {
            v15 = *(_QWORD *)(v13 + v9 + 2000) - a3[125].m128i_i64[0];
            if ( !v15 )
              v15 = _mm_srli_si128(*(__m128i *)(v13 + v9 + 2000), 8).m128i_u64[0]
                  - _mm_srli_si128(a3[125], 8).m128i_u64[0];
            if ( !v15 && *(_DWORD *)(v13 + v9 + 2016) == a3[126].m128i_i32[0] )
              return (struct TracingFailureDetails *)(v13 + v9);
            v16 = *(_QWORD *)(v13 + v9 + 2000) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
            if ( !v16 )
              v16 = _mm_srli_si128(*(__m128i *)(v13 + v9 + 2000), 8).m128i_u64[0]
                  - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
            if ( !v16 )
              return (struct TracingFailureDetails *)(v13 + v9);
            v17 = a3[125].m128i_i64[0] - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
            if ( !v17 )
              v17 = _mm_srli_si128(a3[125], 8).m128i_u64[0] - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
            if ( !v17 )
              return (struct TracingFailureDetails *)(v13 + v9);
          }
        }
      }
    }
    else
    {
      v10 = operator new(0xFEA8u);
      v11 = v10 + 1;
      *v10 = 28;
      `vector constructor iterator'(
        v10 + 1,
        0x918u,
        0x1Cu,
        (void *(*)(void *))TracingFailureDetails::TracingFailureDetails);
      *((_QWORD *)this + 11) = v11;
      if ( !*((_QWORD *)this + 12) )
        *((_QWORD *)this + 12) = operator new(0x1000u);
      if ( !*((_QWORD *)this + 13) )
        *((_QWORD *)this + 13) = operator new(0x1000u);
    }
  }
  return (struct TracingFailureDetails *)v5;
}

```

## disassembly

```asm
0x1800a39bc  mov     [rsp+arg_8], rbx
0x1800a39c1  mov     [rsp+arg_10], rbp
0x1800a39c6  push    rsi
0x1800a39c7  push    rdi
0x1800a39c8  push    r14
0x1800a39ca  sub     rsp, 20h
0x1800a39ce  xor     edi, edi
0x1800a39d0  mov     r10, r8
0x1800a39d3  mov     r11, rdx
0x1800a39d6  mov     rsi, rcx
0x1800a39d9  test    r9, r9
0x1800a39dc  jz      loc_1800A3B58
0x1800a39e2  mov     rcx, [rcx+58h]
0x1800a39e6  test    rcx, rcx
0x1800a39e9  jnz     short loc_1800A3A49
0x1800a39eb  mov     ecx, 0FEA8h; Size
0x1800a39f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a39f5  lea     r8d, [rdi+1Ch]; unsigned __int64
0x1800a39f9  mov     edx, 918h; unsigned __int64
0x1800a39fe  lea     r9, ??0TracingFailureDetails@@QEAA@XZ; void *(*)(void *)
0x1800a3a05  lea     rbx, [rax+8]
0x1800a3a09  mov     [rax], r8
0x1800a3a0c  mov     rcx, rbx; void *
0x1800a3a0f  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800a3a14  mov     [rsi+58h], rbx
0x1800a3a18  mov     ebx, 1000h
0x1800a3a1d  cmp     [rsi+60h], rdi
0x1800a3a21  jnz     short loc_1800A3A2E
0x1800a3a23  mov     ecx, ebx; Size
0x1800a3a25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a3a2a  mov     [rsi+60h], rax
0x1800a3a2e  cmp     [rsi+68h], rdi
0x1800a3a32  jnz     loc_1800A3B58
0x1800a3a38  mov     rcx, rbx; Size
0x1800a3a3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a3a40  mov     [rsi+68h], rax
0x1800a3a44  jmp     loc_1800A3B58
0x1800a3a49  mov     ebp, [rsi+28h]
0x1800a3a4c  mov     r8d, edi
0x1800a3a4f  mov     rsi, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800a3a56  mov     r14d, [rsp+38h+arg_20]
0x1800a3a5b  mov     rbx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800a3a62  cmp     r8d, ebp
0x1800a3a65  jnb     loc_1800A3B58
0x1800a3a6b  mov     eax, r8d
0x1800a3a6e  imul    rdx, rax, 918h
0x1800a3a75  mov     eax, [r10+7CCh]
0x1800a3a7c  cmp     [rdx+rcx+7CCh], eax
0x1800a3a83  jnz     loc_1800A3B4C
0x1800a3a89  mov     rax, [r11]
0x1800a3a8c  sub     rax, [rdx+rcx+905h]
0x1800a3a94  jnz     short loc_1800A3AA2
0x1800a3a96  mov     rax, [r11+8]
0x1800a3a9a  sub     rax, [rdx+rcx+90Dh]
0x1800a3aa2  test    rax, rax
0x1800a3aa5  jnz     loc_1800A3B4C
0x1800a3aab  cmp     [rdx+rcx+8F0h], r14d
0x1800a3ab3  jnz     loc_1800A3B4C
0x1800a3ab9  movups  xmm0, xmmword ptr [r10+7D0h]
0x1800a3ac1  movups  xmm1, xmmword ptr [rdx+rcx+7D0h]
0x1800a3ac9  movq    rax, xmm0
0x1800a3ace  movq    r9, xmm1
0x1800a3ad3  sub     r9, rax
0x1800a3ad6  jnz     short loc_1800A3AEF
0x1800a3ad8  psrldq  xmm1, 8
0x1800a3add  psrldq  xmm0, 8
0x1800a3ae2  movq    r9, xmm1
0x1800a3ae7  movq    rax, xmm0
0x1800a3aec  sub     r9, rax
0x1800a3aef  test    r9, r9
0x1800a3af2  jnz     short loc_1800A3B04
0x1800a3af4  mov     eax, [r10+7E0h]
0x1800a3afb  cmp     [rdx+rcx+7E0h], eax
0x1800a3b02  jz      short loc_1800A3B54
0x1800a3b04  movups  xmm0, xmmword ptr [rdx+rcx+7D0h]
0x1800a3b0c  movq    rax, xmm0
0x1800a3b11  sub     rax, rsi
0x1800a3b14  jnz     short loc_1800A3B23
0x1800a3b16  psrldq  xmm0, 8
0x1800a3b1b  movq    rax, xmm0
0x1800a3b20  sub     rax, rbx
0x1800a3b23  test    rax, rax
0x1800a3b26  jz      short loc_1800A3B54
0x1800a3b28  movups  xmm0, xmmword ptr [r10+7D0h]
0x1800a3b30  movq    rax, xmm0
0x1800a3b35  sub     rax, rsi
0x1800a3b38  jnz     short loc_1800A3B47
0x1800a3b3a  psrldq  xmm0, 8
0x1800a3b3f  movq    rax, xmm0
0x1800a3b44  sub     rax, rbx
0x1800a3b47  test    rax, rax
0x1800a3b4a  jz      short loc_1800A3B54
0x1800a3b4c  inc     r8d
0x1800a3b4f  jmp     loc_1800A3A62
0x1800a3b54  lea     rdi, [rdx+rcx]
0x1800a3b58  mov     rbx, [rsp+38h+arg_8]
0x1800a3b5d  mov     rax, rdi
0x1800a3b60  mov     rbp, [rsp+38h+arg_10]
0x1800a3b65  add     rsp, 20h
0x1800a3b69  pop     r14
0x1800a3b6b  pop     rdi
0x1800a3b6c  pop     rsi
0x1800a3b6d  retn
```
