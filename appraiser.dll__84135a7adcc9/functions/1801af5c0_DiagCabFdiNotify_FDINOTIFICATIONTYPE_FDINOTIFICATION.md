# DiagCabFdiNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x1801af5c0`
- end: `0x1801af8e7`
- name: `?DiagCabFdiNotify@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `807`
- prototype: `INT_PTR __cdecl(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180008570`
- `0x180093a1c`
- `0x1801af5c0`
- `0x1802174d8`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x1801af692`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x1801af692`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801af837`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801af89e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801af837`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801af89e`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1801af71e`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1801af71e`
- `KERNEL32!CreateDirectoryW` at `0x1801af856`
- `KERNEL32!CreateDirectoryW` at `0x1801af856`
- `KERNEL32!SetFileTime` at `0x1801af6aa`
- `KERNEL32!SetFileTime` at `0x1801af6aa`
- `KERNEL32!GetFullPathNameW` at `0x1801af7a3`
- `KERNEL32!GetFullPathNameW` at `0x1801af7cb`
- `KERNEL32!GetFullPathNameW` at `0x1801af7a3`
- `KERNEL32!GetFullPathNameW` at `0x1801af7cb`
- `KERNEL32!MultiByteToWideChar` at `0x1801af6d5`
- `KERNEL32!MultiByteToWideChar` at `0x1801af754`
- `KERNEL32!MultiByteToWideChar` at `0x1801af6d5`
- `KERNEL32!MultiByteToWideChar` at `0x1801af754`
- `KERNEL32!GetLastError` at `0x1801af860`
- `KERNEL32!GetLastError` at `0x1801af86a`
- `KERNEL32!GetLastError` at `0x1801af860`
- `KERNEL32!GetLastError` at `0x1801af86a`
- `KERNEL32!SetFileAttributesW` at `0x1801af715`
- `KERNEL32!SetFileAttributesW` at `0x1801af715`
- `KERNEL32!LocalFileTimeToFileTime` at `0x1801af685`
- `KERNEL32!LocalFileTimeToFileTime` at `0x1801af685`
- `KERNEL32!DosDateTimeToFileTime` at `0x1801af66d`
- `KERNEL32!DosDateTimeToFileTime` at `0x1801af66d`
- `api-ms-win-crt-stdio-l1-1-0!_wopen` at `0x1801af8b9`
- `api-ms-win-crt-stdio-l1-1-0!_wopen` at `0x1801af8b9`

## pseudocode

```c
INT_PTR __fastcall DiagCabFdiNotify(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  void *pv; // r14
  int v4; // edi
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  void *osfhandle; // rax
  signed int FullPathNameW; // eax
  signed int v11; // eax
  size_t v12; // r8
  unsigned __int64 v13; // rax
  wchar_t *i; // rbx
  signed int LastError; // eax
  unsigned int v16; // ecx
  struct _FILETIME FileTime; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME LastWriteTime; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR FilePart[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str[260]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR WideCharStr[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Buffer[264]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR String1[264]; // [rsp+680h] [rbp+580h] BYREF

  pv = pfdin->pv;
  LastWriteTime = 0;
  FileTime = 0;
  FilePart[0] = 0;
  if ( fdint == fdintCABINET_INFO )
    return 0;
  v4 = -1;
  v5 = fdint - 1;
  if ( !v5 )
    return -1;
  v6 = v5 - 1;
  if ( !v6 )
  {
    if ( MultiByteToWideChar(0xFDE9u, 8u, pfdin->psz1, -1, WideCharStr, 260) )
    {
      if ( (int)StringCbPrintfW(&FileName, 0x208u, L"%s\\%s", *((_QWORD *)pv + 2), WideCharStr) < 0 )
      {
LABEL_38:
        if ( *(_QWORD *)pv )
          (*(void (__fastcall **)(WCHAR *, _QWORD))pv)(&FileName, *((_QWORD *)pv + 1));
        return v4;
      }
      FullPathNameW = GetFullPathNameW(&FileName, 0x104u, Buffer, FilePart);
      if ( FullPathNameW )
      {
        if ( FullPathNameW <= 260 )
        {
          v11 = GetFullPathNameW(*((LPCWSTR *)pv + 2), 0x104u, String1, FilePart);
          if ( v11 )
          {
            if ( v11 <= 260 )
            {
              v12 = -1;
              do
                ++v12;
              while ( String1[v12] );
              v13 = -1;
              do
                ++v13;
              while ( Buffer[v13] );
              if ( v12 <= v13 && !wcsncmp_0(String1, Buffer, v12) )
              {
                for ( i = wcschr(Str, 0x5Cu); i; i = wcschr(i + 1, 0x5Cu) )
                {
                  *i = 0;
                  if ( CreateDirectoryW(&FileName, 0) || !GetLastError() )
                  {
                    *i = 92;
                  }
                  else
                  {
                    LastError = GetLastError();
                    v16 = LastError;
                    if ( LastError > 0 )
                      v16 = (unsigned __int16)LastError | 0x80070000;
                    *i = 92;
                    if ( ((v16 + 0x80000000) & 0x80000000) == 0 && v16 != -2147024713 )
                      goto LABEL_38;
                  }
                }
                v4 = _wopen(&FileName, 33025, 0);
                goto LABEL_38;
              }
            }
          }
        }
      }
    }
    return -1;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 0;
    return -1;
  }
  if ( DosDateTimeToFileTime(pfdin->date, pfdin->time, &FileTime) )
  {
    if ( LocalFileTimeToFileTime(&FileTime, &LastWriteTime) )
    {
      osfhandle = (void *)_get_osfhandle(pfdin->hf);
      if ( osfhandle != (void *)-1LL )
        SetFileTime(osfhandle, 0, 0, &LastWriteTime);
    }
  }
  if ( MultiByteToWideChar(0xFDE9u, 8u, pfdin->psz1, -1, WideCharStr, 260) )
  {
    if ( (int)StringCbPrintfW(&FileName, 0x208u, L"%s\\%s", *((_QWORD *)pv + 2), WideCharStr) >= 0 )
      SetFileAttributesW(&FileName, pfdin->attribs & 0x27);
  }
  _o__close(LODWORD(pfdin->hf));
  return 1;
}

```

## disassembly

```asm
0x1801af5c0  mov     [rsp-8+arg_0], rbx
0x1801af5c5  mov     [rsp-8+arg_10], rsi
0x1801af5ca  push    rbp
0x1801af5cb  push    rdi
0x1801af5cc  push    r12
0x1801af5ce  push    r14
0x1801af5d0  push    r15
0x1801af5d2  lea     rbp, [rsp-7A0h]
0x1801af5da  sub     rsp, 8A0h
0x1801af5e1  mov     rax, cs:__security_cookie
0x1801af5e8  xor     rax, rsp
0x1801af5eb  mov     [rbp+7C0h+var_30], rax
0x1801af5f2  mov     r14, [rdx+20h]
0x1801af5f6  xor     r15d, r15d
0x1801af5f9  mov     qword ptr [rsp+8C0h+LastWriteTime.dwLowDateTime], r15
0x1801af5fe  mov     rbx, rdx
0x1801af601  mov     qword ptr [rsp+8C0h+FileTime.dwLowDateTime], r15
0x1801af606  mov     [rsp+8C0h+FilePart], r15
0x1801af60b  test    ecx, ecx
0x1801af60d  jz      short loc_1801AF633
0x1801af60f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801af613  sub     ecx, 1
0x1801af616  jz      loc_1801AF8DF
0x1801af61c  sub     ecx, 1
0x1801af61f  jz      loc_1801AF72E
0x1801af625  sub     ecx, 1
0x1801af628  jz      short loc_1801AF660
0x1801af62a  cmp     ecx, 1
0x1801af62d  jz      loc_1801AF8DF
0x1801af633  xor     eax, eax
0x1801af635  mov     rcx, [rbp+7C0h+var_30]
0x1801af63c  xor     rcx, rsp; StackCookie
0x1801af63f  call    __security_check_cookie
0x1801af644  lea     r11, [rsp+8C0h+var_20]
0x1801af64c  mov     rbx, [r11+30h]
0x1801af650  mov     rsi, [r11+40h]
0x1801af654  mov     rsp, r11
0x1801af657  pop     r15
0x1801af659  pop     r14
0x1801af65b  pop     r12
0x1801af65d  pop     rdi
0x1801af65e  pop     rbp
0x1801af65f  retn
0x1801af660  movzx   edx, word ptr [rdx+32h]; wFatTime
0x1801af664  lea     r8, [rsp+8C0h+FileTime]; lpFileTime
0x1801af669  movzx   ecx, word ptr [rbx+30h]; wFatDate
0x1801af66d  call    cs:__imp_DosDateTimeToFileTime
0x1801af673  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801af677  test    eax, eax
0x1801af679  jz      short loc_1801AF6B0
0x1801af67b  lea     rdx, [rsp+8C0h+LastWriteTime]; lpFileTime
0x1801af680  lea     rcx, [rsp+8C0h+FileTime]; lpLocalFileTime
0x1801af685  call    cs:__imp_LocalFileTimeToFileTime
0x1801af68b  test    eax, eax
0x1801af68d  jz      short loc_1801AF6B0
0x1801af68f  mov     ecx, [rbx+28h]; FileHandle
0x1801af692  call    cs:__imp__get_osfhandle
0x1801af698  cmp     rax, rdi
0x1801af69b  jz      short loc_1801AF6B0
0x1801af69d  lea     r9, [rsp+8C0h+LastWriteTime]; lpLastWriteTime
0x1801af6a2  xor     r8d, r8d; lpLastAccessTime
0x1801af6a5  xor     edx, edx; lpCreationTime
0x1801af6a7  mov     rcx, rax; hFile
0x1801af6aa  call    cs:__imp_SetFileTime
0x1801af6b0  mov     r8, [rbx+8]; lpMultiByteStr
0x1801af6b4  lea     rax, [rbp+7C0h+WideCharStr]
0x1801af6bb  mov     [rsp+8C0h+cchWideChar], 104h; cchWideChar
0x1801af6c3  mov     r9d, edi; cbMultiByte
0x1801af6c6  mov     edx, 8; dwFlags
0x1801af6cb  mov     [rsp+8C0h+lpWideCharStr], rax; lpWideCharStr
0x1801af6d0  mov     ecx, 0FDE9h; CodePage
0x1801af6d5  call    cs:__imp_MultiByteToWideChar
0x1801af6db  test    eax, eax
0x1801af6dd  jz      short loc_1801AF71B
0x1801af6df  mov     r9, [r14+10h]
0x1801af6e3  lea     rax, [rbp+7C0h+WideCharStr]
0x1801af6ea  lea     r8, aSS_1; "%s\\%s"
0x1801af6f1  mov     [rsp+8C0h+lpWideCharStr], rax
0x1801af6f6  mov     edx, 208h; unsigned __int64
0x1801af6fb  lea     rcx, [rsp+8C0h+FileName]; unsigned __int16 *
0x1801af700  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801af705  test    eax, eax
0x1801af707  js      short loc_1801AF71B
0x1801af709  movzx   edx, word ptr [rbx+34h]
0x1801af70d  lea     rcx, [rsp+8C0h+FileName]; lpFileName
0x1801af712  and     edx, 27h; dwFileAttributes
0x1801af715  call    cs:__imp_SetFileAttributesW
0x1801af71b  mov     ecx, [rbx+28h]
0x1801af71e  call    cs:__imp__o__close
0x1801af724  mov     eax, 1
0x1801af729  jmp     loc_1801AF635
0x1801af72e  mov     r8, [rdx+8]; lpMultiByteStr
0x1801af732  lea     rax, [rbp+7C0h+WideCharStr]
0x1801af739  mov     esi, 104h
0x1801af73e  mov     r9d, edi; cbMultiByte
0x1801af741  mov     [rsp+8C0h+cchWideChar], esi; cchWideChar
0x1801af745  mov     edx, 8; dwFlags
0x1801af74a  mov     ecx, 0FDE9h; CodePage
0x1801af74f  mov     [rsp+8C0h+lpWideCharStr], rax; lpWideCharStr
0x1801af754  call    cs:__imp_MultiByteToWideChar
0x1801af75a  test    eax, eax
0x1801af75c  jz      loc_1801AF8DF
0x1801af762  mov     r9, [r14+10h]
0x1801af766  lea     rax, [rbp+7C0h+WideCharStr]
0x1801af76d  lea     r8, aSS_1; "%s\\%s"
0x1801af774  mov     [rsp+8C0h+lpWideCharStr], rax
0x1801af779  mov     edx, 208h; unsigned __int64
0x1801af77e  lea     rcx, [rsp+8C0h+FileName]; unsigned __int16 *
0x1801af783  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801af788  test    eax, eax
0x1801af78a  js      loc_1801AF8C1
0x1801af790  lea     r9, [rsp+8C0h+FilePart]; lpFilePart
0x1801af795  mov     edx, esi; nBufferLength
0x1801af797  lea     r8, [rbp+7C0h+Buffer]; lpBuffer
0x1801af79e  lea     rcx, [rsp+8C0h+FileName]; lpFileName
0x1801af7a3  call    cs:__imp_GetFullPathNameW
0x1801af7a9  test    eax, eax
0x1801af7ab  jz      loc_1801AF8DF
0x1801af7b1  cmp     eax, esi
0x1801af7b3  jg      loc_1801AF8DF
0x1801af7b9  mov     rcx, [r14+10h]; lpFileName
0x1801af7bd  lea     r9, [rsp+8C0h+FilePart]; lpFilePart
0x1801af7c2  lea     r8, [rbp+7C0h+String1]; lpBuffer
0x1801af7c9  mov     edx, esi; nBufferLength
0x1801af7cb  call    cs:__imp_GetFullPathNameW
0x1801af7d1  test    eax, eax
0x1801af7d3  jz      loc_1801AF8DF
0x1801af7d9  cmp     eax, esi
0x1801af7db  jg      loc_1801AF8DF
0x1801af7e1  lea     rax, [rbp+7C0h+String1]
0x1801af7e8  mov     r8, rdi
0x1801af7eb  inc     r8; MaxCount
0x1801af7ee  cmp     [rax+r8*2], r15w
0x1801af7f3  jnz     short loc_1801AF7EB
0x1801af7f5  lea     rcx, [rbp+7C0h+Buffer]
0x1801af7fc  mov     rax, rdi
0x1801af7ff  inc     rax
0x1801af802  cmp     [rcx+rax*2], r15w
0x1801af807  jnz     short loc_1801AF7FF
0x1801af809  cmp     r8, rax
0x1801af80c  ja      loc_1801AF8DF
0x1801af812  lea     rdx, [rbp+7C0h+Buffer]; String2
0x1801af819  lea     rcx, [rbp+7C0h+String1]; String1
0x1801af820  call    wcsncmp_0
0x1801af825  test    eax, eax
0x1801af827  jnz     loc_1801AF8DF
0x1801af82d  lea     esi, [rax+5Ch]
0x1801af830  mov     edx, esi; Ch
0x1801af832  lea     rcx, [rsp+8C0h+Str]; Str
0x1801af837  call    cs:__imp_wcschr
0x1801af83d  mov     rbx, rax
0x1801af840  test    rax, rax
0x1801af843  jz      short loc_1801AF8AC
0x1801af845  mov     r12d, 80000000h
0x1801af84b  xor     edx, edx; lpSecurityAttributes
0x1801af84d  mov     [rbx], r15w
0x1801af851  lea     rcx, [rsp+8C0h+FileName]; lpPathName
0x1801af856  call    cs:__imp_CreateDirectoryW
0x1801af85c  test    eax, eax
0x1801af85e  jnz     short loc_1801AF895
0x1801af860  call    cs:__imp_GetLastError
0x1801af866  test    eax, eax
0x1801af868  jz      short loc_1801AF895
0x1801af86a  call    cs:__imp_GetLastError
0x1801af870  mov     ecx, eax
0x1801af872  test    eax, eax
0x1801af874  jle     short loc_1801AF87F
0x1801af876  movzx   ecx, ax
0x1801af879  or      ecx, 80070000h
0x1801af87f  lea     eax, [rcx+r12]
0x1801af883  mov     [rbx], si
0x1801af886  test    r12d, eax
0x1801af889  jnz     short loc_1801AF898
0x1801af88b  cmp     ecx, 800700B7h
0x1801af891  jnz     short loc_1801AF8C1
0x1801af893  jmp     short loc_1801AF898
0x1801af895  mov     [rbx], si
0x1801af898  mov     edx, esi; Ch
0x1801af89a  lea     rcx, [rbx+2]; Str
0x1801af89e  call    cs:__imp_wcschr
0x1801af8a4  mov     rbx, rax
0x1801af8a7  test    rax, rax
0x1801af8aa  jnz     short loc_1801AF84B
0x1801af8ac  xor     r8d, r8d
0x1801af8af  lea     rcx, [rsp+8C0h+FileName]; FileName
0x1801af8b4  mov     edx, 8101h; OpenFlag
0x1801af8b9  call    cs:__imp__wopen
0x1801af8bf  mov     edi, eax
0x1801af8c1  mov     rax, [r14]
0x1801af8c4  test    rax, rax
0x1801af8c7  jz      short loc_1801AF8D7
0x1801af8c9  mov     rdx, [r14+8]
0x1801af8cd  lea     rcx, [rsp+8C0h+FileName]
0x1801af8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af8d7  movsxd  rax, edi
0x1801af8da  jmp     loc_1801AF635
0x1801af8df  mov     rax, rdi
0x1801af8e2  jmp     loc_1801AF635
```
