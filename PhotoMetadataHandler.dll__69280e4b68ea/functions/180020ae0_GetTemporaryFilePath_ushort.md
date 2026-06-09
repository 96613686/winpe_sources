# GetTemporaryFilePath(ushort *)

- ea: `0x180020ae0`
- end: `0x180020bce`
- name: `?GetTemporaryFilePath@@YAJPEAG@Z`
- size: `238`
- prototype: `__int64 __fastcall(LPWSTR lpTempFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c63c`

## callees

- `0x180016a40`
- `0x180017408`
- `0x180020ae0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180020b4e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180020b8e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180020b4e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180020b8e`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180020b6c`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180020b6c`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180020b2a`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180020b2a`

## pseudocode

```c
__int64 __fastcall GetTemporaryFilePath(LPWSTR lpTempFileName)
{
  HRESULT v2; // ebx
  WCHAR PathName[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(PathName, 0, 0x208u);
  v2 = SHGetFolderPathW(0, 32, 0, 0, PathName);
  if ( v2 >= 0 && GetTempFileNameW(PathName, L"PMH", 0, lpTempFileName) )
    return (unsigned int)v2;
  if ( (unsigned int)GetTempPath2W(260, PathName) )
    return GetTempFileNameW(PathName, L"PMH", 0, lpTempFileName) == 0 ? 0x80004005 : 0;
  return 2147500037LL;
}

```

## disassembly

```asm
0x180020ae0  mov     [rsp+arg_8], rbx
0x180020ae5  push    rdi
0x180020ae6  sub     rsp, 250h
0x180020aed  mov     rax, cs:__security_cookie
0x180020af4  xor     rax, rsp
0x180020af7  mov     [rsp+258h+var_18], rax
0x180020aff  mov     rdi, rcx
0x180020b02  xor     edx, edx; Val
0x180020b04  lea     rcx, [rsp+258h+PathName]; void *
0x180020b09  mov     r8d, 208h; Size
0x180020b0f  call    memset_0
0x180020b14  xor     r9d, r9d; dwFlags
0x180020b17  lea     rax, [rsp+258h+PathName]
0x180020b1c  xor     r8d, r8d; hToken
0x180020b1f  mov     [rsp+258h+pszPath], rax; pszPath
0x180020b24  xor     ecx, ecx; hwnd
0x180020b26  lea     edx, [r9+20h]; csidl
0x180020b2a  call    cs:__imp_SHGetFolderPathW
0x180020b31  nop     dword ptr [rax+rax+00h]
0x180020b36  mov     ebx, eax
0x180020b38  test    eax, eax
0x180020b3a  js      short loc_180020B62
0x180020b3c  mov     r9, rdi; lpTempFileName
0x180020b3f  lea     rdx, PrefixString; "PMH"
0x180020b46  xor     r8d, r8d; uUnique
0x180020b49  lea     rcx, [rsp+258h+PathName]; lpPathName
0x180020b4e  call    cs:__imp_GetTempFileNameW
0x180020b55  nop     dword ptr [rax+rax+00h]
0x180020b5a  test    eax, eax
0x180020b5c  jz      short loc_180020B62
0x180020b5e  mov     eax, ebx
0x180020b60  jmp     short loc_180020BAC
0x180020b62  lea     rdx, [rsp+258h+PathName]
0x180020b67  mov     ecx, 104h
0x180020b6c  call    cs:__imp_GetTempPath2W
0x180020b73  nop     dword ptr [rax+rax+00h]
0x180020b78  test    eax, eax
0x180020b7a  jz      short loc_180020BA7
0x180020b7c  mov     r9, rdi; lpTempFileName
0x180020b7f  lea     rdx, PrefixString; "PMH"
0x180020b86  xor     r8d, r8d; uUnique
0x180020b89  lea     rcx, [rsp+258h+PathName]; lpPathName
0x180020b8e  call    cs:__imp_GetTempFileNameW
0x180020b95  nop     dword ptr [rax+rax+00h]
0x180020b9a  neg     eax
0x180020b9c  sbb     eax, eax
0x180020b9e  not     eax
0x180020ba0  and     eax, 80004005h
0x180020ba5  jmp     short loc_180020BAC
0x180020ba7  mov     eax, 80004005h
0x180020bac  mov     rcx, [rsp+258h+var_18]
0x180020bb4  xor     rcx, rsp; StackCookie
0x180020bb7  call    __security_check_cookie
0x180020bbc  mov     rbx, [rsp+258h+arg_8]
0x180020bc4  add     rsp, 250h
0x180020bcb  pop     rdi
0x180020bcc  retn
```
