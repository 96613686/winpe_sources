# CWispInk::GetDataAsBitmap(tagFORMATETC *,tagSTGMEDIUM *,int)

- ea: `0x1800977dc`
- end: `0x180097a08`
- name: `?GetDataAsBitmap@CWispInk@@IEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@H@Z`
- size: `556`
- prototype: `__int64 __fastcall(CWispInk *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180097f20`

## callees

- `0x18008c684`
- `0x1800977dc`
- `0x18009828c`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800978ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800979ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800978ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800979ae`
- `USER32!InflateRect` at `0x180097867`
- `USER32!InflateRect` at `0x180097867`
- `USER32!GetDC` at `0x180097835`
- `USER32!GetDC` at `0x180097835`
- `USER32!ReleaseDC` at `0x18009788c`
- `USER32!ReleaseDC` at `0x1800979cd`
- `USER32!ReleaseDC` at `0x18009788c`
- `USER32!ReleaseDC` at `0x1800979cd`
- `GDI32!SetMapMode` at `0x1800978e0`
- `GDI32!SetMapMode` at `0x1800978e0`
- `GDI32!Rectangle` at `0x18009793d`
- `GDI32!Rectangle` at `0x18009793d`
- `GDI32!CreateCompatibleBitmap` at `0x18009787e`
- `GDI32!CreateCompatibleBitmap` at `0x18009787e`
- `GDI32!GetStockObject` at `0x180097900`
- `GDI32!GetStockObject` at `0x180097916`
- `GDI32!GetStockObject` at `0x180097900`
- `GDI32!GetStockObject` at `0x180097916`
- `GDI32!DeleteDC` at `0x1800979db`
- `GDI32!DeleteDC` at `0x1800979db`
- `GDI32!SetWindowOrgEx` at `0x1800978f3`
- `GDI32!SetWindowOrgEx` at `0x1800978f3`
- `GDI32!CreateCompatibleDC` at `0x180097841`
- `GDI32!CreateCompatibleDC` at `0x180097841`
- `GDI32!SelectObject` at `0x1800978cf`
- `GDI32!SelectObject` at `0x18009790c`
- `GDI32!SelectObject` at `0x180097922`
- `GDI32!SelectObject` at `0x180097985`
- `GDI32!SelectObject` at `0x1800978cf`
- `GDI32!SelectObject` at `0x18009790c`
- `GDI32!SelectObject` at `0x180097922`
- `GDI32!SelectObject` at `0x180097985`

## pseudocode

```c
__int64 __fastcall CWispInk::GetDataAsBitmap(CWispInk *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3, int a4)
{
  HDC DC; // r14
  HDC CompatibleDC; // rdi
  HBITMAP CompatibleBitmap; // rbx
  signed int v12; // eax
  signed int v13; // ebx
  HGDIOBJ v14; // rsi
  HGDIOBJ StockObject; // rax
  HGDIOBJ v16; // rax
  signed int LastError; // eax
  struct tagRECT rc; // [rsp+30h] [rbp-30h] BYREF
  struct tagRECT v19; // [rsp+40h] [rbp-20h] BYREF

  CWispInk::GetInkRect(this, &rc, 0, 1, 1);
  if ( (a2->tymed & 0x10) == 0 )
    return 2147745892LL;
  DC = GetDC(0);
  CompatibleDC = CreateCompatibleDC(DC);
  if ( !CompatibleDC )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  if ( a4 )
  {
    v13 = a3->tymed != 16 ? 0x80040069 : 0;
    if ( !a3->hBitmap )
    {
      v13 = -2147024809;
      goto LABEL_17;
    }
  }
  else
  {
    InflateRect(&rc, 2, 2);
    CompatibleBitmap = CreateCompatibleBitmap(DC, rc.right - rc.left, rc.bottom - rc.top);
    ReleaseDC(0, DC);
    DC = 0;
    if ( CompatibleBitmap )
    {
      *(_QWORD *)&a3->tymed = 16;
      a3->pUnkForRelease = 0;
      a3->hBitmap = CompatibleBitmap;
LABEL_10:
      v14 = SelectObject(CompatibleDC, a3->hBitmap);
      SetMapMode(CompatibleDC, 1);
      SetWindowOrgEx(CompatibleDC, rc.left, rc.top, 0);
      if ( !a4 )
      {
        StockObject = GetStockObject(0);
        SelectObject(CompatibleDC, StockObject);
        v16 = GetStockObject(6);
        SelectObject(CompatibleDC, v16);
        Rectangle(CompatibleDC, rc.left, rc.top, rc.right, rc.bottom);
      }
      rc = *CWispInk::GetInkRect(this, &v19, 1, 1, 0);
      v13 = CWispInk::DrawInRect(this, CompatibleDC, 0, &rc, 0);
      SelectObject(CompatibleDC, v14);
      goto LABEL_17;
    }
    v12 = GetLastError();
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
  }
  if ( v13 >= 0 )
    goto LABEL_10;
LABEL_17:
  if ( DC )
    ReleaseDC(0, DC);
  if ( CompatibleDC )
    DeleteDC(CompatibleDC);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800977dc  mov     [rsp-28h+arg_8], rbx
0x1800977e1  mov     [rsp-28h+arg_18], rsi
0x1800977e6  push    rbp
0x1800977e7  push    rdi
0x1800977e8  push    r12
0x1800977ea  push    r14
0x1800977ec  push    r15
0x1800977ee  mov     rbp, rsp
0x1800977f1  sub     rsp, 60h
0x1800977f5  mov     rax, cs:__security_cookie
0x1800977fc  xor     rax, rsp
0x1800977ff  mov     [rbp+var_10], rax
0x180097803  mov     r15d, r9d
0x180097806  mov     byte ptr [rsp+60h+bottom], 1; bool
0x18009780b  mov     rsi, r8
0x18009780e  mov     rbx, rdx
0x180097811  mov     r9b, 1; bool
0x180097814  lea     rdx, [rbp+rc]; lprc
0x180097818  xor     r8d, r8d; bool
0x18009781b  mov     r12, rcx
0x18009781e  call    ?GetInkRect@CWispInk@@IEBA?AUtagRECT@@_N00@Z; CWispInk::GetInkRect(bool,bool,bool)
0x180097823  test    byte ptr [rbx+18h], 10h
0x180097827  jnz     short loc_180097833
0x180097829  mov     eax, 80040064h
0x18009782e  jmp     loc_1800979E3
0x180097833  xor     ecx, ecx; hWnd
0x180097835  call    cs:__imp_GetDC
0x18009783b  mov     rcx, rax; hdc
0x18009783e  mov     r14, rax
0x180097841  call    cs:__imp_CreateCompatibleDC
0x180097847  mov     rdi, rax
0x18009784a  test    rax, rax
0x18009784d  jz      loc_1800979AE
0x180097853  test    r15d, r15d
0x180097856  jnz     loc_18009798D
0x18009785c  lea     edx, [r15+2]; dx
0x180097860  mov     r8d, edx; dy
0x180097863  lea     rcx, [rbp+rc]; lprc
0x180097867  call    cs:__imp_InflateRect
0x18009786d  mov     r8d, [rbp+rc.bottom]
0x180097871  mov     rcx, r14; hdc
0x180097874  mov     edx, [rbp+rc.right]
0x180097877  sub     r8d, [rbp+rc.top]; cy
0x18009787b  sub     edx, [rbp+rc.left]; cx
0x18009787e  call    cs:__imp_CreateCompatibleBitmap
0x180097884  mov     rdx, r14; hDC
0x180097887  xor     ecx, ecx; hWnd
0x180097889  mov     rbx, rax
0x18009788c  call    cs:__imp_ReleaseDC
0x180097892  xor     r14d, r14d
0x180097895  test    rbx, rbx
0x180097898  jz      short loc_1800978AB
0x18009789a  mov     qword ptr [rsi], 10h
0x1800978a1  mov     [rsi+10h], r14
0x1800978a5  mov     [rsi+8], rbx
0x1800978a9  jmp     short loc_1800978C8
0x1800978ab  call    cs:__imp_GetLastError
0x1800978b1  mov     ebx, eax
0x1800978b3  test    eax, eax
0x1800978b5  jle     short loc_1800978C0
0x1800978b7  movzx   ebx, ax
0x1800978ba  or      ebx, 80070000h
0x1800978c0  test    ebx, ebx
0x1800978c2  js      loc_1800979C3
0x1800978c8  mov     rdx, [rsi+8]; h
0x1800978cc  mov     rcx, rdi; hdc
0x1800978cf  call    cs:__imp_SelectObject
0x1800978d5  mov     edx, 1; iMode
0x1800978da  mov     rcx, rdi; hdc
0x1800978dd  mov     rsi, rax
0x1800978e0  call    cs:__imp_SetMapMode
0x1800978e6  mov     r8d, [rbp+rc.top]; y
0x1800978ea  xor     r9d, r9d; lppt
0x1800978ed  mov     edx, [rbp+rc.left]; x
0x1800978f0  mov     rcx, rdi; hdc
0x1800978f3  call    cs:__imp_SetWindowOrgEx
0x1800978f9  test    r15d, r15d
0x1800978fc  jnz     short loc_180097943
0x1800978fe  xor     ecx, ecx; i
0x180097900  call    cs:__imp_GetStockObject
0x180097906  mov     rdx, rax; h
0x180097909  mov     rcx, rdi; hdc
0x18009790c  call    cs:__imp_SelectObject
0x180097912  lea     ecx, [r15+6]; i
0x180097916  call    cs:__imp_GetStockObject
0x18009791c  mov     rdx, rax; h
0x18009791f  mov     rcx, rdi; hdc
0x180097922  call    cs:__imp_SelectObject
0x180097928  mov     eax, [rbp+rc.bottom]
0x18009792b  mov     rcx, rdi; hdc
0x18009792e  mov     r9d, [rbp+rc.right]; right
0x180097932  mov     r8d, [rbp+rc.top]; top
0x180097936  mov     edx, [rbp+rc.left]; left
0x180097939  mov     [rsp+60h+bottom], eax; bottom
0x18009793d  call    cs:__imp_Rectangle
0x180097943  mov     r9b, 1; bool
0x180097946  mov     byte ptr [rsp+60h+bottom], 0; bool
0x18009794b  mov     r8b, r9b; bool
0x18009794e  lea     rdx, [rbp+var_20]; lprc
0x180097952  mov     rcx, r12; this
0x180097955  call    ?GetInkRect@CWispInk@@IEBA?AUtagRECT@@_N00@Z; CWispInk::GetInkRect(bool,bool,bool)
0x18009795a  lea     r9, [rbp+rc]; struct tagRECT *
0x18009795e  mov     qword ptr [rsp+60h+bottom], 0; struct CStrokeSetImpl *
0x180097967  xor     r8d, r8d; lprc
0x18009796a  mov     rdx, rdi; HDC
0x18009796d  mov     rcx, r12; this
0x180097970  movups  xmm0, xmmword ptr [rax]
0x180097973  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x180097978  call    ?DrawInRect@CWispInk@@QEAAJPEAUHDC__@@PEBUtagRECT@@1PEBVCStrokeSetImpl@@@Z; CWispInk::DrawInRect(HDC__ *,tagRECT const *,tagRECT const *,CStrokeSetImpl const *)
0x18009797d  mov     rdx, rsi; h
0x180097980  mov     rcx, rdi; hdc
0x180097983  mov     ebx, eax
0x180097985  call    cs:__imp_SelectObject
0x18009798b  jmp     short loc_1800979C3
0x18009798d  mov     eax, [rsi]
0x18009798f  sub     eax, 10h
0x180097992  neg     eax
0x180097994  sbb     ebx, ebx
0x180097996  and     ebx, 80040069h
0x18009799c  cmp     qword ptr [rsi+8], 0
0x1800979a1  jnz     loc_1800978C0
0x1800979a7  mov     ebx, 80070057h
0x1800979ac  jmp     short loc_1800979C3
0x1800979ae  call    cs:__imp_GetLastError
0x1800979b4  mov     ebx, eax
0x1800979b6  test    eax, eax
0x1800979b8  jle     short loc_1800979C3
0x1800979ba  movzx   ebx, ax
0x1800979bd  or      ebx, 80070000h
0x1800979c3  test    r14, r14
0x1800979c6  jz      short loc_1800979D3
0x1800979c8  mov     rdx, r14; hDC
0x1800979cb  xor     ecx, ecx; hWnd
0x1800979cd  call    cs:__imp_ReleaseDC
0x1800979d3  test    rdi, rdi
0x1800979d6  jz      short loc_1800979E1
0x1800979d8  mov     rcx, rdi; hdc
0x1800979db  call    cs:__imp_DeleteDC
0x1800979e1  mov     eax, ebx
0x1800979e3  mov     rcx, [rbp+var_10]
0x1800979e7  xor     rcx, rsp; StackCookie
0x1800979ea  call    __security_check_cookie
0x1800979ef  lea     r11, [rsp+60h+var_s0]
0x1800979f4  mov     rbx, [r11+38h]
0x1800979f8  mov     rsi, [r11+48h]
0x1800979fc  mov     rsp, r11
0x1800979ff  pop     r15
0x180097a01  pop     r14
0x180097a03  pop     r12
0x180097a05  pop     rdi
0x180097a06  pop     rbp
0x180097a07  retn
```
