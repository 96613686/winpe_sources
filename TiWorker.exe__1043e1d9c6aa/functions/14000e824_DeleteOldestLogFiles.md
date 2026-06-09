# DeleteOldestLogFiles

- ea: `0x14000e824`
- end: `0x14000eb7c`
- name: `DeleteOldestLogFiles`
- size: `856`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000f5b0`

## callees

- `0x140002310`
- `0x140002cf8`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x14000e63c`
- `0x14000e824`
- `0x14000f36c`
- `0x14000f4f0`
- `0x1400177d8`
- `0x140017a88`
- `0x140017ec8`
- `0x140023db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ea6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ea6d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000e90e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000e90e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000ea4a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000ea4a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000e9f7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000e9f7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14000e956`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14000e956`

## string_xrefs

- `0x14000ea86`: `Failed to delete oldest backup log.`

## pseudocode

```c
__int64 __fastcall DeleteOldestLogFiles(__int64 a1)
{
  __int64 v2; // r8
  int Property; // eax
  unsigned int v4; // esi
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  const struct std::nothrow_t *v8; // rdx
  HANDLE FirstFileW; // rax
  HANDLE v10; // rbx
  unsigned int v11; // edi
  _OWORD *v12; // rax
  __int64 v13; // rdx
  _WIN32_FIND_DATAW *p_FindFileData; // rcx
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  int v27; // eax
  const struct std::nothrow_t *v28; // rdx
  const struct std::nothrow_t *v29; // rdx
  signed int LastError; // ebx
  __int64 v31; // rdx
  unsigned int v32; // eax
  const struct std::nothrow_t *v33; // rdx
  const struct std::nothrow_t *v34; // rdx
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFindFile; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR v38; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v40[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v42[20]; // [rsp+2B0h] [rbp+1B0h] BYREF
  FILETIME FileTime1; // [rsp+2C4h] [rbp+1C4h] BYREF
  _BYTE v44[548]; // [rsp+2DCh] [rbp+1DCh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  lpFileName = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v42, 0, 0x250u);
  v36 = 0;
  Property = OnlineConfigGetProperty((wchar_t *)L"NumCBSPersistLogs", &v36, v2);
  v4 = v36;
  if ( Property < 0 )
    v4 = 5;
  v5 = SczAllocFromSz(&lpFileName, a1);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 421;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v5);
    goto LABEL_33;
  }
  v5 = SczAllocConcatSz(&lpFileName, L"\\CbsPersist_*.*");
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 422;
    goto LABEL_7;
  }
  while ( 1 )
  {
    hFindFile = 0;
    FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      &hFindFile,
      FirstFileW);
    v10 = hFindFile;
    if ( !hFindFile )
      goto LABEL_30;
    v11 = 0;
    if ( hFindFile == (HANDLE)-1LL )
      goto LABEL_30;
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        if ( !v11 || CompareFileTime(&FileTime1, &FindFileData.ftLastWriteTime) > 0 )
        {
          v12 = v42;
          v13 = 4;
          p_FindFileData = &FindFileData;
          do
          {
            v15 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
            v16 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
            p_FindFileData = (_WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
            *v12 = v15;
            v17 = *(_OWORD *)&p_FindFileData[-1].cFileName[226];
            v12[1] = v16;
            v18 = *(_OWORD *)&p_FindFileData[-1].cFileName[234];
            v12[2] = v17;
            v19 = *(_OWORD *)&p_FindFileData[-1].cFileName[242];
            v12[3] = v18;
            v20 = *(_OWORD *)&p_FindFileData[-1].cFileName[250];
            v12[4] = v19;
            v21 = *(_OWORD *)&p_FindFileData[-1].cFileName[258];
            v12[5] = v20;
            v22 = *(_OWORD *)&p_FindFileData[-1].cAlternateFileName[6];
            v12[6] = v21;
            v12[7] = v22;
            v12 += 8;
            --v13;
          }
          while ( v13 );
          v23 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
          *v12 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
          v24 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
          v12[1] = v23;
          v25 = *(_OWORD *)&p_FindFileData->cFileName[2];
          v12[2] = v24;
          v26 = *(_OWORD *)&p_FindFileData->cFileName[10];
          v12[3] = v25;
          v12[4] = v26;
        }
        ++v11;
      }
    }
    while ( FindNextFileW(v10, &FindFileData) );
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
    if ( v11 <= v4 )
      goto LABEL_30;
    v38 = 0;
    v27 = SczAllocFormatted(&v38, L"%ws\\%ws", a1, v44);
    v6 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
        (const char *)(unsigned int)v27);
      goto LABEL_32;
    }
    if ( !DeleteFileW(v38) )
      break;
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&v38, v28);
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
      v32 = (unsigned __int16)LastError | 0x80070000;
    else
      v32 = LastError;
    v36 = v32;
    *(_QWORD *)v40 = &v36;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v31,
      3,
      (__int64)": {0}",
      (__int64)v40);
  }
  if ( !LastError )
  {
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&v38, v29);
LABEL_30:
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&lpFileName, v34);
    return 0;
  }
  v6 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x1CF,
         (int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
         (const char *)(unsigned int)LastError);
LABEL_32:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&v38, v33);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
LABEL_33:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&lpFileName, v8);
  return v6;
}

```

## disassembly

```asm
0x14000e824  mov     [rsp-8+arg_8], rbx
0x14000e829  mov     [rsp-8+arg_10], rsi
0x14000e82e  push    rbp
0x14000e82f  push    rdi
0x14000e830  push    r14
0x14000e832  lea     rbp, [rsp-410h]
0x14000e83a  sub     rsp, 510h
0x14000e841  mov     rax, cs:__security_cookie
0x14000e848  xor     rax, rsp
0x14000e84b  mov     [rbp+420h+var_20], rax
0x14000e852  mov     r14, rcx
0x14000e855  mov     [rsp+520h+lpFileName], 0
0x14000e85e  mov     ebx, 250h
0x14000e863  lea     rcx, [rsp+520h+FindFileData]; void *
0x14000e868  mov     r8d, ebx; Size
0x14000e86b  xor     edx, edx; Val
0x14000e86d  call    memset_0
0x14000e872  mov     r8d, ebx; Size
0x14000e875  lea     rcx, [rbp+420h+var_270]; void *
0x14000e87c  xor     edx, edx; Val
0x14000e87e  call    memset_0
0x14000e883  lea     rdx, [rsp+520h+var_4F0]; unsigned int *
0x14000e888  mov     [rsp+520h+var_4F0], 0
0x14000e890  lea     rcx, aNumcbspersistl; "NumCBSPersistLogs"
0x14000e897  call    ?OnlineConfigGetProperty@@YAJPEB_WPEAK@Z; OnlineConfigGetProperty(wchar_t const *,ulong *)
0x14000e89c  mov     esi, [rsp+520h+var_4F0]
0x14000e8a0  test    eax, eax
0x14000e8a2  mov     ecx, 5
0x14000e8a7  mov     rdx, r14
0x14000e8aa  cmovs   esi, ecx
0x14000e8ad  lea     rcx, [rsp+520h+lpFileName]
0x14000e8b2  call    SczAllocFromSz
0x14000e8b7  mov     ebx, eax
0x14000e8b9  test    eax, eax
0x14000e8bb  jns     short loc_14000E8C4
0x14000e8bd  mov     edx, 1A5h
0x14000e8c2  jmp     short loc_14000E8E0
0x14000e8c4  lea     rdx, aCbspersist; "\\CbsPersist_*.*"
0x14000e8cb  lea     rcx, [rsp+520h+lpFileName]
0x14000e8d0  call    SczAllocConcatSz
0x14000e8d5  mov     ebx, eax
0x14000e8d7  test    eax, eax
0x14000e8d9  jns     short loc_14000E8FB
0x14000e8db  mov     edx, 1A6h; void *
0x14000e8e0  mov     rcx, [rbp+428h]; this
0x14000e8e7  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000e8ee  mov     r9d, eax; char *
0x14000e8f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e8f6  jmp     loc_14000EB6E
0x14000e8fb  mov     rcx, [rsp+520h+lpFileName]; lpFileName
0x14000e900  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x14000e905  mov     [rsp+520h+hFindFile], 0
0x14000e90e  call    cs:__imp_FindFirstFileW
0x14000e914  mov     rdx, rax
0x14000e917  lea     rcx, [rsp+520h+hFindFile]
0x14000e91c  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x14000e921  mov     rbx, [rsp+520h+hFindFile]
0x14000e926  test    rbx, rbx
0x14000e929  jz      loc_14000EB02
0x14000e92f  xor     edi, edi
0x14000e931  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000e935  jz      loc_14000EB02
0x14000e93b  test    byte ptr [rsp+520h+FindFileData.dwFileAttributes], 10h
0x14000e940  jnz     loc_14000E9EF
0x14000e946  test    edi, edi
0x14000e948  jz      short loc_14000E964
0x14000e94a  lea     rdx, [rsp+520h+FindFileData.ftLastWriteTime]; lpFileTime2
0x14000e94f  lea     rcx, [rbp+420h+FileTime1]; lpFileTime1
0x14000e956  call    cs:__imp_CompareFileTime
0x14000e95c  test    eax, eax
0x14000e95e  jle     loc_14000E9ED
0x14000e964  lea     rax, [rbp+420h+var_270]
0x14000e96b  mov     edx, 4
0x14000e970  lea     rcx, [rsp+520h+FindFileData]
0x14000e975  movups  xmm0, xmmword ptr [rcx]
0x14000e978  movups  xmm1, xmmword ptr [rcx+10h]
0x14000e97c  lea     rcx, [rcx+80h]
0x14000e983  movups  xmmword ptr [rax], xmm0
0x14000e986  movups  xmm0, xmmword ptr [rcx-60h]
0x14000e98a  movups  xmmword ptr [rax+10h], xmm1
0x14000e98e  movups  xmm1, xmmword ptr [rcx-50h]
0x14000e992  movups  xmmword ptr [rax+20h], xmm0
0x14000e996  movups  xmm0, xmmword ptr [rcx-40h]
0x14000e99a  movups  xmmword ptr [rax+30h], xmm1
0x14000e99e  movups  xmm1, xmmword ptr [rcx-30h]
0x14000e9a2  movups  xmmword ptr [rax+40h], xmm0
0x14000e9a6  movups  xmm0, xmmword ptr [rcx-20h]
0x14000e9aa  movups  xmmword ptr [rax+50h], xmm1
0x14000e9ae  movups  xmm1, xmmword ptr [rcx-10h]
0x14000e9b2  movups  xmmword ptr [rax+60h], xmm0
0x14000e9b6  movups  xmmword ptr [rax+70h], xmm1
0x14000e9ba  lea     rax, [rax+80h]
0x14000e9c1  sub     rdx, 1
0x14000e9c5  jnz     short loc_14000E975
0x14000e9c7  movups  xmm0, xmmword ptr [rcx]
0x14000e9ca  movups  xmm1, xmmword ptr [rcx+10h]
0x14000e9ce  movups  xmmword ptr [rax], xmm0
0x14000e9d1  movups  xmm0, xmmword ptr [rcx+20h]
0x14000e9d5  movups  xmmword ptr [rax+10h], xmm1
0x14000e9d9  movups  xmm1, xmmword ptr [rcx+30h]
0x14000e9dd  movups  xmmword ptr [rax+20h], xmm0
0x14000e9e1  movups  xmm0, xmmword ptr [rcx+40h]
0x14000e9e5  movups  xmmword ptr [rax+30h], xmm1
0x14000e9e9  movups  xmmword ptr [rax+40h], xmm0
0x14000e9ed  inc     edi
0x14000e9ef  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x14000e9f4  mov     rcx, rbx; hFindFile
0x14000e9f7  call    cs:__imp_FindNextFileW
0x14000e9fd  test    eax, eax
0x14000e9ff  jnz     loc_14000E93B
0x14000ea05  lea     rcx, [rsp+520h+hFindFile]
0x14000ea0a  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x14000ea0f  cmp     edi, esi
0x14000ea11  jbe     loc_14000EB02
0x14000ea17  lea     r9, [rbp+420h+var_244]
0x14000ea1e  mov     [rsp+520h+var_4E0], 0
0x14000ea27  mov     r8, r14
0x14000ea2a  lea     rdx, aWsWs; "%ws\\%ws"
0x14000ea31  lea     rcx, [rsp+520h+var_4E0]
0x14000ea36  call    SczAllocFormatted
0x14000ea3b  mov     ebx, eax
0x14000ea3d  test    eax, eax
0x14000ea3f  js      loc_14000EB3F
0x14000ea45  mov     rcx, [rsp+520h+var_4E0]; lpFileName
0x14000ea4a  call    cs:__imp_DeleteFileW
0x14000ea50  test    eax, eax
0x14000ea52  jz      short loc_14000EA6D
0x14000ea54  lea     rcx, [rsp+520h+var_4E0]
0x14000ea59  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000ea5e  lea     rcx, [rsp+520h+hFindFile]
0x14000ea63  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x14000ea68  jmp     loc_14000E8FB
0x14000ea6d  call    cs:__imp_GetLastError
0x14000ea73  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ea7a  mov     ebx, eax
0x14000ea7c  test    rcx, rcx
0x14000ea7f  jz      short loc_14000EAD5
0x14000ea81  mov     edi, 3
0x14000ea86  lea     r9, aFailedToDelete_1; "Failed to delete oldest backup log."
0x14000ea8d  mov     r8d, edi
0x14000ea90  xor     edx, edx
0x14000ea92  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000ea97  test    ebx, ebx
0x14000ea99  jg      short loc_14000EA9F
0x14000ea9b  mov     eax, ebx
0x14000ea9d  jmp     short loc_14000EAA7
0x14000ea9f  movzx   eax, bx
0x14000eaa2  or      eax, 80070000h
0x14000eaa7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000eaae  lea     r9, a0; ": {0}"
0x14000eab5  mov     [rsp+520h+var_4F0], eax
0x14000eab9  mov     r8d, edi
0x14000eabc  lea     rax, [rsp+520h+var_4F0]
0x14000eac1  mov     qword ptr [rsp+520h+var_4D0], rax
0x14000eac6  lea     rax, [rsp+520h+var_4D0]
0x14000eacb  mov     qword ptr [rsp+520h+var_500], rax; unsigned int
0x14000ead0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000ead5  test    ebx, ebx
0x14000ead7  jz      short loc_14000EAF8
0x14000ead9  mov     rcx, [rbp+428h]; this
0x14000eae0  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000eae7  mov     r9d, ebx; char *
0x14000eaea  mov     edx, 1CFh; void *
0x14000eaef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000eaf4  mov     ebx, eax
0x14000eaf6  jmp     short loc_14000EB5A
0x14000eaf8  lea     rcx, [rsp+520h+var_4E0]
0x14000eafd  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000eb02  lea     rcx, [rsp+520h+hFindFile]
0x14000eb07  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x14000eb0c  lea     rcx, [rsp+520h+lpFileName]
0x14000eb11  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000eb16  xor     eax, eax
0x14000eb18  mov     rcx, [rbp+420h+var_20]
0x14000eb1f  xor     rcx, rsp; StackCookie
0x14000eb22  call    __security_check_cookie
0x14000eb27  lea     r11, [rsp+520h+var_10]
0x14000eb2f  mov     rbx, [r11+28h]
0x14000eb33  mov     rsi, [r11+30h]
0x14000eb37  mov     rsp, r11
0x14000eb3a  pop     r14
0x14000eb3c  pop     rdi
0x14000eb3d  pop     rbp
0x14000eb3e  retn
0x14000eb3f  mov     rcx, [rbp+428h]; this
0x14000eb46  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000eb4d  mov     r9d, eax; char *
0x14000eb50  mov     edx, 1CDh; void *
0x14000eb55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000eb5a  lea     rcx, [rsp+520h+var_4E0]
0x14000eb5f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000eb64  lea     rcx, [rsp+520h+hFindFile]
0x14000eb69  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x14000eb6e  lea     rcx, [rsp+520h+lpFileName]
0x14000eb73  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000eb78  mov     eax, ebx
0x14000eb7a  jmp     short loc_14000EB18
```
