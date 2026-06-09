# ForcedReboot(void)

- ea: `0x14000f18c`
- end: `0x14000f506`
- name: `?ForcedReboot@@YAJXZ`
- size: `890`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140009594`
- `0x14000f18c`
- `0x1400347e8`
- `0x140034cc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000f30c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000f30c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14000f339`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14000f339`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f392`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f429`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f48f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f392`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f429`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f48f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000f1bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000f1bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000f1cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000f1cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f252`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f2cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f3d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f46f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f4d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f252`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f2cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f3d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f46f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f4d5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x14000f21e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x14000f21e`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x14000f366`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x14000f3fc`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x14000f366`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x14000f3fc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000f299`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000f3c2`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000f459`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000f4bf`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000f299`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000f3c2`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000f459`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000f4bf`

## string_xrefs

- `0x14000f305`: `DMAppsRes.dll`
- `0x14000f215`: `SeShutdownPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 ForcedReboot(void)
{
  HANDLE CurrentProcess; // rax
  const char *v1; // r9
  unsigned int LastError; // ebx
  const char *v4; // r9
  unsigned int v5; // ebx
  const char *v6; // r9
  unsigned int v7; // ebx
  HMODULE Library; // rax
  HMODULE v9; // rbx
  const char *v10; // r9
  unsigned int v11; // edi
  const char *v12; // r9
  unsigned int v13; // edi
  CEnrollmentLogger *Logger; // rax
  LONG HighPart; // [rsp+30h] [rbp-278h] BYREF
  void *TokenHandle[5]; // [rsp+38h] [rbp-270h] BYREF
  char v17; // [rsp+60h] [rbp-248h]
  struct _LUID Luid[2]; // [rsp+68h] [rbp-240h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  *(_OWORD *)&Luid[0].LowPart = 0;
  TokenHandle[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x297,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
                  v1);
    if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(TokenHandle[0]);
    return LastError;
  }
  if ( !LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart) )
  {
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x299,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
           v4);
    if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(TokenHandle[0]);
    return v5;
  }
  Luid[0].LowPart = 1;
  HighPart = Luid[1].HighPart;
  Luid[1].HighPart = 2;
  if ( !AdjustTokenPrivileges(TokenHandle[0], 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
  {
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x29F,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
           v6);
    if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(TokenHandle[0]);
    return v7;
  }
  TokenHandle[2] = Luid;
  TokenHandle[3] = &HighPart;
  TokenHandle[4] = TokenHandle;
  v17 = 1;
  Library = LoadLibraryExW(L"DMAppsRes.dll", 0, 0x802u);
  v9 = Library;
  TokenHandle[1] = Library;
  if ( Library && LoadStringW(Library, 0x65E9u, Buffer, 260) )
  {
    if ( !InitiateSystemShutdownExW(0, Buffer, 0x78u, 1, 1, 0x20004u) )
    {
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2B4,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
              v10);
      FreeLibrary(v9);
      Luid[1].HighPart = HighPart;
      AdjustTokenPrivileges(TokenHandle[0], 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0);
      if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(TokenHandle[0]);
      return v11;
    }
    goto LABEL_25;
  }
  if ( InitiateSystemShutdownExW(0, 0, 0x78u, 1, 1, 0x20004u) )
  {
LABEL_25:
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogForcedReboot(Logger);
    if ( v9 )
      FreeLibrary(v9);
    Luid[1].HighPart = HighPart;
    AdjustTokenPrivileges(TokenHandle[0], 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0);
    if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(TokenHandle[0]);
    return 0;
  }
  v13 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x2B0,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
          v12);
  if ( v9 )
    FreeLibrary(v9);
  Luid[1].HighPart = HighPart;
  AdjustTokenPrivileges(TokenHandle[0], 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0);
  if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(TokenHandle[0]);
  return v13;
}

```

## disassembly

```asm
0x14000f18c  mov     [rsp+arg_0], rbx
0x14000f191  push    rdi
0x14000f192  sub     rsp, 2A0h
0x14000f199  mov     rax, cs:__security_cookie
0x14000f1a0  xor     rax, rsp
0x14000f1a3  mov     [rsp+2A8h+var_18], rax
0x14000f1ab  xorps   xmm0, xmm0
0x14000f1ae  movups  xmmword ptr [rsp+2A8h+Luid.LowPart], xmm0
0x14000f1b3  mov     [rsp+2A8h+TokenHandle], 0
0x14000f1bc  call    cs:__imp_GetCurrentProcess
0x14000f1c2  lea     r8, [rsp+2A8h+TokenHandle]; TokenHandle
0x14000f1c7  mov     edx, 28h ; '('; DesiredAccess
0x14000f1cc  mov     rcx, rax; ProcessHandle
0x14000f1cf  call    cs:__imp_OpenProcessToken
0x14000f1d5  test    eax, eax
0x14000f1d7  jnz     short loc_14000F210
0x14000f1d9  mov     rcx, [rsp+2A8h]; this
0x14000f1e1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000f1e8  mov     edx, 297h; void *
0x14000f1ed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000f1f2  mov     ebx, eax
0x14000f1f4  mov     rcx, [rsp+2A8h+TokenHandle]; hObject
0x14000f1f9  lea     rdx, [rcx-1]
0x14000f1fd  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000f201  ja      short loc_14000F209
0x14000f203  call    cs:__imp_CloseHandle
0x14000f209  mov     eax, ebx
0x14000f20b  jmp     loc_14000F4E4
0x14000f210  lea     r8, [rsp+2A8h+Luid.HighPart]; lpLuid
0x14000f215  lea     rdx, Name; "SeShutdownPrivilege"
0x14000f21c  xor     ecx, ecx; lpSystemName
0x14000f21e  call    cs:__imp_LookupPrivilegeValueW
0x14000f224  test    eax, eax
0x14000f226  jnz     short loc_14000F25F
0x14000f228  mov     rcx, [rsp+2A8h]; this
0x14000f230  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000f237  mov     edx, 299h; void *
0x14000f23c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000f241  mov     ebx, eax
0x14000f243  mov     rcx, [rsp+2A8h+TokenHandle]; hObject
0x14000f248  lea     rdx, [rcx-1]
0x14000f24c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000f250  ja      short loc_14000F258
0x14000f252  call    cs:__imp_CloseHandle
0x14000f258  mov     eax, ebx
0x14000f25a  jmp     loc_14000F4E4
0x14000f25f  mov     edi, 1
0x14000f264  mov     [rsp+2A8h+Luid.LowPart], edi
0x14000f268  mov     eax, [rsp+2A8h+Luid.HighPart+8]
0x14000f26c  mov     [rsp+2A8h+var_278], eax
0x14000f270  mov     [rsp+2A8h+Luid.HighPart+8], 2
0x14000f278  mov     [rsp+2A8h+ReturnLength], 0; ReturnLength
0x14000f281  mov     [rsp+2A8h+PreviousState], 0; PreviousState
0x14000f28a  xor     r9d, r9d; BufferLength
0x14000f28d  lea     r8, [rsp+2A8h+Luid]; NewState
0x14000f292  xor     edx, edx; DisableAllPrivileges
0x14000f294  mov     rcx, [rsp+2A8h+TokenHandle]; TokenHandle
0x14000f299  call    cs:__imp_AdjustTokenPrivileges
0x14000f29f  test    eax, eax
0x14000f2a1  jnz     short loc_14000F2DA
0x14000f2a3  mov     rcx, [rsp+2A8h]; this
0x14000f2ab  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000f2b2  mov     edx, 29Fh; void *
0x14000f2b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000f2bc  mov     ebx, eax
0x14000f2be  mov     rcx, [rsp+2A8h+TokenHandle]; hObject
0x14000f2c3  lea     rdx, [rcx-1]
0x14000f2c7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000f2cb  ja      short loc_14000F2D3
0x14000f2cd  call    cs:__imp_CloseHandle
0x14000f2d3  mov     eax, ebx
0x14000f2d5  jmp     loc_14000F4E4
0x14000f2da  lea     rax, [rsp+2A8h+Luid]
0x14000f2df  mov     [rsp+2A8h+var_260], rax
0x14000f2e4  lea     rax, [rsp+2A8h+var_278]
0x14000f2e9  mov     [rsp+2A8h+var_258], rax
0x14000f2ee  lea     rax, [rsp+2A8h+TokenHandle]
0x14000f2f3  mov     [rsp+2A8h+var_250], rax
0x14000f2f8  mov     [rsp+2A8h+var_248], dil
0x14000f2fd  xor     edx, edx; hFile
0x14000f2ff  mov     r8d, 802h; dwFlags
0x14000f305  lea     rcx, aDmappsresDll; "DMAppsRes.dll"
0x14000f30c  call    cs:__imp_LoadLibraryExW
0x14000f312  mov     rbx, rax
0x14000f315  mov     [rsp+2A8h+var_268], rax
0x14000f31a  test    rax, rax
0x14000f31d  jz      loc_14000F3E5
0x14000f323  mov     r9d, 104h; cchBufferMax
0x14000f329  lea     r8, [rsp+2A8h+Buffer]; lpBuffer
0x14000f331  mov     edx, 65E9h; uID
0x14000f336  mov     rcx, rax; hInstance
0x14000f339  call    cs:__imp_LoadStringW
0x14000f33f  test    eax, eax
0x14000f341  jz      loc_14000F3E5
0x14000f347  mov     dword ptr [rsp+2A8h+ReturnLength], 20004h; dwReason
0x14000f34f  mov     dword ptr [rsp+2A8h+PreviousState], edi; bRebootAfterShutdown
0x14000f353  mov     r9d, edi; bForceAppsClosed
0x14000f356  mov     r8d, 78h ; 'x'; dwTimeout
0x14000f35c  lea     rdx, [rsp+2A8h+Buffer]; lpMessage
0x14000f364  xor     ecx, ecx; lpMachineName
0x14000f366  call    cs:__imp_InitiateSystemShutdownExW
0x14000f36c  test    eax, eax
0x14000f36e  jnz     loc_14000F479
0x14000f374  mov     rcx, [rsp+2A8h]; this
0x14000f37c  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000f383  mov     edx, 2B4h; void *
0x14000f388  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000f38d  mov     edi, eax
0x14000f38f  mov     rcx, rbx; hLibModule
0x14000f392  call    cs:__imp_FreeLibrary
0x14000f398  nop
0x14000f399  mov     ecx, [rsp+2A8h+var_278]
0x14000f39d  mov     [rsp+2A8h+Luid.HighPart+8], ecx
0x14000f3a1  mov     [rsp+2A8h+ReturnLength], 0; ReturnLength
0x14000f3aa  mov     [rsp+2A8h+PreviousState], 0; PreviousState
0x14000f3b3  xor     r9d, r9d; BufferLength
0x14000f3b6  lea     r8, [rsp+2A8h+Luid]; NewState
0x14000f3bb  xor     edx, edx; DisableAllPrivileges
0x14000f3bd  mov     rcx, [rsp+2A8h+TokenHandle]; TokenHandle
0x14000f3c2  call    cs:__imp_AdjustTokenPrivileges
0x14000f3c8  nop
0x14000f3c9  mov     rcx, [rsp+2A8h+TokenHandle]; hObject
0x14000f3ce  lea     rax, [rcx-1]
0x14000f3d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000f3d6  ja      short loc_14000F3DE
0x14000f3d8  call    cs:__imp_CloseHandle
0x14000f3de  mov     eax, edi
0x14000f3e0  jmp     loc_14000F4E4
0x14000f3e5  mov     dword ptr [rsp+2A8h+ReturnLength], 20004h; dwReason
0x14000f3ed  mov     dword ptr [rsp+2A8h+PreviousState], edi; bRebootAfterShutdown
0x14000f3f1  mov     r9d, edi; bForceAppsClosed
0x14000f3f4  xor     edx, edx; lpMessage
0x14000f3f6  xor     ecx, ecx; lpMachineName
0x14000f3f8  lea     r8d, [rdx+78h]; dwTimeout
0x14000f3fc  call    cs:__imp_InitiateSystemShutdownExW
0x14000f402  test    eax, eax
0x14000f404  jnz     short loc_14000F479
0x14000f406  mov     rcx, [rsp+2A8h]; this
0x14000f40e  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000f415  mov     edx, 2B0h; void *
0x14000f41a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000f41f  mov     edi, eax
0x14000f421  test    rbx, rbx
0x14000f424  jz      short loc_14000F430
0x14000f426  mov     rcx, rbx; hLibModule
0x14000f429  call    cs:__imp_FreeLibrary
0x14000f42f  nop
0x14000f430  mov     ecx, [rsp+2A8h+var_278]
0x14000f434  mov     [rsp+2A8h+Luid.HighPart+8], ecx
0x14000f438  mov     [rsp+2A8h+ReturnLength], 0; ReturnLength
0x14000f441  mov     [rsp+2A8h+PreviousState], 0; PreviousState
0x14000f44a  xor     r9d, r9d; BufferLength
0x14000f44d  lea     r8, [rsp+2A8h+Luid]; NewState
0x14000f452  xor     edx, edx; DisableAllPrivileges
0x14000f454  mov     rcx, [rsp+2A8h+TokenHandle]; TokenHandle
0x14000f459  call    cs:__imp_AdjustTokenPrivileges
0x14000f45f  nop
0x14000f460  mov     rcx, [rsp+2A8h+TokenHandle]; hObject
0x14000f465  lea     rax, [rcx-1]
0x14000f469  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000f46d  ja      short loc_14000F475
0x14000f46f  call    cs:__imp_CloseHandle
0x14000f475  mov     eax, edi
0x14000f477  jmp     short loc_14000F4E4
0x14000f479  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000f47e  mov     rcx, rax; this
0x14000f481  call    ?LogForcedReboot@CEnrollmentLogger@@QEAAXXZ; CEnrollmentLogger::LogForcedReboot(void)
0x14000f486  nop
0x14000f487  test    rbx, rbx
0x14000f48a  jz      short loc_14000F496
0x14000f48c  mov     rcx, rbx; hLibModule
0x14000f48f  call    cs:__imp_FreeLibrary
0x14000f495  nop
0x14000f496  mov     eax, [rsp+2A8h+var_278]
0x14000f49a  mov     [rsp+2A8h+Luid.HighPart+8], eax
0x14000f49e  mov     [rsp+2A8h+ReturnLength], 0; ReturnLength
0x14000f4a7  mov     [rsp+2A8h+PreviousState], 0; PreviousState
0x14000f4b0  xor     r9d, r9d; BufferLength
0x14000f4b3  lea     r8, [rsp+2A8h+Luid]; NewState
0x14000f4b8  xor     edx, edx; DisableAllPrivileges
0x14000f4ba  mov     rcx, [rsp+2A8h+TokenHandle]; TokenHandle
0x14000f4bf  call    cs:__imp_AdjustTokenPrivileges
0x14000f4c5  nop
0x14000f4c6  mov     rcx, [rsp+2A8h+TokenHandle]; hObject
0x14000f4cb  lea     rax, [rcx-1]
0x14000f4cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000f4d3  ja      short loc_14000F4DC
0x14000f4d5  call    cs:__imp_CloseHandle
0x14000f4db  nop
0x14000f4dc  xor     eax, eax
0x14000f4de  jmp     short loc_14000F4E4
0x14000f4e0  mov     eax, [rsp+2A8h+var_278]
0x14000f4e4  mov     rcx, [rsp+2A8h+var_18]
0x14000f4ec  xor     rcx, rsp; StackCookie
0x14000f4ef  call    __security_check_cookie
0x14000f4f4  mov     rbx, [rsp+2A8h+arg_0]
0x14000f4fc  add     rsp, 2A0h
0x14000f503  pop     rdi
0x14000f504  retn
```
