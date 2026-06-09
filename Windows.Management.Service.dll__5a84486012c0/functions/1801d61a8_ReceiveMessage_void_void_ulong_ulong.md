# ReceiveMessage(void *,void *,ulong,ulong *)

- ea: `0x1801d61a8`
- end: `0x1801d63c8`
- name: `?ReceiveMessage@@YAJPEAX0KPEAK@Z`
- size: `544`
- prototype: `__int64 __fastcall(HANDLE hFile, void *lpBuffer, DWORD nNumberOfBytesToRead, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1801d525c`
- `0x1801d5730`
- `0x1801d5bb4`
- `0x1801d5e7c`
- `0x1801d6890`

## callees

- `0x180065bac`
- `0x180067a34`
- `0x180067a54`
- `0x1800873a4`
- `0x1801d61a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801d6219`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801d6219`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801d62c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801d62c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d628c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d628c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801d6282`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801d6282`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d62df`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d635a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d62df`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d635a`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801d631d`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801d631d`

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
0x1801d61a8  push    rbp
0x1801d61aa  push    rbx
0x1801d61ab  push    rsi
0x1801d61ac  push    rdi
0x1801d61ad  push    r14
0x1801d61af  push    r15
0x1801d61b1  mov     rbp, rsp
0x1801d61b4  sub     rsp, 58h
0x1801d61b8  mov     rsi, r9
0x1801d61bb  mov     r14d, r8d
0x1801d61be  mov     r15, rdx
0x1801d61c1  mov     rdi, rcx
0x1801d61c4  test    rdx, rdx
0x1801d61c7  jnz     short loc_1801D61EB
0x1801d61c9  mov     edx, 33Ch; void *
0x1801d61ce  mov     ebx, 80070057h
0x1801d61d3  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d61da  mov     r9d, ebx; char *
0x1801d61dd  mov     rcx, [rbp+30h]; this
0x1801d61e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d61e6  jmp     loc_1801D63B9
0x1801d61eb  test    rsi, rsi
0x1801d61ee  jnz     short loc_1801D61F7
0x1801d61f0  mov     edx, 33Dh
0x1801d61f5  jmp     short loc_1801D61CE
0x1801d61f7  test    rdi, rdi
0x1801d61fa  jnz     short loc_1801D6203
0x1801d61fc  mov     edx, 33Eh
0x1801d6201  jmp     short loc_1801D61CE
0x1801d6203  test    r14d, r14d
0x1801d6206  jnz     short loc_1801D620F
0x1801d6208  mov     edx, 33Fh
0x1801d620d  jmp     short loc_1801D61CE
0x1801d620f  xor     r9d, r9d; lpName
0x1801d6212  xor     r8d, r8d; bInitialState
0x1801d6215  xor     edx, edx; bManualReset
0x1801d6217  xor     ecx, ecx; lpEventAttributes
0x1801d6219  call    cs:__imp_CreateEventW
0x1801d621f  mov     rbx, rax
0x1801d6222  mov     [rbp+arg_8], rax
0x1801d6226  test    rax, rax
0x1801d6229  jnz     short loc_1801D6251
0x1801d622b  mov     rcx, [rbp+30h]; this
0x1801d622f  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d6236  mov     edx, 342h; void *
0x1801d623b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d6240  mov     ebx, eax
0x1801d6242  lea     rcx, [rbp+arg_8]
0x1801d6246  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d624b  nop
0x1801d624c  jmp     loc_1801D63B9
0x1801d6251  mov     [rbp+Overlapped.Internal], 0
0x1801d6259  mov     [rbp+Overlapped.InternalHigh], 0
0x1801d6261  mov     [rbp+Overlapped.hEvent], rbx
0x1801d6265  mov     qword ptr [rbp+Overlapped.10h], 0
0x1801d626d  lea     rax, [rbp+Overlapped]
0x1801d6271  mov     qword ptr [rsp+58h+lpOverlapped], rax; unsigned int
0x1801d6276  mov     r9, rsi; lpNumberOfBytesRead
0x1801d6279  mov     r8d, r14d; nNumberOfBytesToRead
0x1801d627c  mov     rdx, r15; lpBuffer
0x1801d627f  mov     rcx, rdi; hFile
0x1801d6282  call    cs:__imp_ReadFile
0x1801d6288  test    eax, eax
0x1801d628a  jnz     short loc_1801D62BF
0x1801d628c  call    cs:__imp_GetLastError
0x1801d6292  cmp     eax, 3E5h
0x1801d6297  jz      short loc_1801D62BF
0x1801d6299  mov     rcx, [rbp+30h]; this
0x1801d629d  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d62a4  mov     edx, 351h; void *
0x1801d62a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d62ae  mov     ebx, eax
0x1801d62b0  lea     rcx, [rbp+arg_8]
0x1801d62b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d62b9  nop
0x1801d62ba  jmp     loc_1801D63B9
0x1801d62bf  mov     edx, 2710h; dwMilliseconds
0x1801d62c4  mov     rcx, rbx; hHandle
0x1801d62c7  call    cs:__imp_WaitForSingleObject
0x1801d62cd  test    eax, eax
0x1801d62cf  jnz     short loc_1801D6313
0x1801d62d1  lea     r9d, [rax+1]; bWait
0x1801d62d5  mov     r8, rsi; lpNumberOfBytesTransferred
0x1801d62d8  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801d62dc  mov     rcx, rdi; hFile
0x1801d62df  call    cs:__imp_GetOverlappedResult
0x1801d62e5  test    eax, eax
0x1801d62e7  jnz     loc_1801D6387
0x1801d62ed  mov     rcx, [rbp+30h]; this
0x1801d62f1  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d62f8  mov     edx, 358h; void *
0x1801d62fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d6302  mov     ebx, eax
0x1801d6304  lea     rcx, [rbp+arg_8]
0x1801d6308  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d630d  nop
0x1801d630e  jmp     loc_1801D63B9
0x1801d6313  cmp     eax, 102h
0x1801d6318  jnz     short loc_1801D6395
0x1801d631a  mov     rcx, rdi; hFile
0x1801d631d  call    cs:__imp_CancelIo
0x1801d6323  test    eax, eax
0x1801d6325  jnz     short loc_1801D634A
0x1801d6327  mov     rcx, [rbp+30h]; this
0x1801d632b  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d6332  mov     edx, 35Dh; void *
0x1801d6337  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d633c  mov     ebx, eax
0x1801d633e  lea     rcx, [rbp+arg_8]
0x1801d6342  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d6347  nop
0x1801d6348  jmp     short loc_1801D63B9
0x1801d634a  mov     r9d, 1; bWait
0x1801d6350  mov     r8, rsi; lpNumberOfBytesTransferred
0x1801d6353  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801d6357  mov     rcx, rdi; hFile
0x1801d635a  call    cs:__imp_GetOverlappedResult
0x1801d6360  test    eax, eax
0x1801d6362  jnz     short loc_1801D6387
0x1801d6364  mov     rcx, [rbp+30h]; this
0x1801d6368  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d636f  mov     edx, 360h; void *
0x1801d6374  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d6379  mov     ebx, eax
0x1801d637b  lea     rcx, [rbp+arg_8]
0x1801d637f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d6384  nop
0x1801d6385  jmp     short loc_1801D63B9
0x1801d6387  lea     rcx, [rbp+arg_8]
0x1801d638b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d6390  nop
0x1801d6391  xor     eax, eax
0x1801d6393  jmp     short loc_1801D63BB
0x1801d6395  mov     rcx, [rbp+30h]; this
0x1801d6399  mov     r9d, eax; char *
0x1801d639c  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d63a3  mov     edx, 364h; void *
0x1801d63a8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801d63ad  mov     ebx, eax
0x1801d63af  lea     rcx, [rbp+arg_8]
0x1801d63b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d63b8  nop
0x1801d63b9  mov     eax, ebx
0x1801d63bb  add     rsp, 58h
0x1801d63bf  pop     r15
0x1801d63c1  pop     r14
0x1801d63c3  pop     rdi
0x1801d63c4  pop     rsi
0x1801d63c5  pop     rbx
0x1801d63c6  pop     rbp
0x1801d63c7  retn
```
