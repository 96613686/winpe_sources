# Microsoft::Diagnostics::Utils::Os::DumpProcess(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,unsigned __int64)

- ea: `0x18026dbd0`
- end: `0x18026e1f6`
- name: `?DumpProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K@Z`
- size: `1574`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *, unsigned int, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801e4348`
- `0x18026da30`

## callees

- `0x1800202a4`
- `0x18002b318`
- `0x18002b7c0`
- `0x18002b9c0`
- `0x18002df00`
- `0x180064e6c`
- `0x180064e8c`
- `0x1800bc658`
- `0x1800e65d4`
- `0x1801b0f48`
- `0x180202f10`
- `0x18020aac0`
- `0x18026dbd0`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18026e0cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18026e0cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18026deac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18026deac`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18026deb5`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18026deb5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18026dc50`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18026dc50`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18026dee4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18026dee4`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18026dd3f`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18026dd3f`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18026dcca`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18026dcca`

## string_xrefs

- `0x18026e051`: `dbghelp.dll`
- `0x18026e0c6`: `MiniDumpWriteDump`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::DumpProcess(
        unsigned int a1,
        _QWORD *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v8; // rax
  HANDLE v9; // rbx
  const char *v10; // r9
  unsigned int LastError; // ebx
  const char *v13; // r9
  unsigned int v14; // ebx
  LPWSTR *v15; // rcx
  unsigned int SystemWow64Directory2W; // eax
  const char *v17; // r9
  unsigned int v18; // ebx
  __int64 v19; // rdx
  LPWSTR *v20; // rax
  int v21; // eax
  unsigned int v22; // ebx
  HANDLE CurrentProcess; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  WCHAR *v27; // rcx
  UINT SystemDirectoryW; // eax
  const char *v29; // r9
  unsigned int v30; // ebx
  __int64 v31; // rdx
  LPWSTR *v32; // rax
  int v33; // eax
  const char *v34; // r9
  unsigned int v35; // ebx
  FARPROC ProcAddress; // rax
  const char *v37; // r9
  unsigned int v38; // ebx
  const char *v39; // r9
  unsigned int v40; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-D8h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-D8h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-D8h]
  __int64 v44; // [rsp+40h] [rbp-B8h] BYREF
  _WORD v45[2]; // [rsp+48h] [rbp-B0h] BYREF
  int v46; // [rsp+4Ch] [rbp-ACh] BYREF
  HMODULE hModule; // [rsp+50h] [rbp-A8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-A0h] BYREF
  _QWORD v49[2]; // [rsp+70h] [rbp-88h] BYREF
  LPWSTR lpBuffer[2]; // [rsp+80h] [rbp-78h] BYREF
  UINT uSize[2]; // [rsp+90h] [rbp-68h]
  unsigned __int64 v52; // [rsp+98h] [rbp-60h]
  _QWORD v53[4]; // [rsp+A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  v8 = std::wstring::wstring(v53, a4);
  if ( *(_QWORD *)(v8 + 24) > 7u )
    v8 = *(_QWORD *)v8;
  v9 = CreateFileW((LPCWSTR)v8, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80u, 0);
  v44 = (__int64)v9;
  std::wstring::_Tidy_deallocate(v53);
  if ( (((unsigned __int64)v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4B2,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                  v10);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
    return LastError;
  }
  std::wstring::wstring(lpBuffer, 260, 0);
  v45[0] = 0;
  if ( !(unsigned int)IsWow64Process2(*a2, v45, 0) )
  {
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x4BE,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
            v13);
    std::wstring::_Tidy_deallocate(lpBuffer);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
    return v14;
  }
  if ( v45[0] )
  {
    v15 = lpBuffer;
    if ( v52 > 7 )
      v15 = (LPWSTR *)lpBuffer[0];
    SystemWow64Directory2W = GetSystemWow64Directory2W(v15, uSize[0]);
    if ( !SystemWow64Directory2W )
    {
      v18 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x4C8,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              v17);
      std::wstring::_Tidy_deallocate(lpBuffer);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
      return v18;
    }
    v19 = SystemWow64Directory2W;
    if ( (unsigned __int64)SystemWow64Directory2W >= *(_QWORD *)uSize )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C9,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
        (const char *)0x8007007ALL,
        dwCreationDisposition);
      std::wstring::_Tidy_deallocate(lpBuffer);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
      return 2147942522LL;
    }
    v20 = lpBuffer;
    if ( v52 > 7 )
      v20 = (LPWSTR *)lpBuffer[0];
    if ( !*(_WORD *)v20 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4CA,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
        (const char *)0x800700A1LL,
        dwCreationDisposition);
      std::wstring::_Tidy_deallocate(lpBuffer);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
      return 2147942561LL;
    }
    std::wstring::resize(lpBuffer, v19);
    v21 = Microsoft::Diagnostics::Utils::Os::LaunchDtDumpOutOfProc((LPCWSTR)lpBuffer, a1, a2, a3, &v44, a5);
    v22 = v21;
    if ( v21 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D2,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
        (const char *)(unsigned int)v21,
        dwCreationDispositiona);
    goto LABEL_20;
  }
  CurrentProcess = GetCurrentProcess();
  if ( a1 == GetProcessId(CurrentProcess) )
  {
    v27 = (WCHAR *)lpBuffer;
    if ( v52 > 7 )
      v27 = lpBuffer[0];
    SystemDirectoryW = GetSystemDirectoryW(v27, uSize[0]);
    if ( SystemDirectoryW )
    {
      v31 = SystemDirectoryW;
      if ( (unsigned __int64)SystemDirectoryW < *(_QWORD *)uSize )
      {
        v32 = lpBuffer;
        if ( v52 > 7 )
          v32 = (LPWSTR *)lpBuffer[0];
        if ( *(_WORD *)v32 )
        {
          std::wstring::resize(lpBuffer, v31);
          v33 = Microsoft::Diagnostics::Utils::Os::LaunchDtDumpOutOfProc((LPCWSTR)lpBuffer, a1, a2, a3, &v44, a5);
          v22 = v33;
          if ( v33 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4E7,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              (const char *)(unsigned int)v33,
              dwCreationDispositionb);
LABEL_20:
          std::wstring::_Tidy_deallocate(lpBuffer);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
          return v22;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4DF,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
          (const char *)0x800700A1LL,
          dwCreationDisposition);
        std::wstring::_Tidy_deallocate(lpBuffer);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
        return 2147942561LL;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4DE,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
          (const char *)0x8007007ALL,
          dwCreationDisposition);
        std::wstring::_Tidy_deallocate(lpBuffer);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
        return 2147942522LL;
      }
    }
    else
    {
      v30 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x4DD,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              v29);
      std::wstring::_Tidy_deallocate(lpBuffer);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
      return v30;
    }
  }
  else
  {
    v49[0] = L"dbghelp.dll";
    v49[1] = std::_WChar_traits<wchar_t>::length(L"dbghelp.dll", v24, v25, v26);
    Microsoft::Diagnostics::Utils::Os::LoadSystemLibrary(&hModule, v49);
    if ( hModule )
    {
      ProcAddress = GetProcAddress(hModule, "MiniDumpWriteDump");
      if ( ProcAddress )
      {
        v46 = 0;
        v53[0] = Microsoft::Diagnostics::Utils::Os::MinidumpCallback;
        v53[1] = &v46;
        if ( ((unsigned int (__fastcall *)(_QWORD, _QWORD, HANDLE, _QWORD, _QWORD, _QWORD, _QWORD *))ProcAddress)(
               *a2,
               a1,
               v9,
               a3,
               0,
               0,
               v53) )
        {
          Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&hModule);
          std::wstring::_Tidy_deallocate(lpBuffer);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
          return 0;
        }
        else
        {
          v40 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x508,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                  v39);
          Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&hModule);
          std::wstring::_Tidy_deallocate(lpBuffer);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
          return v40;
        }
      }
      else
      {
        v38 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x4F3,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                v37);
        Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&hModule);
        std::wstring::_Tidy_deallocate(lpBuffer);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
        return v38;
      }
    }
    else
    {
      v35 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x4EC,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              v34);
      Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&hModule);
      std::wstring::_Tidy_deallocate(lpBuffer);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
      return v35;
    }
  }
}

```

## disassembly

```asm
0x18026dbd0  mov     r11, rsp
0x18026dbd3  push    rbx
0x18026dbd4  push    rsi
0x18026dbd5  push    rdi
0x18026dbd6  push    r14
0x18026dbd8  push    r15
0x18026dbda  sub     rsp, 0D0h
0x18026dbe1  mov     rax, cs:__security_cookie
0x18026dbe8  xor     rax, rsp
0x18026dbeb  mov     [rsp+0F8h+var_38], rax
0x18026dbf3  mov     r14d, r8d
0x18026dbf6  mov     rsi, rdx
0x18026dbf9  mov     edi, ecx
0x18026dbfb  mov     qword ptr [rsp+0F8h+SecurityAttributes.nLength], 18h
0x18026dc04  xor     r15d, r15d
0x18026dc07  mov     [rsp+0F8h+SecurityAttributes.lpSecurityDescriptor], r15
0x18026dc0c  mov     qword ptr [rsp+0F8h+SecurityAttributes.bInheritHandle], 1
0x18026dc15  mov     rdx, r9
0x18026dc18  lea     rcx, [r11-58h]
0x18026dc1c  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18026dc21  cmp     qword ptr [rax+18h], 7
0x18026dc26  jbe     short loc_18026DC2B
0x18026dc28  mov     rax, [rax]
0x18026dc2b  mov     [rsp+0F8h+hTemplateFile], r15; hTemplateFile
0x18026dc30  mov     [rsp+0F8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18026dc38  mov     [rsp+0F8h+dwCreationDisposition], 2; int
0x18026dc40  lea     r9, [rsp+0F8h+SecurityAttributes]; lpSecurityAttributes
0x18026dc45  xor     r8d, r8d; dwShareMode
0x18026dc48  mov     edx, 40000000h; dwDesiredAccess
0x18026dc4d  mov     rcx, rax; lpFileName
0x18026dc50  call    cs:__imp_CreateFileW
0x18026dc56  mov     rbx, rax
0x18026dc59  mov     [rsp+0F8h+var_B8], rax
0x18026dc5e  lea     rcx, [rsp+0F8h+var_58]
0x18026dc66  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026dc6b  lea     rax, [rbx+1]
0x18026dc6f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18026dc75  jnz     short loc_18026DCA3
0x18026dc77  mov     rcx, [rsp+0F8h]; this
0x18026dc7f  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026dc86  mov     edx, 4B2h; void *
0x18026dc8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18026dc90  mov     ebx, eax
0x18026dc92  lea     rcx, [rsp+0F8h+var_B8]
0x18026dc97  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026dc9c  mov     eax, ebx
0x18026dc9e  jmp     loc_18026E1D6
0x18026dca3  xor     r8d, r8d
0x18026dca6  mov     edx, 104h
0x18026dcab  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026dcb3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18026dcb8  nop
0x18026dcb9  mov     [rsp+0F8h+var_B0], r15w
0x18026dcbf  xor     r8d, r8d
0x18026dcc2  lea     rdx, [rsp+0F8h+var_B0]
0x18026dcc7  mov     rcx, [rsi]
0x18026dcca  call    cs:__imp_IsWow64Process2
0x18026dcd0  test    eax, eax
0x18026dcd2  jnz     short loc_18026DD0E
0x18026dcd4  mov     rcx, [rsp+0F8h]; this
0x18026dcdc  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026dce3  mov     edx, 4BEh; void *
0x18026dce8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18026dced  mov     ebx, eax
0x18026dcef  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026dcf7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026dcfc  nop
0x18026dcfd  lea     rcx, [rsp+0F8h+var_B8]
0x18026dd02  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026dd07  mov     eax, ebx
0x18026dd09  jmp     loc_18026E1D6
0x18026dd0e  movzx   r8d, [rsp+0F8h+var_B0]
0x18026dd14  test    r8w, r8w
0x18026dd18  jz      loc_18026DEAC
0x18026dd1e  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026dd26  cmp     [rsp+0F8h+var_60], 7
0x18026dd2f  cmova   rcx, [rsp+0F8h+lpBuffer]
0x18026dd38  mov     edx, [rsp+0F8h+uSize]
0x18026dd3f  call    cs:__imp_GetSystemWow64Directory2W
0x18026dd45  test    eax, eax
0x18026dd47  jnz     short loc_18026DD83
0x18026dd49  mov     rcx, [rsp+0F8h]; this
0x18026dd51  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026dd58  mov     edx, 4C8h; void *
0x18026dd5d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18026dd62  mov     ebx, eax
0x18026dd64  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026dd6c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026dd71  nop
0x18026dd72  lea     rcx, [rsp+0F8h+var_B8]
0x18026dd77  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026dd7c  mov     eax, ebx
0x18026dd7e  jmp     loc_18026E1D6
0x18026dd83  mov     edx, eax
0x18026dd85  cmp     rdx, qword ptr [rsp+0F8h+uSize]
0x18026dd8d  jb      short loc_18026DDD0
0x18026dd8f  mov     rcx, [rsp+0F8h]; this
0x18026dd97  mov     ebx, 8007007Ah
0x18026dd9c  mov     r9d, ebx; char *
0x18026dd9f  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026dda6  mov     edx, 4C9h; void *
0x18026ddab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ddb0  nop
0x18026ddb1  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026ddb9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026ddbe  nop
0x18026ddbf  lea     rcx, [rsp+0F8h+var_B8]
0x18026ddc4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026ddc9  mov     eax, ebx
0x18026ddcb  jmp     loc_18026E1D6
0x18026ddd0  lea     rax, [rsp+0F8h+lpBuffer]
0x18026ddd8  cmp     [rsp+0F8h+var_60], 7
0x18026dde1  cmova   rax, [rsp+0F8h+lpBuffer]
0x18026ddea  cmp     [rax], r15w
0x18026ddee  jnz     short loc_18026DE31
0x18026ddf0  mov     rcx, [rsp+0F8h]; this
0x18026ddf8  mov     ebx, 800700A1h
0x18026ddfd  mov     r9d, ebx; char *
0x18026de00  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026de07  mov     edx, 4CAh; void *
0x18026de0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026de11  nop
0x18026de12  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026de1a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026de1f  nop
0x18026de20  lea     rcx, [rsp+0F8h+var_B8]
0x18026de25  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026de2a  mov     eax, ebx
0x18026de2c  jmp     loc_18026E1D6
0x18026de31  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026de39  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18026de3e  mov     rax, qword ptr [rsp+0F8h+arg_20]
0x18026de46  mov     qword ptr [rsp+0F8h+dwFlagsAndAttributes], rax; unsigned int
0x18026de4b  lea     rax, [rsp+0F8h+var_B8]
0x18026de50  mov     qword ptr [rsp+0F8h+dwCreationDisposition], rax; int
0x18026de55  mov     r9d, r14d
0x18026de58  mov     r8, rsi
0x18026de5b  mov     edx, edi
0x18026de5d  lea     rcx, [rsp+0F8h+lpBuffer]; lpSrc
0x18026de65  call    ?LaunchDtDumpOutOfProc@Os@Utils@Diagnostics@Microsoft@@CAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@8@_K@Z; Microsoft::Diagnostics::Utils::Os::LaunchDtDumpOutOfProc(std::wstring &,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,unsigned __int64)
0x18026de6a  mov     ebx, eax
0x18026de6c  test    eax, eax
0x18026de6e  jns     short loc_18026DE8D
0x18026de70  mov     rcx, [rsp+0F8h]; this
0x18026de78  mov     r9d, eax; char *
0x18026de7b  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026de82  mov     edx, 4D2h; void *
0x18026de87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026de8c  nop
0x18026de8d  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026de95  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026de9a  nop
0x18026de9b  lea     rcx, [rsp+0F8h+var_B8]
0x18026dea0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026dea5  mov     eax, ebx
0x18026dea7  jmp     loc_18026E1D6
0x18026deac  call    cs:__imp_GetCurrentProcess
0x18026deb2  mov     rcx, rax; Process
0x18026deb5  call    cs:__imp_GetProcessId
0x18026debb  cmp     edi, eax
0x18026debd  jnz     loc_18026E051
0x18026dec3  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026decb  cmp     [rsp+0F8h+var_60], 7
0x18026ded4  cmova   rcx, [rsp+0F8h+lpBuffer]; lpBuffer
0x18026dedd  mov     edx, [rsp+0F8h+uSize]; uSize
0x18026dee4  call    cs:__imp_GetSystemDirectoryW
0x18026deea  test    eax, eax
0x18026deec  jnz     short loc_18026DF28
0x18026deee  mov     rcx, [rsp+0F8h]; this
0x18026def6  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026defd  mov     edx, 4DDh; void *
0x18026df02  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18026df07  mov     ebx, eax
0x18026df09  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026df11  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026df16  nop
0x18026df17  lea     rcx, [rsp+0F8h+var_B8]
0x18026df1c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026df21  mov     eax, ebx
0x18026df23  jmp     loc_18026E1D6
0x18026df28  mov     edx, eax
0x18026df2a  cmp     rdx, qword ptr [rsp+0F8h+uSize]
0x18026df32  jb      short loc_18026DF75
0x18026df34  mov     rcx, [rsp+0F8h]; this
0x18026df3c  mov     ebx, 8007007Ah
0x18026df41  mov     r9d, ebx; char *
0x18026df44  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026df4b  mov     edx, 4DEh; void *
0x18026df50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026df55  nop
0x18026df56  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026df5e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026df63  nop
0x18026df64  lea     rcx, [rsp+0F8h+var_B8]
0x18026df69  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026df6e  mov     eax, ebx
0x18026df70  jmp     loc_18026E1D6
0x18026df75  lea     rax, [rsp+0F8h+lpBuffer]
0x18026df7d  cmp     [rsp+0F8h+var_60], 7
0x18026df86  cmova   rax, [rsp+0F8h+lpBuffer]
0x18026df8f  cmp     [rax], r15w
0x18026df93  jnz     short loc_18026DFD6
0x18026df95  mov     rcx, [rsp+0F8h]; this
0x18026df9d  mov     ebx, 800700A1h
0x18026dfa2  mov     r9d, ebx; char *
0x18026dfa5  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026dfac  mov     edx, 4DFh; void *
0x18026dfb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026dfb6  nop
0x18026dfb7  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026dfbf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026dfc4  nop
0x18026dfc5  lea     rcx, [rsp+0F8h+var_B8]
0x18026dfca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026dfcf  mov     eax, ebx
0x18026dfd1  jmp     loc_18026E1D6
0x18026dfd6  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026dfde  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18026dfe3  mov     rax, qword ptr [rsp+0F8h+arg_20]
0x18026dfeb  mov     qword ptr [rsp+0F8h+dwFlagsAndAttributes], rax; unsigned int
0x18026dff0  lea     rax, [rsp+0F8h+var_B8]
0x18026dff5  mov     qword ptr [rsp+0F8h+dwCreationDisposition], rax; int
0x18026dffa  mov     r9d, r14d
0x18026dffd  mov     r8, rsi
0x18026e000  mov     edx, edi
0x18026e002  lea     rcx, [rsp+0F8h+lpBuffer]; lpSrc
0x18026e00a  call    ?LaunchDtDumpOutOfProc@Os@Utils@Diagnostics@Microsoft@@CAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@8@_K@Z; Microsoft::Diagnostics::Utils::Os::LaunchDtDumpOutOfProc(std::wstring &,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,unsigned __int64)
0x18026e00f  mov     ebx, eax
0x18026e011  test    eax, eax
0x18026e013  jns     short loc_18026E032
0x18026e015  mov     rcx, [rsp+0F8h]; this
0x18026e01d  mov     r9d, eax; char *
0x18026e020  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026e027  mov     edx, 4E7h; void *
0x18026e02c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e031  nop
0x18026e032  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026e03a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026e03f  nop
0x18026e040  lea     rcx, [rsp+0F8h+var_B8]
0x18026e045  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026e04a  mov     eax, ebx
0x18026e04c  jmp     loc_18026E1D6
0x18026e051  lea     rcx, aDbghelpDll; "dbghelp.dll"
0x18026e058  mov     [rsp+0F8h+var_88], rcx
0x18026e05d  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18026e062  mov     [rsp+0F8h+var_80], rax
0x18026e067  lea     rdx, [rsp+0F8h+var_88]
0x18026e06c  lea     rcx, [rsp+0F8h+hModule]
0x18026e071  call    ?LoadSystemLibrary@Os@Utils@Diagnostics@Microsoft@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::Os::LoadSystemLibrary(std::wstring_view)
0x18026e076  nop
0x18026e077  mov     rcx, [rsp+0F8h+hModule]; hModule
0x18026e07c  test    rcx, rcx
0x18026e07f  jnz     short loc_18026E0C6
0x18026e081  mov     rcx, [rsp+0F8h]; this
0x18026e089  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026e090  mov     edx, 4ECh; void *
0x18026e095  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18026e09a  mov     ebx, eax
0x18026e09c  lea     rcx, [rsp+0F8h+hModule]
0x18026e0a1  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18026e0a6  nop
0x18026e0a7  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026e0af  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026e0b4  nop
0x18026e0b5  lea     rcx, [rsp+0F8h+var_B8]
0x18026e0ba  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026e0bf  mov     eax, ebx
0x18026e0c1  jmp     loc_18026E1D6
0x18026e0c6  lea     rdx, aMinidumpwrited; "MiniDumpWriteDump"
0x18026e0cd  call    cs:__imp_GetProcAddress
0x18026e0d3  test    rax, rax
0x18026e0d6  jnz     short loc_18026E11D
0x18026e0d8  mov     rcx, [rsp+0F8h]; this
0x18026e0e0  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18026e0e7  mov     edx, 4F3h; void *
0x18026e0ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18026e0f1  mov     ebx, eax
0x18026e0f3  lea     rcx, [rsp+0F8h+hModule]
0x18026e0f8  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18026e0fd  nop
0x18026e0fe  lea     rcx, [rsp+0F8h+lpBuffer]
0x18026e106  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026e10b  nop
0x18026e10c  lea     rcx, [rsp+0F8h+var_B8]
0x18026e111  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18026e116  mov     eax, ebx
0x18026e118  jmp     loc_18026E1D6
0x18026e11d  mov     [rsp+0F8h+var_AC], r15d
0x18026e122  lea     rcx, ?MinidumpCallback@Os@Utils@Diagnostics@Microsoft@@CAHPEAXPEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@@Z; Microsoft::Diagnostics::Utils::Os::MinidumpCallback(void *,_MINIDUMP_CALLBACK_INPUT *,_MINIDUMP_CALLBACK_OUTPUT *)
0x18026e129  mov     [rsp+0F8h+var_58], rcx
0x18026e131  lea     rcx, [rsp+0F8h+var_AC]
0x18026e136  mov     [rsp+0F8h+var_50], rcx
0x18026e13e  lea     rcx, [rsp+0F8h+var_58]
0x18026e146  mov     [rsp+0F8h+hTemplateFile], rcx
0x18026e14b  mov     qword ptr [rsp+0F8h+dwFlagsAndAttributes], r15
0x18026e150  mov     qword ptr [rsp+0F8h+dwCreationDisposition], r15
0x18026e155  mov     r9d, r14d
0x18026e158  mov     r8, rbx
0x18026e15b  mov     edx, edi
  ... truncated ...
```
