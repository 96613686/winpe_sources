# GetShellStyleHInstance(ushort * *)

- ea: `0x1800448e8`
- end: `0x1800449d5`
- name: `?GetShellStyleHInstance@@YAPEAUHINSTANCE__@@PEAPEAG@Z`
- size: `237`
- prototype: `HINSTANCE __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180030aa8`

## callees

- `0x1800448e8`
- `0x180050ba0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004497b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800449b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004497b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800449b0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004499b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004499b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180044945`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180044958`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18004496a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180044945`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180044958`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18004496a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180044933`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180044933`
- `UxTheme!GetCurrentThemeName` at `0x180044924`
- `UxTheme!GetCurrentThemeName` at `0x180044924`

## string_xrefs

- `0x18004495e`: `ShellStyle.dll`
- `0x180044994`: `%SystemRoot%\System32\ShellStyle.dll`

## pseudocode

```c
HINSTANCE __fastcall GetShellStyleHInstance(unsigned __int16 **a1)
{
  HMODULE Library; // rbx
  WCHAR pszThemeFileName[264]; // [rsp+30h] [rbp-2F8h] BYREF
  WCHAR pszColorBuff[104]; // [rsp+240h] [rbp-E8h] BYREF

  Library = 0;
  if ( GetCurrentThemeName(pszThemeFileName, 260, pszColorBuff, 100, 0, 0) < 0
    || (PathRemoveFileSpecW(pszThemeFileName),
        PathAppendW(pszThemeFileName, L"Shell"),
        PathAppendW(pszThemeFileName, pszColorBuff),
        PathAppendW(pszThemeFileName, L"ShellStyle.dll"),
        (Library = LoadLibraryExW(pszThemeFileName, 0, 2u)) == 0) )
  {
    if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\ShellStyle.dll", pszThemeFileName, 0x104u) )
      return LoadLibraryExW(pszThemeFileName, 0, 2u);
  }
  return Library;
}

```

## disassembly

```asm
0x1800448e8  push    rbx
0x1800448ea  sub     rsp, 320h
0x1800448f1  mov     rax, cs:__security_cookie
0x1800448f8  xor     rax, rsp
0x1800448fb  mov     [rsp+328h+var_18], rax
0x180044903  xor     ebx, ebx
0x180044905  lea     r8, [rsp+328h+pszColorBuff]; pszColorBuff
0x18004490d  mov     [rsp+328h+cchMaxSizeChars], ebx; cchMaxSizeChars
0x180044911  lea     rcx, [rsp+328h+pszThemeFileName]; pszThemeFileName
0x180044916  mov     edx, 104h; cchMaxNameChars
0x18004491b  mov     [rsp+328h+pszSizeBuff], rbx; pszSizeBuff
0x180044920  lea     r9d, [rbx+64h]; cchMaxColorChars
0x180044924  call    cs:__imp_GetCurrentThemeName
0x18004492a  test    eax, eax
0x18004492c  js      short loc_180044989
0x18004492e  lea     rcx, [rsp+328h+pszThemeFileName]; pszPath
0x180044933  call    cs:__imp_PathRemoveFileSpecW
0x180044939  lea     rdx, aShell; "Shell"
0x180044940  lea     rcx, [rsp+328h+pszThemeFileName]; pszPath
0x180044945  call    cs:__imp_PathAppendW
0x18004494b  lea     rdx, [rsp+328h+pszColorBuff]; pszMore
0x180044953  lea     rcx, [rsp+328h+pszThemeFileName]; pszPath
0x180044958  call    cs:__imp_PathAppendW
0x18004495e  lea     rdx, aShellstyleDll; "ShellStyle.dll"
0x180044965  lea     rcx, [rsp+328h+pszThemeFileName]; pszPath
0x18004496a  call    cs:__imp_PathAppendW
0x180044970  xor     edx, edx; hFile
0x180044972  lea     r8d, [rbx+2]; dwFlags
0x180044976  lea     rcx, [rsp+328h+pszThemeFileName]; lpLibFileName
0x18004497b  call    cs:__imp_LoadLibraryExW
0x180044981  mov     rbx, rax
0x180044984  test    rax, rax
0x180044987  jnz     short loc_1800449B9
0x180044989  mov     r8d, 104h; nSize
0x18004498f  lea     rdx, [rsp+328h+pszThemeFileName]; lpDst
0x180044994  lea     rcx, aSystemrootSyst_2; "%SystemRoot%\\System32\\ShellStyle.dll"
0x18004499b  call    cs:__imp_ExpandEnvironmentStringsW
0x1800449a1  test    eax, eax
0x1800449a3  jz      short loc_1800449B9
0x1800449a5  xor     edx, edx; hFile
0x1800449a7  lea     rcx, [rsp+328h+pszThemeFileName]; lpLibFileName
0x1800449ac  lea     r8d, [rdx+2]; dwFlags
0x1800449b0  call    cs:__imp_LoadLibraryExW
0x1800449b6  mov     rbx, rax
0x1800449b9  mov     rax, rbx
0x1800449bc  mov     rcx, [rsp+328h+var_18]
0x1800449c4  xor     rcx, rsp; StackCookie
0x1800449c7  call    __security_check_cookie
0x1800449cc  add     rsp, 320h
0x1800449d3  pop     rbx
0x1800449d4  retn
```
