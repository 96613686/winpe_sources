# DeleteOldestLogFiles

- ea: `0x1800443ac`
- end: `0x180044723`
- name: `DeleteOldestLogFiles`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180044c90`

## callees

- `0x18001e51c`
- `0x180022d80`
- `0x1800293a0`
- `0x18003d7d4`
- `0x180041a74`
- `0x180041de8`
- `0x1800442a0`
- `0x1800443ac`
- `0x180044bcc`
- `0x18004c9e0`
- `0x18004cca0`
- `0x18004d3a0`
- `0x18004e878`
- `0x180099cb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004460d`
- `KERNEL32!GetLastError` at `0x18004460d`
- `KERNEL32!DeleteFileW` at `0x1800445e4`
- `KERNEL32!DeleteFileW` at `0x1800445e4`
- `KERNEL32!CompareFileTime` at `0x1800444e4`
- `KERNEL32!CompareFileTime` at `0x1800444e4`
- `KERNEL32!FindFirstFileW` at `0x180044496`
- `KERNEL32!FindFirstFileW` at `0x180044496`
- `KERNEL32!FindNextFileW` at `0x18004458b`
- `KERNEL32!FindNextFileW` at `0x18004458b`

## string_xrefs

- `0x18004462c`: `Failed to delete oldest backup log.`

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
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFindFile; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR v33; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v35[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v37[148]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  lpFileName = 0;
  memset(&FindFileData, 0, sizeof(FindFileData));
  memset(v37, 0, sizeof(v37));
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
        if ( !v9 || CompareFileTime((const FILETIME *)&v37[5], &FindFileData.ftLastWriteTime) > 0 )
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
    v25 = SczAllocFormatted(&v33, L"%ws\\%ws", a1, &v37[11]);
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
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to delete oldest backup log.");
    if ( LastError > 0 )
      v28 = (unsigned __int16)LastError | 0x80070000;
    else
      v28 = LastError;
    v31 = v28;
    *(_QWORD *)v35 = &v31;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v27,
      3,
      (__int64)": {0}",
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
0x1800443ac  mov     [rsp-8+arg_8], rbx
0x1800443b1  mov     [rsp-8+arg_10], rsi
0x1800443b6  push    rbp
0x1800443b7  push    rdi
0x1800443b8  push    r14
0x1800443ba  lea     rbp, [rsp-410h]
0x1800443c2  sub     rsp, 510h
0x1800443c9  mov     rax, cs:__security_cookie
0x1800443d0  xor     rax, rsp
0x1800443d3  mov     [rbp+420h+var_20], rax
0x1800443da  mov     r14, rcx
0x1800443dd  mov     [rsp+520h+lpFileName], 0
0x1800443e6  mov     ebx, 250h
0x1800443eb  lea     rcx, [rsp+520h+FindFileData]; void *
0x1800443f0  mov     r8d, ebx; Size
0x1800443f3  xor     edx, edx; Val
0x1800443f5  call    memset
0x1800443fa  mov     r8d, ebx; Size
0x1800443fd  lea     rcx, [rbp+420h+var_270]; void *
0x180044404  xor     edx, edx; Val
0x180044406  call    memset
0x18004440b  lea     rdx, [rsp+520h+var_4F0]; unsigned int *
0x180044410  mov     [rsp+520h+var_4F0], 0
0x180044418  lea     rcx, aNumcbspersistl; "NumCBSPersistLogs"
0x18004441f  call    ?OnlineConfigGetProperty@@YAJPEB_WPEAK@Z; OnlineConfigGetProperty(wchar_t const *,ulong *)
0x180044424  mov     esi, [rsp+520h+var_4F0]
0x180044428  test    eax, eax
0x18004442a  mov     ecx, 5
0x18004442f  mov     rdx, r14
0x180044432  cmovs   esi, ecx
0x180044435  lea     rcx, [rsp+520h+lpFileName]
0x18004443a  call    SczAllocFromSz
0x18004443f  mov     ebx, eax
0x180044441  test    eax, eax
0x180044443  jns     short loc_18004444C
0x180044445  mov     edx, 1A5h
0x18004444a  jmp     short loc_180044468
0x18004444c  lea     rdx, aCbspersist; "\\CbsPersist_*.*"
0x180044453  lea     rcx, [rsp+520h+lpFileName]
0x180044458  call    SczAllocConcatSz
0x18004445d  mov     ebx, eax
0x18004445f  test    eax, eax
0x180044461  jns     short loc_180044483
0x180044463  mov     edx, 1A6h; void *
0x180044468  mov     rcx, [rbp+428h]; this
0x18004446f  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180044476  mov     r9d, eax; char *
0x180044479  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004447e  jmp     loc_180044715
0x180044483  mov     rcx, [rsp+520h+lpFileName]; lpFileName
0x180044488  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x18004448d  mov     [rsp+520h+hFindFile], 0
0x180044496  call    cs:__imp_FindFirstFileW
0x18004449d  nop     dword ptr [rax+rax+00h]
0x1800444a2  mov     rdx, rax
0x1800444a5  lea     rcx, [rsp+520h+hFindFile]
0x1800444aa  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x1800444af  mov     rbx, [rsp+520h+hFindFile]
0x1800444b4  test    rbx, rbx
0x1800444b7  jz      loc_1800446A8
0x1800444bd  xor     edi, edi
0x1800444bf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800444c3  jz      loc_1800446A8
0x1800444c9  test    byte ptr [rsp+520h+FindFileData.dwFileAttributes], 10h
0x1800444ce  jnz     loc_180044583
0x1800444d4  test    edi, edi
0x1800444d6  jz      short loc_1800444F8
0x1800444d8  lea     rdx, [rsp+520h+FindFileData.ftLastWriteTime]; lpFileTime2
0x1800444dd  lea     rcx, [rbp+420h+FileTime1]; lpFileTime1
0x1800444e4  call    cs:__imp_CompareFileTime
0x1800444eb  nop     dword ptr [rax+rax+00h]
0x1800444f0  test    eax, eax
0x1800444f2  jle     loc_180044581
0x1800444f8  lea     rax, [rbp+420h+var_270]
0x1800444ff  mov     edx, 4
0x180044504  lea     rcx, [rsp+520h+FindFileData]
0x180044509  movups  xmm0, xmmword ptr [rcx]
0x18004450c  movups  xmm1, xmmword ptr [rcx+10h]
0x180044510  lea     rcx, [rcx+80h]
0x180044517  movups  xmmword ptr [rax], xmm0
0x18004451a  movups  xmm0, xmmword ptr [rcx-60h]
0x18004451e  movups  xmmword ptr [rax+10h], xmm1
0x180044522  movups  xmm1, xmmword ptr [rcx-50h]
0x180044526  movups  xmmword ptr [rax+20h], xmm0
0x18004452a  movups  xmm0, xmmword ptr [rcx-40h]
0x18004452e  movups  xmmword ptr [rax+30h], xmm1
0x180044532  movups  xmm1, xmmword ptr [rcx-30h]
0x180044536  movups  xmmword ptr [rax+40h], xmm0
0x18004453a  movups  xmm0, xmmword ptr [rcx-20h]
0x18004453e  movups  xmmword ptr [rax+50h], xmm1
0x180044542  movups  xmm1, xmmword ptr [rcx-10h]
0x180044546  movups  xmmword ptr [rax+60h], xmm0
0x18004454a  movups  xmmword ptr [rax+70h], xmm1
0x18004454e  lea     rax, [rax+80h]
0x180044555  sub     rdx, 1
0x180044559  jnz     short loc_180044509
0x18004455b  movups  xmm0, xmmword ptr [rcx]
0x18004455e  movups  xmm1, xmmword ptr [rcx+10h]
0x180044562  movups  xmmword ptr [rax], xmm0
0x180044565  movups  xmm0, xmmword ptr [rcx+20h]
0x180044569  movups  xmmword ptr [rax+10h], xmm1
0x18004456d  movups  xmm1, xmmword ptr [rcx+30h]
0x180044571  movups  xmmword ptr [rax+20h], xmm0
0x180044575  movups  xmm0, xmmword ptr [rcx+40h]
0x180044579  movups  xmmword ptr [rax+30h], xmm1
0x18004457d  movups  xmmword ptr [rax+40h], xmm0
0x180044581  inc     edi
0x180044583  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x180044588  mov     rcx, rbx; hFindFile
0x18004458b  call    cs:__imp_FindNextFileW
0x180044592  nop     dword ptr [rax+rax+00h]
0x180044597  test    eax, eax
0x180044599  jnz     loc_1800444C9
0x18004459f  lea     rcx, [rsp+520h+hFindFile]
0x1800445a4  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x1800445a9  cmp     edi, esi
0x1800445ab  jbe     loc_1800446A8
0x1800445b1  lea     r9, [rbp+420h+var_244]
0x1800445b8  mov     [rsp+520h+var_4E0], 0
0x1800445c1  mov     r8, r14
0x1800445c4  lea     rdx, aWsWs_0; "%ws\\%ws"
0x1800445cb  lea     rcx, [rsp+520h+var_4E0]
0x1800445d0  call    SczAllocFormatted
0x1800445d5  mov     ebx, eax
0x1800445d7  test    eax, eax
0x1800445d9  js      loc_1800446E6
0x1800445df  mov     rcx, [rsp+520h+var_4E0]; lpFileName
0x1800445e4  call    cs:__imp_DeleteFileW
0x1800445eb  nop     dword ptr [rax+rax+00h]
0x1800445f0  test    eax, eax
0x1800445f2  jz      short loc_18004460D
0x1800445f4  lea     rcx, [rsp+520h+var_4E0]
0x1800445f9  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800445fe  lea     rcx, [rsp+520h+hFindFile]
0x180044603  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x180044608  jmp     loc_180044483
0x18004460d  call    cs:__imp_GetLastError
0x180044614  nop     dword ptr [rax+rax+00h]
0x180044619  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044620  mov     ebx, eax
0x180044622  test    rcx, rcx
0x180044625  jz      short loc_18004467B
0x180044627  mov     edi, 3
0x18004462c  lea     r9, aFailedToDelete; "Failed to delete oldest backup log."
0x180044633  mov     r8d, edi
0x180044636  xor     edx, edx
0x180044638  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004463d  test    ebx, ebx
0x18004463f  jg      short loc_180044645
0x180044641  mov     eax, ebx
0x180044643  jmp     short loc_18004464D
0x180044645  movzx   eax, bx
0x180044648  or      eax, 80070000h
0x18004464d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044654  lea     r9, a0; ": {0}"
0x18004465b  mov     [rsp+520h+var_4F0], eax
0x18004465f  mov     r8d, edi
0x180044662  lea     rax, [rsp+520h+var_4F0]
0x180044667  mov     qword ptr [rsp+520h+var_4D0], rax
0x18004466c  lea     rax, [rsp+520h+var_4D0]
0x180044671  mov     qword ptr [rsp+520h+var_500], rax; unsigned int
0x180044676  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004467b  test    ebx, ebx
0x18004467d  jz      short loc_18004469E
0x18004467f  mov     rcx, [rbp+428h]; this
0x180044686  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x18004468d  mov     r9d, ebx; char *
0x180044690  mov     edx, 1CFh; void *
0x180044695  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004469a  mov     ebx, eax
0x18004469c  jmp     short loc_180044701
0x18004469e  lea     rcx, [rsp+520h+var_4E0]
0x1800446a3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800446a8  lea     rcx, [rsp+520h+hFindFile]
0x1800446ad  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x1800446b2  lea     rcx, [rsp+520h+lpFileName]
0x1800446b7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800446bc  xor     eax, eax
0x1800446be  mov     rcx, [rbp+420h+var_20]
0x1800446c5  xor     rcx, rsp; StackCookie
0x1800446c8  call    __security_check_cookie
0x1800446cd  lea     r11, [rsp+520h+var_10]
0x1800446d5  mov     rbx, [r11+28h]
0x1800446d9  mov     rsi, [r11+30h]
0x1800446dd  mov     rsp, r11
0x1800446e0  pop     r14
0x1800446e2  pop     rdi
0x1800446e3  pop     rbp
0x1800446e4  retn
0x1800446e6  mov     rcx, [rbp+428h]; this
0x1800446ed  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x1800446f4  mov     r9d, eax; char *
0x1800446f7  mov     edx, 1CDh; void *
0x1800446fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044701  lea     rcx, [rsp+520h+var_4E0]
0x180044706  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004470b  lea     rcx, [rsp+520h+hFindFile]
0x180044710  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x180044715  lea     rcx, [rsp+520h+lpFileName]
0x18004471a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004471f  mov     eax, ebx
0x180044721  jmp     short loc_1800446BE
```
