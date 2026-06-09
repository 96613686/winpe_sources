# RemoveCacheFile(ushort const *)

- ea: `0x180034610`
- end: `0x180034834`
- name: `?RemoveCacheFile@@YAKPEBG@Z`
- size: `548`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800345a0`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x180034610`
- `0x18003483c`
- `0x1800543c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180034747`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180034747`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003471f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003471f`
- `KERNEL32!LocalAlloc` at `0x1800346a8`
- `KERNEL32!LocalAlloc` at `0x1800346b6`
- `KERNEL32!LocalAlloc` at `0x1800346a8`
- `KERNEL32!LocalAlloc` at `0x1800346b6`
- `KERNEL32!FindClose` at `0x1800347e5`
- `KERNEL32!FindClose` at `0x1800347e5`
- `KERNEL32!FindNextFileW` at `0x1800347a9`
- `KERNEL32!FindNextFileW` at `0x1800347a9`
- `KERNEL32!FindFirstFileW` at `0x18003475b`
- `KERNEL32!FindFirstFileW` at `0x18003475b`
- `KERNEL32!LocalFree` at `0x1800347c8`
- `KERNEL32!LocalFree` at `0x1800347d6`
- `KERNEL32!LocalFree` at `0x1800347c8`
- `KERNEL32!LocalFree` at `0x1800347d6`
- `KERNEL32!GetLastError` at `0x180034665`
- `KERNEL32!GetLastError` at `0x1800346e7`
- `KERNEL32!GetLastError` at `0x18003476a`
- `KERNEL32!GetLastError` at `0x180034665`
- `KERNEL32!GetLastError` at `0x1800346e7`
- `KERNEL32!GetLastError` at `0x18003476a`
- `USERENV!GetProfilesDirectoryW` at `0x180034657`
- `USERENV!GetProfilesDirectoryW` at `0x1800346dd`
- `USERENV!GetProfilesDirectoryW` at `0x180034657`
- `USERENV!GetProfilesDirectoryW` at `0x1800346dd`

## string_xrefs

- `0x18003466b`: `Failed to get profiles directory %d\n`
- `0x1800346ed`: `Failed to get profiles directory %d\n`
- `0x180034678`: `RemoveCacheFile`
- `0x1800346fc`: `RemoveCacheFile`
- `0x180034800`: `RemoveCacheFile`
- `0x18003472b`: `Failed to copy profiles directory %d\n`

## pseudocode

```c
__int64 __fastcall RemoveCacheFile(const unsigned __int16 *a1)
{
  DWORD LastError; // ebx
  __int64 v3; // rax
  __int64 v4; // r12
  SIZE_T v5; // rbx
  WCHAR *v6; // rdi
  unsigned __int16 *v7; // r15
  __int64 FirstFileW; // rsi
  DWORD v9; // eax
  const char *v10; // r9
  __int64 v11; // r8
  DWORD cchSize[4]; // [rsp+30h] [rbp-2A8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-298h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  cchSize[0] = 0;
  GetProfilesDirectoryW(0, cchSize);
  if ( !cchSize[0] )
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "RemoveCacheFile", 193, "Failed to get profiles directory %d\n", LastError);
    goto LABEL_25;
  }
  v3 = cchSize[0] + 3;
  v4 = (unsigned int)v3;
  v5 = 2 * v3;
  v6 = (WCHAR *)LocalAlloc(0x40u, 2 * v3);
  v7 = (unsigned __int16 *)LocalAlloc(0x40u, v5);
  if ( v7 && v6 )
  {
    FirstFileW = -1;
    if ( GetProfilesDirectoryW(v6, cchSize) )
    {
      v9 = _o_wcscpy_s(v7, v4, v6);
      LastError = v9;
      if ( v9 )
      {
        v10 = "Failed to copy profiles directory %d\n";
        v11 = 218;
        goto LABEL_8;
      }
      LastError = _o_wcscat_s(v6, v4, L"\\*");
      if ( LastError )
        goto LABEL_20;
      FirstFileW = (__int64)FindFirstFileW(v6, &FindFileData);
      if ( FirstFileW != -1 )
      {
        do
        {
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 && FindFileData.cFileName[0] != 46 )
            RemoveChromeFontCache(a1, v7, FindFileData.cFileName);
        }
        while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
        LastError = 0;
        goto LABEL_20;
      }
      v9 = GetLastError();
      v10 = "FindFirstFile failed %d\n";
      v11 = 234;
    }
    else
    {
      v9 = GetLastError();
      v10 = "Failed to get profiles directory %d\n";
      v11 = 211;
    }
    LastError = v9;
LABEL_8:
    AslLogCallPrintf(1, "RemoveCacheFile", v11, v10, v9);
LABEL_20:
    LocalFree(v6);
    goto LABEL_21;
  }
  FirstFileW = -1;
  LastError = 8;
  if ( v6 )
    goto LABEL_20;
LABEL_21:
  if ( v7 )
    LocalFree(v7);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
LABEL_25:
  if ( LastError )
    AslLogCallPrintf(1, "RemoveCacheFile", 267, "Failed with %d\n", LastError);
  return LastError;
}

```

## disassembly

```asm
0x180034610  push    rbx
0x180034612  push    rsi
0x180034613  push    rdi
0x180034614  push    r12
0x180034616  push    r13
0x180034618  push    r15
0x18003461a  sub     rsp, 2A8h
0x180034621  mov     rax, cs:__security_cookie
0x180034628  xor     rax, rsp
0x18003462b  mov     [rsp+2D8h+var_48], rax
0x180034633  mov     r13, rcx
0x180034636  xor     edx, edx; Val
0x180034638  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x18003463d  mov     r8d, 250h; Size
0x180034643  call    memset_0
0x180034648  lea     rdx, [rsp+2D8h+cchSize]; lpcchSize
0x18003464d  mov     [rsp+2D8h+cchSize], 0
0x180034655  xor     ecx, ecx; lpProfileDir
0x180034657  call    cs:__imp_GetProfilesDirectoryW
0x18003465d  mov     eax, [rsp+2D8h+cchSize]
0x180034661  test    eax, eax
0x180034663  jnz     short loc_180034694
0x180034665  call    cs:__imp_GetLastError
0x18003466b  lea     r9, aFailedToGetPro; "Failed to get profiles directory %d\n"
0x180034672  mov     r8d, 0C1h
0x180034678  lea     rdx, aRemovecachefil; "RemoveCacheFile"
0x18003467f  mov     [rsp+2D8h+var_2B8], eax
0x180034683  mov     ecx, 1
0x180034688  mov     ebx, eax
0x18003468a  call    AslLogCallPrintf
0x18003468f  jmp     loc_1800347EB
0x180034694  add     eax, 3
0x180034697  mov     esi, 40h ; '@'
0x18003469c  mov     ecx, esi; uFlags
0x18003469e  mov     r12d, eax
0x1800346a1  lea     rbx, [rax+rax]
0x1800346a5  mov     rdx, rbx; uBytes
0x1800346a8  call    cs:__imp_LocalAlloc
0x1800346ae  mov     rdx, rbx; uBytes
0x1800346b1  mov     ecx, esi; uFlags
0x1800346b3  mov     rdi, rax
0x1800346b6  call    cs:__imp_LocalAlloc
0x1800346bc  mov     r15, rax
0x1800346bf  test    rax, rax
0x1800346c2  jz      loc_1800347B7
0x1800346c8  test    rdi, rdi
0x1800346cb  jz      loc_1800347B7
0x1800346d1  lea     rdx, [rsp+2D8h+cchSize]; lpcchSize
0x1800346d6  mov     rcx, rdi; lpProfileDir
0x1800346d9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800346dd  call    cs:__imp_GetProfilesDirectoryW
0x1800346e3  test    eax, eax
0x1800346e5  jnz     short loc_180034716
0x1800346e7  call    cs:__imp_GetLastError
0x1800346ed  lea     r9, aFailedToGetPro; "Failed to get profiles directory %d\n"
0x1800346f4  mov     r8d, 0D3h
0x1800346fa  mov     ebx, eax
0x1800346fc  lea     rdx, aRemovecachefil; "RemoveCacheFile"
0x180034703  mov     [rsp+2D8h+var_2B8], eax
0x180034707  mov     ecx, 1
0x18003470c  call    AslLogCallPrintf
0x180034711  jmp     loc_1800347C5
0x180034716  mov     r8, rdi
0x180034719  mov     rdx, r12
0x18003471c  mov     rcx, r15
0x18003471f  call    cs:__imp__o_wcscpy_s
0x180034725  mov     ebx, eax
0x180034727  test    eax, eax
0x180034729  jz      short loc_18003473A
0x18003472b  lea     r9, aFailedToCopyPr; "Failed to copy profiles directory %d\n"
0x180034732  mov     r8d, 0DAh
0x180034738  jmp     short loc_1800346FC
0x18003473a  lea     r8, asc_180075210; "\\*"
0x180034741  mov     rdx, r12
0x180034744  mov     rcx, rdi
0x180034747  call    cs:__imp__o_wcscat_s
0x18003474d  mov     ebx, eax
0x18003474f  test    eax, eax
0x180034751  jnz     short loc_1800347C5
0x180034753  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x180034758  mov     rcx, rdi; lpFileName
0x18003475b  call    cs:__imp_FindFirstFileW
0x180034761  mov     rsi, rax
0x180034764  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034768  jnz     short loc_180034782
0x18003476a  call    cs:__imp_GetLastError
0x180034770  lea     r9, aFindfirstfileF_0; "FindFirstFile failed %d\n"
0x180034777  mov     r8d, 0EAh
0x18003477d  jmp     loc_1800346FA
0x180034782  test    byte ptr [rsp+2D8h+FindFileData.dwFileAttributes], 10h
0x180034787  jz      short loc_1800347A1
0x180034789  cmp     [rsp+2D8h+FindFileData.cFileName], 2Eh ; '.'
0x18003478f  jz      short loc_1800347A1
0x180034791  lea     r8, [rsp+2D8h+FindFileData.cFileName]; unsigned __int16 *
0x180034796  mov     rdx, r15; unsigned __int16 *
0x180034799  mov     rcx, r13; unsigned __int16 *
0x18003479c  call    ?RemoveChromeFontCache@@YAKPEBG00@Z; RemoveChromeFontCache(ushort const *,ushort const *,ushort const *)
0x1800347a1  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x1800347a6  mov     rcx, rsi; hFindFile
0x1800347a9  call    cs:__imp_FindNextFileW
0x1800347af  test    eax, eax
0x1800347b1  jnz     short loc_180034782
0x1800347b3  xor     ebx, ebx
0x1800347b5  jmp     short loc_1800347C5
0x1800347b7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800347bb  mov     ebx, 8
0x1800347c0  test    rdi, rdi
0x1800347c3  jz      short loc_1800347CE
0x1800347c5  mov     rcx, rdi; hMem
0x1800347c8  call    cs:__imp_LocalFree
0x1800347ce  test    r15, r15
0x1800347d1  jz      short loc_1800347DC
0x1800347d3  mov     rcx, r15; hMem
0x1800347d6  call    cs:__imp_LocalFree
0x1800347dc  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800347e0  jz      short loc_1800347EB
0x1800347e2  mov     rcx, rsi; hFindFile
0x1800347e5  call    cs:__imp_FindClose
0x1800347eb  test    ebx, ebx
0x1800347ed  jz      short loc_180034811
0x1800347ef  lea     r9, aFailedWithD; "Failed with %d\n"
0x1800347f6  mov     [rsp+2D8h+var_2B8], ebx
0x1800347fa  mov     r8d, 10Bh
0x180034800  lea     rdx, aRemovecachefil; "RemoveCacheFile"
0x180034807  mov     ecx, 1
0x18003480c  call    AslLogCallPrintf
0x180034811  mov     eax, ebx
0x180034813  mov     rcx, [rsp+2D8h+var_48]
0x18003481b  xor     rcx, rsp; StackCookie
0x18003481e  call    __security_check_cookie
0x180034823  add     rsp, 2A8h
0x18003482a  pop     r15
0x18003482c  pop     r13
0x18003482e  pop     r12
0x180034830  pop     rdi
0x180034831  pop     rsi
0x180034832  pop     rbx
0x180034833  retn
```
