# CEditView::OnCreate(tagCREATESTRUCTW *)

- ea: `0x180069180`
- end: `0x1800692e3`
- name: `?OnCreate@CEditView@@IEAAHPEAUtagCREATESTRUCTW@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(CEditView *__hidden this, struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180016330`
- `0x180017020`
- `0x1800277b0`
- `0x18005f460`
- `0x180069180`
- `0x1800d1f92`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18006923e`
- `msvcrt!wcscpy_s` at `0x18006923e`
- `USER32!SendMessageW` at `0x180069286`
- `USER32!SendMessageW` at `0x18006929e`
- `USER32!SendMessageW` at `0x1800692ba`
- `USER32!SendMessageW` at `0x180069286`
- `USER32!SendMessageW` at `0x18006929e`
- `USER32!SendMessageW` at `0x1800692ba`
- `GDI32!GetStockObject` at `0x1800691d0`
- `GDI32!GetStockObject` at `0x1800691d0`
- `GDI32!CreateFontIndirectW` at `0x180069258`
- `GDI32!CreateFontIndirectW` at `0x180069258`
- `GDI32!GetObjectW` at `0x1800691fc`
- `GDI32!GetObjectW` at `0x1800691fc`

## pseudocode

```c
__int64 __fastcall CEditView::OnCreate(HWND *this, struct tagCREATESTRUCTW *a2)
{
  HGDIOBJ StockObject; // rbx
  LOGFONTW lf; // [rsp+20h] [rbp-D8h] BYREF
  _DWORD pv[24]; // [rsp+80h] [rbp-78h] BYREF

  if ( (unsigned int)CView::OnCreate((CView *)this, a2) )
    return 0xFFFFFFFFLL;
  AfxLockGlobals(6);
  if ( !_afxUnicodeFont )
  {
    StockObject = GetStockObject(13);
    memset_0(pv, 0, 0x5Cu);
    GetObjectW(StockObject, 92, pv);
    memset_0(&lf, 0, sizeof(lf));
    lf.lfHeight = pv[0];
    lf.lfWeight = pv[4];
    lf.lfCharSet = 1;
    wcscpy_s(lf.lfFaceName, 0x20u, L"Lucida Sans Unicode");
    AfxCustomLogFont(0xF232u, &lf);
    _afxUnicodeFont = CreateFontIndirectW(&lf);
  }
  AfxUnlockGlobals(6);
  if ( _afxUnicodeFont )
    SendMessageW(this[8], 0x30u, (WPARAM)_afxUnicodeFont, 0);
  SendMessageW(this[8], 0xC5u, 0xFFFFFu, 0);
  SendMessageW(this[8], 0xCBu, 1u, (LPARAM)(this + 19));
  return 0;
}

```

## disassembly

```asm
0x180069180  mov     [rsp+arg_10], rbx
0x180069185  push    rdi
0x180069186  sub     rsp, 0F0h
0x18006918d  mov     rax, cs:__security_cookie
0x180069194  xor     rax, rsp
0x180069197  mov     [rsp+0F8h+var_18], rax
0x18006919f  mov     rdi, rcx
0x1800691a2  call    ?OnCreate@CView@@IEAAHPEAUtagCREATESTRUCTW@@@Z; CView::OnCreate(tagCREATESTRUCTW *)
0x1800691a7  test    eax, eax
0x1800691a9  jz      short loc_1800691B3
0x1800691ab  or      eax, 0FFFFFFFFh
0x1800691ae  jmp     loc_1800692C2
0x1800691b3  mov     ecx, 6; int
0x1800691b8  call    ?AfxLockGlobals@@YAXH@Z; AfxLockGlobals(int)
0x1800691bd  cmp     cs:?_afxUnicodeFont@@3PEAUHFONT__@@EA, 0; HFONT__ * _afxUnicodeFont
0x1800691c5  jnz     loc_180069265
0x1800691cb  mov     ecx, 0Dh; i
0x1800691d0  call    cs:__imp_GetStockObject
0x1800691d6  xor     edx, edx; Val
0x1800691d8  lea     rcx, [rsp+0F8h+pv]; void *
0x1800691e0  mov     rbx, rax
0x1800691e3  lea     r8d, [rdx+5Ch]; Size
0x1800691e7  call    memset_0
0x1800691ec  lea     r8, [rsp+0F8h+pv]; pv
0x1800691f4  mov     edx, 5Ch ; '\'; c
0x1800691f9  mov     rcx, rbx; h
0x1800691fc  call    cs:__imp_GetObjectW
0x180069202  xor     edx, edx; Val
0x180069204  lea     rcx, [rsp+0F8h+lf]; void *
0x180069209  lea     r8d, [rdx+5Ch]; Size
0x18006920d  call    memset_0
0x180069212  mov     eax, [rsp+0F8h+pv]
0x180069219  lea     r8, aLucidaSansUnic; "Lucida Sans Unicode"
0x180069220  mov     [rsp+0F8h+lf.lfHeight], eax
0x180069224  lea     rcx, [rsp+0F8h+lf.lfFaceName]; Destination
0x180069229  mov     eax, [rsp+0F8h+var_68]
0x180069230  mov     edx, 20h ; ' '; SizeInWords
0x180069235  mov     [rsp+0F8h+lf.lfWeight], eax
0x180069239  mov     [rsp+0F8h+lf.lfCharSet], 1
0x18006923e  call    cs:__imp_wcscpy_s
0x180069244  lea     rdx, [rsp+0F8h+lf]; struct tagLOGFONTW *
0x180069249  mov     ecx, 0F232h; unsigned int
0x18006924e  call    ?AfxCustomLogFont@@YAHIPEAUtagLOGFONTW@@@Z; AfxCustomLogFont(uint,tagLOGFONTW *)
0x180069253  lea     rcx, [rsp+0F8h+lf]; lplf
0x180069258  call    cs:__imp_CreateFontIndirectW
0x18006925e  mov     cs:?_afxUnicodeFont@@3PEAUHFONT__@@EA, rax; HFONT__ * _afxUnicodeFont
0x180069265  mov     ecx, 6; int
0x18006926a  call    ?AfxUnlockGlobals@@YAXH@Z; AfxUnlockGlobals(int)
0x18006926f  mov     r8, cs:?_afxUnicodeFont@@3PEAUHFONT__@@EA; wParam
0x180069276  test    r8, r8
0x180069279  jz      short loc_18006928C
0x18006927b  mov     rcx, [rdi+40h]; hWnd
0x18006927f  xor     r9d, r9d; lParam
0x180069282  lea     edx, [r9+30h]; Msg
0x180069286  call    cs:__imp_SendMessageW
0x18006928c  mov     rcx, [rdi+40h]; hWnd
0x180069290  xor     r9d, r9d; lParam
0x180069293  mov     edx, 0C5h; Msg
0x180069298  mov     r8d, 0FFFFFh; wParam
0x18006929e  call    cs:__imp_SendMessageW
0x1800692a4  mov     rcx, [rdi+40h]; hWnd
0x1800692a8  lea     r9, [rdi+98h]; lParam
0x1800692af  mov     edx, 0CBh; Msg
0x1800692b4  mov     r8d, 1; wParam
0x1800692ba  call    cs:__imp_SendMessageW
0x1800692c0  xor     eax, eax
0x1800692c2  mov     rcx, [rsp+0F8h+var_18]
0x1800692ca  xor     rcx, rsp; StackCookie
0x1800692cd  call    __security_check_cookie
0x1800692d2  mov     rbx, [rsp+0F8h+arg_10]
0x1800692da  add     rsp, 0F0h
0x1800692e1  pop     rdi
0x1800692e2  retn
```
