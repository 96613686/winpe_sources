# RtlCombineNtPathSegments

- ea: `0x180023c40`
- end: `0x180023fe5`
- name: `RtlCombineNtPathSegments`
- size: `933`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800177f8`

## callees

- `0x180008140`
- `0x18000f130`
- `0x18000fafc`
- `0x180010794`
- `0x180023c40`
- `0x180024598`
- `0x180031bf8`

## string_xrefs

- `0x180023c71`: `onecore\base\lstring\path.cpp`
- `0x180023cda`: `onecore\base\lstring\path.cpp`
- `0x180023ed9`: `onecore\base\lstring\path.cpp`
- `0x180023f1a`: `onecore\base\lstring\path.cpp`
- `0x180023cf8`: `Not-null check failed: PathOut`
- `0x180023c84`: `RtlCombineNtPathSegments`
- `0x180023ced`: `RtlCombineNtPathSegments`
- `0x180023ef3`: `RtlCombineNtPathSegments`
- `0x180023f34`: `RtlCombineNtPathSegments`
- `0x180023c8f`: `(PathSegmentCount == 0) || (PathSegments != 0)`
- `0x180023f49`: `BytesLeft >= BytesToCopy`

## pseudocode

```c
__int64 __fastcall RtlCombineNtPathSegments(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r15
  const char *v5; // rax
  __int64 result; // rax
  unsigned __int64 v7; // rdi
  unsigned __int64 i; // rbx
  unsigned __int64 *v9; // rcx
  unsigned __int64 v10; // rsi
  __int64 v11; // rsi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rsi
  __int64 v14; // rbx
  __int128 v15; // xmm6
  _WORD *v16; // r14
  int v17; // ebx
  unsigned __int64 v18; // rax
  _WORD *v19; // rdi
  unsigned __int64 *v20; // rax
  unsigned __int64 v21; // r15
  int v22; // r13d
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // r15
  __int64 v25; // rcx
  __int64 v26; // xmm1_8
  char v27; // [rsp+20h] [rbp-60h]
  char v28; // [rsp+21h] [rbp-5Fh]
  __int128 v29; // [rsp+28h] [rbp-58h] BYREF
  __int64 v30; // [rsp+38h] [rbp-48h]
  const char *v31; // [rsp+40h] [rbp-40h]
  unsigned __int64 v32; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v34; // [rsp+58h] [rbp-28h]
  unsigned __int64 *v35; // [rsp+60h] [rbp-20h]
  __int64 v36; // [rsp+68h] [rbp-18h]

  v36 = a2;
  v4 = a2;
  if ( !a2 )
  {
    v30 = 602;
    *(_QWORD *)&v29 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v29 + 1) = "RtlCombineNtPathSegments";
    v5 = "(PathSegmentCount == 0) || (PathSegments != 0)";
LABEL_3:
    v31 = v5;
    RtlReportErrorOrigination(&v29, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a3 )
  {
    v30 = 603;
    *(_QWORD *)&v29 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v29 + 1) = "RtlCombineNtPathSegments";
    v5 = "Not-null check failed: PathOut";
    goto LABEL_3;
  }
  v7 = 0;
  for ( i = 0; i < 2; ++i )
  {
    while ( 1 )
    {
      v33 = 0;
      v9 = (unsigned __int64 *)(v4 + 24 * i);
      v32 = 0;
      v10 = *v9;
      result = RtlTrimNtPathSegment(v9, &v33, &v32);
      if ( (int)result < 0 )
        return result;
      if ( v33 > v10 || v32 > v10 - v33 )
        goto LABEL_58;
      v11 = v10 - v32 - (v33 & -(__int64)(i != 0));
      if ( !v11 )
        goto LABEL_15;
      v12 = v11 + v7;
      if ( v11 + v7 < v7 )
        return 3221225621LL;
      if ( i )
        break;
      v7 += v11;
      i = 1;
    }
    v7 = v12 + 2;
    if ( v12 + 2 < v12 )
      return 3221225621LL;
LABEL_15:
    ;
  }
  v13 = *(_QWORD *)(a3 + 8);
  v14 = 0;
  v30 = 0;
  v15 = 0;
  v29 = 0;
  if ( v7 <= v13 )
  {
    v16 = *(_WORD **)(a3 + 16);
    v28 = 0;
LABEL_25:
    v18 = 0;
    v27 = 1;
    v34 = 0;
    v19 = v16;
    while ( 1 )
    {
      v33 = 0;
      v20 = (unsigned __int64 *)(v4 + 24 * v18);
      v32 = 0;
      v21 = *v20;
      v35 = v20;
      if ( v21 )
      {
        v22 = RtlTrimNtPathSegment(v20, &v33, &v32);
        if ( v22 < 0 )
        {
          if ( v14 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v14);
          return (unsigned int)v22;
        }
        v23 = v33;
        if ( v33 > v21 || v32 > v21 - v33 )
          goto LABEL_58;
        if ( v27 )
        {
          v23 = 0;
        }
        else if ( v33 >= 2 )
        {
          v23 = v33 - 2;
        }
        else if ( v19 == v16 || *(v19 - 1) != 92 )
        {
          if ( v13 < 2 )
          {
            v30 = 694;
            *(_QWORD *)&v29 = "onecore\\base\\lstring\\path.cpp";
            *((_QWORD *)&v29 + 1) = "RtlCombineNtPathSegments";
            v31 = "BytesLeft >= sizeof(WCHAR)";
            RtlReportErrorOrigination(&v29, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225507LL);
LABEL_44:
            if ( v14 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v14);
            return 3221225507LL;
          }
          *v19++ = 92;
          v13 -= 2LL;
        }
        v24 = *v35 - v32 - v23;
        if ( v13 < v24 )
        {
          v30 = 708;
          *(_QWORD *)&v29 = "onecore\\base\\lstring\\path.cpp";
          *((_QWORD *)&v29 + 1) = "RtlCombineNtPathSegments";
          v31 = "BytesLeft >= BytesToCopy";
          RtlReportErrorOrigination(&v29, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225507LL);
          if ( v14 )
            goto LABEL_44;
          return 3221225507LL;
        }
        memcpy_0(v19, (const void *)(v23 + v35[2]), *v35 - v32 - v23);
        v19 = (_WORD *)((char *)v19 + v24);
        v27 = 0;
        v13 -= v24;
      }
      v18 = v34 + 1;
      v34 = v18;
      if ( v18 >= 2 )
      {
        if ( v28 )
        {
          v25 = *(_QWORD *)(a3 + 16);
          v26 = v30;
          v30 = 0;
          *(_OWORD *)a3 = v15;
          *(_QWORD *)(a3 + 16) = v26;
          if ( v25 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v25);
          v14 = v30;
        }
        if ( v19 >= v16 )
        {
          *(_QWORD *)a3 = (char *)v19 - (char *)v16;
          if ( v14 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v14);
          return 0;
        }
LABEL_58:
        INTERNAL_ERROR_ACTION(-1073741595);
      }
      v4 = v36;
    }
  }
  v17 = RtlAllocateLUnicodeString(v7, &v29);
  if ( v17 >= 0 )
  {
    v14 = v30;
    v13 = *((_QWORD *)&v29 + 1);
    v16 = (_WORD *)v30;
    v15 = v29;
    v28 = 1;
    goto LABEL_25;
  }
  if ( v30 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v30);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180023c40  mov     [rsp-38h+arg_0], rbx
0x180023c45  push    rbp
0x180023c46  push    rsi
0x180023c47  push    rdi
0x180023c48  push    r12
0x180023c4a  push    r13
0x180023c4c  push    r14
0x180023c4e  push    r15
0x180023c50  mov     rbp, rsp
0x180023c53  sub     rsp, 80h
0x180023c5a  xor     r13d, r13d
0x180023c5d  movaps  [rsp+80h+var_10], xmm6
0x180023c62  mov     [rbp+var_18], rdx
0x180023c66  mov     r12, r8
0x180023c69  mov     r15, rdx
0x180023c6c  test    rdx, rdx
0x180023c6f  jnz     short loc_180023CD5
0x180023c71  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180023c78  mov     [rbp+var_48], 25Ah
0x180023c80  mov     qword ptr [rbp+var_58], rax
0x180023c84  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180023c8b  mov     qword ptr [rbp+var_58+8], rax
0x180023c8f  lea     rax, aPathsegmentcou; "(PathSegmentCount == 0) || (PathSegment"...
0x180023c96  mov     r8d, 0C000000Dh
0x180023c9c  mov     [rbp+var_40], rax
0x180023ca0  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180023ca7  lea     rcx, [rbp+var_58]
0x180023cab  call    RtlReportErrorOrigination
0x180023cb0  mov     eax, 0C000000Dh
0x180023cb5  mov     rbx, [rsp+80h+arg_0]
0x180023cbd  movaps  xmm6, [rsp+80h+var_10]
0x180023cc2  add     rsp, 80h
0x180023cc9  pop     r15
0x180023ccb  pop     r14
0x180023ccd  pop     r13
0x180023ccf  pop     r12
0x180023cd1  pop     rdi
0x180023cd2  pop     rsi
0x180023cd3  pop     rbp
0x180023cd4  retn
0x180023cd5  test    r12, r12
0x180023cd8  jnz     short loc_180023D01
0x180023cda  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180023ce1  mov     [rbp+var_48], 25Bh
0x180023ce9  mov     qword ptr [rbp+var_58], rax
0x180023ced  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180023cf4  mov     qword ptr [rbp+var_58+8], rax
0x180023cf8  lea     rax, aNotNullCheckFa_0; "Not-null check failed: PathOut"
0x180023cff  jmp     short loc_180023C96
0x180023d01  mov     rdi, r13
0x180023d04  mov     rbx, r13
0x180023d07  lea     rax, [rbx+rbx*2]
0x180023d0b  mov     [rbp+var_30], r13
0x180023d0f  lea     rcx, [r15+rax*8]
0x180023d13  mov     [rbp+var_38], r13
0x180023d17  mov     rsi, [rcx]
0x180023d1a  lea     r8, [rbp+var_38]
0x180023d1e  lea     rdx, [rbp+var_30]
0x180023d22  call    RtlTrimNtPathSegment
0x180023d27  test    eax, eax
0x180023d29  js      short loc_180023CB5
0x180023d2b  mov     rdx, [rbp+var_30]
0x180023d2f  cmp     rdx, rsi
0x180023d32  ja      loc_180023FDA
0x180023d38  mov     rax, rsi
0x180023d3b  sub     rax, rdx
0x180023d3e  cmp     [rbp+var_38], rax
0x180023d42  ja      loc_180023FDA
0x180023d48  mov     rax, rbx
0x180023d4b  neg     rax
0x180023d4e  sbb     rcx, rcx
0x180023d51  sub     rsi, [rbp+var_38]
0x180023d55  and     rcx, rdx
0x180023d58  sub     rsi, rcx
0x180023d5b  jz      short loc_180023D74
0x180023d5d  lea     rax, [rsi+rdi]
0x180023d61  cmp     rax, rdi
0x180023d64  jb      short loc_180023DAA
0x180023d66  test    rbx, rbx
0x180023d69  jz      short loc_180023D9F
0x180023d6b  lea     rdi, [rax+2]
0x180023d6f  cmp     rdi, rax
0x180023d72  jb      short loc_180023DAA
0x180023d74  inc     rbx
0x180023d77  cmp     rbx, 2
0x180023d7b  jb      short loc_180023D07
0x180023d7d  mov     rsi, [r12+8]
0x180023d82  xor     ebx, ebx
0x180023d84  mov     [rbp+var_48], rbx
0x180023d88  xorps   xmm6, xmm6
0x180023d8b  movups  [rbp+var_58], xmm6
0x180023d8f  cmp     rdi, rsi
0x180023d92  ja      short loc_180023DB4
0x180023d94  mov     r14, [r12+10h]
0x180023d99  mov     [rbp+var_5F], r13b
0x180023d9d  jmp     short loc_180023DEE
0x180023d9f  mov     rdi, rax
0x180023da2  inc     rbx
0x180023da5  jmp     loc_180023D07
0x180023daa  mov     eax, 0C0000095h
0x180023daf  jmp     loc_180023CB5
0x180023db4  lea     rdx, [rbp+var_58]
0x180023db8  mov     rcx, rdi
0x180023dbb  call    RtlAllocateLUnicodeString
0x180023dc0  mov     ebx, eax
0x180023dc2  test    eax, eax
0x180023dc4  jns     short loc_180023DDB
0x180023dc6  mov     rcx, [rbp+var_48]
0x180023dca  test    rcx, rcx
0x180023dcd  jz      short loc_180023DD4
0x180023dcf  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180023dd4  mov     eax, ebx
0x180023dd6  jmp     loc_180023CB5
0x180023ddb  mov     rbx, [rbp+var_48]
0x180023ddf  mov     rsi, qword ptr [rbp+var_58+8]
0x180023de3  mov     r14, rbx
0x180023de6  movups  xmm6, [rbp+var_58]
0x180023dea  mov     [rbp+var_5F], 1
0x180023dee  mov     rax, r13
0x180023df1  mov     [rbp+var_60], 1
0x180023df5  mov     [rbp+var_28], rax
0x180023df9  mov     rdi, r14
0x180023dfc  lea     rax, [rax+rax*2]
0x180023e00  mov     [rbp+var_30], r13
0x180023e04  lea     rax, [r15+rax*8]
0x180023e08  mov     [rbp+var_38], r13
0x180023e0c  mov     r15, [rax]
0x180023e0f  mov     [rbp+var_20], rax
0x180023e13  test    r15, r15
0x180023e16  jz      loc_180023EBB
0x180023e1c  lea     r8, [rbp+var_38]
0x180023e20  mov     rcx, rax
0x180023e23  lea     rdx, [rbp+var_30]
0x180023e27  call    RtlTrimNtPathSegment
0x180023e2c  mov     r13d, eax
0x180023e2f  test    eax, eax
0x180023e31  js      loc_180023F75
0x180023e37  mov     rcx, [rbp+var_30]
0x180023e3b  cmp     rcx, r15
0x180023e3e  ja      loc_180023FDA
0x180023e44  sub     r15, rcx
0x180023e47  cmp     [rbp+var_38], r15
0x180023e4b  ja      loc_180023FDA
0x180023e51  xor     r13d, r13d
0x180023e54  cmp     [rbp+var_60], r13b
0x180023e58  jz      short loc_180023E5F
0x180023e5a  mov     ecx, r13d
0x180023e5d  jmp     short loc_180023E8C
0x180023e5f  cmp     rcx, 2
0x180023e63  jnb     short loc_180023E88
0x180023e65  mov     eax, 5Ch ; '\'
0x180023e6a  cmp     rdi, r14
0x180023e6d  jz      short loc_180023E75
0x180023e6f  cmp     [rdi-2], ax
0x180023e73  jz      short loc_180023E8C
0x180023e75  cmp     rsi, 2
0x180023e79  jb      short loc_180023ED9
0x180023e7b  mov     [rdi], ax
0x180023e7e  add     rdi, 2
0x180023e82  sub     rsi, 2
0x180023e86  jmp     short loc_180023E8C
0x180023e88  sub     rcx, 2
0x180023e8c  mov     rax, [rbp+var_20]
0x180023e90  mov     r15, [rax]
0x180023e93  sub     r15, [rbp+var_38]
0x180023e97  sub     r15, rcx
0x180023e9a  cmp     rsi, r15
0x180023e9d  jb      short loc_180023F1A
0x180023e9f  mov     rdx, [rax+10h]
0x180023ea3  mov     r8, r15; Size
0x180023ea6  add     rdx, rcx; Src
0x180023ea9  mov     rcx, rdi; void *
0x180023eac  call    memcpy_0
0x180023eb1  add     rdi, r15
0x180023eb4  mov     [rbp+var_60], r13b
0x180023eb8  sub     rsi, r15
0x180023ebb  mov     rax, [rbp+var_28]
0x180023ebf  inc     rax
0x180023ec2  mov     [rbp+var_28], rax
0x180023ec6  cmp     rax, 2
0x180023eca  jnb     loc_180023F8A
0x180023ed0  mov     r15, [rbp+var_18]
0x180023ed4  jmp     loc_180023DFC
0x180023ed9  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180023ee0  mov     [rbp+var_48], 2B6h
0x180023ee8  mov     qword ptr [rbp+var_58], rax
0x180023eec  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180023ef3  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180023efa  mov     r8d, 0C0000023h
0x180023f00  mov     qword ptr [rbp+var_58+8], rax
0x180023f04  lea     rcx, [rbp+var_58]
0x180023f08  lea     rax, aBytesleftSizeo; "BytesLeft >= sizeof(WCHAR)"
0x180023f0f  mov     [rbp+var_40], rax
0x180023f13  call    RtlReportErrorOrigination
0x180023f18  jmp     short loc_180023F5E
0x180023f1a  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180023f21  mov     [rbp+var_48], 2C4h
0x180023f29  mov     qword ptr [rbp+var_58], rax
0x180023f2d  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180023f34  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180023f3b  mov     r8d, 0C0000023h
0x180023f41  mov     qword ptr [rbp+var_58+8], rax
0x180023f45  lea     rcx, [rbp+var_58]
0x180023f49  lea     rax, aBytesleftBytes; "BytesLeft >= BytesToCopy"
0x180023f50  mov     [rbp+var_40], rax
0x180023f54  call    RtlReportErrorOrigination
0x180023f59  test    rbx, rbx
0x180023f5c  jz      short loc_180023F6B
0x180023f5e  test    rbx, rbx
0x180023f61  jz      short loc_180023F6B
0x180023f63  mov     rcx, rbx
0x180023f66  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180023f6b  mov     eax, 0C0000023h
0x180023f70  jmp     loc_180023CB5
0x180023f75  test    rbx, rbx
0x180023f78  jz      short loc_180023F82
0x180023f7a  mov     rcx, rbx
0x180023f7d  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180023f82  mov     eax, r13d
0x180023f85  jmp     loc_180023CB5
0x180023f8a  cmp     [rbp+var_5F], r13b
0x180023f8e  jz      short loc_180023FBA
0x180023f90  mov     rcx, [r12+10h]
0x180023f95  xor     eax, eax
0x180023f97  movsd   xmm1, [rbp+var_48]
0x180023f9c  mov     [rbp+var_48], rax
0x180023fa0  movups  xmmword ptr [r12], xmm6
0x180023fa5  movsd   qword ptr [r12+10h], xmm1
0x180023fac  test    rcx, rcx
0x180023faf  jz      short loc_180023FB6
0x180023fb1  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180023fb6  mov     rbx, [rbp+var_48]
0x180023fba  cmp     rdi, r14
0x180023fbd  jb      short loc_180023FDA
0x180023fbf  sub     rdi, r14
0x180023fc2  mov     [r12], rdi
0x180023fc6  test    rbx, rbx
0x180023fc9  jz      short loc_180023FD3
0x180023fcb  mov     rcx, rbx
0x180023fce  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180023fd3  xor     eax, eax
0x180023fd5  jmp     loc_180023CB5
0x180023fda  mov     ecx, 0C00000E5h; int
0x180023fdf  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
