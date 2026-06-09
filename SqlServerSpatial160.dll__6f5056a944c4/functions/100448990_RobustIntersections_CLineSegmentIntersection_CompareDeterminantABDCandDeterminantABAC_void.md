# RobustIntersections::CLineSegmentIntersection::CompareDeterminantABDCandDeterminantABAC(void)

- ea: `0x100448990`
- end: `0x100448bb7`
- name: `?CompareDeterminantABDCandDeterminantABAC@CLineSegmentIntersection@RobustIntersections@@AEAA?AW4COMPARISON@2@XZ`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1004473b0`

## callees

- `0x10042a400`
- `0x10042a4e0`
- `0x10042a7a0`
- `0x100448990`
- `0x100468a30`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::CompareDeterminantABDCandDeterminantABAC(__int64 a1)
{
  double v1; // xmm0_8
  double v2; // xmm1_8
  __int64 result; // rax
  double v4; // xmm5_8
  double v5; // xmm3_8
  double v6; // xmm4_8
  double v7; // xmm2_8
  double v8; // xmm0_8
  __int64 v9; // rbx
  __int64 v10; // rax
  unsigned int v11; // ecx
  int v12; // edx
  unsigned int v13; // r9d
  __int64 v14; // r8
  unsigned int v15; // edx
  __int64 v16; // rcx
  _BYTE v17[40]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v18[40]; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v19[40]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v20[40]; // [rsp+98h] [rbp-50h] BYREF

  if ( *(_BYTE *)(a1 + 112) && *(_BYTE *)(a1 + 114) )
  {
    v1 = *(double *)(a1 + 64);
    v2 = *(double *)(a1 + 80);
    if ( v2 <= v1 )
      return v1 > v2;
    else
      return 0xFFFFFFFFLL;
  }
  v4 = *(double *)a1;
  v5 = *(double *)(a1 + 16) - *(double *)(a1 + 32);
  if ( *(double *)a1 == 0.0 && v5 == 0.0 )
    return 0;
  v6 = *(double *)(a1 + 24) - *(double *)(a1 + 40);
  if ( v6 == 0.0 && (*(double *)(a1 + 8) == 0.0 || v5 == 0.0) )
    return 0;
  v7 = v4 * v6;
  v8 = *(double *)(a1 + 8) * v5;
  if ( v4 * v6 >= 0.0 && v8 <= 0.0 )
    return 1;
  if ( v7 <= 0.0 && v8 >= 0.0 )
    return 0xFFFFFFFFLL;
  if ( v7 == v8 )
  {
    RobustIntersections::CZ<128>::CZ<128>(v20);
    RobustIntersections::CZ<128>::CZ<128>(v18);
    RobustIntersections::CZ<128>::CZ<128>(v17);
    RobustIntersections::CZ<128>::CZ<128>(v19);
    v9 = RobustIntersections::CZ<128>::Multiply(v18, v17);
    v10 = RobustIntersections::CZ<128>::Multiply(v20, v19);
    v11 = 0;
    v12 = *(_DWORD *)(v10 + 4);
    if ( v12 > *(_DWORD *)(v9 + 4) )
      return 1;
    if ( v12 < *(_DWORD *)(v9 + 4) )
      return 0xFFFFFFFFLL;
    if ( v12 <= 0 )
    {
      if ( v12 >= 0 )
        return v11;
      v13 = *(_DWORD *)v10;
      v14 = *(_QWORD *)(v10 + 8);
      v15 = *(_DWORD *)v9;
      v16 = *(_QWORD *)(v9 + 8);
    }
    else
    {
      v13 = *(_DWORD *)v9;
      v14 = *(_QWORD *)(v9 + 8);
      v15 = *(_DWORD *)v10;
      v16 = *(_QWORD *)(v10 + 8);
    }
    return (unsigned int)RobustIntersections::EaCompare(v16, v15, v14, v13);
  }
  result = 0xFFFFFFFFLL;
  if ( v7 > v8 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x100448990  sub     rsp, 0E8h
0x100448997  mov     rax, cs:__security_cookie
0x10044899e  xor     rax, rsp
0x1004489a1  mov     [rsp+0E8h+var_28], rax
0x1004489a9  cmp     byte ptr [rcx+70h], 0
0x1004489ad  jz      short loc_100448A05
0x1004489af  cmp     byte ptr [rcx+72h], 0
0x1004489b3  jz      short loc_100448A05
0x1004489b5  movsd   xmm0, qword ptr [rcx+40h]
0x1004489ba  movsd   xmm1, qword ptr [rcx+50h]
0x1004489bf  comisd  xmm1, xmm0
0x1004489c3  jbe     short loc_1004489E2
0x1004489c5  mov     eax, 0FFFFFFFFh
0x1004489ca  mov     rcx, [rsp+0E8h+var_28]
0x1004489d2  xor     rcx, rsp; StackCookie
0x1004489d5  call    __security_check_cookie
0x1004489da  add     rsp, 0E8h
0x1004489e1  retn
0x1004489e2  xor     ecx, ecx
0x1004489e4  comisd  xmm0, xmm1
0x1004489e8  setnbe  cl
0x1004489eb  mov     eax, ecx
0x1004489ed  mov     rcx, [rsp+0E8h+var_28]
0x1004489f5  xor     rcx, rsp; StackCookie
0x1004489f8  call    __security_check_cookie
0x1004489fd  add     rsp, 0E8h
0x100448a04  retn
0x100448a05  movsd   xmm5, qword ptr [rcx]
0x100448a09  xorps   xmm1, xmm1
0x100448a0c  ucomisd xmm5, xmm1
0x100448a10  movsd   xmm3, qword ptr [rcx+10h]
0x100448a15  subsd   xmm3, qword ptr [rcx+20h]
0x100448a1a  jp      short loc_100448A26
0x100448a1c  jnz     short loc_100448A26
0x100448a1e  ucomisd xmm3, xmm1
0x100448a22  jp      short loc_100448A26
0x100448a24  jz      short loc_100448A4D
0x100448a26  movsd   xmm4, qword ptr [rcx+18h]
0x100448a2b  subsd   xmm4, qword ptr [rcx+28h]
0x100448a30  ucomisd xmm4, xmm1
0x100448a34  jp      short loc_100448A69
0x100448a36  jnz     short loc_100448A69
0x100448a38  movsd   xmm0, qword ptr [rcx+8]
0x100448a3d  ucomisd xmm0, xmm1
0x100448a41  jp      short loc_100448A45
0x100448a43  jz      short loc_100448A4D
0x100448a45  ucomisd xmm3, xmm1
0x100448a49  jp      short loc_100448A69
0x100448a4b  jnz     short loc_100448A69
0x100448a4d  xor     ecx, ecx
0x100448a4f  mov     eax, ecx
0x100448a51  mov     rcx, [rsp+0E8h+var_28]
0x100448a59  xor     rcx, rsp; StackCookie
0x100448a5c  call    __security_check_cookie
0x100448a61  add     rsp, 0E8h
0x100448a68  retn
0x100448a69  movaps  xmm2, xmm5
0x100448a6c  movaps  [rsp+0E8h+var_18], xmm6
0x100448a74  movsd   xmm6, qword ptr [rcx+8]
0x100448a79  mulsd   xmm2, xmm4
0x100448a7d  movaps  xmm0, xmm6
0x100448a80  mulsd   xmm0, xmm3
0x100448a84  comisd  xmm2, xmm1
0x100448a88  jb      short loc_100448A9A
0x100448a8a  comisd  xmm1, xmm0
0x100448a8e  jb      short loc_100448A9A
0x100448a90  mov     eax, 1
0x100448a95  jmp     loc_100448B97
0x100448a9a  comisd  xmm1, xmm2
0x100448a9e  jb      short loc_100448AB0
0x100448aa0  comisd  xmm0, xmm1
0x100448aa4  jb      short loc_100448AB0
0x100448aa6  mov     eax, 0FFFFFFFFh
0x100448aab  jmp     loc_100448B97
0x100448ab0  ucomisd xmm2, xmm0
0x100448ab4  jp      loc_100448B86
0x100448aba  jnz     loc_100448B86
0x100448ac0  movaps  xmm1, xmm5
0x100448ac3  mov     [rsp+0E8h+var_8], rbx
0x100448acb  lea     rcx, [rsp+0E8h+var_50]
0x100448ad3  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x100448ad8  movaps  xmm1, xmm6
0x100448adb  lea     rcx, [rsp+0E8h+var_A0]
0x100448ae0  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x100448ae5  movaps  xmm1, xmm3
0x100448ae8  lea     rcx, [rsp+0E8h+var_C8]
0x100448aed  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x100448af2  movaps  xmm1, xmm4
0x100448af5  lea     rcx, [rsp+0E8h+var_78]
0x100448afa  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x100448aff  lea     rdx, [rsp+0E8h+var_C8]
0x100448b04  lea     rcx, [rsp+0E8h+var_A0]
0x100448b09  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100448b0e  lea     rdx, [rsp+0E8h+var_78]
0x100448b13  mov     rbx, rax
0x100448b16  lea     rcx, [rsp+0E8h+var_50]
0x100448b1e  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100448b23  xor     ecx, ecx
0x100448b25  mov     edx, [rax+4]
0x100448b28  cmp     edx, [rbx+4]
0x100448b2b  jle     short loc_100448B3E
0x100448b2d  mov     rbx, [rsp+0E8h+var_8]
0x100448b35  mov     ecx, 1
0x100448b3a  mov     eax, ecx
0x100448b3c  jmp     short loc_100448B97
0x100448b3e  jge     short loc_100448B51
0x100448b40  mov     rbx, [rsp+0E8h+var_8]
0x100448b48  mov     ecx, 0FFFFFFFFh
0x100448b4d  mov     eax, ecx
0x100448b4f  jmp     short loc_100448B97
0x100448b51  test    edx, edx
0x100448b53  jle     short loc_100448B64
0x100448b55  mov     r9d, [rbx]
0x100448b58  mov     r8, [rbx+8]
0x100448b5c  mov     edx, [rax]
0x100448b5e  mov     rcx, [rax+8]
0x100448b62  jmp     short loc_100448B73
0x100448b64  jns     short loc_100448B7A
0x100448b66  mov     r9d, [rax]
0x100448b69  mov     r8, [rax+8]
0x100448b6d  mov     edx, [rbx]
0x100448b6f  mov     rcx, [rbx+8]
0x100448b73  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100448b78  mov     ecx, eax
0x100448b7a  mov     rbx, [rsp+0E8h+var_8]
0x100448b82  mov     eax, ecx
0x100448b84  jmp     short loc_100448B97
0x100448b86  comisd  xmm2, xmm0
0x100448b8a  mov     eax, 0FFFFFFFFh
0x100448b8f  mov     ecx, 1
0x100448b94  cmova   eax, ecx
0x100448b97  movaps  xmm6, [rsp+0E8h+var_18]
0x100448b9f  mov     rcx, [rsp+0E8h+var_28]
0x100448ba7  xor     rcx, rsp; StackCookie
0x100448baa  call    __security_check_cookie
0x100448baf  add     rsp, 0E8h
0x100448bb6  retn
```
