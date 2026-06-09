# CSketchInk::OnDraw(ATL_DRAWINFO &)

- ea: `0x1800753f0`
- end: `0x1800758a8`
- name: `?OnDraw@CSketchInk@@UEAAJAEAUATL_DRAWINFO@@@Z`
- size: `1208`
- prototype: `__int64 __fastcall(CSketchInk *__hidden this, struct ATL_DRAWINFO *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002740`
- `0x180010350`
- `0x1800753f0`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075516`
- `USER32!OffsetRect` at `0x180075486`
- `USER32!OffsetRect` at `0x180075486`
- `GDI32!SetMapMode` at `0x180075572`
- `GDI32!SetMapMode` at `0x180075801`
- `GDI32!SetMapMode` at `0x180075572`
- `GDI32!SetMapMode` at `0x180075801`
- `GDI32!SetViewportOrgEx` at `0x18007558d`
- `GDI32!SetViewportOrgEx` at `0x18007581d`
- `GDI32!SetViewportOrgEx` at `0x18007558d`
- `GDI32!SetViewportOrgEx` at `0x18007581d`
- `GDI32!SetWindowOrgEx` at `0x18007550c`
- `GDI32!SetWindowOrgEx` at `0x1800755d1`
- `GDI32!SetWindowOrgEx` at `0x180075855`
- `GDI32!SetWindowOrgEx` at `0x18007550c`
- `GDI32!SetWindowOrgEx` at `0x1800755d1`
- `GDI32!SetWindowOrgEx` at `0x180075855`
- `GDI32!SetWindowExtEx` at `0x180075547`
- `GDI32!SetWindowExtEx` at `0x1800755f5`
- `GDI32!SetWindowExtEx` at `0x180075871`
- `GDI32!SetWindowExtEx` at `0x180075547`
- `GDI32!SetWindowExtEx` at `0x1800755f5`
- `GDI32!SetWindowExtEx` at `0x180075871`
- `GDI32!GetDeviceCaps` at `0x180075431`
- `GDI32!GetDeviceCaps` at `0x180075431`
- `GDI32!SetViewportExtEx` at `0x1800755b4`
- `GDI32!SetViewportExtEx` at `0x180075839`
- `GDI32!SetViewportExtEx` at `0x1800755b4`
- `GDI32!SetViewportExtEx` at `0x180075839`
- `GDI32!SelectObject` at `0x18007569c`
- `GDI32!SelectObject` at `0x180075795`
- `GDI32!SelectObject` at `0x18007569c`
- `GDI32!SelectObject` at `0x180075795`
- `GDI32!Polyline` at `0x18007576d`
- `GDI32!Polyline` at `0x18007576d`
- `GDI32!DeleteObject` at `0x1800757a3`
- `GDI32!DeleteObject` at `0x1800757a3`
- `GDI32!CreatePenIndirect` at `0x180075687`
- `GDI32!CreatePenIndirect` at `0x180075687`
- `GDI32!MoveToEx` at `0x1800757c7`
- `GDI32!MoveToEx` at `0x1800757c7`
- `GDI32!LineTo` at `0x1800757d8`
- `GDI32!LineTo` at `0x1800757d8`

## pseudocode

```c
signed int __fastcall CSketchInk::OnDraw(CSketchInk *this, HDC *a2)
{
  HDC *v2; // rbx
  CSketchInk *v3; // r15
  int DeviceCaps; // eax
  struct tagRECT v5; // xmm0
  int v6; // edi
  unsigned int v7; // r12d
  int right; // ecx
  int bottom; // eax
  LONG v10; // r14d
  int v11; // r15d
  signed int result; // eax
  unsigned int i; // r13d
  __int64 v14; // rcx
  __int64 v15; // rdi
  unsigned __int64 v16; // rsi
  HPEN v17; // rax
  HGDIOBJ v18; // r12
  int *v19; // r14
  unsigned int v20; // r9d
  __int64 v21; // r8
  int v22; // ebx
  LONG v23; // r13d
  __int64 v24; // rdi
  int v25; // r15d
  HGDIOBJ v26; // rax
  unsigned int v27; // [rsp+20h] [rbp-59h]
  LONG v28; // [rsp+24h] [rbp-55h]
  unsigned int v29; // [rsp+28h] [rbp-51h]
  int iMode; // [rsp+2Ch] [rbp-4Dh]
  struct tagPOINT pt; // [rsp+30h] [rbp-49h] BYREF
  tagSIZE sz; // [rsp+38h] [rbp-41h] BYREF
  LONG left; // [rsp+40h] [rbp-39h]
  int v34; // [rsp+44h] [rbp-35h]
  CSketchInk *v35; // [rsp+48h] [rbp-31h]
  struct tagPOINT v36; // [rsp+50h] [rbp-29h] BYREF
  struct tagSIZE v37; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int64 v38; // [rsp+60h] [rbp-19h]
  HDC *v39; // [rsp+68h] [rbp-11h]
  struct tagRECT rc; // [rsp+70h] [rbp-9h] BYREF
  LOGPEN plpen; // [rsp+80h] [rbp+7h] BYREF

  v2 = a2;
  v39 = a2;
  v3 = this;
  v35 = this;
  DeviceCaps = GetDeviceCaps(a2[4], 2);
  v5 = *(struct tagRECT *)((char *)v3 + 364);
  v34 = DeviceCaps;
  v6 = DeviceCaps;
  pt = 0;
  v36 = 0;
  v7 = 1;
  sz = 0;
  v27 = 1;
  v37 = 0;
  rc = v5;
  v38 = HIDWORD(*(_QWORD *)&v5.left);
  left = v5.left;
  OffsetRect(&rc, -_mm_cvtsi128_si32((__m128i)v5), -v5.top);
  right = rc.right;
  bottom = rc.bottom;
  v10 = rc.right;
  if ( rc.right < rc.bottom )
    v10 = rc.bottom;
  v28 = v10;
  if ( v10 > 0x7FFF )
  {
    do
    {
      v7 *= 2;
      bottom = (int)((double)bottom * 0.5);
      v11 = bottom;
      right = (int)((double)right * 0.5);
      if ( right >= bottom )
        v11 = right;
      v28 = v11;
    }
    while ( v11 > 0x7FFF );
    v3 = v35;
    v10 = v28;
    rc.bottom = bottom;
    rc.right = right;
    v27 = v7;
  }
  if ( v6 == 5 )
  {
    if ( !SetWindowOrgEx(v2[4], rc.left, rc.top, &pt)
      || !SetWindowExtEx(v2[4], rc.right - rc.left, rc.bottom - rc.top, &sz) )
    {
      goto LABEL_10;
    }
    iMode = 0;
  }
  else
  {
    if ( !v2[5] )
      return -2147024809;
    iMode = SetMapMode(v2[4], 8);
    if ( !SetViewportOrgEx(v2[4], *(_DWORD *)v2[5], *((_DWORD *)v2[5] + 1), &v36)
      || !SetViewportExtEx(
            v2[4],
            *((_DWORD *)v2[5] + 2) - *(_DWORD *)v2[5],
            *((_DWORD *)v2[5] + 3) - *((_DWORD *)v2[5] + 1),
            &v37)
      || !SetWindowOrgEx(v2[4], rc.left, rc.top, &pt)
      || !SetWindowExtEx(v2[4], rc.right - rc.left, rc.bottom - rc.top, &sz) )
    {
      goto LABEL_10;
    }
  }
  plpen = 0;
  if ( *((_DWORD *)v3 + 96) && !*((_QWORD *)v3 + 49) )
    return -2147418113;
  for ( i = 0; ; ++i )
  {
    v29 = i;
    if ( i >= *((_DWORD *)v3 + 96) )
      break;
    v14 = *((_QWORD *)v3 + 49);
    v15 = 56LL * i;
    v16 = *(unsigned int *)(v14 + v15);
    if ( (_DWORD)v16 )
    {
      plpen.lopnStyle = 0;
      plpen.lopnWidth = *(POINT *)(v14 + v15 + 12);
      plpen.lopnColor = *(_DWORD *)(v14 + v15 + 8);
      if ( v10 > 0x7FFF )
      {
        plpen.lopnWidth.x /= v7;
        plpen.lopnWidth.y /= v7;
      }
      v17 = CreatePenIndirect(&plpen);
      v18 = v17;
      if ( v17 )
        v18 = SelectObject(v2[4], v17);
      v19 = (int *)WinMalloc(saturated_mul(v16, 8u));
      if ( !v19 )
        return -2147024882;
      if ( !*(_QWORD *)(*((_QWORD *)v3 + 49) + v15 + 24) )
        return -2147418113;
      v20 = 0;
      v21 = 0;
      v22 = v38;
      v23 = left;
      do
      {
        ++v20;
        v19[2 * v21] = (*(_DWORD *)(*(_QWORD *)(v15 + *((_QWORD *)v3 + 49) + 24) + 8 * v21) - v23) / v27;
        v19[2 * v21 + 1] = (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 49) + v15 + 24) + 8 * v21 + 4) - v22) / v27;
        ++v21;
      }
      while ( v20 < (unsigned int)v16 );
      v2 = v39;
      i = v29;
      if ( (unsigned int)v16 <= 1 )
      {
        MoveToEx(v39[4], *v19, v19[1], 0);
        LineTo(v2[4], *v19, v19[1]);
      }
      else
      {
        v24 = 0;
        v25 = 1000;
        do
        {
          if ( (int)v24 + 1000 < (unsigned int)v24 )
            break;
          if ( (int)v24 + 1000 > (unsigned int)v16 )
            v25 = v16 - v24;
          Polyline(v2[4], (const POINT *)&v19[2 * v24], v25);
          v24 = (unsigned int)(v24 + 999);
        }
        while ( (unsigned int)v16 > (unsigned int)v24 );
        v3 = v35;
      }
      WinFree(v19);
      if ( v18 )
      {
        v26 = SelectObject(v2[4], v18);
        if ( v26 )
          DeleteObject(v26);
      }
      v7 = v27;
    }
    v10 = v28;
  }
  if ( (v34 == 5
     || SetMapMode(v2[4], iMode)
     && SetViewportOrgEx(v2[4], v36.x, v36.y, 0)
     && SetViewportExtEx(v2[4], v37.cx, v37.cy, 0))
    && SetWindowOrgEx(v2[4], pt.x, pt.y, 0)
    && SetWindowExtEx(v2[4], sz.cx, sz.cy, 0) )
  {
    return 0;
  }
LABEL_10:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800753f0  mov     [rsp-8+arg_10], rbx
0x1800753f5  push    rbp
0x1800753f6  push    rsi
0x1800753f7  push    rdi
0x1800753f8  push    r12
0x1800753fa  push    r13
0x1800753fc  push    r14
0x1800753fe  push    r15
0x180075400  lea     rbp, [rsp-27h]
0x180075405  sub     rsp, 0A0h
0x18007540c  mov     rax, cs:__security_cookie
0x180075413  xor     rax, rsp
0x180075416  mov     [rbp+57h+var_40], rax
0x18007541a  mov     rbx, rdx
0x18007541d  mov     [rbp+57h+var_68], rdx
0x180075421  mov     r15, rcx
0x180075424  mov     [rbp+57h+var_88], rcx
0x180075428  mov     edx, 2; index
0x18007542d  mov     rcx, [rbx+20h]; hdc
0x180075431  call    cs:__imp_GetDeviceCaps
0x180075437  movups  xmm0, xmmword ptr [r15+16Ch]
0x18007543f  xor     esi, esi
0x180075441  mov     [rbp+57h+var_8C], eax
0x180075444  mov     edi, eax
0x180075446  mov     qword ptr [rbp+57h+pt.x], rsi
0x18007544a  movq    rax, xmm0
0x18007544f  movd    edx, xmm0
0x180075453  shr     rax, 20h
0x180075457  lea     rcx, [rbp+57h+rc]; lprc
0x18007545b  mov     r8d, eax
0x18007545e  mov     qword ptr [rbp+57h+var_80.x], rsi
0x180075462  mov     r12d, 1
0x180075468  mov     qword ptr [rbp+57h+sz.cx], rsi
0x18007546c  neg     r8d; dy
0x18007546f  mov     [rbp+57h+var_B0], r12d
0x180075473  neg     edx; dx
0x180075475  mov     qword ptr [rbp+57h+var_78.cx], rsi
0x180075479  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18007547d  mov     [rbp+57h+var_70], rax
0x180075481  movss   [rbp+57h+var_90], xmm0
0x180075486  call    cs:__imp_OffsetRect
0x18007548c  mov     ecx, [rbp+57h+rc.right]
0x18007548f  mov     edx, 7FFFh
0x180075494  mov     eax, [rbp+57h+rc.bottom]
0x180075497  mov     r14d, ecx
0x18007549a  cmp     ecx, eax
0x18007549c  cmovl   r14d, eax
0x1800754a0  mov     [rbp+57h+var_AC], r14d
0x1800754a4  cmp     r14d, edx
0x1800754a7  jle     short loc_1800754F8
0x1800754a9  movsd   xmm1, cs:__real@3fe0000000000000
0x1800754b1  movd    xmm0, eax
0x1800754b5  add     r12d, r12d
0x1800754b8  cvtdq2pd xmm0, xmm0
0x1800754bc  mulsd   xmm0, xmm1
0x1800754c0  cvttsd2si eax, xmm0
0x1800754c4  movd    xmm0, ecx
0x1800754c8  cvtdq2pd xmm0, xmm0
0x1800754cc  mov     r15d, eax
0x1800754cf  mulsd   xmm0, xmm1
0x1800754d3  cvttsd2si ecx, xmm0
0x1800754d7  cmp     ecx, eax
0x1800754d9  cmovge  r15d, ecx
0x1800754dd  mov     [rbp+57h+var_AC], r15d
0x1800754e1  cmp     r15d, edx
0x1800754e4  jg      short loc_1800754B1
0x1800754e6  mov     r15, [rbp+57h+var_88]
0x1800754ea  mov     r14d, [rbp+57h+var_AC]
0x1800754ee  mov     [rbp+57h+rc.bottom], eax
0x1800754f1  mov     [rbp+57h+rc.right], ecx
0x1800754f4  mov     [rbp+57h+var_B0], r12d
0x1800754f8  cmp     edi, 5
0x1800754fb  jnz     short loc_180075559
0x1800754fd  mov     r8d, [rbp+57h+rc.top]; y
0x180075501  lea     r9, [rbp+57h+pt]; lppt
0x180075505  mov     edx, [rbp+57h+rc.left]; x
0x180075508  mov     rcx, [rbx+20h]; hdc
0x18007550c  call    cs:__imp_SetWindowOrgEx
0x180075512  test    eax, eax
0x180075514  jnz     short loc_180075531
0x180075516  call    cs:__imp_GetLastError
0x18007551c  test    eax, eax
0x18007551e  jle     loc_180075881
0x180075524  movzx   eax, ax
0x180075527  or      eax, 80070000h
0x18007552c  jmp     loc_180075881
0x180075531  mov     r8d, [rbp+57h+rc.bottom]
0x180075535  lea     r9, [rbp+57h+sz]; lpsz
0x180075539  mov     edx, [rbp+57h+rc.right]
0x18007553c  sub     r8d, [rbp+57h+rc.top]; y
0x180075540  sub     edx, [rbp+57h+rc.left]; x
0x180075543  mov     rcx, [rbx+20h]; hdc
0x180075547  call    cs:__imp_SetWindowExtEx
0x18007554d  test    eax, eax
0x18007554f  jz      short loc_180075516
0x180075551  mov     [rbp+57h+iMode], esi
0x180075554  jmp     loc_180075603
0x180075559  cmp     [rbx+28h], rsi
0x18007555d  jnz     short loc_180075569
0x18007555f  mov     eax, 80070057h
0x180075564  jmp     loc_180075881
0x180075569  mov     rcx, [rbx+20h]; hdc
0x18007556d  mov     edx, 8; iMode
0x180075572  call    cs:__imp_SetMapMode
0x180075578  mov     rdx, [rbx+28h]
0x18007557c  lea     r9, [rbp+57h+var_80]; lppt
0x180075580  mov     rcx, [rbx+20h]; hdc
0x180075584  mov     [rbp+57h+iMode], eax
0x180075587  mov     r8d, [rdx+4]; y
0x18007558b  mov     edx, [rdx]; x
0x18007558d  call    cs:__imp_SetViewportOrgEx
0x180075593  test    eax, eax
0x180075595  jz      loc_180075516
0x18007559b  mov     rax, [rbx+28h]
0x18007559f  lea     r9, [rbp+57h+var_78]; lpsz
0x1800755a3  mov     rcx, [rbx+20h]; hdc
0x1800755a7  mov     r8d, [rax+0Ch]
0x1800755ab  mov     edx, [rax+8]
0x1800755ae  sub     r8d, [rax+4]; y
0x1800755b2  sub     edx, [rax]; x
0x1800755b4  call    cs:__imp_SetViewportExtEx
0x1800755ba  test    eax, eax
0x1800755bc  jz      loc_180075516
0x1800755c2  mov     r8d, [rbp+57h+rc.top]; y
0x1800755c6  lea     r9, [rbp+57h+pt]; lppt
0x1800755ca  mov     edx, [rbp+57h+rc.left]; x
0x1800755cd  mov     rcx, [rbx+20h]; hdc
0x1800755d1  call    cs:__imp_SetWindowOrgEx
0x1800755d7  test    eax, eax
0x1800755d9  jz      loc_180075516
0x1800755df  mov     r8d, [rbp+57h+rc.bottom]
0x1800755e3  lea     r9, [rbp+57h+sz]; lpsz
0x1800755e7  mov     edx, [rbp+57h+rc.right]
0x1800755ea  sub     r8d, [rbp+57h+rc.top]; y
0x1800755ee  sub     edx, [rbp+57h+rc.left]; x
0x1800755f1  mov     rcx, [rbx+20h]; hdc
0x1800755f5  call    cs:__imp_SetWindowExtEx
0x1800755fb  test    eax, eax
0x1800755fd  jz      loc_180075516
0x180075603  xorps   xmm0, xmm0
0x180075606  movups  xmmword ptr [rbp+57h+plpen.lopnStyle], xmm0
0x18007560a  cmp     [r15+180h], esi
0x180075611  jbe     short loc_180075620
0x180075613  cmp     [r15+188h], rsi
0x18007561a  jz      loc_1800757E0
0x180075620  mov     r13d, esi
0x180075623  mov     [rbp+57h+var_A8], r13d
0x180075627  cmp     r13d, [r15+180h]
0x18007562e  jnb     loc_1800757F4
0x180075634  mov     rcx, [r15+188h]
0x18007563b  mov     eax, r13d
0x18007563e  imul    rdi, rax, 38h ; '8'
0x180075642  mov     esi, [rcx+rdi]
0x180075645  test    esi, esi
0x180075647  jz      loc_1800757AD
0x18007564d  mov     [rbp+57h+plpen.lopnStyle], 0
0x180075654  mov     rax, [rcx+rdi+0Ch]
0x180075659  mov     qword ptr [rbp+57h+plpen.lopnWidth.x], rax
0x18007565d  mov     eax, [rcx+rdi+8]
0x180075661  mov     [rbp+57h+plpen.lopnColor], eax
0x180075664  cmp     r14d, 7FFFh
0x18007566b  jle     short loc_180075683
0x18007566d  mov     eax, [rbp+57h+plpen.lopnWidth.x]
0x180075670  xor     edx, edx
0x180075672  div     r12d
0x180075675  xor     edx, edx
0x180075677  mov     [rbp+57h+plpen.lopnWidth.x], eax
0x18007567a  mov     eax, [rbp+57h+plpen.lopnWidth.y]
0x18007567d  div     r12d
0x180075680  mov     [rbp+57h+plpen.lopnWidth.y], eax
0x180075683  lea     rcx, [rbp+57h+plpen]; plpen
0x180075687  call    cs:__imp_CreatePenIndirect
0x18007568d  mov     r12, rax
0x180075690  test    rax, rax
0x180075693  jz      short loc_1800756A5
0x180075695  mov     rcx, [rbx+20h]; hdc
0x180075699  mov     rdx, rax; h
0x18007569c  call    cs:__imp_SelectObject
0x1800756a2  mov     r12, rax
0x1800756a5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800756ac  mov     eax, 8
0x1800756b1  mul     rsi
0x1800756b4  cmovb   rax, rcx
0x1800756b8  mov     rcx, rax; unsigned __int64
0x1800756bb  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800756c0  mov     r14, rax
0x1800756c3  test    rax, rax
0x1800756c6  jz      loc_1800757EA
0x1800756cc  mov     rcx, [r15+188h]
0x1800756d3  cmp     qword ptr [rcx+rdi+18h], 0
0x1800756d9  jz      loc_1800757E0
0x1800756df  xor     r9d, r9d
0x1800756e2  test    esi, esi
0x1800756e4  jz      short loc_180075741
0x1800756e6  mov     r10d, [rbp+57h+var_B0]
0x1800756ea  xor     r8d, r8d
0x1800756ed  mov     rbx, [rbp+57h+var_70]
0x1800756f1  mov     r13d, [rbp+57h+var_90]
0x1800756f5  mov     rax, [r15+188h]
0x1800756fc  xor     edx, edx
0x1800756fe  inc     r9d
0x180075701  mov     rcx, [rdi+rax+18h]
0x180075706  mov     eax, [rcx+r8*8]
0x18007570a  sub     eax, r13d
0x18007570d  div     r10d
0x180075710  xor     edx, edx
0x180075712  mov     [r14+r8*8], eax
0x180075716  mov     rax, [r15+188h]
0x18007571d  mov     rcx, [rax+rdi+18h]
0x180075722  mov     eax, [rcx+r8*8+4]
0x180075727  sub     eax, ebx
0x180075729  div     r10d
0x18007572c  mov     [r14+r8*8+4], eax
0x180075731  inc     r8
0x180075734  cmp     r9d, esi
0x180075737  jb      short loc_1800756F5
0x180075739  mov     rbx, [rbp+57h+var_68]
0x18007573d  mov     r13d, [rbp+57h+var_A8]
0x180075741  cmp     esi, 1
0x180075744  jbe     short loc_1800757B9
0x180075746  xor     edi, edi
0x180075748  mov     r15d, 3E8h
0x18007574e  lea     eax, [rdi+3E8h]
0x180075754  cmp     eax, edi
0x180075756  jbe     short loc_18007577D
0x180075758  cmp     eax, esi
0x18007575a  jbe     short loc_180075762
0x18007575c  mov     r15d, esi
0x18007575f  sub     r15d, edi
0x180075762  mov     rcx, [rbx+20h]; hdc
0x180075766  lea     rdx, [r14+rdi*8]; apt
0x18007576a  mov     r8d, r15d; cpt
0x18007576d  call    cs:__imp_Polyline
0x180075773  add     edi, 3E7h
0x180075779  cmp     esi, edi
0x18007577b  ja      short loc_18007574E
0x18007577d  mov     r15, [rbp+57h+var_88]
0x180075781  mov     rcx, r14; void *
0x180075784  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x180075789  test    r12, r12
0x18007578c  jz      short loc_1800757A9
0x18007578e  mov     rcx, [rbx+20h]; hdc
0x180075792  mov     rdx, r12; h
0x180075795  call    cs:__imp_SelectObject
0x18007579b  test    rax, rax
0x18007579e  jz      short loc_1800757A9
0x1800757a0  mov     rcx, rax; ho
0x1800757a3  call    cs:__imp_DeleteObject
0x1800757a9  mov     r12d, [rbp+57h+var_B0]
0x1800757ad  mov     r14d, [rbp+57h+var_AC]
0x1800757b1  inc     r13d
0x1800757b4  jmp     loc_180075623
0x1800757b9  mov     r8d, [r14+4]; y
0x1800757bd  xor     r9d, r9d; lppt
0x1800757c0  mov     edx, [r14]; x
0x1800757c3  mov     rcx, [rbx+20h]; hdc
0x1800757c7  call    cs:__imp_MoveToEx
0x1800757cd  mov     r8d, [r14+4]; y
0x1800757d1  mov     edx, [r14]; x
0x1800757d4  mov     rcx, [rbx+20h]; hdc
0x1800757d8  call    cs:__imp_LineTo
0x1800757de  jmp     short loc_180075781
0x1800757e0  mov     eax, 8000FFFFh
0x1800757e5  jmp     loc_180075881
0x1800757ea  mov     eax, 8007000Eh
0x1800757ef  jmp     loc_180075881
0x1800757f4  cmp     [rbp+57h+var_8C], 5
0x1800757f8  jz      short loc_180075847
0x1800757fa  mov     edx, [rbp+57h+iMode]; iMode
0x1800757fd  mov     rcx, [rbx+20h]; hdc
0x180075801  call    cs:__imp_SetMapMode
0x180075807  test    eax, eax
0x180075809  jz      loc_180075516
0x18007580f  mov     r8d, [rbp+57h+var_80.y]; y
0x180075813  xor     r9d, r9d; lppt
0x180075816  mov     edx, [rbp+57h+var_80.x]; x
0x180075819  mov     rcx, [rbx+20h]; hdc
0x18007581d  call    cs:__imp_SetViewportOrgEx
0x180075823  test    eax, eax
0x180075825  jz      loc_180075516
0x18007582b  mov     r8d, [rbp+57h+var_78.cy]; y
0x18007582f  xor     r9d, r9d; lpsz
0x180075832  mov     edx, [rbp+57h+var_78.cx]; x
0x180075835  mov     rcx, [rbx+20h]; hdc
0x180075839  call    cs:__imp_SetViewportExtEx
0x18007583f  test    eax, eax
0x180075841  jz      loc_180075516
0x180075847  mov     r8d, [rbp+57h+pt.y]; y
0x18007584b  xor     r9d, r9d; lppt
0x18007584e  mov     edx, [rbp+57h+pt.x]; x
0x180075851  mov     rcx, [rbx+20h]; hdc
0x180075855  call    cs:__imp_SetWindowOrgEx
0x18007585b  test    eax, eax
0x18007585d  jz      loc_180075516
0x180075863  mov     r8d, [rbp+57h+sz.cy]; y
0x180075867  xor     r9d, r9d; lpsz
0x18007586a  mov     edx, [rbp+57h+sz.cx]; x
0x18007586d  mov     rcx, [rbx+20h]; hdc
0x180075871  call    cs:__imp_SetWindowExtEx
0x180075877  test    eax, eax
  ... truncated ...
```
