# WindowsFeaturesServerExeExists(void)

- ea: `0x180018460`
- end: `0x1800184ce`
- name: `?WindowsFeaturesServerExeExists@@YAHXZ`
- size: `110`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013c90`
- `0x180042f90`

## callees

- `0x180018460`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x1800184ac`
- `SHLWAPI!PathFileExistsW` at `0x1800184ac`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001849d`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001849d`

## string_xrefs

- `0x180018496`: `%windir%\system32\ServerManager.exe`

## pseudocode

```c
BOOL WindowsFeaturesServerExeExists(void)
{
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(pszPath, 0, 0x208u);
  return (unsigned int)SHExpandEnvironmentStringsW(L"%windir%\\system32\\ServerManager.exe", pszPath, 260)
      && PathFileExistsW(pszPath);
}

```

## disassembly

```asm
0x180018460  sub     rsp, 248h
0x180018467  mov     rax, cs:__security_cookie
0x18001846e  xor     rax, rsp
0x180018471  mov     [rsp+248h+var_18], rax
0x180018479  xor     edx, edx; Val
0x18001847b  lea     rcx, [rsp+248h+pszPath]; void *
0x180018480  mov     r8d, 208h; Size
0x180018486  call    memset_0
0x18001848b  mov     r8d, 104h
0x180018491  lea     rdx, [rsp+248h+pszPath]
0x180018496  lea     rcx, aWindirSystem32; "%windir%\\system32\\ServerManager.exe"
0x18001849d  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800184a3  test    eax, eax
0x1800184a5  jz      short loc_1800184B4
0x1800184a7  lea     rcx, [rsp+248h+pszPath]; pszPath
0x1800184ac  call    cs:__imp_PathFileExistsW
0x1800184b2  jmp     short loc_1800184B6
0x1800184b4  xor     eax, eax
0x1800184b6  mov     rcx, [rsp+248h+var_18]
0x1800184be  xor     rcx, rsp; StackCookie
0x1800184c1  call    __security_check_cookie
0x1800184c6  add     rsp, 248h
0x1800184cd  retn
```
