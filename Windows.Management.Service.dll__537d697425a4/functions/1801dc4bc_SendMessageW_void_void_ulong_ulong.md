# SendMessageW(void *,void *,ulong,ulong *)

- ea: `0x1801dc4bc`
- end: `0x1801dc6fe`
- name: `?SendMessageW@@YAJPEAX0KPEAK@Z`
- size: `578`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1801db080`
- `0x1801db558`
- `0x1801db9dc`
- `0x1801dbca4`
- `0x1801dc748`

## callees

- `0x180065d98`
- `0x180067e34`
- `0x180067e54`
- `0x180088144`
- `0x1801dc4bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801dc521`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801dc521`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801dc5e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801dc5e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc5a0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801dc590`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801dc590`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc5fe`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc689`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc5fe`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc689`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801dc646`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801dc646`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SendMessageW(
        HANDLE hFile,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
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
    v8 = 776;
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
    v8 = 777;
    goto LABEL_3;
  }
  if ( !hFile )
  {
    v8 = 778;
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = EventW;
  v23 = EventW;
  if ( EventW )
  {
    memset(&Overlapped, 0, 24);
    Overlapped.hEvent = EventW;
    if ( WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, lpNumberOfBytesTransferred, &Overlapped)
      || GetLastError() == 997 )
    {
      v14 = WaitForSingleObject(v12, 0x2710u);
      if ( v14 )
      {
        if ( v14 != 258 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x330,
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
                        (void *)0x329,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        v16);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
          return LastError;
        }
        if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x32C,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        v17);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
          return LastError;
        }
      }
      else if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x324,
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
                  (void *)0x31D,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v13);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x30E,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v11);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
  }
  return LastError;
}

```

## disassembly

```asm
0x1801dc4bc  push    rbp
0x1801dc4be  push    rbx
0x1801dc4bf  push    rsi
0x1801dc4c0  push    rdi
0x1801dc4c1  push    r14
0x1801dc4c3  push    r15
0x1801dc4c5  mov     rbp, rsp
0x1801dc4c8  sub     rsp, 58h
0x1801dc4cc  mov     rsi, r9
0x1801dc4cf  mov     r15d, r8d
0x1801dc4d2  mov     r14, rdx
0x1801dc4d5  mov     rdi, rcx
0x1801dc4d8  test    rdx, rdx
0x1801dc4db  jnz     short loc_1801DC4FF
0x1801dc4dd  mov     edx, 308h; void *
0x1801dc4e2  mov     ebx, 80070057h
0x1801dc4e7  mov     rcx, [rbp+30h]; this
0x1801dc4eb  mov     r9d, ebx; char *
0x1801dc4ee  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc4f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dc4fa  jmp     loc_1801DC6EE
0x1801dc4ff  test    rsi, rsi
0x1801dc502  jnz     short loc_1801DC50B
0x1801dc504  mov     edx, 309h
0x1801dc509  jmp     short loc_1801DC4E2
0x1801dc50b  test    rdi, rdi
0x1801dc50e  jnz     short loc_1801DC517
0x1801dc510  mov     edx, 30Ah
0x1801dc515  jmp     short loc_1801DC4E2
0x1801dc517  xor     r9d, r9d; lpName
0x1801dc51a  xor     r8d, r8d; bInitialState
0x1801dc51d  xor     edx, edx; bManualReset
0x1801dc51f  xor     ecx, ecx; lpEventAttributes
0x1801dc521  call    cs:__imp_CreateEventW
0x1801dc528  nop     dword ptr [rax+rax+00h]
0x1801dc52d  mov     rbx, rax
0x1801dc530  mov     [rbp+arg_8], rax
0x1801dc534  test    rax, rax
0x1801dc537  jnz     short loc_1801DC55F
0x1801dc539  mov     rcx, [rbp+30h]; this
0x1801dc53d  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc544  mov     edx, 30Eh; void *
0x1801dc549  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc54e  mov     ebx, eax
0x1801dc550  lea     rcx, [rbp+arg_8]
0x1801dc554  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc559  nop
0x1801dc55a  jmp     loc_1801DC6EE
0x1801dc55f  mov     [rbp+Overlapped.Internal], 0
0x1801dc567  mov     [rbp+Overlapped.InternalHigh], 0
0x1801dc56f  mov     [rbp+Overlapped.hEvent], rbx
0x1801dc573  mov     qword ptr [rbp+Overlapped.10h], 0
0x1801dc57b  lea     rax, [rbp+Overlapped]
0x1801dc57f  mov     qword ptr [rsp+58h+lpOverlapped], rax; unsigned int
0x1801dc584  mov     r9, rsi; lpNumberOfBytesWritten
0x1801dc587  mov     r8d, r15d; nNumberOfBytesToWrite
0x1801dc58a  mov     rdx, r14; lpBuffer
0x1801dc58d  mov     rcx, rdi; hFile
0x1801dc590  call    cs:__imp_WriteFile
0x1801dc597  nop     dword ptr [rax+rax+00h]
0x1801dc59c  test    eax, eax
0x1801dc59e  jnz     short loc_1801DC5D9
0x1801dc5a0  call    cs:__imp_GetLastError
0x1801dc5a7  nop     dword ptr [rax+rax+00h]
0x1801dc5ac  cmp     eax, 3E5h
0x1801dc5b1  jz      short loc_1801DC5D9
0x1801dc5b3  mov     rcx, [rbp+30h]; this
0x1801dc5b7  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc5be  mov     edx, 31Dh; void *
0x1801dc5c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc5c8  mov     ebx, eax
0x1801dc5ca  lea     rcx, [rbp+arg_8]
0x1801dc5ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc5d3  nop
0x1801dc5d4  jmp     loc_1801DC6EE
0x1801dc5d9  mov     edx, 2710h; dwMilliseconds
0x1801dc5de  mov     rcx, rbx; hHandle
0x1801dc5e1  call    cs:__imp_WaitForSingleObject
0x1801dc5e8  nop     dword ptr [rax+rax+00h]
0x1801dc5ed  test    eax, eax
0x1801dc5ef  jnz     short loc_1801DC638
0x1801dc5f1  xor     r9d, r9d; bWait
0x1801dc5f4  mov     r8, rsi; lpNumberOfBytesTransferred
0x1801dc5f7  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801dc5fb  mov     rcx, rdi; hFile
0x1801dc5fe  call    cs:__imp_GetOverlappedResult
0x1801dc605  nop     dword ptr [rax+rax+00h]
0x1801dc60a  test    eax, eax
0x1801dc60c  jnz     loc_1801DC6BC
0x1801dc612  mov     rcx, [rbp+30h]; this
0x1801dc616  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc61d  mov     edx, 324h; void *
0x1801dc622  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc627  mov     ebx, eax
0x1801dc629  lea     rcx, [rbp+arg_8]
0x1801dc62d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc632  nop
0x1801dc633  jmp     loc_1801DC6EE
0x1801dc638  cmp     eax, 102h
0x1801dc63d  jnz     loc_1801DC6CA
0x1801dc643  mov     rcx, rdi; hFile
0x1801dc646  call    cs:__imp_CancelIo
0x1801dc64d  nop     dword ptr [rax+rax+00h]
0x1801dc652  test    eax, eax
0x1801dc654  jnz     short loc_1801DC679
0x1801dc656  mov     rcx, [rbp+30h]; this
0x1801dc65a  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc661  mov     edx, 329h; void *
0x1801dc666  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc66b  mov     ebx, eax
0x1801dc66d  lea     rcx, [rbp+arg_8]
0x1801dc671  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc676  nop
0x1801dc677  jmp     short loc_1801DC6EE
0x1801dc679  mov     r9d, 1; bWait
0x1801dc67f  mov     r8, rsi; lpNumberOfBytesTransferred
0x1801dc682  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801dc686  mov     rcx, rdi; hFile
0x1801dc689  call    cs:__imp_GetOverlappedResult
0x1801dc690  nop     dword ptr [rax+rax+00h]
0x1801dc695  test    eax, eax
0x1801dc697  jnz     short loc_1801DC6BC
0x1801dc699  mov     rcx, [rbp+30h]; this
0x1801dc69d  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc6a4  mov     edx, 32Ch; void *
0x1801dc6a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc6ae  mov     ebx, eax
0x1801dc6b0  lea     rcx, [rbp+arg_8]
0x1801dc6b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc6b9  nop
0x1801dc6ba  jmp     short loc_1801DC6EE
0x1801dc6bc  lea     rcx, [rbp+arg_8]
0x1801dc6c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc6c5  nop
0x1801dc6c6  xor     eax, eax
0x1801dc6c8  jmp     short loc_1801DC6F0
0x1801dc6ca  mov     rcx, [rbp+30h]; this
0x1801dc6ce  mov     r9d, eax; char *
0x1801dc6d1  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc6d8  mov     edx, 330h; void *
0x1801dc6dd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801dc6e2  mov     ebx, eax
0x1801dc6e4  lea     rcx, [rbp+arg_8]
0x1801dc6e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc6ed  nop
0x1801dc6ee  mov     eax, ebx
0x1801dc6f0  add     rsp, 58h
0x1801dc6f4  pop     r15
0x1801dc6f6  pop     r14
0x1801dc6f8  pop     rdi
0x1801dc6f9  pop     rsi
0x1801dc6fa  pop     rbx
0x1801dc6fb  pop     rbp
0x1801dc6fc  retn
```
