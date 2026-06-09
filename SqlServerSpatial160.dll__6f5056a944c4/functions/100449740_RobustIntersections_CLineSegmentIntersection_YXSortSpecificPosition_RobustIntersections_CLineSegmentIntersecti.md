# RobustIntersections::CLineSegmentIntersection::YXSortSpecificPosition(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)

- ea: `0x100449740`
- end: `0x100449998`
- name: `?YXSortSpecificPosition@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@0@Z`
- size: `600`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100448160`

## callees

- `0x100448310`
- `0x100449740`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::YXSortSpecificPosition(__int64 a1, __int64 a2)
{
  unsigned int v3; // edx
  __int64 v4; // r8
  double v5; // xmm3_8
  double v6; // xmm0_8
  int v7; // ecx
  double v8; // xmm4_8
  double v9; // xmm1_8
  double v10; // xmm2_8
  int v11; // ecx
  __int64 v12; // r8
  double v13; // xmm0_8
  double v14; // xmm1_8
  __int128 v16; // [rsp+20h] [rbp-68h] BYREF

  v3 = 0x80000000;
  if ( *(_DWORD *)(a1 + 88) == 2 && *(_DWORD *)(a2 + 88) == 2 )
  {
    v4 = *(unsigned int *)(a1 + 92);
    if ( (_DWORD)v4 )
    {
      if ( (_DWORD)v4 == 2 )
      {
        v5 = *(double *)(a1 + 48) + *(double *)a1;
        v6 = *(double *)(a1 + 56) + *(double *)(a1 + 8);
      }
      else
      {
        v4 = *(unsigned int *)(a1 + 96);
        if ( (_DWORD)v4 )
        {
          if ( (_DWORD)v4 != 2 )
          {
            v12 = *(unsigned int *)(a2 + 92);
            if ( (_DWORD)v12 )
            {
              if ( (_DWORD)v12 == 2 )
              {
                v13 = *(double *)(a2 + 48) + *(double *)a2;
                v14 = *(double *)(a2 + 56) + *(double *)(a2 + 8);
              }
              else
              {
                v12 = *(unsigned int *)(a2 + 96);
                if ( (_DWORD)v12 )
                {
                  if ( (_DWORD)v12 != 2 )
                    return v3;
                  v13 = *(double *)(a2 + 48) + *(double *)(a2 + 32) - *(double *)(a2 + 16);
                  v14 = *(double *)(a2 + 56) + *(double *)(a2 + 40) - *(double *)(a2 + 24);
                }
                else
                {
                  v13 = *(double *)(a2 + 48) + *(double *)(a2 + 32);
                  v14 = *(double *)(a2 + 56) + *(double *)(a2 + 40);
                }
              }
              *(double *)&v16 = v13;
              *((double *)&v16 + 1) = v14;
            }
            else
            {
              v16 = *(_OWORD *)(a2 + 48);
            }
            return (unsigned int)RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPoint(
                                   a1,
                                   (double *)&v16,
                                   v12);
          }
          v5 = *(double *)(a1 + 48) + *(double *)(a1 + 32) - *(double *)(a1 + 16);
          v6 = *(double *)(a1 + 56) + *(double *)(a1 + 40) - *(double *)(a1 + 24);
        }
        else
        {
          v5 = *(double *)(a1 + 48) + *(double *)(a1 + 32);
          v6 = *(double *)(a1 + 56) + *(double *)(a1 + 40);
        }
      }
    }
    else
    {
      v5 = *(double *)(a1 + 48);
      v6 = *(double *)(a1 + 56);
    }
    v7 = *(_DWORD *)(a2 + 92);
    *((double *)&v16 + 1) = v6;
    *(double *)&v16 = v5;
    v8 = v6;
    if ( v7 )
    {
      if ( v7 == 2 )
      {
        v8 = v6;
        v9 = *(double *)(a2 + 48) + *(double *)a2;
        v10 = *(double *)(a2 + 56) + *(double *)(a2 + 8);
      }
      else
      {
        v11 = *(_DWORD *)(a2 + 96);
        if ( v11 )
        {
          if ( v11 != 2 )
            return (unsigned int)-(int)RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPoint(
                                         a2,
                                         (double *)&v16,
                                         v4);
          v8 = v6;
          v9 = *(double *)(a2 + 48) + *(double *)(a2 + 32) - *(double *)(a2 + 16);
          v10 = *(double *)(a2 + 56) + *(double *)(a2 + 40) - *(double *)(a2 + 24);
        }
        else
        {
          v8 = v6;
          v9 = *(double *)(a2 + 48) + *(double *)(a2 + 32);
          v10 = *(double *)(a2 + 56) + *(double *)(a2 + 40);
        }
      }
    }
    else
    {
      v9 = *(double *)(a2 + 48);
      v10 = *(double *)(a2 + 56);
    }
    if ( v6 <= v10 )
    {
      if ( v10 > v8 )
        return (unsigned int)-1;
      if ( v5 <= v9 )
        return (unsigned int)(v9 <= v5) - 1;
    }
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x100449740  sub     rsp, 88h
0x100449747  cmp     dword ptr [rcx+58h], 2
0x10044974b  mov     rax, rdx
0x10044974e  mov     edx, 80000000h
0x100449753  jnz     loc_10044998E
0x100449759  cmp     dword ptr [rax+58h], 2
0x10044975d  jnz     loc_10044998E
0x100449763  mov     r8d, [rcx+5Ch]
0x100449767  movaps  [rsp+88h+var_18], xmm6
0x10044976c  movaps  [rsp+88h+var_28], xmm7
0x100449771  movaps  [rsp+88h+var_38], xmm8
0x100449777  movaps  [rsp+88h+var_48], xmm9
0x10044977d  movaps  [rsp+88h+var_58], xmm10
0x100449783  test    r8d, r8d
0x100449786  jnz     short loc_100449794
0x100449788  movsd   xmm3, qword ptr [rcx+30h]
0x10044978d  movsd   xmm0, qword ptr [rcx+38h]
0x100449792  jmp     short loc_1004497F6
0x100449794  cmp     r8d, 2
0x100449798  jnz     short loc_1004497AF
0x10044979a  movsd   xmm3, qword ptr [rcx+30h]
0x10044979f  movsd   xmm0, qword ptr [rcx+38h]
0x1004497a4  addsd   xmm3, qword ptr [rcx]
0x1004497a8  addsd   xmm0, qword ptr [rcx+8]
0x1004497ad  jmp     short loc_1004497F6
0x1004497af  mov     r8d, [rcx+60h]
0x1004497b3  test    r8d, r8d
0x1004497b6  jnz     short loc_1004497CE
0x1004497b8  movsd   xmm3, qword ptr [rcx+30h]
0x1004497bd  movsd   xmm0, qword ptr [rcx+38h]
0x1004497c2  addsd   xmm3, qword ptr [rcx+20h]
0x1004497c7  addsd   xmm0, qword ptr [rcx+28h]
0x1004497cc  jmp     short loc_1004497F6
0x1004497ce  cmp     r8d, 2
0x1004497d2  jnz     loc_1004498E8
0x1004497d8  movsd   xmm3, qword ptr [rcx+30h]
0x1004497dd  movsd   xmm0, qword ptr [rcx+38h]
0x1004497e2  addsd   xmm3, qword ptr [rcx+20h]
0x1004497e7  addsd   xmm0, qword ptr [rcx+28h]
0x1004497ec  subsd   xmm3, qword ptr [rcx+10h]
0x1004497f1  subsd   xmm0, qword ptr [rcx+18h]
0x1004497f6  mov     ecx, [rax+5Ch]
0x1004497f9  movaps  xmm10, xmm0
0x1004497fd  movsd   qword ptr [rsp+88h+var_68+8], xmm0
0x100449803  movaps  xmm8, xmm0
0x100449807  movsd   qword ptr [rsp+88h+var_68], xmm3
0x10044980d  movaps  xmm6, xmm0
0x100449810  movaps  xmm4, xmm0
0x100449813  movaps  xmm9, xmm0
0x100449817  movaps  xmm7, xmm0
0x10044981a  movaps  xmm5, xmm0
0x10044981d  test    ecx, ecx
0x10044981f  jnz     short loc_10044982D
0x100449821  movsd   xmm1, qword ptr [rax+30h]
0x100449826  movsd   xmm2, qword ptr [rax+38h]
0x10044982b  jmp     short loc_10044989C
0x10044982d  cmp     ecx, 2
0x100449830  jnz     short loc_10044984D
0x100449832  movsd   xmm1, qword ptr [rax+30h]
0x100449837  movaps  xmm0, xmm5
0x10044983a  movsd   xmm2, qword ptr [rax+38h]
0x10044983f  movaps  xmm4, xmm6
0x100449842  addsd   xmm1, qword ptr [rax]
0x100449846  addsd   xmm2, qword ptr [rax+8]
0x10044984b  jmp     short loc_10044989C
0x10044984d  mov     ecx, [rax+60h]
0x100449850  test    ecx, ecx
0x100449852  jnz     short loc_100449871
0x100449854  movsd   xmm1, qword ptr [rax+30h]
0x100449859  movaps  xmm0, xmm7
0x10044985c  movsd   xmm2, qword ptr [rax+38h]
0x100449861  movaps  xmm4, xmm8
0x100449865  addsd   xmm1, qword ptr [rax+20h]
0x10044986a  addsd   xmm2, qword ptr [rax+28h]
0x10044986f  jmp     short loc_10044989C
0x100449871  cmp     ecx, 2
0x100449874  jnz     short loc_1004498D2
0x100449876  movsd   xmm1, qword ptr [rax+30h]
0x10044987b  movaps  xmm0, xmm9
0x10044987f  movsd   xmm2, qword ptr [rax+38h]
0x100449884  movaps  xmm4, xmm10
0x100449888  addsd   xmm1, qword ptr [rax+20h]
0x10044988d  addsd   xmm2, qword ptr [rax+28h]
0x100449892  subsd   xmm1, qword ptr [rax+10h]
0x100449897  subsd   xmm2, qword ptr [rax+18h]
0x10044989c  comisd  xmm0, xmm2
0x1004498a0  ja      short loc_1004498B8
0x1004498a2  comisd  xmm2, xmm4
0x1004498a6  jbe     short loc_1004498B2
0x1004498a8  mov     edx, 0FFFFFFFFh
0x1004498ad  jmp     loc_100449972
0x1004498b2  comisd  xmm3, xmm1
0x1004498b6  jbe     short loc_1004498C2
0x1004498b8  mov     edx, 1
0x1004498bd  jmp     loc_100449972
0x1004498c2  xor     edx, edx
0x1004498c4  comisd  xmm1, xmm3
0x1004498c8  setbe   dl
0x1004498cb  dec     edx
0x1004498cd  jmp     loc_100449972
0x1004498d2  lea     rdx, [rsp+88h+var_68]
0x1004498d7  mov     rcx, rax
0x1004498da  call    ?YXSortTransverseIntersectionAndPoint@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@QEBN@Z; RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPoint(RobustIntersections::CLineSegmentIntersection const &,double const * const)
0x1004498df  mov     edx, eax
0x1004498e1  neg     edx
0x1004498e3  jmp     loc_100449972
0x1004498e8  mov     r8d, [rax+5Ch]
0x1004498ec  test    r8d, r8d
0x1004498ef  jnz     short loc_1004498FC
0x1004498f1  movups  xmm0, xmmword ptr [rax+30h]
0x1004498f5  movups  [rsp+88h+var_68], xmm0
0x1004498fa  jmp     short loc_100449966
0x1004498fc  cmp     r8d, 2
0x100449900  jnz     short loc_100449917
0x100449902  movsd   xmm0, qword ptr [rax+30h]
0x100449907  movsd   xmm1, qword ptr [rax+38h]
0x10044990c  addsd   xmm0, qword ptr [rax]
0x100449910  addsd   xmm1, qword ptr [rax+8]
0x100449915  jmp     short loc_10044995A
0x100449917  mov     r8d, [rax+60h]
0x10044991b  test    r8d, r8d
0x10044991e  jnz     short loc_100449936
0x100449920  movsd   xmm0, qword ptr [rax+30h]
0x100449925  movsd   xmm1, qword ptr [rax+38h]
0x10044992a  addsd   xmm0, qword ptr [rax+20h]
0x10044992f  addsd   xmm1, qword ptr [rax+28h]
0x100449934  jmp     short loc_10044995A
0x100449936  cmp     r8d, 2
0x10044993a  jnz     short loc_100449972
0x10044993c  movsd   xmm0, qword ptr [rax+30h]
0x100449941  movsd   xmm1, qword ptr [rax+38h]
0x100449946  addsd   xmm0, qword ptr [rax+20h]
0x10044994b  addsd   xmm1, qword ptr [rax+28h]
0x100449950  subsd   xmm0, qword ptr [rax+10h]
0x100449955  subsd   xmm1, qword ptr [rax+18h]
0x10044995a  movsd   qword ptr [rsp+88h+var_68], xmm0
0x100449960  movsd   qword ptr [rsp+88h+var_68+8], xmm1
0x100449966  lea     rdx, [rsp+88h+var_68]
0x10044996b  call    ?YXSortTransverseIntersectionAndPoint@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@QEBN@Z; RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPoint(RobustIntersections::CLineSegmentIntersection const &,double const * const)
0x100449970  mov     edx, eax
0x100449972  movaps  xmm9, [rsp+88h+var_48]
0x100449978  movaps  xmm8, [rsp+88h+var_38]
0x10044997e  movaps  xmm7, [rsp+88h+var_28]
0x100449983  movaps  xmm6, [rsp+88h+var_18]
0x100449988  movaps  xmm10, [rsp+88h+var_58]
0x10044998e  mov     eax, edx
0x100449990  add     rsp, 88h
0x100449997  retn
```
