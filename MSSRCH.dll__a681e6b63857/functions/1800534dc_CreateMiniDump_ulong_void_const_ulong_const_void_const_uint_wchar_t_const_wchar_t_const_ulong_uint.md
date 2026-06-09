# CreateMiniDump(ulong,void * * const,ulong * const,void * * const,uint,wchar_t const *,wchar_t const *,ulong *,uint)

- ea: `0x1800534dc`
- end: `0x180053bb2`
- name: `?CreateMiniDump@@YAJKQEAPEAXQEAK0IPEB_W2PEAKI@Z`
- size: `1750`
- prototype: `__int64 __fastcall(unsigned int, void **const, unsigned int *const, void **const, unsigned int, const wchar_t *, PCWSTR, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18005cf90`
- `0x1800c8250`

## callees

- `0x18000c4cc`
- `0x18005268c`
- `0x1800534dc`
- `0x180054cb8`
- `0x1800555f0`
- `0x1800569e0`
- `0x180082390`
- `0x180104754`
- `0x1801244c0`
- `0x18012540e`
- `0x180129e5c`
- `0x1801485ec`
- `0x18020abf0`
- `0x18020ae4c`
- `0x180222f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005365a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005380c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800539df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005365a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005380c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800539df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053574`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053b66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053574`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053b66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005395a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005395a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053b42`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800535c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800535c9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005391b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053afc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005391b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053afc`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800536a1`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18005382c`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180053a01`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800536a1`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18005382c`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180053a01`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x18005376d`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800537c6`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800537e5`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x18005376d`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800537c6`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800537e5`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddFile` at `0x180053976`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddFile` at `0x180053976`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x1800539b2`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x1800539b2`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x18005399c`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x18005399c`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x180053750`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x180053750`
- `api-ms-win-core-debug-minidump-l1-1-0!MiniDumpWriteDump` at `0x18005394d`
- `api-ms-win-core-debug-minidump-l1-1-0!MiniDumpWriteDump` at `0x180053b33`
- `api-ms-win-core-debug-minidump-l1-1-0!MiniDumpWriteDump` at `0x18005394d`
- `api-ms-win-core-debug-minidump-l1-1-0!MiniDumpWriteDump` at `0x180053b33`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x18005387d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x180053a52`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x18005387d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x180053a52`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800538ea`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x180053acb`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800538ea`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x180053acb`

## string_xrefs

- `0x1800536e8`: `MSSrch.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CreateMiniDump(
        unsigned int a1,
        void **const a2,
        unsigned int *const a3,
        void **const a4,
        unsigned int a5,
        const wchar_t *a6,
        PCWSTR a7,
        unsigned int *a8)
{
  HRESULT v10; // ebx
  DWORD v11; // ecx
  LSTATUS v12; // eax
  unsigned int v13; // ecx
  __int64 v14; // rcx
  unsigned int v15; // r8d
  __int64 v16; // rsi
  unsigned int *v17; // r15
  __int64 v18; // rcx
  HANDLE v19; // rbx
  __int64 i; // r14
  __int64 v21; // rcx
  HANDLE FileW; // rax
  void *v23; // r15
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  __int128 v30; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v31; // [rsp+60h] [rbp-A0h]
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[176]; // [rsp+910h] [rbp+810h] BYREF
  HKEY hKey; // [rsp+9C0h] [rbp+8C0h]
  _BYTE v35[192]; // [rsp+9D0h] [rbp+8D0h] BYREF
  WCHAR pwzValue[8]; // [rsp+A90h] [rbp+990h] BYREF
  _BYTE v37[26]; // [rsp+AA0h] [rbp+9A0h] BYREF
  WCHAR pszPath[264]; // [rsp+AC0h] [rbp+9C0h] BYREF
  WCHAR FileName[264]; // [rsp+CD0h] [rbp+BD0h] BYREF
  WCHAR v40[264]; // [rsp+EE0h] [rbp+DE0h] BYREF
  WCHAR Filename[264]; // [rsp+10F0h] [rbp+FF0h] BYREF

  v31 = a3;
  *(_QWORD *)&v30 = a6;
  v10 = 1;
  CSearchRootRegistry::CSearchRootRegistry((CSearchRootRegistry *)v35, 0, 0xF003Fu);
  CRegistry::CRegistry((CRegistry *)v33, (struct CRegistry *)v35, L"Gathering Manager", 0x20019u);
  SetLastError(0);
  cbData[0] = 4;
  Type = 0;
  *(_DWORD *)Data = 0;
  if ( !hKey )
  {
    v11 = 6;
LABEL_59:
    SetLastError(v11);
    goto LABEL_60;
  }
  v12 = RegQueryValueExW(hKey, L"SaveHungMiniDumps", 0, &Type, Data, cbData);
  if ( v12 || Type != 4 )
  {
    v11 = v12;
    goto LABEL_59;
  }
  v13 = *(_DWORD *)Data;
  if ( *(_DWORD *)Data >= 0x64u )
    v13 = *(_DWORD *)Data % 0x64u % 0xA;
  if ( v13 )
  {
    if ( v13 == 1 )
    {
      for ( i = 0; !(_DWORD)i; i = 1 )
      {
        if ( WaitForSingleObject(a2[i], 0) == 258 )
        {
          if ( !K32GetModuleFileNameExW(a2[i], 0, Filename, 0x104u)
            || !(unsigned int)GetExeInformation(v21, Filename, FileName, 260) )
          {
            StringCchPrintfW(FileName, 0x104u, L"%s", L"Unknown");
          }
          if ( SHGetSpecialFolderPathW(0, pszPath, 35, 0) )
          {
            if ( (int)StringCchCatW(pszPath, 0x104u, L"\\WindowsSearch\\MiniDumps") >= 0 )
            {
              LODWORD(hTemplateFile) = *a8;
              if ( (int)StringCchPrintfW(
                          v40,
                          0x104u,
                          L"%s\\%s_%s_%d.kdmp",
                          pszPath,
                          (_QWORD)v30,
                          FileName,
                          hTemplateFile) >= 0 )
              {
                SHCreateDirectoryExW(0, pszPath, 0);
                FileW = CreateFileW(v40, 0x40000000u, 0, 0, 2u, 0, 0);
                v23 = FileW;
                if ( FileW != (HANDLE)-1LL )
                {
                  if ( !MiniDumpWriteDump(
                          a2[i],
                          v31[i],
                          FileW,
                          MiniDumpWithFullMemoryInfo|MiniDumpWithPrivateReadWriteMemory|MiniDumpWithProcessThreadData|MiniDumpWithUnloadedModules|MiniDumpWithHandleData|MiniDumpWithDataSegs,
                          0,
                          0,
                          0) )
                  {
                    v10 = 1;
                    break;
                  }
                  v10 = 0;
                  CloseHandle(v23);
                }
              }
            }
          }
        }
      }
      if ( ++*a8 >= 0xA )
        *a8 = 0;
    }
  }
  else if ( (unsigned __int8)IsWerReportCloseHandlePresent()
         && (unsigned __int8)IsWerReportCloseHandlePresent()
         && (unsigned __int8)IsWerReportCloseHandlePresent()
         && (unsigned __int8)IsWerReportCloseHandlePresent()
         && (unsigned __int8)IsWerReportCloseHandlePresent()
         && WaitForSingleObject(*a2, 0) == 258 )
  {
    memset_0(&pReportInformation, 0, sizeof(pReportInformation));
    pReportInformation.dwSize = 2208;
    pReportInformation.hProcess = *a2;
    if ( K32GetModuleFileNameExW(pReportInformation.hProcess, 0, pReportInformation.wzApplicationPath, 0x104u)
      && (unsigned int)GetExeInformation(
                         v14,
                         pReportInformation.wzApplicationPath,
                         pReportInformation.wzApplicationName,
                         128) )
    {
      v30 = 0;
      CResourceLibrary::Init((CResourceLibrary *)&v30, L"MSSrch.dll");
      CResourceLibrary::LoadResString((CResourceLibrary *)&v30, a1, pReportInformation.wzDescription, 512);
      CResourceLibrary::LoadResString((CResourceLibrary *)&v30, 0x20Au, pReportInformation.wzFriendlyEventName, 128);
      CResourceLibrary::FreeLibs((CResourceLibrary *)&v30);
      *(_QWORD *)cbData = 0;
      v10 = WerReportCreate(
              L"MsSearchTerminateProcess",
              WerReportApplicationHang,
              &pReportInformation,
              (HREPORT *)cbData);
      if ( v10 >= 0 )
        v10 = WerReportSetParameter(*(HREPORT *)cbData, 0, 0, pReportInformation.wzApplicationName);
    }
    else
    {
      v10 = -2147467259;
      *(_QWORD *)cbData = 0;
    }
    *(_OWORD *)pwzValue = 0;
    memset(v37, 0, sizeof(v37));
    if ( v10 >= 0 )
    {
      if ( (unsigned int)GetFileVersionFromImage(pReportInformation.wzApplicationPath, pwzValue, v15) )
      {
        v10 = WerReportSetParameter(*(HREPORT *)cbData, 1u, 0, pwzValue);
        if ( v10 >= 0 )
        {
          v10 = WerReportSetParameter(*(HREPORT *)cbData, 2u, 0, a7);
          if ( v10 >= 0 )
          {
            v16 = 0;
            v17 = v31;
            while ( !(_DWORD)v16 )
            {
              if ( WaitForSingleObject(a2[v16], 0) == 258 )
              {
                if ( !K32GetModuleFileNameExW(a2[v16], 0, Filename, 0x104u)
                  || !(unsigned int)GetExeInformation(v18, Filename, v40, 260) )
                {
                  StringCchPrintfW(v40, 0x104u, L"%s", L"Unknown");
                }
                if ( SHGetSpecialFolderPathW(0, pszPath, 35, 0) )
                {
                  if ( (int)StringCchCatW(pszPath, 0x104u, L"\\WindowsSearch\\MiniDumps") >= 0 )
                  {
                    LODWORD(lpcbData) = 0;
                    if ( (int)StringCchPrintfW(FileName, 0x104u, L"%s\\%s_%d.kdmp", pszPath, v40, lpcbData) >= 0 )
                    {
                      SHCreateDirectoryExW(0, pszPath, 0);
                      v19 = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 0, 0);
                      if ( v19 != (HANDLE)-1LL )
                      {
                        if ( !MiniDumpWriteDump(
                                a2[v16],
                                v17[v16],
                                v19,
                                MiniDumpWithFullMemoryInfo|MiniDumpWithPrivateReadWriteMemory|MiniDumpWithProcessThreadData|MiniDumpWithUnloadedModules|MiniDumpWithHandleData|MiniDumpWithDataSegs,
                                0,
                                0,
                                0) )
                          break;
                        CloseHandle(v19);
                      }
                      v10 = WerReportAddFile(*(HREPORT *)cbData, FileName, WerFileTypeHeapdump, 1u);
                      if ( v10 < 0 )
                        goto LABEL_39;
                    }
                  }
                }
              }
              v16 = 1;
            }
            v10 = WerReportSubmit(*(HREPORT *)cbData, WerConsentNotAsked, 0x104u, 0);
          }
        }
      }
      else
      {
        v10 = -2147467259;
      }
    }
LABEL_39:
    if ( *(_QWORD *)cbData )
      WerReportCloseHandle(*(HREPORT *)cbData);
  }
LABEL_60:
  CRegistry::~CRegistry((CRegistry *)v33);
  CRegistry::~CRegistry((CRegistry *)v35);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800534dc  mov     [rsp-8+arg_18], rbx
0x1800534e1  push    rbp
0x1800534e2  push    rsi
0x1800534e3  push    rdi
0x1800534e4  push    r12
0x1800534e6  push    r13
0x1800534e8  push    r14
0x1800534ea  push    r15
0x1800534ec  lea     rbp, [rsp-1210h]
0x1800534f4  mov     eax, 1310h
0x1800534f9  call    _alloca_probe
0x1800534fe  sub     rsp, rax
0x180053501  mov     rax, cs:__security_cookie
0x180053508  xor     rax, rsp
0x18005350b  mov     [rbp+1240h+var_40], rax
0x180053512  mov     [rsp+1340h+var_12E0], r8
0x180053517  mov     r13, rdx
0x18005351a  mov     r15d, ecx
0x18005351d  mov     rax, [rbp+1240h+arg_28]
0x180053524  mov     qword ptr [rsp+1340h+var_12F0], rax
0x180053529  mov     r14, [rbp+1240h+arg_30]
0x180053530  mov     rsi, [rbp+1240h+arg_38]
0x180053537  mov     ebx, 1
0x18005353c  xor     edx, edx; wchar_t *
0x18005353e  mov     r8d, 0F003Fh; unsigned int
0x180053544  lea     rcx, [rbp+1240h+var_970]; this
0x18005354b  call    ??0CSearchRootRegistry@@QEAA@PEB_WK@Z; CSearchRootRegistry::CSearchRootRegistry(wchar_t const *,ulong)
0x180053550  nop
0x180053551  mov     r9d, 20019h; unsigned int
0x180053557  lea     r8, aGatheringManag_0; "Gathering Manager"
0x18005355e  lea     rdx, [rbp+1240h+var_970]; struct CRegistry *
0x180053565  lea     rcx, [rbp+1240h+var_A30]; this
0x18005356c  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x180053571  nop
0x180053572  xor     ecx, ecx; dwErrCode
0x180053574  call    cs:__imp_SetLastError
0x18005357a  mov     [rsp+1340h+cbData], 4
0x180053582  mov     [rsp+1340h+Type], 0
0x18005358a  mov     dword ptr [rsp+1340h+Data], 0
0x180053592  mov     rcx, [rbp+1240h+hKey]; hKey
0x180053599  test    rcx, rcx
0x18005359c  jnz     short loc_1800535A6
0x18005359e  lea     ecx, [rbx+5]
0x1800535a1  jmp     loc_180053B66
0x1800535a6  lea     rax, [rsp+1340h+cbData]
0x1800535ab  mov     [rsp+1340h+lpcbData], rax; lpcbData
0x1800535b0  lea     rax, [rsp+1340h+Data]
0x1800535b5  mov     [rsp+1340h+lpData], rax; lpData
0x1800535ba  lea     r9, [rsp+1340h+Type]; lpType
0x1800535bf  xor     r8d, r8d; lpReserved
0x1800535c2  lea     rdx, ValueName; "SaveHungMiniDumps"
0x1800535c9  call    cs:__imp_RegQueryValueExW
0x1800535cf  test    eax, eax
0x1800535d1  jnz     loc_180053B64
0x1800535d7  cmp     [rsp+1340h+Type], 4
0x1800535dc  jnz     loc_180053B64
0x1800535e2  mov     ecx, dword ptr [rsp+1340h+Data]
0x1800535e6  cmp     ecx, 64h ; 'd'
0x1800535e9  jb      short loc_18005360B
0x1800535eb  mov     eax, 51EB851Fh
0x1800535f0  mul     ecx
0x1800535f2  shr     edx, 5
0x1800535f5  imul    eax, edx, 64h ; 'd'
0x1800535f8  sub     ecx, eax
0x1800535fa  mov     eax, 0CCCCCCCDh
0x1800535ff  mul     ecx
0x180053601  shr     edx, 3
0x180053604  lea     eax, [rdx+rdx*4]
0x180053607  add     eax, eax
0x180053609  sub     ecx, eax
0x18005360b  test    ecx, ecx
0x18005360d  jnz     loc_1800539BD
0x180053613  call    IsWerReportCloseHandlePresent
0x180053618  test    al, al
0x18005361a  jz      loc_180053B6D
0x180053620  call    IsWerReportCloseHandlePresent
0x180053625  test    al, al
0x180053627  jz      loc_180053B6D
0x18005362d  call    IsWerReportCloseHandlePresent
0x180053632  test    al, al
0x180053634  jz      loc_180053B6D
0x18005363a  call    IsWerReportCloseHandlePresent
0x18005363f  test    al, al
0x180053641  jz      loc_180053B6D
0x180053647  call    IsWerReportCloseHandlePresent
0x18005364c  test    al, al
0x18005364e  jz      loc_180053B6D
0x180053654  xor     edx, edx; dwMilliseconds
0x180053656  mov     rcx, [r13+0]; hHandle
0x18005365a  call    cs:__imp_WaitForSingleObject
0x180053660  mov     r12d, 102h
0x180053666  cmp     eax, r12d
0x180053669  jnz     loc_180053B6D
0x18005366f  mov     ebx, 8A0h
0x180053674  mov     r8d, ebx; Size
0x180053677  xor     edx, edx; Val
0x180053679  lea     rcx, [rsp+1340h+pReportInformation]; void *
0x18005367e  call    memset_0
0x180053683  mov     [rsp+1340h+pReportInformation.dwSize], ebx
0x180053687  mov     rcx, [r13+0]; hProcess
0x18005368b  mov     [rsp+1340h+pReportInformation.hProcess], rcx
0x180053690  lea     edi, [r12+2]
0x180053695  mov     r9d, edi; nSize
0x180053698  lea     r8, [rbp+1240h+pReportInformation.wzApplicationPath]; lpFilename
0x18005369f  xor     edx, edx; hModule
0x1800536a1  call    cs:__imp_K32GetModuleFileNameExW
0x1800536a7  mov     esi, 80004005h
0x1800536ac  test    eax, eax
0x1800536ae  jnz     short loc_1800536C0
0x1800536b0  mov     ebx, esi
0x1800536b2  mov     qword ptr [rsp+1340h+cbData], 0
0x1800536bb  jmp     loc_180053775
0x1800536c0  mov     ebx, 80h
0x1800536c5  mov     r9d, ebx
0x1800536c8  lea     r8, [rbp+1240h+pReportInformation.wzApplicationName]
0x1800536cf  lea     rdx, [rbp+1240h+pReportInformation.wzApplicationPath]
0x1800536d6  call    ?GetExeInformation@@YAHW4FILE_INFOTYPE@@PEB_WPEA_WK@Z; GetExeInformation(FILE_INFOTYPE,wchar_t const *,wchar_t *,ulong)
0x1800536db  test    eax, eax
0x1800536dd  jz      short loc_1800536B0
0x1800536df  xorps   xmm0, xmm0
0x1800536e2  movdqu  [rsp+1340h+var_12F0], xmm0
0x1800536e8  lea     rdx, aMssrchDll_0; "MSSrch.dll"
0x1800536ef  lea     rcx, [rsp+1340h+var_12F0]; this
0x1800536f4  call    ?Init@CResourceLibrary@@QEAAXPEB_W@Z; CResourceLibrary::Init(wchar_t const *)
0x1800536f9  mov     r9d, 200h; int
0x1800536ff  lea     r8, [rbp+1240h+pReportInformation.wzDescription]; wchar_t *
0x180053706  mov     edx, r15d; unsigned int
0x180053709  lea     rcx, [rsp+1340h+var_12F0]; this
0x18005370e  call    ?LoadResString@CResourceLibrary@@QEAAHIPEA_WH@Z; CResourceLibrary::LoadResString(uint,wchar_t *,int)
0x180053713  mov     r9d, ebx; int
0x180053716  lea     r8, [rbp+1240h+pReportInformation.wzFriendlyEventName]; wchar_t *
0x18005371a  mov     edx, 20Ah; unsigned int
0x18005371f  lea     rcx, [rsp+1340h+var_12F0]; this
0x180053724  call    ?LoadResString@CResourceLibrary@@QEAAHIPEA_WH@Z; CResourceLibrary::LoadResString(uint,wchar_t *,int)
0x180053729  lea     rcx, [rsp+1340h+var_12F0]; this
0x18005372e  call    ?FreeLibs@CResourceLibrary@@AEAAXXZ; CResourceLibrary::FreeLibs(void)
0x180053733  mov     qword ptr [rsp+1340h+cbData], 0
0x18005373c  lea     r9, [rsp+1340h+cbData]; phReportHandle
0x180053741  lea     r8, [rsp+1340h+pReportInformation]; pReportInformation
0x180053746  lea     edx, [rbx-7Dh]; repType
0x180053749  lea     rcx, pwzEventType; "MsSearchTerminateProcess"
0x180053750  call    cs:__imp_WerReportCreate
0x180053756  mov     ebx, eax
0x180053758  test    eax, eax
0x18005375a  js      short loc_180053775
0x18005375c  lea     r9, [rbp+1240h+pReportInformation.wzApplicationName]; pwzValue
0x180053763  xor     r8d, r8d; pwzName
0x180053766  xor     edx, edx; dwparamID
0x180053768  mov     rcx, qword ptr [rsp+1340h+cbData]; hReportHandle
0x18005376d  call    cs:__imp_WerReportSetParameter
0x180053773  mov     ebx, eax
0x180053775  xorps   xmm0, xmm0
0x180053778  movups  xmmword ptr [rbp+1240h+pwzValue], xmm0
0x18005377f  movups  xmmword ptr [rbp+1240h+var_8A0], xmm0
0x180053786  movups  xmmword ptr [rbp+1240h+var_8A0+0Ah], xmm0
0x18005378d  test    ebx, ebx
0x18005378f  js      loc_1800539A4
0x180053795  lea     rdx, [rbp+1240h+pwzValue]; wchar_t *
0x18005379c  lea     rcx, [rbp+1240h+pReportInformation.wzApplicationPath]; lpwstrFilename
0x1800537a3  call    ?GetFileVersionFromImage@@YAHPEA_W0K@Z; GetFileVersionFromImage(wchar_t *,wchar_t *,ulong)
0x1800537a8  test    eax, eax
0x1800537aa  jnz     short loc_1800537B3
0x1800537ac  mov     ebx, esi
0x1800537ae  jmp     loc_1800539A4
0x1800537b3  lea     r9, [rbp+1240h+pwzValue]; pwzValue
0x1800537ba  xor     r8d, r8d; pwzName
0x1800537bd  lea     edx, [r8+1]; dwparamID
0x1800537c1  mov     rcx, qword ptr [rsp+1340h+cbData]; hReportHandle
0x1800537c6  call    cs:__imp_WerReportSetParameter
0x1800537cc  mov     ebx, eax
0x1800537ce  test    eax, eax
0x1800537d0  js      loc_1800539A4
0x1800537d6  mov     r9, r14; pwzValue
0x1800537d9  xor     r8d, r8d; pwzName
0x1800537dc  lea     edx, [r8+2]; dwparamID
0x1800537e0  mov     rcx, qword ptr [rsp+1340h+cbData]; hReportHandle
0x1800537e5  call    cs:__imp_WerReportSetParameter
0x1800537eb  mov     ebx, eax
0x1800537ed  test    eax, eax
0x1800537ef  js      loc_1800539A4
0x1800537f5  xor     esi, esi
0x1800537f7  mov     r15, [rsp+1340h+var_12E0]
0x1800537fc  cmp     esi, 1
0x1800537ff  jnb     loc_180053989
0x180053805  xor     edx, edx; dwMilliseconds
0x180053807  mov     rcx, [r13+rsi*8+0]; hHandle
0x18005380c  call    cs:__imp_WaitForSingleObject
0x180053812  cmp     eax, r12d
0x180053815  jnz     loc_180053982
0x18005381b  mov     r9d, edi; nSize
0x18005381e  lea     r8, [rbp+1240h+Filename]; lpFilename
0x180053825  xor     edx, edx; hModule
0x180053827  mov     rcx, [r13+rsi*8+0]; hProcess
0x18005382c  call    cs:__imp_K32GetModuleFileNameExW
0x180053832  test    eax, eax
0x180053834  jz      short loc_180053850
0x180053836  mov     r9d, edi
0x180053839  lea     r8, [rbp+1240h+var_460]
0x180053840  lea     rdx, [rbp+1240h+Filename]
0x180053847  call    ?GetExeInformation@@YAHW4FILE_INFOTYPE@@PEB_WPEA_WK@Z; GetExeInformation(FILE_INFOTYPE,wchar_t const *,wchar_t *,ulong)
0x18005384c  test    eax, eax
0x18005384e  jnz     short loc_18005386D
0x180053850  lea     r9, aUnknown_0; "Unknown"
0x180053857  lea     r8, aS_0; "%s"
0x18005385e  mov     rdx, rdi; unsigned __int64
0x180053861  lea     rcx, [rbp+1240h+var_460]; wchar_t *
0x180053868  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18005386d  xor     r9d, r9d; fCreate
0x180053870  lea     r8d, [r9+23h]; csidl
0x180053874  lea     rdx, [rbp+1240h+pszPath]; pszPath
0x18005387b  xor     ecx, ecx; hwnd
0x18005387d  call    cs:__imp_SHGetSpecialFolderPathW
0x180053883  test    eax, eax
0x180053885  jz      loc_180053982
0x18005388b  lea     r8, aWindowssearchM; "\\WindowsSearch\\MiniDumps"
0x180053892  mov     rdx, rdi; unsigned __int64
0x180053895  lea     rcx, [rbp+1240h+pszPath]; wchar_t *
0x18005389c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800538a1  test    eax, eax
0x1800538a3  js      loc_180053982
0x1800538a9  mov     dword ptr [rsp+1340h+lpcbData], esi
0x1800538ad  lea     rax, [rbp+1240h+var_460]
0x1800538b4  mov     [rsp+1340h+lpData], rax
0x1800538b9  lea     r9, [rbp+1240h+pszPath]
0x1800538c0  lea     r8, aSSDKdmp; "%s\\%s_%d.kdmp"
0x1800538c7  mov     rdx, rdi; unsigned __int64
0x1800538ca  lea     rcx, [rbp+1240h+FileName]; wchar_t *
0x1800538d1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800538d6  test    eax, eax
0x1800538d8  js      loc_180053982
0x1800538de  xor     r8d, r8d; psa
0x1800538e1  lea     rdx, [rbp+1240h+pszPath]; pszPath
0x1800538e8  xor     ecx, ecx; hwnd
0x1800538ea  call    cs:__imp_SHCreateDirectoryExW
0x1800538f0  mov     [rsp+1340h+hTemplateFile], 0; hTemplateFile
0x1800538f9  mov     dword ptr [rsp+1340h+lpcbData], 0; dwFlagsAndAttributes
0x180053901  mov     dword ptr [rsp+1340h+lpData], 2; dwCreationDisposition
0x180053909  xor     r9d, r9d; lpSecurityAttributes
0x18005390c  xor     r8d, r8d; dwShareMode
0x18005390f  mov     edx, 40000000h; dwDesiredAccess
0x180053914  lea     rcx, [rbp+1240h+FileName]; lpFileName
0x18005391b  call    cs:__imp_CreateFileW
0x180053921  mov     rbx, rax
0x180053924  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180053928  jz      short loc_180053960
0x18005392a  xor     eax, eax
0x18005392c  mov     [rsp+1340h+hTemplateFile], rax; CallbackParam
0x180053931  mov     [rsp+1340h+lpcbData], rax; UserStreamParam
0x180053936  mov     [rsp+1340h+lpData], rax; ExceptionParam
0x18005393b  mov     r9d, 0B25h; DumpType
0x180053941  mov     r8, rbx; hFile
0x180053944  mov     edx, [r15+rsi*4]; ProcessId
0x180053948  mov     rcx, [r13+rsi*8+0]; hProcess
0x18005394d  call    cs:__imp_MiniDumpWriteDump
0x180053953  test    eax, eax
0x180053955  jz      short loc_18005398D
0x180053957  mov     rcx, rbx; hObject
0x18005395a  call    cs:__imp_CloseHandle
0x180053960  mov     r9d, 1; dwFileFlags
0x180053966  lea     r8d, [r9+2]; repFileType
0x18005396a  lea     rdx, [rbp+1240h+FileName]; pwzPath
0x180053971  mov     rcx, qword ptr [rsp+1340h+cbData]; hReportHandle
0x180053976  call    cs:__imp_WerReportAddFile
0x18005397c  mov     ebx, eax
0x18005397e  test    eax, eax
0x180053980  js      short loc_1800539A4
0x180053982  inc     esi
0x180053984  jmp     loc_1800537FC
0x180053989  test    ebx, ebx
0x18005398b  js      short loc_1800539A4
0x18005398d  xor     r9d, r9d; pSubmitResult
0x180053990  mov     r8d, edi; dwFlags
0x180053993  lea     edx, [r9+1]; consent
0x180053997  mov     rcx, qword ptr [rsp+1340h+cbData]; hReportHandle
0x18005399c  call    cs:__imp_WerReportSubmit
0x1800539a2  mov     ebx, eax
0x1800539a4  mov     rcx, qword ptr [rsp+1340h+cbData]; hReportHandle
0x1800539a9  test    rcx, rcx
0x1800539ac  jz      loc_180053B6D
0x1800539b2  call    cs:__imp_WerReportCloseHandle
0x1800539b8  jmp     loc_180053B6D
0x1800539bd  cmp     ecx, 1
0x1800539c0  jnz     loc_180053B6D
0x1800539c6  xor     r14d, r14d
0x1800539c9  mov     edi, 104h
0x1800539ce  cmp     r14d, 1
0x1800539d2  jnb     loc_180053B55
0x1800539d8  xor     edx, edx; dwMilliseconds
0x1800539da  mov     rcx, [r13+r14*8+0]; hHandle
0x1800539df  call    cs:__imp_WaitForSingleObject
0x1800539e5  cmp     eax, 102h
0x1800539ea  jnz     loc_180053B48
0x1800539f0  mov     r9d, edi; nSize
0x1800539f3  lea     r8, [rbp+1240h+Filename]; lpFilename
0x1800539fa  xor     edx, edx; hModule
0x1800539fc  mov     rcx, [r13+r14*8+0]; hProcess
0x180053a01  call    cs:__imp_K32GetModuleFileNameExW
0x180053a07  test    eax, eax
0x180053a09  jz      short loc_180053A25
0x180053a0b  mov     r9d, edi
  ... truncated ...
```
