# CLockScreenHistory::_s_DrawImage(HDC__ *,uint,uint,bool,HBITMAP__ *)

- ea: `0x1800bb2d0`
- end: `0x1800bb4bc`
- name: `?_s_DrawImage@CLockScreenHistory@@KAXPEAUHDC__@@II_NPEAUHBITMAP__@@@Z`
- size: `492`
- prototype: `void __usercall(HDC hdcDest@<rcx>, unsigned int wDest@<edx>, unsigned int hSrc@<r8d>, bool@<r9b>, HBITMAP)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800bb1dc`

## callees

- `0x180050ba0`
- `0x180051524`
- `0x1800bb2d0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800bb30f`
- `GDI32!CreateCompatibleDC` at `0x1800bb30f`
- `GDI32!DeleteDC` at `0x1800bb48c`
- `GDI32!DeleteDC` at `0x1800bb48c`
- `GDI32!SelectObject` at `0x1800bb327`
- `GDI32!SelectObject` at `0x1800bb483`
- `GDI32!SelectObject` at `0x1800bb327`
- `GDI32!SelectObject` at `0x1800bb483`
- `GDI32!GetObjectW` at `0x1800bb34d`
- `GDI32!GetObjectW` at `0x1800bb34d`
- `GDI32!StretchBlt` at `0x1800bb477`
- `GDI32!StretchBlt` at `0x1800bb477`

## pseudocode

```c
void __fastcall CLockScreenHistory::_s_DrawImage(HDC hdcDest, int wDest, int hSrc, unsigned __int8 a4, HGDIOBJ h)
{
  int v6; // r12d
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HGDIOBJ v11; // rbp
  float v12; // xmm6_4
  int v13; // eax
  float v14; // xmm4_4
  int v15; // ebx
  signed int v16; // r9d
  int v17; // ecx
  int ySrc; // r11d
  int v19; // r10d
  int xSrc; // eax
  _BYTE pv[4]; // [rsp+60h] [rbp-C8h] BYREF
  int v22; // [rsp+64h] [rbp-C4h]
  int v23; // [rsp+68h] [rbp-C0h]

  v6 = a4;
  CompatibleDC = CreateCompatibleDC(hdcDest);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
  {
    v11 = SelectObject(CompatibleDC, h);
    memset_0(pv, 0, 0x68u);
    if ( GetObjectW(h, 104, pv) )
    {
      v12 = (float)hSrc;
      v13 = v23;
      if ( v22 > v23 )
        v13 = v22;
      v14 = fmaxf(
              fmaxf(
                fmaxf(
                  v12 * (float)((float)v22 / (float)v23),
                  (float)(1.0 / (float)((float)v22 / (float)v23)) * (float)wDest),
                v12),
              (float)wDest)
          / (float)v13;
      v15 = (int)(float)((float)((float)wDest - (float)(v14 * (float)v22)) / (float)(v14 + v14));
      v16 = v22 + 2 * v15;
      v17 = (int)(float)((float)(v12 - (float)(v14 * (float)v23)) / (float)(v14 * 3.0));
      ySrc = -v17;
      if ( v17 >= 0 )
        ySrc = 0;
      if ( wDest < v16 )
        v16 = wDest;
      v19 = v17 + v23 + 2 * v17;
      if ( hSrc < v19 )
        v19 = hSrc;
      xSrc = ((_BYTE)v6 != 0 ? v16 - 1 : 0) - v15;
      if ( v15 >= 0 )
        xSrc = (_BYTE)v6 != 0 ? v16 - 1 : 0;
      StretchBlt(hdcDest, 0, 0, wDest, hSrc, hdcSrc, xSrc, ySrc, v16 * (2 * (v6 ^ 1) - 1), v19, 0xCC0020u);
    }
    SelectObject(hdcSrc, v11);
    DeleteDC(hdcSrc);
  }
}

```

## disassembly

```asm
0x1800bb2d0  mov     rax, rsp
0x1800bb2d3  push    rbx
0x1800bb2d4  push    rbp
0x1800bb2d5  push    rsi
0x1800bb2d6  push    rdi
0x1800bb2d7  push    r12
0x1800bb2d9  push    r14
0x1800bb2db  push    r15
0x1800bb2dd  sub     rsp, 0F0h
0x1800bb2e4  movaps  xmmword ptr [rax-48h], xmm6
0x1800bb2e8  mov     rax, cs:__security_cookie
0x1800bb2ef  xor     rax, rsp
0x1800bb2f2  mov     [rsp+128h+var_58], rax
0x1800bb2fa  mov     rbx, [rsp+128h+h]
0x1800bb302  mov     rsi, rcx
0x1800bb305  movzx   r12d, r9b
0x1800bb309  mov     r15d, r8d
0x1800bb30c  mov     r14d, edx
0x1800bb30f  call    cs:__imp_CreateCompatibleDC
0x1800bb315  mov     rdi, rax
0x1800bb318  test    rax, rax
0x1800bb31b  jz      loc_1800BB492
0x1800bb321  mov     rdx, rbx; h
0x1800bb324  mov     rcx, rax; hdc
0x1800bb327  call    cs:__imp_SelectObject
0x1800bb32d  xor     edx, edx; Val
0x1800bb32f  lea     rcx, [rsp+128h+pv]; void *
0x1800bb334  mov     rbp, rax
0x1800bb337  lea     r8d, [rdx+68h]; Size
0x1800bb33b  call    memset_0
0x1800bb340  lea     r8, [rsp+128h+pv]; pv
0x1800bb345  mov     edx, 68h ; 'h'; c
0x1800bb34a  mov     rcx, rbx; h
0x1800bb34d  call    cs:__imp_GetObjectW
0x1800bb353  test    eax, eax
0x1800bb355  jz      loc_1800BB47D
0x1800bb35b  mov     edx, [rsp+128h+var_C4]
0x1800bb35f  xorps   xmm6, xmm6
0x1800bb362  mov     r8d, [rsp+128h+var_C0]
0x1800bb367  xorps   xmm3, xmm3
0x1800bb36a  movss   xmm0, cs:__real@3f800000
0x1800bb372  cmp     edx, r8d
0x1800bb375  cvtsi2ss xmm6, r15
0x1800bb37a  mov     eax, r8d
0x1800bb37d  mov     [rsp+128h+rop], 0CC0020h; rop
0x1800bb385  cmovg   eax, edx
0x1800bb388  movd    xmm2, edx
0x1800bb38c  movd    xmm5, r8d
0x1800bb391  movaps  xmm4, xmm6
0x1800bb394  cvtdq2ps xmm2, xmm2
0x1800bb397  cvtdq2ps xmm5, xmm5
0x1800bb39a  movaps  xmm1, xmm2
0x1800bb39d  divss   xmm1, xmm5
0x1800bb3a1  cvtsi2ss xmm3, r14
0x1800bb3a6  divss   xmm0, xmm1
0x1800bb3aa  mulss   xmm4, xmm1
0x1800bb3ae  mulss   xmm0, xmm3
0x1800bb3b2  maxss   xmm4, xmm0
0x1800bb3b6  movd    xmm0, eax
0x1800bb3ba  xor     eax, eax
0x1800bb3bc  cvtdq2ps xmm0, xmm0
0x1800bb3bf  maxss   xmm4, xmm6
0x1800bb3c3  maxss   xmm4, xmm3
0x1800bb3c7  divss   xmm4, xmm0
0x1800bb3cb  movaps  xmm1, xmm4
0x1800bb3ce  movaps  xmm0, xmm4
0x1800bb3d1  mulss   xmm1, xmm2
0x1800bb3d5  addss   xmm0, xmm4
0x1800bb3d9  subss   xmm3, xmm1
0x1800bb3dd  movaps  xmm1, xmm4
0x1800bb3e0  mulss   xmm4, cs:__real@40400000
0x1800bb3e8  mulss   xmm1, xmm5
0x1800bb3ec  divss   xmm3, xmm0
0x1800bb3f0  subss   xmm6, xmm1
0x1800bb3f4  cvttss2si ebx, xmm3
0x1800bb3f8  divss   xmm6, xmm4
0x1800bb3fc  lea     r9d, [rdx+rbx*2]
0x1800bb400  cvttss2si ecx, xmm6
0x1800bb404  mov     r11d, ecx
0x1800bb407  neg     r11d
0x1800bb40a  test    ecx, ecx
0x1800bb40c  lea     r10d, [r8+rcx*2]
0x1800bb410  cmovns  r11d, eax
0x1800bb414  cmp     r14d, r9d
0x1800bb417  mov     al, r12b
0x1800bb41a  cmovl   r9d, r14d
0x1800bb41e  add     r10d, ecx
0x1800bb421  cmp     r15d, r10d
0x1800bb424  cmovl   r10d, r15d
0x1800bb428  neg     al
0x1800bb42a  mov     [rsp+128h+hSrc], r10d; hSrc
0x1800bb42f  lea     ecx, [r9-1]
0x1800bb433  sbb     r8d, r8d
0x1800bb436  mov     eax, r12d
0x1800bb439  xor     eax, 1
0x1800bb43c  and     r8d, ecx
0x1800bb43f  mov     rcx, rsi; hdcDest
0x1800bb442  lea     edx, ds:0FFFFFFFFFFFFFFFFh[rax*2]
0x1800bb449  mov     eax, r8d
0x1800bb44c  imul    edx, r9d
0x1800bb450  sub     eax, ebx
0x1800bb452  test    ebx, ebx
0x1800bb454  mov     r9d, r14d; wDest
0x1800bb457  cmovns  eax, r8d
0x1800bb45b  xor     r8d, r8d; yDest
0x1800bb45e  mov     [rsp+128h+wSrc], edx; wSrc
0x1800bb462  xor     edx, edx; xDest
0x1800bb464  mov     [rsp+128h+ySrc], r11d; ySrc
0x1800bb469  mov     [rsp+128h+xSrc], eax; xSrc
0x1800bb46d  mov     [rsp+128h+hdcSrc], rdi; hdcSrc
0x1800bb472  mov     [rsp+128h+hDest], r15d; hDest
0x1800bb477  call    cs:__imp_StretchBlt
0x1800bb47d  mov     rdx, rbp; h
0x1800bb480  mov     rcx, rdi; hdc
0x1800bb483  call    cs:__imp_SelectObject
0x1800bb489  mov     rcx, rdi; hdc
0x1800bb48c  call    cs:__imp_DeleteDC
0x1800bb492  mov     rcx, [rsp+128h+var_58]
0x1800bb49a  xor     rcx, rsp; StackCookie
0x1800bb49d  call    __security_check_cookie
0x1800bb4a2  movaps  xmm6, [rsp+128h+var_48]
0x1800bb4aa  add     rsp, 0F0h
0x1800bb4b1  pop     r15
0x1800bb4b3  pop     r14
0x1800bb4b5  pop     r12
0x1800bb4b7  pop     rdi
0x1800bb4b8  pop     rsi
0x1800bb4b9  pop     rbp
0x1800bb4ba  pop     rbx
0x1800bb4bb  retn
```
