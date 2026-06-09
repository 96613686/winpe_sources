# BeginCrashDetection(void)

- ea: `0x18011726c`
- end: `0x180117535`
- name: `?BeginCrashDetection@@YAXXZ`
- size: `713`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801303ac`

## callees

- `0x180038f08`
- `0x18011726c`
- `0x180160518`
- `0x180188d90`
- `0x1801b9afc`
- `0x1801b9c34`
- `0x1801e4e4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011732e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011732e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011750f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011750f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011736b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801173fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011736b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801173fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801173ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801174d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180117504`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801173ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801174d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180117504`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801172b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801172b8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801172d0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801172d0`

## pseudocode

```c
void BeginCrashDetection(void)
{
  __int64 v0; // rcx
  const wchar_t *v1; // rcx
  unsigned int v2; // r9d
  bool v3; // al
  wchar_t *v4; // rdx
  LSTATUS v5; // eax
  struct CEventLog *EventLog; // rax
  __int64 v7; // rcx
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v12[8]; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME v14; // [rsp+78h] [rbp-88h]
  CSearchRegistryRedirectHelper *v15; // [rsp+80h] [rbp-80h]
  wchar_t v16[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  hKey = 0;
  *(_QWORD *)v12 = 0;
  v3 = (unsigned __int8)RtlIsStateSeparationEnabled(v0)
    && GetSearchRegistryRedirect(v1, (struct CSearchRegistryRedirectHelper **)v12)
    && CSearchRegistryRedirectHelper::MapRegistryKeyPath(
         *(CSearchRegistryRedirectHelper **)v12,
         L"SOFTWARE\\Microsoft\\Windows Search\\Databases\\Windows",
         v16,
         v2) >= 0;
  v4 = v16;
  if ( !v3 )
    v4 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search\\Databases\\Windows";
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 3u, &hKey) )
  {
    cbData = 4;
    v5 = RegQueryValueExW(hKey, L"DBInitFailureCount", 0, &Type, Data, &cbData);
    if ( v5 )
    {
      if ( v5 == 2 )
      {
        *(_DWORD *)Data = 1;
        RegSetValueExW(hKey, L"DBInitFailureCount", 0, 4u, Data, 4u);
        RegSetValueExW(hKey, L"DBInitFailureStamp", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u);
      }
    }
    else if ( Type == 4 )
    {
      if ( *(_DWORD *)Data )
      {
        *(_QWORD *)v12 = 0;
        cbData = 8;
        if ( !RegQueryValueExW(hKey, L"DBInitFailureStamp", 0, &Type, v12, &cbData) && Type == 11 )
        {
          v14 = SystemTimeAsFileTime;
          v15 = *(CSearchRegistryRedirectHelper **)v12;
          if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)v12 >= 0xC92A69C000uLL && *(_DWORD *)Data >= 0x14u )
          {
            EventLog = CFTESystemExceptionReporting::GetEventLog((CFTESystemExceptionReporting *)0xC92A69C000LL);
            RecoveryReportIndexRebuildEx_0(v7, EventLog);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x322,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\invertedapplication.cpp",
              (const char *)0xC0041800LL,
              4710);
          }
        }
      }
      else
      {
        RegSetValueExW(hKey, L"DBInitFailureStamp", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u);
      }
      ++*(_DWORD *)Data;
      RegSetValueExW(hKey, L"DBInitFailureCount", 0, 4u, Data, 4u);
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18011726c  mov     [rsp-8+arg_0], rdi
0x180117271  push    rbp
0x180117272  lea     rbp, [rsp-1B0h]
0x18011727a  sub     rsp, 2B0h
0x180117281  mov     rax, cs:__security_cookie
0x180117288  xor     rax, rsp
0x18011728b  mov     [rbp+1B0h+var_10], rax
0x180117292  lea     rcx, [rsp+2B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180117297  mov     dword ptr [rsp+2B0h+Data], 0
0x18011729f  mov     [rsp+2B0h+Type], 0
0x1801172a7  mov     [rsp+2B0h+cbData], 0
0x1801172af  mov     qword ptr [rsp+2B0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1801172b8  call    cs:__imp_GetSystemTimeAsFileTime
0x1801172be  mov     [rsp+2B0h+hKey], 0
0x1801172c7  mov     qword ptr [rsp+2B0h+var_248], 0
0x1801172d0  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801172d6  lea     rdi, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Search\\Da"...
0x1801172dd  test    al, al
0x1801172df  jz      short loc_180117308
0x1801172e1  lea     rdx, [rsp+2B0h+var_248]; struct CSearchRegistryRedirectHelper **
0x1801172e6  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x1801172eb  test    al, al
0x1801172ed  jz      short loc_180117308
0x1801172ef  mov     rcx, qword ptr [rsp+2B0h+var_248]; this
0x1801172f4  lea     r8, [rbp+1B0h+var_220]; wchar_t *
0x1801172f8  mov     rdx, rdi; wchar_t *
0x1801172fb  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x180117300  test    eax, eax
0x180117302  js      short loc_180117308
0x180117304  mov     al, 1
0x180117306  jmp     short loc_18011730A
0x180117308  xor     al, al
0x18011730a  test    al, al
0x18011730c  lea     rdx, [rbp+1B0h+var_220]
0x180117310  lea     rax, [rsp+2B0h+hKey]
0x180117315  mov     r9d, 3; samDesired
0x18011731b  cmovz   rdx, rdi; lpSubKey
0x18011731f  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180117324  xor     r8d, r8d; ulOptions
0x180117327  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18011732e  call    cs:__imp_RegOpenKeyExW
0x180117334  test    eax, eax
0x180117336  jnz     loc_180117515
0x18011733c  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180117341  lea     edi, [rax+4]
0x180117344  lea     rax, [rsp+2B0h+cbData]
0x180117349  mov     [rsp+2B0h+cbData], edi
0x18011734d  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x180117352  lea     r9, [rsp+2B0h+Type]; lpType
0x180117357  lea     rax, [rsp+2B0h+Data]
0x18011735c  xor     r8d, r8d; lpReserved
0x18011735f  lea     rdx, aDbinitfailurec; "DBInitFailureCount"
0x180117366  mov     [rsp+2B0h+phkResult], rax; lpData
0x18011736b  call    cs:__imp_RegQueryValueExW
0x180117371  test    eax, eax
0x180117373  jnz     loc_1801174AA
0x180117379  cmp     [rsp+2B0h+Type], edi
0x18011737d  jnz     loc_18011750A
0x180117383  lea     rdx, aDbinitfailures; "DBInitFailureStamp"
0x18011738a  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18011738f  cmp     dword ptr [rsp+2B0h+Data], eax
0x180117393  jnz     short loc_1801173D0
0x180117395  lea     rax, [rsp+2B0h+SystemTimeAsFileTime]
0x18011739a  mov     dword ptr [rsp+2B0h+lpcbData], 8; cbData
0x1801173a2  lea     r9d, [rdi+7]; dwType
0x1801173a6  mov     [rsp+2B0h+phkResult], rax; lpData
0x1801173ab  xor     r8d, r8d; Reserved
0x1801173ae  call    cs:__imp_RegSetValueExW
0x1801173b4  inc     dword ptr [rsp+2B0h+Data]
0x1801173b8  lea     rax, [rsp+2B0h+Data]
0x1801173bd  mov     dword ptr [rsp+2B0h+lpcbData], edi
0x1801173c1  lea     rdx, aDbinitfailurec; "DBInitFailureCount"
0x1801173c8  mov     r9d, edi
0x1801173cb  jmp     loc_1801174F7
0x1801173d0  lea     rax, [rsp+2B0h+cbData]
0x1801173d5  mov     qword ptr [rsp+2B0h+var_248], 0
0x1801173de  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x1801173e3  lea     r9, [rsp+2B0h+Type]; lpType
0x1801173e8  lea     rax, [rsp+2B0h+var_248]
0x1801173ed  mov     [rsp+2B0h+cbData], 8
0x1801173f5  xor     r8d, r8d; lpReserved
0x1801173f8  mov     [rsp+2B0h+phkResult], rax; lpData
0x1801173fd  call    cs:__imp_RegQueryValueExW
0x180117403  test    eax, eax
0x180117405  jnz     short loc_1801173B4
0x180117407  cmp     [rsp+2B0h+Type], 0Bh
0x18011740c  jnz     short loc_1801173B4
0x18011740e  mov     eax, [rsp+2B0h+SystemTimeAsFileTime.dwLowDateTime]
0x180117412  mov     ecx, [rsp+2B0h+SystemTimeAsFileTime.dwHighDateTime]
0x180117416  mov     dword ptr [rsp+2B0h+var_238], eax
0x18011741a  mov     eax, dword ptr [rsp+2B0h+var_248]
0x18011741e  mov     dword ptr [rsp+2B0h+var_238+4], ecx
0x180117422  mov     ecx, dword ptr [rsp+2B0h+var_248+4]
0x180117426  mov     dword ptr [rbp+1B0h+var_230], eax
0x180117429  mov     rax, [rsp+2B0h+var_238]
0x18011742e  mov     dword ptr [rbp+1B0h+var_230+4], ecx
0x180117431  mov     rcx, 0C92A69C000h; this
0x18011743b  sub     rax, [rbp+1B0h+var_230]
0x18011743f  cmp     rax, rcx
0x180117442  jb      loc_1801173B4
0x180117448  cmp     dword ptr [rsp+2B0h+Data], 14h
0x18011744d  jb      loc_1801173B4
0x180117453  call    ?GetEventLog@CFTESystemExceptionReporting@@QEAAPEAVCEventLog@@XZ; CFTESystemExceptionReporting::GetEventLog(void)
0x180117458  mov     [rsp+2B0h+var_270], 0
0x180117461  mov     rdx, rax
0x180117464  mov     [rsp+2B0h+var_278], 0
0x18011746d  mov     [rsp+2B0h+var_280], 0
0x180117476  mov     dword ptr [rsp+2B0h+lpcbData], 0C0041801h
0x18011747e  mov     dword ptr [rsp+2B0h+phkResult], 1266h; int
0x180117486  call    RecoveryReportIndexRebuildEx_0
0x18011748b  mov     rcx, [rbp+1B8h]; this
0x180117492  lea     r8, aOnecoreuapBase_246; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180117499  mov     r9d, 0C0041800h; char *
0x18011749f  mov     edx, 322h; void *
0x1801174a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801174aa  cmp     eax, 2
0x1801174ad  jnz     short loc_18011750A
0x1801174af  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1801174b4  lea     rax, [rsp+2B0h+Data]
0x1801174b9  mov     dword ptr [rsp+2B0h+lpcbData], edi; cbData
0x1801174bd  lea     rdx, aDbinitfailurec; "DBInitFailureCount"
0x1801174c4  mov     r9d, edi; dwType
0x1801174c7  mov     [rsp+2B0h+phkResult], rax; lpData
0x1801174cc  xor     r8d, r8d; Reserved
0x1801174cf  mov     dword ptr [rsp+2B0h+Data], 1
0x1801174d7  call    cs:__imp_RegSetValueExW
0x1801174dd  lea     rax, [rsp+2B0h+SystemTimeAsFileTime]
0x1801174e2  mov     dword ptr [rsp+2B0h+lpcbData], 8; cbData
0x1801174ea  mov     r9d, 0Bh; dwType
0x1801174f0  lea     rdx, aDbinitfailures; "DBInitFailureStamp"
0x1801174f7  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1801174fc  xor     r8d, r8d; Reserved
0x1801174ff  mov     [rsp+2B0h+phkResult], rax; lpData
0x180117504  call    cs:__imp_RegSetValueExW
0x18011750a  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18011750f  call    cs:__imp_RegCloseKey
0x180117515  mov     rcx, [rbp+1B0h+var_10]
0x18011751c  xor     rcx, rsp; StackCookie
0x18011751f  call    __security_check_cookie
0x180117524  mov     rdi, [rsp+2B0h+arg_0]
0x18011752c  add     rsp, 2B0h
0x180117533  pop     rbp
0x180117534  retn
```
