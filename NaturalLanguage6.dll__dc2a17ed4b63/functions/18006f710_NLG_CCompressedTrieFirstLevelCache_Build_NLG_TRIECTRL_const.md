# NLG::CCompressedTrieFirstLevelCache::Build(NLG::TRIECTRL const *)

- ea: `0x18006f710`
- end: `0x18006f969`
- name: `?Build@CCompressedTrieFirstLevelCache@NLG@@IEAAXPEBUTRIECTRL@2@@Z`
- size: `601`
- prototype: `void __fastcall(NLG::CCompressedTrieFirstLevelCache *this, const struct NLG::TRIECTRL *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180070230`

## callees

- `0x180011e90`
- `0x180011fe0`
- `0x18002c080`
- `0x180035640`
- `0x18003e188`
- `0x18003ed6c`
- `0x18006f710`
- `0x18009e2c2`
- `0x18009e300`

## pseudocode

```c
void __fastcall NLG::CCompressedTrieFirstLevelCache::Build(
        NLG::CCompressedTrieFirstLevelCache *this,
        const struct NLG::TRIECTRL *a2)
{
  int v4; // ebx
  void *v5; // rax
  size_t v6; // r8
  struct NLG::TRIESCAN *v7; // r8
  int v8; // ecx
  int v9; // r10d
  int i; // r9d
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // edx
  unsigned __int64 v14; // rax
  void *v15; // rax
  void *v16; // rcx
  int v17; // r14d
  int v18; // ebx
  struct NLG::TRIESCAN *v19; // r8
  int Its; // eax
  __m128i v21; // xmm2
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  char epi16; // cl
  int v30; // eax
  _OWORD pExceptionObject[5]; // [rsp+20h] [rbp-39h] BYREF
  __int64 v32; // [rsp+70h] [rbp+17h]
  const void *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !*(_BYTE *)this && *(_DWORD *)(*(_QWORD *)a2 + 20LL) )
  {
    *((_DWORD *)this + 9) = 4096;
    v4 = 0;
    v5 = operator new[](0x4000u);
    v6 = 4LL * *((int *)this + 9);
    *((_QWORD *)this + 3) = v5;
    memset_0(v5, 0, v6);
    memset_0(pExceptionObject, 0, 0x58u);
    while ( NLG::TrieGetNextNode(a2, (const struct NLG::TRIECTRL *)pExceptionObject, v7) )
    {
      v8 = LOWORD(pExceptionObject[0]) >> 4;
      if ( v8 > *((_DWORD *)this + 9) - 1 )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, 534, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      v7 = (struct NLG::TRIESCAN *)v8;
      *(_DWORD *)(*((_QWORD *)this + 3) + 4LL * v8) = (*(_DWORD *)(*((_QWORD *)this + 3) + 4LL * v8) + 1)
                                                    | (1 << (31 - (pExceptionObject[0] & 0xF)));
      ++v4;
    }
    v9 = 0;
    for ( i = 0; i < *((_DWORD *)this + 9); v9 += (unsigned __int16)v13 )
    {
      v11 = *((_QWORD *)this + 3);
      v12 = i++;
      v13 = *(_DWORD *)(v11 + 4 * v12);
      *(_DWORD *)(v11 + 4 * v12) = v9 | v13 & 0xFFFF0000;
    }
    *((_DWORD *)this + 8) = v4;
    v14 = 88LL * v4;
    if ( !is_mul_ok(v4, 0x58u) )
      v14 = -1;
    *((_QWORD *)this + 1) = operator new[](v14);
    v15 = operator new[](saturated_mul(v4, 4u));
    v16 = (void *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 2) = v15;
    memset_0(v16, 0, 88LL * v4);
    memset_0(*((void **)this + 2), 0, 4LL * v4);
    v17 = 0;
    v18 = 0;
    memset_0(pExceptionObject, 0, 0x58u);
    while ( NLG::TrieGetNextNode(a2, (const struct NLG::TRIECTRL *)pExceptionObject, v19) )
    {
      v17 += v18;
      Its = NLG::CCompressedTrieFirstLevelCache::GetIts(*((const int **)this + 3), pExceptionObject[0]);
      v21 = (__m128i)pExceptionObject[0];
      v22 = pExceptionObject[1];
      v23 = pExceptionObject[2];
      v24 = Its;
      v25 = *((_QWORD *)this + 1);
      v26 = 88 * v24;
      *(_OWORD *)(v26 + v25) = pExceptionObject[0];
      *(_OWORD *)(v26 + v25 + 16) = v22;
      v27 = pExceptionObject[3];
      *(_OWORD *)(v26 + v25 + 32) = v23;
      v28 = pExceptionObject[4];
      *(_OWORD *)(v26 + v25 + 48) = v27;
      *(_QWORD *)&v27 = v32;
      *(_OWORD *)(v26 + v25 + 64) = v28;
      *(_QWORD *)(v26 + v25 + 80) = v27;
      epi16 = _mm_extract_epi16(v21, 1);
      *(_DWORD *)(*((_QWORD *)this + 2) + 4 * v24) = v17;
      if ( (epi16 & 4) != 0 )
      {
        v30 = _mm_cvtsi128_si32(_mm_srli_si128(v21, 8));
      }
      else
      {
        v30 = NLG::CountWords(a2, (const struct NLG::TRIECTRL *)pExceptionObject, v19);
        epi16 = BYTE2(pExceptionObject[0]);
      }
      v18 = v30 + 1;
      if ( (epi16 & 1) == 0 )
        v18 = v30;
    }
    *(_BYTE *)this = 1;
  }
}

```

## disassembly

```asm
0x18006f710  mov     [rsp-8+arg_10], rbx
0x18006f715  push    rbp
0x18006f716  push    rsi
0x18006f717  push    rdi
0x18006f718  push    r12
0x18006f71a  push    r14
0x18006f71c  lea     rbp, [rsp-37h]
0x18006f721  sub     rsp, 90h
0x18006f728  mov     rax, cs:__security_cookie
0x18006f72f  xor     rax, rsp
0x18006f732  mov     [rbp+57h+var_30], rax
0x18006f736  cmp     byte ptr [rcx], 0
0x18006f739  mov     rsi, rdx
0x18006f73c  mov     rdi, rcx
0x18006f73f  jnz     loc_18006F946
0x18006f745  mov     rax, [rdx]
0x18006f748  cmp     dword ptr [rax+14h], 0
0x18006f74c  jz      loc_18006F946
0x18006f752  mov     dword ptr [rcx+24h], 1000h
0x18006f759  xor     ebx, ebx
0x18006f75b  mov     ecx, 4000h; unsigned __int64
0x18006f760  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f765  movsxd  r8, dword ptr [rdi+24h]
0x18006f769  xor     edx, edx; Val
0x18006f76b  shl     r8, 2; Size
0x18006f76f  mov     rcx, rax; void *
0x18006f772  mov     [rdi+18h], rax
0x18006f776  call    memset_0
0x18006f77b  lea     r12d, [rbx+58h]
0x18006f77f  xor     edx, edx; Val
0x18006f781  mov     r8d, r12d; Size
0x18006f784  lea     rcx, [rbp+57h+pExceptionObject]; void *
0x18006f788  call    memset_0
0x18006f78d  lea     rdx, [rbp+57h+pExceptionObject]; struct NLG::TRIECTRL *
0x18006f791  mov     rcx, rsi; this
0x18006f794  call    ?TrieGetNextNode@NLG@@YA_NPEBUTRIECTRL@1@PEAUTRIESCAN@1@@Z; NLG::TrieGetNextNode(NLG::TRIECTRL const *,NLG::TRIESCAN *)
0x18006f799  test    al, al
0x18006f79b  jz      short loc_18006F7FF
0x18006f79d  movzx   r9d, word ptr [rbp+57h+pExceptionObject]
0x18006f7a2  mov     eax, [rdi+24h]
0x18006f7a5  mov     ecx, r9d
0x18006f7a8  shr     ecx, 4
0x18006f7ab  dec     eax
0x18006f7ad  cmp     ecx, eax
0x18006f7af  jg      short loc_18006F7DC
0x18006f7b1  mov     rdx, [rdi+18h]
0x18006f7b5  xor     eax, eax
0x18006f7b7  test    ecx, ecx
0x18006f7b9  cmovs   ecx, eax
0x18006f7bc  and     r9d, 0Fh
0x18006f7c0  movsxd  r8, ecx
0x18006f7c3  mov     eax, 1Fh
0x18006f7c8  sub     eax, r9d
0x18006f7cb  mov     ecx, [rdx+r8*4]
0x18006f7cf  inc     ecx
0x18006f7d1  bts     ecx, eax
0x18006f7d4  mov     [rdx+r8*4], ecx
0x18006f7d8  inc     ebx
0x18006f7da  jmp     short loc_18006F78D
0x18006f7dc  mov     r8, [rbp+5Fh]; void *
0x18006f7e0  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18006f7e4  mov     edx, 216h; int
0x18006f7e9  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18006f7ee  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18006f7f5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006f7f9  call    _CxxThrowException_0
0x18006f7ff  xor     r10d, r10d
0x18006f802  xor     r9d, r9d
0x18006f805  cmp     [rdi+24h], r9d
0x18006f809  jle     short loc_18006F833
0x18006f80b  mov     rcx, [rdi+18h]
0x18006f80f  movsxd  r8, r9d
0x18006f812  inc     r9d
0x18006f815  mov     edx, [rcx+r8*4]
0x18006f819  mov     eax, edx
0x18006f81b  and     eax, 0FFFF0000h
0x18006f820  or      eax, r10d
0x18006f823  mov     [rcx+r8*4], eax
0x18006f827  movzx   eax, dx
0x18006f82a  add     r10d, eax
0x18006f82d  cmp     r9d, [rdi+24h]
0x18006f831  jl      short loc_18006F80B
0x18006f833  mov     [rdi+20h], ebx
0x18006f836  mov     rax, r12
0x18006f839  movsxd  rbx, ebx
0x18006f83c  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18006f843  mul     rbx
0x18006f846  cmovb   rax, r14
0x18006f84a  mov     rcx, rax; unsigned __int64
0x18006f84d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f852  mov     [rdi+8], rax
0x18006f856  lea     eax, [r14+5]
0x18006f85a  mul     rbx
0x18006f85d  cmovb   rax, r14
0x18006f861  mov     rcx, rax; unsigned __int64
0x18006f864  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f869  mov     rcx, [rdi+8]; void *
0x18006f86d  xor     edx, edx; Val
0x18006f86f  imul    r8, rbx, 58h ; 'X'; Size
0x18006f873  mov     [rdi+10h], rax
0x18006f877  call    memset_0
0x18006f87c  mov     rcx, [rdi+10h]; void *
0x18006f880  lea     r8, ds:0[rbx*4]; Size
0x18006f888  xor     edx, edx; Val
0x18006f88a  call    memset_0
0x18006f88f  mov     r8, r12; Size
0x18006f892  lea     rcx, [rbp+57h+pExceptionObject]; void *
0x18006f896  xor     edx, edx; Val
0x18006f898  xor     r14d, r14d
0x18006f89b  xor     ebx, ebx
0x18006f89d  call    memset_0
0x18006f8a2  jmp     loc_18006F92F
0x18006f8a7  movzx   edx, word ptr [rbp+57h+pExceptionObject]; unsigned __int16
0x18006f8ab  add     r14d, ebx
0x18006f8ae  mov     rcx, [rdi+18h]; int *
0x18006f8b2  call    ?GetIts@CCompressedTrieFirstLevelCache@NLG@@KAHPEBHG@Z; NLG::CCompressedTrieFirstLevelCache::GetIts(int const *,ushort)
0x18006f8b7  movaps  xmm2, [rbp+57h+pExceptionObject]
0x18006f8bb  movaps  xmm0, [rbp+57h+var_80]
0x18006f8bf  movaps  xmm1, [rbp+57h+var_70]
0x18006f8c3  movsxd  rdx, eax
0x18006f8c6  mov     rax, [rdi+8]
0x18006f8ca  imul    rcx, rdx, 58h ; 'X'
0x18006f8ce  movups  xmmword ptr [rcx+rax], xmm2
0x18006f8d2  movups  xmmword ptr [rcx+rax+10h], xmm0
0x18006f8d7  movaps  xmm0, [rbp+57h+var_60]
0x18006f8db  movups  xmmword ptr [rcx+rax+20h], xmm1
0x18006f8e0  movaps  xmm1, [rbp+57h+var_50]
0x18006f8e4  movups  xmmword ptr [rcx+rax+30h], xmm0
0x18006f8e9  movsd   xmm0, [rbp+57h+var_40]
0x18006f8ee  movups  xmmword ptr [rcx+rax+40h], xmm1
0x18006f8f3  movsd   qword ptr [rcx+rax+50h], xmm0
0x18006f8f9  mov     rax, [rdi+10h]
0x18006f8fd  pextrw  ecx, xmm2, 1
0x18006f902  mov     [rax+rdx*4], r14d
0x18006f906  test    cl, 4
0x18006f909  jz      short loc_18006F916
0x18006f90b  psrldq  xmm2, 8
0x18006f910  movd    eax, xmm2
0x18006f914  jmp     short loc_18006F926
0x18006f916  lea     rdx, [rbp+57h+pExceptionObject]; struct NLG::TRIECTRL *
0x18006f91a  mov     rcx, rsi; this
0x18006f91d  call    ?CountWords@NLG@@YAKPEBUTRIECTRL@1@PEAUTRIESCAN@1@@Z; NLG::CountWords(NLG::TRIECTRL const *,NLG::TRIESCAN *)
0x18006f922  movzx   ecx, word ptr [rbp+57h+pExceptionObject+2]
0x18006f926  test    cl, 1
0x18006f929  lea     ebx, [rax+1]
0x18006f92c  cmovz   ebx, eax
0x18006f92f  lea     rdx, [rbp+57h+pExceptionObject]; struct NLG::TRIECTRL *
0x18006f933  mov     rcx, rsi; this
0x18006f936  call    ?TrieGetNextNode@NLG@@YA_NPEBUTRIECTRL@1@PEAUTRIESCAN@1@@Z; NLG::TrieGetNextNode(NLG::TRIECTRL const *,NLG::TRIESCAN *)
0x18006f93b  test    al, al
0x18006f93d  jnz     loc_18006F8A7
0x18006f943  mov     byte ptr [rdi], 1
0x18006f946  mov     rcx, [rbp+57h+var_30]
0x18006f94a  xor     rcx, rsp; StackCookie
0x18006f94d  call    __security_check_cookie
0x18006f952  mov     rbx, [rsp+0B0h+arg_10]
0x18006f95a  add     rsp, 90h
0x18006f961  pop     r14
0x18006f963  pop     r12
0x18006f965  pop     rdi
0x18006f966  pop     rsi
0x18006f967  pop     rbp
0x18006f968  retn
```
