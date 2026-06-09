# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &)

- ea: `0x18001d0dc`
- end: `0x18001d383`
- name: `??$_Emplace_reallocate@AEBUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z`
- size: `679`
- prototype: `char *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180021fa4`

## callees

- `0x180001b84`
- `0x180001bc8`
- `0x18000a600`
- `0x18000bb3c`
- `0x18000fde8`
- `0x18001d0dc`
- `0x18001f5d4`
- `0x180026964`

## pseudocode

```c
char *__fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  void *v5; // rbx
  __int64 v6; // r9
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 v9; // r13
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // r12
  _QWORD *v12; // rdi
  void *v13; // rax
  __int64 v14; // r14
  char *v15; // rbx
  __int64 v16; // r9
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  __int64 v19; // r14
  char *v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rbp
  __int64 v23; // rax
  unsigned __int64 v24; // rdx
  void *v25; // rcx
  _QWORD *v27; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v28; // [rsp+28h] [rbp-70h]
  unsigned __int64 v29; // [rsp+30h] [rbp-68h]
  _QWORD *v30; // [rsp+38h] [rbp-60h]
  char *v31; // [rsp+40h] [rbp-58h]

  v5 = (void *)*a1;
  v6 = (__int64)(a1[1] - *a1) >> 5;
  if ( v6 == 0x7FFFFFFFFFFFFFFLL )
    std::vector<unsigned int>::_Xlength();
  v7 = (__int64)(a1[2] - (_QWORD)v5) >> 5;
  v8 = v7 >> 1;
  if ( v7 > 0x7FFFFFFFFFFFFFFLL - (v7 >> 1) )
    goto LABEL_35;
  v9 = v6 + 1;
  v10 = v6 + 1;
  if ( v8 + v7 >= v6 + 1 )
    v10 = v8 + v7;
  if ( v10 > 0x7FFFFFFFFFFFFFFLL )
    goto LABEL_35;
  v11 = 32 * v10;
  if ( !(32 * v10) )
  {
    v12 = 0;
    goto LABEL_14;
  }
  if ( v11 < 0x1000 )
  {
    v12 = operator new(32 * v10);
    goto LABEL_14;
  }
  if ( v11 + 39 < v11 )
LABEL_35:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v11 + 39);
  if ( !v13 )
    __fastfail(5u);
  v12 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v12 - 1) = v13;
LABEL_14:
  v14 = (a2 - (__int64)v5) >> 5;
  v15 = (char *)&v12[4 * v14];
  v27 = a1;
  v28 = v12;
  v29 = v10;
  v31 = v15 + 32;
  std::wstring::wstring(v15, a3);
  v30 = v15;
  v16 = a1[1];
  v17 = *a1;
  v18 = v12;
  if ( a2 == v16 )
  {
    for ( ; v17 != v16; v17 += 32 )
    {
      *(_OWORD *)v18 = 0;
      v18[2] = 0;
      v18[3] = 0;
      *(_OWORD *)v18 = *(_OWORD *)v17;
      *((_OWORD *)v18 + 1) = *(_OWORD *)(v17 + 16);
      *(_QWORD *)(v17 + 16) = 0;
      *(_QWORD *)(v17 + 24) = 7;
      *(_WORD *)v17 = 0;
      v18 += 4;
    }
    v19 = 4 * v14;
  }
  else
  {
    while ( v17 != a2 )
    {
      *(_OWORD *)v18 = 0;
      v18[2] = 0;
      v18[3] = 0;
      *(_OWORD *)v18 = *(_OWORD *)v17;
      *((_OWORD *)v18 + 1) = *(_OWORD *)(v17 + 16);
      *(_QWORD *)(v17 + 16) = 0;
      *(_QWORD *)(v17 + 24) = 7;
      *(_WORD *)v17 = 0;
      v18 += 4;
      v17 += 32;
    }
    v30 = v12;
    v19 = 4 * v14;
    v18 = (_QWORD *)a1[1];
    v20 = (char *)&v12[v19 + 4];
    while ( (_QWORD *)a2 != v18 )
    {
      *(_OWORD *)v20 = 0;
      *((_QWORD *)v20 + 2) = 0;
      *((_QWORD *)v20 + 3) = 0;
      *(_OWORD *)v20 = *(_OWORD *)a2;
      *((_OWORD *)v20 + 1) = *(_OWORD *)(a2 + 16);
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 7;
      *(_WORD *)a2 = 0;
      v20 += 32;
      a2 += 32;
    }
  }
  v28 = 0;
  v21 = *a1;
  if ( *a1 )
  {
    v22 = a1[1];
    while ( v21 != v22 )
    {
      std::wstring::~wstring(v21);
      v21 += 32;
    }
    v23 = *a1;
    v24 = (a1[2] - *a1) & 0xFFFFFFFFFFFFFFE0uLL;
    if ( v24 < 0x1000 )
    {
      v25 = (void *)*a1;
    }
    else
    {
      v25 = *(void **)(v23 - 8);
      if ( (unsigned __int64)(v23 - (_QWORD)v25 - 8) > 0x1F )
        __fastfail(5u);
      v24 += 39LL;
    }
    operator delete(v25, v24);
  }
  *a1 = v12;
  a1[1] = &v12[4 * v9];
  a1[2] = &v12[v11 / 8];
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(
    &v27,
    v18);
  return (char *)&v12[v19];
}

```

## disassembly

```asm
0x18001d0dc  mov     [rsp+arg_10], r8
0x18001d0e1  push    rbx
0x18001d0e2  push    rbp
0x18001d0e3  push    rsi
0x18001d0e4  push    rdi
0x18001d0e5  push    r12
0x18001d0e7  push    r13
0x18001d0e9  push    r14
0x18001d0eb  push    r15
0x18001d0ed  sub     rsp, 58h
0x18001d0f1  mov     r15, rdx
0x18001d0f4  mov     rsi, rcx
0x18001d0f7  mov     rbx, [rcx]
0x18001d0fa  mov     r9, [rcx+8]
0x18001d0fe  sub     r9, rbx
0x18001d101  sar     r9, 5
0x18001d105  mov     r8, 7FFFFFFFFFFFFFFh
0x18001d10f  cmp     r9, r8
0x18001d112  jz      loc_18001D377
0x18001d118  mov     rcx, [rcx+10h]
0x18001d11c  sub     rcx, rbx
0x18001d11f  sar     rcx, 5
0x18001d123  mov     rdx, rcx
0x18001d126  shr     rdx, 1
0x18001d129  mov     rax, r8
0x18001d12c  sub     rax, rdx
0x18001d12f  cmp     rcx, rax
0x18001d132  ja      loc_18001D37D
0x18001d138  lea     r13, [r9+1]
0x18001d13c  lea     rax, [rdx+rcx]
0x18001d140  mov     rbp, r13
0x18001d143  cmp     rax, r13
0x18001d146  cmovnb  rbp, rax
0x18001d14a  cmp     rbp, r8
0x18001d14d  ja      loc_18001D37D
0x18001d153  mov     r12, rbp
0x18001d156  shl     r12, 5
0x18001d15a  test    r12, r12
0x18001d15d  jnz     short loc_18001D163
0x18001d15f  xor     edi, edi
0x18001d161  jmp     short loc_18001D1A2
0x18001d163  cmp     r12, 1000h
0x18001d16a  jb      short loc_18001D197
0x18001d16c  lea     rcx, [r12+27h]; Size
0x18001d171  cmp     rcx, r12
0x18001d174  jbe     loc_18001D37D
0x18001d17a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d17f  test    rax, rax
0x18001d182  jnz     short loc_18001D189
0x18001d184  lea     ecx, [rax+5]
0x18001d187  int     29h; Win8: RtlFailFast(ecx)
0x18001d189  lea     rdi, [rax+27h]
0x18001d18d  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18001d191  mov     [rdi-8], rax
0x18001d195  jmp     short loc_18001D1A2
0x18001d197  mov     rcx, r12; Size
0x18001d19a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d19f  mov     rdi, rax
0x18001d1a2  mov     r14, r15
0x18001d1a5  sub     r14, rbx
0x18001d1a8  sar     r14, 5
0x18001d1ac  mov     rbx, r14
0x18001d1af  shl     rbx, 5
0x18001d1b3  add     rbx, rdi
0x18001d1b6  lea     rcx, [rbx+20h]
0x18001d1ba  mov     [rsp+98h+var_78], rsi
0x18001d1bf  mov     [rsp+98h+var_70], rdi
0x18001d1c4  mov     [rsp+98h+var_68], rbp
0x18001d1c9  mov     [rsp+98h+var_60], rcx
0x18001d1ce  mov     [rsp+98h+var_58], rcx
0x18001d1d3  mov     rdx, [rsp+98h+arg_10]
0x18001d1db  mov     rcx, rbx
0x18001d1de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d1e3  mov     [rsp+98h+var_60], rbx
0x18001d1e8  mov     r9, [rsi+8]
0x18001d1ec  mov     rcx, [rsi]
0x18001d1ef  mov     rdx, rdi
0x18001d1f2  cmp     r15, r9
0x18001d1f5  jnz     short loc_18001D24D
0x18001d1f7  cmp     rcx, r9
0x18001d1fa  jz      short loc_18001D244
0x18001d1fc  mov     r8d, 7
0x18001d202  xorps   xmm0, xmm0
0x18001d205  movups  xmmword ptr [rdx], xmm0
0x18001d208  mov     qword ptr [rdx+10h], 0
0x18001d210  mov     qword ptr [rdx+18h], 0
0x18001d218  movups  xmm0, xmmword ptr [rcx]
0x18001d21b  movups  xmmword ptr [rdx], xmm0
0x18001d21e  movups  xmm1, xmmword ptr [rcx+10h]
0x18001d222  movups  xmmword ptr [rdx+10h], xmm1
0x18001d226  mov     qword ptr [rcx+10h], 0
0x18001d22e  mov     [rcx+18h], r8
0x18001d232  xor     eax, eax
0x18001d234  mov     [rcx], ax
0x18001d237  lea     rdx, [rdx+20h]
0x18001d23b  add     rcx, 20h ; ' '
0x18001d23f  cmp     rcx, r9
0x18001d242  jnz     short loc_18001D202
0x18001d244  shl     r14, 5
0x18001d248  jmp     loc_18001D2DA
0x18001d24d  mov     r8d, 7
0x18001d253  xor     r9d, r9d
0x18001d256  cmp     rcx, r15
0x18001d259  jz      short loc_18001D28D
0x18001d25b  xorps   xmm0, xmm0
0x18001d25e  movups  xmmword ptr [rdx], xmm0
0x18001d261  mov     [rdx+10h], r9
0x18001d265  mov     [rdx+18h], r9
0x18001d269  movups  xmm0, xmmword ptr [rcx]
0x18001d26c  movups  xmmword ptr [rdx], xmm0
0x18001d26f  movups  xmm1, xmmword ptr [rcx+10h]
0x18001d273  movups  xmmword ptr [rdx+10h], xmm1
0x18001d277  mov     [rcx+10h], r9
0x18001d27b  mov     [rcx+18h], r8
0x18001d27f  mov     [rcx], r9w
0x18001d283  lea     rdx, [rdx+20h]
0x18001d287  add     rcx, 20h ; ' '
0x18001d28b  jmp     short loc_18001D256
0x18001d28d  mov     [rsp+98h+var_60], rdi
0x18001d292  shl     r14, 5
0x18001d296  mov     rdx, [rsi+8]
0x18001d29a  lea     rcx, [r14+20h]
0x18001d29e  add     rcx, rdi
0x18001d2a1  jmp     short loc_18001D2D5
0x18001d2a3  xorps   xmm0, xmm0
0x18001d2a6  movups  xmmword ptr [rcx], xmm0
0x18001d2a9  mov     [rcx+10h], r9
0x18001d2ad  mov     [rcx+18h], r9
0x18001d2b1  movups  xmm0, xmmword ptr [r15]
0x18001d2b5  movups  xmmword ptr [rcx], xmm0
0x18001d2b8  movups  xmm1, xmmword ptr [r15+10h]
0x18001d2bd  movups  xmmword ptr [rcx+10h], xmm1
0x18001d2c1  mov     [r15+10h], r9
0x18001d2c5  mov     [r15+18h], r8
0x18001d2c9  mov     [r15], r9w
0x18001d2cd  lea     rcx, [rcx+20h]
0x18001d2d1  add     r15, 20h ; ' '
0x18001d2d5  cmp     r15, rdx
0x18001d2d8  jnz     short loc_18001D2A3
0x18001d2da  mov     [rsp+98h+var_70], 0
0x18001d2e3  mov     rbx, [rsi]
0x18001d2e6  test    rbx, rbx
0x18001d2e9  jz      short loc_18001D33F
0x18001d2eb  mov     rbp, [rsi+8]
0x18001d2ef  jmp     short loc_18001D2FD
0x18001d2f1  mov     rcx, rbx
0x18001d2f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d2f9  add     rbx, 20h ; ' '
0x18001d2fd  cmp     rbx, rbp
0x18001d300  jnz     short loc_18001D2F1
0x18001d302  mov     rax, [rsi]
0x18001d305  mov     rdx, [rsi+10h]
0x18001d309  sub     rdx, rax
0x18001d30c  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x18001d310  cmp     rdx, 1000h
0x18001d317  jb      short loc_18001D337
0x18001d319  mov     rcx, [rax-8]
0x18001d31d  sub     rax, rcx
0x18001d320  sub     rax, 8
0x18001d324  cmp     rax, 1Fh
0x18001d328  ja      short loc_18001D330
0x18001d32a  add     rdx, 27h ; '''
0x18001d32e  jmp     short loc_18001D33A
0x18001d330  mov     ecx, 5
0x18001d335  int     29h; Win8: RtlFailFast(ecx)
0x18001d337  mov     rcx, rax; void *
0x18001d33a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d33f  mov     [rsi], rdi
0x18001d342  shl     r13, 5
0x18001d346  add     r13, rdi
0x18001d349  mov     [rsi+8], r13
0x18001d34d  lea     rax, [r12+rdi]
0x18001d351  mov     [rsi+10h], rax
0x18001d355  lea     rbx, [r14+rdi]
0x18001d359  lea     rcx, [rsp+98h+var_78]
0x18001d35e  call    ??1_Reallocation_guard@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001d363  mov     rax, rbx
0x18001d366  add     rsp, 58h
0x18001d36a  pop     r15
0x18001d36c  pop     r14
0x18001d36e  pop     r13
0x18001d370  pop     r12
0x18001d372  pop     rdi
0x18001d373  pop     rsi
0x18001d374  pop     rbp
0x18001d375  pop     rbx
0x18001d376  retn
0x18001d377  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
0x18001d37d  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
