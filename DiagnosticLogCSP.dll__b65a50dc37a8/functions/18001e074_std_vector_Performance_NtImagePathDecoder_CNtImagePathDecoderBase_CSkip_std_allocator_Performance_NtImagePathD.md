# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &)

- ea: `0x18001e074`
- end: `0x18001e31c`
- name: `??$_Emplace_reallocate@AEBUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z`
- size: `680`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180022ee8`

## callees

- `0x180001bb4`
- `0x180001bf8`
- `0x18000a924`
- `0x18000c07c`
- `0x1800105f8`
- `0x18001e074`
- `0x1800205f0`
- `0x180027b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001e074  mov     [rsp+arg_10], r8
0x18001e079  push    rbx
0x18001e07a  push    rbp
0x18001e07b  push    rsi
0x18001e07c  push    rdi
0x18001e07d  push    r12
0x18001e07f  push    r13
0x18001e081  push    r14
0x18001e083  push    r15
0x18001e085  sub     rsp, 58h
0x18001e089  mov     r15, rdx
0x18001e08c  mov     rsi, rcx
0x18001e08f  mov     rbx, [rcx]
0x18001e092  mov     r9, [rcx+8]
0x18001e096  sub     r9, rbx
0x18001e099  sar     r9, 5
0x18001e09d  mov     r8, 7FFFFFFFFFFFFFFh
0x18001e0a7  cmp     r9, r8
0x18001e0aa  jz      loc_18001E310
0x18001e0b0  mov     rcx, [rcx+10h]
0x18001e0b4  sub     rcx, rbx
0x18001e0b7  sar     rcx, 5
0x18001e0bb  mov     rdx, rcx
0x18001e0be  shr     rdx, 1
0x18001e0c1  mov     rax, r8
0x18001e0c4  sub     rax, rdx
0x18001e0c7  cmp     rcx, rax
0x18001e0ca  ja      loc_18001E316
0x18001e0d0  lea     r13, [r9+1]
0x18001e0d4  lea     rax, [rdx+rcx]
0x18001e0d8  mov     rbp, r13
0x18001e0db  cmp     rax, r13
0x18001e0de  cmovnb  rbp, rax
0x18001e0e2  cmp     rbp, r8
0x18001e0e5  ja      loc_18001E316
0x18001e0eb  mov     r12, rbp
0x18001e0ee  shl     r12, 5
0x18001e0f2  test    r12, r12
0x18001e0f5  jnz     short loc_18001E0FB
0x18001e0f7  xor     edi, edi
0x18001e0f9  jmp     short loc_18001E13A
0x18001e0fb  cmp     r12, 1000h
0x18001e102  jb      short loc_18001E12F
0x18001e104  lea     rcx, [r12+27h]; Size
0x18001e109  cmp     rcx, r12
0x18001e10c  jbe     loc_18001E316
0x18001e112  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e117  test    rax, rax
0x18001e11a  jnz     short loc_18001E121
0x18001e11c  lea     ecx, [rax+5]
0x18001e11f  int     29h; Win8: RtlFailFast(ecx)
0x18001e121  lea     rdi, [rax+27h]
0x18001e125  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18001e129  mov     [rdi-8], rax
0x18001e12d  jmp     short loc_18001E13A
0x18001e12f  mov     rcx, r12; Size
0x18001e132  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e137  mov     rdi, rax
0x18001e13a  mov     r14, r15
0x18001e13d  sub     r14, rbx
0x18001e140  sar     r14, 5
0x18001e144  mov     rbx, r14
0x18001e147  shl     rbx, 5
0x18001e14b  add     rbx, rdi
0x18001e14e  lea     rcx, [rbx+20h]
0x18001e152  mov     [rsp+98h+var_78], rsi
0x18001e157  mov     [rsp+98h+var_70], rdi
0x18001e15c  mov     [rsp+98h+var_68], rbp
0x18001e161  mov     [rsp+98h+var_60], rcx
0x18001e166  mov     [rsp+98h+var_58], rcx
0x18001e16b  mov     rdx, [rsp+98h+arg_10]
0x18001e173  mov     rcx, rbx
0x18001e176  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e17b  mov     [rsp+98h+var_60], rbx
0x18001e180  mov     r9, [rsi+8]
0x18001e184  mov     rcx, [rsi]
0x18001e187  mov     rdx, rdi
0x18001e18a  cmp     r15, r9
0x18001e18d  jnz     short loc_18001E1E5
0x18001e18f  cmp     rcx, r9
0x18001e192  jz      short loc_18001E1DC
0x18001e194  mov     r8d, 7
0x18001e19a  xorps   xmm0, xmm0
0x18001e19d  movups  xmmword ptr [rdx], xmm0
0x18001e1a0  mov     qword ptr [rdx+10h], 0
0x18001e1a8  mov     qword ptr [rdx+18h], 0
0x18001e1b0  movups  xmm0, xmmword ptr [rcx]
0x18001e1b3  movups  xmmword ptr [rdx], xmm0
0x18001e1b6  movups  xmm1, xmmword ptr [rcx+10h]
0x18001e1ba  movups  xmmword ptr [rdx+10h], xmm1
0x18001e1be  mov     qword ptr [rcx+10h], 0
0x18001e1c6  mov     [rcx+18h], r8
0x18001e1ca  xor     eax, eax
0x18001e1cc  mov     [rcx], ax
0x18001e1cf  lea     rdx, [rdx+20h]
0x18001e1d3  add     rcx, 20h ; ' '
0x18001e1d7  cmp     rcx, r9
0x18001e1da  jnz     short loc_18001E19A
0x18001e1dc  shl     r14, 5
0x18001e1e0  jmp     loc_18001E272
0x18001e1e5  mov     r8d, 7
0x18001e1eb  xor     r9d, r9d
0x18001e1ee  cmp     rcx, r15
0x18001e1f1  jz      short loc_18001E225
0x18001e1f3  xorps   xmm0, xmm0
0x18001e1f6  movups  xmmword ptr [rdx], xmm0
0x18001e1f9  mov     [rdx+10h], r9
0x18001e1fd  mov     [rdx+18h], r9
0x18001e201  movups  xmm0, xmmword ptr [rcx]
0x18001e204  movups  xmmword ptr [rdx], xmm0
0x18001e207  movups  xmm1, xmmword ptr [rcx+10h]
0x18001e20b  movups  xmmword ptr [rdx+10h], xmm1
0x18001e20f  mov     [rcx+10h], r9
0x18001e213  mov     [rcx+18h], r8
0x18001e217  mov     [rcx], r9w
0x18001e21b  lea     rdx, [rdx+20h]
0x18001e21f  add     rcx, 20h ; ' '
0x18001e223  jmp     short loc_18001E1EE
0x18001e225  mov     [rsp+98h+var_60], rdi
0x18001e22a  shl     r14, 5
0x18001e22e  mov     rdx, [rsi+8]
0x18001e232  lea     rcx, [r14+20h]
0x18001e236  add     rcx, rdi
0x18001e239  jmp     short loc_18001E26D
0x18001e23b  xorps   xmm0, xmm0
0x18001e23e  movups  xmmword ptr [rcx], xmm0
0x18001e241  mov     [rcx+10h], r9
0x18001e245  mov     [rcx+18h], r9
0x18001e249  movups  xmm0, xmmword ptr [r15]
0x18001e24d  movups  xmmword ptr [rcx], xmm0
0x18001e250  movups  xmm1, xmmword ptr [r15+10h]
0x18001e255  movups  xmmword ptr [rcx+10h], xmm1
0x18001e259  mov     [r15+10h], r9
0x18001e25d  mov     [r15+18h], r8
0x18001e261  mov     [r15], r9w
0x18001e265  lea     rcx, [rcx+20h]
0x18001e269  add     r15, 20h ; ' '
0x18001e26d  cmp     r15, rdx
0x18001e270  jnz     short loc_18001E23B
0x18001e272  mov     [rsp+98h+var_70], 0
0x18001e27b  mov     rbx, [rsi]
0x18001e27e  test    rbx, rbx
0x18001e281  jz      short loc_18001E2D7
0x18001e283  mov     rbp, [rsi+8]
0x18001e287  jmp     short loc_18001E295
0x18001e289  mov     rcx, rbx
0x18001e28c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e291  add     rbx, 20h ; ' '
0x18001e295  cmp     rbx, rbp
0x18001e298  jnz     short loc_18001E289
0x18001e29a  mov     rax, [rsi]
0x18001e29d  mov     rdx, [rsi+10h]
0x18001e2a1  sub     rdx, rax
0x18001e2a4  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x18001e2a8  cmp     rdx, 1000h
0x18001e2af  jb      short loc_18001E2CF
0x18001e2b1  mov     rcx, [rax-8]
0x18001e2b5  sub     rax, rcx
0x18001e2b8  sub     rax, 8
0x18001e2bc  cmp     rax, 1Fh
0x18001e2c0  ja      short loc_18001E2C8
0x18001e2c2  add     rdx, 27h ; '''
0x18001e2c6  jmp     short loc_18001E2D2
0x18001e2c8  mov     ecx, 5
0x18001e2cd  int     29h; Win8: RtlFailFast(ecx)
0x18001e2cf  mov     rcx, rax; void *
0x18001e2d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e2d7  mov     [rsi], rdi
0x18001e2da  shl     r13, 5
0x18001e2de  add     r13, rdi
0x18001e2e1  mov     [rsi+8], r13
0x18001e2e5  lea     rax, [r12+rdi]
0x18001e2e9  mov     [rsi+10h], rax
0x18001e2ed  lea     rbx, [r14+rdi]
0x18001e2f1  lea     rcx, [rsp+98h+var_78]
0x18001e2f6  call    ??1_Reallocation_guard@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001e2fb  mov     rax, rbx
0x18001e2fe  add     rsp, 58h
0x18001e302  pop     r15
0x18001e304  pop     r14
0x18001e306  pop     r13
0x18001e308  pop     r12
0x18001e30a  pop     rdi
0x18001e30b  pop     rsi
0x18001e30c  pop     rbp
0x18001e30d  pop     rbx
0x18001e30e  retn
0x18001e310  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
0x18001e316  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
