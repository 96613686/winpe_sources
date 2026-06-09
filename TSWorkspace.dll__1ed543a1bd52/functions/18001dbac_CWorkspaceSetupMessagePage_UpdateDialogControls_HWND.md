# CWorkspaceSetupMessagePage::UpdateDialogControls(HWND__ *)

- ea: `0x18001dbac`
- end: `0x18001de97`
- name: `?UpdateDialogControls@CWorkspaceSetupMessagePage@@AEAAXPEAUHWND__@@@Z`
- size: `747`
- prototype: `void(CWorkspaceSetupMessagePage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18001d978`

## callees

- `0x18001dbac`
- `0x18009a520`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001dd7c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001dd7c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001dd16`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001dd16`
- `USER32!DestroyIcon` at `0x18001dd70`
- `USER32!DestroyIcon` at `0x18001dd70`
- `USER32!LoadImageW` at `0x18001dd49`
- `USER32!LoadImageW` at `0x18001dd49`
- `USER32!SetDlgItemTextW` at `0x18001ddfe`
- `USER32!SetDlgItemTextW` at `0x18001de46`
- `USER32!SetDlgItemTextW` at `0x18001ddfe`
- `USER32!SetDlgItemTextW` at `0x18001de46`
- `USER32!ShowWindow` at `0x18001dddc`
- `USER32!ShowWindow` at `0x18001de24`
- `USER32!ShowWindow` at `0x18001de6c`
- `USER32!ShowWindow` at `0x18001dddc`
- `USER32!ShowWindow` at `0x18001de24`
- `USER32!ShowWindow` at `0x18001de6c`
- `USER32!SetWindowPos` at `0x18001ddce`
- `USER32!SetWindowPos` at `0x18001ddce`
- `USER32!GetWindowRect` at `0x18001dd97`
- `USER32!GetWindowRect` at `0x18001dd97`
- `USER32!GetDlgItem` at `0x18001dcde`
- `USER32!GetDlgItem` at `0x18001dcf8`
- `USER32!GetDlgItem` at `0x18001de0c`
- `USER32!GetDlgItem` at `0x18001de19`
- `USER32!GetDlgItem` at `0x18001de54`
- `USER32!GetDlgItem` at `0x18001de61`
- `USER32!GetDlgItem` at `0x18001dcde`
- `USER32!GetDlgItem` at `0x18001dcf8`
- `USER32!GetDlgItem` at `0x18001de0c`
- `USER32!GetDlgItem` at `0x18001de19`
- `USER32!GetDlgItem` at `0x18001de54`
- `USER32!GetDlgItem` at `0x18001de61`
- `USER32!SendMessageW` at `0x18001dc8f`
- `USER32!SendMessageW` at `0x18001dcbc`
- `USER32!SendMessageW` at `0x18001dd62`
- `USER32!SendMessageW` at `0x18001dc8f`
- `USER32!SendMessageW` at `0x18001dcbc`
- `USER32!SendMessageW` at `0x18001dd62`
- `USER32!GetParent` at `0x18001dbed`
- `USER32!GetParent` at `0x18001dc48`
- `USER32!GetParent` at `0x18001dc7b`
- `USER32!GetParent` at `0x18001dca8`
- `USER32!GetParent` at `0x18001dbed`
- `USER32!GetParent` at `0x18001dc48`
- `USER32!GetParent` at `0x18001dc7b`
- `USER32!GetParent` at `0x18001dca8`
- `USER32!PostMessageW` at `0x18001dc02`
- `USER32!PostMessageW` at `0x18001dc5f`
- `USER32!PostMessageW` at `0x18001dc02`
- `USER32!PostMessageW` at `0x18001dc5f`

## string_xrefs

- `0x18001dd0f`: `imageres.dll`

## pseudocode

```c
void __fastcall CWorkspaceSetupMessagePage::UpdateDialogControls(CWorkspaceSetupMessagePage *this, HWND a2)
{
  __int64 v4; // rbx
  HWND Parent; // rax
  WPARAM v6; // rbx
  HWND v7; // rax
  LPARAM v8; // rbx
  HWND v9; // rax
  LPARAM v10; // rbx
  HWND v11; // rax
  HWND DlgItem; // rbp
  HWND v13; // r15
  int v14; // r12d
  HMODULE LibraryW; // rax
  HMODULE v16; // rbx
  int v17; // r14d
  HANDLE ImageW; // rax
  HICON v19; // rax
  const WCHAR *v20; // r8
  HWND v21; // rax
  int v22; // edx
  const WCHAR *v23; // r8
  HWND v24; // rax
  int v25; // edx
  tagRECT Rect; // [rsp+40h] [rbp-58h] BYREF

  v4 = *(_DWORD *)(*((_QWORD *)this + 22) + 2580LL) != 0 ? 4 : 0;
  Parent = GetParent(a2);
  PostMessageW(Parent, 0x470u, 0, v4 + 2);
  v6 = (*(_DWORD *)(*((_QWORD *)this + 22) + 2576LL) == 0 ? 2 : 0)
     | (*(_DWORD *)(*((_QWORD *)this + 22) + 2572LL) == 0 ? 0x10 : 0)
     | (unsigned __int64)(*(_DWORD *)(*((_QWORD *)this + 22) + 2580LL) != 0 ? 4 : 0);
  v7 = GetParent(a2);
  PostMessageW(v7, 0x48Au, v6, 22);
  v8 = *((_QWORD *)this + 22) + 2584LL;
  if ( *((_QWORD *)this + 22) != -2584 )
  {
    v9 = GetParent(a2);
    SendMessageW(v9, 0x489u, 0, v8);
  }
  v10 = *((_QWORD *)this + 22) + 2684LL;
  if ( *((_QWORD *)this + 22) != -2684 )
  {
    v11 = GetParent(a2);
    SendMessageW(v11, 0x479u, 0, v10);
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 22) + 2568LL) )
  {
    DlgItem = GetDlgItem(a2, 5200);
    if ( DlgItem )
    {
      v13 = GetDlgItem(a2, 5102);
      v14 = *(_DWORD *)(*((_QWORD *)this + 22) + 2568LL);
      LibraryW = LoadLibraryW(L"imageres.dll");
      v16 = LibraryW;
      if ( LibraryW )
      {
        v17 = 0;
        ImageW = LoadImageW(LibraryW, (LPCWSTR)(unsigned __int16)v14, 1u, 32, 32, 0);
        if ( ImageW )
        {
          v19 = (HICON)SendMessageW(v13, 0x172u, 1u, (LPARAM)ImageW);
          if ( v19 )
            DestroyIcon(v19);
          v17 = 1;
        }
        FreeLibrary(v16);
        if ( v17 )
        {
          Rect = 0;
          GetWindowRect(DlgItem, &Rect);
          SetWindowPos(DlgItem, 0, 72, 1, Rect.right - Rect.left - 72, Rect.bottom - Rect.top, 0x210u);
          ShowWindow(v13, 5);
        }
      }
    }
  }
  v20 = (const WCHAR *)(*((_QWORD *)this + 22) + 520LL);
  if ( *v20 )
  {
    SetDlgItemTextW(a2, 5200, v20);
    v21 = GetDlgItem(a2, 5200);
    v22 = 5;
  }
  else
  {
    v21 = GetDlgItem(a2, 5200);
    v22 = 0;
  }
  ShowWindow(v21, v22);
  v23 = (const WCHAR *)(*((_QWORD *)this + 22) + 1544LL);
  if ( *v23 )
  {
    SetDlgItemTextW(a2, 5201, v23);
    v24 = GetDlgItem(a2, 5201);
    v25 = 5;
  }
  else
  {
    v24 = GetDlgItem(a2, 5201);
    v25 = 0;
  }
  ShowWindow(v24, v25);
}

```

## disassembly

```asm
0x18001dbac  mov     [rsp+arg_10], rbx
0x18001dbb1  push    rbp
0x18001dbb2  push    rsi
0x18001dbb3  push    rdi
0x18001dbb4  push    r12
0x18001dbb6  push    r13
0x18001dbb8  push    r14
0x18001dbba  push    r15
0x18001dbbc  sub     rsp, 60h
0x18001dbc0  mov     rax, cs:__security_cookie
0x18001dbc7  xor     rax, rsp
0x18001dbca  mov     [rsp+98h+var_48], rax
0x18001dbcf  mov     rax, [rcx+0B0h]
0x18001dbd6  mov     rdi, rdx
0x18001dbd9  mov     rsi, rcx
0x18001dbdc  mov     rcx, rdi; hWnd
0x18001dbdf  mov     edx, [rax+0A14h]
0x18001dbe5  neg     edx
0x18001dbe7  sbb     rbx, rbx
0x18001dbea  and     ebx, 4
0x18001dbed  call    cs:__imp_GetParent
0x18001dbf3  lea     r9, [rbx+2]; lParam
0x18001dbf7  xor     r8d, r8d; wParam
0x18001dbfa  mov     rcx, rax; hWnd
0x18001dbfd  mov     edx, 470h; Msg
0x18001dc02  call    cs:__imp_PostMessageW
0x18001dc08  mov     rdx, [rsi+0B0h]
0x18001dc0f  mov     eax, [rdx+0A14h]
0x18001dc15  neg     eax
0x18001dc17  mov     eax, [rdx+0A0Ch]
0x18001dc1d  sbb     rbx, rbx
0x18001dc20  and     ebx, 4
0x18001dc23  neg     eax
0x18001dc25  mov     eax, [rdx+0A10h]
0x18001dc2b  sbb     rcx, rcx
0x18001dc2e  not     rcx
0x18001dc31  and     ecx, 10h
0x18001dc34  or      rbx, rcx
0x18001dc37  neg     eax
0x18001dc39  sbb     rcx, rcx
0x18001dc3c  not     rcx
0x18001dc3f  and     ecx, 2
0x18001dc42  or      rbx, rcx
0x18001dc45  mov     rcx, rdi; hWnd
0x18001dc48  call    cs:__imp_GetParent
0x18001dc4e  mov     r9d, 16h; lParam
0x18001dc54  mov     r8, rbx; wParam
0x18001dc57  mov     rcx, rax; hWnd
0x18001dc5a  mov     edx, 48Ah; Msg
0x18001dc5f  call    cs:__imp_PostMessageW
0x18001dc65  mov     rbx, [rsi+0B0h]
0x18001dc6c  xor     r13d, r13d
0x18001dc6f  add     rbx, 0A18h
0x18001dc76  jz      short loc_18001DC95
0x18001dc78  mov     rcx, rdi; hWnd
0x18001dc7b  call    cs:__imp_GetParent
0x18001dc81  mov     r9, rbx; lParam
0x18001dc84  xor     r8d, r8d; wParam
0x18001dc87  mov     rcx, rax; hWnd
0x18001dc8a  mov     edx, 489h; Msg
0x18001dc8f  call    cs:__imp_SendMessageW
0x18001dc95  mov     rbx, [rsi+0B0h]
0x18001dc9c  add     rbx, 0A7Ch
0x18001dca3  jz      short loc_18001DCC2
0x18001dca5  mov     rcx, rdi; hWnd
0x18001dca8  call    cs:__imp_GetParent
0x18001dcae  mov     r9, rbx; lParam
0x18001dcb1  xor     r8d, r8d; wParam
0x18001dcb4  mov     rcx, rax; hWnd
0x18001dcb7  mov     edx, 479h; Msg
0x18001dcbc  call    cs:__imp_SendMessageW
0x18001dcc2  mov     rax, [rsi+0B0h]
0x18001dcc9  cmp     [rax+0A08h], r13d
0x18001dcd0  jz      loc_18001DDE2
0x18001dcd6  mov     edx, 1450h; nIDDlgItem
0x18001dcdb  mov     rcx, rdi; hDlg
0x18001dcde  call    cs:__imp_GetDlgItem
0x18001dce4  mov     rbp, rax
0x18001dce7  test    rax, rax
0x18001dcea  jz      loc_18001DDE2
0x18001dcf0  mov     edx, 13EEh; nIDDlgItem
0x18001dcf5  mov     rcx, rdi; hDlg
0x18001dcf8  call    cs:__imp_GetDlgItem
0x18001dcfe  mov     rcx, [rsi+0B0h]
0x18001dd05  mov     r15, rax
0x18001dd08  mov     r12d, [rcx+0A08h]
0x18001dd0f  lea     rcx, aImageresDll; "imageres.dll"
0x18001dd16  call    cs:__imp_LoadLibraryW
0x18001dd1c  mov     rbx, rax
0x18001dd1f  test    rax, rax
0x18001dd22  jz      loc_18001DDE2
0x18001dd28  mov     r9d, 20h ; ' '; cx
0x18001dd2e  movzx   edx, r12w; name
0x18001dd32  mov     [rsp+98h+fuLoad], r13d; fuLoad
0x18001dd37  mov     rcx, rax; hInst
0x18001dd3a  mov     r14d, r13d
0x18001dd3d  mov     [rsp+98h+cy], r9d; cy
0x18001dd42  lea     r12d, [r9-1Fh]
0x18001dd46  mov     r8d, r12d; type
0x18001dd49  call    cs:__imp_LoadImageW
0x18001dd4f  test    rax, rax
0x18001dd52  jz      short loc_18001DD79
0x18001dd54  mov     r9, rax; lParam
0x18001dd57  mov     r8d, r12d; wParam
0x18001dd5a  mov     edx, 172h; Msg
0x18001dd5f  mov     rcx, r15; hWnd
0x18001dd62  call    cs:__imp_SendMessageW
0x18001dd68  test    rax, rax
0x18001dd6b  jz      short loc_18001DD76
0x18001dd6d  mov     rcx, rax; hIcon
0x18001dd70  call    cs:__imp_DestroyIcon
0x18001dd76  mov     r14d, r12d
0x18001dd79  mov     rcx, rbx; hLibModule
0x18001dd7c  call    cs:__imp_FreeLibrary
0x18001dd82  test    r14d, r14d
0x18001dd85  jz      short loc_18001DDE2
0x18001dd87  xorps   xmm0, xmm0
0x18001dd8a  lea     rdx, [rsp+98h+Rect]; lpRect
0x18001dd8f  mov     rcx, rbp; hWnd
0x18001dd92  movups  xmmword ptr [rsp+98h+Rect.left], xmm0
0x18001dd97  call    cs:__imp_GetWindowRect
0x18001dd9d  mov     ecx, [rsp+98h+Rect.bottom]
0x18001dda1  mov     r8d, 48h ; 'H'; X
0x18001dda7  sub     ecx, [rsp+98h+Rect.top]
0x18001ddab  mov     r9d, r12d; Y
0x18001ddae  mov     eax, [rsp+98h+Rect.right]
0x18001ddb2  xor     edx, edx; hWndInsertAfter
0x18001ddb4  sub     eax, [rsp+98h+Rect.left]
0x18001ddb8  mov     [rsp+98h+uFlags], 210h; uFlags
0x18001ddc0  sub     eax, r8d
0x18001ddc3  mov     [rsp+98h+fuLoad], ecx; cy
0x18001ddc7  mov     rcx, rbp; hWnd
0x18001ddca  mov     [rsp+98h+cy], eax; cx
0x18001ddce  call    cs:__imp_SetWindowPos
0x18001ddd4  mov     edx, 5; nCmdShow
0x18001ddd9  mov     rcx, r15; hWnd
0x18001dddc  call    cs:__imp_ShowWindow
0x18001dde2  mov     r8, [rsi+0B0h]
0x18001dde9  mov     edx, 1450h; nIDDlgItem
0x18001ddee  add     r8, 208h; lpString
0x18001ddf5  mov     rcx, rdi; hDlg
0x18001ddf8  cmp     [r8], r13w
0x18001ddfc  jz      short loc_18001DE19
0x18001ddfe  call    cs:__imp_SetDlgItemTextW
0x18001de04  mov     edx, 1450h; nIDDlgItem
0x18001de09  mov     rcx, rdi; hDlg
0x18001de0c  call    cs:__imp_GetDlgItem
0x18001de12  mov     edx, 5
0x18001de17  jmp     short loc_18001DE21
0x18001de19  call    cs:__imp_GetDlgItem
0x18001de1f  xor     edx, edx; nCmdShow
0x18001de21  mov     rcx, rax; hWnd
0x18001de24  call    cs:__imp_ShowWindow
0x18001de2a  mov     r8, [rsi+0B0h]
0x18001de31  mov     edx, 1451h; nIDDlgItem
0x18001de36  add     r8, 608h; lpString
0x18001de3d  mov     rcx, rdi; hDlg
0x18001de40  cmp     [r8], r13w
0x18001de44  jz      short loc_18001DE61
0x18001de46  call    cs:__imp_SetDlgItemTextW
0x18001de4c  mov     edx, 1451h; nIDDlgItem
0x18001de51  mov     rcx, rdi; hDlg
0x18001de54  call    cs:__imp_GetDlgItem
0x18001de5a  mov     edx, 5
0x18001de5f  jmp     short loc_18001DE69
0x18001de61  call    cs:__imp_GetDlgItem
0x18001de67  xor     edx, edx; nCmdShow
0x18001de69  mov     rcx, rax; hWnd
0x18001de6c  call    cs:__imp_ShowWindow
0x18001de72  mov     rcx, [rsp+98h+var_48]
0x18001de77  xor     rcx, rsp; StackCookie
0x18001de7a  call    __security_check_cookie
0x18001de7f  mov     rbx, [rsp+98h+arg_10]
0x18001de87  add     rsp, 60h
0x18001de8b  pop     r15
0x18001de8d  pop     r14
0x18001de8f  pop     r13
0x18001de91  pop     r12
0x18001de93  pop     rdi
0x18001de94  pop     rsi
0x18001de95  pop     rbp
0x18001de96  retn
```
