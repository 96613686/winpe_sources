# RobustIntersections::CLineSegmentIntersection::CompareDeterminantABDCandDeterminantACDC(void)

- ea: `0x100448790`
- end: `0x100448981`
- name: `?CompareDeterminantABDCandDeterminantACDC@CLineSegmentIntersection@RobustIntersections@@AEAA?AW4COMPARISON@2@XZ`
- size: `497`
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
- `0x100448790`
- `0x100468a30`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::CompareDeterminantABDCandDeterminantACDC(__int64 a1)
{
  double v1; // xmm0_8
  double v2; // xmm1_8
  unsigned int v3; // ecx
  double v4; // xmm5_8
  double v5; // xmm3_8
  double v6; // xmm4_8
  double v7; // xmm2_8
  double v8; // xmm0_8
  __int64 v9; // rbx
  __int64 v10; // rax
  int v11; // edx
  unsigned int v12; // eax
  _BYTE v14[40]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v15[40]; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v16[40]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v17[40]; // [rsp+98h] [rbp-50h] BYREF

  if ( *(_BYTE *)(a1 + 112) && *(_BYTE *)(a1 + 113) )
  {
    v1 = *(double *)(a1 + 64);
    v2 = *(double *)(a1 + 72);
    if ( v2 <= v1 )
      return v1 > v2;
    return (unsigned int)-1;
  }
  v4 = *(double *)(a1 + 16);
  v5 = *(double *)(a1 + 32) - *(double *)a1;
  if ( v4 == 0.0 && v5 == 0.0 )
    return 0;
  v6 = *(double *)(a1 + 40) - *(double *)(a1 + 8);
  if ( v6 == 0.0 && (*(double *)(a1 + 24) == 0.0 || v5 == 0.0) )
    return 0;
  v7 = v4 * v6;
  v8 = *(double *)(a1 + 24) * v5;
  if ( v4 * v6 >= 0.0 && v8 <= 0.0 )
    return 1;
  if ( v7 <= 0.0 && v8 >= 0.0 )
    return (unsigned int)-1;
  if ( v7 == v8 )
  {
    RobustIntersections::CZ<128>::CZ<128>(v17);
    RobustIntersections::CZ<128>::CZ<128>(v15);
    RobustIntersections::CZ<128>::CZ<128>(v14);
    RobustIntersections::CZ<128>::CZ<128>(v16);
    v9 = RobustIntersections::CZ<128>::Multiply(v15, v14);
    v10 = RobustIntersections::CZ<128>::Multiply(v17, v16);
    v3 = 0;
    v11 = *(_DWORD *)(v10 + 4);
    if ( v11 <= *(_DWORD *)(v9 + 4) )
    {
      if ( v11 >= *(_DWORD *)(v9 + 4) )
      {
        if ( v11 <= 0 )
        {
          if ( v11 < 0 )
            return (unsigned int)RobustIntersections::EaCompare(
                                   *(_QWORD *)(v9 + 8),
                                   *(_DWORD *)v9,
                                   *(_QWORD *)(v10 + 8),
                                   *(_DWORD *)v10);
        }
        else
        {
          return (unsigned int)RobustIntersections::EaCompare(
                                 *(_QWORD *)(v10 + 8),
                                 *(_DWORD *)v10,
                                 *(_QWORD *)(v9 + 8),
                                 *(_DWORD *)v9);
        }
      }
      else
      {
        return (unsigned int)-1;
      }
    }
    else
    {
      return 1;
    }
  }
  else
  {
    v12 = -1;
    if ( v7 > v8 )
      return 1;
    return v12;
  }
  return v3;
}

```

## disassembly

```asm
0x100448790  sub     rsp, 0E8h
0x100448797  movaps  [rsp+0E8h+var_18], xmm6
0x10044879f  mov     rax, cs:__security_cookie
0x1004487a6  xor     rax, rsp
0x1004487a9  mov     [rsp+0E8h+var_28], rax
0x1004487b1  cmp     byte ptr [rcx+70h], 0
0x1004487b5  jz      short loc_1004487DF
0x1004487b7  cmp     byte ptr [rcx+71h], 0
0x1004487bb  jz      short loc_1004487DF
0x1004487bd  movsd   xmm0, qword ptr [rcx+40h]
0x1004487c2  movsd   xmm1, qword ptr [rcx+48h]
0x1004487c7  comisd  xmm1, xmm0
0x1004487cb  ja      loc_100448863
0x1004487d1  xor     ecx, ecx
0x1004487d3  comisd  xmm0, xmm1
0x1004487d7  setnbe  cl
0x1004487da  jmp     loc_10044895F
0x1004487df  movsd   xmm5, qword ptr [rcx+10h]
0x1004487e4  xorps   xmm1, xmm1
0x1004487e7  ucomisd xmm5, xmm1
0x1004487eb  movsd   xmm3, qword ptr [rcx+20h]
0x1004487f0  subsd   xmm3, qword ptr [rcx]
0x1004487f4  jp      short loc_100448800
0x1004487f6  jnz     short loc_100448800
0x1004487f8  ucomisd xmm3, xmm1
0x1004487fc  jp      short loc_100448800
0x1004487fe  jz      short loc_100448827
0x100448800  movsd   xmm4, qword ptr [rcx+28h]
0x100448805  subsd   xmm4, qword ptr [rcx+8]
0x10044880a  ucomisd xmm4, xmm1
0x10044880e  jp      short loc_10044882E
0x100448810  jnz     short loc_10044882E
0x100448812  movsd   xmm0, qword ptr [rcx+18h]
0x100448817  ucomisd xmm0, xmm1
0x10044881b  jp      short loc_10044881F
0x10044881d  jz      short loc_100448827
0x10044881f  ucomisd xmm3, xmm1
0x100448823  jp      short loc_10044882E
0x100448825  jnz     short loc_10044882E
0x100448827  xor     ecx, ecx
0x100448829  jmp     loc_10044895F
0x10044882e  movsd   xmm6, qword ptr [rcx+18h]
0x100448833  movaps  xmm2, xmm5
0x100448836  mulsd   xmm2, xmm4
0x10044883a  movaps  xmm0, xmm6
0x10044883d  mulsd   xmm0, xmm3
0x100448841  comisd  xmm2, xmm1
0x100448845  jb      short loc_100448857
0x100448847  comisd  xmm1, xmm0
0x10044884b  jb      short loc_100448857
0x10044884d  mov     ecx, 1
0x100448852  jmp     loc_10044895F
0x100448857  comisd  xmm1, xmm2
0x10044885b  jb      short loc_10044886D
0x10044885d  comisd  xmm0, xmm1
0x100448861  jb      short loc_10044886D
0x100448863  mov     ecx, 0FFFFFFFFh
0x100448868  jmp     loc_10044895F
0x10044886d  ucomisd xmm2, xmm0
0x100448871  jp      loc_10044894C
0x100448877  jnz     loc_10044894C
0x10044887d  movaps  xmm1, xmm5
0x100448880  mov     [rsp+0E8h+var_8], rbx
0x100448888  lea     rcx, [rsp+0E8h+var_50]
0x100448890  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x100448895  movaps  xmm1, xmm6
0x100448898  lea     rcx, [rsp+0E8h+var_A0]
0x10044889d  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x1004488a2  movaps  xmm1, xmm3
0x1004488a5  lea     rcx, [rsp+0E8h+var_C8]
0x1004488aa  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x1004488af  movaps  xmm1, xmm4
0x1004488b2  lea     rcx, [rsp+0E8h+var_78]
0x1004488b7  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x1004488bc  lea     rdx, [rsp+0E8h+var_C8]
0x1004488c1  lea     rcx, [rsp+0E8h+var_A0]
0x1004488c6  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004488cb  lea     rdx, [rsp+0E8h+var_78]
0x1004488d0  mov     rbx, rax
0x1004488d3  lea     rcx, [rsp+0E8h+var_50]
0x1004488db  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004488e0  xor     ecx, ecx
0x1004488e2  mov     edx, [rax+4]
0x1004488e5  cmp     edx, [rbx+4]
0x1004488e8  jle     short loc_1004488F9
0x1004488ea  mov     rbx, [rsp+0E8h+var_8]
0x1004488f2  mov     ecx, 1
0x1004488f7  jmp     short loc_10044895F
0x1004488f9  jge     short loc_10044890A
0x1004488fb  mov     rbx, [rsp+0E8h+var_8]
0x100448903  mov     ecx, 0FFFFFFFFh
0x100448908  jmp     short loc_10044895F
0x10044890a  test    edx, edx
0x10044890c  jle     short loc_10044892C
0x10044890e  mov     r9d, [rbx]
0x100448911  mov     r8, [rbx+8]
0x100448915  mov     edx, [rax]
0x100448917  mov     rcx, [rax+8]
0x10044891b  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100448920  mov     rbx, [rsp+0E8h+var_8]
0x100448928  mov     ecx, eax
0x10044892a  jmp     short loc_10044895F
0x10044892c  jns     short loc_100448942
0x10044892e  mov     r9d, [rax]
0x100448931  mov     r8, [rax+8]
0x100448935  mov     edx, [rbx]
0x100448937  mov     rcx, [rbx+8]
0x10044893b  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100448940  mov     ecx, eax
0x100448942  mov     rbx, [rsp+0E8h+var_8]
0x10044894a  jmp     short loc_10044895F
0x10044894c  mov     ecx, 1
0x100448951  mov     eax, 0FFFFFFFFh
0x100448956  comisd  xmm2, xmm0
0x10044895a  cmova   eax, ecx
0x10044895d  mov     ecx, eax
0x10044895f  mov     eax, ecx
0x100448961  mov     rcx, [rsp+0E8h+var_28]
0x100448969  xor     rcx, rsp; StackCookie
0x10044896c  call    __security_check_cookie
0x100448971  movaps  xmm6, [rsp+0E8h+var_18]
0x100448979  add     rsp, 0E8h
0x100448980  retn
```
