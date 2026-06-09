# CActionsContextMenuProvider::_GenerateContextMenu(IApplicationFrameInternal *,HMENU__ * *)

- ea: `0x18005f11c`
- end: `0x18005f3d3`
- name: `?_GenerateContextMenu@CActionsContextMenuProvider@@AEAAJPEAUIApplicationFrameInternal@@PEAPEAUHMENU__@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(CActionsContextMenuProvider *__hidden this, struct IApplicationFrameInternal *, HMENU *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005eb70`

## callees

- `0x18003fbc0`
- `0x180040270`
- `0x18005ee24`
- `0x18005f11c`
- `0x18005f3dc`

## import_xrefs

- `UxTheme!CloseThemeData` at `0x18005f2d9`
- `UxTheme!CloseThemeData` at `0x18005f2d9`
- `UxTheme!OpenThemeData` at `0x18005f209`
- `UxTheme!OpenThemeData` at `0x18005f209`
- `UxTheme!GetThemeColor` at `0x18005f242`
- `UxTheme!GetThemeColor` at `0x18005f29a`
- `UxTheme!GetThemeColor` at `0x18005f242`
- `UxTheme!GetThemeColor` at `0x18005f29a`
- `USER32!LoadMenuW` at `0x18005f14d`
- `USER32!LoadMenuW` at `0x18005f14d`
- `USER32!GetSubMenu` at `0x18005f184`
- `USER32!GetSubMenu` at `0x18005f184`
- `USER32!RemoveMenu` at `0x18005f1c5`
- `USER32!RemoveMenu` at `0x18005f1c5`
- `USER32!SetMenuItemBitmaps` at `0x18005f34b`
- `USER32!SetMenuItemBitmaps` at `0x18005f34b`
- `USER32!DestroyMenu` at `0x18005f1ed`
- `USER32!DestroyMenu` at `0x18005f3b3`
- `USER32!DestroyMenu` at `0x18005f1ed`
- `USER32!DestroyMenu` at `0x18005f3b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CActionsContextMenuProvider::_GenerateContextMenu(
        CActionsContextMenuProvider *this,
        struct IApplicationFrameInternal *a2,
        HMENU *a3)
{
  HMENU MenuW; // rax
  const char *v6; // r9
  HMENU v7; // rdi
  HMENU SubMenu; // rbx
  const char *v10; // r9
  unsigned int LastError; // esi
  const char *v12; // r9
  unsigned int v13; // r12d
  HTHEME v14; // rsi
  unsigned int v15; // r14d
  int i; // ecx
  UINT j; // r15d
  HBITMAP Bitmap; // rsi
  HBITMAP v19; // rax
  int v20; // eax
  int pColor; // [rsp+20h] [rbp-68h]
  BOOL v22; // [rsp+30h] [rbp-58h]
  HMENU v23; // [rsp+38h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  COLORREF v26; // [rsp+A0h] [rbp+18h] BYREF
  COLORREF v27; // [rsp+A8h] [rbp+20h] BYREF

  *a3 = 0;
  MenuW = LoadMenuW(&_ImageBase, (LPCWSTR)0x2F45);
  v7 = MenuW;
  v23 = MenuW;
  if ( !MenuW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xFA,
             (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\actionsmenuprovider.cpp",
             v6);
  SubMenu = GetSubMenu(MenuW, 0);
  if ( SubMenu )
  {
    if ( RemoveMenu(v7, 0, 0x400u) )
    {
      v13 = 0;
      v22 = 0;
      v14 = OpenThemeData(0, L"MENU");
      if ( v14 )
      {
        v26 = 0;
        if ( GetThemeColor(v14, 9, 1, 3802, &v26) >= 0 )
          LOBYTE(v13) = BYTE2(v26) + 5 * BYTE1(v26) + 2 * (unsigned int)(unsigned __int8)v26 <= 0x400;
        v27 = 0;
        if ( GetThemeColor(v14, 14, 2, 3803, &v27) >= 0 )
          v22 = BYTE2(v27) + 5 * BYTE1(v27) + 2 * (unsigned int)(unsigned __int8)v27 > 0x400;
        CloseThemeData(v14);
      }
      v15 = 0;
      for ( i = 6; i >= 0; --i )
      {
        if ( *((_DWORD *)this + 36) >= dword_180079DE0[i] )
        {
          v15 = i;
          break;
        }
      }
      for ( j = 12102; (int)j <= 12107; ++j )
      {
        Bitmap = (HBITMAP)CActionsContextMenuProvider::_GetBitmap(this, j, v22, v15);
        v19 = (HBITMAP)CActionsContextMenuProvider::_GetBitmap(this, j, v13, v15);
        SetMenuItemBitmaps(SubMenu, j, 0, v19, Bitmap);
      }
      *((_DWORD *)this + 38) = v13;
      *((_DWORD *)this + 37) = v15;
      v20 = CActionsContextMenuProvider::_CleanMenu(this, a2, SubMenu);
      LastError = v20;
      v7 = v23;
      if ( v20 >= 0 )
      {
        *a3 = SubMenu;
        LastError = 0;
        goto LABEL_24;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\actionsmenuprovider.cpp",
        (const char *)(unsigned int)v20,
        pColor);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x100,
                    (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\actionsmenuprovider.cpp",
                    v12);
    }
    DestroyMenu(SubMenu);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xFD,
                  (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\actionsmenuprovider.cpp",
                  v10);
  }
LABEL_24:
  DestroyMenu(v7);
  return LastError;
}

```

## disassembly

```asm
0x18005f11c  mov     [rsp+arg_0], rbx
0x18005f121  mov     [rsp+arg_8], rdx
0x18005f126  push    rbp
0x18005f127  push    rsi
0x18005f128  push    rdi
0x18005f129  push    r12
0x18005f12b  push    r13
0x18005f12d  push    r14
0x18005f12f  push    r15
0x18005f131  sub     rsp, 50h
0x18005f135  mov     r13, r8
0x18005f138  mov     rbp, rcx
0x18005f13b  xor     r15d, r15d
0x18005f13e  mov     [r8], r15
0x18005f141  mov     edx, 2F45h; lpMenuName
0x18005f146  lea     rcx, __ImageBase; hInstance
0x18005f14d  call    cs:__imp_LoadMenuW
0x18005f153  mov     rdi, rax
0x18005f156  mov     [rsp+88h+var_50], rax
0x18005f15b  test    rax, rax
0x18005f15e  jnz     short loc_18005F17F
0x18005f160  mov     rcx, [rsp+88h]; this
0x18005f168  lea     r8, aPcshellShellAp_7; "pcshell\\shell\\applicationframe\\frame"...
0x18005f16f  mov     edx, 0FAh; void *
0x18005f174  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005f179  nop
0x18005f17a  jmp     loc_18005F3BB
0x18005f17f  xor     edx, edx; nPos
0x18005f181  mov     rcx, rdi; hMenu
0x18005f184  call    cs:__imp_GetSubMenu
0x18005f18a  mov     rbx, rax
0x18005f18d  mov     [rsp+88h+var_48], rax
0x18005f192  test    rax, rax
0x18005f195  jnz     short loc_18005F1B7
0x18005f197  mov     rcx, [rsp+88h]; this
0x18005f19f  lea     r8, aPcshellShellAp_7; "pcshell\\shell\\applicationframe\\frame"...
0x18005f1a6  mov     edx, 0FDh; void *
0x18005f1ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005f1b0  mov     esi, eax
0x18005f1b2  jmp     loc_18005F3B0
0x18005f1b7  mov     r14d, 400h
0x18005f1bd  mov     r8d, r14d; uFlags
0x18005f1c0  xor     edx, edx; uPosition
0x18005f1c2  mov     rcx, rdi; hMenu
0x18005f1c5  call    cs:__imp_RemoveMenu
0x18005f1cb  test    eax, eax
0x18005f1cd  jnz     short loc_18005F1F8
0x18005f1cf  mov     rcx, [rsp+88h]; this
0x18005f1d7  lea     r8, aPcshellShellAp_7; "pcshell\\shell\\applicationframe\\frame"...
0x18005f1de  mov     edx, 100h; void *
0x18005f1e3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005f1e8  mov     esi, eax
0x18005f1ea  mov     rcx, rbx; hMenu
0x18005f1ed  call    cs:__imp_DestroyMenu
0x18005f1f3  jmp     loc_18005F3B0
0x18005f1f8  mov     r12d, r15d
0x18005f1fb  mov     [rsp+88h+var_58], r15d
0x18005f200  lea     rdx, aMenu; "MENU"
0x18005f207  xor     ecx, ecx; hwnd
0x18005f209  call    cs:__imp_OpenThemeData
0x18005f20f  mov     rsi, rax
0x18005f212  test    rax, rax
0x18005f215  jz      loc_18005F2DF
0x18005f21b  mov     [rsp+88h+arg_10], r15d
0x18005f223  lea     rax, [rsp+88h+arg_10]
0x18005f22b  mov     qword ptr [rsp+88h+pColor], rax; pColor
0x18005f230  mov     edx, 9; iPartId
0x18005f235  mov     r9d, 0EDAh; iPropId
0x18005f23b  lea     r8d, [rdx-8]; iStateId
0x18005f23f  mov     rcx, rsi; hTheme
0x18005f242  call    cs:__imp_GetThemeColor
0x18005f248  test    eax, eax
0x18005f24a  js      short loc_18005F273
0x18005f24c  mov     edx, [rsp+88h+arg_10]
0x18005f253  movzx   eax, dx
0x18005f256  shr     eax, 8
0x18005f259  lea     ecx, [rax+rax*4]
0x18005f25c  mov     eax, edx
0x18005f25e  shr     eax, 10h
0x18005f261  movzx   eax, al
0x18005f264  add     ecx, eax
0x18005f266  movzx   eax, dl
0x18005f269  lea     ecx, [rcx+rax*2]
0x18005f26c  cmp     ecx, r14d
0x18005f26f  setbe   r12b
0x18005f273  mov     [rsp+88h+arg_18], r15d
0x18005f27b  lea     rax, [rsp+88h+arg_18]
0x18005f283  mov     qword ptr [rsp+88h+pColor], rax; pColor
0x18005f288  mov     edx, 0Eh; iPartId
0x18005f28d  mov     r9d, 0EDBh; iPropId
0x18005f293  lea     r8d, [rdx-0Ch]; iStateId
0x18005f297  mov     rcx, rsi; hTheme
0x18005f29a  call    cs:__imp_GetThemeColor
0x18005f2a0  test    eax, eax
0x18005f2a2  js      short loc_18005F2D6
0x18005f2a4  mov     edx, [rsp+88h+arg_18]
0x18005f2ab  movzx   eax, dx
0x18005f2ae  shr     eax, 8
0x18005f2b1  lea     ecx, [rax+rax*4]
0x18005f2b4  mov     eax, edx
0x18005f2b6  shr     eax, 10h
0x18005f2b9  movzx   eax, al
0x18005f2bc  add     ecx, eax
0x18005f2be  movzx   eax, dl
0x18005f2c1  lea     ecx, [rcx+rax*2]
0x18005f2c4  mov     r14d, r15d
0x18005f2c7  cmp     ecx, 400h
0x18005f2cd  setnbe  r14b
0x18005f2d1  mov     [rsp+88h+var_58], r14d
0x18005f2d6  mov     rcx, rsi; hTheme
0x18005f2d9  call    cs:__imp_CloseThemeData
0x18005f2df  mov     r14d, r15d
0x18005f2e2  mov     ecx, 6
0x18005f2e7  lea     rdx, __ImageBase
0x18005f2ee  test    ecx, ecx
0x18005f2f0  js      short loc_18005F30B
0x18005f2f2  movsxd  rax, ecx
0x18005f2f5  mov     eax, ds:rva dword_180079DE0[rdx+rax*4]
0x18005f2fc  cmp     [rbp+90h], eax
0x18005f302  jge     short loc_18005F308
0x18005f304  dec     ecx
0x18005f306  jmp     short loc_18005F2EE
0x18005f308  mov     r14d, ecx
0x18005f30b  mov     r15d, 2F46h
0x18005f311  mov     edi, [rsp+88h+var_58]
0x18005f315  mov     r9d, r14d
0x18005f318  mov     r8d, edi
0x18005f31b  mov     edx, r15d
0x18005f31e  mov     rcx, rbp
0x18005f321  call    ?_GetBitmap@CActionsContextMenuProvider@@AEAAPEAUHBITMAP__@@KW4BitmapColor@@I@Z; CActionsContextMenuProvider::_GetBitmap(ulong,BitmapColor,uint)
0x18005f326  mov     rsi, rax
0x18005f329  mov     r9d, r14d
0x18005f32c  mov     r8d, r12d
0x18005f32f  mov     edx, r15d
0x18005f332  mov     rcx, rbp
0x18005f335  call    ?_GetBitmap@CActionsContextMenuProvider@@AEAAPEAUHBITMAP__@@KW4BitmapColor@@I@Z; CActionsContextMenuProvider::_GetBitmap(ulong,BitmapColor,uint)
0x18005f33a  mov     qword ptr [rsp+88h+pColor], rsi; int
0x18005f33f  mov     r9, rax; hBitmapUnchecked
0x18005f342  xor     r8d, r8d; uFlags
0x18005f345  mov     edx, r15d; uPosition
0x18005f348  mov     rcx, rbx; hMenu
0x18005f34b  call    cs:__imp_SetMenuItemBitmaps
0x18005f351  inc     r15d
0x18005f354  cmp     r15d, 2F4Bh
0x18005f35b  jle     short loc_18005F315
0x18005f35d  mov     [rbp+98h], r12d
0x18005f364  mov     [rbp+94h], r14d
0x18005f36b  mov     r8, rbx; HMENU
0x18005f36e  mov     rdx, [rsp+88h+arg_8]; struct IApplicationFrameInternal *
0x18005f376  mov     rcx, rbp; this
0x18005f379  call    ?_CleanMenu@CActionsContextMenuProvider@@AEAAJPEAUIApplicationFrameInternal@@PEAUHMENU__@@@Z; CActionsContextMenuProvider::_CleanMenu(IApplicationFrameInternal *,HMENU__ *)
0x18005f37e  mov     esi, eax
0x18005f380  test    eax, eax
0x18005f382  mov     rdi, [rsp+88h+var_50]
0x18005f387  jns     short loc_18005F3AA
0x18005f389  mov     rcx, [rsp+88h]; this
0x18005f391  mov     r9d, eax; char *
0x18005f394  lea     r8, aPcshellShellAp_7; "pcshell\\shell\\applicationframe\\frame"...
0x18005f39b  mov     edx, 121h; void *
0x18005f3a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f3a5  jmp     loc_18005F1EA
0x18005f3aa  mov     [r13+0], rbx
0x18005f3ae  xor     esi, esi
0x18005f3b0  mov     rcx, rdi; hMenu
0x18005f3b3  call    cs:__imp_DestroyMenu
0x18005f3b9  mov     eax, esi
0x18005f3bb  mov     rbx, [rsp+88h+arg_0]
0x18005f3c3  add     rsp, 50h
0x18005f3c7  pop     r15
0x18005f3c9  pop     r14
0x18005f3cb  pop     r13
0x18005f3cd  pop     r12
0x18005f3cf  pop     rdi
0x18005f3d0  pop     rsi
0x18005f3d1  pop     rbp
0x18005f3d2  retn
```
