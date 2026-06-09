# CWnd::CenterWindow(CWnd *)

- ea: `0x18002f090`
- end: `0x18002f2cc`
- name: `?CenterWindow@CWnd@@QEAAXPEAV1@@Z`
- size: `572`
- prototype: `void __fastcall(CWnd *__hidden this, struct CWnd *)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x180006a4c`
- `0x180059300`
- `0x18005a730`
- `0x180063140`
- `0x18008b5e0`
- `0x18008b620`

## callees

- `0x180007110`
- `0x180014a00`
- `0x180027800`
- `0x18002f090`
- `0x18002f2e0`
- `0x18002f3a0`
- `0x1800d1fe0`

## import_xrefs

- `USER32!GetWindowRect` at `0x18002f121`
- `USER32!GetWindowRect` at `0x18002f1b2`
- `USER32!GetWindowRect` at `0x18002f121`
- `USER32!GetWindowRect` at `0x18002f1b2`
- `USER32!GetWindowLongW` at `0x18002f140`
- `USER32!GetWindowLongW` at `0x18002f140`
- `USER32!GetWindow` at `0x18002f0f0`
- `USER32!GetWindow` at `0x18002f0f0`
- `USER32!SendMessageW` at `0x18002f10c`
- `USER32!SendMessageW` at `0x18002f10c`
- `USER32!GetParent` at `0x18002f0e3`
- `USER32!GetParent` at `0x18002f1e2`
- `USER32!GetParent` at `0x18002f0e3`
- `USER32!GetParent` at `0x18002f1e2`
- `USER32!GetClientRect` at `0x18002f1f2`
- `USER32!GetClientRect` at `0x18002f1ff`
- `USER32!GetClientRect` at `0x18002f1f2`
- `USER32!GetClientRect` at `0x18002f1ff`
- `USER32!CopyRect` at `0x18002f1a3`
- `USER32!CopyRect` at `0x18002f1d7`
- `USER32!CopyRect` at `0x18002f1a3`
- `USER32!CopyRect` at `0x18002f1d7`
- `USER32!MapWindowPoints` at `0x18002f212`
- `USER32!MapWindowPoints` at `0x18002f212`

## pseudocode

```c
void __fastcall CWnd::CenterWindow(CWnd *this, struct CWnd *a2)
{
  HWND *v4; // rsi
  unsigned int Style; // ebx
  HWND v6; // rdi
  int v7; // ebx
  HWND v8; // rcx
  HWND Parent; // rax
  LRESULT v10; // rax
  struct CWnd *MainWnd; // rax
  HWND v12; // rcx
  HMONITOR v13; // rax
  HMONITOR v14; // rax
  HWND v15; // rbx
  int v16; // r9d
  int v17; // r11d
  LONG left; // r8d
  LONG v19; // r10d
  LONG v20; // ecx
  LONG top; // r9d
  struct tagRECT v22; // [rsp+40h] [rbp-29h] BYREF
  struct tagRECT rcDst; // [rsp+50h] [rbp-19h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp-9h] BYREF
  tagMONITORINFO v25; // [rsp+70h] [rbp+7h] BYREF

  v4 = (HWND *)((char *)this + 64);
  Style = CWnd::GetStyle(this);
  if ( a2 )
  {
    v6 = (HWND)*((_QWORD *)a2 + 8);
    v7 = Style & 0x40000000;
  }
  else
  {
    v8 = *v4;
    v7 = Style & 0x40000000;
    if ( v7 )
      Parent = GetParent(v8);
    else
      Parent = GetWindow(v8, 4u);
    v6 = Parent;
    if ( Parent )
    {
      v10 = SendMessageW(Parent, 0x36Bu, 0, 0);
      if ( v10 )
        v6 = (HWND)v10;
    }
  }
  GetWindowRect(*v4, &Rect);
  if ( v7 )
  {
    v15 = GetParent(*v4);
    GetClientRect(v15, &v22);
    GetClientRect(v6, &rcDst);
    MapWindowPoints(v6, v15, (LPPOINT)&rcDst, 2u);
  }
  else
  {
    if ( v6 && (GetWindowLongW(v6, -16) & 0x30000000) != 0x10000000 )
      v6 = 0;
    memset(&v25, 0, sizeof(v25));
    v25.cbSize = 40;
    if ( v6 )
    {
      GetWindowRect(v6, &rcDst);
      v14 = xMonitorFromWindow(v6, 2u);
      xGetMonitorInfo(v14, &v25);
    }
    else
    {
      MainWnd = AfxGetMainWnd();
      if ( MainWnd )
        v12 = (HWND)*((_QWORD *)MainWnd + 8);
      else
        v12 = 0;
      v13 = xMonitorFromWindow(v12, 1u);
      xGetMonitorInfo(v13, &v25);
      CopyRect(&rcDst, &v25.rcWork);
    }
    CopyRect(&v22, &v25.rcWork);
  }
  v16 = Rect.right - Rect.left;
  v17 = Rect.bottom - Rect.top;
  left = v22.left;
  v19 = (rcDst.left + rcDst.right) / 2 - (Rect.right - Rect.left) / 2;
  v20 = (rcDst.top + rcDst.bottom) / 2 - (Rect.bottom - Rect.top) / 2;
  if ( v19 >= v22.left )
  {
    left = (rcDst.left + rcDst.right) / 2 - (Rect.right - Rect.left) / 2;
    if ( v19 + v16 > v22.right )
      left = v22.right - v16;
  }
  top = v22.top;
  if ( v20 >= v22.top )
  {
    top = (rcDst.top + rcDst.bottom) / 2 - (Rect.bottom - Rect.top) / 2;
    if ( v20 + v17 > v22.bottom )
      top = v22.bottom - v17;
  }
  CWnd::SetWindowPos(this, 0, left, top, -1, -1, 0x15u);
}

```

## disassembly

```asm
0x18002f090  mov     [rsp-8+arg_10], rbx
0x18002f095  push    rbp
0x18002f096  push    rsi
0x18002f097  push    rdi
0x18002f098  push    r14
0x18002f09a  push    r15
0x18002f09c  lea     rbp, [rsp-37h]
0x18002f0a1  sub     rsp, 0A0h
0x18002f0a8  mov     rax, cs:__security_cookie
0x18002f0af  xor     rax, rsp
0x18002f0b2  mov     [rbp+57h+var_28], rax
0x18002f0b6  mov     rdi, rdx
0x18002f0b9  mov     r14, rcx
0x18002f0bc  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x18002f0c1  lea     rsi, [r14+40h]
0x18002f0c5  mov     ebx, eax
0x18002f0c7  test    rdi, rdi
0x18002f0ca  jz      short loc_18002F0D8
0x18002f0cc  mov     rdi, [rdi+40h]
0x18002f0d0  and     ebx, 40000000h
0x18002f0d6  jmp     short loc_18002F11A
0x18002f0d8  mov     rcx, [rsi]; hWnd
0x18002f0db  and     ebx, 40000000h
0x18002f0e1  jz      short loc_18002F0EB
0x18002f0e3  call    cs:__imp_GetParent
0x18002f0e9  jmp     short loc_18002F0F6
0x18002f0eb  mov     edx, 4; uCmd
0x18002f0f0  call    cs:__imp_GetWindow
0x18002f0f6  mov     rdi, rax
0x18002f0f9  test    rax, rax
0x18002f0fc  jz      short loc_18002F11A
0x18002f0fe  xor     r9d, r9d; lParam
0x18002f101  xor     r8d, r8d; wParam
0x18002f104  mov     edx, 36Bh; Msg
0x18002f109  mov     rcx, rax; hWnd
0x18002f10c  call    cs:__imp_SendMessageW
0x18002f112  test    rax, rax
0x18002f115  jz      short loc_18002F11A
0x18002f117  mov     rdi, rax
0x18002f11a  mov     rcx, [rsi]; hWnd
0x18002f11d  lea     rdx, [rbp+57h+Rect]; lpRect
0x18002f121  call    cs:__imp_GetWindowRect
0x18002f127  mov     r15d, 2
0x18002f12d  test    ebx, ebx
0x18002f12f  jnz     loc_18002F1DF
0x18002f135  test    rdi, rdi
0x18002f138  jz      short loc_18002F156
0x18002f13a  lea     edx, [rbx-10h]; nIndex
0x18002f13d  mov     rcx, rdi; hWnd
0x18002f140  call    cs:__imp_GetWindowLongW
0x18002f146  xor     ecx, ecx
0x18002f148  and     eax, 30000000h
0x18002f14d  cmp     eax, 10000000h
0x18002f152  cmovnz  rdi, rcx
0x18002f156  xorps   xmm0, xmm0
0x18002f159  xor     eax, eax
0x18002f15b  mov     qword ptr [rbp+57h+var_50.rcWork.bottom], rax
0x18002f15f  movups  xmmword ptr [rbp+57h+var_50.cbSize], xmm0
0x18002f163  mov     [rbp+57h+var_50.cbSize], 28h ; '('
0x18002f16a  movups  xmmword ptr [rbp+57h+var_50.rcMonitor.bottom], xmm0
0x18002f16e  test    rdi, rdi
0x18002f171  jnz     short loc_18002F1AB
0x18002f173  call    ?AfxGetMainWnd@@YAPEAVCWnd@@XZ; AfxGetMainWnd(void)
0x18002f178  test    rax, rax
0x18002f17b  jnz     short loc_18002F181
0x18002f17d  xor     ecx, ecx
0x18002f17f  jmp     short loc_18002F185
0x18002f181  mov     rcx, [rax+40h]; HWND
0x18002f185  mov     edx, 1; DWORD
0x18002f18a  call    xMonitorFromWindow
0x18002f18f  mov     rcx, rax; HMONITOR
0x18002f192  lea     rdx, [rbp+57h+var_50]; LPMONITORINFO
0x18002f196  call    xGetMonitorInfo
0x18002f19b  lea     rdx, [rbp+57h+var_50.rcWork]; lprcSrc
0x18002f19f  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18002f1a3  call    cs:__imp_CopyRect
0x18002f1a9  jmp     short loc_18002F1CF
0x18002f1ab  lea     rdx, [rbp+57h+rcDst]; lpRect
0x18002f1af  mov     rcx, rdi; hWnd
0x18002f1b2  call    cs:__imp_GetWindowRect
0x18002f1b8  mov     edx, r15d; DWORD
0x18002f1bb  mov     rcx, rdi; HWND
0x18002f1be  call    xMonitorFromWindow
0x18002f1c3  mov     rcx, rax; HMONITOR
0x18002f1c6  lea     rdx, [rbp+57h+var_50]; LPMONITORINFO
0x18002f1ca  call    xGetMonitorInfo
0x18002f1cf  lea     rdx, [rbp+57h+var_50.rcWork]; lprcSrc
0x18002f1d3  lea     rcx, [rbp+57h+var_80]; lprcDst
0x18002f1d7  call    cs:__imp_CopyRect
0x18002f1dd  jmp     short loc_18002F218
0x18002f1df  mov     rcx, [rsi]; hWnd
0x18002f1e2  call    cs:__imp_GetParent
0x18002f1e8  mov     rcx, rax; hWnd
0x18002f1eb  lea     rdx, [rbp+57h+var_80]; lpRect
0x18002f1ef  mov     rbx, rax
0x18002f1f2  call    cs:__imp_GetClientRect
0x18002f1f8  lea     rdx, [rbp+57h+rcDst]; lpRect
0x18002f1fc  mov     rcx, rdi; hWnd
0x18002f1ff  call    cs:__imp_GetClientRect
0x18002f205  mov     r9d, r15d; cPoints
0x18002f208  lea     r8, [rbp+57h+rcDst]; lpPoints
0x18002f20c  mov     rdx, rbx; hWndTo
0x18002f20f  mov     rcx, rdi; hWndFrom
0x18002f212  call    cs:__imp_MapWindowPoints
0x18002f218  mov     eax, [rbp+57h+rcDst.right]
0x18002f21b  add     eax, [rbp+57h+rcDst.left]
0x18002f21e  mov     r9d, [rbp+57h+Rect.right]
0x18002f222  cdq
0x18002f223  sub     r9d, [rbp+57h+Rect.left]
0x18002f227  mov     r11d, [rbp+57h+Rect.bottom]
0x18002f22b  sub     r11d, [rbp+57h+Rect.top]
0x18002f22f  mov     r8d, [rbp+57h+var_80.left]
0x18002f233  idiv    r15d
0x18002f236  mov     r10d, eax
0x18002f239  mov     eax, r9d
0x18002f23c  cdq
0x18002f23d  idiv    r15d
0x18002f240  sub     r10d, eax
0x18002f243  mov     eax, [rbp+57h+rcDst.bottom]
0x18002f246  add     eax, [rbp+57h+rcDst.top]
0x18002f249  cdq
0x18002f24a  idiv    r15d
0x18002f24d  mov     ecx, eax
0x18002f24f  mov     eax, r11d
0x18002f252  cdq
0x18002f253  idiv    r15d
0x18002f256  sub     ecx, eax
0x18002f258  cmp     r10d, r8d
0x18002f25b  jl      short loc_18002F270
0x18002f25d  lea     eax, [r10+r9]
0x18002f261  mov     r8d, r10d
0x18002f264  cmp     eax, [rbp+57h+var_80.right]
0x18002f267  jle     short loc_18002F270
0x18002f269  mov     r8d, [rbp+57h+var_80.right]
0x18002f26d  sub     r8d, r9d; int
0x18002f270  mov     r9d, [rbp+57h+var_80.top]
0x18002f274  cmp     ecx, r9d
0x18002f277  jl      short loc_18002F28C
0x18002f279  lea     eax, [rcx+r11]
0x18002f27d  mov     r9d, ecx
0x18002f280  cmp     eax, [rbp+57h+var_80.bottom]
0x18002f283  jle     short loc_18002F28C
0x18002f285  mov     r9d, [rbp+57h+var_80.bottom]
0x18002f289  sub     r9d, r11d; int
0x18002f28c  or      eax, 0FFFFFFFFh
0x18002f28f  mov     [rsp+0C0h+var_90], 15h; unsigned int
0x18002f297  mov     [rsp+0C0h+var_98], eax; int
0x18002f29b  xor     edx, edx; struct CWnd *
0x18002f29d  mov     rcx, r14; this
0x18002f2a0  mov     [rsp+0C0h+var_A0], eax; int
0x18002f2a4  call    ?SetWindowPos@CWnd@@QEAAHPEBV1@HHHHI@Z; CWnd::SetWindowPos(CWnd const *,int,int,int,int,uint)
0x18002f2a9  mov     rcx, [rbp+57h+var_28]
0x18002f2ad  xor     rcx, rsp; StackCookie
0x18002f2b0  call    __security_check_cookie
0x18002f2b5  mov     rbx, [rsp+0C0h+arg_10]
0x18002f2bd  add     rsp, 0A0h
0x18002f2c4  pop     r15
0x18002f2c6  pop     r14
0x18002f2c8  pop     rdi
0x18002f2c9  pop     rsi
0x18002f2ca  pop     rbp
0x18002f2cb  retn
```
