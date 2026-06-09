# CTitleBar::_UpdateMouseCursor(tagPOINT)

- ea: `0x180028fd0`
- end: `0x18002926c`
- name: `?_UpdateMouseCursor@CTitleBar@@AEAAXUtagPOINT@@@Z`
- size: `668`
- prototype: `void(CTitleBar *__hidden this, struct tagPOINT)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180028ed8`

## callees

- `0x180028fd0`
- `0x180043c30`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029017`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002903e`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029056`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002906e`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029086`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800290a1`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029184`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029017`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002903e`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029056`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002906e`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029086`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800290a1`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029184`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18002913c`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18002913c`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x18002910f`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x180029128`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x18002910f`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x180029128`
- `USER32!LoadCursorW` at `0x1800290c2`
- `USER32!LoadCursorW` at `0x1800290c2`
- `USER32!SetCursor` at `0x1800290cb`
- `USER32!SetCursor` at `0x1800290cb`

## pseudocode

```c
void __fastcall CTitleBar::_UpdateMouseCursor(CTitleBar *this, POINT a2)
{
  bool v2; // zf
  bool v5; // di
  LONG *v6; // r15
  __int64 v7; // rbp
  __int64 v8; // rdi
  __int64 v9; // rdx
  HCURSOR CursorW; // rax
  __int64 v11; // rdi
  HWND *v12; // r14
  LONG v13; // eax
  LONG v14; // ecx
  __int64 v15; // rdi
  __int64 v16; // rdi
  __int64 v17; // rdi
  __int64 v18; // rdi
  RECT rc; // [rsp+20h] [rbp-48h] BYREF

  v2 = (*((_DWORD *)this + 364) & 0x100) == 0;
  *(POINT *)&rc.left = a2;
  v5 = !v2 && *((_DWORD *)this + 138) == 1;
  v6 = (LONG *)((char *)this + 852);
  if ( PtInRect((const RECT *)((char *)this + 852), a2) || v5 && !rc.top )
  {
    if ( PtInRect((const RECT *)((char *)this + 1300), a2) )
    {
      v7 = 8;
    }
    else if ( PtInRect((const RECT *)((char *)this + 1364), a2) )
    {
      v7 = 9;
    }
    else if ( PtInRect((const RECT *)((char *)this + 1316), a2) )
    {
      v7 = 23;
    }
    else if ( PtInRect((const RECT *)((char *)this + 1332), a2) )
    {
      v7 = 24;
    }
    else
    {
      v7 = 1;
      if ( PtInRect((const RECT *)((char *)this + 1348), a2) )
        v7 = 20;
    }
    v11 = 2;
    v12 = (HWND *)((char *)this + 504);
    if ( (*((_BYTE *)this + 1452) & 2) != 0 && !IsZoomed(*v12) )
    {
      v14 = *((_DWORD *)this + 158);
      if ( rc.top <= v14 )
      {
        if ( a2.x >= v6[2] - v14 - *v6 )
        {
          v11 = 14;
        }
        else
        {
          v11 = 13;
          if ( a2.x > v14 )
            v11 = 12;
        }
      }
    }
    if ( v11 == 2 )
      v11 = v7;
    if ( IsZoomed(*v12) && !IsRectEmpty((const RECT *)((char *)this + 1348)) )
    {
      v2 = *((_BYTE *)this + 559) == 0;
      v13 = *((_DWORD *)this + 214);
      rc = *(RECT *)((char *)this + 1348);
      rc.top = v13;
      if ( !v2 || *((_BYTE *)this + 560) )
        rc.left = *v6;
      else
        rc.right = v6[2];
      if ( PtInRect(&rc, a2) )
        goto LABEL_14;
    }
    if ( v11 == 1 )
      goto LABEL_14;
    v8 = v11 - 2;
    if ( !v8 )
      goto LABEL_14;
    v15 = v8 - 1;
    if ( !v15 )
      goto LABEL_14;
    v16 = v15 - 5;
    if ( !v16 )
      goto LABEL_14;
    v17 = v16 - 1;
    if ( !v17 )
      goto LABEL_14;
    v18 = v17 - 3;
    if ( !v18 )
    {
      v9 = 32645;
      goto LABEL_15;
    }
    if ( v18 == 8 )
    {
LABEL_14:
      v9 = 32512;
LABEL_15:
      CursorW = LoadCursorW(0, (LPCWSTR)v9);
      SetCursor(CursorW);
    }
  }
}

```

## disassembly

```asm
0x180028fd0  mov     [rsp+arg_10], rbx
0x180028fd5  push    rbp
0x180028fd6  push    rsi
0x180028fd7  push    rdi
0x180028fd8  push    r14
0x180028fda  push    r15
0x180028fdc  sub     rsp, 40h
0x180028fe0  mov     rax, cs:__security_cookie
0x180028fe7  xor     rax, rsp
0x180028fea  mov     [rsp+68h+var_38], rax
0x180028fef  test    dword ptr [rcx+5B0h], 100h
0x180028ff9  mov     rbx, rdx
0x180028ffc  mov     rsi, rcx
0x180028fff  mov     qword ptr [rsp+68h+rc.left], rdx
0x180029004  jnz     loc_18002922D
0x18002900a  xor     dil, dil
0x18002900d  lea     r15, [rcx+354h]
0x180029014  mov     rcx, r15; lprc
0x180029017  call    cs:__imp_PtInRect
0x18002901d  test    eax, eax
0x18002901f  jnz     short loc_180029034
0x180029021  test    dil, dil
0x180029024  jz      loc_1800290D1
0x18002902a  cmp     [rsp+68h+rc.top], eax
0x18002902e  jnz     loc_1800290D1
0x180029034  lea     rcx, [rsi+514h]; lprc
0x18002903b  mov     rdx, rbx; pt
0x18002903e  call    cs:__imp_PtInRect
0x180029044  test    eax, eax
0x180029046  jnz     loc_1800290F2
0x18002904c  lea     rcx, [rsi+554h]; lprc
0x180029053  mov     rdx, rbx; pt
0x180029056  call    cs:__imp_PtInRect
0x18002905c  test    eax, eax
0x18002905e  jnz     loc_1800291E6
0x180029064  lea     rcx, [rsi+524h]; lprc
0x18002906b  mov     rdx, rbx; pt
0x18002906e  call    cs:__imp_PtInRect
0x180029074  test    eax, eax
0x180029076  jnz     loc_180029242
0x18002907c  lea     rcx, [rsi+534h]; lprc
0x180029083  mov     rdx, rbx; pt
0x180029086  call    cs:__imp_PtInRect
0x18002908c  test    eax, eax
0x18002908e  jnz     loc_180029223
0x180029094  lea     rcx, [rsi+544h]; lprc
0x18002909b  mov     rdx, rbx; pt
0x18002909e  lea     ebp, [rax+1]
0x1800290a1  call    cs:__imp_PtInRect
0x1800290a7  test    eax, eax
0x1800290a9  lea     ecx, [rbp+13h]
0x1800290ac  cmovnz  ebp, ecx
0x1800290af  jmp     short loc_1800290F7
0x1800290b1  sub     rdi, 2
0x1800290b5  jnz     loc_1800291F0
0x1800290bb  mov     edx, 7F00h; lpCursorName
0x1800290c0  xor     ecx, ecx; hInstance
0x1800290c2  call    cs:__imp_LoadCursorW
0x1800290c8  mov     rcx, rax; hCursor
0x1800290cb  call    cs:__imp_SetCursor
0x1800290d1  mov     rcx, [rsp+68h+var_38]
0x1800290d6  xor     rcx, rsp; StackCookie
0x1800290d9  call    __security_check_cookie
0x1800290de  mov     rbx, [rsp+68h+arg_10]
0x1800290e6  add     rsp, 40h
0x1800290ea  pop     r15
0x1800290ec  pop     r14
0x1800290ee  pop     rdi
0x1800290ef  pop     rsi
0x1800290f0  pop     rbp
0x1800290f1  retn
0x1800290f2  mov     ebp, 8
0x1800290f7  mov     edi, 2
0x1800290fc  lea     r14, [rsi+1F8h]
0x180029103  test    [rsi+5ACh], dil
0x18002910a  jz      short loc_18002911D
0x18002910c  mov     rcx, [r14]; hWnd
0x18002910f  call    cs:__imp_IsZoomed
0x180029115  test    eax, eax
0x180029117  jz      loc_1800291A1
0x18002911d  mov     rcx, [r14]; hWnd
0x180029120  cmp     rdi, 2
0x180029124  cmovz   rdi, rbp
0x180029128  call    cs:__imp_IsZoomed
0x18002912e  test    eax, eax
0x180029130  jz      short loc_180029192
0x180029132  lea     rbp, [rsi+544h]
0x180029139  mov     rcx, rbp; lprc
0x18002913c  call    cs:__imp_IsRectEmpty
0x180029142  test    eax, eax
0x180029144  jnz     short loc_180029192
0x180029146  cmp     byte ptr [rsi+22Fh], 0
0x18002914d  movups  xmm0, xmmword ptr [rbp+0]
0x180029151  mov     eax, [rsi+358h]
0x180029157  movdqu  xmmword ptr [rsp+68h+rc.left], xmm0
0x18002915d  mov     [rsp+68h+rc.top], eax
0x180029161  jnz     loc_180029256
0x180029167  cmp     byte ptr [rsi+230h], 0
0x18002916e  jnz     loc_180029256
0x180029174  mov     eax, [r15+8]
0x180029178  mov     [rsp+68h+rc.right], eax
0x18002917c  mov     rdx, rbx; pt
0x18002917f  lea     rcx, [rsp+68h+rc]; lprc
0x180029184  call    cs:__imp_PtInRect
0x18002918a  test    eax, eax
0x18002918c  jnz     loc_1800290BB
0x180029192  cmp     rdi, 1
0x180029196  jz      loc_1800290BB
0x18002919c  jmp     loc_1800290B1
0x1800291a1  mov     ecx, [rsi+278h]
0x1800291a7  cmp     [rsp+68h+rc.top], ecx
0x1800291ab  mov     eax, [r15+8]
0x1800291af  setle   dl
0x1800291b2  cmp     ebx, ecx
0x1800291b4  setle   r8b
0x1800291b8  sub     eax, ecx
0x1800291ba  sub     eax, [r15]
0x1800291bd  cmp     ebx, eax
0x1800291bf  setnl   al
0x1800291c2  test    dl, dl
0x1800291c4  jz      loc_18002911D
0x1800291ca  test    al, al
0x1800291cc  jnz     short loc_18002924C
0x1800291ce  mov     edi, 0Dh
0x1800291d3  test    r8b, r8b
0x1800291d6  jnz     loc_18002911D
0x1800291dc  mov     edi, 0Ch
0x1800291e1  jmp     loc_18002911D
0x1800291e6  mov     ebp, 9
0x1800291eb  jmp     loc_1800290F7
0x1800291f0  sub     rdi, 1
0x1800291f4  jz      loc_1800290BB
0x1800291fa  sub     rdi, 5
0x1800291fe  jz      loc_1800290BB
0x180029204  sub     rdi, 1
0x180029208  jz      loc_1800290BB
0x18002920e  sub     rdi, 3
0x180029212  jz      short loc_180029262
0x180029214  cmp     rdi, 8
0x180029218  jnz     loc_1800290D1
0x18002921e  jmp     loc_1800290BB
0x180029223  mov     ebp, 18h
0x180029228  jmp     loc_1800290F7
0x18002922d  cmp     dword ptr [rcx+228h], 1
0x180029234  jnz     loc_18002900A
0x18002923a  mov     dil, 1
0x18002923d  jmp     loc_18002900D
0x180029242  mov     ebp, 17h
0x180029247  jmp     loc_1800290F7
0x18002924c  mov     edi, 0Eh
0x180029251  jmp     loc_18002911D
0x180029256  mov     eax, [r15]
0x180029259  mov     [rsp+68h+rc.left], eax
0x18002925d  jmp     loc_18002917C
0x180029262  mov     edx, 7F85h
0x180029267  jmp     loc_1800290C0
```
