# CKernelReport::ConvertLiveDumpAndReport(wchar_t const *,wchar_t const *)

- ea: `0x1400361e8`
- end: `0x14003662e`
- name: `?ConvertLiveDumpAndReport@CKernelReport@@QEAAJPEB_W0@Z`
- size: `1094`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x14003494c`
- `0x1400359ac`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140005430`
- `0x14000c8a0`
- `0x140013ff0`
- `0x140034d9c`
- `0x140035014`
- `0x1400361e8`
- `0x140039c40`
- `0x14003ebec`
- `0x14003f55c`
- `0x14005b770`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140036462`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400364ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140036462`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400364ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140036572`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140036572`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14003632d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14003632d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003657a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003657a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400365d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400365d6`

## string_xrefs

- `0x140036364`: `CreateEvent succeeded for %ws`
- `0x1400365a0`: `CreateEvent failed for live conversion`
- `0x140036432`: `Failed to sprintf registry key name`
- `0x14003648a`: `Could not open key %ws`

## pseudocode

```c
__int64 __fastcall CKernelReport::ConvertLiveDumpAndReport(CKernelReport *this, const wchar_t *a2, const wchar_t *a3)
{
  HKEY MutexW; // r13
  signed int Settings; // ebx
  __int64 v8; // rbx
  __int64 v9; // r8
  const char *v10; // rax
  __int64 v11; // rdx
  LSTATUS v12; // eax
  signed int LastError; // eax
  wil::details *phkResult; // [rsp+20h] [rbp-E0h]
  wil::details *phkResulta; // [rsp+20h] [rbp-E0h]
  wil::details *phkResultb; // [rsp+20h] [rbp-E0h]
  char *v18; // [rsp+30h] [rbp-D0h]
  char *v19; // [rsp+30h] [rbp-D0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v22[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v23[3]; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v24[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD *v25; // [rsp+88h] [rbp-78h]
  _WORD *v26; // [rsp+90h] [rbp-70h]
  _WORD v27[8]; // [rsp+98h] [rbp-68h] BYREF
  _WORD *v28; // [rsp+A8h] [rbp-58h]
  _WORD *v29; // [rsp+B0h] [rbp-50h]
  _WORD v30[8]; // [rsp+B8h] [rbp-48h] BYREF
  _WORD *v31; // [rsp+C8h] [rbp-38h]
  _WORD *v32; // [rsp+D0h] [rbp-30h]
  _WORD v33[8]; // [rsp+D8h] [rbp-28h] BYREF
  _WORD *v34; // [rsp+E8h] [rbp-18h]
  _WORD *v35; // [rsp+F0h] [rbp-10h]
  _WORD v36[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v37[8192]; // [rsp+108h] [rbp+8h] BYREF
  _WORD *v38; // [rsp+2108h] [rbp+2008h]
  _WORD *v39; // [rsp+2110h] [rbp+2010h]
  _WORD v40[8]; // [rsp+2118h] [rbp+2018h] BYREF
  _WORD *v41; // [rsp+2128h] [rbp+2028h]
  _WORD *v42; // [rsp+2130h] [rbp+2030h]
  _WORD v43[8]; // [rsp+2138h] [rbp+2038h] BYREF
  _QWORD v44[2]; // [rsp+2148h] [rbp+2048h] BYREF
  _WORD v45[12]; // [rsp+2158h] [rbp+2058h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+21B8h] [rbp+20B8h]

  v23[0] = 0;
  hKey = 0;
  v25 = v27;
  v26 = v27;
  v27[0] = 0;
  v28 = v30;
  v29 = v30;
  v30[0] = 0;
  v31 = v33;
  v32 = v33;
  v33[0] = 0;
  v34 = v36;
  v35 = v36;
  v36[0] = 0;
  v24[0] = 1;
  v24[1] = 1;
  memset_0(v37, 0, sizeof(v37));
  v38 = v40;
  v39 = v40;
  v40[0] = 0;
  v41 = v43;
  v42 = v43;
  v43[0] = 0;
  v44[0] = v45;
  v44[1] = v45;
  v45[0] = 0;
  lpSubKey[0] = v22;
  lpSubKey[1] = v22;
  v22[0] = 0;
  MutexW = (HKEY)CreateMutexW(0, 1, L"Global\\WerKernelVerticalConvertingLiveDump");
  v23[1] = MutexW;
  if ( (unsigned __int64)MutexW + 1 > 1 && GetLastError() != 183 )
  {
    LODWORD(phkResult) = 0x80000000;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x4AE,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ConvertLiveDumpAndReport",
      phkResult,
      (int)"CreateEvent succeeded for %ws",
      (const char *)L"Global\\WerKernelVerticalConvertingLiveDump");
    if ( a2 && a3 )
    {
      Settings = CLiveDumpSettings::LoadSettings((CLiveDumpSettings *)v24, a2, a3);
      if ( Settings >= 0 )
      {
        v8 = -1;
        if ( v25 )
        {
          v9 = -1;
          do
            ++v9;
          while ( v25[v9] );
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v44, v25);
        do
          ++v8;
        while ( a3[v8] );
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v44, a3, v8);
        Settings = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                     lpSubKey,
                     L"%s\\FullLiveKernelReports\\%s\\%s",
                     g_wszLiveKernelReportsQueueRoot,
                     a2,
                     a3);
        if ( Settings < 0 )
        {
          v10 = "Failed to sprintf registry key name";
          v11 = 1226;
LABEL_24:
          LODWORD(phkResulta) = Settings;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
            "CKernelReport::ConvertLiveDumpAndReport",
            phkResulta,
            (int)v10,
            v19);
          goto LABEL_25;
        }
        v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x3001Bu, &hKey);
        Settings = v12;
        if ( v12 )
        {
          if ( v12 > 0 )
            Settings = (unsigned __int16)v12 | 0x80070000;
          LODWORD(phkResultb) = Settings;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0x4D7,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
            "CKernelReport::ConvertLiveDumpAndReport",
            phkResultb,
            (int)"Could not open key %ws",
            (const char *)lpSubKey[0]);
          goto LABEL_25;
        }
        if ( RegOpenKeyExW(hKey, L"Busy", 0, 1u, v23) )
        {
          Settings = CLiveDumpProcessor::ProcessLiveDump((CLiveDumpProcessor *)v24);
          if ( Settings < 0 )
          {
            v10 = "ProcessLiveDump failed";
            v11 = 1270;
            goto LABEL_24;
          }
          Settings = CKernelReport::ReportLiveReport(this, a2, a3);
        }
        else
        {
          LODWORD(phkResulta) = 0x80000000;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0x4E8,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
            "CKernelReport::ConvertLiveDumpAndReport",
            phkResulta,
            (int)"Full Report is busy for %ws - %ws",
            (const char *)a2,
            a3);
          Settings = -2147019873;
        }
LABEL_25:
        ReleaseMutex(MutexW);
        goto LABEL_31;
      }
    }
    else
    {
      Settings = -2147024809;
    }
    v10 = "liveDumpProcessor initialization failed";
    v11 = 1211;
    goto LABEL_24;
  }
  LastError = GetLastError();
  Settings = LastError;
  if ( LastError > 0 )
    Settings = (unsigned __int16)LastError | 0x80070000;
  if ( Settings >= 0 )
    Settings = -2147467259;
  LODWORD(phkResult) = Settings;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x4A8,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::ConvertLiveDumpAndReport",
    phkResult,
    (int)"CreateEvent failed for live conversion",
    v18);
LABEL_31:
  if ( (unsigned __int64)MutexW + 1 > 1 )
    CloseHandle(MutexW);
  if ( lpSubKey[0] != v22 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  CLiveDumpProcessor::~CLiveDumpProcessor((CLiveDumpProcessor *)v24);
  return (unsigned int)Settings;
}

```

## disassembly

```asm
0x1400361e8  mov     [rsp-8+arg_18], rbx
0x1400361ed  push    rbp
0x1400361ee  push    rsi
0x1400361ef  push    rdi
0x1400361f0  push    r12
0x1400361f2  push    r13
0x1400361f4  push    r14
0x1400361f6  push    r15
0x1400361f8  lea     rbp, [rsp-2080h]
0x140036200  mov     eax, 2180h
0x140036205  call    _alloca_probe
0x14003620a  sub     rsp, rax
0x14003620d  mov     rax, cs:__security_cookie
0x140036214  xor     rax, rsp
0x140036217  mov     [rbp+20B0h+var_40], rax
0x14003621e  mov     r14, r8
0x140036221  mov     r15, rdx
0x140036224  mov     r12, rcx
0x140036227  xor     ebx, ebx
0x140036229  mov     [rsp+21B0h+var_2148], rbx
0x14003622e  mov     [rsp+21B0h+hKey], rbx
0x140036233  lea     rax, [rbp+20B0h+var_2118]
0x140036237  mov     [rbp+20B0h+var_2128], rax
0x14003623b  lea     rax, [rbp+20B0h+var_2118]
0x14003623f  mov     [rbp+20B0h+var_2120], rax
0x140036243  mov     [rbp+20B0h+var_2118], bx
0x140036247  lea     rax, [rbp+20B0h+var_20F8]
0x14003624b  mov     [rbp+20B0h+var_2108], rax
0x14003624f  lea     rax, [rbp+20B0h+var_20F8]
0x140036253  mov     [rbp+20B0h+var_2100], rax
0x140036257  mov     [rbp+20B0h+var_20F8], bx
0x14003625b  lea     rax, [rbp+20B0h+var_20D8]
0x14003625f  mov     [rbp+20B0h+var_20E8], rax
0x140036263  lea     rax, [rbp+20B0h+var_20D8]
0x140036267  mov     [rbp+20B0h+var_20E0], rax
0x14003626b  mov     [rbp+20B0h+var_20D8], bx
0x14003626f  lea     rax, [rbp+20B0h+var_20B8]
0x140036273  mov     [rbp+20B0h+var_20C8], rax
0x140036277  lea     rax, [rbp+20B0h+var_20B8]
0x14003627b  mov     [rbp+20B0h+var_20C0], rax
0x14003627f  mov     [rbp+20B0h+var_20B8], bx
0x140036283  lea     edi, [rbx+1]
0x140036286  mov     [rbp+20B0h+var_2130], edi
0x140036289  mov     [rbp+20B0h+var_212C], edi
0x14003628c  xor     edx, edx; Val
0x14003628e  mov     r8d, 2000h; Size
0x140036294  lea     rcx, [rbp+20B0h+var_20A8]; void *
0x140036298  call    memset_0
0x14003629d  lea     rax, [rbp+20B0h+var_98]
0x1400362a4  mov     [rbp+20B0h+var_A8], rax
0x1400362ab  lea     rax, [rbp+20B0h+var_98]
0x1400362b2  mov     [rbp+20B0h+var_A0], rax
0x1400362b9  mov     [rbp+20B0h+var_98], bx
0x1400362c0  lea     rax, [rbp+20B0h+var_78]
0x1400362c7  mov     [rbp+20B0h+var_88], rax
0x1400362ce  lea     rax, [rbp+20B0h+var_78]
0x1400362d5  mov     [rbp+20B0h+var_80], rax
0x1400362dc  mov     [rbp+20B0h+var_78], bx
0x1400362e3  lea     rax, [rbp+20B0h+var_58]
0x1400362ea  mov     [rbp+20B0h+var_68], rax
0x1400362f1  lea     rax, [rbp+20B0h+var_58]
0x1400362f8  mov     [rbp+20B0h+var_60], rax
0x1400362ff  mov     [rbp+20B0h+var_58], bx
0x140036306  lea     rax, [rsp+21B0h+var_2158]
0x14003630b  mov     [rsp+21B0h+lpSubKey], rax
0x140036310  lea     rax, [rsp+21B0h+var_2158]
0x140036315  mov     [rsp+21B0h+var_2160], rax
0x14003631a  mov     [rsp+21B0h+var_2158], bx
0x14003631f  lea     rsi, aGlobalWerkerne; "Global\\WerKernelVerticalConvertingLive"...
0x140036326  mov     r8, rsi; lpName
0x140036329  mov     edx, edi; bInitialOwner
0x14003632b  xor     ecx, ecx; lpMutexAttributes
0x14003632d  call    cs:__imp_CreateMutexW
0x140036333  mov     r13, rax
0x140036336  mov     [rsp+21B0h+var_2140], rax
0x14003633b  inc     rax
0x14003633e  cmp     rax, rdi
0x140036341  jbe     loc_14003657A
0x140036347  call    cs:__imp_GetLastError
0x14003634d  cmp     eax, 0B7h
0x140036352  jz      loc_14003657A
0x140036358  mov     rcx, [rbp+20B8h]; this
0x14003635f  mov     [rsp+21B0h+var_2180], rsi; char *
0x140036364  lea     rax, aCreateeventSuc; "CreateEvent succeeded for %ws"
0x14003636b  mov     qword ptr [rsp+21B0h+var_2188], rax; int
0x140036370  mov     dword ptr [rsp+21B0h+phkResult], 80000000h; wil::details *
0x140036378  lea     rdi, aCkernelreportC_2; "CKernelReport::ConvertLiveDumpAndReport"
0x14003637f  mov     r9, rdi; char *
0x140036382  lea     rsi, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140036389  mov     r8, rsi; unsigned int
0x14003638c  mov     edx, 4AEh; void *
0x140036391  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140036396  test    r15, r15
0x140036399  jz      loc_140036543
0x14003639f  test    r14, r14
0x1400363a2  jz      loc_140036543
0x1400363a8  mov     r8, r14; wchar_t *
0x1400363ab  mov     rdx, r15; wchar_t *
0x1400363ae  lea     rcx, [rbp+20B0h+var_2130]; this
0x1400363b2  call    ?LoadSettings@CLiveDumpSettings@@QEAAJPEB_W0@Z; CLiveDumpSettings::LoadSettings(wchar_t const *,wchar_t const *)
0x1400363b7  mov     ebx, eax
0x1400363b9  xor     eax, eax
0x1400363bb  test    ebx, ebx
0x1400363bd  js      loc_140036548
0x1400363c3  mov     rdx, [rbp+20B0h+var_2128]
0x1400363c7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400363cb  test    rdx, rdx
0x1400363ce  jz      short loc_1400363DF
0x1400363d0  mov     r8, rbx
0x1400363d3  inc     r8
0x1400363d6  cmp     [rdx+r8*2], ax
0x1400363db  jnz     short loc_1400363D3
0x1400363dd  jmp     short loc_1400363E2
0x1400363df  mov     r8, rax
0x1400363e2  lea     rcx, [rbp+20B0h+var_68]
0x1400363e9  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400363ee  xor     ecx, ecx
0x1400363f0  inc     rbx
0x1400363f3  cmp     [r14+rbx*2], cx
0x1400363f8  jnz     short loc_1400363F0
0x1400363fa  mov     r8, rbx
0x1400363fd  mov     rdx, r14
0x140036400  lea     rcx, [rbp+20B0h+var_68]
0x140036407  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14003640c  mov     [rsp+21B0h+phkResult], r14
0x140036411  mov     r9, r15
0x140036414  lea     r8, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x14003641b  lea     rdx, aSFulllivekerne_0; "%s\\FullLiveKernelReports\\%s\\%s"
0x140036422  lea     rcx, [rsp+21B0h+lpSubKey]
0x140036427  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14003642c  mov     ebx, eax
0x14003642e  test    eax, eax
0x140036430  jns     short loc_140036443
0x140036432  lea     rax, aFailedToSprint; "Failed to sprintf registry key name"
0x140036439  mov     edx, 4CAh
0x14003643e  jmp     loc_140036554
0x140036443  lea     rax, [rsp+21B0h+hKey]
0x140036448  mov     [rsp+21B0h+phkResult], rax; phkResult
0x14003644d  mov     r9d, 3001Bh; samDesired
0x140036453  xor     r8d, r8d; ulOptions
0x140036456  mov     rdx, [rsp+21B0h+lpSubKey]; lpSubKey
0x14003645b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140036462  call    cs:__imp_RegOpenKeyExW
0x140036468  mov     ebx, eax
0x14003646a  test    eax, eax
0x14003646c  jz      short loc_1400364AF
0x14003646e  jle     short loc_140036479
0x140036470  movzx   ebx, bx
0x140036473  or      ebx, 80070000h
0x140036479  mov     rcx, [rbp+20B8h]; this
0x140036480  mov     rax, [rsp+21B0h+lpSubKey]
0x140036485  mov     [rsp+21B0h+var_2180], rax; char *
0x14003648a  lea     rax, aCouldNotOpenKe; "Could not open key %ws"
0x140036491  mov     qword ptr [rsp+21B0h+var_2188], rax; int
0x140036496  mov     dword ptr [rsp+21B0h+phkResult], ebx; wil::details *
0x14003649a  mov     r9, rdi; char *
0x14003649d  mov     r8, rsi; unsigned int
0x1400364a0  mov     edx, 4D7h; void *
0x1400364a5  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400364aa  jmp     loc_14003656F
0x1400364af  lea     rax, [rsp+21B0h+var_2148]
0x1400364b4  mov     [rsp+21B0h+phkResult], rax; phkResult
0x1400364b9  mov     r9d, 1; samDesired
0x1400364bf  xor     r8d, r8d; ulOptions
0x1400364c2  lea     rdx, aBusy; "Busy"
0x1400364c9  mov     rcx, [rsp+21B0h+hKey]; hKey
0x1400364ce  call    cs:__imp_RegOpenKeyExW
0x1400364d4  test    eax, eax
0x1400364d6  jnz     short loc_140036514
0x1400364d8  mov     rcx, [rbp+20B8h]; this
0x1400364df  mov     [rsp+21B0h+var_2178], r14
0x1400364e4  mov     [rsp+21B0h+var_2180], r15; char *
0x1400364e9  lea     rax, aFullReportIsBu; "Full Report is busy for %ws - %ws"
0x1400364f0  mov     qword ptr [rsp+21B0h+var_2188], rax; int
0x1400364f5  mov     dword ptr [rsp+21B0h+phkResult], 80000000h; wil::details *
0x1400364fd  mov     r9, rdi; char *
0x140036500  mov     r8, rsi; unsigned int
0x140036503  mov     edx, 4E8h; void *
0x140036508  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003650d  mov     ebx, 8007139Fh
0x140036512  jmp     short loc_14003656F
0x140036514  lea     rcx, [rbp+20B0h+var_2130]; this
0x140036518  call    ?ProcessLiveDump@CLiveDumpProcessor@@QEAAJXZ; CLiveDumpProcessor::ProcessLiveDump(void)
0x14003651d  mov     ebx, eax
0x14003651f  test    eax, eax
0x140036521  jns     short loc_140036531
0x140036523  lea     rax, aProcesslivedum; "ProcessLiveDump failed"
0x14003652a  mov     edx, 4F6h
0x14003652f  jmp     short loc_140036554
0x140036531  mov     r8, r14; lpSubKey
0x140036534  mov     rdx, r15; wchar_t *
0x140036537  mov     rcx, r12; this
0x14003653a  call    ?ReportLiveReport@CKernelReport@@QEAAJPEB_W0@Z; CKernelReport::ReportLiveReport(wchar_t const *,wchar_t const *)
0x14003653f  mov     ebx, eax
0x140036541  jmp     short loc_14003656F
0x140036543  mov     ebx, 80070057h
0x140036548  lea     rax, aLivedumpproces; "liveDumpProcessor initialization failed"
0x14003654f  mov     edx, 4BBh; void *
0x140036554  mov     qword ptr [rsp+21B0h+var_2188], rax; int
0x140036559  mov     dword ptr [rsp+21B0h+phkResult], ebx; wil::details *
0x14003655d  mov     r9, rdi; char *
0x140036560  mov     r8, rsi; unsigned int
0x140036563  mov     rcx, [rbp+20B8h]; this
0x14003656a  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003656f  mov     rcx, r13; hMutex
0x140036572  call    cs:__imp_ReleaseMutex
0x140036578  jmp     short loc_1400365C9
0x14003657a  call    cs:__imp_GetLastError
0x140036580  mov     ebx, eax
0x140036582  test    eax, eax
0x140036584  jle     short loc_14003658F
0x140036586  movzx   ebx, ax
0x140036589  or      ebx, 80070000h
0x14003658f  mov     eax, 80004005h
0x140036594  test    ebx, ebx
0x140036596  cmovns  ebx, eax
0x140036599  mov     rcx, [rbp+20B8h]; this
0x1400365a0  lea     rax, aCreateeventFai_0; "CreateEvent failed for live conversion"
0x1400365a7  mov     qword ptr [rsp+21B0h+var_2188], rax; int
0x1400365ac  mov     dword ptr [rsp+21B0h+phkResult], ebx; wil::details *
0x1400365b0  lea     r9, aCkernelreportC_2; "CKernelReport::ConvertLiveDumpAndReport"
0x1400365b7  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x1400365be  mov     edx, 4A8h; void *
0x1400365c3  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400365c8  nop
0x1400365c9  lea     rax, [r13+1]
0x1400365cd  cmp     rax, 1
0x1400365d1  jbe     short loc_1400365DD
0x1400365d3  mov     rcx, r13; hObject
0x1400365d6  call    cs:__imp_CloseHandle
0x1400365dc  nop
0x1400365dd  lea     rax, [rsp+21B0h+var_2158]
0x1400365e2  mov     rcx, [rsp+21B0h+lpSubKey]; void *
0x1400365e7  cmp     rcx, rax
0x1400365ea  jz      short loc_1400365F9
0x1400365ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400365f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400365f8  nop
0x1400365f9  lea     rcx, [rbp+20B0h+var_2130]; this
0x1400365fd  call    ??1CLiveDumpProcessor@@QEAA@XZ; CLiveDumpProcessor::~CLiveDumpProcessor(void)
0x140036602  mov     eax, ebx
0x140036604  mov     rcx, [rbp+20B0h+var_40]
0x14003660b  xor     rcx, rsp; StackCookie
0x14003660e  call    __security_check_cookie
0x140036613  mov     rbx, [rsp+21B0h+arg_18]
0x14003661b  add     rsp, 2180h
0x140036622  pop     r15
0x140036624  pop     r14
0x140036626  pop     r13
0x140036628  pop     r12
0x14003662a  pop     rdi
0x14003662b  pop     rsi
0x14003662c  pop     rbp
0x14003662d  retn
```
