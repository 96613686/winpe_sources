# DeleteOldestLogFiles

- ea: `0x18010c29c`
- end: `0x18010c615`
- name: `DeleteOldestLogFiles`
- size: `889`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005b7e4`

## callees

- `0x180013250`
- `0x180015420`
- `0x1800261e0`
- `0x18004e554`
- `0x180055fc8`
- `0x180059a00`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800ec920`
- `0x18010c29c`
- `0x1801128f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010c4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010c4fd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18010c3d4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18010c3d4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010c47b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010c47b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010c386`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010c386`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010c4d4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010c4d4`

## string_xrefs

- `0x18010c51c`: `Failed to delete oldest backup log.`

## pseudocode

```c
__int64 __fastcall DeleteOldestLogFiles(__int64 a1)
{
  int Property; // eax
  unsigned int v3; // esi
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  HANDLE FirstFileW; // rax
  HANDLE v8; // rbx
  unsigned int v9; // edi
  _OWORD *v10; // rax
  __int64 v11; // rdx
  struct _WIN32_FIND_DATAW *p_FindFileData; // rcx
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  int v25; // eax
  signed int LastError; // ebx
  unsigned int v27; // eax
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  unsigned int v30; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFindFile; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR v32; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v34[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v36[20]; // [rsp+2B0h] [rbp+1B0h] BYREF
  FILETIME FileTime1; // [rsp+2C4h] [rbp+1C4h] BYREF
  _BYTE v38[548]; // [rsp+2DCh] [rbp+1DCh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  lpFileName = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v36, 0, 0x250u);
  v30 = 0;
  Property = OnlineConfigGetProperty(L"NumCBSPersistLogs", &v30);
  v3 = v30;
  if ( Property < 0 )
    v3 = 5;
  v4 = SczAllocFromSz(&lpFileName, a1);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 421;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v4,
      v29);
    goto LABEL_33;
  }
  v4 = SczAllocConcatSz(&lpFileName, L"\\CbsPersist_*.*");
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 422;
    goto LABEL_7;
  }
  while ( 1 )
  {
    hFindFile = 0;
    FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      &hFindFile,
      FirstFileW);
    v8 = hFindFile;
    if ( !hFindFile )
      goto LABEL_30;
    v9 = 0;
    if ( hFindFile == (HANDLE)-1LL )
      goto LABEL_30;
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        if ( !v9 || CompareFileTime(&FileTime1, &FindFileData.ftLastWriteTime) > 0 )
        {
          v10 = v36;
          v11 = 4;
          p_FindFileData = &FindFileData;
          do
          {
            v13 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
            v14 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
            p_FindFileData = (struct _WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
            *v10 = v13;
            v15 = *(_OWORD *)&p_FindFileData[-1].cFileName[226];
            v10[1] = v14;
            v16 = *(_OWORD *)&p_FindFileData[-1].cFileName[234];
            v10[2] = v15;
            v17 = *(_OWORD *)&p_FindFileData[-1].cFileName[242];
            v10[3] = v16;
            v18 = *(_OWORD *)&p_FindFileData[-1].cFileName[250];
            v10[4] = v17;
            v19 = *(_OWORD *)&p_FindFileData[-1].cFileName[258];
            v10[5] = v18;
            v20 = *(_OWORD *)&p_FindFileData[-1].cAlternateFileName[6];
            v10[6] = v19;
            v10[7] = v20;
            v10 += 8;
            --v11;
          }
          while ( v11 );
          v21 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
          *v10 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
          v22 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
          v10[1] = v21;
          v23 = *(_OWORD *)&p_FindFileData->cFileName[2];
          v10[2] = v22;
          v24 = *(_OWORD *)&p_FindFileData->cFileName[10];
          v10[3] = v23;
          v10[4] = v24;
        }
        ++v9;
      }
    }
    while ( FindNextFileW(v8, &FindFileData) );
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
    if ( v9 <= v3 )
      goto LABEL_30;
    v32 = 0;
    v25 = SczAllocFormatted(&v32, L"%ws\\%ws", a1, v38);
    v5 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
        (const char *)(unsigned int)v25,
        v29);
      goto LABEL_32;
    }
    if ( !DeleteFileW(v32) )
      break;
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v32);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to delete oldest backup log.");
    if ( LastError > 0 )
      v27 = (unsigned __int16)LastError | 0x80070000;
    else
      v27 = LastError;
    v30 = v27;
    *(_QWORD *)v34 = &v30;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {0}",
      (__int64)v34);
  }
  if ( !LastError )
  {
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v32);
LABEL_30:
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    return 0;
  }
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x1CF,
         (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
         (const char *)(unsigned int)LastError,
         v29);
LABEL_32:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v32);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
LABEL_33:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  return v5;
}

```

## disassembly

```asm
0x18010c29c  mov     [rsp-8+arg_8], rbx
0x18010c2a1  mov     [rsp-8+arg_10], rsi
0x18010c2a6  push    rbp
0x18010c2a7  push    rdi
0x18010c2a8  push    r14
0x18010c2aa  lea     rbp, [rsp-410h]
0x18010c2b2  sub     rsp, 510h
0x18010c2b9  mov     rax, cs:__security_cookie
0x18010c2c0  xor     rax, rsp
0x18010c2c3  mov     [rbp+420h+var_20], rax
0x18010c2ca  mov     r14, rcx
0x18010c2cd  mov     [rsp+520h+lpFileName], 0
0x18010c2d6  mov     ebx, 250h
0x18010c2db  lea     rcx, [rsp+520h+FindFileData]; void *
0x18010c2e0  mov     r8d, ebx; Size
0x18010c2e3  xor     edx, edx; Val
0x18010c2e5  call    memset_0
0x18010c2ea  mov     r8d, ebx; Size
0x18010c2ed  lea     rcx, [rbp+420h+var_270]; void *
0x18010c2f4  xor     edx, edx; Val
0x18010c2f6  call    memset_0
0x18010c2fb  lea     rdx, [rsp+520h+var_4F0]; unsigned int *
0x18010c300  mov     [rsp+520h+var_4F0], 0
0x18010c308  lea     rcx, aNumcbspersistl; "NumCBSPersistLogs"
0x18010c30f  call    ?OnlineConfigGetProperty@@YAJPEB_WPEAK@Z; OnlineConfigGetProperty(wchar_t const *,ulong *)
0x18010c314  mov     esi, [rsp+520h+var_4F0]
0x18010c318  test    eax, eax
0x18010c31a  mov     ecx, 5
0x18010c31f  mov     rdx, r14
0x18010c322  cmovs   esi, ecx
0x18010c325  lea     rcx, [rsp+520h+lpFileName]
0x18010c32a  call    SczAllocFromSz
0x18010c32f  mov     ebx, eax
0x18010c331  test    eax, eax
0x18010c333  jns     short loc_18010C33C
0x18010c335  mov     edx, 1A5h
0x18010c33a  jmp     short loc_18010C358
0x18010c33c  lea     rdx, aCbspersist; "\\CbsPersist_*.*"
0x18010c343  lea     rcx, [rsp+520h+lpFileName]
0x18010c348  call    SczAllocConcatSz
0x18010c34d  mov     ebx, eax
0x18010c34f  test    eax, eax
0x18010c351  jns     short loc_18010C373
0x18010c353  mov     edx, 1A6h; void *
0x18010c358  mov     rcx, [rbp+428h]; this
0x18010c35f  lea     r8, aOnecoreBaseCbs_88; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x18010c366  mov     r9d, eax; char *
0x18010c369  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010c36e  jmp     loc_18010C607
0x18010c373  mov     rcx, [rsp+520h+lpFileName]; lpFileName
0x18010c378  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x18010c37d  mov     [rsp+520h+hFindFile], 0
0x18010c386  call    cs:__imp_FindFirstFileW
0x18010c38d  nop     dword ptr [rax+rax+00h]
0x18010c392  mov     rdx, rax
0x18010c395  lea     rcx, [rsp+520h+hFindFile]
0x18010c39a  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18010c39f  mov     rbx, [rsp+520h+hFindFile]
0x18010c3a4  test    rbx, rbx
0x18010c3a7  jz      loc_18010C59A
0x18010c3ad  xor     edi, edi
0x18010c3af  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18010c3b3  jz      loc_18010C59A
0x18010c3b9  test    byte ptr [rsp+520h+FindFileData.dwFileAttributes], 10h
0x18010c3be  jnz     loc_18010C473
0x18010c3c4  test    edi, edi
0x18010c3c6  jz      short loc_18010C3E8
0x18010c3c8  lea     rdx, [rsp+520h+FindFileData.ftLastWriteTime]; lpFileTime2
0x18010c3cd  lea     rcx, [rbp+420h+FileTime1]; lpFileTime1
0x18010c3d4  call    cs:__imp_CompareFileTime
0x18010c3db  nop     dword ptr [rax+rax+00h]
0x18010c3e0  test    eax, eax
0x18010c3e2  jle     loc_18010C471
0x18010c3e8  lea     rax, [rbp+420h+var_270]
0x18010c3ef  mov     edx, 4
0x18010c3f4  lea     rcx, [rsp+520h+FindFileData]
0x18010c3f9  movups  xmm0, xmmword ptr [rcx]
0x18010c3fc  movups  xmm1, xmmword ptr [rcx+10h]
0x18010c400  lea     rcx, [rcx+80h]
0x18010c407  movups  xmmword ptr [rax], xmm0
0x18010c40a  movups  xmm0, xmmword ptr [rcx-60h]
0x18010c40e  movups  xmmword ptr [rax+10h], xmm1
0x18010c412  movups  xmm1, xmmword ptr [rcx-50h]
0x18010c416  movups  xmmword ptr [rax+20h], xmm0
0x18010c41a  movups  xmm0, xmmword ptr [rcx-40h]
0x18010c41e  movups  xmmword ptr [rax+30h], xmm1
0x18010c422  movups  xmm1, xmmword ptr [rcx-30h]
0x18010c426  movups  xmmword ptr [rax+40h], xmm0
0x18010c42a  movups  xmm0, xmmword ptr [rcx-20h]
0x18010c42e  movups  xmmword ptr [rax+50h], xmm1
0x18010c432  movups  xmm1, xmmword ptr [rcx-10h]
0x18010c436  movups  xmmword ptr [rax+60h], xmm0
0x18010c43a  movups  xmmword ptr [rax+70h], xmm1
0x18010c43e  lea     rax, [rax+80h]
0x18010c445  sub     rdx, 1
0x18010c449  jnz     short loc_18010C3F9
0x18010c44b  movups  xmm0, xmmword ptr [rcx]
0x18010c44e  movups  xmm1, xmmword ptr [rcx+10h]
0x18010c452  movups  xmmword ptr [rax], xmm0
0x18010c455  movups  xmm0, xmmword ptr [rcx+20h]
0x18010c459  movups  xmmword ptr [rax+10h], xmm1
0x18010c45d  movups  xmm1, xmmword ptr [rcx+30h]
0x18010c461  movups  xmmword ptr [rax+20h], xmm0
0x18010c465  movups  xmm0, xmmword ptr [rcx+40h]
0x18010c469  movups  xmmword ptr [rax+30h], xmm1
0x18010c46d  movups  xmmword ptr [rax+40h], xmm0
0x18010c471  inc     edi
0x18010c473  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x18010c478  mov     rcx, rbx; hFindFile
0x18010c47b  call    cs:__imp_FindNextFileW
0x18010c482  nop     dword ptr [rax+rax+00h]
0x18010c487  test    eax, eax
0x18010c489  jnz     loc_18010C3B9
0x18010c48f  lea     rcx, [rsp+520h+hFindFile]
0x18010c494  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x18010c499  cmp     edi, esi
0x18010c49b  jbe     loc_18010C59A
0x18010c4a1  lea     r9, [rbp+420h+var_244]
0x18010c4a8  mov     [rsp+520h+var_4E0], 0
0x18010c4b1  mov     r8, r14
0x18010c4b4  lea     rdx, aWsWs_4; "%ws\\%ws"
0x18010c4bb  lea     rcx, [rsp+520h+var_4E0]
0x18010c4c0  call    SczAllocFormatted
0x18010c4c5  mov     ebx, eax
0x18010c4c7  test    eax, eax
0x18010c4c9  js      loc_18010C5D8
0x18010c4cf  mov     rcx, [rsp+520h+var_4E0]; lpFileName
0x18010c4d4  call    cs:__imp_DeleteFileW
0x18010c4db  nop     dword ptr [rax+rax+00h]
0x18010c4e0  test    eax, eax
0x18010c4e2  jz      short loc_18010C4FD
0x18010c4e4  lea     rcx, [rsp+520h+var_4E0]
0x18010c4e9  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18010c4ee  lea     rcx, [rsp+520h+hFindFile]
0x18010c4f3  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x18010c4f8  jmp     loc_18010C373
0x18010c4fd  call    cs:__imp_GetLastError
0x18010c504  nop     dword ptr [rax+rax+00h]
0x18010c509  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010c510  mov     ebx, eax
0x18010c512  test    rcx, rcx
0x18010c515  jz      short loc_18010C56D
0x18010c517  mov     edi, 3
0x18010c51c  lea     r9, aFailedToDelete_9; "Failed to delete oldest backup log."
0x18010c523  mov     r8d, edi
0x18010c526  xor     edx, edx
0x18010c528  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010c52d  test    ebx, ebx
0x18010c52f  jg      short loc_18010C535
0x18010c531  mov     eax, ebx
0x18010c533  jmp     short loc_18010C53D
0x18010c535  movzx   eax, bx
0x18010c538  or      eax, 80070000h
0x18010c53d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010c544  lea     r9, a0; ": {0}"
0x18010c54b  mov     [rsp+520h+var_4F0], eax
0x18010c54f  mov     r8d, edi
0x18010c552  lea     rax, [rsp+520h+var_4F0]
0x18010c557  mov     dl, 1
0x18010c559  mov     qword ptr [rsp+520h+var_4D0], rax
0x18010c55e  lea     rax, [rsp+520h+var_4D0]
0x18010c563  mov     qword ptr [rsp+520h+var_500], rax; unsigned int
0x18010c568  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010c56d  test    ebx, ebx
0x18010c56f  jz      short loc_18010C590
0x18010c571  mov     rcx, [rbp+428h]; this
0x18010c578  lea     r8, aOnecoreBaseCbs_88; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x18010c57f  mov     r9d, ebx; char *
0x18010c582  mov     edx, 1CFh; void *
0x18010c587  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010c58c  mov     ebx, eax
0x18010c58e  jmp     short loc_18010C5F3
0x18010c590  lea     rcx, [rsp+520h+var_4E0]
0x18010c595  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18010c59a  lea     rcx, [rsp+520h+hFindFile]
0x18010c59f  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x18010c5a4  lea     rcx, [rsp+520h+lpFileName]
0x18010c5a9  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18010c5ae  xor     eax, eax
0x18010c5b0  mov     rcx, [rbp+420h+var_20]
0x18010c5b7  xor     rcx, rsp; StackCookie
0x18010c5ba  call    __security_check_cookie
0x18010c5bf  lea     r11, [rsp+520h+var_10]
0x18010c5c7  mov     rbx, [r11+28h]
0x18010c5cb  mov     rsi, [r11+30h]
0x18010c5cf  mov     rsp, r11
0x18010c5d2  pop     r14
0x18010c5d4  pop     rdi
0x18010c5d5  pop     rbp
0x18010c5d6  retn
0x18010c5d8  mov     rcx, [rbp+428h]; this
0x18010c5df  lea     r8, aOnecoreBaseCbs_88; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x18010c5e6  mov     r9d, eax; char *
0x18010c5e9  mov     edx, 1CDh; void *
0x18010c5ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010c5f3  lea     rcx, [rsp+520h+var_4E0]
0x18010c5f8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18010c5fd  lea     rcx, [rsp+520h+hFindFile]
0x18010c602  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x18010c607  lea     rcx, [rsp+520h+lpFileName]
0x18010c60c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18010c611  mov     eax, ebx
0x18010c613  jmp     short loc_18010C5B0
```
