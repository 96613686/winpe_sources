# MakePrgIcon0Index(HWND__ *,_IMAGELIST *)

- ea: `0x180054ba4`
- end: `0x180054c6c`
- name: `?MakePrgIcon0Index@@YAHPEAUHWND__@@PEAU_IMAGELIST@@@Z`
- size: `200`
- prototype: `int(HWND, struct _IMAGELIST *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800548f0`

## callees

- `0x180054ba4`
- `0x1800565e8`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `SHELL32!SHGetSpecialFolderLocation` at `0x180054bd9`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180054bd9`
- `SHELL32!SHGetFileInfoW` at `0x180054c0e`
- `SHELL32!SHGetFileInfoW` at `0x180054c0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054c1c`
- `USER32!DestroyIcon` at `0x180054c3c`
- `USER32!DestroyIcon` at `0x180054c3c`

## pseudocode

```c
__int64 __fastcall MakePrgIcon0Index(HWND a1, struct _IMAGELIST *a2)
{
  DWORD_PTR v3; // rbx
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-2E8h] BYREF
  SHFILEINFOW psfi; // [rsp+40h] [rbp-2D8h] BYREF

  ppidl = 0;
  if ( SHGetSpecialFolderLocation(a1, 2, &ppidl) < 0 )
    return 0;
  memset_0(&psfi, 0, sizeof(psfi));
  v3 = SHGetFileInfoW(&ppidl->mkid.cb, 0, &psfi, 0x2B8u, 0x109u);
  CoTaskMemFree(ppidl);
  if ( !v3 )
    return 0;
  ImageList_ReplaceIcon(a2, -1, psfi.hIcon);
  DestroyIcon(psfi.hIcon);
  return 1;
}

```

## disassembly

```asm
0x180054ba4  mov     [rsp+arg_10], rbx
0x180054ba9  push    rdi
0x180054baa  sub     rsp, 310h
0x180054bb1  mov     rax, cs:__security_cookie
0x180054bb8  xor     rax, rsp
0x180054bbb  mov     [rsp+318h+var_18], rax
0x180054bc3  mov     rdi, rdx
0x180054bc6  mov     [rsp+318h+ppidl], 0
0x180054bcf  mov     edx, 2; csidl
0x180054bd4  lea     r8, [rsp+318h+ppidl]; ppidl
0x180054bd9  call    cs:__imp_SHGetSpecialFolderLocation
0x180054bdf  test    eax, eax
0x180054be1  js      short loc_180054C49
0x180054be3  mov     ebx, 2B8h
0x180054be8  lea     rcx, [rsp+318h+psfi]; void *
0x180054bed  mov     r8d, ebx; Size
0x180054bf0  xor     edx, edx; Val
0x180054bf2  call    memset_0
0x180054bf7  mov     rcx, [rsp+318h+ppidl]; pszPath
0x180054bfc  lea     r8, [rsp+318h+psfi]; psfi
0x180054c01  mov     r9d, ebx; cbFileInfo
0x180054c04  mov     [rsp+318h+uFlags], 109h; uFlags
0x180054c0c  xor     edx, edx; dwFileAttributes
0x180054c0e  call    cs:__imp_SHGetFileInfoW
0x180054c14  mov     rcx, [rsp+318h+ppidl]; pv
0x180054c19  mov     rbx, rax
0x180054c1c  call    cs:__imp_CoTaskMemFree
0x180054c22  test    rbx, rbx
0x180054c25  jz      short loc_180054C49
0x180054c27  mov     r8, [rsp+318h+psfi.hIcon]; hicon
0x180054c2c  or      edx, 0FFFFFFFFh; i
0x180054c2f  mov     rcx, rdi; himl
0x180054c32  call    ImageList_ReplaceIcon
0x180054c37  mov     rcx, [rsp+318h+psfi.hIcon]; hIcon
0x180054c3c  call    cs:__imp_DestroyIcon
0x180054c42  mov     eax, 1
0x180054c47  jmp     short loc_180054C4B
0x180054c49  xor     eax, eax
0x180054c4b  mov     rcx, [rsp+318h+var_18]
0x180054c53  xor     rcx, rsp; StackCookie
0x180054c56  call    __security_check_cookie
0x180054c5b  mov     rbx, [rsp+318h+arg_10]
0x180054c63  add     rsp, 310h
0x180054c6a  pop     rdi
0x180054c6b  retn
```
