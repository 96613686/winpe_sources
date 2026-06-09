# RemoveSelItem(HWND__ *,HWND__ *)

- ea: `0x180055010`
- end: `0x180055197`
- name: `?RemoveSelItem@@YAXPEAUHWND__@@0@Z`
- size: `391`
- prototype: `void __fastcall(HWND hWnd, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180054140`

## callees

- `0x180002e98`
- `0x18000791c`
- `0x18005486c`
- `0x180055010`
- `0x1800582e0`

## import_xrefs

- `SHELL32!SHFileOperationW` at `0x180055115`
- `SHELL32!SHFileOperationW` at `0x180055115`
- `SHLWAPI!PathFindFileNameW` at `0x180055141`
- `SHLWAPI!PathFindFileNameW` at `0x180055141`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180055077`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180055167`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180055077`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180055167`
- `KERNEL32!lstrlenW` at `0x1800550eb`
- `KERNEL32!lstrlenW` at `0x1800550eb`
- `USER32!SendMessageW` at `0x180055135`
- `USER32!SendMessageW` at `0x180055135`

## pseudocode

```c
void __fastcall RemoveSelItem(HWND hWnd, HWND a2)
{
  struct _FILEITEMDATA *CurSel; // rax
  bool v5; // zf
  FILEOP_FLAGS v6; // cx
  unsigned __int64 v7; // rcx
  LPWSTR FileNameW; // rax
  LPARAM lParam; // [rsp+30h] [rbp-D0h] BYREF
  struct _SHFILEOPSTRUCTW FileOp; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR String[264]; // [rsp+70h] [rbp-90h] BYREF

  lParam = 0;
  CurSel = GetCurSel(a2, (struct _TREEITEM **)&lParam);
  if ( CurSel )
  {
    if ( (*(_BYTE *)CurSel & 2) != 0 )
    {
      v5 = (*(_BYTE *)CurSel & 4) == 0;
      v6 = 64;
      FileOp.hwnd = hWnd;
      *(_QWORD *)&FileOp.wFunc = 3;
      FileOp.pTo = 0;
      if ( v5 )
        v6 = 68;
      FileOp.fFlags = v6;
      memset(&FileOp.fFlags + 1, 0, 22);
      FileOp.pFrom = String;
      StringCchCopyW(String, 0x105u, (const unsigned __int16 *)CurSel + 2);
      v7 = 2LL * lstrlenW(String) + 2;
      if ( v7 >= 0x20A )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)String + v7) = 0;
      if ( !SHFileOperationW(&FileOp) && !FileOp.fAnyOperationsAborted )
        SendMessageW(a2, 0x1101u, 0, lParam);
    }
    else
    {
      FileNameW = PathFindFileNameW((LPCWSTR)CurSel + 2);
      ShellMessageBoxW(g_hinst, hWnd, (LPCWSTR)0x7F3, 0, 0x30u, FileNameW);
    }
  }
  else
  {
    ShellMessageBoxW(g_hinst, hWnd, (LPCWSTR)0x7F6, 0, 0x30u);
  }
}

```

## disassembly

```asm
0x180055010  mov     [rsp-8+arg_10], rbx
0x180055015  mov     [rsp-8+arg_18], rdi
0x18005501a  push    rbp
0x18005501b  lea     rbp, [rsp-190h]
0x180055023  sub     rsp, 290h
0x18005502a  mov     rax, cs:__security_cookie
0x180055031  xor     rax, rsp
0x180055034  mov     [rbp+190h+var_10], rax
0x18005503b  mov     rdi, rdx
0x18005503e  mov     [rsp+290h+lParam], 0
0x180055047  mov     rbx, rcx
0x18005504a  lea     rdx, [rsp+290h+lParam]; struct _TREEITEM **
0x18005504f  mov     rcx, rdi; hWnd
0x180055052  call    ?GetCurSel@@YAPEAU_FILEITEMDATA@@PEAUHWND__@@PEAPEAU_TREEITEM@@@Z; GetCurSel(HWND__ *,_TREEITEM * *)
0x180055057  test    rax, rax
0x18005505a  jnz     short loc_180055082
0x18005505c  mov     rcx, cs:g_hinst; hAppInst
0x180055063  xor     r9d, r9d; lpcTitle
0x180055066  mov     r8d, 7F6h; lpcText
0x18005506c  mov     [rsp+290h+fuStyle], 30h ; '0'; fuStyle
0x180055074  mov     rdx, rbx; hWnd
0x180055077  call    cs:__imp_ShellMessageBoxW
0x18005507d  jmp     loc_18005516D
0x180055082  test    byte ptr [rax], 2
0x180055085  jz      loc_18005513D
0x18005508b  test    byte ptr [rax], 4
0x18005508e  mov     ecx, 40h ; '@'
0x180055093  mov     [rsp+290h+FileOp.hwnd], rbx
0x180055098  mov     qword ptr [rsp+290h+FileOp.wFunc], 3
0x1800550a1  mov     [rsp+290h+FileOp.pTo], 0
0x1800550aa  jnz     short loc_1800550B1
0x1800550ac  mov     ecx, 44h ; 'D'
0x1800550b1  mov     [rsp+290h+FileOp.fFlags], cx
0x1800550b6  lea     r8, [rax+4]; unsigned __int16 *
0x1800550ba  xor     ecx, ecx
0x1800550bc  xorps   xmm0, xmm0
0x1800550bf  mov     word ptr [rsp+290h+FileOp+22h], cx
0x1800550c4  mov     edx, 105h; unsigned __int64
0x1800550c9  mov     dword ptr [rsp+290h+FileOp.lpszProgressTitle+4], ecx
0x1800550cd  lea     rcx, [rsp+290h+String]
0x1800550d2  mov     [rsp+290h+FileOp.pFrom], rcx
0x1800550d7  lea     rcx, [rsp+290h+String]; unsigned __int16 *
0x1800550dc  movups  xmmword ptr [rsp+290h+FileOp.fAnyOperationsAborted], xmm0
0x1800550e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800550e6  lea     rcx, [rsp+290h+String]; lpString
0x1800550eb  call    cs:__imp_lstrlenW
0x1800550f1  movsxd  rcx, eax
0x1800550f4  lea     rcx, ds:2[rcx*2]
0x1800550fc  cmp     rcx, 20Ah
0x180055103  jnb     loc_180055191
0x180055109  xor     eax, eax
0x18005510b  mov     [rsp+rcx+290h+String], ax
0x180055110  lea     rcx, [rsp+290h+FileOp]; lpFileOp
0x180055115  call    cs:__imp_SHFileOperationW
0x18005511b  test    eax, eax
0x18005511d  jnz     short loc_18005516D
0x18005511f  cmp     [rsp+290h+FileOp.fAnyOperationsAborted], eax
0x180055123  jnz     short loc_18005516D
0x180055125  mov     r9, [rsp+290h+lParam]; lParam
0x18005512a  xor     r8d, r8d; wParam
0x18005512d  mov     edx, 1101h; Msg
0x180055132  mov     rcx, rdi; hWnd
0x180055135  call    cs:__imp_SendMessageW
0x18005513b  jmp     short loc_18005516D
0x18005513d  lea     rcx, [rax+4]; pszPath
0x180055141  call    cs:__imp_PathFindFileNameW
0x180055147  mov     rcx, cs:g_hinst; hAppInst
0x18005514e  xor     r9d, r9d; lpcTitle
0x180055151  mov     [rsp+290h+var_268], rax
0x180055156  mov     r8d, 7F3h; lpcText
0x18005515c  mov     rdx, rbx; hWnd
0x18005515f  mov     [rsp+290h+fuStyle], 30h ; '0'; fuStyle
0x180055167  call    cs:__imp_ShellMessageBoxW
0x18005516d  mov     rcx, [rbp+190h+var_10]
0x180055174  xor     rcx, rsp; StackCookie
0x180055177  call    __security_check_cookie
0x18005517c  lea     r11, [rsp+290h+var_s0]
0x180055184  mov     rbx, [r11+20h]
0x180055188  mov     rdi, [r11+28h]
0x18005518c  mov     rsp, r11
0x18005518f  pop     rbp
0x180055190  retn
0x180055191  call    __report_rangecheckfailure
```
