# CShellBrowser::_OnViewMenuPopup(HMENU__ *)

- ea: `0x1801d3ff4`
- end: `0x1801d4135`
- name: `?_OnViewMenuPopup@CShellBrowser@@AEAAXPEAUHMENU__@@@Z`
- size: `321`
- prototype: `void __fastcall(CShellBrowser *__hidden this, HMENU hmenu)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801d3774`

## callees

- `0x18008d938`
- `0x1800f1220`
- `0x1801a8048`
- `0x1801d1100`
- `0x1801d2230`
- `0x1801d3ff4`

## import_xrefs

- `SHCORE!__imp_SHWindowsPolicy` at `0x1801d4060`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801d4060`
- `SHELL32!__imp_Shell_MergeMenus` at `0x1801d40dd`
- `SHELL32!__imp_Shell_MergeMenus` at `0x1801d40dd`
- `SHLWAPI!__imp_IUnknown_QueryStatus` at `0x1801d40a4`
- `SHLWAPI!__imp_IUnknown_QueryStatus` at `0x1801d40a4`
- `SHLWAPI!__imp_SHCheckMenuItem` at `0x1801d40bb`
- `SHLWAPI!__imp_SHCheckMenuItem` at `0x1801d40bb`
- `USER32!LoadMenuW` at `0x1801d4034`
- `USER32!LoadMenuW` at `0x1801d4034`
- `USER32!GetMenuItemCount` at `0x1801d410a`
- `USER32!GetMenuItemCount` at `0x1801d410a`
- `USER32!DeleteMenu` at `0x1801d400e`
- `USER32!DeleteMenu` at `0x1801d4075`
- `USER32!DeleteMenu` at `0x1801d411f`
- `USER32!DeleteMenu` at `0x1801d400e`
- `USER32!DeleteMenu` at `0x1801d4075`
- `USER32!DeleteMenu` at `0x1801d411f`
- `USER32!DestroyMenu` at `0x1801d40e6`
- `USER32!DestroyMenu` at `0x1801d40e6`

## pseudocode

```c
void __fastcall CShellBrowser::_OnViewMenuPopup(CShellBrowser *this, HMENU hmenu)
{
  struct IUnknown *ITBar; // rbp
  HMENU MenuW; // rax
  HMENU v6; // rbx
  HMENU BrowserBarMenu; // rax
  HMENU v8; // rax
  __int64 v9; // [rsp+70h] [rbp+18h] BYREF

  DeleteMenu(hmenu, 0xA201u, 0);
  ITBar = (struct IUnknown *)CShellBrowser::_GetITBar(this);
  if ( ITBar )
  {
    MenuW = LoadMenuW(g_hinst, (LPCWSTR)0x108);
    v6 = MenuW;
    if ( MenuW )
    {
      if ( (unsigned int)PopulateItbarToolbarBands(MenuW, ITBar) )
      {
        if ( (unsigned int)SHWindowsPolicy(POLID_NOBANDCUSTOMIZE) )
        {
          DeleteMenu(v6, 0xA20Cu, 0);
        }
        else
        {
          v9 = 27;
          IUnknown_QueryStatus(ITBar, &CGID_PrivCITCommands, 1, &v9, 0);
          SHCheckMenuItem(v6, 41484, BYTE4(v9) & 2);
        }
        Shell_MergeMenus(hmenu, v6, 0, 0, 0xFFFFFFFF, 2u);
      }
      DestroyMenu(v6);
    }
  }
  BrowserBarMenu = CShellBrowser::_GetBrowserBarMenu(this);
  CShellBrowser::_AddBrowserBarMenuItems(this, BrowserBarMenu);
  v8 = CShellBrowser::_GetBrowserBarMenu(this);
  if ( !GetMenuItemCount(v8) )
    DeleteMenu(hmenu, 0xA230u, 0);
  _SHPrettyMenu(hmenu);
}

```

## disassembly

```asm
0x1801d3ff4  push    rbx
0x1801d3ff6  push    rbp
0x1801d3ff7  push    rsi
0x1801d3ff8  push    rdi
0x1801d3ff9  sub     rsp, 38h
0x1801d3ffd  mov     rdi, rdx
0x1801d4000  mov     rsi, rcx
0x1801d4003  mov     rcx, rdi; hMenu
0x1801d4006  xor     r8d, r8d; uFlags
0x1801d4009  mov     edx, 0A201h; uPosition
0x1801d400e  call    cs:__imp_DeleteMenu
0x1801d4014  mov     rcx, rsi; this
0x1801d4017  call    ?_GetITBar@CShellBrowser@@AEAAPEAUIDockingWindow@@XZ; CShellBrowser::_GetITBar(void)
0x1801d401c  mov     rbp, rax
0x1801d401f  test    rax, rax
0x1801d4022  jz      loc_1801D40EC
0x1801d4028  mov     rcx, cs:g_hinst; hInstance
0x1801d402f  mov     edx, 108h; lpMenuName
0x1801d4034  call    cs:__imp_LoadMenuW
0x1801d403a  mov     rbx, rax
0x1801d403d  test    rax, rax
0x1801d4040  jz      loc_1801D40EC
0x1801d4046  mov     rdx, rbp; struct IUnknown *
0x1801d4049  mov     rcx, rax; hMenu
0x1801d404c  call    ?PopulateItbarToolbarBands@@YAHPEAUHMENU__@@PEAUIUnknown@@@Z; PopulateItbarToolbarBands(HMENU__ *,IUnknown *)
0x1801d4051  test    eax, eax
0x1801d4053  jz      loc_1801D40E3
0x1801d4059  lea     rcx, POLID_NOBANDCUSTOMIZE
0x1801d4060  call    cs:__imp_SHWindowsPolicy
0x1801d4066  test    eax, eax
0x1801d4068  jz      short loc_1801D407D
0x1801d406a  xor     r8d, r8d; uFlags
0x1801d406d  mov     edx, 0A20Ch; uPosition
0x1801d4072  mov     rcx, rbx; hMenu
0x1801d4075  call    cs:__imp_DeleteMenu
0x1801d407b  jmp     short loc_1801D40C1
0x1801d407d  lea     r9, [rsp+58h+arg_10]
0x1801d4082  mov     [rsp+58h+arg_10], 1Bh
0x1801d408b  mov     r8d, 1
0x1801d4091  mov     qword ptr [rsp+58h+uIDAdjustMax], 0
0x1801d409a  lea     rdx, CGID_PrivCITCommands
0x1801d40a1  mov     rcx, rbp
0x1801d40a4  call    cs:__imp_IUnknown_QueryStatus
0x1801d40aa  mov     r8d, dword ptr [rsp+58h+arg_10+4]
0x1801d40af  mov     edx, 0A20Ch
0x1801d40b4  and     r8d, 2
0x1801d40b8  mov     rcx, rbx
0x1801d40bb  call    cs:__imp_SHCheckMenuItem
0x1801d40c1  mov     [rsp+58h+uFlags], 2; uFlags
0x1801d40c9  xor     r9d, r9d; uIDAdjust
0x1801d40cc  xor     r8d, r8d; uInsert
0x1801d40cf  mov     [rsp+58h+uIDAdjustMax], 0FFFFFFFFh; uIDAdjustMax
0x1801d40d7  mov     rdx, rbx; hmSrc
0x1801d40da  mov     rcx, rdi; hmDst
0x1801d40dd  call    cs:__imp_Shell_MergeMenus
0x1801d40e3  mov     rcx, rbx; hMenu
0x1801d40e6  call    cs:__imp_DestroyMenu
0x1801d40ec  mov     rcx, rsi; this
0x1801d40ef  call    ?_GetBrowserBarMenu@CShellBrowser@@AEAAPEAUHMENU__@@XZ; CShellBrowser::_GetBrowserBarMenu(void)
0x1801d40f4  mov     rdx, rax; hmenu
0x1801d40f7  mov     rcx, rsi; this
0x1801d40fa  call    ?_AddBrowserBarMenuItems@CShellBrowser@@AEAAXPEAUHMENU__@@@Z; CShellBrowser::_AddBrowserBarMenuItems(HMENU__ *)
0x1801d40ff  mov     rcx, rsi; this
0x1801d4102  call    ?_GetBrowserBarMenu@CShellBrowser@@AEAAPEAUHMENU__@@XZ; CShellBrowser::_GetBrowserBarMenu(void)
0x1801d4107  mov     rcx, rax; hMenu
0x1801d410a  call    cs:__imp_GetMenuItemCount
0x1801d4110  test    eax, eax
0x1801d4112  jnz     short loc_1801D4125
0x1801d4114  xor     r8d, r8d; uFlags
0x1801d4117  mov     edx, 0A230h; uPosition
0x1801d411c  mov     rcx, rdi; hMenu
0x1801d411f  call    cs:__imp_DeleteMenu
0x1801d4125  mov     rcx, rdi; hmenu
0x1801d4128  add     rsp, 38h
0x1801d412c  pop     rdi
0x1801d412d  pop     rsi
0x1801d412e  pop     rbp
0x1801d412f  pop     rbx
0x1801d4130  jmp     ?_SHPrettyMenu@@YAXPEAUHMENU__@@@Z; _SHPrettyMenu(HMENU__ *)
```
