# SendMessageW(void *,void *,ulong,ulong *)

- ea: `0x1801d6630`
- end: `0x1801d6843`
- name: `?SendMessageW@@YAJPEAX0KPEAK@Z`
- size: `531`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesTransferred)`
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
- `0x1801d6630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801d6695`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801d6695`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801d6743`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801d6743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d6708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d6708`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801d66fe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801d66fe`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d675a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d67d5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d675a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d67d5`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801d6798`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801d6798`

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
0x1801d6630  push    rbp
0x1801d6632  push    rbx
0x1801d6633  push    rsi
0x1801d6634  push    rdi
0x1801d6635  push    r14
0x1801d6637  push    r15
0x1801d6639  mov     rbp, rsp
0x1801d663c  sub     rsp, 58h
0x1801d6640  mov     rsi, r9
0x1801d6643  mov     r15d, r8d
0x1801d6646  mov     r14, rdx
0x1801d6649  mov     rdi, rcx
0x1801d664c  test    rdx, rdx
0x1801d664f  jnz     short loc_1801D6673
0x1801d6651  mov     edx, 308h; void *
0x1801d6656  mov     ebx, 80070057h
0x1801d665b  mov     rcx, [rbp+30h]; this
0x1801d665f  mov     r9d, ebx; char *
0x1801d6662  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d6669  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d666e  jmp     loc_1801D6834
0x1801d6673  test    rsi, rsi
0x1801d6676  jnz     short loc_1801D667F
0x1801d6678  mov     edx, 309h
0x1801d667d  jmp     short loc_1801D6656
0x1801d667f  test    rdi, rdi
0x1801d6682  jnz     short loc_1801D668B
0x1801d6684  mov     edx, 30Ah
0x1801d6689  jmp     short loc_1801D6656
0x1801d668b  xor     r9d, r9d; lpName
0x1801d668e  xor     r8d, r8d; bInitialState
0x1801d6691  xor     edx, edx; bManualReset
0x1801d6693  xor     ecx, ecx; lpEventAttributes
0x1801d6695  call    cs:__imp_CreateEventW
0x1801d669b  mov     rbx, rax
0x1801d669e  mov     [rbp+arg_8], rax
0x1801d66a2  test    rax, rax
0x1801d66a5  jnz     short loc_1801D66CD
0x1801d66a7  mov     rcx, [rbp+30h]; this
0x1801d66ab  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d66b2  mov     edx, 30Eh; void *
0x1801d66b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d66bc  mov     ebx, eax
0x1801d66be  lea     rcx, [rbp+arg_8]
0x1801d66c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d66c7  nop
0x1801d66c8  jmp     loc_1801D6834
0x1801d66cd  mov     [rbp+Overlapped.Internal], 0
0x1801d66d5  mov     [rbp+Overlapped.InternalHigh], 0
0x1801d66dd  mov     [rbp+Overlapped.hEvent], rbx
0x1801d66e1  mov     qword ptr [rbp+Overlapped.10h], 0
0x1801d66e9  lea     rax, [rbp+Overlapped]
0x1801d66ed  mov     qword ptr [rsp+58h+lpOverlapped], rax; unsigned int
0x1801d66f2  mov     r9, rsi; lpNumberOfBytesWritten
0x1801d66f5  mov     r8d, r15d; nNumberOfBytesToWrite
0x1801d66f8  mov     rdx, r14; lpBuffer
0x1801d66fb  mov     rcx, rdi; hFile
0x1801d66fe  call    cs:__imp_WriteFile
0x1801d6704  test    eax, eax
0x1801d6706  jnz     short loc_1801D673B
0x1801d6708  call    cs:__imp_GetLastError
0x1801d670e  cmp     eax, 3E5h
0x1801d6713  jz      short loc_1801D673B
0x1801d6715  mov     rcx, [rbp+30h]; this
0x1801d6719  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d6720  mov     edx, 31Dh; void *
0x1801d6725  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d672a  mov     ebx, eax
0x1801d672c  lea     rcx, [rbp+arg_8]
0x1801d6730  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d6735  nop
0x1801d6736  jmp     loc_1801D6834
0x1801d673b  mov     edx, 2710h; dwMilliseconds
0x1801d6740  mov     rcx, rbx; hHandle
0x1801d6743  call    cs:__imp_WaitForSingleObject
0x1801d6749  test    eax, eax
0x1801d674b  jnz     short loc_1801D678E
0x1801d674d  xor     r9d, r9d; bWait
0x1801d6750  mov     r8, rsi; lpNumberOfBytesTransferred
0x1801d6753  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801d6757  mov     rcx, rdi; hFile
0x1801d675a  call    cs:__imp_GetOverlappedResult
0x1801d6760  test    eax, eax
0x1801d6762  jnz     loc_1801D6802
0x1801d6768  mov     rcx, [rbp+30h]; this
0x1801d676c  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d6773  mov     edx, 324h; void *
0x1801d6778  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d677d  mov     ebx, eax
0x1801d677f  lea     rcx, [rbp+arg_8]
0x1801d6783  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d6788  nop
0x1801d6789  jmp     loc_1801D6834
0x1801d678e  cmp     eax, 102h
0x1801d6793  jnz     short loc_1801D6810
0x1801d6795  mov     rcx, rdi; hFile
0x1801d6798  call    cs:__imp_CancelIo
0x1801d679e  test    eax, eax
0x1801d67a0  jnz     short loc_1801D67C5
0x1801d67a2  mov     rcx, [rbp+30h]; this
0x1801d67a6  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d67ad  mov     edx, 329h; void *
0x1801d67b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d67b7  mov     ebx, eax
0x1801d67b9  lea     rcx, [rbp+arg_8]
0x1801d67bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d67c2  nop
0x1801d67c3  jmp     short loc_1801D6834
0x1801d67c5  mov     r9d, 1; bWait
0x1801d67cb  mov     r8, rsi; lpNumberOfBytesTransferred
0x1801d67ce  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801d67d2  mov     rcx, rdi; hFile
0x1801d67d5  call    cs:__imp_GetOverlappedResult
0x1801d67db  test    eax, eax
0x1801d67dd  jnz     short loc_1801D6802
0x1801d67df  mov     rcx, [rbp+30h]; this
0x1801d67e3  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d67ea  mov     edx, 32Ch; void *
0x1801d67ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d67f4  mov     ebx, eax
0x1801d67f6  lea     rcx, [rbp+arg_8]
0x1801d67fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d67ff  nop
0x1801d6800  jmp     short loc_1801D6834
0x1801d6802  lea     rcx, [rbp+arg_8]
0x1801d6806  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d680b  nop
0x1801d680c  xor     eax, eax
0x1801d680e  jmp     short loc_1801D6836
0x1801d6810  mov     rcx, [rbp+30h]; this
0x1801d6814  mov     r9d, eax; char *
0x1801d6817  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d681e  mov     edx, 330h; void *
0x1801d6823  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801d6828  mov     ebx, eax
0x1801d682a  lea     rcx, [rbp+arg_8]
0x1801d682e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801d6833  nop
0x1801d6834  mov     eax, ebx
0x1801d6836  add     rsp, 58h
0x1801d683a  pop     r15
0x1801d683c  pop     r14
0x1801d683e  pop     rdi
0x1801d683f  pop     rsi
0x1801d6840  pop     rbx
0x1801d6841  pop     rbp
0x1801d6842  retn
```
