# CUpdateEvaluator::InitializeBcp47(void)

- ea: `0x180126c84`
- end: `0x180126ec0`
- name: `?InitializeBcp47@CUpdateEvaluator@@AEAAJXZ`
- size: `572`
- prototype: `__int64 __fastcall(CUpdateEvaluator *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180127cd0`

## callees

- `0x18001255c`
- `0x18001270c`
- `0x1800692fc`
- `0x180126c84`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180126d4b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180126d90`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180126dd5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180126d4b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180126d90`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180126dd5`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180126e4c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180126e86`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180126e4c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180126e86`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180126cc0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180126d07`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180126cc0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180126d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126da8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126e96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126da8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126e96`

## string_xrefs

- `0x180126ce5`: `Bcp47Langs.dll is not available, extended language package filtering will not be available`
- `0x180126cb3`: `Bcp47Langs.dll`
- `0x180126d2c`: `api-ms-win-core-winrt-string-l1-1-0.dll is not available, extended language package filtering will not be available`
- `0x180126cfa`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x180126db4`: `Getting WindowsCreateString function failed`
- `0x180126d89`: `WindowsCreateString`
- `0x180126df9`: `Getting WindowsDeleteString function failed`
- `0x180126dce`: `WindowsDeleteString`

## pseudocode

```c
__int64 __fastcall CUpdateEvaluator::InitializeBcp47(CUpdateEvaluator *this)
{
  HMODULE Library; // rax
  HMODULE v4; // rax
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  FARPROC v7; // rax
  DWORD v8; // eax
  FARPROC v9; // rax
  DWORD v10; // eax
  HMODULE v11; // rcx
  HMODULE v12; // rcx

  if ( *((_BYTE *)this + 176) )
    return 0;
  *((_BYTE *)this + 176) = 1;
  Library = LoadLibraryExW(L"Bcp47Langs.dll", 0, 0x800u);
  if ( *((_QWORD *)this + 17) )
    goto LABEL_27;
  *((_QWORD *)this + 17) = Library;
  if ( !Library )
  {
    LogAdapter::TraceInfo<>("Bcp47Langs.dll is not available, extended language package filtering will not be available");
    return 1;
  }
  v4 = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  if ( *((_QWORD *)this + 19) )
  {
LABEL_27:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180126EBFLL);
  }
  *((_QWORD *)this + 19) = v4;
  if ( v4 )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)this + 17), "Bcp47GetDistance");
    *((_QWORD *)this + 18) = ProcAddress;
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      LogAdapter::TraceAtLevelWin32<unsigned long,>(3, LastError, "Getting Bcp47GetDistance function failed");
    }
    v7 = GetProcAddress(*((HMODULE *)this + 19), "WindowsCreateString");
    *((_QWORD *)this + 21) = v7;
    if ( !v7 )
    {
      v8 = GetLastError();
      LogAdapter::TraceAtLevelWin32<unsigned long,>(3, v8, "Getting WindowsCreateString function failed");
    }
    v9 = GetProcAddress(*((HMODULE *)this + 19), "WindowsDeleteString");
    *((_QWORD *)this + 20) = v9;
    if ( !v9 )
    {
      v10 = GetLastError();
      LogAdapter::TraceAtLevelWin32<unsigned long,>(3, v10, "Getting WindowsDeleteString function failed");
    }
    if ( *((_QWORD *)this + 18) && *((_QWORD *)this + 21) && *((_QWORD *)this + 20) )
      return 0;
    *((_QWORD *)this + 20) = 0;
    *((_QWORD *)this + 21) = 0;
    *((_QWORD *)this + 18) = 0;
    v11 = (HMODULE)*((_QWORD *)this + 19);
    if ( v11 )
    {
      if ( !FreeLibrary(v11) )
      {
        GetLastError();
        __fastfail(7u);
      }
      *((_QWORD *)this + 19) = 0;
    }
  }
  else
  {
    LogAdapter::TraceInfo<>(
      "api-ms-win-core-winrt-string-l1-1-0.dll is not available, extended language package filtering will not be available");
  }
  v12 = (HMODULE)*((_QWORD *)this + 17);
  if ( v12 )
  {
    if ( !FreeLibrary(v12) )
    {
      GetLastError();
      __fastfail(7u);
    }
    *((_QWORD *)this + 17) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180126c84  mov     [rsp+arg_0], rbx
0x180126c89  push    rsi
0x180126c8a  sub     rsp, 20h
0x180126c8e  xor     esi, esi
0x180126c90  mov     rbx, rcx
0x180126c93  cmp     [rcx+0B0h], sil
0x180126c9a  jz      short loc_180126CAA
0x180126c9c  xor     eax, eax
0x180126c9e  mov     rbx, [rsp+28h+arg_0]
0x180126ca3  add     rsp, 20h
0x180126ca7  pop     rsi
0x180126ca8  retn
0x180126caa  mov     byte ptr [rcx+0B0h], 1
0x180126cb1  xor     edx, edx; hFile
0x180126cb3  lea     rcx, aBcp47langsDll; "Bcp47Langs.dll"
0x180126cba  mov     r8d, 800h; dwFlags
0x180126cc0  call    cs:__imp_LoadLibraryExW
0x180126cc7  nop     dword ptr [rax+rax+00h]
0x180126ccc  cmp     [rbx+88h], rsi
0x180126cd3  jnz     loc_180126EB5
0x180126cd9  mov     [rbx+88h], rax
0x180126ce0  test    rax, rax
0x180126ce3  jnz     short loc_180126CF8
0x180126ce5  lea     rcx, aBcp47langsDllI_0; "Bcp47Langs.dll is not available, extend"...
0x180126cec  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180126cf1  mov     eax, 1
0x180126cf6  jmp     short loc_180126C9E
0x180126cf8  xor     edx, edx; hFile
0x180126cfa  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x180126d01  mov     r8d, 800h; dwFlags
0x180126d07  call    cs:__imp_LoadLibraryExW
0x180126d0e  nop     dword ptr [rax+rax+00h]
0x180126d13  cmp     [rbx+98h], rsi
0x180126d1a  jnz     loc_180126EB5
0x180126d20  mov     [rbx+98h], rax
0x180126d27  test    rax, rax
0x180126d2a  jnz     short loc_180126D3D
0x180126d2c  lea     rcx, aApiMsWinCoreWi_1; "api-ms-win-core-winrt-string-l1-1-0.dll"...
0x180126d33  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180126d38  jmp     loc_180126E76
0x180126d3d  mov     rcx, [rbx+88h]; hModule
0x180126d44  lea     rdx, aBcp47getdistan; "Bcp47GetDistance"
0x180126d4b  call    cs:__imp_GetProcAddress
0x180126d52  nop     dword ptr [rax+rax+00h]
0x180126d57  mov     [rbx+90h], rax
0x180126d5e  test    rax, rax
0x180126d61  jnz     short loc_180126D82
0x180126d63  call    cs:__imp_GetLastError
0x180126d6a  nop     dword ptr [rax+rax+00h]
0x180126d6f  lea     r8, aGettingBcp47ge_0; "Getting Bcp47GetDistance function faile"...
0x180126d76  mov     ecx, 3
0x180126d7b  mov     edx, eax
0x180126d7d  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x180126d82  mov     rcx, [rbx+98h]; hModule
0x180126d89  lea     rdx, aWindowscreates; "WindowsCreateString"
0x180126d90  call    cs:__imp_GetProcAddress
0x180126d97  nop     dword ptr [rax+rax+00h]
0x180126d9c  mov     [rbx+0A8h], rax
0x180126da3  test    rax, rax
0x180126da6  jnz     short loc_180126DC7
0x180126da8  call    cs:__imp_GetLastError
0x180126daf  nop     dword ptr [rax+rax+00h]
0x180126db4  lea     r8, aGettingWindows_1; "Getting WindowsCreateString function fa"...
0x180126dbb  mov     ecx, 3
0x180126dc0  mov     edx, eax
0x180126dc2  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x180126dc7  mov     rcx, [rbx+98h]; hModule
0x180126dce  lea     rdx, aWindowsdeletes; "WindowsDeleteString"
0x180126dd5  call    cs:__imp_GetProcAddress
0x180126ddc  nop     dword ptr [rax+rax+00h]
0x180126de1  mov     [rbx+0A0h], rax
0x180126de8  test    rax, rax
0x180126deb  jnz     short loc_180126E0C
0x180126ded  call    cs:__imp_GetLastError
0x180126df4  nop     dword ptr [rax+rax+00h]
0x180126df9  lea     r8, aGettingWindows; "Getting WindowsDeleteString function fa"...
0x180126e00  mov     ecx, 3
0x180126e05  mov     edx, eax
0x180126e07  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x180126e0c  cmp     [rbx+90h], rsi
0x180126e13  jz      short loc_180126E2B
0x180126e15  cmp     [rbx+0A8h], rsi
0x180126e1c  jz      short loc_180126E2B
0x180126e1e  cmp     [rbx+0A0h], rsi
0x180126e25  jnz     loc_180126C9C
0x180126e2b  mov     [rbx+0A0h], rsi
0x180126e32  mov     [rbx+0A8h], rsi
0x180126e39  mov     [rbx+90h], rsi
0x180126e40  mov     rcx, [rbx+98h]; hLibModule
0x180126e47  test    rcx, rcx
0x180126e4a  jz      short loc_180126E76
0x180126e4c  call    cs:__imp_FreeLibrary
0x180126e53  nop     dword ptr [rax+rax+00h]
0x180126e58  test    eax, eax
0x180126e5a  jnz     short loc_180126E6F
0x180126e5c  call    cs:__imp_GetLastError
0x180126e63  nop     dword ptr [rax+rax+00h]
0x180126e68  mov     ecx, 7
0x180126e6d  int     29h; Win8: RtlFailFast(ecx)
0x180126e6f  mov     [rbx+98h], rsi
0x180126e76  mov     rcx, [rbx+88h]; hLibModule
0x180126e7d  test    rcx, rcx
0x180126e80  jz      loc_180126CF1
0x180126e86  call    cs:__imp_FreeLibrary
0x180126e8d  nop     dword ptr [rax+rax+00h]
0x180126e92  test    eax, eax
0x180126e94  jnz     short loc_180126EA9
0x180126e96  call    cs:__imp_GetLastError
0x180126e9d  nop     dword ptr [rax+rax+00h]
0x180126ea2  mov     ecx, 7
0x180126ea7  int     29h; Win8: RtlFailFast(ecx)
0x180126ea9  mov     [rbx+88h], rsi
0x180126eb0  jmp     loc_180126CF1
0x180126eb5  mov     ecx, 0C00000E5h; int
0x180126eba  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
