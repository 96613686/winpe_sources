# DeleteOldestLogFiles

- ea: `0x1400178b8`
- end: `0x140017c10`
- name: `DeleteOldestLogFiles`
- size: `856`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140018630`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016fb4`
- `0x1400177e0`
- `0x1400178b8`
- `0x1400184fc`
- `0x140018574`
- `0x14001cd14`
- `0x14001cfc4`
- `0x14001d404`
- `0x140020f38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017b01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017b01`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140017ade`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140017ade`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1400179ea`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1400179ea`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140017a8b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140017a8b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1400179a2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1400179a2`

## string_xrefs

- `0x140017b1a`: `Failed to delete oldest backup log.`

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
  _WIN32_FIND_DATAW *p_FindFileData; // rcx
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
  int v27; // edx
  unsigned int v28; // eax
  unsigned int v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFindFile; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR v33; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v35[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[20]; // [rsp+2B0h] [rbp+1B0h] BYREF
  FILETIME FileTime1; // [rsp+2C4h] [rbp+1C4h] BYREF
  _BYTE v39[548]; // [rsp+2DCh] [rbp+1DCh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  lpFileName = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v37, 0, 0x250u);
  v31 = 0;
  Property = OnlineConfigGetProperty(L"NumCBSPersistLogs", &v31);
  v3 = v31;
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
      v30);
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
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::TakeOwnership(
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
          v10 = v37;
          v11 = 4;
          p_FindFileData = &FindFileData;
          do
          {
            v13 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
            v14 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
            p_FindFileData = (_WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
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
    v33 = 0;
    v25 = SczAllocFormatted(&v33, L"%ws\\%ws", a1, v39);
    v5 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
        (const char *)(unsigned int)v25,
        v30);
      goto LABEL_32;
    }
    if ( !DeleteFileW(v33) )
      break;
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v33);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to delete oldest backup log.");
    if ( LastError > 0 )
      v28 = (unsigned __int16)LastError | 0x80070000;
    else
      v28 = LastError;
    v31 = v28;
    *(_QWORD *)v35 = &v31;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v27,
      3,
      (unsigned int)": {0}",
      (__int64)v35);
  }
  if ( !LastError )
  {
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v33);
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
         v30);
LABEL_32:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v33);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
LABEL_33:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  return v5;
}

```

## disassembly

```asm
0x1400178b8  mov     [rsp-8+arg_8], rbx
0x1400178bd  mov     [rsp-8+arg_10], rsi
0x1400178c2  push    rbp
0x1400178c3  push    rdi
0x1400178c4  push    r14
0x1400178c6  lea     rbp, [rsp-410h]
0x1400178ce  sub     rsp, 510h
0x1400178d5  mov     rax, cs:__security_cookie
0x1400178dc  xor     rax, rsp
0x1400178df  mov     [rbp+420h+var_20], rax
0x1400178e6  mov     r14, rcx
0x1400178e9  mov     [rsp+520h+lpFileName], 0
0x1400178f2  mov     ebx, 250h
0x1400178f7  lea     rcx, [rsp+520h+FindFileData]; void *
0x1400178fc  mov     r8d, ebx; Size
0x1400178ff  xor     edx, edx; Val
0x140017901  call    memset_0
0x140017906  mov     r8d, ebx; Size
0x140017909  lea     rcx, [rbp+420h+var_270]; void *
0x140017910  xor     edx, edx; Val
0x140017912  call    memset_0
0x140017917  lea     rdx, [rsp+520h+var_4F0]; unsigned int *
0x14001791c  mov     [rsp+520h+var_4F0], 0
0x140017924  lea     rcx, aNumcbspersistl; "NumCBSPersistLogs"
0x14001792b  call    ?OnlineConfigGetProperty@@YAJPEB_WPEAK@Z; OnlineConfigGetProperty(wchar_t const *,ulong *)
0x140017930  mov     esi, [rsp+520h+var_4F0]
0x140017934  test    eax, eax
0x140017936  mov     ecx, 5
0x14001793b  mov     rdx, r14
0x14001793e  cmovs   esi, ecx
0x140017941  lea     rcx, [rsp+520h+lpFileName]
0x140017946  call    SczAllocFromSz
0x14001794b  mov     ebx, eax
0x14001794d  test    eax, eax
0x14001794f  jns     short loc_140017958
0x140017951  mov     edx, 1A5h
0x140017956  jmp     short loc_140017974
0x140017958  lea     rdx, aCbspersist; "\\CbsPersist_*.*"
0x14001795f  lea     rcx, [rsp+520h+lpFileName]
0x140017964  call    SczAllocConcatSz
0x140017969  mov     ebx, eax
0x14001796b  test    eax, eax
0x14001796d  jns     short loc_14001798F
0x14001796f  mov     edx, 1A6h; void *
0x140017974  mov     rcx, [rbp+428h]; this
0x14001797b  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140017982  mov     r9d, eax; char *
0x140017985  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001798a  jmp     loc_140017C02
0x14001798f  mov     rcx, [rsp+520h+lpFileName]; lpFileName
0x140017994  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x140017999  mov     [rsp+520h+hFindFile], 0
0x1400179a2  call    cs:__imp_FindFirstFileW
0x1400179a8  mov     rdx, rax
0x1400179ab  lea     rcx, [rsp+520h+hFindFile]
0x1400179b0  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::TakeOwnership(void *)
0x1400179b5  mov     rbx, [rsp+520h+hFindFile]
0x1400179ba  test    rbx, rbx
0x1400179bd  jz      loc_140017B96
0x1400179c3  xor     edi, edi
0x1400179c5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400179c9  jz      loc_140017B96
0x1400179cf  test    byte ptr [rsp+520h+FindFileData.dwFileAttributes], 10h
0x1400179d4  jnz     loc_140017A83
0x1400179da  test    edi, edi
0x1400179dc  jz      short loc_1400179F8
0x1400179de  lea     rdx, [rsp+520h+FindFileData.ftLastWriteTime]; lpFileTime2
0x1400179e3  lea     rcx, [rbp+420h+FileTime1]; lpFileTime1
0x1400179ea  call    cs:__imp_CompareFileTime
0x1400179f0  test    eax, eax
0x1400179f2  jle     loc_140017A81
0x1400179f8  lea     rax, [rbp+420h+var_270]
0x1400179ff  mov     edx, 4
0x140017a04  lea     rcx, [rsp+520h+FindFileData]
0x140017a09  movups  xmm0, xmmword ptr [rcx]
0x140017a0c  movups  xmm1, xmmword ptr [rcx+10h]
0x140017a10  lea     rcx, [rcx+80h]
0x140017a17  movups  xmmword ptr [rax], xmm0
0x140017a1a  movups  xmm0, xmmword ptr [rcx-60h]
0x140017a1e  movups  xmmword ptr [rax+10h], xmm1
0x140017a22  movups  xmm1, xmmword ptr [rcx-50h]
0x140017a26  movups  xmmword ptr [rax+20h], xmm0
0x140017a2a  movups  xmm0, xmmword ptr [rcx-40h]
0x140017a2e  movups  xmmword ptr [rax+30h], xmm1
0x140017a32  movups  xmm1, xmmword ptr [rcx-30h]
0x140017a36  movups  xmmword ptr [rax+40h], xmm0
0x140017a3a  movups  xmm0, xmmword ptr [rcx-20h]
0x140017a3e  movups  xmmword ptr [rax+50h], xmm1
0x140017a42  movups  xmm1, xmmword ptr [rcx-10h]
0x140017a46  movups  xmmword ptr [rax+60h], xmm0
0x140017a4a  movups  xmmword ptr [rax+70h], xmm1
0x140017a4e  lea     rax, [rax+80h]
0x140017a55  sub     rdx, 1
0x140017a59  jnz     short loc_140017A09
0x140017a5b  movups  xmm0, xmmword ptr [rcx]
0x140017a5e  movups  xmm1, xmmword ptr [rcx+10h]
0x140017a62  movups  xmmword ptr [rax], xmm0
0x140017a65  movups  xmm0, xmmword ptr [rcx+20h]
0x140017a69  movups  xmmword ptr [rax+10h], xmm1
0x140017a6d  movups  xmm1, xmmword ptr [rcx+30h]
0x140017a71  movups  xmmword ptr [rax+20h], xmm0
0x140017a75  movups  xmm0, xmmword ptr [rcx+40h]
0x140017a79  movups  xmmword ptr [rax+30h], xmm1
0x140017a7d  movups  xmmword ptr [rax+40h], xmm0
0x140017a81  inc     edi
0x140017a83  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x140017a88  mov     rcx, rbx; hFindFile
0x140017a8b  call    cs:__imp_FindNextFileW
0x140017a91  test    eax, eax
0x140017a93  jnz     loc_1400179CF
0x140017a99  lea     rcx, [rsp+520h+hFindFile]
0x140017a9e  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140017aa3  cmp     edi, esi
0x140017aa5  jbe     loc_140017B96
0x140017aab  lea     r9, [rbp+420h+var_244]
0x140017ab2  mov     [rsp+520h+var_4E0], 0
0x140017abb  mov     r8, r14
0x140017abe  lea     rdx, aWsWs; "%ws\\%ws"
0x140017ac5  lea     rcx, [rsp+520h+var_4E0]
0x140017aca  call    SczAllocFormatted
0x140017acf  mov     ebx, eax
0x140017ad1  test    eax, eax
0x140017ad3  js      loc_140017BD3
0x140017ad9  mov     rcx, [rsp+520h+var_4E0]; lpFileName
0x140017ade  call    cs:__imp_DeleteFileW
0x140017ae4  test    eax, eax
0x140017ae6  jz      short loc_140017B01
0x140017ae8  lea     rcx, [rsp+520h+var_4E0]
0x140017aed  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017af2  lea     rcx, [rsp+520h+hFindFile]
0x140017af7  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140017afc  jmp     loc_14001798F
0x140017b01  call    cs:__imp_GetLastError
0x140017b07  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017b0e  mov     ebx, eax
0x140017b10  test    rcx, rcx
0x140017b13  jz      short loc_140017B69
0x140017b15  mov     edi, 3
0x140017b1a  lea     r9, aFailedToDelete_0; "Failed to delete oldest backup log."
0x140017b21  mov     r8d, edi
0x140017b24  xor     edx, edx
0x140017b26  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017b2b  test    ebx, ebx
0x140017b2d  jg      short loc_140017B33
0x140017b2f  mov     eax, ebx
0x140017b31  jmp     short loc_140017B3B
0x140017b33  movzx   eax, bx
0x140017b36  or      eax, 80070000h
0x140017b3b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017b42  lea     r9, a0; ": {0}"
0x140017b49  mov     [rsp+520h+var_4F0], eax
0x140017b4d  mov     r8d, edi
0x140017b50  lea     rax, [rsp+520h+var_4F0]
0x140017b55  mov     qword ptr [rsp+520h+var_4D0], rax
0x140017b5a  lea     rax, [rsp+520h+var_4D0]
0x140017b5f  mov     qword ptr [rsp+520h+var_500], rax; unsigned int
0x140017b64  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017b69  test    ebx, ebx
0x140017b6b  jz      short loc_140017B8C
0x140017b6d  mov     rcx, [rbp+428h]; this
0x140017b74  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140017b7b  mov     r9d, ebx; char *
0x140017b7e  mov     edx, 1CFh; void *
0x140017b83  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140017b88  mov     ebx, eax
0x140017b8a  jmp     short loc_140017BEE
0x140017b8c  lea     rcx, [rsp+520h+var_4E0]
0x140017b91  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017b96  lea     rcx, [rsp+520h+hFindFile]
0x140017b9b  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140017ba0  lea     rcx, [rsp+520h+lpFileName]
0x140017ba5  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017baa  xor     eax, eax
0x140017bac  mov     rcx, [rbp+420h+var_20]
0x140017bb3  xor     rcx, rsp; StackCookie
0x140017bb6  call    __security_check_cookie
0x140017bbb  lea     r11, [rsp+520h+var_10]
0x140017bc3  mov     rbx, [r11+28h]
0x140017bc7  mov     rsi, [r11+30h]
0x140017bcb  mov     rsp, r11
0x140017bce  pop     r14
0x140017bd0  pop     rdi
0x140017bd1  pop     rbp
0x140017bd2  retn
0x140017bd3  mov     rcx, [rbp+428h]; this
0x140017bda  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140017be1  mov     r9d, eax; char *
0x140017be4  mov     edx, 1CDh; void *
0x140017be9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017bee  lea     rcx, [rsp+520h+var_4E0]
0x140017bf3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017bf8  lea     rcx, [rsp+520h+hFindFile]
0x140017bfd  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140017c02  lea     rcx, [rsp+520h+lpFileName]
0x140017c07  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017c0c  mov     eax, ebx
0x140017c0e  jmp     short loc_140017BAC
```
