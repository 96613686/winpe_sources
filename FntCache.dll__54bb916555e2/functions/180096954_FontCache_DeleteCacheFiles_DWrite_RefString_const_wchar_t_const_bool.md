# FontCache::DeleteCacheFiles(DWrite::RefString const &,wchar_t const *,bool)

- ea: `0x180096954`
- end: `0x180096a23`
- name: `?DeleteCacheFiles@FontCache@@SAXAEBVRefString@DWrite@@PEB_W_N@Z`
- size: `207`
- prototype: `void __fastcall(const struct DWrite::RefString *, const wchar_t *, char)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a6b7c`
- `0x1800a7190`
- `0x1800b1b50`
- `0x1800b5d70`

## callees

- `0x180096954`
- `0x180096a2c`
- `0x180099b28`
- `0x18009f830`
- `0x1800aa650`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800969d2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800969d2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180096998`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180096998`

## pseudocode

```c
void __fastcall FontCache::DeleteCacheFiles(const struct DWrite::RefString *a1, const wchar_t *a2, char a3)
{
  HANDLE FirstFileW; // rax
  HANDLE v6; // [rsp+20h] [rbp-488h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+28h] [rbp-480h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp-228h] BYREF

  if ( FontCache::CombinePath(a1, a2, FileName) )
  {
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    v6 = FirstFileW;
    while ( FirstFileW != (HANDLE)-1LL )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0
        && FontCache::CombinePath(a1, FindFileData.cFileName, FileName)
        && !DeleteFileW(FileName) )
      {
        if ( a3 )
          FontCache::TryRenameAsObsolete(FileName, a1);
      }
      FileEnumerator::MoveNext((FileEnumerator *)&v6);
      FirstFileW = v6;
    }
  }
}

```

## disassembly

```asm
0x180096954  mov     [rsp+arg_10], rbx
0x180096959  push    rdi
0x18009695a  sub     rsp, 4A0h
0x180096961  mov     rax, cs:__security_cookie
0x180096968  xor     rax, rsp
0x18009696b  mov     [rsp+4A8h+var_18], rax
0x180096973  mov     dil, r8b
0x180096976  mov     rbx, rcx
0x180096979  lea     r8, [rsp+4A8h+FileName]; wchar_t *
0x180096981  call    ?CombinePath@FontCache@@KA_KAEBVRefString@DWrite@@PEB_WPEA_W@Z; FontCache::CombinePath(DWrite::RefString const &,wchar_t const *,wchar_t *)
0x180096986  test    rax, rax
0x180096989  jz      short loc_180096A02
0x18009698b  lea     rdx, [rsp+4A8h+FindFileData]; lpFindFileData
0x180096990  lea     rcx, [rsp+4A8h+FileName]; lpFileName
0x180096998  call    cs:__imp_FindFirstFileW
0x18009699e  mov     [rsp+4A8h+var_488], rax
0x1800969a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800969a7  jz      short loc_180096A02
0x1800969a9  test    byte ptr [rsp+4A8h+FindFileData.dwFileAttributes], 10h
0x1800969ae  jnz     short loc_1800969F1
0x1800969b0  lea     r8, [rsp+4A8h+FileName]; wchar_t *
0x1800969b8  lea     rdx, [rsp+4A8h+FindFileData.cFileName]; wchar_t *
0x1800969bd  mov     rcx, rbx; struct DWrite::RefString *
0x1800969c0  call    ?CombinePath@FontCache@@KA_KAEBVRefString@DWrite@@PEB_WPEA_W@Z; FontCache::CombinePath(DWrite::RefString const &,wchar_t const *,wchar_t *)
0x1800969c5  test    rax, rax
0x1800969c8  jz      short loc_1800969F1
0x1800969ca  lea     rcx, [rsp+4A8h+FileName]; lpFileName
0x1800969d2  call    cs:__imp_DeleteFileW
0x1800969d8  test    eax, eax
0x1800969da  jnz     short loc_1800969F1
0x1800969dc  test    dil, dil
0x1800969df  jz      short loc_1800969F1
0x1800969e1  mov     rdx, rbx; struct DWrite::RefString *
0x1800969e4  lea     rcx, [rsp+4A8h+FileName]; lpExistingFileName
0x1800969ec  call    ?TryRenameAsObsolete@FontCache@@SAJPEB_WAEBVRefString@DWrite@@@Z; FontCache::TryRenameAsObsolete(wchar_t const *,DWrite::RefString const &)
0x1800969f1  lea     rcx, [rsp+4A8h+var_488]; this
0x1800969f6  call    ?MoveNext@FileEnumerator@@QEAA_NXZ; FileEnumerator::MoveNext(void)
0x1800969fb  mov     rax, [rsp+4A8h+var_488]
0x180096a00  jmp     short loc_1800969A3
0x180096a02  mov     rcx, [rsp+4A8h+var_18]
0x180096a0a  xor     rcx, rsp; StackCookie
0x180096a0d  call    __security_check_cookie
0x180096a12  mov     rbx, [rsp+4A8h+arg_10]
0x180096a1a  add     rsp, 4A0h
0x180096a21  pop     rdi
0x180096a22  retn
```
