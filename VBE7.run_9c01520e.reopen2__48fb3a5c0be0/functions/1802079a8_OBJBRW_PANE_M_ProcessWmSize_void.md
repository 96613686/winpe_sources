# OBJBRW_PANE::M_ProcessWmSize(void)

- ea: `0x1802079a8`
- end: `0x180207c39`
- name: `?M_ProcessWmSize@OBJBRW_PANE@@QEAAXXZ`
- size: `657`
- prototype: `void __fastcall(OBJBRW_PANE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180206ddc`

## callees

- `0x1802079a8`
- `0x180207c40`
- `0x180379520`

## import_xrefs

- `USER32!SetWindowPos` at `0x180207a7b`
- `USER32!SetWindowPos` at `0x180207a7b`
- `USER32!GetClientRect` at `0x1802079d9`
- `USER32!GetClientRect` at `0x1802079d9`
- `USER32!SendMessageA` at `0x180207a40`
- `USER32!SendMessageA` at `0x180207b28`
- `USER32!SendMessageA` at `0x180207a40`
- `USER32!SendMessageA` at `0x180207b28`
- `USER32!InvalidateRect` at `0x180207ba8`
- `USER32!InvalidateRect` at `0x180207ba8`
- `USER32!InflateRect` at `0x180207be6`
- `USER32!InflateRect` at `0x180207be6`
- `USER32!MoveWindow` at `0x180207b92`
- `USER32!MoveWindow` at `0x180207c1e`
- `USER32!MoveWindow` at `0x180207b92`
- `USER32!MoveWindow` at `0x180207c1e`

## pseudocode

```c
void __fastcall OBJBRW_PANE::M_ProcessWmSize(OBJBRW_PANE *this)
{
  unsigned int i; // [rsp+40h] [rbp-E0h]
  int v2; // [rsp+44h] [rbp-DCh]
  int v3; // [rsp+48h] [rbp-D8h]
  LPARAM lParam[2]; // [rsp+50h] [rbp-D0h] BYREF
  char v5; // [rsp+60h] [rbp-C0h] BYREF
  HWND hWndInsertAfter; // [rsp+68h] [rbp-B8h]
  int X; // [rsp+70h] [rbp-B0h]
  int Y; // [rsp+74h] [rbp-ACh]
  int v9; // [rsp+78h] [rbp-A8h]
  int cy; // [rsp+7Ch] [rbp-A4h]
  int v11; // [rsp+80h] [rbp-A0h]
  struct tagRECT v12; // [rsp+88h] [rbp-98h]
  struct tagRECT v13; // [rsp+98h] [rbp-88h]
  int v14; // [rsp+B0h] [rbp-70h] BYREF
  int v15; // [rsp+B4h] [rbp-6Ch]
  struct tagRECT v16; // [rsp+F0h] [rbp-30h] BYREF
  struct tagRECT rc; // [rsp+100h] [rbp-20h] BYREF

  GetClientRect(*((HWND *)this + 4), (LPRECT)((char *)this + 68));
  v12 = *(struct tagRECT *)((char *)this + 68);
  v16 = v12;
  if ( !*((_DWORD *)this + 4) )
  {
    OBJBRW_PANE::M_GetSearchRect(this, &v16);
    lParam[0] = (LPARAM)&v16;
    lParam[1] = (LPARAM)&v5;
    SendMessageA(*((HWND *)this + 7), 0x1205u, 0, (LPARAM)lParam);
    SetWindowPos(*((HWND *)this + 7), hWndInsertAfter, X, Y, v9, cy, v11 | 0x40);
    v14 = 1;
    *((_DWORD *)this + 16) = 1;
    v3 = v16.right - v16.left;
    v2 = 0;
    for ( i = 0; i < 3; ++i )
    {
      if ( i == 2 )
      {
        v15 = v3 - v2 - 1;
      }
      else
      {
        v15 = (int)(float)(*((float *)this + i + 24) * (float)v3);
        v2 += v15;
      }
      SendMessageA(*((HWND *)this + 7), 0x1204u, (int)i, (LPARAM)&v14);
    }
    *((_DWORD *)this + 16) = 0;
  }
  if ( *((_QWORD *)this + 5) )
  {
    if ( *((_DWORD *)this + 4) )
      v16.top += dword_1803FF798;
    MoveWindow(*((HWND *)this + 5), v16.left, v16.top, v16.right - v16.left, v16.bottom - v16.top, 1);
    InvalidateRect(*((HWND *)this + 5), 0, 1);
  }
  if ( *((_QWORD *)this + 6) )
  {
    v13 = *(struct tagRECT *)((char *)this + 68);
    rc = v13;
    InflateRect(&rc, -5, -2);
    MoveWindow(*((HWND *)this + 6), rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, 1);
  }
}

```

## disassembly

```asm
0x1802079a8  mov     [rsp-8+arg_0], rcx
0x1802079ad  push    rbp
0x1802079ae  mov     rbp, rsp
0x1802079b1  sub     rsp, 120h
0x1802079b8  mov     rax, cs:__security_cookie
0x1802079bf  xor     rax, rsp
0x1802079c2  mov     [rbp+var_10], rax
0x1802079c6  mov     rax, [rbp+arg_0]
0x1802079ca  add     rax, 44h ; 'D'
0x1802079ce  mov     rdx, rax; lpRect
0x1802079d1  mov     rax, [rbp+arg_0]
0x1802079d5  mov     rcx, [rax+20h]; hWnd
0x1802079d9  call    cs:__imp_GetClientRect
0x1802079df  mov     rax, [rbp+arg_0]
0x1802079e3  movups  xmm0, xmmword ptr [rax+44h]
0x1802079e7  movdqu  [rsp+120h+var_98], xmm0
0x1802079f0  movups  xmm0, [rsp+120h+var_98]
0x1802079f8  movdqu  xmmword ptr [rbp+var_30.left], xmm0
0x1802079fd  mov     rax, [rbp+arg_0]
0x180207a01  cmp     dword ptr [rax+10h], 0
0x180207a05  jnz     loc_180207B3B
0x180207a0b  lea     rdx, [rbp+var_30]; struct tagRECT *
0x180207a0f  mov     rcx, [rbp+arg_0]; this
0x180207a13  call    ?M_GetSearchRect@OBJBRW_PANE@@QEAAXPEAUtagRECT@@@Z; OBJBRW_PANE::M_GetSearchRect(tagRECT *)
0x180207a18  lea     rax, [rbp+var_30]
0x180207a1c  mov     [rsp+120h+lParam], rax
0x180207a21  lea     rax, [rsp+120h+var_C0]
0x180207a26  mov     [rsp+120h+var_C8], rax
0x180207a2b  lea     r9, [rsp+120h+lParam]; lParam
0x180207a30  xor     r8d, r8d; wParam
0x180207a33  mov     edx, 1205h; Msg
0x180207a38  mov     rax, [rbp+arg_0]
0x180207a3c  mov     rcx, [rax+38h]; hWnd
0x180207a40  call    cs:__imp_SendMessageA
0x180207a46  mov     eax, [rsp+120h+var_A0]
0x180207a4d  or      eax, 40h
0x180207a50  mov     [rsp+120h+uFlags], eax; uFlags
0x180207a54  mov     eax, [rsp+120h+var_A4]
0x180207a58  mov     [rsp+120h+cy], eax; cy
0x180207a5c  mov     eax, [rsp+120h+var_A8]
0x180207a60  mov     [rsp+120h+nHeight], eax; cx
0x180207a64  mov     r9d, [rsp+120h+Y]; Y
0x180207a69  mov     r8d, [rsp+120h+X]; X
0x180207a6e  mov     rdx, [rsp+120h+hWndInsertAfter]; hWndInsertAfter
0x180207a73  mov     rax, [rbp+arg_0]
0x180207a77  mov     rcx, [rax+38h]; hWnd
0x180207a7b  call    cs:__imp_SetWindowPos
0x180207a81  mov     dword ptr [rbp+var_70], 1
0x180207a88  mov     rax, [rbp+arg_0]
0x180207a8c  mov     dword ptr [rax+40h], 1
0x180207a93  mov     eax, [rbp+var_30.left]
0x180207a96  mov     ecx, [rbp+var_30.right]
0x180207a99  sub     ecx, eax
0x180207a9b  mov     eax, ecx
0x180207a9d  mov     [rsp+120h+var_D8], eax
0x180207aa1  mov     [rsp+120h+var_DC], 0
0x180207aa9  mov     [rsp+120h+var_E0], 0
0x180207ab1  jmp     short loc_180207ABD
0x180207ab3  mov     eax, [rsp+120h+var_E0]
0x180207ab7  inc     eax
0x180207ab9  mov     [rsp+120h+var_E0], eax
0x180207abd  cmp     [rsp+120h+var_E0], 3
0x180207ac2  jnb     short loc_180207B30
0x180207ac4  cmp     [rsp+120h+var_E0], 2
0x180207ac9  jnz     short loc_180207ADE
0x180207acb  mov     eax, [rsp+120h+var_DC]
0x180207acf  mov     ecx, [rsp+120h+var_D8]
0x180207ad3  sub     ecx, eax
0x180207ad5  mov     eax, ecx
0x180207ad7  dec     eax
0x180207ad9  mov     dword ptr [rbp+var_70+4], eax
0x180207adc  jmp     short loc_180207B0F
0x180207ade  mov     eax, [rsp+120h+var_E0]
0x180207ae2  cvtsi2ss xmm0, [rsp+120h+var_D8]
0x180207ae8  mov     rcx, [rbp+arg_0]
0x180207aec  movss   xmm1, dword ptr [rcx+rax*4+60h]
0x180207af2  mulss   xmm1, xmm0
0x180207af6  movaps  xmm0, xmm1
0x180207af9  cvttss2si eax, xmm0
0x180207afd  mov     dword ptr [rbp+var_70+4], eax
0x180207b00  mov     eax, dword ptr [rbp+var_70+4]
0x180207b03  mov     ecx, [rsp+120h+var_DC]
0x180207b07  add     ecx, eax
0x180207b09  mov     eax, ecx
0x180207b0b  mov     [rsp+120h+var_DC], eax
0x180207b0f  movsxd  rax, [rsp+120h+var_E0]
0x180207b14  lea     r9, [rbp+var_70]; lParam
0x180207b18  mov     r8, rax; wParam
0x180207b1b  mov     edx, 1204h; Msg
0x180207b20  mov     rax, [rbp+arg_0]
0x180207b24  mov     rcx, [rax+38h]; hWnd
0x180207b28  call    cs:__imp_SendMessageA
0x180207b2e  jmp     short loc_180207AB3
0x180207b30  mov     rax, [rbp+arg_0]
0x180207b34  mov     dword ptr [rax+40h], 0
0x180207b3b  mov     rax, [rbp+arg_0]
0x180207b3f  cmp     qword ptr [rax+28h], 0
0x180207b44  jz      short loc_180207BAE
0x180207b46  mov     rax, [rbp+arg_0]
0x180207b4a  cmp     dword ptr [rax+10h], 0
0x180207b4e  jz      short loc_180207B60
0x180207b50  mov     eax, cs:dword_1803FF798
0x180207b56  mov     ecx, [rbp+var_30.top]
0x180207b59  add     ecx, eax
0x180207b5b  mov     eax, ecx
0x180207b5d  mov     [rbp+var_30.top], eax
0x180207b60  mov     eax, [rbp+var_30.top]
0x180207b63  mov     ecx, [rbp+var_30.bottom]
0x180207b66  sub     ecx, eax
0x180207b68  mov     eax, ecx
0x180207b6a  mov     ecx, [rbp+var_30.left]
0x180207b6d  mov     edx, [rbp+var_30.right]
0x180207b70  sub     edx, ecx
0x180207b72  mov     ecx, edx
0x180207b74  mov     [rsp+120h+cy], 1; bRepaint
0x180207b7c  mov     [rsp+120h+nHeight], eax; nHeight
0x180207b80  mov     r9d, ecx; nWidth
0x180207b83  mov     r8d, [rbp+var_30.top]; Y
0x180207b87  mov     edx, [rbp+var_30.left]; X
0x180207b8a  mov     rax, [rbp+arg_0]
0x180207b8e  mov     rcx, [rax+28h]; hWnd
0x180207b92  call    cs:__imp_MoveWindow
0x180207b98  mov     r8d, 1; bErase
0x180207b9e  xor     edx, edx; lpRect
0x180207ba0  mov     rax, [rbp+arg_0]
0x180207ba4  mov     rcx, [rax+28h]; hWnd
0x180207ba8  call    cs:__imp_InvalidateRect
0x180207bae  mov     rax, [rbp+arg_0]
0x180207bb2  cmp     qword ptr [rax+30h], 0
0x180207bb7  jz      short loc_180207C24
0x180207bb9  mov     rax, [rbp+arg_0]
0x180207bbd  movups  xmm0, xmmword ptr [rax+44h]
0x180207bc1  movdqu  [rsp+120h+var_88], xmm0
0x180207bca  movups  xmm0, [rsp+120h+var_88]
0x180207bd2  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x180207bd7  mov     r8d, 0FFFFFFFEh; dy
0x180207bdd  mov     edx, 0FFFFFFFBh; dx
0x180207be2  lea     rcx, [rbp+rc]; lprc
0x180207be6  call    cs:__imp_InflateRect
0x180207bec  mov     eax, [rbp+rc.top]
0x180207bef  mov     ecx, [rbp+rc.bottom]
0x180207bf2  sub     ecx, eax
0x180207bf4  mov     eax, ecx
0x180207bf6  mov     ecx, [rbp+rc.left]
0x180207bf9  mov     edx, [rbp+rc.right]
0x180207bfc  sub     edx, ecx
0x180207bfe  mov     ecx, edx
0x180207c00  mov     [rsp+120h+cy], 1; bRepaint
0x180207c08  mov     [rsp+120h+nHeight], eax; nHeight
0x180207c0c  mov     r9d, ecx; nWidth
0x180207c0f  mov     r8d, [rbp+rc.top]; Y
0x180207c13  mov     edx, [rbp+rc.left]; X
0x180207c16  mov     rax, [rbp+arg_0]
0x180207c1a  mov     rcx, [rax+30h]; hWnd
0x180207c1e  call    cs:__imp_MoveWindow
0x180207c24  mov     rcx, [rbp+var_10]
0x180207c28  xor     rcx, rsp; StackCookie
0x180207c2b  call    __security_check_cookie
0x180207c30  add     rsp, 120h
0x180207c37  pop     rbp
0x180207c38  retn
```
