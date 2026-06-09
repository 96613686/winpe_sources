# _UnwindNestedFrames

- ea: `0x18004a834`
- end: `0x18004acb9`
- name: `_UnwindNestedFrames`
- size: `1157`
- prototype: ``
- caller_count: `8`
- callee_count: `9`
- tags: ``

## callers

- `0x1800455a0`
- `0x1800455e0`
- `0x180045620`
- `0x180045660`
- `0x1800456a0`
- `0x1800456e0`
- `0x180045720`
- `0x180049c20`

## callees

- `0x180037600`
- `0x180042ad0`
- `0x180045780`
- `0x18004a834`
- `0x18004acbc`
- `0x18004ad0c`
- `0x180078c4a`
- `0x180078e90`
- `0x180079024`

## pseudocode

```c
__int64 __fastcall UnwindNestedFrames(__int64 a1, __int64 a2, __int64 a3, char *a4, int *a5)
{
  __int64 v5; // r14
  const char *v6; // rdi
  unsigned int v8; // ecx
  int v9; // r10d
  int v10; // r9d
  __int64 result; // rax
  __int64 v12; // r12
  unsigned int v13; // r13d
  int v14; // eax
  unsigned __int64 v15; // rcx
  __int64 v16; // rdx
  _BYTE *v17; // rbx
  __int64 v18; // r15
  __int64 v19; // rax
  int v20; // r9d
  double v21; // xmm3_8
  __int64 v22; // rax
  _QWORD *v23; // rbx
  _QWORD *v24; // r14
  _QWORD *v25; // rax
  const char *v26; // rcx
  bool v27; // zf
  unsigned int v28; // eax
  int v29; // r8d
  double v30; // xmm0_8
  unsigned int v31; // eax
  int v32; // ecx
  double v33; // xmm0_8
  int v34; // ebx
  int v35; // ecx
  int v36; // eax
  unsigned int v37; // [rsp+60h] [rbp-A0h]
  unsigned int v38; // [rsp+64h] [rbp-9Ch]
  int v39; // [rsp+68h] [rbp-98h]
  int v41; // [rsp+78h] [rbp-88h]
  double v43; // [rsp+88h] [rbp-78h] BYREF
  int *v44; // [rsp+90h] [rbp-70h]
  _QWORD v45[64]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v46[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v47[256]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v5 = a1;
  v6 = a4;
  v8 = *(_DWORD *)(a3 + 20) & 0xFFFEFFFF;
  v9 = a2;
  v44 = a5;
  v37 = v8;
  if ( ((v8 - 7) & 0xFFFFFFF7) != 0 )
    goto LABEL_6;
  if ( (unsigned int)sub_18004ACBC(a4, "%d%*1[:/]%d%c") == 2 )
  {
    result = sub_18004AD0C(v5, a3, (_DWORD)a5, v10);
    if ( (int)result >= 0 )
    {
LABEL_4:
      _mm_lfence();
      return result;
    }
  }
  while ( 1 )
  {
    v8 = v37;
    v9 = a2;
LABEL_6:
    v12 = 0;
    v13 = 0;
    v39 = 0;
    if ( v8 == 1 )
    {
      if ( *v6 == 43 || *v6 == 45 )
      {
        v14 = *v6++;
        v39 = v14;
      }
      do
      {
        v15 = v6[v12];
        if ( (unsigned __int8)v15 <= 0x2Du )
        {
          v16 = 0x280000000001LL;
          if ( _bittest64(&v16, v15) )
            break;
        }
        v47[v12] = v15;
        ++v13;
        ++v12;
      }
      while ( v13 < 0xFF );
      if ( v13 >= 0x100 )
        sub_180079024(v15);
      v47[v12] = 0;
    }
    v17 = v47;
    v18 = 0;
    if ( !v13 )
      LODWORD(v17) = (_DWORD)v6;
    v41 = (int)v17;
    v19 = av_opt_find2(v9, (_DWORD)v17, *(_QWORD *)(a3 + 56), 0, (*(_DWORD *)(a3 + 48) >> 18) & 1, 0);
    if ( !v19 || *(_DWORD *)(v19 + 20) != 11 )
      break;
    v21 = (double)(int)*(_QWORD *)(v19 + 24);
    v43 = v21;
    if ( (*(_DWORD *)(v19 + 48) & 0x20000) == 0 )
      goto LABEL_50;
    av_log(v5, 24, "The \"%s\" option is deprecated: %s\n", *(const char **)v19, *(const char **)(v19 + 8));
LABEL_49:
    v21 = v43;
LABEL_50:
    if ( v37 == 1 )
    {
      v35 = *v44;
      if ( v39 == 43 )
      {
        v36 = v35 | (int)v21;
LABEL_55:
        v43 = (double)v36;
        goto LABEL_56;
      }
      if ( v39 == 45 )
      {
        v36 = v35 & ~(int)v21;
        goto LABEL_55;
      }
    }
LABEL_56:
    result = sub_18004AD0C(v5, a3, (_DWORD)v44, v20);
    if ( (int)result < 0 )
      goto LABEL_4;
    v6 += v12;
    if ( !v13 || !*v6 )
      return 0;
  }
  if ( !*(_QWORD *)(a3 + 56) )
  {
LABEL_43:
    v46[v18] = "default";
    v31 = *(_DWORD *)(a3 + 20);
    if ( v31 == 3 || v31 <= 0x14 && (v32 = 1051654, _bittest(&v32, v31)) )
      v33 = (double)(int)*(_QWORD *)(a3 + 24);
    else
      v33 = *(double *)(a3 + 24);
    *(double *)&v45[v18] = v33;
    v46[v18 + 1] = "max";
    v45[v18 + 1] = *(_QWORD *)(a3 + 40);
    v46[v18 + 2] = "min";
    v45[v18 + 2] = *(_QWORD *)(a3 + 32);
    v46[v18 + 3] = "none";
    v45[v18 + 3] = 0;
    v46[v18 + 4] = "all";
    v45[v18 + 4] = 0xBFF0000000000000uLL;
    v45[v18 + 5] = 0;
    v46[v18 + 5] = 0;
    v34 = av_expr_parse_and_eval(
            (unsigned int)&v43,
            (_DWORD)v17,
            (unsigned int)v46,
            (unsigned int)v45,
            0,
            0,
            0,
            0,
            0,
            0,
            v5);
    if ( v34 < 0 )
    {
      _mm_lfence();
      av_log(v5, 16, "Unable to parse option value \"%s\"\n", v6);
      return (unsigned int)v34;
    }
    goto LABEL_49;
  }
  v22 = a2;
  v23 = 0;
  v38 = 6;
  if ( !a2 )
  {
LABEL_42:
    LODWORD(v17) = v41;
    goto LABEL_43;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v23 )
      {
        v25 = v23 + 8;
        v23 = v25;
        if ( !*v25 || (v24 = v25) == 0 )
        {
LABEL_41:
          v5 = a1;
          goto LABEL_42;
        }
        v22 = a2;
      }
      else
      {
        if ( !*(_QWORD *)v22 )
          goto LABEL_41;
        v23 = *(_QWORD **)(*(_QWORD *)v22 + 16LL);
        if ( !v23 || !*v23 )
          goto LABEL_41;
        v24 = *(_QWORD **)(*(_QWORD *)v22 + 16LL);
      }
      if ( *((_DWORD *)v24 + 5) == 11 )
      {
        v26 = (const char *)v24[7];
        if ( v26 )
        {
          v27 = strcmp(v26, *(const char **)(a3 + 56)) == 0;
          v22 = a2;
          if ( v27 )
            break;
        }
      }
    }
    if ( v38 >= 0x40 )
      break;
    v46[v18] = *v24;
    v28 = *((_DWORD *)v24 + 5);
    if ( v28 == 3 || v28 <= 0x14 && (v29 = 1051654, _bittest(&v29, v28)) )
      v30 = (double)(int)v24[3];
    else
      v30 = *((double *)v24 + 3);
    v22 = a2;
    *(double *)&v45[v18++] = v30;
    ++v38;
  }
  av_log(a1, 16, "const_values array too small for %s\n", *(const char **)(a3 + 56));
  return 3131621040LL;
}

```

## disassembly

```asm
0x18004a834  push    rbp
0x18004a836  push    rbx
0x18004a837  push    rsi
0x18004a838  push    rdi
0x18004a839  push    r12
0x18004a83b  push    r13
0x18004a83d  push    r14
0x18004a83f  push    r15
0x18004a841  lea     rbp, [rsp-4B8h]
0x18004a849  sub     rsp, 5B8h
0x18004a850  mov     rax, cs:__security_cookie
0x18004a857  xor     rax, rsp
0x18004a85a  mov     [rbp+4F0h+var_50], rax
0x18004a861  mov     rbx, [rbp+4F0h+arg_20]
0x18004a868  mov     r14, rcx
0x18004a86b  mov     [rbp+4F0h+var_570], rcx
0x18004a86f  mov     rdi, r9
0x18004a872  mov     ecx, [r8+14h]
0x18004a876  mov     rsi, r8
0x18004a879  btr     ecx, 10h
0x18004a87d  mov     [rsp+5F0h+var_580], rdx
0x18004a882  mov     r10, rdx
0x18004a885  mov     [rbp+4F0h+var_560], rbx
0x18004a889  mov     [rsp+5F0h+var_590], ecx
0x18004a88d  lea     eax, [rcx-7]
0x18004a890  test    eax, 0FFFFFFF7h
0x18004a895  jnz     short loc_18004A8FC
0x18004a897  lea     rax, [rsp+5F0h+var_584]
0x18004a89c  mov     rcx, rdi; Buffer
0x18004a89f  lea     r9, [rsp+5F0h+var_58C]
0x18004a8a4  mov     [rsp+5F0h+var_5D0], rax
0x18004a8a9  lea     r8, [rsp+5F0h+var_588]
0x18004a8ae  lea     rdx, aD1DC
0x18004a8b5  call    sub_18004ACBC
0x18004a8ba  cmp     eax, 2
0x18004a8bd  jnz     short loc_18004A8F3
0x18004a8bf  movsxd  rax, [rsp+5F0h+var_588]
0x18004a8c4  mov     r8, rbx
0x18004a8c7  movsd   xmm3, cs:Y
0x18004a8cf  mov     rdx, rsi
0x18004a8d2  mov     [rsp+5F0h+var_5C8], rax
0x18004a8d7  mov     rcx, r14
0x18004a8da  mov     eax, [rsp+5F0h+var_58C]
0x18004a8de  mov     dword ptr [rsp+5F0h+var_5D0], eax
0x18004a8e2  call    sub_18004AD0C
0x18004a8e7  test    eax, eax
0x18004a8e9  js      short loc_18004A8F3
0x18004a8eb  lfence
0x18004a8ee  jmp     loc_18004AC90
0x18004a8f3  mov     ecx, [rsp+5F0h+var_590]
0x18004a8f7  mov     r10, [rsp+5F0h+var_580]
0x18004a8fc  xor     r12d, r12d
0x18004a8ff  xor     r13d, r13d
0x18004a902  mov     [rsp+5F0h+var_588], r12d
0x18004a907  cmp     ecx, 1
0x18004a90a  jnz     short loc_18004A967
0x18004a90c  cmp     byte ptr [rdi], 2Bh ; '+'
0x18004a90f  jz      short loc_18004A916
0x18004a911  cmp     byte ptr [rdi], 2Dh ; '-'
0x18004a914  jnz     short loc_18004A920
0x18004a916  movsx   eax, byte ptr [rdi]
0x18004a919  inc     rdi
0x18004a91c  mov     [rsp+5F0h+var_588], eax
0x18004a920  movsx   rcx, byte ptr [rdi+r12]
0x18004a925  cmp     cl, 2Dh ; '-'
0x18004a928  ja      short loc_18004A93A
0x18004a92a  mov     rdx, 280000000001h
0x18004a934  bt      rdx, rcx
0x18004a938  jb      short loc_18004A951
0x18004a93a  mov     [rbp+r12+4F0h+var_150], cl
0x18004a942  inc     r13d
0x18004a945  inc     r12
0x18004a948  cmp     r13d, 0FFh
0x18004a94f  jb      short loc_18004A920
0x18004a951  cmp     r13d, 100h
0x18004a958  jnb     loc_18004ACB3
0x18004a95e  mov     [rbp+r12+4F0h+var_150], 0
0x18004a967  mov     eax, [rsi+30h]
0x18004a96a  lea     rbx, [rbp+4F0h+var_150]
0x18004a971  mov     r8, [rsi+38h]
0x18004a975  xor     r15d, r15d
0x18004a978  test    r13d, r13d
0x18004a97b  mov     [rsp+5F0h+var_5C8], r15
0x18004a980  mov     rcx, r10
0x18004a983  cmovz   rbx, rdi
0x18004a987  shr     eax, 12h
0x18004a98a  and     eax, 1
0x18004a98d  mov     [rsp+5F0h+var_578], rbx
0x18004a992  xor     r9d, r9d
0x18004a995  mov     dword ptr [rsp+5F0h+var_5D0], eax
0x18004a999  mov     rdx, rbx
0x18004a99c  call    av_opt_find2
0x18004a9a1  xor     edx, edx
0x18004a9a3  test    rax, rax
0x18004a9a6  jz      short loc_18004A9ED
0x18004a9a8  cmp     dword ptr [rax+14h], 0Bh
0x18004a9ac  jnz     short loc_18004A9ED
0x18004a9ae  xorps   xmm3, xmm3
0x18004a9b1  cvtsi2sd xmm3, qword ptr [rax+18h]
0x18004a9b7  movsd   [rbp+4F0h+var_568], xmm3
0x18004a9bc  test    dword ptr [rax+30h], 20000h
0x18004a9c3  jz      loc_18004ABDB
0x18004a9c9  mov     rcx, [rax+8]
0x18004a9cd  lea     r8, aTheSOptionIsDe
0x18004a9d4  mov     r9, [rax]
0x18004a9d7  lea     edx, [r15+18h]
0x18004a9db  mov     [rsp+5F0h+var_5D0], rcx
0x18004a9e0  mov     rcx, r14
0x18004a9e3  call    av_log
0x18004a9e8  jmp     loc_18004ABD6
0x18004a9ed  cmp     [rsi+38h], rdx
0x18004a9f1  jz      loc_18004AAE7
0x18004a9f7  mov     rax, [rsp+5F0h+var_580]
0x18004a9fc  mov     rbx, rdx
0x18004a9ff  mov     [rsp+5F0h+var_58C], 6
0x18004aa07  test    rax, rax
0x18004aa0a  jz      loc_18004AAE2
0x18004aa10  test    rbx, rbx
0x18004aa13  jnz     short loc_18004AA3C
0x18004aa15  mov     rbx, [rax]
0x18004aa18  test    rbx, rbx
0x18004aa1b  jz      loc_18004AADE
0x18004aa21  mov     rbx, [rbx+10h]
0x18004aa25  test    rbx, rbx
0x18004aa28  jz      loc_18004AADE
0x18004aa2e  cmp     [rbx], rdx
0x18004aa31  jz      loc_18004AADE
0x18004aa37  mov     r14, rbx
0x18004aa3a  jmp     short loc_18004AA5D
0x18004aa3c  lea     rax, [rbx+40h]
0x18004aa40  mov     rbx, rax
0x18004aa43  cmp     [rax], rdx
0x18004aa46  jz      loc_18004AADE
0x18004aa4c  mov     r14, rax
0x18004aa4f  test    rax, rax
0x18004aa52  jz      loc_18004AADE
0x18004aa58  mov     rax, [rsp+5F0h+var_580]
0x18004aa5d  cmp     dword ptr [r14+14h], 0Bh
0x18004aa62  jnz     short loc_18004AA10
0x18004aa64  mov     rcx, [r14+38h]; Str1
0x18004aa68  test    rcx, rcx
0x18004aa6b  jz      short loc_18004AA10
0x18004aa6d  mov     rdx, [rsi+38h]; Str2
0x18004aa71  call    strcmp
0x18004aa76  xor     edx, edx
0x18004aa78  test    eax, eax
0x18004aa7a  mov     rax, [rsp+5F0h+var_580]
0x18004aa7f  jnz     short loc_18004AA10
0x18004aa81  mov     ecx, [rsp+5F0h+var_58C]
0x18004aa85  cmp     ecx, 40h ; '@'
0x18004aa88  jnb     loc_18004AC54
0x18004aa8e  mov     rax, [r14]
0x18004aa91  mov     [rbp+r15*8+4F0h+var_350], rax
0x18004aa99  mov     eax, [r14+14h]
0x18004aa9d  cmp     eax, 3
0x18004aaa0  jz      short loc_18004AABB
0x18004aaa2  cmp     eax, 14h
0x18004aaa5  ja      short loc_18004AAB3
0x18004aaa7  mov     r8d, 100C06h
0x18004aaad  bt      r8d, eax
0x18004aab1  jb      short loc_18004AABB
0x18004aab3  movsd   xmm0, qword ptr [r14+18h]
0x18004aab9  jmp     short loc_18004AAC4
0x18004aabb  xorps   xmm0, xmm0
0x18004aabe  cvtsi2sd xmm0, qword ptr [r14+18h]
0x18004aac4  mov     rax, [rsp+5F0h+var_580]
0x18004aac9  inc     ecx
0x18004aacb  movsd   [rbp+r15*8+4F0h+var_550], xmm0
0x18004aad2  inc     r15
0x18004aad5  mov     [rsp+5F0h+var_58C], ecx
0x18004aad9  jmp     loc_18004AA10
0x18004aade  mov     r14, [rbp+4F0h+var_570]
0x18004aae2  mov     rbx, [rsp+5F0h+var_578]
0x18004aae7  lea     rax, aDefault_0
0x18004aaee  mov     [rbp+r15*8+4F0h+var_350], rax
0x18004aaf6  mov     eax, [rsi+14h]
0x18004aaf9  cmp     eax, 3
0x18004aafc  jz      short loc_18004AB14
0x18004aafe  cmp     eax, 14h
0x18004ab01  ja      short loc_18004AB0D
0x18004ab03  mov     ecx, 100C06h
0x18004ab08  bt      ecx, eax
0x18004ab0b  jb      short loc_18004AB14
0x18004ab0d  movsd   xmm0, qword ptr [rsi+18h]
0x18004ab12  jmp     short loc_18004AB1D
0x18004ab14  xorps   xmm0, xmm0
0x18004ab17  cvtsi2sd xmm0, qword ptr [rsi+18h]
0x18004ab1d  movsd   [rbp+r15*8+4F0h+var_550], xmm0
0x18004ab24  lea     rax, aMax
0x18004ab2b  mov     [rbp+r15*8+4F0h+var_348], rax
0x18004ab33  lea     r9, [rbp+4F0h+var_550]
0x18004ab37  mov     rax, [rsi+28h]
0x18004ab3b  lea     r8, [rbp+4F0h+var_350]
0x18004ab42  mov     [rbp+r15*8+4F0h+var_548], rax
0x18004ab47  lea     rcx, [rbp+4F0h+var_568]
0x18004ab4b  mov     [rsp+5F0h+var_5A0], r14
0x18004ab50  lea     rax, aMin
0x18004ab57  mov     [rbp+r15*8+4F0h+var_340], rax
0x18004ab5f  mov     rax, [rsi+20h]
0x18004ab63  mov     [rbp+r15*8+4F0h+var_540], rax
0x18004ab68  lea     rax, aNone
0x18004ab6f  mov     [rsp+5F0h+var_5A8], edx
0x18004ab73  mov     [rsp+5F0h+var_5B0], rdx
0x18004ab78  mov     [rbp+r15*8+4F0h+var_338], rax
0x18004ab80  lea     rax, aAll
0x18004ab87  mov     [rsp+5F0h+var_5B8], rdx
0x18004ab8c  mov     [rbp+r15*8+4F0h+var_538], rdx
0x18004ab91  mov     [rsp+5F0h+var_5C0], rdx
0x18004ab96  mov     [rbp+r15*8+4F0h+var_330], rax
0x18004ab9e  mov     rax, 0BFF0000000000000h
0x18004aba8  mov     [rsp+5F0h+var_5C8], rdx
0x18004abad  mov     [rbp+r15*8+4F0h+var_530], rax
0x18004abb2  mov     [rbp+r15*8+4F0h+var_528], rdx
0x18004abb7  mov     [rbp+r15*8+4F0h+var_328], rdx
0x18004abbf  mov     [rsp+5F0h+var_5D0], rdx
0x18004abc4  mov     rdx, rbx
0x18004abc7  call    av_expr_parse_and_eval
0x18004abcc  mov     ebx, eax
0x18004abce  test    eax, eax
0x18004abd0  js      loc_18004AC74
0x18004abd6  movsd   xmm3, [rbp+4F0h+var_568]
0x18004abdb  cmp     [rsp+5F0h+var_590], 1
0x18004abe0  mov     rbx, [rbp+4F0h+var_560]
0x18004abe4  jnz     short loc_18004AC18
0x18004abe6  mov     eax, [rsp+5F0h+var_588]
0x18004abea  mov     ecx, [rbx]
0x18004abec  cmp     eax, 2Bh ; '+'
0x18004abef  jnz     short loc_18004ABFB
0x18004abf1  cvttsd2si rax, xmm3
0x18004abf6  or      rax, rcx
0x18004abf9  jmp     short loc_18004AC0B
0x18004abfb  cmp     eax, 2Dh ; '-'
0x18004abfe  jnz     short loc_18004AC18
0x18004ac00  cvttsd2si rax, xmm3
0x18004ac05  not     rax
0x18004ac08  and     rax, rcx
0x18004ac0b  xorps   xmm3, xmm3
0x18004ac0e  cvtsi2sd xmm3, rax
0x18004ac13  movsd   [rbp+4F0h+var_568], xmm3
0x18004ac18  mov     [rsp+5F0h+var_5C8], 1
0x18004ac21  mov     r8, rbx
0x18004ac24  mov     rdx, rsi
0x18004ac27  mov     dword ptr [rsp+5F0h+var_5D0], 1
0x18004ac2f  mov     rcx, r14
0x18004ac32  call    sub_18004AD0C
0x18004ac37  test    eax, eax
0x18004ac39  js      loc_18004A8EB
0x18004ac3f  add     rdi, r12
0x18004ac42  test    r13d, r13d
0x18004ac45  jz      short loc_18004AC50
0x18004ac47  cmp     byte ptr [rdi], 0
0x18004ac4a  jnz     loc_18004A8F3
0x18004ac50  xor     eax, eax
0x18004ac52  jmp     short loc_18004AC90
0x18004ac54  mov     r9, [rsi+38h]
0x18004ac58  lea     r8, aConstValuesArr
0x18004ac5f  mov     rcx, [rbp+4F0h+var_570]
0x18004ac63  mov     edx, 10h
0x18004ac68  call    av_log
0x18004ac6d  mov     eax, 0BAA8BEB0h
0x18004ac72  jmp     short loc_18004AC90
0x18004ac74  lfence
0x18004ac77  mov     r9, rdi
0x18004ac7a  lea     r8, aUnableToParseO_6
0x18004ac81  mov     edx, 10h
0x18004ac86  mov     rcx, r14
0x18004ac89  call    av_log
0x18004ac8e  mov     eax, ebx
0x18004ac90  mov     rcx, [rbp+4F0h+var_50]
0x18004ac97  xor     rcx, rsp; StackCookie
0x18004ac9a  call    __security_check_cookie
0x18004ac9f  add     rsp, 5B8h
0x18004aca6  pop     r15
0x18004aca8  pop     r14
0x18004acaa  pop     r13
0x18004acac  pop     r12
0x18004acae  pop     rdi
0x18004acaf  pop     rsi
0x18004acb0  pop     rbx
0x18004acb1  pop     rbp
0x18004acb2  retn
0x18004acb3  call    sub_180079024
```
