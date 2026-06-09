# MitigationAPICommon::ReadFileIntoByteArray(void *,uchar * *,ulong *,bool)

- ea: `0x18003b6f0`
- end: `0x18003b8b3`
- name: `?ReadFileIntoByteArray@MitigationAPICommon@@SAJPEAXPEAPEAEPEAK_N@Z`
- size: `451`
- prototype: `__int64 __fastcall(HANDLE hFile, unsigned __int8 **, unsigned int *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002bd64`
- `0x18003b8bc`

## callees

- `0x18001206c`
- `0x18001208c`
- `0x180016c30`
- `0x18002545c`
- `0x18002b180`
- `0x18003b6f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b7f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b84c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b7f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b84c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003b724`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003b724`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003b81c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003b81c`

## string_xrefs

- `0x18003b732`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\mitigationapicommon.cpp`
- `0x18003b75f`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\mitigationapicommon.cpp`
- `0x18003b7d8`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\mitigationapicommon.cpp`
- `0x18003b82a`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\mitigationapicommon.cpp`
- `0x18003b86f`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\mitigationapicommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MitigationAPICommon::ReadFileIntoByteArray(HANDLE hFile, LPVOID *a2, unsigned int *a3, char a4)
{
  const char *v8; // r9
  unsigned __int64 QuadPart; // rbx
  unsigned int LastError; // ebx
  void *v12; // rcx
  int v13; // edi
  unsigned int v14; // r10d
  void *v15; // rcx
  const char *v16; // r9
  void *v17; // rcx
  int lpOverlapped; // [rsp+20h] [rbp-40h]
  int lpOverlappeda; // [rsp+20h] [rbp-40h]
  union _LARGE_INTEGER FileSize; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-28h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-20h] BYREF
  void *v23; // [rsp+48h] [rbp-18h] BYREF
  char v24; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp+50h] BYREF

  *a3 = 0;
  *a2 = 0;
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(hFile, &FileSize) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x45,
             (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\mitigationapicommon.cpp",
             v8);
  QuadPart = FileSize.QuadPart;
  if ( FileSize.QuadPart > 0x400000 )
  {
    LastError = -2135164401;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\mitigationapicommon.cpp",
      (const char *)0x80BBFA0FLL,
      lpOverlapped);
    return LastError;
  }
  pv = 0;
  if ( a4 )
    QuadPart = FileSize.QuadPart + 1;
  p_pv = &pv;
  v24 = 1;
  v23 = 0;
  v21 = 0;
  v13 = ULongLongMult(QuadPart, 1u, &v21);
  if ( v13 >= 0 )
    v13 = CTCoAllocPolicy::Alloc(v12, v14, v21, &v23);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\mitigationapicommon.cpp",
      (const char *)(unsigned int)v13,
      lpOverlapped);
    v15 = pv;
    pv = 0;
    if ( v15 )
      CoTaskMemFree(v15);
    return (unsigned int)v13;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(hFile, pv, FileSize.LowPart, &NumberOfBytesRead, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4F,
                  (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\mitigationapicommon.cpp",
                  v16);
    goto LABEL_16;
  }
  if ( FileSize.QuadPart != NumberOfBytesRead )
  {
    LastError = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\mitigationapicommon.cpp",
      (const char *)0x80004005LL,
      lpOverlappeda);
LABEL_16:
    v17 = pv;
    pv = 0;
    if ( v17 )
      CoTaskMemFree(v17);
    return LastError;
  }
  if ( a4 )
    *((_BYTE *)pv + FileSize.QuadPart) = 0;
  *a3 = QuadPart;
  *a2 = pv;
  return 0;
}

```

## disassembly

```asm
0x18003b6f0  mov     [rsp-38h+arg_0], rbx
0x18003b6f5  push    rbp
0x18003b6f6  push    rsi
0x18003b6f7  push    rdi
0x18003b6f8  push    r12
0x18003b6fa  push    r13
0x18003b6fc  push    r14
0x18003b6fe  push    r15
0x18003b700  mov     rbp, rsp
0x18003b703  sub     rsp, 60h
0x18003b707  mov     sil, r9b
0x18003b70a  mov     r14, r8
0x18003b70d  mov     r15, rdx
0x18003b710  mov     r12, rcx
0x18003b713  xor     r13d, r13d
0x18003b716  mov     [r8], r13d
0x18003b719  mov     [rdx], r13
0x18003b71c  mov     qword ptr [rbp+FileSize], r13
0x18003b720  lea     rdx, [rbp+FileSize]; lpFileSize
0x18003b724  call    cs:__imp_GetFileSizeEx
0x18003b72a  test    eax, eax
0x18003b72c  jnz     short loc_18003B746
0x18003b72e  mov     rcx, [rbp+38h]; this
0x18003b732  lea     r8, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003b739  lea     edx, [rax+45h]; void *
0x18003b73c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b741  jmp     loc_18003B89B
0x18003b746  mov     rbx, qword ptr [rbp+FileSize]
0x18003b74a  cmp     rbx, 400000h
0x18003b751  jle     short loc_18003B777
0x18003b753  mov     rcx, [rbp+38h]; this
0x18003b757  mov     ebx, 80BBFA0Fh
0x18003b75c  mov     r9d, ebx; char *
0x18003b75f  lea     r8, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003b766  mov     edx, 48h ; 'H'; void *
0x18003b76b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b770  mov     eax, ebx
0x18003b772  jmp     loc_18003B89B
0x18003b777  mov     [rbp+pv], r13
0x18003b77b  test    sil, sil
0x18003b77e  jz      short loc_18003B783
0x18003b780  inc     rbx
0x18003b783  lea     rax, [rbp+pv]
0x18003b787  mov     [rbp+var_20], rax
0x18003b78b  mov     r10d, 1
0x18003b791  mov     [rbp+var_10], r10b
0x18003b795  mov     [rbp+var_18], r13
0x18003b799  mov     [rbp+var_28], r13
0x18003b79d  lea     r8, [rbp+var_28]; unsigned __int64 *
0x18003b7a1  mov     edx, r10d; unsigned __int64
0x18003b7a4  mov     rcx, rbx; unsigned __int64
0x18003b7a7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003b7ac  mov     edi, eax
0x18003b7ae  test    eax, eax
0x18003b7b0  js      short loc_18003B7C4
0x18003b7b2  lea     r9, [rbp+var_18]; void **
0x18003b7b6  mov     r8, [rbp+var_28]; unsigned __int64
0x18003b7ba  mov     edx, r10d; unsigned int
0x18003b7bd  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003b7c2  mov     edi, eax
0x18003b7c4  lea     rcx, [rbp+var_20]
0x18003b7c8  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003b7cd  test    edi, edi
0x18003b7cf  jns     short loc_18003B804
0x18003b7d1  mov     rcx, [rbp+38h]; this
0x18003b7d5  mov     r9d, edi; char *
0x18003b7d8  lea     r8, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003b7df  mov     edx, 4Ch ; 'L'; void *
0x18003b7e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b7e9  nop
0x18003b7ea  mov     rcx, [rbp+pv]; pv
0x18003b7ee  mov     [rbp+pv], r13
0x18003b7f2  test    rcx, rcx
0x18003b7f5  jz      short loc_18003B7FD
0x18003b7f7  call    cs:__imp_CoTaskMemFree
0x18003b7fd  mov     eax, edi
0x18003b7ff  jmp     loc_18003B89B
0x18003b804  mov     [rbp+NumberOfBytesRead], r13d
0x18003b808  mov     qword ptr [rsp+60h+lpOverlapped], r13; int
0x18003b80d  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003b811  mov     r8d, dword ptr [rbp+FileSize]; nNumberOfBytesToRead
0x18003b815  mov     rdx, [rbp+pv]; lpBuffer
0x18003b819  mov     rcx, r12; hFile
0x18003b81c  call    cs:__imp_ReadFile
0x18003b822  test    eax, eax
0x18003b824  jnz     short loc_18003B857
0x18003b826  mov     rcx, [rbp+38h]; this
0x18003b82a  lea     r8, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003b831  lea     edx, [rax+4Fh]; void *
0x18003b834  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b839  mov     ebx, eax
0x18003b83b  mov     rcx, [rbp+pv]; pv
0x18003b83f  mov     [rbp+pv], r13
0x18003b843  test    rcx, rcx
0x18003b846  jz      loc_18003B770
0x18003b84c  call    cs:__imp_CoTaskMemFree
0x18003b852  jmp     loc_18003B770
0x18003b857  mov     ecx, [rbp+NumberOfBytesRead]
0x18003b85a  mov     rax, qword ptr [rbp+FileSize]
0x18003b85e  cmp     rax, rcx
0x18003b861  jz      short loc_18003B882
0x18003b863  mov     rcx, [rbp+38h]; this
0x18003b867  mov     ebx, 80004005h
0x18003b86c  mov     r9d, ebx; char *
0x18003b86f  lea     r8, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003b876  mov     edx, 50h ; 'P'; void *
0x18003b87b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b880  jmp     short loc_18003B83B
0x18003b882  test    sil, sil
0x18003b885  jz      short loc_18003B88F
0x18003b887  mov     rcx, [rbp+pv]
0x18003b88b  mov     [rcx+rax], r13b
0x18003b88f  mov     [r14], ebx
0x18003b892  mov     rax, [rbp+pv]
0x18003b896  mov     [r15], rax
0x18003b899  xor     eax, eax
0x18003b89b  mov     rbx, [rsp+60h+arg_0]
0x18003b8a3  add     rsp, 60h
0x18003b8a7  pop     r15
0x18003b8a9  pop     r14
0x18003b8ab  pop     r13
0x18003b8ad  pop     r12
0x18003b8af  pop     rdi
0x18003b8b0  pop     rsi
0x18003b8b1  pop     rbp
0x18003b8b2  retn
```
