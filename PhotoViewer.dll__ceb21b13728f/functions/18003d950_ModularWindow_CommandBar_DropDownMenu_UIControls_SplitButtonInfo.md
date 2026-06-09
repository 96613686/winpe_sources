# ModularWindow::CommandBar::DropDownMenu(UIControls::SplitButtonInfo *)

- ea: `0x18003d950`
- end: `0x18003dd20`
- name: `?DropDownMenu@CommandBar@ModularWindow@@UEAAJPEAUSplitButtonInfo@UIControls@@@Z`
- size: `976`
- prototype: `__int64 __fastcall(ModularWindow::CommandBar *__hidden this, struct UIControls::SplitButtonInfo *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800294ac`
- `0x180035868`
- `0x18003942c`
- `0x18003d950`
- `0x18003dd28`
- `0x18003f800`
- `0x18006c20c`
- `0x18006ce90`
- `0x18006d008`
- `0x18006d440`
- `0x18006e910`
- `0x180076000`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003daf0`
- `KERNEL32!GetCurrentThreadId` at `0x18003db14`
- `KERNEL32!GetCurrentThreadId` at `0x18003daf0`
- `KERNEL32!GetCurrentThreadId` at `0x18003db14`
- `USER32!GetDlgCtrlID` at `0x18003dc3f`
- `USER32!GetDlgCtrlID` at `0x18003dc3f`
- `USER32!UnhookWindowsHookEx` at `0x18003dbe3`
- `USER32!UnhookWindowsHookEx` at `0x18003dbf0`
- `USER32!UnhookWindowsHookEx` at `0x18003dbe3`
- `USER32!UnhookWindowsHookEx` at `0x18003dbf0`
- `USER32!SetWindowsHookExW` at `0x18003db07`
- `USER32!SetWindowsHookExW` at `0x18003db2b`
- `USER32!SetWindowsHookExW` at `0x18003db07`
- `USER32!SetWindowsHookExW` at `0x18003db2b`
- `USER32!SystemParametersInfoW` at `0x18003db9d`
- `USER32!SystemParametersInfoW` at `0x18003db9d`
- `USER32!DestroyMenu` at `0x18003dcaa`
- `USER32!DestroyMenu` at `0x18003dd04`
- `USER32!DestroyMenu` at `0x18003dcaa`
- `USER32!DestroyMenu` at `0x18003dd04`
- `USER32!TrackPopupMenuEx` at `0x18003dbd6`
- `USER32!TrackPopupMenuEx` at `0x18003dbd6`
- `USER32!GetMenuItemCount` at `0x18003da49`
- `USER32!GetMenuItemCount` at `0x18003da49`
- `USER32!GetClientRect` at `0x18003db4d`
- `USER32!GetClientRect` at `0x18003dc60`
- `USER32!GetClientRect` at `0x18003db4d`
- `USER32!GetClientRect` at `0x18003dc60`
- `USER32!GetSubMenu` at `0x18003da7c`
- `USER32!GetSubMenu` at `0x18003daa1`
- `USER32!GetSubMenu` at `0x18003da7c`
- `USER32!GetSubMenu` at `0x18003daa1`
- `UxTheme!IsAppThemed` at `0x18003dad0`
- `UxTheme!IsAppThemed` at `0x18003dad0`

## pseudocode

```c
__int64 __fastcall ModularWindow::CommandBar::DropDownMenu(
        ModularWindow::CommandBar *this,
        struct UIControls::SplitButtonInfo *a2)
{
  __int128 v2; // xmm0
  ModularWindow::CommandBar *v3; // r15
  int v5; // ecx
  HMENU SubMenu; // r14
  HMENU v7; // rbx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  HMENU Handle; // rax
  int v13; // edi
  int v14; // edx
  HMENU v15; // rdx
  int v16; // r12d
  int v17; // r13d
  DWORD CurrentThreadId; // eax
  DWORD v19; // eax
  HWND v20; // rcx
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  int pvParam; // [rsp+30h] [rbp-49h] BYREF
  __int64 v26; // [rsp+38h] [rbp-41h] BYREF
  int y; // [rsp+40h] [rbp-39h]
  __int64 v28; // [rsp+48h] [rbp-31h] BYREF
  HMENU hMenu; // [rsp+50h] [rbp-29h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-21h] BYREF
  int x[4]; // [rsp+68h] [rbp-11h] BYREF
  int v32; // [rsp+78h] [rbp-1h]
  TPMPARAMS tpm; // [rsp+80h] [rbp+7h] BYREF

  v2 = *(_OWORD *)a2;
  v3 = (ModularWindow::CommandBar *)((char *)this - 176);
  v32 = *((_DWORD *)a2 + 4);
  *(_OWORD *)x = v2;
  while ( 1 )
  {
    v26 = 0;
    v28 = 0;
    UIBase::SmartMenu::SmartMenu((UIBase::SmartMenu *)&hMenu, (unsigned int)a2);
    v5 = x[0];
    SubMenu = 0;
    v7 = hMenu;
    *((_DWORD *)v3 + 1314) = -1;
    v8 = v5 - 60002;
    if ( !v8 )
    {
      *((_DWORD *)this + 1269) = 0;
      v14 = 0;
      goto LABEL_14;
    }
    v9 = v8 - 3;
    if ( v9 )
      break;
    *((_DWORD *)this + 1269) = 1;
    SubMenu = GetSubMenu(v7, 2);
    ModularWindow::CommandBar::UpdateOpwMenu(v3, SubMenu);
    v15 = SubMenu;
LABEL_15:
    ModularWindow::TaskModelState::UpdateMenu((ModularWindow::CommandBar *)((char *)this + 4600), v15);
LABEL_16:
    if ( SubMenu )
    {
      v16 = x[1];
      v17 = x[3];
      y = v32;
      if ( IsAppThemed() )
        ModularWindowPrivate::MenuBitmapsHelper::AddIconsToMenu(
          (ModularWindow::CommandBar *)((char *)this + 5144),
          SubMenu);
      ModularWindow::CommandBar::s_pCommandBar = v3;
      CurrentThreadId = GetCurrentThreadId();
      ModularWindow::CommandBar::s_hMenuMsgMouseHook = SetWindowsHookExW(
                                                         7,
                                                         ModularWindow::CommandBar::MouseInputFilter,
                                                         0,
                                                         CurrentThreadId);
      v19 = GetCurrentThreadId();
      ModularWindow::CommandBar::s_hMenuMsgKeyboardHook = SetWindowsHookExW(
                                                            2,
                                                            ModularWindow::CommandBar::KeyboardInputFilter,
                                                            0,
                                                            v19);
      v20 = (HWND)*((_QWORD *)this - 21);
      Rect = 0;
      GetClientRect(v20, &Rect);
      v21 = *((_DWORD *)this + 1262);
      Rect.top += v21;
      Rect.bottom -= v21;
      ATL::CWindow::ClientToScreen((ModularWindow::CommandBar *)((char *)this - 168), &Rect);
      tpm.rcExclude = Rect;
      tpm.cbSize = 20;
      pvParam = 0;
      SystemParametersInfoW(0x1Bu, 0, &pvParam, 0);
      if ( pvParam )
        v16 = v17;
      TrackPopupMenuEx(SubMenu, pvParam != 0 ? 5192 : 5184, v16, y, *((HWND *)this - 21), &tpm);
      UnhookWindowsHookEx(ModularWindow::CommandBar::s_hMenuMsgMouseHook);
      UnhookWindowsHookEx(ModularWindow::CommandBar::s_hMenuMsgKeyboardHook);
      v22 = *((int *)this + 1269);
      ModularWindow::CommandBar::s_pCommandBar = 0;
      UIControls::SplitButtonEx::SetMenuDroppedState((ModularWindow::CommandBar *)((char *)this + 640 * v22 + 56), 0);
      v23 = *((int *)this + 1270);
      *((_DWORD *)this + 1269) = -1;
      if ( (int)v23 >= 0 )
      {
        x[0] = GetDlgCtrlID(*((HWND *)this + 80 * v23 + 8));
        GetClientRect(*((HWND *)this + 80 * *((int *)this + 1270) + 8), (LPRECT)&x[1]);
        ATL::CWindow::ClientToScreen(
          (ModularWindow::CommandBar *)((char *)this + 640 * *((int *)this + 1270) + 64),
          (struct tagRECT *)&x[1]);
        UIControls::SplitButtonEx::SetMenuDroppedState(
          (ModularWindow::CommandBar *)((char *)this + 640 * *((int *)this + 1270) + 56),
          1);
      }
    }
    if ( v7 )
    {
      DestroyMenu(v7);
      hMenu = 0;
    }
    ModularWindow::SmartPopupMenu::~SmartPopupMenu((ModularWindow::SmartPopupMenu *)&v28);
    ModularWindow::SmartPopupMenu::~SmartPopupMenu((ModularWindow::SmartPopupMenu *)&v26);
    if ( *((_DWORD *)this + 1270) == -1 )
      return 0;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    *((_DWORD *)this + 1269) = 3;
    v14 = 1;
LABEL_14:
    SubMenu = GetSubMenu(v7, v14);
    v15 = SubMenu;
    goto LABEL_15;
  }
  v11 = v10 - 2;
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      *((_DWORD *)this + 1269) = 5;
      SubMenu = ModularWindow::SmartPopupMenu::GetHandle((ModularWindow::SmartPopupMenu *)&v26);
      Handle = ModularWindow::SmartPopupMenu::GetHandle((ModularWindow::SmartPopupMenu *)&v28);
      ModularWindow::CommandBar::PopulateChevronMenu(v3, SubMenu, v7, Handle);
    }
    goto LABEL_16;
  }
  *((_DWORD *)this + 1269) = 4;
  SubMenu = ModularWindow::SmartPopupMenu::GetHandle((ModularWindow::SmartPopupMenu *)&v26);
  v13 = ModularWindow::CommandBar::PopulateOpenWithMenu(v3, SubMenu);
  if ( v13 >= 0 )
  {
    if ( GetMenuItemCount(SubMenu) < 1 )
      SubMenu = 0;
    goto LABEL_16;
  }
  if ( v7 )
    DestroyMenu(v7);
  ModularWindow::SmartPopupMenu::~SmartPopupMenu((ModularWindow::SmartPopupMenu *)&v28);
  ModularWindow::SmartPopupMenu::~SmartPopupMenu((ModularWindow::SmartPopupMenu *)&v26);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18003d950  mov     [rsp-8+arg_10], rbx
0x18003d955  push    rbp
0x18003d956  push    rsi
0x18003d957  push    rdi
0x18003d958  push    r12
0x18003d95a  push    r13
0x18003d95c  push    r14
0x18003d95e  push    r15
0x18003d960  lea     rbp, [rsp-27h]
0x18003d965  sub     rsp, 0A0h
0x18003d96c  mov     rax, cs:__security_cookie
0x18003d973  xor     rax, rsp
0x18003d976  mov     [rbp+57h+var_38], rax
0x18003d97a  movups  xmm0, xmmword ptr [rdx]
0x18003d97d  mov     eax, [rdx+10h]
0x18003d980  lea     r15, [rcx-0B0h]
0x18003d987  mov     rsi, rcx
0x18003d98a  mov     [rbp+57h+var_58], eax
0x18003d98d  movups  xmmword ptr [rbp+57h+x], xmm0
0x18003d991  xor     r12d, r12d
0x18003d994  lea     rcx, [rbp+57h+hMenu]; this
0x18003d998  mov     [rbp+57h+var_98], r12
0x18003d99c  mov     [rbp+57h+var_88], r12
0x18003d9a0  call    ??0SmartMenu@UIBase@@QEAA@I@Z; UIBase::SmartMenu::SmartMenu(uint)
0x18003d9a5  mov     ecx, [rbp+57h+x]
0x18003d9a8  mov     r14, r12
0x18003d9ab  mov     rbx, [rbp+57h+hMenu]
0x18003d9af  mov     dword ptr [r15+1488h], 0FFFFFFFFh
0x18003d9ba  sub     ecx, 0EA62h
0x18003d9c0  jz      loc_18003DA95
0x18003d9c6  sub     ecx, 3
0x18003d9c9  jz      loc_18003DA6A
0x18003d9cf  sub     ecx, 1
0x18003d9d2  jz      loc_18003DA59
0x18003d9d8  sub     ecx, 2
0x18003d9db  jz      short loc_18003DA1B
0x18003d9dd  cmp     ecx, 1
0x18003d9e0  jnz     loc_18003DAB9
0x18003d9e6  lea     rcx, [rbp+57h+var_98]; this
0x18003d9ea  mov     dword ptr [rsi+13D4h], 5
0x18003d9f4  call    ?GetHandle@SmartPopupMenu@ModularWindow@@QEAAPEAUHMENU__@@XZ; ModularWindow::SmartPopupMenu::GetHandle(void)
0x18003d9f9  lea     rcx, [rbp+57h+var_88]; this
0x18003d9fd  mov     r14, rax
0x18003da00  call    ?GetHandle@SmartPopupMenu@ModularWindow@@QEAAPEAUHMENU__@@XZ; ModularWindow::SmartPopupMenu::GetHandle(void)
0x18003da05  mov     r9, rax; HMENU
0x18003da08  mov     r8, rbx; hMenu
0x18003da0b  mov     rdx, r14; hmenu
0x18003da0e  mov     rcx, r15; this
0x18003da11  call    ?PopulateChevronMenu@CommandBar@ModularWindow@@AEAAXPEAUHMENU__@@00@Z; ModularWindow::CommandBar::PopulateChevronMenu(HMENU__ *,HMENU__ *,HMENU__ *)
0x18003da16  jmp     loc_18003DAB9
0x18003da1b  lea     rcx, [rbp+57h+var_98]; this
0x18003da1f  mov     dword ptr [rsi+13D4h], 4
0x18003da29  call    ?GetHandle@SmartPopupMenu@ModularWindow@@QEAAPEAUHMENU__@@XZ; ModularWindow::SmartPopupMenu::GetHandle(void)
0x18003da2e  mov     rdx, rax; HMENU
0x18003da31  mov     rcx, r15; this
0x18003da34  mov     r14, rax
0x18003da37  call    ?PopulateOpenWithMenu@CommandBar@ModularWindow@@AEAAJPEAUHMENU__@@@Z; ModularWindow::CommandBar::PopulateOpenWithMenu(HMENU__ *)
0x18003da3c  mov     edi, eax
0x18003da3e  test    eax, eax
0x18003da40  js      loc_18003DCFC
0x18003da46  mov     rcx, r14; hMenu
0x18003da49  call    cs:__imp_GetMenuItemCount
0x18003da4f  cmp     eax, 1
0x18003da52  jge     short loc_18003DAB9
0x18003da54  mov     r14, r12
0x18003da57  jmp     short loc_18003DAB9
0x18003da59  mov     dword ptr [rsi+13D4h], 3
0x18003da63  mov     edx, 1
0x18003da68  jmp     short loc_18003DA9E
0x18003da6a  mov     edx, 2; nPos
0x18003da6f  mov     dword ptr [rsi+13D4h], 1
0x18003da79  mov     rcx, rbx; hMenu
0x18003da7c  call    cs:__imp_GetSubMenu
0x18003da82  mov     rdx, rax; HMENU
0x18003da85  mov     rcx, r15; this
0x18003da88  mov     r14, rax
0x18003da8b  call    ?UpdateOpwMenu@CommandBar@ModularWindow@@AEAAJPEAUHMENU__@@@Z; ModularWindow::CommandBar::UpdateOpwMenu(HMENU__ *)
0x18003da90  mov     rdx, r14
0x18003da93  jmp     short loc_18003DAAD
0x18003da95  mov     [rsi+13D4h], r12d
0x18003da9c  xor     edx, edx; nPos
0x18003da9e  mov     rcx, rbx; hMenu
0x18003daa1  call    cs:__imp_GetSubMenu
0x18003daa7  mov     r14, rax
0x18003daaa  mov     rdx, rax; HMENU
0x18003daad  lea     rcx, [rsi+11F8h]; this
0x18003dab4  call    ?UpdateMenu@TaskModelState@ModularWindow@@QEAAXPEAUHMENU__@@@Z; ModularWindow::TaskModelState::UpdateMenu(HMENU__ *)
0x18003dab9  test    r14, r14
0x18003dabc  jz      loc_18003DCA2
0x18003dac2  mov     eax, [rbp+57h+var_58]
0x18003dac5  mov     r12d, [rbp+57h+x+4]
0x18003dac9  mov     r13d, [rbp+57h+x+0Ch]
0x18003dacd  mov     [rbp+57h+y], eax
0x18003dad0  call    cs:__imp_IsAppThemed
0x18003dad6  test    eax, eax
0x18003dad8  jz      short loc_18003DAE9
0x18003dada  lea     rcx, [rsi+1418h]; this
0x18003dae1  mov     rdx, r14; HMENU
0x18003dae4  call    ?AddIconsToMenu@MenuBitmapsHelper@ModularWindowPrivate@@QEAAXPEAUHMENU__@@@Z; ModularWindowPrivate::MenuBitmapsHelper::AddIconsToMenu(HMENU__ *)
0x18003dae9  mov     cs:?s_pCommandBar@CommandBar@ModularWindow@@0PEAV12@EA, r15; ModularWindow::CommandBar * ModularWindow::CommandBar::s_pCommandBar
0x18003daf0  call    cs:__imp_GetCurrentThreadId
0x18003daf6  xor     r8d, r8d; hmod
0x18003daf9  lea     rdx, ?MouseInputFilter@CommandBar@ModularWindow@@CA_JH_K_J@Z; lpfn
0x18003db00  mov     r9d, eax; dwThreadId
0x18003db03  lea     ecx, [r8+7]; idHook
0x18003db07  call    cs:__imp_SetWindowsHookExW
0x18003db0d  mov     cs:?s_hMenuMsgMouseHook@CommandBar@ModularWindow@@0PEAUHHOOK__@@EA, rax; HHOOK__ * ModularWindow::CommandBar::s_hMenuMsgMouseHook
0x18003db14  call    cs:__imp_GetCurrentThreadId
0x18003db1a  xor     r8d, r8d; hmod
0x18003db1d  lea     rdx, ?KeyboardInputFilter@CommandBar@ModularWindow@@CA_JH_K_J@Z; lpfn
0x18003db24  mov     r9d, eax; dwThreadId
0x18003db27  lea     ecx, [r8+2]; idHook
0x18003db2b  call    cs:__imp_SetWindowsHookExW
0x18003db31  xorps   xmm0, xmm0
0x18003db34  lea     rdi, [rsi-0A8h]
0x18003db3b  lea     rdx, [rbp+57h+Rect]; lpRect
0x18003db3f  mov     cs:?s_hMenuMsgKeyboardHook@CommandBar@ModularWindow@@0PEAUHHOOK__@@EA, rax; HHOOK__ * ModularWindow::CommandBar::s_hMenuMsgKeyboardHook
0x18003db46  mov     rcx, [rdi]; hWnd
0x18003db49  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18003db4d  call    cs:__imp_GetClientRect
0x18003db53  mov     eax, [rsi+13B8h]
0x18003db59  lea     rdx, [rbp+57h+Rect]; struct tagRECT *
0x18003db5d  add     [rbp+57h+Rect.top], eax
0x18003db60  mov     rcx, rdi; this
0x18003db63  sub     [rbp+57h+Rect.bottom], eax
0x18003db66  call    ?ClientToScreen@CWindow@ATL@@QEBAHPEAUtagRECT@@@Z; ATL::CWindow::ClientToScreen(tagRECT *)
0x18003db6b  mov     eax, [rbp+57h+Rect.left]
0x18003db6e  lea     r8, [rbp+57h+pvParam]; pvParam
0x18003db72  mov     [rbp+57h+tpm.rcExclude.left], eax
0x18003db75  xor     edx, edx; uiParam
0x18003db77  mov     eax, [rbp+57h+Rect.top]
0x18003db7a  xor     r9d, r9d; fWinIni
0x18003db7d  mov     [rbp+57h+tpm.rcExclude.top], eax
0x18003db80  mov     eax, [rbp+57h+Rect.right]
0x18003db83  mov     [rbp+57h+tpm.rcExclude.right], eax
0x18003db86  lea     ecx, [rdx+1Bh]; uiAction
0x18003db89  mov     eax, [rbp+57h+Rect.bottom]
0x18003db8c  mov     [rbp+57h+tpm.rcExclude.bottom], eax
0x18003db8f  mov     [rbp+57h+tpm.cbSize], 14h
0x18003db96  mov     [rbp+57h+pvParam], 0
0x18003db9d  call    cs:__imp_SystemParametersInfoW
0x18003dba3  mov     ecx, [rbp+57h+pvParam]
0x18003dba6  mov     eax, ecx
0x18003dba8  mov     r9d, [rbp+57h+y]; y
0x18003dbac  neg     eax
0x18003dbae  lea     rax, [rbp+57h+tpm]
0x18003dbb2  sbb     edx, edx
0x18003dbb4  mov     [rsp+0D0h+lptpm], rax; lptpm
0x18003dbb9  mov     rax, [rdi]
0x18003dbbc  and     edx, 8
0x18003dbbf  add     edx, 1440h; uFlags
0x18003dbc5  mov     [rsp+0D0h+hwnd], rax; hwnd
0x18003dbca  test    ecx, ecx
0x18003dbcc  mov     rcx, r14; hMenu
0x18003dbcf  cmovnz  r12d, r13d
0x18003dbd3  mov     r8d, r12d; x
0x18003dbd6  call    cs:__imp_TrackPopupMenuEx
0x18003dbdc  mov     rcx, cs:?s_hMenuMsgMouseHook@CommandBar@ModularWindow@@0PEAUHHOOK__@@EA; hhk
0x18003dbe3  call    cs:__imp_UnhookWindowsHookEx
0x18003dbe9  mov     rcx, cs:?s_hMenuMsgKeyboardHook@CommandBar@ModularWindow@@0PEAUHHOOK__@@EA; hhk
0x18003dbf0  call    cs:__imp_UnhookWindowsHookEx
0x18003dbf6  movsxd  rax, dword ptr [rsi+13D4h]
0x18003dbfd  xor     r12d, r12d
0x18003dc00  xor     edx, edx; bool
0x18003dc02  mov     cs:?s_pCommandBar@CommandBar@ModularWindow@@0PEAV12@EA, r12; ModularWindow::CommandBar * ModularWindow::CommandBar::s_pCommandBar
0x18003dc09  lea     rcx, [rax+rax*4]
0x18003dc0d  shl     rcx, 7
0x18003dc11  add     rcx, 38h ; '8'
0x18003dc15  add     rcx, rsi; this
0x18003dc18  call    ?SetMenuDroppedState@SplitButtonEx@UIControls@@QEAAX_N@Z; UIControls::SplitButtonEx::SetMenuDroppedState(bool)
0x18003dc1d  movsxd  rax, dword ptr [rsi+13D8h]
0x18003dc24  mov     dword ptr [rsi+13D4h], 0FFFFFFFFh
0x18003dc2e  test    eax, eax
0x18003dc30  js      short loc_18003DCA2
0x18003dc32  lea     rcx, [rax+rax*4]
0x18003dc36  shl     rcx, 7
0x18003dc3a  mov     rcx, [rcx+rsi+40h]; hWnd
0x18003dc3f  call    cs:__imp_GetDlgCtrlID
0x18003dc45  mov     [rbp+57h+x], eax
0x18003dc48  lea     rdx, [rbp+57h+x+4]; lpRect
0x18003dc4c  movsxd  rax, dword ptr [rsi+13D8h]
0x18003dc53  lea     rcx, [rax+rax*4]
0x18003dc57  shl     rcx, 7
0x18003dc5b  mov     rcx, [rcx+rsi+40h]; hWnd
0x18003dc60  call    cs:__imp_GetClientRect
0x18003dc66  movsxd  rax, dword ptr [rsi+13D8h]
0x18003dc6d  lea     rdx, [rbp+57h+x+4]; struct tagRECT *
0x18003dc71  lea     rcx, [rax+rax*4]
0x18003dc75  shl     rcx, 7
0x18003dc79  add     rcx, 40h ; '@'
0x18003dc7d  add     rcx, rsi; this
0x18003dc80  call    ?ClientToScreen@CWindow@ATL@@QEBAHPEAUtagRECT@@@Z; ATL::CWindow::ClientToScreen(tagRECT *)
0x18003dc85  movsxd  rax, dword ptr [rsi+13D8h]
0x18003dc8c  mov     dl, 1; bool
0x18003dc8e  lea     rcx, [rax+rax*4]
0x18003dc92  shl     rcx, 7
0x18003dc96  add     rcx, 38h ; '8'
0x18003dc9a  add     rcx, rsi; this
0x18003dc9d  call    ?SetMenuDroppedState@SplitButtonEx@UIControls@@QEAAX_N@Z; UIControls::SplitButtonEx::SetMenuDroppedState(bool)
0x18003dca2  test    rbx, rbx
0x18003dca5  jz      short loc_18003DCB4
0x18003dca7  mov     rcx, rbx; hMenu
0x18003dcaa  call    cs:__imp_DestroyMenu
0x18003dcb0  mov     [rbp+57h+hMenu], r12
0x18003dcb4  lea     rcx, [rbp+57h+var_88]; this
0x18003dcb8  call    ??1SmartPopupMenu@ModularWindow@@QEAA@XZ; ModularWindow::SmartPopupMenu::~SmartPopupMenu(void)
0x18003dcbd  lea     rcx, [rbp+57h+var_98]; this
0x18003dcc1  call    ??1SmartPopupMenu@ModularWindow@@QEAA@XZ; ModularWindow::SmartPopupMenu::~SmartPopupMenu(void)
0x18003dcc6  cmp     dword ptr [rsi+13D8h], 0FFFFFFFFh
0x18003dccd  jnz     loc_18003D994
0x18003dcd3  xor     eax, eax
0x18003dcd5  mov     rcx, [rbp+57h+var_38]
0x18003dcd9  xor     rcx, rsp; StackCookie
0x18003dcdc  call    __security_check_cookie
0x18003dce1  mov     rbx, [rsp+0D0h+arg_10]
0x18003dce9  add     rsp, 0A0h
0x18003dcf0  pop     r15
0x18003dcf2  pop     r14
0x18003dcf4  pop     r13
0x18003dcf6  pop     r12
0x18003dcf8  pop     rdi
0x18003dcf9  pop     rsi
0x18003dcfa  pop     rbp
0x18003dcfb  retn
0x18003dcfc  test    rbx, rbx
0x18003dcff  jz      short loc_18003DD0A
0x18003dd01  mov     rcx, rbx; hMenu
0x18003dd04  call    cs:__imp_DestroyMenu
0x18003dd0a  lea     rcx, [rbp+57h+var_88]; this
0x18003dd0e  call    ??1SmartPopupMenu@ModularWindow@@QEAA@XZ; ModularWindow::SmartPopupMenu::~SmartPopupMenu(void)
0x18003dd13  lea     rcx, [rbp+57h+var_98]; this
0x18003dd17  call    ??1SmartPopupMenu@ModularWindow@@QEAA@XZ; ModularWindow::SmartPopupMenu::~SmartPopupMenu(void)
0x18003dd1c  mov     eax, edi
0x18003dd1e  jmp     short loc_18003DCD5
```
