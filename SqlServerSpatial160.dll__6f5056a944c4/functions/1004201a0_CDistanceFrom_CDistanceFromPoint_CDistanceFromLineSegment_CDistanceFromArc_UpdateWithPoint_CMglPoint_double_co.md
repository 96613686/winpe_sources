# CDistanceFrom<CDistanceFromPoint,CDistanceFromLineSegment,CDistanceFromArc>::UpdateWithPoint(CMglPoint<double> const &)

- ea: `0x1004201a0`
- end: `0x10042023b`
- name: `?UpdateWithPoint@?$CDistanceFrom@VCDistanceFromPoint@@VCDistanceFromLineSegment@@VCDistanceFromArc@@@@QEAAJAEBV?$CMglPoint@N@@@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x10041d9f0`

## callees

- `0x100425d60`
- `0x100468a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDistanceFrom<CDistanceFromPoint,CDistanceFromLineSegment,CDistanceFromArc>::UpdateWithPoint(
        __int64 *a1,
        __int128 *a2)
{
  _QWORD v3[4]; // [rsp+48h] [rbp-40h] BYREF
  __int128 v4; // [rsp+68h] [rbp-20h]

  v3[3] = a1[1];
  v3[0] = &CDistanceFromPoint::`vftable';
  v4 = *a2;
  return InternalPopulate<CGeometrySinkD>(*a1, (__int64)v3, 0, 1u, 255, 0, 1);
}

```

## disassembly

```asm
0x1004201a0  mov     r11, rsp
0x1004201a3  push    rbx
0x1004201a4  sub     rsp, 80h
0x1004201ab  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x1004201b3  mov     rax, cs:__security_cookie
0x1004201ba  xor     rax, rsp
0x1004201bd  mov     [rsp+88h+var_10], rax
0x1004201c2  mov     rax, [rcx+8]
0x1004201c6  lea     rbx, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x1004201cd  mov     [r11-40h], rbx
0x1004201d1  lea     r8, ??_7CGeometrySinkD@@6B@; const CGeometrySinkD::`vftable'
0x1004201d8  mov     [r11-40h], r8
0x1004201dc  lea     r8, ??_7CDistanceFromAtom@@6B@; const CDistanceFromAtom::`vftable'
0x1004201e3  mov     [r11-40h], r8
0x1004201e7  mov     [r11-28h], rax
0x1004201eb  lea     rax, ??_7CDistanceFromPoint@@6B@; const CDistanceFromPoint::`vftable'
0x1004201f2  mov     [r11-40h], rax
0x1004201f6  movups  xmm0, xmmword ptr [rdx]
0x1004201f9  movups  [rsp+88h+var_20], xmm0
0x1004201fe  mov     [rsp+88h+var_58], 1; char
0x100420203  mov     [rsp+88h+var_60], 0; char
0x100420208  mov     [rsp+88h+var_68], 0FFh; char
0x10042020d  mov     r9b, 1
0x100420210  xor     r8d, r8d
0x100420213  lea     rdx, [r11-40h]; int
0x100420217  mov     rcx, [rcx]; int
0x10042021a  call    ??$InternalPopulate@VCGeometrySinkD@@@@YAJAEBUGeoData@@PEAVCGeometrySinkD@@W4MGL_WINDING_RULE@@_NE33@Z; InternalPopulate<CGeometrySinkD>(GeoData const &,CGeometrySinkD *,MGL_WINDING_RULE,bool,uchar,bool,bool)
0x10042021f  nop
0x100420220  mov     [rsp+88h+var_40], rbx
0x100420225  mov     rcx, [rsp+88h+var_10]
0x10042022a  xor     rcx, rsp; StackCookie
0x10042022d  call    __security_check_cookie
0x100420232  add     rsp, 80h
0x100420239  pop     rbx
0x10042023a  retn
```
