# GetTemporaryFilePath(ushort *)

- ea: `0x18001fb3c`
- end: `0x18001fc11`
- name: `?GetTemporaryFilePath@@YAJPEAG@Z`
- size: `213`
- prototype: `__int64 __fastcall(LPWSTR lpTempFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b95c`

## callees

- `0x180016020`
- `0x1800169b8`
- `0x18001fb3c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001fba4`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001fbd8`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001fba4`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001fbd8`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001fbbc`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001fbbc`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18001fb86`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18001fb86`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18001fb3c  mov     [rsp+arg_8], rbx
0x18001fb41  push    rdi
0x18001fb42  sub     rsp, 250h
0x18001fb49  mov     rax, cs:__security_cookie
0x18001fb50  xor     rax, rsp
0x18001fb53  mov     [rsp+258h+var_18], rax
0x18001fb5b  mov     rdi, rcx
0x18001fb5e  xor     edx, edx; Val
0x18001fb60  lea     rcx, [rsp+258h+PathName]; void *
0x18001fb65  mov     r8d, 208h; Size
0x18001fb6b  call    memset_0
0x18001fb70  xor     r9d, r9d; dwFlags
0x18001fb73  lea     rax, [rsp+258h+PathName]
0x18001fb78  xor     r8d, r8d; hToken
0x18001fb7b  mov     [rsp+258h+pszPath], rax; pszPath
0x18001fb80  xor     ecx, ecx; hwnd
0x18001fb82  lea     edx, [r9+20h]; csidl
0x18001fb86  call    cs:__imp_SHGetFolderPathW
0x18001fb8c  mov     ebx, eax
0x18001fb8e  test    eax, eax
0x18001fb90  js      short loc_18001FBB2
0x18001fb92  mov     r9, rdi; lpTempFileName
0x18001fb95  lea     rdx, PrefixString; "PMH"
0x18001fb9c  xor     r8d, r8d; uUnique
0x18001fb9f  lea     rcx, [rsp+258h+PathName]; lpPathName
0x18001fba4  call    cs:__imp_GetTempFileNameW
0x18001fbaa  test    eax, eax
0x18001fbac  jz      short loc_18001FBB2
0x18001fbae  mov     eax, ebx
0x18001fbb0  jmp     short loc_18001FBF0
0x18001fbb2  lea     rdx, [rsp+258h+PathName]
0x18001fbb7  mov     ecx, 104h
0x18001fbbc  call    cs:__imp_GetTempPath2W
0x18001fbc2  test    eax, eax
0x18001fbc4  jz      short loc_18001FBEB
0x18001fbc6  mov     r9, rdi; lpTempFileName
0x18001fbc9  lea     rdx, PrefixString; "PMH"
0x18001fbd0  xor     r8d, r8d; uUnique
0x18001fbd3  lea     rcx, [rsp+258h+PathName]; lpPathName
0x18001fbd8  call    cs:__imp_GetTempFileNameW
0x18001fbde  neg     eax
0x18001fbe0  sbb     eax, eax
0x18001fbe2  not     eax
0x18001fbe4  and     eax, 80004005h
0x18001fbe9  jmp     short loc_18001FBF0
0x18001fbeb  mov     eax, 80004005h
0x18001fbf0  mov     rcx, [rsp+258h+var_18]
0x18001fbf8  xor     rcx, rsp; StackCookie
0x18001fbfb  call    __security_check_cookie
0x18001fc00  mov     rbx, [rsp+258h+arg_8]
0x18001fc08  add     rsp, 250h
0x18001fc0f  pop     rdi
0x18001fc10  retn
```
