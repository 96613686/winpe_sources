# CreateActionListInternalExclusive

- ea: `0x18006ce04`
- end: `0x18006d4b2`
- name: `CreateActionListInternalExclusive`
- size: `1710`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180071cf0`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001b9e4`
- `0x180065a7c`
- `0x180069378`
- `0x18006ce04`

## import_xrefs

- `ntdll!NtClose` at `0x18006d081`
- `ntdll!NtClose` at `0x18006d247`
- `ntdll!NtClose` at `0x18006d413`
- `ntdll!NtClose` at `0x18006d458`
- `ntdll!NtClose` at `0x18006d081`
- `ntdll!NtClose` at `0x18006d247`
- `ntdll!NtClose` at `0x18006d413`
- `ntdll!NtClose` at `0x18006d458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cf56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d0f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d1fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cf56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d0f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d1fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d2d1`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18006cec1`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18006ceee`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18006cec1`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18006ceee`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006cffb`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006d047`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006d1b4`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006d1ee`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006d28b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006d2c1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006cffb`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006d047`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006d1b4`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006d1ee`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006d28b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18006d2c1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18006cf2b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18006cf2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d22d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d3f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d43e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d22d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d3f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006d43e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006d0c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006d0c2`

## string_xrefs

- `0x18006ceb8`: `Cbscore.dll`
- `0x18006cee5`: `ServicingUAPI.dll`
- `0x18006d34e`: `arbiter: --- CreateActionlist end with result: {0} ---`
- `0x18006d385`: `Failed to create action list.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateActionListInternalExclusive(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8,
        int a9,
        wchar_t *a10,
        __int64 a11,
        struct ActionList **a12)
{
  char v14; // r14
  BOOL ModuleHandle; // eax
  BOOL v16; // ebx
  BOOL v17; // eax
  HANDLE MutexW; // rax
  signed int LastError; // eax
  unsigned int v20; // edi
  __int64 v21; // rdx
  const char *v22; // r9
  __int64 result; // rax
  DWORD v24; // eax
  unsigned int v25; // edi
  signed int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rdx
  int ActionListInternal; // edi
  __int64 v30; // rcx
  __int64 v31; // rdx
  int *v32; // [rsp+20h] [rbp-C8h]
  int *v33; // [rsp+20h] [rbp-C8h]
  int v34[2]; // [rsp+60h] [rbp-88h] BYREF
  int v35[2]; // [rsp+68h] [rbp-80h] BYREF
  HANDLE *p_Handle; // [rsp+70h] [rbp-78h]
  char v37; // [rsp+78h] [rbp-70h]
  __int64 v38; // [rsp+80h] [rbp-68h]
  HANDLE Handle; // [rsp+88h] [rbp-60h] BYREF
  wchar_t *v40; // [rsp+90h] [rbp-58h] BYREF
  HMODULE hLibModule; // [rsp+98h] [rbp-50h] BYREF
  HMODULE phModule; // [rsp+A0h] [rbp-48h] BYREF
  int v43; // [rsp+A8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v38 = -2;
  *(_QWORD *)v35 = a5;
  v40 = a10;
  *(_QWORD *)v34 = a11;
  if ( a12 )
    *a12 = 0;
  Handle = 0;
  p_Handle = &Handle;
  v14 = 0;
  v37 = 0;
  phModule = 0;
  hLibModule = 0;
  ModuleHandle = GetModuleHandleExW(0, L"Cbscore.dll", &phModule);
  try
  {
    v16 = ModuleHandle;
    if ( hLibModule )
      goto LABEL_87;
    v17 = GetModuleHandleExW(0, L"ServicingUAPI.dll", &hLibModule);
    if ( v16 || v17 )
    {
      LogAdapter::TraceInfo<>("Arbiter invoked from servicing stack; skip locking");
      goto LABEL_61;
    }
    if ( a8 )
    {
      LogAdapter::TraceInfo<>("Arbiter invoked for offline servicing; skip locking");
LABEL_61:
      if ( hLibModule )
      {
        if ( !FreeLibrary(hLibModule) )
        {
          GetLastError();
          __fastfail(7u);
        }
        hLibModule = 0;
      }
      if ( phModule && !FreeLibrary(phModule) )
      {
        GetLastError();
        __fastfail(7u);
      }
      ActionListInternal = CreateActionListInternal(
                             0,
                             a2,
                             a3,
                             0,
                             *(wchar_t **)v35,
                             0,
                             0,
                             a8,
                             0,
                             v40,
                             *(wchar_t **)v34,
                             a12);
      v43 = ActionListInternal;
      v30 = *(_QWORD *)&LogAdapter::g_Logger;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LOBYTE(v28) = 1;
        LogAdapter::Logger::LogNumObjects<long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v28,
          1,
          "arbiter: --- CreateActionlist end with result: {0} ---",
          &v43);
        v30 = *(_QWORD *)&LogAdapter::g_Logger;
        ActionListInternal = v43;
      }
      if ( ActionListInternal >= 0 )
      {
        if ( v14 && Handle )
          ReleaseMutex(Handle);
        if ( Handle && NtClose(Handle) < 0 )
          __fastfail(7u);
        return 0;
      }
      else
      {
        LODWORD(v40) = ActionListInternal;
        if ( v30 )
        {
          LogAdapter::Logger::LogNumObjects<>(v30, 0, 3, "Failed to create action list.");
          *(_QWORD *)v35 = &v40;
          v33 = v35;
          LOBYTE(v31) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v31,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7C5,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)ActionListInternal,
          (int)v33);
        if ( v14 && Handle )
          ReleaseMutex(Handle);
        if ( Handle && NtClose(Handle) < 0 )
          __fastfail(7u);
        return (unsigned int)ActionListInternal;
      }
    }
    MutexW = CreateMutexW(0, 0, L"BDA50A95-17AC-40FE-83B6-DAE899448200");
    if ( Handle )
    {
LABEL_87:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18006D4B0LL);
    }
    Handle = MutexW;
    if ( !MutexW )
    {
      LastError = GetLastError();
      v20 = LastError;
      if ( LastError > 0 )
        v20 = (unsigned __int16)LastError | 0x80070000;
      if ( (v20 & 0x80000000) != 0 )
      {
        LODWORD(v40) = v20;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to initialize the arbiter mutex");
          *(_QWORD *)v34 = &v40;
          v32 = v34;
          LOBYTE(v21) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v21,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7A5,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)v20,
          (int)v32);
        if ( hLibModule )
        {
          if ( !FreeLibrary(hLibModule) )
          {
            GetLastError();
            __fastfail(7u);
          }
          hLibModule = 0;
        }
        if ( phModule )
        {
          if ( !FreeLibrary(phModule) )
          {
            GetLastError();
            __fastfail(7u);
          }
          phModule = 0;
        }
        if ( Handle && NtClose(Handle) < 0 )
          __fastfail(7u);
        return v20;
      }
      MutexW = Handle;
      if ( !Handle )
        __fastfail(7u);
    }
    v24 = WaitForSingleObject(MutexW, 0x927C0u);
    if ( !v24 )
    {
      v14 = 1;
      v37 = 1;
      goto LABEL_61;
    }
    if ( v24 == 128 )
    {
      v14 = 1;
      v37 = 1;
      v25 = -2147418113;
      goto LABEL_42;
    }
    if ( v24 != 258 )
    {
      if ( v24 != -1 )
      {
        v25 = -2147467259;
LABEL_42:
        LODWORD(v40) = v25;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to acquire the mutex");
          *(_QWORD *)v34 = &v40;
          v32 = v34;
          LOBYTE(v27) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v27,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7B2,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)v25,
          (int)v32);
        if ( hLibModule )
        {
          if ( !FreeLibrary(hLibModule) )
          {
            GetLastError();
            __fastfail(7u);
          }
          hLibModule = 0;
        }
        if ( phModule )
        {
          if ( !FreeLibrary(phModule) )
          {
            GetLastError();
            __fastfail(7u);
          }
          phModule = 0;
        }
        if ( v14 && Handle )
          ReleaseMutex(Handle);
        if ( Handle && NtClose(Handle) < 0 )
          __fastfail(7u);
        return v25;
      }
      v26 = GetLastError();
      v25 = v26;
      if ( v26 > 0 )
        v25 = (unsigned __int16)v26 | 0x80070000;
      if ( v25 != -2147023436 )
      {
        if ( (v25 & 0x80000000) == 0 )
          goto LABEL_61;
        goto LABEL_42;
      }
    }
    v25 = -2146467823;
    goto LABEL_42;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7C9,
                           (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x18006ce04  mov     rax, rsp
0x18006ce07  push    rdi
0x18006ce08  push    r12
0x18006ce0a  push    r13
0x18006ce0c  push    r14
0x18006ce0e  push    r15
0x18006ce10  sub     rsp, 0C0h
0x18006ce17  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x18006ce1f  mov     [rax+8], rbx
0x18006ce23  mov     [rax+20h], rsi
0x18006ce27  mov     rax, cs:__security_cookie
0x18006ce2e  xor     rax, rsp
0x18006ce31  mov     [rsp+0E8h+var_38], rax
0x18006ce39  mov     r13, r8
0x18006ce3c  mov     r12d, edx
0x18006ce3f  mov     rax, [rsp+0E8h+arg_20]
0x18006ce47  mov     qword ptr [rsp+0E8h+var_80], rax
0x18006ce4c  mov     r15, [rsp+0E8h+arg_38]
0x18006ce54  mov     rax, [rsp+0E8h+arg_48]
0x18006ce5c  mov     [rsp+0E8h+var_58], rax
0x18006ce64  mov     rax, [rsp+0E8h+arg_50]
0x18006ce6c  mov     qword ptr [rsp+0E8h+var_88], rax
0x18006ce71  mov     rsi, [rsp+0E8h+arg_58]
0x18006ce79  xor     edi, edi
0x18006ce7b  test    rsi, rsi
0x18006ce7e  jz      short loc_18006CE83
0x18006ce80  mov     [rsi], rdi
0x18006ce83  mov     [rsp+0E8h+Handle], rdi
0x18006ce8b  lea     rax, [rsp+0E8h+Handle]
0x18006ce93  mov     [rsp+0E8h+var_78], rax
0x18006ce98  mov     r14b, dil
0x18006ce9b  mov     [rsp+0E8h+var_70], dil
0x18006cea0  mov     [rsp+0E8h+phModule], rdi
0x18006cea8  mov     [rsp+0E8h+hLibModule], rdi
0x18006ceb0  lea     r8, [rsp+0E8h+phModule]; phModule
0x18006ceb8  lea     rdx, aCbscoreDll_1; "Cbscore.dll"
0x18006cebf  xor     ecx, ecx; dwFlags
0x18006cec1  call    cs:__imp_GetModuleHandleExW
0x18006cec8  nop     dword ptr [rax+rax+00h]
0x18006cecd  mov     ebx, eax
0x18006cecf  cmp     [rsp+0E8h+hLibModule], rdi
0x18006ced7  jnz     loc_18006D4A6
0x18006cedd  lea     r8, [rsp+0E8h+hLibModule]; phModule
0x18006cee5  lea     rdx, aServicinguapiD_0; "ServicingUAPI.dll"
0x18006ceec  xor     ecx, ecx; dwFlags
0x18006ceee  call    cs:__imp_GetModuleHandleExW
0x18006cef5  nop     dword ptr [rax+rax+00h]
0x18006cefa  test    ebx, ebx
0x18006cefc  jnz     loc_18006D26D
0x18006cf02  test    eax, eax
0x18006cf04  jnz     loc_18006D26D
0x18006cf0a  test    r15, r15
0x18006cf0d  jz      short loc_18006CF20
0x18006cf0f  lea     rcx, aArbiterInvoked; "Arbiter invoked for offline servicing; "...
0x18006cf16  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18006cf1b  jmp     loc_18006D279
0x18006cf20  lea     r8, aBda50a9517ac40; "BDA50A95-17AC-40FE-83B6-DAE899448200"
0x18006cf27  xor     edx, edx; bInitialOwner
0x18006cf29  xor     ecx, ecx; lpMutexAttributes
0x18006cf2b  call    cs:__imp_CreateMutexW
0x18006cf32  nop     dword ptr [rax+rax+00h]
0x18006cf37  cmp     [rsp+0E8h+Handle], rdi
0x18006cf3f  jnz     loc_18006D4A6
0x18006cf45  mov     [rsp+0E8h+Handle], rax
0x18006cf4d  test    rax, rax
0x18006cf50  jnz     loc_18006D0B5
0x18006cf56  call    cs:__imp_GetLastError
0x18006cf5d  nop     dword ptr [rax+rax+00h]
0x18006cf62  mov     edi, eax
0x18006cf64  test    eax, eax
0x18006cf66  jle     short loc_18006CF71
0x18006cf68  movzx   edi, ax
0x18006cf6b  or      edi, 80070000h
0x18006cf71  test    edi, edi
0x18006cf73  jns     loc_18006D09D
0x18006cf79  mov     dword ptr [rsp+0E8h+var_58], edi
0x18006cf80  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006cf87  test    rcx, rcx
0x18006cf8a  jz      short loc_18006CFD1
0x18006cf8c  lea     r9, aFailedToInitia_3; "Failed to initialize the arbiter mutex"
0x18006cf93  mov     esi, 3
0x18006cf98  mov     r8d, esi
0x18006cf9b  xor     edx, edx
0x18006cf9d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18006cfa2  lea     rax, [rsp+0E8h+var_58]
0x18006cfaa  mov     qword ptr [rsp+0E8h+var_88], rax
0x18006cfaf  lea     rax, [rsp+0E8h+var_88]
0x18006cfb4  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x18006cfb9  lea     r9, asc_1801CAFB4; ": {}"
0x18006cfc0  mov     r8d, esi
0x18006cfc3  mov     dl, 1
0x18006cfc5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006cfcc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18006cfd1  mov     rcx, [rsp+0E8h]; this
0x18006cfd9  mov     r9d, edi; char *
0x18006cfdc  lea     r8, aOnecoreBaseSer_24; "onecore\\base\\servicing\\arbiter\\arbi"...
0x18006cfe3  mov     edx, 7A5h; void *
0x18006cfe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cfed  nop
0x18006cfee  mov     rcx, [rsp+0E8h+hLibModule]; hLibModule
0x18006cff6  test    rcx, rcx
0x18006cff9  jz      short loc_18006D035
0x18006cffb  call    cs:__imp_FreeLibrary
0x18006d002  nop     dword ptr [rax+rax+00h]
0x18006d007  test    eax, eax
0x18006d009  jnz     short loc_18006D022
0x18006d00b  call    cs:__imp_GetLastError
0x18006d012  nop     dword ptr [rax+rax+00h]
0x18006d017  mov     ebx, 7
0x18006d01c  mov     ecx, ebx
0x18006d01e  int     29h; Win8: RtlFailFast(ecx)
0x18006d020  jmp     short loc_18006D027
0x18006d022  mov     ebx, 7
0x18006d027  mov     [rsp+0E8h+hLibModule], 0
0x18006d033  jmp     short loc_18006D03A
0x18006d035  mov     ebx, 7
0x18006d03a  mov     rcx, [rsp+0E8h+phModule]; hLibModule
0x18006d042  test    rcx, rcx
0x18006d045  jz      short loc_18006D074
0x18006d047  call    cs:__imp_FreeLibrary
0x18006d04e  nop     dword ptr [rax+rax+00h]
0x18006d053  test    eax, eax
0x18006d055  jnz     short loc_18006D068
0x18006d057  call    cs:__imp_GetLastError
0x18006d05e  nop     dword ptr [rax+rax+00h]
0x18006d063  mov     rcx, rbx
0x18006d066  int     29h; Win8: RtlFailFast(ecx)
0x18006d068  mov     [rsp+0E8h+phModule], 0
0x18006d074  mov     rcx, [rsp+0E8h+Handle]; Handle
0x18006d07c  test    rcx, rcx
0x18006d07f  jz      short loc_18006D096
0x18006d081  call    cs:__imp_NtClose
0x18006d088  nop     dword ptr [rax+rax+00h]
0x18006d08d  test    eax, eax
0x18006d08f  jns     short loc_18006D096
0x18006d091  mov     rcx, rbx
0x18006d094  int     29h; Win8: RtlFailFast(ecx)
0x18006d096  mov     eax, edi
0x18006d098  jmp     loc_18006D478
0x18006d09d  mov     rax, [rsp+0E8h+Handle]
0x18006d0a5  xor     edi, edi
0x18006d0a7  test    rax, rax
0x18006d0aa  jnz     short loc_18006D0B5
0x18006d0ac  lea     ebx, [rax+7]
0x18006d0af  mov     ecx, ebx
0x18006d0b1  int     29h; Win8: RtlFailFast(ecx)
0x18006d0b3  jmp     short loc_18006D0BA
0x18006d0b5  mov     ebx, 7
0x18006d0ba  mov     edx, 927C0h; dwMilliseconds
0x18006d0bf  mov     rcx, rax; hHandle
0x18006d0c2  call    cs:__imp_WaitForSingleObject
0x18006d0c9  nop     dword ptr [rax+rax+00h]
0x18006d0ce  test    eax, eax
0x18006d0d0  jz      loc_18006D263
0x18006d0d6  cmp     eax, 80h
0x18006d0db  jz      short loc_18006D125
0x18006d0dd  cmp     eax, 102h
0x18006d0e2  jz      short loc_18006D11E
0x18006d0e4  cmp     eax, 0FFFFFFFFh
0x18006d0e7  jz      short loc_18006D0F0
0x18006d0e9  mov     edi, 80004005h
0x18006d0ee  jmp     short loc_18006D132
0x18006d0f0  call    cs:__imp_GetLastError
0x18006d0f7  nop     dword ptr [rax+rax+00h]
0x18006d0fc  mov     edi, eax
0x18006d0fe  test    eax, eax
0x18006d100  jle     short loc_18006D10B
0x18006d102  movzx   edi, ax
0x18006d105  or      edi, 80070000h
0x18006d10b  cmp     edi, 800705B4h
0x18006d111  jz      short loc_18006D11E
0x18006d113  test    edi, edi
0x18006d115  js      short loc_18006D132
0x18006d117  xor     edi, edi
0x18006d119  jmp     loc_18006D27E
0x18006d11e  mov     edi, 800F8011h
0x18006d123  jmp     short loc_18006D132
0x18006d125  mov     r14b, 1
0x18006d128  mov     [rsp+0E8h+var_70], r14b
0x18006d12d  mov     edi, 8000FFFFh
0x18006d132  mov     dword ptr [rsp+0E8h+var_58], edi
0x18006d139  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006d140  test    rcx, rcx
0x18006d143  jz      short loc_18006D18A
0x18006d145  lea     r9, aFailedToAcquir_3; "Failed to acquire the mutex"
0x18006d14c  mov     esi, 3
0x18006d151  mov     r8d, esi
0x18006d154  xor     edx, edx
0x18006d156  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18006d15b  lea     rax, [rsp+0E8h+var_58]
0x18006d163  mov     qword ptr [rsp+0E8h+var_88], rax
0x18006d168  lea     rax, [rsp+0E8h+var_88]
0x18006d16d  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x18006d172  lea     r9, asc_1801CAFB4; ": {}"
0x18006d179  mov     r8d, esi
0x18006d17c  mov     dl, 1
0x18006d17e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006d185  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18006d18a  mov     rcx, [rsp+0E8h]; this
0x18006d192  mov     r9d, edi; char *
0x18006d195  lea     r8, aOnecoreBaseSer_24; "onecore\\base\\servicing\\arbiter\\arbi"...
0x18006d19c  mov     edx, 7B2h; void *
0x18006d1a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d1a6  nop
0x18006d1a7  mov     rcx, [rsp+0E8h+hLibModule]; hLibModule
0x18006d1af  test    rcx, rcx
0x18006d1b2  jz      short loc_18006D1E1
0x18006d1b4  call    cs:__imp_FreeLibrary
0x18006d1bb  nop     dword ptr [rax+rax+00h]
0x18006d1c0  test    eax, eax
0x18006d1c2  jnz     short loc_18006D1D5
0x18006d1c4  call    cs:__imp_GetLastError
0x18006d1cb  nop     dword ptr [rax+rax+00h]
0x18006d1d0  mov     rcx, rbx
0x18006d1d3  int     29h; Win8: RtlFailFast(ecx)
0x18006d1d5  mov     [rsp+0E8h+hLibModule], 0
0x18006d1e1  mov     rcx, [rsp+0E8h+phModule]; hLibModule
0x18006d1e9  test    rcx, rcx
0x18006d1ec  jz      short loc_18006D21B
0x18006d1ee  call    cs:__imp_FreeLibrary
0x18006d1f5  nop     dword ptr [rax+rax+00h]
0x18006d1fa  test    eax, eax
0x18006d1fc  jnz     short loc_18006D20F
0x18006d1fe  call    cs:__imp_GetLastError
0x18006d205  nop     dword ptr [rax+rax+00h]
0x18006d20a  mov     rcx, rbx
0x18006d20d  int     29h; Win8: RtlFailFast(ecx)
0x18006d20f  mov     [rsp+0E8h+phModule], 0
0x18006d21b  test    r14b, r14b
0x18006d21e  jz      short loc_18006D23A
0x18006d220  mov     rcx, [rsp+0E8h+Handle]; hMutex
0x18006d228  test    rcx, rcx
0x18006d22b  jz      short loc_18006D23A
0x18006d22d  call    cs:__imp_ReleaseMutex
0x18006d234  nop     dword ptr [rax+rax+00h]
0x18006d239  nop
0x18006d23a  mov     rcx, [rsp+0E8h+Handle]; Handle
0x18006d242  test    rcx, rcx
0x18006d245  jz      short loc_18006D25C
0x18006d247  call    cs:__imp_NtClose
0x18006d24e  nop     dword ptr [rax+rax+00h]
0x18006d253  test    eax, eax
0x18006d255  jns     short loc_18006D25C
0x18006d257  mov     rcx, rbx
0x18006d25a  int     29h; Win8: RtlFailFast(ecx)
0x18006d25c  mov     eax, edi
0x18006d25e  jmp     loc_18006D478
0x18006d263  mov     r14b, 1
0x18006d266  mov     [rsp+0E8h+var_70], r14b
0x18006d26b  jmp     short loc_18006D27E
0x18006d26d  lea     rcx, aArbiterInvoked_0; "Arbiter invoked from servicing stack; s"...
0x18006d274  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18006d279  mov     ebx, 7
0x18006d27e  mov     rcx, [rsp+0E8h+hLibModule]; hLibModule
0x18006d286  test    rcx, rcx
0x18006d289  jz      short loc_18006D2B4
0x18006d28b  call    cs:__imp_FreeLibrary
0x18006d292  nop     dword ptr [rax+rax+00h]
0x18006d297  test    eax, eax
0x18006d299  jnz     short loc_18006D2AC
0x18006d29b  call    cs:__imp_GetLastError
0x18006d2a2  nop     dword ptr [rax+rax+00h]
0x18006d2a7  mov     rcx, rbx
0x18006d2aa  int     29h; Win8: RtlFailFast(ecx)
0x18006d2ac  mov     [rsp+0E8h+hLibModule], rdi
0x18006d2b4  mov     rcx, [rsp+0E8h+phModule]; hLibModule
0x18006d2bc  test    rcx, rcx
0x18006d2bf  jz      short loc_18006D2E2
0x18006d2c1  call    cs:__imp_FreeLibrary
0x18006d2c8  nop     dword ptr [rax+rax+00h]
0x18006d2cd  test    eax, eax
0x18006d2cf  jnz     short loc_18006D2E2
0x18006d2d1  call    cs:__imp_GetLastError
0x18006d2d8  nop     dword ptr [rax+rax+00h]
0x18006d2dd  mov     rcx, rbx
0x18006d2e0  int     29h; Win8: RtlFailFast(ecx)
0x18006d2e2  mov     [rsp+0E8h+var_90], rsi
0x18006d2e7  mov     rax, qword ptr [rsp+0E8h+var_88]
0x18006d2ec  mov     [rsp+0E8h+var_98], rax
0x18006d2f1  mov     rax, [rsp+0E8h+var_58]
0x18006d2f9  mov     [rsp+0E8h+var_A0], rax
0x18006d2fe  mov     [rsp+0E8h+var_A8], rdi
0x18006d303  mov     [rsp+0E8h+var_B0], r15
0x18006d308  mov     [rsp+0E8h+var_B8], rdi
0x18006d30d  mov     [rsp+0E8h+var_C0], rdi
0x18006d312  mov     rax, qword ptr [rsp+0E8h+var_80]
0x18006d317  mov     qword ptr [rsp+0E8h+var_C8], rax
0x18006d31c  xor     r9d, r9d
0x18006d31f  mov     r8, r13
0x18006d322  mov     edx, r12d
0x18006d325  xor     ecx, ecx
0x18006d327  call    CreateActionListInternal
0x18006d32c  mov     edi, eax
0x18006d32e  mov     [rsp+0E8h+var_40], eax
0x18006d335  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006d33c  test    rcx, rcx
0x18006d33f  jz      short loc_18006D371
0x18006d341  lea     rax, [rsp+0E8h+var_40]
0x18006d349  mov     qword ptr [rsp+0E8h+var_C8], rax
0x18006d34e  lea     r9, aArbiterCreatea_0; "arbiter: --- CreateActionlist end with "...
  ... truncated ...
```
