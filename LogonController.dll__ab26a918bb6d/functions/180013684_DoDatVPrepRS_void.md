# _DoDatVPrepRS(void)

- ea: `0x180013684`
- end: `0x1800139bd`
- name: `?_DoDatVPrepRS@@YAJXZ`
- size: `825`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180061420`

## callees

- `0x180013684`
- `0x18005d488`
- `0x18005d4e8`
- `0x18005d5a0`
- `0x18006c000`
- `0x18006cad0`
- `0x180085e60`
- `0x180085f54`
- `0x180086030`
- `0x180086560`
- `0x1800868f4`
- `0x180086a08`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x1800138cd`
- `KERNEL32!FindNextFileW` at `0x1800138cd`
- `KERNEL32!FindFirstFileExW` at `0x18001382b`
- `KERNEL32!FindFirstFileExW` at `0x18001382b`
- `KERNEL32!CompareStringOrdinal` at `0x180013880`
- `KERNEL32!CompareStringOrdinal` at `0x1800138a5`
- `KERNEL32!CompareStringOrdinal` at `0x180013880`
- `KERNEL32!CompareStringOrdinal` at `0x1800138a5`
- `KERNEL32!GetLastError` at `0x1800138d7`
- `KERNEL32!GetLastError` at `0x1800138d7`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800137c0`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800137c0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1800136f6`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1800136f6`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x18001392c`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x18001392c`
- `USERENV!GetProfilesDirectoryW` at `0x180013781`
- `USERENV!GetProfilesDirectoryW` at `0x180013781`

## string_xrefs

- `0x1800136c5`: `DatVPrepComplete`
- `0x180013917`: `DatVPrepComplete`

## pseudocode

```c
__int64 _DoDatVPrepRS(void)
{
  int PersistedRegistryValueW; // eax
  unsigned int LastError; // ebx
  const char *v3; // r9
  HRESULT v4; // eax
  const char *v5; // r9
  unsigned int v6; // eax
  DWORD v7; // eax
  int v8; // eax
  unsigned int lpSearchFilter; // [rsp+20h] [rbp-E0h]
  HANDLE FirstFile; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchSize[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v12[42]; // [rsp+60h] [rbp-A0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR ProfileDir[264]; // [rsp+400h] [rbp+300h] BYREF
  WCHAR pszPathOut[264]; // [rsp+610h] [rbp+510h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+838h] [rbp+738h]

  PersistedRegistryValueW = GetPersistedRegistryValueW(
                              L"CloudExperienceHost",
                              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
                              L"DatVPrepComplete",
                              24);
  LastError = PersistedRegistryValueW;
  if ( PersistedRegistryValueW > 0 )
    LastError = (unsigned __int16)PersistedRegistryValueW | 0x80070000;
  if ( (LastError & 0x80000000) != 0 && LastError != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
      (const char *)LastError,
      0);
    return LastError;
  }
  wil::ActivityBase<DatVPrepLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DatVPrepLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v12);
  v12[0] = &DatVPrepTelemetry::DoDatVPrepRS::`vftable';
  DatVPrepTelemetry::DoDatVPrepRS::StartActivity((DatVPrepTelemetry::DoDatVPrepRS *)v12);
  cchSize[0] = 260;
  if ( !GetProfilesDirectoryW(ProfileDir, cchSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x78,
                  (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
                  v3);
LABEL_28:
    DatVPrepTelemetry::DoDatVPrepRS::~DoDatVPrepRS((DatVPrepTelemetry::DoDatVPrepRS *)v12);
    return LastError;
  }
  v4 = PathCchCombine(pszPathOut, 0x104u, ProfileDir, L"*");
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
      (const char *)(unsigned int)v4,
      0);
    goto LABEL_28;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFile = FindFirstFileExW(pszPathOut, FindExInfoBasic, &FindFileData, FindExSearchLimitToDirectories, 0, 0);
  if ( FirstFile == (HANDLE)-1LL )
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x7F,
           (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
           v5);
LABEL_13:
    LastError = v6;
LABEL_27:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&FirstFile);
    goto LABEL_28;
  }
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && CompareStringOrdinal(L".", -1, FindFileData.cFileName, -1, 1) != 2
      && CompareStringOrdinal(L"..", -1, FindFileData.cFileName, -1, 1) != 2 )
    {
      ProcessProfileFolder(ProfileDir, FindFileData.cFileName);
    }
  }
  while ( FindNextFileW(FirstFile, &FindFileData) );
  v7 = GetLastError();
  if ( v7 != 18 )
  {
    if ( !v7 )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&FirstFile);
      LastError = 0;
      goto LABEL_28;
    }
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x95,
           (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
           (const char *)v7,
           lpSearchFilter);
    goto LABEL_13;
  }
  v8 = SetPersistedRegistryBOOL(
         L"CloudExperienceHost",
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
         L"DatVPrepComplete",
         1);
  LastError = v8;
  if ( v8 > 0 )
    LastError = (unsigned __int16)v8 | 0x80070000;
  if ( (LastError & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
      (const char *)LastError,
      lpSearchFilter);
    goto LABEL_27;
  }
  wil::ActivityBase<DatVPrepLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&FirstFile);
  DatVPrepTelemetry::DoDatVPrepRS::~DoDatVPrepRS((DatVPrepTelemetry::DoDatVPrepRS *)v12);
  return 0;
}

```

## disassembly

```asm
0x180013684  mov     [rsp-8+arg_0], rbx
0x180013689  mov     [rsp-8+arg_8], r14
0x18001368e  push    rbp
0x18001368f  lea     rbp, [rsp-730h]
0x180013697  sub     rsp, 830h
0x18001369e  mov     rax, cs:__security_cookie
0x1800136a5  xor     rax, rsp
0x1800136a8  mov     [rbp+730h+var_10], rax
0x1800136af  mov     [rsp+830h+var_7F8], 0
0x1800136b8  lea     rax, [rsp+830h+var_7F0]
0x1800136bd  mov     [rsp+830h+var_800], 4
0x1800136c5  lea     r8, aDatvprepcomple; "DatVPrepComplete"
0x1800136cc  mov     qword ptr [rsp+830h+dwAdditionalFlags], rax
0x1800136d1  lea     rdx, aSoftwareMicros_22; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800136d8  mov     r9d, 18h
0x1800136de  mov     [rsp+830h+lpSearchFilter], 0; int
0x1800136e7  lea     rcx, aCloudexperienc; "CloudExperienceHost"
0x1800136ee  mov     [rsp+830h+var_7F0], 0
0x1800136f6  call    cs:__imp_GetPersistedRegistryValueW
0x1800136fc  mov     ebx, eax
0x1800136fe  test    eax, eax
0x180013700  jle     short loc_18001370B
0x180013702  movzx   ebx, ax
0x180013705  or      ebx, 80070000h
0x18001370b  test    ebx, ebx
0x18001370d  jns     short loc_180013739
0x18001370f  cmp     ebx, 80070002h
0x180013715  jz      short loc_18001374C
0x180013717  mov     rcx, [rbp+738h]; this
0x18001371e  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x180013725  mov     r9d, ebx; char *
0x180013728  mov     edx, 70h ; 'p'; void *
0x18001372d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013732  mov     eax, ebx
0x180013734  jmp     loc_180013999
0x180013739  cmp     ebx, 80070002h
0x18001373f  jz      short loc_18001374C
0x180013741  cmp     [rsp+830h+var_7F0], 0
0x180013746  jnz     loc_180013997
0x18001374c  lea     rcx, [rsp+830h+var_7D0]; struct wil::details::IFailureCallback *
0x180013751  call    ??0?$ActivityBase@VDatVPrepLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DatVPrepLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DatVPrepLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180013756  lea     rax, ??_7DoDatVPrepRS@DatVPrepTelemetry@@6B@; const DatVPrepTelemetry::DoDatVPrepRS::`vftable'
0x18001375d  lea     rcx, [rsp+830h+var_7D0]; this
0x180013762  mov     [rsp+830h+var_7D0], rax
0x180013767  call    ?StartActivity@DoDatVPrepRS@DatVPrepTelemetry@@QEAAXXZ; DatVPrepTelemetry::DoDatVPrepRS::StartActivity(void)
0x18001376c  mov     ebx, 104h
0x180013771  lea     rdx, [rsp+830h+cchSize]; lpcchSize
0x180013776  lea     rcx, [rbp+730h+ProfileDir]; lpProfileDir
0x18001377d  mov     [rsp+830h+cchSize], ebx
0x180013781  call    cs:__imp_GetProfilesDirectoryW
0x180013787  test    eax, eax
0x180013789  jnz     short loc_1800137A8
0x18001378b  mov     rcx, [rbp+738h]; this
0x180013792  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x180013799  lea     edx, [rax+78h]; void *
0x18001379c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800137a1  mov     ebx, eax
0x1800137a3  jmp     loc_18001396A
0x1800137a8  lea     r9, pszMore; "*"
0x1800137af  mov     rdx, rbx; cchPathOut
0x1800137b2  lea     r8, [rbp+730h+ProfileDir]; pszPathIn
0x1800137b9  lea     rcx, [rbp+730h+pszPathOut]; pszPathOut
0x1800137c0  call    cs:__imp_PathCchCombine
0x1800137c6  mov     ebx, eax
0x1800137c8  test    eax, eax
0x1800137ca  jns     short loc_1800137EC
0x1800137cc  mov     rcx, [rbp+738h]; this
0x1800137d3  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800137da  mov     r9d, eax; char *
0x1800137dd  mov     edx, 7Bh ; '{'; void *
0x1800137e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800137e7  jmp     loc_18001396A
0x1800137ec  xor     edx, edx; Val
0x1800137ee  lea     rcx, [rbp+730h+FindFileData]; void *
0x1800137f5  mov     r8d, 250h; Size
0x1800137fb  call    memset_0
0x180013800  mov     r14d, 1
0x180013806  mov     [rsp+830h+dwAdditionalFlags], 0; dwAdditionalFlags
0x18001380e  mov     r9d, r14d; fSearchOp
0x180013811  mov     [rsp+830h+lpSearchFilter], 0; lpSearchFilter
0x18001381a  mov     edx, r14d; fInfoLevelId
0x18001381d  lea     r8, [rbp+730h+FindFileData]; lpFindFileData
0x180013824  lea     rcx, [rbp+730h+pszPathOut]; lpFileName
0x18001382b  call    cs:__imp_FindFirstFileExW
0x180013831  mov     [rsp+830h+var_7E8], rax
0x180013836  mov     rbx, rax
0x180013839  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001383d  jnz     short loc_18001385D
0x18001383f  mov     rcx, [rbp+738h]; this
0x180013846  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x18001384d  lea     edx, [r14+7Eh]; void *
0x180013851  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013856  mov     ebx, eax
0x180013858  jmp     loc_180013960
0x18001385d  test    [rbp+730h+FindFileData], 10h
0x180013864  jz      short loc_1800138C3
0x180013866  or      r9d, 0FFFFFFFFh; cchCount2
0x18001386a  mov     dword ptr [rsp+830h+lpSearchFilter], r14d; bIgnoreCase
0x18001386f  or      edx, r9d; cchCount1
0x180013872  lea     r8, [rbp+730h+String2]; lpString2
0x180013879  lea     rcx, String1; "."
0x180013880  call    cs:__imp_CompareStringOrdinal
0x180013886  cmp     eax, 2
0x180013889  jz      short loc_1800138C3
0x18001388b  or      r9d, 0FFFFFFFFh; cchCount2
0x18001388f  mov     dword ptr [rsp+830h+lpSearchFilter], r14d; int
0x180013894  or      edx, r9d; cchCount1
0x180013897  lea     r8, [rbp+730h+String2]; lpString2
0x18001389e  lea     rcx, asc_1800AF450; ".."
0x1800138a5  call    cs:__imp_CompareStringOrdinal
0x1800138ab  cmp     eax, 2
0x1800138ae  jz      short loc_1800138C3
0x1800138b0  lea     rdx, [rbp+730h+String2]; pszMore
0x1800138b7  lea     rcx, [rbp+730h+ProfileDir]; pszPathIn
0x1800138be  call    ?ProcessProfileFolder@@YAJPEBG0@Z; ProcessProfileFolder(ushort const *,ushort const *)
0x1800138c3  lea     rdx, [rbp+730h+FindFileData]; lpFindFileData
0x1800138ca  mov     rcx, rbx; hFindFile
0x1800138cd  call    cs:__imp_FindNextFileW
0x1800138d3  test    eax, eax
0x1800138d5  jnz     short loc_18001385D
0x1800138d7  call    cs:__imp_GetLastError
0x1800138dd  cmp     eax, 12h
0x1800138e0  jz      short loc_180013914
0x1800138e2  test    eax, eax
0x1800138e4  jz      short loc_180013906
0x1800138e6  mov     rcx, [rbp+738h]; this
0x1800138ed  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800138f4  mov     r9d, eax; char *
0x1800138f7  mov     edx, 95h; void *
0x1800138fc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013901  jmp     loc_180013856
0x180013906  lea     rcx, [rsp+830h+var_7E8]
0x18001390b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180013910  xor     ebx, ebx
0x180013912  jmp     short loc_18001396A
0x180013914  mov     r9d, r14d
0x180013917  lea     r8, aDatvprepcomple; "DatVPrepComplete"
0x18001391e  lea     rdx, aSoftwareMicros_22; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180013925  lea     rcx, aCloudexperienc; "CloudExperienceHost"
0x18001392c  call    cs:__imp_SetPersistedRegistryBOOL
0x180013932  mov     ebx, eax
0x180013934  test    eax, eax
0x180013936  jle     short loc_180013941
0x180013938  movzx   ebx, ax
0x18001393b  or      ebx, 80070000h
0x180013941  test    ebx, ebx
0x180013943  jns     short loc_180013979
0x180013945  mov     rcx, [rbp+738h]; this
0x18001394c  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x180013953  mov     r9d, ebx; char *
0x180013956  mov     edx, 9Ah; void *
0x18001395b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013960  lea     rcx, [rsp+830h+var_7E8]
0x180013965  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18001396a  lea     rcx, [rsp+830h+var_7D0]; this
0x18001396f  call    ??1DoDatVPrepRS@DatVPrepTelemetry@@QEAA@XZ; DatVPrepTelemetry::DoDatVPrepRS::~DoDatVPrepRS(void)
0x180013974  jmp     loc_180013732
0x180013979  lea     rcx, [rsp+830h+var_7D0]
0x18001397e  call    ?Stop@?$ActivityBase@VDatVPrepLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DatVPrepLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180013983  lea     rcx, [rsp+830h+var_7E8]
0x180013988  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18001398d  lea     rcx, [rsp+830h+var_7D0]; this
0x180013992  call    ??1DoDatVPrepRS@DatVPrepTelemetry@@QEAA@XZ; DatVPrepTelemetry::DoDatVPrepRS::~DoDatVPrepRS(void)
0x180013997  xor     eax, eax
0x180013999  mov     rcx, [rbp+730h+var_10]
0x1800139a0  xor     rcx, rsp; StackCookie
0x1800139a3  call    __security_check_cookie
0x1800139a8  lea     r11, [rsp+830h+var_s0]
0x1800139b0  mov     rbx, [r11+10h]
0x1800139b4  mov     r14, [r11+18h]
0x1800139b8  mov     rsp, r11
0x1800139bb  pop     rbp
0x1800139bc  retn
```
