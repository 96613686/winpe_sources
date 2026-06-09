# _MoveDlgItem(void *,HWND__ *,int,int,int)

- ea: `0x1800073ec`
- end: `0x1800074a0`
- name: `?_MoveDlgItem@@YAXPEAXPEAUHWND__@@HHH@Z`
- size: `180`
- prototype: `void __usercall(HDWP hWinPosInfo@<rcx>, HWND hWndTo@<rdx>, int nIDDlgItem@<r8d>, int@<r9d>, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800074a8`

## callees

- `0x180012fc0`

## import_xrefs

- `USER32!GetDlgItem` at `0x18000741b`
- `USER32!GetDlgItem` at `0x18000741b`
- `USER32!GetClientRect` at `0x18000742c`
- `USER32!GetClientRect` at `0x18000742c`
- `USER32!MapWindowPoints` at `0x180007443`
- `USER32!MapWindowPoints` at `0x180007443`
- `USER32!DeferWindowPos` at `0x180007484`
- `USER32!DeferWindowPos` at `0x180007484`

## pseudocode

```c
void __fastcall _MoveDlgItem(HDWP hWinPosInfo, HWND hWndTo, int nIDDlgItem, int a4, int a5)
{
  HWND DlgItem; // rbx
  tagRECT Rect; // [rsp+40h] [rbp-48h] BYREF

  Rect = 0;
  DlgItem = GetDlgItem(hWndTo, nIDDlgItem);
  GetClientRect(DlgItem, &Rect);
  MapWindowPoints(DlgItem, hWndTo, (LPPOINT)&Rect, 2u);
  DeferWindowPos(hWinPosInfo, DlgItem, 0, a4 + Rect.left, a5 + Rect.top, 0, 0, 0x55u);
}

```

## disassembly

```asm
0x1800073ec  push    rbx
0x1800073ee  push    rbp
0x1800073ef  push    rsi
0x1800073f0  push    rdi
0x1800073f1  sub     rsp, 68h
0x1800073f5  mov     rax, cs:__security_cookie
0x1800073fc  xor     rax, rsp
0x1800073ff  mov     [rsp+88h+var_38], rax
0x180007404  mov     rdi, rdx
0x180007407  mov     rbp, rcx
0x18000740a  xorps   xmm0, xmm0
0x18000740d  mov     rcx, rdi; hDlg
0x180007410  mov     edx, r8d; nIDDlgItem
0x180007413  mov     esi, r9d
0x180007416  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x18000741b  call    cs:__imp_GetDlgItem
0x180007421  mov     rcx, rax; hWnd
0x180007424  lea     rdx, [rsp+88h+Rect]; lpRect
0x180007429  mov     rbx, rax
0x18000742c  call    cs:__imp_GetClientRect
0x180007432  mov     r9d, 2; cPoints
0x180007438  lea     r8, [rsp+88h+Rect]; lpPoints
0x18000743d  mov     rdx, rdi; hWndTo
0x180007440  mov     rcx, rbx; hWndFrom
0x180007443  call    cs:__imp_MapWindowPoints
0x180007449  mov     r10d, [rsp+88h+Rect.top]
0x18000744e  xor     r8d, r8d; hWndInsertAfter
0x180007451  mov     r9d, [rsp+88h+Rect.left]
0x180007456  mov     rdx, rbx; hWnd
0x180007459  add     r10d, [rsp+88h+arg_20]
0x180007461  add     r9d, esi; x
0x180007464  mov     [rsp+88h+uFlags], 55h ; 'U'; uFlags
0x18000746c  mov     rcx, rbp; hWinPosInfo
0x18000746f  mov     [rsp+88h+cy], 0; cy
0x180007477  mov     [rsp+88h+var_60], 0; cx
0x18000747f  mov     [rsp+88h+y], r10d; y
0x180007484  call    cs:__imp_DeferWindowPos
0x18000748a  mov     rcx, [rsp+88h+var_38]
0x18000748f  xor     rcx, rsp; StackCookie
0x180007492  call    __security_check_cookie
0x180007497  add     rsp, 68h
0x18000749b  pop     rdi
0x18000749c  pop     rsi
0x18000749d  pop     rbp
0x18000749e  pop     rbx
0x18000749f  retn
```
