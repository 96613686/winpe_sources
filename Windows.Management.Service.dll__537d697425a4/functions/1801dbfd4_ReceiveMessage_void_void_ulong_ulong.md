# ReceiveMessage(void *,void *,ulong,ulong *)

- ea: `0x1801dbfd4`
- end: `0x1801dc223`
- name: `?ReceiveMessage@@YAJPEAX0KPEAK@Z`
- size: `591`
- prototype: `__int64 __fastcall(HANDLE hFile, void *lpBuffer, DWORD nNumberOfBytesToRead, LPDWORD lpNumberOfBytesTransferred)`
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
- `0x1801dbfd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801dc045`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801dc045`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801dc105`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801dc105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc0c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc0c4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801dc0b4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801dc0b4`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc123`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc1ae`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc123`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc1ae`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801dc16b`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801dc16b`

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
0x1801dbfd4  push    rbp
0x1801dbfd6  push    rbx
0x1801dbfd7  push    rsi
0x1801dbfd8  push    rdi
0x1801dbfd9  push    r14
0x1801dbfdb  push    r15
0x1801dbfdd  mov     rbp, rsp
0x1801dbfe0  sub     rsp, 58h
0x1801dbfe4  mov     rsi, r9
0x1801dbfe7  mov     r14d, r8d
0x1801dbfea  mov     r15, rdx
0x1801dbfed  mov     rdi, rcx
0x1801dbff0  test    rdx, rdx
0x1801dbff3  jnz     short loc_1801DC017
0x1801dbff5  mov     edx, 33Ch; void *
0x1801dbffa  mov     ebx, 80070057h
0x1801dbfff  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc006  mov     r9d, ebx; char *
0x1801dc009  mov     rcx, [rbp+30h]; this
0x1801dc00d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dc012  jmp     loc_1801DC213
0x1801dc017  test    rsi, rsi
0x1801dc01a  jnz     short loc_1801DC023
0x1801dc01c  mov     edx, 33Dh
0x1801dc021  jmp     short loc_1801DBFFA
0x1801dc023  test    rdi, rdi
0x1801dc026  jnz     short loc_1801DC02F
0x1801dc028  mov     edx, 33Eh
0x1801dc02d  jmp     short loc_1801DBFFA
0x1801dc02f  test    r14d, r14d
0x1801dc032  jnz     short loc_1801DC03B
0x1801dc034  mov     edx, 33Fh
0x1801dc039  jmp     short loc_1801DBFFA
0x1801dc03b  xor     r9d, r9d; lpName
0x1801dc03e  xor     r8d, r8d; bInitialState
0x1801dc041  xor     edx, edx; bManualReset
0x1801dc043  xor     ecx, ecx; lpEventAttributes
0x1801dc045  call    cs:__imp_CreateEventW
0x1801dc04c  nop     dword ptr [rax+rax+00h]
0x1801dc051  mov     rbx, rax
0x1801dc054  mov     [rbp+arg_8], rax
0x1801dc058  test    rax, rax
0x1801dc05b  jnz     short loc_1801DC083
0x1801dc05d  mov     rcx, [rbp+30h]; this
0x1801dc061  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc068  mov     edx, 342h; void *
0x1801dc06d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc072  mov     ebx, eax
0x1801dc074  lea     rcx, [rbp+arg_8]
0x1801dc078  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc07d  nop
0x1801dc07e  jmp     loc_1801DC213
0x1801dc083  mov     [rbp+Overlapped.Internal], 0
0x1801dc08b  mov     [rbp+Overlapped.InternalHigh], 0
0x1801dc093  mov     [rbp+Overlapped.hEvent], rbx
0x1801dc097  mov     qword ptr [rbp+Overlapped.10h], 0
0x1801dc09f  lea     rax, [rbp+Overlapped]
0x1801dc0a3  mov     qword ptr [rsp+58h+lpOverlapped], rax; unsigned int
0x1801dc0a8  mov     r9, rsi; lpNumberOfBytesRead
0x1801dc0ab  mov     r8d, r14d; nNumberOfBytesToRead
0x1801dc0ae  mov     rdx, r15; lpBuffer
0x1801dc0b1  mov     rcx, rdi; hFile
0x1801dc0b4  call    cs:__imp_ReadFile
0x1801dc0bb  nop     dword ptr [rax+rax+00h]
0x1801dc0c0  test    eax, eax
0x1801dc0c2  jnz     short loc_1801DC0FD
0x1801dc0c4  call    cs:__imp_GetLastError
0x1801dc0cb  nop     dword ptr [rax+rax+00h]
0x1801dc0d0  cmp     eax, 3E5h
0x1801dc0d5  jz      short loc_1801DC0FD
0x1801dc0d7  mov     rcx, [rbp+30h]; this
0x1801dc0db  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc0e2  mov     edx, 351h; void *
0x1801dc0e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc0ec  mov     ebx, eax
0x1801dc0ee  lea     rcx, [rbp+arg_8]
0x1801dc0f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc0f7  nop
0x1801dc0f8  jmp     loc_1801DC213
0x1801dc0fd  mov     edx, 2710h; dwMilliseconds
0x1801dc102  mov     rcx, rbx; hHandle
0x1801dc105  call    cs:__imp_WaitForSingleObject
0x1801dc10c  nop     dword ptr [rax+rax+00h]
0x1801dc111  test    eax, eax
0x1801dc113  jnz     short loc_1801DC15D
0x1801dc115  lea     r9d, [rax+1]; bWait
0x1801dc119  mov     r8, rsi; lpNumberOfBytesTransferred
0x1801dc11c  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801dc120  mov     rcx, rdi; hFile
0x1801dc123  call    cs:__imp_GetOverlappedResult
0x1801dc12a  nop     dword ptr [rax+rax+00h]
0x1801dc12f  test    eax, eax
0x1801dc131  jnz     loc_1801DC1E1
0x1801dc137  mov     rcx, [rbp+30h]; this
0x1801dc13b  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc142  mov     edx, 358h; void *
0x1801dc147  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc14c  mov     ebx, eax
0x1801dc14e  lea     rcx, [rbp+arg_8]
0x1801dc152  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc157  nop
0x1801dc158  jmp     loc_1801DC213
0x1801dc15d  cmp     eax, 102h
0x1801dc162  jnz     loc_1801DC1EF
0x1801dc168  mov     rcx, rdi; hFile
0x1801dc16b  call    cs:__imp_CancelIo
0x1801dc172  nop     dword ptr [rax+rax+00h]
0x1801dc177  test    eax, eax
0x1801dc179  jnz     short loc_1801DC19E
0x1801dc17b  mov     rcx, [rbp+30h]; this
0x1801dc17f  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc186  mov     edx, 35Dh; void *
0x1801dc18b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc190  mov     ebx, eax
0x1801dc192  lea     rcx, [rbp+arg_8]
0x1801dc196  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc19b  nop
0x1801dc19c  jmp     short loc_1801DC213
0x1801dc19e  mov     r9d, 1; bWait
0x1801dc1a4  mov     r8, rsi; lpNumberOfBytesTransferred
0x1801dc1a7  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801dc1ab  mov     rcx, rdi; hFile
0x1801dc1ae  call    cs:__imp_GetOverlappedResult
0x1801dc1b5  nop     dword ptr [rax+rax+00h]
0x1801dc1ba  test    eax, eax
0x1801dc1bc  jnz     short loc_1801DC1E1
0x1801dc1be  mov     rcx, [rbp+30h]; this
0x1801dc1c2  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc1c9  mov     edx, 360h; void *
0x1801dc1ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc1d3  mov     ebx, eax
0x1801dc1d5  lea     rcx, [rbp+arg_8]
0x1801dc1d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc1de  nop
0x1801dc1df  jmp     short loc_1801DC213
0x1801dc1e1  lea     rcx, [rbp+arg_8]
0x1801dc1e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc1ea  nop
0x1801dc1eb  xor     eax, eax
0x1801dc1ed  jmp     short loc_1801DC215
0x1801dc1ef  mov     rcx, [rbp+30h]; this
0x1801dc1f3  mov     r9d, eax; char *
0x1801dc1f6  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dc1fd  mov     edx, 364h; void *
0x1801dc202  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801dc207  mov     ebx, eax
0x1801dc209  lea     rcx, [rbp+arg_8]
0x1801dc20d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801dc212  nop
0x1801dc213  mov     eax, ebx
0x1801dc215  add     rsp, 58h
0x1801dc219  pop     r15
0x1801dc21b  pop     r14
0x1801dc21d  pop     rdi
0x1801dc21e  pop     rsi
0x1801dc21f  pop     rbx
0x1801dc220  pop     rbp
0x1801dc221  retn
```
