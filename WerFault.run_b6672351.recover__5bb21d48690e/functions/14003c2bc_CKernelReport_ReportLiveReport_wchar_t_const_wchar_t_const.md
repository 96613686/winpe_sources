# CKernelReport::ReportLiveReport(wchar_t const *,wchar_t const *)

- ea: `0x14003c2bc`
- end: `0x14003c779`
- name: `?ReportLiveReport@CKernelReport@@QEAAJPEB_W0@Z`
- size: `1213`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this, const wchar_t *, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x140036e5c`
- `0x140038760`
- `0x14003b784`

## callees

- `0x140002748`
- `0x14000551c`
- `0x1400372dc`
- `0x1400373a0`
- `0x140037610`
- `0x140037978`
- `0x140038c4c`
- `0x14003a67c`
- `0x14003c2bc`
- `0x14003c780`
- `0x1400420a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c6f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c70e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c725`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c73b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c752`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c6f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c70e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c725`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c73b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c752`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c407`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c45f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c4b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c50d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c569`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c407`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c45f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c4b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c50d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c569`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14003c683`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14003c683`

## string_xrefs

- `0x14003c42e`: `RegOpenKeyEx failed for root`
- `0x14003c486`: `RegOpenKeyEx failed for root`
- `0x14003c4dd`: `RegOpenKeyEx failed for report type`
- `0x14003c534`: `RegOpenKeyEx failed for report type`
- `0x14003c654`: `Failed live report. Path %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
        v8 = 2501;
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
          v8 = 2515;
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
            v8 = 2529;
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
              v8 = 2543;
            }
            else
            {
              v18 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v25);
              if ( !RegOpenKeyExW(v23, L"Busy", 0, 1u, v18) )
              {
                LODWORD(phkResult) = 0x80000000;
                wil::details::in1diag4::Log_HrMsg(
                  retaddr,
                  (void *)0x9FC,
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
                        (void *)0xA20,
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
                  v8 = 2584;
                }
                else
                {
                  v7 = "Sprintf Failed";
                  v8 = 2576;
                }
              }
              else
              {
                v7 = "Failed to get the live kernel report";
                v8 = 2569;
              }
            }
          }
        }
      }
    }
    else
    {
      v7 = "Failed to load livedump settings";
      v8 = 2488;
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
    (void *)0x9AD,
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
0x14003c2bc  mov     [rsp-8+arg_0], rbx
0x14003c2c1  mov     [rsp-8+arg_10], rsi
0x14003c2c6  push    rbp
0x14003c2c7  push    rdi
0x14003c2c8  push    r14
0x14003c2ca  lea     rbp, [rsp-10h]
0x14003c2cf  sub     rsp, 110h
0x14003c2d6  mov     rdi, r8
0x14003c2d9  mov     rsi, rdx
0x14003c2dc  mov     r14, rcx
0x14003c2df  mov     [rsp+120h+var_D8], 0
0x14003c2e8  mov     [rbp+20h+arg_8], 0
0x14003c2f0  mov     [rsp+120h+var_E0], 0
0x14003c2f9  mov     [rsp+120h+var_D0], 0
0x14003c302  mov     [rbp+20h+hKey], 0
0x14003c30a  lea     rax, [rsp+120h+var_B8]
0x14003c30f  mov     [rsp+120h+var_C8], rax
0x14003c314  lea     rax, [rsp+120h+var_B8]
0x14003c319  mov     [rsp+120h+var_C0], rax
0x14003c31e  xor     eax, eax
0x14003c320  mov     [rsp+120h+var_B8], ax
0x14003c325  lea     rax, [rbp+20h+var_88]
0x14003c329  mov     [rbp+20h+var_98], rax
0x14003c32d  lea     rax, [rbp+20h+var_88]
0x14003c331  mov     [rbp+20h+var_90], rax
0x14003c335  xor     eax, eax
0x14003c337  mov     [rbp+20h+var_88], ax
0x14003c33b  lea     rax, [rbp+20h+var_68]
0x14003c33f  mov     [rbp+20h+var_78], rax
0x14003c343  lea     rax, [rbp+20h+var_68]
0x14003c347  mov     [rbp+20h+var_70], rax
0x14003c34b  xor     eax, eax
0x14003c34d  mov     [rbp+20h+var_68], ax
0x14003c351  lea     rax, [rbp+20h+var_48]
0x14003c355  mov     [rbp+20h+var_58], rax
0x14003c359  lea     rax, [rbp+20h+var_48]
0x14003c35d  mov     [rbp+20h+var_50], rax
0x14003c361  xor     eax, eax
0x14003c363  mov     [rbp+20h+var_48], ax
0x14003c367  lea     rax, [rbp+20h+var_28]
0x14003c36b  mov     [rbp+20h+var_38], rax
0x14003c36f  lea     rax, [rbp+20h+var_28]
0x14003c373  mov     [rbp+20h+var_30], rax
0x14003c377  xor     eax, eax
0x14003c379  mov     [rbp+20h+var_28], ax
0x14003c37d  mov     [rbp+20h+var_A0], 1
0x14003c384  mov     [rbp+20h+var_9C], 1
0x14003c38b  test    rdx, rdx
0x14003c38e  jz      loc_14003C696
0x14003c394  test    r8, r8
0x14003c397  jz      loc_14003C696
0x14003c39d  xor     r8d, r8d; wchar_t *
0x14003c3a0  xor     edx, edx; wchar_t *
0x14003c3a2  lea     rcx, [rbp+20h+var_A0]; this
0x14003c3a6  call    ?LoadSettings@CLiveDumpSettings@@QEAAJPEB_W0@Z; CLiveDumpSettings::LoadSettings(wchar_t const *,wchar_t const *)
0x14003c3ab  mov     ebx, eax
0x14003c3ad  test    eax, eax
0x14003c3af  jns     short loc_14003C3E2
0x14003c3b1  lea     rax, aFailedToLoadLi; "Failed to load livedump settings"
0x14003c3b8  mov     edx, 9B8h; void *
0x14003c3bd  mov     qword ptr [rsp+120h+var_F8], rax; int
0x14003c3c2  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c3c9  lea     r9, aCkernelreportR_0; "CKernelReport::ReportLiveReport"
0x14003c3d0  mov     dword ptr [rsp+120h+phkResult], ebx; wil::details *
0x14003c3d4  mov     rcx, [rbp+28h]; this
0x14003c3d8  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c3dd  jmp     loc_14003C68F
0x14003c3e2  lea     rcx, [rbp+20h+hKey]
0x14003c3e6  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003c3eb  mov     [rsp+120h+phkResult], rax; phkResult
0x14003c3f0  mov     r9d, 0F003Fh; samDesired
0x14003c3f6  xor     r8d, r8d; ulOptions
0x14003c3f9  lea     rdx, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x14003c400  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003c407  call    cs:__imp_RegOpenKeyExW
0x14003c40e  nop     dword ptr [rax+rax+00h]
0x14003c413  mov     ebx, eax
0x14003c415  test    eax, eax
0x14003c417  jz      short loc_14003C43C
0x14003c419  jle     short loc_14003C424
0x14003c41b  movzx   ebx, ax
0x14003c41e  or      ebx, 80070000h
0x14003c424  mov     eax, 80004005h
0x14003c429  test    ebx, ebx
0x14003c42b  cmovns  ebx, eax
0x14003c42e  lea     rax, aRegopenkeyexFa; "RegOpenKeyEx failed for root"
0x14003c435  mov     edx, 9C5h
0x14003c43a  jmp     short loc_14003C3BD
0x14003c43c  lea     rcx, [rsp+120h+var_D8]
0x14003c441  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003c446  mov     [rsp+120h+phkResult], rax; phkResult
0x14003c44b  mov     r9d, 0F003Fh; samDesired
0x14003c451  xor     r8d, r8d; ulOptions
0x14003c454  lea     rdx, aLivekernelrepo_0; "LiveKernelReports"
0x14003c45b  mov     rcx, [rbp+20h+hKey]; hKey
0x14003c45f  call    cs:__imp_RegOpenKeyExW
0x14003c466  nop     dword ptr [rax+rax+00h]
0x14003c46b  mov     ebx, eax
0x14003c46d  test    eax, eax
0x14003c46f  jz      short loc_14003C497
0x14003c471  jle     short loc_14003C47C
0x14003c473  movzx   ebx, ax
0x14003c476  or      ebx, 80070000h
0x14003c47c  mov     eax, 80004005h
0x14003c481  test    ebx, ebx
0x14003c483  cmovns  ebx, eax
0x14003c486  lea     rax, aRegopenkeyexFa; "RegOpenKeyEx failed for root"
0x14003c48d  mov     edx, 9D3h
0x14003c492  jmp     loc_14003C3BD
0x14003c497  lea     rcx, [rbp+20h+arg_8]
0x14003c49b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003c4a0  mov     [rsp+120h+phkResult], rax; phkResult
0x14003c4a5  mov     r9d, 10008h; samDesired
0x14003c4ab  xor     r8d, r8d; ulOptions
0x14003c4ae  mov     rdx, rsi; lpSubKey
0x14003c4b1  mov     rcx, [rsp+120h+var_D8]; hKey
0x14003c4b6  call    cs:__imp_RegOpenKeyExW
0x14003c4bd  nop     dword ptr [rax+rax+00h]
0x14003c4c2  mov     ebx, eax
0x14003c4c4  test    eax, eax
0x14003c4c6  jz      short loc_14003C4EE
0x14003c4c8  jle     short loc_14003C4D3
0x14003c4ca  movzx   ebx, ax
0x14003c4cd  or      ebx, 80070000h
0x14003c4d3  mov     eax, 80004005h
0x14003c4d8  test    ebx, ebx
0x14003c4da  cmovns  ebx, eax
0x14003c4dd  lea     rax, aRegopenkeyexFa_1; "RegOpenKeyEx failed for report type"
0x14003c4e4  mov     edx, 9E1h
0x14003c4e9  jmp     loc_14003C3BD
0x14003c4ee  lea     rcx, [rsp+120h+var_E0]
0x14003c4f3  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003c4f8  mov     [rsp+120h+phkResult], rax; phkResult
0x14003c4fd  mov     r9d, 9; samDesired
0x14003c503  xor     r8d, r8d; ulOptions
0x14003c506  mov     rdx, rdi; lpSubKey
0x14003c509  mov     rcx, [rbp+20h+arg_8]; hKey
0x14003c50d  call    cs:__imp_RegOpenKeyExW
0x14003c514  nop     dword ptr [rax+rax+00h]
0x14003c519  mov     ebx, eax
0x14003c51b  test    eax, eax
0x14003c51d  jz      short loc_14003C545
0x14003c51f  jle     short loc_14003C52A
0x14003c521  movzx   ebx, ax
0x14003c524  or      ebx, 80070000h
0x14003c52a  mov     eax, 80004005h
0x14003c52f  test    ebx, ebx
0x14003c531  cmovns  ebx, eax
0x14003c534  lea     rax, aRegopenkeyexFa_1; "RegOpenKeyEx failed for report type"
0x14003c53b  mov     edx, 9EFh
0x14003c540  jmp     loc_14003C3BD
0x14003c545  lea     rcx, [rsp+120h+var_D0]
0x14003c54a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003c54f  mov     [rsp+120h+phkResult], rax; phkResult
0x14003c554  mov     r9d, 1; samDesired
0x14003c55a  xor     r8d, r8d; ulOptions
0x14003c55d  lea     rdx, aBusy; "Busy"
0x14003c564  mov     rcx, [rsp+120h+var_E0]; hKey
0x14003c569  call    cs:__imp_RegOpenKeyExW
0x14003c570  nop     dword ptr [rax+rax+00h]
0x14003c575  test    eax, eax
0x14003c577  jnz     short loc_14003C5BD
0x14003c579  mov     rcx, [rbp+28h]; this
0x14003c57d  mov     [rsp+120h+var_E8], rdi
0x14003c582  mov     [rsp+120h+var_F0], rsi; char *
0x14003c587  lea     rax, aReportIsBusyFo; "Report is busy for %ws - %ws"
0x14003c58e  mov     qword ptr [rsp+120h+var_F8], rax; int
0x14003c593  mov     dword ptr [rsp+120h+phkResult], 80000000h; wil::details *
0x14003c59b  lea     r9, aCkernelreportR_0; "CKernelReport::ReportLiveReport"
0x14003c5a2  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c5a9  mov     edx, 9FCh; void *
0x14003c5ae  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c5b3  mov     ebx, 8007139Fh
0x14003c5b8  jmp     loc_14003C68F
0x14003c5bd  lea     rdx, [rsp+120h+var_C8]
0x14003c5c2  call    ?GetLiveReportsStoreRoot@CKernelReport@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CKernelReport::GetLiveReportsStoreRoot(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14003c5c7  mov     ebx, eax
0x14003c5c9  test    eax, eax
0x14003c5cb  jns     short loc_14003C5DE
0x14003c5cd  lea     rax, aFailedToGetThe; "Failed to get the live kernel report"
0x14003c5d4  mov     edx, 0A09h
0x14003c5d9  jmp     loc_14003C3BD
0x14003c5de  mov     r9, rdi
0x14003c5e1  mov     r8, rsi
0x14003c5e4  lea     rdx, aSS_3; "%s\\%s"
0x14003c5eb  lea     rcx, [rsp+120h+var_C8]
0x14003c5f0  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14003c5f5  mov     ebx, eax
0x14003c5f7  test    eax, eax
0x14003c5f9  jns     short loc_14003C60C
0x14003c5fb  lea     rax, aSprintfFailed_0; "Sprintf Failed"
0x14003c602  mov     edx, 0A10h
0x14003c607  jmp     loc_14003C3BD
0x14003c60c  mov     rdx, [rsp+120h+var_C8]; wchar_t *
0x14003c611  mov     rcx, r14; this
0x14003c614  call    ?ExtractBootId@CKernelReport@@AEAAJPEB_W@Z; CKernelReport::ExtractBootId(wchar_t const *)
0x14003c619  mov     ebx, eax
0x14003c61b  test    eax, eax
0x14003c61d  jns     short loc_14003C630
0x14003c61f  lea     rax, aExtractbootidF; "ExtractBootId failed"
0x14003c626  mov     edx, 0A18h
0x14003c62b  jmp     loc_14003C3BD
0x14003c630  mov     r8, rdi; wchar_t *
0x14003c633  mov     rdx, [rsp+120h+var_C8]; wchar_t *
0x14003c638  mov     rcx, r14; this
0x14003c63b  call    ?SendLiveReport@CKernelReport@@AEAAJPEB_W0@Z; CKernelReport::SendLiveReport(wchar_t const *,wchar_t const *)
0x14003c640  mov     ebx, eax
0x14003c642  test    eax, eax
0x14003c644  jns     short loc_14003C67C
0x14003c646  mov     rcx, [rbp+28h]; this
0x14003c64a  mov     rax, [rsp+120h+var_C8]
0x14003c64f  mov     [rsp+120h+var_F0], rax; char *
0x14003c654  lea     rax, aFailedLiveRepo; "Failed live report. Path %ws"
0x14003c65b  mov     qword ptr [rsp+120h+var_F8], rax; int
0x14003c660  mov     dword ptr [rsp+120h+phkResult], ebx; wil::details *
0x14003c664  lea     r9, aCkernelreportR_0; "CKernelReport::ReportLiveReport"
0x14003c66b  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c672  mov     edx, 0A20h; void *
0x14003c677  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c67c  mov     rdx, rdi; lpSubKey
0x14003c67f  mov     rcx, [rbp+20h+arg_8]; hKey
0x14003c683  call    cs:__imp_RegDeleteKeyW
0x14003c68a  nop     dword ptr [rax+rax+00h]
0x14003c68f  call    ?CheckAndDeleteLiveMemoryDump@CKernelReport@@AEAAXXZ; CKernelReport::CheckAndDeleteLiveMemoryDump(void)
0x14003c694  jmp     short loc_14003C6C8
0x14003c696  mov     rcx, [rbp+28h]; this
0x14003c69a  lea     rax, aInvalidParams; "Invalid params"
0x14003c6a1  mov     qword ptr [rsp+120h+var_F8], rax; int
0x14003c6a6  mov     ebx, 80070057h
0x14003c6ab  mov     dword ptr [rsp+120h+phkResult], ebx; wil::details *
0x14003c6af  lea     r9, aCkernelreportR_0; "CKernelReport::ReportLiveReport"
0x14003c6b6  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c6bd  mov     edx, 9ADh; void *
0x14003c6c2  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c6c7  nop
0x14003c6c8  lea     rcx, [rbp+20h+var_A0]; this
0x14003c6cc  call    ??1CLiveDumpSettings@@QEAA@XZ; CLiveDumpSettings::~CLiveDumpSettings(void)
0x14003c6d1  nop
0x14003c6d2  lea     rax, [rsp+120h+var_B8]
0x14003c6d7  mov     rcx, [rsp+120h+var_C8]; void *
0x14003c6dc  cmp     rcx, rax
0x14003c6df  jz      short loc_14003C6EE
0x14003c6e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003c6e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c6ed  nop
0x14003c6ee  mov     rcx, [rbp+20h+hKey]; hKey
0x14003c6f2  test    rcx, rcx
0x14003c6f5  jz      short loc_14003C704
0x14003c6f7  call    cs:__imp_RegCloseKey
0x14003c6fe  nop     dword ptr [rax+rax+00h]
0x14003c703  nop
0x14003c704  mov     rcx, [rsp+120h+var_D0]; hKey
0x14003c709  test    rcx, rcx
0x14003c70c  jz      short loc_14003C71B
0x14003c70e  call    cs:__imp_RegCloseKey
0x14003c715  nop     dword ptr [rax+rax+00h]
0x14003c71a  nop
0x14003c71b  mov     rcx, [rsp+120h+var_E0]; hKey
0x14003c720  test    rcx, rcx
0x14003c723  jz      short loc_14003C732
0x14003c725  call    cs:__imp_RegCloseKey
0x14003c72c  nop     dword ptr [rax+rax+00h]
0x14003c731  nop
0x14003c732  mov     rcx, [rbp+20h+arg_8]; hKey
0x14003c736  test    rcx, rcx
0x14003c739  jz      short loc_14003C748
0x14003c73b  call    cs:__imp_RegCloseKey
0x14003c742  nop     dword ptr [rax+rax+00h]
0x14003c747  nop
0x14003c748  mov     rcx, [rsp+120h+var_D8]; hKey
0x14003c74d  test    rcx, rcx
0x14003c750  jz      short loc_14003C75E
0x14003c752  call    cs:__imp_RegCloseKey
0x14003c759  nop     dword ptr [rax+rax+00h]
0x14003c75e  mov     eax, ebx
0x14003c760  lea     r11, [rsp+120h+var_10]
0x14003c768  mov     rbx, [r11+20h]
0x14003c76c  mov     rsi, [r11+30h]
0x14003c770  mov     rsp, r11
0x14003c773  pop     r14
0x14003c775  pop     rdi
0x14003c776  pop     rbp
0x14003c777  retn
```
