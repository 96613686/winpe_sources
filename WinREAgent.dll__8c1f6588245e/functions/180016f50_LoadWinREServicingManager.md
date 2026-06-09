# LoadWinREServicingManager

- ea: `0x180016f50`
- end: `0x1800170c0`
- name: `LoadWinREServicingManager`
- size: `368`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800164f0`
- `0x180016f50`
- `0x18001b044`
- `0x180037344`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180016fa9`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180016fa9`
- `KERNEL32!GetLastError` at `0x180016fb3`
- `KERNEL32!GetLastError` at `0x180016ff5`
- `KERNEL32!GetLastError` at `0x180016fb3`
- `KERNEL32!GetLastError` at `0x180016ff5`

## string_xrefs

- `0x180016fc7`: `Failed to get system Windows directory`
- `0x180016fdb`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180017055`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x180016fe2`: `WinREAgent::LoadWinREServicingManager`
- `0x18001705c`: `WinREAgent::LoadWinREServicingManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LoadWinREServicingManager(_QWORD *a1)
{
  signed int LastError; // eax
  signed int v3; // eax
  unsigned int v4; // ebx
  struct WinREAgent::WinREServicingManager **v5; // rax
  __int64 v6; // rax
  void **v8; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v9 = 0;
  v8 = &RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::`vftable';
  memset_0(Buffer, 0, 0x20Au);
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    v5 = (struct WinREAgent::WinREServicingManager **)((__int64 (__fastcall *)(void ***))v8[1])(&v8);
    v4 = WinREAgent::WinREServicingManager::Load(Buffer[0], v5);
    if ( (v4 & 0x80000000) == 0 )
    {
      v6 = v9;
      v9 = 0;
      *a1 = v6;
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        v4,
        "WinREAgent::LoadWinREServicingManager",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        123,
        L"Failed to load servicing manager");
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "WinREAgent::LoadWinREServicingManager",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
      119,
      L"Failed to get system Windows directory");
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  v8 = &RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::`vftable';
  RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::Release(&v8);
  return v4;
}

```

## disassembly

```asm
0x180016f50  push    rbp
0x180016f52  push    rbx
0x180016f53  push    rsi
0x180016f54  push    rdi
0x180016f55  lea     rbp, [rsp-168h]
0x180016f5d  sub     rsp, 268h
0x180016f64  mov     rax, cs:__security_cookie
0x180016f6b  xor     rax, rsp
0x180016f6e  mov     [rbp+180h+var_30], rax
0x180016f75  mov     rdi, rcx
0x180016f78  mov     [rsp+280h+var_248], 0
0x180016f81  lea     rsi, ??_7?$CAutoRelease@PEAVWinREServicingManager@WinREAgent@@@RAII@@6B@; const RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::`vftable'
0x180016f88  mov     [rsp+280h+var_250], rsi
0x180016f8d  xor     edx, edx; Val
0x180016f8f  mov     r8d, 20Ah; Size
0x180016f95  lea     rcx, [rsp+280h+Buffer]; void *
0x180016f9a  call    memset_0
0x180016f9f  mov     edx, 104h; uSize
0x180016fa4  lea     rcx, [rsp+280h+Buffer]; lpBuffer
0x180016fa9  call    cs:__imp_GetSystemWindowsDirectoryW
0x180016faf  test    eax, eax
0x180016fb1  jnz     short loc_18001701B
0x180016fb3  call    cs:__imp_GetLastError
0x180016fb9  mov     edi, 80070000h
0x180016fbe  test    eax, eax
0x180016fc0  jle     short loc_180016FC7
0x180016fc2  movzx   eax, ax
0x180016fc5  or      eax, edi
0x180016fc7  lea     rcx, aFailedToGetSys_0; "Failed to get system Windows directory"
0x180016fce  mov     [rsp+280h+var_258], rcx
0x180016fd3  mov     [rsp+280h+var_260], 77h ; 'w'
0x180016fdb  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180016fe2  lea     r8, aWinreagentLoad; "WinREAgent::LoadWinREServicingManager"
0x180016fe9  mov     edx, eax
0x180016feb  mov     ecx, 2
0x180016ff0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180016ff5  call    cs:__imp_GetLastError
0x180016ffb  mov     ebx, eax
0x180016ffd  test    eax, eax
0x180016fff  jle     short loc_180017006
0x180017001  movzx   ebx, ax
0x180017004  or      ebx, edi
0x180017006  mov     [rsp+280h+var_250], rsi
0x18001700b  lea     rcx, [rsp+280h+var_250]
0x180017010  call    ?Release@?$CAutoRelease@PEAVWinREServicingManager@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::Release(void)
0x180017015  nop
0x180017016  jmp     loc_1800170A3
0x18001701b  mov     rax, [rsp+280h+var_250]
0x180017020  lea     rcx, [rsp+280h+var_250]
0x180017025  mov     rax, [rax+8]
0x180017029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001702e  mov     rdx, rax; struct WinREAgent::WinREServicingManager **
0x180017031  movzx   ecx, [rsp+280h+Buffer]; unsigned __int16
0x180017036  call    ?Load@WinREServicingManager@WinREAgent@@SAJGPEAPEAV12@@Z; WinREAgent::WinREServicingManager::Load(ushort,WinREAgent::WinREServicingManager * *)
0x18001703b  mov     ebx, eax
0x18001703d  test    eax, eax
0x18001703f  jns     short loc_180017082
0x180017041  lea     rax, aFailedToLoadSe; "Failed to load servicing manager"
0x180017048  mov     [rsp+280h+var_258], rax
0x18001704d  mov     [rsp+280h+var_260], 7Bh ; '{'
0x180017055  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001705c  lea     r8, aWinreagentLoad; "WinREAgent::LoadWinREServicingManager"
0x180017063  mov     edx, ebx
0x180017065  mov     ecx, 2
0x18001706a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001706f  nop
0x180017070  mov     [rsp+280h+var_250], rsi
0x180017075  lea     rcx, [rsp+280h+var_250]
0x18001707a  call    ?Release@?$CAutoRelease@PEAVWinREServicingManager@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::Release(void)
0x18001707f  nop
0x180017080  jmp     short loc_1800170A3
0x180017082  mov     rax, [rsp+280h+var_248]
0x180017087  mov     [rsp+280h+var_248], 0
0x180017090  mov     [rdi], rax
0x180017093  mov     [rsp+280h+var_250], rsi
0x180017098  lea     rcx, [rsp+280h+var_250]
0x18001709d  call    ?Release@?$CAutoRelease@PEAVWinREServicingManager@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::Release(void)
0x1800170a2  nop
0x1800170a3  mov     eax, ebx
0x1800170a5  mov     rcx, [rbp+180h+var_30]
0x1800170ac  xor     rcx, rsp; StackCookie
0x1800170af  call    __security_check_cookie
0x1800170b4  add     rsp, 268h
0x1800170bb  pop     rdi
0x1800170bc  pop     rsi
0x1800170bd  pop     rbx
0x1800170be  pop     rbp
0x1800170bf  retn
```
