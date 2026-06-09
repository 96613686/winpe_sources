# CPANE::PaintIMEComposition(HDC__ *,uint,uint)

- ea: `0x180246e54`
- end: `0x18024742f`
- name: `?PaintIMEComposition@CPANE@@QEAAXPEAUHDC__@@II@Z`
- size: `1499`
- prototype: `void __fastcall(CPANE *__hidden this, HDC, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18013d728`

## callees

- `0x180246e54`
- `0x180247a24`
- `0x180379520`

## import_xrefs

- `USER32!SetRect` at `0x18024706c`
- `USER32!SetRect` at `0x18024706c`
- `GDI32!LineTo` at `0x1802473a8`
- `GDI32!LineTo` at `0x1802473a8`
- `GDI32!MoveToEx` at `0x180247224`
- `GDI32!MoveToEx` at `0x180247288`
- `GDI32!MoveToEx` at `0x180247358`
- `GDI32!MoveToEx` at `0x1802473be`
- `GDI32!MoveToEx` at `0x180247224`
- `GDI32!MoveToEx` at `0x180247288`
- `GDI32!MoveToEx` at `0x180247358`
- `GDI32!MoveToEx` at `0x1802473be`
- `GDI32!GetCurrentPositionEx` at `0x180246fef`
- `GDI32!GetCurrentPositionEx` at `0x180247190`
- `GDI32!GetCurrentPositionEx` at `0x18024720a`
- `GDI32!GetCurrentPositionEx` at `0x180247319`
- `GDI32!GetCurrentPositionEx` at `0x180246fef`
- `GDI32!GetCurrentPositionEx` at `0x180247190`
- `GDI32!GetCurrentPositionEx` at `0x18024720a`
- `GDI32!GetCurrentPositionEx` at `0x180247319`
- `GDI32!ExtTextOutA` at `0x1802471de`
- `GDI32!ExtTextOutA` at `0x180247272`
- `GDI32!ExtTextOutA` at `0x1802471de`
- `GDI32!ExtTextOutA` at `0x180247272`
- `GDI32!SetBkMode` at `0x1802471fb`
- `GDI32!SetBkMode` at `0x180247297`
- `GDI32!SetBkMode` at `0x180247328`
- `GDI32!SetBkMode` at `0x1802473cb`
- `GDI32!SetBkMode` at `0x1802471fb`
- `GDI32!SetBkMode` at `0x180247297`
- `GDI32!SetBkMode` at `0x180247328`
- `GDI32!SetBkMode` at `0x1802473cb`
- `GDI32!SelectObject` at `0x180247306`
- `GDI32!SelectObject` at `0x1802473d9`
- `GDI32!SelectObject` at `0x180247306`
- `GDI32!SelectObject` at `0x1802473d9`
- `GDI32!SetTextColor` at `0x180247123`
- `GDI32!SetTextColor` at `0x180247123`
- `GDI32!SetBkColor` at `0x180247181`
- `GDI32!SetBkColor` at `0x180247181`
- `GDI32!DeleteObject` at `0x1802473e3`
- `GDI32!DeleteObject` at `0x1802473e3`
- `GDI32!CreatePen` at `0x1802472e9`
- `GDI32!CreatePen` at `0x1802472e9`

## pseudocode

```c
void __fastcall CPANE::PaintIMEComposition(CPANE *this, HDC a2, unsigned int a3, int a4)
{
  struct tagPOINT pt; // [rsp+40h] [rbp-90h] BYREF
  __int64 *v5; // [rsp+48h] [rbp-88h]
  int v6; // [rsp+50h] [rbp-80h]
  int CompositionString; // [rsp+54h] [rbp-7Ch]
  int v8; // [rsp+58h] [rbp-78h]
  COLORREF color; // [rsp+5Ch] [rbp-74h]
  char v10; // [rsp+60h] [rbp-70h]
  struct tagPOINT v11; // [rsp+68h] [rbp-68h] BYREF
  __int64 Context; // [rsp+70h] [rbp-60h]
  int x; // [rsp+78h] [rbp-58h]
  int iStyle; // [rsp+7Ch] [rbp-54h]
  COLORREF v15; // [rsp+80h] [rbp-50h]
  COLORREF v16; // [rsp+84h] [rbp-4Ch]
  int mode; // [rsp+88h] [rbp-48h]
  HGDIOBJ h; // [rsp+90h] [rbp-40h]
  HGDIOBJ v19; // [rsp+98h] [rbp-38h]
  _DWORD v20[4]; // [rsp+A0h] [rbp-30h] BYREF
  struct tagRECT rc; // [rsp+B0h] [rbp-20h] BYREF
  unsigned int v26; // [rsp+F8h] [rbp+28h]

  Context = 0;
  Context = pImmGetContext(*((_QWORD *)this + 35));
  if ( !Context )
    goto LABEL_49;
  if ( (g_SystemLangId & 0x3FF) == 0x11 )
  {
    CompositionString = pImmGetCompositionString(Context, 16, qword_180400AA8, (unsigned int)dword_180400AB0);
    if ( CompositionString <= 0 )
      goto LABEL_49;
  }
  else
  {
    CompositionString = 2;
    *(_BYTE *)qword_180400AA8 = 1;
    *(_BYTE *)(qword_180400AA8 + 1) = 1;
  }
  v8 = CompositionString - (a4 - a3);
  v6 = v8 + 1;
  v26 = a3 + 1;
  while ( v8 < CompositionString )
  {
    while ( *(unsigned __int8 *)(qword_180400AA8 + v8) == *(unsigned __int8 *)(qword_180400AA8 + v6)
         && v6 < CompositionString )
    {
      ++v6;
      ++v26;
    }
    v10 = *(_BYTE *)(qword_180400AA8 + v8);
    if ( v10 )
    {
      switch ( v10 )
      {
        case 1:
          v5 = &qword_1803F5678;
          GetCurrentPositionEx(a2, &pt);
          v20[0] = 0;
          v20[1] = 128;
          v20[2] = pt.x;
          v20[3] = *(_DWORD *)(*((_QWORD *)this + 33) + 260LL) + pt.y;
          SetRect(
            &rc,
            pt.x,
            pt.y,
            *(_DWORD *)(*((_QWORD *)this + 33) + 256LL) + pt.x,
            *(_DWORD *)(*((_QWORD *)this + 33) + 260LL) + pt.y);
          pImmSetCandidateWindow(Context, v20);
          SetIMEFont(*((_QWORD *)this + 35), *(_QWORD *)(*((_QWORD *)this + 33) + 176LL));
          break;
        case 2:
          v5 = &qword_1803F56A0;
          break;
        case 3:
          v5 = &qword_1803F56C8;
          break;
        default:
          goto LABEL_49;
      }
    }
    else
    {
      v5 = &qword_1803F5650;
    }
    if ( *((_DWORD *)v5 + 3) )
    {
      if ( *((_DWORD *)v5 + 4) )
        v16 = g_clrrefWindowText;
      else
        v16 = g_clrrefWindowBack;
      color = v16;
    }
    else
    {
      color = *((_DWORD *)v5 + 5);
    }
    if ( (g_SystemLangId & 0x3FF) != 0x12 )
      SetTextColor(a2, color);
    if ( *((_DWORD *)v5 + 6) )
    {
      if ( *((_DWORD *)v5 + 7) )
        v15 = g_clrrefWindowText;
      else
        v15 = g_clrrefWindowBack;
      color = v15;
    }
    else
    {
      color = *((_DWORD *)v5 + 8);
    }
    if ( (g_SystemLangId & 0x3FF) != 0x12 )
      SetBkColor(a2, color);
    GetCurrentPositionEx(a2, &pt);
    ExtTextOutA(a2, 0, 0, 4u, (const RECT *)((char *)this + 92), (LPCSTR)&dword_18040017C + a3, v26 - a3, 0);
    if ( *(_DWORD *)v5 )
    {
      SetBkMode(a2, 1);
      GetCurrentPositionEx(a2, &v11);
      MoveToEx(a2, pt.x + 1, pt.y, 0);
      ExtTextOutA(a2, 0, 0, 4u, (const RECT *)((char *)this + 92), (LPCSTR)&dword_18040017C + a3, v26 - a3, 0);
      MoveToEx(a2, v11.x, v11.y, 0);
      SetBkMode(a2, 2);
    }
    if ( *((_DWORD *)v5 + 2) != -1 && pt.x < *((_DWORD *)this + 25) )
    {
      iStyle = *((_DWORD *)v5 + 2) == 2003 ? 0 : 2;
      h = CreatePen(iStyle, 1, 0);
      if ( h )
      {
        v19 = SelectObject(a2, h);
        GetCurrentPositionEx(a2, &v11);
        mode = SetBkMode(a2, 1);
        MoveToEx(a2, pt.x, pt.y + *(_DWORD *)(*((_QWORD *)this + 33) + 260LL) - 1, 0);
        if ( v11.x - 1 >= *((_DWORD *)this + 25) )
          x = *((_DWORD *)this + 25);
        else
          x = v11.x - 1;
        LineTo(a2, x, pt.y + *(_DWORD *)(*((_QWORD *)this + 33) + 260LL) - 1);
        MoveToEx(a2, v11.x, v11.y, 0);
        SetBkMode(a2, mode);
        SelectObject(a2, v19);
        DeleteObject(h);
      }
    }
    v8 = v6;
    a3 = v26;
  }
LABEL_49:
  if ( Context )
    pImmReleaseContext(*((_QWORD *)this + 35), Context);
}

```

## disassembly

```asm
0x180246e54  mov     [rsp-8+arg_18], r9d
0x180246e59  mov     [rsp-8+arg_10], r8d
0x180246e5e  mov     [rsp-8+hdc], rdx
0x180246e63  mov     [rsp-8+arg_0], rcx
0x180246e68  push    rbp
0x180246e69  mov     rbp, rsp
0x180246e6c  sub     rsp, 0D0h
0x180246e73  mov     rax, cs:__security_cookie
0x180246e7a  xor     rax, rsp
0x180246e7d  mov     [rbp+var_10], rax
0x180246e81  mov     [rsp+0D0h+var_60], 0
0x180246e8a  mov     rax, [rbp+arg_0]
0x180246e8e  mov     rcx, [rax+118h]
0x180246e95  call    cs:pImmGetContext
0x180246e9b  mov     [rsp+0D0h+var_60], rax
0x180246ea0  cmp     [rsp+0D0h+var_60], 0
0x180246ea6  jnz     short loc_180246EB2
0x180246ea8  jmp     loc_1802473FC
0x180246ead  jmp     loc_1802473FC
0x180246eb2  movzx   eax, cs:g_SystemLangId
0x180246eb9  and     eax, 3FFh
0x180246ebe  cmp     eax, 11h
0x180246ec1  jnz     short loc_180246EF8
0x180246ec3  mov     r9d, cs:dword_180400AB0
0x180246eca  mov     r8, cs:qword_180400AA8
0x180246ed1  mov     edx, 10h
0x180246ed6  mov     rcx, [rsp+0D0h+var_60]
0x180246edb  call    cs:pImmGetCompositionString
0x180246ee1  mov     [rsp+0D0h+var_7C], eax
0x180246ee5  cmp     [rsp+0D0h+var_7C], 0
0x180246eea  jg      short loc_180246EF6
0x180246eec  jmp     loc_1802473FC
0x180246ef1  jmp     loc_1802473FC
0x180246ef6  jmp     short loc_180246F15
0x180246ef8  mov     [rsp+0D0h+var_7C], 2
0x180246f00  mov     rax, cs:qword_180400AA8
0x180246f07  mov     byte ptr [rax], 1
0x180246f0a  mov     rax, cs:qword_180400AA8
0x180246f11  mov     byte ptr [rax+1], 1
0x180246f15  mov     eax, [rbp+arg_10]
0x180246f18  mov     ecx, [rbp+arg_18]
0x180246f1b  sub     ecx, eax
0x180246f1d  mov     eax, ecx
0x180246f1f  mov     ecx, [rsp+0D0h+var_7C]
0x180246f23  sub     ecx, eax
0x180246f25  mov     eax, ecx
0x180246f27  mov     [rsp+0D0h+var_78], eax
0x180246f2b  mov     eax, [rsp+0D0h+var_78]
0x180246f2f  inc     eax
0x180246f31  mov     [rsp+0D0h+var_80], eax
0x180246f35  mov     eax, [rbp+arg_10]
0x180246f38  inc     eax
0x180246f3a  mov     [rbp+arg_18], eax
0x180246f3d  mov     eax, [rsp+0D0h+var_7C]
0x180246f41  cmp     [rsp+0D0h+var_78], eax
0x180246f45  jge     loc_1802473FC
0x180246f4b  movsxd  rax, [rsp+0D0h+var_78]
0x180246f50  mov     rcx, cs:qword_180400AA8
0x180246f57  movzx   eax, byte ptr [rcx+rax]
0x180246f5b  movsxd  rcx, [rsp+0D0h+var_80]
0x180246f60  mov     rdx, cs:qword_180400AA8
0x180246f67  movzx   ecx, byte ptr [rdx+rcx]
0x180246f6b  cmp     eax, ecx
0x180246f6d  jnz     short loc_180246F8D
0x180246f6f  mov     eax, [rsp+0D0h+var_7C]
0x180246f73  cmp     [rsp+0D0h+var_80], eax
0x180246f77  jge     short loc_180246F8D
0x180246f79  mov     eax, [rsp+0D0h+var_80]
0x180246f7d  inc     eax
0x180246f7f  mov     [rsp+0D0h+var_80], eax
0x180246f83  mov     eax, [rbp+arg_18]
0x180246f86  inc     eax
0x180246f88  mov     [rbp+arg_18], eax
0x180246f8b  jmp     short loc_180246F4B
0x180246f8d  movsxd  rax, [rsp+0D0h+var_78]
0x180246f92  mov     rcx, cs:qword_180400AA8
0x180246f99  mov     al, [rcx+rax]
0x180246f9c  mov     [rsp+0D0h+var_70], al
0x180246fa0  cmp     [rsp+0D0h+var_70], 0
0x180246fa5  jz      short loc_180246FC9
0x180246fa7  cmp     [rsp+0D0h+var_70], 1
0x180246fac  jz      short loc_180246FDA
0x180246fae  cmp     [rsp+0D0h+var_70], 2
0x180246fb3  jz      loc_1802470A5
0x180246fb9  cmp     [rsp+0D0h+var_70], 3
0x180246fbe  jz      loc_1802470B3
0x180246fc4  jmp     loc_1802470C1
0x180246fc9  lea     rax, qword_1803F5650
0x180246fd0  mov     [rsp+0D0h+var_88], rax
0x180246fd5  jmp     loc_1802470CB
0x180246fda  lea     rax, qword_1803F5678
0x180246fe1  mov     [rsp+0D0h+var_88], rax
0x180246fe6  lea     rdx, [rsp+0D0h+pt]; lppt
0x180246feb  mov     rcx, [rbp+hdc]; hdc
0x180246fef  call    cs:__imp_GetCurrentPositionEx
0x180246ff5  mov     [rbp+var_30], 0
0x180246ffc  mov     [rbp+var_2C], 80h
0x180247003  mov     eax, [rsp+0D0h+pt.x]
0x180247007  mov     [rbp+var_28], eax
0x18024700a  mov     rax, [rbp+arg_0]
0x18024700e  mov     rax, [rax+108h]
0x180247015  mov     eax, [rax+104h]
0x18024701b  mov     ecx, [rsp+0D0h+pt.y]
0x18024701f  add     ecx, eax
0x180247021  mov     eax, ecx
0x180247023  mov     [rbp+var_24], eax
0x180247026  mov     rax, [rbp+arg_0]
0x18024702a  mov     rax, [rax+108h]
0x180247031  mov     eax, [rax+104h]
0x180247037  mov     ecx, [rsp+0D0h+pt.y]
0x18024703b  add     ecx, eax
0x18024703d  mov     eax, ecx
0x18024703f  mov     rcx, [rbp+arg_0]
0x180247043  mov     rcx, [rcx+108h]
0x18024704a  mov     ecx, [rcx+100h]
0x180247050  mov     edx, [rsp+0D0h+pt.x]
0x180247054  add     edx, ecx
0x180247056  mov     ecx, edx
0x180247058  mov     [rsp+0D0h+yBottom], eax; yBottom
0x18024705c  mov     r9d, ecx; xRight
0x18024705f  mov     r8d, [rsp+0D0h+pt.y]; yTop
0x180247064  mov     edx, [rsp+0D0h+pt.x]; xLeft
0x180247068  lea     rcx, [rbp+rc]; lprc
0x18024706c  call    cs:__imp_SetRect
0x180247072  lea     rdx, [rbp+var_30]
0x180247076  mov     rcx, [rsp+0D0h+var_60]
0x18024707b  call    cs:pImmSetCandidateWindow
0x180247081  mov     rax, [rbp+arg_0]
0x180247085  mov     rax, [rax+108h]
0x18024708c  mov     rdx, [rax+0B0h]
0x180247093  mov     rax, [rbp+arg_0]
0x180247097  mov     rcx, [rax+118h]
0x18024709e  call    SetIMEFont
0x1802470a3  jmp     short loc_1802470CB
0x1802470a5  lea     rax, qword_1803F56A0
0x1802470ac  mov     [rsp+0D0h+var_88], rax
0x1802470b1  jmp     short loc_1802470CB
0x1802470b3  lea     rax, qword_1803F56C8
0x1802470ba  mov     [rsp+0D0h+var_88], rax
0x1802470bf  jmp     short loc_1802470CB
0x1802470c1  jmp     loc_1802473FC
0x1802470c6  jmp     loc_1802473FC
0x1802470cb  mov     rax, [rsp+0D0h+var_88]
0x1802470d0  cmp     dword ptr [rax+0Ch], 0
0x1802470d4  jz      short loc_1802470FE
0x1802470d6  mov     rax, [rsp+0D0h+var_88]
0x1802470db  cmp     dword ptr [rax+10h], 0
0x1802470df  jz      short loc_1802470EC
0x1802470e1  mov     eax, cs:?g_clrrefWindowText@@3KA; ulong g_clrrefWindowText
0x1802470e7  mov     [rbp+var_4C], eax
0x1802470ea  jmp     short loc_1802470F5
0x1802470ec  mov     eax, cs:?g_clrrefWindowBack@@3KA; ulong g_clrrefWindowBack
0x1802470f2  mov     [rbp+var_4C], eax
0x1802470f5  mov     eax, [rbp+var_4C]
0x1802470f8  mov     [rsp+0D0h+color], eax
0x1802470fc  jmp     short loc_18024710A
0x1802470fe  mov     rax, [rsp+0D0h+var_88]
0x180247103  mov     eax, [rax+14h]
0x180247106  mov     [rsp+0D0h+color], eax
0x18024710a  movzx   eax, cs:g_SystemLangId
0x180247111  and     eax, 3FFh
0x180247116  cmp     eax, 12h
0x180247119  jz      short loc_180247129
0x18024711b  mov     edx, [rsp+0D0h+color]; color
0x18024711f  mov     rcx, [rbp+hdc]; hdc
0x180247123  call    cs:__imp_SetTextColor
0x180247129  mov     rax, [rsp+0D0h+var_88]
0x18024712e  cmp     dword ptr [rax+18h], 0
0x180247132  jz      short loc_18024715C
0x180247134  mov     rax, [rsp+0D0h+var_88]
0x180247139  cmp     dword ptr [rax+1Ch], 0
0x18024713d  jz      short loc_18024714A
0x18024713f  mov     eax, cs:?g_clrrefWindowText@@3KA; ulong g_clrrefWindowText
0x180247145  mov     [rbp+var_50], eax
0x180247148  jmp     short loc_180247153
0x18024714a  mov     eax, cs:?g_clrrefWindowBack@@3KA; ulong g_clrrefWindowBack
0x180247150  mov     [rbp+var_50], eax
0x180247153  mov     eax, [rbp+var_50]
0x180247156  mov     [rsp+0D0h+color], eax
0x18024715a  jmp     short loc_180247168
0x18024715c  mov     rax, [rsp+0D0h+var_88]
0x180247161  mov     eax, [rax+20h]
0x180247164  mov     [rsp+0D0h+color], eax
0x180247168  movzx   eax, cs:g_SystemLangId
0x18024716f  and     eax, 3FFh
0x180247174  cmp     eax, 12h
0x180247177  jz      short loc_180247187
0x180247179  mov     edx, [rsp+0D0h+color]; color
0x18024717d  mov     rcx, [rbp+hdc]; hdc
0x180247181  call    cs:__imp_SetBkColor
0x180247187  lea     rdx, [rsp+0D0h+pt]; lppt
0x18024718c  mov     rcx, [rbp+hdc]; hdc
0x180247190  call    cs:__imp_GetCurrentPositionEx
0x180247196  mov     eax, [rbp+arg_10]
0x180247199  mov     ecx, [rbp+arg_18]
0x18024719c  sub     ecx, eax
0x18024719e  mov     eax, ecx
0x1802471a0  mov     ecx, [rbp+arg_10]
0x1802471a3  lea     rdx, dword_18040017C
0x1802471aa  add     rdx, rcx
0x1802471ad  mov     rcx, rdx
0x1802471b0  mov     rdx, [rbp+arg_0]
0x1802471b4  add     rdx, 5Ch ; '\'
0x1802471b8  mov     [rsp+0D0h+lpDx], 0; lpDx
0x1802471c1  mov     [rsp+0D0h+c], eax; c
0x1802471c5  mov     [rsp+0D0h+lpString], rcx; lpString
0x1802471ca  mov     qword ptr [rsp+0D0h+yBottom], rdx; lprect
0x1802471cf  mov     r9d, 4; options
0x1802471d5  xor     r8d, r8d; y
0x1802471d8  xor     edx, edx; x
0x1802471da  mov     rcx, [rbp+hdc]; hdc
0x1802471de  call    cs:__imp_ExtTextOutA
0x1802471e4  mov     rax, [rsp+0D0h+var_88]
0x1802471e9  cmp     dword ptr [rax], 0
0x1802471ec  jz      loc_18024729D
0x1802471f2  mov     edx, 1; mode
0x1802471f7  mov     rcx, [rbp+hdc]; hdc
0x1802471fb  call    cs:__imp_SetBkMode
0x180247201  lea     rdx, [rsp+0D0h+var_68]; lppt
0x180247206  mov     rcx, [rbp+hdc]; hdc
0x18024720a  call    cs:__imp_GetCurrentPositionEx
0x180247210  mov     eax, [rsp+0D0h+pt.x]
0x180247214  inc     eax
0x180247216  xor     r9d, r9d; lppt
0x180247219  mov     r8d, [rsp+0D0h+pt.y]; y
0x18024721e  mov     edx, eax; x
0x180247220  mov     rcx, [rbp+hdc]; hdc
0x180247224  call    cs:__imp_MoveToEx
0x18024722a  mov     eax, [rbp+arg_10]
0x18024722d  mov     ecx, [rbp+arg_18]
0x180247230  sub     ecx, eax
0x180247232  mov     eax, ecx
0x180247234  mov     ecx, [rbp+arg_10]
0x180247237  lea     rdx, dword_18040017C
0x18024723e  add     rdx, rcx
0x180247241  mov     rcx, rdx
0x180247244  mov     rdx, [rbp+arg_0]
0x180247248  add     rdx, 5Ch ; '\'
0x18024724c  mov     [rsp+0D0h+lpDx], 0; lpDx
0x180247255  mov     [rsp+0D0h+c], eax; c
0x180247259  mov     [rsp+0D0h+lpString], rcx; lpString
0x18024725e  mov     qword ptr [rsp+0D0h+yBottom], rdx; lprect
0x180247263  mov     r9d, 4; options
0x180247269  xor     r8d, r8d; y
0x18024726c  xor     edx, edx; x
0x18024726e  mov     rcx, [rbp+hdc]; hdc
0x180247272  call    cs:__imp_ExtTextOutA
0x180247278  xor     r9d, r9d; lppt
0x18024727b  mov     r8d, [rsp+0D0h+var_68.y]; y
0x180247280  mov     edx, [rsp+0D0h+var_68.x]; x
0x180247284  mov     rcx, [rbp+hdc]; hdc
0x180247288  call    cs:__imp_MoveToEx
0x18024728e  mov     edx, 2; mode
0x180247293  mov     rcx, [rbp+hdc]; hdc
0x180247297  call    cs:__imp_SetBkMode
0x18024729d  mov     rax, [rsp+0D0h+var_88]
0x1802472a2  cmp     dword ptr [rax+8], 0FFFFFFFFh
0x1802472a6  jz      loc_1802473E9
0x1802472ac  mov     rax, [rbp+arg_0]
0x1802472b0  mov     eax, [rax+64h]
0x1802472b3  cmp     [rsp+0D0h+pt.x], eax
0x1802472b7  jge     loc_1802473E9
0x1802472bd  mov     rax, [rsp+0D0h+var_88]
0x1802472c2  cmp     dword ptr [rax+8], 7D3h
0x1802472c9  jnz     short loc_1802472D5
0x1802472cb  mov     [rsp+0D0h+iStyle], 0
0x1802472d3  jmp     short loc_1802472DD
0x1802472d5  mov     [rsp+0D0h+iStyle], 2
0x1802472dd  xor     r8d, r8d; color
0x1802472e0  mov     edx, 1; cWidth
0x1802472e5  mov     ecx, [rsp+0D0h+iStyle]; iStyle
0x1802472e9  call    cs:__imp_CreatePen
0x1802472ef  mov     [rbp+h], rax
0x1802472f3  cmp     [rbp+h], 0
0x1802472f8  jz      loc_1802473E9
0x1802472fe  mov     rdx, [rbp+h]; h
0x180247302  mov     rcx, [rbp+hdc]; hdc
0x180247306  call    cs:__imp_SelectObject
0x18024730c  mov     [rbp+var_38], rax
0x180247310  lea     rdx, [rsp+0D0h+var_68]; lppt
0x180247315  mov     rcx, [rbp+hdc]; hdc
0x180247319  call    cs:__imp_GetCurrentPositionEx
0x18024731f  mov     edx, 1; mode
0x180247324  mov     rcx, [rbp+hdc]; hdc
0x180247328  call    cs:__imp_SetBkMode
0x18024732e  mov     [rbp+mode], eax
0x180247331  mov     rax, [rbp+arg_0]
0x180247335  mov     rax, [rax+108h]
0x18024733c  mov     eax, [rax+104h]
0x180247342  mov     ecx, [rsp+0D0h+pt.y]
0x180247346  lea     eax, [rcx+rax-1]
0x18024734a  xor     r9d, r9d; lppt
0x18024734d  mov     r8d, eax; y
0x180247350  mov     edx, [rsp+0D0h+pt.x]; x
0x180247354  mov     rcx, [rbp+hdc]; hdc
0x180247358  call    cs:__imp_MoveToEx
0x18024735e  mov     eax, [rsp+0D0h+var_68.x]
0x180247362  dec     eax
0x180247364  mov     rcx, [rbp+arg_0]
0x180247368  cmp     eax, [rcx+64h]
  ... truncated ...
```
