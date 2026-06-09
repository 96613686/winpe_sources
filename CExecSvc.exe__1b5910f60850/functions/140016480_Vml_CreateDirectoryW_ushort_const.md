# Vml::CreateDirectoryW(ushort const *)

- ea: `0x140016480`
- end: `0x1400165dd`
- name: `?CreateDirectoryW@Vml@@YAKPEBG@Z`
- size: `349`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x140016cc0`

## callees

- `0x140002310`
- `0x140016480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400164ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001658f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400164ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001658f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400164bc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140016585`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400164bc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140016585`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001659e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001659e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1400164a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1400164a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x140016543`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x140016543`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x140016534`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x140016534`

## pseudocode

```c
__int64 __fastcall Vml::CreateDirectoryW(LPCWSTR lpPathName, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rdi
  DWORD LastError; // ebx
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  WCHAR *v7; // rcx
  LPWSTR v8; // rax
  LPWSTR v9; // rdi
  WCHAR v10; // ax
  DWORD v11; // eax
  DWORD FileAttributesW; // eax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-248h] BYREF

  v2 = lpPathName;
  if ( PathIsRelativeW(lpPathName) )
    return 161;
  if ( CreateDirectoryW(v2, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError != 3 )
    return LastError;
  v4 = pszPath;
  v5 = 260;
  v6 = 2147483646;
  do
  {
    if ( !v6 )
      break;
    if ( !*v2 )
      break;
    *v4++ = *v2++;
    --v6;
    --v5;
  }
  while ( v5 );
  v7 = v4 - 1;
  if ( v5 )
    v7 = v4;
  *v7 = 0;
  if ( !v5 || PathCchAddBackslash(pszPath, 0x104u) < 0 )
    return 206;
  v8 = PathSkipRootW(pszPath);
  v9 = v8;
  if ( v8 )
  {
    if ( *v8 )
    {
      LastError = 183;
      while ( 1 )
      {
        v10 = *v9;
        do
        {
          if ( v10 == 92 )
            break;
          v10 = *++v9;
        }
        while ( *v9 );
        if ( *v9 )
        {
          *v9 = 0;
          if ( !CreateDirectoryW(pszPath, 0) )
          {
            v11 = GetLastError();
            if ( v11 != 183 )
              return v11;
            FileAttributesW = GetFileAttributesW(pszPath);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
              return LastError;
          }
        }
        *v9++ = 92;
        if ( !*v9 )
          return 0;
      }
    }
    return 0;
  }
  return 161;
}

```

## disassembly

```asm
0x140016480  push    rbx
0x140016482  push    rbp
0x140016483  push    rsi
0x140016484  push    rdi
0x140016485  sub     rsp, 248h
0x14001648c  mov     rax, cs:__security_cookie
0x140016493  xor     rax, rsp
0x140016496  mov     [rsp+268h+var_38], rax
0x14001649e  mov     rdi, rcx
0x1400164a1  call    cs:__imp_PathIsRelativeW
0x1400164a7  xor     esi, esi
0x1400164a9  test    eax, eax
0x1400164ab  jz      short loc_1400164B7
0x1400164ad  mov     ebx, 0A1h
0x1400164b2  jmp     loc_1400165BB
0x1400164b7  xor     edx, edx; lpSecurityAttributes
0x1400164b9  mov     rcx, rdi; lpPathName
0x1400164bc  call    cs:__imp_CreateDirectoryW
0x1400164c2  test    eax, eax
0x1400164c4  jnz     loc_1400165B9
0x1400164ca  call    cs:__imp_GetLastError
0x1400164d0  mov     ebx, eax
0x1400164d2  cmp     eax, 3
0x1400164d5  jnz     loc_1400165BB
0x1400164db  mov     r9d, 104h
0x1400164e1  lea     rax, [rsp+268h+pszPath]
0x1400164e6  mov     edx, r9d
0x1400164e9  mov     ecx, 7FFFFFFEh
0x1400164ee  test    rcx, rcx
0x1400164f1  jz      short loc_140016512
0x1400164f3  movzx   r8d, word ptr [rdi]
0x1400164f7  test    r8w, r8w
0x1400164fb  jz      short loc_140016512
0x1400164fd  mov     [rax], r8w
0x140016501  add     rdi, 2
0x140016505  add     rax, 2
0x140016509  dec     rcx
0x14001650c  sub     rdx, 1
0x140016510  jnz     short loc_1400164EE
0x140016512  test    rdx, rdx
0x140016515  lea     rcx, [rax-2]
0x140016519  cmovnz  rcx, rax
0x14001651d  mov     [rcx], si
0x140016520  jnz     short loc_14001652C
0x140016522  mov     ebx, 0CEh
0x140016527  jmp     loc_1400165BB
0x14001652c  mov     rdx, r9; cchPath
0x14001652f  lea     rcx, [rsp+268h+pszPath]; pszPath
0x140016534  call    cs:__imp_PathCchAddBackslash
0x14001653a  test    eax, eax
0x14001653c  js      short loc_140016522
0x14001653e  lea     rcx, [rsp+268h+pszPath]; pszPath
0x140016543  call    cs:__imp_PathSkipRootW
0x140016549  mov     rdi, rax
0x14001654c  test    rax, rax
0x14001654f  jz      loc_1400164AD
0x140016555  cmp     [rax], si
0x140016558  jz      short loc_1400165B9
0x14001655a  mov     ebp, 5Ch ; '\'
0x14001655f  lea     ebx, [rbp+5Bh]
0x140016562  movzx   eax, word ptr [rdi]
0x140016565  cmp     ax, bp
0x140016568  jz      short loc_140016576
0x14001656a  add     rdi, 2
0x14001656e  movzx   eax, word ptr [rdi]
0x140016571  test    ax, ax
0x140016574  jnz     short loc_140016565
0x140016576  cmp     [rdi], si
0x140016579  jz      short loc_1400165AD
0x14001657b  xor     edx, edx; lpSecurityAttributes
0x14001657d  mov     [rdi], si
0x140016580  lea     rcx, [rsp+268h+pszPath]; lpPathName
0x140016585  call    cs:__imp_CreateDirectoryW
0x14001658b  test    eax, eax
0x14001658d  jnz     short loc_1400165AD
0x14001658f  call    cs:__imp_GetLastError
0x140016595  cmp     eax, ebx
0x140016597  jnz     short loc_1400165D9
0x140016599  lea     rcx, [rsp+268h+pszPath]; lpFileName
0x14001659e  call    cs:__imp_GetFileAttributesW
0x1400165a4  cmp     eax, 0FFFFFFFFh
0x1400165a7  jz      short loc_1400165BB
0x1400165a9  test    al, 10h
0x1400165ab  jz      short loc_1400165BB
0x1400165ad  mov     [rdi], bp
0x1400165b0  add     rdi, 2
0x1400165b4  cmp     [rdi], si
0x1400165b7  jnz     short loc_140016562
0x1400165b9  mov     ebx, esi
0x1400165bb  mov     eax, ebx
0x1400165bd  mov     rcx, [rsp+268h+var_38]
0x1400165c5  xor     rcx, rsp; StackCookie
0x1400165c8  call    __security_check_cookie
0x1400165cd  add     rsp, 248h
0x1400165d4  pop     rdi
0x1400165d5  pop     rsi
0x1400165d6  pop     rbp
0x1400165d7  pop     rbx
0x1400165d8  retn
0x1400165d9  mov     ebx, eax
0x1400165db  jmp     short loc_1400165BB
```
