# DSMAP::DrawItem(tagDRAWITEMSTRUCT *)

- ea: `0x181446f68`
- end: `0x1814474df`
- name: `?DrawItem@DSMAP@@IEAAXPEAUtagDRAWITEMSTRUCT@@@Z`
- size: `1399`
- prototype: `void __fastcall(DSMAP *__hidden this, struct tagDRAWITEMSTRUCT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x181448ef0`

## callees

- `0x180239aa0`
- `0x18023c2e0`
- `0x180741be8`
- `0x181446f68`
- `0x1814474e0`

## import_xrefs

- `Mso30Win32Client!__imp_MsoSgnWzCompare` at `0x181447370`
- `Mso30Win32Client!__imp_MsoSgnWzCompare` at `0x1814473a0`
- `Mso30Win32Client!__imp_MsoSgnWzCompare` at `0x181447370`
- `Mso30Win32Client!__imp_MsoSgnWzCompare` at `0x1814473a0`
- `USER32!GetFocus` at `0x181447160`
- `USER32!GetFocus` at `0x181447160`
- `USER32!DrawTextW` at `0x18144740a`
- `USER32!DrawTextW` at `0x18144740a`
- `USER32!GetSysColor` at `0x181446fc7`
- `USER32!GetSysColor` at `0x181446fd4`
- `USER32!GetSysColor` at `0x181446fe5`
- `USER32!GetSysColor` at `0x18144702d`
- `USER32!GetSysColor` at `0x181447043`
- `USER32!GetSysColor` at `0x18144727f`
- `USER32!GetSysColor` at `0x181447295`
- `USER32!GetSysColor` at `0x1814472b2`
- `USER32!GetSysColor` at `0x1814472c8`
- `USER32!GetSysColor` at `0x181446fc7`
- `USER32!GetSysColor` at `0x181446fd4`
- `USER32!GetSysColor` at `0x181446fe5`
- `USER32!GetSysColor` at `0x18144702d`
- `USER32!GetSysColor` at `0x181447043`
- `USER32!GetSysColor` at `0x18144727f`
- `USER32!GetSysColor` at `0x181447295`
- `USER32!GetSysColor` at `0x1814472b2`
- `USER32!GetSysColor` at `0x1814472c8`
- `USER32!FillRect` at `0x1814472ed`
- `USER32!FillRect` at `0x1814472ed`
- `USER32!DrawFocusRect` at `0x181447444`
- `USER32!DrawFocusRect` at `0x181447444`
- `USER32!SendMessageW` at `0x181447023`
- `USER32!SendMessageW` at `0x181447197`
- `USER32!SendMessageW` at `0x181447251`
- `USER32!SendMessageW` at `0x181447423`
- `USER32!SendMessageW` at `0x181447023`
- `USER32!SendMessageW` at `0x181447197`
- `USER32!SendMessageW` at `0x181447251`
- `USER32!SendMessageW` at `0x181447423`
- `GDI32!MoveToEx` at `0x181447303`
- `GDI32!MoveToEx` at `0x181447303`
- `GDI32!LineTo` at `0x181447318`
- `GDI32!LineTo` at `0x18144732d`
- `GDI32!LineTo` at `0x181447318`
- `GDI32!LineTo` at `0x18144732d`
- `GDI32!CreatePen` at `0x18144710f`
- `GDI32!CreatePen` at `0x18144710f`
- `GDI32!SaveDC` at `0x181446ff0`
- `GDI32!SaveDC` at `0x181446ff0`
- `GDI32!RestoreDC` at `0x18144747f`
- `GDI32!RestoreDC` at `0x18144747f`
- `GDI32!SetTextColor` at `0x18144728a`
- `GDI32!SetTextColor` at `0x1814472bd`
- `GDI32!SetTextColor` at `0x18144728a`
- `GDI32!SetTextColor` at `0x1814472bd`
- `GDI32!SetBkColor` at `0x1814472a0`
- `GDI32!SetBkColor` at `0x1814472d3`
- `GDI32!SetBkColor` at `0x1814472a0`
- `GDI32!SetBkColor` at `0x1814472d3`
- `GDI32!SelectObject` at `0x1814471d7`
- `GDI32!SelectObject` at `0x18144745a`
- `GDI32!SelectObject` at `0x1814471d7`
- `GDI32!SelectObject` at `0x18144745a`
- `GDI32!DeleteObject` at `0x1814471cb`
- `GDI32!DeleteObject` at `0x181447472`
- `GDI32!DeleteObject` at `0x18144748d`
- `GDI32!DeleteObject` at `0x18144749b`
- `GDI32!DeleteObject` at `0x1814474a9`
- `GDI32!DeleteObject` at `0x1814471cb`
- `GDI32!DeleteObject` at `0x181447472`
- `GDI32!DeleteObject` at `0x18144748d`
- `GDI32!DeleteObject` at `0x18144749b`
- `GDI32!DeleteObject` at `0x1814474a9`
- `GDI32!CreateSolidBrush` at `0x181447035`
- `GDI32!CreateSolidBrush` at `0x18144704b`
- `GDI32!CreateSolidBrush` at `0x1814470c2`
- `GDI32!CreateSolidBrush` at `0x181447035`
- `GDI32!CreateSolidBrush` at `0x18144704b`
- `GDI32!CreateSolidBrush` at `0x1814470c2`
- `GDI32!CreateRectRgnIndirect` at `0x1814471aa`
- `GDI32!CreateRectRgnIndirect` at `0x1814471aa`
- `GDI32!SelectClipRgn` at `0x1814471c2`
- `GDI32!SelectClipRgn` at `0x1814471c2`

## pseudocode

```c
void __fastcall DSMAP::DrawItem(DSMAP *this, struct tagDRAWITEMSTRUCT *a2)
{
  UINT itemID; // r12d
  HDC hDC; // r14
  DWORD SysColor; // esi
  DWORD v6; // edi
  DWORD v7; // ebx
  int v8; // eax
  HWND hwndItem; // rcx
  COLORREF v10; // eax
  COLORREF v11; // eax
  HBRUSH v12; // r13
  HBRUSH SolidBrush; // r12
  HPEN Pen; // rax
  HBRUSH v15; // rbx
  HPEN v16; // rsi
  bool v17; // di
  HWND Focus; // rax
  HWND v19; // rcx
  HRGN RectRgnIndirect; // rax
  HRGN v21; // rbx
  HWND v22; // rcx
  int v23; // ebx
  __int64 v24; // rsi
  COLORREF v25; // eax
  COLORREF v26; // eax
  HBRUSH v27; // r8
  COLORREF v28; // eax
  COLORREF v29; // eax
  bool v30; // r9
  int v31; // edx
  char v32; // [rsp+38h] [rbp-D0h]
  int v33; // [rsp+3Ch] [rbp-CCh]
  int v34; // [rsp+40h] [rbp-C8h]
  HBRUSH ho; // [rsp+48h] [rbp-C0h]
  HBRUSH hbr; // [rsp+50h] [rbp-B8h]
  int nSavedDC; // [rsp+58h] [rbp-B0h]
  HPEN v38; // [rsp+60h] [rbp-A8h]
  HGDIOBJ v39; // [rsp+68h] [rbp-A0h]
  _OWORD v40[3]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-68h]
  _DWORD lParam[3]; // [rsp+A8h] [rbp-60h] BYREF
  int v43; // [rsp+B4h] [rbp-54h]
  int v44; // [rsp+B8h] [rbp-50h]
  RECT rc; // [rsp+108h] [rbp+0h] BYREF
  struct tagRECT v46; // [rsp+118h] [rbp+10h] BYREF
  LPARAM v47[2]; // [rsp+128h] [rbp+20h] BYREF
  WCHAR chText[256]; // [rsp+138h] [rbp+30h] BYREF

  itemID = a2->itemID;
  hDC = a2->hDC;
  *(_QWORD *)&v46.left = this;
  v33 = itemID;
  memset_0(lParam, 0, 0x58u);
  SysColor = GetSysColor(13);
  v6 = GetSysColor(15);
  v7 = GetSysColor(5);
  v8 = SaveDC(hDC);
  hwndItem = a2->hwndItem;
  nSavedDC = v8;
  lParam[0] = 8;
  lParam[1] = itemID;
  lParam[2] = 0;
  v44 = 0xFFFF;
  SendMessageW(hwndItem, 0x104Bu, 0, (LPARAM)lParam);
  v10 = GetSysColor(13);
  ho = CreateSolidBrush(v10);
  v11 = GetSysColor(5);
  hbr = CreateSolidBrush(v11);
  v12 = hbr;
  SolidBrush = CreateSolidBrush(
                 (unsigned __int8)(((unsigned __int8)v6 + 5 * (unsigned int)(unsigned __int8)v7) / 6)
               | ((unsigned __int8)((BYTE2(v6) + 5 * (unsigned int)BYTE2(v7)) / 6) << 16)
               | ((unsigned __int8)((BYTE1(v6) + 5 * BYTE1(v7)) / 6u) << 8));
  Pen = CreatePen(
          0,
          1,
          (((unsigned int)(unsigned __int8)SysColor + 765) >> 2)
        | ((BYTE2(SysColor) + 765) << 14) & 0xFFFF0000
        | ((unsigned int)(BYTE1(SysColor) + 765) >> 2 << 8));
  v15 = ho;
  v16 = Pen;
  v38 = Pen;
  if ( ho && hbr )
  {
    if ( !Pen )
      goto LABEL_47;
    if ( SolidBrush )
    {
      v17 = (v43 & 8) != 0 || (v43 & 2) != 0;
      if ( (v43 & 1) != 0 && (Focus = GetFocus(), v19 = a2->hwndItem, Focus == v19) )
      {
        v32 = 1;
      }
      else
      {
        v19 = a2->hwndItem;
        v32 = 0;
      }
      *(_OWORD *)v47 = 0;
      SendMessageW(v19, 0x100Eu, v33, (LPARAM)v47);
      rc = *(RECT *)v47;
      RectRgnIndirect = CreateRectRgnIndirect((const RECT *)v47);
      v21 = RectRgnIndirect;
      if ( RectRgnIndirect )
      {
        SelectClipRgn(hDC, RectRgnIndirect);
        DeleteObject(v21);
        v39 = SelectObject(hDC, v16);
        v41 = 0;
        rc.right = rc.left;
        v22 = a2->hwndItem;
        memset(v40, 0, sizeof(v40));
        LODWORD(v40[0]) = 3;
        if ( v22 != *(HWND *)(*(_QWORD *)&v46.left + 576LL)
          || v33 < 0
          || v33 >= ***(_DWORD ***)&v46.left
          || (v34 = 1, *(_DWORD *)(*(_QWORD *)(**(_QWORD **)&v46.left + 24LL) + 4LL * v33) == -1) )
        {
          v34 = 0;
        }
        v23 = 0;
        if ( (unsigned int)SendMessageW(v22, 0x105Fu, 0, (LPARAM)v40) )
        {
          v24 = *(_QWORD *)&v46.left;
          while ( 1 )
          {
            rc.left = rc.right;
            rc.right += DWORD2(v40[0]);
            if ( v17 )
            {
              v25 = GetSysColor(14);
              SetTextColor(hDC, v25);
              v26 = GetSysColor(13);
              SetBkColor(hDC, v26);
              v27 = ho;
            }
            else
            {
              v28 = GetSysColor(8);
              SetTextColor(hDC, v28);
              v29 = GetSysColor(5);
              SetBkColor(hDC, v29);
              v27 = SolidBrush;
              if ( !v34 )
                v27 = hbr;
            }
            FillRect(hDC, &rc, v27);
            MoveToEx(hDC, rc.left, rc.bottom - 1, 0);
            LineTo(hDC, rc.right - 1, rc.bottom - 1);
            LineTo(hDC, rc.right - 1, rc.top - 1);
            ListView_GetItemTextW(a2->hwndItem, v33, v23, chText, 255);
            if ( v23 == 1 )
            {
              if ( a2->hwndItem != *(HWND *)(v24 + 576) || (unsigned int)MsoSgnWzCompare(chText, L"__Mapped", 4) )
                goto LABEL_34;
              v30 = 0;
            }
            else
            {
              if ( v23 != 2
                || a2->hwndItem != *(HWND *)(v24 + 576)
                || (unsigned int)MsoSgnWzCompare(chText, L"__Added", 4) )
              {
LABEL_34:
                if ( (BYTE4(v40[0]) & 3) == 1 )
                  v31 = 2;
                else
                  v31 = (BYTE4(v40[0]) & 3) == 2;
                v46 = rc;
                v46.right = rc.right - 4;
                v46.left = _mm_cvtsi128_si32((__m128i)rc) + 4;
                DrawTextW(hDC, chText, -1, &v46, v31 | 0x8824);
                goto LABEL_38;
              }
              v30 = 1;
            }
            DSMAP::DrawMappedIcon(hDC, &rc, v17, v30);
LABEL_38:
            if ( !(unsigned int)SendMessageW(a2->hwndItem, 0x105Fu, ++v23, (LPARAM)v40) )
            {
              v16 = v38;
              break;
            }
          }
        }
        if ( v32 )
          DrawFocusRect(hDC, (const RECT *)v47);
        if ( v39 )
          SelectObject(hDC, v39);
      }
      v12 = hbr;
      v15 = ho;
    }
  }
  if ( v16 )
    DeleteObject(v16);
LABEL_47:
  RestoreDC(hDC, nSavedDC);
  if ( v12 )
    DeleteObject(v12);
  if ( SolidBrush )
    DeleteObject(SolidBrush);
  if ( v15 )
    DeleteObject(v15);
}

```

## disassembly

```asm
0x181446f68  mov     rax, rsp
0x181446f6b  mov     [rax+8], rbx
0x181446f6f  mov     [rax+18h], rsi
0x181446f73  mov     [rax+20h], rdi
0x181446f77  push    rbp
0x181446f78  push    r12
0x181446f7a  push    r13
0x181446f7c  push    r14
0x181446f7e  push    r15
0x181446f80  lea     rbp, [rax-268h]
0x181446f87  sub     rsp, 340h
0x181446f8e  mov     rax, cs:__security_cookie
0x181446f95  xor     rax, rsp
0x181446f98  mov     [rbp+260h+var_30], rax
0x181446f9f  mov     r12d, [rdx+8]
0x181446fa3  mov     r15, rdx
0x181446fa6  mov     r14, [rdx+20h]
0x181446faa  xor     edx, edx; Val
0x181446fac  mov     qword ptr [rbp+260h+var_250.left], rcx
0x181446fb0  lea     rcx, [rbp+260h+lParam]; void *
0x181446fb4  mov     [rsp+360h+var_32C], r12d
0x181446fb9  lea     r8d, [rdx+58h]; Size
0x181446fbd  call    memset_0
0x181446fc2  mov     ecx, 0Dh; nIndex
0x181446fc7  call    cs:__imp_GetSysColor
0x181446fcd  mov     ecx, 0Fh; nIndex
0x181446fd2  mov     esi, eax
0x181446fd4  call    cs:__imp_GetSysColor
0x181446fda  mov     r13d, 5
0x181446fe0  mov     edi, eax
0x181446fe2  mov     ecx, r13d; nIndex
0x181446fe5  call    cs:__imp_GetSysColor
0x181446feb  mov     rcx, r14; hdc
0x181446fee  mov     ebx, eax
0x181446ff0  call    cs:__imp_SaveDC
0x181446ff6  mov     rcx, [r15+18h]; hWnd
0x181446ffa  lea     r9, [rbp+260h+lParam]; lParam
0x181446ffe  xor     r8d, r8d; wParam
0x181447001  mov     [rsp+360h+nSavedDC], eax
0x181447005  mov     edx, 104Bh; Msg
0x18144700a  mov     dword ptr [rbp+260h+lParam], 8
0x181447011  mov     dword ptr [rbp+260h+lParam+4], r12d
0x181447015  mov     [rbp+260h+var_2B8], 0
0x18144701c  mov     [rbp+260h+var_2B0], 0FFFFh
0x181447023  call    cs:__imp_SendMessageW
0x181447029  lea     ecx, [r13+8]; nIndex
0x18144702d  call    cs:__imp_GetSysColor
0x181447033  mov     ecx, eax; color
0x181447035  call    cs:__imp_CreateSolidBrush
0x18144703b  mov     ecx, r13d; nIndex
0x18144703e  mov     [rsp+360h+ho], rax
0x181447043  call    cs:__imp_GetSysColor
0x181447049  mov     ecx, eax; color
0x18144704b  call    cs:__imp_CreateSolidBrush
0x181447051  mov     [rsp+360h+hbr], rax
0x181447056  mov     r10d, 0AAAAAAABh
0x18144705c  mov     r13, rax
0x18144705f  mov     ecx, ebx
0x181447061  shr     ecx, 10h
0x181447064  mov     eax, r10d
0x181447067  movzx   ecx, cl
0x18144706a  lea     edx, [rcx+rcx*4]
0x18144706d  mov     ecx, edi
0x18144706f  shr     ecx, 10h
0x181447072  movzx   ecx, cl
0x181447075  add     edx, ecx
0x181447077  movzx   ecx, di
0x18144707a  mul     edx
0x18144707c  shr     ecx, 8
0x18144707f  shr     edx, 2
0x181447082  movzx   r9d, dl
0x181447086  movzx   eax, bx
0x181447089  shr     eax, 8
0x18144708c  shl     r9d, 10h
0x181447090  lea     edx, [rax+rax*4]
0x181447093  mov     eax, r10d
0x181447096  add     edx, ecx
0x181447098  mul     edx
0x18144709a  mov     eax, r10d
0x18144709d  shr     edx, 2
0x1814470a0  movzx   ecx, dl
0x1814470a3  movzx   edx, bl
0x1814470a6  shl     ecx, 8
0x1814470a9  or      ecx, r9d
0x1814470ac  lea     r8d, [rdx+rdx*4]
0x1814470b0  movzx   edx, dil
0x1814470b4  add     r8d, edx
0x1814470b7  mul     r8d
0x1814470ba  shr     edx, 2
0x1814470bd  movzx   eax, dl
0x1814470c0  or      ecx, eax; color
0x1814470c2  call    cs:__imp_CreateSolidBrush
0x1814470c8  movzx   r8d, si
0x1814470cc  mov     r12, rax
0x1814470cf  shr     r8d, 8
0x1814470d3  mov     r9d, 2FDh
0x1814470d9  movzx   eax, sil
0x1814470dd  add     r8d, r9d
0x1814470e0  mov     ecx, esi
0x1814470e2  shr     r8d, 2
0x1814470e6  add     eax, r9d
0x1814470e9  shr     ecx, 10h
0x1814470ec  movzx   edx, cl
0x1814470ef  xor     ecx, ecx; iStyle
0x1814470f1  add     edx, r9d
0x1814470f4  shl     r8d, 8
0x1814470f8  shl     edx, 0Eh
0x1814470fb  and     edx, 0FFFF0000h
0x181447101  shr     eax, 2
0x181447104  or      r8d, edx
0x181447107  mov     edx, 1; cWidth
0x18144710c  or      r8d, eax; color
0x18144710f  call    cs:__imp_CreatePen
0x181447115  mov     rbx, [rsp+360h+ho]
0x18144711a  mov     rsi, rax
0x18144711d  mov     [rsp+360h+var_308], rax
0x181447122  test    rbx, rbx
0x181447125  jz      loc_18144746A
0x18144712b  test    r13, r13
0x18144712e  jz      loc_18144746A
0x181447134  test    rax, rax
0x181447137  jz      loc_181447478
0x18144713d  test    r12, r12
0x181447140  jz      loc_18144746A
0x181447146  mov     ecx, [rbp+260h+var_2B4]
0x181447149  test    cl, 8
0x18144714c  jnz     short loc_181447158
0x18144714e  test    cl, 2
0x181447151  jnz     short loc_181447158
0x181447153  xor     dil, dil
0x181447156  jmp     short loc_18144715B
0x181447158  mov     dil, 1
0x18144715b  test    cl, 1
0x18144715e  jz      short loc_181447176
0x181447160  call    cs:__imp_GetFocus
0x181447166  mov     rcx, [r15+18h]
0x18144716a  cmp     rax, rcx
0x18144716d  jnz     short loc_181447176
0x18144716f  mov     byte ptr [rsp+360h+var_330], 1
0x181447174  jmp     short loc_18144717F
0x181447176  mov     rcx, [r15+18h]; hWnd
0x18144717a  mov     byte ptr [rsp+360h+var_330], 0
0x18144717f  movsxd  r13, [rsp+360h+var_32C]
0x181447184  lea     r9, [rbp+260h+var_240]; lParam
0x181447188  xorps   xmm0, xmm0
0x18144718b  mov     r8, r13; wParam
0x18144718e  mov     edx, 100Eh; Msg
0x181447193  movups  xmmword ptr [rbp+260h+var_240], xmm0
0x181447197  call    cs:__imp_SendMessageW
0x18144719d  movaps  xmm0, xmmword ptr [rbp+260h+var_240]
0x1814471a1  lea     rcx, [rbp+260h+var_240]; lprect
0x1814471a5  movdqa  xmmword ptr [rbp+260h+rc.left], xmm0
0x1814471aa  call    cs:__imp_CreateRectRgnIndirect
0x1814471b0  mov     rbx, rax
0x1814471b3  test    rax, rax
0x1814471b6  jz      loc_181447460
0x1814471bc  mov     rdx, rax; hrgn
0x1814471bf  mov     rcx, r14; hdc
0x1814471c2  call    cs:__imp_SelectClipRgn
0x1814471c8  mov     rcx, rbx; ho
0x1814471cb  call    cs:__imp_DeleteObject
0x1814471d1  mov     rdx, rsi; h
0x1814471d4  mov     rcx, r14; hdc
0x1814471d7  call    cs:__imp_SelectObject
0x1814471dd  mov     ecx, [rbp+260h+rc.left]
0x1814471e0  xorps   xmm0, xmm0
0x1814471e3  mov     [rsp+360h+var_300], rax
0x1814471e8  xor     eax, eax
0x1814471ea  mov     [rbp+260h+var_2C8], rax
0x1814471ee  mov     rax, qword ptr [rbp+260h+var_250.left]
0x1814471f2  mov     [rbp+260h+rc.right], ecx
0x1814471f5  mov     rcx, [r15+18h]; hWnd
0x1814471f9  movups  xmmword ptr [rsp+360h+var_300+8], xmm0
0x1814471fe  mov     dword ptr [rsp+360h+var_300+8], 3
0x181447206  movups  [rsp+360h+var_2F0+8], xmm0
0x18144720b  movups  [rbp+260h+var_2D8], xmm0
0x18144720f  cmp     rcx, [rax+240h]
0x181447216  jnz     short loc_18144723A
0x181447218  mov     edx, [rsp+360h+var_32C]
0x18144721c  test    edx, edx
0x18144721e  js      short loc_18144723A
0x181447220  mov     rax, [rax]
0x181447223  cmp     edx, [rax]
0x181447225  jge     short loc_18144723A
0x181447227  mov     rax, [rax+18h]
0x18144722b  mov     dword ptr [rsp+360h+var_328], 1
0x181447233  cmp     dword ptr [rax+r13*4], 0FFFFFFFFh
0x181447238  jnz     short loc_181447242
0x18144723a  mov     dword ptr [rsp+360h+var_328], 0
0x181447242  lea     r9, [rsp+360h+var_300+8]; lParam
0x181447247  xor     r8d, r8d; wParam
0x18144724a  mov     edx, 105Fh; Msg
0x18144724f  xor     ebx, ebx
0x181447251  call    cs:__imp_SendMessageW
0x181447257  test    eax, eax
0x181447259  jz      loc_181447436
0x18144725f  mov     r13, [rsp+360h+hbr]
0x181447264  mov     rsi, qword ptr [rbp+260h+var_250.left]
0x181447268  mov     eax, [rbp+260h+rc.right]
0x18144726b  mov     [rbp+260h+rc.left], eax
0x18144726e  add     eax, dword ptr [rsp+360h+var_2F0]
0x181447272  mov     [rbp+260h+rc.right], eax
0x181447275  test    dil, dil
0x181447278  jz      short loc_1814472AD
0x18144727a  mov     ecx, 0Eh; nIndex
0x18144727f  call    cs:__imp_GetSysColor
0x181447285  mov     edx, eax; color
0x181447287  mov     rcx, r14; hdc
0x18144728a  call    cs:__imp_SetTextColor
0x181447290  mov     ecx, 0Dh; nIndex
0x181447295  call    cs:__imp_GetSysColor
0x18144729b  mov     edx, eax; color
0x18144729d  mov     rcx, r14; hdc
0x1814472a0  call    cs:__imp_SetBkColor
0x1814472a6  mov     r8, [rsp+360h+ho]
0x1814472ab  jmp     short loc_1814472E6
0x1814472ad  mov     ecx, 8; nIndex
0x1814472b2  call    cs:__imp_GetSysColor
0x1814472b8  mov     edx, eax; color
0x1814472ba  mov     rcx, r14; hdc
0x1814472bd  call    cs:__imp_SetTextColor
0x1814472c3  mov     ecx, 5; nIndex
0x1814472c8  call    cs:__imp_GetSysColor
0x1814472ce  mov     edx, eax; color
0x1814472d0  mov     rcx, r14; hdc
0x1814472d3  call    cs:__imp_SetBkColor
0x1814472d9  cmp     dword ptr [rsp+360h+var_328], 0
0x1814472de  mov     r8, r12
0x1814472e1  jnz     short loc_1814472E6
0x1814472e3  mov     r8, r13; hbr
0x1814472e6  lea     rdx, [rbp+260h+rc]; lprc
0x1814472ea  mov     rcx, r14; hDC
0x1814472ed  call    cs:__imp_FillRect
0x1814472f3  mov     r8d, [rbp+260h+rc.bottom]
0x1814472f7  xor     r9d, r9d; lppt
0x1814472fa  mov     edx, [rbp+260h+rc.left]; x
0x1814472fd  dec     r8d; y
0x181447300  mov     rcx, r14; hdc
0x181447303  call    cs:__imp_MoveToEx
0x181447309  mov     r8d, [rbp+260h+rc.bottom]
0x18144730d  mov     rcx, r14; hdc
0x181447310  mov     edx, [rbp+260h+rc.right]
0x181447313  dec     r8d; y
0x181447316  dec     edx; x
0x181447318  call    cs:__imp_LineTo
0x18144731e  mov     r8d, [rbp+260h+rc.top]
0x181447322  mov     rcx, r14; hdc
0x181447325  mov     edx, [rbp+260h+rc.right]
0x181447328  dec     r8d; y
0x18144732b  dec     edx; x
0x18144732d  call    cs:__imp_LineTo
0x181447333  mov     edx, [rsp+360h+var_32C]; int
0x181447337  lea     r9, [rbp+260h+chText]; wchar_t *
0x18144733b  mov     rcx, [r15+18h]; hWnd
0x18144733f  mov     r8d, ebx; int
0x181447342  mov     [rsp+360h+format], 0FFh; int
0x18144734a  call    ?ListView_GetItemTextW@@YAHPEAUHWND__@@HHPEA_WH@Z; ListView_GetItemTextW(HWND__ *,int,int,wchar_t *,int)
0x18144734f  cmp     ebx, 1
0x181447352  jnz     short loc_18144737F
0x181447354  mov     rax, [rsi+240h]
0x18144735b  cmp     [r15+18h], rax
0x18144735f  jnz     short loc_1814473BE
0x181447361  lea     r8d, [rbx+3]
0x181447365  lea     rdx, ?s_wszFieldMapped@DSMAP@@0QB_WB; "__Mapped"
0x18144736c  lea     rcx, [rbp+260h+chText]
0x181447370  call    cs:__imp_MsoSgnWzCompare
0x181447376  test    eax, eax
0x181447378  jnz     short loc_1814473BE
0x18144737a  xor     r9d, r9d
0x18144737d  jmp     short loc_1814473AD
0x18144737f  cmp     ebx, 2
0x181447382  jnz     short loc_1814473BE
0x181447384  mov     rax, [rsi+240h]
0x18144738b  cmp     [r15+18h], rax
0x18144738f  jnz     short loc_1814473BE
0x181447391  lea     r8d, [rbx+2]
0x181447395  lea     rdx, ?s_wszFieldAdded@DSMAP@@0QB_WB; "__Added"
0x18144739c  lea     rcx, [rbp+260h+chText]
0x1814473a0  call    cs:__imp_MsoSgnWzCompare
0x1814473a6  test    eax, eax
0x1814473a8  jnz     short loc_1814473BE
0x1814473aa  mov     r9b, 1; bool
0x1814473ad  mov     r8b, dil; bool
0x1814473b0  lea     rdx, [rbp+260h+rc]; struct tagRECT *
0x1814473b4  mov     rcx, r14; hdc
0x1814473b7  call    ?DrawMappedIcon@DSMAP@@KAXPEAUHDC__@@PEBUtagRECT@@_N2@Z; DSMAP::DrawMappedIcon(HDC__ *,tagRECT const *,bool,bool)
0x1814473bc  jmp     short loc_181447410
0x1814473be  mov     ecx, dword ptr [rsp+360h+var_300+0Ch]
0x1814473c2  xor     edx, edx
0x1814473c4  and     ecx, 3
0x1814473c7  sub     ecx, 1
0x1814473ca  jz      short loc_1814473D5
0x1814473cc  cmp     ecx, 1
0x1814473cf  jnz     short loc_1814473DA
0x1814473d1  mov     edx, ecx
0x1814473d3  jmp     short loc_1814473DA
0x1814473d5  mov     edx, 2
0x1814473da  movaps  xmm0, xmmword ptr [rbp+260h+rc.left]
0x1814473de  lea     r9, [rbp+260h+var_250]; lprc
0x1814473e2  or      edx, 8824h
  ... truncated ...
```
