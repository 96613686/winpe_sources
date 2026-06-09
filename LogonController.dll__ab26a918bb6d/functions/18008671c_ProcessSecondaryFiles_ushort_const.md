# ProcessSecondaryFiles(ushort const *)

- ea: `0x18008671c`
- end: `0x1800868cc`
- name: `?ProcessSecondaryFiles@@YAJPEBG@Z`
- size: `432`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180086560`

## callees

- `0x18005d488`
- `0x18005d5a0`
- `0x180066a54`
- `0x18006c000`
- `0x18006cad0`
- `0x180085f54`
- `0x180085f78`
- `0x18008671c`
- `0x180086d30`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x180086834`
- `KERNEL32!FindNextFileW` at `0x180086834`
- `KERNEL32!DeleteFileW` at `0x18008680d`
- `KERNEL32!DeleteFileW` at `0x18008680d`
- `KERNEL32!FindFirstFileExW` at `0x1800867ba`
- `KERNEL32!FindFirstFileExW` at `0x1800867ba`
- `KERNEL32!GetLastError` at `0x18008683e`
- `KERNEL32!GetLastError` at `0x18008683e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18008675a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800867f6`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18008675a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800867f6`

## pseudocode

```c
__int64 __fastcall ProcessSecondaryFiles(PCWSTR pszPathIn)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  HRESULT v4; // eax
  HRESULT v5; // edi
  const char *v6; // r9
  DWORD LastError; // eax
  int lpSearchFilter; // [rsp+20h] [rbp-E0h]
  unsigned int lpSearchFiltera; // [rsp+20h] [rbp-E0h]
  HANDLE v11[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[80]; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR FileName[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+738h] [rbp+638h]

  v2 = PathCchCombine(pszPathOut, 0x104u, pszPathIn, L"settings.*");
  v3 = v2;
  if ( v2 >= 0 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v11[0] = FindFirstFileExW(pszPathOut, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
    if ( v11[0] == (HANDLE)-1LL )
    {
LABEL_11:
      v3 = 0;
    }
    else
    {
      DatVPrepTelemetry::WatchCurrentThread(v12, "DoDatVPrepRSSecondaryFiles");
      do
      {
        v4 = PathCchCombine(FileName, 0x104u, pszPathIn, FindFileData.cFileName);
        v5 = v4;
        if ( v4 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2B,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
            (const char *)(unsigned int)v4,
            lpSearchFiltera);
          v3 = v5;
          goto LABEL_18;
        }
        if ( !DeleteFileW(FileName) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x2C,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
            v6);
      }
      while ( FindNextFileW(v11[0], &FindFileData) );
      LastError = GetLastError();
      if ( LastError == 18 )
      {
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v12);
        goto LABEL_11;
      }
      if ( LastError )
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x37,
               (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
               (const char *)LastError,
               lpSearchFiltera);
      else
        v3 = 0;
LABEL_18:
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v12);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(v11);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
      (const char *)(unsigned int)v2,
      lpSearchFilter);
  }
  return v3;
}

```

## disassembly

```asm
0x18008671c  push    rbp
0x18008671e  push    rbx
0x18008671f  push    rsi
0x180086720  push    rdi
0x180086721  lea     rbp, [rsp-618h]
0x180086729  sub     rsp, 718h
0x180086730  mov     rax, cs:__security_cookie
0x180086737  xor     rax, rsp
0x18008673a  mov     [rbp+630h+var_30], rax
0x180086741  mov     rsi, rcx
0x180086744  lea     r9, aSettings; "settings.*"
0x18008674b  mov     r8, rcx; pszPathIn
0x18008674e  mov     edx, 104h; cchPathOut
0x180086753  lea     rcx, [rbp+630h+pszPathOut]; pszPathOut
0x18008675a  call    cs:__imp_PathCchCombine
0x180086760  mov     ebx, eax
0x180086762  test    eax, eax
0x180086764  jns     short loc_180086786
0x180086766  mov     rcx, [rbp+638h]; this
0x18008676d  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x180086774  mov     r9d, eax; char *
0x180086777  mov     edx, 1Fh; void *
0x18008677c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086781  jmp     loc_18008685F
0x180086786  xor     edx, edx; Val
0x180086788  lea     rcx, [rbp+630h+FindFileData]; void *
0x18008678c  mov     r8d, 250h; Size
0x180086792  call    memset_0
0x180086797  xor     r9d, r9d; fSearchOp
0x18008679a  mov     [rsp+730h+dwAdditionalFlags], 0; dwAdditionalFlags
0x1800867a2  lea     r8, [rbp+630h+FindFileData]; lpFindFileData
0x1800867a6  mov     [rsp+730h+lpSearchFilter], 0; int
0x1800867af  lea     rcx, [rbp+630h+pszPathOut]; lpFileName
0x1800867b6  lea     edx, [r9+1]; fInfoLevelId
0x1800867ba  call    cs:__imp_FindFirstFileExW
0x1800867c0  mov     [rsp+730h+var_700], rax
0x1800867c5  mov     rbx, rax
0x1800867c8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800867cc  jz      loc_180086853
0x1800867d2  lea     rdx, aDodatvpreprsse; "DoDatVPrepRSSecondaryFiles"
0x1800867d9  lea     rcx, [rsp+730h+var_6F0]
0x1800867de  call    ?WatchCurrentThread@DatVPrepTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; DatVPrepTelemetry::WatchCurrentThread(char const *)
0x1800867e3  lea     r9, [rbp+630h+pszMore]; pszMore
0x1800867e7  mov     r8, rsi; pszPathIn
0x1800867ea  mov     edx, 104h; cchPathOut
0x1800867ef  lea     rcx, [rbp+630h+FileName]; pszPathOut
0x1800867f6  call    cs:__imp_PathCchCombine
0x1800867fc  mov     edi, eax
0x1800867fe  test    eax, eax
0x180086800  js      loc_1800868A3
0x180086806  lea     rcx, [rbp+630h+FileName]; lpFileName
0x18008680d  call    cs:__imp_DeleteFileW
0x180086813  test    eax, eax
0x180086815  jnz     short loc_18008682D
0x180086817  mov     rcx, [rbp+638h]; this
0x18008681e  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x180086825  lea     edx, [rax+2Ch]; void *
0x180086828  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18008682d  lea     rdx, [rbp+630h+FindFileData]; lpFindFileData
0x180086831  mov     rcx, rbx; hFindFile
0x180086834  call    cs:__imp_FindNextFileW
0x18008683a  test    eax, eax
0x18008683c  jnz     short loc_1800867E3
0x18008683e  call    cs:__imp_GetLastError
0x180086844  cmp     eax, 12h
0x180086847  jnz     short loc_18008687C
0x180086849  lea     rcx, [rsp+730h+var_6F0]; this
0x18008684e  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180086853  xor     ebx, ebx
0x180086855  lea     rcx, [rsp+730h+var_700]
0x18008685a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18008685f  mov     eax, ebx
0x180086861  mov     rcx, [rbp+630h+var_30]
0x180086868  xor     rcx, rsp; StackCookie
0x18008686b  call    __security_check_cookie
0x180086870  add     rsp, 718h
0x180086877  pop     rdi
0x180086878  pop     rsi
0x180086879  pop     rbx
0x18008687a  pop     rbp
0x18008687b  retn
0x18008687c  test    eax, eax
0x18008687e  jz      short loc_18008689F
0x180086880  mov     rcx, [rbp+638h]; this
0x180086887  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x18008688e  mov     r9d, eax; char *
0x180086891  mov     edx, 37h ; '7'; void *
0x180086896  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008689b  mov     ebx, eax
0x18008689d  jmp     short loc_1800868C0
0x18008689f  xor     ebx, ebx
0x1800868a1  jmp     short loc_1800868C0
0x1800868a3  mov     rcx, [rbp+638h]; this
0x1800868aa  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800868b1  mov     r9d, edi; char *
0x1800868b4  mov     edx, 2Bh ; '+'; void *
0x1800868b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800868be  mov     ebx, edi
0x1800868c0  lea     rcx, [rsp+730h+var_6F0]; this
0x1800868c5  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800868ca  jmp     short loc_180086855
```
