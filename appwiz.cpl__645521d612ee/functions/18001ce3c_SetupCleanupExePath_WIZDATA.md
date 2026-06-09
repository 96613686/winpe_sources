# SetupCleanupExePath(_WIZDATA *)

- ea: `0x18001ce3c`
- end: `0x18001cfc6`
- name: `?SetupCleanupExePath@@YAHPEAU_WIZDATA@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(struct _WIZDATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001d0a0`

## callees

- `0x18000791c`
- `0x18001c264`
- `0x18001c4b0`
- `0x18001ce3c`
- `0x18001cfcc`

## import_xrefs

- `SHELL32!__imp_PathResolve` at `0x18001cf34`
- `SHELL32!__imp_PathResolve` at `0x18001cf34`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18001cf25`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18001cf25`
- `SHLWAPI!PathQuoteSpacesW` at `0x18001ce82`
- `SHLWAPI!PathQuoteSpacesW` at `0x18001cf74`
- `SHLWAPI!PathQuoteSpacesW` at `0x18001ce82`
- `SHLWAPI!PathQuoteSpacesW` at `0x18001cf74`
- `SHLWAPI!PathRemoveBlanksW` at `0x18001ce8b`
- `SHLWAPI!PathRemoveBlanksW` at `0x18001ce8b`
- `SHLWAPI!PathFileExistsW` at `0x18001ce75`
- `SHLWAPI!PathFileExistsW` at `0x18001ce75`
- `SHLWAPI!PathGetArgsW` at `0x18001cefc`
- `SHLWAPI!PathGetArgsW` at `0x18001cefc`
- `SHLWAPI!PathFindExtensionW` at `0x18001cf41`
- `SHLWAPI!PathFindExtensionW` at `0x18001cf41`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18001cfa7`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18001cfa7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001cec4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001cec4`
- `KERNEL32!lstrcmpW` at `0x18001ced0`
- `KERNEL32!lstrcmpW` at `0x18001ced0`
- `USER32!LoadCursorW` at `0x18001cea2`
- `USER32!LoadCursorW` at `0x18001cea2`
- `USER32!GetDlgItemTextW` at `0x18001ce6c`
- `USER32!GetDlgItemTextW` at `0x18001ce6c`
- `USER32!SetCursor` at `0x18001ceab`
- `USER32!SetCursor` at `0x18001cf7d`
- `USER32!SetCursor` at `0x18001ceab`
- `USER32!SetCursor` at `0x18001cf7d`

## pseudocode

```c
__int64 __fastcall SetupCleanupExePath(struct _WIZDATA *a1)
{
  WCHAR *v1; // rsi
  unsigned int v3; // ebp
  HCURSOR CursorW; // rax
  HCURSOR v5; // r15
  WCHAR *v6; // rbx
  const unsigned __int16 *ArgsW; // rax
  _WORD *v8; // r11
  const unsigned __int16 *ExtensionW; // r14

  v1 = (WCHAR *)((char *)a1 + 12);
  v3 = 0;
  GetDlgItemTextW(*(HWND *)a1, 1003, (LPWSTR)a1 + 6, 260);
  if ( PathFileExistsW(v1) )
    PathQuoteSpacesW(v1);
  PathRemoveBlanksW(v1);
  if ( !*v1 )
    goto LABEL_13;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v5 = SetCursor(CursorW);
  ExpandEnvironmentStringsW(v1, (LPWSTR)a1 + 266, 0x104u);
  if ( lstrcmpW(v1, (LPCWSTR)a1 + 266) )
    *((_DWORD *)a1 + 2) |= 0x10000000u;
  v6 = (WCHAR *)((char *)a1 + ((*((_DWORD *)a1 + 2) & 0x10000000) != 0 ? 0x208 : 0) + 12);
  ArgsW = PathGetArgsW(v6);
  StringCchCopyW((unsigned __int16 *)a1 + 526, 0x104u, ArgsW);
  if ( *v8 )
    *(v8 - 1) = 0;
  PathUnquoteSpacesW(v6);
  if ( PathResolve(v6, 0, 3u) )
  {
    v3 = 1;
    ExtensionW = PathFindExtensionW(v6);
    FindWorkingDir(a1);
    if ( (*((_DWORD *)a1 + 2) & 0x10000000) != 0 )
    {
      if ( *ExtensionW )
        _ReplaceCmdlineExtension(v1, ExtensionW);
    }
  }
  PathQuoteSpacesW(v6);
  SetCursor(v5);
  if ( !v3 )
  {
LABEL_13:
    ShellMessageBoxW(g_hinst, *(HWND *)a1, (LPCWSTR)0x7D3, 0, 0x30u, v1);
    BrowseSetActive(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x18001ce3c  push    rbx
0x18001ce3e  push    rbp
0x18001ce3f  push    rsi
0x18001ce40  push    rdi
0x18001ce41  push    r12
0x18001ce43  push    r14
0x18001ce45  push    r15
0x18001ce47  sub     rsp, 30h
0x18001ce4b  lea     rsi, [rcx+0Ch]
0x18001ce4f  mov     rdi, rcx
0x18001ce52  mov     rcx, [rcx]; hDlg
0x18001ce55  mov     r14d, 104h
0x18001ce5b  xor     r12d, r12d
0x18001ce5e  mov     r9d, r14d; cchMax
0x18001ce61  mov     r8, rsi; lpString
0x18001ce64  mov     edx, 3EBh; nIDDlgItem
0x18001ce69  mov     ebp, r12d
0x18001ce6c  call    cs:__imp_GetDlgItemTextW
0x18001ce72  mov     rcx, rsi; pszPath
0x18001ce75  call    cs:__imp_PathFileExistsW
0x18001ce7b  test    eax, eax
0x18001ce7d  jz      short loc_18001CE88
0x18001ce7f  mov     rcx, rsi; lpsz
0x18001ce82  call    cs:__imp_PathQuoteSpacesW
0x18001ce88  mov     rcx, rsi; pszPath
0x18001ce8b  call    cs:__imp_PathRemoveBlanksW
0x18001ce91  cmp     [rsi], r12w
0x18001ce95  jz      loc_18001CF87
0x18001ce9b  mov     edx, 7F02h; lpCursorName
0x18001cea0  xor     ecx, ecx; hInstance
0x18001cea2  call    cs:__imp_LoadCursorW
0x18001cea8  mov     rcx, rax; hCursor
0x18001ceab  call    cs:__imp_SetCursor
0x18001ceb1  lea     rbx, [rdi+214h]
0x18001ceb8  mov     r8d, r14d; nSize
0x18001cebb  mov     rdx, rbx; lpDst
0x18001cebe  mov     rcx, rsi; lpSrc
0x18001cec1  mov     r15, rax
0x18001cec4  call    cs:__imp_ExpandEnvironmentStringsW
0x18001ceca  mov     rdx, rbx; lpString2
0x18001cecd  mov     rcx, rsi; lpString1
0x18001ced0  call    cs:__imp_lstrcmpW
0x18001ced6  test    eax, eax
0x18001ced8  jz      short loc_18001CEDF
0x18001ceda  bts     dword ptr [rdi+8], 1Ch
0x18001cedf  mov     eax, [rdi+8]
0x18001cee2  lea     rbx, [rdi+0Ch]
0x18001cee6  and     eax, 10000000h
0x18001ceeb  neg     eax
0x18001ceed  sbb     rcx, rcx
0x18001cef0  and     ecx, 208h
0x18001cef6  add     rbx, rcx
0x18001cef9  mov     rcx, rbx; pszPath
0x18001cefc  call    cs:__imp_PathGetArgsW
0x18001cf02  lea     rcx, [rdi+41Ch]; unsigned __int16 *
0x18001cf09  mov     rdx, r14; unsigned __int64
0x18001cf0c  mov     r8, rax; unsigned __int16 *
0x18001cf0f  mov     r11, rax
0x18001cf12  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001cf17  cmp     [r11], r12w
0x18001cf1b  jz      short loc_18001CF22
0x18001cf1d  mov     [r11-2], r12w
0x18001cf22  mov     rcx, rbx; lpsz
0x18001cf25  call    cs:__imp_PathUnquoteSpacesW
0x18001cf2b  xor     edx, edx; dirs
0x18001cf2d  mov     rcx, rbx; pszPath
0x18001cf30  lea     r8d, [rdx+3]; fFlags
0x18001cf34  call    cs:__imp_PathResolve
0x18001cf3a  test    eax, eax
0x18001cf3c  jz      short loc_18001CF71
0x18001cf3e  mov     rcx, rbx; pszPath
0x18001cf41  call    cs:__imp_PathFindExtensionW
0x18001cf47  mov     rcx, rdi; struct _WIZDATA *
0x18001cf4a  mov     ebp, 1
0x18001cf4f  mov     r14, rax
0x18001cf52  call    ?FindWorkingDir@@YAXPEAU_WIZDATA@@@Z; FindWorkingDir(_WIZDATA *)
0x18001cf57  test    dword ptr [rdi+8], 10000000h
0x18001cf5e  jz      short loc_18001CF71
0x18001cf60  cmp     [r14], r12w
0x18001cf64  jz      short loc_18001CF71
0x18001cf66  mov     rdx, r14; unsigned __int16 *
0x18001cf69  mov     rcx, rsi; unsigned __int16 *
0x18001cf6c  call    ?_ReplaceCmdlineExtension@@YAXPEAGPEBG@Z; _ReplaceCmdlineExtension(ushort *,ushort const *)
0x18001cf71  mov     rcx, rbx; lpsz
0x18001cf74  call    cs:__imp_PathQuoteSpacesW
0x18001cf7a  mov     rcx, r15; hCursor
0x18001cf7d  call    cs:__imp_SetCursor
0x18001cf83  test    ebp, ebp
0x18001cf85  jnz     short loc_18001CFB5
0x18001cf87  mov     rdx, [rdi]; hWnd
0x18001cf8a  xor     r9d, r9d; lpcTitle
0x18001cf8d  mov     rcx, cs:g_hinst; hAppInst
0x18001cf94  mov     r8d, 7D3h; lpcText
0x18001cf9a  mov     [rsp+68h+var_40], rsi
0x18001cf9f  mov     [rsp+68h+fuStyle], 30h ; '0'; fuStyle
0x18001cfa7  call    cs:__imp_ShellMessageBoxW
0x18001cfad  mov     rcx, rdi; struct _WIZDATA *
0x18001cfb0  call    ?BrowseSetActive@@YAXPEAU_WIZDATA@@@Z; BrowseSetActive(_WIZDATA *)
0x18001cfb5  mov     eax, ebp
0x18001cfb7  add     rsp, 30h
0x18001cfbb  pop     r15
0x18001cfbd  pop     r14
0x18001cfbf  pop     r12
0x18001cfc1  pop     rdi
0x18001cfc2  pop     rsi
0x18001cfc3  pop     rbp
0x18001cfc4  pop     rbx
0x18001cfc5  retn
```
