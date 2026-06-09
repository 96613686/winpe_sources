# MODVWR::ResizePane(PANE *,tagRECT *,HRGN__ *,int)

- ea: `0x1801fcf1c`
- end: `0x1801fd2f6`
- name: `?ResizePane@MODVWR@@AEAAXPEAVPANE@@PEAUtagRECT@@PEAUHRGN__@@H@Z`
- size: `986`
- prototype: `void __fastcall(MODVWR *__hidden this, struct PANE *, struct tagRECT *, HRGN, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1801fac54`
- `0x1801fc91c`
- `0x1801fec20`

## callees

- `0x1801fcf1c`
- `0x180379520`

## import_xrefs

- `USER32!HideCaret` at `0x1801fd0dd`
- `USER32!HideCaret` at `0x1801fd0dd`
- `USER32!ScrollDC` at `0x1801fd235`
- `USER32!ScrollDC` at `0x1801fd235`
- `USER32!ShowCaret` at `0x1801fd29e`
- `USER32!ShowCaret` at `0x1801fd29e`
- `USER32!ValidateRect` at `0x1801fd247`
- `USER32!ValidateRect` at `0x1801fd247`
- `USER32!GetDC` at `0x1801fd09a`
- `USER32!GetDC` at `0x1801fd09a`
- `USER32!ReleaseDC` at `0x1801fd283`
- `USER32!ReleaseDC` at `0x1801fd283`
- `USER32!InvalidateRgn` at `0x1801fd25d`
- `USER32!InvalidateRgn` at `0x1801fd25d`
- `GDI32!RectInRegion` at `0x1801fd1e1`
- `GDI32!RectInRegion` at `0x1801fd1e1`
- `GDI32!CreateRectRgn` at `0x1801fd0ed`
- `GDI32!CreateRectRgn` at `0x1801fd0ed`
- `GDI32!SelectClipRgn` at `0x1801fd0c2`
- `GDI32!SelectClipRgn` at `0x1801fd0c2`
- `GDI32!DeleteObject` at `0x1801fd270`
- `GDI32!DeleteObject` at `0x1801fd270`

## pseudocode

```c
void __fastcall MODVWR::ResizePane(MODVWR *this, struct PANE *a2, struct tagRECT *a3, HRGN a4, int a5)
{
  __int128 v5; // xmm0
  int v6; // [rsp+40h] [rbp-B0h]
  LONG bottom; // [rsp+44h] [rbp-ACh]
  LONG right; // [rsp+48h] [rbp-A8h]
  HRGN hRgn; // [rsp+50h] [rbp-A0h]
  LONG v10; // [rsp+58h] [rbp-98h]
  HDC hdc; // [rsp+60h] [rbp-90h]
  RECT v12; // [rsp+A8h] [rbp-48h] BYREF
  RECT Rect; // [rsp+B8h] [rbp-38h] BYREF
  RECT rect; // [rsp+C8h] [rbp-28h] BYREF
  RECT v15; // [rsp+D8h] [rbp-18h] BYREF

  (**((void (__fastcall ***)(char *, struct PANE *, RECT *))this + 1))((char *)this + 8, a2, &v12);
  if ( !a3 || !a4 )
    goto LABEL_30;
  if ( *(_QWORD *)&v12.left == *(_QWORD *)&a3->left )
  {
    if ( v12.right > a3->right )
    {
      v15 = v12;
      v15.left = a3->right;
      (*(void (__fastcall **)(char *, RECT *, _QWORD))(*((_QWORD *)this + 1) + 48LL))((char *)this + 8, &v15, 0);
    }
    if ( v12.bottom > a3->bottom )
    {
      v15 = v12;
      v15.top = a3->bottom;
      (*(void (__fastcall **)(char *, RECT *, _QWORD))(*((_QWORD *)this + 1) + 48LL))((char *)this + 8, &v15, 0);
    }
    goto LABEL_31;
  }
  v10 = a3->bottom >= v12.bottom ? v12.bottom : a3->bottom;
  v6 = v10 - a3->top;
  if ( v6 > 0 )
  {
    hdc = GetDC(*((HWND *)this + 4));
    if ( !hdc )
      return;
    SelectClipRgn(hdc, 0);
    if ( *((_DWORD *)this + 44) )
      HideCaret(*((HWND *)this + 4));
    hRgn = CreateRectRgn(0, 0, 0, 0);
    Rect = v12;
    if ( v12.bottom >= v6 + v12.top )
      bottom = v6 + v12.top;
    else
      bottom = v12.bottom;
    Rect.bottom = bottom;
    if ( v12.right >= a3->right - a3->left + v12.left )
      right = a3->right - a3->left + v12.left;
    else
      right = v12.right;
    Rect.right = right;
    (*(void (__fastcall **)(char *, RECT *, _QWORD))(*((_QWORD *)this + 1) + 48LL))((char *)this + 8, &v12, 0);
    v5 = (__int128)*a3;
    *(_QWORD *)&rect.left = *(_QWORD *)&a3->left;
    rect.bottom = Rect.bottom - Rect.top + DWORD1(v5);
    rect.right = Rect.right - Rect.left + v5;
    if ( !RectInRegion(a4, &rect) )
    {
      ScrollDC(hdc, Rect.left - a3->left, Rect.top - a3->top, &rect, (const RECT *)((char *)this + 56), hRgn, 0);
      ValidateRect(*((HWND *)this + 4), &Rect);
      InvalidateRgn(*((HWND *)this + 4), hRgn, 0);
    }
    if ( hRgn )
      DeleteObject(hRgn);
    ReleaseDC(*((HWND *)this + 4), hdc);
    if ( *((_DWORD *)this + 44) )
      ShowCaret(*((HWND *)this + 4));
  }
  else
  {
LABEL_30:
    (*(void (__fastcall **)(char *, RECT *, _QWORD))(*((_QWORD *)this + 1) + 48LL))((char *)this + 8, &v12, 0);
  }
LABEL_31:
  if ( a5 )
    (*(void (__fastcall **)(struct PANE *))(*(_QWORD *)a2 + 8LL))(a2);
}

```

## disassembly

```asm
0x1801fcf1c  mov     [rsp-8+hrgn], r9
0x1801fcf21  mov     [rsp-8+arg_10], r8
0x1801fcf26  mov     [rsp-8+arg_8], rdx
0x1801fcf2b  mov     [rsp-8+arg_0], rcx
0x1801fcf30  push    rbp
0x1801fcf31  mov     rbp, rsp
0x1801fcf34  sub     rsp, 0F0h
0x1801fcf3b  mov     rax, cs:__security_cookie
0x1801fcf42  xor     rax, rsp
0x1801fcf45  mov     [rbp+var_8], rax
0x1801fcf49  mov     rax, [rbp+arg_0]
0x1801fcf4d  add     rax, 8
0x1801fcf51  mov     rcx, [rbp+arg_0]
0x1801fcf55  mov     rcx, [rcx+8]
0x1801fcf59  mov     [rbp+var_68], rcx
0x1801fcf5d  lea     r8, [rbp+var_48]
0x1801fcf61  mov     rdx, [rbp+arg_8]
0x1801fcf65  mov     rcx, rax
0x1801fcf68  mov     rax, [rbp+var_68]
0x1801fcf6c  call    qword ptr [rax]
0x1801fcf6e  cmp     [rbp+arg_10], 0
0x1801fcf73  jz      short loc_1801FCF7C
0x1801fcf75  cmp     [rbp+hrgn], 0
0x1801fcf7a  jnz     short loc_1801FCFA6
0x1801fcf7c  mov     rax, [rbp+arg_0]
0x1801fcf80  add     rax, 8
0x1801fcf84  mov     rcx, [rbp+arg_0]
0x1801fcf88  mov     rcx, [rcx+8]
0x1801fcf8c  mov     [rbp+var_60], rcx
0x1801fcf90  xor     r8d, r8d
0x1801fcf93  lea     rdx, [rbp+var_48]
0x1801fcf97  mov     rcx, rax
0x1801fcf9a  mov     rax, [rbp+var_60]
0x1801fcf9e  call    qword ptr [rax+30h]
0x1801fcfa1  jmp     loc_1801FD2CD
0x1801fcfa6  mov     rax, [rbp+arg_10]
0x1801fcfaa  mov     eax, [rax+4]
0x1801fcfad  cmp     dword ptr [rbp+var_48+4], eax
0x1801fcfb0  jnz     loc_1801FD054
0x1801fcfb6  mov     rax, [rbp+arg_10]
0x1801fcfba  mov     eax, [rax]
0x1801fcfbc  cmp     dword ptr [rbp+var_48], eax
0x1801fcfbf  jnz     loc_1801FD054
0x1801fcfc5  mov     rax, [rbp+arg_10]
0x1801fcfc9  mov     eax, [rax+8]
0x1801fcfcc  cmp     dword ptr [rbp+var_48+8], eax
0x1801fcfcf  jle     short loc_1801FD00B
0x1801fcfd1  movups  xmm0, [rbp+var_48]
0x1801fcfd5  movdqu  [rbp+var_18], xmm0
0x1801fcfda  mov     rax, [rbp+arg_10]
0x1801fcfde  mov     eax, [rax+8]
0x1801fcfe1  mov     dword ptr [rbp+var_18], eax
0x1801fcfe4  mov     rax, [rbp+arg_0]
0x1801fcfe8  add     rax, 8
0x1801fcfec  mov     rcx, [rbp+arg_0]
0x1801fcff0  mov     rcx, [rcx+8]
0x1801fcff4  mov     [rsp+0F0h+var_88], rcx
0x1801fcff9  xor     r8d, r8d
0x1801fcffc  lea     rdx, [rbp+var_18]
0x1801fd000  mov     rcx, rax
0x1801fd003  mov     rax, [rsp+0F0h+var_88]
0x1801fd008  call    qword ptr [rax+30h]
0x1801fd00b  mov     rax, [rbp+arg_10]
0x1801fd00f  mov     eax, [rax+0Ch]
0x1801fd012  cmp     dword ptr [rbp+var_48+0Ch], eax
0x1801fd015  jle     short loc_1801FD04F
0x1801fd017  movups  xmm0, [rbp+var_48]
0x1801fd01b  movdqu  [rbp+var_18], xmm0
0x1801fd020  mov     rax, [rbp+arg_10]
0x1801fd024  mov     eax, [rax+0Ch]
0x1801fd027  mov     dword ptr [rbp+var_18+4], eax
0x1801fd02a  mov     rax, [rbp+arg_0]
0x1801fd02e  add     rax, 8
0x1801fd032  mov     rcx, [rbp+arg_0]
0x1801fd036  mov     rcx, [rcx+8]
0x1801fd03a  mov     [rbp+var_70], rcx
0x1801fd03e  xor     r8d, r8d
0x1801fd041  lea     rdx, [rbp+var_18]
0x1801fd045  mov     rcx, rax
0x1801fd048  mov     rax, [rbp+var_70]
0x1801fd04c  call    qword ptr [rax+30h]
0x1801fd04f  jmp     loc_1801FD2CD
0x1801fd054  mov     rax, [rbp+arg_10]
0x1801fd058  mov     ecx, dword ptr [rbp+var_48+0Ch]
0x1801fd05b  cmp     [rax+0Ch], ecx
0x1801fd05e  jge     short loc_1801FD06D
0x1801fd060  mov     rax, [rbp+arg_10]
0x1801fd064  mov     eax, [rax+0Ch]
0x1801fd067  mov     [rsp+0F0h+var_98], eax
0x1801fd06b  jmp     short loc_1801FD074
0x1801fd06d  mov     eax, dword ptr [rbp+var_48+0Ch]
0x1801fd070  mov     [rsp+0F0h+var_98], eax
0x1801fd074  mov     rax, [rbp+arg_10]
0x1801fd078  mov     eax, [rax+4]
0x1801fd07b  mov     ecx, [rsp+0F0h+var_98]
0x1801fd07f  sub     ecx, eax
0x1801fd081  mov     eax, ecx
0x1801fd083  mov     [rsp+0F0h+var_B0], eax
0x1801fd087  cmp     [rsp+0F0h+var_B0], 0
0x1801fd08c  jle     loc_1801FD2A6
0x1801fd092  mov     rax, [rbp+arg_0]
0x1801fd096  mov     rcx, [rax+20h]; hWnd
0x1801fd09a  call    cs:__imp_GetDC
0x1801fd0a0  mov     [rsp+0F0h+hdc], rax
0x1801fd0a5  mov     [rsp+0F0h+hRgn], 0
0x1801fd0ae  cmp     [rsp+0F0h+hdc], 0
0x1801fd0b4  jnz     short loc_1801FD0BB
0x1801fd0b6  jmp     loc_1801FD2E1
0x1801fd0bb  xor     edx, edx; hrgn
0x1801fd0bd  mov     rcx, [rsp+0F0h+hdc]; hdc
0x1801fd0c2  call    cs:__imp_SelectClipRgn
0x1801fd0c8  mov     rax, [rbp+arg_0]
0x1801fd0cc  cmp     dword ptr [rax+0B0h], 0
0x1801fd0d3  jz      short loc_1801FD0E3
0x1801fd0d5  mov     rax, [rbp+arg_0]
0x1801fd0d9  mov     rcx, [rax+20h]; hWnd
0x1801fd0dd  call    cs:__imp_HideCaret
0x1801fd0e3  xor     r9d, r9d; y2
0x1801fd0e6  xor     r8d, r8d; x2
0x1801fd0e9  xor     edx, edx; y1
0x1801fd0eb  xor     ecx, ecx; x1
0x1801fd0ed  call    cs:__imp_CreateRectRgn
0x1801fd0f3  mov     [rsp+0F0h+hRgn], rax
0x1801fd0f8  movups  xmm0, [rbp+var_48]
0x1801fd0fc  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x1801fd101  mov     eax, [rsp+0F0h+var_B0]
0x1801fd105  mov     ecx, dword ptr [rbp+var_48+4]
0x1801fd108  add     ecx, eax
0x1801fd10a  mov     eax, ecx
0x1801fd10c  cmp     dword ptr [rbp+var_48+0Ch], eax
0x1801fd10f  jge     short loc_1801FD11A
0x1801fd111  mov     eax, dword ptr [rbp+var_48+0Ch]
0x1801fd114  mov     [rsp+0F0h+var_AC], eax
0x1801fd118  jmp     short loc_1801FD129
0x1801fd11a  mov     eax, [rsp+0F0h+var_B0]
0x1801fd11e  mov     ecx, dword ptr [rbp+var_48+4]
0x1801fd121  add     ecx, eax
0x1801fd123  mov     eax, ecx
0x1801fd125  mov     [rsp+0F0h+var_AC], eax
0x1801fd129  mov     eax, [rsp+0F0h+var_AC]
0x1801fd12d  mov     [rbp+Rect.bottom], eax
0x1801fd130  mov     rax, [rbp+arg_10]
0x1801fd134  mov     rcx, [rbp+arg_10]
0x1801fd138  mov     ecx, [rcx]
0x1801fd13a  mov     eax, [rax+8]
0x1801fd13d  sub     eax, ecx
0x1801fd13f  mov     ecx, dword ptr [rbp+var_48]
0x1801fd142  add     ecx, eax
0x1801fd144  mov     eax, ecx
0x1801fd146  cmp     dword ptr [rbp+var_48+8], eax
0x1801fd149  jge     short loc_1801FD154
0x1801fd14b  mov     eax, dword ptr [rbp+var_48+8]
0x1801fd14e  mov     [rsp+0F0h+var_A8], eax
0x1801fd152  jmp     short loc_1801FD16E
0x1801fd154  mov     rax, [rbp+arg_10]
0x1801fd158  mov     rcx, [rbp+arg_10]
0x1801fd15c  mov     ecx, [rcx]
0x1801fd15e  mov     eax, [rax+8]
0x1801fd161  sub     eax, ecx
0x1801fd163  mov     ecx, dword ptr [rbp+var_48]
0x1801fd166  add     ecx, eax
0x1801fd168  mov     eax, ecx
0x1801fd16a  mov     [rsp+0F0h+var_A8], eax
0x1801fd16e  mov     eax, [rsp+0F0h+var_A8]
0x1801fd172  mov     [rbp+Rect.right], eax
0x1801fd175  mov     rax, [rbp+arg_0]
0x1801fd179  add     rax, 8
0x1801fd17d  mov     rcx, [rbp+arg_0]
0x1801fd181  mov     rcx, [rcx+8]
0x1801fd185  mov     [rsp+0F0h+var_78], rcx
0x1801fd18a  xor     r8d, r8d
0x1801fd18d  lea     rdx, [rbp+var_48]
0x1801fd191  mov     rcx, rax
0x1801fd194  mov     rax, [rsp+0F0h+var_78]
0x1801fd199  call    qword ptr [rax+30h]
0x1801fd19c  mov     rax, [rbp+arg_10]
0x1801fd1a0  movups  xmm0, xmmword ptr [rax]
0x1801fd1a3  movdqu  [rbp+var_58], xmm0
0x1801fd1a8  movups  xmm0, [rbp+var_58]
0x1801fd1ac  movdqu  xmmword ptr [rbp+rect.left], xmm0
0x1801fd1b1  mov     eax, [rbp+Rect.top]
0x1801fd1b4  mov     ecx, [rbp+Rect.bottom]
0x1801fd1b7  sub     ecx, eax
0x1801fd1b9  mov     eax, ecx
0x1801fd1bb  mov     ecx, [rbp+rect.top]
0x1801fd1be  add     ecx, eax
0x1801fd1c0  mov     eax, ecx
0x1801fd1c2  mov     [rbp+rect.bottom], eax
0x1801fd1c5  mov     eax, [rbp+Rect.left]
0x1801fd1c8  mov     ecx, [rbp+Rect.right]
0x1801fd1cb  sub     ecx, eax
0x1801fd1cd  mov     eax, ecx
0x1801fd1cf  mov     ecx, [rbp+rect.left]
0x1801fd1d2  add     ecx, eax
0x1801fd1d4  mov     eax, ecx
0x1801fd1d6  mov     [rbp+rect.right], eax
0x1801fd1d9  lea     rdx, [rbp+rect]; lprect
0x1801fd1dd  mov     rcx, [rbp+hrgn]; hrgn
0x1801fd1e1  call    cs:__imp_RectInRegion
0x1801fd1e7  test    eax, eax
0x1801fd1e9  jnz     short loc_1801FD263
0x1801fd1eb  mov     rax, [rbp+arg_0]
0x1801fd1ef  add     rax, 38h ; '8'
0x1801fd1f3  mov     rcx, [rbp+arg_10]
0x1801fd1f7  mov     ecx, [rcx+4]
0x1801fd1fa  mov     edx, [rbp+Rect.top]
0x1801fd1fd  sub     edx, ecx
0x1801fd1ff  mov     ecx, edx
0x1801fd201  mov     rdx, [rbp+arg_10]
0x1801fd205  mov     edx, [rdx]
0x1801fd207  mov     r8d, [rbp+Rect.left]
0x1801fd20b  sub     r8d, edx
0x1801fd20e  mov     edx, r8d; dx
0x1801fd211  mov     [rsp+0F0h+lprcUpdate], 0; lprcUpdate
0x1801fd21a  mov     r8, [rsp+0F0h+hRgn]
0x1801fd21f  mov     [rsp+0F0h+hrgnUpdate], r8; hrgnUpdate
0x1801fd224  mov     [rsp+0F0h+lprcClip], rax; lprcClip
0x1801fd229  lea     r9, [rbp+rect]; lprcScroll
0x1801fd22d  mov     r8d, ecx; dy
0x1801fd230  mov     rcx, [rsp+0F0h+hdc]; hDC
0x1801fd235  call    cs:__imp_ScrollDC
0x1801fd23b  lea     rdx, [rbp+Rect]; lpRect
0x1801fd23f  mov     rax, [rbp+arg_0]
0x1801fd243  mov     rcx, [rax+20h]; hWnd
0x1801fd247  call    cs:__imp_ValidateRect
0x1801fd24d  xor     r8d, r8d; bErase
0x1801fd250  mov     rdx, [rsp+0F0h+hRgn]; hRgn
0x1801fd255  mov     rax, [rbp+arg_0]
0x1801fd259  mov     rcx, [rax+20h]; hWnd
0x1801fd25d  call    cs:__imp_InvalidateRgn
0x1801fd263  cmp     [rsp+0F0h+hRgn], 0
0x1801fd269  jz      short loc_1801FD276
0x1801fd26b  mov     rcx, [rsp+0F0h+hRgn]; ho
0x1801fd270  call    cs:__imp_DeleteObject
0x1801fd276  mov     rdx, [rsp+0F0h+hdc]; hDC
0x1801fd27b  mov     rax, [rbp+arg_0]
0x1801fd27f  mov     rcx, [rax+20h]; hWnd
0x1801fd283  call    cs:__imp_ReleaseDC
0x1801fd289  mov     rax, [rbp+arg_0]
0x1801fd28d  cmp     dword ptr [rax+0B0h], 0
0x1801fd294  jz      short loc_1801FD2A4
0x1801fd296  mov     rax, [rbp+arg_0]
0x1801fd29a  mov     rcx, [rax+20h]; hWnd
0x1801fd29e  call    cs:__imp_ShowCaret
0x1801fd2a4  jmp     short loc_1801FD2CD
0x1801fd2a6  mov     rax, [rbp+arg_0]
0x1801fd2aa  add     rax, 8
0x1801fd2ae  mov     rcx, [rbp+arg_0]
0x1801fd2b2  mov     rcx, [rcx+8]
0x1801fd2b6  mov     [rsp+0F0h+var_80], rcx
0x1801fd2bb  xor     r8d, r8d
0x1801fd2be  lea     rdx, [rbp+var_48]
0x1801fd2c2  mov     rcx, rax
0x1801fd2c5  mov     rax, [rsp+0F0h+var_80]
0x1801fd2ca  call    qword ptr [rax+30h]
0x1801fd2cd  cmp     [rbp+arg_20], 0
0x1801fd2d1  jz      short loc_1801FD2E1
0x1801fd2d3  mov     rax, [rbp+arg_8]
0x1801fd2d7  mov     rax, [rax]
0x1801fd2da  mov     rcx, [rbp+arg_8]
0x1801fd2de  call    qword ptr [rax+8]
0x1801fd2e1  mov     rcx, [rbp+var_8]
0x1801fd2e5  xor     rcx, rsp; StackCookie
0x1801fd2e8  call    __security_check_cookie
0x1801fd2ed  add     rsp, 0F0h
0x1801fd2f4  pop     rbp
0x1801fd2f5  retn
```
