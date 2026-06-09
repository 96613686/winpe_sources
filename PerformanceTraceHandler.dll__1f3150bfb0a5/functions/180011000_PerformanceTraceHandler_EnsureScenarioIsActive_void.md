# PerformanceTraceHandler::EnsureScenarioIsActive(void)

- ea: `0x180011000`
- end: `0x180011175`
- name: `?EnsureScenarioIsActive@PerformanceTraceHandler@@AEAAJXZ`
- size: `373`
- prototype: `__int64 __fastcall(PerformanceTraceHandler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180011cd8`

## callees

- `0x180007f1c`
- `0x180007f3c`
- `0x180010a90`
- `0x180010ca4`
- `0x180011000`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001103c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800110c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001103c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800110c3`

## string_xrefs

- `0x180011085`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`
- `0x18001111f`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::EnsureScenarioIsActive(PerformanceTraceHandler *this)
{
  HMODULE *v1; // rdi
  FARPROC ProcAddress; // rax
  const char *v4; // r9
  int LastError; // eax
  __int64 v6; // rcx
  unsigned int v7; // esi
  FARPROC v9; // rax
  const char *v10; // r9
  int v11; // eax
  unsigned int v12; // edi
  int v13; // [rsp+20h] [rbp-48h]
  __int128 v14; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v16; // [rsp+70h] [rbp+8h] BYREF
  char v17; // [rsp+78h] [rbp+10h] BYREF

  v1 = (HMODULE *)((char *)this + 64);
  v16 = 0;
  ProcAddress = (FARPROC)*((_QWORD *)this + 9);
  if ( ProcAddress
    || (ProcAddress = GetProcAddress(*v1, "UtcIsScenarioActive"), (*((_QWORD *)this + 9) = ProcAddress) != 0) )
  {
    v6 = *((_QWORD *)this + 7);
    v14 = DIAGTRACK_START_PERF_REPRO_SCENARIO_ID;
    LastError = ((__int64 (__fastcall *)(__int64, __int128 *, int *))ProcAddress)(v6, &v14, &v16);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x68,
                  (unsigned int)"onecore\\internal\\base\\inc\\utcapiwrapperex.h",
                  v4);
  }
  v7 = LastError;
  if ( LastError >= 0 )
  {
    if ( v16
      || ((v9 = (FARPROC)*((_QWORD *)this + 15)) != 0
       || (v9 = GetProcAddress(*v1, "UtcDownloadLatestSettingsForNamespaceEx"), (*((_QWORD *)this + 15) = v9) != 0)
        ? (v13 = 1,
           v11 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, const wchar_t *, __int64))v9)(
                   *((_QWORD *)this + 7),
                   L"windows",
                   L"uif_ondemand",
                   1))
        : (v11 = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0xC7,
                   (unsigned int)"onecore\\internal\\base\\inc\\utcapiwrapperex.h",
                   v10)),
          v12 = v11,
          v11 >= 0) )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                              (char *)this + 192,
                              &v17)
               + 272LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(&v17);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
        (const char *)(unsigned int)v11,
        v13);
      return v12;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
      (const char *)(unsigned int)LastError,
      v13);
    return v7;
  }
}

```

## disassembly

```asm
0x180011000  mov     rax, rsp
0x180011003  mov     [rax+18h], rbx
0x180011007  mov     [rax+20h], rsi
0x18001100b  push    rdi
0x18001100c  sub     rsp, 60h
0x180011010  movaps  xmmword ptr [rax-18h], xmm6
0x180011014  lea     rdi, [rcx+40h]
0x180011018  movups  xmm6, cs:DIAGTRACK_START_PERF_REPRO_SCENARIO_ID
0x18001101f  mov     dword ptr [rax+8], 0
0x180011026  mov     rbx, rcx
0x180011029  mov     rax, [rcx+48h]
0x18001102d  test    rax, rax
0x180011030  jnz     short loc_180011061
0x180011032  mov     rcx, [rdi]; hModule
0x180011035  lea     rdx, aUtcisscenarioa; "UtcIsScenarioActive"
0x18001103c  call    cs:__imp_GetProcAddress
0x180011042  mov     [rbx+48h], rax
0x180011046  test    rax, rax
0x180011049  jnz     short loc_180011061
0x18001104b  mov     rcx, [rsp+68h]; this
0x180011050  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\utcapiwra"...
0x180011057  lea     edx, [rax+68h]; void *
0x18001105a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001105f  jmp     short loc_18001107A
0x180011061  mov     rcx, [rbx+38h]
0x180011065  lea     r8, [rsp+68h+arg_0]
0x18001106a  lea     rdx, [rsp+68h+var_28]
0x18001106f  movdqa  [rsp+68h+var_28], xmm6
0x180011075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001107a  mov     esi, eax
0x18001107c  test    eax, eax
0x18001107e  jns     short loc_1800110A0
0x180011080  mov     rcx, [rsp+68h]; this
0x180011085  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001108c  mov     r9d, eax; char *
0x18001108f  mov     edx, 67h ; 'g'; void *
0x180011094  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011099  mov     eax, esi
0x18001109b  jmp     loc_18001115E
0x1800110a0  cmp     [rsp+68h+arg_0], 0
0x1800110a5  mov     esi, 1
0x1800110aa  jnz     loc_180011137
0x1800110b0  mov     rax, [rbx+78h]
0x1800110b4  test    rax, rax
0x1800110b7  jnz     short loc_1800110EA
0x1800110b9  mov     rcx, [rdi]; hModule
0x1800110bc  lea     rdx, aUtcdownloadlat; "UtcDownloadLatestSettingsForNamespaceEx"
0x1800110c3  call    cs:__imp_GetProcAddress
0x1800110c9  mov     [rbx+78h], rax
0x1800110cd  test    rax, rax
0x1800110d0  jnz     short loc_1800110EA
0x1800110d2  mov     rcx, [rsp+68h]; this
0x1800110d7  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\utcapiwra"...
0x1800110de  mov     edx, 0C7h; void *
0x1800110e3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800110e8  jmp     short loc_180011114
0x1800110ea  mov     rcx, [rbx+38h]
0x1800110ee  lea     r8, aUifOndemand; "uif_ondemand"
0x1800110f5  mov     [rsp+68h+var_38], 493E0h
0x1800110fd  lea     rdx, aWindows; "windows"
0x180011104  mov     [rsp+68h+var_40], esi
0x180011108  mov     r9d, esi
0x18001110b  mov     [rsp+68h+var_48], esi; int
0x18001110f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011114  mov     edi, eax
0x180011116  test    eax, eax
0x180011118  jns     short loc_180011137
0x18001111a  mov     rcx, [rsp+68h]; this
0x18001111f  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x180011126  mov     r9d, eax; char *
0x180011129  mov     edx, 6Ch ; 'l'; void *
0x18001112e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011133  mov     eax, edi
0x180011135  jmp     short loc_18001115E
0x180011137  lea     rcx, [rbx+0C0h]
0x18001113e  lea     rdx, [rsp+68h+arg_8]
0x180011143  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x180011148  mov     rcx, [rax]
0x18001114b  mov     [rcx+110h], sil
0x180011152  lea     rcx, [rsp+68h+arg_8]
0x180011157  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x18001115c  xor     eax, eax
0x18001115e  movaps  xmm6, [rsp+68h+var_18]
0x180011163  lea     r11, [rsp+68h+var_8]
0x180011168  mov     rbx, [r11+20h]
0x18001116c  mov     rsi, [r11+28h]
0x180011170  mov     rsp, r11
0x180011173  pop     rdi
0x180011174  retn
```
