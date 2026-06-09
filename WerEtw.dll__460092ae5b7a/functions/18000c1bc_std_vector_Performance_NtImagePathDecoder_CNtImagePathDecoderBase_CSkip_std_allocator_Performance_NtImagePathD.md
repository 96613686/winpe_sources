# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &)

- ea: `0x18000c1bc`
- end: `0x18000c463`
- name: `??$_Emplace_reallocate@AEBUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z`
- size: `679`
- prototype: `char *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180011394`

## callees

- `0x180001894`
- `0x1800018a0`
- `0x18000b534`
- `0x18000be50`
- `0x18000c1bc`
- `0x18000d074`
- `0x18000e9b0`
- `0x180015b68`

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
  void *v24; // rcx
  _QWORD *v26; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v27; // [rsp+28h] [rbp-70h]
  unsigned __int64 v28; // [rsp+30h] [rbp-68h]
  _QWORD *v29; // [rsp+38h] [rbp-60h]
  char *v30; // [rsp+40h] [rbp-58h]

  v5 = (void *)*a1;
  v6 = (__int64)(a1[1] - *a1) >> 5;
  if ( v6 == 0x7FFFFFFFFFFFFFFLL )
    std::vector<unsigned int>::_Xlength();
  v7 = (__int64)(a1[2] - (_QWORD)v5) >> 5;
  v8 = v7 >> 1;
  if ( v7 > 0x7FFFFFFFFFFFFFFLL - (v7 >> 1) )
    goto LABEL_34;
  v9 = v6 + 1;
  v10 = v6 + 1;
  if ( v8 + v7 >= v6 + 1 )
    v10 = v8 + v7;
  if ( v10 > 0x7FFFFFFFFFFFFFFLL )
    goto LABEL_34;
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
LABEL_34:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v11 + 39);
  if ( !v13 )
    __fastfail(5u);
  v12 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v12 - 1) = v13;
LABEL_14:
  v14 = (a2 - (__int64)v5) >> 5;
  v15 = (char *)&v12[4 * v14];
  v26 = a1;
  v27 = v12;
  v28 = v10;
  v30 = v15 + 32;
  std::wstring::wstring(v15, a3);
  v29 = v15;
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
    v29 = v12;
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
  v27 = 0;
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
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFE0uLL) < 0x1000 )
    {
      v24 = (void *)*a1;
    }
    else
    {
      v24 = *(void **)(v23 - 8);
      if ( (unsigned __int64)(v23 - (_QWORD)v24 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v24);
  }
  *a1 = v12;
  a1[1] = &v12[4 * v9];
  a1[2] = &v12[v11 / 8];
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(
    &v26,
    v18);
  return (char *)&v12[v19];
}

```

## disassembly

```asm
0x18000c1bc  mov     [rsp+arg_10], r8
0x18000c1c1  push    rbx
0x18000c1c2  push    rbp
0x18000c1c3  push    rsi
0x18000c1c4  push    rdi
0x18000c1c5  push    r12
0x18000c1c7  push    r13
0x18000c1c9  push    r14
0x18000c1cb  push    r15
0x18000c1cd  sub     rsp, 58h
0x18000c1d1  mov     r15, rdx
0x18000c1d4  mov     rsi, rcx
0x18000c1d7  mov     rbx, [rcx]
0x18000c1da  mov     r9, [rcx+8]
0x18000c1de  sub     r9, rbx
0x18000c1e1  sar     r9, 5
0x18000c1e5  mov     r8, 7FFFFFFFFFFFFFFh
0x18000c1ef  cmp     r9, r8
0x18000c1f2  jz      loc_18000C457
0x18000c1f8  mov     rcx, [rcx+10h]
0x18000c1fc  sub     rcx, rbx
0x18000c1ff  sar     rcx, 5
0x18000c203  mov     rdx, rcx
0x18000c206  shr     rdx, 1
0x18000c209  mov     rax, r8
0x18000c20c  sub     rax, rdx
0x18000c20f  cmp     rcx, rax
0x18000c212  ja      loc_18000C45D
0x18000c218  lea     r13, [r9+1]
0x18000c21c  lea     rax, [rdx+rcx]
0x18000c220  mov     rbp, r13
0x18000c223  cmp     rax, r13
0x18000c226  cmovnb  rbp, rax
0x18000c22a  cmp     rbp, r8
0x18000c22d  ja      loc_18000C45D
0x18000c233  mov     r12, rbp
0x18000c236  shl     r12, 5
0x18000c23a  test    r12, r12
0x18000c23d  jnz     short loc_18000C243
0x18000c23f  xor     edi, edi
0x18000c241  jmp     short loc_18000C282
0x18000c243  cmp     r12, 1000h
0x18000c24a  jb      short loc_18000C277
0x18000c24c  lea     rcx, [r12+27h]; Size
0x18000c251  cmp     rcx, r12
0x18000c254  jbe     loc_18000C45D
0x18000c25a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c25f  test    rax, rax
0x18000c262  jnz     short loc_18000C269
0x18000c264  lea     ecx, [rax+5]
0x18000c267  int     29h; Win8: RtlFailFast(ecx)
0x18000c269  lea     rdi, [rax+27h]
0x18000c26d  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000c271  mov     [rdi-8], rax
0x18000c275  jmp     short loc_18000C282
0x18000c277  mov     rcx, r12; Size
0x18000c27a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c27f  mov     rdi, rax
0x18000c282  mov     r14, r15
0x18000c285  sub     r14, rbx
0x18000c288  sar     r14, 5
0x18000c28c  mov     rbx, r14
0x18000c28f  shl     rbx, 5
0x18000c293  add     rbx, rdi
0x18000c296  lea     rcx, [rbx+20h]
0x18000c29a  mov     [rsp+98h+var_78], rsi
0x18000c29f  mov     [rsp+98h+var_70], rdi
0x18000c2a4  mov     [rsp+98h+var_68], rbp
0x18000c2a9  mov     [rsp+98h+var_60], rcx
0x18000c2ae  mov     [rsp+98h+var_58], rcx
0x18000c2b3  mov     rdx, [rsp+98h+arg_10]
0x18000c2bb  mov     rcx, rbx
0x18000c2be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c2c3  mov     [rsp+98h+var_60], rbx
0x18000c2c8  mov     r9, [rsi+8]
0x18000c2cc  mov     rcx, [rsi]
0x18000c2cf  mov     rdx, rdi
0x18000c2d2  cmp     r15, r9
0x18000c2d5  jnz     short loc_18000C32D
0x18000c2d7  cmp     rcx, r9
0x18000c2da  jz      short loc_18000C324
0x18000c2dc  mov     r8d, 7
0x18000c2e2  xorps   xmm0, xmm0
0x18000c2e5  movups  xmmword ptr [rdx], xmm0
0x18000c2e8  mov     qword ptr [rdx+10h], 0
0x18000c2f0  mov     qword ptr [rdx+18h], 0
0x18000c2f8  movups  xmm0, xmmword ptr [rcx]
0x18000c2fb  movups  xmmword ptr [rdx], xmm0
0x18000c2fe  movups  xmm1, xmmword ptr [rcx+10h]
0x18000c302  movups  xmmword ptr [rdx+10h], xmm1
0x18000c306  mov     qword ptr [rcx+10h], 0
0x18000c30e  mov     [rcx+18h], r8
0x18000c312  xor     eax, eax
0x18000c314  mov     [rcx], ax
0x18000c317  lea     rdx, [rdx+20h]
0x18000c31b  add     rcx, 20h ; ' '
0x18000c31f  cmp     rcx, r9
0x18000c322  jnz     short loc_18000C2E2
0x18000c324  shl     r14, 5
0x18000c328  jmp     loc_18000C3BA
0x18000c32d  mov     r8d, 7
0x18000c333  xor     r9d, r9d
0x18000c336  cmp     rcx, r15
0x18000c339  jz      short loc_18000C36D
0x18000c33b  xorps   xmm0, xmm0
0x18000c33e  movups  xmmword ptr [rdx], xmm0
0x18000c341  mov     [rdx+10h], r9
0x18000c345  mov     [rdx+18h], r9
0x18000c349  movups  xmm0, xmmword ptr [rcx]
0x18000c34c  movups  xmmword ptr [rdx], xmm0
0x18000c34f  movups  xmm1, xmmword ptr [rcx+10h]
0x18000c353  movups  xmmword ptr [rdx+10h], xmm1
0x18000c357  mov     [rcx+10h], r9
0x18000c35b  mov     [rcx+18h], r8
0x18000c35f  mov     [rcx], r9w
0x18000c363  lea     rdx, [rdx+20h]
0x18000c367  add     rcx, 20h ; ' '
0x18000c36b  jmp     short loc_18000C336
0x18000c36d  mov     [rsp+98h+var_60], rdi
0x18000c372  shl     r14, 5
0x18000c376  mov     rdx, [rsi+8]
0x18000c37a  lea     rcx, [r14+20h]
0x18000c37e  add     rcx, rdi
0x18000c381  jmp     short loc_18000C3B5
0x18000c383  xorps   xmm0, xmm0
0x18000c386  movups  xmmword ptr [rcx], xmm0
0x18000c389  mov     [rcx+10h], r9
0x18000c38d  mov     [rcx+18h], r9
0x18000c391  movups  xmm0, xmmword ptr [r15]
0x18000c395  movups  xmmword ptr [rcx], xmm0
0x18000c398  movups  xmm1, xmmword ptr [r15+10h]
0x18000c39d  movups  xmmword ptr [rcx+10h], xmm1
0x18000c3a1  mov     [r15+10h], r9
0x18000c3a5  mov     [r15+18h], r8
0x18000c3a9  mov     [r15], r9w
0x18000c3ad  lea     rcx, [rcx+20h]
0x18000c3b1  add     r15, 20h ; ' '
0x18000c3b5  cmp     r15, rdx
0x18000c3b8  jnz     short loc_18000C383
0x18000c3ba  mov     [rsp+98h+var_70], 0
0x18000c3c3  mov     rbx, [rsi]
0x18000c3c6  test    rbx, rbx
0x18000c3c9  jz      short loc_18000C41F
0x18000c3cb  mov     rbp, [rsi+8]
0x18000c3cf  jmp     short loc_18000C3DD
0x18000c3d1  mov     rcx, rbx
0x18000c3d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c3d9  add     rbx, 20h ; ' '
0x18000c3dd  cmp     rbx, rbp
0x18000c3e0  jnz     short loc_18000C3D1
0x18000c3e2  mov     rax, [rsi]
0x18000c3e5  mov     rdx, [rsi+10h]
0x18000c3e9  sub     rdx, rax
0x18000c3ec  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18000c3f0  cmp     rdx, 1000h
0x18000c3f7  jb      short loc_18000C417
0x18000c3f9  mov     rcx, [rax-8]
0x18000c3fd  sub     rax, rcx
0x18000c400  sub     rax, 8
0x18000c404  cmp     rax, 1Fh
0x18000c408  ja      short loc_18000C410
0x18000c40a  add     rdx, 27h ; '''
0x18000c40e  jmp     short loc_18000C41A
0x18000c410  mov     ecx, 5
0x18000c415  int     29h; Win8: RtlFailFast(ecx)
0x18000c417  mov     rcx, rax; Block
0x18000c41a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c41f  mov     [rsi], rdi
0x18000c422  shl     r13, 5
0x18000c426  add     r13, rdi
0x18000c429  mov     [rsi+8], r13
0x18000c42d  lea     rax, [r12+rdi]
0x18000c431  mov     [rsi+10h], rax
0x18000c435  lea     rbx, [r14+rdi]
0x18000c439  lea     rcx, [rsp+98h+var_78]
0x18000c43e  call    ??1_Reallocation_guard@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000c443  mov     rax, rbx
0x18000c446  add     rsp, 58h
0x18000c44a  pop     r15
0x18000c44c  pop     r14
0x18000c44e  pop     r13
0x18000c450  pop     r12
0x18000c452  pop     rdi
0x18000c453  pop     rsi
0x18000c454  pop     rbp
0x18000c455  pop     rbx
0x18000c456  retn
0x18000c457  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
0x18000c45d  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
