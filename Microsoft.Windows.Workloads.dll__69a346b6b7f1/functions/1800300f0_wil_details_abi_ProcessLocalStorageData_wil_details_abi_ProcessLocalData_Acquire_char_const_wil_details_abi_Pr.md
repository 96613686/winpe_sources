# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800300f0`
- end: `0x1800302e5`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `501`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18002f200`

## callees

- `0x180002b80`
- `0x180010a50`
- `0x18002d300`
- `0x18002e1e0`
- `0x18002e200`
- `0x18002eb70`
- `0x1800300f0`
- `0x180030560`
- `0x180034ef0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18003011f`
- `KERNEL32!GetCurrentProcessId` at `0x18003011f`
- `KERNEL32!CloseHandle` at `0x18003017d`
- `KERNEL32!CloseHandle` at `0x18003017d`
- `KERNEL32!ReleaseMutex` at `0x180030267`
- `KERNEL32!ReleaseMutex` at `0x180030267`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800301bc`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800301bc`
- `KERNEL32!CreateMutexExW` at `0x18003015b`
- `KERNEL32!CreateMutexExW` at `0x18003015b`

## pseudocode

```c
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
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  unsigned int v19; // r8d
  const char *v20; // r9
  int v21; // [rsp+20h] [rbp-258h]
  int v22; // [rsp+20h] [rbp-258h]
  HANDLE v23; // [rsp+30h] [rbp-248h]
  unsigned __int64 v24; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v21 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v23 = Mutex;
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
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v12, &v24, (bool *)v14);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    _mm_lfence();
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    _mm_lfence();
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)LastErrorFailHr, v22);
    v17 = 299;
LABEL_20:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)LastErrorFailHr, v21);
    goto LABEL_15;
  }
  v18 = (_DWORD *)(4 * v24);
  if ( 4 * v24 )
  {
    *a2 = v18;
    ++*v18;
  }
  else
  {
    v6 = v23;
    LastErrorFailHr = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    if ( (LastErrorFailHr & 0x80000000) != 0 )
    {
      v17 = 308;
      goto LABEL_20;
    }
  }
  LastErrorFailHr = 0;
LABEL_15:
  if ( v15 && !ReleaseMutex(v15) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v19, v20);
LABEL_3:
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v8, v9);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800300f0  mov     [rsp+arg_10], rbx
0x1800300f5  push    rsi
0x1800300f6  push    rdi
0x1800300f7  push    r14
0x1800300f9  sub     rsp, 260h
0x180030100  mov     rax, cs:__security_cookie
0x180030107  xor     rax, rsp
0x18003010a  mov     [rsp+278h+var_28], rax
0x180030112  mov     r14, rdx
0x180030115  mov     qword ptr [rdx], 0
0x18003011c  mov     rbx, rcx
0x18003011f  call    cs:__imp_GetCurrentProcessId
0x180030125  mov     [rsp+278h+var_250], rbx
0x18003012a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180030131  mov     r9d, eax
0x180030134  mov     [rsp+278h+var_258], 78h ; 'x'; int
0x18003013c  mov     edx, 104h; unsigned __int64
0x180030141  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180030146  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18003014b  mov     r9d, 1F0001h; dwDesiredAccess
0x180030151  lea     rdx, [rsp+278h+Name]; lpName
0x180030156  xor     r8d, r8d; dwFlags
0x180030159  xor     ecx, ecx; lpMutexAttributes
0x18003015b  call    cs:__imp_CreateMutexExW
0x180030161  mov     [rsp+278h+var_248], rax
0x180030166  mov     rbx, rax
0x180030169  test    rax, rax
0x18003016c  jnz     short loc_1800301B1
0x18003016e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180030173  mov     edi, eax
0x180030175  test    rbx, rbx
0x180030178  jz      short loc_18003018B
0x18003017a  mov     rcx, rbx; hObject
0x18003017d  call    cs:__imp_CloseHandle
0x180030183  test    eax, eax
0x180030185  jz      loc_1800302D2
0x18003018b  mov     eax, edi
0x18003018d  mov     rcx, [rsp+278h+var_28]
0x180030195  xor     rcx, rsp; StackCookie
0x180030198  call    __security_check_cookie
0x18003019d  mov     rbx, [rsp+278h+arg_10]
0x1800301a5  add     rsp, 260h
0x1800301ac  pop     r14
0x1800301ae  pop     rdi
0x1800301af  pop     rsi
0x1800301b0  retn
0x1800301b1  xor     r8d, r8d; bAlertable
0x1800301b4  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800301b9  mov     rcx, rbx; hHandle
0x1800301bc  call    cs:__imp_WaitForSingleObjectEx
0x1800301c2  cmp     eax, 102h
0x1800301c7  jz      short loc_1800301D9
0x1800301c9  test    eax, 0FFFFFF7Fh
0x1800301ce  jnz     loc_1800302B1
0x1800301d4  mov     rsi, rbx
0x1800301d7  jmp     short loc_1800301DB
0x1800301d9  xor     esi, esi
0x1800301db  lea     r8, [rsp+278h+var_240]; unsigned __int64 *
0x1800301e0  mov     [rsp+278h+var_240], 0
0x1800301e9  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800301ee  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800301f3  mov     edi, eax
0x1800301f5  test    eax, eax
0x1800301f7  jns     short loc_18003023E
0x1800301f9  lfence
0x1800301fc  mov     rcx, [rsp+278h]; this
0x180030204  lea     r8, aWil; "wil"
0x18003020b  mov     r9d, eax; char *
0x18003020e  mov     edx, 64h ; 'd'; void *
0x180030213  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030218  lfence
0x18003021b  mov     rcx, [rsp+278h]; this
0x180030223  lea     r8, aWil; "wil"
0x18003022a  mov     r9d, edi; char *
0x18003022d  mov     edx, 6Dh ; 'm'; void *
0x180030232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030237  mov     edx, 12Bh
0x18003023c  jmp     short loc_180030298
0x18003023e  mov     rax, [rsp+278h+var_240]
0x180030243  lea     rcx, ds:0[rax*4]
0x18003024b  test    rcx, rcx
0x18003024e  jz      short loc_180030276
0x180030250  mov     [r14], rcx
0x180030253  mov     eax, [rcx]
0x180030255  inc     eax
0x180030257  mov     [rcx], eax
0x180030259  xor     edi, edi
0x18003025b  test    rsi, rsi
0x18003025e  jz      loc_180030175
0x180030264  mov     rcx, rsi; hMutex
0x180030267  call    cs:__imp_ReleaseMutex
0x18003026d  test    eax, eax
0x18003026f  jz      short loc_1800302BF
0x180030271  jmp     loc_180030175
0x180030276  mov     r8, r14
0x180030279  lea     rdx, [rsp+278h+var_248]
0x18003027e  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180030283  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180030288  mov     rbx, [rsp+278h+var_248]
0x18003028d  mov     edi, eax
0x18003028f  test    eax, eax
0x180030291  jns     short loc_180030259
0x180030293  mov     edx, 134h; void *
0x180030298  mov     rcx, [rsp+278h]; this
0x1800302a0  lea     r8, aWil; "wil"
0x1800302a7  mov     r9d, edi; char *
0x1800302aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800302af  jmp     short loc_18003025B
0x1800302b1  mov     rcx, [rsp+278h]; this
0x1800302b9  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800302bf  mov     rcx, [rsp+278h]; this
0x1800302c7  mov     edx, 9D7h; void *
0x1800302cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800302d2  mov     rcx, [rsp+278h]; this
0x1800302da  mov     edx, 9CDh; void *
0x1800302df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
