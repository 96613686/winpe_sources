# ReceiveMessage(void *,void *,ulong,ulong *)

- ea: `0x18009d368`
- end: `0x18009d5b7`
- name: `?ReceiveMessage@@YAJPEAX0KPEAK@Z`
- size: `591`
- prototype: `__int64 __fastcall(HANDLE hFile, void *lpBuffer, DWORD nNumberOfBytesToRead, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18009c3a4`
- `0x18009c87c`
- `0x18009cd00`
- `0x18009cffc`
- `0x18009dadc`

## callees

- `0x180053f9c`
- `0x180057c4c`
- `0x180057c6c`
- `0x18005d508`
- `0x18009d368`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009d3d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009d3d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009d499`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009d499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d458`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009d448`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009d448`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18009d4ff`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18009d4ff`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009d4b7`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009d542`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009d4b7`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009d542`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ReceiveMessage(
        HANDLE hFile,
        void *lpBuffer,
        DWORD nNumberOfBytesToRead,
        LPDWORD lpNumberOfBytesTransferred)
{
  __int64 v8; // rdx
  unsigned int LastError; // ebx
  HANDLE EventW; // rax
  const char *v11; // r9
  void *v12; // rbx
  const char *v13; // r9
  DWORD v14; // eax
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // r9
  int lpOverlapped; // [rsp+20h] [rbp-38h]
  unsigned int lpOverlappeda; // [rsp+20h] [rbp-38h]
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  HANDLE v23; // [rsp+98h] [rbp+40h] BYREF

  if ( !lpBuffer )
  {
    v8 = 828;
LABEL_3:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
      (const char *)0x80070057LL,
      lpOverlapped);
    return LastError;
  }
  if ( !lpNumberOfBytesTransferred )
  {
    v8 = 829;
    goto LABEL_3;
  }
  if ( !hFile )
  {
    v8 = 830;
    goto LABEL_3;
  }
  if ( !nNumberOfBytesToRead )
  {
    v8 = 831;
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = EventW;
  v23 = EventW;
  if ( EventW )
  {
    memset(&Overlapped, 0, 24);
    Overlapped.hEvent = EventW;
    if ( ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, lpNumberOfBytesTransferred, &Overlapped)
      || GetLastError() == 997 )
    {
      v14 = WaitForSingleObject(v12, 0x2710u);
      if ( v14 )
      {
        if ( v14 != 258 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x364,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        (const char *)v14,
                        lpOverlappeda);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
          return LastError;
        }
        if ( !CancelIo(hFile) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x35D,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        v16);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
          return LastError;
        }
        if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x360,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        v17);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
          return LastError;
        }
      }
      else if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x358,
                      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                      v15);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        return LastError;
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
      return 0;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x351,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v13);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x342,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v11);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
  }
  return LastError;
}

```

## disassembly

```asm
0x18009d368  push    rbp
0x18009d36a  push    rbx
0x18009d36b  push    rsi
0x18009d36c  push    rdi
0x18009d36d  push    r14
0x18009d36f  push    r15
0x18009d371  mov     rbp, rsp
0x18009d374  sub     rsp, 58h
0x18009d378  mov     rsi, r9
0x18009d37b  mov     r14d, r8d
0x18009d37e  mov     r15, rdx
0x18009d381  mov     rdi, rcx
0x18009d384  test    rdx, rdx
0x18009d387  jnz     short loc_18009D3AB
0x18009d389  mov     edx, 33Ch; void *
0x18009d38e  mov     ebx, 80070057h
0x18009d393  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d39a  mov     r9d, ebx; char *
0x18009d39d  mov     rcx, [rbp+30h]; this
0x18009d3a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d3a6  jmp     loc_18009D5A7
0x18009d3ab  test    rsi, rsi
0x18009d3ae  jnz     short loc_18009D3B7
0x18009d3b0  mov     edx, 33Dh
0x18009d3b5  jmp     short loc_18009D38E
0x18009d3b7  test    rdi, rdi
0x18009d3ba  jnz     short loc_18009D3C3
0x18009d3bc  mov     edx, 33Eh
0x18009d3c1  jmp     short loc_18009D38E
0x18009d3c3  test    r14d, r14d
0x18009d3c6  jnz     short loc_18009D3CF
0x18009d3c8  mov     edx, 33Fh
0x18009d3cd  jmp     short loc_18009D38E
0x18009d3cf  xor     r9d, r9d; lpName
0x18009d3d2  xor     r8d, r8d; bInitialState
0x18009d3d5  xor     edx, edx; bManualReset
0x18009d3d7  xor     ecx, ecx; lpEventAttributes
0x18009d3d9  call    cs:__imp_CreateEventW
0x18009d3e0  nop     dword ptr [rax+rax+00h]
0x18009d3e5  mov     rbx, rax
0x18009d3e8  mov     [rbp+arg_8], rax
0x18009d3ec  test    rax, rax
0x18009d3ef  jnz     short loc_18009D417
0x18009d3f1  mov     rcx, [rbp+30h]; this
0x18009d3f5  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d3fc  mov     edx, 342h; void *
0x18009d401  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d406  mov     ebx, eax
0x18009d408  lea     rcx, [rbp+arg_8]
0x18009d40c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d411  nop
0x18009d412  jmp     loc_18009D5A7
0x18009d417  mov     [rbp+Overlapped.Internal], 0
0x18009d41f  mov     [rbp+Overlapped.InternalHigh], 0
0x18009d427  mov     [rbp+Overlapped.hEvent], rbx
0x18009d42b  mov     qword ptr [rbp+Overlapped.10h], 0
0x18009d433  lea     rax, [rbp+Overlapped]
0x18009d437  mov     qword ptr [rsp+58h+lpOverlapped], rax; unsigned int
0x18009d43c  mov     r9, rsi; lpNumberOfBytesRead
0x18009d43f  mov     r8d, r14d; nNumberOfBytesToRead
0x18009d442  mov     rdx, r15; lpBuffer
0x18009d445  mov     rcx, rdi; hFile
0x18009d448  call    cs:__imp_ReadFile
0x18009d44f  nop     dword ptr [rax+rax+00h]
0x18009d454  test    eax, eax
0x18009d456  jnz     short loc_18009D491
0x18009d458  call    cs:__imp_GetLastError
0x18009d45f  nop     dword ptr [rax+rax+00h]
0x18009d464  cmp     eax, 3E5h
0x18009d469  jz      short loc_18009D491
0x18009d46b  mov     rcx, [rbp+30h]; this
0x18009d46f  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d476  mov     edx, 351h; void *
0x18009d47b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d480  mov     ebx, eax
0x18009d482  lea     rcx, [rbp+arg_8]
0x18009d486  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d48b  nop
0x18009d48c  jmp     loc_18009D5A7
0x18009d491  mov     edx, 2710h; dwMilliseconds
0x18009d496  mov     rcx, rbx; hHandle
0x18009d499  call    cs:__imp_WaitForSingleObject
0x18009d4a0  nop     dword ptr [rax+rax+00h]
0x18009d4a5  test    eax, eax
0x18009d4a7  jnz     short loc_18009D4F1
0x18009d4a9  lea     r9d, [rax+1]; bWait
0x18009d4ad  mov     r8, rsi; lpNumberOfBytesTransferred
0x18009d4b0  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18009d4b4  mov     rcx, rdi; hFile
0x18009d4b7  call    cs:__imp_GetOverlappedResult
0x18009d4be  nop     dword ptr [rax+rax+00h]
0x18009d4c3  test    eax, eax
0x18009d4c5  jnz     loc_18009D575
0x18009d4cb  mov     rcx, [rbp+30h]; this
0x18009d4cf  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d4d6  mov     edx, 358h; void *
0x18009d4db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d4e0  mov     ebx, eax
0x18009d4e2  lea     rcx, [rbp+arg_8]
0x18009d4e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d4eb  nop
0x18009d4ec  jmp     loc_18009D5A7
0x18009d4f1  cmp     eax, 102h
0x18009d4f6  jnz     loc_18009D583
0x18009d4fc  mov     rcx, rdi; hFile
0x18009d4ff  call    cs:__imp_CancelIo
0x18009d506  nop     dword ptr [rax+rax+00h]
0x18009d50b  test    eax, eax
0x18009d50d  jnz     short loc_18009D532
0x18009d50f  mov     rcx, [rbp+30h]; this
0x18009d513  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d51a  mov     edx, 35Dh; void *
0x18009d51f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d524  mov     ebx, eax
0x18009d526  lea     rcx, [rbp+arg_8]
0x18009d52a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d52f  nop
0x18009d530  jmp     short loc_18009D5A7
0x18009d532  mov     r9d, 1; bWait
0x18009d538  mov     r8, rsi; lpNumberOfBytesTransferred
0x18009d53b  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18009d53f  mov     rcx, rdi; hFile
0x18009d542  call    cs:__imp_GetOverlappedResult
0x18009d549  nop     dword ptr [rax+rax+00h]
0x18009d54e  test    eax, eax
0x18009d550  jnz     short loc_18009D575
0x18009d552  mov     rcx, [rbp+30h]; this
0x18009d556  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d55d  mov     edx, 360h; void *
0x18009d562  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d567  mov     ebx, eax
0x18009d569  lea     rcx, [rbp+arg_8]
0x18009d56d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d572  nop
0x18009d573  jmp     short loc_18009D5A7
0x18009d575  lea     rcx, [rbp+arg_8]
0x18009d579  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d57e  nop
0x18009d57f  xor     eax, eax
0x18009d581  jmp     short loc_18009D5A9
0x18009d583  mov     rcx, [rbp+30h]; this
0x18009d587  mov     r9d, eax; char *
0x18009d58a  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d591  mov     edx, 364h; void *
0x18009d596  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009d59b  mov     ebx, eax
0x18009d59d  lea     rcx, [rbp+arg_8]
0x18009d5a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d5a6  nop
0x18009d5a7  mov     eax, ebx
0x18009d5a9  add     rsp, 58h
0x18009d5ad  pop     r15
0x18009d5af  pop     r14
0x18009d5b1  pop     rdi
0x18009d5b2  pop     rsi
0x18009d5b3  pop     rbx
0x18009d5b4  pop     rbp
0x18009d5b5  retn
```
