# FallbackLoadString(int,char * *,wchar_t * *)

- ea: `0x14000d9d0`
- end: `0x14000dc05`
- name: `?FallbackLoadString@@YAJHPEAPEADPEAPEA_W@Z`
- size: `565`
- prototype: `__int64 __fastcall(DWORD dwMessageId, va_list *Arguments, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x14000dc5c`

## callees

- `0x140002360`
- `0x1400067bc`
- `0x140006c50`
- `0x14000726c`
- `0x14000952c`
- `0x14000d9d0`
- `0x140015a08`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x14000dabf`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x14000dabf`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x14000da4b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x14000da4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000db32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000db32`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000da8a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000db03`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000da8a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000db03`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14000dbc6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14000dbe3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14000dbc6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14000dbe3`

## string_xrefs

- `0x14000da2d`: `%windir%\servicing\trustedinstaller.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FallbackLoadString(DWORD dwMessageId, va_list *Arguments, wchar_t **a3)
{
  HMODULE Library; // rax
  DWORD v7; // ebx
  wchar_t *v8; // rcx
  HMODULE v9; // rdx
  signed int LastError; // ebx
  int v11; // edx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int lpBuffer; // [rsp+20h] [rbp-60h]
  unsigned int v16[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v17; // [rsp+48h] [rbp-38h]
  WCHAR *v18; // [rsp+50h] [rbp-30h]
  char v19; // [rsp+58h] [rbp-28h]
  WCHAR Buffer[4]; // [rsp+60h] [rbp-20h] BYREF
  HMODULE phModule; // [rsp+68h] [rbp-18h] BYREF
  LPCWSTR lpLibFileName; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v17 = -2;
  *(_QWORD *)Buffer = 0;
  v18 = Buffer;
  v19 = 1;
  lpLibFileName = 0;
  Library = (HMODULE)vhTrustedInstaller;
  if ( vhTrustedInstaller
    || ((v7 = 0, (int)PathExpand((LPWSTR *)&lpLibFileName) < 0)
      ? (Library = (HMODULE)vhTrustedInstaller)
      : (HMODULE)(Library = LoadLibraryExW(lpLibFileName, 0, 0x22u), vhTrustedInstaller = Library),
        Library) )
  {
    v7 = FormatMessageW(0x900u, Library, dwMessageId, 0, Buffer, 0, Arguments);
    if ( v7 )
    {
      v8 = *(wchar_t **)Buffer;
      if ( *(_QWORD *)Buffer )
        goto LABEL_16;
    }
  }
  v9 = (HMODULE)vhSelfModule;
  if ( vhSelfModule
    || ((phModule = 0, !GetModuleHandleExW(6u, (LPCWSTR)FallbackLoadString, &phModule))
      ? (v9 = (HMODULE)vhSelfModule)
      : (HMODULE)(v9 = phModule, vhSelfModule = phModule),
        v9) )
  {
    v7 = FormatMessageW(0x900u, v9, dwMessageId, 0, Buffer, 0, Arguments);
  }
  if ( v7 )
  {
    v8 = *(wchar_t **)Buffer;
    if ( *(_QWORD *)Buffer )
    {
LABEL_16:
      *a3 = v8;
      *(_QWORD *)Buffer = 0;
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
      return 0;
    }
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting caption text");
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    else
      v12 = LastError;
    LODWORD(phModule) = v12;
    *(_QWORD *)v16 = &phModule;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v11,
      3,
      (unsigned int)": {0}",
      (__int64)v16);
  }
  if ( !LastError )
  {
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
    if ( *(_QWORD *)Buffer )
      LocalFree(*(HLOCAL *)Buffer);
    return 0;
  }
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\gui\\pkgmgr.cpp",
          (const char *)(unsigned int)LastError,
          lpBuffer);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  return v13;
}

```

## disassembly

```asm
0x14000d9d0  push    rbp
0x14000d9d2  push    rbx
0x14000d9d3  push    rsi
0x14000d9d4  push    rdi
0x14000d9d5  push    r14
0x14000d9d7  mov     rbp, rsp
0x14000d9da  sub     rsp, 80h
0x14000d9e1  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x14000d9e9  mov     rax, cs:__security_cookie
0x14000d9f0  xor     rax, rsp
0x14000d9f3  mov     [rbp+var_8], rax
0x14000d9f7  mov     rdi, r8
0x14000d9fa  mov     r14, rdx
0x14000d9fd  mov     esi, ecx
0x14000d9ff  mov     qword ptr [rbp+Buffer], 0
0x14000da07  lea     rax, [rbp+Buffer]
0x14000da0b  mov     [rbp+var_30], rax
0x14000da0f  mov     [rbp+var_28], 1
0x14000da13  mov     [rbp+lpLibFileName], 0
0x14000da1b  mov     rax, cs:?vhTrustedInstaller@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * vhTrustedInstaller
0x14000da22  test    rax, rax
0x14000da25  jnz     short loc_14000DA66
0x14000da27  xor     ebx, ebx
0x14000da29  lea     r8d, [rax+3]
0x14000da2d  lea     rdx, aWindirServicin; "%windir%\\servicing\\trustedinstaller.e"...
0x14000da34  lea     rcx, [rbp+lpLibFileName]
0x14000da38  call    PathExpand
0x14000da3d  test    eax, eax
0x14000da3f  js      short loc_14000DA5A
0x14000da41  xor     edx, edx; hFile
0x14000da43  lea     r8d, [rbx+22h]; dwFlags
0x14000da47  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x14000da4b  call    cs:__imp_LoadLibraryExW
0x14000da51  mov     cs:?vhTrustedInstaller@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhTrustedInstaller
0x14000da58  jmp     short loc_14000DA61
0x14000da5a  mov     rax, cs:?vhTrustedInstaller@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * vhTrustedInstaller
0x14000da61  test    rax, rax
0x14000da64  jz      short loc_14000DA9F
0x14000da66  mov     [rsp+80h+Arguments], r14; Arguments
0x14000da6b  mov     [rsp+80h+nSize], 0; nSize
0x14000da73  lea     rcx, [rbp+Buffer]
0x14000da77  mov     [rsp+80h+lpBuffer], rcx; lpBuffer
0x14000da7c  xor     r9d, r9d; dwLanguageId
0x14000da7f  mov     r8d, esi; dwMessageId
0x14000da82  mov     rdx, rax; lpSource
0x14000da85  mov     ecx, 900h; dwFlags
0x14000da8a  call    cs:__imp_FormatMessageW
0x14000da90  mov     ebx, eax
0x14000da92  test    eax, eax
0x14000da94  jz      short loc_14000DA9F
0x14000da96  mov     rcx, qword ptr [rbp+Buffer]
0x14000da9a  test    rcx, rcx
0x14000da9d  jnz     short loc_14000DB18
0x14000da9f  mov     rdx, cs:?vhSelfModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * vhSelfModule
0x14000daa6  test    rdx, rdx
0x14000daa9  jnz     short loc_14000DAE2
0x14000daab  mov     [rbp+phModule], rdx
0x14000daaf  lea     r8, [rbp+phModule]; phModule
0x14000dab3  lea     rdx, ?FallbackLoadString@@YAJHPEAPEADPEAPEA_W@Z; lpModuleName
0x14000daba  mov     ecx, 6; dwFlags
0x14000dabf  call    cs:__imp_GetModuleHandleExW
0x14000dac5  test    eax, eax
0x14000dac7  jz      short loc_14000DAD6
0x14000dac9  mov     rdx, [rbp+phModule]
0x14000dacd  mov     cs:?vhSelfModule@@3PEAUHINSTANCE__@@EA, rdx; HINSTANCE__ * vhSelfModule
0x14000dad4  jmp     short loc_14000DADD
0x14000dad6  mov     rdx, cs:?vhSelfModule@@3PEAUHINSTANCE__@@EA; lpSource
0x14000dadd  test    rdx, rdx
0x14000dae0  jz      short loc_14000DB0B
0x14000dae2  mov     [rsp+80h+Arguments], r14; Arguments
0x14000dae7  mov     [rsp+80h+nSize], 0; nSize
0x14000daef  lea     rax, [rbp+Buffer]
0x14000daf3  mov     [rsp+80h+lpBuffer], rax; lpBuffer
0x14000daf8  xor     r9d, r9d; dwLanguageId
0x14000dafb  mov     r8d, esi; dwMessageId
0x14000dafe  mov     ecx, 900h; dwFlags
0x14000db03  call    cs:__imp_FormatMessageW
0x14000db09  mov     ebx, eax
0x14000db0b  test    ebx, ebx
0x14000db0d  jz      short loc_14000DB32
0x14000db0f  mov     rcx, qword ptr [rbp+Buffer]
0x14000db13  test    rcx, rcx
0x14000db16  jz      short loc_14000DB32
0x14000db18  mov     [rdi], rcx
0x14000db1b  mov     qword ptr [rbp+Buffer], 0
0x14000db23  lea     rcx, [rbp+lpLibFileName]
0x14000db27  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000db2c  nop
0x14000db2d  jmp     loc_14000DBE9
0x14000db32  call    cs:__imp_GetLastError
0x14000db38  mov     ebx, eax
0x14000db3a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000db41  test    rcx, rcx
0x14000db44  jz      short loc_14000DB95
0x14000db46  lea     r9, aFailedGettingC; "Failed getting caption text"
0x14000db4d  xor     edx, edx
0x14000db4f  lea     r8d, [rdx+3]
0x14000db53  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000db58  test    ebx, ebx
0x14000db5a  jg      short loc_14000DB60
0x14000db5c  mov     eax, ebx
0x14000db5e  jmp     short loc_14000DB68
0x14000db60  movzx   eax, bx
0x14000db63  or      eax, 80070000h
0x14000db68  mov     dword ptr [rbp+phModule], eax
0x14000db6b  lea     rax, [rbp+phModule]
0x14000db6f  mov     qword ptr [rbp+var_40], rax
0x14000db73  lea     rax, [rbp+var_40]
0x14000db77  mov     [rsp+80h+lpBuffer], rax; unsigned int
0x14000db7c  lea     r9, a0; ": {0}"
0x14000db83  mov     r8d, 3
0x14000db89  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000db90  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000db95  test    ebx, ebx
0x14000db97  jz      short loc_14000DBD0
0x14000db99  mov     rcx, [rbp+28h]; this
0x14000db9d  mov     r9d, ebx; char *
0x14000dba0  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\pkgmgrshim\\gui\\pk"...
0x14000dba7  mov     edx, 4Fh ; 'O'; void *
0x14000dbac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000dbb1  mov     ebx, eax
0x14000dbb3  lea     rcx, [rbp+lpLibFileName]
0x14000dbb7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000dbbc  nop
0x14000dbbd  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x14000dbc1  test    rcx, rcx
0x14000dbc4  jz      short loc_14000DBCC
0x14000dbc6  call    cs:__imp_LocalFree
0x14000dbcc  mov     eax, ebx
0x14000dbce  jmp     short loc_14000DBEB
0x14000dbd0  lea     rcx, [rbp+lpLibFileName]
0x14000dbd4  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000dbd9  nop
0x14000dbda  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x14000dbde  test    rcx, rcx
0x14000dbe1  jz      short loc_14000DBE9
0x14000dbe3  call    cs:__imp_LocalFree
0x14000dbe9  xor     eax, eax
0x14000dbeb  mov     rcx, [rbp+var_8]
0x14000dbef  xor     rcx, rsp; StackCookie
0x14000dbf2  call    __security_check_cookie
0x14000dbf7  add     rsp, 80h
0x14000dbfe  pop     r14
0x14000dc00  pop     rdi
0x14000dc01  pop     rsi
0x14000dc02  pop     rbx
0x14000dc03  pop     rbp
0x14000dc04  retn
```
