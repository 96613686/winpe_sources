# CKernelReport::ReportLiveReport(wchar_t const *,wchar_t const *)

- ea: `0x140039c40`
- end: `0x14003a0ba`
- name: `?ReportLiveReport@CKernelReport@@QEAAJPEB_W0@Z`
- size: `1146`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this, const wchar_t *, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x14003494c`
- `0x1400361e8`
- `0x140039230`

## callees

- `0x140002728`
- `0x140005468`
- `0x140034d9c`
- `0x140034e60`
- `0x140035090`
- `0x14003546c`
- `0x1400366a0`
- `0x1400380cc`
- `0x140039c40`
- `0x14003a0c0`
- `0x14003f55c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a068`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a089`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a09a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a068`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a089`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a09a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039d8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039ddd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039e2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039e7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039ed5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039d8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039ddd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039e2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039e7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140039ed5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140039fe9`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140039fe9`

## string_xrefs

- `0x140039dac`: `RegOpenKeyEx failed for root`
- `0x140039dfe`: `RegOpenKeyEx failed for root`
- `0x140039e4f`: `RegOpenKeyEx failed for report type`
- `0x140039ea0`: `RegOpenKeyEx failed for report type`
- `0x140039fba`: `Failed live report. Path %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CKernelReport::ReportLiveReport(CKernelReport *this, const wchar_t *a2, LPCWSTR lpSubKey)
{
  signed int Settings; // ebx
  const char *v7; // rax
  __int64 v8; // rdx
  CKernelReport *v9; // rcx
  HKEY *v10; // rax
  LSTATUS v11; // eax
  HKEY *v12; // rax
  LSTATUS v13; // eax
  HKEY *v14; // rax
  LSTATUS v15; // eax
  HKEY *v16; // rax
  LSTATUS v17; // eax
  HKEY *v18; // rax
  __int64 v19; // rcx
  wil::details *phkResult; // [rsp+20h] [rbp-E0h]
  char *v22; // [rsp+30h] [rbp-D0h]
  HKEY v23; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v24; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v25; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v26[2]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v27[12]; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v28[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD *v29; // [rsp+88h] [rbp-78h]
  _WORD *v30; // [rsp+90h] [rbp-70h]
  _WORD v31[8]; // [rsp+98h] [rbp-68h] BYREF
  _WORD *v32; // [rsp+A8h] [rbp-58h]
  _WORD *v33; // [rsp+B0h] [rbp-50h]
  _WORD v34[8]; // [rsp+B8h] [rbp-48h] BYREF
  _WORD *v35; // [rsp+C8h] [rbp-38h]
  _WORD *v36; // [rsp+D0h] [rbp-30h]
  _WORD v37[8]; // [rsp+D8h] [rbp-28h] BYREF
  _WORD *v38; // [rsp+E8h] [rbp-18h]
  _WORD *v39; // [rsp+F0h] [rbp-10h]
  _WORD v40[12]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+128h] [rbp+28h]
  HKEY v42; // [rsp+138h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+148h] [rbp+48h] BYREF

  v24 = 0;
  v42 = 0;
  v23 = 0;
  v25 = 0;
  hKey = 0;
  v26[0] = v27;
  v26[1] = v27;
  v27[0] = 0;
  v29 = v31;
  v30 = v31;
  v31[0] = 0;
  v32 = v34;
  v33 = v34;
  v34[0] = 0;
  v35 = v37;
  v36 = v37;
  v37[0] = 0;
  v38 = v40;
  v39 = v40;
  v40[0] = 0;
  v28[0] = 1;
  v28[1] = 1;
  if ( a2 && lpSubKey )
  {
    Settings = CLiveDumpSettings::LoadSettings((CLiveDumpSettings *)v28, 0, 0);
    if ( Settings >= 0 )
    {
      v10 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_wszLiveKernelReportsQueueRoot, 0, 0xF003Fu, v10);
      Settings = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          Settings = (unsigned __int16)v11 | 0x80070000;
        if ( Settings >= 0 )
          Settings = -2147467259;
        v7 = "RegOpenKeyEx failed for root";
        v8 = 2383;
      }
      else
      {
        v12 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v24);
        v13 = RegOpenKeyExW(hKey, L"LiveKernelReports", 0, 0xF003Fu, v12);
        Settings = v13;
        if ( v13 )
        {
          if ( v13 > 0 )
            Settings = (unsigned __int16)v13 | 0x80070000;
          if ( Settings >= 0 )
            Settings = -2147467259;
          v7 = "RegOpenKeyEx failed for root";
          v8 = 2397;
        }
        else
        {
          v14 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v42);
          v15 = RegOpenKeyExW(v24, a2, 0, 0x10008u, v14);
          Settings = v15;
          if ( v15 )
          {
            if ( v15 > 0 )
              Settings = (unsigned __int16)v15 | 0x80070000;
            if ( Settings >= 0 )
              Settings = -2147467259;
            v7 = "RegOpenKeyEx failed for report type";
            v8 = 2411;
          }
          else
          {
            v16 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v23);
            v17 = RegOpenKeyExW(v42, lpSubKey, 0, 9u, v16);
            Settings = v17;
            if ( v17 )
            {
              if ( v17 > 0 )
                Settings = (unsigned __int16)v17 | 0x80070000;
              if ( Settings >= 0 )
                Settings = -2147467259;
              v7 = "RegOpenKeyEx failed for report type";
              v8 = 2425;
            }
            else
            {
              v18 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v25);
              if ( !RegOpenKeyExW(v23, L"Busy", 0, 1u, v18) )
              {
                LODWORD(phkResult) = 0x80000000;
                wil::details::in1diag4::Log_HrMsg(
                  retaddr,
                  (void *)0x986,
                  (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                  "CKernelReport::ReportLiveReport",
                  phkResult,
                  (int)"Report is busy for %ws - %ws",
                  (const char *)a2,
                  lpSubKey);
                Settings = -2147019873;
                goto LABEL_41;
              }
              Settings = CKernelReport::GetLiveReportsStoreRoot(v19, v26);
              if ( Settings >= 0 )
              {
                Settings = tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             v26,
                             L"%s\\%s",
                             a2,
                             lpSubKey);
                if ( Settings >= 0 )
                {
                  Settings = CKernelReport::ExtractBootId(this, v26[0]);
                  if ( Settings >= 0 )
                  {
                    Settings = CKernelReport::SendLiveReport(this, v26[0], lpSubKey);
                    if ( Settings < 0 )
                    {
                      LODWORD(phkResult) = Settings;
                      wil::details::in1diag4::Log_HrMsg(
                        retaddr,
                        (void *)0x9AA,
                        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                        "CKernelReport::ReportLiveReport",
                        phkResult,
                        (int)"Failed live report. Path %ws",
                        (const char *)v26[0]);
                    }
                    RegDeleteKeyW(v42, lpSubKey);
                    goto LABEL_41;
                  }
                  v7 = "ExtractBootId failed";
                  v8 = 2466;
                }
                else
                {
                  v7 = "Sprintf Failed";
                  v8 = 2458;
                }
              }
              else
              {
                v7 = "Failed to get the live kernel report";
                v8 = 2451;
              }
            }
          }
        }
      }
    }
    else
    {
      v7 = "Failed to load livedump settings";
      v8 = 2370;
    }
    LODWORD(phkResult) = Settings;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ReportLiveReport",
      phkResult,
      (int)v7,
      v22);
LABEL_41:
    CKernelReport::CheckAndDeleteLiveMemoryDump(v9);
    goto LABEL_43;
  }
  Settings = -2147024809;
  LODWORD(phkResult) = -2147024809;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x937,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::ReportLiveReport",
    phkResult,
    (int)"Invalid params",
    v22);
LABEL_43:
  CLiveDumpSettings::~CLiveDumpSettings((CLiveDumpSettings *)v28);
  if ( v26[0] != v27 )
    operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v25 )
    RegCloseKey(v25);
  if ( v23 )
    RegCloseKey(v23);
  if ( v42 )
    RegCloseKey(v42);
  if ( v24 )
    RegCloseKey(v24);
  return (unsigned int)Settings;
}

```

## disassembly

```asm
0x140039c40  mov     [rsp-8+arg_0], rbx
0x140039c45  mov     [rsp-8+arg_10], rsi
0x140039c4a  push    rbp
0x140039c4b  push    rdi
0x140039c4c  push    r14
0x140039c4e  lea     rbp, [rsp-10h]
0x140039c53  sub     rsp, 110h
0x140039c5a  mov     rdi, r8
0x140039c5d  mov     rsi, rdx
0x140039c60  mov     r14, rcx
0x140039c63  mov     [rsp+120h+var_D8], 0
0x140039c6c  mov     [rbp+20h+arg_8], 0
0x140039c74  mov     [rsp+120h+var_E0], 0
0x140039c7d  mov     [rsp+120h+var_D0], 0
0x140039c86  mov     [rbp+20h+hKey], 0
0x140039c8e  lea     rax, [rsp+120h+var_B8]
0x140039c93  mov     [rsp+120h+var_C8], rax
0x140039c98  lea     rax, [rsp+120h+var_B8]
0x140039c9d  mov     [rsp+120h+var_C0], rax
0x140039ca2  xor     eax, eax
0x140039ca4  mov     [rsp+120h+var_B8], ax
0x140039ca9  lea     rax, [rbp+20h+var_88]
0x140039cad  mov     [rbp+20h+var_98], rax
0x140039cb1  lea     rax, [rbp+20h+var_88]
0x140039cb5  mov     [rbp+20h+var_90], rax
0x140039cb9  xor     eax, eax
0x140039cbb  mov     [rbp+20h+var_88], ax
0x140039cbf  lea     rax, [rbp+20h+var_68]
0x140039cc3  mov     [rbp+20h+var_78], rax
0x140039cc7  lea     rax, [rbp+20h+var_68]
0x140039ccb  mov     [rbp+20h+var_70], rax
0x140039ccf  xor     eax, eax
0x140039cd1  mov     [rbp+20h+var_68], ax
0x140039cd5  lea     rax, [rbp+20h+var_48]
0x140039cd9  mov     [rbp+20h+var_58], rax
0x140039cdd  lea     rax, [rbp+20h+var_48]
0x140039ce1  mov     [rbp+20h+var_50], rax
0x140039ce5  xor     eax, eax
0x140039ce7  mov     [rbp+20h+var_48], ax
0x140039ceb  lea     rax, [rbp+20h+var_28]
0x140039cef  mov     [rbp+20h+var_38], rax
0x140039cf3  lea     rax, [rbp+20h+var_28]
0x140039cf7  mov     [rbp+20h+var_30], rax
0x140039cfb  xor     eax, eax
0x140039cfd  mov     [rbp+20h+var_28], ax
0x140039d01  mov     [rbp+20h+var_A0], 1
0x140039d08  mov     [rbp+20h+var_9C], 1
0x140039d0f  test    rdx, rdx
0x140039d12  jz      loc_140039FF6
0x140039d18  test    r8, r8
0x140039d1b  jz      loc_140039FF6
0x140039d21  xor     r8d, r8d; wchar_t *
0x140039d24  xor     edx, edx; wchar_t *
0x140039d26  lea     rcx, [rbp+20h+var_A0]; this
0x140039d2a  call    ?LoadSettings@CLiveDumpSettings@@QEAAJPEB_W0@Z; CLiveDumpSettings::LoadSettings(wchar_t const *,wchar_t const *)
0x140039d2f  mov     ebx, eax
0x140039d31  test    eax, eax
0x140039d33  jns     short loc_140039D66
0x140039d35  lea     rax, aFailedToLoadLi; "Failed to load livedump settings"
0x140039d3c  mov     edx, 942h; void *
0x140039d41  mov     qword ptr [rsp+120h+var_F8], rax; int
0x140039d46  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140039d4d  lea     r9, aCkernelreportR_0; "CKernelReport::ReportLiveReport"
0x140039d54  mov     dword ptr [rsp+120h+phkResult], ebx; wil::details *
0x140039d58  mov     rcx, [rbp+28h]; this
0x140039d5c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140039d61  jmp     loc_140039FEF
0x140039d66  lea     rcx, [rbp+20h+hKey]
0x140039d6a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140039d6f  mov     [rsp+120h+phkResult], rax; phkResult
0x140039d74  mov     r9d, 0F003Fh; samDesired
0x140039d7a  xor     r8d, r8d; ulOptions
0x140039d7d  lea     rdx, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x140039d84  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140039d8b  call    cs:__imp_RegOpenKeyExW
0x140039d91  mov     ebx, eax
0x140039d93  test    eax, eax
0x140039d95  jz      short loc_140039DBA
0x140039d97  jle     short loc_140039DA2
0x140039d99  movzx   ebx, ax
0x140039d9c  or      ebx, 80070000h
0x140039da2  mov     eax, 80004005h
0x140039da7  test    ebx, ebx
0x140039da9  cmovns  ebx, eax
0x140039dac  lea     rax, aRegopenkeyexFa; "RegOpenKeyEx failed for root"
0x140039db3  mov     edx, 94Fh
0x140039db8  jmp     short loc_140039D41
0x140039dba  lea     rcx, [rsp+120h+var_D8]
0x140039dbf  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140039dc4  mov     [rsp+120h+phkResult], rax; phkResult
0x140039dc9  mov     r9d, 0F003Fh; samDesired
0x140039dcf  xor     r8d, r8d; ulOptions
0x140039dd2  lea     rdx, aLivekernelrepo_0; "LiveKernelReports"
0x140039dd9  mov     rcx, [rbp+20h+hKey]; hKey
0x140039ddd  call    cs:__imp_RegOpenKeyExW
0x140039de3  mov     ebx, eax
0x140039de5  test    eax, eax
0x140039de7  jz      short loc_140039E0F
0x140039de9  jle     short loc_140039DF4
0x140039deb  movzx   ebx, ax
0x140039dee  or      ebx, 80070000h
0x140039df4  mov     eax, 80004005h
0x140039df9  test    ebx, ebx
0x140039dfb  cmovns  ebx, eax
0x140039dfe  lea     rax, aRegopenkeyexFa; "RegOpenKeyEx failed for root"
0x140039e05  mov     edx, 95Dh
0x140039e0a  jmp     loc_140039D41
0x140039e0f  lea     rcx, [rbp+20h+arg_8]
0x140039e13  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140039e18  mov     [rsp+120h+phkResult], rax; phkResult
0x140039e1d  mov     r9d, 10008h; samDesired
0x140039e23  xor     r8d, r8d; ulOptions
0x140039e26  mov     rdx, rsi; lpSubKey
0x140039e29  mov     rcx, [rsp+120h+var_D8]; hKey
0x140039e2e  call    cs:__imp_RegOpenKeyExW
0x140039e34  mov     ebx, eax
0x140039e36  test    eax, eax
0x140039e38  jz      short loc_140039E60
0x140039e3a  jle     short loc_140039E45
0x140039e3c  movzx   ebx, ax
0x140039e3f  or      ebx, 80070000h
0x140039e45  mov     eax, 80004005h
0x140039e4a  test    ebx, ebx
0x140039e4c  cmovns  ebx, eax
0x140039e4f  lea     rax, aRegopenkeyexFa_1; "RegOpenKeyEx failed for report type"
0x140039e56  mov     edx, 96Bh
0x140039e5b  jmp     loc_140039D41
0x140039e60  lea     rcx, [rsp+120h+var_E0]
0x140039e65  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140039e6a  mov     [rsp+120h+phkResult], rax; phkResult
0x140039e6f  mov     r9d, 9; samDesired
0x140039e75  xor     r8d, r8d; ulOptions
0x140039e78  mov     rdx, rdi; lpSubKey
0x140039e7b  mov     rcx, [rbp+20h+arg_8]; hKey
0x140039e7f  call    cs:__imp_RegOpenKeyExW
0x140039e85  mov     ebx, eax
0x140039e87  test    eax, eax
0x140039e89  jz      short loc_140039EB1
0x140039e8b  jle     short loc_140039E96
0x140039e8d  movzx   ebx, ax
0x140039e90  or      ebx, 80070000h
0x140039e96  mov     eax, 80004005h
0x140039e9b  test    ebx, ebx
0x140039e9d  cmovns  ebx, eax
0x140039ea0  lea     rax, aRegopenkeyexFa_1; "RegOpenKeyEx failed for report type"
0x140039ea7  mov     edx, 979h
0x140039eac  jmp     loc_140039D41
0x140039eb1  lea     rcx, [rsp+120h+var_D0]
0x140039eb6  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140039ebb  mov     [rsp+120h+phkResult], rax; phkResult
0x140039ec0  mov     r9d, 1; samDesired
0x140039ec6  xor     r8d, r8d; ulOptions
0x140039ec9  lea     rdx, aBusy; "Busy"
0x140039ed0  mov     rcx, [rsp+120h+var_E0]; hKey
0x140039ed5  call    cs:__imp_RegOpenKeyExW
0x140039edb  test    eax, eax
0x140039edd  jnz     short loc_140039F23
0x140039edf  mov     rcx, [rbp+28h]; this
0x140039ee3  mov     [rsp+120h+var_E8], rdi
0x140039ee8  mov     [rsp+120h+var_F0], rsi; char *
0x140039eed  lea     rax, aReportIsBusyFo; "Report is busy for %ws - %ws"
0x140039ef4  mov     qword ptr [rsp+120h+var_F8], rax; int
0x140039ef9  mov     dword ptr [rsp+120h+phkResult], 80000000h; wil::details *
0x140039f01  lea     r9, aCkernelreportR_0; "CKernelReport::ReportLiveReport"
0x140039f08  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140039f0f  mov     edx, 986h; void *
0x140039f14  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140039f19  mov     ebx, 8007139Fh
0x140039f1e  jmp     loc_140039FEF
0x140039f23  lea     rdx, [rsp+120h+var_C8]
0x140039f28  call    ?GetLiveReportsStoreRoot@CKernelReport@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CKernelReport::GetLiveReportsStoreRoot(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140039f2d  mov     ebx, eax
0x140039f2f  test    eax, eax
0x140039f31  jns     short loc_140039F44
0x140039f33  lea     rax, aFailedToGetThe; "Failed to get the live kernel report"
0x140039f3a  mov     edx, 993h
0x140039f3f  jmp     loc_140039D41
0x140039f44  mov     r9, rdi
0x140039f47  mov     r8, rsi
0x140039f4a  lea     rdx, aSS_3; "%s\\%s"
0x140039f51  lea     rcx, [rsp+120h+var_C8]
0x140039f56  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140039f5b  mov     ebx, eax
0x140039f5d  test    eax, eax
0x140039f5f  jns     short loc_140039F72
0x140039f61  lea     rax, aSprintfFailed_0; "Sprintf Failed"
0x140039f68  mov     edx, 99Ah
0x140039f6d  jmp     loc_140039D41
0x140039f72  mov     rdx, [rsp+120h+var_C8]; wchar_t *
0x140039f77  mov     rcx, r14; this
0x140039f7a  call    ?ExtractBootId@CKernelReport@@AEAAJPEB_W@Z; CKernelReport::ExtractBootId(wchar_t const *)
0x140039f7f  mov     ebx, eax
0x140039f81  test    eax, eax
0x140039f83  jns     short loc_140039F96
0x140039f85  lea     rax, aExtractbootidF; "ExtractBootId failed"
0x140039f8c  mov     edx, 9A2h
0x140039f91  jmp     loc_140039D41
0x140039f96  mov     r8, rdi; wchar_t *
0x140039f99  mov     rdx, [rsp+120h+var_C8]; wchar_t *
0x140039f9e  mov     rcx, r14; this
0x140039fa1  call    ?SendLiveReport@CKernelReport@@AEAAJPEB_W0@Z; CKernelReport::SendLiveReport(wchar_t const *,wchar_t const *)
0x140039fa6  mov     ebx, eax
0x140039fa8  test    eax, eax
0x140039faa  jns     short loc_140039FE2
0x140039fac  mov     rcx, [rbp+28h]; this
0x140039fb0  mov     rax, [rsp+120h+var_C8]
0x140039fb5  mov     [rsp+120h+var_F0], rax; char *
0x140039fba  lea     rax, aFailedLiveRepo; "Failed live report. Path %ws"
0x140039fc1  mov     qword ptr [rsp+120h+var_F8], rax; int
0x140039fc6  mov     dword ptr [rsp+120h+phkResult], ebx; wil::details *
0x140039fca  lea     r9, aCkernelreportR_0; "CKernelReport::ReportLiveReport"
0x140039fd1  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140039fd8  mov     edx, 9AAh; void *
0x140039fdd  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140039fe2  mov     rdx, rdi; lpSubKey
0x140039fe5  mov     rcx, [rbp+20h+arg_8]; hKey
0x140039fe9  call    cs:__imp_RegDeleteKeyW
0x140039fef  call    ?CheckAndDeleteLiveMemoryDump@CKernelReport@@AEAAXXZ; CKernelReport::CheckAndDeleteLiveMemoryDump(void)
0x140039ff4  jmp     short loc_14003A028
0x140039ff6  mov     rcx, [rbp+28h]; this
0x140039ffa  lea     rax, aInvalidParams; "Invalid params"
0x14003a001  mov     qword ptr [rsp+120h+var_F8], rax; int
0x14003a006  mov     ebx, 80070057h
0x14003a00b  mov     dword ptr [rsp+120h+phkResult], ebx; wil::details *
0x14003a00f  lea     r9, aCkernelreportR_0; "CKernelReport::ReportLiveReport"
0x14003a016  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003a01d  mov     edx, 937h; void *
0x14003a022  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003a027  nop
0x14003a028  lea     rcx, [rbp+20h+var_A0]; this
0x14003a02c  call    ??1CLiveDumpSettings@@QEAA@XZ; CLiveDumpSettings::~CLiveDumpSettings(void)
0x14003a031  nop
0x14003a032  lea     rax, [rsp+120h+var_B8]
0x14003a037  mov     rcx, [rsp+120h+var_C8]; void *
0x14003a03c  cmp     rcx, rax
0x14003a03f  jz      short loc_14003A04E
0x14003a041  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003a048  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003a04d  nop
0x14003a04e  mov     rcx, [rbp+20h+hKey]; hKey
0x14003a052  test    rcx, rcx
0x14003a055  jz      short loc_14003A05E
0x14003a057  call    cs:__imp_RegCloseKey
0x14003a05d  nop
0x14003a05e  mov     rcx, [rsp+120h+var_D0]; hKey
0x14003a063  test    rcx, rcx
0x14003a066  jz      short loc_14003A06F
0x14003a068  call    cs:__imp_RegCloseKey
0x14003a06e  nop
0x14003a06f  mov     rcx, [rsp+120h+var_E0]; hKey
0x14003a074  test    rcx, rcx
0x14003a077  jz      short loc_14003A080
0x14003a079  call    cs:__imp_RegCloseKey
0x14003a07f  nop
0x14003a080  mov     rcx, [rbp+20h+arg_8]; hKey
0x14003a084  test    rcx, rcx
0x14003a087  jz      short loc_14003A090
0x14003a089  call    cs:__imp_RegCloseKey
0x14003a08f  nop
0x14003a090  mov     rcx, [rsp+120h+var_D8]; hKey
0x14003a095  test    rcx, rcx
0x14003a098  jz      short loc_14003A0A0
0x14003a09a  call    cs:__imp_RegCloseKey
0x14003a0a0  mov     eax, ebx
0x14003a0a2  lea     r11, [rsp+120h+var_10]
0x14003a0aa  mov     rbx, [r11+20h]
0x14003a0ae  mov     rsi, [r11+30h]
0x14003a0b2  mov     rsp, r11
0x14003a0b5  pop     r14
0x14003a0b7  pop     rdi
0x14003a0b8  pop     rbp
0x14003a0b9  retn
```
