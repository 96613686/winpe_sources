# CPANE::SetLnTop(uint)

- ea: `0x1802b2dcc`
- end: `0x1802b30ad`
- name: `?SetLnTop@CPANE@@QEAAXI@Z`
- size: `737`
- prototype: `void __fastcall(CPANE *__hidden this, unsigned int)`
- caller_count: `12`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18013c2fc`
- `0x1801f340c`
- `0x180202444`
- `0x18023d168`
- `0x18023d378`
- `0x180243174`
- `0x1802b2954`
- `0x1802b310c`
- `0x1802b34b8`
- `0x1803219e8`
- `0x18035fcc8`
- `0x180360a2c`

## callees

- `0x18013beb0`
- `0x18013c0c8`
- `0x18013cf00`
- `0x1801f3860`
- `0x1802b2dcc`
- `0x1802b30b4`
- `0x180379520`

## import_xrefs

- `USER32!HideCaret` at `0x1802b2f11`
- `USER32!HideCaret` at `0x1802b2f11`
- `USER32!ScrollDC` at `0x1802b2f70`
- `USER32!ScrollDC` at `0x1802b2f70`
- `USER32!GetUpdateRect` at `0x1802b2e78`
- `USER32!GetUpdateRect` at `0x1802b2e78`
- `USER32!ShowCaret` at `0x1802b303a`
- `USER32!ShowCaret` at `0x1802b303a`
- `USER32!GetDC` at `0x1802b2ec1`
- `USER32!GetDC` at `0x1802b2ec1`
- `USER32!ReleaseDC` at `0x1802b2ffb`
- `USER32!ReleaseDC` at `0x1802b2ffb`
- `USER32!InvalidateRgn` at `0x1802b3014`
- `USER32!InvalidateRgn` at `0x1802b3014`
- `USER32!IntersectRect` at `0x1802b2e92`
- `USER32!IntersectRect` at `0x1802b2e92`
- `GDI32!OffsetRgn` at `0x1802b2fb3`
- `GDI32!OffsetRgn` at `0x1802b2fb3`
- `GDI32!CreateRectRgn` at `0x1802b2ef1`
- `GDI32!CreateRectRgn` at `0x1802b2ef1`
- `GDI32!CombineRgn` at `0x1802b2fda`
- `GDI32!CombineRgn` at `0x1802b2fda`
- `GDI32!CreateRectRgnIndirect` at `0x1802b2f8f`
- `GDI32!CreateRectRgnIndirect` at `0x1802b2f8f`
- `GDI32!DeleteObject` at `0x1802b2fe5`
- `GDI32!DeleteObject` at `0x1802b301f`
- `GDI32!DeleteObject` at `0x1802b2fe5`
- `GDI32!DeleteObject` at `0x1802b301f`

## pseudocode

```c
void __fastcall CPANE::SetLnTop(CPANE *this, unsigned int a2)
{
  int v2; // [rsp+40h] [rbp-60h]
  unsigned int v3; // [rsp+44h] [rbp-5Ch]
  int v4; // [rsp+48h] [rbp-58h]
  HRGN hRgn; // [rsp+50h] [rbp-50h]
  HDC hDC; // [rsp+58h] [rbp-48h]
  HRGN hrgnSrc2; // [rsp+60h] [rbp-40h]
  struct tagRECT rcDst; // [rsp+78h] [rbp-28h] BYREF
  struct tagRECT Rect; // [rsp+88h] [rbp-18h] BYREF
  unsigned int valid; // [rsp+B8h] [rbp+18h]

  v3 = CPANE::DlnHeight(this);
  v4 = *(_DWORD *)(*((_QWORD *)this + 33) + 260LL);
  valid = CPANE::ValidLnTopFromLnTop(this, a2);
  if ( *((_DWORD *)this + 30) != valid )
  {
    v2 = *((_DWORD *)this + 30) - valid;
    *((_DWORD *)this + 30) = valid;
    if ( v3 )
    {
      if ( *((_QWORD *)this + 8) )
      {
        GetUpdateRect(*((HWND *)this + 35), &Rect, 0);
        if ( IntersectRect(&rcDst, (const RECT *)((char *)this + 92), &Rect) )
        {
          CPANE::RefreshLines(this, *((_DWORD *)this + 30), v3);
        }
        else
        {
          hDC = GetDC(*((HWND *)this + 35));
          if ( !hDC )
            return;
          hRgn = CreateRectRgn(0, 0, 0, 0);
          if ( *((_DWORD *)this + 18) == 1 )
            HideCaret(*((HWND *)this + 35));
          rcDst = *(struct tagRECT *)((char *)this + 92);
          rcDst.left = *((_DWORD *)this + 19);
          ScrollDC(hDC, 0, v4 * v2, &rcDst, &rcDst, hRgn, 0);
          if ( *((_QWORD *)this + 20) )
          {
            hrgnSrc2 = CreateRectRgnIndirect((const RECT *)((char *)this + 92));
            OffsetRgn(*((HRGN *)this + 20), 0, v4 * v2);
            CombineRgn(*((HRGN *)this + 20), *((HRGN *)this + 20), hrgnSrc2, 1);
            DeleteObject(hrgnSrc2);
          }
          ReleaseDC(*((HWND *)this + 35), hDC);
          InvalidateRgn(*((HWND *)this + 35), hRgn, 0);
          DeleteObject(hRgn);
          if ( *((_DWORD *)this + 18) == 1 )
            ShowCaret(*((HWND *)this + 35));
          if ( v2 <= 0 )
            CPANE::RefreshLines(this, v2 + v3 + *((_DWORD *)this + 30), -v2);
          else
            CPANE::RefreshLines(this, *((_DWORD *)this + 30), v2);
        }
        CPANE::RefreshScrollPos(this, 1u);
        CPANE::RefreshCursorPos(this);
      }
    }
  }
}

```

## disassembly

```asm
0x1802b2dcc  mov     [rsp-8+arg_8], edx
0x1802b2dd0  mov     [rsp-8+arg_0], rcx
0x1802b2dd5  push    rbp
0x1802b2dd6  mov     rbp, rsp
0x1802b2dd9  sub     rsp, 0A0h
0x1802b2de0  mov     rax, cs:__security_cookie
0x1802b2de7  xor     rax, rsp
0x1802b2dea  mov     [rbp+var_8], rax
0x1802b2dee  mov     rcx, [rbp+arg_0]; this
0x1802b2df2  call    ?DlnHeight@CPANE@@QEAAIXZ; CPANE::DlnHeight(void)
0x1802b2df7  mov     [rsp+0A0h+var_5C], eax
0x1802b2dfb  mov     rax, [rbp+arg_0]
0x1802b2dff  mov     rax, [rax+108h]
0x1802b2e06  mov     eax, [rax+104h]
0x1802b2e0c  mov     [rsp+0A0h+var_58], eax
0x1802b2e10  mov     edx, [rbp+arg_8]; unsigned int
0x1802b2e13  mov     rcx, [rbp+arg_0]; this
0x1802b2e17  call    ?ValidLnTopFromLnTop@CPANE@@QEAAII@Z; CPANE::ValidLnTopFromLnTop(uint)
0x1802b2e1c  mov     [rbp+arg_8], eax
0x1802b2e1f  mov     rax, [rbp+arg_0]
0x1802b2e23  mov     ecx, [rbp+arg_8]
0x1802b2e26  cmp     [rax+78h], ecx
0x1802b2e29  jnz     short loc_1802B2E30
0x1802b2e2b  jmp     loc_1802B3098
0x1802b2e30  mov     rax, [rbp+arg_0]
0x1802b2e34  mov     ecx, [rbp+arg_8]
0x1802b2e37  mov     eax, [rax+78h]
0x1802b2e3a  sub     eax, ecx
0x1802b2e3c  mov     [rsp+0A0h+var_60], eax
0x1802b2e40  mov     rax, [rbp+arg_0]
0x1802b2e44  mov     ecx, [rbp+arg_8]
0x1802b2e47  mov     [rax+78h], ecx
0x1802b2e4a  cmp     [rsp+0A0h+var_5C], 0
0x1802b2e4f  jnz     short loc_1802B2E56
0x1802b2e51  jmp     loc_1802B3098
0x1802b2e56  mov     rax, [rbp+arg_0]
0x1802b2e5a  cmp     qword ptr [rax+40h], 0
0x1802b2e5f  jnz     short loc_1802B2E66
0x1802b2e61  jmp     loc_1802B3098
0x1802b2e66  xor     r8d, r8d; bErase
0x1802b2e69  lea     rdx, [rbp+Rect]; lpRect
0x1802b2e6d  mov     rax, [rbp+arg_0]
0x1802b2e71  mov     rcx, [rax+118h]; hWnd
0x1802b2e78  call    cs:__imp_GetUpdateRect
0x1802b2e7e  mov     rax, [rbp+arg_0]
0x1802b2e82  add     rax, 5Ch ; '\'
0x1802b2e86  lea     r8, [rbp+Rect]; lprcSrc2
0x1802b2e8a  mov     rdx, rax; lprcSrc1
0x1802b2e8d  lea     rcx, [rsp+0A0h+rcDst]; lprcDst
0x1802b2e92  call    cs:__imp_IntersectRect
0x1802b2e98  test    eax, eax
0x1802b2e9a  jz      short loc_1802B2EB6
0x1802b2e9c  mov     r8d, [rsp+0A0h+var_5C]; unsigned int
0x1802b2ea1  mov     rax, [rbp+arg_0]
0x1802b2ea5  mov     edx, [rax+78h]; unsigned int
0x1802b2ea8  mov     rcx, [rbp+arg_0]; this
0x1802b2eac  call    ?RefreshLines@CPANE@@QEAAXII@Z; CPANE::RefreshLines(uint,uint)
0x1802b2eb1  jmp     loc_1802B3081
0x1802b2eb6  mov     rax, [rbp+arg_0]
0x1802b2eba  mov     rcx, [rax+118h]; hWnd
0x1802b2ec1  call    cs:__imp_GetDC
0x1802b2ec7  mov     [rsp+0A0h+hDC], rax
0x1802b2ecc  mov     [rsp+0A0h+hRgn], 0
0x1802b2ed5  cmp     [rsp+0A0h+hDC], 0
0x1802b2edb  jnz     short loc_1802B2EE7
0x1802b2edd  jmp     loc_1802B3098
0x1802b2ee2  jmp     loc_1802B3098
0x1802b2ee7  xor     r9d, r9d; y2
0x1802b2eea  xor     r8d, r8d; x2
0x1802b2eed  xor     edx, edx; y1
0x1802b2eef  xor     ecx, ecx; x1
0x1802b2ef1  call    cs:__imp_CreateRectRgn
0x1802b2ef7  mov     [rsp+0A0h+hRgn], rax
0x1802b2efc  mov     rax, [rbp+arg_0]
0x1802b2f00  cmp     dword ptr [rax+48h], 1
0x1802b2f04  jnz     short loc_1802B2F17
0x1802b2f06  mov     rax, [rbp+arg_0]
0x1802b2f0a  mov     rcx, [rax+118h]; hWnd
0x1802b2f11  call    cs:__imp_HideCaret
0x1802b2f17  mov     rax, [rbp+arg_0]
0x1802b2f1b  movups  xmm0, xmmword ptr [rax+5Ch]
0x1802b2f1f  movdqu  [rsp+0A0h+var_38], xmm0
0x1802b2f25  movups  xmm0, [rsp+0A0h+var_38]
0x1802b2f2a  movdqu  xmmword ptr [rsp+0A0h+rcDst.left], xmm0
0x1802b2f30  mov     rax, [rbp+arg_0]
0x1802b2f34  mov     eax, [rax+4Ch]
0x1802b2f37  mov     [rsp+0A0h+rcDst.left], eax
0x1802b2f3b  mov     eax, [rsp+0A0h+var_60]
0x1802b2f3f  imul    eax, [rsp+0A0h+var_58]
0x1802b2f44  mov     [rsp+0A0h+lprcUpdate], 0; lprcUpdate
0x1802b2f4d  mov     rcx, [rsp+0A0h+hRgn]
0x1802b2f52  mov     [rsp+0A0h+hrgnUpdate], rcx; hrgnUpdate
0x1802b2f57  lea     rcx, [rsp+0A0h+rcDst]
0x1802b2f5c  mov     [rsp+0A0h+lprcClip], rcx; lprcClip
0x1802b2f61  lea     r9, [rsp+0A0h+rcDst]; lprcScroll
0x1802b2f66  mov     r8d, eax; dy
0x1802b2f69  xor     edx, edx; dx
0x1802b2f6b  mov     rcx, [rsp+0A0h+hDC]; hDC
0x1802b2f70  call    cs:__imp_ScrollDC
0x1802b2f76  mov     rax, [rbp+arg_0]
0x1802b2f7a  cmp     qword ptr [rax+0A0h], 0
0x1802b2f82  jz      short loc_1802B2FEB
0x1802b2f84  mov     rax, [rbp+arg_0]
0x1802b2f88  add     rax, 5Ch ; '\'
0x1802b2f8c  mov     rcx, rax; lprect
0x1802b2f8f  call    cs:__imp_CreateRectRgnIndirect
0x1802b2f95  mov     [rsp+0A0h+hrgnSrc2], rax
0x1802b2f9a  mov     eax, [rsp+0A0h+var_60]
0x1802b2f9e  imul    eax, [rsp+0A0h+var_58]
0x1802b2fa3  mov     r8d, eax; y
0x1802b2fa6  xor     edx, edx; x
0x1802b2fa8  mov     rax, [rbp+arg_0]
0x1802b2fac  mov     rcx, [rax+0A0h]; hrgn
0x1802b2fb3  call    cs:__imp_OffsetRgn
0x1802b2fb9  mov     r9d, 1; iMode
0x1802b2fbf  mov     r8, [rsp+0A0h+hrgnSrc2]; hrgnSrc2
0x1802b2fc4  mov     rax, [rbp+arg_0]
0x1802b2fc8  mov     rdx, [rax+0A0h]; hrgnSrc1
0x1802b2fcf  mov     rax, [rbp+arg_0]
0x1802b2fd3  mov     rcx, [rax+0A0h]; hrgnDst
0x1802b2fda  call    cs:__imp_CombineRgn
0x1802b2fe0  mov     rcx, [rsp+0A0h+hrgnSrc2]; ho
0x1802b2fe5  call    cs:__imp_DeleteObject
0x1802b2feb  mov     rdx, [rsp+0A0h+hDC]; hDC
0x1802b2ff0  mov     rax, [rbp+arg_0]
0x1802b2ff4  mov     rcx, [rax+118h]; hWnd
0x1802b2ffb  call    cs:__imp_ReleaseDC
0x1802b3001  xor     r8d, r8d; bErase
0x1802b3004  mov     rdx, [rsp+0A0h+hRgn]; hRgn
0x1802b3009  mov     rax, [rbp+arg_0]
0x1802b300d  mov     rcx, [rax+118h]; hWnd
0x1802b3014  call    cs:__imp_InvalidateRgn
0x1802b301a  mov     rcx, [rsp+0A0h+hRgn]; ho
0x1802b301f  call    cs:__imp_DeleteObject
0x1802b3025  mov     rax, [rbp+arg_0]
0x1802b3029  cmp     dword ptr [rax+48h], 1
0x1802b302d  jnz     short loc_1802B3040
0x1802b302f  mov     rax, [rbp+arg_0]
0x1802b3033  mov     rcx, [rax+118h]; hWnd
0x1802b303a  call    cs:__imp_ShowCaret
0x1802b3040  cmp     [rsp+0A0h+var_60], 0
0x1802b3045  jle     short loc_1802B305E
0x1802b3047  mov     r8d, [rsp+0A0h+var_60]; unsigned int
0x1802b304c  mov     rax, [rbp+arg_0]
0x1802b3050  mov     edx, [rax+78h]; unsigned int
0x1802b3053  mov     rcx, [rbp+arg_0]; this
0x1802b3057  call    ?RefreshLines@CPANE@@QEAAXII@Z; CPANE::RefreshLines(uint,uint)
0x1802b305c  jmp     short loc_1802B3081
0x1802b305e  mov     eax, [rsp+0A0h+var_60]
0x1802b3062  neg     eax
0x1802b3064  mov     rcx, [rbp+arg_0]
0x1802b3068  mov     ecx, [rcx+78h]
0x1802b306b  add     ecx, [rsp+0A0h+var_5C]
0x1802b306f  add     ecx, [rsp+0A0h+var_60]
0x1802b3073  mov     r8d, eax; unsigned int
0x1802b3076  mov     edx, ecx; unsigned int
0x1802b3078  mov     rcx, [rbp+arg_0]; this
0x1802b307c  call    ?RefreshLines@CPANE@@QEAAXII@Z; CPANE::RefreshLines(uint,uint)
0x1802b3081  mov     edx, 1; unsigned int
0x1802b3086  mov     rcx, [rbp+arg_0]; this
0x1802b308a  call    ?RefreshScrollPos@CPANE@@QEAAXI@Z; CPANE::RefreshScrollPos(uint)
0x1802b308f  mov     rcx, [rbp+arg_0]; this
0x1802b3093  call    ?RefreshCursorPos@CPANE@@QEAAXXZ; CPANE::RefreshCursorPos(void)
0x1802b3098  mov     rcx, [rbp+var_8]
0x1802b309c  xor     rcx, rsp; StackCookie
0x1802b309f  call    __security_check_cookie
0x1802b30a4  add     rsp, 0A0h
0x1802b30ab  pop     rbp
0x1802b30ac  retn
```
