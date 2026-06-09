# BorderWindow::Update(void)

- ea: `0x1800120e4`
- end: `0x180012208`
- name: `?Update@BorderWindow@@QEAAXXZ`
- size: `292`
- prototype: `void __fastcall(BorderWindow *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001ee28`
- `0x1800257e0`
- `0x18002b910`

## callees

- `0x180001800`
- `0x1800120e4`

## import_xrefs

- `USER32!SetWindowPos` at `0x1800121dc`
- `USER32!SetWindowPos` at `0x1800121dc`
- `USER32!IsWindowVisible` at `0x180012116`
- `USER32!IsWindowVisible` at `0x180012116`
- `USER32!IsIconic` at `0x180012128`
- `USER32!IsIconic` at `0x180012128`
- `USER32!IsZoomed` at `0x18001213a`
- `USER32!IsZoomed` at `0x18001213a`
- `USER32!GetWindowRect` at `0x180012159`
- `USER32!GetWindowRect` at `0x180012159`
- `USER32!ShowWindow` at `0x1800121ea`
- `USER32!ShowWindow` at `0x1800121ea`
- `USER32!IsWindowEnabled` at `0x180012104`
- `USER32!IsWindowEnabled` at `0x180012104`

## pseudocode

```c
void __fastcall BorderWindow::Update(HWND *this)
{
  HWND v2; // rcx
  int v3; // edx
  LONG left; // r8d
  LONG right; // ecx
  LONG top; // r10d
  LONG bottom; // r9d
  int v8; // edx
  int v9; // edx
  struct tagRECT Rect; // [rsp+40h] [rbp-28h] BYREF

  if ( !IsWindowEnabled(this[1]) || !IsWindowVisible(this[10]) || IsIconic(this[10]) || IsZoomed(this[10]) )
  {
    ShowWindow(this[1], 0);
  }
  else
  {
    v2 = this[10];
    Rect = 0;
    GetWindowRect(v2, &Rect);
    v3 = *((_DWORD *)this + 22);
    left = Rect.left;
    right = Rect.right;
    top = Rect.top;
    bottom = Rect.bottom;
    if ( v3 )
    {
      v8 = v3 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          if ( v9 == 1 )
          {
            left = Rect.left - 8;
            right = Rect.right + 8;
            top = Rect.bottom;
            bottom = Rect.bottom + 8;
          }
        }
        else
        {
          right = Rect.right + 8;
          left = Rect.right;
        }
      }
      else
      {
        left = Rect.left - 8;
        right = Rect.right + 8;
        bottom = Rect.top;
        top = Rect.top - 8;
      }
    }
    else
    {
      left = Rect.left - 8;
      right = Rect.left;
    }
    SetWindowPos(this[1], 0, left, top, right - left, bottom - top, 0x254u);
  }
}

```

## disassembly

```asm
0x1800120e4  mov     [rsp+arg_8], rbx
0x1800120e9  push    rdi
0x1800120ea  sub     rsp, 60h
0x1800120ee  mov     rax, cs:__security_cookie
0x1800120f5  xor     rax, rsp
0x1800120f8  mov     [rsp+68h+var_18], rax
0x1800120fd  mov     rbx, rcx
0x180012100  mov     rcx, [rcx+8]; hWnd
0x180012104  call    cs:__imp_IsWindowEnabled
0x18001210a  test    eax, eax
0x18001210c  jz      loc_1800121E4
0x180012112  mov     rcx, [rbx+50h]; hWnd
0x180012116  call    cs:__imp_IsWindowVisible
0x18001211c  test    eax, eax
0x18001211e  jz      loc_1800121E4
0x180012124  mov     rcx, [rbx+50h]; hWnd
0x180012128  call    cs:__imp_IsIconic
0x18001212e  test    eax, eax
0x180012130  jnz     loc_1800121E4
0x180012136  mov     rcx, [rbx+50h]; hWnd
0x18001213a  call    cs:__imp_IsZoomed
0x180012140  test    eax, eax
0x180012142  jnz     loc_1800121E4
0x180012148  mov     rcx, [rbx+50h]; hWnd
0x18001214c  lea     rdx, [rsp+68h+Rect]; lpRect
0x180012151  xorps   xmm0, xmm0
0x180012154  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x180012159  call    cs:__imp_GetWindowRect
0x18001215f  mov     edx, [rbx+58h]
0x180012162  mov     r8d, [rsp+68h+Rect.left]
0x180012167  mov     r11d, r8d
0x18001216a  mov     ecx, [rsp+68h+Rect.right]
0x18001216e  mov     edi, ecx
0x180012170  mov     r10d, [rsp+68h+Rect.top]
0x180012175  mov     r9d, [rsp+68h+Rect.bottom]
0x18001217a  test    edx, edx
0x18001217c  jz      short loc_1800121B5
0x18001217e  sub     edx, 1
0x180012181  jz      short loc_1800121A5
0x180012183  sub     edx, 1
0x180012186  jz      short loc_18001219D
0x180012188  cmp     edx, 1
0x18001218b  jnz     short loc_1800121BC
0x18001218d  sub     r8d, 8
0x180012191  add     ecx, 8
0x180012194  mov     r10d, r9d
0x180012197  add     r9d, 8
0x18001219b  jmp     short loc_1800121BC
0x18001219d  add     ecx, 8
0x1800121a0  mov     r8d, edi
0x1800121a3  jmp     short loc_1800121BC
0x1800121a5  add     r8d, 0FFFFFFF8h
0x1800121a9  add     ecx, 8
0x1800121ac  mov     r9d, r10d
0x1800121af  add     r10d, 0FFFFFFF8h
0x1800121b3  jmp     short loc_1800121BC
0x1800121b5  add     r8d, 0FFFFFFF8h; X
0x1800121b9  mov     ecx, r11d
0x1800121bc  sub     r9d, r10d
0x1800121bf  mov     [rsp+68h+uFlags], 254h; uFlags
0x1800121c7  sub     ecx, r8d
0x1800121ca  mov     [rsp+68h+cy], r9d; cy
0x1800121cf  mov     [rsp+68h+var_48], ecx; cx
0x1800121d3  mov     r9d, r10d; Y
0x1800121d6  mov     rcx, [rbx+8]; hWnd
0x1800121da  xor     edx, edx; hWndInsertAfter
0x1800121dc  call    cs:__imp_SetWindowPos
0x1800121e2  jmp     short loc_1800121F0
0x1800121e4  mov     rcx, [rbx+8]; hWnd
0x1800121e8  xor     edx, edx; nCmdShow
0x1800121ea  call    cs:__imp_ShowWindow
0x1800121f0  mov     rcx, [rsp+68h+var_18]
0x1800121f5  xor     rcx, rsp; StackCookie
0x1800121f8  call    __security_check_cookie
0x1800121fd  mov     rbx, [rsp+68h+arg_8]
0x180012202  add     rsp, 60h
0x180012206  pop     rdi
0x180012207  retn
```
