# MyLoadLibrary(ushort const *)

- ea: `0x180008f2c`
- end: `0x180008ffc`
- name: `?MyLoadLibrary@@YAPEAUHINSTANCE__@@PEBG@Z`
- size: `208`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002450`
- `0x180007968`

## callees

- `0x180006c80`
- `0x180008f2c`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180008f89`
- `KERNEL32!GetFileAttributesW` at `0x180008f89`
- `KERNEL32!LoadLibraryExW` at `0x180008fa3`
- `KERNEL32!LoadLibraryExW` at `0x180008fb9`
- `KERNEL32!LoadLibraryExW` at `0x180008fcf`
- `KERNEL32!LoadLibraryExW` at `0x180008fa3`
- `KERNEL32!LoadLibraryExW` at `0x180008fb9`
- `KERNEL32!LoadLibraryExW` at `0x180008fcf`
- `KERNEL32!LoadLibraryW` at `0x180008fdd`
- `KERNEL32!LoadLibraryW` at `0x180008fdd`

## string_xrefs

- `0x180008f51`: `SETUPAPI.DLL`

## pseudocode

```c
HINSTANCE __fastcall MyLoadLibrary(const unsigned __int16 *a1)
{
  DWORD FileAttributesW; // eax
  HINSTANCE result; // rax
  ULONG v3; // [rsp+20h] [rbp-238h]
  WCHAR pszPathOut[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !(unsigned int)GetThisModulePath(pszPathOut)
    || (PathIsUnc2(L"SETUPAPI.DLL"),
        PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, L"SETUPAPI.DLL", v3),
        FileAttributesW = GetFileAttributesW(pszPathOut),
        FileAttributesW == -1)
    || (FileAttributesW & 0x10) != 0
    || (result = LoadLibraryExW(pszPathOut, 0, 8u)) == 0 )
  {
    result = LoadLibraryExW(L"SETUPAPI.DLL", 0, 0x800u);
    if ( !result )
    {
      result = LoadLibraryExW(L"SETUPAPI.DLL", 0, 0x1000u);
      if ( !result )
        return LoadLibraryW(L"SETUPAPI.DLL");
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008f2c  push    rbx
0x180008f2e  sub     rsp, 250h
0x180008f35  mov     rax, cs:__security_cookie
0x180008f3c  xor     rax, rsp
0x180008f3f  mov     [rsp+258h+var_18], rax
0x180008f47  lea     rcx, [rsp+258h+pszPathOut]; lpszStart
0x180008f4c  call    ?GetThisModulePath@@YAHPEAGH@Z; GetThisModulePath(ushort *,int)
0x180008f51  lea     rbx, FileName; "SETUPAPI.DLL"
0x180008f58  test    eax, eax
0x180008f5a  jz      short loc_180008FAE
0x180008f5c  lea     r8, IsBackslash
0x180008f63  xor     edx, edx
0x180008f65  mov     rcx, rbx; unsigned __int16 *
0x180008f68  call    PathIsUnc2
0x180008f6d  mov     r9, rbx; pszMore
0x180008f70  lea     r8, [rsp+258h+pszPathOut]; pszPathIn
0x180008f75  mov     edx, 104h; cchPathOut
0x180008f7a  lea     rcx, [rsp+258h+pszPathOut]; pszPathOut
0x180008f7f  call    PathCchCombineEx
0x180008f84  lea     rcx, [rsp+258h+pszPathOut]; lpFileName
0x180008f89  call    cs:__imp_GetFileAttributesW
0x180008f8f  cmp     eax, 0FFFFFFFFh
0x180008f92  jz      short loc_180008FAE
0x180008f94  test    al, 10h
0x180008f96  jnz     short loc_180008FAE
0x180008f98  xor     edx, edx; hFile
0x180008f9a  lea     rcx, [rsp+258h+pszPathOut]; lpLibFileName
0x180008f9f  lea     r8d, [rdx+8]; dwFlags
0x180008fa3  call    cs:__imp_LoadLibraryExW
0x180008fa9  test    rax, rax
0x180008fac  jnz     short loc_180008FE3
0x180008fae  xor     edx, edx; hFile
0x180008fb0  mov     r8d, 800h; dwFlags
0x180008fb6  mov     rcx, rbx; lpLibFileName
0x180008fb9  call    cs:__imp_LoadLibraryExW
0x180008fbf  test    rax, rax
0x180008fc2  jnz     short loc_180008FE3
0x180008fc4  xor     edx, edx; hFile
0x180008fc6  mov     r8d, 1000h; dwFlags
0x180008fcc  mov     rcx, rbx; lpLibFileName
0x180008fcf  call    cs:__imp_LoadLibraryExW
0x180008fd5  test    rax, rax
0x180008fd8  jnz     short loc_180008FE3
0x180008fda  mov     rcx, rbx; lpLibFileName
0x180008fdd  call    cs:__imp_LoadLibraryW
0x180008fe3  mov     rcx, [rsp+258h+var_18]
0x180008feb  xor     rcx, rsp; StackCookie
0x180008fee  call    __security_check_cookie
0x180008ff3  add     rsp, 250h
0x180008ffa  pop     rbx
0x180008ffb  retn
```
