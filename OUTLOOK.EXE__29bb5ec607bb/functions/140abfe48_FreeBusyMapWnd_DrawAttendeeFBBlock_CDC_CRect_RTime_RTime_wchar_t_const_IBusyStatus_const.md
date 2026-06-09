# FreeBusyMapWnd::DrawAttendeeFBBlock(CDC *,CRect,RTime,RTime,wchar_t const *,IBusyStatus const *)

- ea: `0x140abfe48`
- end: `0x140ac056b`
- name: `?DrawAttendeeFBBlock@FreeBusyMapWnd@@AEAAXPEAVCDC@@VCRect@@VRTime@@2PEB_WPEBUIBusyStatus@@@Z`
- size: `1827`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x140abdd2c`
- `0x140abe170`
- `0x140abf790`

## callees

- `0x140256a30`
- `0x140257d70`
- `0x140257e1c`
- `0x140503f00`
- `0x1406706b0`
- `0x14074c3c0`
- `0x1407e99f0`
- `0x140abfe48`
- `0x140ac0570`
- `0x140ac0a30`
- `0x140ac1480`
- `0x140ac1494`

## import_xrefs

- `OLMAPI32!EtwTraceErrorTag` at `0x140ac0375`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac0375`
- `GDI32!GetBkColor` at `0x140ac0057`
- `GDI32!GetBkColor` at `0x140ac0057`
- `GDI32!CreateFontIndirectA` at `0x140ac020b`
- `GDI32!CreateFontIndirectA` at `0x140ac020b`
- `GDI32!GetObjectA` at `0x140ac01f1`
- `GDI32!GetObjectA` at `0x140ac01f1`
- `GDI32!SetTextColor` at `0x140ac0269`
- `GDI32!SetTextColor` at `0x140ac0269`
- `GDI32!GetTextMetricsA` at `0x140ac04aa`
- `GDI32!GetTextMetricsA` at `0x140ac04aa`
- `gdiplus!GdipDeletePen` at `0x140ac032d`
- `gdiplus!GdipDeletePen` at `0x140ac032d`
- `gdiplus!GdipSetSmoothingMode` at `0x140abffbc`
- `gdiplus!GdipSetSmoothingMode` at `0x140abffbc`
- `gdiplus!GdipDeleteGraphics` at `0x140ac0341`
- `gdiplus!GdipDeleteGraphics` at `0x140ac0341`
- `gdiplus!GdipDeleteBrush` at `0x140ac02e1`
- `gdiplus!GdipDeleteBrush` at `0x140ac039f`
- `gdiplus!GdipDeleteBrush` at `0x140ac0403`
- `gdiplus!GdipDeleteBrush` at `0x140ac02e1`
- `gdiplus!GdipDeleteBrush` at `0x140ac039f`
- `gdiplus!GdipDeleteBrush` at `0x140ac0403`
- `gdiplus!GdipCreateFromHDC` at `0x140abfeea`
- `gdiplus!GdipCreateFromHDC` at `0x140abfeea`
- `gdiplus!GdipCreateSolidFill` at `0x140ac0144`
- `gdiplus!GdipCreateSolidFill` at `0x140ac0144`
- `gdiplus!GdipFillPath` at `0x140ac0160`
- `gdiplus!GdipFillPath` at `0x140ac0160`
- `gdiplus!GdipCreatePath` at `0x140abff0d`
- `gdiplus!GdipCreatePath` at `0x140ac00fa`
- `gdiplus!GdipCreatePath` at `0x140abff0d`
- `gdiplus!GdipCreatePath` at `0x140ac00fa`
- `gdiplus!GdipDeletePath` at `0x140ac02eb`
- `gdiplus!GdipDeletePath` at `0x140ac0338`
- `gdiplus!GdipDeletePath` at `0x140ac0381`
- `gdiplus!GdipDeletePath` at `0x140ac03a9`
- `gdiplus!GdipDeletePath` at `0x140ac03eb`
- `gdiplus!GdipDeletePath` at `0x140ac040d`
- `gdiplus!GdipDeletePath` at `0x140ac0445`
- `gdiplus!GdipDeletePath` at `0x140ac02eb`
- `gdiplus!GdipDeletePath` at `0x140ac0338`
- `gdiplus!GdipDeletePath` at `0x140ac0381`
- `gdiplus!GdipDeletePath` at `0x140ac03a9`
- `gdiplus!GdipDeletePath` at `0x140ac03eb`
- `gdiplus!GdipDeletePath` at `0x140ac040d`
- `gdiplus!GdipDeletePath` at `0x140ac0445`
- `gdiplus!GdipCreatePen1` at `0x140ac0094`
- `gdiplus!GdipCreatePen1` at `0x140ac0094`
- `gdiplus!GdipDrawPath` at `0x140ac0322`
- `gdiplus!GdipDrawPath` at `0x140ac0322`
- `gdiplus!GdipDrawLineI` at `0x140ac0193`
- `gdiplus!GdipDrawLineI` at `0x140ac0193`
- `USER32!InflateRect` at `0x140ac01b9`
- `USER32!InflateRect` at `0x140ac01b9`
- `USER32!GetClientRect` at `0x140ac0525`
- `USER32!GetClientRect` at `0x140ac0525`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x140ac02b9`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x140ac02b9`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x140abffa6`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x140ac0279`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x140abffa6`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x140ac0279`

## pseudocode

```c
__int64 __fastcall FreeBusyMapWnd::DrawAttendeeFBBlock(
        __int64 a1,
        HDC *a2,
        struct tagRECT *a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7)
{
  int v10; // ecx
  LONG *p_right; // r12
  __int64 result; // rax
  HDC v13; // rcx
  __int64 v14; // r13
  int v15; // eax
  int v16; // ecx
  unsigned int v17; // ebx
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  COLORREF BkColor; // eax
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // r13
  __int64 v26; // r12
  int v27; // eax
  int v28; // eax
  __int64 v29; // r15
  __int64 v30; // rax
  void *v31; // rcx
  HFONT v32; // rax
  __int64 v33; // rdx
  COLORREF v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rdx
  LONG left; // ebx
  LONG right; // ecx
  LONG v39; // ecx
  LONG v40; // edx
  bool v41; // [rsp+40h] [rbp-C0h]
  __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v43[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h] BYREF
  int v45; // [rsp+68h] [rbp-98h]
  unsigned int v46; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v47; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h] BYREF
  struct tagRECT v49; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+90h] [rbp-70h] BYREF
  int v51; // [rsp+98h] [rbp-68h]
  struct tagRECT v52; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-50h] BYREF
  int v54; // [rsp+B8h] [rbp-48h]
  void **v55; // [rsp+C0h] [rbp-40h]
  __int64 v56; // [rsp+C8h] [rbp-38h]
  int v57; // [rsp+D0h] [rbp-30h]
  struct tagRECT Rect; // [rsp+D8h] [rbp-28h] BYREF
  LOGFONTA pv; // [rsp+E8h] [rbp-18h] BYREF
  struct tagTEXTMETRICA tm; // [rsp+128h] [rbp+28h] BYREF

  *(_QWORD *)&v52.left = a6;
  if ( !*(_DWORD *)(a1 + 112) || (v10 = 1, !a6) )
    v10 = 0;
  p_right = &a3->right;
  result = FreeBusyMapWnd::DistancesFromApptBlock(a1, a4, a5, a3, &a3->right, 1, v10);
  if ( (_DWORD)result )
  {
    v13 = 0;
    if ( a2 )
      v13 = a2[1];
    v48 = 0;
    LODWORD(v42) = GdipCreateFromHDC(v13, &v48);
    v14 = v48;
    v53 = v48;
    v44 = 0;
    v45 = GdipCreatePath(0, &v44);
    v46 = -16777216;
    v47 = -16777216;
    Rect = 0;
    if ( (int)a5 % 1440 / 60 == *(_DWORD *)(a1 + 168) % 1440 / 60 )
      *p_right -= 3;
    if ( MsoFRtlUI() )
    {
      left = a3->left;
      GetClientRect(*(HWND *)(a1 + 8), &Rect);
      right = Rect.right;
      a3->left = Rect.right - *p_right - 1;
      a3->right = right - left - 1;
    }
    v15 = GdipSetSmoothingMode(v14, 4);
    v16 = v42;
    if ( v15 )
      v16 = v15;
    v54 = v16;
    v49 = *a3;
    if ( !(unsigned int)GPCreateTabRectPath(&v44, &v49, 1) )
    {
      v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a7 + 112LL))(a7);
      LOBYTE(v18) = -1;
      v19 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)a7 + 184LL))(a7, v18, &v46);
      if ( v19 < 0 )
      {
        v36 = 282964;
      }
      else
      {
        LOBYTE(v20) = -1;
        v19 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)a7 + 192LL))(a7, v20, &v47);
        if ( v19 >= 0 )
        {
          BkColor = GetBkColor(a2[2]);
          LOBYTE(v22) = -1;
          if ( (unsigned int)GPFillFreeBusyRegion(&v53, &v44, v22, v17, BkColor) )
          {
            GdipDeletePath(v44);
            v35 = v53;
            return GdipDeleteGraphics(v35);
          }
          v50 = 0;
          v51 = GdipCreatePen1(v46, v23, 0, &v50);
          v24 = v53;
          v25 = *(_QWORD *)&v52.left;
          if ( *(_QWORD *)&v52.left && *(_DWORD *)(a1 + 112) )
          {
            memset(&pv, 0, sizeof(pv));
            v43[1] = 0;
            v43[0] = &CFont::`vftable';
            v41 = FreeBusyMapWnd::FSupportsDensityChange((FreeBusyMapWnd *)a1);
            a3->left += 5;
            *(_QWORD *)&v49.left = 0;
            v49.right = GdipCreatePath(0, &v49);
            v52 = *a3;
            if ( (unsigned int)GPCreateTabRectPath(&v49, &v52, 0) )
            {
              GdipDeletePath(*(_QWORD *)&v49.left);
              v43[0] = &CGdiObject::`vftable';
              CGdiObject::DeleteObject((CGdiObject *)v43);
              v43[0] = &CObject::`vftable';
              goto LABEL_34;
            }
            v55 = &Gdiplus::LinearGradientBrush::`vftable';
            v42 = 0;
            v57 = GdipCreateSolidFill(v47, &v42);
            v26 = v42;
            v56 = v42;
            v27 = GdipFillPath(v24, v42, *(_QWORD *)&v49.left);
            if ( v27 )
              v54 = v27;
            else
              v27 = 0;
            if ( v27
              || ((v28 = GdipDrawLineI(v24, v50, (unsigned int)a3->left, (unsigned int)a3->top, a3->left, a3->bottom)) != 0
                ? (v54 = v28)
                : (v28 = 0),
                  v28) )
            {
              GdipDeleteBrush(v26);
              GdipDeletePath(*(_QWORD *)&v49.left);
              v43[0] = &CGdiObject::`vftable';
              CGdiObject::DeleteObject((CGdiObject *)v43);
              v43[0] = &CObject::`vftable';
              goto LABEL_34;
            }
            v29 = -1;
            InflateRect(a3, -1, -1);
            a3->left += 3;
            LODWORD(v42) = a3->top;
            if ( !v41 )
              goto LABEL_26;
            memset(&tm, 0, sizeof(tm));
            *(_QWORD *)&v52.left = (*((__int64 (__fastcall **)(HDC *, _QWORD))*a2 + 11))(a2, *(_QWORD *)(a1 + 248));
            GetTextMetricsA(a2[2], &tm);
            LODWORD(v48) = tm.tmHeight;
            if ( *(_QWORD *)&v52.left )
              (*((void (__fastcall **)(HDC *))*a2 + 11))(a2);
            if ( a3->bottom - a3->top > (int)v48 )
            {
              *(_QWORD *)&v52.left = (*((__int64 (__fastcall **)(HDC *, _QWORD))*a2 + 11))(a2, *(_QWORD *)(a1 + 248));
              LODWORD(v42) = a3->top + (a3->bottom - a3->top - (int)v48) / 2;
            }
            else
            {
LABEL_26:
              v30 = *(_QWORD *)(a1 + 248);
              if ( v30 )
                v31 = *(void **)(v30 + 8);
              else
                v31 = 0;
              GetObjectA(v31, 60, &pv);
              *(_QWORD *)&pv.lfHeight = (unsigned int)(a3->bottom - a3->top);
              v32 = CreateFontIndirectA(&pv);
              CGdiObject::Attach((CGdiObject *)v43, v32);
              *(_QWORD *)&v52.left = (*((__int64 (__fastcall **)(HDC *, _QWORD *))*a2 + 11))(a2, v43);
            }
            CDC::SetBkMode((CDC *)a2, 1);
            LOBYTE(v33) = *(_BYTE *)(a1 + 815);
            v34 = ColorFromClrUtil(*(_QWORD *)(a1 + 848), v33, 15, 3022);
            SetTextColor(a2[1], v34);
            CDC::SetTextAlign((CDC *)a2, 0);
            if ( MsoFRtlUI() )
            {
              v39 = a3->left;
              v40 = Rect.right;
              a3->left = Rect.right - a3->right - 1;
              a3->right = v40 - v39 - 1;
            }
            do
              ++v29;
            while ( *(_WORD *)(v25 + 2 * v29) );
            MsoExtTextOutW(a2[1], (unsigned int)a3->left, (unsigned int)v42, 4, a3, v25, v29, 0);
            (*((void (__fastcall **)(HDC *, _QWORD))*a2 + 11))(a2, *(_QWORD *)&v52.left);
            CGdiObject::DeleteObject((CGdiObject *)v43);
            GdipDeleteBrush(v26);
            GdipDeletePath(*(_QWORD *)&v49.left);
            v43[0] = &CGdiObject::`vftable';
            CGdiObject::DeleteObject((CGdiObject *)v43);
          }
          GdipDrawPath(v24, v50, v44);
LABEL_34:
          GdipDeletePen(v50);
          GdipDeletePath(v44);
          v35 = v24;
          return GdipDeleteGraphics(v35);
        }
        v36 = 282965;
      }
      EtwTraceErrorTag((unsigned int)v19, v36);
    }
    GdipDeletePath(v44);
    v35 = v14;
    return GdipDeleteGraphics(v35);
  }
  return result;
}

```

## disassembly

```asm
0x140abfe48  mov     [rsp-8+arg_18], rbx
0x140abfe4d  push    rbp
0x140abfe4e  push    rsi
0x140abfe4f  push    rdi
0x140abfe50  push    r12
0x140abfe52  push    r13
0x140abfe54  push    r14
0x140abfe56  push    r15
0x140abfe58  lea     rbp, [rsp-70h]
0x140abfe5d  sub     rsp, 170h
0x140abfe64  mov     rax, cs:__security_cookie
0x140abfe6b  xor     rax, rsp
0x140abfe6e  mov     [rbp+0A0h+var_40], rax
0x140abfe72  mov     eax, r9d
0x140abfe75  mov     rdi, r8
0x140abfe78  mov     rsi, rdx
0x140abfe7b  mov     r14, rcx
0x140abfe7e  mov     rcx, [rbp+0A0h+arg_28]
0x140abfe85  mov     qword ptr [rbp+0A0h+var_100], rcx
0x140abfe89  mov     r15, [rbp+0A0h+arg_30]
0x140abfe90  mov     edx, 1
0x140abfe95  xor     r13d, r13d
0x140abfe98  cmp     [r14+70h], r13d
0x140abfe9c  jnz     loc_140AC038C
0x140abfea2  mov     ecx, r13d
0x140abfea5  lea     r12, [r8+8]
0x140abfea9  mov     [rsp+1A0h+var_170], ecx
0x140abfead  mov     dword ptr [rsp+1A0h+var_178], edx
0x140abfeb1  mov     [rsp+1A0h+var_180], r12
0x140abfeb6  mov     r9, rdi
0x140abfeb9  mov     ebx, [rbp+0A0h+arg_20]
0x140abfebf  mov     r8d, ebx
0x140abfec2  mov     edx, eax
0x140abfec4  mov     rcx, r14
0x140abfec7  call    ?DistancesFromApptBlock@FreeBusyMapWnd@@AEAAHVRTime@@0AEAH1HH@Z
0x140abfecc  test    eax, eax
0x140abfece  jz      loc_140AC0347
0x140abfed4  test    rsi, rsi
0x140abfed7  mov     rcx, r13
0x140abfeda  jz      short loc_140ABFEE0
0x140abfedc  mov     rcx, [rsi+8]
0x140abfee0  mov     [rsp+1A0h+var_128], r13
0x140abfee5  lea     rdx, [rsp+1A0h+var_128]
0x140abfeea  call    cs:__imp_GdipCreateFromHDC
0x140abfef0  mov     dword ptr [rsp+1A0h+var_158], eax
0x140abfef4  mov     r13, [rsp+1A0h+var_128]
0x140abfef9  mov     [rbp+0A0h+var_F0], r13
0x140abfefd  mov     [rsp+1A0h+var_140], 0
0x140abff06  lea     rdx, [rsp+1A0h+var_140]
0x140abff0b  xor     ecx, ecx
0x140abff0d  call    cs:__imp_GdipCreatePath
0x140abff13  mov     [rsp+1A0h+var_138], eax
0x140abff17  mov     eax, 0FF000000h
0x140abff1c  mov     [rsp+1A0h+var_130], eax
0x140abff20  mov     [rsp+1A0h+var_12C], eax
0x140abff24  xorps   xmm0, xmm0
0x140abff27  movups  xmmword ptr [rbp+0A0h+Rect.left], xmm0
0x140abff2b  mov     r11d, 0B60B60B7h
0x140abff31  mov     eax, r11d
0x140abff34  imul    ebx
0x140abff36  add     edx, ebx
0x140abff38  sar     edx, 0Ah
0x140abff3b  mov     eax, edx
0x140abff3d  shr     eax, 1Fh
0x140abff40  add     edx, eax
0x140abff42  imul    eax, edx, 5A0h
0x140abff48  sub     ebx, eax
0x140abff4a  mov     r10d, 88888889h
0x140abff50  mov     eax, r10d
0x140abff53  imul    ebx
0x140abff55  lea     r9d, [rbx+rdx]
0x140abff59  sar     r9d, 5
0x140abff5d  mov     ecx, r9d
0x140abff60  shr     ecx, 1Fh
0x140abff63  add     r9d, ecx
0x140abff66  mov     r8d, [r14+0A8h]
0x140abff6d  mov     eax, r11d
0x140abff70  imul    r8d
0x140abff73  add     edx, r8d
0x140abff76  sar     edx, 0Ah
0x140abff79  mov     ecx, edx
0x140abff7b  shr     ecx, 1Fh
0x140abff7e  add     edx, ecx
0x140abff80  imul    ecx, edx, 5A0h
0x140abff86  sub     r8d, ecx
0x140abff89  mov     eax, r10d
0x140abff8c  imul    r8d
0x140abff8f  add     edx, r8d
0x140abff92  sar     edx, 5
0x140abff95  mov     eax, edx
0x140abff97  shr     eax, 1Fh
0x140abff9a  add     edx, eax
0x140abff9c  cmp     r9d, edx
0x140abff9f  jnz     short loc_140ABFFA6
0x140abffa1  add     dword ptr [r12], 0FFFFFFFDh
0x140abffa6  call    cs:__imp_?MsoFRtlUI@@YAHXZ
0x140abffac  test    eax, eax
0x140abffae  jnz     loc_140AC051B
0x140abffb4  mov     edx, 4
0x140abffb9  mov     rcx, r13
0x140abffbc  call    cs:__imp_GdipSetSmoothingMode
0x140abffc2  test    eax, eax
0x140abffc4  mov     ecx, dword ptr [rsp+1A0h+var_158]
0x140abffc8  cmovnz  ecx, eax
0x140abffcb  mov     [rbp+0A0h+var_E8], ecx
0x140abffce  movaps  xmm0, xmmword ptr [rdi]
0x140abffd1  movdqa  [rbp+0A0h+var_120], xmm0
0x140abffd6  mov     dword ptr [rsp+1A0h+var_180], 0Fh
0x140abffde  mov     r8d, 1
0x140abffe4  lea     rdx, [rbp+0A0h+var_120]
0x140abffe8  lea     rcx, [rsp+1A0h+var_140]
0x140abffed  call    ?GPCreateTabRectPath@@YA?AW4Status@Gdiplus@@PEAVGraphicsPath@2@UtagRECT@@KHK@Z
0x140abfff2  test    eax, eax
0x140abfff4  jnz     loc_140AC037C
0x140abfffa  mov     rax, [r15]
0x140abfffd  mov     rcx, r15
0x140ac0000  mov     rax, [rax+70h]
0x140ac0004  call    cs:__guard_dispatch_icall_fptr
0x140ac000a  mov     ebx, eax
0x140ac000c  mov     rcx, [r15]
0x140ac000f  mov     rax, [rcx+0B8h]
0x140ac0016  lea     r8, [rsp+1A0h+var_130]
0x140ac001b  mov     dl, 0FFh
0x140ac001d  mov     rcx, r15
0x140ac0020  call    cs:__guard_dispatch_icall_fptr
0x140ac0026  test    eax, eax
0x140ac0028  js      loc_140AC036E
0x140ac002e  mov     rax, [r15]
0x140ac0031  lea     r8, [rsp+1A0h+var_12C]
0x140ac0036  mov     dl, 0FFh
0x140ac0038  mov     rcx, r15
0x140ac003b  mov     rax, [rax+0C0h]
0x140ac0042  call    cs:__guard_dispatch_icall_fptr
0x140ac0048  xor     r15d, r15d
0x140ac004b  test    eax, eax
0x140ac004d  js      loc_140AC0544
0x140ac0053  mov     rcx, [rsi+10h]; hdc
0x140ac0057  call    cs:__imp_GetBkColor
0x140ac005d  mov     dword ptr [rsp+1A0h+var_180], eax
0x140ac0061  mov     r9d, ebx
0x140ac0064  mov     r8b, 0FFh
0x140ac0067  lea     rdx, [rsp+1A0h+var_140]
0x140ac006c  lea     rcx, [rbp+0A0h+var_F0]
0x140ac0070  call    ?GPFillFreeBusyRegion@@YA?AW4Status@Gdiplus@@AEAVGraphics@2@AEAVGraphicsPath@2@EW4FBBrush@@K@Z
0x140ac0075  test    eax, eax
0x140ac0077  jnz     loc_140AC03E6
0x140ac007d  mov     [rbp+0A0h+var_110], r15
0x140ac0081  lea     r9, [rbp+0A0h+var_110]
0x140ac0085  xor     r8d, r8d
0x140ac0088  movss   xmm1, cs:__real@3f800000
0x140ac0090  mov     ecx, [rsp+1A0h+var_130]
0x140ac0094  call    cs:__imp_GdipCreatePen1
0x140ac009a  mov     [rbp+0A0h+var_108], eax
0x140ac009d  mov     rbx, [rbp+0A0h+var_F0]
0x140ac00a1  mov     r13, qword ptr [rbp+0A0h+var_100]
0x140ac00a5  test    r13, r13
0x140ac00a8  jz      loc_140AC0316
0x140ac00ae  cmp     [r14+70h], r15d
0x140ac00b2  jz      loc_140AC0316
0x140ac00b8  xorps   xmm0, xmm0
0x140ac00bb  xor     eax, eax
0x140ac00bd  movups  [rbp+0A0h+pv], xmm0
0x140ac00c1  movups  [rbp+0A0h+var_A8], xmm0
0x140ac00c5  movups  [rbp+0A0h+var_98], xmm0
0x140ac00c9  mov     [rbp+0A0h+var_88], rax
0x140ac00cd  mov     [rbp+0A0h+var_80], eax
0x140ac00d0  mov     [rsp+1A0h+var_148], r15
0x140ac00d5  lea     rax, ??_7CFont@@6B@
0x140ac00dc  mov     [rsp+1A0h+var_150], rax
0x140ac00e1  mov     rcx, r14; this
0x140ac00e4  call    ?FSupportsDensityChange@FreeBusyMapWnd@@IEAA_NXZ
0x140ac00e9  mov     [rsp+1A0h+var_160], al
0x140ac00ed  add     dword ptr [rdi], 5
0x140ac00f0  mov     qword ptr [rbp+0A0h+var_120], r15
0x140ac00f4  lea     rdx, [rbp+0A0h+var_120]
0x140ac00f8  xor     ecx, ecx
0x140ac00fa  call    cs:__imp_GdipCreatePath
0x140ac0100  mov     dword ptr [rbp+0A0h+var_120+8], eax
0x140ac0103  movaps  xmm0, xmmword ptr [rdi]
0x140ac0106  movdqa  [rbp+0A0h+var_100], xmm0
0x140ac010b  mov     dword ptr [rsp+1A0h+var_180], 6
0x140ac0113  xor     r8d, r8d
0x140ac0116  lea     rdx, [rbp+0A0h+var_100]
0x140ac011a  lea     rcx, [rbp+0A0h+var_120]
0x140ac011e  call    ?GPCreateTabRectPath@@YA?AW4Status@Gdiplus@@PEAVGraphicsPath@2@UtagRECT@@KHK@Z
0x140ac0123  test    eax, eax
0x140ac0125  jnz     loc_140AC0441
0x140ac012b  lea     rax, ??_7LinearGradientBrush@Gdiplus@@6B@
0x140ac0132  mov     [rbp+0A0h+var_E0], rax
0x140ac0136  mov     [rsp+1A0h+var_158], r15
0x140ac013b  lea     rdx, [rsp+1A0h+var_158]
0x140ac0140  mov     ecx, [rsp+1A0h+var_12C]
0x140ac0144  call    cs:__imp_GdipCreateSolidFill
0x140ac014a  mov     [rbp+0A0h+var_D0], eax
0x140ac014d  mov     r12, [rsp+1A0h+var_158]
0x140ac0152  mov     [rbp+0A0h+var_D8], r12
0x140ac0156  mov     r8, qword ptr [rbp+0A0h+var_120]
0x140ac015a  mov     rdx, r12
0x140ac015d  mov     rcx, rbx
0x140ac0160  call    cs:__imp_GdipFillPath
0x140ac0166  test    eax, eax
0x140ac0168  jnz     loc_140AC03D6
0x140ac016e  mov     eax, r15d
0x140ac0171  test    eax, eax
0x140ac0173  jnz     loc_140AC0400
0x140ac0179  mov     r8d, [rdi]
0x140ac017c  mov     eax, [rdi+0Ch]
0x140ac017f  mov     dword ptr [rsp+1A0h+var_178], eax
0x140ac0183  mov     dword ptr [rsp+1A0h+var_180], r8d
0x140ac0188  mov     r9d, [rdi+4]
0x140ac018c  mov     rdx, [rbp+0A0h+var_110]
0x140ac0190  mov     rcx, rbx
0x140ac0193  call    cs:__imp_GdipDrawLineI
0x140ac0199  test    eax, eax
0x140ac019b  jnz     loc_140AC03DE
0x140ac01a1  mov     eax, r15d
0x140ac01a4  test    eax, eax
0x140ac01a6  jnz     loc_140AC039C
0x140ac01ac  or      r15, 0FFFFFFFFFFFFFFFFh
0x140ac01b0  mov     r8d, r15d; dy
0x140ac01b3  mov     edx, r15d; dx
0x140ac01b6  mov     rcx, rdi; lprc
0x140ac01b9  call    cs:__imp_InflateRect
0x140ac01bf  add     dword ptr [rdi], 3
0x140ac01c2  mov     eax, [rdi+4]
0x140ac01c5  mov     dword ptr [rsp+1A0h+var_158], eax
0x140ac01c9  cmp     [rsp+1A0h+var_160], 0
0x140ac01ce  jnz     loc_140AC0472
0x140ac01d4  mov     rax, [r14+0F8h]
0x140ac01db  test    rax, rax
0x140ac01de  jz      loc_140AC043A
0x140ac01e4  mov     rcx, [rax+8]; h
0x140ac01e8  lea     r8, [rbp+0A0h+pv]; pv
0x140ac01ec  mov     edx, 3Ch ; '<'; c
0x140ac01f1  call    cs:__imp_GetObjectA
0x140ac01f7  mov     dword ptr [rbp+0A0h+pv+4], 0
0x140ac01fe  mov     eax, [rdi+0Ch]
0x140ac0201  sub     eax, [rdi+4]
0x140ac0204  mov     dword ptr [rbp+0A0h+pv], eax
0x140ac0207  lea     rcx, [rbp+0A0h+pv]; lplf
0x140ac020b  call    cs:__imp_CreateFontIndirectA
0x140ac0211  mov     rdx, rax; void *
0x140ac0214  lea     rcx, [rsp+1A0h+var_150]; this
0x140ac0219  call    ?Attach@CGdiObject@@QEAAHPEAX@Z
0x140ac021e  mov     rax, [rsi]
0x140ac0221  lea     rdx, [rsp+1A0h+var_150]
0x140ac0226  mov     rcx, rsi
0x140ac0229  mov     rax, [rax+58h]
0x140ac022d  call    cs:__guard_dispatch_icall_fptr
0x140ac0233  mov     qword ptr [rbp+0A0h+var_100], rax
0x140ac0237  mov     edx, 1; int
0x140ac023c  mov     rcx, rsi; this
0x140ac023f  call    ?SetBkMode@CDC@@QEAAHH@Z
0x140ac0244  mov     r8d, 0Fh
0x140ac024a  mov     r9d, 0BCEh
0x140ac0250  mov     dl, [r14+32Fh]
0x140ac0257  mov     rcx, [r14+350h]
0x140ac025e  call    ?ColorFromClrUtil@@YAKPEAU?$ITPalette@W4OutlookCustomSwatch@OLKColor@@@UIColor@Mso@@_NW4OutlookCustomSwatch@OLKColor@@W4_msocbvcr@@@Z
0x140ac0263  mov     edx, eax; color
0x140ac0265  mov     rcx, [rsi+8]; hdc
0x140ac0269  call    cs:__imp_SetTextColor
0x140ac026f  xor     edx, edx; unsigned int
0x140ac0271  mov     rcx, rsi; this
0x140ac0274  call    ?SetTextAlign@CDC@@QEAAII@Z
0x140ac0279  call    cs:__imp_?MsoFRtlUI@@YAHXZ
0x140ac027f  xor     ecx, ecx
0x140ac0281  test    eax, eax
0x140ac0283  jnz     loc_140AC054E
0x140ac0289  inc     r15
0x140ac028c  cmp     [r13+r15*2+0], cx
0x140ac0292  jnz     short loc_140AC0289
0x140ac0294  mov     [rsp+1A0h+var_168], rcx
0x140ac0299  mov     [rsp+1A0h+var_170], r15d
0x140ac029e  mov     [rsp+1A0h+var_178], r13
0x140ac02a3  mov     [rsp+1A0h+var_180], rdi
0x140ac02a8  mov     r9d, 4
0x140ac02ae  mov     r8d, dword ptr [rsp+1A0h+var_158]
0x140ac02b3  mov     edx, [rdi]
0x140ac02b5  mov     rcx, [rsi+8]
0x140ac02b9  call    cs:__imp_MsoExtTextOutW
0x140ac02bf  mov     rax, [rsi]
0x140ac02c2  mov     rdx, qword ptr [rbp+0A0h+var_100]
0x140ac02c6  mov     rcx, rsi
0x140ac02c9  mov     rax, [rax+58h]
0x140ac02cd  call    cs:__guard_dispatch_icall_fptr
0x140ac02d3  lea     rcx, [rsp+1A0h+var_150]; this
0x140ac02d8  call    ?DeleteObject@CGdiObject@@QEAAHXZ
0x140ac02dd  nop
0x140ac02de  mov     rcx, r12
0x140ac02e1  call    cs:__imp_GdipDeleteBrush
0x140ac02e7  mov     rcx, qword ptr [rbp+0A0h+var_120]
0x140ac02eb  call    cs:__imp_GdipDeletePath
0x140ac02f1  lea     rax, ??_7CGdiObject@@6B@
0x140ac02f8  mov     [rsp+1A0h+var_150], rax
0x140ac02fd  lea     rcx, [rsp+1A0h+var_150]; this
0x140ac0302  nop     dword ptr [rax+00h]
0x140ac0306  nop     word ptr [rax+rax+00000000h]
0x140ac0310  call    ?DeleteObject@CGdiObject@@QEAAHXZ
0x140ac0315  nop
0x140ac0316  mov     r8, [rsp+1A0h+var_140]
  ... truncated ...
```
