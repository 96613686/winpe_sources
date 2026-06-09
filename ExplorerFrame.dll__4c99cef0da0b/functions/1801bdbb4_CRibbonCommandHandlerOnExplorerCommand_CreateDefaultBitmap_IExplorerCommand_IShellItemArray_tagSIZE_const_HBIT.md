# CRibbonCommandHandlerOnExplorerCommand::_CreateDefaultBitmap(IExplorerCommand *,IShellItemArray *,tagSIZE const &,HBITMAP__ * *)

- ea: `0x1801bdbb4`
- end: `0x1801bdda1`
- name: `?_CreateDefaultBitmap@CRibbonCommandHandlerOnExplorerCommand@@IEAAJPEAUIExplorerCommand@@PEAUIShellItemArray@@AEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z`
- size: `493`
- prototype: `int(CRibbonCommandHandlerOnExplorerCommand *__hidden this, struct IExplorerCommand *, struct IShellItemArray *, const struct tagSIZE *, HBITMAP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18006f02c`

## callees

- `0x18006f414`
- `0x1800899cc`
- `0x1800fa368`
- `0x18013f7d0`
- `0x1801bc544`
- `0x1801bdbb4`
- `0x1801be188`

## import_xrefs

- `SHLWAPI!__imp_SHFillRectClr` at `0x1801bdc7d`
- `SHLWAPI!__imp_SHFillRectClr` at `0x1801bdc7d`
- `GDI32!DeleteDC` at `0x1801bdd6e`
- `GDI32!DeleteDC` at `0x1801bdd6e`
- `GDI32!DeleteObject` at `0x1801bdd7c`
- `GDI32!DeleteObject` at `0x1801bdd7c`
- `GDI32!SelectObject` at `0x1801bdc3e`
- `GDI32!SelectObject` at `0x1801bdd45`
- `GDI32!SelectObject` at `0x1801bdc3e`
- `GDI32!SelectObject` at `0x1801bdd45`
- `GDI32!CreateCompatibleDC` at `0x1801bdc12`
- `GDI32!CreateCompatibleDC` at `0x1801bdc12`
- `UxTheme!CloseThemeData` at `0x1801bdd35`
- `UxTheme!CloseThemeData` at `0x1801bdd35`
- `UxTheme!DrawThemeBackground` at `0x1801bdd2a`
- `UxTheme!DrawThemeBackground` at `0x1801bdd2a`
- `UxTheme!OpenThemeData` at `0x1801bdcd4`
- `UxTheme!OpenThemeData` at `0x1801bdcd4`

## pseudocode

```c
__int64 __fastcall CRibbonCommandHandlerOnExplorerCommand::_CreateDefaultBitmap(
        CRibbonCommandHandlerOnExplorerCommand *this,
        struct IExplorerCommand *a2,
        struct IShellItemArray *a3,
        const struct tagSIZE *a4,
        HBITMAP *a5)
{
  HRESULT Error; // ebx
  HDC CompatibleDC; // rsi
  HGDIOBJ v10; // rdi
  HGDIOBJ v11; // r15
  CRibbonCommandHandlerOnExplorerCommand *v12; // rcx
  HWND Window; // rax
  HTHEME v14; // r14
  unsigned int v15; // r9d
  HBITMAP v16; // r14
  HGDIOBJ h; // [rsp+30h] [rbp-38h] BYREF
  CRibbonCommandHandlerOnExplorerCommand *v19; // [rsp+38h] [rbp-30h]
  HBITMAP *v20; // [rsp+40h] [rbp-28h]
  RECT pRect; // [rsp+48h] [rbp-20h] BYREF

  v19 = this;
  v20 = a5;
  h = 0;
  *a5 = 0;
  Error = Create32BitHBITMAP((HDC)this, a4, (void **)&a3->lpVtbl, (HBITMAP *)&h);
  if ( Error < 0 )
    return (unsigned int)Error;
  CompatibleDC = CreateCompatibleDC(0);
  if ( !CompatibleDC )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      v10 = h;
      goto LABEL_20;
    }
  }
  v10 = h;
  v11 = SelectObject(CompatibleDC, h);
  if ( v11 || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    pRect.right = a4->cx;
    pRect.bottom = a4->cy;
    *(_QWORD *)&pRect.left = 0;
    SHFillRectClr(CompatibleDC, &pRect, 0xFFFFFFFFLL);
    if ( !_ShouldProvideAutoIcons(a2)
      || (LODWORD(h) = 0,
          Error = CRibbonCommandHandlerOnExplorerCommand::_GetStateNormalized(v12, a2, a3, 0, (unsigned int *)&h),
          Error >= 0)
      && (((unsigned __int8)h & 8) == 0
       || (Window = CRibbonCommandHandlerOnExplorerCommand::_GetWindow(v19), (v14 = OpenThemeData(Window, L"Menu")) == 0)
       || (((unsigned __int8)h & 1) == 0
         ? (v15 = ((unsigned __int8)h & 0x10 | 8u) >> 3)
         : (v15 = ((unsigned __int8)h & 0x10) != 0 ? 4 : 2),
           Error = DrawThemeBackground(v14, CompatibleDC, 11, v15, &pRect, 0),
           CloseThemeData(v14),
           Error >= 0)) )
    {
      v16 = (HBITMAP)SelectObject(CompatibleDC, v11);
      if ( v16 )
      {
        Error = 0;
LABEL_18:
        v10 = 0;
        *v20 = v16;
        goto LABEL_19;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_18;
    }
  }
LABEL_19:
  DeleteDC(CompatibleDC);
LABEL_20:
  if ( v10 )
    DeleteObject(v10);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1801bdbb4  push    rbp
0x1801bdbb6  push    rbx
0x1801bdbb7  push    rsi
0x1801bdbb8  push    rdi
0x1801bdbb9  push    r12
0x1801bdbbb  push    r13
0x1801bdbbd  push    r14
0x1801bdbbf  push    r15
0x1801bdbc1  mov     rbp, rsp
0x1801bdbc4  sub     rsp, 68h
0x1801bdbc8  mov     rax, cs:__security_cookie
0x1801bdbcf  xor     rax, rsp
0x1801bdbd2  mov     [rbp+var_10], rax
0x1801bdbd6  mov     rax, [rbp+arg_20]
0x1801bdbda  mov     r12, r9
0x1801bdbdd  mov     r14, rdx
0x1801bdbe0  mov     [rbp+var_30], rcx
0x1801bdbe4  lea     r9, [rbp+h]; HBITMAP *
0x1801bdbe8  mov     [rbp+var_28], rax
0x1801bdbec  mov     rdx, r12; struct tagSIZE *
0x1801bdbef  mov     [rbp+h], 0
0x1801bdbf7  mov     qword ptr [rax], 0
0x1801bdbfe  mov     r13, r8
0x1801bdc01  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x1801bdc06  mov     ebx, eax
0x1801bdc08  test    eax, eax
0x1801bdc0a  js      loc_1801BDD82
0x1801bdc10  xor     ecx, ecx; hdc
0x1801bdc12  call    cs:__imp_CreateCompatibleDC
0x1801bdc18  mov     rsi, rax
0x1801bdc1b  test    rax, rax
0x1801bdc1e  jnz     short loc_1801BDC34
0x1801bdc20  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801bdc25  mov     ebx, eax
0x1801bdc27  test    eax, eax
0x1801bdc29  jns     short loc_1801BDC34
0x1801bdc2b  mov     rdi, [rbp+h]
0x1801bdc2f  jmp     loc_1801BDD74
0x1801bdc34  mov     rdi, [rbp+h]
0x1801bdc38  mov     rcx, rsi; hdc
0x1801bdc3b  mov     rdx, rdi; h
0x1801bdc3e  call    cs:__imp_SelectObject
0x1801bdc44  mov     r15, rax
0x1801bdc47  test    rax, rax
0x1801bdc4a  jnz     short loc_1801BDC5B
0x1801bdc4c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801bdc51  mov     ebx, eax
0x1801bdc53  test    eax, eax
0x1801bdc55  js      loc_1801BDD6B
0x1801bdc5b  mov     ecx, [r12]
0x1801bdc5f  lea     rdx, [rbp+var_20]
0x1801bdc63  mov     [rbp+var_20.right], ecx
0x1801bdc66  or      r8d, 0FFFFFFFFh
0x1801bdc6a  mov     ecx, [r12+4]
0x1801bdc6f  mov     [rbp+var_20.bottom], ecx
0x1801bdc72  mov     rcx, rsi
0x1801bdc75  mov     qword ptr [rbp+var_20.left], 0
0x1801bdc7d  call    cs:__imp_SHFillRectClr
0x1801bdc83  mov     rcx, r14; struct IExplorerCommand *
0x1801bdc86  call    ?_ShouldProvideAutoIcons@@YA_NPEAUIExplorerCommand@@@Z; _ShouldProvideAutoIcons(IExplorerCommand *)
0x1801bdc8b  test    al, al
0x1801bdc8d  jz      loc_1801BDD3F
0x1801bdc93  lea     rax, [rbp+h]
0x1801bdc97  mov     dword ptr [rbp+h], 0
0x1801bdc9e  xor     r9d, r9d; int
0x1801bdca1  mov     [rsp+68h+pRect], rax; unsigned int *
0x1801bdca6  mov     r8, r13; struct IShellItemArray *
0x1801bdca9  mov     rdx, r14; struct IExplorerCommand *
0x1801bdcac  call    ?_GetStateNormalized@CRibbonCommandHandlerOnExplorerCommand@@IEAAJPEAUIExplorerCommand@@PEAUIShellItemArray@@HPEAK@Z; CRibbonCommandHandlerOnExplorerCommand::_GetStateNormalized(IExplorerCommand *,IShellItemArray *,int,ulong *)
0x1801bdcb1  mov     ebx, eax
0x1801bdcb3  test    eax, eax
0x1801bdcb5  js      loc_1801BDD6B
0x1801bdcbb  test    byte ptr [rbp+h], 8
0x1801bdcbf  jz      short loc_1801BDD3F
0x1801bdcc1  mov     rcx, [rbp+var_30]; this
0x1801bdcc5  call    ?_GetWindow@CRibbonCommandHandlerOnExplorerCommand@@IEAAPEAUHWND__@@XZ; CRibbonCommandHandlerOnExplorerCommand::_GetWindow(void)
0x1801bdcca  mov     rcx, rax; hwnd
0x1801bdccd  lea     rdx, aMenu_0; "Menu"
0x1801bdcd4  call    cs:__imp_OpenThemeData
0x1801bdcda  mov     r14, rax
0x1801bdcdd  test    rax, rax
0x1801bdce0  jz      short loc_1801BDD3F
0x1801bdce2  mov     ecx, dword ptr [rbp+h]
0x1801bdce5  test    cl, 1
0x1801bdce8  jz      short loc_1801BDCFC
0x1801bdcea  and     cl, 10h
0x1801bdced  neg     cl
0x1801bdcef  sbb     r9d, r9d
0x1801bdcf2  and     r9d, 2
0x1801bdcf6  add     r9d, 2
0x1801bdcfa  jmp     short loc_1801BDD0C
0x1801bdcfc  movzx   r9d, cl
0x1801bdd00  and     r9d, 10h
0x1801bdd04  or      r9d, 8
0x1801bdd08  shr     r9d, 3; iStateId
0x1801bdd0c  lea     rax, [rbp+var_20]
0x1801bdd10  mov     [rsp+68h+pClipRect], 0; pClipRect
0x1801bdd19  mov     r8d, 0Bh; iPartId
0x1801bdd1f  mov     [rsp+68h+pRect], rax; pRect
0x1801bdd24  mov     rdx, rsi; hdc
0x1801bdd27  mov     rcx, r14; hTheme
0x1801bdd2a  call    cs:__imp_DrawThemeBackground
0x1801bdd30  mov     rcx, r14; hTheme
0x1801bdd33  mov     ebx, eax
0x1801bdd35  call    cs:__imp_CloseThemeData
0x1801bdd3b  test    ebx, ebx
0x1801bdd3d  js      short loc_1801BDD6B
0x1801bdd3f  mov     rdx, r15; h
0x1801bdd42  mov     rcx, rsi; hdc
0x1801bdd45  call    cs:__imp_SelectObject
0x1801bdd4b  mov     r14, rax
0x1801bdd4e  test    rax, rax
0x1801bdd51  jz      short loc_1801BDD57
0x1801bdd53  xor     ebx, ebx
0x1801bdd55  jmp     short loc_1801BDD62
0x1801bdd57  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801bdd5c  mov     ebx, eax
0x1801bdd5e  test    eax, eax
0x1801bdd60  js      short loc_1801BDD6B
0x1801bdd62  mov     rax, [rbp+var_28]
0x1801bdd66  xor     edi, edi
0x1801bdd68  mov     [rax], r14
0x1801bdd6b  mov     rcx, rsi; hdc
0x1801bdd6e  call    cs:__imp_DeleteDC
0x1801bdd74  test    rdi, rdi
0x1801bdd77  jz      short loc_1801BDD82
0x1801bdd79  mov     rcx, rdi; ho
0x1801bdd7c  call    cs:__imp_DeleteObject
0x1801bdd82  mov     eax, ebx
0x1801bdd84  mov     rcx, [rbp+var_10]
0x1801bdd88  xor     rcx, rsp; StackCookie
0x1801bdd8b  call    __security_check_cookie
0x1801bdd90  add     rsp, 68h
0x1801bdd94  pop     r15
0x1801bdd96  pop     r14
0x1801bdd98  pop     r13
0x1801bdd9a  pop     r12
0x1801bdd9c  pop     rdi
0x1801bdd9d  pop     rsi
0x1801bdd9e  pop     rbx
0x1801bdd9f  pop     rbp
0x1801bdda0  retn
```
