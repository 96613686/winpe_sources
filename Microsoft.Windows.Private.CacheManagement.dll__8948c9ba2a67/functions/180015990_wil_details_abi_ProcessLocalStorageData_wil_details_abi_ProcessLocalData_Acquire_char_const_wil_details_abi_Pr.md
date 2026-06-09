# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180015990`
- end: `0x180015b8d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `509`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180014f70`

## callees

- `0x180002720`
- `0x180013850`
- `0x180013f70`
- `0x180013fb0`
- `0x180013fd0`
- `0x180014900`
- `0x180015990`
- `0x180015db0`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180015b4a`
- `KERNEL32!ReleaseMutex` at `0x180015b4a`
- `KERNEL32!WaitForSingleObjectEx` at `0x180015a5c`
- `KERNEL32!WaitForSingleObjectEx` at `0x180015a5c`
- `KERNEL32!CloseHandle` at `0x180015a1d`
- `KERNEL32!CloseHandle` at `0x180015a1d`
- `KERNEL32!CreateMutexExW` at `0x1800159fb`
- `KERNEL32!CreateMutexExW` at `0x1800159fb`
- `KERNEL32!GetCurrentProcessId` at `0x1800159bf`
- `KERNEL32!GetCurrentProcessId` at `0x1800159bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  unsigned int LastErrorFailHr; // edi
  unsigned int v8; // r8d
  const char *v9; // r9
  DWORD v11; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  char *v14; // r9
  void *v15; // rsi
  int ValueInternal; // eax
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  _DWORD *v20; // rcx
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  const char *v24; // r9
  int v25; // [rsp+20h] [rbp-258h]
  int v26; // [rsp+20h] [rbp-258h]
  HANDLE v27; // [rsp+30h] [rbp-248h]
  unsigned __int64 v28; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v27 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_3;
  }
  v11 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v11 == 258 )
  {
    v15 = 0;
  }
  else
  {
    if ( (v11 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v12, v13, v14);
    v15 = v6;
  }
  v28 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v12, &v28, (bool *)v14);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v20 = (_DWORD *)(4 * v28);
    if ( 4 * v28 )
    {
      *a2 = v20;
      ++*v20;
    }
    else
    {
      v21 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v21;
      if ( v21 < 0 )
      {
        _mm_lfence();
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v22, (const char *)(unsigned int)v21, 120);
        v6 = v27;
        goto LABEL_18;
      }
      v6 = v27;
    }
    LastErrorFailHr = 0;
    goto LABEL_18;
  }
  _mm_lfence();
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v17, (const char *)(unsigned int)ValueInternal, 120);
  _mm_lfence();
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v18, (const char *)LastErrorFailHr, v25);
  _mm_lfence();
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v19, (const char *)LastErrorFailHr, v26);
LABEL_18:
  if ( v15 && !ReleaseMutex(v15) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v23, v24);
LABEL_3:
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v8, v9);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180015990  mov     [rsp+arg_10], rbx
0x180015995  push    rsi
0x180015996  push    rdi
0x180015997  push    r14
0x180015999  sub     rsp, 260h
0x1800159a0  mov     rax, cs:__security_cookie
0x1800159a7  xor     rax, rsp
0x1800159aa  mov     [rsp+278h+var_28], rax
0x1800159b2  mov     r14, rdx
0x1800159b5  mov     qword ptr [rdx], 0
0x1800159bc  mov     rbx, rcx
0x1800159bf  call    cs:__imp_GetCurrentProcessId
0x1800159c5  mov     [rsp+278h+var_250], rbx
0x1800159ca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800159d1  mov     r9d, eax
0x1800159d4  mov     [rsp+278h+var_258], 78h ; 'x'; int
0x1800159dc  mov     edx, 104h; unsigned __int64
0x1800159e1  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800159e6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800159eb  mov     r9d, 1F0001h; dwDesiredAccess
0x1800159f1  lea     rdx, [rsp+278h+Name]; lpName
0x1800159f6  xor     r8d, r8d; dwFlags
0x1800159f9  xor     ecx, ecx; lpMutexAttributes
0x1800159fb  call    cs:__imp_CreateMutexExW
0x180015a01  mov     [rsp+278h+var_248], rax
0x180015a06  mov     rbx, rax
0x180015a09  test    rax, rax
0x180015a0c  jnz     short loc_180015A51
0x180015a0e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180015a13  mov     edi, eax
0x180015a15  test    rbx, rbx
0x180015a18  jz      short loc_180015A2B
0x180015a1a  mov     rcx, rbx; hObject
0x180015a1d  call    cs:__imp_CloseHandle
0x180015a23  test    eax, eax
0x180015a25  jz      loc_180015B7A
0x180015a2b  mov     eax, edi
0x180015a2d  mov     rcx, [rsp+278h+var_28]
0x180015a35  xor     rcx, rsp; StackCookie
0x180015a38  call    __security_check_cookie
0x180015a3d  mov     rbx, [rsp+278h+arg_10]
0x180015a45  add     rsp, 260h
0x180015a4c  pop     r14
0x180015a4e  pop     rdi
0x180015a4f  pop     rsi
0x180015a50  retn
0x180015a51  xor     r8d, r8d; bAlertable
0x180015a54  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180015a59  mov     rcx, rbx; hHandle
0x180015a5c  call    cs:__imp_WaitForSingleObjectEx
0x180015a62  cmp     eax, 102h
0x180015a67  jz      short loc_180015A79
0x180015a69  test    eax, 0FFFFFF7Fh
0x180015a6e  jnz     loc_180015B59
0x180015a74  mov     rsi, rbx
0x180015a77  jmp     short loc_180015A7B
0x180015a79  xor     esi, esi
0x180015a7b  lea     r8, [rsp+278h+var_240]; unsigned __int64 *
0x180015a80  mov     [rsp+278h+var_240], 0
0x180015a89  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180015a8e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180015a93  mov     edi, eax
0x180015a95  test    eax, eax
0x180015a97  jns     short loc_180015AE3
0x180015a99  lfence
0x180015a9c  mov     rcx, [rsp+278h]; this
0x180015aa4  mov     r9d, eax; char *
0x180015aa7  mov     edx, 64h ; 'd'; void *
0x180015aac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ab1  lfence
0x180015ab4  mov     rcx, [rsp+278h]; this
0x180015abc  mov     r9d, edi; char *
0x180015abf  mov     edx, 6Dh ; 'm'; void *
0x180015ac4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ac9  lfence
0x180015acc  mov     rcx, [rsp+278h]; this
0x180015ad4  mov     r9d, edi; char *
0x180015ad7  mov     edx, 12Bh; void *
0x180015adc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ae1  jmp     short loc_180015B3E
0x180015ae3  mov     rax, [rsp+278h+var_240]
0x180015ae8  lea     rcx, ds:0[rax*4]
0x180015af0  test    rcx, rcx
0x180015af3  jz      short loc_180015B00
0x180015af5  mov     [r14], rcx
0x180015af8  mov     eax, [rcx]
0x180015afa  inc     eax
0x180015afc  mov     [rcx], eax
0x180015afe  jmp     short loc_180015B3C
0x180015b00  mov     r8, r14
0x180015b03  lea     rdx, [rsp+278h+var_248]
0x180015b08  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180015b0d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180015b12  mov     edi, eax
0x180015b14  test    eax, eax
0x180015b16  jns     short loc_180015B37
0x180015b18  lfence
0x180015b1b  mov     rcx, [rsp+278h]; this
0x180015b23  mov     r9d, eax; char *
0x180015b26  mov     edx, 134h; void *
0x180015b2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b30  mov     rbx, [rsp+278h+var_248]
0x180015b35  jmp     short loc_180015B3E
0x180015b37  mov     rbx, [rsp+278h+var_248]
0x180015b3c  xor     edi, edi
0x180015b3e  test    rsi, rsi
0x180015b41  jz      loc_180015A15
0x180015b47  mov     rcx, rsi; hMutex
0x180015b4a  call    cs:__imp_ReleaseMutex
0x180015b50  test    eax, eax
0x180015b52  jz      short loc_180015B67
0x180015b54  jmp     loc_180015A15
0x180015b59  mov     rcx, [rsp+278h]; this
0x180015b61  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180015b67  mov     rcx, [rsp+278h]; this
0x180015b6f  mov     edx, 9D7h; void *
0x180015b74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015b7a  mov     rcx, [rsp+278h]; this
0x180015b82  mov     edx, 9CDh; void *
0x180015b87  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
