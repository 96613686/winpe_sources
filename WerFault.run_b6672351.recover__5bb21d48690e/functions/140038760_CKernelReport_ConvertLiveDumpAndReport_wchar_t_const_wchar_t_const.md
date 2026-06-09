# CKernelReport::ConvertLiveDumpAndReport(wchar_t const *,wchar_t const *)

- ea: `0x140038760`
- end: `0x140038bd1`
- name: `?ConvertLiveDumpAndReport@CKernelReport@@QEAAJPEB_W0@Z`
- size: `1137`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x140036e5c`
- `0x140037ec4`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x1400054e4`
- `0x14000ca20`
- `0x140014a88`
- `0x1400372dc`
- `0x140037594`
- `0x140038760`
- `0x14003c2bc`
- `0x1400416f4`
- `0x1400420a4`
- `0x14005f510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400389e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140038a58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400389e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140038a58`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140038b02`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140038b02`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400388a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400388a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400388c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038b10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400388c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038b10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140038b72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140038b72`

## string_xrefs

- `0x1400388e8`: `CreateEvent succeeded for %ws`
- `0x140038b3c`: `CreateEvent failed for live conversion`
- `0x1400389b6`: `Failed to sprintf registry key name`
- `0x140038a14`: `Could not open key %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
      (void *)0x4A2,
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
          v11 = 1214;
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
            (void *)0x4CB,
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
            v11 = 1258;
            goto LABEL_24;
          }
          Settings = CKernelReport::ReportLiveReport(this, a2, a3);
        }
        else
        {
          LODWORD(phkResulta) = 0x80000000;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0x4DC,
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
    v11 = 1199;
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
    (void *)0x49C,
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
0x140038760  mov     [rsp-8+arg_18], rbx
0x140038765  push    rbp
0x140038766  push    rsi
0x140038767  push    rdi
0x140038768  push    r12
0x14003876a  push    r13
0x14003876c  push    r14
0x14003876e  push    r15
0x140038770  lea     rbp, [rsp-2080h]
0x140038778  mov     eax, 2180h
0x14003877d  call    _alloca_probe
0x140038782  sub     rsp, rax
0x140038785  mov     rax, cs:__security_cookie
0x14003878c  xor     rax, rsp
0x14003878f  mov     [rbp+20B0h+var_40], rax
0x140038796  mov     r14, r8
0x140038799  mov     r15, rdx
0x14003879c  mov     r12, rcx
0x14003879f  xor     ebx, ebx
0x1400387a1  mov     [rsp+21B0h+var_2148], rbx
0x1400387a6  mov     [rsp+21B0h+hKey], rbx
0x1400387ab  lea     rax, [rbp+20B0h+var_2118]
0x1400387af  mov     [rbp+20B0h+var_2128], rax
0x1400387b3  lea     rax, [rbp+20B0h+var_2118]
0x1400387b7  mov     [rbp+20B0h+var_2120], rax
0x1400387bb  mov     [rbp+20B0h+var_2118], bx
0x1400387bf  lea     rax, [rbp+20B0h+var_20F8]
0x1400387c3  mov     [rbp+20B0h+var_2108], rax
0x1400387c7  lea     rax, [rbp+20B0h+var_20F8]
0x1400387cb  mov     [rbp+20B0h+var_2100], rax
0x1400387cf  mov     [rbp+20B0h+var_20F8], bx
0x1400387d3  lea     rax, [rbp+20B0h+var_20D8]
0x1400387d7  mov     [rbp+20B0h+var_20E8], rax
0x1400387db  lea     rax, [rbp+20B0h+var_20D8]
0x1400387df  mov     [rbp+20B0h+var_20E0], rax
0x1400387e3  mov     [rbp+20B0h+var_20D8], bx
0x1400387e7  lea     rax, [rbp+20B0h+var_20B8]
0x1400387eb  mov     [rbp+20B0h+var_20C8], rax
0x1400387ef  lea     rax, [rbp+20B0h+var_20B8]
0x1400387f3  mov     [rbp+20B0h+var_20C0], rax
0x1400387f7  mov     [rbp+20B0h+var_20B8], bx
0x1400387fb  lea     edi, [rbx+1]
0x1400387fe  mov     [rbp+20B0h+var_2130], edi
0x140038801  mov     [rbp+20B0h+var_212C], edi
0x140038804  xor     edx, edx; Val
0x140038806  mov     r8d, 2000h; Size
0x14003880c  lea     rcx, [rbp+20B0h+var_20A8]; void *
0x140038810  call    memset_0
0x140038815  lea     rax, [rbp+20B0h+var_98]
0x14003881c  mov     [rbp+20B0h+var_A8], rax
0x140038823  lea     rax, [rbp+20B0h+var_98]
0x14003882a  mov     [rbp+20B0h+var_A0], rax
0x140038831  mov     [rbp+20B0h+var_98], bx
0x140038838  lea     rax, [rbp+20B0h+var_78]
0x14003883f  mov     [rbp+20B0h+var_88], rax
0x140038846  lea     rax, [rbp+20B0h+var_78]
0x14003884d  mov     [rbp+20B0h+var_80], rax
0x140038854  mov     [rbp+20B0h+var_78], bx
0x14003885b  lea     rax, [rbp+20B0h+var_58]
0x140038862  mov     [rbp+20B0h+var_68], rax
0x140038869  lea     rax, [rbp+20B0h+var_58]
0x140038870  mov     [rbp+20B0h+var_60], rax
0x140038877  mov     [rbp+20B0h+var_58], bx
0x14003887e  lea     rax, [rsp+21B0h+var_2158]
0x140038883  mov     [rsp+21B0h+lpSubKey], rax
0x140038888  lea     rax, [rsp+21B0h+var_2158]
0x14003888d  mov     [rsp+21B0h+var_2160], rax
0x140038892  mov     [rsp+21B0h+var_2158], bx
0x140038897  lea     rsi, aGlobalWerkerne; "Global\\WerKernelVerticalConvertingLive"...
0x14003889e  mov     r8, rsi; lpName
0x1400388a1  mov     edx, edi; bInitialOwner
0x1400388a3  xor     ecx, ecx; lpMutexAttributes
0x1400388a5  call    cs:__imp_CreateMutexW
0x1400388ac  nop     dword ptr [rax+rax+00h]
0x1400388b1  mov     r13, rax
0x1400388b4  mov     [rsp+21B0h+var_2140], rax
0x1400388b9  inc     rax
0x1400388bc  cmp     rax, rdi
0x1400388bf  jbe     loc_140038B10
0x1400388c5  call    cs:__imp_GetLastError
0x1400388cc  nop     dword ptr [rax+rax+00h]
0x1400388d1  cmp     eax, 0B7h
0x1400388d6  jz      loc_140038B10
0x1400388dc  mov     rcx, [rbp+20B8h]; this
0x1400388e3  mov     [rsp+21B0h+var_2180], rsi; char *
0x1400388e8  lea     rax, aCreateeventSuc; "CreateEvent succeeded for %ws"
0x1400388ef  mov     qword ptr [rsp+21B0h+var_2188], rax; int
0x1400388f4  mov     dword ptr [rsp+21B0h+phkResult], 80000000h; wil::details *
0x1400388fc  lea     rdi, aCkernelreportC_2; "CKernelReport::ConvertLiveDumpAndReport"
0x140038903  mov     r9, rdi; char *
0x140038906  lea     rsi, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003890d  mov     r8, rsi; unsigned int
0x140038910  mov     edx, 4A2h; void *
0x140038915  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003891a  test    r15, r15
0x14003891d  jz      loc_140038AD3
0x140038923  test    r14, r14
0x140038926  jz      loc_140038AD3
0x14003892c  mov     r8, r14; wchar_t *
0x14003892f  mov     rdx, r15; wchar_t *
0x140038932  lea     rcx, [rbp+20B0h+var_2130]; this
0x140038936  call    ?LoadSettings@CLiveDumpSettings@@QEAAJPEB_W0@Z; CLiveDumpSettings::LoadSettings(wchar_t const *,wchar_t const *)
0x14003893b  mov     ebx, eax
0x14003893d  xor     eax, eax
0x14003893f  test    ebx, ebx
0x140038941  js      loc_140038AD8
0x140038947  mov     rdx, [rbp+20B0h+var_2128]
0x14003894b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003894f  test    rdx, rdx
0x140038952  jz      short loc_140038963
0x140038954  mov     r8, rbx
0x140038957  inc     r8
0x14003895a  cmp     [rdx+r8*2], ax
0x14003895f  jnz     short loc_140038957
0x140038961  jmp     short loc_140038966
0x140038963  mov     r8, rax
0x140038966  lea     rcx, [rbp+20B0h+var_68]
0x14003896d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140038972  xor     ecx, ecx
0x140038974  inc     rbx
0x140038977  cmp     [r14+rbx*2], cx
0x14003897c  jnz     short loc_140038974
0x14003897e  mov     r8, rbx
0x140038981  mov     rdx, r14
0x140038984  lea     rcx, [rbp+20B0h+var_68]
0x14003898b  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140038990  mov     [rsp+21B0h+phkResult], r14
0x140038995  mov     r9, r15
0x140038998  lea     r8, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x14003899f  lea     rdx, aSFulllivekerne_0; "%s\\FullLiveKernelReports\\%s\\%s"
0x1400389a6  lea     rcx, [rsp+21B0h+lpSubKey]
0x1400389ab  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400389b0  mov     ebx, eax
0x1400389b2  test    eax, eax
0x1400389b4  jns     short loc_1400389C7
0x1400389b6  lea     rax, aFailedToSprint; "Failed to sprintf registry key name"
0x1400389bd  mov     edx, 4BEh
0x1400389c2  jmp     loc_140038AE4
0x1400389c7  lea     rax, [rsp+21B0h+hKey]
0x1400389cc  mov     [rsp+21B0h+phkResult], rax; phkResult
0x1400389d1  mov     r9d, 3001Bh; samDesired
0x1400389d7  xor     r8d, r8d; ulOptions
0x1400389da  mov     rdx, [rsp+21B0h+lpSubKey]; lpSubKey
0x1400389df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400389e6  call    cs:__imp_RegOpenKeyExW
0x1400389ed  nop     dword ptr [rax+rax+00h]
0x1400389f2  mov     ebx, eax
0x1400389f4  test    eax, eax
0x1400389f6  jz      short loc_140038A39
0x1400389f8  jle     short loc_140038A03
0x1400389fa  movzx   ebx, bx
0x1400389fd  or      ebx, 80070000h
0x140038a03  mov     rcx, [rbp+20B8h]; this
0x140038a0a  mov     rax, [rsp+21B0h+lpSubKey]
0x140038a0f  mov     [rsp+21B0h+var_2180], rax; char *
0x140038a14  lea     rax, aCouldNotOpenKe; "Could not open key %ws"
0x140038a1b  mov     qword ptr [rsp+21B0h+var_2188], rax; int
0x140038a20  mov     dword ptr [rsp+21B0h+phkResult], ebx; wil::details *
0x140038a24  mov     r9, rdi; char *
0x140038a27  mov     r8, rsi; unsigned int
0x140038a2a  mov     edx, 4CBh; void *
0x140038a2f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038a34  jmp     loc_140038AFF
0x140038a39  lea     rax, [rsp+21B0h+var_2148]
0x140038a3e  mov     [rsp+21B0h+phkResult], rax; phkResult
0x140038a43  mov     r9d, 1; samDesired
0x140038a49  xor     r8d, r8d; ulOptions
0x140038a4c  lea     rdx, aBusy; "Busy"
0x140038a53  mov     rcx, [rsp+21B0h+hKey]; hKey
0x140038a58  call    cs:__imp_RegOpenKeyExW
0x140038a5f  nop     dword ptr [rax+rax+00h]
0x140038a64  test    eax, eax
0x140038a66  jnz     short loc_140038AA4
0x140038a68  mov     rcx, [rbp+20B8h]; this
0x140038a6f  mov     [rsp+21B0h+var_2178], r14
0x140038a74  mov     [rsp+21B0h+var_2180], r15; char *
0x140038a79  lea     rax, aFullReportIsBu; "Full Report is busy for %ws - %ws"
0x140038a80  mov     qword ptr [rsp+21B0h+var_2188], rax; int
0x140038a85  mov     dword ptr [rsp+21B0h+phkResult], 80000000h; wil::details *
0x140038a8d  mov     r9, rdi; char *
0x140038a90  mov     r8, rsi; unsigned int
0x140038a93  mov     edx, 4DCh; void *
0x140038a98  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038a9d  mov     ebx, 8007139Fh
0x140038aa2  jmp     short loc_140038AFF
0x140038aa4  lea     rcx, [rbp+20B0h+var_2130]; this
0x140038aa8  call    ?ProcessLiveDump@CLiveDumpProcessor@@QEAAJXZ; CLiveDumpProcessor::ProcessLiveDump(void)
0x140038aad  mov     ebx, eax
0x140038aaf  test    eax, eax
0x140038ab1  jns     short loc_140038AC1
0x140038ab3  lea     rax, aProcesslivedum; "ProcessLiveDump failed"
0x140038aba  mov     edx, 4EAh
0x140038abf  jmp     short loc_140038AE4
0x140038ac1  mov     r8, r14; lpSubKey
0x140038ac4  mov     rdx, r15; wchar_t *
0x140038ac7  mov     rcx, r12; this
0x140038aca  call    ?ReportLiveReport@CKernelReport@@QEAAJPEB_W0@Z; CKernelReport::ReportLiveReport(wchar_t const *,wchar_t const *)
0x140038acf  mov     ebx, eax
0x140038ad1  jmp     short loc_140038AFF
0x140038ad3  mov     ebx, 80070057h
0x140038ad8  lea     rax, aLivedumpproces; "liveDumpProcessor initialization failed"
0x140038adf  mov     edx, 4AFh; void *
0x140038ae4  mov     qword ptr [rsp+21B0h+var_2188], rax; int
0x140038ae9  mov     dword ptr [rsp+21B0h+phkResult], ebx; wil::details *
0x140038aed  mov     r9, rdi; char *
0x140038af0  mov     r8, rsi; unsigned int
0x140038af3  mov     rcx, [rbp+20B8h]; this
0x140038afa  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038aff  mov     rcx, r13; hMutex
0x140038b02  call    cs:__imp_ReleaseMutex
0x140038b09  nop     dword ptr [rax+rax+00h]
0x140038b0e  jmp     short loc_140038B65
0x140038b10  call    cs:__imp_GetLastError
0x140038b17  nop     dword ptr [rax+rax+00h]
0x140038b1c  mov     ebx, eax
0x140038b1e  test    eax, eax
0x140038b20  jle     short loc_140038B2B
0x140038b22  movzx   ebx, ax
0x140038b25  or      ebx, 80070000h
0x140038b2b  mov     eax, 80004005h
0x140038b30  test    ebx, ebx
0x140038b32  cmovns  ebx, eax
0x140038b35  mov     rcx, [rbp+20B8h]; this
0x140038b3c  lea     rax, aCreateeventFai_0; "CreateEvent failed for live conversion"
0x140038b43  mov     qword ptr [rsp+21B0h+var_2188], rax; int
0x140038b48  mov     dword ptr [rsp+21B0h+phkResult], ebx; wil::details *
0x140038b4c  lea     r9, aCkernelreportC_2; "CKernelReport::ConvertLiveDumpAndReport"
0x140038b53  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140038b5a  mov     edx, 49Ch; void *
0x140038b5f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038b64  nop
0x140038b65  lea     rax, [r13+1]
0x140038b69  cmp     rax, 1
0x140038b6d  jbe     short loc_140038B7F
0x140038b6f  mov     rcx, r13; hObject
0x140038b72  call    cs:__imp_CloseHandle
0x140038b79  nop     dword ptr [rax+rax+00h]
0x140038b7e  nop
0x140038b7f  lea     rax, [rsp+21B0h+var_2158]
0x140038b84  mov     rcx, [rsp+21B0h+lpSubKey]; void *
0x140038b89  cmp     rcx, rax
0x140038b8c  jz      short loc_140038B9B
0x140038b8e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140038b95  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140038b9a  nop
0x140038b9b  lea     rcx, [rbp+20B0h+var_2130]; this
0x140038b9f  call    ??1CLiveDumpProcessor@@QEAA@XZ; CLiveDumpProcessor::~CLiveDumpProcessor(void)
0x140038ba4  mov     eax, ebx
0x140038ba6  mov     rcx, [rbp+20B0h+var_40]
0x140038bad  xor     rcx, rsp; StackCookie
0x140038bb0  call    __security_check_cookie
0x140038bb5  mov     rbx, [rsp+21B0h+arg_18]
0x140038bbd  add     rsp, 2180h
0x140038bc4  pop     r15
0x140038bc6  pop     r14
0x140038bc8  pop     r13
0x140038bca  pop     r12
0x140038bcc  pop     rdi
0x140038bcd  pop     rsi
0x140038bce  pop     rbp
0x140038bcf  retn
```
