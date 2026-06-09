# NextPushed(_WIZDATA *)

- ea: `0x18001c5cc`
- end: `0x18001c97b`
- name: `?NextPushed@@YAHPEAU_WIZDATA@@@Z`
- size: `943`
- prototype: `__int64 __fastcall(struct _WIZDATA *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001d0a0`

## callees

- `0x18000791c`
- `0x18001c264`
- `0x18001c310`
- `0x18001c4b0`
- `0x18001c5cc`
- `0x18001cd5c`
- `0x18001d3e0`
- `0x18001d4f0`
- `0x180059010`

## import_xrefs

- `SHELL32!__imp_PathResolve` at `0x18001c7d4`
- `SHELL32!__imp_PathResolve` at `0x18001c83f`
- `SHELL32!__imp_PathResolve` at `0x18001c7d4`
- `SHELL32!__imp_PathResolve` at `0x18001c83f`
- `SHELL32!__imp_SHValidateUNC` at `0x18001c79a`
- `SHELL32!__imp_SHValidateUNC` at `0x18001c79a`
- `SHLWAPI!PathRemoveArgsW` at `0x18001c831`
- `SHLWAPI!PathRemoveArgsW` at `0x18001c831`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18001c694`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18001c6b5`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18001c694`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18001c6b5`
- `SHLWAPI!PathIsRootW` at `0x18001c7ab`
- `SHLWAPI!PathIsRootW` at `0x18001c7ab`
- `SHLWAPI!PathRemoveBlanksW` at `0x18001c601`
- `SHLWAPI!PathRemoveBlanksW` at `0x18001c601`
- `SHLWAPI!PathFileExistsW` at `0x18001c654`
- `SHLWAPI!PathFileExistsW` at `0x18001c654`
- `SHLWAPI!PathGetArgsW` at `0x18001c66b`
- `SHLWAPI!PathGetArgsW` at `0x18001c6a1`
- `SHLWAPI!PathGetArgsW` at `0x18001c66b`
- `SHLWAPI!PathGetArgsW` at `0x18001c6a1`
- `SHLWAPI!PathFindExtensionW` at `0x18001c7e5`
- `SHLWAPI!PathFindExtensionW` at `0x18001c8af`
- `SHLWAPI!PathFindExtensionW` at `0x18001c8f1`
- `SHLWAPI!PathFindExtensionW` at `0x18001c7e5`
- `SHLWAPI!PathFindExtensionW` at `0x18001c8af`
- `SHLWAPI!PathFindExtensionW` at `0x18001c8f1`
- `SHLWAPI!PathIsUNCW` at `0x18001c785`
- `SHLWAPI!PathIsUNCW` at `0x18001c785`
- `SHLWAPI!__imp_StrCmpCW` at `0x18001c627`
- `SHLWAPI!__imp_StrCmpCW` at `0x18001c627`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18001c940`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18001c940`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001c617`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001c617`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001c828`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001c828`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18001c7c2`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18001c7c2`
- `KERNEL32!lstrcmpiW` at `0x18001c7f5`
- `KERNEL32!lstrcmpiW` at `0x18001c85c`
- `KERNEL32!lstrcmpiW` at `0x18001c7f5`
- `KERNEL32!lstrcmpiW` at `0x18001c85c`
- `USER32!LoadCursorW` at `0x18001c6cc`
- `USER32!LoadCursorW` at `0x18001c6cc`
- `USER32!GetDlgItemTextW` at `0x18001c5f8`
- `USER32!GetDlgItemTextW` at `0x18001c5f8`
- `USER32!SetCursor` at `0x18001c6d5`
- `USER32!SetCursor` at `0x18001c917`
- `USER32!SetCursor` at `0x18001c971`
- `USER32!SetCursor` at `0x18001c6d5`
- `USER32!SetCursor` at `0x18001c917`
- `USER32!SetCursor` at `0x18001c971`

## pseudocode

```c
__int64 __fastcall NextPushed(struct _WIZDATA *a1)
{
  WCHAR *v1; // r14
  unsigned int *v3; // rdi
  WCHAR *v4; // rsi
  const unsigned __int16 *ArgsW; // rax
  _WORD *v6; // r11
  LPWSTR v7; // rax
  HCURSOR CursorW; // rax
  HCURSOR v9; // rax
  _QWORD *v10; // rbp
  __int64 v11; // rcx
  _QWORD *v12; // r15
  __int64 v13; // rcx
  BOOL IsUNCW; // ebp
  const WCHAR *ExtensionW; // rax
  const WCHAR *v16; // rcx
  _WORD *v17; // rax
  LPWSTR v18; // rax
  unsigned __int16 *v19; // rbp
  unsigned __int64 v20; // rdi
  const unsigned __int16 *v21; // rax
  unsigned int v22; // ebx
  int lpWideCharStr; // [rsp+20h] [rbp-98h]
  int v25; // [rsp+30h] [rbp-88h]
  int v26; // [rsp+40h] [rbp-78h]
  HCURSOR hCursor; // [rsp+C0h] [rbp+8h]

  v1 = (WCHAR *)((char *)a1 + 12);
  GetDlgItemTextW(*(HWND *)a1, 1003, (LPWSTR)a1 + 6, 260);
  PathRemoveBlanksW(v1);
  SHExpandEnvironmentStringsW(v1, (char *)a1 + 532, 260);
  v3 = (unsigned int *)((char *)a1 + 8);
  if ( StrCmpCW(v1, (LPCWSTR)a1 + 266) )
    *v3 |= 0x10000000u;
  v4 = (WCHAR *)((char *)a1 + ((*v3 & 0x10000000) != 0 ? 0x208 : 0) + 12);
  if ( !PathFileExistsW(v4) )
  {
    if ( !*v4 )
    {
LABEL_41:
      BrowseSetActive(a1);
      return 0;
    }
    ArgsW = PathGetArgsW(v1);
    StringCchCopyW((unsigned __int16 *)a1 + 526, 0x104u, ArgsW);
    if ( *v6 )
      *(v6 - 1) = 0;
    PathUnquoteSpacesW(v1);
    if ( (*v3 & 0x10000000) != 0 )
    {
      v7 = PathGetArgsW((LPCWSTR)a1 + 266);
      if ( *v7 )
        *(v7 - 1) = 0;
      PathUnquoteSpacesW((LPWSTR)a1 + 266);
    }
  }
  if ( !*v4 )
    goto LABEL_41;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v9 = SetCursor(CursorW);
  *v3 &= ~0x200u;
  v10 = (_QWORD *)((char *)a1 + 3304);
  v11 = *((_QWORD *)a1 + 413);
  hCursor = v9;
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *v10 = 0;
  }
  v12 = (_QWORD *)((char *)a1 + 3832);
  v13 = *((_QWORD *)a1 + 479);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *v12 = 0;
  }
  DetermineLinkHandler(
    *v3,
    (unsigned __int16 *)a1 + 266,
    lpWideCharStr,
    (LPWSTR)a1 + 786,
    v25,
    (__int64)a1 + 3312,
    v26,
    *((_QWORD *)a1 + 328),
    *(_QWORD *)a1,
    (struct INewShortcutHookW **)a1 + 413,
    (struct INewShortcutHookA **)a1 + 479);
  if ( *v10 || *v12 )
  {
    *v3 |= 2u;
    goto LABEL_43;
  }
  IsUNCW = PathIsUNCW(v4);
  if ( IsUNCW && !SHValidateUNC(*(HWND *)a1, v4, 0)
    || (!PathIsRootW(v4) || IsUNCW || !GetDriveTypeW(v4)) && !PathResolve(v4, 0, 3u) )
  {
    goto LABEL_40;
  }
  ExtensionW = PathFindExtensionW(v4);
  if ( !lstrcmpiW(ExtensionW, L".pif") )
  {
    if ( !(unsigned int)ReadPifProps(a1) )
      goto LABEL_40;
    MultiByteToWideChar(0, 0, (LPCCH)a1 + 2666, -1, v4, 260);
    PathRemoveArgsW(v4);
    if ( !PathResolve(v4, 0, 3u) )
      goto LABEL_40;
  }
  if ( (v16 = (const WCHAR *)*((_QWORD *)a1 + 412)) != 0 && !lstrcmpiW(v16, v4)
    || (DetermineExeType(a1), FindWorkingDir(a1), *((_WORD *)a1 + 786) = 0, (v17 = (_WORD *)*((_QWORD *)a1 + 328)) != 0)
    && *v17
    && !(unsigned int)DetermineDefaultTitle(a1) )
  {
LABEL_40:
    SetCursor(hCursor);
    ShellMessageBoxW(g_hinst, *(HWND *)a1, (LPCWSTR)0x7D3, (LPCWSTR)0x898, 0x30u, v1);
    goto LABEL_41;
  }
  if ( (*v3 & 0x10000000) == 0 )
    goto LABEL_43;
  v18 = PathFindExtensionW(v1);
  v19 = v18;
  if ( *v18 || !*v1 || *(v18 - 1) == 37 )
    goto LABEL_43;
  if ( v18 > v1 )
  {
    v20 = ((char *)v18 - (char *)a1 - 12) >> 1;
    if ( v20 < 0x104 )
    {
      v21 = PathFindExtensionW(v4);
      StringCchCopyW(v19, 260 - v20, v21);
LABEL_43:
      v22 = 1;
      goto LABEL_44;
    }
  }
  v22 = 0;
LABEL_44:
  SetCursor(hCursor);
  return v22;
}

```

## disassembly

```asm
0x18001c5cc  push    rbx
0x18001c5ce  push    rbp
0x18001c5cf  push    rsi
0x18001c5d0  push    rdi
0x18001c5d1  push    r12
0x18001c5d3  push    r13
0x18001c5d5  push    r14
0x18001c5d7  push    r15
0x18001c5d9  sub     rsp, 78h
0x18001c5dd  lea     r14, [rcx+0Ch]
0x18001c5e1  mov     rbx, rcx
0x18001c5e4  mov     rcx, [rcx]; hDlg
0x18001c5e7  mov     r12d, 104h
0x18001c5ed  mov     r9d, r12d; cchMax
0x18001c5f0  mov     r8, r14; lpString
0x18001c5f3  mov     edx, 3EBh; nIDDlgItem
0x18001c5f8  call    cs:__imp_GetDlgItemTextW
0x18001c5fe  mov     rcx, r14; pszPath
0x18001c601  call    cs:__imp_PathRemoveBlanksW
0x18001c607  lea     r13, [rbx+214h]
0x18001c60e  mov     r8d, r12d
0x18001c611  mov     rdx, r13
0x18001c614  mov     rcx, r14
0x18001c617  call    cs:__imp_SHExpandEnvironmentStringsW
0x18001c61d  mov     rdx, r13; pszStr2
0x18001c620  lea     rdi, [rbx+8]
0x18001c624  mov     rcx, r14; pszStr1
0x18001c627  call    cs:__imp_StrCmpCW
0x18001c62d  xor     r15d, r15d
0x18001c630  mov     ebp, 10000000h
0x18001c635  test    eax, eax
0x18001c637  jz      short loc_18001C63B
0x18001c639  or      [rdi], ebp
0x18001c63b  mov     eax, [rdi]
0x18001c63d  lea     rsi, [rbx+0Ch]
0x18001c641  and     eax, ebp
0x18001c643  neg     eax
0x18001c645  sbb     rcx, rcx
0x18001c648  and     ecx, 208h
0x18001c64e  add     rsi, rcx
0x18001c651  mov     rcx, rsi; pszPath
0x18001c654  call    cs:__imp_PathFileExistsW
0x18001c65a  test    eax, eax
0x18001c65c  jnz     short loc_18001C6BB
0x18001c65e  cmp     [rsi], r15w
0x18001c662  jz      loc_18001C946
0x18001c668  mov     rcx, r14; pszPath
0x18001c66b  call    cs:__imp_PathGetArgsW
0x18001c671  lea     rcx, [rbx+41Ch]; unsigned __int16 *
0x18001c678  mov     rdx, r12; unsigned __int64
0x18001c67b  mov     r8, rax; unsigned __int16 *
0x18001c67e  mov     r11, rax
0x18001c681  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c686  cmp     [r11], r15w
0x18001c68a  jz      short loc_18001C691
0x18001c68c  mov     [r11-2], r15w
0x18001c691  mov     rcx, r14; lpsz
0x18001c694  call    cs:__imp_PathUnquoteSpacesW
0x18001c69a  test    [rdi], ebp
0x18001c69c  jz      short loc_18001C6BB
0x18001c69e  mov     rcx, r13; pszPath
0x18001c6a1  call    cs:__imp_PathGetArgsW
0x18001c6a7  cmp     [rax], r15w
0x18001c6ab  jz      short loc_18001C6B2
0x18001c6ad  mov     [rax-2], r15w
0x18001c6b2  mov     rcx, r13; lpsz
0x18001c6b5  call    cs:__imp_PathUnquoteSpacesW
0x18001c6bb  cmp     [rsi], r15w
0x18001c6bf  jz      loc_18001C946
0x18001c6c5  mov     edx, 7F02h; lpCursorName
0x18001c6ca  xor     ecx, ecx; hInstance
0x18001c6cc  call    cs:__imp_LoadCursorW
0x18001c6d2  mov     rcx, rax; hCursor
0x18001c6d5  call    cs:__imp_SetCursor
0x18001c6db  btr     dword ptr [rdi], 9
0x18001c6df  lea     rbp, [rbx+0CE8h]
0x18001c6e6  mov     rcx, [rbp+0]
0x18001c6ea  mov     [rsp+0B8h+hCursor], rax
0x18001c6f2  test    rcx, rcx
0x18001c6f5  jz      short loc_18001C707
0x18001c6f7  mov     rdx, [rcx]
0x18001c6fa  mov     rax, [rdx+10h]
0x18001c6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c703  mov     [rbp+0], r15
0x18001c707  lea     r15, [rbx+0EF8h]
0x18001c70e  mov     rcx, [r15]
0x18001c711  test    rcx, rcx
0x18001c714  jz      short loc_18001C729
0x18001c716  mov     rax, [rcx]
0x18001c719  mov     rax, [rax+10h]
0x18001c71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c722  mov     qword ptr [r15], 0
0x18001c729  mov     rax, [rbx]
0x18001c72c  lea     rcx, [rbx+0CF0h]
0x18001c733  mov     [rsp+0B8h+var_58], r15; struct INewShortcutHookA **
0x18001c738  lea     rdx, [rbx+624h]
0x18001c73f  mov     [rsp+0B8h+var_60], rbp; struct INewShortcutHookW **
0x18001c744  mov     r9, r14
0x18001c747  mov     [rsp+0B8h+var_68], rax; __int64
0x18001c74c  mov     rax, [rbx+0A40h]
0x18001c753  mov     [rsp+0B8h+var_70], rax; __int64
0x18001c758  mov     [rsp+0B8h+var_80], rcx; __int64
0x18001c75d  mov     ecx, [rdi]; unsigned int
0x18001c75f  mov     qword ptr [rsp+0B8h+cchWideChar], rdx; LPWSTR
0x18001c764  mov     rdx, r13; unsigned __int16 *
0x18001c767  call    DetermineLinkHandler
0x18001c76c  xor     r13d, r13d
0x18001c76f  cmp     [rbp+0], r13
0x18001c773  jnz     loc_18001C961
0x18001c779  cmp     [r15], r13
0x18001c77c  jnz     loc_18001C961
0x18001c782  mov     rcx, rsi; pszPath
0x18001c785  call    cs:__imp_PathIsUNCW
0x18001c78b  mov     ebp, eax
0x18001c78d  test    eax, eax
0x18001c78f  jz      short loc_18001C7A8
0x18001c791  mov     rcx, [rbx]; hwndOwner
0x18001c794  xor     r8d, r8d; fConnect
0x18001c797  mov     rdx, rsi; pszFile
0x18001c79a  call    cs:__imp_SHValidateUNC
0x18001c7a0  test    eax, eax
0x18001c7a2  jz      loc_18001C90F
0x18001c7a8  mov     rcx, rsi; pszPath
0x18001c7ab  call    cs:__imp_PathIsRootW
0x18001c7b1  mov     r15d, 3
0x18001c7b7  test    eax, eax
0x18001c7b9  jz      short loc_18001C7CC
0x18001c7bb  test    ebp, ebp
0x18001c7bd  jnz     short loc_18001C7CC
0x18001c7bf  mov     rcx, rsi; lpRootPathName
0x18001c7c2  call    cs:__imp_GetDriveTypeW
0x18001c7c8  test    eax, eax
0x18001c7ca  jnz     short loc_18001C7E2
0x18001c7cc  mov     r8d, r15d; fFlags
0x18001c7cf  xor     edx, edx; dirs
0x18001c7d1  mov     rcx, rsi; pszPath
0x18001c7d4  call    cs:__imp_PathResolve
0x18001c7da  test    eax, eax
0x18001c7dc  jz      loc_18001C90F
0x18001c7e2  mov     rcx, rsi; pszPath
0x18001c7e5  call    cs:__imp_PathFindExtensionW
0x18001c7eb  mov     rcx, rax; lpString1
0x18001c7ee  lea     rdx, c_szPIF; ".pif"
0x18001c7f5  call    cs:__imp_lstrcmpiW
0x18001c7fb  test    eax, eax
0x18001c7fd  jnz     short loc_18001C84D
0x18001c7ff  mov     rcx, rbx; struct _WIZDATA *
0x18001c802  call    ?ReadPifProps@@YAHPEAU_WIZDATA@@@Z; ReadPifProps(_WIZDATA *)
0x18001c807  test    eax, eax
0x18001c809  jz      loc_18001C90F
0x18001c80f  lea     r8, [rbx+0A6Ah]; lpMultiByteStr
0x18001c816  mov     [rsp+0B8h+cchWideChar], r12d; cchWideChar
0x18001c81b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001c81f  mov     [rsp+0B8h+lpWideCharStr], rsi; lpWideCharStr
0x18001c824  xor     edx, edx; dwFlags
0x18001c826  xor     ecx, ecx; CodePage
0x18001c828  call    cs:__imp_MultiByteToWideChar
0x18001c82e  mov     rcx, rsi; pszPath
0x18001c831  call    cs:__imp_PathRemoveArgsW
0x18001c837  mov     r8d, r15d; fFlags
0x18001c83a  xor     edx, edx; dirs
0x18001c83c  mov     rcx, rsi; pszPath
0x18001c83f  call    cs:__imp_PathResolve
0x18001c845  test    eax, eax
0x18001c847  jz      loc_18001C90F
0x18001c84d  mov     rcx, [rbx+0CE0h]; lpString1
0x18001c854  test    rcx, rcx
0x18001c857  jz      short loc_18001C86A
0x18001c859  mov     rdx, rsi; lpString2
0x18001c85c  call    cs:__imp_lstrcmpiW
0x18001c862  test    eax, eax
0x18001c864  jz      loc_18001C90F
0x18001c86a  mov     rcx, rbx; struct _WIZDATA *
0x18001c86d  call    ?DetermineExeType@@YAXPEAU_WIZDATA@@@Z; DetermineExeType(_WIZDATA *)
0x18001c872  mov     rcx, rbx; struct _WIZDATA *
0x18001c875  call    ?FindWorkingDir@@YAXPEAU_WIZDATA@@@Z; FindWorkingDir(_WIZDATA *)
0x18001c87a  mov     [rbx+624h], r13w
0x18001c882  mov     rax, [rbx+0A40h]
0x18001c889  test    rax, rax
0x18001c88c  jz      short loc_18001C8A0
0x18001c88e  cmp     [rax], r13w
0x18001c892  jz      short loc_18001C8A0
0x18001c894  mov     rcx, rbx
0x18001c897  call    DetermineDefaultTitle
0x18001c89c  test    eax, eax
0x18001c89e  jz      short loc_18001C90F
0x18001c8a0  test    dword ptr [rdi], 10000000h
0x18001c8a6  jz      loc_18001C964
0x18001c8ac  mov     rcx, r14; pszPath
0x18001c8af  call    cs:__imp_PathFindExtensionW
0x18001c8b5  mov     rbp, rax
0x18001c8b8  cmp     [rax], r13w
0x18001c8bc  jnz     loc_18001C964
0x18001c8c2  cmp     [r14], r13w
0x18001c8c6  jz      loc_18001C964
0x18001c8cc  cmp     word ptr [rax-2], 25h ; '%'
0x18001c8d1  jz      loc_18001C964
0x18001c8d7  cmp     rax, r14
0x18001c8da  jbe     short loc_18001C90A
0x18001c8dc  mov     rdi, rax
0x18001c8df  sub     rdi, rbx
0x18001c8e2  sub     rdi, 0Ch
0x18001c8e6  sar     rdi, 1
0x18001c8e9  cmp     rdi, r12
0x18001c8ec  jnb     short loc_18001C90A
0x18001c8ee  mov     rcx, rsi; pszPath
0x18001c8f1  call    cs:__imp_PathFindExtensionW
0x18001c8f7  sub     r12, rdi
0x18001c8fa  mov     rcx, rbp; unsigned __int16 *
0x18001c8fd  mov     r8, rax; unsigned __int16 *
0x18001c900  mov     rdx, r12; unsigned __int64
0x18001c903  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c908  jmp     short loc_18001C964
0x18001c90a  mov     ebx, r13d
0x18001c90d  jmp     short loc_18001C969
0x18001c90f  mov     rcx, [rsp+0B8h+hCursor]; hCursor
0x18001c917  call    cs:__imp_SetCursor
0x18001c91d  mov     rdx, [rbx]; hWnd
0x18001c920  mov     r9d, 898h; lpcTitle
0x18001c926  mov     rcx, cs:g_hinst; hAppInst
0x18001c92d  mov     r8d, 7D3h; lpcText
0x18001c933  mov     qword ptr [rsp+0B8h+cchWideChar], r14
0x18001c938  mov     dword ptr [rsp+0B8h+lpWideCharStr], 30h ; '0'; fuStyle
0x18001c940  call    cs:__imp_ShellMessageBoxW
0x18001c946  mov     rcx, rbx; struct _WIZDATA *
0x18001c949  call    ?BrowseSetActive@@YAXPEAU_WIZDATA@@@Z; BrowseSetActive(_WIZDATA *)
0x18001c94e  xor     eax, eax
0x18001c950  add     rsp, 78h
0x18001c954  pop     r15
0x18001c956  pop     r14
0x18001c958  pop     r13
0x18001c95a  pop     r12
0x18001c95c  pop     rdi
0x18001c95d  pop     rsi
0x18001c95e  pop     rbp
0x18001c95f  pop     rbx
0x18001c960  retn
0x18001c961  or      dword ptr [rdi], 2
0x18001c964  mov     ebx, 1
0x18001c969  mov     rcx, [rsp+0B8h+hCursor]; hCursor
0x18001c971  call    cs:__imp_SetCursor
0x18001c977  mov     eax, ebx
0x18001c979  jmp     short loc_18001C950
```
