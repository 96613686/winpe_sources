# InputBoxDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18002dcf0`
- end: `0x18002e16c`
- name: `?InputBoxDlgProc@@YAHPEAUHWND__@@I_K_J@Z`
- size: `1148`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180013de4`
- `0x18001cf44`
- `0x18002dcf0`
- `0x180057ba0`
- `0x18005c860`
- `0x1800e15b8`
- `0x1800e15d0`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18002ddba`
- `KERNEL32!MultiByteToWideChar` at `0x18002ddeb`
- `KERNEL32!MultiByteToWideChar` at `0x18002ddba`
- `KERNEL32!MultiByteToWideChar` at `0x18002ddeb`
- `USER32!SetWindowLongPtrA` at `0x18002de19`
- `USER32!SetWindowLongPtrA` at `0x18002de19`
- `USER32!GetWindowTextA` at `0x18002dd87`
- `USER32!GetWindowTextA` at `0x18002dd87`
- `USER32!DrawTextA` at `0x18002decf`
- `USER32!DrawTextA` at `0x18002decf`
- `USER32!GetDlgItem` at `0x18002dd74`
- `USER32!GetDlgItem` at `0x18002de27`
- `USER32!GetDlgItem` at `0x18002df8f`
- `USER32!GetDlgItem` at `0x18002e0fa`
- `USER32!GetDlgItem` at `0x18002dd74`
- `USER32!GetDlgItem` at `0x18002de27`
- `USER32!GetDlgItem` at `0x18002df8f`
- `USER32!GetDlgItem` at `0x18002e0fa`
- `USER32!SendDlgItemMessageA` at `0x18002e00f`
- `USER32!SendDlgItemMessageA` at `0x18002e00f`
- `USER32!SetDlgItemTextA` at `0x18002e024`
- `USER32!SetDlgItemTextA` at `0x18002e024`
- `USER32!EndDialog` at `0x18002ddf9`
- `USER32!EndDialog` at `0x18002ddf9`
- `USER32!ShowWindow` at `0x18002e106`
- `USER32!ShowWindow` at `0x18002e106`
- `USER32!SetWindowPos` at `0x18002df3f`
- `USER32!SetWindowPos` at `0x18002df84`
- `USER32!SetWindowPos` at `0x18002dfe2`
- `USER32!SetWindowPos` at `0x18002df3f`
- `USER32!SetWindowPos` at `0x18002df84`
- `USER32!SetWindowPos` at `0x18002dfe2`
- `USER32!GetDC` at `0x18002de79`
- `USER32!GetDC` at `0x18002de79`
- `USER32!ReleaseDC` at `0x18002dedb`
- `USER32!ReleaseDC` at `0x18002dedb`
- `USER32!SetWindowTextA` at `0x18002de08`
- `USER32!SetWindowTextA` at `0x18002dff5`
- `USER32!SetWindowTextA` at `0x18002de08`
- `USER32!SetWindowTextA` at `0x18002dff5`
- `USER32!GetClientRect` at `0x18002dea9`
- `USER32!GetClientRect` at `0x18002dea9`
- `USER32!MapWindowPoints` at `0x18002dfb6`
- `USER32!MapWindowPoints` at `0x18002dfb6`
- `USER32!GetWindowLongPtrA` at `0x18002dd98`
- `USER32!GetWindowLongPtrA` at `0x18002dd98`
- `USER32!SystemParametersInfoA` at `0x18002de43`
- `USER32!SystemParametersInfoA` at `0x18002de43`
- `USER32!GetParent` at `0x18002e056`
- `USER32!GetParent` at `0x18002e056`
- `USER32!SendMessageA` at `0x18002de70`
- `USER32!SendMessageA` at `0x18002de8f`
- `USER32!SendMessageA` at `0x18002de70`
- `USER32!SendMessageA` at `0x18002de8f`
- `USER32!GetWindowRect` at `0x18002df04`
- `USER32!GetWindowRect` at `0x18002df4d`
- `USER32!GetWindowRect` at `0x18002dfa0`
- `USER32!GetWindowRect` at `0x18002e032`
- `USER32!GetWindowRect` at `0x18002df04`
- `USER32!GetWindowRect` at `0x18002df4d`
- `USER32!GetWindowRect` at `0x18002dfa0`
- `USER32!GetWindowRect` at `0x18002e032`
- `USER32!MoveWindow` at `0x18002e0cd`
- `USER32!MoveWindow` at `0x18002e0cd`
- `GDI32!SelectObject` at `0x18002de9b`
- `GDI32!SelectObject` at `0x18002de9b`
- `GDI32!CreateFontIndirectA` at `0x18002de57`
- `GDI32!CreateFontIndirectA` at `0x18002de57`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002ddc7`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002ddc7`

## pseudocode

```c
__int64 __fastcall InputBoxDlgProc(HWND a1, int a2, __int16 a3, LONG_PTR a4)
{
  int v6; // edx
  int v7; // edx
  HWND v9; // rax
  int WindowTextA; // r13d
  LONG_PTR WindowLongPtrA; // rbx
  int cchWideChar; // edi
  WCHAR *lpWideCharStr; // rax
  HWND DlgItem; // r13
  int v15; // r14d
  HFONT v16; // rax
  HDC DC; // rdi
  void *v18; // rax
  int v19; // ebx
  HWND v20; // rbx
  const CHAR *v21; // r8
  unsigned int v22; // eax
  int v23; // ebx
  unsigned int v24; // eax
  int v25; // eax
  _BYTE *v26; // rax
  HWND v27; // rax
  HWND ThreadHwndMain; // rax
  int v29; // [rsp+40h] [rbp-C0h]
  struct tagRECT v30; // [rsp+48h] [rbp-B8h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-A8h] BYREF
  struct tagRECT v32; // [rsp+68h] [rbp-98h] BYREF
  CHAR String[280]; // [rsp+80h] [rbp-80h] BYREF
  LOGFONTA lf; // [rsp+198h] [rbp+98h] BYREF

  v6 = a2 - 83;
  if ( v6 )
  {
    v7 = v6 - 189;
    if ( !v7 )
    {
      SetWindowTextA(a1, *(LPCSTR *)(a4 + 8));
      SetWindowLongPtrA(a1, -21, a4);
      DlgItem = GetDlgItem(a1, 4901);
      *(_DWORD *)String = 344;
      v15 = 0;
      if ( SystemParametersInfoA(0x29u, 0x158u, String, 0) )
      {
        v16 = CreateFontIndirectA(&lf);
        if ( v16 )
          SendMessageA(DlgItem, 0x30u, (WPARAM)v16, 1);
      }
      DC = GetDC(DlgItem);
      v18 = (void *)SendMessageA(DlgItem, 0x31u, 0, 0);
      SelectObject(DC, v18);
      GetClientRect(DlgItem, &Rect);
      v19 = Rect.bottom - Rect.top;
      DrawTextA(DC, *(LPCSTR *)a4, -1, &Rect, 0xE50u);
      ReleaseDC(DlgItem, DC);
      v29 = Rect.bottom - Rect.top - v19;
      if ( v29 > 0 )
      {
        GetWindowRect(a1, &v30);
        SetWindowPos(a1, 0, 0, 0, v30.right - v30.left, v29 + v30.bottom - v30.top, 0x16u);
        GetWindowRect(DlgItem, &v30);
        SetWindowPos(DlgItem, 0, 0, 0, v30.right - v30.left, v29 + v30.bottom - v30.top, 0x16u);
        v20 = GetDlgItem(a1, 4900);
        GetWindowRect(v20, &v30);
        MapWindowPoints(0, a1, (LPPOINT)&v30, 2u);
        SetWindowPos(v20, 0, v30.left, v29 + v30.top, 0, 0, 0x15u);
      }
      if ( *(_QWORD *)a4 )
        SetWindowTextA(DlgItem, *(LPCSTR *)a4);
      SendDlgItemMessageA(a1, 4900, 0xC5u, 0xFFu, 0);
      v21 = *(const CHAR **)(a4 + 16);
      if ( v21 )
        SetDlgItemTextA(a1, 4900, v21);
      GetWindowRect(a1, &v32);
      if ( *(_DWORD *)(a4 + 24) == 0x80000000 || *(_DWORD *)(a4 + 28) == 0x80000000 )
      {
        DlgInit(a1);
      }
      else
      {
        GetParent(a1);
        v22 = DPIMGR::DpiX((DPIMGR *)g_dpiMgr);
        v23 = RoundDiv(*(_DWORD *)(a4 + 24), 0x5A0 / v22);
        v24 = DPIMGR::DpiY((DPIMGR *)g_dpiMgr);
        v25 = RoundDiv(*(_DWORD *)(a4 + 28), 0x5A0 / v24);
        MoveWindow(a1, v23, v25, v32.right - v32.left, v32.bottom - v32.top, 1);
      }
      v26 = *(_BYTE **)(a4 + 32);
      if ( v26 && *v26 )
        v15 = 5;
      v27 = GetDlgItem(a1, 4902);
      ShowWindow(v27, v15);
      return 1;
    }
    if ( v7 != 1 )
      return 0;
    switch ( a3 )
    {
      case 1:
        v9 = GetDlgItem(a1, 4900);
        WindowTextA = GetWindowTextA(v9, String, 255);
        WindowLongPtrA = GetWindowLongPtrA(a1, -21);
        cchWideChar = MultiByteToWideChar(0, 0, String, -1, 0, 0) - 1;
        lpWideCharStr = SysAllocStringLen(0, cchWideChar);
        *(_QWORD *)(WindowLongPtrA + 48) = lpWideCharStr;
        if ( lpWideCharStr )
          MultiByteToWideChar(0, 0, String, WindowTextA + 1, lpWideCharStr, cchWideChar);
        break;
      case 2:
        break;
      case 4902:
        goto LABEL_29;
      default:
        return 0;
    }
    EndDialog(a1, 1);
  }
  else if ( bEnable )
  {
LABEL_29:
    ThreadHwndMain = GetThreadHwndMain();
    CallHelp(ThreadHwndMain, qword_1803F99F0, 1u, dword_1803F99EC);
  }
  return 1;
}

```

## disassembly

```asm
0x18002dcf0  mov     [rsp-8+arg_8], rbx
0x18002dcf5  mov     [rsp-8+arg_10], rdi
0x18002dcfa  push    rbp
0x18002dcfb  push    r12
0x18002dcfd  push    r13
0x18002dcff  push    r14
0x18002dd01  push    r15
0x18002dd03  lea     rbp, [rsp-0F0h]
0x18002dd0b  mov     eax, 1F0h
0x18002dd10  call    _alloca_probe
0x18002dd15  sub     rsp, rax
0x18002dd18  mov     rax, cs:__security_cookie
0x18002dd1f  xor     rax, rsp
0x18002dd22  mov     [rbp+110h+var_30], rax
0x18002dd29  mov     r12, r9
0x18002dd2c  mov     r15, rcx
0x18002dd2f  sub     edx, 53h ; 'S'
0x18002dd32  jz      loc_18002E10E
0x18002dd38  sub     edx, 0BDh
0x18002dd3e  jz      loc_18002DE04
0x18002dd44  dec     edx
0x18002dd46  jnz     short loc_18002DD65
0x18002dd48  movzx   ecx, r8w
0x18002dd4c  dec     ecx
0x18002dd4e  jz      short loc_18002DD6C
0x18002dd50  dec     ecx
0x18002dd52  jz      loc_18002DDF1
0x18002dd58  mov     edi, 1324h
0x18002dd5d  cmp     ecx, edi
0x18002dd5f  jz      loc_18002E11A
0x18002dd65  xor     eax, eax
0x18002dd67  jmp     loc_18002E140
0x18002dd6c  mov     edx, 1324h; nIDDlgItem
0x18002dd71  mov     rcx, r15; hDlg
0x18002dd74  call    cs:__imp_GetDlgItem
0x18002dd7a  lea     rdx, [rbp+110h+String]; lpString
0x18002dd7e  mov     r8d, 0FFh; nMaxCount
0x18002dd84  mov     rcx, rax; hWnd
0x18002dd87  call    cs:__imp_GetWindowTextA
0x18002dd8d  mov     edx, 0FFFFFFEBh; nIndex
0x18002dd92  mov     rcx, r15; hWnd
0x18002dd95  mov     r13d, eax
0x18002dd98  call    cs:__imp_GetWindowLongPtrA
0x18002dd9e  xor     r14d, r14d
0x18002dda1  lea     r8, [rbp+110h+String]; lpMultiByteStr
0x18002dda5  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002dda9  xor     edx, edx; dwFlags
0x18002ddab  xor     ecx, ecx; CodePage
0x18002ddad  mov     [rsp+210h+cchWideChar], r14d; cchWideChar
0x18002ddb2  mov     rbx, rax
0x18002ddb5  mov     [rsp+210h+lpWideCharStr], r14; lpWideCharStr
0x18002ddba  call    cs:__imp_MultiByteToWideChar
0x18002ddc0  xor     ecx, ecx; strIn
0x18002ddc2  lea     edi, [rax-1]
0x18002ddc5  mov     edx, edi; ui
0x18002ddc7  call    cs:__imp_SysAllocStringLen
0x18002ddcd  mov     [rbx+30h], rax
0x18002ddd1  test    rax, rax
0x18002ddd4  jz      short loc_18002DDF1
0x18002ddd6  lea     r9d, [r13+1]; cbMultiByte
0x18002ddda  lea     r8, [rbp+110h+String]; lpMultiByteStr
0x18002ddde  xor     edx, edx; dwFlags
0x18002dde0  xor     ecx, ecx; CodePage
0x18002dde2  mov     [rsp+210h+cchWideChar], edi; cchWideChar
0x18002dde6  mov     [rsp+210h+lpWideCharStr], rax; lpWideCharStr
0x18002ddeb  call    cs:__imp_MultiByteToWideChar
0x18002ddf1  mov     edx, 1; nResult
0x18002ddf6  mov     rcx, r15; hDlg
0x18002ddf9  call    cs:__imp_EndDialog
0x18002ddff  jmp     loc_18002E13B
0x18002de04  mov     rdx, [r9+8]; lpString
0x18002de08  call    cs:__imp_SetWindowTextA
0x18002de0e  mov     r8, r12; dwNewLong
0x18002de11  mov     edx, 0FFFFFFEBh; nIndex
0x18002de16  mov     rcx, r15; hWnd
0x18002de19  call    cs:__imp_SetWindowLongPtrA
0x18002de1f  mov     edx, 1325h; nIDDlgItem
0x18002de24  mov     rcx, r15; hDlg
0x18002de27  call    cs:__imp_GetDlgItem
0x18002de2d  xor     r9d, r9d; fWinIni
0x18002de30  mov     edx, 158h; uiParam
0x18002de35  lea     ecx, [r9+29h]; uiAction
0x18002de39  lea     r8, [rbp+110h+String]; pvParam
0x18002de3d  mov     r13, rax
0x18002de40  mov     dword ptr [rbp+110h+String], edx
0x18002de43  call    cs:__imp_SystemParametersInfoA
0x18002de49  xor     r14d, r14d
0x18002de4c  test    eax, eax
0x18002de4e  jz      short loc_18002DE76
0x18002de50  lea     rcx, [rbp+110h+lf]; lplf
0x18002de57  call    cs:__imp_CreateFontIndirectA
0x18002de5d  test    rax, rax
0x18002de60  jz      short loc_18002DE76
0x18002de62  lea     r9d, [r14+1]; lParam
0x18002de66  lea     edx, [r14+30h]; Msg
0x18002de6a  mov     r8, rax; wParam
0x18002de6d  mov     rcx, r13; hWnd
0x18002de70  call    cs:__imp_SendMessageA
0x18002de76  mov     rcx, r13; hWnd
0x18002de79  call    cs:__imp_GetDC
0x18002de7f  xor     r9d, r9d; lParam
0x18002de82  xor     r8d, r8d; wParam
0x18002de85  lea     edx, [r9+31h]; Msg
0x18002de89  mov     rcx, r13; hWnd
0x18002de8c  mov     rdi, rax
0x18002de8f  call    cs:__imp_SendMessageA
0x18002de95  mov     rcx, rdi; hdc
0x18002de98  mov     rdx, rax; h
0x18002de9b  call    cs:__imp_SelectObject
0x18002dea1  lea     rdx, [rsp+210h+Rect]; lpRect
0x18002dea6  mov     rcx, r13; hWnd
0x18002dea9  call    cs:__imp_GetClientRect
0x18002deaf  mov     ebx, [rsp+210h+Rect.bottom]
0x18002deb3  mov     rdx, [r12]; lpchText
0x18002deb7  sub     ebx, [rsp+210h+Rect.top]
0x18002debb  lea     r9, [rsp+210h+Rect]; lprc
0x18002dec0  or      r8d, 0FFFFFFFFh; cchText
0x18002dec4  mov     rcx, rdi; hdc
0x18002dec7  mov     dword ptr [rsp+210h+lpWideCharStr], 0E50h; format
0x18002decf  call    cs:__imp_DrawTextA
0x18002ded5  mov     rdx, rdi; hDC
0x18002ded8  mov     rcx, r13; hWnd
0x18002dedb  call    cs:__imp_ReleaseDC
0x18002dee1  mov     eax, [rsp+210h+Rect.bottom]
0x18002dee5  mov     edi, 1324h
0x18002deea  sub     eax, [rsp+210h+Rect.top]
0x18002deee  sub     eax, ebx
0x18002def0  mov     [rsp+210h+var_1D0], eax
0x18002def4  test    eax, eax
0x18002def6  jle     loc_18002DFE8
0x18002defc  lea     rdx, [rsp+210h+var_1C8]; lpRect
0x18002df01  mov     rcx, r15; hWnd
0x18002df04  call    cs:__imp_GetWindowRect
0x18002df0a  mov     r11d, [rsp+210h+var_1C8.bottom]
0x18002df0f  mov     eax, [rsp+210h+var_1C8.right]
0x18002df13  sub     r11d, [rsp+210h+var_1C8.top]
0x18002df18  sub     eax, [rsp+210h+var_1C8.left]
0x18002df1c  mov     ebx, [rsp+210h+var_1D0]
0x18002df20  add     r11d, ebx
0x18002df23  mov     [rsp+210h+uFlags], 16h; uFlags
0x18002df2b  xor     r9d, r9d; Y
0x18002df2e  mov     [rsp+210h+cchWideChar], r11d; cy
0x18002df33  xor     r8d, r8d; X
0x18002df36  xor     edx, edx; hWndInsertAfter
0x18002df38  mov     rcx, r15; hWnd
0x18002df3b  mov     dword ptr [rsp+210h+lpWideCharStr], eax; cx
0x18002df3f  call    cs:__imp_SetWindowPos
0x18002df45  lea     rdx, [rsp+210h+var_1C8]; lpRect
0x18002df4a  mov     rcx, r13; hWnd
0x18002df4d  call    cs:__imp_GetWindowRect
0x18002df53  mov     r11d, [rsp+210h+var_1C8.bottom]
0x18002df58  mov     eax, [rsp+210h+var_1C8.right]
0x18002df5c  sub     r11d, [rsp+210h+var_1C8.top]
0x18002df61  sub     eax, [rsp+210h+var_1C8.left]
0x18002df65  mov     [rsp+210h+uFlags], 16h; uFlags
0x18002df6d  add     r11d, ebx
0x18002df70  xor     r9d, r9d; Y
0x18002df73  xor     r8d, r8d; X
0x18002df76  mov     [rsp+210h+cchWideChar], r11d; cy
0x18002df7b  xor     edx, edx; hWndInsertAfter
0x18002df7d  mov     rcx, r13; hWnd
0x18002df80  mov     dword ptr [rsp+210h+lpWideCharStr], eax; cx
0x18002df84  call    cs:__imp_SetWindowPos
0x18002df8a  mov     edx, edi; nIDDlgItem
0x18002df8c  mov     rcx, r15; hDlg
0x18002df8f  call    cs:__imp_GetDlgItem
0x18002df95  lea     rdx, [rsp+210h+var_1C8]; lpRect
0x18002df9a  mov     rcx, rax; hWnd
0x18002df9d  mov     rbx, rax
0x18002dfa0  call    cs:__imp_GetWindowRect
0x18002dfa6  lea     r8, [rsp+210h+var_1C8]; lpPoints
0x18002dfab  mov     r9d, 2; cPoints
0x18002dfb1  mov     rdx, r15; hWndTo
0x18002dfb4  xor     ecx, ecx; hWndFrom
0x18002dfb6  call    cs:__imp_MapWindowPoints
0x18002dfbc  mov     r9d, [rsp+210h+var_1C8.top]
0x18002dfc1  mov     r8d, [rsp+210h+var_1C8.left]; X
0x18002dfc6  add     r9d, [rsp+210h+var_1D0]; Y
0x18002dfcb  mov     [rsp+210h+uFlags], 15h; uFlags
0x18002dfd3  xor     edx, edx; hWndInsertAfter
0x18002dfd5  mov     rcx, rbx; hWnd
0x18002dfd8  mov     [rsp+210h+cchWideChar], r14d; cy
0x18002dfdd  mov     dword ptr [rsp+210h+lpWideCharStr], r14d; cx
0x18002dfe2  call    cs:__imp_SetWindowPos
0x18002dfe8  cmp     [r12], r14
0x18002dfec  jz      short loc_18002DFFB
0x18002dfee  mov     rdx, [r12]; lpString
0x18002dff2  mov     rcx, r13; hWnd
0x18002dff5  call    cs:__imp_SetWindowTextA
0x18002dffb  mov     r9d, 0FFh; wParam
0x18002e001  mov     edx, edi; nIDDlgItem
0x18002e003  mov     rcx, r15; hDlg
0x18002e006  lea     r8d, [r9-3Ah]; Msg
0x18002e00a  mov     [rsp+210h+lpWideCharStr], r14; lParam
0x18002e00f  call    cs:__imp_SendDlgItemMessageA
0x18002e015  mov     r8, [r12+10h]; lpString
0x18002e01a  test    r8, r8
0x18002e01d  jz      short loc_18002E02A
0x18002e01f  mov     edx, edi; nIDDlgItem
0x18002e021  mov     rcx, r15; hDlg
0x18002e024  call    cs:__imp_SetDlgItemTextA
0x18002e02a  lea     rdx, [rsp+210h+var_1A8]; lpRect
0x18002e02f  mov     rcx, r15; hWnd
0x18002e032  call    cs:__imp_GetWindowRect
0x18002e038  mov     eax, 80000000h
0x18002e03d  cmp     [r12+18h], eax
0x18002e042  jz      loc_18002E0D5
0x18002e048  cmp     [r12+1Ch], eax
0x18002e04d  jz      loc_18002E0D5
0x18002e053  mov     rcx, r15; hWnd
0x18002e056  call    cs:__imp_GetParent
0x18002e05c  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x18002e063  call    ?DpiX@DPIMGR@@QEAAIXZ; DPIMGR::DpiX(void)
0x18002e068  mov     ecx, [r12+18h]; int
0x18002e06d  xor     edx, edx
0x18002e06f  mov     r11d, eax
0x18002e072  mov     edi, 5A0h
0x18002e077  mov     eax, edi
0x18002e079  div     r11d
0x18002e07c  mov     edx, eax; int
0x18002e07e  call    ?RoundDiv@@YAHJJ@Z; RoundDiv(long,long)
0x18002e083  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x18002e08a  mov     ebx, eax
0x18002e08c  call    ?DpiY@DPIMGR@@QEAAIXZ; DPIMGR::DpiY(void)
0x18002e091  mov     ecx, [r12+1Ch]; int
0x18002e096  mov     r11d, eax
0x18002e099  xor     edx, edx
0x18002e09b  mov     eax, edi
0x18002e09d  div     r11d
0x18002e0a0  mov     edx, eax; int
0x18002e0a2  call    ?RoundDiv@@YAHJJ@Z; RoundDiv(long,long)
0x18002e0a7  mov     ecx, [rsp+210h+var_1A8.bottom]
0x18002e0ab  mov     r9d, [rsp+210h+var_1A8.right]
0x18002e0b0  sub     ecx, [rsp+210h+var_1A8.top]
0x18002e0b4  sub     r9d, [rsp+210h+var_1A8.left]; nWidth
0x18002e0b9  mov     [rsp+210h+cchWideChar], 1; bRepaint
0x18002e0c1  mov     dword ptr [rsp+210h+lpWideCharStr], ecx; nHeight
0x18002e0c5  mov     r8d, eax; Y
0x18002e0c8  mov     edx, ebx; X
0x18002e0ca  mov     rcx, r15; hWnd
0x18002e0cd  call    cs:__imp_MoveWindow
0x18002e0d3  jmp     short loc_18002E0DD
0x18002e0d5  mov     rcx, r15; HWND
0x18002e0d8  call    ?DlgInit@@YAXPEAUHWND__@@@Z; DlgInit(HWND__ *)
0x18002e0dd  mov     rax, [r12+20h]
0x18002e0e2  test    rax, rax
0x18002e0e5  jz      short loc_18002E0F2
0x18002e0e7  cmp     [rax], r14b
0x18002e0ea  jz      short loc_18002E0F2
0x18002e0ec  mov     r14d, 5
0x18002e0f2  mov     edx, 1326h; nIDDlgItem
0x18002e0f7  mov     rcx, r15; hDlg
0x18002e0fa  call    cs:__imp_GetDlgItem
0x18002e100  mov     edx, r14d; nCmdShow
0x18002e103  mov     rcx, rax; hWnd
0x18002e106  call    cs:__imp_ShowWindow
0x18002e10c  jmp     short loc_18002E13B
0x18002e10e  xor     r14d, r14d
0x18002e111  cmp     cs:bEnable, r14d
0x18002e118  jz      short loc_18002E13B
0x18002e11a  call    ?GetThreadHwndMain@@YAPEAUHWND__@@XZ; GetThreadHwndMain(void)
0x18002e11f  mov     r9d, cs:dword_1803F99EC; int
0x18002e126  mov     rdx, cs:qword_1803F99F0; char *
0x18002e12d  mov     rcx, rax; HWND
0x18002e130  mov     r8d, 1; unsigned int
0x18002e136  call    ?CallHelp@@YAHPEAUHWND__@@PEBDIJ@Z; CallHelp(HWND__ *,char const *,uint,long)
0x18002e13b  mov     eax, 1
0x18002e140  mov     rcx, [rbp+110h+var_30]
0x18002e147  xor     rcx, rsp; StackCookie
0x18002e14a  call    __security_check_cookie
0x18002e14f  lea     r11, [rsp+210h+var_20]
0x18002e157  mov     rbx, [r11+38h]
0x18002e15b  mov     rdi, [r11+40h]
0x18002e15f  mov     rsp, r11
0x18002e162  pop     r15
0x18002e164  pop     r14
0x18002e166  pop     r13
0x18002e168  pop     r12
0x18002e16a  pop     rbp
0x18002e16b  retn
```
