# OpenINFEngineA

- ea: `0x180010670`
- end: `0x180010700`
- name: `OpenINFEngineA`
- size: `144`
- prototype: `HRESULT __stdcall(LPCSTR pszInfFilename, LPCSTR pszInstallSection, DWORD dwFlags, HINF *phInf, PVOID pvReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180010670`
- `0x180010710`
- `0x1800173a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800106e4`
- `KERNEL32!LocalFree` at `0x1800106ed`
- `KERNEL32!LocalFree` at `0x1800106e4`
- `KERNEL32!LocalFree` at `0x1800106ed`

## pseudocode

```c
HRESULT __stdcall OpenINFEngineA(
        LPCSTR pszInfFilename,
        LPCSTR pszInstallSection,
        DWORD dwFlags,
        HINF *phInf,
        PVOID pvReserved)
{
  HRESULT v8; // edi

  v8 = -2147467259;
  if ( (int)ThunkToUnicode(pszInfFilename) >= 0 && (int)ThunkToUnicode(pszInstallSection) >= 0 )
    v8 = OpenINFEngineW(0, 0, dwFlags, phInf, pvReserved);
  LocalFree(0);
  LocalFree(0);
  return v8;
}

```

## disassembly

```asm
0x180010670  push    rbx; OpenINFEngine
0x180010672  push    rbp
0x180010673  push    rsi
0x180010674  push    rdi
0x180010675  push    r14
0x180010677  sub     rsp, 40h
0x18001067b  mov     rsi, rdx
0x18001067e  mov     [rsp+68h+pszInfFilename], 0
0x180010687  xor     ebx, ebx
0x180010689  lea     rdx, [rsp+68h+pszInfFilename]
0x18001068e  mov     [rsp+68h+pszInstallSection], rbx
0x180010693  mov     rbp, r9
0x180010696  mov     r14d, r8d
0x180010699  mov     edi, 80004005h
0x18001069e  call    ThunkToUnicode
0x1800106a3  test    eax, eax
0x1800106a5  js      short loc_1800106DF
0x1800106a7  lea     rdx, [rsp+68h+pszInstallSection]
0x1800106ac  mov     rcx, rsi; lpMultiByteStr
0x1800106af  call    ThunkToUnicode
0x1800106b4  mov     rbx, [rsp+68h+pszInstallSection]
0x1800106b9  test    eax, eax
0x1800106bb  js      short loc_1800106DF
0x1800106bd  mov     rax, [rsp+68h+pvReserved]
0x1800106c5  mov     r9, rbp; phInf
0x1800106c8  mov     rcx, [rsp+68h+pszInfFilename]; pszInfFilename
0x1800106cd  mov     r8d, r14d; dwFlags
0x1800106d0  mov     rdx, rbx; pszInstallSection
0x1800106d3  mov     [rsp+68h+var_48], rax; pvReserved
0x1800106d8  call    OpenINFEngineW
0x1800106dd  mov     edi, eax
0x1800106df  mov     rcx, [rsp+68h+pszInfFilename]; hMem
0x1800106e4  call    cs:__imp_LocalFree
0x1800106ea  mov     rcx, rbx; hMem
0x1800106ed  call    cs:__imp_LocalFree
0x1800106f3  mov     eax, edi
0x1800106f5  add     rsp, 40h
0x1800106f9  pop     r14
0x1800106fb  pop     rdi
0x1800106fc  pop     rsi
0x1800106fd  pop     rbp
0x1800106fe  pop     rbx
0x1800106ff  retn
```
