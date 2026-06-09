# CLiveDumpProcessor::ProcessLiveDump(void)

- ea: `0x14003ebec`
- end: `0x14003edc7`
- name: `?ProcessLiveDump@CLiveDumpProcessor@@QEAAJXZ`
- size: `475`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400361e8`

## callees

- `0x140002728`
- `0x140005430`
- `0x140005468`
- `0x140034d9c`
- `0x14003e244`
- `0x14003e3b0`
- `0x14003eabc`
- `0x14003ebec`
- `0x14003edd0`
- `0x14003f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003ed9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003ed9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003ed0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003ed0d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14003ed4c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14003ed4c`

## string_xrefs

- `0x14003ecc2`: `Failed to sprintf registry key name`
- `0x14003ed2d`: `Could not open key %ws`
- `0x14003ed6c`: `Could not delete ReportId %ws tree`
- `0x14003ecce`: `CLiveDumpProcessor::CompleteFullLiveReport`
- `0x14003ed85`: `CLiveDumpProcessor::CompleteFullLiveReport`
- `0x14003ec45`: `Failed to create mini live report.`

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
0x14003ebec  push    rbp
0x14003ebee  push    rbx
0x14003ebef  push    rsi
0x14003ebf0  push    rdi
0x14003ebf1  mov     rbp, rsp
0x14003ebf4  sub     rsp, 68h
0x14003ebf8  mov     rdi, rcx
0x14003ebfb  call    ?ReadDumpHeader@CLiveDumpProcessor@@AEAAJXZ; CLiveDumpProcessor::ReadDumpHeader(void)
0x14003ec00  lea     rsi, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003ec07  mov     ebx, eax
0x14003ec09  test    eax, eax
0x14003ec0b  jns     short loc_14003EC37
0x14003ec0d  lea     rax, aNoLiveDumpWasP; "No live dump was present"
0x14003ec14  mov     edx, 27Dh; void *
0x14003ec19  mov     rcx, [rbp+20h]; this
0x14003ec1d  lea     r9, aClivedumpproce_3; "CLiveDumpProcessor::ProcessLiveDump"
0x14003ec24  mov     qword ptr [rsp+68h+var_40], rax; int
0x14003ec29  mov     r8, rsi; unsigned int
0x14003ec2c  mov     dword ptr [rsp+68h+phkResult], ebx; wil::details *
0x14003ec30  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ec35  jmp     short loc_14003EC7D
0x14003ec37  mov     rcx, rdi; this
0x14003ec3a  call    ?CreateMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ; CLiveDumpProcessor::CreateMiniLiveReport(void)
0x14003ec3f  mov     ebx, eax
0x14003ec41  test    eax, eax
0x14003ec43  jns     short loc_14003EC53
0x14003ec45  lea     rax, aFailedToCreate_1; "Failed to create mini live report."
0x14003ec4c  mov     edx, 289h
0x14003ec51  jmp     short loc_14003EC19
0x14003ec53  mov     rcx, rdi; this
0x14003ec56  call    ?ConvertLiveDump@CLiveDumpProcessor@@AEAAJXZ; CLiveDumpProcessor::ConvertLiveDump(void)
0x14003ec5b  mov     ebx, eax
0x14003ec5d  test    eax, eax
0x14003ec5f  jns     short loc_14003EC6F
0x14003ec61  lea     rax, aConvertingLive; "Converting live dump failed"
0x14003ec68  mov     edx, 294h
0x14003ec6d  jmp     short loc_14003EC19
0x14003ec6f  mov     rcx, rdi; this
0x14003ec72  call    ?SubmitMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ; CLiveDumpProcessor::SubmitMiniLiveReport(void)
0x14003ec77  mov     ebx, eax
0x14003ec79  test    eax, eax
0x14003ec7b  jns     short loc_14003EC85
0x14003ec7d  mov     rcx, rdi; this
0x14003ec80  call    ?CancelMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ; CLiveDumpProcessor::CancelMiniLiveReport(void)
0x14003ec85  mov     r9, [rdi+48h]
0x14003ec89  lea     rax, [rbp+var_18]
0x14003ec8d  mov     [rbp+lpSubKey], rax
0x14003ec91  lea     r8, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x14003ec98  lea     rax, [rbp+var_18]
0x14003ec9c  mov     [rbp+var_20], rax
0x14003eca0  lea     rdx, aSFulllivekerne; "%s\\FullLiveKernelReports\\%s"
0x14003eca7  xor     eax, eax
0x14003eca9  lea     rcx, [rbp+lpSubKey]
0x14003ecad  mov     [rbp+var_18], ax
0x14003ecb1  mov     [rbp+hKey], rax
0x14003ecb5  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14003ecba  test    eax, eax
0x14003ecbc  jns     short loc_14003ECEB
0x14003ecbe  mov     rcx, [rbp+20h]; this
0x14003ecc2  lea     rdx, aFailedToSprint; "Failed to sprintf registry key name"
0x14003ecc9  mov     qword ptr [rsp+68h+var_40], rdx; int
0x14003ecce  lea     r9, aClivedumpproce; "CLiveDumpProcessor::CompleteFullLiveRep"...
0x14003ecd5  mov     edx, 110h; void *
0x14003ecda  mov     dword ptr [rsp+68h+phkResult], eax; wil::details *
0x14003ecde  mov     r8, rsi; unsigned int
0x14003ece1  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ece6  jmp     loc_14003ED94
0x14003eceb  lea     rcx, [rbp+hKey]
0x14003ecef  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003ecf4  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14003ecf8  mov     r9d, 3001Bh; samDesired
0x14003ecfe  xor     r8d, r8d; ulOptions
0x14003ed01  mov     [rsp+68h+phkResult], rax; phkResult
0x14003ed06  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003ed0d  call    cs:__imp_RegOpenKeyExW
0x14003ed13  mov     edx, eax
0x14003ed15  test    eax, eax
0x14003ed17  jz      short loc_14003ED44
0x14003ed19  jle     short loc_14003ED24
0x14003ed1b  movzx   edx, ax
0x14003ed1e  or      edx, 80070000h
0x14003ed24  mov     rax, [rbp+lpSubKey]
0x14003ed28  mov     [rsp+68h+var_38], rax
0x14003ed2d  lea     rax, aCouldNotOpenKe; "Could not open key %ws"
0x14003ed34  mov     qword ptr [rsp+68h+var_40], rax
0x14003ed39  mov     dword ptr [rsp+68h+phkResult], edx
0x14003ed3d  mov     edx, 11Dh
0x14003ed42  jmp     short loc_14003ED81
0x14003ed44  mov     rdx, [rdi+68h]; lpSubKey
0x14003ed48  mov     rcx, [rbp+hKey]; hKey
0x14003ed4c  call    cs:__imp_RegDeleteTreeW
0x14003ed52  mov     edx, eax
0x14003ed54  test    eax, eax
0x14003ed56  jz      short loc_14003ED94
0x14003ed58  jle     short loc_14003ED63
0x14003ed5a  movzx   edx, ax
0x14003ed5d  or      edx, 80070000h
0x14003ed63  mov     rax, [rdi+68h]
0x14003ed67  mov     [rsp+68h+var_38], rax; char *
0x14003ed6c  lea     rax, aCouldNotDelete_0; "Could not delete ReportId %ws tree"
0x14003ed73  mov     qword ptr [rsp+68h+var_40], rax; int
0x14003ed78  mov     dword ptr [rsp+68h+phkResult], edx; wil::details *
0x14003ed7c  mov     edx, 127h; void *
0x14003ed81  mov     rcx, [rbp+20h]; this
0x14003ed85  lea     r9, aClivedumpproce; "CLiveDumpProcessor::CompleteFullLiveRep"...
0x14003ed8c  mov     r8, rsi; unsigned int
0x14003ed8f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ed94  mov     rcx, [rbp+hKey]; hKey
0x14003ed98  test    rcx, rcx
0x14003ed9b  jz      short loc_14003EDA3
0x14003ed9d  call    cs:__imp_RegCloseKey
0x14003eda3  mov     rcx, [rbp+lpSubKey]; void *
0x14003eda7  lea     rax, [rbp+var_18]
0x14003edab  cmp     rcx, rax
0x14003edae  jz      short loc_14003EDBC
0x14003edb0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003edb7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003edbc  mov     eax, ebx
0x14003edbe  add     rsp, 68h
0x14003edc2  pop     rdi
0x14003edc3  pop     rsi
0x14003edc4  pop     rbx
0x14003edc5  pop     rbp
0x14003edc6  retn
```
