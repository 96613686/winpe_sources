# CreateLink

- ea: `0x18002e9ac`
- end: `0x18002ed0a`
- name: `CreateLink`
- size: `862`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180055290`

## callees

- `0x18000791c`
- `0x18002e61c`
- `0x18002e764`
- `0x18002e9ac`
- `0x18002ed10`
- `0x18002ed68`
- `0x1800582a2`
- `0x1800582e0`
- `0x1800583a0`
- `0x180059010`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x18002ebe4`
- `SHELL32!SHChangeNotify` at `0x18002ec8f`
- `SHELL32!SHChangeNotify` at `0x18002ebe4`
- `SHELL32!SHChangeNotify` at `0x18002ec8f`
- `SHELL32!__imp_SHAddToRecentDocsEx` at `0x18002ece2`
- `SHELL32!__imp_SHAddToRecentDocsEx` at `0x18002ece2`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002ec28`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002ec28`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ecbf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ecbf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002eb88`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002eb88`
- `USER32!LoadCursorW` at `0x18002e9e1`
- `USER32!LoadCursorW` at `0x18002e9e1`
- `USER32!SetCursor` at `0x18002e9ea`
- `USER32!SetCursor` at `0x18002ec98`
- `USER32!SetCursor` at `0x18002e9ea`
- `USER32!SetCursor` at `0x18002ec98`

## pseudocode

```c
_BOOL8 __fastcall CreateLink(__int64 a1)
{
  HCURSOR CursorW; // rax
  HCURSOR v3; // rsi
  int LinkElevated; // ebx
  unsigned int v5; // r11d
  unsigned int v6; // r11d
  unsigned int v7; // r11d
  unsigned __int64 v8; // r11
  const unsigned __int16 *v9; // r8
  unsigned __int64 v10; // r11
  unsigned __int64 v11; // r11
  const unsigned __int16 *v12; // r8
  int cchWideChar; // r11d
  int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  unsigned __int16 *v19; // rdx
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v22[260]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 v23[260]; // [rsp+23Ch] [rbp+13Ch] BYREF
  unsigned __int16 v24[260]; // [rsp+444h] [rbp+344h] BYREF
  unsigned __int16 v25[260]; // [rsp+64Ch] [rbp+54Ch] BYREF
  unsigned __int16 v26[260]; // [rsp+854h] [rbp+754h] BYREF
  unsigned __int16 v27[260]; // [rsp+A5Ch] [rbp+95Ch] BYREF
  unsigned __int16 v28[260]; // [rsp+C64h] [rbp+B64h] BYREF
  unsigned __int16 v29[260]; // [rsp+E6Ch] [rbp+D6Ch] BYREF
  WCHAR String1[260]; // [rsp+1074h] [rbp+F74h] BYREF
  WCHAR WideCharStr[266]; // [rsp+127Ch] [rbp+117Ch] BYREF
  unsigned __int16 dwItem1[264]; // [rsp+1490h] [rbp+1390h] BYREF

  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v3 = SetCursor(CursorW);
  memset_0(dwItem1, 0, 0x208u);
  GetLinkName(dwItem1);
  memset_0(&v21, 0, 0x1458u);
  v21 = *(_DWORD *)(a1 + 8);
  WideCharStr[260] = *(_WORD *)(a1 + 2940);
  LinkElevated = StringCchCopyW(v22, 0x104u, dwItem1);
  if ( LinkElevated >= 0 )
  {
    LinkElevated = StringCchCopyW(v23, v5, (const unsigned __int16 *)(a1 + 12));
    if ( LinkElevated >= 0 )
    {
      LinkElevated = StringCchCopyW(v24, v6, (const unsigned __int16 *)(a1 + 1052));
      if ( LinkElevated >= 0 )
      {
        LinkElevated = StringCchCopyW(v25, v7, (const unsigned __int16 *)(a1 + 2092));
        if ( LinkElevated >= 0 )
        {
          v9 = *(const unsigned __int16 **)(a1 + 3296);
          if ( !v9 || (LinkElevated = StringCchCopyW(v26, (unsigned int)v8, v9), LinkElevated >= 0) )
          {
            LinkElevated = StringCchCopyW(v27, v8, (const unsigned __int16 *)(a1 + 532));
            if ( LinkElevated >= 0 )
            {
              LinkElevated = StringCchCopyW(v28, v10, (const unsigned __int16 *)(a1 + 1572));
              if ( LinkElevated >= 0 )
              {
                v12 = *(const unsigned __int16 **)(a1 + 2624);
                if ( !v12 || (LinkElevated = StringCchCopyW(v29, v11, v12), LinkElevated >= 0) )
                {
                  LinkElevated = StringCchCopyW(String1, v11, (const unsigned __int16 *)(a1 + 3312));
                  if ( LinkElevated >= 0 )
                  {
                    MultiByteToWideChar(0, 0, (LPCCH)(a1 + 2860), -1, WideCharStr, cchWideChar);
                    v14 = _RenameLink((struct tagCREATELINKDATA *)&v21, *(HWND *)a1);
                    LinkElevated = v14;
                    if ( v14 < 0 )
                    {
                      if ( v14 == -2147024891 || v14 == -2144927711 )
                      {
                        LinkElevated = _CreateLinkElevated(
                                         (struct tagCREATELINKDATA *)&v21,
                                         *(HWND *)a1,
                                         *(struct INewShortcutHookW **)(a1 + 3304));
                        if ( LinkElevated >= 0 )
                          SHChangeNotify(0x2000, 0x1005u, dwItem1, 0);
                      }
                    }
                    else
                    {
                      v15 = *(_QWORD *)(a1 + 3304);
                      *(_QWORD *)(a1 + 3296) = 0;
                      v26[0] = 0;
                      v16 = CreateNewLink(&v21, v15);
                      LinkElevated = v16;
                      if ( v16 >= 0
                        || v16 == -2147024891
                        && (LinkElevated = _CreateLinkElevated(
                                             (struct tagCREATELINKDATA *)&v21,
                                             *(HWND *)a1,
                                             *(struct INewShortcutHookW **)(a1 + 3304)),
                            LinkElevated >= 0) )
                      {
                        SHChangeNotify(0x2000, 0x1005u, dwItem1, 0);
                      }
                      else
                      {
                        ShellMessageBoxW(g_hinst, *(HWND *)a1, (LPCWSTR)0x7EB, 0, 0x30u);
                      }
                      v17 = *(_QWORD *)(a1 + 3304);
                      *(_QWORD *)(a1 + 3304) = 0;
                      if ( v17 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  SetCursor(v3);
  if ( LinkElevated >= 0 )
  {
    v18 = CompareStringOrdinal(String1, -1, L".url", -1, 1);
    v19 = dwItem1;
    if ( v18 != 2 )
      v19 = v23;
    SHAddToRecentDocsEx(3, v19);
  }
  return LinkElevated >= 0;
}

```

## disassembly

```asm
0x18002e9ac  push    rbp
0x18002e9ae  push    rbx
0x18002e9af  push    rsi
0x18002e9b0  push    rdi
0x18002e9b1  lea     rbp, [rsp-15B8h]
0x18002e9b9  mov     eax, 16B8h
0x18002e9be  call    _alloca_probe
0x18002e9c3  sub     rsp, rax
0x18002e9c6  mov     rax, cs:__security_cookie
0x18002e9cd  xor     rax, rsp
0x18002e9d0  mov     [rbp+15D0h+var_30], rax
0x18002e9d7  mov     rdi, rcx
0x18002e9da  mov     edx, 7F02h; lpCursorName
0x18002e9df  xor     ecx, ecx; hInstance
0x18002e9e1  call    cs:__imp_LoadCursorW
0x18002e9e7  mov     rcx, rax; hCursor
0x18002e9ea  call    cs:__imp_SetCursor
0x18002e9f0  xor     edx, edx; Val
0x18002e9f2  lea     rcx, [rbp+15D0h+dwItem1]; void *
0x18002e9f9  mov     r8d, 208h; Size
0x18002e9ff  mov     rsi, rax
0x18002ea02  call    memset_0
0x18002ea07  mov     r8, rdi
0x18002ea0a  lea     rcx, [rbp+15D0h+dwItem1]; unsigned __int16 *
0x18002ea11  call    GetLinkName
0x18002ea16  xor     edx, edx; Val
0x18002ea18  lea     rcx, [rsp+16D0h+var_16A0]; void *
0x18002ea1d  mov     r8d, 1458h; Size
0x18002ea23  call    memset_0
0x18002ea28  mov     ecx, [rdi+8]
0x18002ea2b  lea     r8, [rbp+15D0h+dwItem1]; unsigned __int16 *
0x18002ea32  mov     [rsp+16D0h+var_16A0], ecx
0x18002ea36  mov     r11d, 104h
0x18002ea3c  movzx   ecx, word ptr [rdi+0B7Ch]
0x18002ea43  mov     edx, r11d; unsigned __int64
0x18002ea46  mov     [rbp+15D0h+var_24C], cx
0x18002ea4d  lea     rcx, [rsp+16D0h+var_169C]; unsigned __int16 *
0x18002ea52  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ea57  mov     ebx, eax
0x18002ea59  test    eax, eax
0x18002ea5b  js      loc_18002EC95
0x18002ea61  lea     r8, [rdi+0Ch]; unsigned __int16 *
0x18002ea65  mov     edx, r11d; unsigned __int64
0x18002ea68  lea     rcx, [rbp+15D0h+var_1494]; unsigned __int16 *
0x18002ea6f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ea74  mov     ebx, eax
0x18002ea76  test    eax, eax
0x18002ea78  js      loc_18002EC95
0x18002ea7e  lea     r8, [rdi+41Ch]; unsigned __int16 *
0x18002ea85  mov     edx, r11d; unsigned __int64
0x18002ea88  lea     rcx, [rbp+15D0h+var_128C]; unsigned __int16 *
0x18002ea8f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ea94  mov     ebx, eax
0x18002ea96  test    eax, eax
0x18002ea98  js      loc_18002EC95
0x18002ea9e  lea     r8, [rdi+82Ch]; unsigned __int16 *
0x18002eaa5  mov     edx, r11d; unsigned __int64
0x18002eaa8  lea     rcx, [rbp+15D0h+var_1084]; unsigned __int16 *
0x18002eaaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002eab4  mov     ebx, eax
0x18002eab6  test    eax, eax
0x18002eab8  js      loc_18002EC95
0x18002eabe  mov     r8, [rdi+0CE0h]; unsigned __int16 *
0x18002eac5  test    r8, r8
0x18002eac8  jz      short loc_18002EAE3
0x18002eaca  mov     edx, r11d; unsigned __int64
0x18002eacd  lea     rcx, [rbp+15D0h+var_E7C]; unsigned __int16 *
0x18002ead4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ead9  mov     ebx, eax
0x18002eadb  test    eax, eax
0x18002eadd  js      loc_18002EC95
0x18002eae3  lea     r8, [rdi+214h]; unsigned __int16 *
0x18002eaea  mov     rdx, r11; unsigned __int64
0x18002eaed  lea     rcx, [rbp+15D0h+var_C74]; unsigned __int16 *
0x18002eaf4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002eaf9  mov     ebx, eax
0x18002eafb  test    eax, eax
0x18002eafd  js      loc_18002EC95
0x18002eb03  lea     r8, [rdi+624h]; unsigned __int16 *
0x18002eb0a  mov     rdx, r11; unsigned __int64
0x18002eb0d  lea     rcx, [rbp+15D0h+var_A6C]; unsigned __int16 *
0x18002eb14  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002eb19  mov     ebx, eax
0x18002eb1b  test    eax, eax
0x18002eb1d  js      loc_18002EC95
0x18002eb23  mov     r8, [rdi+0A40h]; unsigned __int16 *
0x18002eb2a  test    r8, r8
0x18002eb2d  jz      short loc_18002EB48
0x18002eb2f  mov     rdx, r11; unsigned __int64
0x18002eb32  lea     rcx, [rbp+15D0h+var_864]; unsigned __int16 *
0x18002eb39  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002eb3e  mov     ebx, eax
0x18002eb40  test    eax, eax
0x18002eb42  js      loc_18002EC95
0x18002eb48  lea     r8, [rdi+0CF0h]; unsigned __int16 *
0x18002eb4f  mov     rdx, r11; unsigned __int64
0x18002eb52  lea     rcx, [rbp+15D0h+String1]; unsigned __int16 *
0x18002eb59  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002eb5e  mov     ebx, eax
0x18002eb60  test    eax, eax
0x18002eb62  js      loc_18002EC95
0x18002eb68  lea     rax, [rbp+15D0h+WideCharStr]
0x18002eb6f  mov     [rsp+16D0h+cchWideChar], r11d; cchWideChar
0x18002eb74  lea     r8, [rdi+0B2Ch]; lpMultiByteStr
0x18002eb7b  mov     [rsp+16D0h+lpWideCharStr], rax; lpWideCharStr
0x18002eb80  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002eb84  xor     edx, edx; dwFlags
0x18002eb86  xor     ecx, ecx; CodePage
0x18002eb88  call    cs:__imp_MultiByteToWideChar
0x18002eb8e  mov     rdx, [rdi]; HWND
0x18002eb91  lea     rcx, [rsp+16D0h+var_16A0]; struct tagCREATELINKDATA *
0x18002eb96  call    ?_RenameLink@@YAJPEAUtagCREATELINKDATA@@PEAUHWND__@@@Z; _RenameLink(tagCREATELINKDATA *,HWND__ *)
0x18002eb9b  mov     ebx, eax
0x18002eb9d  test    eax, eax
0x18002eb9f  js      loc_18002EC53
0x18002eba5  mov     rdx, [rdi+0CE8h]
0x18002ebac  lea     rcx, [rsp+16D0h+var_16A0]
0x18002ebb1  xor     eax, eax
0x18002ebb3  mov     qword ptr [rdi+0CE0h], 0
0x18002ebbe  mov     [rbp+15D0h+var_E7C], ax
0x18002ebc5  call    _CreateNewLink
0x18002ebca  mov     ebx, eax
0x18002ebcc  test    eax, eax
0x18002ebce  js      short loc_18002EBEC
0x18002ebd0  xor     r9d, r9d; dwItem2
0x18002ebd3  lea     r8, [rbp+15D0h+dwItem1]; dwItem1
0x18002ebda  mov     edx, 1005h; uFlags
0x18002ebdf  mov     ecx, 2000h; wEventId
0x18002ebe4  call    cs:__imp_SHChangeNotify
0x18002ebea  jmp     short loc_18002EC2E
0x18002ebec  cmp     eax, 80070005h
0x18002ebf1  jnz     short loc_18002EC0D
0x18002ebf3  mov     r8, [rdi+0CE8h]; struct INewShortcutHookW *
0x18002ebfa  lea     rcx, [rsp+16D0h+var_16A0]; struct tagCREATELINKDATA *
0x18002ebff  mov     rdx, [rdi]; HWND
0x18002ec02  call    ?_CreateLinkElevated@@YAJPEAUtagCREATELINKDATA@@PEAUHWND__@@PEAUINewShortcutHookW@@@Z; _CreateLinkElevated(tagCREATELINKDATA *,HWND__ *,INewShortcutHookW *)
0x18002ec07  mov     ebx, eax
0x18002ec09  test    eax, eax
0x18002ec0b  jns     short loc_18002EBD0
0x18002ec0d  mov     rdx, [rdi]; hWnd
0x18002ec10  xor     r9d, r9d; lpcTitle
0x18002ec13  mov     rcx, cs:g_hinst; hAppInst
0x18002ec1a  mov     r8d, 7EBh; lpcText
0x18002ec20  mov     dword ptr [rsp+16D0h+lpWideCharStr], 30h ; '0'; fuStyle
0x18002ec28  call    cs:__imp_ShellMessageBoxW
0x18002ec2e  mov     rcx, [rdi+0CE8h]
0x18002ec35  mov     qword ptr [rdi+0CE8h], 0
0x18002ec40  test    rcx, rcx
0x18002ec43  jz      short loc_18002EC95
0x18002ec45  mov     rax, [rcx]
0x18002ec48  mov     rax, [rax+10h]
0x18002ec4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec51  jmp     short loc_18002EC95
0x18002ec53  cmp     eax, 80070005h
0x18002ec58  jz      short loc_18002EC61
0x18002ec5a  cmp     eax, 80270021h
0x18002ec5f  jnz     short loc_18002EC95
0x18002ec61  mov     r8, [rdi+0CE8h]; struct INewShortcutHookW *
0x18002ec68  lea     rcx, [rsp+16D0h+var_16A0]; struct tagCREATELINKDATA *
0x18002ec6d  mov     rdx, [rdi]; HWND
0x18002ec70  call    ?_CreateLinkElevated@@YAJPEAUtagCREATELINKDATA@@PEAUHWND__@@PEAUINewShortcutHookW@@@Z; _CreateLinkElevated(tagCREATELINKDATA *,HWND__ *,INewShortcutHookW *)
0x18002ec75  mov     ebx, eax
0x18002ec77  test    eax, eax
0x18002ec79  js      short loc_18002EC95
0x18002ec7b  xor     r9d, r9d; dwItem2
0x18002ec7e  lea     r8, [rbp+15D0h+dwItem1]; dwItem1
0x18002ec85  mov     edx, 1005h; uFlags
0x18002ec8a  mov     ecx, 2000h; wEventId
0x18002ec8f  call    cs:__imp_SHChangeNotify
0x18002ec95  mov     rcx, rsi; hCursor
0x18002ec98  call    cs:__imp_SetCursor
0x18002ec9e  test    ebx, ebx
0x18002eca0  js      short loc_18002ECE8
0x18002eca2  or      r9d, 0FFFFFFFFh; cchCount2
0x18002eca6  mov     dword ptr [rsp+16D0h+lpWideCharStr], 1; bIgnoreCase
0x18002ecae  or      edx, r9d; cchCount1
0x18002ecb1  lea     r8, aUrl; ".url"
0x18002ecb8  lea     rcx, [rbp+15D0h+String1]; lpString1
0x18002ecbf  call    cs:__imp_CompareStringOrdinal
0x18002ecc5  mov     r8d, 4
0x18002eccb  lea     rdx, [rbp+15D0h+dwItem1]
0x18002ecd2  lea     ecx, [r8-1]
0x18002ecd6  cmp     eax, 2
0x18002ecd9  jz      short loc_18002ECE2
0x18002ecdb  lea     rdx, [rbp+15D0h+var_1494]
0x18002ece2  call    cs:__imp_SHAddToRecentDocsEx
0x18002ece8  not     ebx
0x18002ecea  shr     ebx, 1Fh
0x18002eced  mov     eax, ebx
0x18002ecef  mov     rcx, [rbp+15D0h+var_30]
0x18002ecf6  xor     rcx, rsp; StackCookie
0x18002ecf9  call    __security_check_cookie
0x18002ecfe  add     rsp, 16B8h
0x18002ed05  pop     rdi
0x18002ed06  pop     rsi
0x18002ed07  pop     rbx
0x18002ed08  pop     rbp
0x18002ed09  retn
```
