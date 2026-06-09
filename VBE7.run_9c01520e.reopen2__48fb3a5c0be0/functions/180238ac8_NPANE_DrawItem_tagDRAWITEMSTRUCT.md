# NPANE::DrawItem(tagDRAWITEMSTRUCT *)

- ea: `0x180238ac8`
- end: `0x180238dc7`
- name: `?DrawItem@NPANE@@AEAAXPEAUtagDRAWITEMSTRUCT@@@Z`
- size: `767`
- prototype: `void __fastcall(NPANE *__hidden this, struct tagDRAWITEMSTRUCT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180237c28`

## callees

- `0x1800e1af0`
- `0x180238ac8`
- `0x180289b60`
- `0x180379520`

## import_xrefs

- `USER32!FillRect` at `0x180238bb4`
- `USER32!FillRect` at `0x180238bb4`
- `USER32!GetSysColor` at `0x180238b39`
- `USER32!GetSysColor` at `0x180238b58`
- `USER32!GetSysColor` at `0x180238b39`
- `USER32!GetSysColor` at `0x180238b58`
- `USER32!SendMessageA` at `0x180238bf6`
- `USER32!SendMessageA` at `0x180238c59`
- `USER32!SendMessageA` at `0x180238c79`
- `USER32!SendMessageA` at `0x180238bf6`
- `USER32!SendMessageA` at `0x180238c59`
- `USER32!SendMessageA` at `0x180238c79`
- `USER32!DrawFocusRect` at `0x180238dab`
- `USER32!DrawFocusRect` at `0x180238dab`
- `GDI32!GetBkColor` at `0x180238b90`
- `GDI32!GetBkColor` at `0x180238b90`
- `GDI32!ExtTextOutA` at `0x180238d0f`
- `GDI32!ExtTextOutA` at `0x180238d0f`
- `GDI32!SelectObject` at `0x180238ca1`
- `GDI32!SelectObject` at `0x180238cc5`
- `GDI32!SelectObject` at `0x180238d2a`
- `GDI32!SelectObject` at `0x180238ca1`
- `GDI32!SelectObject` at `0x180238cc5`
- `GDI32!SelectObject` at `0x180238d2a`
- `GDI32!SetTextColor` at `0x180238b49`
- `GDI32!SetTextColor` at `0x180238d5e`
- `GDI32!SetTextColor` at `0x180238b49`
- `GDI32!SetTextColor` at `0x180238d5e`
- `GDI32!SetBkColor` at `0x180238b68`
- `GDI32!SetBkColor` at `0x180238d70`
- `GDI32!SetBkColor` at `0x180238b68`
- `GDI32!SetBkColor` at `0x180238d70`
- `GDI32!DeleteObject` at `0x180238bc7`
- `GDI32!DeleteObject` at `0x180238bc7`
- `GDI32!CreateSolidBrush` at `0x180238b98`
- `GDI32!CreateSolidBrush` at `0x180238b98`

## pseudocode

```c
void __fastcall NPANE::DrawItem(NPANE *this, struct tagDRAWITEMSTRUCT *a2)
{
  COLORREF SysColor; // eax
  COLORREF v3; // eax
  COLORREF BkColor; // eax
  int v5; // [rsp+40h] [rbp-80h]
  COLORREF color; // [rsp+44h] [rbp-7Ch]
  COLORREF v7; // [rsp+48h] [rbp-78h]
  HGDIOBJ h; // [rsp+50h] [rbp-70h]
  HBRUSH hbr; // [rsp+58h] [rbp-68h]
  void *lParam; // [rsp+60h] [rbp-60h]
  RECT rc; // [rsp+98h] [rbp-28h] BYREF

  if ( a2->itemAction == 1 || a2->itemAction == 2 )
  {
    color = 0;
    v7 = 0;
    if ( (a2->itemState & 1) != 0 )
    {
      SysColor = GetSysColor(14);
      color = SetTextColor(a2->hDC, SysColor);
      v3 = GetSysColor(13);
      v7 = SetBkColor(a2->hDC, v3);
    }
    rc = a2->rcItem;
    BkColor = GetBkColor(a2->hDC);
    hbr = CreateSolidBrush(BkColor);
    FillRect(a2->hDC, &rc, hbr);
    if ( hbr )
      DeleteObject(hbr);
    if ( a2->itemID != -1 )
    {
      v5 = SendMessageA(a2->hwndItem, 0x149u, (int)a2->itemID, 0) + 1;
      lParam = operator new(v5);
      memset(lParam, 0, v5);
      SendMessageA(a2->hwndItem, 0x148u, (int)a2->itemID, (LPARAM)lParam);
      if ( (unsigned int)SendMessageA(a2->hwndItem, 0x150u, a2->itemID, 0) )
        h = SelectObject(a2->hDC, *(HGDIOBJ *)(*((_QWORD *)this + 2) + 1008LL));
      else
        h = SelectObject(a2->hDC, *(HGDIOBJ *)(*((_QWORD *)this + 2) + 1016LL));
      ExtTextOutA(a2->hDC, rc.left + 1, rc.top, 6u, &rc, (LPCSTR)lParam, v5 - 1, 0);
      if ( h )
        SelectObject(a2->hDC, h);
      operator delete(lParam);
    }
    if ( (a2->itemState & 1) != 0 )
    {
      SetTextColor(a2->hDC, color);
      SetBkColor(a2->hDC, v7);
    }
  }
  if ( a2->itemAction == 1 && (a2->itemState & 0x10) != 0 || a2->itemAction == 4 )
    DrawFocusRect(a2->hDC, &a2->rcItem);
}

```

## disassembly

```asm
0x180238ac8  mov     [rsp-8+arg_8], rdx
0x180238acd  mov     [rsp-8+arg_0], rcx
0x180238ad2  push    rbp
0x180238ad3  mov     rbp, rsp
0x180238ad6  push    rdi
0x180238ad7  sub     rsp, 0B8h
0x180238ade  mov     rax, cs:__security_cookie
0x180238ae5  xor     rax, rsp
0x180238ae8  mov     [rbp+var_18], rax
0x180238aec  mov     [rsp+0C0h+h], 0
0x180238af5  mov     rax, [rbp+arg_8]
0x180238af9  cmp     dword ptr [rax+0Ch], 1
0x180238afd  jz      short loc_180238B0D
0x180238aff  mov     rax, [rbp+arg_8]
0x180238b03  cmp     dword ptr [rax+0Ch], 2
0x180238b07  jnz     loc_180238D76
0x180238b0d  mov     [rsp+0C0h+hbr], 0
0x180238b16  mov     [rsp+0C0h+color], 0
0x180238b1e  mov     [rsp+0C0h+var_78], 0
0x180238b26  mov     rax, [rbp+arg_8]
0x180238b2a  mov     eax, [rax+10h]
0x180238b2d  and     eax, 1
0x180238b30  test    eax, eax
0x180238b32  jz      short loc_180238B72
0x180238b34  mov     ecx, 0Eh; nIndex
0x180238b39  call    cs:__imp_GetSysColor
0x180238b3f  mov     edx, eax; color
0x180238b41  mov     rax, [rbp+arg_8]
0x180238b45  mov     rcx, [rax+20h]; hdc
0x180238b49  call    cs:__imp_SetTextColor
0x180238b4f  mov     [rsp+0C0h+color], eax
0x180238b53  mov     ecx, 0Dh; nIndex
0x180238b58  call    cs:__imp_GetSysColor
0x180238b5e  mov     edx, eax; color
0x180238b60  mov     rax, [rbp+arg_8]
0x180238b64  mov     rcx, [rax+20h]; hdc
0x180238b68  call    cs:__imp_SetBkColor
0x180238b6e  mov     [rsp+0C0h+var_78], eax
0x180238b72  mov     rax, [rbp+arg_8]
0x180238b76  movups  xmm0, xmmword ptr [rax+28h]
0x180238b7a  movdqu  [rbp+var_38], xmm0
0x180238b7f  movups  xmm0, [rbp+var_38]
0x180238b83  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x180238b88  mov     rax, [rbp+arg_8]
0x180238b8c  mov     rcx, [rax+20h]; hdc
0x180238b90  call    cs:__imp_GetBkColor
0x180238b96  mov     ecx, eax; color
0x180238b98  call    cs:__imp_CreateSolidBrush
0x180238b9e  mov     [rsp+0C0h+hbr], rax
0x180238ba3  mov     r8, [rsp+0C0h+hbr]; hbr
0x180238ba8  lea     rdx, [rbp+rc]; lprc
0x180238bac  mov     rax, [rbp+arg_8]
0x180238bb0  mov     rcx, [rax+20h]; hDC
0x180238bb4  call    cs:__imp_FillRect
0x180238bba  cmp     [rsp+0C0h+hbr], 0
0x180238bc0  jz      short loc_180238BCD
0x180238bc2  mov     rcx, [rsp+0C0h+hbr]; ho
0x180238bc7  call    cs:__imp_DeleteObject
0x180238bcd  mov     rax, [rbp+arg_8]
0x180238bd1  cmp     dword ptr [rax+8], 0FFFFFFFFh
0x180238bd5  jz      loc_180238D44
0x180238bdb  mov     rax, [rbp+arg_8]
0x180238bdf  movsxd  rax, dword ptr [rax+8]
0x180238be3  xor     r9d, r9d; lParam
0x180238be6  mov     r8, rax; wParam
0x180238be9  mov     edx, 149h; Msg
0x180238bee  mov     rax, [rbp+arg_8]
0x180238bf2  mov     rcx, [rax+18h]; hWnd
0x180238bf6  call    cs:__imp_SendMessageA
0x180238bfc  inc     eax
0x180238bfe  mov     [rsp+0C0h+var_80], eax
0x180238c02  mov     eax, [rsp+0C0h+var_80]
0x180238c06  mov     [rsp+0C0h+var_58], eax
0x180238c0a  movsxd  rax, [rsp+0C0h+var_80]
0x180238c0f  mov     rcx, rax; unsigned __int64
0x180238c12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180238c17  mov     [rsp+0C0h+var_50], rax
0x180238c1c  mov     rax, [rsp+0C0h+var_50]
0x180238c21  mov     [rsp+0C0h+lParam], rax
0x180238c26  movsxd  rax, [rsp+0C0h+var_58]
0x180238c2b  mov     [rbp+var_40], rax
0x180238c2f  mov     rdi, [rsp+0C0h+lParam]
0x180238c34  xor     eax, eax
0x180238c36  mov     rcx, [rbp+var_40]
0x180238c3a  rep stosb
0x180238c3c  mov     rax, [rbp+arg_8]
0x180238c40  movsxd  rax, dword ptr [rax+8]
0x180238c44  mov     r9, [rsp+0C0h+lParam]; lParam
0x180238c49  mov     r8, rax; wParam
0x180238c4c  mov     edx, 148h; Msg
0x180238c51  mov     rax, [rbp+arg_8]
0x180238c55  mov     rcx, [rax+18h]; hWnd
0x180238c59  call    cs:__imp_SendMessageA
0x180238c5f  mov     rax, [rbp+arg_8]
0x180238c63  mov     eax, [rax+8]
0x180238c66  xor     r9d, r9d; lParam
0x180238c69  mov     r8d, eax; wParam
0x180238c6c  mov     edx, 150h; Msg
0x180238c71  mov     rax, [rbp+arg_8]
0x180238c75  mov     rcx, [rax+18h]; hWnd
0x180238c79  call    cs:__imp_SendMessageA
0x180238c7f  mov     [rsp+0C0h+var_54], eax
0x180238c83  cmp     [rsp+0C0h+var_54], 0
0x180238c88  jz      short loc_180238CAE
0x180238c8a  mov     rax, [rbp+arg_0]
0x180238c8e  mov     rax, [rax+10h]
0x180238c92  mov     rdx, [rax+3F0h]; h
0x180238c99  mov     rax, [rbp+arg_8]
0x180238c9d  mov     rcx, [rax+20h]; hdc
0x180238ca1  call    cs:__imp_SelectObject
0x180238ca7  mov     [rsp+0C0h+h], rax
0x180238cac  jmp     short loc_180238CD0
0x180238cae  mov     rax, [rbp+arg_0]
0x180238cb2  mov     rax, [rax+10h]
0x180238cb6  mov     rdx, [rax+3F8h]; h
0x180238cbd  mov     rax, [rbp+arg_8]
0x180238cc1  mov     rcx, [rax+20h]; hdc
0x180238cc5  call    cs:__imp_SelectObject
0x180238ccb  mov     [rsp+0C0h+h], rax
0x180238cd0  mov     eax, [rsp+0C0h+var_80]
0x180238cd4  dec     eax
0x180238cd6  mov     ecx, [rbp+rc.left]
0x180238cd9  inc     ecx
0x180238cdb  mov     [rsp+0C0h+lpDx], 0; lpDx
0x180238ce4  mov     [rsp+0C0h+c], eax; c
0x180238ce8  mov     rax, [rsp+0C0h+lParam]
0x180238ced  mov     [rsp+0C0h+lpString], rax; lpString
0x180238cf2  lea     rax, [rbp+rc]
0x180238cf6  mov     [rsp+0C0h+lprect], rax; lprect
0x180238cfb  mov     r9d, 6; options
0x180238d01  mov     r8d, [rbp+rc.top]; y
0x180238d05  mov     edx, ecx; x
0x180238d07  mov     rax, [rbp+arg_8]
0x180238d0b  mov     rcx, [rax+20h]; hdc
0x180238d0f  call    cs:__imp_ExtTextOutA
0x180238d15  cmp     [rsp+0C0h+h], 0
0x180238d1b  jz      short loc_180238D30
0x180238d1d  mov     rdx, [rsp+0C0h+h]; h
0x180238d22  mov     rax, [rbp+arg_8]
0x180238d26  mov     rcx, [rax+20h]; hdc
0x180238d2a  call    cs:__imp_SelectObject
0x180238d30  mov     rax, [rsp+0C0h+lParam]
0x180238d35  mov     [rsp+0C0h+var_48], rax
0x180238d3a  mov     rcx, [rsp+0C0h+var_48]; void *
0x180238d3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180238d44  mov     rax, [rbp+arg_8]
0x180238d48  mov     eax, [rax+10h]
0x180238d4b  and     eax, 1
0x180238d4e  test    eax, eax
0x180238d50  jz      short loc_180238D76
0x180238d52  mov     edx, [rsp+0C0h+color]; color
0x180238d56  mov     rax, [rbp+arg_8]
0x180238d5a  mov     rcx, [rax+20h]; hdc
0x180238d5e  call    cs:__imp_SetTextColor
0x180238d64  mov     edx, [rsp+0C0h+var_78]; color
0x180238d68  mov     rax, [rbp+arg_8]
0x180238d6c  mov     rcx, [rax+20h]; hdc
0x180238d70  call    cs:__imp_SetBkColor
0x180238d76  mov     rax, [rbp+arg_8]
0x180238d7a  cmp     dword ptr [rax+0Ch], 1
0x180238d7e  jnz     short loc_180238D8E
0x180238d80  mov     rax, [rbp+arg_8]
0x180238d84  mov     eax, [rax+10h]
0x180238d87  and     eax, 10h
0x180238d8a  test    eax, eax
0x180238d8c  jnz     short loc_180238D98
0x180238d8e  mov     rax, [rbp+arg_8]
0x180238d92  cmp     dword ptr [rax+0Ch], 4
0x180238d96  jnz     short loc_180238DB1
0x180238d98  mov     rax, [rbp+arg_8]
0x180238d9c  add     rax, 28h ; '('
0x180238da0  mov     rdx, rax; lprc
0x180238da3  mov     rax, [rbp+arg_8]
0x180238da7  mov     rcx, [rax+20h]; hDC
0x180238dab  call    cs:__imp_DrawFocusRect
0x180238db1  mov     rcx, [rbp+var_18]
0x180238db5  xor     rcx, rsp; StackCookie
0x180238db8  call    __security_check_cookie
0x180238dbd  add     rsp, 0B8h
0x180238dc4  pop     rdi
0x180238dc5  pop     rbp
0x180238dc6  retn
```
