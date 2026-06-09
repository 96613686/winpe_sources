# RebootCheckOnInstallA

- ea: `0x180010810`
- end: `0x180010899`
- name: `RebootCheckOnInstallA`
- size: `137`
- prototype: `HRESULT __stdcall(HWND hwnd, LPCSTR pszINF, LPCSTR pszSec, DWORD dwReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180010810`
- `0x1800108a0`
- `0x1800173a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001087d`
- `KERNEL32!LocalFree` at `0x180010886`
- `KERNEL32!LocalFree` at `0x18001087d`
- `KERNEL32!LocalFree` at `0x180010886`

## pseudocode

```c
HRESULT __stdcall RebootCheckOnInstallA(HWND hwnd, LPCSTR pszINF, LPCSTR pszSec, DWORD dwReserved)
{
  HRESULT v7; // edi

  v7 = -2147467259;
  if ( (int)ThunkToUnicode(pszINF) >= 0 && (int)ThunkToUnicode(pszSec) >= 0 )
    v7 = RebootCheckOnInstallW(hwnd, 0, 0, dwReserved);
  LocalFree(0);
  LocalFree(0);
  return v7;
}

```

## disassembly

```asm
0x180010810  push    rbx; RebootCheckOnInstall
0x180010812  push    rbp
0x180010813  push    rsi
0x180010814  push    rdi
0x180010815  push    r14
0x180010817  sub     rsp, 30h
0x18001081b  mov     rax, rdx
0x18001081e  mov     [rsp+58h+pszINF], 0
0x180010827  mov     r14, rcx
0x18001082a  lea     rdx, [rsp+58h+pszINF]
0x18001082f  xor     ebx, ebx
0x180010831  mov     rcx, rax; lpMultiByteStr
0x180010834  mov     ebp, r9d
0x180010837  mov     [rsp+58h+pszSec], rbx
0x18001083c  mov     rsi, r8
0x18001083f  mov     edi, 80004005h
0x180010844  call    ThunkToUnicode
0x180010849  test    eax, eax
0x18001084b  js      short loc_180010878
0x18001084d  lea     rdx, [rsp+58h+pszSec]
0x180010852  mov     rcx, rsi; lpMultiByteStr
0x180010855  call    ThunkToUnicode
0x18001085a  mov     rbx, [rsp+58h+pszSec]
0x18001085f  test    eax, eax
0x180010861  js      short loc_180010878
0x180010863  mov     rdx, [rsp+58h+pszINF]; pszINF
0x180010868  mov     r9d, ebp; dwReserved
0x18001086b  mov     r8, rbx; pszSec
0x18001086e  mov     rcx, r14; hwnd
0x180010871  call    RebootCheckOnInstallW
0x180010876  mov     edi, eax
0x180010878  mov     rcx, [rsp+58h+pszINF]; hMem
0x18001087d  call    cs:__imp_LocalFree
0x180010883  mov     rcx, rbx; hMem
0x180010886  call    cs:__imp_LocalFree
0x18001088c  mov     eax, edi
0x18001088e  add     rsp, 30h
0x180010892  pop     r14
0x180010894  pop     rdi
0x180010895  pop     rsi
0x180010896  pop     rbp
0x180010897  pop     rbx
0x180010898  retn
```
