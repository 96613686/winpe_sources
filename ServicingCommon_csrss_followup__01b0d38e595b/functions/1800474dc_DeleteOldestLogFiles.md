# DeleteOldestLogFiles

- ea: `0x1800474dc`
- end: `0x180047853`
- name: `DeleteOldestLogFiles`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180047e20`

## callees

- `0x180020440`
- `0x180026c90`
- `0x18002d2b0`
- `0x180046650`
- `0x180046ca4`
- `0x1800473d4`
- `0x1800474dc`
- `0x180047c5c`
- `0x180047d5c`
- `0x18004fb00`
- `0x18004fdc0`
- `0x1800504d0`
- `0x1800519ac`
- `0x180097e20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004773d`
- `KERNEL32!GetLastError` at `0x18004773d`
- `KERNEL32!DeleteFileW` at `0x180047714`
- `KERNEL32!DeleteFileW` at `0x180047714`
- `KERNEL32!CompareFileTime` at `0x180047614`
- `KERNEL32!CompareFileTime` at `0x180047614`
- `KERNEL32!FindFirstFileW` at `0x1800475c6`
- `KERNEL32!FindFirstFileW` at `0x1800475c6`
- `KERNEL32!FindNextFileW` at `0x1800476bb`
- `KERNEL32!FindNextFileW` at `0x1800476bb`

## string_xrefs

- `0x18004775c`: `Failed to delete oldest backup log.`

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
0x1800474dc  mov     [rsp-8+arg_8], rbx
0x1800474e1  mov     [rsp-8+arg_10], rsi
0x1800474e6  push    rbp
0x1800474e7  push    rdi
0x1800474e8  push    r14
0x1800474ea  lea     rbp, [rsp-410h]
0x1800474f2  sub     rsp, 510h
0x1800474f9  mov     rax, cs:__security_cookie
0x180047500  xor     rax, rsp
0x180047503  mov     [rbp+420h+var_20], rax
0x18004750a  mov     r14, rcx
0x18004750d  mov     [rsp+520h+lpFileName], 0
0x180047516  mov     ebx, 250h
0x18004751b  lea     rcx, [rsp+520h+FindFileData]; void *
0x180047520  mov     r8d, ebx; Size
0x180047523  xor     edx, edx; Val
0x180047525  call    memset
0x18004752a  mov     r8d, ebx; Size
0x18004752d  lea     rcx, [rbp+420h+var_270]; void *
0x180047534  xor     edx, edx; Val
0x180047536  call    memset
0x18004753b  lea     rdx, [rsp+520h+var_4F0]; unsigned int *
0x180047540  mov     [rsp+520h+var_4F0], 0
0x180047548  lea     rcx, aNumcbspersistl; "NumCBSPersistLogs"
0x18004754f  call    ?OnlineConfigGetProperty@@YAJPEB_WPEAK@Z; OnlineConfigGetProperty(wchar_t const *,ulong *)
0x180047554  mov     esi, [rsp+520h+var_4F0]
0x180047558  test    eax, eax
0x18004755a  mov     ecx, 5
0x18004755f  mov     rdx, r14
0x180047562  cmovs   esi, ecx
0x180047565  lea     rcx, [rsp+520h+lpFileName]
0x18004756a  call    SczAllocFromSz
0x18004756f  mov     ebx, eax
0x180047571  test    eax, eax
0x180047573  jns     short loc_18004757C
0x180047575  mov     edx, 1A5h
0x18004757a  jmp     short loc_180047598
0x18004757c  lea     rdx, aCbspersist; "\\CbsPersist_*.*"
0x180047583  lea     rcx, [rsp+520h+lpFileName]
0x180047588  call    SczAllocConcatSz
0x18004758d  mov     ebx, eax
0x18004758f  test    eax, eax
0x180047591  jns     short loc_1800475B3
0x180047593  mov     edx, 1A6h; void *
0x180047598  mov     rcx, [rbp+428h]; this
0x18004759f  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x1800475a6  mov     r9d, eax; char *
0x1800475a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800475ae  jmp     loc_180047845
0x1800475b3  mov     rcx, [rsp+520h+lpFileName]; lpFileName
0x1800475b8  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x1800475bd  mov     [rsp+520h+hFindFile], 0
0x1800475c6  call    cs:__imp_FindFirstFileW
0x1800475cd  nop     dword ptr [rax+rax+00h]
0x1800475d2  mov     rdx, rax
0x1800475d5  lea     rcx, [rsp+520h+hFindFile]
0x1800475da  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x1800475df  mov     rbx, [rsp+520h+hFindFile]
0x1800475e4  test    rbx, rbx
0x1800475e7  jz      loc_1800477D8
0x1800475ed  xor     edi, edi
0x1800475ef  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800475f3  jz      loc_1800477D8
0x1800475f9  test    byte ptr [rsp+520h+FindFileData.dwFileAttributes], 10h
0x1800475fe  jnz     loc_1800476B3
0x180047604  test    edi, edi
0x180047606  jz      short loc_180047628
0x180047608  lea     rdx, [rsp+520h+FindFileData.ftLastWriteTime]; lpFileTime2
0x18004760d  lea     rcx, [rbp+420h+FileTime1]; lpFileTime1
0x180047614  call    cs:__imp_CompareFileTime
0x18004761b  nop     dword ptr [rax+rax+00h]
0x180047620  test    eax, eax
0x180047622  jle     loc_1800476B1
0x180047628  lea     rax, [rbp+420h+var_270]
0x18004762f  mov     edx, 4
0x180047634  lea     rcx, [rsp+520h+FindFileData]
0x180047639  movups  xmm0, xmmword ptr [rcx]
0x18004763c  movups  xmm1, xmmword ptr [rcx+10h]
0x180047640  lea     rcx, [rcx+80h]
0x180047647  movups  xmmword ptr [rax], xmm0
0x18004764a  movups  xmm0, xmmword ptr [rcx-60h]
0x18004764e  movups  xmmword ptr [rax+10h], xmm1
0x180047652  movups  xmm1, xmmword ptr [rcx-50h]
0x180047656  movups  xmmword ptr [rax+20h], xmm0
0x18004765a  movups  xmm0, xmmword ptr [rcx-40h]
0x18004765e  movups  xmmword ptr [rax+30h], xmm1
0x180047662  movups  xmm1, xmmword ptr [rcx-30h]
0x180047666  movups  xmmword ptr [rax+40h], xmm0
0x18004766a  movups  xmm0, xmmword ptr [rcx-20h]
0x18004766e  movups  xmmword ptr [rax+50h], xmm1
0x180047672  movups  xmm1, xmmword ptr [rcx-10h]
0x180047676  movups  xmmword ptr [rax+60h], xmm0
0x18004767a  movups  xmmword ptr [rax+70h], xmm1
0x18004767e  lea     rax, [rax+80h]
0x180047685  sub     rdx, 1
0x180047689  jnz     short loc_180047639
0x18004768b  movups  xmm0, xmmword ptr [rcx]
0x18004768e  movups  xmm1, xmmword ptr [rcx+10h]
0x180047692  movups  xmmword ptr [rax], xmm0
0x180047695  movups  xmm0, xmmword ptr [rcx+20h]
0x180047699  movups  xmmword ptr [rax+10h], xmm1
0x18004769d  movups  xmm1, xmmword ptr [rcx+30h]
0x1800476a1  movups  xmmword ptr [rax+20h], xmm0
0x1800476a5  movups  xmm0, xmmword ptr [rcx+40h]
0x1800476a9  movups  xmmword ptr [rax+30h], xmm1
0x1800476ad  movups  xmmword ptr [rax+40h], xmm0
0x1800476b1  inc     edi
0x1800476b3  lea     rdx, [rsp+520h+FindFileData]; lpFindFileData
0x1800476b8  mov     rcx, rbx; hFindFile
0x1800476bb  call    cs:__imp_FindNextFileW
0x1800476c2  nop     dword ptr [rax+rax+00h]
0x1800476c7  test    eax, eax
0x1800476c9  jnz     loc_1800475F9
0x1800476cf  lea     rcx, [rsp+520h+hFindFile]
0x1800476d4  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x1800476d9  cmp     edi, esi
0x1800476db  jbe     loc_1800477D8
0x1800476e1  lea     r9, [rbp+420h+var_244]
0x1800476e8  mov     [rsp+520h+var_4E0], 0
0x1800476f1  mov     r8, r14
0x1800476f4  lea     rdx, aWsWs_0; "%ws\\%ws"
0x1800476fb  lea     rcx, [rsp+520h+var_4E0]
0x180047700  call    SczAllocFormatted
0x180047705  mov     ebx, eax
0x180047707  test    eax, eax
0x180047709  js      loc_180047816
0x18004770f  mov     rcx, [rsp+520h+var_4E0]; lpFileName
0x180047714  call    cs:__imp_DeleteFileW
0x18004771b  nop     dword ptr [rax+rax+00h]
0x180047720  test    eax, eax
0x180047722  jz      short loc_18004773D
0x180047724  lea     rcx, [rsp+520h+var_4E0]
0x180047729  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004772e  lea     rcx, [rsp+520h+hFindFile]
0x180047733  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x180047738  jmp     loc_1800475B3
0x18004773d  call    cs:__imp_GetLastError
0x180047744  nop     dword ptr [rax+rax+00h]
0x180047749  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047750  mov     ebx, eax
0x180047752  test    rcx, rcx
0x180047755  jz      short loc_1800477AB
0x180047757  mov     edi, 3
0x18004775c  lea     r9, aFailedToDelete; "Failed to delete oldest backup log."
0x180047763  mov     r8d, edi
0x180047766  xor     edx, edx
0x180047768  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004776d  test    ebx, ebx
0x18004776f  jg      short loc_180047775
0x180047771  mov     eax, ebx
0x180047773  jmp     short loc_18004777D
0x180047775  movzx   eax, bx
0x180047778  or      eax, 80070000h
0x18004777d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047784  lea     r9, a0; ": {0}"
0x18004778b  mov     [rsp+520h+var_4F0], eax
0x18004778f  mov     r8d, edi
0x180047792  lea     rax, [rsp+520h+var_4F0]
0x180047797  mov     qword ptr [rsp+520h+var_4D0], rax
0x18004779c  lea     rax, [rsp+520h+var_4D0]
0x1800477a1  mov     qword ptr [rsp+520h+var_500], rax; unsigned int
0x1800477a6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800477ab  test    ebx, ebx
0x1800477ad  jz      short loc_1800477CE
0x1800477af  mov     rcx, [rbp+428h]; this
0x1800477b6  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x1800477bd  mov     r9d, ebx; char *
0x1800477c0  mov     edx, 1CFh; void *
0x1800477c5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800477ca  mov     ebx, eax
0x1800477cc  jmp     short loc_180047831
0x1800477ce  lea     rcx, [rsp+520h+var_4E0]
0x1800477d3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800477d8  lea     rcx, [rsp+520h+hFindFile]
0x1800477dd  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x1800477e2  lea     rcx, [rsp+520h+lpFileName]
0x1800477e7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800477ec  xor     eax, eax
0x1800477ee  mov     rcx, [rbp+420h+var_20]
0x1800477f5  xor     rcx, rsp; StackCookie
0x1800477f8  call    __security_check_cookie
0x1800477fd  lea     r11, [rsp+520h+var_10]
0x180047805  mov     rbx, [r11+28h]
0x180047809  mov     rsi, [r11+30h]
0x18004780d  mov     rsp, r11
0x180047810  pop     r14
0x180047812  pop     rdi
0x180047813  pop     rbp
0x180047814  retn
0x180047816  mov     rcx, [rbp+428h]; this
0x18004781d  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180047824  mov     r9d, eax; char *
0x180047827  mov     edx, 1CDh; void *
0x18004782c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047831  lea     rcx, [rsp+520h+var_4E0]
0x180047836  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004783b  lea     rcx, [rsp+520h+hFindFile]
0x180047840  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x180047845  lea     rcx, [rsp+520h+lpFileName]
0x18004784a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004784f  mov     eax, ebx
0x180047851  jmp     short loc_1800477EE
```
