# SendIoctl(void *,int,void *,ulong,void *,ulong,ulong *)

- ea: `0x18009d5c0`
- end: `0x18009d848`
- name: `?SendIoctl@@YAJPEAXH0K0KPEAK@Z`
- size: `648`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int@<edx>, void *@<r8>, unsigned int@<r9d>, void *, unsigned int, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

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
- `0x18009d5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009d62d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009d62d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009d70f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009d70f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d6ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d6ce`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18009d776`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18009d776`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18009d6be`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18009d6be`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009d72e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009d7bd`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009d72e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18009d7bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SendIoctl(
        HANDLE hFile,
        __int64 a2,
        void *a3,
        DWORD a4,
        LPVOID a5,
        unsigned int a6,
        unsigned int *a7)
{
  __int64 v9; // rdx
  unsigned int LastError; // ebx
  void *v11; // rsi
  HANDLE EventW; // rax
  const char *v13; // r9
  void *v14; // rbx
  const char *v15; // r9
  DWORD v16; // eax
  const char *v17; // r9
  const char *v18; // r9
  const char *v19; // r9
  int lpOutBuffer; // [rsp+20h] [rbp-40h]
  unsigned int lpOutBuffera; // [rsp+20h] [rbp-40h]
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HANDLE v25; // [rsp+90h] [rbp+30h] BYREF
  DWORD BytesReturned; // [rsp+98h] [rbp+38h] BYREF

  BytesReturned = a4;
  if ( !a3 )
  {
    v9 = 714;
LABEL_3:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
      (const char *)0x80070057LL,
      lpOutBuffer);
    return LastError;
  }
  v11 = a5;
  if ( !a5 )
  {
    v9 = 715;
    goto LABEL_3;
  }
  if ( !hFile )
  {
    v9 = 716;
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v14 = EventW;
  v25 = EventW;
  if ( !EventW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2D1,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v13);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    return LastError;
  }
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = EventW;
  BytesReturned = 0;
  if ( !DeviceIoControl(hFile, 0x8000E004, a3, 0x10u, v11, 8u, &BytesReturned, &Overlapped) && GetLastError() != 997 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2E4,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v15);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    return LastError;
  }
  v16 = WaitForSingleObject(v14, 0x2710u);
  if ( v16 )
  {
    if ( v16 != 258 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x2F7,
                    (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                    (const char *)v16,
                    lpOutBuffera);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
      return LastError;
    }
    if ( !CancelIo(hFile) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2F0,
                    (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                    v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
      return LastError;
    }
    if ( !GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2F3,
                    (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                    v19);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
      return LastError;
    }
  }
  else if ( !GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2EB,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v17);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    return LastError;
  }
  if ( a7 )
    *a7 = BytesReturned;
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
  return 0;
}

```

## disassembly

```asm
0x18009d5c0  mov     [rsp-18h+arg_0], rbx
0x18009d5c5  mov     [rsp-18h+arg_8], rsi
0x18009d5ca  mov     [rsp-18h+BytesReturned], r9d
0x18009d5cf  push    rbp
0x18009d5d0  push    rdi
0x18009d5d1  push    r14
0x18009d5d3  mov     rbp, rsp
0x18009d5d6  sub     rsp, 60h
0x18009d5da  mov     r14, r8
0x18009d5dd  mov     rdi, rcx
0x18009d5e0  test    r8, r8
0x18009d5e3  jnz     short loc_18009D607
0x18009d5e5  mov     edx, 2CAh; void *
0x18009d5ea  mov     ebx, 80070057h
0x18009d5ef  mov     rcx, [rbp+18h]; this
0x18009d5f3  mov     r9d, ebx; char *
0x18009d5f6  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d5fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d602  jmp     loc_18009D830
0x18009d607  mov     rsi, [rbp+arg_20]
0x18009d60b  test    rsi, rsi
0x18009d60e  jnz     short loc_18009D617
0x18009d610  mov     edx, 2CBh
0x18009d615  jmp     short loc_18009D5EA
0x18009d617  test    rdi, rdi
0x18009d61a  jnz     short loc_18009D623
0x18009d61c  mov     edx, 2CCh
0x18009d621  jmp     short loc_18009D5EA
0x18009d623  xor     r9d, r9d; lpName
0x18009d626  xor     r8d, r8d; bInitialState
0x18009d629  xor     edx, edx; bManualReset
0x18009d62b  xor     ecx, ecx; lpEventAttributes
0x18009d62d  call    cs:__imp_CreateEventW
0x18009d634  nop     dword ptr [rax+rax+00h]
0x18009d639  mov     rbx, rax
0x18009d63c  mov     [rbp+arg_10], rax
0x18009d640  test    rax, rax
0x18009d643  jnz     short loc_18009D66B
0x18009d645  mov     rcx, [rbp+18h]; this
0x18009d649  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d650  mov     edx, 2D1h; void *
0x18009d655  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d65a  mov     ebx, eax
0x18009d65c  lea     rcx, [rbp+arg_10]
0x18009d660  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d665  nop
0x18009d666  jmp     loc_18009D830
0x18009d66b  mov     [rbp+Overlapped.Internal], 0
0x18009d673  mov     [rbp+Overlapped.InternalHigh], 0
0x18009d67b  mov     [rbp+Overlapped.hEvent], rbx
0x18009d67f  mov     qword ptr [rbp+Overlapped.10h], 0
0x18009d687  mov     [rbp+BytesReturned], 0
0x18009d68e  lea     rax, [rbp+Overlapped]
0x18009d692  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x18009d697  lea     rax, [rbp+BytesReturned]
0x18009d69b  mov     [rsp+60h+lpBytesReturned], rax; lpBytesReturned
0x18009d6a0  mov     [rsp+60h+nOutBufferSize], 8; nOutBufferSize
0x18009d6a8  mov     [rsp+60h+lpOutBuffer], rsi; unsigned int
0x18009d6ad  mov     r9d, 10h; nInBufferSize
0x18009d6b3  mov     r8, r14; lpInBuffer
0x18009d6b6  mov     edx, 8000E004h; dwIoControlCode
0x18009d6bb  mov     rcx, rdi; hDevice
0x18009d6be  call    cs:__imp_DeviceIoControl
0x18009d6c5  nop     dword ptr [rax+rax+00h]
0x18009d6ca  test    eax, eax
0x18009d6cc  jnz     short loc_18009D707
0x18009d6ce  call    cs:__imp_GetLastError
0x18009d6d5  nop     dword ptr [rax+rax+00h]
0x18009d6da  cmp     eax, 3E5h
0x18009d6df  jz      short loc_18009D707
0x18009d6e1  mov     rcx, [rbp+18h]; this
0x18009d6e5  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d6ec  mov     edx, 2E4h; void *
0x18009d6f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d6f6  mov     ebx, eax
0x18009d6f8  lea     rcx, [rbp+arg_10]
0x18009d6fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d701  nop
0x18009d702  jmp     loc_18009D830
0x18009d707  mov     edx, 2710h; dwMilliseconds
0x18009d70c  mov     rcx, rbx; hHandle
0x18009d70f  call    cs:__imp_WaitForSingleObject
0x18009d716  nop     dword ptr [rax+rax+00h]
0x18009d71b  test    eax, eax
0x18009d71d  jnz     short loc_18009D768
0x18009d71f  lea     r9d, [rax+1]; bWait
0x18009d723  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x18009d727  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18009d72b  mov     rcx, rdi; hFile
0x18009d72e  call    cs:__imp_GetOverlappedResult
0x18009d735  nop     dword ptr [rax+rax+00h]
0x18009d73a  test    eax, eax
0x18009d73c  jnz     loc_18009D7F0
0x18009d742  mov     rcx, [rbp+18h]; this
0x18009d746  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d74d  mov     edx, 2EBh; void *
0x18009d752  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d757  mov     ebx, eax
0x18009d759  lea     rcx, [rbp+arg_10]
0x18009d75d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d762  nop
0x18009d763  jmp     loc_18009D830
0x18009d768  cmp     eax, 102h
0x18009d76d  jnz     loc_18009D80C
0x18009d773  mov     rcx, rdi; hFile
0x18009d776  call    cs:__imp_CancelIo
0x18009d77d  nop     dword ptr [rax+rax+00h]
0x18009d782  test    eax, eax
0x18009d784  jnz     short loc_18009D7AC
0x18009d786  mov     rcx, [rbp+18h]; this
0x18009d78a  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d791  mov     edx, 2F0h; void *
0x18009d796  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d79b  mov     ebx, eax
0x18009d79d  lea     rcx, [rbp+arg_10]
0x18009d7a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d7a6  nop
0x18009d7a7  jmp     loc_18009D830
0x18009d7ac  mov     r9d, 1; bWait
0x18009d7b2  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x18009d7b6  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18009d7ba  mov     rcx, rdi; hFile
0x18009d7bd  call    cs:__imp_GetOverlappedResult
0x18009d7c4  nop     dword ptr [rax+rax+00h]
0x18009d7c9  test    eax, eax
0x18009d7cb  jnz     short loc_18009D7F0
0x18009d7cd  mov     rcx, [rbp+18h]; this
0x18009d7d1  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d7d8  mov     edx, 2F3h; void *
0x18009d7dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009d7e2  mov     ebx, eax
0x18009d7e4  lea     rcx, [rbp+arg_10]
0x18009d7e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d7ed  nop
0x18009d7ee  jmp     short loc_18009D830
0x18009d7f0  mov     rcx, [rbp+arg_30]
0x18009d7f4  test    rcx, rcx
0x18009d7f7  jz      short loc_18009D7FE
0x18009d7f9  mov     eax, [rbp+BytesReturned]
0x18009d7fc  mov     [rcx], eax
0x18009d7fe  lea     rcx, [rbp+arg_10]
0x18009d802  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d807  nop
0x18009d808  xor     eax, eax
0x18009d80a  jmp     short loc_18009D832
0x18009d80c  mov     rcx, [rbp+18h]; this
0x18009d810  mov     r9d, eax; char *
0x18009d813  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009d81a  mov     edx, 2F7h; void *
0x18009d81f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009d824  mov     ebx, eax
0x18009d826  lea     rcx, [rbp+arg_10]
0x18009d82a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009d82f  nop
0x18009d830  mov     eax, ebx
0x18009d832  lea     r11, [rsp+60h+var_s0]
0x18009d837  mov     rbx, [r11+20h]
0x18009d83b  mov     rsi, [r11+28h]
0x18009d83f  mov     rsp, r11
0x18009d842  pop     r14
0x18009d844  pop     rdi
0x18009d845  pop     rbp
0x18009d846  retn
```
