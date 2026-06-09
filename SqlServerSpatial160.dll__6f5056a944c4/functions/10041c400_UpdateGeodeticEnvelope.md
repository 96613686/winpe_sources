# UpdateGeodeticEnvelope

- ea: `0x10041c400`
- end: `0x10041c59e`
- name: `UpdateGeodeticEnvelope`
- size: `414`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x10041c400`
- `0x100421170`
- `0x100421240`
- `0x100425d60`
- `0x1004676d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall UpdateGeodeticEnvelope(__int64 a1, double a2, __int128 *a3)
{
  int v5; // ebx
  __int128 v6; // xmm4
  __int128 v7; // xmm1
  int v9[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v10[3]; // [rsp+50h] [rbp-B8h]
  __int128 v11; // [rsp+68h] [rbp-A0h]
  _BYTE v12[24]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v13; // [rsp+90h] [rbp-78h]
  __int64 v14; // [rsp+98h] [rbp-70h]
  _QWORD v15[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v16; // [rsp+B8h] [rbp-50h]
  __int128 v17; // [rsp+C8h] [rbp-40h]
  _BYTE v18[24]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v19; // [rsp+F0h] [rbp-18h]
  __int64 v20; // [rsp+F8h] [rbp-10h]
  __int64 v21; // [rsp+100h] [rbp-8h]

  v21 = -2;
  *(_QWORD *)v9 = &CCap::`vftable';
  *(double *)v10 = a2;
  *((double *)&v11 + 1) = DOUBLE_N1_0;
  ArrayOverPages<CPoint3D,Default_Allocator<CPoint3D>>::ArrayOverPages<CPoint3D,Default_Allocator<CPoint3D>>(v12);
  v13 = 0;
  v14 = 0;
  if ( *(_BYTE *)(a1 + 77) )
  {
    *(_OWORD *)&v10[1] = 0;
    v11 = _xmm;
    v5 = 0;
  }
  else
  {
    v5 = InternalPopulate<CGeometrySinkD>(a1, (__int64)v9, 1u, 1u, 255, 0, 1);
  }
  if ( v5 >= 0 )
  {
    v6 = a3[1];
    v7 = *a3;
    v15[0] = &CCap::`vftable';
    *(double *)&v15[1] = DOUBLE_1_0;
    v16 = v7;
    v17 = v6;
    ArrayOverPages<CPoint3D,Default_Allocator<CPoint3D>>::ArrayOverPages<CPoint3D,Default_Allocator<CPoint3D>>(v18);
    v19 = 0;
    v20 = 0;
    CCap::UnionWith((CCap *)v9, (const struct CCap *)v15);
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v18);
    v15[0] = &IMglGeometrySink::`vftable';
    *a3 = *(_OWORD *)&v10[1];
    a3[1] = v11;
  }
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x10041c400  mov     rax, rsp
0x10041c403  push    rbp
0x10041c404  push    r13
0x10041c406  push    r15
0x10041c408  lea     rbp, [rax-28h]
0x10041c40c  sub     rsp, 110h
0x10041c413  mov     [rbp+20h+var_28], 0FFFFFFFFFFFFFFFEh
0x10041c41b  mov     [rax+8], rbx
0x10041c41f  mov     [rax+10h], rsi
0x10041c423  mov     [rax+18h], rdi
0x10041c427  mov     [rax+20h], r12
0x10041c42b  movaps  xmmword ptr [rax-28h], xmm6
0x10041c42f  mov     rdi, r8
0x10041c432  mov     rbx, rcx
0x10041c435  lea     rsi, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x10041c43c  mov     qword ptr [rsp+120h+var_E0], rsi
0x10041c441  lea     r15, ??_7CGeometrySinkD@@6B@; const CGeometrySinkD::`vftable'
0x10041c448  mov     qword ptr [rsp+120h+var_E0], r15
0x10041c44d  lea     r12, ??_7CGeodeticSink@@6B@; const CGeodeticSink::`vftable'
0x10041c454  mov     qword ptr [rsp+120h+var_E0], r12
0x10041c459  lea     r13, ??_7CCap@@6B@; const CCap::`vftable'
0x10041c460  mov     qword ptr [rsp+120h+var_E0], r13
0x10041c465  movsd   qword ptr [rsp+120h+var_D8], xmm1
0x10041c46b  movsd   xmm0, cs:__real@bff0000000000000
0x10041c473  movsd   qword ptr [rsp+120h+var_C0+8], xmm0
0x10041c479  lea     rcx, [rsp+120h+var_B0]
0x10041c47e  call    ??0?$ArrayOverPages@VCPoint3D@@V?$Default_Allocator@VCPoint3D@@@@@@QEAA@XZ; ArrayOverPages<CPoint3D,Default_Allocator<CPoint3D>>::ArrayOverPages<CPoint3D,Default_Allocator<CPoint3D>>(void)
0x10041c483  nop
0x10041c484  mov     [rbp+20h+var_98], 0
0x10041c48c  xorps   xmm6, xmm6
0x10041c48f  movsd   [rbp+20h+var_90], xmm6
0x10041c494  cmp     byte ptr [rbx+4Dh], 0
0x10041c498  jz      short loc_10041C4CA
0x10041c49a  xorps   xmm0, xmm0
0x10041c49d  movaps  xmmword ptr [rsp+120h+var_D8+8], xmm0
0x10041c4a2  movaps  xmm1, cs:__xmm@40100000000000003ff0000000000000
0x10041c4a9  movaps  [rsp+120h+var_C0], xmm1
0x10041c4ae  mov     rcx, [rbp+20h+var_98]
0x10041c4b2  test    rcx, rcx
0x10041c4b5  jz      short loc_10041C4C6
0x10041c4b7  mov     rax, [rcx]
0x10041c4ba  xor     r8d, r8d
0x10041c4bd  lea     edx, [r8+6]
0x10041c4c1  call    qword ptr [rax+8]
0x10041c4c4  jmp     short loc_10041C4EF
0x10041c4c6  xor     ebx, ebx
0x10041c4c8  jmp     short loc_10041C4F1
0x10041c4ca  mov     [rsp+120h+var_F0], 1; char
0x10041c4cf  mov     [rsp+120h+var_F8], 0; char
0x10041c4d4  mov     [rsp+120h+var_100], 0FFh; char
0x10041c4d9  mov     r9b, 1
0x10041c4dc  mov     r8d, 1
0x10041c4e2  lea     rdx, [rsp+120h+var_E0]; int
0x10041c4e7  mov     rcx, rbx; int
0x10041c4ea  call    ??$InternalPopulate@VCGeometrySinkD@@@@YAJAEBUGeoData@@PEAVCGeometrySinkD@@W4MGL_WINDING_RULE@@_NE33@Z; InternalPopulate<CGeometrySinkD>(GeoData const &,CGeometrySinkD *,MGL_WINDING_RULE,bool,uchar,bool,bool)
0x10041c4ef  mov     ebx, eax
0x10041c4f1  test    ebx, ebx
0x10041c4f3  js      short loc_10041C566
0x10041c4f5  movups  xmm4, xmmword ptr [rdi+10h]
0x10041c4f9  movups  xmm1, xmmword ptr [rdi]
0x10041c4fc  mov     [rbp+20h+var_80], rsi
0x10041c500  mov     [rbp+20h+var_80], r15
0x10041c504  mov     [rbp+20h+var_80], r12
0x10041c508  mov     [rbp+20h+var_80], r13
0x10041c50c  movsd   xmm0, cs:__real@3ff0000000000000
0x10041c514  movsd   [rbp+20h+var_78], xmm0
0x10041c519  movups  [rbp+20h+var_70], xmm1
0x10041c51d  movups  [rbp+20h+var_60], xmm4
0x10041c521  lea     rcx, [rbp+20h+var_50]
0x10041c525  call    ??0?$ArrayOverPages@VCPoint3D@@V?$Default_Allocator@VCPoint3D@@@@@@QEAA@XZ; ArrayOverPages<CPoint3D,Default_Allocator<CPoint3D>>::ArrayOverPages<CPoint3D,Default_Allocator<CPoint3D>>(void)
0x10041c52a  nop
0x10041c52b  mov     [rbp+20h+var_38], 0
0x10041c533  movsd   [rbp+20h+var_30], xmm6
0x10041c538  lea     rdx, [rbp+20h+var_80]; struct CCap *
0x10041c53c  lea     rcx, [rsp+120h+var_E0]; this
0x10041c541  call    ?UnionWith@CCap@@QEAAXAEBV1@@Z; CCap::UnionWith(CCap const &)
0x10041c546  nop
0x10041c547  lea     rcx, [rbp+20h+var_50]
0x10041c54b  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10041c550  nop
0x10041c551  mov     [rbp+20h+var_80], rsi
0x10041c555  movaps  xmm0, xmmword ptr [rsp+120h+var_D8+8]
0x10041c55a  movups  xmmword ptr [rdi], xmm0
0x10041c55d  movaps  xmm0, [rsp+120h+var_C0]
0x10041c562  movups  xmmword ptr [rdi+10h], xmm0
0x10041c566  lea     rcx, [rsp+120h+var_B0]
0x10041c56b  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10041c570  nop
0x10041c571  mov     qword ptr [rsp+120h+var_E0], rsi
0x10041c576  mov     eax, ebx
0x10041c578  lea     r11, [rsp+120h+var_10]
0x10041c580  mov     rbx, [r11+20h]
0x10041c584  mov     rsi, [r11+28h]
0x10041c588  mov     rdi, [r11+30h]
0x10041c58c  mov     r12, [r11+38h]
0x10041c590  movaps  xmm6, xmmword ptr [r11-10h]
0x10041c595  mov     rsp, r11
0x10041c598  pop     r15
0x10041c59a  pop     r13
0x10041c59c  pop     rbp
0x10041c59d  retn
```
