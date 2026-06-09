# MsiGetProductInfoExW

- ea: `0x18001f700`
- end: `0x18001fd07`
- name: `MsiGetProductInfoExW`
- size: `1543`
- prototype: `UINT __stdcall(LPCWSTR szProductCode, LPCWSTR szUserSid, MSIINSTALLCONTEXT dwContext, LPCWSTR szProperty, LPWSTR szValue, LPDWORD pcchValue)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180129c60`
- `0x180189720`
- `0x18018d420`

## callees

- `0x18001ec50`
- `0x18001f700`
- `0x18001fd10`
- `0x180025a18`
- `0x1800a9d48`
- `0x180157094`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18001fba4`
- `ADVAPI32!SetThreadToken` at `0x18001fbc5`
- `ADVAPI32!SetThreadToken` at `0x18001fc4f`
- `ADVAPI32!SetThreadToken` at `0x18001fcad`
- `ADVAPI32!SetThreadToken` at `0x18001fba4`
- `ADVAPI32!SetThreadToken` at `0x18001fbc5`
- `ADVAPI32!SetThreadToken` at `0x18001fc4f`
- `ADVAPI32!SetThreadToken` at `0x18001fcad`
- `ADVAPI32!OpenThreadToken` at `0x18001f997`
- `ADVAPI32!OpenThreadToken` at `0x18001fa1c`
- `ADVAPI32!OpenThreadToken` at `0x18001f997`
- `ADVAPI32!OpenThreadToken` at `0x18001fa1c`
- `ADVAPI32!OpenProcessToken` at `0x18001f9c6`
- `ADVAPI32!OpenProcessToken` at `0x18001fa4f`
- `ADVAPI32!OpenProcessToken` at `0x18001f9c6`
- `ADVAPI32!OpenProcessToken` at `0x18001fa4f`
- `KERNEL32!CloseHandle` at `0x18001fb6e`
- `KERNEL32!CloseHandle` at `0x18001fb91`
- `KERNEL32!CloseHandle` at `0x18001fbb8`
- `KERNEL32!CloseHandle` at `0x18001fbd9`
- `KERNEL32!CloseHandle` at `0x18001fb6e`
- `KERNEL32!CloseHandle` at `0x18001fb91`
- `KERNEL32!CloseHandle` at `0x18001fbb8`
- `KERNEL32!CloseHandle` at `0x18001fbd9`
- `KERNEL32!LeaveCriticalSection` at `0x18001f78a`
- `KERNEL32!LeaveCriticalSection` at `0x18001f7e4`
- `KERNEL32!LeaveCriticalSection` at `0x18001f8ab`
- `KERNEL32!LeaveCriticalSection` at `0x18001f90f`
- `KERNEL32!LeaveCriticalSection` at `0x18001faa7`
- `KERNEL32!LeaveCriticalSection` at `0x18001fb51`
- `KERNEL32!LeaveCriticalSection` at `0x18001f78a`
- `KERNEL32!LeaveCriticalSection` at `0x18001f7e4`
- `KERNEL32!LeaveCriticalSection` at `0x18001f8ab`
- `KERNEL32!LeaveCriticalSection` at `0x18001f90f`
- `KERNEL32!LeaveCriticalSection` at `0x18001faa7`
- `KERNEL32!LeaveCriticalSection` at `0x18001fb51`
- `KERNEL32!GetLastError` at `0x18001f7a0`
- `KERNEL32!GetLastError` at `0x18001f7a0`
- `KERNEL32!OutputDebugStringW` at `0x18001fa8a`
- `KERNEL32!OutputDebugStringW` at `0x18001fa8a`
- `KERNEL32!EnterCriticalSection` at `0x18001f76e`
- `KERNEL32!EnterCriticalSection` at `0x18001f7c3`
- `KERNEL32!EnterCriticalSection` at `0x18001f831`
- `KERNEL32!EnterCriticalSection` at `0x18001f8fc`
- `KERNEL32!EnterCriticalSection` at `0x18001f76e`
- `KERNEL32!EnterCriticalSection` at `0x18001f7c3`
- `KERNEL32!EnterCriticalSection` at `0x18001f831`
- `KERNEL32!EnterCriticalSection` at `0x18001f8fc`
- `KERNEL32!GlobalAlloc` at `0x18001f949`
- `KERNEL32!GlobalAlloc` at `0x18001f949`
- `KERNEL32!GetCurrentThread` at `0x18001f97e`
- `KERNEL32!GetCurrentThread` at `0x18001fa03`
- `KERNEL32!GetCurrentThread` at `0x18001f97e`
- `KERNEL32!GetCurrentThread` at `0x18001fa03`
- `KERNEL32!GetCurrentProcess` at `0x18001f9b3`
- `KERNEL32!GetCurrentProcess` at `0x18001fa3c`
- `KERNEL32!GetCurrentProcess` at `0x18001f9b3`
- `KERNEL32!GetCurrentProcess` at `0x18001fa3c`
- `KERNEL32!TlsSetValue` at `0x18001f7b3`
- `KERNEL32!TlsSetValue` at `0x18001f924`
- `KERNEL32!TlsSetValue` at `0x18001f7b3`
- `KERNEL32!TlsSetValue` at `0x18001f924`
- `KERNEL32!TlsGetValue` at `0x18001f792`
- `KERNEL32!TlsGetValue` at `0x18001f792`
- `KERNEL32!TlsAlloc` at `0x18001fb33`
- `KERNEL32!TlsAlloc` at `0x18001fb33`

## string_xrefs

- `0x18001fa83`: `Failed to release Service\n`
- `0x18001faf8`: `MsiGetProductInfoExW is returning: %u`
- `0x18001fbf1`: `Entering MsiGetProductInfoExW. szProductCode: %s, szUserSid: %s, dwInstallContext: %d, szProperty: %s`

## pseudocode

```c
UINT __stdcall MsiGetProductInfoExW(
        LPCWSTR szProductCode,
        LPCWSTR szUserSid,
        MSIINSTALLCONTEXT dwContext,
        LPCWSTR szProperty,
        LPWSTR szValue,
        LPDWORD pcchValue)
{
  int v10; // eax
  void *Value; // rdi
  char v12; // bp
  DWORD v13; // ebx
  UINT Info; // esi
  int v15; // eax
  DWORD v16; // ebx
  CMsiServices *v18; // rax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  BOOL v23; // ebx
  BOOL v24; // ebx
  const unsigned __int16 *v25; // r10
  const unsigned __int16 *v26; // rcx
  const unsigned __int16 *v27; // rax
  void *TokenHandle; // [rsp+60h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-30h] BYREF

  if ( g_dmDiagnosticMode )
  {
    v25 = szProperty;
    if ( !szProperty )
      v25 = &Default;
    v26 = szUserSid;
    v27 = szProductCode;
    if ( !szUserSid )
      v26 = &Default;
    if ( !szProductCode )
      v27 = &Default;
    DebugString(
      9,
      0,
      0,
      L"Entering MsiGetProductInfoExW. szProductCode: %s, szUserSid: %s, dwInstallContext: %d, szProperty: %s",
      v27,
      v26,
      (const unsigned __int16 *)(int)dwContext,
      v25,
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  v10 = dword_180306D40;
  Value = 0;
  v12 = 0;
  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &hObject) )
    {
      v23 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v23;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v10 = dword_180306D40;
  }
  if ( g_scServerContext != 2 && v10 == 1 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v13 = g_dwImpersonationSlot;
    if ( g_dwImpersonationSlot == -1
      && (g_dwImpersonationSlot = TlsAlloc(), v13 = g_dwImpersonationSlot, g_dwImpersonationSlot == -1) )
    {
      LeaveCriticalSection(&g_csImpersonationLock);
    }
    else
    {
      LeaveCriticalSection(&g_csImpersonationLock);
      Value = TlsGetValue(v13);
      if ( Value || !GetLastError() )
      {
        TlsSetValue(v13, (LPVOID)0xFFFFFFFF80000000LL);
        v12 = 1;
      }
    }
  }
  EnterCriticalSection(&g_csSharedServicesLock);
  if ( !g_piSharedServices )
  {
    v18 = (CMsiServices *)GlobalAlloc(0x40u, 0x78u);
    if ( v18 )
    {
      g_piSharedServices = CMsiServices::CMsiServices(v18);
      if ( g_piSharedServices )
        goto LABEL_10;
    }
    else
    {
      g_piSharedServices = 0;
    }
    LeaveCriticalSection(&g_csSharedServicesLock);
    goto LABEL_49;
  }
LABEL_10:
  ++g_cSharedServices;
  LeaveCriticalSection(&g_csSharedServicesLock);
  if ( !g_piSharedServices )
  {
LABEL_49:
    Info = 1627;
    goto LABEL_20;
  }
  Info = GetInfoEx(szProductCode, szUserSid, dwContext, 0, szProperty, szValue, pcchValue);
  EnterCriticalSection(&g_csSharedServicesLock);
  if ( !--g_cSharedServices )
  {
    if ( g_piSharedDllsRegKey )
    {
      (*(void (__fastcall **)(struct IMsiRegKey *))(*(_QWORD *)g_piSharedDllsRegKey + 16LL))(g_piSharedDllsRegKey);
      g_piSharedDllsRegKey = 0;
    }
    if ( g_piSharedDllsRegKey32 )
    {
      (*(void (__fastcall **)(struct IMsiRegKey *))(*(_QWORD *)g_piSharedDllsRegKey32 + 16LL))(g_piSharedDllsRegKey32);
      g_piSharedDllsRegKey32 = 0;
    }
    (*(void (__fastcall **)(struct IMsiServices *))(*(_QWORD *)g_piSharedServices + 160LL))(g_piSharedServices);
    while ( (*(int (__fastcall **)(struct IMsiServices *))(*(_QWORD *)g_piSharedServices + 16LL))(g_piSharedServices) > 0 )
      OutputDebugStringW(L"Failed to release Service\r\n");
    g_piSharedServices = 0;
  }
  LeaveCriticalSection(&g_csSharedServicesLock);
LABEL_20:
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"MsiGetProductInfoExW is returning: %u",
      (const unsigned __int16 *)Info,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  v15 = dword_180306D40;
  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (void *)-1LL;
    v21 = GetCurrentThread();
    if ( OpenThreadToken(v21, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    v22 = GetCurrentProcess();
    if ( OpenProcessToken(v22, 8u, &hObject) )
    {
      v24 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v24;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v15 = dword_180306D40;
  }
  if ( v15 == 1 && g_scServerContext != 2 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v16 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v16 != -1 )
    {
      if ( v12 )
        TlsSetValue(v16, Value);
    }
  }
  return Info;
}

```

## disassembly

```asm
0x18001f700  mov     rax, rsp
0x18001f703  push    rbp
0x18001f704  push    rsi
0x18001f705  push    rdi
0x18001f706  sub     rsp, 80h
0x18001f70d  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18001f714  mov     rsi, r9
0x18001f717  mov     [rax+10h], r12
0x18001f71b  mov     [rax+18h], r13
0x18001f71f  lea     r13, aNull; "(NULL)"
0x18001f726  mov     [rax-20h], r14
0x18001f72a  mov     r14, rdx
0x18001f72d  mov     [rax-28h], r15
0x18001f731  mov     r15, rcx
0x18001f734  movsxd  r12, r8d
0x18001f737  jnz     loc_18001FBE4
0x18001f73d  mov     eax, cs:dword_180306D40
0x18001f743  xor     edi, edi
0x18001f745  xor     bpl, bpl
0x18001f748  mov     [rsp+98h+arg_0], rbx
0x18001f750  cmp     eax, 0FFFFFFFFh
0x18001f753  jz      loc_18001F975
0x18001f759  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18001f760  jz      short loc_18001F7BC
0x18001f762  cmp     eax, 1
0x18001f765  jnz     short loc_18001F7BC
0x18001f767  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f76e  call    cs:__imp_EnterCriticalSection
0x18001f774  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18001f77a  cmp     ebx, 0FFFFFFFFh
0x18001f77d  jz      loc_18001FB33
0x18001f783  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f78a  call    cs:__imp_LeaveCriticalSection
0x18001f790  mov     ecx, ebx; dwTlsIndex
0x18001f792  call    cs:__imp_TlsGetValue
0x18001f798  mov     rdi, rax
0x18001f79b  test    rax, rax
0x18001f79e  jnz     short loc_18001F7AA
0x18001f7a0  call    cs:__imp_GetLastError
0x18001f7a6  test    eax, eax
0x18001f7a8  jnz     short loc_18001F7BC
0x18001f7aa  mov     rdx, 0FFFFFFFF80000000h; lpTlsValue
0x18001f7b1  mov     ecx, ebx; dwTlsIndex
0x18001f7b3  call    cs:__imp_TlsSetValue
0x18001f7b9  mov     bpl, 1
0x18001f7bc  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f7c3  call    cs:__imp_EnterCriticalSection
0x18001f7c9  cmp     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, 0; IMsiServices * g_piSharedServices
0x18001f7d1  jz      loc_18001F93F
0x18001f7d7  inc     cs:?g_cSharedServices@@3HA; int g_cSharedServices
0x18001f7dd  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f7e4  call    cs:__imp_LeaveCriticalSection
0x18001f7ea  cmp     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, 0; IMsiServices * g_piSharedServices
0x18001f7f2  jz      loc_18001FAAD
0x18001f7f8  mov     rax, [rsp+98h+pcchValue]
0x18001f800  xor     r9d, r9d; bool
0x18001f803  mov     [rsp+98h+var_68], rax; unsigned int *
0x18001f808  mov     r8d, r12d; enum tagMSIINSTALLCONTEXT
0x18001f80b  mov     rax, [rsp+98h+szValue]
0x18001f813  mov     rdx, r14; unsigned __int16 *
0x18001f816  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x18001f81b  mov     rcx, r15; unsigned __int16 *
0x18001f81e  mov     [rsp+98h+var_78], rsi; unsigned __int16 *
0x18001f823  call    ?GetInfoEx@@YAKPEBG0W4tagMSIINSTALLCONTEXT@@_N0PEAGPEAK@Z; GetInfoEx(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,bool,ushort const *,ushort *,ulong *)
0x18001f828  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f82f  mov     esi, eax
0x18001f831  call    cs:__imp_EnterCriticalSection
0x18001f837  mov     ecx, cs:?g_cSharedServices@@3HA; int g_cSharedServices
0x18001f83d  sub     ecx, 1
0x18001f840  mov     cs:?g_cSharedServices@@3HA, ecx; int g_cSharedServices
0x18001f846  jnz     short loc_18001F8A4
0x18001f848  mov     rcx, cs:?g_piSharedDllsRegKey@@3PEAVIMsiRegKey@@EA; IMsiRegKey * g_piSharedDllsRegKey
0x18001f84f  test    rcx, rcx
0x18001f852  jnz     loc_18001FAB7
0x18001f858  mov     rcx, cs:?g_piSharedDllsRegKey32@@3PEAVIMsiRegKey@@EA; IMsiRegKey * g_piSharedDllsRegKey32
0x18001f85f  test    rcx, rcx
0x18001f862  jnz     loc_18001FAD3
0x18001f868  mov     rcx, cs:?g_piSharedServices@@3PEAVIMsiServices@@EA; IMsiServices * g_piSharedServices
0x18001f86f  mov     rax, [rcx]
0x18001f872  mov     rax, [rax+0A0h]
0x18001f879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f87e  mov     rcx, cs:?g_piSharedServices@@3PEAVIMsiServices@@EA; IMsiServices * g_piSharedServices
0x18001f885  mov     rax, [rcx]
0x18001f888  mov     rax, [rax+10h]
0x18001f88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f891  test    eax, eax
0x18001f893  jg      loc_18001FA83
0x18001f899  mov     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, 0; IMsiServices * g_piSharedServices
0x18001f8a4  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f8ab  call    cs:__imp_LeaveCriticalSection
0x18001f8b1  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18001f8b8  mov     r15, [rsp+98h+var_28]
0x18001f8bd  mov     r14, [rsp+98h+var_20]
0x18001f8c2  mov     r12, [rsp+98h+arg_8]
0x18001f8ca  jnz     loc_18001FAEF
0x18001f8d0  mov     eax, cs:dword_180306D40
0x18001f8d6  cmp     eax, 0FFFFFFFFh
0x18001f8d9  jz      loc_18001F9FA
0x18001f8df  mov     r13, [rsp+98h+arg_10]
0x18001f8e7  cmp     eax, 1
0x18001f8ea  jnz     short loc_18001F92A
0x18001f8ec  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18001f8f3  jz      short loc_18001F92A
0x18001f8f5  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f8fc  call    cs:__imp_EnterCriticalSection
0x18001f902  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18001f908  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f90f  call    cs:__imp_LeaveCriticalSection
0x18001f915  cmp     ebx, 0FFFFFFFFh
0x18001f918  jz      short loc_18001F92A
0x18001f91a  test    bpl, bpl
0x18001f91d  jz      short loc_18001F92A
0x18001f91f  mov     rdx, rdi; lpTlsValue
0x18001f922  mov     ecx, ebx; dwTlsIndex
0x18001f924  call    cs:__imp_TlsSetValue
0x18001f92a  mov     rbx, [rsp+98h+arg_0]
0x18001f932  mov     eax, esi
0x18001f934  add     rsp, 80h
0x18001f93b  pop     rdi
0x18001f93c  pop     rsi
0x18001f93d  pop     rbp
0x18001f93e  retn
0x18001f93f  mov     edx, 78h ; 'x'; dwBytes
0x18001f944  mov     ecx, 40h ; '@'; uFlags
0x18001f949  call    cs:__imp_GlobalAlloc
0x18001f94f  test    rax, rax
0x18001f952  jz      loc_18001FA95
0x18001f958  mov     rcx, rax; this
0x18001f95b  call    ??0CMsiServices@@QEAA@XZ; CMsiServices::CMsiServices(void)
0x18001f960  mov     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, rax; IMsiServices * g_piSharedServices
0x18001f967  test    rax, rax
0x18001f96a  jnz     loc_18001F7D7
0x18001f970  jmp     loc_18001FAA0
0x18001f975  mov     [rsp+98h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001f97e  call    cs:__imp_GetCurrentThread
0x18001f984  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x18001f989  mov     edx, 4; DesiredAccess
0x18001f98e  mov     rcx, rax; ThreadHandle
0x18001f991  mov     r8d, 1; OpenAsSelf
0x18001f997  call    cs:__imp_OpenThreadToken
0x18001f99d  test    eax, eax
0x18001f99f  jnz     loc_18001FC4B
0x18001f9a5  mov     [rsp+98h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001f9ae  mov     [rsp+98h+hObject], rdi
0x18001f9b3  call    cs:__imp_GetCurrentProcess
0x18001f9b9  lea     r8, [rsp+98h+hObject]; TokenHandle
0x18001f9be  mov     edx, 8; DesiredAccess
0x18001f9c3  mov     rcx, rax; ProcessHandle
0x18001f9c6  call    cs:__imp_OpenProcessToken
0x18001f9cc  test    eax, eax
0x18001f9ce  jnz     loc_18001FB5C
0x18001f9d4  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x18001f9da  jnz     loc_18001FC67
0x18001f9e0  mov     rdx, [rsp+98h+TokenHandle]; Token
0x18001f9e5  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001f9e9  jnz     loc_18001FBA2
0x18001f9ef  mov     eax, cs:dword_180306D40
0x18001f9f5  jmp     loc_18001F759
0x18001f9fa  mov     [rsp+98h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001fa03  call    cs:__imp_GetCurrentThread
0x18001fa09  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x18001fa0e  mov     edx, 4; DesiredAccess
0x18001fa13  mov     rcx, rax; ThreadHandle
0x18001fa16  mov     r8d, 1; OpenAsSelf
0x18001fa1c  call    cs:__imp_OpenThreadToken
0x18001fa22  test    eax, eax
0x18001fa24  jnz     loc_18001FCA9
0x18001fa2a  mov     [rsp+98h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001fa33  mov     [rsp+98h+hObject], 0
0x18001fa3c  call    cs:__imp_GetCurrentProcess
0x18001fa42  lea     r8, [rsp+98h+hObject]; TokenHandle
0x18001fa47  mov     edx, 8; DesiredAccess
0x18001fa4c  mov     rcx, rax; ProcessHandle
0x18001fa4f  call    cs:__imp_OpenProcessToken
0x18001fa55  test    eax, eax
0x18001fa57  jnz     loc_18001FB7F
0x18001fa5d  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18001fa63  jnz     loc_18001FCC5
0x18001fa69  mov     rdx, [rsp+98h+TokenHandle]; Token
0x18001fa6e  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001fa72  jnz     loc_18001FBC3
0x18001fa78  mov     eax, cs:dword_180306D40
0x18001fa7e  jmp     loc_18001F8DF
0x18001fa83  lea     rcx, aFailedToReleas; "Failed to release Service\r\n"
0x18001fa8a  call    cs:__imp_OutputDebugStringW
0x18001fa90  jmp     loc_18001F87E
0x18001fa95  mov     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, 0; IMsiServices * g_piSharedServices
0x18001faa0  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001faa7  call    cs:__imp_LeaveCriticalSection
0x18001faad  mov     esi, 65Bh
0x18001fab2  jmp     loc_18001F8B1
0x18001fab7  mov     rdx, [rcx]
0x18001faba  mov     rax, [rdx+10h]
0x18001fabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fac3  mov     cs:?g_piSharedDllsRegKey@@3PEAVIMsiRegKey@@EA, 0; IMsiRegKey * g_piSharedDllsRegKey
0x18001face  jmp     loc_18001F858
0x18001fad3  mov     rax, [rcx]
0x18001fad6  mov     rax, [rax+10h]
0x18001fada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fadf  mov     cs:?g_piSharedDllsRegKey32@@3PEAVIMsiRegKey@@EA, 0; IMsiRegKey * g_piSharedDllsRegKey32
0x18001faea  jmp     loc_18001F868
0x18001faef  xor     edx, edx; unsigned __int16
0x18001faf1  mov     eax, esi
0x18001faf3  mov     [rsp+98h+var_40], rdx; void *
0x18001faf8  lea     r9, aMsigetproducti_5; "MsiGetProductInfoExW is returning: %u"
0x18001faff  mov     [rsp+98h+var_48], edx; unsigned int
0x18001fb03  xor     r8d, r8d; int
0x18001fb06  mov     [rsp+98h+var_50], r13; unsigned __int16 *
0x18001fb0b  mov     ecx, 9; int
0x18001fb10  mov     [rsp+98h+var_58], r13; unsigned __int16 *
0x18001fb15  mov     [rsp+98h+var_60], r13; unsigned __int16 *
0x18001fb1a  mov     [rsp+98h+var_68], r13; unsigned __int16 *
0x18001fb1f  mov     [rsp+98h+var_70], r13; unsigned __int16 *
0x18001fb24  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x18001fb29  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18001fb2e  jmp     loc_18001F8D0
0x18001fb33  call    cs:__imp_TlsAlloc
0x18001fb39  mov     cs:?g_dwImpersonationSlot@@3KA, eax; ulong g_dwImpersonationSlot
0x18001fb3f  mov     ebx, eax
0x18001fb41  cmp     eax, 0FFFFFFFFh
0x18001fb44  jnz     loc_18001F783
0x18001fb4a  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001fb51  call    cs:__imp_LeaveCriticalSection
0x18001fb57  jmp     loc_18001F7BC
0x18001fb5c  mov     rcx, [rsp+98h+hObject]; void *
0x18001fb61  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x18001fb66  mov     rcx, [rsp+98h+hObject]; hObject
0x18001fb6b  movzx   ebx, al
0x18001fb6e  call    cs:__imp_CloseHandle
0x18001fb74  mov     cs:dword_180306D40, ebx
0x18001fb7a  jmp     loc_18001F9E0
0x18001fb7f  mov     rcx, [rsp+98h+hObject]; void *
0x18001fb84  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x18001fb89  mov     rcx, [rsp+98h+hObject]; hObject
0x18001fb8e  movzx   ebx, al
0x18001fb91  call    cs:__imp_CloseHandle
0x18001fb97  mov     cs:dword_180306D40, ebx
0x18001fb9d  jmp     loc_18001FA69
0x18001fba2  xor     ecx, ecx; Thread
0x18001fba4  call    cs:__imp_SetThreadToken
0x18001fbaa  test    eax, eax
0x18001fbac  jnz     short loc_18001FBB3
0x18001fbae  call    ExitProcessIfNotClient
0x18001fbb3  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x18001fbb8  call    cs:__imp_CloseHandle
0x18001fbbe  jmp     loc_18001F9EF
0x18001fbc3  xor     ecx, ecx; Thread
0x18001fbc5  call    cs:__imp_SetThreadToken
0x18001fbcb  test    eax, eax
0x18001fbcd  jnz     short loc_18001FBD4
0x18001fbcf  call    ExitProcessIfNotClient
0x18001fbd4  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x18001fbd9  call    cs:__imp_CloseHandle
0x18001fbdf  jmp     loc_18001FA78
0x18001fbe4  lea     rdx, Default
0x18001fbeb  test    rsi, rsi
0x18001fbee  mov     r10, rsi
0x18001fbf1  lea     r9, aEnteringMsiget_3; "Entering MsiGetProductInfoExW. szProduc"...
0x18001fbf8  cmovz   r10, rdx
0x18001fbfc  mov     rcx, r14
0x18001fbff  test    r14, r14
0x18001fc02  mov     rax, r15
0x18001fc05  cmovz   rcx, rdx
0x18001fc09  test    r15, r15
0x18001fc0c  cmovz   rax, rdx
0x18001fc10  xor     edx, edx; unsigned __int16
0x18001fc12  mov     [rsp+98h+var_40], rdx; void *
0x18001fc17  xor     r8d, r8d; int
0x18001fc1a  mov     [rsp+98h+var_48], edx; unsigned int
0x18001fc1e  mov     [rsp+98h+var_50], r13; unsigned __int16 *
0x18001fc23  mov     [rsp+98h+var_58], r13; unsigned __int16 *
0x18001fc28  mov     [rsp+98h+var_60], r10; unsigned __int16 *
0x18001fc2d  mov     [rsp+98h+var_68], r12; unsigned __int16 *
0x18001fc32  mov     [rsp+98h+var_70], rcx; unsigned __int16 *
0x18001fc37  mov     ecx, 9; int
0x18001fc3c  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x18001fc41  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18001fc46  jmp     loc_18001F73D
0x18001fc4b  xor     edx, edx; Token
0x18001fc4d  xor     ecx, ecx; Thread
0x18001fc4f  call    cs:__imp_SetThreadToken
0x18001fc55  test    eax, eax
0x18001fc57  jnz     loc_18001F9AE
0x18001fc5d  call    ExitProcessIfNotClient
0x18001fc62  jmp     loc_18001F9AE
0x18001fc67  xor     edx, edx; unsigned __int16
0x18001fc69  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x18001fc70  mov     [rsp+98h+var_40], rdx; void *
0x18001fc75  xor     r8d, r8d; int
0x18001fc78  mov     [rsp+98h+var_48], edx; unsigned int
0x18001fc7c  mov     ecx, 9; int
0x18001fc81  mov     [rsp+98h+var_50], r13; unsigned __int16 *
0x18001fc86  mov     [rsp+98h+var_58], r13; unsigned __int16 *
0x18001fc8b  mov     [rsp+98h+var_60], r13; unsigned __int16 *
0x18001fc90  mov     [rsp+98h+var_68], r13; unsigned __int16 *
0x18001fc95  mov     [rsp+98h+var_70], r13; unsigned __int16 *
0x18001fc9a  mov     [rsp+98h+var_78], r13; unsigned __int16 *
0x18001fc9f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18001fca4  jmp     loc_18001F9E0
0x18001fca9  xor     edx, edx; Token
  ... truncated ...
```
