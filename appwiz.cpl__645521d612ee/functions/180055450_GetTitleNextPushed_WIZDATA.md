# GetTitleNextPushed(_WIZDATA *)

- ea: `0x180055450`
- end: `0x180055574`
- name: `?GetTitleNextPushed@@YAHPEAU_WIZDATA@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct _WIZDATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180055290`

## callees

- `0x18002ed10`
- `0x180055450`
- `0x1800582e0`

## import_xrefs

- `SHELL32!__imp_PathCleanupSpec` at `0x1800554aa`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800554aa`
- `SHLWAPI!PathFileExistsW` at `0x1800554ca`
- `SHLWAPI!PathFileExistsW` at `0x1800554ca`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180055517`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180055547`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180055517`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180055547`
- `KERNEL32!lstrcmpiW` at `0x1800554e5`
- `KERNEL32!lstrcmpiW` at `0x1800554e5`
- `USER32!GetDlgItemTextW` at `0x18005548f`
- `USER32!GetDlgItemTextW` at `0x18005548f`

## pseudocode

```c
_BOOL8 __fastcall GetTitleNextPushed(struct _WIZDATA *a1)
{
  WCHAR *v1; // rdi
  const WCHAR *v3; // rcx
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  v1 = (WCHAR *)((char *)a1 + 1572);
  GetDlgItemTextW(*(HWND *)a1, 1020, (LPWSTR)a1 + 786, 260);
  if ( !*v1 )
    return 0;
  if ( PathCleanupSpec(*((PCWSTR *)a1 + 328), v1) || !(unsigned int)GetLinkName(pszPath) )
  {
    ShellMessageBoxW(g_hinst, *(HWND *)a1, (LPCWSTR)0x80C, (LPCWSTR)0x898, 0x30u);
    return 0;
  }
  return !PathFileExistsW(pszPath)
      || (v3 = (const WCHAR *)*((_QWORD *)a1 + 412)) != 0 && !lstrcmpiW(v3, pszPath)
      || ShellMessageBoxW(g_hinst, *(HWND *)a1, (LPCWSTR)0x7DC, (LPCWSTR)0x7DD, 0x14u, v1) == 6;
}

```

## disassembly

```asm
0x180055450  mov     [rsp+arg_8], rbx
0x180055455  mov     [rsp+arg_10], rsi
0x18005545a  push    rdi
0x18005545b  sub     rsp, 250h
0x180055462  mov     rax, cs:__security_cookie
0x180055469  xor     rax, rsp
0x18005546c  mov     [rsp+258h+var_18], rax
0x180055474  lea     rdi, [rcx+624h]
0x18005547b  mov     rbx, rcx
0x18005547e  mov     rcx, [rcx]; hDlg
0x180055481  mov     r8, rdi; lpString
0x180055484  mov     r9d, 104h; cchMax
0x18005548a  mov     edx, 3FCh; nIDDlgItem
0x18005548f  call    cs:__imp_GetDlgItemTextW
0x180055495  xor     esi, esi
0x180055497  cmp     [rdi], si
0x18005549a  jz      loc_18005554D
0x1800554a0  mov     rcx, [rbx+0A40h]; pszDir
0x1800554a7  mov     rdx, rdi; pszSpec
0x1800554aa  call    cs:__imp_PathCleanupSpec
0x1800554b0  test    eax, eax
0x1800554b2  jnz     short loc_180055529
0x1800554b4  mov     r8, rbx
0x1800554b7  lea     rcx, [rsp+258h+pszPath]; unsigned __int16 *
0x1800554bc  call    GetLinkName
0x1800554c1  test    eax, eax
0x1800554c3  jz      short loc_180055529
0x1800554c5  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800554ca  call    cs:__imp_PathFileExistsW
0x1800554d0  test    eax, eax
0x1800554d2  jz      short loc_1800554EF
0x1800554d4  mov     rcx, [rbx+0CE0h]; lpString1
0x1800554db  test    rcx, rcx
0x1800554de  jz      short loc_1800554F6
0x1800554e0  lea     rdx, [rsp+258h+pszPath]; lpString2
0x1800554e5  call    cs:__imp_lstrcmpiW
0x1800554eb  test    eax, eax
0x1800554ed  jnz     short loc_1800554F6
0x1800554ef  mov     eax, 1
0x1800554f4  jmp     short loc_18005554F
0x1800554f6  mov     rdx, [rbx]; hWnd
0x1800554f9  mov     r9d, 7DDh; lpcTitle
0x1800554ff  mov     rcx, cs:g_hinst; hAppInst
0x180055506  mov     [rsp+258h+var_230], rdi
0x18005550b  mov     [rsp+258h+fuStyle], 14h; fuStyle
0x180055513  lea     r8d, [r9-1]; lpcText
0x180055517  call    cs:__imp_ShellMessageBoxW
0x18005551d  cmp     eax, 6
0x180055520  mov     ecx, esi
0x180055522  setz    cl
0x180055525  mov     eax, ecx
0x180055527  jmp     short loc_18005554F
0x180055529  mov     rdx, [rbx]; hWnd
0x18005552c  mov     r9d, 898h; lpcTitle
0x180055532  mov     rcx, cs:g_hinst; hAppInst
0x180055539  mov     r8d, 80Ch; lpcText
0x18005553f  mov     [rsp+258h+fuStyle], 30h ; '0'; fuStyle
0x180055547  call    cs:__imp_ShellMessageBoxW
0x18005554d  xor     eax, eax
0x18005554f  mov     rcx, [rsp+258h+var_18]
0x180055557  xor     rcx, rsp; StackCookie
0x18005555a  call    __security_check_cookie
0x18005555f  lea     r11, [rsp+258h+var_8]
0x180055567  mov     rbx, [r11+18h]
0x18005556b  mov     rsi, [r11+20h]
0x18005556f  mov     rsp, r11
0x180055572  pop     rdi
0x180055573  retn
```
