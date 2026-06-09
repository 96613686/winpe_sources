# RunSetupCommandA

- ea: `0x18000bcb0`
- end: `0x18000bd9e`
- name: `RunSetupCommandA`
- size: `238`
- prototype: `HRESULT __stdcall(HWND hWnd, LPCSTR szCmdName, LPCSTR szInfSection, LPCSTR szDir, LPCSTR lpszTitle, HANDLE *phEXE, DWORD dwFlags, LPVOID pvReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000bcb0`
- `0x18000bdb0`
- `0x1800173a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000bd6c`
- `KERNEL32!LocalFree` at `0x18000bd76`
- `KERNEL32!LocalFree` at `0x18000bd80`
- `KERNEL32!LocalFree` at `0x18000bd89`
- `KERNEL32!LocalFree` at `0x18000bd6c`
- `KERNEL32!LocalFree` at `0x18000bd76`
- `KERNEL32!LocalFree` at `0x18000bd80`
- `KERNEL32!LocalFree` at `0x18000bd89`

## pseudocode

```c
HRESULT __stdcall RunSetupCommandA(
        HWND hWnd,
        LPCSTR szCmdName,
        LPCSTR szInfSection,
        LPCSTR szDir,
        LPCSTR lpszTitle,
        HANDLE *phEXE,
        DWORD dwFlags,
        LPVOID pvReserved)
{
  HRESULT v11; // edi

  v11 = -2147467259;
  if ( (int)ThunkToUnicode(szCmdName) >= 0
    && (int)ThunkToUnicode(szInfSection) >= 0
    && (int)ThunkToUnicode(szDir) >= 0
    && (int)ThunkToUnicode(lpszTitle) >= 0 )
  {
    v11 = RunSetupCommandW(hWnd, 0, 0, 0, 0, phEXE, dwFlags, pvReserved);
  }
  LocalFree(0);
  LocalFree(0);
  LocalFree(0);
  LocalFree(0);
  return v11;
}

```

## disassembly

```asm
0x18000bcb0  push    rbp; RunSetupCommand
0x18000bcb2  push    rbx
0x18000bcb3  push    rsi
0x18000bcb4  push    rdi
0x18000bcb5  push    r14
0x18000bcb7  push    r15
0x18000bcb9  mov     rbp, rsp
0x18000bcbc  sub     rsp, 68h
0x18000bcc0  mov     rax, rdx
0x18000bcc3  mov     [rbp+szCmdName], 0
0x18000bccb  mov     r15, rcx
0x18000bcce  mov     [rbp+szInfSection], 0
0x18000bcd6  xor     ebx, ebx
0x18000bcd8  mov     [rbp+szDir], 0
0x18000bce0  mov     rcx, rax; lpMultiByteStr
0x18000bce3  mov     [rbp+var_28], rbx
0x18000bce7  lea     rdx, [rbp+szCmdName]
0x18000bceb  mov     r14, r9
0x18000bcee  mov     rsi, r8
0x18000bcf1  mov     edi, 80004005h
0x18000bcf6  call    ThunkToUnicode
0x18000bcfb  test    eax, eax
0x18000bcfd  js      short loc_18000BD68
0x18000bcff  lea     rdx, [rbp+szInfSection]
0x18000bd03  mov     rcx, rsi; lpMultiByteStr
0x18000bd06  call    ThunkToUnicode
0x18000bd0b  test    eax, eax
0x18000bd0d  js      short loc_18000BD68
0x18000bd0f  lea     rdx, [rbp+szDir]
0x18000bd13  mov     rcx, r14; lpMultiByteStr
0x18000bd16  call    ThunkToUnicode
0x18000bd1b  test    eax, eax
0x18000bd1d  js      short loc_18000BD68
0x18000bd1f  mov     rcx, [rbp+lpszTitle]; lpMultiByteStr
0x18000bd23  lea     rdx, [rbp+var_28]
0x18000bd27  call    ThunkToUnicode
0x18000bd2c  mov     rbx, [rbp+var_28]
0x18000bd30  test    eax, eax
0x18000bd32  js      short loc_18000BD68
0x18000bd34  mov     rax, [rbp+pvReserved]
0x18000bd38  mov     rcx, r15; hWnd
0x18000bd3b  mov     r9, [rbp+szDir]; szDir
0x18000bd3f  mov     r8, [rbp+szInfSection]; szInfSection
0x18000bd43  mov     rdx, [rbp+szCmdName]; szCmdName
0x18000bd47  mov     [rsp+68h+var_30], rax; pvReserved
0x18000bd4c  mov     eax, [rbp+dwFlags]
0x18000bd4f  mov     [rsp+68h+var_38], eax; dwFlags
0x18000bd53  mov     rax, [rbp+phEXE]
0x18000bd57  mov     [rsp+68h+var_40], rax; phEXE
0x18000bd5c  mov     [rsp+68h+var_48], rbx; lpszTitle
0x18000bd61  call    RunSetupCommandW
0x18000bd66  mov     edi, eax
0x18000bd68  mov     rcx, [rbp+szCmdName]; hMem
0x18000bd6c  call    cs:__imp_LocalFree
0x18000bd72  mov     rcx, [rbp+szInfSection]; hMem
0x18000bd76  call    cs:__imp_LocalFree
0x18000bd7c  mov     rcx, [rbp+szDir]; hMem
0x18000bd80  call    cs:__imp_LocalFree
0x18000bd86  mov     rcx, rbx; hMem
0x18000bd89  call    cs:__imp_LocalFree
0x18000bd8f  mov     eax, edi
0x18000bd91  add     rsp, 68h
0x18000bd95  pop     r15
0x18000bd97  pop     r14
0x18000bd99  pop     rdi
0x18000bd9a  pop     rsi
0x18000bd9b  pop     rbx
0x18000bd9c  pop     rbp
0x18000bd9d  retn
```
