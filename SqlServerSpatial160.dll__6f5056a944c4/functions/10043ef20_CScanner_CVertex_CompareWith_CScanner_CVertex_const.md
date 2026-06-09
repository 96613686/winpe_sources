# CScanner::CVertex::CompareWith(CScanner::CVertex const *)

- ea: `0x10043ef20`
- end: `0x10043efd5`
- name: `?CompareWith@CVertex@CScanner@@QEBA?AW4COMPARISON@RobustIntersections@@PEBV12@@Z`
- size: `181`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100440160`
- `0x100441700`
- `0x1004418f0`
- `0x100441c90`
- `0x1004425b0`
- `0x100442fd0`
- `0x100443920`
- `0x100443da0`
- `0x100443f60`
- `0x100444000`

## callees

- `0x10043ef20`
- `0x100448160`
- `0x100448310`

## pseudocode

```c
__int64 __fastcall CScanner::CVertex::CompareWith(__int64 a1, __int64 a2)
{
  int v3; // edx
  double v4; // xmm0_8
  double v5; // xmm1_8
  double v7; // xmm0_8
  double v8; // xmm1_8
  __int128 v9; // xmm0
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int128 v12; // [rsp+20h] [rbp-18h] BYREF

  v3 = *(_DWORD *)(a2 + 16);
  if ( (*(_BYTE *)(a1 + 16) & 5) != 0 )
  {
    if ( (v3 & 5) != 0 )
    {
      v4 = *(double *)(a1 + 56);
      v5 = *(double *)(a2 + 56);
      if ( v5 > v4 )
        return 0xFFFFFFFFLL;
      if ( v4 > v5 )
        return 1;
      v7 = *(double *)(a1 + 48);
      v8 = *(double *)(a2 + 48);
      if ( v8 <= v7 )
        return v7 > v8;
      else
        return 0xFFFFFFFFLL;
    }
    else
    {
      v9 = *(_OWORD *)(a1 + 48);
      v10 = *(_QWORD *)(a2 + 64);
      v12 = v9;
      return (unsigned int)-RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPoint(
                              v10,
                              &v12);
    }
  }
  else
  {
    v11 = *(_QWORD *)(a1 + 64);
    if ( (v3 & 5) != 0 )
    {
      v12 = *(_OWORD *)(a2 + 48);
      return RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPoint(v11, &v12);
    }
    else if ( v11 == *(_QWORD *)(a2 + 64) )
    {
      return 0;
    }
    else
    {
      return RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPair();
    }
  }
}

```

## disassembly

```asm
0x10043ef20  sub     rsp, 38h
0x10043ef24  test    byte ptr [rcx+10h], 5
0x10043ef28  mov     rax, rdx
0x10043ef2b  mov     edx, [rdx+10h]
0x10043ef2e  jz      short loc_10043EF9B
0x10043ef30  test    dl, 5
0x10043ef33  jz      short loc_10043EF7D
0x10043ef35  movsd   xmm0, qword ptr [rcx+38h]
0x10043ef3a  movsd   xmm1, qword ptr [rax+38h]
0x10043ef3f  comisd  xmm1, xmm0
0x10043ef43  ja      short loc_10043EF65
0x10043ef45  comisd  xmm0, xmm1
0x10043ef49  jbe     short loc_10043EF55
0x10043ef4b  mov     eax, 1
0x10043ef50  add     rsp, 38h
0x10043ef54  retn
0x10043ef55  movsd   xmm0, qword ptr [rcx+30h]
0x10043ef5a  movsd   xmm1, qword ptr [rax+30h]
0x10043ef5f  comisd  xmm1, xmm0
0x10043ef63  jbe     short loc_10043EF6F
0x10043ef65  mov     eax, 0FFFFFFFFh
0x10043ef6a  add     rsp, 38h
0x10043ef6e  retn
0x10043ef6f  xor     eax, eax
0x10043ef71  comisd  xmm0, xmm1
0x10043ef75  setnbe  al
0x10043ef78  add     rsp, 38h
0x10043ef7c  retn
0x10043ef7d  movups  xmm0, xmmword ptr [rcx+30h]
0x10043ef81  mov     rcx, [rax+40h]
0x10043ef85  lea     rdx, [rsp+38h+var_18]
0x10043ef8a  movups  [rsp+38h+var_18], xmm0
0x10043ef8f  call    ?YXSortTransverseIntersectionAndPoint@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@QEBN@Z; RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPoint(RobustIntersections::CLineSegmentIntersection const &,double const * const)
0x10043ef94  neg     eax
0x10043ef96  add     rsp, 38h
0x10043ef9a  retn
0x10043ef9b  mov     rcx, [rcx+40h]
0x10043ef9f  test    dl, 5
0x10043efa2  jz      short loc_10043EFBC
0x10043efa4  movups  xmm0, xmmword ptr [rax+30h]
0x10043efa8  lea     rdx, [rsp+38h+var_18]
0x10043efad  movups  [rsp+38h+var_18], xmm0
0x10043efb2  call    ?YXSortTransverseIntersectionAndPoint@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@QEBN@Z; RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPoint(RobustIntersections::CLineSegmentIntersection const &,double const * const)
0x10043efb7  add     rsp, 38h
0x10043efbb  retn
0x10043efbc  mov     rdx, [rax+40h]
0x10043efc0  cmp     rcx, rdx
0x10043efc3  jnz     short loc_10043EFCC
0x10043efc5  xor     eax, eax
0x10043efc7  add     rsp, 38h
0x10043efcb  retn
0x10043efcc  add     rsp, 38h
0x10043efd0  jmp     ?YXSortTransverseIntersectionPair@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@0@Z; RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPair(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)
```
