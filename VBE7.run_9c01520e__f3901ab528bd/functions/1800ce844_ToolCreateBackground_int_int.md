# ToolCreateBackground(int,int)

- ea: `0x1800ce844`
- end: `0x1800cec74`
- name: `?ToolCreateBackground@@YAXHH@Z`
- size: `1072`
- prototype: `void __fastcall(int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800d0780`

## callees

- `0x180001180`
- `0x1800187f0`
- `0x1800ce844`
- `0x1800d07c4`
- `0x1800d0870`
- `0x1800d0e74`
- `0x1800d1654`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800ce888`
- `USER32!GetSystemMetrics` at `0x1800ce894`
- `USER32!GetSystemMetrics` at `0x1800ce888`
- `USER32!GetSystemMetrics` at `0x1800ce894`
- `USER32!DrawEdge` at `0x1800ceac5`
- `USER32!DrawEdge` at `0x1800ceb62`
- `USER32!DrawEdge` at `0x1800ceac5`
- `USER32!DrawEdge` at `0x1800ceb62`
- `USER32!DrawTextA` at `0x1800ceae8`
- `USER32!DrawTextA` at `0x1800ceb85`
- `USER32!DrawTextA` at `0x1800ceae8`
- `USER32!DrawTextA` at `0x1800ceb85`
- `USER32!GetDC` at `0x1800ce8b7`
- `USER32!GetDC` at `0x1800ce8b7`
- `USER32!ReleaseDC` at `0x1800cebf1`
- `USER32!ReleaseDC` at `0x1800cebf1`
- `USER32!GetSysColor` at `0x1800cea50`
- `USER32!GetSysColor` at `0x1800cea50`
- `GDI32!CreateCompatibleBitmap` at `0x1800ce8f2`
- `GDI32!CreateCompatibleBitmap` at `0x1800ce8f2`
- `GDI32!CreateCompatibleDC` at `0x1800ce8d0`
- `GDI32!CreateCompatibleDC` at `0x1800ce9b6`
- `GDI32!CreateCompatibleDC` at `0x1800ce8d0`
- `GDI32!CreateCompatibleDC` at `0x1800ce9b6`
- `GDI32!BitBlt` at `0x1800cec54`
- `GDI32!BitBlt` at `0x1800cec54`
- `GDI32!DeleteDC` at `0x1800ce9df`
- `GDI32!DeleteDC` at `0x1800cebdc`
- `GDI32!DeleteDC` at `0x1800cec69`
- `GDI32!DeleteDC` at `0x1800ce9df`
- `GDI32!DeleteDC` at `0x1800cebdc`
- `GDI32!DeleteDC` at `0x1800cec69`
- `GDI32!PatBlt` at `0x1800ce957`
- `GDI32!PatBlt` at `0x1800ce957`
- `GDI32!SetBkMode` at `0x1800cea37`
- `GDI32!SetBkMode` at `0x1800cea37`
- `GDI32!SelectObject` at `0x1800ce90e`
- `GDI32!SelectObject` at `0x1800ce930`
- `GDI32!SelectObject` at `0x1800ce9ca`
- `GDI32!SelectObject` at `0x1800cea26`
- `GDI32!SelectObject` at `0x1800cebaf`
- `GDI32!SelectObject` at `0x1800cebce`
- `GDI32!SelectObject` at `0x1800cec60`
- `GDI32!SelectObject` at `0x1800ce90e`
- `GDI32!SelectObject` at `0x1800ce930`
- `GDI32!SelectObject` at `0x1800ce9ca`
- `GDI32!SelectObject` at `0x1800cea26`
- `GDI32!SelectObject` at `0x1800cebaf`
- `GDI32!SelectObject` at `0x1800cebce`
- `GDI32!SelectObject` at `0x1800cec60`
- `GDI32!SetTextColor` at `0x1800cea45`
- `GDI32!SetTextColor` at `0x1800cea45`
- `GDI32!SetBkColor` at `0x1800cea5b`
- `GDI32!SetBkColor` at `0x1800cea5b`
- `GDI32!DeleteObject` at `0x1800cebbd`
- `GDI32!DeleteObject` at `0x1800cebbd`

## pseudocode

```c
void __fastcall ToolCreateBackground(int a1, int a2)
{
  HDC CompatibleDC; // rbx
  HGDIOBJ v5; // r14
  HGDIOBJ v6; // r12
  HDC DC; // rax
  HDC v8; // rsi
  HBITMAP CompatibleBitmap; // rax
  HBRUSH v10; // rax
  char *v11; // rdx
  int i; // r11d
  HDC v13; // rax
  HDC v14; // rdi
  HGDIOBJ v15; // r15
  int v16; // r11d
  HFONT v17; // rax
  HGDIOBJ v18; // r15
  COLORREF SysColor; // eax
  int v20; // edi
  struct tagRECT v21; // xmm5
  int top; // eax
  const CHAR *v23; // rax
  int bottom; // eax
  int v25; // edi
  const CHAR *v26; // rax
  int SystemMetrics; // [rsp+50h] [rbp-9h]
  int v28; // [rsp+54h] [rbp-5h]
  HDC v29; // [rsp+58h] [rbp-1h]
  struct tagRECT rc; // [rsp+60h] [rbp+7h] BYREF
  struct tagRECT qrc; // [rsp+70h] [rbp+17h] BYREF

  CompatibleDC = 0;
  v5 = 0;
  SystemMetrics = GetSystemMetrics(45);
  v28 = GetSystemMetrics(46);
  _ToolUpdate();
  v6 = qword_1803F38A0;
  qword_1803F38A0 = 0;
  DC = GetDC(hwnd);
  v8 = DC;
  v29 = DC;
  if ( !DC )
    goto LABEL_27;
  CompatibleDC = CreateCompatibleDC(DC);
  if ( !CompatibleDC )
    goto LABEL_27;
  CompatibleBitmap = CreateCompatibleBitmap(v8, w, dword_1803F38C4);
  qword_1803F38A0 = CompatibleBitmap;
  if ( !CompatibleBitmap )
    goto LABEL_27;
  v5 = SelectObject(CompatibleDC, CompatibleBitmap);
  if ( !v5 )
    goto LABEL_27;
  v10 = BrHbrushCreate(0x8000000F);
  SelectObject(CompatibleDC, v10);
  PatBlt(CompatibleDC, 0, 0, w, dword_1803F38C4, 0xF00021u);
  v11 = (char *)qword_1803F38E8;
  for ( i = 0; i < dword_1803F38DC; v11 += 16 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 464LL) + 32LL) + 32LL) == dword_1803F3904 )
      break;
    ++i;
  }
  dword_1803F3900 = i;
  if ( !a1 && !a2 )
  {
    if ( dword_1803F38E0 )
    {
      v13 = CreateCompatibleDC(v8);
      v14 = v13;
      if ( v13 )
      {
        v15 = SelectObject(v13, v6);
        if ( v15 )
        {
          BitBlt(CompatibleDC, 0, 0, w, dword_1803F38C4, v14, 0, 0, 0xCC0020u);
          SelectObject(v14, v15);
          DeleteDC(v14);
          goto LABEL_15;
        }
        DeleteDC(v14);
      }
    }
  }
  dword_1803F38E0 = 0;
  PalDrawToolBitmaps(CompatibleDC);
LABEL_15:
  PalDrawCtlBitmaps(CompatibleDC, a2);
  v16 = dword_1803F393C;
  if ( dword_1803F393C >= dword_1803F38E0 )
    v16 = -1;
  dword_1803F393C = v16;
  v17 = HfontIdeLight();
  v18 = SelectObject(CompatibleDC, v17);
  SetBkMode(CompatibleDC, 2);
  SetTextColor(CompatibleDC, 0x12u);
  SysColor = GetSysColor(15);
  SetBkColor(CompatibleDC, SysColor);
  v20 = dword_1803F3904;
  v21 = left;
  qrc = left;
  top = left.top - 1;
  if ( dword_1803F3904 >= 0 )
  {
    do
    {
      qrc.bottom = top;
      qrc.top = top - _nTabHeight;
      rc.right = qrc.right - SystemMetrics;
      rc.top = v28 + top - _nTabHeight;
      rc.bottom = top - v28;
      rc.left = SystemMetrics + qrc.left;
      DrawEdge(CompatibleDC, &qrc, 5u, 0xFu);
      v23 = SzOfGrp(v20);
      DrawTextA(CompatibleDC, v23, -1, &rc, 0x25u);
      top = qrc.top;
      if ( qrc.top < 0 )
        break;
      --v20;
    }
    while ( v20 >= 0 );
    v20 = dword_1803F3904;
    v21 = left;
    v8 = v29;
  }
  qrc = v21;
  bottom = v21.bottom - 1;
  v25 = v20 + 1;
  qrc.bottom = v21.bottom - 1;
  if ( v25 < dword_1803F3908 )
  {
    do
    {
      qrc.top = bottom;
      qrc.bottom = _nTabHeight + bottom;
      rc.right = qrc.right - SystemMetrics;
      rc.top = v28 + bottom;
      rc.bottom = _nTabHeight + bottom - v28;
      rc.left = SystemMetrics + qrc.left;
      DrawEdge(CompatibleDC, &qrc, 5u, 0xFu);
      v26 = SzOfGrp(v25);
      DrawTextA(CompatibleDC, v26, -1, &rc, 0x25u);
      bottom = qrc.bottom;
      if ( qrc.bottom > dword_1803F38C4 )
        break;
      ++v25;
    }
    while ( v25 < dword_1803F3908 );
    v8 = v29;
  }
  if ( v18 )
    SelectObject(CompatibleDC, v18);
LABEL_27:
  if ( v6 )
    DeleteObject(v6);
  if ( v5 )
    SelectObject(CompatibleDC, v5);
  if ( CompatibleDC )
    DeleteDC(CompatibleDC);
  if ( v8 )
    ReleaseDC(hwnd, v8);
}

```

## disassembly

```asm
0x1800ce844  mov     rax, rsp
0x1800ce847  mov     [rax+8], rbx
0x1800ce84b  mov     [rax+18h], rsi
0x1800ce84f  mov     [rax+20h], rdi
0x1800ce853  push    rbp
0x1800ce854  push    r12
0x1800ce856  push    r13
0x1800ce858  push    r14
0x1800ce85a  push    r15
0x1800ce85c  lea     rbp, [rax-5Fh]
0x1800ce860  mov     eax, 90h
0x1800ce865  call    _alloca_probe
0x1800ce86a  sub     rsp, rax
0x1800ce86d  mov     rax, cs:__security_cookie
0x1800ce874  xor     rax, rsp
0x1800ce877  mov     [rbp+57h+var_30], rax
0x1800ce87b  mov     edi, ecx
0x1800ce87d  xor     ebx, ebx
0x1800ce87f  mov     r13d, edx
0x1800ce882  lea     ecx, [rbx+2Dh]; nIndex
0x1800ce885  xor     r14d, r14d
0x1800ce888  call    cs:__imp_GetSystemMetrics
0x1800ce88e  lea     ecx, [rbx+2Eh]; nIndex
0x1800ce891  mov     [rbp+57h+var_60], eax
0x1800ce894  call    cs:__imp_GetSystemMetrics
0x1800ce89a  mov     [rbp+57h+var_5C], eax
0x1800ce89d  call    ?_ToolUpdate@@YAXXZ; _ToolUpdate(void)
0x1800ce8a2  mov     r12, cs:qword_1803F38A0
0x1800ce8a9  mov     rcx, cs:hwnd; hWnd
0x1800ce8b0  and     cs:qword_1803F38A0, rbx
0x1800ce8b7  call    cs:__imp_GetDC
0x1800ce8bd  mov     rsi, rax
0x1800ce8c0  mov     [rbp+57h+var_58], rax
0x1800ce8c4  test    rax, rax
0x1800ce8c7  jz      loc_1800CEBB5
0x1800ce8cd  mov     rcx, rax; hdc
0x1800ce8d0  call    cs:__imp_CreateCompatibleDC
0x1800ce8d6  mov     rbx, rax
0x1800ce8d9  test    rax, rax
0x1800ce8dc  jz      loc_1800CEBB5
0x1800ce8e2  mov     r8d, cs:dword_1803F38C4; cy
0x1800ce8e9  mov     edx, cs:w; cx
0x1800ce8ef  mov     rcx, rsi; hdc
0x1800ce8f2  call    cs:__imp_CreateCompatibleBitmap
0x1800ce8f8  mov     cs:qword_1803F38A0, rax
0x1800ce8ff  test    rax, rax
0x1800ce902  jz      loc_1800CEBB5
0x1800ce908  mov     rdx, rax; h
0x1800ce90b  mov     rcx, rbx; hdc
0x1800ce90e  call    cs:__imp_SelectObject
0x1800ce914  mov     r14, rax
0x1800ce917  test    rax, rax
0x1800ce91a  jz      loc_1800CEBB5
0x1800ce920  mov     ecx, 8000000Fh; unsigned int
0x1800ce925  call    ?BrHbrushCreate@@YAPEAUHBRUSH__@@K@Z; BrHbrushCreate(ulong)
0x1800ce92a  mov     rcx, rbx; hdc
0x1800ce92d  mov     rdx, rax; h
0x1800ce930  call    cs:__imp_SelectObject
0x1800ce936  mov     ecx, cs:dword_1803F38C4
0x1800ce93c  mov     r9d, cs:w; w
0x1800ce943  mov     [rsp+0B0h+rop], 0F00021h; rop
0x1800ce94b  mov     [rsp+0B0h+h], ecx; h
0x1800ce94f  xor     r8d, r8d; y
0x1800ce952  mov     rcx, rbx; hdc
0x1800ce955  xor     edx, edx; x
0x1800ce957  call    cs:__imp_PatBlt
0x1800ce95d  mov     r8d, cs:dword_1803F38DC
0x1800ce964  mov     rdx, cs:qword_1803F38E8
0x1800ce96b  xor     r11d, r11d
0x1800ce96e  test    r8d, r8d
0x1800ce971  jle     short loc_1800CE99A
0x1800ce973  mov     r9d, cs:dword_1803F3904
0x1800ce97a  mov     rax, [rdx]
0x1800ce97d  mov     rcx, [rax+1D0h]
0x1800ce984  mov     rax, [rcx+20h]
0x1800ce988  cmp     [rax+20h], r9d
0x1800ce98c  jz      short loc_1800CE99A
0x1800ce98e  inc     r11d
0x1800ce991  add     rdx, 10h
0x1800ce995  cmp     r11d, r8d
0x1800ce998  jl      short loc_1800CE97A
0x1800ce99a  mov     cs:dword_1803F3900, r11d
0x1800ce9a1  test    edi, edi
0x1800ce9a3  jnz     short loc_1800CE9E5
0x1800ce9a5  test    r13d, r13d
0x1800ce9a8  jnz     short loc_1800CE9E5
0x1800ce9aa  cmp     cs:dword_1803F38E0, r13d
0x1800ce9b1  jz      short loc_1800CE9E5
0x1800ce9b3  mov     rcx, rsi; hdc
0x1800ce9b6  call    cs:__imp_CreateCompatibleDC
0x1800ce9bc  mov     rdi, rax
0x1800ce9bf  test    rax, rax
0x1800ce9c2  jz      short loc_1800CE9E5
0x1800ce9c4  mov     rdx, r12; h
0x1800ce9c7  mov     rcx, rax; hdc
0x1800ce9ca  call    cs:__imp_SelectObject
0x1800ce9d0  mov     r15, rax
0x1800ce9d3  test    rax, rax
0x1800ce9d6  jnz     loc_1800CEC24
0x1800ce9dc  mov     rcx, rdi; hdc
0x1800ce9df  call    cs:__imp_DeleteDC
0x1800ce9e5  and     cs:dword_1803F38E0, 0
0x1800ce9ec  mov     rcx, rbx; HDC
0x1800ce9ef  call    ?PalDrawToolBitmaps@@YAXPEAUHDC__@@@Z; PalDrawToolBitmaps(HDC__ *)
0x1800ce9f4  mov     edx, r13d; int
0x1800ce9f7  mov     rcx, rbx; HDC
0x1800ce9fa  call    ?PalDrawCtlBitmaps@@YAXPEAUHDC__@@H@Z; PalDrawCtlBitmaps(HDC__ *,int)
0x1800ce9ff  mov     r11d, cs:dword_1803F393C
0x1800cea06  or      eax, 0FFFFFFFFh
0x1800cea09  cmp     r11d, cs:dword_1803F38E0
0x1800cea10  cmovnb  r11d, eax
0x1800cea14  mov     cs:dword_1803F393C, r11d
0x1800cea1b  call    ?HfontIdeLight@@YAPEAUHFONT__@@XZ; HfontIdeLight(void)
0x1800cea20  mov     rcx, rbx; hdc
0x1800cea23  mov     rdx, rax; h
0x1800cea26  call    cs:__imp_SelectObject
0x1800cea2c  mov     edx, 2; mode
0x1800cea31  mov     rcx, rbx; hdc
0x1800cea34  mov     r15, rax
0x1800cea37  call    cs:__imp_SetBkMode
0x1800cea3d  mov     edx, 12h; color
0x1800cea42  mov     rcx, rbx; hdc
0x1800cea45  call    cs:__imp_SetTextColor
0x1800cea4b  mov     ecx, 0Fh; nIndex
0x1800cea50  call    cs:__imp_GetSysColor
0x1800cea56  mov     rcx, rbx; hdc
0x1800cea59  mov     edx, eax; color
0x1800cea5b  call    cs:__imp_SetBkColor
0x1800cea61  mov     edi, cs:dword_1803F3904
0x1800cea67  mov     r13d, [rbp+57h+var_60]
0x1800cea6b  movaps  xmm5, xmmword ptr cs:left.left
0x1800cea72  movdqu  xmmword ptr [rbp+57h+qrc.left], xmm5
0x1800cea77  mov     rax, qword ptr [rbp+57h+qrc.left]
0x1800cea7b  shr     rax, 20h
0x1800cea7f  dec     eax
0x1800cea81  test    edi, edi
0x1800cea83  js      loc_1800CEB0A
0x1800cea89  mov     esi, [rbp+57h+var_5C]
0x1800cea8c  mov     ecx, [rbp+57h+qrc.left]
0x1800cea8f  mov     [rbp+57h+qrc.bottom], eax
0x1800cea92  sub     eax, cs:?_nTabHeight@@3HA; int _nTabHeight
0x1800cea98  add     ecx, r13d
0x1800cea9b  mov     [rbp+57h+qrc.top], eax
0x1800cea9e  mov     r9d, 0Fh; grfFlags
0x1800ceaa4  lea     r8d, [r9-0Ah]; edge
0x1800ceaa8  lea     rdx, [rbp+57h+qrc]; qrc
0x1800ceaac  movaps  xmm0, xmmword ptr [rbp+57h+qrc.left]
0x1800ceab0  movdqa  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800ceab5  sub     [rbp+57h+rc.right], r13d
0x1800ceab9  add     [rbp+57h+rc.top], esi
0x1800ceabc  sub     [rbp+57h+rc.bottom], esi
0x1800ceabf  mov     [rbp+57h+rc.left], ecx
0x1800ceac2  mov     rcx, rbx; hdc
0x1800ceac5  call    cs:__imp_DrawEdge
0x1800ceacb  mov     ecx, edi; int
0x1800ceacd  call    ?SzOfGrp@@YAPEADH@Z; SzOfGrp(int)
0x1800cead2  lea     r9, [rbp+57h+rc]; lprc
0x1800cead6  or      r8d, 0FFFFFFFFh; cchText
0x1800ceada  mov     rcx, rbx; hdc
0x1800ceadd  mov     rdx, rax; lpchText
0x1800ceae0  mov     [rsp+0B0h+h], 25h ; '%'; format
0x1800ceae8  call    cs:__imp_DrawTextA
0x1800ceaee  mov     eax, [rbp+57h+qrc.top]
0x1800ceaf1  test    eax, eax
0x1800ceaf3  js      short loc_1800CEAF9
0x1800ceaf5  dec     edi
0x1800ceaf7  jns     short loc_1800CEA8C
0x1800ceaf9  mov     edi, cs:dword_1803F3904
0x1800ceaff  movaps  xmm5, xmmword ptr cs:left.left
0x1800ceb06  mov     rsi, [rbp+57h+var_58]
0x1800ceb0a  movdqu  xmmword ptr [rbp+57h+qrc.left], xmm5
0x1800ceb0f  mov     rax, qword ptr [rbp+57h+qrc.right]
0x1800ceb13  shr     rax, 20h
0x1800ceb17  dec     eax
0x1800ceb19  inc     edi
0x1800ceb1b  cmp     edi, cs:dword_1803F3908
0x1800ceb21  mov     [rbp+57h+qrc.bottom], eax
0x1800ceb24  jge     short loc_1800CEBA4
0x1800ceb26  mov     esi, [rbp+57h+var_5C]
0x1800ceb29  mov     ecx, [rbp+57h+qrc.left]
0x1800ceb2c  mov     [rbp+57h+qrc.top], eax
0x1800ceb2f  add     eax, cs:?_nTabHeight@@3HA; int _nTabHeight
0x1800ceb35  add     ecx, r13d
0x1800ceb38  mov     [rbp+57h+qrc.bottom], eax
0x1800ceb3b  mov     r9d, 0Fh; grfFlags
0x1800ceb41  lea     r8d, [r9-0Ah]; edge
0x1800ceb45  lea     rdx, [rbp+57h+qrc]; qrc
0x1800ceb49  movaps  xmm0, xmmword ptr [rbp+57h+qrc.left]
0x1800ceb4d  movdqa  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800ceb52  sub     [rbp+57h+rc.right], r13d
0x1800ceb56  add     [rbp+57h+rc.top], esi
0x1800ceb59  sub     [rbp+57h+rc.bottom], esi
0x1800ceb5c  mov     [rbp+57h+rc.left], ecx
0x1800ceb5f  mov     rcx, rbx; hdc
0x1800ceb62  call    cs:__imp_DrawEdge
0x1800ceb68  mov     ecx, edi; int
0x1800ceb6a  call    ?SzOfGrp@@YAPEADH@Z; SzOfGrp(int)
0x1800ceb6f  lea     r9, [rbp+57h+rc]; lprc
0x1800ceb73  or      r8d, 0FFFFFFFFh; cchText
0x1800ceb77  mov     rcx, rbx; hdc
0x1800ceb7a  mov     rdx, rax; lpchText
0x1800ceb7d  mov     [rsp+0B0h+h], 25h ; '%'; format
0x1800ceb85  call    cs:__imp_DrawTextA
0x1800ceb8b  mov     eax, [rbp+57h+qrc.bottom]
0x1800ceb8e  cmp     eax, cs:dword_1803F38C4
0x1800ceb94  jg      short loc_1800CEBA0
0x1800ceb96  inc     edi
0x1800ceb98  cmp     edi, cs:dword_1803F3908
0x1800ceb9e  jl      short loc_1800CEB29
0x1800ceba0  mov     rsi, [rbp+57h+var_58]
0x1800ceba4  test    r15, r15
0x1800ceba7  jz      short loc_1800CEBB5
0x1800ceba9  mov     rdx, r15; h
0x1800cebac  mov     rcx, rbx; hdc
0x1800cebaf  call    cs:__imp_SelectObject
0x1800cebb5  test    r12, r12
0x1800cebb8  jz      short loc_1800CEBC3
0x1800cebba  mov     rcx, r12; ho
0x1800cebbd  call    cs:__imp_DeleteObject
0x1800cebc3  test    r14, r14
0x1800cebc6  jz      short loc_1800CEBD4
0x1800cebc8  mov     rdx, r14; h
0x1800cebcb  mov     rcx, rbx; hdc
0x1800cebce  call    cs:__imp_SelectObject
0x1800cebd4  test    rbx, rbx
0x1800cebd7  jz      short loc_1800CEBE2
0x1800cebd9  mov     rcx, rbx; hdc
0x1800cebdc  call    cs:__imp_DeleteDC
0x1800cebe2  test    rsi, rsi
0x1800cebe5  jz      short loc_1800CEBF7
0x1800cebe7  mov     rcx, cs:hwnd; hWnd
0x1800cebee  mov     rdx, rsi; hDC
0x1800cebf1  call    cs:__imp_ReleaseDC
0x1800cebf7  mov     rcx, [rbp+57h+var_30]
0x1800cebfb  xor     rcx, rsp; StackCookie
0x1800cebfe  call    __security_check_cookie
0x1800cec03  lea     r11, [rsp+0B0h+var_20]
0x1800cec0b  mov     rbx, [r11+30h]
0x1800cec0f  mov     rsi, [r11+40h]
0x1800cec13  mov     rdi, [r11+48h]
0x1800cec17  mov     rsp, r11
0x1800cec1a  pop     r15
0x1800cec1c  pop     r14
0x1800cec1e  pop     r13
0x1800cec20  pop     r12
0x1800cec22  pop     rbp
0x1800cec23  retn
0x1800cec24  mov     eax, cs:dword_1803F38C4
0x1800cec2a  mov     r9d, cs:w; cx
0x1800cec31  mov     [rsp+0B0h+var_70], 0CC0020h; rop
0x1800cec39  and     [rsp+0B0h+var_78], 0
0x1800cec3e  and     [rsp+0B0h+var_80], 0
0x1800cec43  xor     r8d, r8d; y
0x1800cec46  xor     edx, edx; x
0x1800cec48  mov     rcx, rbx; hdc
0x1800cec4b  mov     qword ptr [rsp+0B0h+rop], rdi; hdcSrc
0x1800cec50  mov     [rsp+0B0h+h], eax; cy
0x1800cec54  call    cs:__imp_BitBlt
0x1800cec5a  mov     rdx, r15; h
0x1800cec5d  mov     rcx, rdi; hdc
0x1800cec60  call    cs:__imp_SelectObject
0x1800cec66  mov     rcx, rdi; hdc
0x1800cec69  call    cs:__imp_DeleteDC
0x1800cec6f  jmp     loc_1800CE9F4
```
