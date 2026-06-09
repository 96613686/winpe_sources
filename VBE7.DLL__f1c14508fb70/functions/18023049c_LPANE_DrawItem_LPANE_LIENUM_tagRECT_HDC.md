# LPANE::DrawItem(LPANE::LIENUM *,tagRECT *,HDC__ *)

- ea: `0x18023049c`
- end: `0x180230c15`
- name: `?DrawItem@LPANE@@MEAAXPEAULIENUM@1@PEAUtagRECT@@PEAUHDC__@@@Z`
- size: `1913`
- prototype: `void __fastcall(LPANE *__hidden this, struct LPANE::LIENUM *, struct tagRECT *, HDC)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180232f88`

## callees

- `0x1800fd1e4`
- `0x18013ec0c`
- `0x180144ac4`
- `0x18022bb70`
- `0x18022fb8c`
- `0x18023049c`
- `0x180231a48`
- `0x180231af8`
- `0x180231cd4`
- `0x180248d64`
- `0x180379520`

## import_xrefs

- `MSVCR100!_mbsncat_s` at `0x180230a09`
- `MSVCR100!_mbsncat_s` at `0x180230a09`
- `USER32!GetSysColor` at `0x1802304fa`
- `USER32!GetSysColor` at `0x180230515`
- `USER32!GetSysColor` at `0x180230526`
- `USER32!GetSysColor` at `0x180230541`
- `USER32!GetSysColor` at `0x180230b30`
- `USER32!GetSysColor` at `0x1802304fa`
- `USER32!GetSysColor` at `0x180230515`
- `USER32!GetSysColor` at `0x180230526`
- `USER32!GetSysColor` at `0x180230541`
- `USER32!GetSysColor` at `0x180230b30`
- `USER32!IntersectRect` at `0x180230830`
- `USER32!IntersectRect` at `0x180230a34`
- `USER32!IntersectRect` at `0x180230b16`
- `USER32!IntersectRect` at `0x180230830`
- `USER32!IntersectRect` at `0x180230a34`
- `USER32!IntersectRect` at `0x180230b16`
- `GDI32!LineTo` at `0x1802306d1`
- `GDI32!LineTo` at `0x1802307c8`
- `GDI32!LineTo` at `0x1802308c4`
- `GDI32!LineTo` at `0x1802306d1`
- `GDI32!LineTo` at `0x1802307c8`
- `GDI32!LineTo` at `0x1802308c4`
- `GDI32!MoveToEx` at `0x1802306b2`
- `GDI32!MoveToEx` at `0x180230793`
- `GDI32!MoveToEx` at `0x1802308a5`
- `GDI32!MoveToEx` at `0x1802306b2`
- `GDI32!MoveToEx` at `0x180230793`
- `GDI32!MoveToEx` at `0x1802308a5`
- `GDI32!SelectObject` at `0x1802305d3`
- `GDI32!SelectObject` at `0x180230be7`
- `GDI32!SelectObject` at `0x1802305d3`
- `GDI32!SelectObject` at `0x180230be7`
- `GDI32!SetTextColor` at `0x180230553`
- `GDI32!SetTextColor` at `0x180230b3c`
- `GDI32!SetTextColor` at `0x180230bb1`
- `GDI32!SetTextColor` at `0x180230bd0`
- `GDI32!SetTextColor` at `0x180230553`
- `GDI32!SetTextColor` at `0x180230b3c`
- `GDI32!SetTextColor` at `0x180230bb1`
- `GDI32!SetTextColor` at `0x180230bd0`
- `GDI32!SetBkColor` at `0x180230506`
- `GDI32!SetBkColor` at `0x180230532`
- `GDI32!SetBkColor` at `0x180230bbf`
- `GDI32!SetBkColor` at `0x180230506`
- `GDI32!SetBkColor` at `0x180230532`
- `GDI32!SetBkColor` at `0x180230bbf`
- `GDI32!DeleteObject` at `0x180230bfa`
- `GDI32!DeleteObject` at `0x180230bfa`
- `GDI32!CreatePen` at `0x1802305ad`
- `GDI32!CreatePen` at `0x1802305ad`

## pseudocode

```c
void __fastcall LPANE::DrawItem(LPANE *this, struct LPANE::LIENUM *a2, struct tagRECT *a3, HDC a4)
{
  COLORREF SysColor; // eax
  COLORREF v5; // eax
  COLORREF v6; // eax
  COLORREF v7; // eax
  int i; // [rsp+30h] [rbp-F0h]
  int v9; // [rsp+34h] [rbp-ECh]
  DWORD color; // [rsp+3Ch] [rbp-E4h]
  signed int v11; // [rsp+40h] [rbp-E0h]
  _BYTE v12[4]; // [rsp+44h] [rbp-DCh] BYREF
  LPANEITEM *v13; // [rsp+48h] [rbp-D8h]
  HGDIOBJ h; // [rsp+50h] [rbp-D0h]
  COLORREF v15; // [rsp+58h] [rbp-C8h]
  _BYTE *j; // [rsp+60h] [rbp-C0h] BYREF
  HGDIOBJ v17; // [rsp+68h] [rbp-B8h]
  unsigned __int8 *Src; // [rsp+70h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+78h] [rbp-A8h]
  __int64 v20; // [rsp+80h] [rbp-A0h]
  COLORREF v21; // [rsp+88h] [rbp-98h]
  __int64 v22; // [rsp+90h] [rbp-90h]
  signed int v23; // [rsp+98h] [rbp-88h]
  int v24; // [rsp+9Ch] [rbp-84h]
  int v25; // [rsp+A0h] [rbp-80h]
  __int64 v26; // [rsp+A8h] [rbp-78h]
  int v27; // [rsp+B0h] [rbp-70h]
  int v28; // [rsp+B4h] [rbp-6Ch]
  HBITMAP v29; // [rsp+B8h] [rbp-68h]
  __int64 v30; // [rsp+C0h] [rbp-60h]
  __int64 v31; // [rsp+C8h] [rbp-58h]
  __int64 v32; // [rsp+D0h] [rbp-50h]
  __int64 v33; // [rsp+D8h] [rbp-48h]
  __int64 v34; // [rsp+E0h] [rbp-40h]
  int y[4]; // [rsp+E8h] [rbp-38h] BYREF
  struct tagRECT v36; // [rsp+F8h] [rbp-28h] BYREF
  struct tagRECT rcDst; // [rsp+108h] [rbp-18h] BYREF

  h = 0;
  v17 = 0;
  if ( *((_DWORD *)this + 20) == *((_DWORD *)a2 + 6) && *((_DWORD *)this + 15) )
  {
    SysColor = GetSysColor(13);
    v15 = SetBkColor(a4, SysColor);
    color = GetSysColor(14);
    v5 = SetTextColor(a4, color);
  }
  else
  {
    v6 = GetSysColor(5);
    v15 = SetBkColor(a4, v6);
    color = GetSysColor(8);
    v5 = SetTextColor(a4, color);
  }
  v21 = v5;
  LPANE::GetItemRect(this, *((_DWORD *)a2 + 6), &v36);
  *(struct tagRECT *)y = v36;
  LPANE::DrawListText(this, a4, (char *)&Class, &v36);
  v13 = *(LPANEITEM **)a2;
  h = CreatePen(0, 1, color);
  if ( h )
  {
    v17 = SelectObject(a4, h);
    if ( v17 )
    {
      v13 = *(LPANEITEM **)a2;
      v11 = *((_DWORD *)a2 + 4);
      for ( i = *((_DWORD *)a2 + 5); i; --i )
      {
        LPANE::GetExpandBtnRect(this, *((_DWORD *)a2 + 6), i - 1, (struct tagRECT *)y);
        if ( i == *((_DWORD *)a2 + 5) && v11 == (unsigned int)LPANEITEM::ChildCount(v13) - 1 )
          y[3] = (y[3] + y[1]) / 2;
        if ( i == *((_DWORD *)a2 + 5) || v11 < (int)(LPANEITEM::ChildCount(v13) - 1) )
        {
          MoveToEx(a4, (y[2] + y[0]) / 2, y[1], 0);
          LineTo(a4, (y[2] + y[0]) / 2, y[3]);
        }
        v30 = *((_QWORD *)v13 + 3);
        v23 = *(_DWORD *)(v30 + 16);
        v11 = v23;
        v13 = *(LPANEITEM **)v13;
      }
      LPANE::GetExpandBtnRect(this, *((_DWORD *)a2 + 6), *((_DWORD *)a2 + 5), (struct tagRECT *)y);
      if ( *((_DWORD *)a2 + 5) )
      {
        LPANE::GetExpandBtnRect(this, *((_DWORD *)a2 + 6), *((_DWORD *)a2 + 5) - 1, &rcDst);
        v24 = (y[3] + y[1]) / 2;
        MoveToEx(a4, (rcDst.right + rcDst.left) / 2, v24, 0);
        v28 = (y[3] + y[1]) / 2;
        LineTo(a4, (y[2] + y[0]) / 2, v28);
      }
      v22 = v33;
      v22 = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 56LL))(v22, *((unsigned int *)a2 + 4));
      if ( v9 && v9 != 2 && IntersectRect(&rcDst, (const RECT *)y, a3) )
      {
        if ( v9 == 1 )
        {
          if ( *((_QWORD *)a2 + 1) && (v25 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 36LL)) != 0 )
          {
            v29 = (HBITMAP)g_hbmpLPaneCollapse;
            v27 = (y[3] + y[1]) / 2;
            MoveToEx(a4, (y[2] + y[0]) / 2, v27, 0);
            LineTo(a4, (y[2] + y[0]) / 2, v36.bottom);
          }
          else
          {
            v29 = (HBITMAP)g_hbmpLPaneExpand;
          }
        }
        LPANE::DrawBitmap(this, a4, v29, (struct tagRECT *)y);
      }
      y[0] = y[2];
      y[2] = *((_DWORD *)this + 39) + v36.left;
      v19 = v34;
      v19 = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
      if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v19 + 48LL))(
             v19,
             *((unsigned int *)a2 + 4),
             0,
             *((_QWORD *)this + 4),
             *((_DWORD *)this + 10)) >= 0 )
      {
        v26 = v31;
        v26 = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
        if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, _BYTE *, int))(*(_QWORD *)v26 + 48LL))(
               v26,
               *((unsigned int *)a2 + 4),
               7,
               v12,
               2) >= 0 )
        {
          if ( v12[0] )
          {
            Src = 0;
            BstrAOfParmStrid(57106, &Class, &Src);
            if ( Src )
            {
              _mbsncat_s(
                *((unsigned __int8 **)this + 4),
                *((unsigned int *)this + 10),
                Src,
                (unsigned int)(*((_DWORD *)this + 10) - 1));
              SysFreeStringA(Src);
            }
          }
          if ( **((_BYTE **)this + 4) && IntersectRect(&rcDst, (const RECT *)y, a3) )
            LPANE::DrawListText(this, a4, *((char **)this + 4), (struct tagRECT *)y);
          if ( (unsigned int)EbMode() != 1 )
          {
            y[0] = *((_DWORD *)this + 39) + v36.left;
            y[2] = *((_DWORD *)this + 40) + v36.left;
            v20 = v32;
            v20 = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
            if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD))(*(_QWORD *)v20 + 48LL))(
                   v20,
                   *((unsigned int *)a2 + 4),
                   1,
                   *((_QWORD *)this + 4),
                   *((_DWORD *)this + 10)) >= 0
              && **((_BYTE **)this + 4)
              && IntersectRect(&rcDst, (const RECT *)y, a3) )
            {
              if ( v9 == 1 )
              {
                v7 = GetSysColor(17);
                SetTextColor(a4, v7);
              }
              for ( j = (_BYTE *)*((_QWORD *)this + 4); *j; xincc(&j) )
              {
                if ( *j == 10 || *j == 13 )
                  *j = 32;
              }
              LPANE::DrawListText(this, a4, *((char **)this + 4), (struct tagRECT *)y);
              if ( v9 == 1 )
                SetTextColor(a4, color);
            }
          }
        }
      }
    }
  }
  SetBkColor(a4, v15);
  SetTextColor(a4, v21);
  if ( v17 )
    SelectObject(a4, v17);
  if ( h )
    DeleteObject(h);
}

```

## disassembly

```asm
0x18023049c  mov     [rsp-8+hdc], r9
0x1802304a1  mov     [rsp-8+lprcSrc2], r8
0x1802304a6  mov     [rsp-8+arg_8], rdx
0x1802304ab  mov     [rsp-8+arg_0], rcx
0x1802304b0  push    rbp
0x1802304b1  mov     rbp, rsp
0x1802304b4  sub     rsp, 120h
0x1802304bb  mov     rax, cs:__security_cookie
0x1802304c2  xor     rax, rsp
0x1802304c5  mov     [rbp+var_8], rax
0x1802304c9  mov     [rsp+120h+h], 0
0x1802304d2  mov     [rsp+120h+var_B8], 0
0x1802304db  mov     rax, [rbp+arg_0]
0x1802304df  mov     rcx, [rbp+arg_8]
0x1802304e3  mov     ecx, [rcx+18h]
0x1802304e6  cmp     [rax+50h], ecx
0x1802304e9  jnz     short loc_180230521
0x1802304eb  mov     rax, [rbp+arg_0]
0x1802304ef  cmp     dword ptr [rax+3Ch], 0
0x1802304f3  jz      short loc_180230521
0x1802304f5  mov     ecx, 0Dh; nIndex
0x1802304fa  call    cs:__imp_GetSysColor
0x180230500  mov     edx, eax; color
0x180230502  mov     rcx, [rbp+hdc]; hdc
0x180230506  call    cs:__imp_SetBkColor
0x18023050c  mov     [rsp+120h+var_C8], eax
0x180230510  mov     ecx, 0Eh; nIndex
0x180230515  call    cs:__imp_GetSysColor
0x18023051b  mov     [rsp+120h+color], eax
0x18023051f  jmp     short loc_18023054B
0x180230521  mov     ecx, 5; nIndex
0x180230526  call    cs:__imp_GetSysColor
0x18023052c  mov     edx, eax; color
0x18023052e  mov     rcx, [rbp+hdc]; hdc
0x180230532  call    cs:__imp_SetBkColor
0x180230538  mov     [rsp+120h+var_C8], eax
0x18023053c  mov     ecx, 8; nIndex
0x180230541  call    cs:__imp_GetSysColor
0x180230547  mov     [rsp+120h+color], eax
0x18023054b  mov     edx, [rsp+120h+color]; color
0x18023054f  mov     rcx, [rbp+hdc]; hdc
0x180230553  call    cs:__imp_SetTextColor
0x180230559  mov     [rsp+120h+var_98], eax
0x180230560  lea     r8, [rbp+var_28]; struct tagRECT *
0x180230564  mov     rax, [rbp+arg_8]
0x180230568  mov     edx, [rax+18h]; int
0x18023056b  mov     rcx, [rbp+arg_0]; this
0x18023056f  call    ?GetItemRect@LPANE@@IEAAHJQEAUtagRECT@@@Z; LPANE::GetItemRect(long,tagRECT * const)
0x180230574  movups  xmm0, xmmword ptr [rbp+var_28.left]
0x180230578  movdqu  xmmword ptr [rbp+y], xmm0
0x18023057d  lea     r9, [rbp+var_28]; struct tagRECT *
0x180230581  lea     r8, Class; char *
0x180230588  mov     rdx, [rbp+hdc]; HDC
0x18023058c  mov     rcx, [rbp+arg_0]; this
0x180230590  call    ?DrawListText@LPANE@@IEAAXPEAUHDC__@@PEADPEAUtagRECT@@@Z; LPANE::DrawListText(HDC__ *,char *,tagRECT *)
0x180230595  mov     rax, [rbp+arg_8]
0x180230599  mov     rax, [rax]
0x18023059c  mov     [rsp+120h+var_D8], rax
0x1802305a1  mov     r8d, [rsp+120h+color]; color
0x1802305a6  mov     edx, 1; cWidth
0x1802305ab  xor     ecx, ecx; iStyle
0x1802305ad  call    cs:__imp_CreatePen
0x1802305b3  mov     [rsp+120h+h], rax
0x1802305b8  cmp     [rsp+120h+h], 0
0x1802305be  jnz     short loc_1802305CA
0x1802305c0  jmp     loc_180230BB7
0x1802305c5  jmp     loc_180230BB7
0x1802305ca  mov     rdx, [rsp+120h+h]; h
0x1802305cf  mov     rcx, [rbp+hdc]; hdc
0x1802305d3  call    cs:__imp_SelectObject
0x1802305d9  mov     [rsp+120h+var_B8], rax
0x1802305de  cmp     [rsp+120h+var_B8], 0
0x1802305e4  jnz     short loc_1802305F0
0x1802305e6  jmp     loc_180230BB7
0x1802305eb  jmp     loc_180230BB7
0x1802305f0  mov     rax, [rbp+arg_8]
0x1802305f4  mov     rax, [rax]
0x1802305f7  mov     [rsp+120h+var_D8], rax
0x1802305fc  mov     rax, [rbp+arg_8]
0x180230600  mov     eax, [rax+10h]
0x180230603  mov     [rsp+120h+var_E0], eax
0x180230607  mov     rax, [rbp+arg_8]
0x18023060b  mov     eax, [rax+14h]
0x18023060e  mov     [rsp+120h+var_F0], eax
0x180230612  jmp     short loc_18023061E
0x180230614  mov     eax, [rsp+120h+var_F0]
0x180230618  dec     eax
0x18023061a  mov     [rsp+120h+var_F0], eax
0x18023061e  cmp     [rsp+120h+var_F0], 0
0x180230623  jbe     loc_18023070F
0x180230629  mov     eax, [rsp+120h+var_F0]
0x18023062d  dec     eax
0x18023062f  lea     r9, [rbp+y]; struct tagRECT *
0x180230633  mov     r8d, eax; unsigned int
0x180230636  mov     rax, [rbp+arg_8]
0x18023063a  mov     edx, [rax+18h]; int
0x18023063d  mov     rcx, [rbp+arg_0]; this
0x180230641  call    ?GetExpandBtnRect@LPANE@@QEAAXJIPEAUtagRECT@@@Z; LPANE::GetExpandBtnRect(long,uint,tagRECT *)
0x180230646  mov     rax, [rbp+arg_8]
0x18023064a  mov     eax, [rax+14h]
0x18023064d  cmp     [rsp+120h+var_F0], eax
0x180230651  jnz     short loc_180230677
0x180230653  mov     rcx, [rsp+120h+var_D8]; this
0x180230658  call    ?ChildCount@LPANEITEM@@QEAAJXZ; LPANEITEM::ChildCount(void)
0x18023065d  dec     eax
0x18023065f  cmp     [rsp+120h+var_E0], eax
0x180230663  jnz     short loc_180230677
0x180230665  mov     eax, [rbp+y+0Ch]
0x180230668  mov     ecx, [rbp+y+4]
0x18023066b  add     ecx, eax
0x18023066d  mov     eax, ecx
0x18023066f  cdq
0x180230670  sub     eax, edx
0x180230672  sar     eax, 1
0x180230674  mov     [rbp+y+0Ch], eax
0x180230677  mov     rax, [rbp+arg_8]
0x18023067b  mov     eax, [rax+14h]
0x18023067e  cmp     [rsp+120h+var_F0], eax
0x180230682  jz      short loc_180230696
0x180230684  mov     rcx, [rsp+120h+var_D8]; this
0x180230689  call    ?ChildCount@LPANEITEM@@QEAAJXZ; LPANEITEM::ChildCount(void)
0x18023068e  dec     eax
0x180230690  cmp     [rsp+120h+var_E0], eax
0x180230694  jge     short loc_1802306D7
0x180230696  mov     eax, [rbp+y+8]
0x180230699  mov     ecx, [rbp+y]
0x18023069c  add     ecx, eax
0x18023069e  mov     eax, ecx
0x1802306a0  cdq
0x1802306a1  sub     eax, edx
0x1802306a3  sar     eax, 1
0x1802306a5  xor     r9d, r9d; lppt
0x1802306a8  mov     r8d, [rbp+y+4]; y
0x1802306ac  mov     edx, eax; x
0x1802306ae  mov     rcx, [rbp+hdc]; hdc
0x1802306b2  call    cs:__imp_MoveToEx
0x1802306b8  mov     eax, [rbp+y+8]
0x1802306bb  mov     ecx, [rbp+y]
0x1802306be  add     ecx, eax
0x1802306c0  mov     eax, ecx
0x1802306c2  cdq
0x1802306c3  sub     eax, edx
0x1802306c5  sar     eax, 1
0x1802306c7  mov     r8d, [rbp+y+0Ch]; y
0x1802306cb  mov     edx, eax; x
0x1802306cd  mov     rcx, [rbp+hdc]; hdc
0x1802306d1  call    cs:__imp_LineTo
0x1802306d7  mov     rax, [rsp+120h+var_D8]
0x1802306dc  mov     rax, [rax+18h]
0x1802306e0  mov     [rbp+var_60], rax
0x1802306e4  mov     rax, [rbp+var_60]
0x1802306e8  mov     eax, [rax+10h]
0x1802306eb  mov     [rsp+120h+var_88], eax
0x1802306f2  mov     eax, [rsp+120h+var_88]
0x1802306f9  mov     [rsp+120h+var_E0], eax
0x1802306fd  mov     rax, [rsp+120h+var_D8]
0x180230702  mov     rax, [rax]
0x180230705  mov     [rsp+120h+var_D8], rax
0x18023070a  jmp     loc_180230614
0x18023070f  lea     r9, [rbp+y]; struct tagRECT *
0x180230713  mov     rax, [rbp+arg_8]
0x180230717  mov     r8d, [rax+14h]; unsigned int
0x18023071b  mov     rax, [rbp+arg_8]
0x18023071f  mov     edx, [rax+18h]; int
0x180230722  mov     rcx, [rbp+arg_0]; this
0x180230726  call    ?GetExpandBtnRect@LPANE@@QEAAXJIPEAUtagRECT@@@Z; LPANE::GetExpandBtnRect(long,uint,tagRECT *)
0x18023072b  mov     rax, [rbp+arg_8]
0x18023072f  cmp     dword ptr [rax+14h], 0
0x180230733  jbe     loc_1802307CE
0x180230739  mov     rax, [rbp+arg_8]
0x18023073d  mov     eax, [rax+14h]
0x180230740  dec     eax
0x180230742  lea     r9, [rbp+rcDst]; struct tagRECT *
0x180230746  mov     r8d, eax; unsigned int
0x180230749  mov     rax, [rbp+arg_8]
0x18023074d  mov     edx, [rax+18h]; int
0x180230750  mov     rcx, [rbp+arg_0]; this
0x180230754  call    ?GetExpandBtnRect@LPANE@@QEAAXJIPEAUtagRECT@@@Z; LPANE::GetExpandBtnRect(long,uint,tagRECT *)
0x180230759  mov     eax, [rbp+y+0Ch]
0x18023075c  mov     ecx, [rbp+y+4]
0x18023075f  add     ecx, eax
0x180230761  mov     eax, ecx
0x180230763  cdq
0x180230764  sub     eax, edx
0x180230766  sar     eax, 1
0x180230768  mov     [rsp+120h+var_84], eax
0x18023076f  mov     ecx, [rbp+rcDst.right]
0x180230772  mov     edx, [rbp+rcDst.left]
0x180230775  add     edx, ecx
0x180230777  mov     ecx, edx
0x180230779  mov     eax, ecx
0x18023077b  cdq
0x18023077c  sub     eax, edx
0x18023077e  sar     eax, 1
0x180230780  xor     r9d, r9d; lppt
0x180230783  mov     ecx, [rsp+120h+var_84]
0x18023078a  mov     r8d, ecx; y
0x18023078d  mov     edx, eax; x
0x18023078f  mov     rcx, [rbp+hdc]; hdc
0x180230793  call    cs:__imp_MoveToEx
0x180230799  mov     eax, [rbp+y+0Ch]
0x18023079c  mov     ecx, [rbp+y+4]
0x18023079f  add     ecx, eax
0x1802307a1  mov     eax, ecx
0x1802307a3  cdq
0x1802307a4  sub     eax, edx
0x1802307a6  sar     eax, 1
0x1802307a8  mov     [rbp+var_6C], eax
0x1802307ab  mov     ecx, [rbp+y+8]
0x1802307ae  mov     edx, [rbp+y]
0x1802307b1  add     edx, ecx
0x1802307b3  mov     ecx, edx
0x1802307b5  mov     eax, ecx
0x1802307b7  cdq
0x1802307b8  sub     eax, edx
0x1802307ba  sar     eax, 1
0x1802307bc  mov     ecx, [rbp+var_6C]
0x1802307bf  mov     r8d, ecx; y
0x1802307c2  mov     edx, eax; x
0x1802307c4  mov     rcx, [rbp+hdc]; hdc
0x1802307c8  call    cs:__imp_LineTo
0x1802307ce  mov     rax, [rbp+var_48]
0x1802307d2  mov     [rsp+120h+var_90], rax
0x1802307da  mov     rax, [rbp+arg_8]
0x1802307de  mov     rax, [rax]
0x1802307e1  mov     rax, [rax+18h]
0x1802307e5  mov     [rsp+120h+var_90], rax
0x1802307ed  mov     rax, [rsp+120h+var_90]
0x1802307f5  mov     rax, [rax]
0x1802307f8  mov     rcx, [rbp+arg_8]
0x1802307fc  mov     edx, [rcx+10h]
0x1802307ff  mov     rcx, [rsp+120h+var_90]
0x180230807  call    qword ptr [rax+38h]
0x18023080a  mov     [rsp+120h+var_EC], eax
0x18023080e  cmp     [rsp+120h+var_EC], 0
0x180230813  jz      loc_1802308EC
0x180230819  cmp     [rsp+120h+var_EC], 2
0x18023081e  jz      loc_1802308EC
0x180230824  mov     r8, [rbp+lprcSrc2]; lprcSrc2
0x180230828  lea     rdx, [rbp+y]; lprcSrc1
0x18023082c  lea     rcx, [rbp+rcDst]; lprcDst
0x180230830  call    cs:__imp_IntersectRect
0x180230836  test    eax, eax
0x180230838  jz      loc_1802308EC
0x18023083e  cmp     [rsp+120h+var_EC], 1
0x180230843  jnz     loc_1802308D7
0x180230849  mov     rax, [rbp+arg_8]
0x18023084d  cmp     qword ptr [rax+8], 0
0x180230852  jz      short loc_1802308CC
0x180230854  mov     rax, [rbp+arg_8]
0x180230858  mov     rax, [rax+8]
0x18023085c  mov     eax, [rax+24h]
0x18023085f  mov     [rbp+var_80], eax
0x180230862  cmp     [rbp+var_80], 0
0x180230866  jz      short loc_1802308CC
0x180230868  mov     rax, cs:?g_hbmpLPaneCollapse@@3PEAUHBITMAP__@@EA; HBITMAP__ * g_hbmpLPaneCollapse
0x18023086f  mov     [rbp+var_68], rax
0x180230873  mov     eax, [rbp+y+0Ch]
0x180230876  mov     ecx, [rbp+y+4]
0x180230879  add     ecx, eax
0x18023087b  mov     eax, ecx
0x18023087d  cdq
0x18023087e  sub     eax, edx
0x180230880  sar     eax, 1
0x180230882  mov     [rbp+var_70], eax
0x180230885  mov     ecx, [rbp+y+8]
0x180230888  mov     edx, [rbp+y]
0x18023088b  add     edx, ecx
0x18023088d  mov     ecx, edx
0x18023088f  mov     eax, ecx
0x180230891  cdq
0x180230892  sub     eax, edx
0x180230894  sar     eax, 1
0x180230896  xor     r9d, r9d; lppt
0x180230899  mov     ecx, [rbp+var_70]
0x18023089c  mov     r8d, ecx; y
0x18023089f  mov     edx, eax; x
0x1802308a1  mov     rcx, [rbp+hdc]; hdc
0x1802308a5  call    cs:__imp_MoveToEx
0x1802308ab  mov     eax, [rbp+y+8]
0x1802308ae  mov     ecx, [rbp+y]
0x1802308b1  add     ecx, eax
0x1802308b3  mov     eax, ecx
0x1802308b5  cdq
0x1802308b6  sub     eax, edx
0x1802308b8  sar     eax, 1
0x1802308ba  mov     r8d, [rbp+var_28.bottom]; y
0x1802308be  mov     edx, eax; x
0x1802308c0  mov     rcx, [rbp+hdc]; hdc
0x1802308c4  call    cs:__imp_LineTo
0x1802308ca  jmp     short loc_1802308D7
0x1802308cc  mov     rax, cs:?g_hbmpLPaneExpand@@3PEAUHBITMAP__@@EA; HBITMAP__ * g_hbmpLPaneExpand
0x1802308d3  mov     [rbp+var_68], rax
0x1802308d7  lea     r9, [rbp+y]; struct tagRECT *
0x1802308db  mov     r8, [rbp+var_68]; HBITMAP
0x1802308df  mov     rdx, [rbp+hdc]; HDC
0x1802308e3  mov     rcx, [rbp+arg_0]; this
0x1802308e7  call    ?DrawBitmap@LPANE@@IEAAXPEAUHDC__@@PEAUHBITMAP__@@PEAUtagRECT@@@Z; LPANE::DrawBitmap(HDC__ *,HBITMAP__ *,tagRECT *)
0x1802308ec  mov     eax, [rbp+y+8]
0x1802308ef  mov     [rbp+y], eax
  ... truncated ...
```
