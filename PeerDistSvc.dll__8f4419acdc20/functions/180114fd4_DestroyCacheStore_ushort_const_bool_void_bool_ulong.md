# DestroyCacheStore(ushort const *,bool,void *,bool,ulong)

- ea: `0x180114fd4`
- end: `0x180115571`
- name: `?DestroyCacheStore@@YAKPEBG_NPEAX1K@Z`
- size: `1437`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, bool, void *, bool, unsigned int)`
- caller_count: `8`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800429b4`
- `0x180043eb4`
- `0x180049a28`
- `0x18004cde0`
- `0x18004fc38`
- `0x180057cf0`
- `0x180058188`
- `0x180114fd4`

## callees

- `0x1800082d0`
- `0x1800094d4`
- `0x180009ec4`
- `0x18000cf48`
- `0x18000cfc0`
- `0x180018340`
- `0x180114ae0`
- `0x180114fd4`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011534c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801153fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801154cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011534c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801153fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801154cf`
- `KERNEL32!lstrcmpW` at `0x1801151de`
- `KERNEL32!lstrcmpW` at `0x1801151f8`
- `KERNEL32!lstrcmpW` at `0x1801151de`
- `KERNEL32!lstrcmpW` at `0x1801151f8`
- `KERNEL32!FindNextFileW` at `0x1801153f0`
- `KERNEL32!FindNextFileW` at `0x1801153f0`
- `KERNEL32!FindFirstFileExW` at `0x180115161`
- `KERNEL32!FindFirstFileExW` at `0x180115161`
- `KERNEL32!FindClose` at `0x18011553f`
- `KERNEL32!FindClose` at `0x18011553f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18011533e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18011533e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1801154c5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1801154c5`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x180115336`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x180115336`
- `api-ms-win-core-kernel32-legacy-l1-1-3!FindFirstFileTransactedW` at `0x18011514f`
- `api-ms-win-core-kernel32-legacy-l1-1-3!FindFirstFileTransactedW` at `0x18011514f`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x180115429`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x180115429`

## pseudocode

```c
__int64 __fastcall DestroyCacheStore(const unsigned __int16 *a1, char a2, char *a3, bool a4, unsigned int a5)
{
  int v8; // eax
  DWORD appended; // ebx
  CHostedCacheMsgEncoding *v10; // rcx
  int v11; // edx
  WCHAR *v12; // r9
  HANDLE FirstFile; // rax
  void *v14; // r15
  int v15; // eax
  CHostedCacheMsgEncoding *v16; // rcx
  int v17; // edx
  WCHAR *v18; // r9
  BOOL v19; // eax
  BOOL v20; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR PathName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR FileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids);
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v8 = StringCchCopyW(FileName, 0x104u, a1);
  if ( v8 < 0 )
  {
    appended = TnoWin32ErrFromHR(v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return appended;
    }
    v11 = 31;
LABEL_10:
    LODWORD(v12) = (_DWORD)a1;
LABEL_11:
    WPP_SF_Sd(
      *((_QWORD *)v10 + 2),
      v11,
      (unsigned int)WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
      (_DWORD)v12,
      appended);
    return appended;
  }
  appended = AppendFilePath(FileName, L"*");
  if ( appended )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return appended;
    }
    v11 = 32;
    goto LABEL_10;
  }
  if ( (unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    FirstFile = FindFirstFileExW(FileName, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  else
    FirstFile = FindFirstFileTransactedW(FileName, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0, a3);
  v14 = FirstFile;
  if ( FirstFile != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      FindFileData.cFileName[259] = 0;
      if ( lstrcmpW(FindFileData.cFileName, L".") && lstrcmpW(FindFileData.cFileName, L"..") )
      {
        v15 = StringCchCopyW(PathName, 0x104u, a1);
        if ( v15 < 0 )
        {
          appended = TnoWin32ErrFromHR(v15);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            v17 = 34;
            goto LABEL_89;
          }
          goto LABEL_91;
        }
        appended = AppendFilePath(PathName, FindFileData.cFileName);
        if ( appended )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              (unsigned int)WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
              (unsigned int)PathName,
              (__int64)FindFileData.cFileName,
              appended);
          }
          goto LABEL_91;
        }
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( a5 )
          {
            appended = DestroyCacheStore(PathName, 1, a3, a4, a5 - 1);
            if ( appended )
            {
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                goto LABEL_91;
              }
              v17 = 37;
LABEL_42:
              v18 = PathName;
              goto LABEL_90;
            }
          }
          else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              36,
              (unsigned int)WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
              (unsigned int)FindFileData.cFileName,
              0);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids, PathName);
          }
          if ( (unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
            v19 = DeleteFileW(PathName);
          else
            v19 = DeleteFileTransactedW(PathName, a3);
          if ( !v19 )
          {
            appended = GetLastError();
            if ( appended - 2 <= 1 || appended == 5 && a4 || appended == 32 && a4 )
            {
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  39,
                  (unsigned int)WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
                  (unsigned int)PathName,
                  appended);
              }
            }
            else if ( appended )
            {
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                goto LABEL_91;
              }
              v17 = 40;
              goto LABEL_42;
            }
          }
        }
      }
      if ( !FindNextFileW(v14, &FindFileData) )
      {
        appended = GetLastError();
        if ( appended == 18 )
        {
          if ( !a2
            || ((unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFDuLL
              ? (v20 = RemoveDirectoryW(a1))
              : (v20 = RemoveDirectoryTransactedW(a1, a3)),
                v20) )
          {
            appended = 0;
            goto LABEL_91;
          }
          appended = GetLastError();
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            v17 = 42;
            goto LABEL_89;
          }
LABEL_91:
          FindClose(v14);
          return appended;
        }
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_91;
        }
        v17 = 41;
LABEL_89:
        LODWORD(v18) = (_DWORD)a1;
LABEL_90:
        WPP_SF_Sd(
          *((_QWORD *)v16 + 2),
          v17,
          (unsigned int)WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
          (_DWORD)v18,
          appended);
        goto LABEL_91;
      }
    }
  }
  appended = GetLastError();
  if ( appended - 2 <= 1 )
    return 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v11 = 33;
    v12 = FileName;
    goto LABEL_11;
  }
  return appended;
}

```

## disassembly

```asm
0x180114fd4  mov     [rsp-8+arg_8], rbx
0x180114fd9  push    rbp
0x180114fda  push    rsi
0x180114fdb  push    rdi
0x180114fdc  push    r12
0x180114fde  push    r13
0x180114fe0  push    r14
0x180114fe2  push    r15
0x180114fe4  lea     rbp, [rsp-5D0h]
0x180114fec  sub     rsp, 6D0h
0x180114ff3  mov     rax, cs:__security_cookie
0x180114ffa  xor     rax, rsp
0x180114ffd  mov     [rbp+600h+var_40], rax
0x180115004  mov     r12b, r9b
0x180115007  mov     [rsp+700h+var_6C0], dl
0x18011500b  mov     rsi, r8
0x18011500e  mov     rdi, rcx
0x180115011  mov     rcx, cs:WPP_GLOBAL_Control
0x180115018  lea     rax, WPP_GLOBAL_Control
0x18011501f  mov     r13d, 1
0x180115025  cmp     rcx, rax
0x180115028  jz      short loc_18011504D
0x18011502a  test    [rcx+1Ch], r13b
0x18011502e  jz      short loc_18011504D
0x180115030  cmp     byte ptr [rcx+19h], 4
0x180115034  jb      short loc_18011504D
0x180115036  mov     rcx, [rcx+10h]
0x18011503a  lea     edx, [r13+1Dh]
0x18011503e  mov     r9, r8
0x180115041  lea     r8, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids
0x180115048  call    WPP_SF_q
0x18011504d  xor     r15d, r15d
0x180115050  lea     rcx, [rsp+700h+FindFileData]; void *
0x180115055  xor     edx, edx; Val
0x180115057  movzx   r14d, r15b
0x18011505b  mov     r8d, 250h; Size
0x180115061  call    memset_0
0x180115066  lea     rax, [rsi-1]
0x18011506a  mov     r8, rdi; unsigned __int16 *
0x18011506d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180115071  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x180115078  mov     edx, 104h; unsigned __int64
0x18011507d  cmovbe  r14d, r13d
0x180115081  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180115086  test    eax, eax
0x180115088  jns     short loc_1801150DE
0x18011508a  mov     ecx, eax; int
0x18011508c  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180115091  mov     ebx, eax
0x180115093  mov     rcx, cs:WPP_GLOBAL_Control
0x18011509a  lea     rax, WPP_GLOBAL_Control
0x1801150a1  cmp     rcx, rax
0x1801150a4  jz      loc_180115545
0x1801150aa  test    [rcx+1Ch], r13b
0x1801150ae  jz      loc_180115545
0x1801150b4  cmp     [rcx+19h], r13b
0x1801150b8  jb      loc_180115545
0x1801150be  lea     edx, [r15+1Fh]
0x1801150c2  mov     r9, rdi
0x1801150c5  mov     rcx, [rcx+10h]
0x1801150c9  lea     r8, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids
0x1801150d0  mov     dword ptr [rsp+700h+lpSearchFilter], ebx
0x1801150d4  call    WPP_SF_Sd
0x1801150d9  jmp     loc_180115545
0x1801150de  lea     rdx, asc_180174A68; "*"
0x1801150e5  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x1801150ec  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x1801150f1  mov     ebx, eax
0x1801150f3  test    eax, eax
0x1801150f5  jz      short loc_180115129
0x1801150f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801150fe  lea     rax, WPP_GLOBAL_Control
0x180115105  cmp     rcx, rax
0x180115108  jz      loc_180115545
0x18011510e  test    [rcx+1Ch], r13b
0x180115112  jz      loc_180115545
0x180115118  cmp     [rcx+19h], r13b
0x18011511c  jb      loc_180115545
0x180115122  mov     edx, 20h ; ' '
0x180115127  jmp     short loc_1801150C2
0x180115129  xor     r9d, r9d; fSearchOp
0x18011512c  lea     r8, [rsp+700h+FindFileData]; lpFindFileData
0x180115131  lea     rcx, [rbp+600h+FileName]; lpFileName
0x180115138  mov     edx, r13d; fInfoLevelId
0x18011513b  test    r14b, r14b
0x18011513e  jz      short loc_180115157
0x180115140  mov     [rsp+700h+hTransaction], rsi; hTransaction
0x180115145  mov     [rsp+700h+dwAdditionalFlags], r15d; dwAdditionalFlags
0x18011514a  mov     [rsp+700h+lpSearchFilter], r15; lpSearchFilter
0x18011514f  call    cs:__imp_FindFirstFileTransactedW
0x180115155  jmp     short loc_180115167
0x180115157  mov     [rsp+700h+dwAdditionalFlags], r15d; dwAdditionalFlags
0x18011515c  mov     [rsp+700h+lpSearchFilter], r15; lpSearchFilter
0x180115161  call    cs:__imp_FindFirstFileExW
0x180115167  mov     r15, rax
0x18011516a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011516e  jnz     short loc_1801151C2
0x180115170  call    cs:__imp_GetLastError
0x180115176  mov     ebx, eax
0x180115178  add     eax, 0FFFFFFFEh
0x18011517b  cmp     eax, r13d
0x18011517e  jbe     short loc_1801151BB
0x180115180  mov     rcx, cs:WPP_GLOBAL_Control
0x180115187  lea     rax, WPP_GLOBAL_Control
0x18011518e  cmp     rcx, rax
0x180115191  jz      loc_180115545
0x180115197  test    [rcx+1Ch], r13b
0x18011519b  jz      loc_180115545
0x1801151a1  cmp     [rcx+19h], r13b
0x1801151a5  jb      loc_180115545
0x1801151ab  lea     edx, [r15+22h]
0x1801151af  lea     r9, [rbp+600h+FileName]
0x1801151b6  jmp     loc_1801150C5
0x1801151bb  xor     ebx, ebx
0x1801151bd  jmp     loc_180115545
0x1801151c2  mov     r13d, [rbp+600h+arg_20]
0x1801151c9  xor     eax, eax
0x1801151cb  lea     rdx, asc_180174AA4; "."
0x1801151d2  lea     rcx, [rsp+700h+String1]; lpString1
0x1801151d7  mov     [rbp+600h+var_47E], ax
0x1801151de  call    cs:__imp_lstrcmpW
0x1801151e4  test    eax, eax
0x1801151e6  jz      loc_1801153E8
0x1801151ec  lea     rdx, asc_180174AA8; ".."
0x1801151f3  lea     rcx, [rsp+700h+String1]; lpString1
0x1801151f8  call    cs:__imp_lstrcmpW
0x1801151fe  test    eax, eax
0x180115200  jz      loc_1801153E8
0x180115206  mov     r8, rdi; unsigned __int16 *
0x180115209  lea     rcx, [rbp+600h+PathName]; unsigned __int16 *
0x180115210  mov     edx, 104h; unsigned __int64
0x180115215  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18011521a  test    eax, eax
0x18011521c  js      loc_18011548E
0x180115222  lea     rdx, [rsp+700h+String1]; unsigned __int16 *
0x180115227  lea     rcx, [rbp+600h+PathName]; unsigned __int16 *
0x18011522e  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x180115233  mov     ebx, eax
0x180115235  test    eax, eax
0x180115237  jnz     loc_180115434
0x18011523d  test    [rsp+700h+FindFileData], 10h
0x180115242  jz      loc_1801152EC
0x180115248  test    r13d, r13d
0x18011524b  jnz     short loc_18011528A
0x18011524d  mov     rcx, cs:WPP_GLOBAL_Control
0x180115254  lea     rax, WPP_GLOBAL_Control
0x18011525b  cmp     rcx, rax
0x18011525e  jz      loc_1801153E8
0x180115264  test    byte ptr [rcx+1Ch], 1
0x180115268  jz      loc_1801153E8
0x18011526e  cmp     byte ptr [rcx+19h], 4
0x180115272  jb      loc_1801153E8
0x180115278  lea     edx, [rbx+24h]
0x18011527b  mov     dword ptr [rsp+700h+lpSearchFilter], r13d
0x180115280  lea     r9, [rsp+700h+String1]
0x180115285  jmp     loc_1801153D8
0x18011528a  lea     eax, [r13-1]
0x18011528e  mov     r9b, r12b; bool
0x180115291  mov     r8, rsi; void *
0x180115294  mov     dword ptr [rsp+700h+lpSearchFilter], eax; unsigned int
0x180115298  mov     dl, 1; bool
0x18011529a  lea     rcx, [rbp+600h+PathName]; unsigned __int16 *
0x1801152a1  call    ?DestroyCacheStore@@YAKPEBG_NPEAX1K@Z; DestroyCacheStore(ushort const *,bool,void *,bool,ulong)
0x1801152a6  mov     ebx, eax
0x1801152a8  test    eax, eax
0x1801152aa  jz      loc_1801153E8
0x1801152b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801152b7  lea     rax, WPP_GLOBAL_Control
0x1801152be  cmp     rcx, rax
0x1801152c1  jz      loc_18011553C
0x1801152c7  test    byte ptr [rcx+1Ch], 1
0x1801152cb  jz      loc_18011553C
0x1801152d1  cmp     byte ptr [rcx+19h], 1
0x1801152d5  jb      loc_18011553C
0x1801152db  mov     edx, 25h ; '%'
0x1801152e0  lea     r9, [rbp+600h+PathName]
0x1801152e7  jmp     loc_180115528
0x1801152ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1801152f3  lea     rax, WPP_GLOBAL_Control
0x1801152fa  cmp     rcx, rax
0x1801152fd  jz      short loc_180115327
0x1801152ff  test    byte ptr [rcx+1Ch], 1
0x180115303  jz      short loc_180115327
0x180115305  cmp     byte ptr [rcx+19h], 3
0x180115309  jb      short loc_180115327
0x18011530b  mov     rcx, [rcx+10h]
0x18011530f  lea     r9, [rbp+600h+PathName]
0x180115316  mov     edx, 26h ; '&'
0x18011531b  lea     r8, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids
0x180115322  call    WPP_SF_S
0x180115327  lea     rcx, [rbp+600h+PathName]; lpFileName
0x18011532e  test    r14b, r14b
0x180115331  jz      short loc_18011533E
0x180115333  mov     rdx, rsi; hTransaction
0x180115336  call    cs:__imp_DeleteFileTransactedW
0x18011533c  jmp     short loc_180115344
0x18011533e  call    cs:__imp_DeleteFileW
0x180115344  test    eax, eax
0x180115346  jnz     loc_1801153E8
0x18011534c  call    cs:__imp_GetLastError
0x180115352  mov     ebx, eax
0x180115354  add     eax, 0FFFFFFFEh
0x180115357  cmp     eax, 1
0x18011535a  jbe     short loc_1801153A9
0x18011535c  cmp     ebx, 5
0x18011535f  jnz     short loc_180115366
0x180115361  test    r12b, r12b
0x180115364  jnz     short loc_1801153A9
0x180115366  cmp     ebx, 20h ; ' '
0x180115369  jnz     short loc_180115370
0x18011536b  test    r12b, r12b
0x18011536e  jnz     short loc_1801153A9
0x180115370  test    ebx, ebx
0x180115372  jz      short loc_1801153E8
0x180115374  mov     rcx, cs:WPP_GLOBAL_Control
0x18011537b  lea     rax, WPP_GLOBAL_Control
0x180115382  cmp     rcx, rax
0x180115385  jz      loc_18011553C
0x18011538b  test    byte ptr [rcx+1Ch], 1
0x18011538f  jz      loc_18011553C
0x180115395  cmp     byte ptr [rcx+19h], 1
0x180115399  jb      loc_18011553C
0x18011539f  mov     edx, 28h ; '('
0x1801153a4  jmp     loc_1801152E0
0x1801153a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801153b0  lea     rax, WPP_GLOBAL_Control
0x1801153b7  cmp     rcx, rax
0x1801153ba  jz      short loc_1801153E8
0x1801153bc  test    byte ptr [rcx+1Ch], 1
0x1801153c0  jz      short loc_1801153E8
0x1801153c2  cmp     byte ptr [rcx+19h], 4
0x1801153c6  jb      short loc_1801153E8
0x1801153c8  mov     edx, 27h ; '''
0x1801153cd  mov     dword ptr [rsp+700h+lpSearchFilter], ebx
0x1801153d1  lea     r9, [rbp+600h+PathName]
0x1801153d8  mov     rcx, [rcx+10h]
0x1801153dc  lea     r8, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids
0x1801153e3  call    WPP_SF_Sd
0x1801153e8  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x1801153ed  mov     rcx, r15; hFindFile
0x1801153f0  call    cs:__imp_FindNextFileW
0x1801153f6  test    eax, eax
0x1801153f8  jnz     loc_1801151C9
0x1801153fe  call    cs:__imp_GetLastError
0x180115404  mov     ebx, eax
0x180115406  cmp     eax, 12h
0x180115409  jnz     loc_180115501
0x18011540f  cmp     [rsp+700h+var_6C0], 0
0x180115414  jz      loc_1801154FD
0x18011541a  mov     rcx, rdi; lpPathName
0x18011541d  test    r14b, r14b
0x180115420  jz      loc_1801154C5
0x180115426  mov     rdx, rsi; hTransaction
0x180115429  call    cs:__imp_RemoveDirectoryTransactedW
0x18011542f  jmp     loc_1801154CB
0x180115434  mov     rcx, cs:WPP_GLOBAL_Control
0x18011543b  lea     rax, WPP_GLOBAL_Control
0x180115442  cmp     rcx, rax
0x180115445  jz      loc_18011553C
0x18011544b  test    byte ptr [rcx+1Ch], 1
0x18011544f  jz      loc_18011553C
0x180115455  cmp     byte ptr [rcx+19h], 1
0x180115459  jb      loc_18011553C
0x18011545f  mov     rcx, [rcx+10h]
0x180115463  lea     rax, [rsp+700h+String1]
0x180115468  mov     edx, 23h ; '#'
0x18011546d  mov     [rsp+700h+dwAdditionalFlags], ebx
0x180115471  lea     r9, [rbp+600h+PathName]
0x180115478  mov     [rsp+700h+lpSearchFilter], rax
0x18011547d  lea     r8, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids
0x180115484  call    WPP_SF_SSD
0x180115489  jmp     loc_18011553C
0x18011548e  mov     ecx, eax; int
0x180115490  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180115495  mov     ebx, eax
0x180115497  mov     rcx, cs:WPP_GLOBAL_Control
0x18011549e  lea     rax, WPP_GLOBAL_Control
0x1801154a5  cmp     rcx, rax
0x1801154a8  jz      loc_18011553C
0x1801154ae  test    byte ptr [rcx+1Ch], 1
0x1801154b2  jz      loc_18011553C
0x1801154b8  cmp     byte ptr [rcx+19h], 1
0x1801154bc  jb      short loc_18011553C
0x1801154be  mov     edx, 22h ; '"'
0x1801154c3  jmp     short loc_180115525
0x1801154c5  call    cs:__imp_RemoveDirectoryW
0x1801154cb  test    eax, eax
0x1801154cd  jnz     short loc_1801154FD
0x1801154cf  call    cs:__imp_GetLastError
0x1801154d5  mov     ebx, eax
0x1801154d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801154de  lea     rax, WPP_GLOBAL_Control
0x1801154e5  cmp     rcx, rax
0x1801154e8  jz      short loc_18011553C
0x1801154ea  test    byte ptr [rcx+1Ch], 1
0x1801154ee  jz      short loc_18011553C
0x1801154f0  cmp     byte ptr [rcx+19h], 1
0x1801154f4  jb      short loc_18011553C
0x1801154f6  mov     edx, 2Ah ; '*'
0x1801154fb  jmp     short loc_180115525
  ... truncated ...
```
