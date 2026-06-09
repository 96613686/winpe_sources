# MODVWR::Resize(int,int,int)

- ea: `0x1801fc91c`
- end: `0x1801fcf16`
- name: `?Resize@MODVWR@@AEAAXHHH@Z`
- size: `1530`
- prototype: `void __fastcall(MODVWR *__hidden this, int, int, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1801f8fc4`
- `0x1801fb474`
- `0x1801fc30c`

## callees

- `0x1801fadb0`
- `0x1801fbbdc`
- `0x1801fc804`
- `0x1801fc91c`
- `0x1801fcf1c`
- `0x1801fd2fc`
- `0x1801fdb00`
- `0x1801fe4dc`
- `0x1801fec20`
- `0x180379520`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1801fccf6`
- `KERNEL32!MulDiv` at `0x1801fccf6`
- `USER32!HideCaret` at `0x1801fcc32`
- `USER32!HideCaret` at `0x1801fcc32`
- `USER32!ShowCaret` at `0x1801fce6e`
- `USER32!ShowCaret` at `0x1801fce6e`
- `USER32!GetWindowPlacement` at `0x1801fc994`
- `USER32!GetWindowPlacement` at `0x1801fc994`
- `USER32!EqualRect` at `0x1801fcad8`
- `USER32!EqualRect` at `0x1801fcb0b`
- `USER32!EqualRect` at `0x1801fcb3e`
- `USER32!EqualRect` at `0x1801fcad8`
- `USER32!EqualRect` at `0x1801fcb0b`
- `USER32!EqualRect` at `0x1801fcb3e`
- `USER32!GetUpdateRgn` at `0x1801fcc65`
- `USER32!GetUpdateRgn` at `0x1801fcc65`
- `GDI32!CreateRectRgn` at `0x1801fcc42`
- `GDI32!CreateRectRgn` at `0x1801fcc42`
- `GDI32!DeleteObject` at `0x1801fcee4`
- `GDI32!DeleteObject` at `0x1801fcee4`

## pseudocode

```c
void __fastcall MODVWR::Resize(MODVWR *this, int a2, int a3, int a4)
{
  int v4; // ecx
  int v5; // [rsp+40h] [rbp-120h] BYREF
  int v6; // [rsp+44h] [rbp-11Ch] BYREF
  int v7; // [rsp+48h] [rbp-118h] BYREF
  HRGN hRgn; // [rsp+50h] [rbp-110h]
  int v9; // [rsp+58h] [rbp-108h] BYREF
  int v10; // [rsp+5Ch] [rbp-104h]
  int v11; // [rsp+60h] [rbp-100h]
  BOOL v12; // [rsp+64h] [rbp-FCh]
  int v13; // [rsp+68h] [rbp-F8h]
  BOOL v14; // [rsp+6Ch] [rbp-F4h]
  BOOL v15; // [rsp+70h] [rbp-F0h]
  int v16; // [rsp+74h] [rbp-ECh]
  int nNumber; // [rsp+78h] [rbp-E8h]
  int v18; // [rsp+7Ch] [rbp-E4h] BYREF
  __int64 v19; // [rsp+80h] [rbp-E0h]
  __int64 v20; // [rsp+88h] [rbp-D8h]
  struct tagRECT v21; // [rsp+90h] [rbp-D0h] BYREF
  WINDOWPLACEMENT wndpl; // [rsp+A0h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+D0h] [rbp-90h]
  RECT v24; // [rsp+D8h] [rbp-88h]
  RECT v25; // [rsp+E8h] [rbp-78h]
  RECT v26; // [rsp+F8h] [rbp-68h]
  RECT v27; // [rsp+108h] [rbp-58h] BYREF
  RECT rc1; // [rsp+118h] [rbp-48h] BYREF
  RECT v29; // [rsp+128h] [rbp-38h] BYREF
  struct tagRECT v30; // [rsp+138h] [rbp-28h] BYREF
  struct tagRECT v31; // [rsp+148h] [rbp-18h] BYREF

  v11 = 0;
  v9 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  hRgn = 0;
  wndpl.length = 44;
  GetWindowPlacement(*((HWND *)this + 4), &wndpl);
  if ( wndpl.showCmd != 2 )
  {
    v10 = *((_DWORD *)this + 15);
    v16 = *((_DWORD *)this + 17);
    if ( *((_QWORD *)this + 24) )
      MODVWR::RectOfRectid(this, 6, &v21);
    if ( *((_QWORD *)this + 23) )
      MODVWR::RectOfRectid(this, 7, &v30);
    if ( *((_QWORD *)this + 28) )
      MODVWR::RectOfRectid(this, 8, &v31);
    v24 = *(RECT *)((char *)this + 72);
    rc1 = v24;
    v26 = *(RECT *)((char *)this + 88);
    v27 = v26;
    v25 = *(RECT *)((char *)this + 104);
    v29 = v25;
    MODVWR::UpdateSizes(this, a4, &v9, &v5, &v6, &v7, &v18);
    if ( a2 )
    {
      v5 = 1;
      v6 = 1;
      v7 = 1;
    }
    else
    {
      v14 = !EqualRect(&rc1, (const RECT *)((char *)this + 72));
      v5 = v14;
      v15 = !EqualRect(&v27, (const RECT *)((char *)this + 88));
      v6 = v15;
      v12 = !EqualRect(&v29, (const RECT *)((char *)this + 104));
      v7 = v12;
    }
    if ( a3 )
      v5 = 1;
    if ( v5 )
    {
      v20 = *((_QWORD *)this + 1);
      (*(void (__fastcall **)(char *, RECT *, _QWORD))(v20 + 48))((char *)this + 8, &rc1, 0);
    }
    if ( v6 )
    {
      v19 = *((_QWORD *)this + 1);
      (*(void (__fastcall **)(char *, RECT *, _QWORD))(v19 + 48))((char *)this + 8, &v27, 0);
    }
    if ( v7 )
    {
      v23 = *((_QWORD *)this + 1);
      (*(void (__fastcall **)(char *, RECT *, _QWORD))(v23 + 48))((char *)this + 8, &v29, 0);
    }
    if ( v9 || a3 )
    {
      if ( *((_DWORD *)this + 44) )
        HideCaret(*((HWND *)this + 4));
      hRgn = CreateRectRgn(0, 0, 0, 0);
      if ( hRgn )
        GetUpdateRgn(*((HWND *)this + 4), hRgn, 0);
      MODVWR::InvalidateScrollbarArea(this, v5, v6, v7);
      if ( *((int *)this + 51) > 0 && (*((_DWORD *)this + 42) || *((_QWORD *)this + 6)) )
      {
        if ( v16 == v10 )
        {
          v11 = *((_DWORD *)this + 15) + (*((_DWORD *)this + 17) - *((_DWORD *)this + 15)) / 2;
        }
        else
        {
          v4 = *((_DWORD *)this + 17) - *((_DWORD *)this + 15);
          nNumber = *((_DWORD *)this + 51) - v10;
          v11 = *((_DWORD *)this + 15) + MulDiv(nNumber, v4, v16 - v10);
        }
        MODVWR::DropSplitter(this, 1, 1, v11);
      }
      if ( *((_QWORD *)this + 23) )
        MODVWR::ResizePane(this, *((struct PANE **)this + 23), &v30, hRgn, 0);
      if ( *((_QWORD *)this + 24) )
        MODVWR::ResizePane(this, *((struct PANE **)this + 24), &v21, hRgn, 0);
      if ( v18 )
        MODVWR::ResizePane(this, *((struct PANE **)this + 28), &v31, hRgn, 1);
      MODVWR::RefreshScrollbars(this, v5, v6, 0);
      if ( *((_QWORD *)this + 23) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 8LL))(*((_QWORD *)this + 23));
      if ( *((_QWORD *)this + 24) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 24) + 8LL))(*((_QWORD *)this + 24));
      if ( v9 )
        MODVWR::Invalidate3DBorders(this);
      if ( *((_DWORD *)this + 44) )
        ShowCaret(*((HWND *)this + 4));
    }
    else if ( v5 || v6 || v7 )
    {
      MODVWR::InvalidateScrollbarArea(this, v5, v6, v7);
      v13 = a2 != 0;
      MODVWR::RefreshScrollbars(this, v5, v6, v13);
    }
    if ( hRgn )
      DeleteObject(hRgn);
  }
  MODVWR::HandleCaretExistence(this, 0xFFFFFFFFFFFFFFFFuLL, -1);
}

```

## disassembly

```asm
0x1801fc91c  mov     [rsp-8+arg_18], r9d
0x1801fc921  mov     [rsp-8+arg_10], r8d
0x1801fc926  mov     [rsp-8+arg_8], edx
0x1801fc92a  mov     [rsp-8+arg_0], rcx
0x1801fc92f  push    rbp
0x1801fc930  mov     rbp, rsp
0x1801fc933  sub     rsp, 160h
0x1801fc93a  mov     rax, cs:__security_cookie
0x1801fc941  xor     rax, rsp
0x1801fc944  mov     [rbp+var_8], rax
0x1801fc948  mov     [rsp+160h+var_100], 0
0x1801fc950  mov     [rsp+160h+var_108], 0
0x1801fc958  mov     [rsp+160h+var_120], 0
0x1801fc960  mov     [rsp+160h+var_11C], 0
0x1801fc968  mov     [rsp+160h+var_118], 0
0x1801fc970  mov     [rsp+160h+hRgn], 0
0x1801fc979  mov     [rsp+160h+wndpl.length], 2Ch ; ','
0x1801fc984  lea     rdx, [rsp+160h+wndpl]; lpwndpl
0x1801fc98c  mov     rax, [rbp+arg_0]
0x1801fc990  mov     rcx, [rax+20h]; hWnd
0x1801fc994  call    cs:__imp_GetWindowPlacement
0x1801fc99a  cmp     [rsp+160h+wndpl.showCmd], 2
0x1801fc9a2  jnz     short loc_1801FC9AE
0x1801fc9a4  jmp     loc_1801FCEEA
0x1801fc9a9  jmp     loc_1801FCEEA
0x1801fc9ae  mov     rax, [rbp+arg_0]
0x1801fc9b2  mov     eax, [rax+3Ch]
0x1801fc9b5  mov     [rsp+160h+var_104], eax
0x1801fc9b9  mov     rax, [rbp+arg_0]
0x1801fc9bd  mov     eax, [rax+44h]
0x1801fc9c0  mov     [rsp+160h+var_EC], eax
0x1801fc9c4  mov     rax, [rbp+arg_0]
0x1801fc9c8  cmp     qword ptr [rax+0C0h], 0
0x1801fc9d0  jz      short loc_1801FC9E8
0x1801fc9d2  lea     r8, [rsp+160h+var_D0]
0x1801fc9da  mov     edx, 6
0x1801fc9df  mov     rcx, [rbp+arg_0]
0x1801fc9e3  call    ?RectOfRectid@MODVWR@@AEAAHW4RECTID@@PEAUtagRECT@@@Z; MODVWR::RectOfRectid(RECTID,tagRECT *)
0x1801fc9e8  mov     rax, [rbp+arg_0]
0x1801fc9ec  cmp     qword ptr [rax+0B8h], 0
0x1801fc9f4  jz      short loc_1801FCA08
0x1801fc9f6  lea     r8, [rbp+var_28]
0x1801fc9fa  mov     edx, 7
0x1801fc9ff  mov     rcx, [rbp+arg_0]
0x1801fca03  call    ?RectOfRectid@MODVWR@@AEAAHW4RECTID@@PEAUtagRECT@@@Z; MODVWR::RectOfRectid(RECTID,tagRECT *)
0x1801fca08  mov     rax, [rbp+arg_0]
0x1801fca0c  cmp     qword ptr [rax+0E0h], 0
0x1801fca14  jz      short loc_1801FCA28
0x1801fca16  lea     r8, [rbp+var_18]
0x1801fca1a  mov     edx, 8
0x1801fca1f  mov     rcx, [rbp+arg_0]
0x1801fca23  call    ?RectOfRectid@MODVWR@@AEAAHW4RECTID@@PEAUtagRECT@@@Z; MODVWR::RectOfRectid(RECTID,tagRECT *)
0x1801fca28  mov     rax, [rbp+arg_0]
0x1801fca2c  movups  xmm0, xmmword ptr [rax+48h]
0x1801fca30  movdqu  [rsp+160h+var_88], xmm0
0x1801fca39  movups  xmm0, [rsp+160h+var_88]
0x1801fca41  movdqu  xmmword ptr [rbp+rc1.left], xmm0
0x1801fca46  mov     rax, [rbp+arg_0]
0x1801fca4a  movups  xmm0, xmmword ptr [rax+58h]
0x1801fca4e  movdqu  [rbp+var_68], xmm0
0x1801fca53  movups  xmm0, [rbp+var_68]
0x1801fca57  movdqu  xmmword ptr [rbp+var_58.left], xmm0
0x1801fca5c  mov     rax, [rbp+arg_0]
0x1801fca60  movups  xmm0, xmmword ptr [rax+68h]
0x1801fca64  movdqu  [rbp+var_78], xmm0
0x1801fca69  movups  xmm0, [rbp+var_78]
0x1801fca6d  movdqu  xmmword ptr [rbp+var_38.left], xmm0
0x1801fca72  lea     rax, [rsp+160h+var_E4]
0x1801fca77  mov     [rsp+160h+var_130], rax; int *
0x1801fca7c  lea     rax, [rsp+160h+var_118]
0x1801fca81  mov     [rsp+160h+var_138], rax; int *
0x1801fca86  lea     rax, [rsp+160h+var_11C]
0x1801fca8b  mov     [rsp+160h+var_140], rax; int *
0x1801fca90  lea     r9, [rsp+160h+var_120]; int *
0x1801fca95  lea     r8, [rsp+160h+var_108]; int *
0x1801fca9a  mov     edx, [rbp+arg_18]; int
0x1801fca9d  mov     rcx, [rbp+arg_0]; this
0x1801fcaa1  call    ?UpdateSizes@MODVWR@@AEAAXHPEAH0000@Z; MODVWR::UpdateSizes(int,int *,int *,int *,int *,int *)
0x1801fcaa6  cmp     [rbp+arg_8], 0
0x1801fcaaa  jz      short loc_1801FCAC9
0x1801fcaac  mov     [rsp+160h+var_120], 1
0x1801fcab4  mov     [rsp+160h+var_11C], 1
0x1801fcabc  mov     [rsp+160h+var_118], 1
0x1801fcac4  jmp     loc_1801FCB62
0x1801fcac9  mov     rax, [rbp+arg_0]
0x1801fcacd  add     rax, 48h ; 'H'
0x1801fcad1  mov     rdx, rax; lprc2
0x1801fcad4  lea     rcx, [rbp+rc1]; lprc1
0x1801fcad8  call    cs:__imp_EqualRect
0x1801fcade  test    eax, eax
0x1801fcae0  jnz     short loc_1801FCAEC
0x1801fcae2  mov     [rsp+160h+var_F4], 1
0x1801fcaea  jmp     short loc_1801FCAF4
0x1801fcaec  mov     [rsp+160h+var_F4], 0
0x1801fcaf4  mov     eax, [rsp+160h+var_F4]
0x1801fcaf8  mov     [rsp+160h+var_120], eax
0x1801fcafc  mov     rax, [rbp+arg_0]
0x1801fcb00  add     rax, 58h ; 'X'
0x1801fcb04  mov     rdx, rax; lprc2
0x1801fcb07  lea     rcx, [rbp+var_58]; lprc1
0x1801fcb0b  call    cs:__imp_EqualRect
0x1801fcb11  test    eax, eax
0x1801fcb13  jnz     short loc_1801FCB1F
0x1801fcb15  mov     [rsp+160h+var_F0], 1
0x1801fcb1d  jmp     short loc_1801FCB27
0x1801fcb1f  mov     [rsp+160h+var_F0], 0
0x1801fcb27  mov     eax, [rsp+160h+var_F0]
0x1801fcb2b  mov     [rsp+160h+var_11C], eax
0x1801fcb2f  mov     rax, [rbp+arg_0]
0x1801fcb33  add     rax, 68h ; 'h'
0x1801fcb37  mov     rdx, rax; lprc2
0x1801fcb3a  lea     rcx, [rbp+var_38]; lprc1
0x1801fcb3e  call    cs:__imp_EqualRect
0x1801fcb44  test    eax, eax
0x1801fcb46  jnz     short loc_1801FCB52
0x1801fcb48  mov     [rsp+160h+var_FC], 1
0x1801fcb50  jmp     short loc_1801FCB5A
0x1801fcb52  mov     [rsp+160h+var_FC], 0
0x1801fcb5a  mov     eax, [rsp+160h+var_FC]
0x1801fcb5e  mov     [rsp+160h+var_118], eax
0x1801fcb62  cmp     [rbp+arg_10], 0
0x1801fcb66  jz      short loc_1801FCB70
0x1801fcb68  mov     [rsp+160h+var_120], 1
0x1801fcb70  cmp     [rsp+160h+var_120], 0
0x1801fcb75  jz      short loc_1801FCBA4
0x1801fcb77  mov     rax, [rbp+arg_0]
0x1801fcb7b  add     rax, 8
0x1801fcb7f  mov     rcx, [rbp+arg_0]
0x1801fcb83  mov     rcx, [rcx+8]
0x1801fcb87  mov     [rsp+160h+var_D8], rcx
0x1801fcb8f  xor     r8d, r8d
0x1801fcb92  lea     rdx, [rbp+rc1]
0x1801fcb96  mov     rcx, rax
0x1801fcb99  mov     rax, [rsp+160h+var_D8]
0x1801fcba1  call    qword ptr [rax+30h]
0x1801fcba4  cmp     [rsp+160h+var_11C], 0
0x1801fcba9  jz      short loc_1801FCBD8
0x1801fcbab  mov     rax, [rbp+arg_0]
0x1801fcbaf  add     rax, 8
0x1801fcbb3  mov     rcx, [rbp+arg_0]
0x1801fcbb7  mov     rcx, [rcx+8]
0x1801fcbbb  mov     [rsp+160h+var_E0], rcx
0x1801fcbc3  xor     r8d, r8d
0x1801fcbc6  lea     rdx, [rbp+var_58]
0x1801fcbca  mov     rcx, rax
0x1801fcbcd  mov     rax, [rsp+160h+var_E0]
0x1801fcbd5  call    qword ptr [rax+30h]
0x1801fcbd8  cmp     [rsp+160h+var_118], 0
0x1801fcbdd  jz      short loc_1801FCC0C
0x1801fcbdf  mov     rax, [rbp+arg_0]
0x1801fcbe3  add     rax, 8
0x1801fcbe7  mov     rcx, [rbp+arg_0]
0x1801fcbeb  mov     rcx, [rcx+8]
0x1801fcbef  mov     [rsp+160h+var_90], rcx
0x1801fcbf7  xor     r8d, r8d
0x1801fcbfa  lea     rdx, [rbp+var_38]
0x1801fcbfe  mov     rcx, rax
0x1801fcc01  mov     rax, [rsp+160h+var_90]
0x1801fcc09  call    qword ptr [rax+30h]
0x1801fcc0c  cmp     [rsp+160h+var_108], 0
0x1801fcc11  jnz     short loc_1801FCC1D
0x1801fcc13  cmp     [rbp+arg_10], 0
0x1801fcc17  jz      loc_1801FCE76
0x1801fcc1d  mov     rax, [rbp+arg_0]
0x1801fcc21  cmp     dword ptr [rax+0B0h], 0
0x1801fcc28  jz      short loc_1801FCC38
0x1801fcc2a  mov     rax, [rbp+arg_0]
0x1801fcc2e  mov     rcx, [rax+20h]; hWnd
0x1801fcc32  call    cs:__imp_HideCaret
0x1801fcc38  xor     r9d, r9d; y2
0x1801fcc3b  xor     r8d, r8d; x2
0x1801fcc3e  xor     edx, edx; y1
0x1801fcc40  xor     ecx, ecx; x1
0x1801fcc42  call    cs:__imp_CreateRectRgn
0x1801fcc48  mov     [rsp+160h+hRgn], rax
0x1801fcc4d  cmp     [rsp+160h+hRgn], 0
0x1801fcc53  jz      short loc_1801FCC6B
0x1801fcc55  xor     r8d, r8d; bErase
0x1801fcc58  mov     rdx, [rsp+160h+hRgn]; hRgn
0x1801fcc5d  mov     rax, [rbp+arg_0]
0x1801fcc61  mov     rcx, [rax+20h]; hWnd
0x1801fcc65  call    cs:__imp_GetUpdateRgn
0x1801fcc6b  mov     r9d, [rsp+160h+var_118]; int
0x1801fcc70  mov     r8d, [rsp+160h+var_11C]; int
0x1801fcc75  mov     edx, [rsp+160h+var_120]; int
0x1801fcc79  mov     rcx, [rbp+arg_0]; this
0x1801fcc7d  call    ?InvalidateScrollbarArea@MODVWR@@AEAAXHHH@Z; MODVWR::InvalidateScrollbarArea(int,int,int)
0x1801fcc82  mov     rax, [rbp+arg_0]
0x1801fcc86  cmp     dword ptr [rax+0CCh], 0
0x1801fcc8d  jle     loc_1801FCD4A
0x1801fcc93  mov     rax, [rbp+arg_0]
0x1801fcc97  cmp     dword ptr [rax+0A8h], 0
0x1801fcc9e  jnz     short loc_1801FCCAF
0x1801fcca0  mov     rax, [rbp+arg_0]
0x1801fcca4  cmp     qword ptr [rax+30h], 0
0x1801fcca9  jz      loc_1801FCD4A
0x1801fccaf  mov     eax, [rsp+160h+var_104]
0x1801fccb3  cmp     [rsp+160h+var_EC], eax
0x1801fccb7  jz      short loc_1801FCD09
0x1801fccb9  mov     eax, [rsp+160h+var_104]
0x1801fccbd  mov     ecx, [rsp+160h+var_EC]
0x1801fccc1  sub     ecx, eax
0x1801fccc3  mov     eax, ecx
0x1801fccc5  mov     rcx, [rbp+arg_0]
0x1801fccc9  mov     rdx, [rbp+arg_0]
0x1801fcccd  mov     edx, [rdx+3Ch]
0x1801fccd0  mov     ecx, [rcx+44h]
0x1801fccd3  sub     ecx, edx
0x1801fccd5  mov     rdx, [rbp+arg_0]
0x1801fccd9  mov     r8d, [rsp+160h+var_104]
0x1801fccde  mov     edx, [rdx+0CCh]
0x1801fcce4  sub     edx, r8d
0x1801fcce7  mov     [rsp+160h+nNumber], edx
0x1801fcceb  mov     r8d, eax; nDenominator
0x1801fccee  mov     edx, ecx; nNumerator
0x1801fccf0  mov     eax, [rsp+160h+nNumber]
0x1801fccf4  mov     ecx, eax; nNumber
0x1801fccf6  call    cs:__imp_MulDiv
0x1801fccfc  mov     rcx, [rbp+arg_0]
0x1801fcd00  add     eax, [rcx+3Ch]
0x1801fcd03  mov     [rsp+160h+var_100], eax
0x1801fcd07  jmp     short loc_1801FCD29
0x1801fcd09  mov     rax, [rbp+arg_0]
0x1801fcd0d  mov     rcx, [rbp+arg_0]
0x1801fcd11  mov     ecx, [rcx+3Ch]
0x1801fcd14  mov     eax, [rax+44h]
0x1801fcd17  sub     eax, ecx
0x1801fcd19  cdq
0x1801fcd1a  sub     eax, edx
0x1801fcd1c  sar     eax, 1
0x1801fcd1e  mov     rcx, [rbp+arg_0]
0x1801fcd22  add     eax, [rcx+3Ch]
0x1801fcd25  mov     [rsp+160h+var_100], eax
0x1801fcd29  mov     dword ptr [rsp+160h+var_140], 0; int
0x1801fcd31  mov     r9d, [rsp+160h+var_100]; int
0x1801fcd36  mov     r8d, 1; int
0x1801fcd3c  mov     edx, 1; int
0x1801fcd41  mov     rcx, [rbp+arg_0]; this
0x1801fcd45  call    ?DropSplitter@MODVWR@@AEAAXHHHH@Z; MODVWR::DropSplitter(int,int,int,int)
0x1801fcd4a  mov     rax, [rbp+arg_0]
0x1801fcd4e  cmp     qword ptr [rax+0B8h], 0
0x1801fcd56  jz      short loc_1801FCD7D
0x1801fcd58  mov     dword ptr [rsp+160h+var_140], 0; int
0x1801fcd60  mov     r9, [rsp+160h+hRgn]; HRGN
0x1801fcd65  lea     r8, [rbp+var_28]; struct tagRECT *
0x1801fcd69  mov     rax, [rbp+arg_0]
0x1801fcd6d  mov     rdx, [rax+0B8h]; struct PANE *
0x1801fcd74  mov     rcx, [rbp+arg_0]; this
0x1801fcd78  call    ?ResizePane@MODVWR@@AEAAXPEAVPANE@@PEAUtagRECT@@PEAUHRGN__@@H@Z; MODVWR::ResizePane(PANE *,tagRECT *,HRGN__ *,int)
0x1801fcd7d  mov     rax, [rbp+arg_0]
0x1801fcd81  cmp     qword ptr [rax+0C0h], 0
0x1801fcd89  jz      short loc_1801FCDB4
0x1801fcd8b  mov     dword ptr [rsp+160h+var_140], 0; int
0x1801fcd93  mov     r9, [rsp+160h+hRgn]; HRGN
0x1801fcd98  lea     r8, [rsp+160h+var_D0]; struct tagRECT *
0x1801fcda0  mov     rax, [rbp+arg_0]
0x1801fcda4  mov     rdx, [rax+0C0h]; struct PANE *
0x1801fcdab  mov     rcx, [rbp+arg_0]; this
0x1801fcdaf  call    ?ResizePane@MODVWR@@AEAAXPEAVPANE@@PEAUtagRECT@@PEAUHRGN__@@H@Z; MODVWR::ResizePane(PANE *,tagRECT *,HRGN__ *,int)
0x1801fcdb4  cmp     [rsp+160h+var_E4], 0
0x1801fcdb9  jz      short loc_1801FCDE0
0x1801fcdbb  mov     dword ptr [rsp+160h+var_140], 1; int
0x1801fcdc3  mov     r9, [rsp+160h+hRgn]; HRGN
0x1801fcdc8  lea     r8, [rbp+var_18]; struct tagRECT *
0x1801fcdcc  mov     rax, [rbp+arg_0]
0x1801fcdd0  mov     rdx, [rax+0E0h]; struct PANE *
0x1801fcdd7  mov     rcx, [rbp+arg_0]; this
0x1801fcddb  call    ?ResizePane@MODVWR@@AEAAXPEAVPANE@@PEAUtagRECT@@PEAUHRGN__@@H@Z; MODVWR::ResizePane(PANE *,tagRECT *,HRGN__ *,int)
0x1801fcde0  xor     r9d, r9d; int
0x1801fcde3  mov     r8d, [rsp+160h+var_11C]; int
0x1801fcde8  mov     edx, [rsp+160h+var_120]; int
0x1801fcdec  mov     rcx, [rbp+arg_0]; this
0x1801fcdf0  call    ?RefreshScrollbars@MODVWR@@AEAAXHHH@Z; MODVWR::RefreshScrollbars(int,int,int)
0x1801fcdf5  mov     rax, [rbp+arg_0]
0x1801fcdf9  cmp     qword ptr [rax+0B8h], 0
0x1801fce01  jz      short loc_1801FCE1F
0x1801fce03  mov     rax, [rbp+arg_0]
0x1801fce07  mov     rax, [rax+0B8h]
0x1801fce0e  mov     rcx, [rbp+arg_0]
0x1801fce12  mov     rcx, [rcx+0B8h]
0x1801fce19  mov     rax, [rax]
0x1801fce1c  call    qword ptr [rax+8]
0x1801fce1f  mov     rax, [rbp+arg_0]
0x1801fce23  cmp     qword ptr [rax+0C0h], 0
0x1801fce2b  jz      short loc_1801FCE49
0x1801fce2d  mov     rax, [rbp+arg_0]
0x1801fce31  mov     rax, [rax+0C0h]
0x1801fce38  mov     rcx, [rbp+arg_0]
0x1801fce3c  mov     rcx, [rcx+0C0h]
0x1801fce43  mov     rax, [rax]
0x1801fce46  call    qword ptr [rax+8]
0x1801fce49  cmp     [rsp+160h+var_108], 0
0x1801fce4e  jz      short loc_1801FCE59
0x1801fce50  mov     rcx, [rbp+arg_0]; this
0x1801fce54  call    ?Invalidate3DBorders@MODVWR@@AEAAXXZ; MODVWR::Invalidate3DBorders(void)
0x1801fce59  mov     rax, [rbp+arg_0]
0x1801fce5d  cmp     dword ptr [rax+0B0h], 0
0x1801fce64  jz      short loc_1801FCE74
0x1801fce66  mov     rax, [rbp+arg_0]
0x1801fce6a  mov     rcx, [rax+20h]; hWnd
  ... truncated ...
```
