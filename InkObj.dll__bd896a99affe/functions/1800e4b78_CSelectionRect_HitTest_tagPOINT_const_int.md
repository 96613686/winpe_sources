# CSelectionRect::HitTest(tagPOINT const &,int)

- ea: `0x1800e4b78`
- end: `0x1800e4e56`
- name: `?HitTest@CSelectionRect@@QEAA?AW4SelectionHitResult@@AEBUtagPOINT@@H@Z`
- size: `734`
- prototype: `enum SelectionHitResult __fastcall(RECT *lprcSrc, const struct tagPOINT *, int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d7fd0`
- `0x1800dbb50`
- `0x1800e2340`
- `0x1800e6370`
- `0x1800ea7d0`
- `0x1800f2954`

## callees

- `0x1800e4b78`
- `0x180104f30`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800e4bba`
- `USER32!IsRectEmpty` at `0x1800e4bba`
- `USER32!InflateRect` at `0x1800e4c3e`
- `USER32!InflateRect` at `0x1800e4c63`
- `USER32!InflateRect` at `0x1800e4c83`
- `USER32!InflateRect` at `0x1800e4c3e`
- `USER32!InflateRect` at `0x1800e4c63`
- `USER32!InflateRect` at `0x1800e4c83`
- `USER32!CopyRect` at `0x1800e4c29`
- `USER32!CopyRect` at `0x1800e4c4e`
- `USER32!CopyRect` at `0x1800e4c73`
- `USER32!CopyRect` at `0x1800e4c29`
- `USER32!CopyRect` at `0x1800e4c4e`
- `USER32!CopyRect` at `0x1800e4c73`
- `USER32!PtInRect` at `0x1800e4dfe`
- `USER32!PtInRect` at `0x1800e4dfe`

## pseudocode

```c
__int64 __fastcall CSelectionRect::HitTest(RECT *lprcSrc, const struct tagPOINT *a2, int a3)
{
  unsigned int v3; // edi
  int v5; // eax
  int v6; // edi
  int v7; // eax
  bool v8; // zf
  int v9; // esi
  int v10; // r12d
  int v11; // eax
  int v12; // ebx
  LONG v13; // eax
  LONG v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+24h] [rbp-DCh]
  int v17; // [rsp+28h] [rbp-D8h]
  struct tagRECT rcDst; // [rsp+40h] [rbp-C0h] BYREF
  struct tagRECT rc; // [rsp+50h] [rbp-B0h] BYREF
  struct tagRECT v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+70h] [rbp-90h]
  _DWORD v25[21]; // [rsp+74h] [rbp-8Ch] BYREF
  int v26; // [rsp+C8h] [rbp-38h]
  int v27; // [rsp+CCh] [rbp-34h]
  int v28; // [rsp+D0h] [rbp-30h]
  int v29; // [rsp+D4h] [rbp-2Ch]
  int v30; // [rsp+D8h] [rbp-28h]
  int v31; // [rsp+DCh] [rbp-24h]
  int v32; // [rsp+E0h] [rbp-20h]
  int v33; // [rsp+E4h] [rbp-1Ch]
  int v34; // [rsp+E8h] [rbp-18h]
  int v35; // [rsp+ECh] [rbp-14h]
  int v36; // [rsp+F0h] [rbp-10h]
  int v37; // [rsp+F4h] [rbp-Ch]
  int v38; // [rsp+F8h] [rbp-8h]
  int v39; // [rsp+FCh] [rbp-4h]
  int v40; // [rsp+100h] [rbp+0h]
  int v41; // [rsp+104h] [rbp+4h]
  int v42; // [rsp+108h] [rbp+8h]
  int v43; // [rsp+10Ch] [rbp+Ch]
  int v44; // [rsp+110h] [rbp+10h]
  LONG left; // [rsp+114h] [rbp+14h]
  LONG top; // [rsp+118h] [rbp+18h]
  int v47; // [rsp+11Ch] [rbp+1Ch]
  int v48; // [rsp+120h] [rbp+20h]

  v3 = 0;
  v15 = 0;
  if ( !IsRectEmpty(lprcSrc) )
  {
    v5 = (lprcSrc[4].left + 1) / 2;
    rc = 0;
    v6 = v5;
    v7 = (lprcSrc[4].top + 1) / 2;
    v8 = lprcSrc[3].top == 0;
    v9 = v7;
    v23 = 0;
    rcDst = 0;
    if ( v8 )
    {
      v16 = (lprcSrc[3].bottom + 1) / 2;
      v17 = (lprcSrc[3].right + 1) / 2;
    }
    else
    {
      v16 = v7;
      v17 = v6;
    }
    CopyRect(&rcDst, lprcSrc);
    InflateRect(&rcDst, 8, 8);
    CopyRect(&rc, &rcDst);
    InflateRect(&rc, -v6, -v9);
    CopyRect(&v23, &rcDst);
    InflateRect(&v23, v6, v9);
    v25[5] = v23.left + 1;
    v10 = (rcDst.right + rcDst.left) / 2;
    v25[10] = v23.left + 1;
    v11 = (rcDst.bottom + rcDst.top) / 2;
    v25[1] = v23.top + 1;
    v25[11] = v23.top + 1;
    v24 = 3;
    v25[0] = rc.right + 1;
    v25[6] = rc.bottom + 1;
    v25[16] = rc.bottom + 1;
    v25[2] = v23.right;
    v25[20] = v23.left + 2;
    v27 = rc.left - 1;
    v30 = rc.right + 2;
    v25[3] = rc.top;
    v25[4] = 4;
    v25[7] = rc.left;
    v25[8] = v23.bottom;
    v25[9] = 1;
    v25[12] = rc.left;
    v25[13] = rc.top;
    v25[14] = 2;
    v25[15] = rc.right + 1;
    v25[17] = v23.right;
    v25[18] = v23.bottom;
    v25[19] = 6;
    v26 = v11 - v16 + 1;
    v28 = v11 + v16;
    v29 = 5;
    v31 = v26;
    v32 = v23.right - 1;
    v33 = v11 + v16;
    v36 = v23.top + 2;
    v34 = 7;
    v35 = v10 - v17 + 1;
    v38 = rc.top - 1;
    v41 = rc.bottom + 2;
    v43 = v23.bottom - 1;
    left = rcDst.left;
    top = rcDst.top;
    v37 = v10 + v17;
    v47 = rcDst.right + 1;
    v39 = 8;
    v48 = rcDst.bottom + 1;
    v12 = 0;
    v40 = v35;
    v42 = v10 + v17;
    v44 = 9;
    while ( v12 < 9 )
    {
      if ( PtInRect((const RECT *)&v25[5 * v12], *a2) )
      {
        v13 = v25[5 * v12 - 1];
        v15 = v13;
        goto LABEL_11;
      }
      ++v12;
    }
    v13 = 0;
LABEL_11:
    v3 = v15;
    if ( a3 )
      lprcSrc[4].right = v13;
  }
  return v3;
}

```

## disassembly

```asm
0x1800e4b78  mov     [rsp-8+arg_10], rbx
0x1800e4b7d  push    rbp
0x1800e4b7e  push    rsi
0x1800e4b7f  push    rdi
0x1800e4b80  push    r12
0x1800e4b82  push    r13
0x1800e4b84  push    r14
0x1800e4b86  push    r15
0x1800e4b88  lea     rbp, [rsp-40h]
0x1800e4b8d  sub     rsp, 140h
0x1800e4b94  mov     rax, cs:__security_cookie
0x1800e4b9b  xor     rax, rsp
0x1800e4b9e  mov     [rbp+70h+var_40], rax
0x1800e4ba2  xor     edi, edi
0x1800e4ba4  mov     [rsp+170h+var_144], r8d
0x1800e4ba9  mov     [rsp+170h+var_150], edi
0x1800e4bad  mov     rbx, rcx
0x1800e4bb0  mov     [rsp+170h+var_140], rdx
0x1800e4bb5  mov     [rsp+170h+var_138], rcx
0x1800e4bba  call    cs:__imp_IsRectEmpty
0x1800e4bc0  test    eax, eax
0x1800e4bc2  jnz     loc_1800E4E2D
0x1800e4bc8  mov     eax, [rbx+40h]
0x1800e4bcb  lea     r14d, [rdi+2]
0x1800e4bcf  inc     eax
0x1800e4bd1  xorps   xmm0, xmm0
0x1800e4bd4  cdq
0x1800e4bd5  xorps   xmm1, xmm1
0x1800e4bd8  idiv    r14d
0x1800e4bdb  movups  xmmword ptr [rsp+170h+rc.left], xmm0
0x1800e4be0  mov     edi, eax
0x1800e4be2  mov     eax, [rbx+44h]
0x1800e4be5  inc     eax
0x1800e4be7  cdq
0x1800e4be8  idiv    r14d
0x1800e4beb  cmp     dword ptr [rbx+34h], 0
0x1800e4bef  mov     esi, eax
0x1800e4bf1  movups  xmmword ptr [rsp+170h+var_110.left], xmm1
0x1800e4bf6  movups  xmmword ptr [rsp+170h+rcDst.left], xmm0
0x1800e4bfb  jz      short loc_1800E4C07
0x1800e4bfd  mov     [rsp+170h+var_14C], eax
0x1800e4c01  mov     [rsp+170h+var_148], edi
0x1800e4c05  jmp     short loc_1800E4C21
0x1800e4c07  mov     eax, [rbx+3Ch]
0x1800e4c0a  inc     eax
0x1800e4c0c  cdq
0x1800e4c0d  idiv    r14d
0x1800e4c10  mov     [rsp+170h+var_14C], eax
0x1800e4c14  mov     eax, [rbx+38h]
0x1800e4c17  inc     eax
0x1800e4c19  cdq
0x1800e4c1a  idiv    r14d
0x1800e4c1d  mov     [rsp+170h+var_148], eax
0x1800e4c21  mov     rdx, rbx; lprcSrc
0x1800e4c24  lea     rcx, [rsp+170h+rcDst]; lprcDst
0x1800e4c29  call    cs:__imp_CopyRect
0x1800e4c2f  mov     eax, 8
0x1800e4c34  lea     rcx, [rsp+170h+rcDst]; lprc
0x1800e4c39  mov     r8d, eax; dy
0x1800e4c3c  mov     edx, eax; dx
0x1800e4c3e  call    cs:__imp_InflateRect
0x1800e4c44  lea     rdx, [rsp+170h+rcDst]; lprcSrc
0x1800e4c49  lea     rcx, [rsp+170h+rc]; lprcDst
0x1800e4c4e  call    cs:__imp_CopyRect
0x1800e4c54  mov     r8d, esi
0x1800e4c57  lea     rcx, [rsp+170h+rc]; lprc
0x1800e4c5c  mov     edx, edi
0x1800e4c5e  neg     r8d; dy
0x1800e4c61  neg     edx; dx
0x1800e4c63  call    cs:__imp_InflateRect
0x1800e4c69  lea     rdx, [rsp+170h+rcDst]; lprcSrc
0x1800e4c6e  lea     rcx, [rsp+170h+var_110]; lprcDst
0x1800e4c73  call    cs:__imp_CopyRect
0x1800e4c79  mov     r8d, esi; dy
0x1800e4c7c  lea     rcx, [rsp+170h+var_110]; lprc
0x1800e4c81  mov     edx, edi; dx
0x1800e4c83  call    cs:__imp_InflateRect
0x1800e4c89  mov     eax, [rsp+170h+rcDst.left]
0x1800e4c8d  add     eax, [rsp+170h+rcDst.right]
0x1800e4c91  mov     r9d, [rsp+170h+rc.left]
0x1800e4c96  cdq
0x1800e4c97  mov     r8d, [rsp+170h+var_110.left]
0x1800e4c9c  mov     edi, [rsp+170h+rc.right]
0x1800e4ca0  mov     r11d, [rsp+170h+var_110.right]
0x1800e4ca5  mov     r15d, [rsp+170h+rc.top]
0x1800e4caa  mov     esi, [rsp+170h+var_110.bottom]
0x1800e4cae  lea     ecx, [r8+1]
0x1800e4cb2  mov     r13d, [rsp+170h+var_110.top]
0x1800e4cb7  lea     r10d, [rdi+1]
0x1800e4cbb  idiv    r14d
0x1800e4cbe  mov     [rbp+70h+var_E8], ecx
0x1800e4cc1  mov     r12d, eax
0x1800e4cc4  mov     [rbp+70h+var_D4], ecx
0x1800e4cc7  mov     eax, [rsp+170h+rcDst.top]
0x1800e4ccb  add     eax, [rsp+170h+rcDst.bottom]
0x1800e4ccf  mov     ecx, [rsp+170h+var_14C]
0x1800e4cd3  cdq
0x1800e4cd4  idiv    r14d
0x1800e4cd7  mov     r14d, [rsp+170h+rc.bottom]
0x1800e4cdc  lea     edx, [r13+1]
0x1800e4ce0  mov     ebx, eax
0x1800e4ce2  mov     [rsp+170h+var_F8], edx
0x1800e4ce6  mov     [rbp+70h+var_D0], edx
0x1800e4ce9  mov     edx, ebx
0x1800e4ceb  sub     edx, ecx
0x1800e4ced  mov     [rsp+170h+var_100], 3
0x1800e4cf5  lea     eax, [r14+1]
0x1800e4cf9  mov     [rsp+170h+var_FC], r10d
0x1800e4cfe  mov     [rbp+70h+var_E4], eax
0x1800e4d01  inc     edx
0x1800e4d03  mov     [rbp+70h+var_BC], eax
0x1800e4d06  add     ecx, ebx
0x1800e4d08  lea     eax, [r8+2]
0x1800e4d0c  mov     [rsp+170h+var_F4], r11d
0x1800e4d11  mov     [rbp+70h+var_AC], eax
0x1800e4d14  lea     eax, [r9-1]
0x1800e4d18  mov     [rbp+70h+var_A4], eax
0x1800e4d1b  lea     eax, [rdi+2]
0x1800e4d1e  mov     [rbp+70h+var_98], eax
0x1800e4d21  mov     [rbp+70h+var_F0], r15d
0x1800e4d25  mov     [rbp+70h+var_EC], 4
0x1800e4d2c  mov     [rbp+70h+var_E0], r9d
0x1800e4d30  mov     [rbp+70h+var_DC], esi
0x1800e4d33  mov     [rbp+70h+var_D8], 1
0x1800e4d3a  mov     [rbp+70h+var_CC], r9d
0x1800e4d3e  mov     [rbp+70h+var_C8], r15d
0x1800e4d42  mov     [rbp+70h+var_C4], 2
0x1800e4d49  mov     [rbp+70h+var_C0], r10d
0x1800e4d4d  mov     [rbp+70h+var_B8], r11d
0x1800e4d51  mov     [rbp+70h+var_B4], esi
0x1800e4d54  mov     [rbp+70h+var_B0], 6
0x1800e4d5b  mov     [rbp+70h+var_A8], edx
0x1800e4d5e  mov     [rbp+70h+var_A0], ecx
0x1800e4d61  mov     [rbp+70h+var_9C], 5
0x1800e4d68  mov     [rbp+70h+var_94], edx
0x1800e4d6b  lea     eax, [r11-1]
0x1800e4d6f  mov     [rbp+70h+var_90], eax
0x1800e4d72  mov     edx, r12d
0x1800e4d75  lea     eax, [r13+2]
0x1800e4d79  mov     [rbp+70h+var_8C], ecx
0x1800e4d7c  mov     ecx, [rsp+170h+var_148]
0x1800e4d80  sub     edx, ecx
0x1800e4d82  mov     [rbp+70h+var_80], eax
0x1800e4d85  inc     edx
0x1800e4d87  add     ecx, r12d
0x1800e4d8a  mov     [rbp+70h+var_88], 7
0x1800e4d91  lea     eax, [r15-1]
0x1800e4d95  mov     [rbp+70h+var_84], edx
0x1800e4d98  mov     [rbp+70h+var_78], eax
0x1800e4d9b  lea     eax, [r14+2]
0x1800e4d9f  mov     [rbp+70h+var_6C], eax
0x1800e4da2  lea     eax, [rsi-1]
0x1800e4da5  mov     rsi, [rsp+170h+var_140]
0x1800e4daa  mov     [rbp+70h+var_64], eax
0x1800e4dad  mov     eax, [rsp+170h+rcDst.left]
0x1800e4db1  mov     [rbp+70h+var_5C], eax
0x1800e4db4  mov     eax, [rsp+170h+rcDst.top]
0x1800e4db8  mov     [rbp+70h+var_58], eax
0x1800e4dbb  mov     eax, [rsp+170h+rcDst.right]
0x1800e4dbf  inc     eax
0x1800e4dc1  mov     [rbp+70h+var_7C], ecx
0x1800e4dc4  mov     [rbp+70h+var_54], eax
0x1800e4dc7  mov     eax, [rsp+170h+rcDst.bottom]
0x1800e4dcb  inc     eax
0x1800e4dcd  mov     [rbp+70h+var_74], 8
0x1800e4dd4  mov     [rbp+70h+var_50], eax
0x1800e4dd7  xor     ebx, ebx
0x1800e4dd9  mov     [rbp+70h+var_70], edx
0x1800e4ddc  mov     [rbp+70h+var_68], ecx
0x1800e4ddf  mov     [rbp+70h+var_60], 9
0x1800e4de6  cmp     ebx, 9
0x1800e4de9  jge     short loc_1800E4E16
0x1800e4deb  mov     rdx, [rsi]; pt
0x1800e4dee  lea     rcx, [rsp+170h+var_FC]
0x1800e4df3  movsxd  rax, ebx
0x1800e4df6  lea     rdi, [rax+rax*4]
0x1800e4dfa  lea     rcx, [rcx+rdi*4]; lprc
0x1800e4dfe  call    cs:__imp_PtInRect
0x1800e4e04  test    eax, eax
0x1800e4e06  jnz     short loc_1800E4E0C
0x1800e4e08  inc     ebx
0x1800e4e0a  jmp     short loc_1800E4DE6
0x1800e4e0c  mov     eax, [rsp+rdi*4+170h+var_100]
0x1800e4e10  mov     [rsp+170h+var_150], eax
0x1800e4e14  jmp     short loc_1800E4E1A
0x1800e4e16  mov     eax, [rsp+170h+var_150]
0x1800e4e1a  cmp     [rsp+170h+var_144], 0
0x1800e4e1f  mov     edi, [rsp+170h+var_150]
0x1800e4e23  jz      short loc_1800E4E2D
0x1800e4e25  mov     rcx, [rsp+170h+var_138]
0x1800e4e2a  mov     [rcx+48h], eax
0x1800e4e2d  mov     eax, edi
0x1800e4e2f  mov     rcx, [rbp+70h+var_40]
0x1800e4e33  xor     rcx, rsp; StackCookie
0x1800e4e36  call    __security_check_cookie
0x1800e4e3b  mov     rbx, [rsp+170h+arg_10]
0x1800e4e43  add     rsp, 140h
0x1800e4e4a  pop     r15
0x1800e4e4c  pop     r14
0x1800e4e4e  pop     r13
0x1800e4e50  pop     r12
0x1800e4e52  pop     rdi
0x1800e4e53  pop     rsi
0x1800e4e54  pop     rbp
0x1800e4e55  retn
```
