# SendMessageW(void *,void *,ulong,ulong *)

- ea: `0x18009d850`
- end: `0x18009da92`
- name: `?SendMessageW@@YAJPEAX0KPEAK@Z`
- size: `578`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesTransferred)`
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
- `0x18009d850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009d8b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009d8b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009d975`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009d975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d934`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009d924`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009d924`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18009d9da`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18009d9da`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009d992`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009da1d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009d992`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009da1d`

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
0x18009d850  push    rbp
0x18009d852  push    rbx
0x18009d853  push    rsi
0x18009d854  push    rdi
0x18009d855  push    r14
0x18009d857  push    r15
0x18009d859  mov     rbp, rsp
0x18009d85c  sub     rsp, 58h
0x18009d860  mov     rsi, r9
0x18009d863  mov     r15d, r8d
0x18009d866  mov     r14, rdx
0x18009d869  mov     rdi, rcx
0x18009d86c  test    rdx, rdx
0x18009d86f  jnz     short loc_18009D893
0x18009d871  mov     edx, 308h; void *
0x18009d876  mov     ebx, 80070057h
0x18009d87b  mov     rcx, [rbp+30h]; this
0x18009d87f  mov     r9d, ebx; char *
0x18009d882  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d88e  jmp     loc_18009DA82
0x18009d893  test    rsi, rsi
0x18009d896  jnz     short loc_18009D89F
0x18009d898  mov     edx, 309h
0x18009d89d  jmp     short loc_18009D876
0x18009d89f  test    rdi, rdi
0x18009d8a2  jnz     short loc_18009D8AB
0x18009d8a4  mov     edx, 30Ah
0x18009d8a9  jmp     short loc_18009D876
0x18009d8ab  xor     r9d, r9d; lpName
0x18009d8ae  xor     r8d, r8d; bInitialState
0x18009d8b1  xor     edx, edx; bManualReset
0x18009d8b3  xor     ecx, ecx; lpEventAttributes
0x18009d8b5  call    cs:__imp_CreateEventW
0x18009d8bc  nop     dword ptr [rax+rax+00h]
0x18009d8c1  mov     rbx, rax
0x18009d8c4  mov     [rbp+arg_8], rax
0x18009d8c8  test    rax, rax
0x18009d8cb  jnz     short loc_18009D8F3
0x18009d8cd  mov     rcx, [rbp+30h]; this
0x18009d8d1  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d8d8  mov     edx, 30Eh; void *
0x18009d8dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d8e2  mov     ebx, eax
0x18009d8e4  lea     rcx, [rbp+arg_8]
0x18009d8e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d8ed  nop
0x18009d8ee  jmp     loc_18009DA82
0x18009d8f3  mov     [rbp+Overlapped.Internal], 0
0x18009d8fb  mov     [rbp+Overlapped.InternalHigh], 0
0x18009d903  mov     [rbp+Overlapped.hEvent], rbx
0x18009d907  mov     qword ptr [rbp+Overlapped.10h], 0
0x18009d90f  lea     rax, [rbp+Overlapped]
0x18009d913  mov     qword ptr [rsp+58h+lpOverlapped], rax; unsigned int
0x18009d918  mov     r9, rsi; lpNumberOfBytesWritten
0x18009d91b  mov     r8d, r15d; nNumberOfBytesToWrite
0x18009d91e  mov     rdx, r14; lpBuffer
0x18009d921  mov     rcx, rdi; hFile
0x18009d924  call    cs:__imp_WriteFile
0x18009d92b  nop     dword ptr [rax+rax+00h]
0x18009d930  test    eax, eax
0x18009d932  jnz     short loc_18009D96D
0x18009d934  call    cs:__imp_GetLastError
0x18009d93b  nop     dword ptr [rax+rax+00h]
0x18009d940  cmp     eax, 3E5h
0x18009d945  jz      short loc_18009D96D
0x18009d947  mov     rcx, [rbp+30h]; this
0x18009d94b  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d952  mov     edx, 31Dh; void *
0x18009d957  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d95c  mov     ebx, eax
0x18009d95e  lea     rcx, [rbp+arg_8]
0x18009d962  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d967  nop
0x18009d968  jmp     loc_18009DA82
0x18009d96d  mov     edx, 2710h; dwMilliseconds
0x18009d972  mov     rcx, rbx; hHandle
0x18009d975  call    cs:__imp_WaitForSingleObject
0x18009d97c  nop     dword ptr [rax+rax+00h]
0x18009d981  test    eax, eax
0x18009d983  jnz     short loc_18009D9CC
0x18009d985  xor     r9d, r9d; bWait
0x18009d988  mov     r8, rsi; lpNumberOfBytesTransferred
0x18009d98b  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18009d98f  mov     rcx, rdi; hFile
0x18009d992  call    cs:__imp_GetOverlappedResult
0x18009d999  nop     dword ptr [rax+rax+00h]
0x18009d99e  test    eax, eax
0x18009d9a0  jnz     loc_18009DA50
0x18009d9a6  mov     rcx, [rbp+30h]; this
0x18009d9aa  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d9b1  mov     edx, 324h; void *
0x18009d9b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d9bb  mov     ebx, eax
0x18009d9bd  lea     rcx, [rbp+arg_8]
0x18009d9c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d9c6  nop
0x18009d9c7  jmp     loc_18009DA82
0x18009d9cc  cmp     eax, 102h
0x18009d9d1  jnz     loc_18009DA5E
0x18009d9d7  mov     rcx, rdi; hFile
0x18009d9da  call    cs:__imp_CancelIo
0x18009d9e1  nop     dword ptr [rax+rax+00h]
0x18009d9e6  test    eax, eax
0x18009d9e8  jnz     short loc_18009DA0D
0x18009d9ea  mov     rcx, [rbp+30h]; this
0x18009d9ee  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d9f5  mov     edx, 329h; void *
0x18009d9fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d9ff  mov     ebx, eax
0x18009da01  lea     rcx, [rbp+arg_8]
0x18009da05  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009da0a  nop
0x18009da0b  jmp     short loc_18009DA82
0x18009da0d  mov     r9d, 1; bWait
0x18009da13  mov     r8, rsi; lpNumberOfBytesTransferred
0x18009da16  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18009da1a  mov     rcx, rdi; hFile
0x18009da1d  call    cs:__imp_GetOverlappedResult
0x18009da24  nop     dword ptr [rax+rax+00h]
0x18009da29  test    eax, eax
0x18009da2b  jnz     short loc_18009DA50
0x18009da2d  mov     rcx, [rbp+30h]; this
0x18009da31  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009da38  mov     edx, 32Ch; void *
0x18009da3d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009da42  mov     ebx, eax
0x18009da44  lea     rcx, [rbp+arg_8]
0x18009da48  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009da4d  nop
0x18009da4e  jmp     short loc_18009DA82
0x18009da50  lea     rcx, [rbp+arg_8]
0x18009da54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009da59  nop
0x18009da5a  xor     eax, eax
0x18009da5c  jmp     short loc_18009DA84
0x18009da5e  mov     rcx, [rbp+30h]; this
0x18009da62  mov     r9d, eax; char *
0x18009da65  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009da6c  mov     edx, 330h; void *
0x18009da71  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009da76  mov     ebx, eax
0x18009da78  lea     rcx, [rbp+arg_8]
0x18009da7c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009da81  nop
0x18009da82  mov     eax, ebx
0x18009da84  add     rsp, 58h
0x18009da88  pop     r15
0x18009da8a  pop     r14
0x18009da8c  pop     rdi
0x18009da8d  pop     rsi
0x18009da8e  pop     rbx
0x18009da8f  pop     rbp
0x18009da90  retn
```
