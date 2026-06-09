# DrawMonoButton(HDC__ *,tagRECT const *,uint,ushort)

- ea: `0x1800297b8`
- end: `0x180029b0e`
- name: `?DrawMonoButton@@YAXPEAUHDC__@@PEBUtagRECT@@IG@Z`
- size: `854`
- prototype: `void __fastcall(HDC, const struct tagRECT *, unsigned int, unsigned __int16)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18007f080`
- `0x1800b3f14`

## callees

- `0x180028b30`
- `0x180029624`
- `0x1800297b8`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `USER32!LoadBitmapA` at `0x180029930`
- `USER32!LoadBitmapA` at `0x180029930`
- `USER32!CopyRect` at `0x180029882`
- `USER32!CopyRect` at `0x180029882`
- `USER32!GetSysColor` at `0x1800297fc`
- `USER32!GetSysColor` at `0x180029809`
- `USER32!GetSysColor` at `0x180029817`
- `USER32!GetSysColor` at `0x180029827`
- `USER32!GetSysColor` at `0x18002983e`
- `USER32!GetSysColor` at `0x18002984c`
- `USER32!GetSysColor` at `0x1800299e6`
- `USER32!GetSysColor` at `0x180029a21`
- `USER32!GetSysColor` at `0x1800297fc`
- `USER32!GetSysColor` at `0x180029809`
- `USER32!GetSysColor` at `0x180029817`
- `USER32!GetSysColor` at `0x180029827`
- `USER32!GetSysColor` at `0x18002983e`
- `USER32!GetSysColor` at `0x18002984c`
- `USER32!GetSysColor` at `0x1800299e6`
- `USER32!GetSysColor` at `0x180029a21`
- `USER32!OffsetRect` at `0x180029a0b`
- `USER32!OffsetRect` at `0x180029a0b`
- `USER32!DrawFocusRect` at `0x180029ac0`
- `USER32!DrawFocusRect` at `0x180029ac0`
- `USER32!InflateRect` at `0x1800298b0`
- `USER32!InflateRect` at `0x1800298d9`
- `USER32!InflateRect` at `0x180029ab3`
- `USER32!InflateRect` at `0x1800298b0`
- `USER32!InflateRect` at `0x1800298d9`
- `USER32!InflateRect` at `0x180029ab3`
- `GDI32!StretchBlt` at `0x180029a8a`
- `GDI32!StretchBlt` at `0x180029a8a`
- `GDI32!ExtTextOutA` at `0x180029914`
- `GDI32!ExtTextOutA` at `0x180029914`
- `GDI32!GetObjectA` at `0x18002994c`
- `GDI32!GetObjectA` at `0x18002994c`
- `GDI32!SelectObject` at `0x180029a3f`
- `GDI32!SelectObject` at `0x180029a3f`
- `GDI32!SetTextColor` at `0x180029a2c`
- `GDI32!SetTextColor` at `0x180029acc`
- `GDI32!SetTextColor` at `0x180029a2c`
- `GDI32!SetTextColor` at `0x180029acc`
- `GDI32!SetBkColor` at `0x1800298e5`
- `GDI32!SetBkColor` at `0x18002991f`
- `GDI32!SetBkColor` at `0x1800299f1`
- `GDI32!SetBkColor` at `0x180029ad8`
- `GDI32!SetBkColor` at `0x1800298e5`
- `GDI32!SetBkColor` at `0x18002991f`
- `GDI32!SetBkColor` at `0x1800299f1`
- `GDI32!SetBkColor` at `0x180029ad8`
- `GDI32!DeleteObject` at `0x180029ae1`
- `GDI32!DeleteObject` at `0x180029ae1`

## pseudocode

```c
void __fastcall DrawMonoButton(HDC a1, const struct tagRECT *a2, __int16 a3, unsigned __int16 a4)
{
  DWORD SysColor; // edi
  DWORD v7; // r15d
  DWORD v8; // ebx
  DWORD v9; // r13d
  DWORD v10; // ecx
  DWORD v11; // eax
  DWORD v12; // eax
  COLORREF v13; // ebx
  HBITMAP BitmapA; // rax
  HBITMAP v15; // r13
  int v16; // edi
  int v17; // ebx
  int v18; // ecx
  int v19; // r8d
  COLORREF v20; // eax
  int v21; // ecx
  COLORREF v22; // eax
  COLORREF v23; // r15d
  HBITMAP v24; // r12
  DWORD color; // [rsp+64h] [rbp-25h]
  COLORREF colora; // [rsp+64h] [rbp-25h]
  _BYTE pv[4]; // [rsp+70h] [rbp-19h] BYREF
  int wDest; // [rsp+74h] [rbp-15h]
  int hDest; // [rsp+78h] [rbp-11h]
  struct tagRECT rcDst; // [rsp+90h] [rbp+7h] BYREF

  SysColor = GetSysColor(20);
  v7 = GetSysColor(6);
  color = GetSysColor(15);
  v8 = color;
  v9 = GetSysColor(16);
  if ( Sys_fWin95Shell )
  {
    v7 = GetSysColor(21);
    v8 = GetSysColor(22);
  }
  if ( a3 < 0 )
  {
    v10 = SysColor;
    SysColor = v8;
    v8 = v10;
  }
  if ( (a3 & 1) != 0 )
  {
    v11 = SysColor;
    SysColor = v7;
    v7 = v11;
    v12 = v8;
    v8 = v9;
    v9 = v12;
  }
  CopyRect(&rcDst, a2);
  DrawRec3d(a1, &rcDst, SysColor, v7, 0xFu);
  InflateRect(&rcDst, -1, -1);
  DrawRec3d(a1, &rcDst, v8, v9, 0xFu);
  InflateRect(&rcDst, -1, -1);
  v13 = SetBkColor(a1, color);
  ExtTextOutA(a1, 0, 0, 2u, &rcDst, 0, 0, 0);
  SetBkColor(a1, v13);
  BitmapA = LoadBitmapA(Rby_hmodThun, (LPCSTR)a4);
  v15 = BitmapA;
  if ( BitmapA )
  {
    GetObjectA(BitmapA, 32, pv);
    v16 = wDest;
    v17 = hDest;
    rcDst = *a2;
    v18 = rcDst.right - rcDst.left;
    v19 = rcDst.bottom - rcDst.top;
    if ( wDest > rcDst.right - rcDst.left || hDest > v19 )
    {
      v16 = wDest / 2;
      v17 = hDest / 2;
    }
    else if ( 3 * wDest <= v18 || 3 * hDest <= v19 )
    {
      v16 = 2 * wDest;
      v17 = 2 * hDest;
    }
    rcDst.left += (v18 - v16) / 2;
    rcDst.right = rcDst.left + v16;
    rcDst.top += (v19 - v17) / 2;
    rcDst.bottom = rcDst.top + v17;
    v20 = GetSysColor(15);
    colora = SetBkColor(a1, v20);
    if ( (a3 & 1) != 0 )
      OffsetRect(&rcDst, 1, 1);
    v21 = 16;
    if ( (a3 & 6) == 0 )
      v21 = 18;
    v22 = GetSysColor(v21);
    v23 = SetTextColor(a1, v22);
    v24 = (HBITMAP)SelectObject(hdcDest, v15);
    if ( v24 )
    {
      StretchBlt(a1, rcDst.left, rcDst.top, v16, v17, hdcDest, 0, 0, wDest, hDest, 0xCC0020u);
      RestoreBitmap(hdcDest, v24);
    }
    if ( (a3 & 0x10) != 0 )
    {
      InflateRect(&rcDst, 1, 1);
      DrawFocusRect(a1, &rcDst);
    }
    SetTextColor(a1, v23);
    SetBkColor(a1, colora);
    DeleteObject(v15);
  }
}

```

## disassembly

```asm
0x1800297b8  mov     [rsp-8+arg_10], rbx
0x1800297bd  push    rbp
0x1800297be  push    rsi
0x1800297bf  push    rdi
0x1800297c0  push    r12
0x1800297c2  push    r13
0x1800297c4  push    r14
0x1800297c6  push    r15
0x1800297c8  lea     rbp, [rsp-27h]
0x1800297cd  mov     eax, 0B0h
0x1800297d2  call    _alloca_probe
0x1800297d7  sub     rsp, rax
0x1800297da  mov     rax, cs:__security_cookie
0x1800297e1  xor     rax, rsp
0x1800297e4  mov     [rbp+57h+var_40], rax
0x1800297e8  mov     rsi, rcx
0x1800297eb  mov     ecx, 14h; nIndex
0x1800297f0  mov     [rbp+57h+var_80], r9w
0x1800297f5  mov     r14d, r8d
0x1800297f8  mov     [rbp+57h+lprcSrc], rdx
0x1800297fc  call    cs:__imp_GetSysColor
0x180029802  mov     ecx, 6; nIndex
0x180029807  mov     edi, eax
0x180029809  call    cs:__imp_GetSysColor
0x18002980f  mov     ecx, 0Fh; nIndex
0x180029814  mov     r15d, eax
0x180029817  call    cs:__imp_GetSysColor
0x18002981d  mov     ecx, 10h; nIndex
0x180029822  mov     [rbp+57h+color], eax
0x180029825  mov     ebx, eax
0x180029827  call    cs:__imp_GetSysColor
0x18002982d  cmp     cs:?Sys_fWin95Shell@@3HA, 0; int Sys_fWin95Shell
0x180029834  mov     r13d, eax
0x180029837  jz      short loc_180029854
0x180029839  mov     ecx, 15h; nIndex
0x18002983e  call    cs:__imp_GetSysColor
0x180029844  mov     ecx, 16h; nIndex
0x180029849  mov     r15d, eax
0x18002984c  call    cs:__imp_GetSysColor
0x180029852  mov     ebx, eax
0x180029854  bt      r14d, 0Fh
0x180029859  jnb     short loc_180029861
0x18002985b  mov     ecx, edi
0x18002985d  mov     edi, ebx
0x18002985f  mov     ebx, ecx
0x180029861  mov     r12d, r14d
0x180029864  and     r12d, 1
0x180029868  jz      short loc_18002987A
0x18002986a  mov     eax, edi
0x18002986c  mov     edi, r15d
0x18002986f  mov     r15d, eax
0x180029872  mov     eax, ebx
0x180029874  mov     ebx, r13d
0x180029877  mov     r13d, eax
0x18002987a  mov     rdx, [rbp+57h+lprcSrc]; lprcSrc
0x18002987e  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x180029882  call    cs:__imp_CopyRect
0x180029888  mov     eax, 0Fh
0x18002988d  lea     rdx, [rbp+57h+rcDst]; struct tagRECT *
0x180029891  mov     r9d, r15d; unsigned int
0x180029894  mov     r8d, edi; unsigned int
0x180029897  mov     rcx, rsi; HDC
0x18002989a  mov     word ptr [rsp+0E0h+lprect], ax; unsigned __int16
0x18002989f  call    ?DrawRec3d@@YAXPEAUHDC__@@PEBUtagRECT@@KKG@Z; DrawRec3d(HDC__ *,tagRECT const *,ulong,ulong,ushort)
0x1800298a4  or      edi, 0FFFFFFFFh
0x1800298a7  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800298ab  mov     r8d, edi; dy
0x1800298ae  mov     edx, edi; dx
0x1800298b0  call    cs:__imp_InflateRect
0x1800298b6  lea     eax, [rdi+10h]
0x1800298b9  lea     rdx, [rbp+57h+rcDst]; struct tagRECT *
0x1800298bd  mov     r9d, r13d; unsigned int
0x1800298c0  mov     r8d, ebx; unsigned int
0x1800298c3  mov     rcx, rsi; HDC
0x1800298c6  mov     word ptr [rsp+0E0h+lprect], ax; unsigned __int16
0x1800298cb  call    ?DrawRec3d@@YAXPEAUHDC__@@PEBUtagRECT@@KKG@Z; DrawRec3d(HDC__ *,tagRECT const *,ulong,ulong,ushort)
0x1800298d0  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800298d4  mov     r8d, edi; dy
0x1800298d7  mov     edx, edi; dx
0x1800298d9  call    cs:__imp_InflateRect
0x1800298df  mov     edx, [rbp+57h+color]; color
0x1800298e2  mov     rcx, rsi; hdc
0x1800298e5  call    cs:__imp_SetBkColor
0x1800298eb  xor     r15d, r15d
0x1800298ee  lea     r9d, [rdi+3]; options
0x1800298f2  mov     [rsp+0E0h+lpDx], r15; ySrc
0x1800298f7  mov     ebx, eax
0x1800298f9  lea     rax, [rbp+57h+rcDst]
0x1800298fd  mov     [rsp+0E0h+c], r15d; xSrc
0x180029902  xor     r8d, r8d; y
0x180029905  xor     edx, edx; x
0x180029907  mov     rcx, rsi; hdc
0x18002990a  mov     [rsp+0E0h+lpString], r15; lpString
0x18002990f  mov     [rsp+0E0h+lprect], rax; lprect
0x180029914  call    cs:__imp_ExtTextOutA
0x18002991a  mov     edx, ebx; color
0x18002991c  mov     rcx, rsi; hdc
0x18002991f  call    cs:__imp_SetBkColor
0x180029925  movzx   edx, [rbp+57h+var_80]; lpBitmapName
0x180029929  mov     rcx, cs:?Rby_hmodThun@@3PEAUHINSTANCE__@@EA; hInstance
0x180029930  call    cs:__imp_LoadBitmapA
0x180029936  mov     r13, rax
0x180029939  test    rax, rax
0x18002993c  jz      loc_180029AE7
0x180029942  lea     r8, [rbp+57h+pv]; pv
0x180029946  lea     edx, [rdi+21h]; c
0x180029949  mov     rcx, rax; h
0x18002994c  call    cs:__imp_GetObjectA
0x180029952  mov     rax, [rbp+57h+lprcSrc]
0x180029956  mov     edi, [rbp+57h+wDest]
0x180029959  movups  xmm0, xmmword ptr [rax]
0x18002995c  mov     ebx, [rbp+57h+hDest]
0x18002995f  movdqu  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180029964  mov     rax, qword ptr [rbp+57h+rcDst.left]
0x180029968  mov     r8, qword ptr [rbp+57h+rcDst.right]
0x18002996c  mov     ecx, [rbp+57h+rcDst.right]
0x18002996f  mov     r9d, [rbp+57h+rcDst.left]
0x180029973  shr     rax, 20h
0x180029977  shr     r8, 20h
0x18002997b  sub     ecx, r9d
0x18002997e  sub     r8d, eax
0x180029981  cmp     edi, ecx
0x180029983  jg      short loc_18002999F
0x180029985  cmp     ebx, r8d
0x180029988  jg      short loc_18002999F
0x18002998a  lea     eax, [rdi+rdi*2]
0x18002998d  cmp     eax, ecx
0x18002998f  jle     short loc_180029999
0x180029991  lea     eax, [rbx+rbx*2]
0x180029994  cmp     eax, r8d
0x180029997  jg      short loc_1800299B1
0x180029999  add     edi, edi
0x18002999b  add     ebx, ebx
0x18002999d  jmp     short loc_1800299B1
0x18002999f  mov     eax, edi
0x1800299a1  cdq
0x1800299a2  sub     eax, edx
0x1800299a4  sar     eax, 1
0x1800299a6  mov     edi, eax
0x1800299a8  mov     eax, ebx
0x1800299aa  cdq
0x1800299ab  sub     eax, edx
0x1800299ad  sar     eax, 1
0x1800299af  mov     ebx, eax
0x1800299b1  sub     ecx, edi
0x1800299b3  sub     r8d, ebx
0x1800299b6  mov     eax, ecx
0x1800299b8  cdq
0x1800299b9  sub     eax, edx
0x1800299bb  sar     eax, 1
0x1800299bd  add     r9d, eax
0x1800299c0  mov     eax, r8d
0x1800299c3  cdq
0x1800299c4  lea     ecx, [r9+rdi]
0x1800299c8  mov     [rbp+57h+rcDst.left], r9d
0x1800299cc  mov     [rbp+57h+rcDst.right], ecx
0x1800299cf  mov     ecx, [rbp+57h+rcDst.top]
0x1800299d2  sub     eax, edx
0x1800299d4  sar     eax, 1
0x1800299d6  add     ecx, eax
0x1800299d8  mov     [rbp+57h+rcDst.top], ecx
0x1800299db  lea     eax, [rcx+rbx]
0x1800299de  mov     ecx, 0Fh; nIndex
0x1800299e3  mov     [rbp+57h+rcDst.bottom], eax
0x1800299e6  call    cs:__imp_GetSysColor
0x1800299ec  mov     rcx, rsi; hdc
0x1800299ef  mov     edx, eax; color
0x1800299f1  call    cs:__imp_SetBkColor
0x1800299f7  mov     [rbp+57h+color], eax
0x1800299fa  test    r12d, r12d
0x1800299fd  jz      short loc_180029A11
0x1800299ff  mov     edx, 1; dx
0x180029a04  lea     rcx, [rbp+57h+rcDst]; lprc
0x180029a08  mov     r8d, edx; dy
0x180029a0b  call    cs:__imp_OffsetRect
0x180029a11  mov     ecx, 10h
0x180029a16  test    r14b, 6
0x180029a1a  jnz     short loc_180029A21
0x180029a1c  mov     ecx, 12h; nIndex
0x180029a21  call    cs:__imp_GetSysColor
0x180029a27  mov     rcx, rsi; hdc
0x180029a2a  mov     edx, eax; color
0x180029a2c  call    cs:__imp_SetTextColor
0x180029a32  mov     rcx, cs:hdcDest; hdc
0x180029a39  mov     rdx, r13; h
0x180029a3c  mov     r15d, eax
0x180029a3f  call    cs:__imp_SelectObject
0x180029a45  mov     r12, rax
0x180029a48  test    rax, rax
0x180029a4b  jz      short loc_180029A9F
0x180029a4d  mov     ecx, [rbp+57h+hDest]
0x180029a50  mov     r8d, [rbp+57h+rcDst.top]; yDest
0x180029a54  mov     edx, [rbp+57h+rcDst.left]; xDest
0x180029a57  mov     [rsp+0E0h+rop], 0CC0020h; rop
0x180029a5f  mov     [rsp+0E0h+hSrc], ecx; hSrc
0x180029a63  mov     ecx, [rbp+57h+wDest]
0x180029a66  mov     [rsp+0E0h+wSrc], ecx; wSrc
0x180029a6a  mov     rcx, cs:hdcDest
0x180029a71  and     dword ptr [rsp+0E0h+lpDx], 0
0x180029a76  and     [rsp+0E0h+c], 0
0x180029a7b  mov     [rsp+0E0h+lpString], rcx; hdcSrc
0x180029a80  mov     r9d, edi; wDest
0x180029a83  mov     rcx, rsi; hdcDest
0x180029a86  mov     dword ptr [rsp+0E0h+lprect], ebx; hDest
0x180029a8a  call    cs:__imp_StretchBlt
0x180029a90  mov     rcx, cs:hdcDest; HDC
0x180029a97  mov     rdx, r12; HBITMAP
0x180029a9a  call    ?RestoreBitmap@@YAXPEAUHDC__@@PEAUHBITMAP__@@@Z; RestoreBitmap(HDC__ *,HBITMAP__ *)
0x180029a9f  test    r14b, 10h
0x180029aa3  jz      short loc_180029AC6
0x180029aa5  mov     eax, 1
0x180029aaa  lea     rcx, [rbp+57h+rcDst]; lprc
0x180029aae  mov     r8d, eax; dy
0x180029ab1  mov     edx, eax; dx
0x180029ab3  call    cs:__imp_InflateRect
0x180029ab9  lea     rdx, [rbp+57h+rcDst]; lprc
0x180029abd  mov     rcx, rsi; hDC
0x180029ac0  call    cs:__imp_DrawFocusRect
0x180029ac6  mov     edx, r15d; color
0x180029ac9  mov     rcx, rsi; hdc
0x180029acc  call    cs:__imp_SetTextColor
0x180029ad2  mov     edx, [rbp+57h+color]; color
0x180029ad5  mov     rcx, rsi; hdc
0x180029ad8  call    cs:__imp_SetBkColor
0x180029ade  mov     rcx, r13; ho
0x180029ae1  call    cs:__imp_DeleteObject
0x180029ae7  mov     rcx, [rbp+57h+var_40]
0x180029aeb  xor     rcx, rsp; StackCookie
0x180029aee  call    __security_check_cookie
0x180029af3  mov     rbx, [rsp+0E0h+arg_10]
0x180029afb  add     rsp, 0B0h
0x180029b02  pop     r15
0x180029b04  pop     r14
0x180029b06  pop     r13
0x180029b08  pop     r12
0x180029b0a  pop     rdi
0x180029b0b  pop     rsi
0x180029b0c  pop     rbp
0x180029b0d  retn
```
