# std::deque<std::pair<unsigned __int64,unsigned __int64>,std::allocator<std::pair<unsigned __int64,unsigned __int64>>>::_Growmap(unsigned __int64)

- ea: `0x18001606c`
- end: `0x18001621e`
- name: `?_Growmap@?$deque@U?$pair@_K_K@std@@V?$allocator@U?$pair@_K_K@std@@@2@@std@@AEAAX_K@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012c60`

## callees

- `0x180009e14`
- `0x180009f84`
- `0x18001606c`
- `0x180016284`
- `0x18004a078`

## import_xrefs

- `VCRUNTIME140!memset` at `0x180016159`
- `VCRUNTIME140!memset` at `0x18001619c`
- `VCRUNTIME140!memset` at `0x180016159`
- `VCRUNTIME140!memset` at `0x18001619c`
- `VCRUNTIME140!memmove` at `0x180016128`
- `VCRUNTIME140!memmove` at `0x180016143`
- `VCRUNTIME140!memmove` at `0x180016172`
- `VCRUNTIME140!memmove` at `0x18001618d`
- `VCRUNTIME140!memmove` at `0x180016128`
- `VCRUNTIME140!memmove` at `0x180016143`
- `VCRUNTIME140!memmove` at `0x180016172`
- `VCRUNTIME140!memmove` at `0x18001618d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001620b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001620b`

## pseudocode

```c
void __fastcall std::deque<std::pair<unsigned __int64,unsigned __int64>>::_Growmap(_QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  __int64 v5; // r15
  char *v6; // r14
  unsigned __int64 v7; // rcx
  char *v8; // r12
  __int64 v9; // rax
  unsigned __int64 v10; // rsi
  size_t v11; // rbx
  char *v12; // r12
  const void *v13; // rdx
  size_t v14; // r8
  char *v15; // rcx
  _QWORD *v16; // rcx

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0xFFFFFFFFFFFFFFFLL - v2 < v2 )
      std::deque<ATL::CComPtr<ITraceEvent>>::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3];
  if ( v2 > 0x1FFFFFFFFFFFFFFFLL )
    __scrt_throw_std_bad_array_new_length();
  _mm_lfence();
  v5 = 8 * v4;
  v6 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(8 * v2);
  v7 = v2 >> 1;
  v8 = &v6[8 * v4];
  while ( v2 <= v7 )
    v2 *= 2LL;
  v9 = a1[2];
  v10 = v2 - v9;
  v11 = 8 * v9 - v5;
  memmove(v8, (const void *)(a1[1] + v5), v11);
  v12 = &v8[v11];
  _mm_lfence();
  v13 = (const void *)a1[1];
  if ( v4 > v10 )
  {
    memmove(v12, v13, 8 * v10);
    memmove(v6, (const void *)(8 * v10 + a1[1]), v5 - 8 * v10);
    v15 = &v6[v5 - 8 * v10];
    v14 = 8 * v10;
  }
  else
  {
    memmove(v12, v13, 8 * v4);
    memset(&v12[v5], 0, 8 * (v10 - v4));
    v14 = 8 * v4;
    v15 = v6;
  }
  memset(v15, 0, v14);
  v16 = (_QWORD *)a1[1];
  if ( v16 )
  {
    if ( (unsigned __int64)(8LL * a1[2]) >= 0x1000 )
    {
      if ( (unsigned __int64)v16 - *(v16 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v16 = (_QWORD *)*(v16 - 1);
    }
    operator delete(v16);
  }
  a1[2] += v10;
  a1[1] = v6;
}

```

## disassembly

```asm
0x18001606c  mov     [rsp+arg_8], rbx
0x180016071  mov     [rsp+arg_10], rbp
0x180016076  push    rsi
0x180016077  push    rdi
0x180016078  push    r12
0x18001607a  push    r14
0x18001607c  push    r15
0x18001607e  sub     rsp, 30h
0x180016082  mov     rbp, rcx
0x180016085  mov     esi, 1
0x18001608a  mov     rcx, [rcx+10h]
0x18001608e  test    rcx, rcx
0x180016091  cmovnz  rsi, rcx
0x180016095  mov     rax, rsi
0x180016098  sub     rax, rcx
0x18001609b  cmp     rax, 1
0x18001609f  jb      short loc_1800160A7
0x1800160a1  cmp     rsi, 8
0x1800160a5  jnb     short loc_1800160C2
0x1800160a7  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800160b1  sub     rax, rsi
0x1800160b4  cmp     rax, rsi
0x1800160b7  jb      loc_180016218
0x1800160bd  add     rsi, rsi
0x1800160c0  jmp     short loc_180016095
0x1800160c2  mov     rdi, [rbp+18h]
0x1800160c6  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800160d0  cmp     rsi, rax
0x1800160d3  ja      loc_180016212
0x1800160d9  lfence
0x1800160dc  lea     rcx, ds:0[rsi*8]
0x1800160e4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800160e9  lea     r15, ds:0[rdi*8]
0x1800160f1  mov     rcx, rsi
0x1800160f4  mov     r14, rax
0x1800160f7  shr     rcx, 1
0x1800160fa  lea     r12, [r15+rax]
0x1800160fe  jmp     short loc_180016103
0x180016100  add     rsi, rsi
0x180016103  cmp     rsi, rcx
0x180016106  jbe     short loc_180016100
0x180016108  mov     rcx, [rbp+8]
0x18001610c  mov     rax, [rbp+10h]
0x180016110  sub     rsi, rax
0x180016113  shl     rax, 3
0x180016117  lea     rdx, [rcx+r15]; Src
0x18001611b  sub     rax, rdx
0x18001611e  lea     rbx, [rax+rcx]
0x180016122  mov     rcx, r12; void *
0x180016125  mov     r8, rbx; Size
0x180016128  call    cs:__imp_memmove
0x18001612e  add     r12, rbx
0x180016131  lfence
0x180016134  mov     rdx, [rbp+8]; Src
0x180016138  mov     rcx, r12; void *
0x18001613b  cmp     rdi, rsi
0x18001613e  ja      short loc_180016167
0x180016140  mov     r8, r15; Size
0x180016143  call    cs:__imp_memmove
0x180016149  mov     r8, rsi
0x18001614c  lea     rcx, [r15+r12]; void *
0x180016150  sub     r8, rdi
0x180016153  xor     edx, edx; Val
0x180016155  shl     r8, 3; Size
0x180016159  call    cs:__imp_memset
0x18001615f  mov     r8, r15
0x180016162  mov     rcx, r14
0x180016165  jmp     short loc_18001619A
0x180016167  lea     rdi, ds:0[rsi*8]
0x18001616f  mov     r8, rdi; Size
0x180016172  call    cs:__imp_memmove
0x180016178  mov     rax, [rbp+8]
0x18001617c  mov     rcx, r14; void *
0x18001617f  lea     rdx, [rdi+rax]; Src
0x180016183  sub     rax, rdx
0x180016186  lea     rbx, [rax+r15]
0x18001618a  mov     r8, rbx; Size
0x18001618d  call    cs:__imp_memmove
0x180016193  lea     rcx, [rbx+r14]; void *
0x180016197  mov     r8, rdi; Size
0x18001619a  xor     edx, edx; Val
0x18001619c  call    cs:__imp_memset
0x1800161a2  mov     rcx, [rbp+8]
0x1800161a6  test    rcx, rcx
0x1800161a9  jz      short loc_1800161D9
0x1800161ab  mov     rdx, [rbp+10h]
0x1800161af  shl     rdx, 3
0x1800161b3  cmp     rdx, 1000h
0x1800161ba  jb      short loc_1800161D4
0x1800161bc  mov     rax, [rcx-8]
0x1800161c0  add     rdx, 27h ; '''
0x1800161c4  sub     rcx, rax
0x1800161c7  sub     rcx, 8
0x1800161cb  cmp     rcx, 1Fh
0x1800161cf  ja      short loc_1800161F8
0x1800161d1  mov     rcx, rax; Block
0x1800161d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800161d9  add     [rbp+10h], rsi
0x1800161dd  mov     rbx, [rsp+58h+arg_8]
0x1800161e2  mov     [rbp+8], r14
0x1800161e6  mov     rbp, [rsp+58h+arg_10]
0x1800161eb  add     rsp, 30h
0x1800161ef  pop     r15
0x1800161f1  pop     r14
0x1800161f3  pop     r12
0x1800161f5  pop     rdi
0x1800161f6  pop     rsi
0x1800161f7  retn
0x1800161f8  xor     r9d, r9d; LineNo
0x1800161fb  mov     [rsp+58h+Reserved], 0; Reserved
0x180016204  xor     r8d, r8d; FileName
0x180016207  xor     edx, edx; FunctionName
0x180016209  xor     ecx, ecx; Expression
0x18001620b  call    cs:__imp__invoke_watson
0x180016212  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180016218  call    ?_Xlen@?$deque@V?$CComPtr@UITraceEvent@@@ATL@@V?$allocator@V?$CComPtr@UITraceEvent@@@ATL@@@std@@@std@@CAXXZ; std::deque<ATL::CComPtr<ITraceEvent>>::_Xlen(void)
```
