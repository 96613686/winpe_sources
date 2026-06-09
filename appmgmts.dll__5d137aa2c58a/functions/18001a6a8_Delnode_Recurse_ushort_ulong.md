# Delnode_Recurse(ushort *,ulong)

- ea: `0x18001a6a8`
- end: `0x18001a95a`
- name: `?Delnode_Recurse@@YAHPEAGK@Z`
- size: `690`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001a140`
- `0x18001a6a8`

## callees

- `0x180002aa0`
- `0x180013368`
- `0x18001a558`
- `0x18001a6a8`
- `0x18001ab78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a88f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a88f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a933`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a941`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a933`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a941`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a700`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a761`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a700`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a761`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001a779`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001a7f3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001a779`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001a7f3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a8d3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a903`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a8d3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a903`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001a90f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001a90f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001a87c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001a8ca`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001a87c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001a8ca`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001a920`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001a920`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001a885`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001a8b5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001a885`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001a8b5`
- `KERNEL32!lstrcmpiW` at `0x18001a814`
- `KERNEL32!lstrcmpiW` at `0x18001a82c`
- `KERNEL32!lstrcmpiW` at `0x18001a814`
- `KERNEL32!lstrcmpiW` at `0x18001a82c`

## pseudocode

```c
__int64 __fastcall Delnode_Recurse(unsigned __int16 *a1, unsigned int a2)
{
  __int64 v2; // rbp
  unsigned int v4; // esi
  __int64 v5; // rax
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbx
  int v8; // r12d
  unsigned __int16 *v9; // rax
  unsigned __int64 v10; // r13
  unsigned __int16 *v11; // r15
  struct _WIN32_FIND_DATAW *v12; // rax
  struct _WIN32_FIND_DATAW *v13; // rdi
  HANDLE FirstFileW; // r14
  DWORD v15; // edx
  unsigned int v17; // [rsp+78h] [rbp+10h] BYREF

  LODWORD(v2) = a2;
  v17 = 0;
  v4 = 0;
  if ( a1 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a1[v5] );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  if ( (int)v5 + 262 <= a2 )
  {
    v8 = 0;
    v7 = a1;
  }
  else
  {
    v2 = a2 + 520;
    v6 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v2);
    v7 = v6;
    if ( !v6 )
      return v4;
    StringCchCopyW(v6, (unsigned int)v2, a1);
    v8 = 1;
  }
  v9 = CheckSlashEx(v7, v2, &v17);
  v10 = v17;
  v11 = v9;
  StringCchCopyW(v9, v17, L"*.*");
  v12 = (struct _WIN32_FIND_DATAW *)LocalAlloc(0x40u, 0x250u);
  v13 = v12;
  if ( v12 )
  {
    FirstFileW = FindFirstFileW(v7, v12);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      if ( GetLastError() == 2 || GetLastError() == 3 )
      {
LABEL_38:
        v4 = 1;
        goto LABEL_39;
      }
      if ( GetLastError() != 5 )
        goto LABEL_39;
      *v11 = 0;
      if ( (int)TakeOwnership(v7) < 0 )
        goto LABEL_39;
      if ( (int)AddAdminAccess(v7) < 0 )
        goto LABEL_39;
      StringCchCopyW(v11, (unsigned int)v10, L"*.*");
      FirstFileW = FindFirstFileW(v7, v13);
      if ( FirstFileW == (HANDLE)-1LL )
        goto LABEL_39;
    }
    do
    {
      if ( lstrcmpiW(v13->cFileName, L".") && lstrcmpiW(v13->cFileName, L"..") )
      {
        StringCchCopyW(v11, v10, v13->cFileName);
        if ( (v13->dwFileAttributes & 0x10) != 0 )
        {
          if ( (v13->dwFileAttributes & 0x400) == 0 )
          {
            Delnode_Recurse(v7, v2);
            StringCchCopyW(v11, v10, v13->cFileName);
          }
          if ( (v13->dwFileAttributes & 1) != 0 )
          {
            v15 = v13->dwFileAttributes & 0xFFFFFFFE;
            v13->dwFileAttributes = v15;
            SetFileAttributesW(v7, v15);
          }
          if ( !RemoveDirectoryW(v7)
            && GetLastError() == 5
            && (int)TakeOwnership(v7) >= 0
            && (int)AddAdminAccess(v7) >= 0 )
          {
            RemoveDirectoryW(v7);
          }
        }
        else
        {
          if ( (v13->dwFileAttributes & 5) != 0 )
            SetFileAttributesW(v7, 0x80u);
          if ( !DeleteFileW(v7) && GetLastError() == 5 && (int)TakeOwnership(v7) >= 0 && (int)AddAdminAccess(v7) >= 0 )
            DeleteFileW(v7);
        }
      }
    }
    while ( FindNextFileW(FirstFileW, v13) );
    FindClose(FirstFileW);
    goto LABEL_38;
  }
LABEL_39:
  if ( v8 )
    LocalFree(v7);
  if ( v13 )
    LocalFree(v13);
  return v4;
}

```

## disassembly

```asm
0x18001a6a8  push    rbx
0x18001a6aa  push    rbp
0x18001a6ab  push    rsi
0x18001a6ac  push    rdi
0x18001a6ad  push    r12
0x18001a6af  push    r13
0x18001a6b1  push    r14
0x18001a6b3  push    r15
0x18001a6b5  sub     rsp, 28h
0x18001a6b9  xor     r15d, r15d
0x18001a6bc  mov     ebp, edx
0x18001a6be  mov     [rsp+68h+arg_8], r15d
0x18001a6c3  mov     rdi, rcx
0x18001a6c6  mov     esi, r15d
0x18001a6c9  test    rcx, rcx
0x18001a6cc  jnz     short loc_18001A6D3
0x18001a6ce  mov     eax, r15d
0x18001a6d1  jmp     short loc_18001A6E1
0x18001a6d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a6d7  inc     rax
0x18001a6da  cmp     [rcx+rax*2], r15w
0x18001a6df  jnz     short loc_18001A6D7
0x18001a6e1  add     eax, 106h
0x18001a6e6  cmp     eax, ebp
0x18001a6e8  jbe     short loc_18001A728
0x18001a6ea  add     ebp, 208h
0x18001a6f0  mov     ecx, 40h ; '@'; uFlags
0x18001a6f5  mov     r14d, ebp
0x18001a6f8  lea     rdx, ds:0[rbp*2]; uBytes
0x18001a700  call    cs:__imp_LocalAlloc
0x18001a706  mov     rbx, rax
0x18001a709  test    rax, rax
0x18001a70c  jz      loc_18001A947
0x18001a712  mov     r8, rdi; unsigned __int16 *
0x18001a715  mov     edx, r14d; unsigned __int64
0x18001a718  mov     rcx, rax; unsigned __int16 *
0x18001a71b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a720  mov     r12d, 1
0x18001a726  jmp     short loc_18001A72E
0x18001a728  mov     r12d, r15d
0x18001a72b  mov     rbx, rdi
0x18001a72e  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18001a733  mov     edx, ebp; unsigned int
0x18001a735  mov     rcx, rbx; unsigned __int16 *
0x18001a738  call    ?CheckSlashEx@@YAPEAGPEAGIPEAI@Z; CheckSlashEx(ushort *,uint,uint *)
0x18001a73d  mov     r13d, [rsp+68h+arg_8]
0x18001a742  lea     r8, asc_180030950; "*.*"
0x18001a749  mov     edx, r13d; unsigned __int64
0x18001a74c  mov     rcx, rax; unsigned __int16 *
0x18001a74f  mov     r15, rax
0x18001a752  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a757  mov     edx, 250h; uBytes
0x18001a75c  mov     ecx, 40h ; '@'; uFlags
0x18001a761  call    cs:__imp_LocalAlloc
0x18001a767  mov     rdi, rax
0x18001a76a  test    rax, rax
0x18001a76d  jz      loc_18001A92B
0x18001a773  mov     rdx, rax; lpFindFileData
0x18001a776  mov     rcx, rbx; lpFileName
0x18001a779  call    cs:__imp_FindFirstFileW
0x18001a77f  mov     r14, rax
0x18001a782  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a786  jnz     short loc_18001A806
0x18001a788  call    cs:__imp_GetLastError
0x18001a78e  cmp     eax, 2
0x18001a791  jz      loc_18001A926
0x18001a797  call    cs:__imp_GetLastError
0x18001a79d  cmp     eax, 3
0x18001a7a0  jz      loc_18001A926
0x18001a7a6  call    cs:__imp_GetLastError
0x18001a7ac  cmp     eax, 5
0x18001a7af  jnz     loc_18001A92B
0x18001a7b5  xor     eax, eax
0x18001a7b7  mov     rcx, rbx; pObjectName
0x18001a7ba  mov     [r15], ax
0x18001a7be  call    ?TakeOwnership@@YAJPEBG@Z; TakeOwnership(ushort const *)
0x18001a7c3  test    eax, eax
0x18001a7c5  js      loc_18001A92B
0x18001a7cb  mov     rcx, rbx; pObjectName
0x18001a7ce  call    ?AddAdminAccess@@YAJPEBG@Z; AddAdminAccess(ushort const *)
0x18001a7d3  test    eax, eax
0x18001a7d5  js      loc_18001A92B
0x18001a7db  lea     r8, asc_180030950; "*.*"
0x18001a7e2  mov     edx, r13d; unsigned __int64
0x18001a7e5  mov     rcx, r15; unsigned __int16 *
0x18001a7e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a7ed  mov     rdx, rdi; lpFindFileData
0x18001a7f0  mov     rcx, rbx; lpFileName
0x18001a7f3  call    cs:__imp_FindFirstFileW
0x18001a7f9  mov     r14, rax
0x18001a7fc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a800  jz      loc_18001A92B
0x18001a806  lea     rsi, [rdi+2Ch]
0x18001a80a  lea     rdx, asc_180030948; "."
0x18001a811  mov     rcx, rsi; lpString1
0x18001a814  call    cs:__imp_lstrcmpiW
0x18001a81a  test    eax, eax
0x18001a81c  jz      loc_18001A909
0x18001a822  lea     rdx, asc_180030940; ".."
0x18001a829  mov     rcx, rsi; lpString1
0x18001a82c  call    cs:__imp_lstrcmpiW
0x18001a832  test    eax, eax
0x18001a834  jz      loc_18001A909
0x18001a83a  mov     r8, rsi; unsigned __int16 *
0x18001a83d  mov     rdx, r13; unsigned __int64
0x18001a840  mov     rcx, r15; unsigned __int16 *
0x18001a843  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a848  test    byte ptr [rdi], 10h
0x18001a84b  jz      short loc_18001A8BD
0x18001a84d  test    dword ptr [rdi], 400h
0x18001a853  jnz     short loc_18001A86D
0x18001a855  mov     edx, ebp; unsigned int
0x18001a857  mov     rcx, rbx; unsigned __int16 *
0x18001a85a  call    ?Delnode_Recurse@@YAHPEAGK@Z; Delnode_Recurse(ushort *,ulong)
0x18001a85f  mov     r8, rsi; unsigned __int16 *
0x18001a862  mov     rdx, r13; unsigned __int64
0x18001a865  mov     rcx, r15; unsigned __int16 *
0x18001a868  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a86d  mov     edx, [rdi]
0x18001a86f  test    dl, 1
0x18001a872  jz      short loc_18001A882
0x18001a874  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18001a877  mov     rcx, rbx; lpFileName
0x18001a87a  mov     [rdi], edx
0x18001a87c  call    cs:__imp_SetFileAttributesW
0x18001a882  mov     rcx, rbx; lpPathName
0x18001a885  call    cs:__imp_RemoveDirectoryW
0x18001a88b  test    eax, eax
0x18001a88d  jnz     short loc_18001A909
0x18001a88f  call    cs:__imp_GetLastError
0x18001a895  cmp     eax, 5
0x18001a898  jnz     short loc_18001A909
0x18001a89a  mov     rcx, rbx; pObjectName
0x18001a89d  call    ?TakeOwnership@@YAJPEBG@Z; TakeOwnership(ushort const *)
0x18001a8a2  test    eax, eax
0x18001a8a4  js      short loc_18001A909
0x18001a8a6  mov     rcx, rbx; pObjectName
0x18001a8a9  call    ?AddAdminAccess@@YAJPEBG@Z; AddAdminAccess(ushort const *)
0x18001a8ae  test    eax, eax
0x18001a8b0  js      short loc_18001A909
0x18001a8b2  mov     rcx, rbx; lpPathName
0x18001a8b5  call    cs:__imp_RemoveDirectoryW
0x18001a8bb  jmp     short loc_18001A909
0x18001a8bd  test    byte ptr [rdi], 5
0x18001a8c0  jz      short loc_18001A8D0
0x18001a8c2  mov     edx, 80h; dwFileAttributes
0x18001a8c7  mov     rcx, rbx; lpFileName
0x18001a8ca  call    cs:__imp_SetFileAttributesW
0x18001a8d0  mov     rcx, rbx; lpFileName
0x18001a8d3  call    cs:__imp_DeleteFileW
0x18001a8d9  test    eax, eax
0x18001a8db  jnz     short loc_18001A909
0x18001a8dd  call    cs:__imp_GetLastError
0x18001a8e3  cmp     eax, 5
0x18001a8e6  jnz     short loc_18001A909
0x18001a8e8  mov     rcx, rbx; pObjectName
0x18001a8eb  call    ?TakeOwnership@@YAJPEBG@Z; TakeOwnership(ushort const *)
0x18001a8f0  test    eax, eax
0x18001a8f2  js      short loc_18001A909
0x18001a8f4  mov     rcx, rbx; pObjectName
0x18001a8f7  call    ?AddAdminAccess@@YAJPEBG@Z; AddAdminAccess(ushort const *)
0x18001a8fc  test    eax, eax
0x18001a8fe  js      short loc_18001A909
0x18001a900  mov     rcx, rbx; lpFileName
0x18001a903  call    cs:__imp_DeleteFileW
0x18001a909  mov     rdx, rdi; lpFindFileData
0x18001a90c  mov     rcx, r14; hFindFile
0x18001a90f  call    cs:__imp_FindNextFileW
0x18001a915  test    eax, eax
0x18001a917  jnz     loc_18001A80A
0x18001a91d  mov     rcx, r14; hFindFile
0x18001a920  call    cs:__imp_FindClose
0x18001a926  mov     esi, 1
0x18001a92b  test    r12d, r12d
0x18001a92e  jz      short loc_18001A939
0x18001a930  mov     rcx, rbx; hMem
0x18001a933  call    cs:__imp_LocalFree
0x18001a939  test    rdi, rdi
0x18001a93c  jz      short loc_18001A947
0x18001a93e  mov     rcx, rdi; hMem
0x18001a941  call    cs:__imp_LocalFree
0x18001a947  mov     eax, esi
0x18001a949  add     rsp, 28h
0x18001a94d  pop     r15
0x18001a94f  pop     r14
0x18001a951  pop     r13
0x18001a953  pop     r12
0x18001a955  pop     rdi
0x18001a956  pop     rsi
0x18001a957  pop     rbp
0x18001a958  pop     rbx
0x18001a959  retn
```
