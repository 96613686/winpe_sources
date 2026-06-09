# AthGetTempUniquePathW(ulong,ushort *)

- ea: `0x1800095a8`
- end: `0x180009748`
- name: `?AthGetTempUniquePathW@@YAKKPEAG@Z`
- size: `416`
- prototype: `unsigned int(unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000ab80`
- `0x18000af00`

## callees

- `0x180001150`
- `0x180003614`
- `0x1800046b4`
- `0x1800095a8`
- `0x180012f82`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetTempPathA` at `0x1800095df`
- `KERNEL32!GetTempPathA` at `0x1800095df`
- `KERNEL32!GetTempFileNameA` at `0x180009605`
- `KERNEL32!GetTempFileNameA` at `0x180009605`
- `KERNEL32!DeleteFileA` at `0x180009719`
- `KERNEL32!DeleteFileA` at `0x180009719`
- `SHLWAPI!PathFindFileNameA` at `0x18000961a`
- `SHLWAPI!PathFindFileNameA` at `0x1800096ad`
- `SHLWAPI!PathFindFileNameA` at `0x18000961a`
- `SHLWAPI!PathFindFileNameA` at `0x1800096ad`
- `SHLWAPI!PathFindExtensionA` at `0x18000962a`
- `SHLWAPI!PathFindExtensionA` at `0x18000962a`
- `WININET!CreateUrlCacheEntryA` at `0x18000969e`
- `WININET!CreateUrlCacheEntryA` at `0x18000969e`

## pseudocode

```c
__int64 __fastcall AthGetTempUniquePathW(__int64 a1, unsigned __int16 *a2)
{
  const char *FileNameA; // rbx
  LPSTR ExtensionA; // rax
  unsigned int v5; // eax
  unsigned __int64 v6; // rdx
  LPSTR v7; // rax
  WCHAR *v8; // rax
  WCHAR *v9; // rsi
  __int64 v10; // rbx
  CHAR szFileName[272]; // [rsp+30h] [rbp-D0h] BYREF
  CHAR Buffer[288]; // [rsp+140h] [rbp+40h] BYREF
  CHAR TempFileName[272]; // [rsp+260h] [rbp+160h] BYREF

  if ( !GetTempPathA(0x118u, Buffer) )
    goto LABEL_20;
  if ( !GetTempFileNameA(Buffer, "wbk", 0, TempFileName) )
    goto LABEL_20;
  FileNameA = PathFindFileNameA(TempFileName);
  ExtensionA = PathFindExtensionA(TempFileName);
  if ( !FileNameA )
    goto LABEL_20;
  if ( ExtensionA && ExtensionA >= FileNameA )
  {
    v5 = (_DWORD)ExtensionA - (_DWORD)FileNameA + 1;
    if ( v5 > 0x104 )
      v5 = 260;
    v6 = v5;
  }
  else
  {
    v6 = 260;
  }
  StringCchCopyA(szFileName, v6, FileNameA);
  StringCchPrintfA(Buffer, 0x118u, "http://%s.bogus", szFileName);
  Buffer[279] = 0;
  szFileName[0] = 0;
  if ( CreateUrlCacheEntryA(Buffer, 0, 0, szFileName, 0) )
  {
    v7 = PathFindFileNameA(szFileName);
    if ( v7 )
      *v7 = 0;
    v8 = PszToUnicode(0, szFileName);
    v9 = v8;
    if ( !v8 )
      goto LABEL_18;
    v10 = -1;
    do
      ++v10;
    while ( v8[v10] );
    if ( (unsigned int)v10 < 0x104 )
    {
      memcpy_0(a2, v8, 2LL * (unsigned int)(v10 + 1));
    }
    else
    {
LABEL_18:
      *a2 = 0;
      LODWORD(v10) = 0;
    }
    ((void (__fastcall *)(LPMALLOC, WCHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v9);
    DeleteFileA(TempFileName);
    return (unsigned int)v10;
  }
  else
  {
LABEL_20:
    *a2 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x1800095a8  push    rbp
0x1800095aa  push    rbx
0x1800095ab  push    rsi
0x1800095ac  push    rdi
0x1800095ad  push    r14
0x1800095af  push    r15
0x1800095b1  lea     rbp, [rsp-288h]
0x1800095b9  sub     rsp, 388h
0x1800095c0  mov     rax, cs:__security_cookie
0x1800095c7  xor     rax, rsp
0x1800095ca  mov     [rbp+2B0h+var_40], rax
0x1800095d1  mov     r14, rdx
0x1800095d4  mov     esi, 118h
0x1800095d9  mov     ecx, esi; nBufferLength
0x1800095db  lea     rdx, [rbp+2B0h+Buffer]; lpBuffer
0x1800095df  call    cs:__imp_GetTempPathA
0x1800095e5  xor     r15d, r15d
0x1800095e8  test    eax, eax
0x1800095ea  jz      loc_180009723
0x1800095f0  lea     r9, [rbp+2B0h+TempFileName]; lpTempFileName
0x1800095f7  xor     r8d, r8d; uUnique
0x1800095fa  lea     rdx, PrefixString; "wbk"
0x180009601  lea     rcx, [rbp+2B0h+Buffer]; lpPathName
0x180009605  call    cs:__imp_GetTempFileNameA
0x18000960b  test    eax, eax
0x18000960d  jz      loc_180009723
0x180009613  lea     rcx, [rbp+2B0h+TempFileName]; pszPath
0x18000961a  call    cs:__imp_PathFindFileNameA
0x180009620  lea     rcx, [rbp+2B0h+TempFileName]; pszPath
0x180009627  mov     rbx, rax
0x18000962a  call    cs:__imp_PathFindExtensionA
0x180009630  test    rbx, rbx
0x180009633  jz      loc_180009723
0x180009639  test    rax, rax
0x18000963c  jz      short loc_180009653
0x18000963e  cmp     rax, rbx
0x180009641  jb      short loc_180009653
0x180009643  sub     eax, ebx
0x180009645  lea     edi, [rsi-14h]
0x180009648  inc     eax
0x18000964a  cmp     eax, edi
0x18000964c  cmova   eax, edi
0x18000964f  mov     edx, eax
0x180009651  jmp     short loc_18000965A
0x180009653  mov     edi, 104h
0x180009658  mov     edx, edi; unsigned __int64
0x18000965a  mov     r8, rbx; char *
0x18000965d  lea     rcx, [rsp+3B0h+szFileName]; char *
0x180009662  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180009667  lea     r9, [rsp+3B0h+szFileName]
0x18000966c  mov     rdx, rsi; unsigned __int64
0x18000966f  lea     r8, aHttpSBogus; "http://%s.bogus"
0x180009676  lea     rcx, [rbp+2B0h+Buffer]; char *
0x18000967a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000967f  lea     r9, [rsp+3B0h+szFileName]; lpszFileName
0x180009684  mov     [rbp+2B0h+var_159], r15b
0x18000968b  xor     r8d, r8d; lpszFileExtension
0x18000968e  mov     [rsp+3B0h+szFileName], r15b
0x180009693  xor     edx, edx; dwExpectedFileSize
0x180009695  mov     [rsp+3B0h+dwReserved], r15d; dwReserved
0x18000969a  lea     rcx, [rbp+2B0h+Buffer]; lpszUrlName
0x18000969e  call    cs:__imp_CreateUrlCacheEntryA
0x1800096a4  test    eax, eax
0x1800096a6  jz      short loc_180009723
0x1800096a8  lea     rcx, [rsp+3B0h+szFileName]; pszPath
0x1800096ad  call    cs:__imp_PathFindFileNameA
0x1800096b3  test    rax, rax
0x1800096b6  jz      short loc_1800096BB
0x1800096b8  mov     [rax], r15b
0x1800096bb  lea     rdx, [rsp+3B0h+szFileName]; lpMultiByteStr
0x1800096c0  xor     ecx, ecx; CodePage
0x1800096c2  call    PszToUnicode
0x1800096c7  mov     rsi, rax
0x1800096ca  test    rax, rax
0x1800096cd  jz      short loc_1800096F5
0x1800096cf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800096d3  inc     rbx
0x1800096d6  cmp     [rax+rbx*2], r15w
0x1800096db  jnz     short loc_1800096D3
0x1800096dd  cmp     ebx, edi
0x1800096df  jnb     short loc_1800096F5
0x1800096e1  lea     r8d, [rbx+1]
0x1800096e5  mov     rdx, rsi; Src
0x1800096e8  add     r8, r8; Size
0x1800096eb  mov     rcx, r14; void *
0x1800096ee  call    memcpy_0
0x1800096f3  jmp     short loc_1800096FC
0x1800096f5  mov     [r14], r15w
0x1800096f9  mov     ebx, r15d
0x1800096fc  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180009703  mov     rdx, [rcx]
0x180009706  mov     rax, [rdx+28h]
0x18000970a  mov     rdx, rsi
0x18000970d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009712  lea     rcx, [rbp+2B0h+TempFileName]; lpFileName
0x180009719  call    cs:__imp_DeleteFileA
0x18000971f  mov     eax, ebx
0x180009721  jmp     short loc_180009729
0x180009723  mov     [r14], r15w
0x180009727  xor     eax, eax
0x180009729  mov     rcx, [rbp+2B0h+var_40]
0x180009730  xor     rcx, rsp; StackCookie
0x180009733  call    __security_check_cookie
0x180009738  add     rsp, 388h
0x18000973f  pop     r15
0x180009741  pop     r14
0x180009743  pop     rdi
0x180009744  pop     rsi
0x180009745  pop     rbx
0x180009746  pop     rbp
0x180009747  retn
```
