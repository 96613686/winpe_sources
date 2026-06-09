# CScrollView::FillOutsideRect(CDC *,CBrush *)

- ea: `0x180067080`
- end: `0x180067142`
- name: `?FillOutsideRect@CScrollView@@QEAAXPEAVCDC@@PEAVCBrush@@@Z`
- size: `194`
- prototype: `void __fastcall(CScrollView *__hidden this, struct CDC *, struct CBrush *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180067080`
- `0x1800d1fe0`

## import_xrefs

- `USER32!GetClientRect` at `0x1800670a9`
- `USER32!GetClientRect` at `0x1800670a9`
- `USER32!FillRect` at `0x1800670df`
- `USER32!FillRect` at `0x180067127`
- `USER32!FillRect` at `0x1800670df`
- `USER32!FillRect` at `0x180067127`
- `USER32!IsRectEmpty` at `0x1800670be`
- `USER32!IsRectEmpty` at `0x180067106`
- `USER32!IsRectEmpty` at `0x1800670be`
- `USER32!IsRectEmpty` at `0x180067106`

## pseudocode

```c
void __fastcall CScrollView::FillOutsideRect(CScrollView *this, HDC *a2, struct CBrush *a3)
{
  HBRUSH v6; // r8
  HBRUSH v7; // r8
  struct tagRECT Rect; // [rsp+20h] [rbp-38h] BYREF

  GetClientRect(*((HWND *)this + 8), &Rect);
  Rect.left = *((_DWORD *)this + 37);
  if ( !IsRectEmpty(&Rect) )
  {
    if ( a3 )
      v6 = (HBRUSH)*((_QWORD *)a3 + 1);
    else
      v6 = 0;
    FillRect(a2[1], &Rect, v6);
  }
  Rect.right = *((_DWORD *)this + 37);
  Rect.top = *((_DWORD *)this + 38);
  Rect.left = 0;
  if ( !IsRectEmpty(&Rect) )
  {
    if ( a3 )
      v7 = (HBRUSH)*((_QWORD *)a3 + 1);
    else
      v7 = 0;
    FillRect(a2[1], &Rect, v7);
  }
}

```

## disassembly

```asm
0x180067080  push    rbx
0x180067082  push    rsi
0x180067083  push    rdi
0x180067084  sub     rsp, 40h
0x180067088  mov     rax, cs:__security_cookie
0x18006708f  xor     rax, rsp
0x180067092  mov     [rsp+58h+var_28], rax
0x180067097  mov     rsi, rdx
0x18006709a  mov     rdi, rcx
0x18006709d  mov     rcx, [rcx+40h]; hWnd
0x1800670a1  lea     rdx, [rsp+58h+Rect]; lpRect
0x1800670a6  mov     rbx, r8
0x1800670a9  call    cs:__imp_GetClientRect
0x1800670af  mov     eax, [rdi+94h]
0x1800670b5  lea     rcx, [rsp+58h+Rect]; lprc
0x1800670ba  mov     [rsp+58h+Rect.left], eax
0x1800670be  call    cs:__imp_IsRectEmpty
0x1800670c4  test    eax, eax
0x1800670c6  jnz     short loc_1800670E5
0x1800670c8  test    rbx, rbx
0x1800670cb  jnz     short loc_1800670D2
0x1800670cd  xor     r8d, r8d
0x1800670d0  jmp     short loc_1800670D6
0x1800670d2  mov     r8, [rbx+8]; hbr
0x1800670d6  mov     rcx, [rsi+8]; hDC
0x1800670da  lea     rdx, [rsp+58h+Rect]; lprc
0x1800670df  call    cs:__imp_FillRect
0x1800670e5  mov     eax, [rdi+94h]
0x1800670eb  lea     rcx, [rsp+58h+Rect]; lprc
0x1800670f0  mov     [rsp+58h+Rect.right], eax
0x1800670f4  mov     eax, [rdi+98h]
0x1800670fa  mov     [rsp+58h+Rect.top], eax
0x1800670fe  mov     [rsp+58h+Rect.left], 0
0x180067106  call    cs:__imp_IsRectEmpty
0x18006710c  test    eax, eax
0x18006710e  jnz     short loc_18006712D
0x180067110  test    rbx, rbx
0x180067113  jnz     short loc_18006711A
0x180067115  xor     r8d, r8d
0x180067118  jmp     short loc_18006711E
0x18006711a  mov     r8, [rbx+8]; hbr
0x18006711e  mov     rcx, [rsi+8]; hDC
0x180067122  lea     rdx, [rsp+58h+Rect]; lprc
0x180067127  call    cs:__imp_FillRect
0x18006712d  mov     rcx, [rsp+58h+var_28]
0x180067132  xor     rcx, rsp; StackCookie
0x180067135  call    __security_check_cookie
0x18006713a  add     rsp, 40h
0x18006713e  pop     rdi
0x18006713f  pop     rsi
0x180067140  pop     rbx
0x180067141  retn
```
