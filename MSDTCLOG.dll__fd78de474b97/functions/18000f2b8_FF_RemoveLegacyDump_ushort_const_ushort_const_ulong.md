# FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)

- ea: `0x18000f2b8`
- end: `0x18000f4d5`
- name: `?FF_RemoveLegacyDump@@YAXPEBG0K@Z`
- size: `541`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000ee14`

## callees

- `0x18000abd4`
- `0x18000e000`
- `0x18000f2b8`
- `0x18001280a`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000f3f8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000f3f8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000f43d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000f488`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000f43d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000f488`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f44a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f495`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f44a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f495`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000f4a4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000f4a4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000f372`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000f372`
- `msvcrt!wcsrchr` at `0x18000f45a`
- `msvcrt!wcsrchr` at `0x18000f45a`
- `msvcrt!_wcsicmp` at `0x18000f39f`
- `msvcrt!_wcsicmp` at `0x18000f39f`

## pseudocode

```c
void __fastcall FF_RemoveLegacyDump(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v6; // edi
  HANDLE FirstFileW; // rbx
  __int64 v8; // rcx
  WCHAR *cFileName; // r8
  __int64 v10; // rdx
  wchar_t *v11; // rax
  wchar_t *v12; // rcx
  wchar_t *v13; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Str[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t String1[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR FileName[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(String1, 0, 0x20Au);
  memset_0(Str, 0, 0x20Au);
  v6 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  StringCchPrintfW(FileName, 0x104u, L"%s\\%s*.dmp", a2, a1);
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    do
    {
      ++v6;
      if ( !String1[0] || _wcsicmp(String1, FindFileData.cFileName) > 0 )
      {
        v8 = 2147483646;
        cFileName = FindFileData.cFileName;
        v10 = 261;
        v11 = String1;
        do
        {
          if ( !v8 )
            break;
          if ( !*cFileName )
            break;
          *v11++ = *cFileName++;
          --v8;
          --v10;
        }
        while ( v10 );
        v12 = v11 - 1;
        if ( v10 )
          v12 = v11;
        *v12 = 0;
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
  }
  if ( v6 >= a3 )
  {
    StringCchPrintfW(Str, 0x105u, L"%s\\%s", a2, String1);
    SetFileAttributesW(Str, 0x80u);
    DeleteFileW(Str);
    v13 = wcsrchr(Str, 0x2Eu);
    if ( v13 )
    {
      *v13 = 0;
      StringCchCatW(Str, 0x105u, L".txt");
      SetFileAttributesW(Str, 0x80u);
      DeleteFileW(Str);
    }
  }
  if ( FirstFileW != (HANDLE)-1LL )
    FindClose(FirstFileW);
}

```

## disassembly

```asm
0x18000f2b8  mov     [rsp-8+arg_10], rbx
0x18000f2bd  mov     [rsp-8+arg_18], rsi
0x18000f2c2  push    rbp
0x18000f2c3  push    rdi
0x18000f2c4  push    r12
0x18000f2c6  push    r14
0x18000f2c8  push    r15
0x18000f2ca  lea     rbp, [rsp-7C0h]
0x18000f2d2  sub     rsp, 8C0h
0x18000f2d9  mov     rax, cs:__security_cookie
0x18000f2e0  xor     rax, rsp
0x18000f2e3  mov     [rbp+7E0h+var_30], rax
0x18000f2ea  mov     esi, r8d
0x18000f2ed  mov     r14, rdx
0x18000f2f0  mov     rbx, rcx
0x18000f2f3  xor     edx, edx; Val
0x18000f2f5  mov     r8d, 208h; Size
0x18000f2fb  lea     rcx, [rbp+7E0h+FileName]; void *
0x18000f302  call    memset_0
0x18000f307  mov     edi, 20Ah
0x18000f30c  lea     rcx, [rbp+7E0h+String1]; void *
0x18000f313  mov     r8d, edi; Size
0x18000f316  xor     edx, edx; Val
0x18000f318  call    memset_0
0x18000f31d  mov     r8d, edi; Size
0x18000f320  lea     rcx, [rbp+7E0h+Str]; void *
0x18000f327  xor     edx, edx; Val
0x18000f329  call    memset_0
0x18000f32e  xor     r15d, r15d
0x18000f331  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x18000f336  xor     edx, edx; Val
0x18000f338  mov     r8d, 250h; Size
0x18000f33e  mov     edi, r15d
0x18000f341  call    memset_0
0x18000f346  mov     r9, r14
0x18000f349  mov     [rsp+8E0h+var_8C0], rbx
0x18000f34e  lea     r8, aSSDmp_0; "%s\\%s*.dmp"
0x18000f355  mov     edx, 104h; unsigned __int64
0x18000f35a  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x18000f361  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f366  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18000f36b  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x18000f372  call    cs:__imp_FindFirstFileW
0x18000f378  mov     rbx, rax
0x18000f37b  mov     r12d, 105h
0x18000f381  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f385  jz      short loc_18000F402
0x18000f387  inc     edi
0x18000f389  cmp     [rbp+7E0h+String1], r15w
0x18000f391  jz      short loc_18000F3A9
0x18000f393  lea     rdx, [rsp+8E0h+FindFileData.cFileName]; String2
0x18000f398  lea     rcx, [rbp+7E0h+String1]; String1
0x18000f39f  call    cs:__imp__wcsicmp
0x18000f3a5  test    eax, eax
0x18000f3a7  jle     short loc_18000F3F0
0x18000f3a9  mov     ecx, 7FFFFFFEh
0x18000f3ae  lea     r8, [rsp+8E0h+FindFileData.cFileName]
0x18000f3b3  mov     rdx, r12
0x18000f3b6  lea     rax, [rbp+7E0h+String1]
0x18000f3bd  test    rcx, rcx
0x18000f3c0  jz      short loc_18000F3E1
0x18000f3c2  movzx   r9d, word ptr [r8]
0x18000f3c6  test    r9w, r9w
0x18000f3ca  jz      short loc_18000F3E1
0x18000f3cc  mov     [rax], r9w
0x18000f3d0  add     r8, 2
0x18000f3d4  add     rax, 2
0x18000f3d8  dec     rcx
0x18000f3db  sub     rdx, 1
0x18000f3df  jnz     short loc_18000F3BD
0x18000f3e1  test    rdx, rdx
0x18000f3e4  lea     rcx, [rax-2]
0x18000f3e8  cmovnz  rcx, rax
0x18000f3ec  mov     [rcx], r15w
0x18000f3f0  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18000f3f5  mov     rcx, rbx; hFindFile
0x18000f3f8  call    cs:__imp_FindNextFileW
0x18000f3fe  test    eax, eax
0x18000f400  jnz     short loc_18000F387
0x18000f402  cmp     edi, esi
0x18000f404  jb      loc_18000F49B
0x18000f40a  lea     rax, [rbp+7E0h+String1]
0x18000f411  mov     r9, r14
0x18000f414  lea     r8, aSS_0; "%s\\%s"
0x18000f41b  mov     [rsp+8E0h+var_8C0], rax
0x18000f420  mov     rdx, r12; unsigned __int64
0x18000f423  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x18000f42a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f42f  mov     edi, 80h
0x18000f434  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18000f43b  mov     edx, edi; dwFileAttributes
0x18000f43d  call    cs:__imp_SetFileAttributesW
0x18000f443  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18000f44a  call    cs:__imp_DeleteFileW
0x18000f450  lea     edx, [rdi-52h]; Ch
0x18000f453  lea     rcx, [rbp+7E0h+Str]; Str
0x18000f45a  call    cs:__imp_wcsrchr
0x18000f460  test    rax, rax
0x18000f463  jz      short loc_18000F49B
0x18000f465  lea     r8, aTxt; ".txt"
0x18000f46c  mov     [rax], r15w
0x18000f470  mov     rdx, r12; unsigned __int64
0x18000f473  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x18000f47a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f47f  mov     edx, edi; dwFileAttributes
0x18000f481  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18000f488  call    cs:__imp_SetFileAttributesW
0x18000f48e  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18000f495  call    cs:__imp_DeleteFileW
0x18000f49b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000f49f  jz      short loc_18000F4AA
0x18000f4a1  mov     rcx, rbx; hFindFile
0x18000f4a4  call    cs:__imp_FindClose
0x18000f4aa  mov     rcx, [rbp+7E0h+var_30]
0x18000f4b1  xor     rcx, rsp; StackCookie
0x18000f4b4  call    __security_check_cookie
0x18000f4b9  lea     r11, [rsp+8E0h+var_20]
0x18000f4c1  mov     rbx, [r11+40h]
0x18000f4c5  mov     rsi, [r11+48h]
0x18000f4c9  mov     rsp, r11
0x18000f4cc  pop     r15
0x18000f4ce  pop     r14
0x18000f4d0  pop     r12
0x18000f4d2  pop     rdi
0x18000f4d3  pop     rbp
0x18000f4d4  retn
```
