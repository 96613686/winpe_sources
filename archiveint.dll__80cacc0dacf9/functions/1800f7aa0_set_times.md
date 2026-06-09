# set_times

- ea: `0x1800f7aa0`
- end: `0x1800f7bfc`
- name: `set_times`
- size: `348`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800f49d0`
- `0x1800f7c04`

## callees

- `0x180006c00`
- `0x1800ee770`
- `0x1800ef3f8`
- `0x1800f7aa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7b4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7b4c`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800f7bb9`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800f7bb9`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800f7b40`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800f7b40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f7bc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f7bd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f7bc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f7bd4`

## pseudocode

```c
__int64 __fastcall set_times(
        __int64 a1,
        __int64 a2,
        __int16 a3,
        const WCHAR *a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        unsigned int a10,
        FILETIME LastWriteTime)
{
  void *v12; // rbx
  wchar_t *v14; // rdi
  void *v15; // r10
  FILETIME *p_CreationTime; // rdx
  FILETIME LastAccessTime; // [rsp+30h] [rbp-38h] BYREF
  __int128 v18; // [rsp+38h] [rbp-30h] BYREF
  __int128 v19; // [rsp+48h] [rbp-20h]
  FILETIME CreationTime; // [rsp+98h] [rbp+30h] BYREF

  LastAccessTime = 0;
  CreationTime = 0;
  LastWriteTime = 0;
  if ( a2 != -1 )
  {
    v12 = 0;
LABEL_7:
    LastAccessTime = (FILETIME)unix_to_ntfs(a5, a6);
    LastWriteTime = (FILETIME)unix_to_ntfs(a9, a10);
    if ( a7 > 0 || a8 > 0 )
    {
      CreationTime = (FILETIME)unix_to_ntfs(a7, (unsigned int)a8);
      p_CreationTime = &CreationTime;
    }
    else
    {
      p_CreationTime = 0;
    }
    if ( SetFileTime(v15, p_CreationTime, &LastAccessTime, &LastWriteTime) )
    {
      CloseHandle(v12);
      return 0;
    }
    goto LABEL_13;
  }
  v18 = 0;
  v19 = 0;
  if ( (a3 & 0xF000) == 0xA000 )
    return 0;
  v12 = 0;
  v14 = _la_win_permissive_name_w(a4);
  if ( v14 )
  {
    v18 = 0;
    LODWORD(v18) = 32;
    DWORD2(v18) = 0x2000000;
    v19 = 0;
    v12 = (void *)CreateFile2(v14, 256, 0, 3, &v18);
    free(v14);
    if ( v12 != (void *)-1LL )
      goto LABEL_7;
  }
LABEL_13:
  CloseHandle(v12);
  archive_set_error(a1, 22, "Can't restore time");
  return 4294967276LL;
}

```

## disassembly

```asm
0x1800f7aa0  push    rbp
0x1800f7aa2  push    rbx
0x1800f7aa3  push    rsi
0x1800f7aa4  push    rdi
0x1800f7aa5  mov     rbp, rsp
0x1800f7aa8  sub     rsp, 68h
0x1800f7aac  mov     qword ptr [rbp+LastAccessTime.dwLowDateTime], 0
0x1800f7ab4  mov     r10, rdx
0x1800f7ab7  mov     qword ptr [rbp+CreationTime.dwLowDateTime], 0
0x1800f7abf  mov     rsi, rcx
0x1800f7ac2  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], 0
0x1800f7aca  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800f7ace  jz      short loc_1800F7AD7
0x1800f7ad0  xor     ebx, ebx
0x1800f7ad2  jmp     loc_1800F7B5B
0x1800f7ad7  xorps   xmm0, xmm0
0x1800f7ada  and     r8d, 0F000h
0x1800f7ae1  movups  [rbp+var_30], xmm0
0x1800f7ae5  movups  [rbp+var_20], xmm0
0x1800f7ae9  cmp     r8d, 0A000h
0x1800f7af0  jnz     short loc_1800F7AF9
0x1800f7af2  xor     eax, eax
0x1800f7af4  jmp     loc_1800F7BF3
0x1800f7af9  mov     rcx, r9; lpFileName
0x1800f7afc  xor     ebx, ebx
0x1800f7afe  call    __la_win_permissive_name_w
0x1800f7b03  mov     rdi, rax
0x1800f7b06  test    rax, rax
0x1800f7b09  jz      loc_1800F7BD1
0x1800f7b0f  xorps   xmm0, xmm0
0x1800f7b12  lea     rax, [rbp+var_30]
0x1800f7b16  movups  [rbp+var_30], xmm0
0x1800f7b1a  lea     r9d, [rbx+3]
0x1800f7b1e  mov     dword ptr [rbp+var_30], 20h ; ' '
0x1800f7b25  xor     r8d, r8d
0x1800f7b28  mov     dword ptr [rbp+var_30+8], 2000000h
0x1800f7b2f  mov     edx, 100h
0x1800f7b34  mov     [rsp+68h+var_48], rax
0x1800f7b39  mov     rcx, rdi
0x1800f7b3c  movups  [rbp+var_20], xmm0
0x1800f7b40  call    cs:__imp_CreateFile2
0x1800f7b46  mov     rcx, rdi; Block
0x1800f7b49  mov     rbx, rax
0x1800f7b4c  call    cs:__imp_free
0x1800f7b52  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800f7b56  jz      short loc_1800F7BD1
0x1800f7b58  mov     r10, rbx
0x1800f7b5b  mov     edx, [rbp+arg_28]
0x1800f7b5e  mov     rcx, [rbp+arg_20]
0x1800f7b62  call    unix_to_ntfs
0x1800f7b67  mov     edx, [rbp+arg_48]
0x1800f7b6a  mov     rcx, [rbp+arg_40]
0x1800f7b6e  mov     [rbp+LastAccessTime.dwLowDateTime], eax
0x1800f7b71  shr     rax, 20h
0x1800f7b75  mov     [rbp+LastAccessTime.dwHighDateTime], eax
0x1800f7b78  call    unix_to_ntfs
0x1800f7b7d  mov     rcx, [rbp+arg_30]
0x1800f7b81  mov     edx, [rbp+arg_38]
0x1800f7b84  mov     [rbp+LastWriteTime.dwLowDateTime], eax
0x1800f7b87  shr     rax, 20h
0x1800f7b8b  mov     [rbp+LastWriteTime.dwHighDateTime], eax
0x1800f7b8e  test    rcx, rcx
0x1800f7b91  jg      short loc_1800F7B9B
0x1800f7b93  test    edx, edx
0x1800f7b95  jg      short loc_1800F7B9B
0x1800f7b97  xor     edx, edx
0x1800f7b99  jmp     short loc_1800F7BAE
0x1800f7b9b  call    unix_to_ntfs
0x1800f7ba0  mov     [rbp+CreationTime.dwLowDateTime], eax
0x1800f7ba3  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x1800f7ba7  shr     rax, 20h
0x1800f7bab  mov     [rbp+CreationTime.dwHighDateTime], eax
0x1800f7bae  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x1800f7bb2  mov     rcx, r10; hFile
0x1800f7bb5  lea     r8, [rbp+LastAccessTime]; lpLastAccessTime
0x1800f7bb9  call    cs:__imp_SetFileTime
0x1800f7bbf  test    eax, eax
0x1800f7bc1  jz      short loc_1800F7BD1
0x1800f7bc3  mov     rcx, rbx; hObject
0x1800f7bc6  call    cs:__imp_CloseHandle
0x1800f7bcc  jmp     loc_1800F7AF2
0x1800f7bd1  mov     rcx, rbx; hObject
0x1800f7bd4  call    cs:__imp_CloseHandle
0x1800f7bda  lea     r8, aCanTRestoreTim; "Can't restore time"
0x1800f7be1  mov     edx, 16h
0x1800f7be6  mov     rcx, rsi
0x1800f7be9  call    archive_set_error
0x1800f7bee  mov     eax, 0FFFFFFECh
0x1800f7bf3  add     rsp, 68h
0x1800f7bf7  pop     rdi
0x1800f7bf8  pop     rsi
0x1800f7bf9  pop     rbx
0x1800f7bfa  pop     rbp
0x1800f7bfb  retn
```
