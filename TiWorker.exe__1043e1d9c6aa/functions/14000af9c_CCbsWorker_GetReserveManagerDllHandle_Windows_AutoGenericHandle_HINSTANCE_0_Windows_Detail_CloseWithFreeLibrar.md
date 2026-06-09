# CCbsWorker::GetReserveManagerDllHandle(Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *)

- ea: `0x14000af9c`
- end: `0x14000b0df`
- name: `?GetReserveManagerDllHandle@CCbsWorker@@AEAAJPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x14000b2f8`

## callees

- `0x140006514`
- `0x140006d44`
- `0x14000af9c`
- `0x14000e328`
- `0x140016bf8`
- `0x1400177d8`
- `0x140018740`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x14000b04c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x14000b04c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b063`

## string_xrefs

- `0x14000b0ae`: `Error: Not reversed from impersonation on func: %s`
- `0x14000b022`: `ReserveManager.dll`
- `0x14000afe2`: `Failed to get module path`
- `0x14000b005`: `Failed to ensure servicing stack path ended with a backslash: %ws`
- `0x14000b039`: `Failed to concat full path to dll path`
- `0x14000b07a`: `Failed to load reserve manager dll`
- `0x14000b0a4`: `CCbsWorker::GetReserveManagerDllHandle`

## pseudocode

```c
__int64 __fastcall CCbsWorker::GetReserveManagerDllHandle(__int64 a1, _QWORD *a2)
{
  signed int v3; // ebx
  const char *v4; // r9
  int ModulePath; // eax
  __int64 v6; // rdx
  HMODULE Library; // rax
  signed int LastError; // eax
  LPCWSTR lpLibFileName[3]; // [rsp+30h] [rbp-18h] BYREF

  lpLibFileName[0] = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    v4 = "No auto handle specified";
LABEL_15:
    v6 = (unsigned int)v3;
    goto LABEL_16;
  }
  ModulePath = PathGetModulePath((__int64)lpLibFileName);
  v3 = ModulePath;
  if ( ModulePath >= 0 )
  {
    v3 = SczEnsureBackslashTerminated(lpLibFileName);
    if ( v3 < 0 )
    {
      CBSWdsLog(
        0x4000000,
        (unsigned int)v3,
        1,
        "Failed to ensure servicing stack path ended with a backslash: %ws",
        lpLibFileName[0]);
      goto LABEL_17;
    }
    ModulePath = SczAllocConcatSz(lpLibFileName, L"ReserveManager.dll");
    v3 = ModulePath;
    if ( ModulePath >= 0 )
    {
      Library = LoadLibraryExW(lpLibFileName[0], 0, 0);
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
        a2,
        Library);
      if ( *a2 )
        goto LABEL_17;
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v4 = "Failed to load reserve manager dll";
      if ( v3 >= 0 )
        v3 = -2147467259;
      goto LABEL_15;
    }
    v4 = "Failed to concat full path to dll path";
  }
  else
  {
    v4 = "Failed to get module path";
  }
  v6 = (unsigned int)ModulePath;
LABEL_16:
  CBSWdsLog(0x4000000, v6, 1, v4);
LABEL_17:
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(
      0x4000000,
      0,
      0,
      "Error: Not reversed from impersonation on func: %s",
      "CCbsWorker::GetReserveManagerDllHandle");
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpLibFileName);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000af9c  mov     [rsp+arg_0], rbx
0x14000afa1  mov     [rsp+arg_10], rsi
0x14000afa6  push    rdi
0x14000afa7  sub     rsp, 40h
0x14000afab  mov     [rsp+48h+lpLibFileName], 0
0x14000afb4  mov     rdi, rdx
0x14000afb7  mov     esi, 4000000h
0x14000afbc  test    rdx, rdx
0x14000afbf  jnz     short loc_14000AFD2
0x14000afc1  mov     ebx, 80070057h
0x14000afc6  lea     r9, aNoAutoHandleSp; "No auto handle specified"
0x14000afcd  jmp     loc_14000B089
0x14000afd2  lea     rcx, [rsp+48h+lpLibFileName]
0x14000afd7  call    PathGetModulePath
0x14000afdc  mov     ebx, eax
0x14000afde  test    eax, eax
0x14000afe0  jns     short loc_14000AFF0
0x14000afe2  lea     r9, aFailedToGetMod; "Failed to get module path"
0x14000afe9  mov     edx, eax
0x14000afeb  jmp     loc_14000B08B
0x14000aff0  lea     rcx, [rsp+48h+lpLibFileName]
0x14000aff5  call    SczEnsureBackslashTerminated
0x14000affa  mov     ebx, eax
0x14000affc  test    eax, eax
0x14000affe  jns     short loc_14000B022
0x14000b000  mov     rax, [rsp+48h+lpLibFileName]
0x14000b005  lea     r9, aFailedToEnsure; "Failed to ensure servicing stack path e"...
0x14000b00c  mov     r8d, 1
0x14000b012  mov     [rsp+48h+var_28], rax
0x14000b017  mov     edx, ebx
0x14000b019  mov     ecx, esi
0x14000b01b  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b020  jmp     short loc_14000B098
0x14000b022  lea     rdx, aReservemanager; "ReserveManager.dll"
0x14000b029  lea     rcx, [rsp+48h+lpLibFileName]
0x14000b02e  call    SczAllocConcatSz
0x14000b033  mov     ebx, eax
0x14000b035  test    eax, eax
0x14000b037  jns     short loc_14000B042
0x14000b039  lea     r9, aFailedToConcat_1; "Failed to concat full path to dll path"
0x14000b040  jmp     short loc_14000AFE9
0x14000b042  mov     rcx, [rsp+48h+lpLibFileName]; lpLibFileName
0x14000b047  xor     r8d, r8d; dwFlags
0x14000b04a  xor     edx, edx; hFile
0x14000b04c  call    cs:__imp_LoadLibraryExW
0x14000b052  mov     rdx, rax
0x14000b055  mov     rcx, rdi
0x14000b058  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x14000b05d  cmp     qword ptr [rdi], 0
0x14000b061  jnz     short loc_14000B098
0x14000b063  call    cs:__imp_GetLastError
0x14000b069  mov     ebx, eax
0x14000b06b  test    eax, eax
0x14000b06d  jle     short loc_14000B078
0x14000b06f  movzx   ebx, ax
0x14000b072  or      ebx, 80070000h
0x14000b078  test    ebx, ebx
0x14000b07a  lea     r9, aFailedToLoadRe; "Failed to load reserve manager dll"
0x14000b081  mov     eax, 80004005h
0x14000b086  cmovns  ebx, eax
0x14000b089  mov     edx, ebx
0x14000b08b  mov     r8d, 1
0x14000b091  mov     ecx, esi
0x14000b093  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b098  mov     eax, gs:179Ch
0x14000b0a0  test    eax, eax
0x14000b0a2  jz      short loc_14000B0C3
0x14000b0a4  lea     rax, aCcbsworkerGetr; "CCbsWorker::GetReserveManagerDllHandle"
0x14000b0ab  xor     r8d, r8d
0x14000b0ae  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000b0b5  mov     [rsp+48h+var_28], rax
0x14000b0ba  xor     edx, edx
0x14000b0bc  mov     ecx, esi
0x14000b0be  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b0c3  lea     rcx, [rsp+48h+lpLibFileName]
0x14000b0c8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000b0cd  mov     rsi, [rsp+48h+arg_10]
0x14000b0d2  mov     eax, ebx
0x14000b0d4  mov     rbx, [rsp+48h+arg_0]
0x14000b0d9  add     rsp, 40h
0x14000b0dd  pop     rdi
0x14000b0de  retn
```
