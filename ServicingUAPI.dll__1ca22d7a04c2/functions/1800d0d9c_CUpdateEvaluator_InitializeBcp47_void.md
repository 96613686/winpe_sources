# CUpdateEvaluator::InitializeBcp47(void)

- ea: `0x1800d0d9c`
- end: `0x1800d0fd8`
- name: `?InitializeBcp47@CUpdateEvaluator@@AEAAJXZ`
- size: `572`
- prototype: `__int64 __fastcall(CUpdateEvaluator *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800d1d68`

## callees

- `0x18000aedc`
- `0x18001b9e4`
- `0x180027fc8`
- `0x1800d0d9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0fae`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800d0e63`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800d0ea8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800d0eed`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800d0e63`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800d0ea8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800d0eed`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800d0f64`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800d0f9e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800d0f64`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800d0f9e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800d0dd8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800d0e1f`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800d0dd8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800d0e1f`

## string_xrefs

- `0x1800d0e44`: `api-ms-win-core-winrt-string-l1-1-0.dll is not available, extended language package filtering will not be available`
- `0x1800d0e12`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x1800d0dfd`: `Bcp47Langs.dll is not available, extended language package filtering will not be available`
- `0x1800d0dcb`: `Bcp47Langs.dll`
- `0x1800d0ecc`: `Getting WindowsCreateString function failed`
- `0x1800d0ea1`: `WindowsCreateString`
- `0x1800d0f11`: `Getting WindowsDeleteString function failed`
- `0x1800d0ee6`: `WindowsDeleteString`

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
    JUMPOUT(0x1800D0FD7LL);
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
0x1800d0d9c  mov     [rsp+arg_0], rbx
0x1800d0da1  push    rsi
0x1800d0da2  sub     rsp, 20h
0x1800d0da6  xor     esi, esi
0x1800d0da8  mov     rbx, rcx
0x1800d0dab  cmp     [rcx+0B0h], sil
0x1800d0db2  jz      short loc_1800D0DC2
0x1800d0db4  xor     eax, eax
0x1800d0db6  mov     rbx, [rsp+28h+arg_0]
0x1800d0dbb  add     rsp, 20h
0x1800d0dbf  pop     rsi
0x1800d0dc0  retn
0x1800d0dc2  mov     byte ptr [rcx+0B0h], 1
0x1800d0dc9  xor     edx, edx; hFile
0x1800d0dcb  lea     rcx, aBcp47langsDll; "Bcp47Langs.dll"
0x1800d0dd2  mov     r8d, 800h; dwFlags
0x1800d0dd8  call    cs:__imp_LoadLibraryExW
0x1800d0ddf  nop     dword ptr [rax+rax+00h]
0x1800d0de4  cmp     [rbx+88h], rsi
0x1800d0deb  jnz     loc_1800D0FCD
0x1800d0df1  mov     [rbx+88h], rax
0x1800d0df8  test    rax, rax
0x1800d0dfb  jnz     short loc_1800D0E10
0x1800d0dfd  lea     rcx, aBcp47langsDllI_0; "Bcp47Langs.dll is not available, extend"...
0x1800d0e04  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800d0e09  mov     eax, 1
0x1800d0e0e  jmp     short loc_1800D0DB6
0x1800d0e10  xor     edx, edx; hFile
0x1800d0e12  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800d0e19  mov     r8d, 800h; dwFlags
0x1800d0e1f  call    cs:__imp_LoadLibraryExW
0x1800d0e26  nop     dword ptr [rax+rax+00h]
0x1800d0e2b  cmp     [rbx+98h], rsi
0x1800d0e32  jnz     loc_1800D0FCD
0x1800d0e38  mov     [rbx+98h], rax
0x1800d0e3f  test    rax, rax
0x1800d0e42  jnz     short loc_1800D0E55
0x1800d0e44  lea     rcx, aApiMsWinCoreWi_1; "api-ms-win-core-winrt-string-l1-1-0.dll"...
0x1800d0e4b  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800d0e50  jmp     loc_1800D0F8E
0x1800d0e55  mov     rcx, [rbx+88h]; hModule
0x1800d0e5c  lea     rdx, aBcp47getdistan; "Bcp47GetDistance"
0x1800d0e63  call    cs:__imp_GetProcAddress
0x1800d0e6a  nop     dword ptr [rax+rax+00h]
0x1800d0e6f  mov     [rbx+90h], rax
0x1800d0e76  test    rax, rax
0x1800d0e79  jnz     short loc_1800D0E9A
0x1800d0e7b  call    cs:__imp_GetLastError
0x1800d0e82  nop     dword ptr [rax+rax+00h]
0x1800d0e87  lea     r8, aGettingBcp47ge_0; "Getting Bcp47GetDistance function faile"...
0x1800d0e8e  mov     ecx, 3
0x1800d0e93  mov     edx, eax
0x1800d0e95  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x1800d0e9a  mov     rcx, [rbx+98h]; hModule
0x1800d0ea1  lea     rdx, aWindowscreates; "WindowsCreateString"
0x1800d0ea8  call    cs:__imp_GetProcAddress
0x1800d0eaf  nop     dword ptr [rax+rax+00h]
0x1800d0eb4  mov     [rbx+0A8h], rax
0x1800d0ebb  test    rax, rax
0x1800d0ebe  jnz     short loc_1800D0EDF
0x1800d0ec0  call    cs:__imp_GetLastError
0x1800d0ec7  nop     dword ptr [rax+rax+00h]
0x1800d0ecc  lea     r8, aGettingWindows_1; "Getting WindowsCreateString function fa"...
0x1800d0ed3  mov     ecx, 3
0x1800d0ed8  mov     edx, eax
0x1800d0eda  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x1800d0edf  mov     rcx, [rbx+98h]; hModule
0x1800d0ee6  lea     rdx, aWindowsdeletes; "WindowsDeleteString"
0x1800d0eed  call    cs:__imp_GetProcAddress
0x1800d0ef4  nop     dword ptr [rax+rax+00h]
0x1800d0ef9  mov     [rbx+0A0h], rax
0x1800d0f00  test    rax, rax
0x1800d0f03  jnz     short loc_1800D0F24
0x1800d0f05  call    cs:__imp_GetLastError
0x1800d0f0c  nop     dword ptr [rax+rax+00h]
0x1800d0f11  lea     r8, aGettingWindows; "Getting WindowsDeleteString function fa"...
0x1800d0f18  mov     ecx, 3
0x1800d0f1d  mov     edx, eax
0x1800d0f1f  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x1800d0f24  cmp     [rbx+90h], rsi
0x1800d0f2b  jz      short loc_1800D0F43
0x1800d0f2d  cmp     [rbx+0A8h], rsi
0x1800d0f34  jz      short loc_1800D0F43
0x1800d0f36  cmp     [rbx+0A0h], rsi
0x1800d0f3d  jnz     loc_1800D0DB4
0x1800d0f43  mov     [rbx+0A0h], rsi
0x1800d0f4a  mov     [rbx+0A8h], rsi
0x1800d0f51  mov     [rbx+90h], rsi
0x1800d0f58  mov     rcx, [rbx+98h]; hLibModule
0x1800d0f5f  test    rcx, rcx
0x1800d0f62  jz      short loc_1800D0F8E
0x1800d0f64  call    cs:__imp_FreeLibrary
0x1800d0f6b  nop     dword ptr [rax+rax+00h]
0x1800d0f70  test    eax, eax
0x1800d0f72  jnz     short loc_1800D0F87
0x1800d0f74  call    cs:__imp_GetLastError
0x1800d0f7b  nop     dword ptr [rax+rax+00h]
0x1800d0f80  mov     ecx, 7
0x1800d0f85  int     29h; Win8: RtlFailFast(ecx)
0x1800d0f87  mov     [rbx+98h], rsi
0x1800d0f8e  mov     rcx, [rbx+88h]; hLibModule
0x1800d0f95  test    rcx, rcx
0x1800d0f98  jz      loc_1800D0E09
0x1800d0f9e  call    cs:__imp_FreeLibrary
0x1800d0fa5  nop     dword ptr [rax+rax+00h]
0x1800d0faa  test    eax, eax
0x1800d0fac  jnz     short loc_1800D0FC1
0x1800d0fae  call    cs:__imp_GetLastError
0x1800d0fb5  nop     dword ptr [rax+rax+00h]
0x1800d0fba  mov     ecx, 7
0x1800d0fbf  int     29h; Win8: RtlFailFast(ecx)
0x1800d0fc1  mov     [rbx+88h], rsi
0x1800d0fc8  jmp     loc_1800D0E09
0x1800d0fcd  mov     ecx, 0C00000E5h; int
0x1800d0fd2  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
