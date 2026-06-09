# CLiveDumpProcessor::ProcessLiveDump(void)

- ea: `0x1400416f4`
- end: `0x1400418e2`
- name: `?ProcessLiveDump@CLiveDumpProcessor@@QEAAJXZ`
- size: `494`
- prototype: `__int64 __fastcall(CLiveDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140038760`

## callees

- `0x140002748`
- `0x1400054e4`
- `0x14000551c`
- `0x1400372dc`
- `0x140040c98`
- `0x140040e18`
- `0x1400415b8`
- `0x1400416f4`
- `0x1400418e8`
- `0x140041b40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400418b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400418b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140041815`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140041815`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14004185a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14004185a`

## string_xrefs

- `0x1400417ca`: `Failed to sprintf registry key name`
- `0x14004183b`: `Could not open key %ws`
- `0x140041880`: `Could not delete ReportId %ws tree`
- `0x1400417d6`: `CLiveDumpProcessor::CompleteFullLiveReport`
- `0x140041899`: `CLiveDumpProcessor::CompleteFullLiveReport`
- `0x14004174d`: `Failed to create mini live report.`

## pseudocode

```c
__int64 __fastcall CLiveDumpProcessor::ProcessLiveDump(LPCWSTR *this)
{
  int DumpHeader; // ebx
  const char *v3; // rax
  __int64 v4; // rdx
  LPCWSTR v5; // r9
  int v6; // eax
  HKEY *v7; // rax
  LSTATUS v8; // eax
  unsigned int v9; // edx
  LSTATUS v10; // eax
  unsigned int v11; // edx
  wil::details *phkResult; // [rsp+20h] [rbp-48h]
  wil::details *phkResulta; // [rsp+20h] [rbp-48h]
  char *v15; // [rsp+30h] [rbp-38h]
  LPCWSTR lpSubKey[2]; // [rsp+40h] [rbp-28h] BYREF
  _WORD v17[12]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+88h] [rbp+20h]
  HKEY hKey; // [rsp+90h] [rbp+28h] BYREF

  DumpHeader = CLiveDumpProcessor::ReadDumpHeader((CLiveDumpProcessor *)this);
  if ( DumpHeader >= 0 )
  {
    DumpHeader = CLiveDumpProcessor::CreateMiniLiveReport((CLiveDumpProcessor *)this);
    if ( DumpHeader >= 0 )
    {
      DumpHeader = CLiveDumpProcessor::ConvertLiveDump((CLiveDumpProcessor *)this);
      if ( DumpHeader >= 0 )
      {
        DumpHeader = CLiveDumpProcessor::SubmitMiniLiveReport((CLiveDumpProcessor *)this);
        if ( DumpHeader >= 0 )
          goto LABEL_10;
        goto LABEL_9;
      }
      v3 = "Converting live dump failed";
      v4 = 660;
    }
    else
    {
      v3 = "Failed to create mini live report.";
      v4 = 649;
    }
  }
  else
  {
    v3 = "No live dump was present";
    v4 = 637;
  }
  LODWORD(phkResult) = DumpHeader;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
    "CLiveDumpProcessor::ProcessLiveDump",
    phkResult,
    (int)v3,
    v15);
LABEL_9:
  CLiveDumpProcessor::CancelMiniLiveReport((CLiveDumpProcessor *)this);
LABEL_10:
  v5 = this[9];
  lpSubKey[0] = v17;
  lpSubKey[1] = v17;
  v17[0] = 0;
  hKey = 0;
  v6 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpSubKey,
         L"%s\\FullLiveKernelReports\\%s",
         g_wszLiveKernelReportsQueueRoot,
         v5);
  if ( v6 >= 0 )
  {
    v7 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x3001Bu, v7);
    v9 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      LODWORD(phkResulta) = v9;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x11D,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
        "CLiveDumpProcessor::CompleteFullLiveReport",
        phkResulta,
        (int)"Could not open key %ws",
        (const char *)lpSubKey[0]);
    }
    else
    {
      v10 = RegDeleteTreeW(hKey, this[13]);
      v11 = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          v11 = (unsigned __int16)v10 | 0x80070000;
        LODWORD(phkResulta) = v11;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x127,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
          "CLiveDumpProcessor::CompleteFullLiveReport",
          phkResulta,
          (int)"Could not delete ReportId %ws tree",
          (const char *)this[13]);
      }
    }
  }
  else
  {
    LODWORD(phkResult) = v6;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x110,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::CompleteFullLiveReport",
      phkResult,
      (int)"Failed to sprintf registry key name",
      v15);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpSubKey[0] != v17 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)DumpHeader;
}

```

## disassembly

```asm
0x1400416f4  push    rbp
0x1400416f6  push    rbx
0x1400416f7  push    rsi
0x1400416f8  push    rdi
0x1400416f9  mov     rbp, rsp
0x1400416fc  sub     rsp, 68h
0x140041700  mov     rdi, rcx
0x140041703  call    ?ReadDumpHeader@CLiveDumpProcessor@@AEAAJXZ; CLiveDumpProcessor::ReadDumpHeader(void)
0x140041708  lea     rsi, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14004170f  mov     ebx, eax
0x140041711  test    eax, eax
0x140041713  jns     short loc_14004173F
0x140041715  lea     rax, aNoLiveDumpWasP; "No live dump was present"
0x14004171c  mov     edx, 27Dh; void *
0x140041721  mov     rcx, [rbp+20h]; this
0x140041725  lea     r9, aClivedumpproce_3; "CLiveDumpProcessor::ProcessLiveDump"
0x14004172c  mov     qword ptr [rsp+68h+var_40], rax; int
0x140041731  mov     r8, rsi; unsigned int
0x140041734  mov     dword ptr [rsp+68h+phkResult], ebx; wil::details *
0x140041738  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14004173d  jmp     short loc_140041785
0x14004173f  mov     rcx, rdi; this
0x140041742  call    ?CreateMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ; CLiveDumpProcessor::CreateMiniLiveReport(void)
0x140041747  mov     ebx, eax
0x140041749  test    eax, eax
0x14004174b  jns     short loc_14004175B
0x14004174d  lea     rax, aFailedToCreate_1; "Failed to create mini live report."
0x140041754  mov     edx, 289h
0x140041759  jmp     short loc_140041721
0x14004175b  mov     rcx, rdi; this
0x14004175e  call    ?ConvertLiveDump@CLiveDumpProcessor@@AEAAJXZ; CLiveDumpProcessor::ConvertLiveDump(void)
0x140041763  mov     ebx, eax
0x140041765  test    eax, eax
0x140041767  jns     short loc_140041777
0x140041769  lea     rax, aConvertingLive; "Converting live dump failed"
0x140041770  mov     edx, 294h
0x140041775  jmp     short loc_140041721
0x140041777  mov     rcx, rdi; this
0x14004177a  call    ?SubmitMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ; CLiveDumpProcessor::SubmitMiniLiveReport(void)
0x14004177f  mov     ebx, eax
0x140041781  test    eax, eax
0x140041783  jns     short loc_14004178D
0x140041785  mov     rcx, rdi; this
0x140041788  call    ?CancelMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ; CLiveDumpProcessor::CancelMiniLiveReport(void)
0x14004178d  mov     r9, [rdi+48h]
0x140041791  lea     rax, [rbp+var_18]
0x140041795  mov     [rbp+lpSubKey], rax
0x140041799  lea     r8, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x1400417a0  lea     rax, [rbp+var_18]
0x1400417a4  mov     [rbp+var_20], rax
0x1400417a8  lea     rdx, aSFulllivekerne; "%s\\FullLiveKernelReports\\%s"
0x1400417af  xor     eax, eax
0x1400417b1  lea     rcx, [rbp+lpSubKey]
0x1400417b5  mov     [rbp+var_18], ax
0x1400417b9  mov     [rbp+hKey], rax
0x1400417bd  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400417c2  test    eax, eax
0x1400417c4  jns     short loc_1400417F3
0x1400417c6  mov     rcx, [rbp+20h]; this
0x1400417ca  lea     rdx, aFailedToSprint; "Failed to sprintf registry key name"
0x1400417d1  mov     qword ptr [rsp+68h+var_40], rdx; int
0x1400417d6  lea     r9, aClivedumpproce; "CLiveDumpProcessor::CompleteFullLiveRep"...
0x1400417dd  mov     edx, 110h; void *
0x1400417e2  mov     dword ptr [rsp+68h+phkResult], eax; wil::details *
0x1400417e6  mov     r8, rsi; unsigned int
0x1400417e9  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400417ee  jmp     loc_1400418A8
0x1400417f3  lea     rcx, [rbp+hKey]
0x1400417f7  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400417fc  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x140041800  mov     r9d, 3001Bh; samDesired
0x140041806  xor     r8d, r8d; ulOptions
0x140041809  mov     [rsp+68h+phkResult], rax; phkResult
0x14004180e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140041815  call    cs:__imp_RegOpenKeyExW
0x14004181c  nop     dword ptr [rax+rax+00h]
0x140041821  mov     edx, eax
0x140041823  test    eax, eax
0x140041825  jz      short loc_140041852
0x140041827  jle     short loc_140041832
0x140041829  movzx   edx, ax
0x14004182c  or      edx, 80070000h
0x140041832  mov     rax, [rbp+lpSubKey]
0x140041836  mov     [rsp+68h+var_38], rax
0x14004183b  lea     rax, aCouldNotOpenKe; "Could not open key %ws"
0x140041842  mov     qword ptr [rsp+68h+var_40], rax
0x140041847  mov     dword ptr [rsp+68h+phkResult], edx
0x14004184b  mov     edx, 11Dh
0x140041850  jmp     short loc_140041895
0x140041852  mov     rdx, [rdi+68h]; lpSubKey
0x140041856  mov     rcx, [rbp+hKey]; hKey
0x14004185a  call    cs:__imp_RegDeleteTreeW
0x140041861  nop     dword ptr [rax+rax+00h]
0x140041866  mov     edx, eax
0x140041868  test    eax, eax
0x14004186a  jz      short loc_1400418A8
0x14004186c  jle     short loc_140041877
0x14004186e  movzx   edx, ax
0x140041871  or      edx, 80070000h
0x140041877  mov     rax, [rdi+68h]
0x14004187b  mov     [rsp+68h+var_38], rax; char *
0x140041880  lea     rax, aCouldNotDelete_0; "Could not delete ReportId %ws tree"
0x140041887  mov     qword ptr [rsp+68h+var_40], rax; int
0x14004188c  mov     dword ptr [rsp+68h+phkResult], edx; wil::details *
0x140041890  mov     edx, 127h; void *
0x140041895  mov     rcx, [rbp+20h]; this
0x140041899  lea     r9, aClivedumpproce; "CLiveDumpProcessor::CompleteFullLiveRep"...
0x1400418a0  mov     r8, rsi; unsigned int
0x1400418a3  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400418a8  mov     rcx, [rbp+hKey]; hKey
0x1400418ac  test    rcx, rcx
0x1400418af  jz      short loc_1400418BD
0x1400418b1  call    cs:__imp_RegCloseKey
0x1400418b8  nop     dword ptr [rax+rax+00h]
0x1400418bd  mov     rcx, [rbp+lpSubKey]; void *
0x1400418c1  lea     rax, [rbp+var_18]
0x1400418c5  cmp     rcx, rax
0x1400418c8  jz      short loc_1400418D6
0x1400418ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400418d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400418d6  mov     eax, ebx
0x1400418d8  add     rsp, 68h
0x1400418dc  pop     rdi
0x1400418dd  pop     rsi
0x1400418de  pop     rbx
0x1400418df  pop     rbp
0x1400418e0  retn
```
