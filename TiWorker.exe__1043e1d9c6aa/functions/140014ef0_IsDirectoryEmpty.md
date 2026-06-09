# IsDirectoryEmpty

- ea: `0x140014ef0`
- end: `0x1400150a6`
- name: `IsDirectoryEmpty`
- size: `438`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x14000ed6c`

## callees

- `0x140002310`
- `0x140002cf8`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x14000e63c`
- `0x14000f4f0`
- `0x140012558`
- `0x140014ef0`
- `0x1400177d8`
- `0x140018090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015087`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140015004`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140015004`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14001503c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14001503c`

## string_xrefs

- `0x140014f64`: `Invalid path specified`

## pseudocode

```c
__int64 __fastcall IsDirectoryEmpty(__int64 a1, _BYTE *a2)
{
  signed int LastError; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  const struct std::nothrow_t *v9; // rdx
  HANDLE FirstFileW; // rax
  HANDLE v11; // rbx
  LPCWSTR lpFileName; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFindFile; // [rsp+38h] [rbp-C8h] BYREF
  int *v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  hFindFile = 0;
  lpFileName = 0;
  if ( !a1 )
  {
    LastError = -2147024809;
    v16 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid path specified");
      v15 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)&v15);
    }
    v6 = 2147942487LL;
    v7 = 480;
    goto LABEL_8;
  }
  *a2 = 1;
  v8 = SczAllocFromSzAndEnsureBackslash(&lpFileName, a1);
  LastError = v8;
  if ( v8 < 0 )
  {
    v7 = 484;
LABEL_7:
    v6 = (unsigned int)v8;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v6);
    goto LABEL_15;
  }
  v8 = SczAllocConcatSz(&lpFileName, L"*");
  LastError = v8;
  if ( v8 < 0 )
  {
    v7 = 485;
    goto LABEL_7;
  }
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &hFindFile,
    FirstFileW);
  v11 = hFindFile;
  if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    while ( IsDotFile(FindFileData.cFileName) )
    {
      if ( !FindNextFileW(v11, &FindFileData) )
        goto LABEL_14;
    }
    *a2 = 0;
    goto LABEL_14;
  }
  LastError = GetLastError();
  if ( (unsigned int)(LastError - 2) <= 1 )
  {
LABEL_14:
    LastError = 0;
    goto LABEL_15;
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&lpFileName, v9);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140014ef0  mov     [rsp-8+arg_10], rbx
0x140014ef5  mov     [rsp-8+arg_18], rdi
0x140014efa  push    rbp
0x140014efb  lea     rbp, [rsp-1B0h]
0x140014f03  sub     rsp, 2B0h
0x140014f0a  mov     rax, cs:__security_cookie
0x140014f11  xor     rax, rsp
0x140014f14  mov     [rbp+1B0h+var_10], rax
0x140014f1b  mov     rdi, rdx
0x140014f1e  mov     rbx, rcx
0x140014f21  xor     edx, edx; Val
0x140014f23  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x140014f28  mov     r8d, 250h; Size
0x140014f2e  call    memset_0
0x140014f33  mov     [rsp+2B0h+hFindFile], 0
0x140014f3c  mov     [rsp+2B0h+lpFileName], 0
0x140014f45  test    rbx, rbx
0x140014f48  jnz     short loc_140014FA9
0x140014f4a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014f51  mov     ebx, 80070057h
0x140014f56  mov     [rsp+2B0h+var_268], ebx
0x140014f5a  test    rcx, rcx
0x140014f5d  jz      short loc_140014F9F
0x140014f5f  mov     edi, 3
0x140014f64  lea     r9, aInvalidPathSpe; "Invalid path specified"
0x140014f6b  mov     r8d, edi
0x140014f6e  xor     edx, edx
0x140014f70  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140014f75  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014f7c  lea     rax, [rsp+2B0h+var_268]
0x140014f81  mov     [rsp+2B0h+var_270], rax
0x140014f86  lea     r9, asc_140030534; ": {}"
0x140014f8d  lea     rax, [rsp+2B0h+var_270]
0x140014f92  mov     r8d, edi
0x140014f95  mov     [rsp+2B0h+var_290], rax
0x140014f9a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140014f9f  mov     r9d, ebx
0x140014fa2  mov     edx, 1E0h
0x140014fa7  jmp     short loc_140014FC7
0x140014fa9  mov     rdx, rbx
0x140014fac  mov     byte ptr [rdi], 1
0x140014faf  lea     rcx, [rsp+2B0h+lpFileName]
0x140014fb4  call    SczAllocFromSzAndEnsureBackslash
0x140014fb9  mov     ebx, eax
0x140014fbb  test    eax, eax
0x140014fbd  jns     short loc_140014FDC
0x140014fbf  mov     edx, 1E4h; void *
0x140014fc4  mov     r9d, eax; char *
0x140014fc7  mov     rcx, [rbp+1B8h]; this
0x140014fce  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140014fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014fda  jmp     short loc_140015048
0x140014fdc  lea     rdx, asc_140032658; "*"
0x140014fe3  lea     rcx, [rsp+2B0h+lpFileName]
0x140014fe8  call    SczAllocConcatSz
0x140014fed  mov     ebx, eax
0x140014fef  test    eax, eax
0x140014ff1  jns     short loc_140014FFA
0x140014ff3  mov     edx, 1E5h
0x140014ff8  jmp     short loc_140014FC4
0x140014ffa  mov     rcx, [rsp+2B0h+lpFileName]; lpFileName
0x140014fff  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x140015004  call    cs:__imp_FindFirstFileW
0x14001500a  mov     rdx, rax
0x14001500d  lea     rcx, [rsp+2B0h+hFindFile]
0x140015012  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x140015017  mov     rbx, [rsp+2B0h+hFindFile]
0x14001501c  lea     rax, [rbx-1]
0x140015020  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140015024  ja      short loc_140015087
0x140015026  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; wchar_t *
0x14001502b  call    ?IsDotFile@@YA_NPEB_W@Z; IsDotFile(wchar_t const *)
0x140015030  test    al, al
0x140015032  jz      short loc_140015082
0x140015034  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x140015039  mov     rcx, rbx; hFindFile
0x14001503c  call    cs:__imp_FindNextFileW
0x140015042  test    eax, eax
0x140015044  jnz     short loc_140015026
0x140015046  xor     ebx, ebx
0x140015048  lea     rcx, [rsp+2B0h+lpFileName]
0x14001504d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015052  lea     rcx, [rsp+2B0h+hFindFile]
0x140015057  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x14001505c  mov     eax, ebx
0x14001505e  mov     rcx, [rbp+1B0h+var_10]
0x140015065  xor     rcx, rsp; StackCookie
0x140015068  call    __security_check_cookie
0x14001506d  lea     r11, [rsp+2B0h+var_s0]
0x140015075  mov     rbx, [r11+20h]
0x140015079  mov     rdi, [r11+28h]
0x14001507d  mov     rsp, r11
0x140015080  pop     rbp
0x140015081  retn
0x140015082  mov     byte ptr [rdi], 0
0x140015085  jmp     short loc_140015046
0x140015087  call    cs:__imp_GetLastError
0x14001508d  mov     ebx, eax
0x14001508f  add     eax, 0FFFFFFFEh
0x140015092  cmp     eax, 1
0x140015095  jbe     short loc_140015046
0x140015097  test    ebx, ebx
0x140015099  jle     short loc_140015048
0x14001509b  movzx   ebx, bx
0x14001509e  or      ebx, 80070000h
0x1400150a4  jmp     short loc_140015048
```
