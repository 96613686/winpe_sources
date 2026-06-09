# wWinMain

- ea: `0x14000a678`
- end: `0x14000ab15`
- name: `wWinMain`
- size: `1181`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140001f70`

## callees

- `0x140002120`
- `0x1400023ec`
- `0x140002c58`
- `0x1400062ac`
- `0x140006614`
- `0x140006dd8`
- `0x140006ed8`
- `0x140007188`
- `0x140007ad8`
- `0x140007ec8`
- `0x1400087e4`
- `0x140008a04`
- `0x1400095d8`
- `0x14000a140`
- `0x14000a188`
- `0x14000a678`
- `0x14000ad20`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000a98e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000a98e`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14000a6b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14000a6b2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14000a976`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14000a976`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14000a9ab`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14000a9ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aa01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aa18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aa01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aa18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a8ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a8ab`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000a6b8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000a6b8`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x14000a6cb`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x14000a6cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000aa4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000aa4d`

## string_xrefs

- `0x14000aa8a`: `onecore\enduser\windowsupdate\undocked\stubexes\main.cpp`
- `0x14000aabf`: `onecore\enduser\windowsupdate\undocked\stubexes\main.cpp`
- `0x14000aad8`: `onecore\enduser\windowsupdate\undocked\stubexes\main.cpp`
- `0x14000aaf1`: `onecore\enduser\windowsupdate\undocked\stubexes\main.cpp`
- `0x14000aaa3`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  const WCHAR *CommandLineW; // rax
  LPWSTR *v5; // rbx
  const char *v6; // r9
  unsigned __int64 v7; // r8
  __int64 v8; // r14
  __int64 v9; // r9
  int v10; // r15d
  LPWSTR *v11; // rcx
  unsigned __int64 v12; // rdx
  LPWSTR v13; // r10
  __int64 v14; // rsi
  LPWSTR *v15; // rdi
  uus::Session *v16; // rax
  __int64 v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  void *v21; // rdi
  WCHAR *v22; // rdx
  const WCHAR *v23; // rcx
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  LPWSTR *v27; // rax
  LPCWSTR *v28; // rax
  DWORD v29; // edi
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  char v36; // [rsp+50h] [rbp-B0h] BYREF
  char v37; // [rsp+51h] [rbp-AFh] BYREF
  _BYTE v38[2]; // [rsp+52h] [rbp-AEh] BYREF
  int pNumArgs; // [rsp+54h] [rbp-ACh] BYREF
  DWORD ExitCode; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v47; // [rsp+110h] [rbp+10h]
  unsigned __int64 v48; // [rsp+118h] [rbp+18h]
  LPCWSTR lpApplicationName[3]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v50; // [rsp+138h] [rbp+38h]
  _BYTE v51[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v52[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v53[32]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v38[0] = 0;
  SetErrorMode(0x8003u);
  CommandLineW = GetCommandLineW();
  pNumArgs = 0;
  v5 = CommandLineToArgvW(CommandLineW, &pNumArgs);
  if ( !v5 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\undocked\\stubexes\\main.cpp",
      v6);
  v47 = 0;
  v7 = 7;
  v8 = -1;
  v48 = 7;
  v9 = 0;
  v10 = 1;
  *(_OWORD *)lpCommandLine = 0;
  LOWORD(lpCommandLine[0]) = 0;
  if ( pNumArgs > 1 )
  {
    while ( 1 )
    {
      if ( v9 )
      {
        v11 = lpCommandLine;
        if ( v7 == v9 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
            lpCommandLine,
            1);
        }
        else
        {
          v47 = v9 + 1;
          if ( v7 > 7 )
            v11 = (LPWSTR *)lpCommandLine[0];
          *((_WORD *)v11 + v9) = asc_14000DDDC[0];
          *((_WORD *)v11 + v9 + 1) = 0;
        }
        v9 = v47;
        v7 = v48;
      }
      v12 = -1;
      v13 = v5[v10];
      do
        ++v12;
      while ( v13[v12] );
      if ( v12 > v7 - v9 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          lpCommandLine,
          v12);
      }
      else
      {
        v14 = v12 + v9;
        v47 = v12 + v9;
        v15 = lpCommandLine;
        if ( v7 > 7 )
          v15 = (LPWSTR *)lpCommandLine[0];
        memmove_0((char *)v15 + 2 * v9, v13, 2 * v12);
        *((_WORD *)v15 + v14) = 0;
      }
      if ( ++v10 >= pNumArgs )
        break;
      v7 = v48;
      v9 = v47;
    }
  }
  v37 = 1;
  v16 = (uus::Session *)operator new(0x10u);
  v17 = uus::Session::Session(v16, L"UIEOrchestrator");
  v42 = 19;
  v41 = L"UIEOrchestrator.exe";
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v53);
  v18 = *(_QWORD *)(v17 + 8);
  if ( v18 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 40LL))(v18, 1);
    do
      ++v8;
    while ( *(_WORD *)(v19 + 2 * v8) );
    v41 = (const wchar_t *)v19;
    v42 = v8;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v51);
  }
  else
  {
    pv = 0;
    v20 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            0,
            &pv);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x250,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
        (const char *)(unsigned int)v20,
        bInheritHandles);
    v21 = pv;
    do
      ++v8;
    while ( *((_WORD *)pv + v8) );
    v41 = (const wchar_t *)pv;
    v42 = v8;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v52);
    if ( v21 )
      CoTaskMemFree(v21);
    uus::Utility::GetGuestOrNativeArchFolder(v51, v52);
    std::wstring::~wstring(v52);
  }
  std::filesystem::operator/(lpApplicationName, (struct std::filesystem::path *)v51, (std::filesystem *)v53);
  std::wstring::~wstring(v51);
  std::wstring::~wstring(v53);
  v36 = 0;
  uus::UndockedStubTelemetry::UusLogStubDefines<bool &,bool &,bool>(v38, &v37, &v36);
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  v22 = (WCHAR *)lpCommandLine;
  *(_QWORD *)&ProcessInformation.dwProcessId = 0;
  v23 = (const WCHAR *)lpApplicationName;
  if ( v48 > 7 )
    v22 = lpCommandLine[0];
  if ( v50 > 7 )
    v23 = lpApplicationName[0];
  *(_OWORD *)&ProcessInformation.hProcess = 0;
  if ( !CreateProcessW(v23, v22, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\enduser\\windowsupdate\\undocked\\stubexes\\main.cpp",
      v24);
  if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\enduser\\windowsupdate\\undocked\\stubexes\\main.cpp",
      v25);
  ExitCode = 0;
  if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\enduser\\windowsupdate\\undocked\\stubexes\\main.cpp",
      v26);
  v27 = lpCommandLine;
  if ( v48 > 7 )
    v27 = (LPWSTR *)lpCommandLine[0];
  pv = v27;
  v28 = lpApplicationName;
  if ( v50 > 7 )
    v28 = (LPCWSTR *)lpApplicationName[0];
  v41 = (const wchar_t *)v28;
  uus::UndockedStubTelemetry::UusLogStubExe2Exe<unsigned short const *,unsigned short const *,unsigned long &>(
    &v41,
    &pv,
    &ExitCode);
  v29 = ExitCode;
  if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
  if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  std::wstring::~wstring(lpApplicationName);
  (**(void (__fastcall ***)(__int64, __int64))v17)(v17, 1);
  std::wstring::~wstring(lpCommandLine);
  LocalFree(v5);
  return v29;
}

```

## disassembly

```asm
0x14000a678  push    rbp
0x14000a67a  push    rbx
0x14000a67b  push    rsi
0x14000a67c  push    rdi
0x14000a67d  push    r12
0x14000a67f  push    r13
0x14000a681  push    r14
0x14000a683  push    r15
0x14000a685  lea     rbp, [rsp-0B8h]
0x14000a68d  sub     rsp, 1B8h
0x14000a694  mov     rax, cs:__security_cookie
0x14000a69b  xor     rax, rsp
0x14000a69e  mov     [rbp+0F0h+var_50], rax
0x14000a6a5  xor     r12d, r12d
0x14000a6a8  mov     ecx, 8003h; uMode
0x14000a6ad  mov     [rsp+1F0h+var_19E], r12b
0x14000a6b2  call    cs:__imp_SetErrorMode
0x14000a6b8  call    cs:__imp_GetCommandLineW
0x14000a6be  lea     rdx, [rsp+1F0h+pNumArgs]; pNumArgs
0x14000a6c3  mov     [rsp+1F0h+pNumArgs], r12d
0x14000a6c8  mov     rcx, rax; lpCmdLine
0x14000a6cb  call    cs:__imp_CommandLineToArgvW
0x14000a6d1  mov     rcx, [rbp+0F8h]; this
0x14000a6d8  test    rax, rax
0x14000a6db  mov     rbx, rax
0x14000a6de  setz    al
0x14000a6e1  test    al, al
0x14000a6e3  jnz     loc_14000AA8A
0x14000a6e9  lea     r13d, [r12+1]
0x14000a6ee  mov     [rbp+0F0h+var_E0], r12
0x14000a6f2  xorps   xmm0, xmm0
0x14000a6f5  lea     r8d, [r12+7]
0x14000a6fa  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000a6fe  mov     [rbp+0F0h+var_D8], r8
0x14000a702  mov     r9d, r12d
0x14000a705  mov     r15d, r13d
0x14000a708  movups  xmmword ptr [rbp+0F0h+lpCommandLine], xmm0
0x14000a70c  mov     word ptr [rbp+0F0h+lpCommandLine], r12w
0x14000a711  cmp     [rsp+1F0h+pNumArgs], r13d
0x14000a716  jle     loc_14000A7E2
0x14000a71c  test    r9, r9
0x14000a71f  jz      short loc_14000A76F
0x14000a721  mov     rax, r8
0x14000a724  lea     rcx, [rbp+0F0h+lpCommandLine]; Src
0x14000a728  sub     rax, r9
0x14000a72b  cmp     rax, r13
0x14000a72e  jb      short loc_14000A753
0x14000a730  mov     eax, dword ptr cs:asc_14000DDDC; " "
0x14000a736  lea     rdx, [r9+1]
0x14000a73a  mov     [rbp+0F0h+var_E0], rdx
0x14000a73e  cmp     r8, 7
0x14000a742  cmova   rcx, [rbp+0F0h+lpCommandLine]
0x14000a747  mov     [rcx+r9*2], ax
0x14000a74c  mov     [rcx+rdx*2], r12w
0x14000a751  jmp     short loc_14000A767
0x14000a753  lea     r9, asc_14000DDDC; " "
0x14000a75a  mov     qword ptr [rsp+1F0h+bInheritHandles], r13; __int64
0x14000a75f  mov     rdx, r13
0x14000a762  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000a767  mov     r9, [rbp+0F0h+var_E0]
0x14000a76b  mov     r8, [rbp+0F0h+var_D8]
0x14000a76f  movsxd  rax, r15d
0x14000a772  mov     rdx, r14
0x14000a775  mov     r10, [rbx+rax*8]
0x14000a779  inc     rdx
0x14000a77c  cmp     [r10+rdx*2], r12w
0x14000a781  jnz     short loc_14000A779
0x14000a783  mov     rax, r8
0x14000a786  sub     rax, r9
0x14000a789  cmp     rdx, rax
0x14000a78c  ja      short loc_14000A7BA
0x14000a78e  cmp     r8, 7
0x14000a792  lea     rsi, [rdx+r9]
0x14000a796  lea     r8, [rdx+rdx]; Size
0x14000a79a  mov     [rbp+0F0h+var_E0], rsi
0x14000a79e  lea     rdi, [rbp+0F0h+lpCommandLine]
0x14000a7a2  mov     rdx, r10; Src
0x14000a7a5  cmova   rdi, [rbp+0F0h+lpCommandLine]
0x14000a7aa  lea     rcx, [rdi+r9*2]; void *
0x14000a7ae  call    memmove_0
0x14000a7b3  mov     [rdi+rsi*2], r12w
0x14000a7b8  jmp     short loc_14000A7CB
0x14000a7ba  mov     r9, r10
0x14000a7bd  mov     qword ptr [rsp+1F0h+bInheritHandles], rdx; __int64
0x14000a7c2  lea     rcx, [rbp+0F0h+lpCommandLine]; Src
0x14000a7c6  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000a7cb  add     r15d, r13d
0x14000a7ce  cmp     r15d, [rsp+1F0h+pNumArgs]
0x14000a7d3  jge     short loc_14000A7E2
0x14000a7d5  mov     r8, [rbp+0F0h+var_D8]
0x14000a7d9  mov     r9, [rbp+0F0h+var_E0]
0x14000a7dd  jmp     loc_14000A71C
0x14000a7e2  mov     ecx, 10h; Size
0x14000a7e7  mov     [rsp+1F0h+var_19F], r13b
0x14000a7ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a7f1  lea     rdx, aUieorchestrato; "UIEOrchestrator"
0x14000a7f8  mov     rcx, rax; this
0x14000a7fb  call    ??0Session@uus@@QEAA@PEBG@Z; uus::Session::Session(ushort const *)
0x14000a800  mov     rsi, rax
0x14000a803  mov     [rsp+1F0h+var_188], 13h
0x14000a80c  lea     rax, aUieorchestrato_0; "UIEOrchestrator.exe"
0x14000a813  lea     rdx, [rsp+1F0h+var_190]
0x14000a818  mov     [rsp+1F0h+var_190], rax
0x14000a81d  lea     rcx, [rbp+0F0h+var_70]; void *
0x14000a824  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x14000a829  mov     rcx, [rsi+8]
0x14000a82d  test    rcx, rcx
0x14000a830  jz      short loc_14000A865
0x14000a832  mov     rdx, [rcx]
0x14000a835  mov     rax, [rdx+28h]
0x14000a839  mov     edx, r13d
0x14000a83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a841  inc     r14
0x14000a844  cmp     [rax+r14*2], r12w
0x14000a849  jnz     short loc_14000A841
0x14000a84b  lea     rdx, [rsp+1F0h+var_190]
0x14000a850  mov     [rsp+1F0h+var_190], rax
0x14000a855  lea     rcx, [rbp+0F0h+var_B0]; void *
0x14000a859  mov     [rsp+1F0h+var_188], r14
0x14000a85e  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x14000a863  jmp     short loc_14000A8C7
0x14000a865  lea     rdx, [rsp+1F0h+pv]
0x14000a86a  mov     [rsp+1F0h+pv], r12
0x14000a86f  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14000a874  test    eax, eax
0x14000a876  js      loc_14000AA9C
0x14000a87c  mov     rdi, [rsp+1F0h+pv]
0x14000a881  inc     r14
0x14000a884  cmp     [rdi+r14*2], r12w
0x14000a889  jnz     short loc_14000A881
0x14000a88b  lea     rdx, [rsp+1F0h+var_190]
0x14000a890  mov     [rsp+1F0h+var_190], rdi
0x14000a895  lea     rcx, [rbp+0F0h+var_90]; void *
0x14000a899  mov     [rsp+1F0h+var_188], r14
0x14000a89e  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x14000a8a3  test    rdi, rdi
0x14000a8a6  jz      short loc_14000A8B1
0x14000a8a8  mov     rcx, rdi; pv
0x14000a8ab  call    cs:__imp_CoTaskMemFree
0x14000a8b1  lea     rdx, [rbp+0F0h+var_90]
0x14000a8b5  lea     rcx, [rbp+0F0h+var_B0]
0x14000a8b9  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x14000a8be  lea     rcx, [rbp+0F0h+var_90]
0x14000a8c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a8c7  lea     r8, [rbp+0F0h+var_70]; this
0x14000a8ce  lea     rdx, [rbp+0F0h+var_B0]; struct std::filesystem::path *
0x14000a8d2  lea     rcx, [rbp+0F0h+lpApplicationName]; Src
0x14000a8d6  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x14000a8db  lea     rcx, [rbp+0F0h+var_B0]
0x14000a8df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a8e4  lea     rcx, [rbp+0F0h+var_70]
0x14000a8eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a8f0  lea     r8, [rsp+1F0h+var_1A0]
0x14000a8f5  mov     [rsp+1F0h+var_1A0], r12b
0x14000a8fa  lea     rdx, [rsp+1F0h+var_19F]
0x14000a8ff  lea     rcx, [rsp+1F0h+var_19E]
0x14000a904  call    ??$UusLogStubDefines@AEA_NAEA_N_N@UndockedStubTelemetry@uus@@SAXAEA_N0$$QEA_N@Z; uus::UndockedStubTelemetry::UusLogStubDefines<bool &,bool &,bool>(bool &,bool &,bool &&)
0x14000a909  xor     edx, edx; Val
0x14000a90b  lea     rcx, [rbp+0F0h+StartupInfo+4]; void *
0x14000a90f  lea     r8d, [rdx+64h]; Size
0x14000a913  call    memset_0
0x14000a918  xor     eax, eax
0x14000a91a  mov     [rbp+0F0h+StartupInfo.cb], 68h ; 'h'
0x14000a921  cmp     [rbp+0F0h+var_D8], 7
0x14000a926  lea     rdx, [rbp+0F0h+lpCommandLine]
0x14000a92a  mov     qword ptr [rbp+0F0h+ProcessInformation.dwProcessId], rax
0x14000a92e  lea     rcx, [rbp+0F0h+lpApplicationName]
0x14000a932  cmova   rdx, [rbp+0F0h+lpCommandLine]; lpCommandLine
0x14000a937  lea     rax, [rsp+1F0h+ProcessInformation]
0x14000a93c  cmp     [rbp+0F0h+var_B8], 7
0x14000a941  xorps   xmm0, xmm0
0x14000a944  mov     [rsp+1F0h+lpProcessInformation], rax; lpProcessInformation
0x14000a949  lea     rax, [rbp+0F0h+StartupInfo]
0x14000a94d  cmova   rcx, [rbp+0F0h+lpApplicationName]; lpApplicationName
0x14000a952  xor     r9d, r9d; lpThreadAttributes
0x14000a955  mov     [rsp+1F0h+lpStartupInfo], rax; lpStartupInfo
0x14000a95a  xor     r8d, r8d; lpProcessAttributes
0x14000a95d  mov     [rsp+1F0h+lpCurrentDirectory], r12; lpCurrentDirectory
0x14000a962  mov     [rsp+1F0h+lpEnvironment], r12; lpEnvironment
0x14000a967  mov     [rsp+1F0h+dwCreationFlags], r12d; dwCreationFlags
0x14000a96c  mov     [rsp+1F0h+bInheritHandles], r12d; bInheritHandles
0x14000a971  movups  xmmword ptr [rsp+1F0h+ProcessInformation.hProcess], xmm0
0x14000a976  call    cs:__imp_CreateProcessW
0x14000a97c  test    eax, eax
0x14000a97e  jz      loc_14000AAB8
0x14000a984  mov     rcx, [rsp+1F0h+ProcessInformation.hProcess]; hHandle
0x14000a989  or      edi, 0FFFFFFFFh
0x14000a98c  mov     edx, edi; dwMilliseconds
0x14000a98e  call    cs:__imp_WaitForSingleObject
0x14000a994  cmp     eax, edi
0x14000a996  jz      loc_14000AAD1
0x14000a99c  mov     rcx, [rsp+1F0h+ProcessInformation.hProcess]; hProcess
0x14000a9a1  lea     rdx, [rsp+1F0h+ExitCode]; lpExitCode
0x14000a9a6  mov     [rsp+1F0h+ExitCode], r12d
0x14000a9ab  call    cs:__imp_GetExitCodeProcess
0x14000a9b1  test    eax, eax
0x14000a9b3  jz      loc_14000AAEA
0x14000a9b9  cmp     [rbp+0F0h+var_D8], 7
0x14000a9be  lea     rax, [rbp+0F0h+lpCommandLine]
0x14000a9c2  lea     r8, [rsp+1F0h+ExitCode]
0x14000a9c7  cmova   rax, [rbp+0F0h+lpCommandLine]
0x14000a9cc  lea     rdx, [rsp+1F0h+pv]
0x14000a9d1  cmp     [rbp+0F0h+var_B8], 7
0x14000a9d6  lea     rcx, [rsp+1F0h+var_190]
0x14000a9db  mov     [rsp+1F0h+pv], rax
0x14000a9e0  lea     rax, [rbp+0F0h+lpApplicationName]
0x14000a9e4  cmova   rax, [rbp+0F0h+lpApplicationName]
0x14000a9e9  mov     [rsp+1F0h+var_190], rax
0x14000a9ee  call    ??$UusLogStubExe2Exe@PEBGPEBGAEAK@UndockedStubTelemetry@uus@@SAX$$QEAPEBG0AEAK@Z; uus::UndockedStubTelemetry::UusLogStubExe2Exe<ushort const *,ushort const *,ulong &>(ushort const * &&,ushort const * &&,ulong &)
0x14000a9f3  mov     rcx, [rsp+1F0h+ProcessInformation.hProcess]; hObject
0x14000a9f8  mov     edi, [rsp+1F0h+ExitCode]
0x14000a9fc  test    rcx, rcx
0x14000a9ff  jz      short loc_14000AA0F
0x14000aa01  call    cs:__imp_CloseHandle
0x14000aa07  test    eax, eax
0x14000aa09  jz      loc_14000AB03
0x14000aa0f  mov     rcx, [rbp+0F0h+ProcessInformation.hThread]; hObject
0x14000aa13  test    rcx, rcx
0x14000aa16  jz      short loc_14000AA22
0x14000aa18  call    cs:__imp_CloseHandle
0x14000aa1e  test    eax, eax
0x14000aa20  jz      short loc_14000AA78
0x14000aa22  lea     rcx, [rbp+0F0h+lpApplicationName]
0x14000aa26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000aa2b  mov     rax, [rsi]
0x14000aa2e  mov     edx, r13d
0x14000aa31  mov     rcx, rsi
0x14000aa34  mov     rax, [rax]
0x14000aa37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa3c  lea     rcx, [rbp+0F0h+lpCommandLine]
0x14000aa40  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000aa45  test    rbx, rbx
0x14000aa48  jz      short loc_14000AA53
0x14000aa4a  mov     rcx, rbx; hMem
0x14000aa4d  call    cs:__imp_LocalFree
0x14000aa53  mov     eax, edi
0x14000aa55  mov     rcx, [rbp+0F0h+var_50]
0x14000aa5c  xor     rcx, rsp; StackCookie
0x14000aa5f  call    __security_check_cookie
0x14000aa64  add     rsp, 1B8h
0x14000aa6b  pop     r15
0x14000aa6d  pop     r14
0x14000aa6f  pop     r13
0x14000aa71  pop     r12
0x14000aa73  pop     rdi
0x14000aa74  pop     rsi
0x14000aa75  pop     rbx
0x14000aa76  pop     rbp
0x14000aa77  retn
0x14000aa78  mov     rcx, [rbp+0F8h]; this
0x14000aa7f  mov     edx, 0A0Bh; void *
0x14000aa84  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000aa8a  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x14000aa91  mov     edx, 1Ch; void *
0x14000aa96  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14000aa9c  mov     rcx, [rbp+0F8h]; this
0x14000aaa3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000aaaa  mov     r9d, eax; char *
0x14000aaad  mov     edx, 250h; void *
0x14000aab2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000aab8  mov     rcx, [rbp+0F8h]; this
0x14000aabf  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x14000aac6  mov     edx, 58h ; 'X'; void *
0x14000aacb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14000aad1  mov     rcx, [rbp+0F8h]; this
0x14000aad8  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x14000aadf  mov     edx, 5Bh ; '['; void *
0x14000aae4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14000aaea  mov     rcx, [rbp+0F8h]; this
0x14000aaf1  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x14000aaf8  mov     edx, 5Eh ; '^'; void *
0x14000aafd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14000ab03  mov     rcx, [rbp+0F8h]; this
0x14000ab0a  mov     edx, 0A0Bh; void *
0x14000ab0f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
