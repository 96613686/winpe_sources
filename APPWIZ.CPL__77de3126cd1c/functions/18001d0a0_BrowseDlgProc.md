# BrowseDlgProc

- ea: `0x18001d0a0`
- end: `0x18001d291`
- name: `BrowseDlgProc`
- size: `497`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001c118`
- `0x18001c264`
- `0x18001c5cc`
- `0x18001cde0`
- `0x18001ce3c`
- `0x18001d0a0`
- `0x180052d98`
- `0x180052f08`

## import_xrefs

- `SHLWAPI!SHAutoComplete` at `0x18001d1e1`
- `SHLWAPI!SHAutoComplete` at `0x18001d1e1`
- `USER32!GetWindowLongPtrW` at `0x18001d0bb`
- `USER32!GetWindowLongPtrW` at `0x18001d0bb`
- `USER32!SetWindowLongPtrW` at `0x18001d1a5`
- `USER32!SetWindowLongPtrW` at `0x18001d27b`
- `USER32!SetWindowLongPtrW` at `0x18001d1a5`
- `USER32!SetWindowLongPtrW` at `0x18001d27b`
- `USER32!GetDlgItem` at `0x18001d115`
- `USER32!GetDlgItem` at `0x18001d1b3`
- `USER32!GetDlgItem` at `0x18001d1d6`
- `USER32!GetDlgItem` at `0x18001d115`
- `USER32!GetDlgItem` at `0x18001d1b3`
- `USER32!GetDlgItem` at `0x18001d1d6`
- `USER32!SetFocus` at `0x18001d121`
- `USER32!SetFocus` at `0x18001d121`
- `USER32!SendMessageW` at `0x18001d136`
- `USER32!SendMessageW` at `0x18001d1c8`
- `USER32!SendMessageW` at `0x18001d136`
- `USER32!SendMessageW` at `0x18001d1c8`

## pseudocode

```c
__int64 __fastcall BrowseDlgProc(HWND hWnd, int a2, int a3, LONG_PTR a4)
{
  LONG_PTR WindowLongPtrW; // rax
  struct _WIZDATA *v9; // rbx
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // edi
  HWND v16; // rbx
  HWND DlgItem; // rax
  HWND v18; // rax
  int v19; // eax

  WindowLongPtrW = GetWindowLongPtrW(hWnd, 16);
  v9 = 0;
  if ( WindowLongPtrW )
    v9 = *(struct _WIZDATA **)(WindowLongPtrW + 48);
  v10 = a2 - 2;
  if ( !v10 )
    return 1;
  v11 = v10 - 76;
  if ( !v11 )
  {
    if ( !a4 )
      return 1;
    v19 = *(_DWORD *)(a4 + 16);
    switch ( v19 )
    {
      case -208:
        if ( !v9 || (unsigned int)SetupCleanupExePath(v9) && (unsigned int)ExecSetupProg(v9) )
          return 1;
        BrowseSetActive(v9);
        break;
      case -207:
        if ( !v9 || (unsigned int)NextPushed(v9) )
          return 1;
        break;
      case -203:
        if ( v9 )
          CleanUpWizData(v9);
        return 1;
      case -200:
        if ( v9 )
        {
          *(_QWORD *)v9 = hWnd;
          BrowseSetActive(v9);
        }
        return 1;
      default:
        return 0;
    }
    SetWindowLongPtrW(hWnd, 0, -1);
    return 1;
  }
  v12 = v11 - 5;
  if ( !v12 )
    return 1;
  v13 = v12 - 40;
  if ( !v13 )
    return 1;
  v14 = v13 - 149;
  if ( !v14 )
  {
    **(_QWORD **)(a4 + 48) = hWnd;
    SetWindowLongPtrW(hWnd, 16, a4);
    DlgItem = GetDlgItem(hWnd, 1003);
    SendMessageW(DlgItem, 0xC5u, 0x103u, 0);
    v18 = GetDlgItem(hWnd, 1003);
    SHAutoComplete(v18, 0);
    return 1;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    if ( (unsigned __int16)a3 == 1003 )
    {
      if ( HIWORD(a3) == 768 && v9 )
        SetBrowseButtons(v9);
    }
    else if ( (unsigned __int16)a3 == 1004 )
    {
      if ( v9 )
        BrowseForFileOrFolder(v9);
    }
    return 1;
  }
  if ( v15 != 32495 )
    return 0;
  v16 = GetDlgItem(hWnd, 1003);
  SetFocus(v16);
  SendMessageW(v16, 0xB1u, 0, -1);
  return 1;
}

```

## disassembly

```asm
0x18001d0a0  push    rbx
0x18001d0a2  push    rbp
0x18001d0a3  push    rsi
0x18001d0a4  push    rdi
0x18001d0a5  push    r14
0x18001d0a7  sub     rsp, 20h
0x18001d0ab  mov     edi, edx
0x18001d0ad  mov     r14, r9
0x18001d0b0  mov     edx, 10h; nIndex
0x18001d0b5  mov     rbp, r8
0x18001d0b8  mov     rsi, rcx
0x18001d0bb  call    cs:__imp_GetWindowLongPtrW
0x18001d0c1  xor     ebx, ebx
0x18001d0c3  test    rax, rax
0x18001d0c6  jz      short loc_18001D0CC
0x18001d0c8  mov     rbx, [rax+30h]
0x18001d0cc  sub     edi, 2
0x18001d0cf  jz      loc_18001D281
0x18001d0d5  sub     edi, 4Ch ; 'L'
0x18001d0d8  jz      loc_18001D1EC
0x18001d0de  sub     edi, 5
0x18001d0e1  jz      loc_18001D281
0x18001d0e7  sub     edi, 28h ; '('
0x18001d0ea  jz      loc_18001D281
0x18001d0f0  sub     edi, 95h
0x18001d0f6  jz      loc_18001D193
0x18001d0fc  sub     edi, 1
0x18001d0ff  jz      short loc_18001D141
0x18001d101  cmp     edi, 7EEFh
0x18001d107  jnz     loc_18001D215
0x18001d10d  mov     edx, 3EBh; nIDDlgItem
0x18001d112  mov     rcx, rsi; hDlg
0x18001d115  call    cs:__imp_GetDlgItem
0x18001d11b  mov     rcx, rax; hWnd
0x18001d11e  mov     rbx, rax
0x18001d121  call    cs:__imp_SetFocus
0x18001d127  or      r9, 0FFFFFFFFFFFFFFFFh; lParam
0x18001d12b  xor     r8d, r8d; wParam
0x18001d12e  mov     edx, 0B1h; Msg
0x18001d133  mov     rcx, rbx; hWnd
0x18001d136  call    cs:__imp_SendMessageW
0x18001d13c  jmp     loc_18001D281
0x18001d141  movzx   ecx, bp
0x18001d144  sub     ecx, 3EBh
0x18001d14a  jz      short loc_18001D16B
0x18001d14c  cmp     ecx, 1
0x18001d14f  jnz     loc_18001D281
0x18001d155  test    rbx, rbx
0x18001d158  jz      loc_18001D281
0x18001d15e  mov     rcx, rbx; struct _WIZDATA *
0x18001d161  call    ?BrowseForFileOrFolder@@YAXPEAU_WIZDATA@@@Z; BrowseForFileOrFolder(_WIZDATA *)
0x18001d166  jmp     loc_18001D281
0x18001d16b  shr     rbp, 10h
0x18001d16f  mov     eax, 300h
0x18001d174  cmp     bp, ax
0x18001d177  jnz     loc_18001D281
0x18001d17d  test    rbx, rbx
0x18001d180  jz      loc_18001D281
0x18001d186  mov     rcx, rbx; struct _WIZDATA *
0x18001d189  call    ?SetBrowseButtons@@YAXPEAU_WIZDATA@@@Z; SetBrowseButtons(_WIZDATA *)
0x18001d18e  jmp     loc_18001D281
0x18001d193  mov     rax, [r14+30h]
0x18001d197  mov     r8, r14; dwNewLong
0x18001d19a  mov     edx, 10h; nIndex
0x18001d19f  mov     rcx, rsi; hWnd
0x18001d1a2  mov     [rax], rsi
0x18001d1a5  call    cs:__imp_SetWindowLongPtrW
0x18001d1ab  mov     edx, 3EBh; nIDDlgItem
0x18001d1b0  mov     rcx, rsi; hDlg
0x18001d1b3  call    cs:__imp_GetDlgItem
0x18001d1b9  mov     edx, 0C5h; Msg
0x18001d1be  xor     r9d, r9d; lParam
0x18001d1c1  mov     rcx, rax; hWnd
0x18001d1c4  lea     r8d, [rdx+3Eh]; wParam
0x18001d1c8  call    cs:__imp_SendMessageW
0x18001d1ce  mov     edx, 3EBh; nIDDlgItem
0x18001d1d3  mov     rcx, rsi; hDlg
0x18001d1d6  call    cs:__imp_GetDlgItem
0x18001d1dc  mov     rcx, rax; hwndEdit
0x18001d1df  xor     edx, edx; dwFlags
0x18001d1e1  call    cs:__imp_SHAutoComplete
0x18001d1e7  jmp     loc_18001D281
0x18001d1ec  test    r14, r14
0x18001d1ef  jz      loc_18001D281
0x18001d1f5  mov     eax, [r14+10h]
0x18001d1f9  cmp     eax, 0FFFFFF30h
0x18001d1fe  jz      short loc_18001D24D
0x18001d200  cmp     eax, 0FFFFFF31h
0x18001d205  jz      short loc_18001D23A
0x18001d207  cmp     eax, 0FFFFFF35h
0x18001d20c  jz      short loc_18001D22B
0x18001d20e  cmp     eax, 0FFFFFF38h
0x18001d213  jz      short loc_18001D219
0x18001d215  xor     eax, eax
0x18001d217  jmp     short loc_18001D286
0x18001d219  test    rbx, rbx
0x18001d21c  jz      short loc_18001D281
0x18001d21e  mov     rcx, rbx; struct _WIZDATA *
0x18001d221  mov     [rbx], rsi
0x18001d224  call    ?BrowseSetActive@@YAXPEAU_WIZDATA@@@Z; BrowseSetActive(_WIZDATA *)
0x18001d229  jmp     short loc_18001D281
0x18001d22b  test    rbx, rbx
0x18001d22e  jz      short loc_18001D281
0x18001d230  mov     rcx, rbx
0x18001d233  call    CleanUpWizData
0x18001d238  jmp     short loc_18001D281
0x18001d23a  test    rbx, rbx
0x18001d23d  jz      short loc_18001D281
0x18001d23f  mov     rcx, rbx; struct _WIZDATA *
0x18001d242  call    ?NextPushed@@YAHPEAU_WIZDATA@@@Z; NextPushed(_WIZDATA *)
0x18001d247  test    eax, eax
0x18001d249  jnz     short loc_18001D281
0x18001d24b  jmp     short loc_18001D272
0x18001d24d  test    rbx, rbx
0x18001d250  jz      short loc_18001D281
0x18001d252  mov     rcx, rbx; struct _WIZDATA *
0x18001d255  call    ?SetupCleanupExePath@@YAHPEAU_WIZDATA@@@Z; SetupCleanupExePath(_WIZDATA *)
0x18001d25a  test    eax, eax
0x18001d25c  jz      short loc_18001D26A
0x18001d25e  mov     rcx, rbx
0x18001d261  call    ExecSetupProg
0x18001d266  test    eax, eax
0x18001d268  jnz     short loc_18001D281
0x18001d26a  mov     rcx, rbx; struct _WIZDATA *
0x18001d26d  call    ?BrowseSetActive@@YAXPEAU_WIZDATA@@@Z; BrowseSetActive(_WIZDATA *)
0x18001d272  or      r8, 0FFFFFFFFFFFFFFFFh; dwNewLong
0x18001d276  xor     edx, edx; nIndex
0x18001d278  mov     rcx, rsi; hWnd
0x18001d27b  call    cs:__imp_SetWindowLongPtrW
0x18001d281  mov     eax, 1
0x18001d286  add     rsp, 20h
0x18001d28a  pop     r14
0x18001d28c  pop     rdi
0x18001d28d  pop     rsi
0x18001d28e  pop     rbp
0x18001d28f  pop     rbx
0x18001d290  retn
```
