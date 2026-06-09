# AdvInstallFileA

- ea: `0x180002360`
- end: `0x180002443`
- name: `AdvInstallFileA`
- size: `227`
- prototype: `HRESULT __stdcall(HWND hwnd, LPCSTR lpszSourceDir, LPCSTR lpszSourceFile, LPCSTR lpszDestDir, LPCSTR lpszDestFile, DWORD dwFlags, DWORD dwReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180002360`
- `0x180002450`
- `0x1800173a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180002411`
- `KERNEL32!LocalFree` at `0x18000241b`
- `KERNEL32!LocalFree` at `0x180002425`
- `KERNEL32!LocalFree` at `0x18000242e`
- `KERNEL32!LocalFree` at `0x180002411`
- `KERNEL32!LocalFree` at `0x18000241b`
- `KERNEL32!LocalFree` at `0x180002425`
- `KERNEL32!LocalFree` at `0x18000242e`

## pseudocode

```c
HRESULT __stdcall AdvInstallFileA(
        HWND hwnd,
        LPCSTR lpszSourceDir,
        LPCSTR lpszSourceFile,
        LPCSTR lpszDestDir,
        LPCSTR lpszDestFile,
        DWORD dwFlags,
        DWORD dwReserved)
{
  HRESULT v10; // edi

  v10 = -2147467259;
  if ( (int)ThunkToUnicode(lpszSourceDir) >= 0
    && (int)ThunkToUnicode(lpszSourceFile) >= 0
    && (int)ThunkToUnicode(lpszDestDir) >= 0
    && (int)ThunkToUnicode(lpszDestFile) >= 0 )
  {
    v10 = AdvInstallFileW(hwnd, 0, 0, 0, 0, dwFlags, dwReserved);
  }
  LocalFree(0);
  LocalFree(0);
  LocalFree(0);
  LocalFree(0);
  return v10;
}

```

## disassembly

```asm
0x180002360  push    rbp; AdvInstallFile
0x180002362  push    rbx
0x180002363  push    rsi
0x180002364  push    rdi
0x180002365  push    r14
0x180002367  push    r15
0x180002369  mov     rbp, rsp
0x18000236c  sub     rsp, 68h
0x180002370  mov     rax, rdx
0x180002373  mov     [rbp+lpszSourceDir], 0
0x18000237b  mov     r15, rcx
0x18000237e  mov     [rbp+lpszSourceFile], 0
0x180002386  xor     ebx, ebx
0x180002388  mov     [rbp+lpszDestDir], 0
0x180002390  mov     rcx, rax; lpMultiByteStr
0x180002393  mov     [rbp+var_28], rbx
0x180002397  lea     rdx, [rbp+lpszSourceDir]
0x18000239b  mov     r14, r9
0x18000239e  mov     rsi, r8
0x1800023a1  mov     edi, 80004005h
0x1800023a6  call    ThunkToUnicode
0x1800023ab  test    eax, eax
0x1800023ad  js      short loc_18000240D
0x1800023af  lea     rdx, [rbp+lpszSourceFile]
0x1800023b3  mov     rcx, rsi; lpMultiByteStr
0x1800023b6  call    ThunkToUnicode
0x1800023bb  test    eax, eax
0x1800023bd  js      short loc_18000240D
0x1800023bf  lea     rdx, [rbp+lpszDestDir]
0x1800023c3  mov     rcx, r14; lpMultiByteStr
0x1800023c6  call    ThunkToUnicode
0x1800023cb  test    eax, eax
0x1800023cd  js      short loc_18000240D
0x1800023cf  mov     rcx, [rbp+lpszDestFile]; lpMultiByteStr
0x1800023d3  lea     rdx, [rbp+var_28]
0x1800023d7  call    ThunkToUnicode
0x1800023dc  mov     rbx, [rbp+var_28]
0x1800023e0  test    eax, eax
0x1800023e2  js      short loc_18000240D
0x1800023e4  mov     eax, [rbp+dwReserved]
0x1800023e7  mov     rcx, r15; hwnd
0x1800023ea  mov     r9, [rbp+lpszDestDir]; lpszDestDir
0x1800023ee  mov     r8, [rbp+lpszSourceFile]; lpszSourceFile
0x1800023f2  mov     rdx, [rbp+lpszSourceDir]; lpszSourceDir
0x1800023f6  mov     [rsp+68h+var_38], eax; dwReserved
0x1800023fa  mov     eax, [rbp+dwFlags]
0x1800023fd  mov     [rsp+68h+var_40], eax; dwFlags
0x180002401  mov     [rsp+68h+var_48], rbx; lpszDestFile
0x180002406  call    AdvInstallFileW
0x18000240b  mov     edi, eax
0x18000240d  mov     rcx, [rbp+lpszSourceDir]; hMem
0x180002411  call    cs:__imp_LocalFree
0x180002417  mov     rcx, [rbp+lpszSourceFile]; hMem
0x18000241b  call    cs:__imp_LocalFree
0x180002421  mov     rcx, [rbp+lpszDestDir]; hMem
0x180002425  call    cs:__imp_LocalFree
0x18000242b  mov     rcx, rbx; hMem
0x18000242e  call    cs:__imp_LocalFree
0x180002434  mov     eax, edi
0x180002436  add     rsp, 68h
0x18000243a  pop     r15
0x18000243c  pop     r14
0x18000243e  pop     rdi
0x18000243f  pop     rsi
0x180002440  pop     rbx
0x180002441  pop     rbp
0x180002442  retn
```
