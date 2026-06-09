# CScenarioCtrlUpgradeMobile::GetPostRebootResult(_MoUpdatePostRebootResultData *,long *)

- ea: `0x180064930`
- end: `0x180064d81`
- name: `?GetPostRebootResult@CScenarioCtrlUpgradeMobile@@UEAAJPEAU_MoUpdatePostRebootResultData@@PEAJ@Z`
- size: `1105`
- prototype: `__int64 __fastcall(CScenarioCtrlUpgradeMobile *__hidden this, struct _MoUpdatePostRebootResultData *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800059d0`
- `0x180064930`
- `0x180066f44`
- `0x180077664`
- `0x180078b9c`
- `0x18008b360`
- `0x18008b38c`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180064a3e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180064abb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180064a3e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180064abb`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180064aed`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180064c2c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180064caa`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180064aed`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180064c2c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180064caa`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180064a17`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180064a17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800649db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064aff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064c3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064cbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064d08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800649db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064aff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064c3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064cbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064d08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800649f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064b14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064c53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064cd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064d1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800649f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064b14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064c53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064cd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064d1d`

## string_xrefs

- `0x1800649bf`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlUpgradeMobileImpl.h`
- `0x180064ad7`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlUpgradeMobileImpl.h`
- `0x180064c95`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlUpgradeMobileImpl.h`
- `0x180064cf0`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlUpgradeMobileImpl.h`
- `0x180064d44`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlUpgradeMobileImpl.h`
- `0x180064a34`: `GetUpdateResultsEx`
- `0x180064a5b`: `Calling IU GetUpdateResultsEx.`
- `0x180064aa0`: `GetUpdateResultEx FAILED: [0x%X]. Will try using GetUpdateResults().`
- `0x180064ab1`: `GetUpdateResults`
- `0x180064b37`: `Calling IU GetUpdateResult.`
- `0x180064bba`: `GetUpdateResult state: [%d], UpdateResult: [0x%X], RollbackReason: [%d].`
- `0x180064c79`: `GetUpdateResult FAILED: [0x%X].`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CScenarioCtrlUpgradeMobile::GetPostRebootResult(
        CScenarioCtrlUpgradeMobile *this,
        struct _MoUpdatePostRebootResultData *a2,
        int *a3)
{
  int UpdateAPIPath; // eax
  unsigned int v7; // esi
  const char *v8; // r9
  LPCWSTR v9; // rbx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  LPCWSTR v12; // rbx
  HMODULE Library; // rax
  const char *v14; // r9
  HMODULE v15; // r15
  FARPROC ProcAddress; // rsi
  __int64 v17; // rcx
  int v18; // eax
  int v19; // r9d
  int v20; // eax
  __int64 v21; // rcx
  FARPROC v22; // rsi
  const char *v23; // r9
  unsigned int LastError; // edi
  HANDLE v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // esi
  int v28; // ecx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  HANDLE v32; // rax
  __int64 v33; // rcx
  HANDLE v34; // rax
  unsigned int v35; // edi
  HANDLE v36; // rax
  int v37; // [rsp+20h] [rbp-78h]
  LPCWSTR lpLibFileName[3]; // [rsp+30h] [rbp-68h] BYREF
  int v39; // [rsp+48h] [rbp-50h] BYREF
  int v40; // [rsp+4Ch] [rbp-4Ch] BYREF
  __int64 v41; // [rsp+50h] [rbp-48h] BYREF
  __int64 v42; // [rsp+58h] [rbp-40h]
  __int64 v43; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  lpLibFileName[1] = (LPCWSTR)-2LL;
  try
  {
    v39 = 0;
    lpLibFileName[0] = 0;
    v40 = 0;
    v41 = 24;
    v42 = 0;
    v43 = 0;
    if ( !a3 || !a2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17C,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlUpgradeMobileImpl.h",
        (const char *)0x80004003LL,
        v37);
      return 2147500035LL;
    }
    UpdateAPIPath = CMoUpdateHelpersT<CEmptyType>::GetUpdateAPIPath((__int64)this, lpLibFileName);
    v7 = UpdateAPIPath;
    if ( UpdateAPIPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17E,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlUpgradeMobileImpl.h",
        (const char *)(unsigned int)UpdateAPIPath,
        v37);
      v9 = lpLibFileName[0];
      if ( lpLibFileName[0] )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v9 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      return v7;
    }
    v12 = lpLibFileName[0];
    Library = LoadLibraryExW(lpLibFileName[0], 0, 0);
    v15 = Library;
    if ( Library )
    {
      lpLibFileName[2] = (LPCWSTR)Library;
      ProcAddress = GetProcAddress(Library, "GetUpdateResultsEx");
      if ( ProcAddress )
      {
        v17 = *((_QWORD *)this + 4);
        if ( v17 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v17, 2, L"Calling IU GetUpdateResultsEx.");
        v18 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v41);
        if ( v18 >= 0 )
        {
          v19 = v42;
          v40 = v42;
          v20 = HIDWORD(v42);
          v39 = HIDWORD(v42);
LABEL_24:
          v28 = 0;
          switch ( v19 )
          {
            case 2:
            case 7:
              v20 = -805306323;
              break;
            case 5:
              v20 = -2147019873;
              break;
            case 6:
              v20 = -1047526386;
              v28 = HIDWORD(v43);
              break;
            default:
LABEL_32:
              *(_DWORD *)a2 = v19;
              *((_DWORD *)a2 + 1) = v28;
              if ( *((_QWORD *)this + 4) )
              {
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  *((_QWORD *)this + 4),
                  2,
                  L"GetUpdateResult state: [%d], UpdateResult: [0x%X], RollbackReason: [%d].");
                v20 = v39;
              }
              if ( v20 >= 0 )
              {
                v29 = *((_QWORD *)this + 4);
                if ( v29 )
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v29, 2, L"Executing Post Reboot Actions...");
                v30 = (*(__int64 (__fastcall **)(CScenarioCtrlUpgradeMobile *))(*(_QWORD *)this + 120LL))(this);
                if ( v30 < 0 )
                {
                  v31 = *((_QWORD *)this + 4);
                  if ( v31 )
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v31,
                      3,
                      L"Ignoring ExecPostRebootActions() failure: [0x%X].",
                      (unsigned int)v30);
                }
                v20 = v39;
              }
              *a3 = v20;
              FreeLibrary(v15);
              if ( v12 )
              {
                v32 = GetProcessHeap();
                HeapFree(v32, 0, (LPVOID)(v12 - 2));
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              }
              return 0;
          }
          v39 = v20;
          goto LABEL_32;
        }
        v21 = *((_QWORD *)this + 4);
        if ( v21 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v21,
            4,
            L"GetUpdateResultEx FAILED: [0x%X]. Will try using GetUpdateResults().",
            (unsigned int)v18);
      }
      v22 = GetProcAddress(v15, "GetUpdateResults");
      if ( v22 )
      {
        v26 = *((_QWORD *)this + 4);
        if ( v26 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v26, 2, L"Calling IU GetUpdateResult.");
        v27 = ((__int64 (__fastcall *)(int *, int *))v22)(&v40, &v39);
        if ( (v27 & 0x80000000) == 0 )
        {
          v20 = v39;
          v19 = v40;
          goto LABEL_24;
        }
        v33 = *((_QWORD *)this + 4);
        if ( v33 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v33, 2, L"GetUpdateResult FAILED: [0x%X].", v27);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BA,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlUpgradeMobileImpl.h",
          (const char *)v27,
          v37);
        FreeLibrary(v15);
        if ( v12 )
        {
          v34 = GetProcessHeap();
          HeapFree(v34, 0, (LPVOID)(v12 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        result = v27;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x197,
                      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlUpgradeMobileImpl.h",
                      v23);
        FreeLibrary(v15);
        if ( v12 )
        {
          v25 = GetProcessHeap();
          HeapFree(v25, 0, (LPVOID)(v12 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        result = LastError;
      }
    }
    else
    {
      v35 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x180,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlUpgradeMobileImpl.h",
              v14);
      if ( v12 )
      {
        v36 = GetProcessHeap();
        HeapFree(v36, 0, (LPVOID)(v12 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      result = v35;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1CE,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlUpgradeMobileImpl.h",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180064930  mov     r11, rsp
0x180064933  push    rsi
0x180064934  push    rdi
0x180064935  push    r12
0x180064937  push    r13
0x180064939  push    r15
0x18006493b  sub     rsp, 70h
0x18006493f  mov     qword ptr [r11-60h], 0FFFFFFFFFFFFFFFEh
0x180064947  mov     [r11+20h], rbx
0x18006494b  mov     rax, cs:__security_cookie
0x180064952  xor     rax, rsp
0x180064955  mov     [rsp+98h+var_30], rax
0x18006495a  mov     r13, r8
0x18006495d  mov     r12, rdx
0x180064960  mov     rdi, rcx
0x180064963  mov     [rsp+98h+var_50], 0
0x18006496b  mov     qword ptr [r11-68h], 0
0x180064973  mov     [rsp+98h+var_4C], 0
0x18006497b  mov     qword ptr [r11-48h], 18h
0x180064983  mov     qword ptr [r11-40h], 0
0x18006498b  mov     qword ptr [r11-38h], 0
0x180064993  test    r8, r8
0x180064996  jz      loc_180064D34
0x18006499c  test    rdx, rdx
0x18006499f  jz      loc_180064D34
0x1800649a5  lea     rdx, [r11-68h]
0x1800649a9  call    ?GetUpdateAPIPath@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEB_WPEAPEA_W@Z; CMoUpdateHelpersT<CEmptyType>::GetUpdateAPIPath(wchar_t const *,wchar_t * *)
0x1800649ae  mov     esi, eax
0x1800649b0  test    eax, eax
0x1800649b2  jns     short loc_180064A0A
0x1800649b4  mov     rcx, [rsp+98h]; this
0x1800649bc  mov     r9d, eax; char *
0x1800649bf  lea     r8, aOnecoreBaseNts_33; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x1800649c6  mov     edx, 17Eh; void *
0x1800649cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800649d0  nop
0x1800649d1  mov     rbx, [rsp+98h+lpLibFileName]
0x1800649d6  test    rbx, rbx
0x1800649d9  jz      short loc_180064A03
0x1800649db  call    cs:__imp_GetProcessHeap
0x1800649e2  nop     dword ptr [rax+rax+00h]
0x1800649e7  mov     rcx, rax; hHeap
0x1800649ea  lea     r8, [rbx-4]; lpMem
0x1800649ee  xor     edx, edx; dwFlags
0x1800649f0  call    cs:__imp_HeapFree
0x1800649f7  nop     dword ptr [rax+rax+00h]
0x1800649fc  xor     ecx, ecx
0x1800649fe  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064a03  mov     eax, esi
0x180064a05  jmp     loc_180064D5E
0x180064a0a  mov     rbx, [rsp+98h+lpLibFileName]
0x180064a0f  xor     r8d, r8d; dwFlags
0x180064a12  xor     edx, edx; hFile
0x180064a14  mov     rcx, rbx; lpLibFileName
0x180064a17  call    cs:__imp_LoadLibraryExW
0x180064a1e  nop     dword ptr [rax+rax+00h]
0x180064a23  mov     r15, rax
0x180064a26  test    rax, rax
0x180064a29  jz      loc_180064CE8
0x180064a2f  mov     [rsp+98h+var_58], rax
0x180064a34  lea     rdx, aGetupdateresul_3; "GetUpdateResultsEx"
0x180064a3b  mov     rcx, rax; hModule
0x180064a3e  call    cs:__imp_GetProcAddress
0x180064a45  nop     dword ptr [rax+rax+00h]
0x180064a4a  mov     rsi, rax
0x180064a4d  test    rax, rax
0x180064a50  jz      short loc_180064AB1
0x180064a52  mov     rcx, [rdi+20h]
0x180064a56  test    rcx, rcx
0x180064a59  jz      short loc_180064A6C
0x180064a5b  lea     r8, aCallingIuGetup_0; "Calling IU GetUpdateResultsEx."
0x180064a62  mov     edx, 2
0x180064a67  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180064a6c  lea     rcx, [rsp+98h+var_48]
0x180064a71  mov     rax, rsi
0x180064a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a79  test    eax, eax
0x180064a7b  js      short loc_180064A94
0x180064a7d  mov     r9d, [rsp+98h+var_40]
0x180064a82  mov     [rsp+98h+var_4C], r9d
0x180064a87  mov     eax, [rsp+98h+var_3C]
0x180064a8b  mov     [rsp+98h+var_50], eax
0x180064a8f  jmp     loc_180064B6D
0x180064a94  mov     rcx, [rdi+20h]
0x180064a98  test    rcx, rcx
0x180064a9b  jz      short loc_180064AB1
0x180064a9d  mov     r9d, eax
0x180064aa0  lea     r8, aGetupdateresul; "GetUpdateResultEx FAILED: [0x%X]. Will "...
0x180064aa7  mov     edx, 4
0x180064aac  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180064ab1  lea     rdx, aGetupdateresul_0; "GetUpdateResults"
0x180064ab8  mov     rcx, r15; hModule
0x180064abb  call    cs:__imp_GetProcAddress
0x180064ac2  nop     dword ptr [rax+rax+00h]
0x180064ac7  mov     rsi, rax
0x180064aca  test    rax, rax
0x180064acd  jnz     short loc_180064B2E
0x180064acf  mov     rcx, [rsp+98h]; this
0x180064ad7  lea     r8, aOnecoreBaseNts_33; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x180064ade  mov     edx, 197h; void *
0x180064ae3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180064ae8  mov     edi, eax
0x180064aea  mov     rcx, r15; hLibModule
0x180064aed  call    cs:__imp_FreeLibrary
0x180064af4  nop     dword ptr [rax+rax+00h]
0x180064af9  nop
0x180064afa  test    rbx, rbx
0x180064afd  jz      short loc_180064B27
0x180064aff  call    cs:__imp_GetProcessHeap
0x180064b06  nop     dword ptr [rax+rax+00h]
0x180064b0b  mov     rcx, rax; hHeap
0x180064b0e  lea     r8, [rbx-4]; lpMem
0x180064b12  xor     edx, edx; dwFlags
0x180064b14  call    cs:__imp_HeapFree
0x180064b1b  nop     dword ptr [rax+rax+00h]
0x180064b20  xor     ecx, ecx
0x180064b22  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064b27  mov     eax, edi
0x180064b29  jmp     loc_180064D5E
0x180064b2e  mov     rcx, [rdi+20h]
0x180064b32  test    rcx, rcx
0x180064b35  jz      short loc_180064B48
0x180064b37  lea     r8, aCallingIuGetup; "Calling IU GetUpdateResult."
0x180064b3e  mov     edx, 2
0x180064b43  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180064b48  lea     rdx, [rsp+98h+var_50]
0x180064b4d  lea     rcx, [rsp+98h+var_4C]
0x180064b52  mov     rax, rsi
0x180064b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b5a  mov     esi, eax
0x180064b5c  test    eax, eax
0x180064b5e  js      loc_180064C6D
0x180064b64  mov     eax, [rsp+98h+var_50]
0x180064b68  mov     r9d, [rsp+98h+var_4C]
0x180064b6d  xor     ecx, ecx
0x180064b6f  cmp     r9d, 2
0x180064b73  jz      short loc_180064B99
0x180064b75  cmp     r9d, 7
0x180064b79  jz      short loc_180064B99
0x180064b7b  cmp     r9d, 5
0x180064b7f  jnz     short loc_180064B88
0x180064b81  mov     eax, 8007139Fh
0x180064b86  jmp     short loc_180064B9E
0x180064b88  cmp     r9d, 6
0x180064b8c  jnz     short loc_180064BA2
0x180064b8e  mov     eax, 0C190040Eh
0x180064b93  mov     ecx, [rsp+98h+var_34]
0x180064b97  jmp     short loc_180064B9E
0x180064b99  mov     eax, 0D000002Dh
0x180064b9e  mov     [rsp+98h+var_50], eax
0x180064ba2  mov     [r12], r9d
0x180064ba6  mov     [r12+4], ecx
0x180064bab  cmp     qword ptr [rdi+20h], 0
0x180064bb0  jz      short loc_180064BD3
0x180064bb2  mov     [rsp+98h+var_70], ecx
0x180064bb6  mov     [rsp+98h+var_78], eax
0x180064bba  lea     r8, aGetupdateresul_2; "GetUpdateResult state: [%d], UpdateResu"...
0x180064bc1  mov     edx, 2
0x180064bc6  mov     rcx, [rdi+20h]
0x180064bca  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180064bcf  mov     eax, [rsp+98h+var_50]
0x180064bd3  test    eax, eax
0x180064bd5  js      short loc_180064C25
0x180064bd7  mov     rcx, [rdi+20h]
0x180064bdb  test    rcx, rcx
0x180064bde  jz      short loc_180064BF1
0x180064be0  lea     r8, aExecutingPostR; "Executing Post Reboot Actions..."
0x180064be7  mov     edx, 2
0x180064bec  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180064bf1  mov     rax, [rdi]
0x180064bf4  mov     rcx, rdi
0x180064bf7  mov     rax, [rax+78h]
0x180064bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c00  test    eax, eax
0x180064c02  jns     short loc_180064C21
0x180064c04  mov     rcx, [rdi+20h]
0x180064c08  test    rcx, rcx
0x180064c0b  jz      short loc_180064C21
0x180064c0d  mov     r9d, eax
0x180064c10  lea     r8, aIgnoringExecpo; "Ignoring ExecPostRebootActions() failur"...
0x180064c17  mov     edx, 3
0x180064c1c  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180064c21  mov     eax, [rsp+98h+var_50]
0x180064c25  mov     [r13+0], eax
0x180064c29  mov     rcx, r15; hLibModule
0x180064c2c  call    cs:__imp_FreeLibrary
0x180064c33  nop     dword ptr [rax+rax+00h]
0x180064c38  nop
0x180064c39  test    rbx, rbx
0x180064c3c  jz      short loc_180064C66
0x180064c3e  call    cs:__imp_GetProcessHeap
0x180064c45  nop     dword ptr [rax+rax+00h]
0x180064c4a  mov     rcx, rax; hHeap
0x180064c4d  lea     r8, [rbx-4]; lpMem
0x180064c51  xor     edx, edx; dwFlags
0x180064c53  call    cs:__imp_HeapFree
0x180064c5a  nop     dword ptr [rax+rax+00h]
0x180064c5f  xor     ecx, ecx
0x180064c61  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064c66  xor     eax, eax
0x180064c68  jmp     loc_180064D5E
0x180064c6d  mov     rcx, [rdi+20h]
0x180064c71  test    rcx, rcx
0x180064c74  jz      short loc_180064C8A
0x180064c76  mov     r9d, esi
0x180064c79  lea     r8, aGetupdateresul_1; "GetUpdateResult FAILED: [0x%X]."
0x180064c80  mov     edx, 2
0x180064c85  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180064c8a  mov     rcx, [rsp+98h]; this
0x180064c92  mov     r9d, esi; char *
0x180064c95  lea     r8, aOnecoreBaseNts_33; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x180064c9c  mov     edx, 1BAh; void *
0x180064ca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064ca6  nop
0x180064ca7  mov     rcx, r15; hLibModule
0x180064caa  call    cs:__imp_FreeLibrary
0x180064cb1  nop     dword ptr [rax+rax+00h]
0x180064cb6  nop
0x180064cb7  test    rbx, rbx
0x180064cba  jz      short loc_180064CE4
0x180064cbc  call    cs:__imp_GetProcessHeap
0x180064cc3  nop     dword ptr [rax+rax+00h]
0x180064cc8  mov     rcx, rax; hHeap
0x180064ccb  lea     r8, [rbx-4]; lpMem
0x180064ccf  xor     edx, edx; dwFlags
0x180064cd1  call    cs:__imp_HeapFree
0x180064cd8  nop     dword ptr [rax+rax+00h]
0x180064cdd  xor     ecx, ecx
0x180064cdf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064ce4  mov     eax, esi
0x180064ce6  jmp     short loc_180064D5E
0x180064ce8  mov     rcx, [rsp+98h]; this
0x180064cf0  lea     r8, aOnecoreBaseNts_33; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x180064cf7  mov     edx, 180h; void *
0x180064cfc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180064d01  mov     edi, eax
0x180064d03  test    rbx, rbx
0x180064d06  jz      short loc_180064D30
0x180064d08  call    cs:__imp_GetProcessHeap
0x180064d0f  nop     dword ptr [rax+rax+00h]
0x180064d14  mov     rcx, rax; hHeap
0x180064d17  lea     r8, [rbx-4]; lpMem
0x180064d1b  xor     edx, edx; dwFlags
0x180064d1d  call    cs:__imp_HeapFree
0x180064d24  nop     dword ptr [rax+rax+00h]
0x180064d29  xor     ecx, ecx
0x180064d2b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064d30  mov     eax, edi
0x180064d32  jmp     short loc_180064D5E
0x180064d34  mov     rcx, [rsp+98h]; this
0x180064d3c  mov     ebx, 80004003h
0x180064d41  mov     r9d, ebx; char *
0x180064d44  lea     r8, aOnecoreBaseNts_33; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x180064d4b  mov     edx, 17Ch; void *
0x180064d50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064d55  nop
0x180064d56  mov     eax, ebx
0x180064d58  jmp     short loc_180064D5E
0x180064d5a  mov     eax, [rsp+98h+var_4C]
0x180064d5e  mov     rcx, [rsp+98h+var_30]
0x180064d63  xor     rcx, rsp; StackCookie
0x180064d66  call    __security_check_cookie
0x180064d6b  mov     rbx, [rsp+98h+arg_18]
0x180064d73  add     rsp, 70h
0x180064d77  pop     r15
0x180064d79  pop     r13
0x180064d7b  pop     r12
0x180064d7d  pop     rdi
0x180064d7e  pop     rsi
0x180064d7f  retn
```
