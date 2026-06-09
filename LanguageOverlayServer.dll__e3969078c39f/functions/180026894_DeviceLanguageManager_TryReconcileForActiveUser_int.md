# DeviceLanguageManager::_TryReconcileForActiveUser(int *)

- ea: `0x180026894`
- end: `0x180026c39`
- name: `?_TryReconcileForActiveUser@DeviceLanguageManager@@AEAAJPEAH@Z`
- size: `933`
- prototype: `__int64 __fastcall(DeviceLanguageManager *__hidden this, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ff6c`

## callees

- `0x180003a00`
- `0x1800044b8`
- `0x180009064`
- `0x180009084`
- `0x1800099c4`
- `0x1800120b0`
- `0x1800266a0`
- `0x180026894`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180026acd`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180026acd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026971`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800269c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ba2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026bdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026bf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026971`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800269c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026b6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ba2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026bdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026bf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c05`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180026a00`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180026a00`
- `ntdll!RtlGetNtSystemRoot` at `0x1800268f1`
- `ntdll!RtlGetNtSystemRoot` at `0x1800268f1`

## string_xrefs

- `0x180026951`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\devicelanguagemanager.cpp`
- `0x1800269a3`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\devicelanguagemanager.cpp`
- `0x180026a12`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\devicelanguagemanager.cpp`
- `0x180026adf`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\devicelanguagemanager.cpp`
- `0x180026b4d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\devicelanguagemanager.cpp`
- `0x180026b7f`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\devicelanguagemanager.cpp`
- `0x180026bb7`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\devicelanguagemanager.cpp`
- `0x18002697e`: `\system32\schtasks.exe /Run /i /TN "\Microsoft\Windows\LanguageComponentsInstaller\ReconcileLanguageResources"`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DeviceLanguageManager::_TryReconcileForActiveUser(DeviceLanguageManager *this, int *a2)
{
  const char *v3; // r9
  char *v4; // rcx
  __int64 v5; // rbx
  WCHAR *NtSystemRoot; // rax
  unsigned __int64 v7; // rdx
  WCHAR *v8; // r8
  WCHAR v9; // cx
  unsigned int v10; // ebx
  WCHAR *v11; // rcx
  __int64 result; // rax
  int v13; // eax
  unsigned int v14; // ebx
  const char *v15; // r9
  unsigned int LastError; // ebx
  const char *v17; // r9
  unsigned int v18; // ebx
  HANDLE hProcess; // rcx
  unsigned int v20; // ebx
  int TokenType; // [rsp+20h] [rbp-308h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-2C8h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-2B0h] BYREF
  HANDLE hToken; // [rsp+80h] [rbp-2A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-298h] BYREF
  WCHAR CommandLine[264]; // [rsp+100h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  try
  {
    *a2 = 0;
    DeviceLanguageManager::_TryGetActiveUserToken(this, &hObject);
    v4 = (char *)hObject;
    if ( !hObject )
    {
LABEL_43:
      if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v4);
      return 0;
    }
    memset_0(CommandLine, 0, 0x208u);
    v5 = 2147483646;
    NtSystemRoot = (WCHAR *)RtlGetNtSystemRoot();
    v7 = 260;
    v8 = CommandLine;
    do
    {
      if ( !v5 )
        break;
      v9 = *NtSystemRoot;
      if ( !*NtSystemRoot )
        break;
      ++NtSystemRoot;
      *v8++ = v9;
      --v5;
      --v7;
    }
    while ( v7 );
    v10 = v7 == 0 ? 0x8007007A : 0;
    v11 = v8 - 1;
    if ( v7 )
      v11 = v8;
    *v11 = 0;
    if ( !v7 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicelanguagemanager.cpp",
        (const char *)v10,
        TokenType);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return v10;
    }
    v13 = StringCchCatW(
            CommandLine,
            v7,
            L"\\system32\\schtasks.exe /Run /i /TN \"\\Microsoft\\Windows\\LanguageComponentsInstaller\\ReconcileLanguageResources\"");
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicelanguagemanager.cpp",
        (const char *)(unsigned int)v13,
        TokenType);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return v14;
    }
    hToken = 0;
    if ( !DuplicateTokenEx(hObject, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hToken) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x114,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicelanguagemanager.cpp",
                    v15);
      if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hToken);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return LastError;
    }
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    if ( !CreateProcessAsUserW(hToken, 0, CommandLine, 0, 0, 0, 0x30u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v18 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x125,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicelanguagemanager.cpp",
              v17);
      if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hToken);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return v18;
    }
    hProcess = ProcessInformation.hProcess;
    if ( (unsigned __int64)ProcessInformation.hProcess - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      *a2 = 1;
      if ( !CloseHandle(hProcess) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x12A,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicelanguagemanager.cpp",
          v3);
      if ( (unsigned __int64)ProcessInformation.hThread - 1 <= 0xFFFFFFFFFFFFFFFDuLL
        && !CloseHandle(ProcessInformation.hThread) )
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x12D,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicelanguagemanager.cpp",
          v3);
      }
      if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hToken);
      v4 = (char *)hObject;
      goto LABEL_43;
    }
    v20 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x126,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicelanguagemanager.cpp",
            v17);
    if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hToken);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    result = v20;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x132,
                           (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicela"
                                         "nguagemanager.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x180026894  mov     [rsp+arg_0], rbx
0x180026899  mov     [rsp+arg_10], rsi
0x18002689e  push    rdi
0x18002689f  sub     rsp, 320h
0x1800268a6  mov     rax, cs:__security_cookie
0x1800268ad  xor     rax, rsp
0x1800268b0  mov     [rsp+328h+var_18], rax
0x1800268b8  mov     rdi, rdx
0x1800268bb  xor     esi, esi
0x1800268bd  mov     [rdx], esi
0x1800268bf  lea     rdx, [rsp+328h+hObject]
0x1800268c4  call    ?_TryGetActiveUserToken@DeviceLanguageManager@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; DeviceLanguageManager::_TryGetActiveUserToken(void)
0x1800268c9  mov     rcx, [rsp+328h+hObject]; hObject
0x1800268ce  test    rcx, rcx
0x1800268d1  jz      loc_180026BFB
0x1800268d7  xor     edx, edx; Val
0x1800268d9  mov     r8d, 208h; Size
0x1800268df  lea     rcx, [rsp+328h+CommandLine]; void *
0x1800268e7  call    memset_0
0x1800268ec  mov     ebx, 7FFFFFFEh
0x1800268f1  call    cs:__imp_RtlGetNtSystemRoot
0x1800268f7  mov     edx, 104h
0x1800268fc  lea     r8, [rsp+328h+CommandLine]
0x180026904  test    rbx, rbx
0x180026907  jz      short loc_180026926
0x180026909  movzx   ecx, word ptr [rax]
0x18002690c  test    cx, cx
0x18002690f  jz      short loc_180026926
0x180026911  add     rax, 2
0x180026915  mov     [r8], cx
0x180026919  add     r8, 2
0x18002691d  dec     rbx
0x180026920  sub     rdx, 1; unsigned __int64
0x180026924  jnz     short loc_180026904
0x180026926  mov     rax, rdx
0x180026929  neg     rax
0x18002692c  sbb     ebx, ebx
0x18002692e  not     ebx
0x180026930  and     ebx, 8007007Ah
0x180026936  lea     rcx, [r8-2]
0x18002693a  test    rdx, rdx
0x18002693d  cmovnz  rcx, r8
0x180026941  mov     [rcx], si
0x180026944  jnz     short loc_18002697E
0x180026946  mov     rcx, [rsp+328h]; this
0x18002694e  mov     r9d, ebx; char *
0x180026951  lea     r8, aOnecoreBaseLan_20; "onecore\\base\\languageoverlay\\service"...
0x180026958  mov     edx, 108h; void *
0x18002695d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026962  mov     rcx, [rsp+328h+hObject]; hObject
0x180026967  lea     rdx, [rcx-1]
0x18002696b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002696f  ja      short loc_180026977
0x180026971  call    cs:__imp_CloseHandle
0x180026977  mov     eax, ebx
0x180026979  jmp     loc_180026C13
0x18002697e  lea     r8, aSystem32Schtas; "\\system32\\schtasks.exe /Run /i /TN \""...
0x180026985  lea     rcx, [rsp+328h+CommandLine]; unsigned __int16 *
0x18002698d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026992  mov     ebx, eax
0x180026994  test    eax, eax
0x180026996  jns     short loc_1800269D0
0x180026998  mov     rcx, [rsp+328h]; this
0x1800269a0  mov     r9d, eax; char *
0x1800269a3  lea     r8, aOnecoreBaseLan_20; "onecore\\base\\languageoverlay\\service"...
0x1800269aa  mov     edx, 109h; void *
0x1800269af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800269b4  mov     rcx, [rsp+328h+hObject]; hObject
0x1800269b9  lea     rdx, [rcx-1]
0x1800269bd  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800269c1  ja      short loc_1800269C9
0x1800269c3  call    cs:__imp_CloseHandle
0x1800269c9  mov     eax, ebx
0x1800269cb  jmp     loc_180026C13
0x1800269d0  mov     [rsp+328h+hToken], rsi
0x1800269d8  lea     rax, [rsp+328h+hToken]
0x1800269e0  mov     [rsp+328h+phNewToken], rax; phNewToken
0x1800269e5  mov     [rsp+328h+TokenType], 1; TokenType
0x1800269ed  mov     r9d, 2; ImpersonationLevel
0x1800269f3  xor     r8d, r8d; lpTokenAttributes
0x1800269f6  mov     edx, 2000000h; dwDesiredAccess
0x1800269fb  mov     rcx, [rsp+328h+hObject]; hExistingToken
0x180026a00  call    cs:__imp_DuplicateTokenEx
0x180026a06  test    eax, eax
0x180026a08  jnz     short loc_180026A59
0x180026a0a  mov     rcx, [rsp+328h]; this
0x180026a12  lea     r8, aOnecoreBaseLan_20; "onecore\\base\\languageoverlay\\service"...
0x180026a19  mov     edx, 114h; void *
0x180026a1e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026a23  mov     ebx, eax
0x180026a25  mov     rcx, [rsp+328h+hToken]; hObject
0x180026a2d  lea     rdx, [rcx-1]
0x180026a31  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180026a35  ja      short loc_180026A3D
0x180026a37  call    cs:__imp_CloseHandle
0x180026a3d  mov     rcx, [rsp+328h+hObject]; hObject
0x180026a42  lea     rdx, [rcx-1]
0x180026a46  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180026a4a  ja      short loc_180026A52
0x180026a4c  call    cs:__imp_CloseHandle
0x180026a52  mov     eax, ebx
0x180026a54  jmp     loc_180026C13
0x180026a59  xorps   xmm0, xmm0
0x180026a5c  xor     eax, eax
0x180026a5e  movups  xmmword ptr [rsp+328h+ProcessInformation.hProcess], xmm0
0x180026a63  mov     qword ptr [rsp+328h+ProcessInformation.dwProcessId], rax
0x180026a68  xor     edx, edx; Val
0x180026a6a  lea     r8d, [rax+64h]; Size
0x180026a6e  lea     rcx, [rsp+328h+StartupInfo+4]; void *
0x180026a76  call    memset_0
0x180026a7b  mov     [rsp+328h+StartupInfo.cb], 68h ; 'h'
0x180026a86  lea     rax, [rsp+328h+ProcessInformation]
0x180026a8b  mov     [rsp+328h+lpProcessInformation], rax; lpProcessInformation
0x180026a90  lea     rax, [rsp+328h+StartupInfo]
0x180026a98  mov     [rsp+328h+lpStartupInfo], rax; lpStartupInfo
0x180026a9d  mov     [rsp+328h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x180026aa2  mov     [rsp+328h+lpEnvironment], rsi; lpEnvironment
0x180026aa7  mov     [rsp+328h+dwCreationFlags], 30h ; '0'; dwCreationFlags
0x180026aaf  mov     dword ptr [rsp+328h+phNewToken], esi; bInheritHandles
0x180026ab3  mov     qword ptr [rsp+328h+TokenType], rsi; lpThreadAttributes
0x180026ab8  xor     r9d, r9d; lpProcessAttributes
0x180026abb  lea     r8, [rsp+328h+CommandLine]; lpCommandLine
0x180026ac3  xor     edx, edx; lpApplicationName
0x180026ac5  mov     rcx, [rsp+328h+hToken]; hToken
0x180026acd  call    cs:__imp_CreateProcessAsUserW
0x180026ad3  test    eax, eax
0x180026ad5  jnz     short loc_180026B26
0x180026ad7  mov     rcx, [rsp+328h]; this
0x180026adf  lea     r8, aOnecoreBaseLan_20; "onecore\\base\\languageoverlay\\service"...
0x180026ae6  mov     edx, 125h; void *
0x180026aeb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026af0  mov     ebx, eax
0x180026af2  mov     rcx, [rsp+328h+hToken]; hObject
0x180026afa  lea     rdx, [rcx-1]
0x180026afe  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180026b02  ja      short loc_180026B0A
0x180026b04  call    cs:__imp_CloseHandle
0x180026b0a  mov     rcx, [rsp+328h+hObject]; hObject
0x180026b0f  lea     rdx, [rcx-1]
0x180026b13  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180026b17  ja      short loc_180026B1F
0x180026b19  call    cs:__imp_CloseHandle
0x180026b1f  mov     eax, ebx
0x180026b21  jmp     loc_180026C13
0x180026b26  mov     rcx, [rsp+328h+ProcessInformation.hProcess]; hObject
0x180026b2b  lea     rax, [rcx-1]
0x180026b2f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026b33  ja      short loc_180026BAF
0x180026b35  mov     dword ptr [rdi], 1
0x180026b3b  call    cs:__imp_CloseHandle
0x180026b41  mov     rcx, [rsp+328h]; this
0x180026b49  test    eax, eax
0x180026b4b  jnz     short loc_180026B5E
0x180026b4d  lea     r8, aOnecoreBaseLan_20; "onecore\\base\\languageoverlay\\service"...
0x180026b54  mov     edx, 12Ah; void *
0x180026b59  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180026b5e  mov     rcx, [rsp+328h+ProcessInformation.hThread]; hObject
0x180026b63  lea     rax, [rcx-1]
0x180026b67  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026b6b  ja      short loc_180026B90
0x180026b6d  call    cs:__imp_CloseHandle
0x180026b73  mov     rcx, [rsp+328h]; this
0x180026b7b  test    eax, eax
0x180026b7d  jnz     short loc_180026B90
0x180026b7f  lea     r8, aOnecoreBaseLan_20; "onecore\\base\\languageoverlay\\service"...
0x180026b86  mov     edx, 12Dh; void *
0x180026b8b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180026b90  mov     rcx, [rsp+328h+hToken]; hObject
0x180026b98  lea     rax, [rcx-1]
0x180026b9c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026ba0  ja      short loc_180026BA8
0x180026ba2  call    cs:__imp_CloseHandle
0x180026ba8  mov     rcx, [rsp+328h+hObject]
0x180026bad  jmp     short loc_180026BFB
0x180026baf  mov     rcx, [rsp+328h]; this
0x180026bb7  lea     r8, aOnecoreBaseLan_20; "onecore\\base\\languageoverlay\\service"...
0x180026bbe  mov     edx, 126h; void *
0x180026bc3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026bc8  mov     ebx, eax
0x180026bca  mov     rcx, [rsp+328h+hToken]; hObject
0x180026bd2  lea     rdx, [rcx-1]
0x180026bd6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180026bda  ja      short loc_180026BE2
0x180026bdc  call    cs:__imp_CloseHandle
0x180026be2  mov     rcx, [rsp+328h+hObject]; hObject
0x180026be7  lea     rdx, [rcx-1]
0x180026beb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180026bef  ja      short loc_180026BF7
0x180026bf1  call    cs:__imp_CloseHandle
0x180026bf7  mov     eax, ebx
0x180026bf9  jmp     short loc_180026C13
0x180026bfb  lea     rax, [rcx-1]
0x180026bff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026c03  ja      short loc_180026C0B
0x180026c05  call    cs:__imp_CloseHandle
0x180026c0b  xor     eax, eax
0x180026c0d  jmp     short loc_180026C13
0x180026c0f  mov     eax, dword ptr [rsp+328h+hObject]
0x180026c13  mov     rcx, [rsp+328h+var_18]
0x180026c1b  xor     rcx, rsp; StackCookie
0x180026c1e  call    __security_check_cookie
0x180026c23  lea     r11, [rsp+328h+var_8]
0x180026c2b  mov     rbx, [r11+10h]
0x180026c2f  mov     rsi, [r11+20h]
0x180026c33  mov     rsp, r11
0x180026c36  pop     rdi
0x180026c37  retn
```
