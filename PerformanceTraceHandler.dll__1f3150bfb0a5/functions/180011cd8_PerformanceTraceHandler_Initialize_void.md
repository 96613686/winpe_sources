# PerformanceTraceHandler::Initialize(void)

- ea: `0x180011cd8`
- end: `0x180011e26`
- name: `?Initialize@PerformanceTraceHandler@@AEAAJXZ`
- size: `334`
- prototype: `__int64 __fastcall(PerformanceTraceHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012890`

## callees

- `0x180007f1c`
- `0x180007f3c`
- `0x18000b628`
- `0x180011000`
- `0x180011bd4`
- `0x180011cd8`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011d85`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011d85`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011db3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011db3`

## string_xrefs

- `0x180011d78`: `utcapi.dll`
- `0x180011da9`: `UtcCreateSessionHandle`
- `0x180011ddb`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::Initialize(PerformanceTraceHandler *this)
{
  HMODULE Library; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  int LastError; // eax
  FARPROC ProcAddress; // rax
  int IsActive; // ebx
  __int64 v8; // rdx
  _QWORD v10[18]; // [rsp+20h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  memset(v10, 0, 112);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper((Microsoft::Diagnostics::UtcApiWrapper *)v10);
  Library = LoadLibraryExW(L"utcapi.dll", 0, 0x800u);
  *((_QWORD *)this + 8) = Library;
  if ( !Library )
  {
    v4 = 88;
LABEL_3:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v4,
                  (unsigned int)"onecore\\internal\\base\\inc\\utcapiwrapperex.h",
                  v3);
    goto LABEL_7;
  }
  ProcAddress = GetProcAddress(Library, "UtcCreateSessionHandle");
  if ( !ProcAddress )
  {
    v4 = 91;
    goto LABEL_3;
  }
  LastError = ((__int64 (__fastcall *)(char *))ProcAddress)((char *)this + 56);
LABEL_7:
  IsActive = LastError;
  if ( LastError < 0 )
  {
    v8 = 133;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
      (const char *)(unsigned int)IsActive,
      v10[0]);
    return (unsigned int)IsActive;
  }
  IsActive = PerformanceTraceHandler::EnsureScenarioIsActive(this);
  if ( IsActive < 0 )
  {
    v8 = 135;
    goto LABEL_9;
  }
  IsActive = PerformanceTraceHandler::InitalizeTraceFolderPath(this);
  if ( IsActive < 0 )
  {
    v8 = 136;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x180011cd8  push    rbp
0x180011cda  push    rbx
0x180011cdb  push    rsi
0x180011cdc  push    rdi
0x180011cdd  lea     rbp, [rsp-3Fh]
0x180011ce2  sub     rsp, 98h
0x180011ce9  xor     esi, esi
0x180011ceb  mov     rdi, rcx
0x180011cee  mov     [rbp+57h+var_90], rsi
0x180011cf2  mov     [rbp+57h+var_88], rsi
0x180011cf6  mov     [rbp+57h+var_80], rsi
0x180011cfa  mov     [rbp+57h+var_78], rsi
0x180011cfe  mov     [rbp+57h+var_70], rsi
0x180011d02  mov     [rbp+57h+var_68], rsi
0x180011d06  mov     [rbp+57h+var_60], rsi
0x180011d0a  mov     [rbp+57h+var_58], rsi
0x180011d0e  mov     [rbp+57h+var_50], rsi
0x180011d12  mov     [rbp+57h+var_48], rsi
0x180011d16  mov     [rbp+57h+var_40], rsi
0x180011d1a  mov     [rbp+57h+var_38], rsi
0x180011d1e  mov     [rbp+57h+var_30], rsi
0x180011d22  mov     [rbp+57h+var_28], rsi
0x180011d26  mov     [rcx+38h], rsi
0x180011d2a  mov     [rcx+40h], rsi
0x180011d2e  mov     [rcx+48h], rsi
0x180011d32  mov     [rcx+50h], rsi
0x180011d36  mov     [rcx+58h], rsi
0x180011d3a  mov     [rcx+60h], rsi
0x180011d3e  mov     [rcx+68h], rsi
0x180011d42  mov     [rcx+70h], rsi
0x180011d46  mov     [rcx+78h], rsi
0x180011d4a  mov     [rcx+80h], rsi
0x180011d51  mov     [rcx+88h], rsi
0x180011d58  mov     [rcx+90h], rsi
0x180011d5f  mov     [rcx+98h], rsi
0x180011d66  mov     [rcx+0A0h], rsi
0x180011d6d  lea     rcx, [rbp+57h+var_90]; this
0x180011d71  call    ??1UtcApiWrapper@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper(void)
0x180011d76  xor     edx, edx; hFile
0x180011d78  lea     rcx, aUtcapiDll; "utcapi.dll"
0x180011d7f  mov     r8d, 800h; dwFlags
0x180011d85  call    cs:__imp_LoadLibraryExW
0x180011d8b  mov     [rdi+40h], rax
0x180011d8f  test    rax, rax
0x180011d92  jnz     short loc_180011DA9
0x180011d94  lea     edx, [rsi+58h]; void *
0x180011d97  mov     rcx, [rbp+5Fh]; this
0x180011d9b  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\utcapiwra"...
0x180011da2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011da7  jmp     short loc_180011DCC
0x180011da9  lea     rdx, aUtccreatesessi; "UtcCreateSessionHandle"
0x180011db0  mov     rcx, rax; hModule
0x180011db3  call    cs:__imp_GetProcAddress
0x180011db9  test    rax, rax
0x180011dbc  jnz     short loc_180011DC3
0x180011dbe  lea     edx, [rax+5Bh]
0x180011dc1  jmp     short loc_180011D97
0x180011dc3  lea     rcx, [rdi+38h]
0x180011dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dcc  mov     ebx, eax
0x180011dce  test    eax, eax
0x180011dd0  jns     short loc_180011DEE
0x180011dd2  mov     edx, 85h; void *
0x180011dd7  mov     rcx, [rbp+5Fh]; this
0x180011ddb  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x180011de2  mov     r9d, ebx; char *
0x180011de5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011dea  mov     eax, ebx
0x180011dec  jmp     short loc_180011E1A
0x180011dee  mov     rcx, rdi; this
0x180011df1  call    ?EnsureScenarioIsActive@PerformanceTraceHandler@@AEAAJXZ; PerformanceTraceHandler::EnsureScenarioIsActive(void)
0x180011df6  mov     ebx, eax
0x180011df8  test    eax, eax
0x180011dfa  jns     short loc_180011E03
0x180011dfc  mov     edx, 87h
0x180011e01  jmp     short loc_180011DD7
0x180011e03  mov     rcx, rdi; this
0x180011e06  call    ?InitalizeTraceFolderPath@PerformanceTraceHandler@@AEAAJXZ; PerformanceTraceHandler::InitalizeTraceFolderPath(void)
0x180011e0b  mov     ebx, eax
0x180011e0d  test    eax, eax
0x180011e0f  jns     short loc_180011E18
0x180011e11  mov     edx, 88h
0x180011e16  jmp     short loc_180011DD7
0x180011e18  xor     eax, eax
0x180011e1a  add     rsp, 98h
0x180011e21  pop     rdi
0x180011e22  pop     rsi
0x180011e23  pop     rbx
0x180011e24  pop     rbp
0x180011e25  retn
```
