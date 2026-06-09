# RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPointUsingExactArithmetic(RobustIntersections::CLineSegmentIntersection const &,double const * const,bool)

- ea: `0x100449c10`
- end: `0x100449f3d`
- name: `?YXSortTransverseIntersectionAndPointUsingExactArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@QEBN_N@Z`
- size: `813`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x100448310`

## callees

- `0x10042a4e0`
- `0x10042a7a0`
- `0x100449c10`
- `0x10044b4a0`
- `0x10044b820`
- `0x100468a30`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPointUsingExactArithmetic(
        __int64 a1,
        double *a2,
        char a3)
{
  unsigned int v6; // edi
  unsigned int v7; // ecx
  __int64 result; // rax
  unsigned int v9; // r9d
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  double v14; // xmm1_8
  unsigned __int64 v15; // rcx
  double v16; // xmm1_8
  unsigned __int64 v17; // rcx
  unsigned int v18; // r9d
  __int64 v19; // r8
  unsigned int v20; // edx
  __int64 v21; // rcx
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh]
  __int128 *v24; // [rsp+28h] [rbp-D8h]
  __int128 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h]
  int v27; // [rsp+48h] [rbp-B8h]
  unsigned int v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+54h] [rbp-ACh]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  _BYTE v31[4]; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+84h] [rbp-7Ch]
  _BYTE v33[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v34; // [rsp+B4h] [rbp-4Ch]
  _BYTE v35[4]; // [rsp+E0h] [rbp-20h] BYREF
  int v36; // [rsp+E4h] [rbp-1Ch]
  _BYTE v37[48]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v38[48]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v39[48]; // [rsp+170h] [rbp+70h] BYREF

  RobustIntersections::CZ<192>::CZ<192>(v35);
  RobustIntersections::CZ<192>::CZ<192>(v31);
  RobustIntersections::CZ<192>::CZ<192>(v39);
  RobustIntersections::CZ<192>::CZ<192>(v38);
  RobustIntersections::CZ<192>::CZ<192>(v37);
  RobustIntersections::CZ<192>::CZ<192>(v33);
  RobustIntersections::CZ<128>::Multiply(v35, v38);
  RobustIntersections::CZ<128>::Multiply(v31, v39);
  v32 = -v32;
  RobustIntersections::CZ<128>::Add(v35, v31);
  v32 = -v32;
  RobustIntersections::CZ<128>::Multiply(v37, v38);
  RobustIntersections::CZ<128>::Multiply(v33, v39);
  v34 = -v34;
  RobustIntersections::CZ<128>::Add(v37, v33);
  v34 = -v34;
  v6 = 0;
  if ( a3 )
    goto LABEL_16;
  RobustIntersections::CZ<192>::CZ<192>(&v22);
  RobustIntersections::CZ<192>::CZ<192>(&v28);
  RobustIntersections::CZ<128>::Multiply(&v22, v35);
  RobustIntersections::CZ<128>::Multiply(&v28, v37);
  v7 = 0;
  if ( v29 > v23 )
  {
    v7 = 1;
    result = 1;
    goto LABEL_12;
  }
  if ( v29 < v23 )
  {
    v7 = -1;
    result = 0xFFFFFFFFLL;
    goto LABEL_12;
  }
  if ( v29 <= 0 )
  {
    if ( v29 >= 0 )
      goto LABEL_11;
    v9 = v28;
    v10 = v30;
    v11 = v22;
    v12 = (__int64)v24;
  }
  else
  {
    v9 = v22;
    v10 = (__int64)v24;
    v11 = v28;
    v12 = v30;
  }
  v7 = RobustIntersections::EaCompare(v12, v11, v10, v9);
LABEL_11:
  result = v7;
  if ( !v7 )
    goto LABEL_16;
LABEL_12:
  if ( v36 != 1 )
  {
    result = 0xFFFFFFFFLL;
    if ( v7 == -1 )
      result = 1;
  }
  if ( (result & 0x7FFFFFFF) == 0 )
  {
LABEL_16:
    v13 = 0;
    v14 = *a2 - *(double *)(a1 + 48);
    v22 = 7;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    if ( v14 <= 0.0 )
    {
      if ( v14 >= 0.0 )
      {
        v23 = 0;
      }
      else
      {
        *(_QWORD *)&v16 = *(_QWORD *)&v14 ^ _xmm;
        v17 = 0;
        if ( v16 >= 9.223372036854776e18 )
        {
          v16 = v16 - 9.223372036854776e18;
          if ( v16 < 9.223372036854776e18 )
            v17 = 0x8000000000000000uLL;
        }
        v23 = -1;
        v13 = v17 + (unsigned int)(int)v16;
      }
    }
    else
    {
      v15 = 0;
      if ( v14 >= 9.223372036854776e18 )
      {
        v14 = v14 - 9.223372036854776e18;
        if ( v14 < 9.223372036854776e18 )
          v15 = 0x8000000000000000uLL;
      }
      v23 = 1;
      v13 = v15 + (unsigned int)(int)v14;
    }
    *(_QWORD *)&v25 = v13;
    v24 = &v25;
    RobustIntersections::CZ<192>::CZ<192>(&v28);
    RobustIntersections::CZ<128>::Multiply(&v22, v35);
    RobustIntersections::CZ<128>::Multiply(&v28, v37);
    if ( v36 == 1 )
    {
      if ( v29 <= v23 )
      {
        if ( v29 >= v23 )
        {
          if ( v29 <= 0 )
          {
            if ( v29 < 0 )
            {
LABEL_32:
              v18 = v28;
              v19 = v30;
              v20 = v22;
              v21 = (__int64)v24;
              return (unsigned int)RobustIntersections::EaCompare(v21, v20, v19, v18);
            }
            return v6;
          }
          goto LABEL_39;
        }
        return (unsigned int)-1;
      }
    }
    else if ( v23 <= v29 )
    {
      if ( v23 >= v29 )
      {
        if ( v23 > 0 )
          goto LABEL_32;
        if ( v23 >= 0 )
          return v6;
LABEL_39:
        v21 = v30;
        v20 = v28;
        v19 = (__int64)v24;
        v18 = v22;
        return (unsigned int)RobustIntersections::EaCompare(v21, v20, v19, v18);
      }
      return (unsigned int)-1;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x100449c10  mov     [rsp-8+arg_0], rbx
0x100449c15  mov     [rsp-8+arg_8], rsi
0x100449c1a  mov     [rsp-8+arg_10], rdi
0x100449c1f  push    rbp
0x100449c20  push    r14
0x100449c22  push    r15
0x100449c24  lea     rbp, [rsp-0B0h]
0x100449c2c  sub     rsp, 1B0h
0x100449c33  mov     rax, cs:__security_cookie
0x100449c3a  xor     rax, rsp
0x100449c3d  mov     [rbp+0C0h+var_20], rax
0x100449c44  movsd   xmm1, qword ptr [rcx]
0x100449c48  mov     rsi, rcx
0x100449c4b  lea     rcx, [rbp+0C0h+var_E0]
0x100449c4f  movzx   ebx, r8b
0x100449c53  mov     r14, rdx
0x100449c56  call    ??0?$CZ@$0MA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<192>::CZ<192>(double)
0x100449c5b  movsd   xmm1, qword ptr [rsi+8]
0x100449c60  lea     rcx, [rbp+0C0h+var_140]
0x100449c64  call    ??0?$CZ@$0MA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<192>::CZ<192>(double)
0x100449c69  movsd   xmm1, qword ptr [rsi+10h]
0x100449c6e  lea     rcx, [rbp+0C0h+var_50]
0x100449c72  call    ??0?$CZ@$0MA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<192>::CZ<192>(double)
0x100449c77  movsd   xmm1, qword ptr [rsi+18h]
0x100449c7c  lea     rcx, [rbp+0C0h+var_80]
0x100449c80  call    ??0?$CZ@$0MA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<192>::CZ<192>(double)
0x100449c85  movsd   xmm1, qword ptr [rsi+20h]
0x100449c8a  lea     rcx, [rbp+0C0h+var_B0]
0x100449c8e  call    ??0?$CZ@$0MA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<192>::CZ<192>(double)
0x100449c93  movsd   xmm1, qword ptr [rsi+28h]
0x100449c98  lea     rcx, [rbp+0C0h+var_110]
0x100449c9c  call    ??0?$CZ@$0MA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<192>::CZ<192>(double)
0x100449ca1  lea     rdx, [rbp+0C0h+var_80]
0x100449ca5  lea     rcx, [rbp+0C0h+var_E0]
0x100449ca9  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449cae  lea     rdx, [rbp+0C0h+var_50]
0x100449cb2  lea     rcx, [rbp+0C0h+var_140]
0x100449cb6  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449cbb  neg     [rbp+0C0h+var_13C]
0x100449cbe  lea     rdx, [rbp+0C0h+var_140]
0x100449cc2  lea     rcx, [rbp+0C0h+var_E0]
0x100449cc6  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x100449ccb  neg     [rbp+0C0h+var_13C]
0x100449cce  lea     rdx, [rbp+0C0h+var_80]
0x100449cd2  lea     rcx, [rbp+0C0h+var_B0]
0x100449cd6  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449cdb  lea     rdx, [rbp+0C0h+var_50]
0x100449cdf  lea     rcx, [rbp+0C0h+var_110]
0x100449ce3  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449ce8  neg     [rbp+0C0h+var_10C]
0x100449ceb  lea     rdx, [rbp+0C0h+var_110]
0x100449cef  lea     rcx, [rbp+0C0h+var_B0]
0x100449cf3  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x100449cf8  neg     [rbp+0C0h+var_10C]
0x100449cfb  xor     edi, edi
0x100449cfd  lea     r15d, [rdi+1]
0x100449d01  test    bl, bl
0x100449d03  jnz     loc_100449DBF
0x100449d09  movsd   xmm1, qword ptr [r14+8]
0x100449d0f  lea     rcx, [rsp+1C0h+var_1A0]
0x100449d14  subsd   xmm1, qword ptr [rsi+38h]
0x100449d19  call    ??0?$CZ@$0MA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<192>::CZ<192>(double)
0x100449d1e  movsd   xmm1, qword ptr [rsi+8]
0x100449d23  lea     rcx, [rsp+1C0h+var_170]
0x100449d28  call    ??0?$CZ@$0MA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<192>::CZ<192>(double)
0x100449d2d  lea     rdx, [rbp+0C0h+var_E0]
0x100449d31  lea     rcx, [rsp+1C0h+var_1A0]
0x100449d36  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449d3b  lea     rdx, [rbp+0C0h+var_B0]
0x100449d3f  lea     rcx, [rsp+1C0h+var_170]
0x100449d44  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449d49  mov     eax, [rsp+1C0h+var_16C]
0x100449d4d  mov     ecx, edi
0x100449d4f  cmp     eax, [rsp+1C0h+var_19C]
0x100449d53  jle     short loc_100449D5D
0x100449d55  mov     ecx, r15d
0x100449d58  mov     eax, r15d
0x100449d5b  jmp     short loc_100449DA3
0x100449d5d  jge     short loc_100449D68
0x100449d5f  mov     ecx, 0FFFFFFFFh
0x100449d64  mov     eax, ecx
0x100449d66  jmp     short loc_100449DA3
0x100449d68  test    eax, eax
0x100449d6a  jle     short loc_100449D81
0x100449d6c  mov     r9d, [rsp+1C0h+var_1A0]
0x100449d71  mov     r8, [rsp+1C0h+var_198]
0x100449d76  mov     edx, [rsp+1C0h+var_170]
0x100449d7a  mov     rcx, [rsp+1C0h+var_168]
0x100449d7f  jmp     short loc_100449D96
0x100449d81  jns     short loc_100449D9D
0x100449d83  mov     r9d, [rsp+1C0h+var_170]
0x100449d88  mov     r8, [rsp+1C0h+var_168]
0x100449d8d  mov     edx, [rsp+1C0h+var_1A0]
0x100449d91  mov     rcx, [rsp+1C0h+var_198]
0x100449d96  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100449d9b  mov     ecx, eax
0x100449d9d  mov     eax, ecx
0x100449d9f  test    ecx, ecx
0x100449da1  jz      short loc_100449DBF
0x100449da3  cmp     [rbp+0C0h+var_DC], r15d
0x100449da7  jz      short loc_100449DB4
0x100449da9  mov     eax, 0FFFFFFFFh
0x100449dae  cmp     ecx, eax
0x100449db0  cmovz   eax, r15d
0x100449db4  test    eax, 7FFFFFFFh
0x100449db9  jnz     loc_100449F11
0x100449dbf  movsd   xmm1, qword ptr [r14]
0x100449dc4  xor     eax, eax
0x100449dc6  subsd   xmm1, qword ptr [rsi+30h]
0x100449dcb  xorps   xmm0, xmm0
0x100449dce  mov     [rsp+1C0h+var_1A0], 7
0x100449dd6  movups  [rsp+1C0h+var_190], xmm0
0x100449ddb  mov     [rsp+1C0h+var_180], rax
0x100449de0  mov     [rsp+1C0h+var_178], eax
0x100449de4  comisd  xmm1, xmm0
0x100449de8  jbe     short loc_100449E20
0x100449dea  movsd   xmm0, cs:__real@43e0000000000000
0x100449df2  xor     ecx, ecx
0x100449df4  comisd  xmm1, xmm0
0x100449df8  jb      short loc_100449E11
0x100449dfa  subsd   xmm1, xmm0
0x100449dfe  comisd  xmm1, xmm0
0x100449e02  jnb     short loc_100449E11
0x100449e04  mov     rax, 8000000000000000h
0x100449e0e  mov     rcx, rax
0x100449e11  cvttsd2si rax, xmm1
0x100449e16  mov     [rsp+1C0h+var_19C], r15d
0x100449e1b  add     rax, rcx
0x100449e1e  jmp     short loc_100449E6A
0x100449e20  comisd  xmm0, xmm1
0x100449e24  jbe     short loc_100449E66
0x100449e26  xorps   xmm1, cs:__xmm@80000000000000008000000000000000
0x100449e2d  xor     ecx, ecx
0x100449e2f  movsd   xmm0, cs:__real@43e0000000000000
0x100449e37  comisd  xmm1, xmm0
0x100449e3b  jb      short loc_100449E54
0x100449e3d  subsd   xmm1, xmm0
0x100449e41  comisd  xmm1, xmm0
0x100449e45  jnb     short loc_100449E54
0x100449e47  mov     rax, 8000000000000000h
0x100449e51  mov     rcx, rax
0x100449e54  cvttsd2si rax, xmm1
0x100449e59  mov     [rsp+1C0h+var_19C], 0FFFFFFFFh
0x100449e61  add     rax, rcx
0x100449e64  jmp     short loc_100449E6A
0x100449e66  mov     [rsp+1C0h+var_19C], edi
0x100449e6a  movsd   xmm1, qword ptr [rsi]
0x100449e6e  lea     rcx, [rsp+1C0h+var_170]
0x100449e73  mov     dword ptr [rsp+1C0h+var_190], eax
0x100449e77  shr     rax, 20h
0x100449e7b  mov     dword ptr [rsp+1C0h+var_190+4], eax
0x100449e7f  lea     rax, [rsp+1C0h+var_190]
0x100449e84  mov     [rsp+1C0h+var_198], rax
0x100449e89  call    ??0?$CZ@$0MA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<192>::CZ<192>(double)
0x100449e8e  lea     rdx, [rbp+0C0h+var_E0]
0x100449e92  lea     rcx, [rsp+1C0h+var_1A0]
0x100449e97  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449e9c  lea     rdx, [rbp+0C0h+var_B0]
0x100449ea0  lea     rcx, [rsp+1C0h+var_170]
0x100449ea5  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449eaa  cmp     [rbp+0C0h+var_DC], r15d
0x100449eae  jnz     short loc_100449ED7
0x100449eb0  mov     eax, [rsp+1C0h+var_16C]
0x100449eb4  cmp     eax, [rsp+1C0h+var_19C]
0x100449eb8  jg      short loc_100449EE1
0x100449eba  jl      short loc_100449EE8
0x100449ebc  test    eax, eax
0x100449ebe  jg      short loc_100449EF5
0x100449ec0  jns     short loc_100449F0F
0x100449ec2  mov     r9d, [rsp+1C0h+var_170]
0x100449ec7  mov     r8, [rsp+1C0h+var_168]
0x100449ecc  mov     edx, [rsp+1C0h+var_1A0]
0x100449ed0  mov     rcx, [rsp+1C0h+var_198]
0x100449ed5  jmp     short loc_100449F08
0x100449ed7  mov     eax, [rsp+1C0h+var_19C]
0x100449edb  cmp     eax, [rsp+1C0h+var_16C]
0x100449edf  jle     short loc_100449EE6
0x100449ee1  mov     edi, r15d
0x100449ee4  jmp     short loc_100449F0F
0x100449ee6  jge     short loc_100449EEF
0x100449ee8  mov     edi, 0FFFFFFFFh
0x100449eed  jmp     short loc_100449F0F
0x100449eef  test    eax, eax
0x100449ef1  jg      short loc_100449EC2
0x100449ef3  jns     short loc_100449F0F
0x100449ef5  mov     rcx, [rsp+1C0h+var_168]
0x100449efa  mov     edx, [rsp+1C0h+var_170]
0x100449efe  mov     r8, [rsp+1C0h+var_198]
0x100449f03  mov     r9d, [rsp+1C0h+var_1A0]
0x100449f08  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100449f0d  mov     edi, eax
0x100449f0f  mov     eax, edi
0x100449f11  mov     rcx, [rbp+0C0h+var_20]
0x100449f18  xor     rcx, rsp; StackCookie
0x100449f1b  call    __security_check_cookie
0x100449f20  lea     r11, [rsp+1C0h+var_10]
0x100449f28  mov     rbx, [r11+20h]
0x100449f2c  mov     rsi, [r11+28h]
0x100449f30  mov     rdi, [r11+30h]
0x100449f34  mov     rsp, r11
0x100449f37  pop     r15
0x100449f39  pop     r14
0x100449f3b  pop     rbp
0x100449f3c  retn
```
