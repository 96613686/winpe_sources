# POPUPTIP::Size(tagSIZE *,tagRECT *,uint,uint)

- ea: `0x18025d614`
- end: `0x18025d9f6`
- name: `?Size@POPUPTIP@@QEAAXPEAUtagSIZE@@PEAUtagRECT@@II@Z`
- size: `994`
- prototype: `void __fastcall(POPUPTIP *__hidden this, struct tagSIZE *, struct tagRECT *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800f8200`
- `0x18025dbf4`

## callees

- `0x1800f6510`
- `0x180153d3c`
- `0x1801f4654`
- `0x1801f4838`
- `0x18025d614`
- `0x18025dda8`
- `0x180379520`

## import_xrefs

- `USER32!CallWindowProcA` at `0x18025d787`
- `USER32!CallWindowProcA` at `0x18025d7ae`
- `USER32!CallWindowProcA` at `0x18025d7d5`
- `USER32!CallWindowProcA` at `0x18025d787`
- `USER32!CallWindowProcA` at `0x18025d7ae`
- `USER32!CallWindowProcA` at `0x18025d7d5`
- `USER32!ClientToScreen` at `0x18025d6b1`
- `USER32!ClientToScreen` at `0x18025d937`
- `USER32!ClientToScreen` at `0x18025d6b1`
- `USER32!ClientToScreen` at `0x18025d937`
- `USER32!MoveWindow` at `0x18025d760`
- `USER32!MoveWindow` at `0x18025d821`
- `USER32!MoveWindow` at `0x18025d991`
- `USER32!MoveWindow` at `0x18025d760`
- `USER32!MoveWindow` at `0x18025d821`
- `USER32!MoveWindow` at `0x18025d991`

## pseudocode

```c
void __fastcall POPUPTIP::Size(
        POPUPTIP *this,
        struct tagSIZE *a2,
        struct tagRECT *a3,
        unsigned int a4,
        unsigned int a5)
{
  HWND v5; // rax
  LONG nWidth; // [rsp+30h] [rbp-60h]
  int nWidtha; // [rsp+30h] [rbp-60h]
  int v8; // [rsp+34h] [rbp-5Ch]
  __int64 v9; // [rsp+38h] [rbp-58h] BYREF
  struct tagPOINT v10; // [rsp+40h] [rbp-50h] BYREF
  int v11; // [rsp+48h] [rbp-48h]
  LONG x; // [rsp+4Ch] [rbp-44h]
  struct tagPOINT Point; // [rsp+50h] [rbp-40h] BYREF
  int v14; // [rsp+58h] [rbp-38h] BYREF
  struct tagRECT *v15; // [rsp+60h] [rbp-30h]
  char *v16; // [rsp+68h] [rbp-28h]
  int v17; // [rsp+70h] [rbp-20h] BYREF
  _BYTE v18[4]; // [rsp+74h] [rbp-1Ch] BYREF
  struct tagRECT v19; // [rsp+78h] [rbp-18h] BYREF
  struct tagRECT *v22; // [rsp+B0h] [rbp+20h]

  v22 = a3;
  nWidth = -100000;
  if ( !a3 )
  {
    Point.x = CPANE::XFromIch(*((_QWORD *)this + 4), a5, a4, 0);
    Point.y = CPANE::YFromLn(*((CPANE **)this + 4), a5 + 1);
    v16 = (char *)CodePaneProvider::GetCodePane(*((CodePaneProvider **)this + 4)) + 8;
    v5 = (HWND)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v16 + 32LL))(v16);
    ClientToScreen(v5, &Point);
    v22 = &v19;
    ScreenWorkingRectFromPoint(&Point, &v19);
  }
  v15 = v22;
  v11 = 3 * (v22->right - v22->left) / 5;
  v8 = v22->right - *((_DWORD *)this + 19);
  if ( v8 >= 300 )
  {
    if ( v8 > v11 )
      v8 = v11;
  }
  else
  {
    v8 = 300;
  }
  MoveWindow(*((HWND *)this + 6), 4, 1, v8 - 8, 10, 0);
  CallWindowProcA((WNDPROC)g_lpfnPopupTipRtfWndProc, *((HWND *)this + 6), 0x445u, 0, 0x40000);
  CallWindowProcA((WNDPROC)g_lpfnPopupTipRtfWndProc, *((HWND *)this + 6), 0x441u, 0, 0);
  CallWindowProcA((WNDPROC)g_lpfnPopupTipRtfWndProc, *((HWND *)this + 6), 0x445u, 0, 0);
  MoveWindow(
    *((HWND *)this + 6),
    *((_DWORD *)this + 3),
    *((_DWORD *)this + 4),
    *((_DWORD *)this + 5) - *((_DWORD *)this + 3),
    *((_DWORD *)this + 6) - *((_DWORD *)this + 4),
    0);
  (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64 *))(**((_QWORD **)this + 7) + 192LL))(
    *((_QWORD *)this + 7),
    3221225473LL,
    0x3FFFFFFF,
    &v9);
  (*(void (__fastcall **)(__int64, __int64, int *, _BYTE *))(*(_QWORD *)v9 + 432LL))(v9, 32, &v17, v18);
  do
  {
    if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct tagPOINT *, LONG *))(*(_QWORD *)v9 + 432LL))(
           v9,
           2,
           &v10,
           &v10.y) == 1 )
      (*(void (__fastcall **)(__int64, _QWORD, struct tagPOINT *, LONG *))(*(_QWORD *)v9 + 432LL))(v9, 0, &v10, &v10.y);
    (*(void (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v9 + 296LL))(v9, 5, 0xFFFFFFFFLL, &v14);
    if ( nWidth <= v10.x )
      x = v10.x;
    else
      x = nWidth;
    nWidth = x;
  }
  while ( v14 );
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10.y = 0;
  v10.x = 0;
  ClientToScreen(*((HWND *)this + 6), &v10);
  nWidtha = nWidth - (4 * v10.x - 3 * v17);
  MoveWindow(
    *((HWND *)this + 6),
    *((_DWORD *)this + 3),
    *((_DWORD *)this + 4),
    nWidtha,
    *((_DWORD *)this + 6) - *((_DWORD *)this + 4),
    0);
  POPUPTIP::DeferWindowSize(this, nWidtha + 8, *((_DWORD *)this + 6) - *((_DWORD *)this + 4) + 2);
  if ( a2 )
  {
    a2->cx = *((_DWORD *)this + 21);
    a2->cy = *((_DWORD *)this + 22);
  }
}

```

## disassembly

```asm
0x18025d614  mov     [rsp-8+arg_18], r9d
0x18025d619  mov     [rsp-8+arg_10], r8
0x18025d61e  mov     [rsp-8+arg_8], rdx
0x18025d623  mov     [rsp-8+arg_0], rcx
0x18025d628  push    rbp
0x18025d629  mov     rbp, rsp
0x18025d62c  sub     rsp, 90h
0x18025d633  mov     rax, cs:__security_cookie
0x18025d63a  xor     rax, rsp
0x18025d63d  mov     [rbp+var_8], rax
0x18025d641  mov     [rsp+90h+nWidth], 0FFFE7960h
0x18025d649  cmp     [rbp+arg_10], 0
0x18025d64e  jnz     short loc_18025D6CF
0x18025d650  xor     r9d, r9d
0x18025d653  mov     r8d, [rbp+arg_18]
0x18025d657  mov     edx, [rbp+arg_20]
0x18025d65a  mov     rax, [rbp+arg_0]
0x18025d65e  mov     rcx, [rax+20h]
0x18025d662  call    ?XFromIch@CPANE@@QEAAHIIW4SPACE_MODE@@@Z; CPANE::XFromIch(uint,uint,SPACE_MODE)
0x18025d667  mov     [rsp+90h+Point.x], eax
0x18025d66b  mov     eax, [rbp+arg_20]
0x18025d66e  inc     eax
0x18025d670  mov     edx, eax; unsigned int
0x18025d672  mov     rax, [rbp+arg_0]
0x18025d676  mov     rcx, [rax+20h]; this
0x18025d67a  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18025d67f  mov     [rsp+90h+Point.y], eax
0x18025d683  mov     rax, [rbp+arg_0]
0x18025d687  mov     rcx, [rax+20h]; this
0x18025d68b  call    ?GetCodePane@CodePaneProvider@@QEAAPEAVCPANE@@XZ; CodePaneProvider::GetCodePane(void)
0x18025d690  add     rax, 8
0x18025d694  mov     [rsp+90h+var_28], rax
0x18025d699  mov     rax, [rsp+90h+var_28]
0x18025d69e  mov     rax, [rax]
0x18025d6a1  mov     rcx, [rsp+90h+var_28]
0x18025d6a6  call    qword ptr [rax+20h]
0x18025d6a9  lea     rdx, [rsp+90h+Point]; lpPoint
0x18025d6ae  mov     rcx, rax; hWnd
0x18025d6b1  call    cs:__imp_ClientToScreen
0x18025d6b7  lea     rax, [rsp+90h+var_18]
0x18025d6bc  mov     [rbp+arg_10], rax
0x18025d6c0  lea     rdx, [rsp+90h+var_18]; struct tagRECT *
0x18025d6c5  lea     rcx, [rsp+90h+Point]; struct tagPOINT *
0x18025d6ca  call    ?ScreenWorkingRectFromPoint@@YAXAEBUtagPOINT@@AEAUtagRECT@@@Z; ScreenWorkingRectFromPoint(tagPOINT const &,tagRECT &)
0x18025d6cf  mov     rax, [rbp+arg_10]
0x18025d6d3  mov     [rsp+90h+var_30], rax
0x18025d6d8  mov     rax, [rsp+90h+var_30]
0x18025d6dd  mov     rcx, [rsp+90h+var_30]
0x18025d6e2  mov     ecx, [rcx]
0x18025d6e4  mov     eax, [rax+8]
0x18025d6e7  sub     eax, ecx
0x18025d6e9  imul    eax, 3
0x18025d6ec  cdq
0x18025d6ed  mov     ecx, 5
0x18025d6f2  idiv    ecx
0x18025d6f4  mov     [rsp+90h+var_48], eax
0x18025d6f8  mov     rax, [rsp+90h+var_30]
0x18025d6fd  mov     rcx, [rbp+arg_0]
0x18025d701  mov     ecx, [rcx+4Ch]
0x18025d704  mov     eax, [rax+8]
0x18025d707  sub     eax, ecx
0x18025d709  mov     [rsp+90h+var_5C], eax
0x18025d70d  cmp     [rsp+90h+var_5C], 12Ch
0x18025d715  jge     short loc_18025D721
0x18025d717  mov     [rsp+90h+var_5C], 12Ch
0x18025d71f  jmp     short loc_18025D733
0x18025d721  mov     eax, [rsp+90h+var_48]
0x18025d725  cmp     [rsp+90h+var_5C], eax
0x18025d729  jle     short loc_18025D733
0x18025d72b  mov     eax, [rsp+90h+var_48]
0x18025d72f  mov     [rsp+90h+var_5C], eax
0x18025d733  mov     eax, [rsp+90h+var_5C]
0x18025d737  sub     eax, 8
0x18025d73a  mov     [rsp+90h+bRepaint], 0; bRepaint
0x18025d742  mov     [rsp+90h+nHeight], 0Ah; nHeight
0x18025d74a  mov     r9d, eax; nWidth
0x18025d74d  mov     r8d, 1; Y
0x18025d753  mov     edx, 4; X
0x18025d758  mov     rax, [rbp+arg_0]
0x18025d75c  mov     rcx, [rax+30h]; hWnd
0x18025d760  call    cs:__imp_MoveWindow
0x18025d766  mov     qword ptr [rsp+90h+nHeight], 40000h; lParam
0x18025d76f  xor     r9d, r9d; wParam
0x18025d772  mov     r8d, 445h; Msg
0x18025d778  mov     rax, [rbp+arg_0]
0x18025d77c  mov     rdx, [rax+30h]; hWnd
0x18025d780  mov     rcx, cs:?g_lpfnPopupTipRtfWndProc@@3P6A_JPEAUHWND__@@I_K_J@ZEA; lpPrevWndFunc
0x18025d787  call    cs:__imp_CallWindowProcA
0x18025d78d  mov     qword ptr [rsp+90h+nHeight], 0; lParam
0x18025d796  xor     r9d, r9d; wParam
0x18025d799  mov     r8d, 441h; Msg
0x18025d79f  mov     rax, [rbp+arg_0]
0x18025d7a3  mov     rdx, [rax+30h]; hWnd
0x18025d7a7  mov     rcx, cs:?g_lpfnPopupTipRtfWndProc@@3P6A_JPEAUHWND__@@I_K_J@ZEA; lpPrevWndFunc
0x18025d7ae  call    cs:__imp_CallWindowProcA
0x18025d7b4  mov     qword ptr [rsp+90h+nHeight], 0; lParam
0x18025d7bd  xor     r9d, r9d; wParam
0x18025d7c0  mov     r8d, 445h; Msg
0x18025d7c6  mov     rax, [rbp+arg_0]
0x18025d7ca  mov     rdx, [rax+30h]; hWnd
0x18025d7ce  mov     rcx, cs:?g_lpfnPopupTipRtfWndProc@@3P6A_JPEAUHWND__@@I_K_J@ZEA; lpPrevWndFunc
0x18025d7d5  call    cs:__imp_CallWindowProcA
0x18025d7db  mov     rax, [rbp+arg_0]
0x18025d7df  mov     rcx, [rbp+arg_0]
0x18025d7e3  mov     ecx, [rcx+10h]
0x18025d7e6  mov     eax, [rax+18h]
0x18025d7e9  sub     eax, ecx
0x18025d7eb  mov     rcx, [rbp+arg_0]
0x18025d7ef  mov     rdx, [rbp+arg_0]
0x18025d7f3  mov     edx, [rdx+0Ch]
0x18025d7f6  mov     ecx, [rcx+14h]
0x18025d7f9  sub     ecx, edx
0x18025d7fb  mov     [rsp+90h+bRepaint], 0; bRepaint
0x18025d803  mov     [rsp+90h+nHeight], eax; nHeight
0x18025d807  mov     r9d, ecx; nWidth
0x18025d80a  mov     rax, [rbp+arg_0]
0x18025d80e  mov     r8d, [rax+10h]; Y
0x18025d812  mov     rax, [rbp+arg_0]
0x18025d816  mov     edx, [rax+0Ch]; X
0x18025d819  mov     rax, [rbp+arg_0]
0x18025d81d  mov     rcx, [rax+30h]; hWnd
0x18025d821  call    cs:__imp_MoveWindow
0x18025d827  mov     rax, [rbp+arg_0]
0x18025d82b  mov     rax, [rax+38h]
0x18025d82f  mov     rcx, [rbp+arg_0]
0x18025d833  mov     rcx, [rcx+38h]
0x18025d837  mov     rax, [rax]
0x18025d83a  lea     r9, [rsp+90h+var_58]
0x18025d83f  mov     r8d, 3FFFFFFFh
0x18025d845  mov     edx, 0C0000001h
0x18025d84a  call    qword ptr [rax+0C0h]
0x18025d850  mov     rax, [rsp+90h+var_58]
0x18025d855  mov     rax, [rax]
0x18025d858  lea     r9, [rsp+90h+var_1C]
0x18025d85d  lea     r8, [rsp+90h+var_20]
0x18025d862  mov     edx, 20h ; ' '
0x18025d867  mov     rcx, [rsp+90h+var_58]
0x18025d86c  call    qword ptr [rax+1B0h]
0x18025d872  mov     rax, [rsp+90h+var_58]
0x18025d877  mov     rax, [rax]
0x18025d87a  lea     r9, [rsp+90h+var_50.y]
0x18025d87f  lea     r8, [rsp+90h+var_50]
0x18025d884  mov     edx, 2
0x18025d889  mov     rcx, [rsp+90h+var_58]
0x18025d88e  call    qword ptr [rax+1B0h]
0x18025d894  cmp     eax, 1
0x18025d897  jnz     short loc_18025D8B8
0x18025d899  mov     rax, [rsp+90h+var_58]
0x18025d89e  mov     rax, [rax]
0x18025d8a1  lea     r9, [rsp+90h+var_50.y]
0x18025d8a6  lea     r8, [rsp+90h+var_50]
0x18025d8ab  xor     edx, edx
0x18025d8ad  mov     rcx, [rsp+90h+var_58]
0x18025d8b2  call    qword ptr [rax+1B0h]
0x18025d8b8  mov     rax, [rsp+90h+var_58]
0x18025d8bd  mov     rax, [rax]
0x18025d8c0  lea     r9, [rsp+90h+var_38]
0x18025d8c5  mov     r8d, 0FFFFFFFFh
0x18025d8cb  mov     edx, 5
0x18025d8d0  mov     rcx, [rsp+90h+var_58]
0x18025d8d5  call    qword ptr [rax+128h]
0x18025d8db  mov     eax, [rsp+90h+var_50.x]
0x18025d8df  cmp     [rsp+90h+nWidth], eax
0x18025d8e3  jle     short loc_18025D8EF
0x18025d8e5  mov     eax, [rsp+90h+nWidth]
0x18025d8e9  mov     [rsp+90h+var_44], eax
0x18025d8ed  jmp     short loc_18025D8F7
0x18025d8ef  mov     eax, [rsp+90h+var_50.x]
0x18025d8f3  mov     [rsp+90h+var_44], eax
0x18025d8f7  mov     eax, [rsp+90h+var_44]
0x18025d8fb  mov     [rsp+90h+nWidth], eax
0x18025d8ff  cmp     [rsp+90h+var_38], 0
0x18025d904  jnz     loc_18025D872
0x18025d90a  mov     rax, [rsp+90h+var_58]
0x18025d90f  mov     rax, [rax]
0x18025d912  mov     rcx, [rsp+90h+var_58]
0x18025d917  call    qword ptr [rax+10h]
0x18025d91a  mov     [rsp+90h+var_50.y], 0
0x18025d922  mov     eax, [rsp+90h+var_50.y]
0x18025d926  mov     [rsp+90h+var_50.x], eax
0x18025d92a  lea     rdx, [rsp+90h+var_50]; lpPoint
0x18025d92f  mov     rax, [rbp+arg_0]
0x18025d933  mov     rcx, [rax+30h]; hWnd
0x18025d937  call    cs:__imp_ClientToScreen
0x18025d93d  mov     eax, [rsp+90h+var_50.x]
0x18025d941  shl     eax, 2
0x18025d944  mov     ecx, [rsp+90h+var_20]
0x18025d948  imul    ecx, 3
0x18025d94b  sub     eax, ecx
0x18025d94d  mov     ecx, [rsp+90h+nWidth]
0x18025d951  sub     ecx, eax
0x18025d953  mov     eax, ecx
0x18025d955  mov     [rsp+90h+nWidth], eax
0x18025d959  mov     rax, [rbp+arg_0]
0x18025d95d  mov     rcx, [rbp+arg_0]
0x18025d961  mov     ecx, [rcx+10h]
0x18025d964  mov     eax, [rax+18h]
0x18025d967  sub     eax, ecx
0x18025d969  mov     [rsp+90h+bRepaint], 0; bRepaint
0x18025d971  mov     [rsp+90h+nHeight], eax; nHeight
0x18025d975  mov     r9d, [rsp+90h+nWidth]; nWidth
0x18025d97a  mov     rax, [rbp+arg_0]
0x18025d97e  mov     r8d, [rax+10h]; Y
0x18025d982  mov     rax, [rbp+arg_0]
0x18025d986  mov     edx, [rax+0Ch]; X
0x18025d989  mov     rax, [rbp+arg_0]
0x18025d98d  mov     rcx, [rax+30h]; hWnd
0x18025d991  call    cs:__imp_MoveWindow
0x18025d997  mov     rax, [rbp+arg_0]
0x18025d99b  mov     rcx, [rbp+arg_0]
0x18025d99f  mov     ecx, [rcx+10h]
0x18025d9a2  mov     eax, [rax+18h]
0x18025d9a5  sub     eax, ecx
0x18025d9a7  add     eax, 2
0x18025d9aa  mov     ecx, [rsp+90h+nWidth]
0x18025d9ae  add     ecx, 8
0x18025d9b1  mov     r8d, eax; int
0x18025d9b4  mov     edx, ecx; int
0x18025d9b6  mov     rcx, [rbp+arg_0]; this
0x18025d9ba  call    ?DeferWindowSize@POPUPTIP@@AEAAXHH@Z; POPUPTIP::DeferWindowSize(int,int)
0x18025d9bf  cmp     [rbp+arg_8], 0
0x18025d9c4  jz      short loc_18025D9E1
0x18025d9c6  mov     rax, [rbp+arg_8]
0x18025d9ca  mov     rcx, [rbp+arg_0]
0x18025d9ce  mov     ecx, [rcx+54h]
0x18025d9d1  mov     [rax], ecx
0x18025d9d3  mov     rax, [rbp+arg_8]
0x18025d9d7  mov     rcx, [rbp+arg_0]
0x18025d9db  mov     ecx, [rcx+58h]
0x18025d9de  mov     [rax+4], ecx
0x18025d9e1  mov     rcx, [rbp+var_8]
0x18025d9e5  xor     rcx, rsp; StackCookie
0x18025d9e8  call    __security_check_cookie
0x18025d9ed  add     rsp, 90h
0x18025d9f4  pop     rbp
0x18025d9f5  retn
```
