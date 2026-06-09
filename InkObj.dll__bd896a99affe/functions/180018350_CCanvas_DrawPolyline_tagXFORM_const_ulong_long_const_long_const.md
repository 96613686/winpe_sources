# CCanvas::DrawPolyline(tagXFORM const *,ulong,long const *,long const *)

- ea: `0x180018350`
- end: `0x180018997`
- name: `?DrawPolyline@CCanvas@@QEAAJPEBUtagXFORM@@KPEBJ1@Z`
- size: `1607`
- prototype: `__int64 __fastcall(CCanvas *__hidden this, const struct tagXFORM *, unsigned int, const int *, const int *)`
- caller_count: `3`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x18000f0d0`
- `0x180089390`
- `0x180093350`

## callees

- `0x180002740`
- `0x180010350`
- `0x180010918`
- `0x180018350`
- `0x180018be0`
- `0x18001acf0`
- `0x180036950`
- `0x180037478`
- `0x180038010`
- `0x18009922c`
- `0x18009938c`
- `0x1800993b8`
- `0x1800998ec`
- `0x180099c7c`
- `0x180099ca8`
- `0x180099ea8`
- `0x18009e590`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018496`
- `GDI32!Ellipse` at `0x180018563`
- `GDI32!Ellipse` at `0x180018563`
- `GDI32!CreateSolidBrush` at `0x1800184e3`
- `GDI32!CreateSolidBrush` at `0x1800184e3`
- `GDI32!CreatePen` at `0x180018500`
- `GDI32!CreatePen` at `0x180018500`
- `GDI32!SelectObject` at `0x18001851c`
- `GDI32!SelectObject` at `0x18001852f`
- `GDI32!SelectObject` at `0x180018573`
- `GDI32!SelectObject` at `0x180018583`
- `GDI32!SelectObject` at `0x18001851c`
- `GDI32!SelectObject` at `0x18001852f`
- `GDI32!SelectObject` at `0x180018573`
- `GDI32!SelectObject` at `0x180018583`
- `GDI32!Polyline` at `0x18001848c`
- `GDI32!Polyline` at `0x18001848c`
- `GDI32!DeleteObject` at `0x18001858c`
- `GDI32!DeleteObject` at `0x18001859c`
- `GDI32!DeleteObject` at `0x18001858c`
- `GDI32!DeleteObject` at `0x18001859c`
- `gdiplus!GdipAddPathLine2` at `0x1800186bb`
- `gdiplus!GdipAddPathLine2` at `0x1800186bb`
- `gdiplus!GdipDeletePath` at `0x18001872d`
- `gdiplus!GdipDeletePath` at `0x18001872d`
- `gdiplus!GdipCreatePath` at `0x1800186a6`
- `gdiplus!GdipCreatePath` at `0x1800186a6`
- `gdiplus!GdipGetPenFillType` at `0x180018893`
- `gdiplus!GdipGetPenFillType` at `0x180018893`
- `gdiplus!GdipFillEllipse` at `0x180018937`
- `gdiplus!GdipFillEllipse` at `0x180018937`
- `gdiplus!GdipGetPenColor` at `0x1800188b7`
- `gdiplus!GdipGetPenColor` at `0x1800188b7`
- `gdiplus!GdipAlloc` at `0x1800188d4`
- `gdiplus!GdipAlloc` at `0x1800188d4`
- `gdiplus!GdipDrawEllipse` at `0x180018857`
- `gdiplus!GdipDrawEllipse` at `0x180018857`
- `gdiplus!GdipDrawLines` at `0x180018749`
- `gdiplus!GdipDrawLines` at `0x180018749`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCanvas::DrawPolyline(CCanvas *this, const struct tagXFORM *a2, unsigned int a3, int *a4, int *a5)
{
  unsigned __int64 v6; // r15
  unsigned int v9; // esi
  char v11; // cl
  unsigned int j; // eax
  POINT *v13; // rbx
  signed int LastError; // eax
  HBRUSH SolidBrush; // r15
  HPEN Pen; // r13
  HGDIOBJ v17; // rdi
  HGDIOBJ v18; // rbx
  char v19; // dl
  int v20; // r9d
  unsigned int i; // eax
  struct Gdiplus::PointF *v22; // rax
  struct Gdiplus::PointF *v23; // rbx
  unsigned int v24; // eax
  unsigned int v25; // edi
  __int64 v26; // rsi
  unsigned int v27; // eax
  float v28; // xmm2_4
  float v29; // xmm3_4
  __int64 v30; // rbx
  unsigned int v31; // eax
  int v32; // ebx
  _QWORD *v33; // rsi
  int PenFillType; // eax
  _DWORD *v35; // rdi
  int PenColor; // eax
  Gdiplus::SolidBrush *v37; // rax
  __int64 v38; // rax
  void (__fastcall ***v39)(_QWORD, __int64); // rbx
  __int64 v40; // rdi
  unsigned int v41; // eax
  bool v42[8]; // [rsp+38h] [rbp-D0h] BYREF
  struct tagPOINT v43; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v44; // [rsp+48h] [rbp-C0h]
  __int64 v45; // [rsp+50h] [rbp-B8h] BYREF
  Gdiplus::SolidBrush *v46; // [rsp+58h] [rbp-B0h] BYREF
  struct Gdiplus::PointF *v47; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v48[1600]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v49[1600]; // [rsp+6A8h] [rbp+5A0h] BYREF

  v43 = (struct tagPOINT)a4;
  v6 = a3;
  v9 = 0;
  if ( !a3 )
    return 0;
  if ( !*((_DWORD *)this + 61) )
  {
    if ( !*((_QWORD *)this + 1) || !*((_QWORD *)this + 2) )
      return 2147500035LL;
    v19 = 1;
    v20 = *a4;
    for ( i = 1; i < a3; ++i )
    {
      if ( v20 != a4[i] || *a5 != a5[i] )
      {
        v19 = 0;
        break;
      }
    }
    if ( a3 != 1 && !v19 )
    {
      `vector constructor iterator'(v48, 8u, 0xC8u, (void *(*)(void *))Gdiplus::PointF::PointF);
      if ( (unsigned int)v6 <= 0xC8 )
      {
        v23 = (struct Gdiplus::PointF *)v48;
      }
      else
      {
        v22 = (struct Gdiplus::PointF *)WinMalloc(saturated_mul(v6, 8u));
        v23 = v22;
        v47 = v22;
        if ( v22 )
          `vector constructor iterator'(v22, 8u, v6, (void *(*)(void *))Gdiplus::PointF::PointF);
        else
          v23 = 0;
        if ( !v23 )
          return 2147942414LL;
      }
      TransformXYsToPoints(a2, *(const int **)&v43, a5, v6, v23);
      if ( *((_BYTE *)this + 208) )
      {
        v43 = 0;
        v44 = GdipCreatePath(0, &v43);
        v24 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GdipAddPathLine2)(v43, v23, (unsigned int)v6);
        v25 = v24;
        if ( v24 )
        {
          v44 = v24;
        }
        else
        {
          v25 = Gdiplus::GraphicsPath::Widen(&v43, *((_QWORD *)this + 2));
          if ( !v25 )
          {
            Gdiplus::GraphicsPath::Outline(&v43);
            Gdiplus::Pen::SetWidth(*((_QWORD *)this + 2));
            Gdiplus::Pen::SetAlignment(*((_QWORD *)this + 2));
            v25 = Gdiplus::Graphics::DrawPath(*((_QWORD *)this + 1), *((_QWORD *)this + 2), &v43);
          }
        }
        ((void (__fastcall *)(_QWORD))GdipDeletePath)(v43);
      }
      else
      {
        v26 = *((_QWORD *)this + 1);
        v27 = GdipDrawLines(*(_QWORD *)v26, **((_QWORD **)this + 2), v23, (unsigned int)v6);
        v25 = v27;
        if ( v27 )
          *(_DWORD *)(v26 + 8) = v27;
        else
          v25 = 0;
      }
      if ( (unsigned int)v6 >= 3 )
        v9 = HRESULTFromStatus(v25);
      else
        v9 = 0;
      if ( v23 != (struct Gdiplus::PointF *)v48 )
        WinFree(v23);
      return v9;
    }
    Gdiplus::PointF::PointF((Gdiplus::PointF *)&v43);
    v28 = (float)*a4;
    v29 = (float)*a5;
    if ( a2 )
    {
      *(float *)&v43.x = (float)((float)(v29 * a2->eM21) + (float)(v28 * a2->eM11)) + a2->eDx;
      *(float *)&v43.y = (float)((float)(v28 * a2->eM12) + (float)(v29 * a2->eM22)) + a2->eDy;
    }
    else
    {
      *(float *)&v43.x = (float)*a4;
      *(float *)&v43.y = v29;
    }
    Gdiplus::Pen::GetWidth(*((Gdiplus::Pen **)this + 2));
    if ( *((_BYTE *)this + 208) )
    {
      Gdiplus::Pen::SetWidth(*((_QWORD *)this + 2));
      Gdiplus::Pen::SetAlignment(*((_QWORD *)this + 2));
      v30 = *((_QWORD *)this + 1);
      v31 = GdipDrawEllipse(*(_QWORD *)v30, **((_QWORD **)this + 2));
      if ( v31 )
        *(_DWORD *)(v30 + 8) = v31;
      else
        v31 = 0;
      return (unsigned int)HRESULTFromStatus(v31);
    }
    v32 = -16777216;
    LODWORD(v47) = -16777216;
    v33 = (_QWORD *)*((_QWORD *)this + 2);
    LODWORD(v45) = 0;
    PenFillType = GdipGetPenFillType(*v33, &v45);
    v35 = v33 + 1;
    if ( PenFillType )
      *v35 = PenFillType;
    if ( !(_DWORD)v45 )
    {
      LODWORD(v46) = 0;
      PenColor = GdipGetPenColor(*v33, &v46);
      if ( PenColor )
        *v35 = PenColor;
      if ( !*v35 )
        v32 = (int)v46;
      LODWORD(v47) = v32;
    }
    v37 = (Gdiplus::SolidBrush *)GdipAlloc(24);
    v46 = v37;
    if ( v37 )
    {
      v38 = Gdiplus::SolidBrush::SolidBrush(v37, (const struct Gdiplus::Color *)&v47);
      v39 = (void (__fastcall ***)(_QWORD, __int64))v38;
      if ( v38 )
      {
        v40 = *((_QWORD *)this + 1);
        v41 = GdipFillEllipse(*(_QWORD *)v40, *(_QWORD *)(v38 + 8));
        if ( v41 )
          *(_DWORD *)(v40 + 8) = v41;
        else
          v41 = 0;
        v9 = HRESULTFromStatus(v41);
        (**v39)(v39, 1);
        return v9;
      }
    }
    return 2147942414LL;
  }
  if ( *((_QWORD *)this + 31) )
  {
    v42[0] = 0;
    v42[1] = CCanvas::UpdateWorldTransforms(this, v42);
    v11 = 1;
    for ( j = 1; j < (unsigned int)v6; ++j )
    {
      if ( *a4 != a4[j] || *a5 != a5[j] )
      {
        v11 = 0;
        break;
      }
    }
    if ( (_DWORD)v6 != 1 && !v11 )
    {
      if ( (unsigned int)v6 <= 0xC8 )
      {
        v13 = (POINT *)v49;
      }
      else
      {
        v13 = (POINT *)WinMalloc(saturated_mul(v6, 8u));
        if ( !v13 )
          goto LABEL_15;
      }
      Transform(a2, v6, *(const int **)&v43, a5, v13);
      if ( !Polyline(*((HDC *)this + 31), v13, v6) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v13 != (POINT *)v49 )
        WinFree(v13);
      goto LABEL_16;
    }
    Transform(a2, 1u, a4, a5, &v43);
    SolidBrush = CreateSolidBrush(*((_DWORD *)this + 80));
    if ( SolidBrush )
    {
      Pen = CreatePen(0, 0, *((_DWORD *)this + 80));
      if ( Pen )
      {
        v17 = SelectObject(*((HDC *)this + 31), SolidBrush);
        v18 = SelectObject(*((HDC *)this + 31), Pen);
        Ellipse(
          *((HDC *)this + 31),
          v43.x - (*((_DWORD *)this + 78) >> 1),
          v43.y - (*((_DWORD *)this + 78) >> 1),
          (*((_DWORD *)this + 78) >> 1) + v43.x,
          (*((_DWORD *)this + 78) >> 1) + v43.y);
        SelectObject(*((HDC *)this + 31), v17);
        SelectObject(*((HDC *)this + 31), v18);
        DeleteObject(Pen);
      }
      else
      {
        v9 = -2147024882;
      }
      DeleteObject(SolidBrush);
      goto LABEL_16;
    }
LABEL_15:
    v9 = -2147024882;
LABEL_16:
    if ( v42[1] )
      CCanvas::RestoreWorldTransforms(this, v42[0]);
    return v9;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180018350  mov     rax, rsp
0x180018353  push    rbp
0x180018354  push    rbx
0x180018355  push    rsi
0x180018356  push    rdi
0x180018357  push    r12
0x180018359  push    r13
0x18001835b  push    r14
0x18001835d  push    r15
0x18001835f  lea     rbp, [rax-0C48h]
0x180018366  sub     rsp, 0D08h
0x18001836d  movaps  xmmword ptr [rax-58h], xmm6
0x180018371  mov     rax, cs:__security_cookie
0x180018378  xor     rax, rsp
0x18001837b  mov     [rbp+0C40h+var_60], rax
0x180018382  mov     rbx, r9
0x180018385  mov     qword ptr [rsp+0D40h+var_D08.x], rbx
0x18001838a  mov     r15d, r8d
0x18001838d  mov     rdi, rdx
0x180018390  mov     r14, rcx
0x180018393  mov     r13, [rbp+0C40h+arg_20]
0x18001839a  xor     esi, esi
0x18001839c  test    r8d, r8d
0x18001839f  jnz     short loc_1800183A8
0x1800183a1  xor     eax, eax
0x1800183a3  jmp     loc_18001896C
0x1800183a8  cmp     [rcx+0F4h], esi
0x1800183ae  jz      loc_1800185A7
0x1800183b4  cmp     [rcx+0F8h], rsi
0x1800183bb  jz      loc_180018967
0x1800183c1  mov     [rsp+0D40h+var_D10], sil
0x1800183c6  lea     rdx, [rsp+0D40h+var_D10]; bool *
0x1800183cb  call    ?UpdateWorldTransforms@CCanvas@@IEAA_NAEA_N@Z; CCanvas::UpdateWorldTransforms(bool &)
0x1800183d0  mov     [rsp+0D40h+var_D10+1], al
0x1800183d4  mov     r12d, 1
0x1800183da  mov     cl, r12b
0x1800183dd  mov     r9d, [rbx]
0x1800183e0  mov     r8d, [r13+0]
0x1800183e4  mov     eax, r12d
0x1800183e7  cmp     eax, r15d
0x1800183ea  jnb     short loc_180018402
0x1800183ec  mov     edx, eax
0x1800183ee  cmp     r9d, [rbx+rdx*4]
0x1800183f2  jnz     short loc_180018400
0x1800183f4  cmp     r8d, [r13+rdx*4+0]
0x1800183f9  jnz     short loc_180018400
0x1800183fb  add     eax, r12d
0x1800183fe  jmp     short loc_1800183E7
0x180018400  xor     cl, cl
0x180018402  cmp     r15d, r12d
0x180018405  jz      loc_1800184C1
0x18001840b  test    cl, cl
0x18001840d  jnz     loc_1800184C1
0x180018413  cmp     r15d, 0C8h
0x18001841a  jbe     short loc_180018460
0x18001841c  mov     eax, 8
0x180018421  mul     r15
0x180018424  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001842b  cmovb   rax, rcx
0x18001842f  mov     rcx, rax; unsigned __int64
0x180018432  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x180018437  mov     rbx, rax
0x18001843a  test    rax, rax
0x18001843d  jnz     short loc_180018467
0x18001843f  mov     esi, 8007000Eh
0x180018444  cmp     [rsp+0D40h+var_D10+1], r12b
0x180018449  jnz     loc_180018963
0x18001844f  mov     dl, [rsp+0D40h+var_D10]; bool
0x180018453  mov     rcx, r14; this
0x180018456  call    ?RestoreWorldTransforms@CCanvas@@IEAAX_N@Z; CCanvas::RestoreWorldTransforms(bool)
0x18001845b  jmp     loc_180018963
0x180018460  lea     rbx, [rbp+0C40h+var_6A0]
0x180018467  mov     qword ptr [rsp+0D40h+bottom], rbx; struct tagPOINT *
0x18001846c  mov     r9, r13; int *
0x18001846f  mov     r8, qword ptr [rsp+0D40h+var_D08.x]; int *
0x180018474  mov     edx, r15d; unsigned int
0x180018477  mov     rcx, rdi; struct tagXFORM *
0x18001847a  call    ?Transform@@YAXPEBUtagXFORM@@KPEBJ1PEAUtagPOINT@@@Z; Transform(tagXFORM const *,ulong,long const *,long const *,tagPOINT *)
0x18001847f  mov     r8d, r15d; cpt
0x180018482  mov     rdx, rbx; apt
0x180018485  mov     rcx, [r14+0F8h]; hdc
0x18001848c  call    cs:__imp_Polyline
0x180018492  test    eax, eax
0x180018494  jnz     short loc_1800184AB
0x180018496  call    cs:__imp_GetLastError
0x18001849c  mov     esi, eax
0x18001849e  test    eax, eax
0x1800184a0  jle     short loc_1800184AB
0x1800184a2  movzx   esi, ax
0x1800184a5  or      esi, 80070000h
0x1800184ab  lea     rax, [rbp+0C40h+var_6A0]
0x1800184b2  cmp     rbx, rax
0x1800184b5  jz      short loc_180018444
0x1800184b7  mov     rcx, rbx; void *
0x1800184ba  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800184bf  jmp     short loc_180018444
0x1800184c1  lea     rax, [rsp+0D40h+var_D08]
0x1800184c6  mov     qword ptr [rsp+0D40h+bottom], rax; struct tagPOINT *
0x1800184cb  mov     r9, r13; int *
0x1800184ce  mov     r8, rbx; int *
0x1800184d1  mov     edx, r12d; unsigned int
0x1800184d4  mov     rcx, rdi; struct tagXFORM *
0x1800184d7  call    ?Transform@@YAXPEBUtagXFORM@@KPEBJ1PEAUtagPOINT@@@Z; Transform(tagXFORM const *,ulong,long const *,long const *,tagPOINT *)
0x1800184dc  mov     ecx, [r14+140h]; color
0x1800184e3  call    cs:__imp_CreateSolidBrush
0x1800184e9  mov     r15, rax
0x1800184ec  test    rax, rax
0x1800184ef  jz      loc_18001843F
0x1800184f5  mov     r8d, [r14+140h]; color
0x1800184fc  xor     edx, edx; cWidth
0x1800184fe  xor     ecx, ecx; iStyle
0x180018500  call    cs:__imp_CreatePen
0x180018506  mov     r13, rax
0x180018509  test    rax, rax
0x18001850c  jz      loc_180018594
0x180018512  mov     rdx, r15; h
0x180018515  mov     rcx, [r14+0F8h]; hdc
0x18001851c  call    cs:__imp_SelectObject
0x180018522  mov     rdi, rax
0x180018525  mov     rdx, r13; h
0x180018528  mov     rcx, [r14+0F8h]; hdc
0x18001852f  call    cs:__imp_SelectObject
0x180018535  mov     rbx, rax
0x180018538  mov     ecx, [r14+138h]
0x18001853f  shr     ecx, 1
0x180018541  mov     r8d, [rsp+0D40h+var_D08.y]
0x180018546  lea     eax, [rcx+r8]
0x18001854a  mov     rdx, qword ptr [rsp+0D40h+var_D08.x]
0x18001854f  lea     r9d, [rcx+rdx]; right
0x180018553  sub     r8d, ecx; top
0x180018556  sub     edx, ecx; left
0x180018558  mov     [rsp+0D40h+bottom], eax; bottom
0x18001855c  mov     rcx, [r14+0F8h]; hdc
0x180018563  call    cs:__imp_Ellipse
0x180018569  mov     rdx, rdi; h
0x18001856c  mov     rcx, [r14+0F8h]; hdc
0x180018573  call    cs:__imp_SelectObject
0x180018579  mov     rdx, rbx; h
0x18001857c  mov     rcx, [r14+0F8h]; hdc
0x180018583  call    cs:__imp_SelectObject
0x180018589  mov     rcx, r13; ho
0x18001858c  call    cs:__imp_DeleteObject
0x180018592  jmp     short loc_180018599
0x180018594  mov     esi, 8007000Eh
0x180018599  mov     rcx, r15; ho
0x18001859c  call    cs:__imp_DeleteObject
0x1800185a2  jmp     loc_180018444
0x1800185a7  cmp     [rcx+8], rsi
0x1800185ab  jz      loc_180018967
0x1800185b1  cmp     [rcx+10h], rsi
0x1800185b5  jz      loc_180018967
0x1800185bb  mov     r12d, 1
0x1800185c1  mov     dl, r12b
0x1800185c4  mov     r9d, [r9]
0x1800185c7  mov     r8d, [r13+0]
0x1800185cb  mov     eax, r12d
0x1800185ce  cmp     eax, r15d
0x1800185d1  jnb     short loc_1800185EA
0x1800185d3  mov     ecx, eax
0x1800185d5  cmp     r9d, [rbx+rcx*4]
0x1800185d9  jnz     short loc_1800185E7
0x1800185db  cmp     r8d, [r13+rcx*4+0]
0x1800185e0  jnz     short loc_1800185E7
0x1800185e2  add     eax, r12d
0x1800185e5  jmp     short loc_1800185CE
0x1800185e7  mov     dl, sil
0x1800185ea  cmp     r15d, r12d
0x1800185ed  jz      loc_18001878A
0x1800185f3  test    dl, dl
0x1800185f5  jnz     loc_18001878A
0x1800185fb  lea     r9, ??0PointF@Gdiplus@@QEAA@XZ; void *(*)(void *)
0x180018602  mov     esi, 8
0x180018607  mov     r8d, 0C8h; unsigned __int64
0x18001860d  mov     edx, esi; unsigned __int64
0x18001860f  lea     rcx, [rsp+0D40h+var_CE0]; void *
0x180018614  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180018619  cmp     r15d, 0C8h
0x180018620  jbe     short loc_18001866B
0x180018622  mov     eax, esi
0x180018624  mul     r15
0x180018627  lea     rcx, [rsi-9]
0x18001862b  cmovb   rax, rcx
0x18001862f  mov     rcx, rax; unsigned __int64
0x180018632  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x180018637  mov     rbx, rax
0x18001863a  mov     [rsp+0D40h+var_CE8], rax
0x18001863f  test    rax, rax
0x180018642  jz      short loc_18001865A
0x180018644  lea     r9, ??0PointF@Gdiplus@@QEAA@XZ; void *(*)(void *)
0x18001864b  mov     r8, r15; unsigned __int64
0x18001864e  mov     edx, esi; unsigned __int64
0x180018650  mov     rcx, rax; void *
0x180018653  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180018658  jmp     short loc_18001865C
0x18001865a  xor     ebx, ebx
0x18001865c  test    rbx, rbx
0x18001865f  jnz     short loc_180018670
0x180018661  mov     eax, 8007000Eh
0x180018666  jmp     loc_18001896C
0x18001866b  lea     rbx, [rsp+0D40h+var_CE0]
0x180018670  mov     qword ptr [rsp+0D40h+bottom], rbx; struct Gdiplus::PointF *
0x180018675  mov     r9d, r15d; unsigned int
0x180018678  mov     r8, r13; int *
0x18001867b  mov     rdx, qword ptr [rsp+0D40h+var_D08.x]; int *
0x180018680  mov     rcx, rdi; struct tagXFORM *
0x180018683  call    ?TransformXYsToPoints@@YAXPEBUtagXFORM@@PEBJ1KPEAVPointF@Gdiplus@@@Z; TransformXYsToPoints(tagXFORM const *,long const *,long const *,ulong,Gdiplus::PointF *)
0x180018688  cmp     byte ptr [r14+0D0h], 0
0x180018690  jz      loc_180018735
0x180018696  mov     qword ptr [rsp+0D40h+var_D08.x], 0
0x18001869f  lea     rdx, [rsp+0D40h+var_D08]
0x1800186a4  xor     ecx, ecx
0x1800186a6  call    cs:__imp_GdipCreatePath
0x1800186ac  mov     [rsp+0D40h+var_D00], eax
0x1800186b0  mov     r8d, r15d
0x1800186b3  mov     rdx, rbx
0x1800186b6  mov     rcx, qword ptr [rsp+0D40h+var_D08.x]
0x1800186bb  call    cs:__imp_GdipAddPathLine2
0x1800186c1  mov     edi, eax
0x1800186c3  test    eax, eax
0x1800186c5  jz      short loc_1800186CD
0x1800186c7  mov     [rsp+0D40h+var_D00], eax
0x1800186cb  jmp     short loc_180018728
0x1800186cd  movss   xmm6, cs:__real@3e800000
0x1800186d5  movaps  xmm3, xmm6
0x1800186d8  mov     rdx, [r14+10h]
0x1800186dc  lea     rcx, [rsp+0D40h+var_D08]
0x1800186e1  call    ?Widen@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@PEBVMatrix@2@M@Z; Gdiplus::GraphicsPath::Widen(Gdiplus::Pen const *,Gdiplus::Matrix const *,float)
0x1800186e6  mov     edi, eax
0x1800186e8  test    eax, eax
0x1800186ea  jnz     short loc_180018728
0x1800186ec  movaps  xmm2, xmm6
0x1800186ef  lea     rcx, [rsp+0D40h+var_D08]
0x1800186f4  call    ?Outline@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@PEBVMatrix@2@M@Z; Gdiplus::GraphicsPath::Outline(Gdiplus::Matrix const *,float)
0x1800186f9  movss   xmm1, dword ptr [r14+0D4h]
0x180018702  mov     rcx, [r14+10h]
0x180018706  call    ?SetWidth@Pen@Gdiplus@@QEAA?AW4Status@2@M@Z; Gdiplus::Pen::SetWidth(float)
0x18001870b  mov     rcx, [r14+10h]
0x18001870f  call    ?SetAlignment@Pen@Gdiplus@@QEAA?AW4Status@2@W4PenAlignment@2@@Z; Gdiplus::Pen::SetAlignment(Gdiplus::PenAlignment)
0x180018714  lea     r8, [rsp+0D40h+var_D08]
0x180018719  mov     rdx, [r14+10h]
0x18001871d  mov     rcx, [r14+8]
0x180018721  call    ?DrawPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::DrawPath(Gdiplus::Pen const *,Gdiplus::GraphicsPath const *)
0x180018726  mov     edi, eax
0x180018728  mov     rcx, qword ptr [rsp+0D40h+var_D08.x]
0x18001872d  call    cs:__imp_GdipDeletePath
0x180018733  jmp     short loc_18001875C
0x180018735  mov     rsi, [r14+8]
0x180018739  mov     rdx, [r14+10h]
0x18001873d  mov     r9d, r15d
0x180018740  mov     r8, rbx
0x180018743  mov     rdx, [rdx]
0x180018746  mov     rcx, [rsi]
0x180018749  call    cs:__imp_GdipDrawLines
0x18001874f  mov     edi, eax
0x180018751  test    eax, eax
0x180018753  jz      short loc_18001875A
0x180018755  mov     [rsi+8], eax
0x180018758  jmp     short loc_18001875C
0x18001875a  xor     edi, edi
0x18001875c  cmp     r15d, 3
0x180018760  jnb     short loc_180018766
0x180018762  xor     esi, esi
0x180018764  jmp     short loc_18001876F
0x180018766  mov     ecx, edi
0x180018768  call    HRESULTFromStatus
0x18001876d  mov     esi, eax
0x18001876f  lea     rax, [rsp+0D40h+var_CE0]
0x180018774  cmp     rbx, rax
0x180018777  jz      loc_180018963
0x18001877d  mov     rcx, rbx; void *
0x180018780  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x180018785  jmp     loc_180018963
0x18001878a  lea     rcx, [rsp+0D40h+var_D08]; this
0x18001878f  call    ??0PointF@Gdiplus@@QEAA@XZ; Gdiplus::PointF::PointF(void)
0x180018794  movd    xmm2, dword ptr [rbx]
0x180018798  cvtdq2ps xmm2, xmm2
0x18001879b  movd    xmm3, dword ptr [r13+0]
0x1800187a1  cvtdq2ps xmm3, xmm3
0x1800187a4  test    rdi, rdi
0x1800187a7  jz      short loc_1800187E2
0x1800187a9  movaps  xmm1, xmm3
0x1800187ac  mulss   xmm1, dword ptr [rdi+8]
0x1800187b1  movaps  xmm0, xmm2
0x1800187b4  mulss   xmm0, dword ptr [rdi]
0x1800187b8  addss   xmm1, xmm0
0x1800187bc  addss   xmm1, dword ptr [rdi+10h]
0x1800187c1  movss   [rsp+0D40h+var_D08.x], xmm1
0x1800187c7  mulss   xmm2, dword ptr [rdi+4]
0x1800187cc  mulss   xmm3, dword ptr [rdi+0Ch]
0x1800187d1  addss   xmm2, xmm3
0x1800187d5  addss   xmm2, dword ptr [rdi+14h]
0x1800187da  movss   [rsp+0D40h+var_D08.y], xmm2
0x1800187e0  jmp     short loc_1800187EE
0x1800187e2  movss   [rsp+0D40h+var_D08.x], xmm2
0x1800187e8  movss   [rsp+0D40h+var_D08.y], xmm3
0x1800187ee  mov     rcx, [r14+10h]; this
0x1800187f2  call    ?GetWidth@Pen@Gdiplus@@QEBAMXZ; Gdiplus::Pen::GetWidth(void)
0x1800187f7  movaps  xmm6, xmm0
0x1800187fa  cmp     [r14+0D0h], sil
0x180018801  jz      short loc_180018876
  ... truncated ...
```
