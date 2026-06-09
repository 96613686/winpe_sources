# DirectorySizeFileCallback

- ea: `0x180042680`
- end: `0x18004284e`
- name: `DirectorySizeFileCallback`
- size: `462`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001e51c`
- `0x1800293a0`
- `0x180041a74`
- `0x180041de8`
- `0x180042680`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800427f8`
- `KERNEL32!GetLastError` at `0x1800427f8`
- `KERNEL32!GetCompressedFileSizeW` at `0x1800427e4`
- `KERNEL32!GetCompressedFileSizeW` at `0x1800427e4`

## pseudocode

```c
__int64 __fastcall DirectorySizeFileCallback(const WCHAR *a1, __int64 a2, unsigned int *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-30h]
  int v11[2]; // [rsp+30h] [rbp-20h] BYREF
  int v12; // [rsp+38h] [rbp-18h] BYREF
  DWORD FileSizeHigh[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  if ( !a1 )
  {
    v12 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file specified");
      *(_QWORD *)v11 = &v12;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v11);
    }
    v6 = 203;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
      (const char *)0x80070057LL,
      v10);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v12 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No find data specified");
      *(_QWORD *)v11 = &v12;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v11);
    }
    v6 = 204;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v12 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No context specified");
      *(_QWORD *)v11 = &v12;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v11);
    }
    v6 = 205;
    goto LABEL_5;
  }
  FileSizeHigh[1] = 0;
  FileSizeHigh[0] = GetCompressedFileSizeW(a1, &FileSizeHigh[1]);
  if ( FileSizeHigh[0] == -1 && GetLastError() )
  {
    FileSizeHigh[1] = *(_DWORD *)(a2 + 28);
    FileSizeHigh[0] = *(_DWORD *)(a2 + 32);
  }
  *((_QWORD *)a3 + 1) += *a3
                       + *(_QWORD *)FileSizeHigh
                       - 1LL
                       - ((unsigned __int64)*a3 + *(_QWORD *)FileSizeHigh - 1LL) % *a3;
  return 0;
}

```

## disassembly

```asm
0x180042680  mov     [rsp-8+arg_8], rbx
0x180042685  mov     [rsp-8+arg_18], rdi
0x18004268a  push    rbp
0x18004268b  mov     rbp, rsp
0x18004268e  sub     rsp, 50h
0x180042692  mov     rax, cs:__security_cookie
0x180042699  xor     rax, rsp
0x18004269c  mov     [rbp+var_8], rax
0x1800426a0  mov     rdi, r8
0x1800426a3  mov     rbx, rdx
0x1800426a6  test    rcx, rcx
0x1800426a9  jnz     short loc_18004271B
0x1800426ab  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800426b2  mov     ebx, 80070057h
0x1800426b7  mov     [rbp+var_18], ebx
0x1800426ba  test    rcx, rcx
0x1800426bd  jz      short loc_1800426FC
0x1800426bf  mov     edi, 3
0x1800426c4  lea     r9, aNoFileSpecifie; "No file specified"
0x1800426cb  mov     r8d, edi
0x1800426ce  xor     edx, edx
0x1800426d0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800426d5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800426dc  lea     rax, [rbp+var_18]
0x1800426e0  mov     qword ptr [rbp+var_20], rax
0x1800426e4  lea     r9, asc_1800AFB70; ": {}"
0x1800426eb  lea     rax, [rbp+var_20]
0x1800426ef  mov     r8d, edi
0x1800426f2  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800426f7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800426fc  mov     edx, 0CBh; void *
0x180042701  mov     rcx, [rbp+8]; this
0x180042705  lea     r8, aOnecoreBaseCbs_12; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x18004270c  mov     r9d, ebx; char *
0x18004270f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042714  mov     eax, ebx
0x180042716  jmp     loc_180042831
0x18004271b  test    rbx, rbx
0x18004271e  jnz     short loc_180042778
0x180042720  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042727  mov     ebx, 80070057h
0x18004272c  mov     [rbp+var_18], ebx
0x18004272f  test    rcx, rcx
0x180042732  jz      short loc_180042771
0x180042734  mov     edi, 3
0x180042739  lea     r9, aNoFindDataSpec; "No find data specified"
0x180042740  mov     r8d, edi
0x180042743  xor     edx, edx
0x180042745  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004274a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042751  lea     rax, [rbp+var_18]
0x180042755  mov     qword ptr [rbp+var_20], rax
0x180042759  lea     r9, asc_1800AFB70; ": {}"
0x180042760  lea     rax, [rbp+var_20]
0x180042764  mov     r8d, edi
0x180042767  mov     qword ptr [rsp+50h+var_30], rax
0x18004276c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180042771  mov     edx, 0CCh
0x180042776  jmp     short loc_180042701
0x180042778  test    rdi, rdi
0x18004277b  jnz     short loc_1800427D8
0x18004277d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042784  mov     ebx, 80070057h
0x180042789  mov     [rbp+var_18], ebx
0x18004278c  test    rcx, rcx
0x18004278f  jz      short loc_1800427CE
0x180042791  mov     edi, 3
0x180042796  lea     r9, aNoContextSpeci; "No context specified"
0x18004279d  mov     r8d, edi
0x1800427a0  xor     edx, edx
0x1800427a2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800427a7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800427ae  lea     rax, [rbp+var_18]
0x1800427b2  mov     qword ptr [rbp+var_20], rax
0x1800427b6  lea     r9, asc_1800AFB70; ": {}"
0x1800427bd  lea     rax, [rbp+var_20]
0x1800427c1  mov     r8d, edi
0x1800427c4  mov     qword ptr [rsp+50h+var_30], rax
0x1800427c9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800427ce  mov     edx, 0CDh
0x1800427d3  jmp     loc_180042701
0x1800427d8  lea     rdx, [rbp+FileSizeHigh+4]; lpFileSizeHigh
0x1800427dc  mov     qword ptr [rbp-10h], 0
0x1800427e4  call    cs:__imp_GetCompressedFileSizeW
0x1800427eb  nop     dword ptr [rax+rax+00h]
0x1800427f0  mov     [rbp+FileSizeHigh], eax
0x1800427f3  cmp     eax, 0FFFFFFFFh
0x1800427f6  jnz     short loc_180042814
0x1800427f8  call    cs:__imp_GetLastError
0x1800427ff  nop     dword ptr [rax+rax+00h]
0x180042804  test    eax, eax
0x180042806  jz      short loc_180042814
0x180042808  mov     eax, [rbx+1Ch]
0x18004280b  mov     [rbp+FileSizeHigh+4], eax
0x18004280e  mov     eax, [rbx+20h]
0x180042811  mov     [rbp+FileSizeHigh], eax
0x180042814  mov     ecx, [rdi]
0x180042816  xor     edx, edx
0x180042818  mov     r8, qword ptr [rbp+FileSizeHigh]
0x18004281c  dec     r8
0x18004281f  add     r8, rcx
0x180042822  mov     rax, r8
0x180042825  div     rcx
0x180042828  sub     r8, rdx
0x18004282b  add     [rdi+8], r8
0x18004282f  xor     eax, eax
0x180042831  mov     rcx, [rbp+var_8]
0x180042835  xor     rcx, rsp; StackCookie
0x180042838  call    __security_check_cookie
0x18004283d  mov     rbx, [rsp+50h+arg_8]
0x180042842  mov     rdi, [rsp+50h+arg_18]
0x180042847  add     rsp, 50h
0x18004284b  pop     rbp
0x18004284c  retn
```
