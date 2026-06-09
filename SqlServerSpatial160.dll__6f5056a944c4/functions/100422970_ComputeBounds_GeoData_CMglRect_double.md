# ComputeBounds(GeoData,CMglRect<double> *)

- ea: `0x100422970`
- end: `0x100422af8`
- name: `?ComputeBounds@@YAJUGeoData@@PEAV?$CMglRect@N@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(int)`
- caller_count: `21`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10040dcf0`
- `0x10040de70`
- `0x10040e5c0`
- `0x10040ee80`
- `0x10040f200`
- `0x10040fad0`
- `0x1004102d0`
- `0x100410d70`
- `0x100411400`
- `0x100413e50`
- `0x100414150`
- `0x1004145a0`
- `0x100414770`
- `0x100415260`
- `0x100415550`
- `0x100415880`
- `0x100415d10`
- `0x1004162a0`
- `0x100423450`
- `0x1004284a0`
- `0x100429370`

## callees

- `0x100422970`
- `0x100425d60`
- `0x100468a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ComputeBounds(__int64 a1, double *a2)
{
  unsigned int v4; // ecx
  __int64 result; // rax
  double v6; // xmm0_8
  __int64 v7; // xmm2_8
  double v8; // xmm1_8
  double *v9; // rax
  double *v10; // rdx
  int v11[2]; // [rsp+50h] [rbp-58h] BYREF
  double v12; // [rsp+58h] [rbp-50h]
  __int128 v13; // [rsp+60h] [rbp-48h]
  double v14; // [rsp+70h] [rbp-38h]
  char v15; // [rsp+78h] [rbp-30h]

  v4 = 0;
  if ( *(_DWORD *)(a1 + 8) || *(_BYTE *)(*(_QWORD *)(a1 + 48) + 8LL) == 11 )
  {
    *(_QWORD *)v11 = &CBoundsModule::`vftable';
    v12 = DOUBLE_1_797693134862316e308;
    v13 = _xmm;
    v14 = DOUBLE_N1_797693134862316e308;
    v15 = 0;
    result = InternalPopulate<CGeometrySinkD>(a1, (__int64)v11, 0, 1u, 255, 0, 1);
    v4 = result;
    if ( (int)result < 0 )
    {
      _mm_lfence();
      *(_QWORD *)v11 = &IMglGeometrySink::`vftable';
      return result;
    }
    v6 = v14;
    v7 = *((_QWORD *)&v13 + 1);
    v8 = *(double *)&v13;
    if ( v12 <= *(double *)&v13 || *((double *)&v13 + 1) <= v14 )
    {
      v9 = a2 + 3;
      v10 = a2 + 1;
      if ( v15 )
      {
        v6 = NAN;
        *a2 = NAN;
        a2[2] = NAN;
        v8 = NAN;
      }
      else
      {
        *a2 = v12;
        *((_QWORD *)a2 + 2) = v7;
      }
    }
    else
    {
      v9 = a2 + 3;
      v10 = a2 + 1;
      a2[2] = 1.797693134862316e308;
      *a2 = 1.797693134862316e308;
      v6 = DOUBLE_2_225073858507201eN308;
      v8 = DOUBLE_2_225073858507201eN308;
    }
    *v10 = v8;
    *v9 = v6;
    *(_QWORD *)v11 = &IMglGeometrySink::`vftable';
  }
  return v4;
}

```

## disassembly

```asm
0x100422970  mov     rax, rsp
0x100422973  push    rdi
0x100422974  sub     rsp, 0A0h
0x10042297b  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x100422983  mov     [rax+18h], rbx
0x100422987  mov     [rax+20h], rsi
0x10042298b  mov     rax, cs:__security_cookie
0x100422992  xor     rax, rsp
0x100422995  mov     [rsp+0A8h+var_18], rax
0x10042299d  mov     rbx, rdx
0x1004229a0  mov     r10, rcx
0x1004229a3  xor     ecx, ecx
0x1004229a5  cmp     [r10+8], ecx
0x1004229a9  jnz     short loc_1004229B9
0x1004229ab  mov     rax, [r10+30h]
0x1004229af  cmp     byte ptr [rax+8], 0Bh
0x1004229b3  jnz     loc_100422AD1
0x1004229b9  lea     rdi, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x1004229c0  mov     qword ptr [rsp+0A8h+var_58], rdi
0x1004229c5  lea     rax, ??_7CGeometrySinkD@@6B@; const CGeometrySinkD::`vftable'
0x1004229cc  mov     qword ptr [rsp+0A8h+var_58], rax
0x1004229d1  lea     rsi, ??_7CBoundsModule@@6B@; const CBoundsModule::`vftable'
0x1004229d8  mov     qword ptr [rsp+0A8h+var_58], rsi
0x1004229dd  movsd   xmm0, cs:__real@7fefffffffffffff
0x1004229e5  movsd   [rsp+0A8h+var_50], xmm0
0x1004229eb  movaps  xmm1, cs:__xmm@7fefffffffffffffffefffffffffffff
0x1004229f2  movaps  [rsp+0A8h+var_48], xmm1
0x1004229f7  movsd   xmm0, cs:__real@ffefffffffffffff
0x1004229ff  movsd   [rsp+0A8h+var_38], xmm0
0x100422a05  mov     [rsp+0A8h+var_30], 0
0x100422a0a  mov     [rsp+0A8h+var_78], 1; char
0x100422a0f  mov     [rsp+0A8h+var_80], 0; char
0x100422a14  mov     [rsp+0A8h+var_88], 0FFh; char
0x100422a19  mov     r9b, 1
0x100422a1c  xor     r8d, r8d
0x100422a1f  lea     rdx, [rsp+0A8h+var_58]; int
0x100422a24  mov     rcx, r10; int
0x100422a27  call    ??$InternalPopulate@VCGeometrySinkD@@@@YAJAEBUGeoData@@PEAVCGeometrySinkD@@W4MGL_WINDING_RULE@@_NE33@Z; InternalPopulate<CGeometrySinkD>(GeoData const &,CGeometrySinkD *,MGL_WINDING_RULE,bool,uchar,bool,bool)
0x100422a2c  mov     ecx, eax
0x100422a2e  test    eax, eax
0x100422a30  jns     short loc_100422A44
0x100422a32  lfence
0x100422a35  mov     qword ptr [rsp+0A8h+var_58], rsi
0x100422a3a  mov     qword ptr [rsp+0A8h+var_58], rdi
0x100422a3f  jmp     loc_100422AD3
0x100422a44  movsd   xmm0, [rsp+0A8h+var_38]
0x100422a4a  movsd   xmm2, qword ptr [rsp+0A8h+var_48+8]
0x100422a50  movsd   xmm3, [rsp+0A8h+var_50]
0x100422a56  movsd   xmm1, qword ptr [rsp+0A8h+var_48]
0x100422a5c  comisd  xmm3, xmm1
0x100422a60  jbe     short loc_100422A8E
0x100422a62  comisd  xmm2, xmm0
0x100422a66  jbe     short loc_100422A8E
0x100422a68  lea     rax, [rbx+18h]
0x100422a6c  lea     rdx, [rbx+8]
0x100422a70  mov     r8, 7FEFFFFFFFFFFFFFh
0x100422a7a  mov     [rbx+10h], r8
0x100422a7e  mov     [rbx], r8
0x100422a81  movsd   xmm0, cs:__real@0010000000000000
0x100422a89  movaps  xmm1, xmm0
0x100422a8c  jmp     short loc_100422ABF
0x100422a8e  lea     rax, [rbx+18h]
0x100422a92  lea     rdx, [rbx+8]
0x100422a96  cmp     [rsp+0A8h+var_30], 0
0x100422a9b  jz      short loc_100422AB6
0x100422a9d  movss   xmm0, cs:?FLOAT_QNAN@@3MB; float const FLOAT_QNAN
0x100422aa5  cvtps2pd xmm0, xmm0
0x100422aa8  movsd   qword ptr [rbx], xmm0
0x100422aac  movsd   qword ptr [rbx+10h], xmm0
0x100422ab1  movaps  xmm1, xmm0
0x100422ab4  jmp     short loc_100422ABF
0x100422ab6  movsd   qword ptr [rbx], xmm3
0x100422aba  movsd   qword ptr [rbx+10h], xmm2
0x100422abf  movsd   qword ptr [rdx], xmm1
0x100422ac3  movsd   qword ptr [rax], xmm0
0x100422ac7  mov     qword ptr [rsp+0A8h+var_58], rsi
0x100422acc  mov     qword ptr [rsp+0A8h+var_58], rdi
0x100422ad1  mov     eax, ecx
0x100422ad3  mov     rcx, [rsp+0A8h+var_18]
0x100422adb  xor     rcx, rsp; StackCookie
0x100422ade  call    __security_check_cookie
0x100422ae3  lea     r11, [rsp+0A8h+var_8]
0x100422aeb  mov     rbx, [r11+20h]
0x100422aef  mov     rsi, [r11+28h]
0x100422af3  mov     rsp, r11
0x100422af6  pop     rdi
0x100422af7  retn
```
