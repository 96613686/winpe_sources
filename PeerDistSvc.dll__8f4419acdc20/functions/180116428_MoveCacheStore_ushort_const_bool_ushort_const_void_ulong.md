# MoveCacheStore(ushort const *,bool,ushort const *,void *,ulong)

- ea: `0x180116428`
- end: `0x180116a85`
- name: `?MoveCacheStore@@YAKPEBG_N0PEAXK@Z`
- size: `1629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char, const unsigned __int16 *, char *, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180037df4`
- `0x18004a140`
- `0x180116428`

## callees

- `0x1800082d0`
- `0x1800094d4`
- `0x180009ec4`
- `0x18000cf48`
- `0x18000cfc0`
- `0x180018340`
- `0x180114ae0`
- `0x180116428`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801165ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801166f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801169e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801165ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801166f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801169e3`
- `KERNEL32!lstrcmpW` at `0x18011661e`
- `KERNEL32!lstrcmpW` at `0x180116638`
- `KERNEL32!lstrcmpW` at `0x18011661e`
- `KERNEL32!lstrcmpW` at `0x180116638`
- `KERNEL32!FindNextFileW` at `0x180116805`
- `KERNEL32!FindNextFileW` at `0x180116805`
- `KERNEL32!FindFirstFileExW` at `0x1801165ab`
- `KERNEL32!FindFirstFileExW` at `0x1801165ab`
- `KERNEL32!FindClose` at `0x180116a53`
- `KERNEL32!FindClose` at `0x180116a53`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801166ed`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801166ed`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1801169d9`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1801169d9`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1801167ef`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1801167ef`
- `api-ms-win-core-kernel32-legacy-l1-1-3!MoveFileTransactedW` at `0x1801167e1`
- `api-ms-win-core-kernel32-legacy-l1-1-3!MoveFileTransactedW` at `0x1801167e1`
- `api-ms-win-core-kernel32-legacy-l1-1-3!FindFirstFileTransactedW` at `0x180116592`
- `api-ms-win-core-kernel32-legacy-l1-1-3!FindFirstFileTransactedW` at `0x180116592`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x18011683e`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x18011683e`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x1801166dc`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x1801166dc`

## pseudocode

```c
__int64 __fastcall MoveCacheStore(
        const unsigned __int16 *a1,
        char a2,
        const unsigned __int16 *a3,
        char *a4,
        unsigned int a5)
{
  int v8; // eax
  unsigned int appended; // eax
  DWORD LastError; // ebx
  CHostedCacheMsgEncoding *v11; // rcx
  int v12; // edx
  HANDLE FirstFile; // rax
  void *v14; // r12
  int v15; // eax
  int v16; // eax
  BOOL DirectoryW; // eax
  BOOL v18; // eax
  BOOL v19; // eax
  CHostedCacheMsgEncoding *v20; // rcx
  int v21; // edx
  WCHAR *v22; // r9
  CHostedCacheMsgEncoding *v23; // rcx
  int v24; // edx
  WCHAR *cFileName; // rax
  WCHAR *v26; // r9
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR NewDirectory[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR FileName[264]; // [rsp+6C0h] [rbp+5C0h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids);
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v8 = StringCchCopyW(FileName, 0x104u, a1);
  if ( v8 < 0 )
  {
    appended = TnoWin32ErrFromHR(v8);
    LastError = appended;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return LastError;
    }
    v12 = 44;
    goto LABEL_10;
  }
  appended = AppendFilePath(FileName, L"*");
  LastError = appended;
  if ( appended )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return LastError;
    }
    v12 = 45;
LABEL_10:
    WPP_SF_Sd(
      *((_QWORD *)v11 + 2),
      v12,
      (unsigned int)WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
      (_DWORD)a1,
      appended);
    return LastError;
  }
  if ( (unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    FirstFile = FindFirstFileExW(FileName, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  else
    FirstFile = FindFirstFileTransactedW(FileName, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0, a4);
  v14 = FirstFile;
  if ( FirstFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        (unsigned int)WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
        (unsigned int)FileName,
        LastError);
    }
    return LastError;
  }
  do
  {
    FindFileData.cFileName[259] = 0;
    if ( lstrcmpW(FindFileData.cFileName, L".") && lstrcmpW(FindFileData.cFileName, L"..") )
    {
      v15 = StringCchCopyW(ExistingFileName, 0x104u, a1);
      if ( v15 < 0 )
      {
        LastError = TnoWin32ErrFromHR(v15);
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_96;
        }
        v21 = 47;
        goto LABEL_94;
      }
      LastError = AppendFilePath(ExistingFileName, FindFileData.cFileName);
      if ( LastError )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_96;
        }
        v24 = 48;
        cFileName = FindFileData.cFileName;
LABEL_77:
        v26 = ExistingFileName;
LABEL_78:
        WPP_SF_SSD(
          *((_QWORD *)v23 + 2),
          v24,
          (unsigned int)WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
          (_DWORD)v26,
          (__int64)cFileName,
          LastError);
        goto LABEL_96;
      }
      v16 = StringCchCopyW(NewDirectory, 0x104u, a3);
      if ( v16 < 0 )
      {
        LastError = TnoWin32ErrFromHR(v16);
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_96;
        }
        v21 = 49;
        LODWORD(v22) = (_DWORD)a3;
LABEL_95:
        WPP_SF_Sd(
          *((_QWORD *)v20 + 2),
          v21,
          (unsigned int)WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
          (_DWORD)v22,
          LastError);
        goto LABEL_96;
      }
      LastError = AppendFilePath(NewDirectory, FindFileData.cFileName);
      if ( LastError )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_96;
        }
        v24 = 50;
        cFileName = FindFileData.cFileName;
        v26 = NewDirectory;
        goto LABEL_78;
      }
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        if ( a5 )
        {
          if ( (unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
            DirectoryW = CreateDirectoryW(NewDirectory, 0);
          else
            DirectoryW = CreateDirectoryTransactedW(0, NewDirectory, 0, a4);
          if ( !DirectoryW )
          {
            LastError = GetLastError();
            if ( LastError == 183 )
            {
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  51,
                  (unsigned int)WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
                  (unsigned int)NewDirectory,
                  183);
              }
            }
            else if ( LastError )
            {
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
              {
                goto LABEL_96;
              }
              v21 = 52;
              v22 = NewDirectory;
              goto LABEL_95;
            }
          }
          LastError = MoveCacheStore(ExistingFileName, 1, NewDirectory, a4, a5 - 1);
          if ( LastError )
            goto LABEL_96;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
            ExistingFileName);
        }
        if ( (unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          v18 = MoveFileExW(ExistingFileName, NewDirectory, 2u);
        else
          v18 = MoveFileTransactedW(ExistingFileName, NewDirectory, 0, 0, 2u, a4);
        if ( !v18 )
        {
          LastError = GetLastError();
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            v24 = 54;
            cFileName = NewDirectory;
            goto LABEL_77;
          }
          goto LABEL_96;
        }
      }
    }
  }
  while ( FindNextFileW(v14, &FindFileData) );
  LastError = GetLastError();
  if ( LastError != 18 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_96;
    }
    v21 = 55;
LABEL_94:
    LODWORD(v22) = (_DWORD)a1;
    goto LABEL_95;
  }
  if ( !a2
    || ((unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL
      ? (v19 = RemoveDirectoryW(a1))
      : (v19 = RemoveDirectoryTransactedW(a1, a4)),
        v19) )
  {
    LastError = 0;
    goto LABEL_96;
  }
  LastError = GetLastError();
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v21 = 56;
    goto LABEL_94;
  }
LABEL_96:
  FindClose(v14);
  return LastError;
}

```

## disassembly

```asm
0x180116428  mov     [rsp-8+arg_8], rbx
0x18011642d  push    rbp
0x18011642e  push    rsi
0x18011642f  push    rdi
0x180116430  push    r12
0x180116432  push    r13
0x180116434  push    r14
0x180116436  push    r15
0x180116438  lea     rbp, [rsp-7E0h]
0x180116440  sub     rsp, 8E0h
0x180116447  mov     rax, cs:__security_cookie
0x18011644e  xor     rax, rsp
0x180116451  mov     [rbp+810h+var_40], rax
0x180116458  mov     rsi, r9
0x18011645b  mov     [rsp+910h+var_8D0], dl
0x18011645f  mov     r13, r8
0x180116462  mov     rdi, rcx
0x180116465  mov     rcx, cs:WPP_GLOBAL_Control
0x18011646c  lea     r12, WPP_GLOBAL_Control
0x180116473  mov     r15d, 1
0x180116479  cmp     rcx, r12
0x18011647c  jz      short loc_18011649E
0x18011647e  test    [rcx+1Ch], r15b
0x180116482  jz      short loc_18011649E
0x180116484  cmp     byte ptr [rcx+19h], 4
0x180116488  jb      short loc_18011649E
0x18011648a  mov     rcx, [rcx+10h]
0x18011648e  lea     edx, [r15+2Ah]
0x180116492  lea     r8, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids
0x180116499  call    WPP_SF_q
0x18011649e  xor     edx, edx; Val
0x1801164a0  lea     rcx, [rsp+910h+FindFileData]; void *
0x1801164a5  mov     r8d, 250h; Size
0x1801164ab  xor     bl, bl
0x1801164ad  call    memset_0
0x1801164b2  lea     rax, [rsi-1]
0x1801164b6  movzx   r14d, bl
0x1801164ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801164be  lea     rcx, [rbp+810h+FileName]; unsigned __int16 *
0x1801164c5  mov     r8, rdi; unsigned __int16 *
0x1801164c8  mov     edx, 104h; unsigned __int64
0x1801164cd  cmovbe  r14d, r15d
0x1801164d1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801164d6  test    eax, eax
0x1801164d8  jns     short loc_180116528
0x1801164da  mov     ecx, eax; int
0x1801164dc  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x1801164e1  mov     ebx, eax
0x1801164e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801164ea  cmp     rcx, r12
0x1801164ed  jz      loc_180116A59
0x1801164f3  test    [rcx+1Ch], r15b
0x1801164f7  jz      loc_180116A59
0x1801164fd  cmp     [rcx+19h], r15b
0x180116501  jb      loc_180116A59
0x180116507  mov     edx, 2Ch ; ','
0x18011650c  mov     dword ptr [rsp+910h+lpSearchFilter], eax
0x180116510  mov     r9, rdi
0x180116513  mov     rcx, [rcx+10h]
0x180116517  lea     r8, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids
0x18011651e  call    WPP_SF_Sd
0x180116523  jmp     loc_180116A59
0x180116528  lea     rdx, asc_180174A68; "*"
0x18011652f  lea     rcx, [rbp+810h+FileName]; unsigned __int16 *
0x180116536  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x18011653b  mov     ebx, eax
0x18011653d  test    eax, eax
0x18011653f  jz      short loc_18011656C
0x180116541  mov     rcx, cs:WPP_GLOBAL_Control
0x180116548  cmp     rcx, r12
0x18011654b  jz      loc_180116A59
0x180116551  test    [rcx+1Ch], r15b
0x180116555  jz      loc_180116A59
0x18011655b  cmp     [rcx+19h], r15b
0x18011655f  jb      loc_180116A59
0x180116565  mov     edx, 2Dh ; '-'
0x18011656a  jmp     short loc_18011650C
0x18011656c  xor     r9d, r9d; fSearchOp
0x18011656f  lea     r8, [rsp+910h+FindFileData]; lpFindFileData
0x180116574  lea     rcx, [rbp+810h+FileName]; lpFileName
0x18011657b  mov     edx, r15d; fInfoLevelId
0x18011657e  test    r14b, r14b
0x180116581  jz      short loc_18011659A
0x180116583  mov     [rsp+910h+hTransaction], rsi; hTransaction
0x180116588  mov     [rsp+910h+dwAdditionalFlags], r9d; dwAdditionalFlags
0x18011658d  mov     [rsp+910h+lpSearchFilter], r9; lpSearchFilter
0x180116592  call    cs:__imp_FindFirstFileTransactedW
0x180116598  jmp     short loc_1801165B1
0x18011659a  mov     [rsp+910h+dwAdditionalFlags], 0; dwAdditionalFlags
0x1801165a2  mov     [rsp+910h+lpSearchFilter], 0; lpSearchFilter
0x1801165ab  call    cs:__imp_FindFirstFileExW
0x1801165b1  mov     r12, rax
0x1801165b4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801165b8  jnz     short loc_180116602
0x1801165ba  call    cs:__imp_GetLastError
0x1801165c0  mov     ebx, eax
0x1801165c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801165c9  lea     rax, WPP_GLOBAL_Control
0x1801165d0  cmp     rcx, rax
0x1801165d3  jz      loc_180116A59
0x1801165d9  test    [rcx+1Ch], r15b
0x1801165dd  jz      loc_180116A59
0x1801165e3  cmp     [rcx+19h], r15b
0x1801165e7  jb      loc_180116A59
0x1801165ed  lea     edx, [r12+2Fh]
0x1801165f2  mov     dword ptr [rsp+910h+lpSearchFilter], ebx
0x1801165f6  lea     r9, [rbp+810h+FileName]
0x1801165fd  jmp     loc_180116513
0x180116602  mov     r15d, [rbp+810h+arg_20]
0x180116609  xor     eax, eax
0x18011660b  lea     rdx, asc_180174AA4; "."
0x180116612  lea     rcx, [rsp+910h+String1]; lpString1
0x180116617  mov     [rbp+810h+var_68E], ax
0x18011661e  call    cs:__imp_lstrcmpW
0x180116624  test    eax, eax
0x180116626  jz      loc_1801167FD
0x18011662c  lea     rdx, asc_180174AA8; ".."
0x180116633  lea     rcx, [rsp+910h+String1]; lpString1
0x180116638  call    cs:__imp_lstrcmpW
0x18011663e  test    eax, eax
0x180116640  jz      loc_1801167FD
0x180116646  mov     r8, rdi; unsigned __int16 *
0x180116649  lea     rcx, [rbp+810h+ExistingFileName]; unsigned __int16 *
0x180116650  mov     edx, 104h; unsigned __int64
0x180116655  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18011665a  test    eax, eax
0x18011665c  js      loc_1801169A2
0x180116662  lea     rdx, [rsp+910h+String1]; unsigned __int16 *
0x180116667  lea     rcx, [rbp+810h+ExistingFileName]; unsigned __int16 *
0x18011666e  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x180116673  mov     ebx, eax
0x180116675  test    eax, eax
0x180116677  jnz     loc_180116948
0x18011667d  mov     r8, r13; unsigned __int16 *
0x180116680  lea     rcx, [rbp+810h+NewDirectory]; unsigned __int16 *
0x180116687  mov     edx, 104h; unsigned __int64
0x18011668c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180116691  test    eax, eax
0x180116693  js      loc_180116907
0x180116699  lea     rdx, [rsp+910h+String1]; unsigned __int16 *
0x18011669e  lea     rcx, [rbp+810h+NewDirectory]; unsigned __int16 *
0x1801166a5  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x1801166aa  mov     ebx, eax
0x1801166ac  test    eax, eax
0x1801166ae  jnz     loc_1801168C9
0x1801166b4  test    [rsp+910h+FindFileData], 10h
0x1801166b9  jz      loc_180116780
0x1801166bf  test    r15d, r15d
0x1801166c2  jz      loc_1801167FD
0x1801166c8  test    r14b, r14b
0x1801166cb  jz      short loc_1801166E4
0x1801166cd  mov     r9, rsi; hTransaction
0x1801166d0  lea     rdx, [rbp+810h+NewDirectory]; lpNewDirectory
0x1801166d7  xor     r8d, r8d; lpSecurityAttributes
0x1801166da  xor     ecx, ecx; lpTemplateDirectory
0x1801166dc  call    cs:__imp_CreateDirectoryTransactedW
0x1801166e2  jmp     short loc_1801166F3
0x1801166e4  xor     edx, edx; lpSecurityAttributes
0x1801166e6  lea     rcx, [rbp+810h+NewDirectory]; lpPathName
0x1801166ed  call    cs:__imp_CreateDirectoryW
0x1801166f3  test    eax, eax
0x1801166f5  jnz     short loc_180116754
0x1801166f7  call    cs:__imp_GetLastError
0x1801166fd  mov     r8d, 0B7h
0x180116703  mov     ebx, eax
0x180116705  cmp     eax, r8d
0x180116708  jnz     short loc_18011674C
0x18011670a  mov     rcx, cs:WPP_GLOBAL_Control
0x180116711  lea     rax, WPP_GLOBAL_Control
0x180116718  cmp     rcx, rax
0x18011671b  jz      short loc_180116754
0x18011671d  test    byte ptr [rcx+1Ch], 1
0x180116721  jz      short loc_180116754
0x180116723  cmp     byte ptr [rcx+19h], 4
0x180116727  jb      short loc_180116754
0x180116729  mov     rcx, [rcx+10h]
0x18011672d  lea     r9, [rbp+810h+NewDirectory]
0x180116734  mov     dword ptr [rsp+910h+lpSearchFilter], r8d
0x180116739  mov     edx, 33h ; '3'
0x18011673e  lea     r8, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids
0x180116745  call    WPP_SF_Sd
0x18011674a  jmp     short loc_180116754
0x18011674c  test    ebx, ebx
0x18011674e  jnz     loc_180116849
0x180116754  lea     eax, [r15-1]
0x180116758  mov     r9, rsi; void *
0x18011675b  lea     r8, [rbp+810h+NewDirectory]; unsigned __int16 *
0x180116762  mov     dword ptr [rsp+910h+lpSearchFilter], eax; unsigned int
0x180116766  mov     dl, 1; bool
0x180116768  lea     rcx, [rbp+810h+ExistingFileName]; unsigned __int16 *
0x18011676f  call    ?MoveCacheStore@@YAKPEBG_N0PEAXK@Z; MoveCacheStore(ushort const *,bool,ushort const *,void *,ulong)
0x180116774  mov     ebx, eax
0x180116776  test    eax, eax
0x180116778  jnz     loc_180116A50
0x18011677e  jmp     short loc_1801167FD
0x180116780  mov     rcx, cs:WPP_GLOBAL_Control
0x180116787  lea     rax, WPP_GLOBAL_Control
0x18011678e  cmp     rcx, rax
0x180116791  jz      short loc_1801167BB
0x180116793  test    byte ptr [rcx+1Ch], 1
0x180116797  jz      short loc_1801167BB
0x180116799  cmp     byte ptr [rcx+19h], 3
0x18011679d  jb      short loc_1801167BB
0x18011679f  mov     rcx, [rcx+10h]
0x1801167a3  lea     r9, [rbp+810h+ExistingFileName]
0x1801167aa  mov     edx, 35h ; '5'
0x1801167af  lea     r8, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids
0x1801167b6  call    WPP_SF_S
0x1801167bb  lea     rdx, [rbp+810h+NewDirectory]; lpNewFileName
0x1801167c2  lea     rcx, [rbp+810h+ExistingFileName]; lpExistingFileName
0x1801167c9  test    r14b, r14b
0x1801167cc  jz      short loc_1801167E9
0x1801167ce  mov     qword ptr [rsp+910h+dwAdditionalFlags], rsi; hTransaction
0x1801167d3  xor     r9d, r9d; lpData
0x1801167d6  xor     r8d, r8d; lpProgressRoutine
0x1801167d9  mov     dword ptr [rsp+910h+lpSearchFilter], 2; dwFlags
0x1801167e1  call    cs:__imp_MoveFileTransactedW
0x1801167e7  jmp     short loc_1801167F5
0x1801167e9  mov     r8d, 2; dwFlags
0x1801167ef  call    cs:__imp_MoveFileExW
0x1801167f5  test    eax, eax
0x1801167f7  jz      loc_180116885
0x1801167fd  lea     rdx, [rsp+910h+FindFileData]; lpFindFileData
0x180116802  mov     rcx, r12; hFindFile
0x180116805  call    cs:__imp_FindNextFileW
0x18011680b  test    eax, eax
0x18011680d  jnz     loc_180116609
0x180116813  call    cs:__imp_GetLastError
0x180116819  mov     ebx, eax
0x18011681b  cmp     eax, 12h
0x18011681e  jnz     loc_180116A15
0x180116824  cmp     [rsp+910h+var_8D0], 0
0x180116829  jz      loc_180116A11
0x18011682f  mov     rcx, rdi; lpPathName
0x180116832  test    r14b, r14b
0x180116835  jz      loc_1801169D9
0x18011683b  mov     rdx, rsi; hTransaction
0x18011683e  call    cs:__imp_RemoveDirectoryTransactedW
0x180116844  jmp     loc_1801169DF
0x180116849  mov     rcx, cs:WPP_GLOBAL_Control
0x180116850  lea     rax, WPP_GLOBAL_Control
0x180116857  cmp     rcx, rax
0x18011685a  jz      loc_180116A50
0x180116860  test    byte ptr [rcx+1Ch], 1
0x180116864  jz      loc_180116A50
0x18011686a  cmp     byte ptr [rcx+19h], 4
0x18011686e  jb      loc_180116A50
0x180116874  mov     edx, 34h ; '4'
0x180116879  lea     r9, [rbp+810h+NewDirectory]
0x180116880  jmp     loc_180116A3C
0x180116885  call    cs:__imp_GetLastError
0x18011688b  mov     ebx, eax
0x18011688d  mov     rcx, cs:WPP_GLOBAL_Control
0x180116894  lea     rax, WPP_GLOBAL_Control
0x18011689b  cmp     rcx, rax
0x18011689e  jz      loc_180116A50
0x1801168a4  test    byte ptr [rcx+1Ch], 1
0x1801168a8  jz      loc_180116A50
0x1801168ae  cmp     byte ptr [rcx+19h], 1
0x1801168b2  jb      loc_180116A50
0x1801168b8  mov     edx, 36h ; '6'
0x1801168bd  lea     rax, [rbp+810h+NewDirectory]
0x1801168c4  jmp     loc_18011697D
0x1801168c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801168d0  lea     rax, WPP_GLOBAL_Control
0x1801168d7  cmp     rcx, rax
0x1801168da  jz      loc_180116A50
0x1801168e0  test    byte ptr [rcx+1Ch], 1
0x1801168e4  jz      loc_180116A50
0x1801168ea  cmp     byte ptr [rcx+19h], 1
0x1801168ee  jb      loc_180116A50
0x1801168f4  mov     edx, 32h ; '2'
0x1801168f9  lea     rax, [rsp+910h+String1]
0x1801168fe  lea     r9, [rbp+810h+NewDirectory]
0x180116905  jmp     short loc_180116984
0x180116907  mov     ecx, eax; int
0x180116909  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x18011690e  mov     ebx, eax
0x180116910  mov     rcx, cs:WPP_GLOBAL_Control
0x180116917  lea     rax, WPP_GLOBAL_Control
0x18011691e  cmp     rcx, rax
0x180116921  jz      loc_180116A50
0x180116927  test    byte ptr [rcx+1Ch], 1
0x18011692b  jz      loc_180116A50
0x180116931  cmp     byte ptr [rcx+19h], 1
0x180116935  jb      loc_180116A50
0x18011693b  mov     edx, 31h ; '1'
0x180116940  mov     r9, r13
0x180116943  jmp     loc_180116A3C
0x180116948  mov     rcx, cs:WPP_GLOBAL_Control
0x18011694f  lea     rax, WPP_GLOBAL_Control
0x180116956  cmp     rcx, rax
0x180116959  jz      loc_180116A50
0x18011695f  test    byte ptr [rcx+1Ch], 1
0x180116963  jz      loc_180116A50
0x180116969  cmp     byte ptr [rcx+19h], 1
0x18011696d  jb      loc_180116A50
0x180116973  mov     edx, 30h ; '0'
0x180116978  lea     rax, [rsp+910h+String1]
0x18011697d  lea     r9, [rbp+810h+ExistingFileName]
  ... truncated ...
```
