# DiagCabFdiNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x180025770`
- end: `0x180025a09`
- name: `?DiagCabFdiNotify@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `665`
- prototype: `INT_PTR __fastcall(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180003fc0`
- `0x180025770`
- `0x180025be4`
- `0x180025fd8`
- `0x180026134`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x18002582d`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x18002582d`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1800258b9`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1800258b9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025870`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800258ef`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025870`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800258ef`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180025820`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180025820`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002593e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180025966`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002593e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180025966`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180025845`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180025845`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800258b0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800258b0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180025808`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180025808`
- `api-ms-win-crt-stdio-l1-1-0!_wopen` at `0x1800259db`
- `api-ms-win-crt-stdio-l1-1-0!_wopen` at `0x1800259db`

## pseudocode

```c
INT_PTR __fastcall DiagCabFdiNotify(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  void *pv; // r14
  int v4; // ebx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  void *osfhandle; // rax
  signed int FullPathNameW; // eax
  signed int v11; // eax
  size_t v12; // r8
  unsigned __int64 v13; // rax
  struct _FILETIME FileTime; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME LastWriteTime; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR FilePart[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
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
      if ( (int)StringCbPrintfW(FileName, 0x208u, L"%s\\%s", *((_QWORD *)pv + 2), WideCharStr) < 0 )
      {
LABEL_29:
        if ( *(_QWORD *)pv )
          (*(void (__fastcall **)(WCHAR *, _QWORD))pv)(FileName, *((_QWORD *)pv + 1));
        return v4;
      }
      FullPathNameW = GetFullPathNameW(FileName, 0x104u, Buffer, FilePart);
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
                if ( (int)DiagCreatePath(FileName) >= 0 )
                  v4 = _wopen(FileName, 33025, 0);
                goto LABEL_29;
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
    if ( (int)StringCbPrintfW(FileName, 0x208u, L"%s\\%s", *((_QWORD *)pv + 2), WideCharStr) >= 0 )
      SetFileAttributesW(FileName, pfdin->attribs & 0x27);
  }
  _o__close(LODWORD(pfdin->hf));
  return 1;
}

```

## disassembly

```asm
0x180025770  push    rbp
0x180025772  push    rbx
0x180025773  push    rsi
0x180025774  push    rdi
0x180025775  push    r14
0x180025777  push    r15
0x180025779  lea     rbp, [rsp-7A8h]
0x180025781  sub     rsp, 8A8h
0x180025788  mov     rax, cs:__security_cookie
0x18002578f  xor     rax, rsp
0x180025792  mov     [rbp+7D0h+var_40], rax
0x180025799  mov     r14, [rdx+20h]
0x18002579d  xor     r15d, r15d
0x1800257a0  mov     qword ptr [rsp+8D0h+LastWriteTime.dwLowDateTime], r15
0x1800257a5  mov     rdi, rdx
0x1800257a8  mov     qword ptr [rsp+8D0h+FileTime.dwLowDateTime], r15
0x1800257ad  mov     [rsp+8D0h+FilePart], r15
0x1800257b2  test    ecx, ecx
0x1800257b4  jz      short loc_1800257DA
0x1800257b6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800257ba  sub     ecx, 1
0x1800257bd  jz      loc_180025A01
0x1800257c3  sub     ecx, 1
0x1800257c6  jz      loc_1800258C9
0x1800257cc  sub     ecx, 1
0x1800257cf  jz      short loc_1800257FB
0x1800257d1  cmp     ecx, 1
0x1800257d4  jz      loc_180025A01
0x1800257da  xor     eax, eax
0x1800257dc  mov     rcx, [rbp+7D0h+var_40]
0x1800257e3  xor     rcx, rsp; StackCookie
0x1800257e6  call    __security_check_cookie
0x1800257eb  add     rsp, 8A8h
0x1800257f2  pop     r15
0x1800257f4  pop     r14
0x1800257f6  pop     rdi
0x1800257f7  pop     rsi
0x1800257f8  pop     rbx
0x1800257f9  pop     rbp
0x1800257fa  retn
0x1800257fb  movzx   edx, word ptr [rdx+32h]; wFatTime
0x1800257ff  lea     r8, [rsp+8D0h+FileTime]; lpFileTime
0x180025804  movzx   ecx, word ptr [rdi+30h]; wFatDate
0x180025808  call    cs:__imp_DosDateTimeToFileTime
0x18002580e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025812  test    eax, eax
0x180025814  jz      short loc_18002584B
0x180025816  lea     rdx, [rsp+8D0h+LastWriteTime]; lpFileTime
0x18002581b  lea     rcx, [rsp+8D0h+FileTime]; lpLocalFileTime
0x180025820  call    cs:__imp_LocalFileTimeToFileTime
0x180025826  test    eax, eax
0x180025828  jz      short loc_18002584B
0x18002582a  mov     ecx, [rdi+28h]; FileHandle
0x18002582d  call    cs:__imp__get_osfhandle
0x180025833  cmp     rax, rbx
0x180025836  jz      short loc_18002584B
0x180025838  lea     r9, [rsp+8D0h+LastWriteTime]; lpLastWriteTime
0x18002583d  xor     r8d, r8d; lpLastAccessTime
0x180025840  xor     edx, edx; lpCreationTime
0x180025842  mov     rcx, rax; hFile
0x180025845  call    cs:__imp_SetFileTime
0x18002584b  mov     r8, [rdi+8]; lpMultiByteStr
0x18002584f  lea     rax, [rbp+7D0h+WideCharStr]
0x180025856  mov     [rsp+8D0h+cchWideChar], 104h; cchWideChar
0x18002585e  mov     r9d, ebx; cbMultiByte
0x180025861  mov     edx, 8; dwFlags
0x180025866  mov     [rsp+8D0h+lpWideCharStr], rax; lpWideCharStr
0x18002586b  mov     ecx, 0FDE9h; CodePage
0x180025870  call    cs:__imp_MultiByteToWideChar
0x180025876  test    eax, eax
0x180025878  jz      short loc_1800258B6
0x18002587a  mov     r9, [r14+10h]
0x18002587e  lea     rax, [rbp+7D0h+WideCharStr]
0x180025885  lea     r8, aSS_0; "%s\\%s"
0x18002588c  mov     [rsp+8D0h+lpWideCharStr], rax
0x180025891  mov     edx, 208h; unsigned __int64
0x180025896  lea     rcx, [rsp+8D0h+FileName]; unsigned __int16 *
0x18002589b  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800258a0  test    eax, eax
0x1800258a2  js      short loc_1800258B6
0x1800258a4  movzx   edx, word ptr [rdi+34h]
0x1800258a8  lea     rcx, [rsp+8D0h+FileName]; lpFileName
0x1800258ad  and     edx, 27h; dwFileAttributes
0x1800258b0  call    cs:__imp_SetFileAttributesW
0x1800258b6  mov     ecx, [rdi+28h]
0x1800258b9  call    cs:__imp__o__close
0x1800258bf  mov     eax, 1
0x1800258c4  jmp     loc_1800257DC
0x1800258c9  mov     r8, [rdx+8]; lpMultiByteStr
0x1800258cd  lea     rax, [rbp+7D0h+WideCharStr]
0x1800258d4  mov     esi, 104h
0x1800258d9  mov     r9d, ebx; cbMultiByte
0x1800258dc  mov     [rsp+8D0h+cchWideChar], esi; cchWideChar
0x1800258e0  mov     edx, 8; dwFlags
0x1800258e5  mov     ecx, 0FDE9h; CodePage
0x1800258ea  mov     [rsp+8D0h+lpWideCharStr], rax; lpWideCharStr
0x1800258ef  call    cs:__imp_MultiByteToWideChar
0x1800258f5  test    eax, eax
0x1800258f7  jz      loc_180025A01
0x1800258fd  mov     r9, [r14+10h]
0x180025901  lea     rax, [rbp+7D0h+WideCharStr]
0x180025908  lea     r8, aSS_0; "%s\\%s"
0x18002590f  mov     [rsp+8D0h+lpWideCharStr], rax
0x180025914  mov     edx, 208h; unsigned __int64
0x180025919  lea     rcx, [rsp+8D0h+FileName]; unsigned __int16 *
0x18002591e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025923  test    eax, eax
0x180025925  js      loc_1800259E3
0x18002592b  lea     r9, [rsp+8D0h+FilePart]; lpFilePart
0x180025930  mov     edx, esi; nBufferLength
0x180025932  lea     r8, [rbp+7D0h+Buffer]; lpBuffer
0x180025939  lea     rcx, [rsp+8D0h+FileName]; lpFileName
0x18002593e  call    cs:__imp_GetFullPathNameW
0x180025944  test    eax, eax
0x180025946  jz      loc_180025A01
0x18002594c  cmp     eax, esi
0x18002594e  jg      loc_180025A01
0x180025954  mov     rcx, [r14+10h]; lpFileName
0x180025958  lea     r9, [rsp+8D0h+FilePart]; lpFilePart
0x18002595d  lea     r8, [rbp+7D0h+String1]; lpBuffer
0x180025964  mov     edx, esi; nBufferLength
0x180025966  call    cs:__imp_GetFullPathNameW
0x18002596c  test    eax, eax
0x18002596e  jz      loc_180025A01
0x180025974  cmp     eax, esi
0x180025976  jg      loc_180025A01
0x18002597c  lea     rax, [rbp+7D0h+String1]
0x180025983  mov     r8, rbx
0x180025986  inc     r8; MaxCount
0x180025989  cmp     [rax+r8*2], r15w
0x18002598e  jnz     short loc_180025986
0x180025990  lea     rcx, [rbp+7D0h+Buffer]
0x180025997  mov     rax, rbx
0x18002599a  inc     rax
0x18002599d  cmp     [rcx+rax*2], r15w
0x1800259a2  jnz     short loc_18002599A
0x1800259a4  cmp     r8, rax
0x1800259a7  ja      short loc_180025A01
0x1800259a9  lea     rdx, [rbp+7D0h+Buffer]; String2
0x1800259b0  lea     rcx, [rbp+7D0h+String1]; String1
0x1800259b7  call    wcsncmp_0
0x1800259bc  test    eax, eax
0x1800259be  jnz     short loc_180025A01
0x1800259c0  lea     rcx, [rsp+8D0h+FileName]; lpPathName
0x1800259c5  call    ?DiagCreatePath@@YAJPEAG@Z; DiagCreatePath(ushort *)
0x1800259ca  test    eax, eax
0x1800259cc  js      short loc_1800259E3
0x1800259ce  xor     r8d, r8d
0x1800259d1  lea     rcx, [rsp+8D0h+FileName]; FileName
0x1800259d6  mov     edx, 8101h; OpenFlag
0x1800259db  call    cs:__imp__wopen
0x1800259e1  mov     ebx, eax
0x1800259e3  mov     rax, [r14]
0x1800259e6  test    rax, rax
0x1800259e9  jz      short loc_1800259F9
0x1800259eb  mov     rdx, [r14+8]
0x1800259ef  lea     rcx, [rsp+8D0h+FileName]
0x1800259f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259f9  movsxd  rax, ebx
0x1800259fc  jmp     loc_1800257DC
0x180025a01  mov     rax, rbx
0x180025a04  jmp     loc_1800257DC
```
