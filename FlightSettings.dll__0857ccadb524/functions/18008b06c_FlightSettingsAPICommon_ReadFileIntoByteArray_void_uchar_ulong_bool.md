# FlightSettingsAPICommon::ReadFileIntoByteArray(void *,uchar * *,ulong *,bool)

- ea: `0x18008b06c`
- end: `0x18008b20b`
- name: `?ReadFileIntoByteArray@FlightSettingsAPICommon@@CAJPEAXPEAPEAEPEAK_N@Z`
- size: `415`
- prototype: `__int64 __fastcall(HANDLE hFile, unsigned __int8 **, unsigned int *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18008afb0`
- `0x18008b214`

## callees

- `0x18000cc6c`
- `0x18000cc8c`
- `0x180016898`
- `0x18002f830`
- `0x180085564`
- `0x18008b06c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008b0a0`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008b0a0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008b19c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008b19c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b179`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b179`

## string_xrefs

- `0x18008b0ae`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`
- `0x18008b0dc`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`
- `0x18008b154`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`
- `0x18008b1aa`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FlightSettingsAPICommon::ReadFileIntoByteArray(HANDLE hFile, LPVOID *a2, unsigned int *a3, char a4)
{
  const char *v8; // r9
  DWORD LowPart; // eax
  int LastError; // ebx
  unsigned int v12; // esi
  void *v13; // rcx
  unsigned int v14; // r10d
  __int64 v15; // rdx
  void *v16; // rcx
  const char *v17; // r9
  int lpOverlapped; // [rsp+20h] [rbp-40h]
  union _LARGE_INTEGER FileSize; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-28h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-20h] BYREF
  void *v22; // [rsp+48h] [rbp-18h] BYREF
  char v23; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp+50h] BYREF

  *a3 = 0;
  *a2 = 0;
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(hFile, &FileSize) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x287,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
             v8);
  LowPart = FileSize.LowPart;
  if ( FileSize.QuadPart > 0x400000 )
  {
    LastError = -2146698737;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28A,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
      (const char *)0x800BFA0FLL,
      lpOverlapped);
    return (unsigned int)LastError;
  }
  if ( a4 )
    LowPart = FileSize.LowPart + 1;
  pv = 0;
  p_pv = &pv;
  v23 = 1;
  v22 = 0;
  v20 = 0;
  v12 = LowPart;
  LastError = ULongLongMult(LowPart, 1u, &v20);
  if ( LastError >= 0 )
    LastError = CTCoAllocPolicy::Alloc(v13, v14, v20, &v22);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( LastError < 0 )
  {
    v15 = 655;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
      (const char *)(unsigned int)LastError,
      lpOverlapped);
    goto LABEL_13;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(hFile, pv, FileSize.LowPart, &NumberOfBytesRead, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x292,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
                  v17);
LABEL_13:
    v16 = pv;
    pv = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    return (unsigned int)LastError;
  }
  if ( FileSize.QuadPart != NumberOfBytesRead )
  {
    LastError = -2147467259;
    v15 = 659;
    goto LABEL_12;
  }
  if ( a4 )
    *((_BYTE *)pv + FileSize.QuadPart) = 0;
  *a3 = v12;
  *a2 = pv;
  return 0;
}

```

## disassembly

```asm
0x18008b06c  mov     [rsp-38h+arg_0], rbx
0x18008b071  push    rbp
0x18008b072  push    rsi
0x18008b073  push    rdi
0x18008b074  push    r12
0x18008b076  push    r13
0x18008b078  push    r14
0x18008b07a  push    r15
0x18008b07c  mov     rbp, rsp
0x18008b07f  sub     rsp, 60h
0x18008b083  mov     dil, r9b
0x18008b086  mov     r14, r8
0x18008b089  mov     r15, rdx
0x18008b08c  mov     r12, rcx
0x18008b08f  xor     r13d, r13d
0x18008b092  mov     [r8], r13d
0x18008b095  mov     [rdx], r13
0x18008b098  mov     qword ptr [rbp+FileSize], r13
0x18008b09c  lea     rdx, [rbp+FileSize]; lpFileSize
0x18008b0a0  call    cs:__imp_GetFileSizeEx
0x18008b0a6  test    eax, eax
0x18008b0a8  jnz     short loc_18008B0C4
0x18008b0aa  mov     rcx, [rbp+38h]; this
0x18008b0ae  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x18008b0b5  mov     edx, 287h; void *
0x18008b0ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008b0bf  jmp     loc_18008B1F3
0x18008b0c4  mov     rax, qword ptr [rbp+FileSize]
0x18008b0c8  cmp     rax, 400000h
0x18008b0ce  jle     short loc_18008B0F4
0x18008b0d0  mov     rcx, [rbp+38h]; this
0x18008b0d4  mov     ebx, 800BFA0Fh
0x18008b0d9  mov     r9d, ebx; char *
0x18008b0dc  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x18008b0e3  mov     edx, 28Ah; void *
0x18008b0e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b0ed  mov     eax, ebx
0x18008b0ef  jmp     loc_18008B1F3
0x18008b0f4  test    dil, dil
0x18008b0f7  jz      short loc_18008B0FC
0x18008b0f9  inc     rax
0x18008b0fc  mov     [rbp+pv], r13
0x18008b100  lea     rcx, [rbp+pv]
0x18008b104  mov     [rbp+var_20], rcx
0x18008b108  mov     r10d, 1
0x18008b10e  mov     [rbp+var_10], r10b
0x18008b112  mov     [rbp+var_18], r13
0x18008b116  mov     [rbp+var_28], r13
0x18008b11a  mov     esi, eax
0x18008b11c  mov     ecx, eax; unsigned __int64
0x18008b11e  lea     r8, [rbp+var_28]; unsigned __int64 *
0x18008b122  mov     edx, r10d; unsigned __int64
0x18008b125  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18008b12a  mov     ebx, eax
0x18008b12c  test    eax, eax
0x18008b12e  js      short loc_18008B142
0x18008b130  lea     r9, [rbp+var_18]; void **
0x18008b134  mov     r8, [rbp+var_28]; unsigned __int64
0x18008b138  mov     edx, r10d; unsigned int
0x18008b13b  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18008b140  mov     ebx, eax
0x18008b142  lea     rcx, [rbp+var_20]
0x18008b146  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18008b14b  test    ebx, ebx
0x18008b14d  jns     short loc_18008B184
0x18008b14f  mov     edx, 28Fh; void *
0x18008b154  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x18008b15b  mov     r9d, ebx; char *
0x18008b15e  mov     rcx, [rbp+38h]; this
0x18008b162  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b167  nop
0x18008b168  mov     rcx, [rbp+pv]; pv
0x18008b16c  mov     [rbp+pv], r13
0x18008b170  test    rcx, rcx
0x18008b173  jz      loc_18008B0ED
0x18008b179  call    cs:__imp_CoTaskMemFree
0x18008b17f  jmp     loc_18008B0ED
0x18008b184  mov     [rbp+NumberOfBytesRead], r13d
0x18008b188  mov     qword ptr [rsp+60h+lpOverlapped], r13; lpOverlapped
0x18008b18d  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008b191  mov     r8d, dword ptr [rbp+FileSize]; nNumberOfBytesToRead
0x18008b195  mov     rdx, [rbp+pv]; lpBuffer
0x18008b199  mov     rcx, r12; hFile
0x18008b19c  call    cs:__imp_ReadFile
0x18008b1a2  test    eax, eax
0x18008b1a4  jnz     short loc_18008B1BF
0x18008b1a6  mov     rcx, [rbp+38h]; this
0x18008b1aa  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x18008b1b1  mov     edx, 292h; void *
0x18008b1b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008b1bb  mov     ebx, eax
0x18008b1bd  jmp     short loc_18008B168
0x18008b1bf  mov     ecx, [rbp+NumberOfBytesRead]
0x18008b1c2  mov     rax, qword ptr [rbp+FileSize]
0x18008b1c6  cmp     rax, rcx
0x18008b1c9  jz      short loc_18008B1DA
0x18008b1cb  mov     ebx, 80004005h
0x18008b1d0  mov     edx, 293h
0x18008b1d5  jmp     loc_18008B154
0x18008b1da  test    dil, dil
0x18008b1dd  jz      short loc_18008B1E7
0x18008b1df  mov     rcx, [rbp+pv]
0x18008b1e3  mov     [rcx+rax], r13b
0x18008b1e7  mov     [r14], esi
0x18008b1ea  mov     rax, [rbp+pv]
0x18008b1ee  mov     [r15], rax
0x18008b1f1  xor     eax, eax
0x18008b1f3  mov     rbx, [rsp+60h+arg_0]
0x18008b1fb  add     rsp, 60h
0x18008b1ff  pop     r15
0x18008b201  pop     r14
0x18008b203  pop     r13
0x18008b205  pop     r12
0x18008b207  pop     rdi
0x18008b208  pop     rsi
0x18008b209  pop     rbp
0x18008b20a  retn
```
