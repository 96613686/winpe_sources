# ComputeDeterminantExactSign(double,double,double,double,double *)

- ea: `0x100447050`
- end: `0x10044723f`
- name: `?ComputeDeterminantExactSign@@YA?AW4SIGNINDICATOR@RobustIntersections@@NNNNPEAN@Z`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1004473b0`

## callees

- `0x10042a400`
- `0x10042a4e0`
- `0x10042a7a0`
- `0x100447050`
- `0x10044b4a0`
- `0x100468a30`

## pseudocode

```c
__int64 __fastcall ComputeDeterminantExactSign(double a1, double a2, double a3, double a4, double *a5)
{
  double v5; // xmm5_8
  double v6; // xmm6_8
  unsigned int v7; // ebx
  int v8; // edi
  unsigned int v9; // r9d
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rcx
  double v13; // xmm1_8
  double v14; // xmm2_8
  int *v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  __int64 result; // rax
  __int64 v19; // [rsp+24h] [rbp-95h] BYREF
  int v20; // [rsp+2Ch] [rbp-8Dh]
  __int64 v21; // [rsp+30h] [rbp-89h]
  int v22; // [rsp+38h] [rbp-81h]
  char v23; // [rsp+3Ch] [rbp-7Dh] BYREF
  unsigned int v24; // [rsp+50h] [rbp-69h] BYREF
  int v25; // [rsp+54h] [rbp-65h]
  __int64 v26; // [rsp+58h] [rbp-61h]
  _BYTE v27[40]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v28[40]; // [rsp+A0h] [rbp-19h] BYREF

  v5 = a1 * a4;
  v6 = a2 * a3;
  *a5 = a1 * a4 - a2 * a3;
  if ( a1 * a4 != a2 * a3 || COERCE_DOUBLE(*(_QWORD *)&v5 & _xmm) <= 9.007199254740992e15 )
  {
    if ( v5 <= v6 )
      return (unsigned int)(v6 <= v5) - 1;
    else
      return 1;
  }
  _mm_lfence();
  RobustIntersections::CZ<128>::CZ<128>((char *)&v19 + 4);
  RobustIntersections::CZ<128>::CZ<128>(&v24);
  RobustIntersections::CZ<128>::CZ<128>(v28);
  RobustIntersections::CZ<128>::CZ<128>(v27);
  RobustIntersections::CZ<128>::Multiply((char *)&v19 + 4, v27);
  RobustIntersections::CZ<128>::Multiply(&v24, v28);
  v7 = 0;
  v8 = v25;
  if ( v20 <= v25 )
  {
    if ( v20 >= v25 )
    {
      if ( v20 <= 0 )
      {
        if ( v20 >= 0 )
          goto LABEL_12;
        v9 = HIDWORD(v19);
        v10 = v21;
        v11 = v24;
        v12 = v26;
      }
      else
      {
        v9 = v24;
        v10 = v26;
        v11 = HIDWORD(v19);
        v12 = v21;
      }
      v7 = RobustIntersections::EaCompare(v12, v11, v10, v9);
      goto LABEL_12;
    }
    v7 = -1;
  }
  else
  {
    v7 = 1;
  }
LABEL_12:
  v25 = -v8;
  RobustIntersections::CZ<128>::Add((char *)&v19 + 4, &v24);
  v13 = DOUBLE_1_0;
  v14 = (double)v22;
  if ( HIDWORD(v19) > 1 )
  {
    v15 = (int *)&v23;
    v16 = (unsigned int)(HIDWORD(v19) - 1);
    do
    {
      v17 = *v15;
      v13 = v13 * 4294967296.0;
      ++v15;
      v14 = v14 + (double)v17 * v13;
      --v16;
    }
    while ( v16 );
  }
  result = v7;
  *a5 = (double)v20 * v14;
  return result;
}

```

## disassembly

```asm
0x100447050  mov     r11, rsp
0x100447053  mov     [r11+10h], rbx
0x100447057  mov     [r11+18h], rsi
0x10044705b  push    rbp
0x10044705c  lea     rbp, [r11-57h]
0x100447060  sub     rsp, 100h
0x100447067  movaps  xmmword ptr [r11-18h], xmm6
0x10044706c  movaps  xmmword ptr [r11-28h], xmm7
0x100447071  movaps  xmmword ptr [r11-38h], xmm8
0x100447076  mov     rax, cs:__security_cookie
0x10044707d  xor     rax, rsp
0x100447080  mov     [rbp+4Fh+var_40], rax
0x100447084  mov     rsi, [rbp+4Fh+arg_20]
0x100447088  movaps  xmm5, xmm0
0x10044708b  mulsd   xmm5, xmm3
0x10044708f  movaps  xmm6, xmm1
0x100447092  mulsd   xmm6, xmm2
0x100447096  movaps  xmm7, xmm1
0x100447099  movaps  xmm8, xmm0
0x10044709d  movaps  xmm4, xmm5
0x1004470a0  ucomisd xmm5, xmm6
0x1004470a4  subsd   xmm4, xmm6
0x1004470a8  movsd   qword ptr [rsi], xmm4
0x1004470ac  jp      loc_1004471F6
0x1004470b2  jnz     loc_1004471F6
0x1004470b8  movsd   xmm0, cs:__real@4340000000000000
0x1004470c0  movaps  xmm1, xmm5
0x1004470c3  andps   xmm1, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1004470ca  comisd  xmm0, xmm1
0x1004470ce  jnb     loc_1004471F6
0x1004470d4  mov     [r11+8], rdi
0x1004470d8  lfence
0x1004470db  movaps  xmm1, xmm8
0x1004470df  lea     rcx, [rsp+100h+var_E4+4]
0x1004470e4  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x1004470e9  movaps  xmm1, xmm7
0x1004470ec  lea     rcx, [rbp+4Fh+var_B8]
0x1004470f0  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x1004470f5  movaps  xmm1, xmm2
0x1004470f8  lea     rcx, [rbp+4Fh+var_68]
0x1004470fc  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x100447101  movaps  xmm1, xmm3
0x100447104  lea     rcx, [rbp+4Fh+var_90]
0x100447108  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x10044710d  lea     rdx, [rbp+4Fh+var_90]
0x100447111  lea     rcx, [rsp+100h+var_E4+4]
0x100447116  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044711b  lea     rdx, [rbp+4Fh+var_68]
0x10044711f  lea     rcx, [rbp+4Fh+var_B8]
0x100447123  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100447128  mov     rax, [rsp+24h]
0x10044712d  xor     ebx, ebx
0x10044712f  mov     edi, [rbp+4Fh+var_B4]
0x100447132  cmp     eax, edi
0x100447134  jle     short loc_10044713D
0x100447136  mov     ebx, 1
0x10044713b  jmp     short loc_100447177
0x10044713d  jge     short loc_100447146
0x10044713f  mov     ebx, 0FFFFFFFFh
0x100447144  jmp     short loc_100447177
0x100447146  test    eax, eax
0x100447148  jle     short loc_10044715D
0x10044714a  mov     r9d, [rbp+4Fh+var_B8]
0x10044714e  mov     r8, [rbp+4Fh+var_B0]
0x100447152  mov     edx, dword ptr [rsp+100h+var_E4+4]
0x100447156  mov     rcx, [rsp+100h+var_D8]
0x10044715b  jmp     short loc_100447170
0x10044715d  jns     short loc_100447177
0x10044715f  mov     r9d, dword ptr [rsp+100h+var_E4+4]
0x100447164  mov     r8, [rsp+100h+var_D8]
0x100447169  mov     edx, [rbp+4Fh+var_B8]
0x10044716c  mov     rcx, [rbp+4Fh+var_B0]
0x100447170  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100447175  mov     ebx, eax
0x100447177  neg     edi
0x100447179  lea     rdx, [rbp+4Fh+var_B8]
0x10044717d  lea     rcx, [rsp+100h+var_E4+4]
0x100447182  mov     [rbp+4Fh+var_B4], edi
0x100447185  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x10044718a  mov     eax, [rsp+100h+var_D0]
0x10044718e  xorps   xmm2, xmm2
0x100447191  movsd   xmm1, cs:__real@3ff0000000000000
0x100447199  mov     rdi, [rsp+100h+arg_0]
0x1004471a1  cvtsi2sd xmm2, rax
0x1004471a6  mov     eax, dword ptr [rsp+100h+var_E4+4]
0x1004471aa  cmp     eax, 1
0x1004471ad  jbe     short loc_1004471E0
0x1004471af  movsd   xmm3, cs:__real@41f0000000000000
0x1004471b7  lea     rcx, [rbp+4Fh+var_CC]
0x1004471bb  lea     edx, [rax-1]
0x1004471be  xchg    ax, ax
0x1004471c0  mov     eax, [rcx]
0x1004471c2  xorps   xmm0, xmm0
0x1004471c5  mulsd   xmm1, xmm3
0x1004471c9  add     rcx, 4
0x1004471cd  cvtsi2sd xmm0, rax
0x1004471d2  mulsd   xmm0, xmm1
0x1004471d6  addsd   xmm2, xmm0
0x1004471da  sub     rdx, 1
0x1004471de  jnz     short loc_1004471C0
0x1004471e0  movd    xmm0, [rsp+100h+var_DC]
0x1004471e6  mov     eax, ebx
0x1004471e8  cvtdq2pd xmm0, xmm0
0x1004471ec  mulsd   xmm0, xmm2
0x1004471f0  movsd   qword ptr [rsi], xmm0
0x1004471f4  jmp     short loc_10044720F
0x1004471f6  comisd  xmm5, xmm6
0x1004471fa  jbe     short loc_100447203
0x1004471fc  mov     eax, 1
0x100447201  jmp     short loc_10044720F
0x100447203  xor     ebx, ebx
0x100447205  comisd  xmm6, xmm5
0x100447209  setbe   bl
0x10044720c  lea     eax, [rbx-1]
0x10044720f  mov     rcx, [rbp+4Fh+var_40]
0x100447213  xor     rcx, rsp; StackCookie
0x100447216  call    __security_check_cookie
0x10044721b  lea     r11, [rsp+100h+var_s0]
0x100447223  mov     rbx, [r11+18h]
0x100447227  mov     rsi, [r11+20h]
0x10044722b  movaps  xmm6, xmmword ptr [r11-10h]
0x100447230  movaps  xmm7, xmmword ptr [r11-20h]
0x100447235  movaps  xmm8, xmmword ptr [r11-30h]
0x10044723a  mov     rsp, r11
0x10044723d  pop     rbp
0x10044723e  retn
```
