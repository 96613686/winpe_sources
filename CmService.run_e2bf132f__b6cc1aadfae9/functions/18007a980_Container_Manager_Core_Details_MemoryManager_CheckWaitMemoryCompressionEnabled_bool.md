# Container::Manager::Core::Details::MemoryManager::CheckWaitMemoryCompressionEnabled(bool &)

- ea: `0x18007a980`
- end: `0x18007aba5`
- name: `?CheckWaitMemoryCompressionEnabled@MemoryManager@Details@Core@Manager@Container@@CAJAEA_N@Z`
- size: `549`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007cc18`

## callees

- `0x180004bd0`
- `0x18000da68`
- `0x18000dad8`
- `0x18007a980`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007aa74`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007aaef`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007aa74`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007aaef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aa01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aa01`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18007a9f1`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18007a9f1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007a9d1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007a9d1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007aa2e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ab2d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ab3c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ab66`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007aa2e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ab2d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ab3c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ab66`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007a9a9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007a9a9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18007aa53`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18007aa53`
- `ext-ms-win-sysmain-pfapi-l1-1-0!PfRpcSendCommand` at `0x18007aad4`
- `ext-ms-win-sysmain-pfapi-l1-1-0!PfRpcSendCommand` at `0x18007aad4`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::MemoryManager::CheckWaitMemoryCompressionEnabled(bool *a1)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rdi
  SC_HANDLE v5; // rax
  const char *v6; // r9
  SC_HANDLE v7; // rbx
  const char *v8; // r9
  int v9; // eax
  unsigned int LastError; // esi
  int v11; // esi
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // r14d
  unsigned int v16; // [rsp+20h] [rbp-58h] BYREF
  _DWORD v17[2]; // [rsp+28h] [rbp-50h] BYREF
  __int128 v18; // [rsp+30h] [rbp-48h]
  __int64 v19; // [rsp+40h] [rbp-38h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v2 = OpenSCManagerW(0, 0, 1u);
  v4 = v2;
  if ( !v2 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x129,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
             v3);
  v5 = OpenServiceW(v2, L"sysmain", 0x14u);
  v7 = v5;
  if ( !v5 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x12F,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
                  v6);
LABEL_24:
    CloseServiceHandle(v4);
    return LastError;
  }
  if ( !StartServiceW(v5, 0, 0) && GetLastError() != 1056 )
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x136,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
           v8);
LABEL_6:
    LastError = v9;
    CloseServiceHandle(v7);
    goto LABEL_24;
  }
  v11 = 0;
  while ( 1 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(v7, &ServiceStatus) )
      break;
LABEL_11:
    Sleep(0x64u);
    if ( (unsigned int)++v11 >= 0x12C )
    {
LABEL_12:
      v12 = 357;
LABEL_13:
      v13 = 1077;
LABEL_14:
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
             (const char *)v13,
             v16);
      goto LABEL_6;
    }
  }
  if ( ServiceStatus.dwCurrentState != 4 )
  {
    if ( ServiceStatus.dwCurrentState != 2 )
      goto LABEL_12;
    goto LABEL_11;
  }
  v19 = 0;
  v18 = 0;
  v17[0] = 1;
  v17[1] = 75497476;
  v16 = 32;
  while ( 1 )
  {
    v14 = PfRpcSendCommand(v17, &v16);
    if ( v14 != 1008 )
      break;
    Sleep(0x64u);
    if ( (unsigned int)++v11 >= 0x12C )
    {
      if ( v11 == 300 )
      {
        v12 = 386;
        goto LABEL_13;
      }
      goto LABEL_21;
    }
  }
  if ( v14 )
  {
LABEL_21:
    v13 = v14;
    v12 = 390;
    goto LABEL_14;
  }
  *a1 = (_DWORD)v19 != 0;
  CloseServiceHandle(v7);
  CloseServiceHandle(v4);
  return 0;
}

```

## disassembly

```asm
0x18007a980  push    rbp
0x18007a982  push    rbx
0x18007a983  push    rsi
0x18007a984  push    rdi
0x18007a985  push    r14
0x18007a987  push    r15
0x18007a989  mov     rbp, rsp
0x18007a98c  sub     rsp, 78h
0x18007a990  mov     rax, cs:__security_cookie
0x18007a997  xor     rax, rsp
0x18007a99a  mov     [rbp+var_10], rax
0x18007a99e  xor     edx, edx; lpDatabaseName
0x18007a9a0  mov     r15, rcx
0x18007a9a3  xor     ecx, ecx; lpMachineName
0x18007a9a5  lea     r8d, [rdx+1]; dwDesiredAccess
0x18007a9a9  call    cs:__imp_OpenSCManagerW
0x18007a9b0  nop     dword ptr [rax+rax+00h]
0x18007a9b5  mov     rdi, rax
0x18007a9b8  test    rax, rax
0x18007a9bb  jz      loc_18007AB76
0x18007a9c1  mov     r8d, 14h; dwDesiredAccess
0x18007a9c7  lea     rdx, aSysmain; "sysmain"
0x18007a9ce  mov     rcx, rax; hSCManager
0x18007a9d1  call    cs:__imp_OpenServiceW
0x18007a9d8  nop     dword ptr [rax+rax+00h]
0x18007a9dd  mov     rbx, rax
0x18007a9e0  test    rax, rax
0x18007a9e3  jz      loc_18007AB4C
0x18007a9e9  xor     r8d, r8d; lpServiceArgVectors
0x18007a9ec  xor     edx, edx; dwNumServiceArgs
0x18007a9ee  mov     rcx, rax; hService
0x18007a9f1  call    cs:__imp_StartServiceW
0x18007a9f8  nop     dword ptr [rax+rax+00h]
0x18007a9fd  test    eax, eax
0x18007a9ff  jnz     short loc_18007AA3F
0x18007aa01  call    cs:__imp_GetLastError
0x18007aa08  nop     dword ptr [rax+rax+00h]
0x18007aa0d  cmp     eax, 420h
0x18007aa12  jz      short loc_18007AA3F
0x18007aa14  mov     rcx, [rbp+30h]; this
0x18007aa18  lea     r8, aOnecoreBaseGen_32; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18007aa1f  mov     edx, 136h; void *
0x18007aa24  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007aa29  mov     rcx, rbx; hSCObject
0x18007aa2c  mov     esi, eax
0x18007aa2e  call    cs:__imp_CloseServiceHandle
0x18007aa35  nop     dword ptr [rax+rax+00h]
0x18007aa3a  jmp     loc_18007AB63
0x18007aa3f  xor     esi, esi
0x18007aa41  xorps   xmm0, xmm0
0x18007aa44  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18007aa48  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x18007aa4c  mov     rcx, rbx; hService
0x18007aa4f  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x18007aa53  call    cs:__imp_QueryServiceStatus
0x18007aa5a  nop     dword ptr [rax+rax+00h]
0x18007aa5f  test    eax, eax
0x18007aa61  jz      short loc_18007AA6F
0x18007aa63  cmp     [rbp+ServiceStatus.dwCurrentState], 4
0x18007aa67  jz      short loc_18007AAA7
0x18007aa69  cmp     [rbp+ServiceStatus.dwCurrentState], 2
0x18007aa6d  jnz     short loc_18007AA8A
0x18007aa6f  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18007aa74  call    cs:__imp_Sleep
0x18007aa7b  nop     dword ptr [rax+rax+00h]
0x18007aa80  inc     esi
0x18007aa82  cmp     esi, 12Ch
0x18007aa88  jb      short loc_18007AA41
0x18007aa8a  mov     edx, 165h; void *
0x18007aa8f  mov     r9d, 435h; char *
0x18007aa95  mov     rcx, [rbp+30h]; this
0x18007aa99  lea     r8, aOnecoreBaseGen_32; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18007aaa0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007aaa5  jmp     short loc_18007AA29
0x18007aaa7  xorps   xmm0, xmm0
0x18007aaaa  mov     [rbp+var_38], 0
0x18007aab2  movdqu  [rbp+var_48], xmm0
0x18007aab7  mov     [rbp+var_50], 1
0x18007aabe  mov     [rbp+var_4C], 4800004h
0x18007aac5  mov     [rbp+var_58], 20h ; ' '
0x18007aacc  lea     rdx, [rbp+var_58]
0x18007aad0  lea     rcx, [rbp+var_50]
0x18007aad4  call    cs:__imp_PfRpcSendCommand
0x18007aadb  nop     dword ptr [rax+rax+00h]
0x18007aae0  mov     r14d, eax
0x18007aae3  cmp     eax, 3F0h
0x18007aae8  jnz     short loc_18007AB0E
0x18007aaea  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18007aaef  call    cs:__imp_Sleep
0x18007aaf6  nop     dword ptr [rax+rax+00h]
0x18007aafb  inc     esi
0x18007aafd  cmp     esi, 12Ch
0x18007ab03  jb      short loc_18007AACC
0x18007ab05  jnz     short loc_18007AB13
0x18007ab07  mov     edx, 182h
0x18007ab0c  jmp     short loc_18007AA8F
0x18007ab0e  test    r14d, r14d
0x18007ab11  jz      short loc_18007AB20
0x18007ab13  mov     r9d, r14d
0x18007ab16  mov     edx, 186h
0x18007ab1b  jmp     loc_18007AA95
0x18007ab20  cmp     dword ptr [rbp+var_38], 0
0x18007ab24  mov     rcx, rbx; hSCObject
0x18007ab27  setnz   al
0x18007ab2a  mov     [r15], al
0x18007ab2d  call    cs:__imp_CloseServiceHandle
0x18007ab34  nop     dword ptr [rax+rax+00h]
0x18007ab39  mov     rcx, rdi; hSCObject
0x18007ab3c  call    cs:__imp_CloseServiceHandle
0x18007ab43  nop     dword ptr [rax+rax+00h]
0x18007ab48  xor     eax, eax
0x18007ab4a  jmp     short loc_18007AB8B
0x18007ab4c  mov     rcx, [rbp+30h]; this
0x18007ab50  lea     r8, aOnecoreBaseGen_32; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18007ab57  mov     edx, 12Fh; void *
0x18007ab5c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007ab61  mov     esi, eax
0x18007ab63  mov     rcx, rdi; hSCObject
0x18007ab66  call    cs:__imp_CloseServiceHandle
0x18007ab6d  nop     dword ptr [rax+rax+00h]
0x18007ab72  mov     eax, esi
0x18007ab74  jmp     short loc_18007AB8B
0x18007ab76  mov     rcx, [rbp+30h]; this
0x18007ab7a  lea     r8, aOnecoreBaseGen_32; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18007ab81  mov     edx, 129h; void *
0x18007ab86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007ab8b  mov     rcx, [rbp+var_10]
0x18007ab8f  xor     rcx, rsp; StackCookie
0x18007ab92  call    __security_check_cookie
0x18007ab97  add     rsp, 78h
0x18007ab9b  pop     r15
0x18007ab9d  pop     r14
0x18007ab9f  pop     rdi
0x18007aba0  pop     rsi
0x18007aba1  pop     rbx
0x18007aba2  pop     rbp
0x18007aba3  retn
```
