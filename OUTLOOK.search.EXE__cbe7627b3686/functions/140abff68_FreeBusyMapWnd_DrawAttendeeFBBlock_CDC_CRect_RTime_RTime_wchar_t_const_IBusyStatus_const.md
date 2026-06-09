# FreeBusyMapWnd::DrawAttendeeFBBlock(CDC *,CRect,RTime,RTime,wchar_t const *,IBusyStatus const *)

- ea: `0x140abff68`
- end: `0x140ac068b`
- name: `?DrawAttendeeFBBlock@FreeBusyMapWnd@@AEAAXPEAVCDC@@VCRect@@VRTime@@2PEB_WPEBUIBusyStatus@@@Z`
- size: `1827`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x140abde4c`
- `0x140abe290`
- `0x140abf8b0`

## callees

- `0x140257240`
- `0x140258580`
- `0x14025862c`
- `0x1405049f0`
- `0x14066f0d0`
- `0x140770254`
- `0x1407e9990`
- `0x140abff68`
- `0x140ac0690`
- `0x140ac0b50`
- `0x140ac15a0`
- `0x140ac15b4`

## import_xrefs

- `OLMAPI32!EtwTraceErrorTag` at `0x140ac0495`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac0495`
- `GDI32!GetBkColor` at `0x140ac0177`
- `GDI32!GetBkColor` at `0x140ac0177`
- `GDI32!CreateFontIndirectA` at `0x140ac032b`
- `GDI32!CreateFontIndirectA` at `0x140ac032b`
- `GDI32!GetObjectA` at `0x140ac0311`
- `GDI32!GetObjectA` at `0x140ac0311`
- `GDI32!SetTextColor` at `0x140ac0389`
- `GDI32!SetTextColor` at `0x140ac0389`
- `GDI32!GetTextMetricsA` at `0x140ac05ca`
- `GDI32!GetTextMetricsA` at `0x140ac05ca`
- `gdiplus!GdipDeletePen` at `0x140ac044d`
- `gdiplus!GdipDeletePen` at `0x140ac044d`
- `gdiplus!GdipSetSmoothingMode` at `0x140ac00dc`
- `gdiplus!GdipSetSmoothingMode` at `0x140ac00dc`
- `gdiplus!GdipDeleteGraphics` at `0x140ac0461`
- `gdiplus!GdipDeleteGraphics` at `0x140ac0461`
- `gdiplus!GdipDeleteBrush` at `0x140ac0401`
- `gdiplus!GdipDeleteBrush` at `0x140ac04bf`
- `gdiplus!GdipDeleteBrush` at `0x140ac0523`
- `gdiplus!GdipDeleteBrush` at `0x140ac0401`
- `gdiplus!GdipDeleteBrush` at `0x140ac04bf`
- `gdiplus!GdipDeleteBrush` at `0x140ac0523`
- `gdiplus!GdipCreateFromHDC` at `0x140ac000a`
- `gdiplus!GdipCreateFromHDC` at `0x140ac000a`
- `gdiplus!GdipCreateSolidFill` at `0x140ac0264`
- `gdiplus!GdipCreateSolidFill` at `0x140ac0264`
- `gdiplus!GdipFillPath` at `0x140ac0280`
- `gdiplus!GdipFillPath` at `0x140ac0280`
- `gdiplus!GdipCreatePath` at `0x140ac002d`
- `gdiplus!GdipCreatePath` at `0x140ac021a`
- `gdiplus!GdipCreatePath` at `0x140ac002d`
- `gdiplus!GdipCreatePath` at `0x140ac021a`
- `gdiplus!GdipDeletePath` at `0x140ac040b`
- `gdiplus!GdipDeletePath` at `0x140ac0458`
- `gdiplus!GdipDeletePath` at `0x140ac04a1`
- `gdiplus!GdipDeletePath` at `0x140ac04c9`
- `gdiplus!GdipDeletePath` at `0x140ac050b`
- `gdiplus!GdipDeletePath` at `0x140ac052d`
- `gdiplus!GdipDeletePath` at `0x140ac0565`
- `gdiplus!GdipDeletePath` at `0x140ac040b`
- `gdiplus!GdipDeletePath` at `0x140ac0458`
- `gdiplus!GdipDeletePath` at `0x140ac04a1`
- `gdiplus!GdipDeletePath` at `0x140ac04c9`
- `gdiplus!GdipDeletePath` at `0x140ac050b`
- `gdiplus!GdipDeletePath` at `0x140ac052d`
- `gdiplus!GdipDeletePath` at `0x140ac0565`
- `gdiplus!GdipCreatePen1` at `0x140ac01b4`
- `gdiplus!GdipCreatePen1` at `0x140ac01b4`
- `gdiplus!GdipDrawPath` at `0x140ac0442`
- `gdiplus!GdipDrawPath` at `0x140ac0442`
- `gdiplus!GdipDrawLineI` at `0x140ac02b3`
- `gdiplus!GdipDrawLineI` at `0x140ac02b3`
- `USER32!InflateRect` at `0x140ac02d9`
- `USER32!InflateRect` at `0x140ac02d9`
- `USER32!GetClientRect` at `0x140ac0645`
- `USER32!GetClientRect` at `0x140ac0645`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x140ac03d9`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x140ac03d9`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x140ac00c6`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x140ac0399`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x140ac00c6`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x140ac0399`

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
0x140abff68  mov     [rsp-8+arg_18], rbx
0x140abff6d  push    rbp
0x140abff6e  push    rsi
0x140abff6f  push    rdi
0x140abff70  push    r12
0x140abff72  push    r13
0x140abff74  push    r14
0x140abff76  push    r15
0x140abff78  lea     rbp, [rsp-70h]
0x140abff7d  sub     rsp, 170h
0x140abff84  mov     rax, cs:__security_cookie
0x140abff8b  xor     rax, rsp
0x140abff8e  mov     [rbp+0A0h+var_40], rax
0x140abff92  mov     eax, r9d
0x140abff95  mov     rdi, r8
0x140abff98  mov     rsi, rdx
0x140abff9b  mov     r14, rcx
0x140abff9e  mov     rcx, [rbp+0A0h+arg_28]
0x140abffa5  mov     qword ptr [rbp+0A0h+var_100], rcx
0x140abffa9  mov     r15, [rbp+0A0h+arg_30]
0x140abffb0  mov     edx, 1
0x140abffb5  xor     r13d, r13d
0x140abffb8  cmp     [r14+70h], r13d
0x140abffbc  jnz     loc_140AC04AC
0x140abffc2  mov     ecx, r13d
0x140abffc5  lea     r12, [r8+8]
0x140abffc9  mov     [rsp+1A0h+var_170], ecx
0x140abffcd  mov     dword ptr [rsp+1A0h+var_178], edx
0x140abffd1  mov     [rsp+1A0h+var_180], r12
0x140abffd6  mov     r9, rdi
0x140abffd9  mov     ebx, [rbp+0A0h+arg_20]
0x140abffdf  mov     r8d, ebx
0x140abffe2  mov     edx, eax
0x140abffe4  mov     rcx, r14
0x140abffe7  call    ?DistancesFromApptBlock@FreeBusyMapWnd@@AEAAHVRTime@@0AEAH1HH@Z
0x140abffec  test    eax, eax
0x140abffee  jz      loc_140AC0467
0x140abfff4  test    rsi, rsi
0x140abfff7  mov     rcx, r13
0x140abfffa  jz      short loc_140AC0000
0x140abfffc  mov     rcx, [rsi+8]
0x140ac0000  mov     [rsp+1A0h+var_128], r13
0x140ac0005  lea     rdx, [rsp+1A0h+var_128]
0x140ac000a  call    cs:__imp_GdipCreateFromHDC
0x140ac0010  mov     dword ptr [rsp+1A0h+var_158], eax
0x140ac0014  mov     r13, [rsp+1A0h+var_128]
0x140ac0019  mov     [rbp+0A0h+var_F0], r13
0x140ac001d  mov     [rsp+1A0h+var_140], 0
0x140ac0026  lea     rdx, [rsp+1A0h+var_140]
0x140ac002b  xor     ecx, ecx
0x140ac002d  call    cs:__imp_GdipCreatePath
0x140ac0033  mov     [rsp+1A0h+var_138], eax
0x140ac0037  mov     eax, 0FF000000h
0x140ac003c  mov     [rsp+1A0h+var_130], eax
0x140ac0040  mov     [rsp+1A0h+var_12C], eax
0x140ac0044  xorps   xmm0, xmm0
0x140ac0047  movups  xmmword ptr [rbp+0A0h+Rect.left], xmm0
0x140ac004b  mov     r11d, 0B60B60B7h
0x140ac0051  mov     eax, r11d
0x140ac0054  imul    ebx
0x140ac0056  add     edx, ebx
0x140ac0058  sar     edx, 0Ah
0x140ac005b  mov     eax, edx
0x140ac005d  shr     eax, 1Fh
0x140ac0060  add     edx, eax
0x140ac0062  imul    eax, edx, 5A0h
0x140ac0068  sub     ebx, eax
0x140ac006a  mov     r10d, 88888889h
0x140ac0070  mov     eax, r10d
0x140ac0073  imul    ebx
0x140ac0075  lea     r9d, [rbx+rdx]
0x140ac0079  sar     r9d, 5
0x140ac007d  mov     ecx, r9d
0x140ac0080  shr     ecx, 1Fh
0x140ac0083  add     r9d, ecx
0x140ac0086  mov     r8d, [r14+0A8h]
0x140ac008d  mov     eax, r11d
0x140ac0090  imul    r8d
0x140ac0093  add     edx, r8d
0x140ac0096  sar     edx, 0Ah
0x140ac0099  mov     ecx, edx
0x140ac009b  shr     ecx, 1Fh
0x140ac009e  add     edx, ecx
0x140ac00a0  imul    ecx, edx, 5A0h
0x140ac00a6  sub     r8d, ecx
0x140ac00a9  mov     eax, r10d
0x140ac00ac  imul    r8d
0x140ac00af  add     edx, r8d
0x140ac00b2  sar     edx, 5
0x140ac00b5  mov     eax, edx
0x140ac00b7  shr     eax, 1Fh
0x140ac00ba  add     edx, eax
0x140ac00bc  cmp     r9d, edx
0x140ac00bf  jnz     short loc_140AC00C6
0x140ac00c1  add     dword ptr [r12], 0FFFFFFFDh
0x140ac00c6  call    cs:__imp_?MsoFRtlUI@@YAHXZ
0x140ac00cc  test    eax, eax
0x140ac00ce  jnz     loc_140AC063B
0x140ac00d4  mov     edx, 4
0x140ac00d9  mov     rcx, r13
0x140ac00dc  call    cs:__imp_GdipSetSmoothingMode
0x140ac00e2  test    eax, eax
0x140ac00e4  mov     ecx, dword ptr [rsp+1A0h+var_158]
0x140ac00e8  cmovnz  ecx, eax
0x140ac00eb  mov     [rbp+0A0h+var_E8], ecx
0x140ac00ee  movaps  xmm0, xmmword ptr [rdi]
0x140ac00f1  movdqa  [rbp+0A0h+var_120], xmm0
0x140ac00f6  mov     dword ptr [rsp+1A0h+var_180], 0Fh
0x140ac00fe  mov     r8d, 1
0x140ac0104  lea     rdx, [rbp+0A0h+var_120]
0x140ac0108  lea     rcx, [rsp+1A0h+var_140]
0x140ac010d  call    ?GPCreateTabRectPath@@YA?AW4Status@Gdiplus@@PEAVGraphicsPath@2@UtagRECT@@KHK@Z
0x140ac0112  test    eax, eax
0x140ac0114  jnz     loc_140AC049C
0x140ac011a  mov     rax, [r15]
0x140ac011d  mov     rcx, r15
0x140ac0120  mov     rax, [rax+70h]
0x140ac0124  call    cs:__guard_dispatch_icall_fptr
0x140ac012a  mov     ebx, eax
0x140ac012c  mov     rcx, [r15]
0x140ac012f  mov     rax, [rcx+0B8h]
0x140ac0136  lea     r8, [rsp+1A0h+var_130]
0x140ac013b  mov     dl, 0FFh
0x140ac013d  mov     rcx, r15
0x140ac0140  call    cs:__guard_dispatch_icall_fptr
0x140ac0146  test    eax, eax
0x140ac0148  js      loc_140AC048E
0x140ac014e  mov     rax, [r15]
0x140ac0151  lea     r8, [rsp+1A0h+var_12C]
0x140ac0156  mov     dl, 0FFh
0x140ac0158  mov     rcx, r15
0x140ac015b  mov     rax, [rax+0C0h]
0x140ac0162  call    cs:__guard_dispatch_icall_fptr
0x140ac0168  xor     r15d, r15d
0x140ac016b  test    eax, eax
0x140ac016d  js      loc_140AC0664
0x140ac0173  mov     rcx, [rsi+10h]; hdc
0x140ac0177  call    cs:__imp_GetBkColor
0x140ac017d  mov     dword ptr [rsp+1A0h+var_180], eax
0x140ac0181  mov     r9d, ebx
0x140ac0184  mov     r8b, 0FFh
0x140ac0187  lea     rdx, [rsp+1A0h+var_140]
0x140ac018c  lea     rcx, [rbp+0A0h+var_F0]
0x140ac0190  call    ?GPFillFreeBusyRegion@@YA?AW4Status@Gdiplus@@AEAVGraphics@2@AEAVGraphicsPath@2@EW4FBBrush@@K@Z
0x140ac0195  test    eax, eax
0x140ac0197  jnz     loc_140AC0506
0x140ac019d  mov     [rbp+0A0h+var_110], r15
0x140ac01a1  lea     r9, [rbp+0A0h+var_110]
0x140ac01a5  xor     r8d, r8d
0x140ac01a8  movss   xmm1, cs:__real@3f800000
0x140ac01b0  mov     ecx, [rsp+1A0h+var_130]
0x140ac01b4  call    cs:__imp_GdipCreatePen1
0x140ac01ba  mov     [rbp+0A0h+var_108], eax
0x140ac01bd  mov     rbx, [rbp+0A0h+var_F0]
0x140ac01c1  mov     r13, qword ptr [rbp+0A0h+var_100]
0x140ac01c5  test    r13, r13
0x140ac01c8  jz      loc_140AC0436
0x140ac01ce  cmp     [r14+70h], r15d
0x140ac01d2  jz      loc_140AC0436
0x140ac01d8  xorps   xmm0, xmm0
0x140ac01db  xor     eax, eax
0x140ac01dd  movups  [rbp+0A0h+pv], xmm0
0x140ac01e1  movups  [rbp+0A0h+var_A8], xmm0
0x140ac01e5  movups  [rbp+0A0h+var_98], xmm0
0x140ac01e9  mov     [rbp+0A0h+var_88], rax
0x140ac01ed  mov     [rbp+0A0h+var_80], eax
0x140ac01f0  mov     [rsp+1A0h+var_148], r15
0x140ac01f5  lea     rax, ??_7CFont@@6B@
0x140ac01fc  mov     [rsp+1A0h+var_150], rax
0x140ac0201  mov     rcx, r14; this
0x140ac0204  call    ?FSupportsDensityChange@FreeBusyMapWnd@@IEAA_NXZ
0x140ac0209  mov     [rsp+1A0h+var_160], al
0x140ac020d  add     dword ptr [rdi], 5
0x140ac0210  mov     qword ptr [rbp+0A0h+var_120], r15
0x140ac0214  lea     rdx, [rbp+0A0h+var_120]
0x140ac0218  xor     ecx, ecx
0x140ac021a  call    cs:__imp_GdipCreatePath
0x140ac0220  mov     dword ptr [rbp+0A0h+var_120+8], eax
0x140ac0223  movaps  xmm0, xmmword ptr [rdi]
0x140ac0226  movdqa  [rbp+0A0h+var_100], xmm0
0x140ac022b  mov     dword ptr [rsp+1A0h+var_180], 6
0x140ac0233  xor     r8d, r8d
0x140ac0236  lea     rdx, [rbp+0A0h+var_100]
0x140ac023a  lea     rcx, [rbp+0A0h+var_120]
0x140ac023e  call    ?GPCreateTabRectPath@@YA?AW4Status@Gdiplus@@PEAVGraphicsPath@2@UtagRECT@@KHK@Z
0x140ac0243  test    eax, eax
0x140ac0245  jnz     loc_140AC0561
0x140ac024b  lea     rax, ??_7LinearGradientBrush@Gdiplus@@6B@
0x140ac0252  mov     [rbp+0A0h+var_E0], rax
0x140ac0256  mov     [rsp+1A0h+var_158], r15
0x140ac025b  lea     rdx, [rsp+1A0h+var_158]
0x140ac0260  mov     ecx, [rsp+1A0h+var_12C]
0x140ac0264  call    cs:__imp_GdipCreateSolidFill
0x140ac026a  mov     [rbp+0A0h+var_D0], eax
0x140ac026d  mov     r12, [rsp+1A0h+var_158]
0x140ac0272  mov     [rbp+0A0h+var_D8], r12
0x140ac0276  mov     r8, qword ptr [rbp+0A0h+var_120]
0x140ac027a  mov     rdx, r12
0x140ac027d  mov     rcx, rbx
0x140ac0280  call    cs:__imp_GdipFillPath
0x140ac0286  test    eax, eax
0x140ac0288  jnz     loc_140AC04F6
0x140ac028e  mov     eax, r15d
0x140ac0291  test    eax, eax
0x140ac0293  jnz     loc_140AC0520
0x140ac0299  mov     r8d, [rdi]
0x140ac029c  mov     eax, [rdi+0Ch]
0x140ac029f  mov     dword ptr [rsp+1A0h+var_178], eax
0x140ac02a3  mov     dword ptr [rsp+1A0h+var_180], r8d
0x140ac02a8  mov     r9d, [rdi+4]
0x140ac02ac  mov     rdx, [rbp+0A0h+var_110]
0x140ac02b0  mov     rcx, rbx
0x140ac02b3  call    cs:__imp_GdipDrawLineI
0x140ac02b9  test    eax, eax
0x140ac02bb  jnz     loc_140AC04FE
0x140ac02c1  mov     eax, r15d
0x140ac02c4  test    eax, eax
0x140ac02c6  jnz     loc_140AC04BC
0x140ac02cc  or      r15, 0FFFFFFFFFFFFFFFFh
0x140ac02d0  mov     r8d, r15d; dy
0x140ac02d3  mov     edx, r15d; dx
0x140ac02d6  mov     rcx, rdi; lprc
0x140ac02d9  call    cs:__imp_InflateRect
0x140ac02df  add     dword ptr [rdi], 3
0x140ac02e2  mov     eax, [rdi+4]
0x140ac02e5  mov     dword ptr [rsp+1A0h+var_158], eax
0x140ac02e9  cmp     [rsp+1A0h+var_160], 0
0x140ac02ee  jnz     loc_140AC0592
0x140ac02f4  mov     rax, [r14+0F8h]
0x140ac02fb  test    rax, rax
0x140ac02fe  jz      loc_140AC055A
0x140ac0304  mov     rcx, [rax+8]; h
0x140ac0308  lea     r8, [rbp+0A0h+pv]; pv
0x140ac030c  mov     edx, 3Ch ; '<'; c
0x140ac0311  call    cs:__imp_GetObjectA
0x140ac0317  mov     dword ptr [rbp+0A0h+pv+4], 0
0x140ac031e  mov     eax, [rdi+0Ch]
0x140ac0321  sub     eax, [rdi+4]
0x140ac0324  mov     dword ptr [rbp+0A0h+pv], eax
0x140ac0327  lea     rcx, [rbp+0A0h+pv]; lplf
0x140ac032b  call    cs:__imp_CreateFontIndirectA
0x140ac0331  mov     rdx, rax; void *
0x140ac0334  lea     rcx, [rsp+1A0h+var_150]; this
0x140ac0339  call    ?Attach@CGdiObject@@QEAAHPEAX@Z
0x140ac033e  mov     rax, [rsi]
0x140ac0341  lea     rdx, [rsp+1A0h+var_150]
0x140ac0346  mov     rcx, rsi
0x140ac0349  mov     rax, [rax+58h]
0x140ac034d  call    cs:__guard_dispatch_icall_fptr
0x140ac0353  mov     qword ptr [rbp+0A0h+var_100], rax
0x140ac0357  mov     edx, 1; int
0x140ac035c  mov     rcx, rsi; this
0x140ac035f  call    ?SetBkMode@CDC@@QEAAHH@Z
0x140ac0364  mov     r8d, 0Fh
0x140ac036a  mov     r9d, 0BCEh
0x140ac0370  mov     dl, [r14+32Fh]
0x140ac0377  mov     rcx, [r14+350h]
0x140ac037e  call    ?ColorFromClrUtil@@YAKPEAU?$ITPalette@W4OutlookCustomSwatch@OLKColor@@@UIColor@Mso@@_NW4OutlookCustomSwatch@OLKColor@@W4_msocbvcr@@@Z
0x140ac0383  mov     edx, eax; color
0x140ac0385  mov     rcx, [rsi+8]; hdc
0x140ac0389  call    cs:__imp_SetTextColor
0x140ac038f  xor     edx, edx; unsigned int
0x140ac0391  mov     rcx, rsi; this
0x140ac0394  call    ?SetTextAlign@CDC@@QEAAII@Z
0x140ac0399  call    cs:__imp_?MsoFRtlUI@@YAHXZ
0x140ac039f  xor     ecx, ecx
0x140ac03a1  test    eax, eax
0x140ac03a3  jnz     loc_140AC066E
0x140ac03a9  inc     r15
0x140ac03ac  cmp     [r13+r15*2+0], cx
0x140ac03b2  jnz     short loc_140AC03A9
0x140ac03b4  mov     [rsp+1A0h+var_168], rcx
0x140ac03b9  mov     [rsp+1A0h+var_170], r15d
0x140ac03be  mov     [rsp+1A0h+var_178], r13
0x140ac03c3  mov     [rsp+1A0h+var_180], rdi
0x140ac03c8  mov     r9d, 4
0x140ac03ce  mov     r8d, dword ptr [rsp+1A0h+var_158]
0x140ac03d3  mov     edx, [rdi]
0x140ac03d5  mov     rcx, [rsi+8]
0x140ac03d9  call    cs:__imp_MsoExtTextOutW
0x140ac03df  mov     rax, [rsi]
0x140ac03e2  mov     rdx, qword ptr [rbp+0A0h+var_100]
0x140ac03e6  mov     rcx, rsi
0x140ac03e9  mov     rax, [rax+58h]
0x140ac03ed  call    cs:__guard_dispatch_icall_fptr
0x140ac03f3  lea     rcx, [rsp+1A0h+var_150]; this
0x140ac03f8  call    ?DeleteObject@CGdiObject@@QEAAHXZ
0x140ac03fd  nop
0x140ac03fe  mov     rcx, r12
0x140ac0401  call    cs:__imp_GdipDeleteBrush
0x140ac0407  mov     rcx, qword ptr [rbp+0A0h+var_120]
0x140ac040b  call    cs:__imp_GdipDeletePath
0x140ac0411  lea     rax, ??_7CGdiObject@@6B@
0x140ac0418  mov     [rsp+1A0h+var_150], rax
0x140ac041d  lea     rcx, [rsp+1A0h+var_150]; this
0x140ac0422  nop     dword ptr [rax+00h]
0x140ac0426  nop     word ptr [rax+rax+00000000h]
0x140ac0430  call    ?DeleteObject@CGdiObject@@QEAAHXZ
0x140ac0435  nop
0x140ac0436  mov     r8, [rsp+1A0h+var_140]
  ... truncated ...
```
