# IsDirectoryEmpty

- ea: `0x14001fab0`
- end: `0x14001fc66`
- name: `IsDirectoryEmpty`
- size: `438`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x140017ecc`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016fb4`
- `0x1400177e0`
- `0x140018574`
- `0x14001cd14`
- `0x14001d5cc`
- `0x14001e914`
- `0x14001fab0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fc47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fc47`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14001fbfc`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14001fbfc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14001fbc4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14001fbc4`

## string_xrefs

- `0x14001fb24`: `Invalid path specified`

## pseudocode

```c
__int64 __fastcall IsDirectoryEmpty(__int64 a1, _BYTE *a2)
{
  signed int LastError; // ebx
  int v5; // edx
  __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  HANDLE FirstFileW; // rax
  HANDLE v10; // rbx
  int v12; // [rsp+20h] [rbp-E0h]
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
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid path specified");
      v15 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
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
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v6,
      v12);
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
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::TakeOwnership(
    &hFindFile,
    FirstFileW);
  v10 = hFindFile;
  if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    while ( IsDotFile(FindFileData.cFileName) )
    {
      if ( !FindNextFileW(v10, &FindFileData) )
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
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14001fab0  mov     [rsp-8+arg_10], rbx
0x14001fab5  mov     [rsp-8+arg_18], rdi
0x14001faba  push    rbp
0x14001fabb  lea     rbp, [rsp-1B0h]
0x14001fac3  sub     rsp, 2B0h
0x14001faca  mov     rax, cs:__security_cookie
0x14001fad1  xor     rax, rsp
0x14001fad4  mov     [rbp+1B0h+var_10], rax
0x14001fadb  mov     rdi, rdx
0x14001fade  mov     rbx, rcx
0x14001fae1  xor     edx, edx; Val
0x14001fae3  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x14001fae8  mov     r8d, 250h; Size
0x14001faee  call    memset_0
0x14001faf3  mov     [rsp+2B0h+hFindFile], 0
0x14001fafc  mov     [rsp+2B0h+lpFileName], 0
0x14001fb05  test    rbx, rbx
0x14001fb08  jnz     short loc_14001FB69
0x14001fb0a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001fb11  mov     ebx, 80070057h
0x14001fb16  mov     [rsp+2B0h+var_268], ebx
0x14001fb1a  test    rcx, rcx
0x14001fb1d  jz      short loc_14001FB5F
0x14001fb1f  mov     edi, 3
0x14001fb24  lea     r9, aInvalidPathSpe; "Invalid path specified"
0x14001fb2b  mov     r8d, edi
0x14001fb2e  xor     edx, edx
0x14001fb30  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001fb35  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001fb3c  lea     rax, [rsp+2B0h+var_268]
0x14001fb41  mov     [rsp+2B0h+var_270], rax
0x14001fb46  lea     r9, asc_1400353E8; ": {}"
0x14001fb4d  lea     rax, [rsp+2B0h+var_270]
0x14001fb52  mov     r8d, edi
0x14001fb55  mov     qword ptr [rsp+2B0h+var_290], rax
0x14001fb5a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001fb5f  mov     r9d, ebx
0x14001fb62  mov     edx, 1E0h
0x14001fb67  jmp     short loc_14001FB87
0x14001fb69  mov     rdx, rbx
0x14001fb6c  mov     byte ptr [rdi], 1
0x14001fb6f  lea     rcx, [rsp+2B0h+lpFileName]
0x14001fb74  call    SczAllocFromSzAndEnsureBackslash
0x14001fb79  mov     ebx, eax
0x14001fb7b  test    eax, eax
0x14001fb7d  jns     short loc_14001FB9C
0x14001fb7f  mov     edx, 1E4h; void *
0x14001fb84  mov     r9d, eax; char *
0x14001fb87  mov     rcx, [rbp+1B8h]; this
0x14001fb8e  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001fb95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001fb9a  jmp     short loc_14001FC08
0x14001fb9c  lea     rdx, asc_140036EB8; "*"
0x14001fba3  lea     rcx, [rsp+2B0h+lpFileName]
0x14001fba8  call    SczAllocConcatSz
0x14001fbad  mov     ebx, eax
0x14001fbaf  test    eax, eax
0x14001fbb1  jns     short loc_14001FBBA
0x14001fbb3  mov     edx, 1E5h
0x14001fbb8  jmp     short loc_14001FB84
0x14001fbba  mov     rcx, [rsp+2B0h+lpFileName]; lpFileName
0x14001fbbf  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x14001fbc4  call    cs:__imp_FindFirstFileW
0x14001fbca  mov     rdx, rax
0x14001fbcd  lea     rcx, [rsp+2B0h+hFindFile]
0x14001fbd2  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::TakeOwnership(void *)
0x14001fbd7  mov     rbx, [rsp+2B0h+hFindFile]
0x14001fbdc  lea     rax, [rbx-1]
0x14001fbe0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001fbe4  ja      short loc_14001FC47
0x14001fbe6  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; wchar_t *
0x14001fbeb  call    ?IsDotFile@@YA_NPEB_W@Z; IsDotFile(wchar_t const *)
0x14001fbf0  test    al, al
0x14001fbf2  jz      short loc_14001FC42
0x14001fbf4  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x14001fbf9  mov     rcx, rbx; hFindFile
0x14001fbfc  call    cs:__imp_FindNextFileW
0x14001fc02  test    eax, eax
0x14001fc04  jnz     short loc_14001FBE6
0x14001fc06  xor     ebx, ebx
0x14001fc08  lea     rcx, [rsp+2B0h+lpFileName]
0x14001fc0d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001fc12  lea     rcx, [rsp+2B0h+hFindFile]
0x14001fc17  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x14001fc1c  mov     eax, ebx
0x14001fc1e  mov     rcx, [rbp+1B0h+var_10]
0x14001fc25  xor     rcx, rsp; StackCookie
0x14001fc28  call    __security_check_cookie
0x14001fc2d  lea     r11, [rsp+2B0h+var_s0]
0x14001fc35  mov     rbx, [r11+20h]
0x14001fc39  mov     rdi, [r11+28h]
0x14001fc3d  mov     rsp, r11
0x14001fc40  pop     rbp
0x14001fc41  retn
0x14001fc42  mov     byte ptr [rdi], 0
0x14001fc45  jmp     short loc_14001FC06
0x14001fc47  call    cs:__imp_GetLastError
0x14001fc4d  mov     ebx, eax
0x14001fc4f  add     eax, 0FFFFFFFEh
0x14001fc52  cmp     eax, 1
0x14001fc55  jbe     short loc_14001FC06
0x14001fc57  test    ebx, ebx
0x14001fc59  jle     short loc_14001FC08
0x14001fc5b  movzx   ebx, bx
0x14001fc5e  or      ebx, 80070000h
0x14001fc64  jmp     short loc_14001FC08
```
