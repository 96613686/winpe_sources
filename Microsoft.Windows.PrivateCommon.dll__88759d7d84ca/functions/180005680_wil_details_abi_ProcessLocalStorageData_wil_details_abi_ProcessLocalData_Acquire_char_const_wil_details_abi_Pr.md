# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005680`
- end: `0x18000587d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `509`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180004a50`

## callees

- `0x180002180`
- `0x180002ca0`
- `0x180003e90`
- `0x180003ed0`
- `0x180003ef0`
- `0x1800043e0`
- `0x180005680`
- `0x180005aa0`
- `0x180007280`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18000583a`
- `KERNEL32!ReleaseMutex` at `0x18000583a`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000574c`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000574c`
- `KERNEL32!CloseHandle` at `0x18000570d`
- `KERNEL32!CloseHandle` at `0x18000570d`
- `KERNEL32!CreateMutexExW` at `0x1800056eb`
- `KERNEL32!CreateMutexExW` at `0x1800056eb`
- `KERNEL32!GetCurrentProcessId` at `0x1800056af`
- `KERNEL32!GetCurrentProcessId` at `0x1800056af`

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
  int v8; // r8d
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
  int v23; // r8d
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
0x180005680  mov     [rsp+arg_10], rbx
0x180005685  push    rsi
0x180005686  push    rdi
0x180005687  push    r14
0x180005689  sub     rsp, 260h
0x180005690  mov     rax, cs:__security_cookie
0x180005697  xor     rax, rsp
0x18000569a  mov     [rsp+278h+var_28], rax
0x1800056a2  mov     r14, rdx
0x1800056a5  mov     qword ptr [rdx], 0
0x1800056ac  mov     rbx, rcx
0x1800056af  call    cs:__imp_GetCurrentProcessId
0x1800056b5  mov     [rsp+278h+var_250], rbx
0x1800056ba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800056c1  mov     r9d, eax
0x1800056c4  mov     [rsp+278h+var_258], 78h ; 'x'; int
0x1800056cc  mov     edx, 104h; unsigned __int64
0x1800056d1  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800056d6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800056db  mov     r9d, 1F0001h; dwDesiredAccess
0x1800056e1  lea     rdx, [rsp+278h+Name]; lpName
0x1800056e6  xor     r8d, r8d; dwFlags
0x1800056e9  xor     ecx, ecx; lpMutexAttributes
0x1800056eb  call    cs:__imp_CreateMutexExW
0x1800056f1  mov     [rsp+278h+var_248], rax
0x1800056f6  mov     rbx, rax
0x1800056f9  test    rax, rax
0x1800056fc  jnz     short loc_180005741
0x1800056fe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005703  mov     edi, eax
0x180005705  test    rbx, rbx
0x180005708  jz      short loc_18000571B
0x18000570a  mov     rcx, rbx; hObject
0x18000570d  call    cs:__imp_CloseHandle
0x180005713  test    eax, eax
0x180005715  jz      loc_18000586A
0x18000571b  mov     eax, edi
0x18000571d  mov     rcx, [rsp+278h+var_28]
0x180005725  xor     rcx, rsp; StackCookie
0x180005728  call    __security_check_cookie
0x18000572d  mov     rbx, [rsp+278h+arg_10]
0x180005735  add     rsp, 260h
0x18000573c  pop     r14
0x18000573e  pop     rdi
0x18000573f  pop     rsi
0x180005740  retn
0x180005741  xor     r8d, r8d; bAlertable
0x180005744  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180005749  mov     rcx, rbx; hHandle
0x18000574c  call    cs:__imp_WaitForSingleObjectEx
0x180005752  cmp     eax, 102h
0x180005757  jz      short loc_180005769
0x180005759  test    eax, 0FFFFFF7Fh
0x18000575e  jnz     loc_180005849
0x180005764  mov     rsi, rbx
0x180005767  jmp     short loc_18000576B
0x180005769  xor     esi, esi
0x18000576b  lea     r8, [rsp+278h+var_240]; unsigned __int64 *
0x180005770  mov     [rsp+278h+var_240], 0
0x180005779  lea     rcx, [rsp+278h+Name]; wchar_t *
0x18000577e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180005783  mov     edi, eax
0x180005785  test    eax, eax
0x180005787  jns     short loc_1800057D3
0x180005789  lfence
0x18000578c  mov     rcx, [rsp+278h]; this
0x180005794  mov     r9d, eax; char *
0x180005797  mov     edx, 64h ; 'd'; void *
0x18000579c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057a1  lfence
0x1800057a4  mov     rcx, [rsp+278h]; this
0x1800057ac  mov     r9d, edi; char *
0x1800057af  mov     edx, 6Dh ; 'm'; void *
0x1800057b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057b9  lfence
0x1800057bc  mov     rcx, [rsp+278h]; this
0x1800057c4  mov     r9d, edi; char *
0x1800057c7  mov     edx, 12Bh; void *
0x1800057cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057d1  jmp     short loc_18000582E
0x1800057d3  mov     rax, [rsp+278h+var_240]
0x1800057d8  lea     rcx, ds:0[rax*4]
0x1800057e0  test    rcx, rcx
0x1800057e3  jz      short loc_1800057F0
0x1800057e5  mov     [r14], rcx
0x1800057e8  mov     eax, [rcx]
0x1800057ea  inc     eax
0x1800057ec  mov     [rcx], eax
0x1800057ee  jmp     short loc_18000582C
0x1800057f0  mov     r8, r14
0x1800057f3  lea     rdx, [rsp+278h+var_248]
0x1800057f8  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800057fd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005802  mov     edi, eax
0x180005804  test    eax, eax
0x180005806  jns     short loc_180005827
0x180005808  lfence
0x18000580b  mov     rcx, [rsp+278h]; this
0x180005813  mov     r9d, eax; char *
0x180005816  mov     edx, 134h; void *
0x18000581b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005820  mov     rbx, [rsp+278h+var_248]
0x180005825  jmp     short loc_18000582E
0x180005827  mov     rbx, [rsp+278h+var_248]
0x18000582c  xor     edi, edi
0x18000582e  test    rsi, rsi
0x180005831  jz      loc_180005705
0x180005837  mov     rcx, rsi; hMutex
0x18000583a  call    cs:__imp_ReleaseMutex
0x180005840  test    eax, eax
0x180005842  jz      short loc_180005857
0x180005844  jmp     loc_180005705
0x180005849  mov     rcx, [rsp+278h]; this
0x180005851  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005857  mov     rcx, [rsp+278h]; this
0x18000585f  mov     edx, 9D7h; void *
0x180005864  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000586a  mov     rcx, [rsp+278h]; this
0x180005872  mov     edx, 9CDh; void *
0x180005877  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
