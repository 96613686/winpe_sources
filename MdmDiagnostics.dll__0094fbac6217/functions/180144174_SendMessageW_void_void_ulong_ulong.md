# SendMessageW(void *,void *,ulong,ulong *)

- ea: `0x180144174`
- end: `0x180144387`
- name: `?SendMessageW@@YAJPEAX0KPEAK@Z`
- size: `531`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180142d30`
- `0x180143204`
- `0x180143688`
- `0x180143984`
- `0x1801443d4`

## callees

- `0x1800e7cc0`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x180104108`
- `0x180144174`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180144242`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180144242`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180144287`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180144287`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801441d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801441d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014424c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014424c`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801442dc`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801442dc`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18014429e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180144319`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18014429e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180144319`

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
0x180144174  push    rbp
0x180144176  push    rbx
0x180144177  push    rsi
0x180144178  push    rdi
0x180144179  push    r14
0x18014417b  push    r15
0x18014417d  mov     rbp, rsp
0x180144180  sub     rsp, 58h
0x180144184  mov     rsi, r9
0x180144187  mov     r15d, r8d
0x18014418a  mov     r14, rdx
0x18014418d  mov     rdi, rcx
0x180144190  test    rdx, rdx
0x180144193  jnz     short loc_1801441B7
0x180144195  mov     edx, 308h; void *
0x18014419a  mov     ebx, 80070057h
0x18014419f  mov     rcx, [rbp+30h]; this
0x1801441a3  mov     r9d, ebx; char *
0x1801441a6  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801441ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801441b2  jmp     loc_180144378
0x1801441b7  test    rsi, rsi
0x1801441ba  jnz     short loc_1801441C3
0x1801441bc  mov     edx, 309h
0x1801441c1  jmp     short loc_18014419A
0x1801441c3  test    rdi, rdi
0x1801441c6  jnz     short loc_1801441CF
0x1801441c8  mov     edx, 30Ah
0x1801441cd  jmp     short loc_18014419A
0x1801441cf  xor     r9d, r9d; lpName
0x1801441d2  xor     r8d, r8d; bInitialState
0x1801441d5  xor     edx, edx; bManualReset
0x1801441d7  xor     ecx, ecx; lpEventAttributes
0x1801441d9  call    cs:__imp_CreateEventW
0x1801441df  mov     rbx, rax
0x1801441e2  mov     [rbp+arg_8], rax
0x1801441e6  test    rax, rax
0x1801441e9  jnz     short loc_180144211
0x1801441eb  mov     rcx, [rbp+30h]; this
0x1801441ef  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801441f6  mov     edx, 30Eh; void *
0x1801441fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180144200  mov     ebx, eax
0x180144202  lea     rcx, [rbp+arg_8]
0x180144206  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014420b  nop
0x18014420c  jmp     loc_180144378
0x180144211  mov     [rbp+Overlapped.Internal], 0
0x180144219  mov     [rbp+Overlapped.InternalHigh], 0
0x180144221  mov     [rbp+Overlapped.hEvent], rbx
0x180144225  mov     qword ptr [rbp+Overlapped.10h], 0
0x18014422d  lea     rax, [rbp+Overlapped]
0x180144231  mov     qword ptr [rsp+58h+lpOverlapped], rax; unsigned int
0x180144236  mov     r9, rsi; lpNumberOfBytesWritten
0x180144239  mov     r8d, r15d; nNumberOfBytesToWrite
0x18014423c  mov     rdx, r14; lpBuffer
0x18014423f  mov     rcx, rdi; hFile
0x180144242  call    cs:__imp_WriteFile
0x180144248  test    eax, eax
0x18014424a  jnz     short loc_18014427F
0x18014424c  call    cs:__imp_GetLastError
0x180144252  cmp     eax, 3E5h
0x180144257  jz      short loc_18014427F
0x180144259  mov     rcx, [rbp+30h]; this
0x18014425d  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180144264  mov     edx, 31Dh; void *
0x180144269  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18014426e  mov     ebx, eax
0x180144270  lea     rcx, [rbp+arg_8]
0x180144274  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180144279  nop
0x18014427a  jmp     loc_180144378
0x18014427f  mov     edx, 2710h; dwMilliseconds
0x180144284  mov     rcx, rbx; hHandle
0x180144287  call    cs:__imp_WaitForSingleObject
0x18014428d  test    eax, eax
0x18014428f  jnz     short loc_1801442D2
0x180144291  xor     r9d, r9d; bWait
0x180144294  mov     r8, rsi; lpNumberOfBytesTransferred
0x180144297  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18014429b  mov     rcx, rdi; hFile
0x18014429e  call    cs:__imp_GetOverlappedResult
0x1801442a4  test    eax, eax
0x1801442a6  jnz     loc_180144346
0x1801442ac  mov     rcx, [rbp+30h]; this
0x1801442b0  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801442b7  mov     edx, 324h; void *
0x1801442bc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801442c1  mov     ebx, eax
0x1801442c3  lea     rcx, [rbp+arg_8]
0x1801442c7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801442cc  nop
0x1801442cd  jmp     loc_180144378
0x1801442d2  cmp     eax, 102h
0x1801442d7  jnz     short loc_180144354
0x1801442d9  mov     rcx, rdi; hFile
0x1801442dc  call    cs:__imp_CancelIo
0x1801442e2  test    eax, eax
0x1801442e4  jnz     short loc_180144309
0x1801442e6  mov     rcx, [rbp+30h]; this
0x1801442ea  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801442f1  mov     edx, 329h; void *
0x1801442f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801442fb  mov     ebx, eax
0x1801442fd  lea     rcx, [rbp+arg_8]
0x180144301  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180144306  nop
0x180144307  jmp     short loc_180144378
0x180144309  mov     r9d, 1; bWait
0x18014430f  mov     r8, rsi; lpNumberOfBytesTransferred
0x180144312  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180144316  mov     rcx, rdi; hFile
0x180144319  call    cs:__imp_GetOverlappedResult
0x18014431f  test    eax, eax
0x180144321  jnz     short loc_180144346
0x180144323  mov     rcx, [rbp+30h]; this
0x180144327  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18014432e  mov     edx, 32Ch; void *
0x180144333  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180144338  mov     ebx, eax
0x18014433a  lea     rcx, [rbp+arg_8]
0x18014433e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180144343  nop
0x180144344  jmp     short loc_180144378
0x180144346  lea     rcx, [rbp+arg_8]
0x18014434a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014434f  nop
0x180144350  xor     eax, eax
0x180144352  jmp     short loc_18014437A
0x180144354  mov     rcx, [rbp+30h]; this
0x180144358  mov     r9d, eax; char *
0x18014435b  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180144362  mov     edx, 330h; void *
0x180144367  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18014436c  mov     ebx, eax
0x18014436e  lea     rcx, [rbp+arg_8]
0x180144372  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180144377  nop
0x180144378  mov     eax, ebx
0x18014437a  add     rsp, 58h
0x18014437e  pop     r15
0x180144380  pop     r14
0x180144382  pop     rdi
0x180144383  pop     rsi
0x180144384  pop     rbx
0x180144385  pop     rbp
0x180144386  retn
```
