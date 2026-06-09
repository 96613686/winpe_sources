# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800435d0`
- end: `0x1800437cd`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `509`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180042bb0`

## callees

- `0x18003c660`
- `0x18003c9e0`
- `0x180041330`
- `0x180041660`
- `0x180041c60`
- `0x180042540`
- `0x1800435d0`
- `0x1800439f0`
- `0x18004c070`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004365d`
- `KERNEL32!CloseHandle` at `0x18004365d`
- `KERNEL32!GetCurrentProcessId` at `0x1800435ff`
- `KERNEL32!GetCurrentProcessId` at `0x1800435ff`
- `KERNEL32!ReleaseMutex` at `0x18004378a`
- `KERNEL32!ReleaseMutex` at `0x18004378a`
- `KERNEL32!CreateMutexExW` at `0x18004363b`
- `KERNEL32!CreateMutexExW` at `0x18004363b`
- `KERNEL32!WaitForSingleObjectEx` at `0x18004369c`
- `KERNEL32!WaitForSingleObjectEx` at `0x18004369c`

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
0x1800435d0  mov     [rsp+arg_10], rbx
0x1800435d5  push    rsi
0x1800435d6  push    rdi
0x1800435d7  push    r14
0x1800435d9  sub     rsp, 260h
0x1800435e0  mov     rax, cs:__security_cookie
0x1800435e7  xor     rax, rsp
0x1800435ea  mov     [rsp+278h+var_28], rax
0x1800435f2  mov     r14, rdx
0x1800435f5  mov     qword ptr [rdx], 0
0x1800435fc  mov     rbx, rcx
0x1800435ff  call    cs:__imp_GetCurrentProcessId
0x180043605  mov     [rsp+278h+var_250], rbx
0x18004360a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180043611  mov     r9d, eax
0x180043614  mov     [rsp+278h+var_258], 78h ; 'x'; int
0x18004361c  mov     edx, 104h; unsigned __int64
0x180043621  lea     rcx, [rsp+278h+Name]; Buffer
0x180043626  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18004362b  mov     r9d, 1F0001h; dwDesiredAccess
0x180043631  lea     rdx, [rsp+278h+Name]; lpName
0x180043636  xor     r8d, r8d; dwFlags
0x180043639  xor     ecx, ecx; lpMutexAttributes
0x18004363b  call    cs:__imp_CreateMutexExW
0x180043641  mov     [rsp+278h+var_248], rax
0x180043646  mov     rbx, rax
0x180043649  test    rax, rax
0x18004364c  jnz     short loc_180043691
0x18004364e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180043653  mov     edi, eax
0x180043655  test    rbx, rbx
0x180043658  jz      short loc_18004366B
0x18004365a  mov     rcx, rbx; hObject
0x18004365d  call    cs:__imp_CloseHandle
0x180043663  test    eax, eax
0x180043665  jz      loc_1800437BA
0x18004366b  mov     eax, edi
0x18004366d  mov     rcx, [rsp+278h+var_28]
0x180043675  xor     rcx, rsp; StackCookie
0x180043678  call    __security_check_cookie
0x18004367d  mov     rbx, [rsp+278h+arg_10]
0x180043685  add     rsp, 260h
0x18004368c  pop     r14
0x18004368e  pop     rdi
0x18004368f  pop     rsi
0x180043690  retn
0x180043691  xor     r8d, r8d; bAlertable
0x180043694  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180043699  mov     rcx, rbx; hHandle
0x18004369c  call    cs:__imp_WaitForSingleObjectEx
0x1800436a2  cmp     eax, 102h
0x1800436a7  jz      short loc_1800436B9
0x1800436a9  test    eax, 0FFFFFF7Fh
0x1800436ae  jnz     loc_180043799
0x1800436b4  mov     rsi, rbx
0x1800436b7  jmp     short loc_1800436BB
0x1800436b9  xor     esi, esi
0x1800436bb  lea     r8, [rsp+278h+var_240]; unsigned __int64 *
0x1800436c0  mov     [rsp+278h+var_240], 0
0x1800436c9  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800436ce  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800436d3  mov     edi, eax
0x1800436d5  test    eax, eax
0x1800436d7  jns     short loc_180043723
0x1800436d9  lfence
0x1800436dc  mov     rcx, [rsp+278h]; this
0x1800436e4  mov     r9d, eax; char *
0x1800436e7  mov     edx, 64h ; 'd'; void *
0x1800436ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800436f1  lfence
0x1800436f4  mov     rcx, [rsp+278h]; this
0x1800436fc  mov     r9d, edi; char *
0x1800436ff  mov     edx, 6Dh ; 'm'; void *
0x180043704  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043709  lfence
0x18004370c  mov     rcx, [rsp+278h]; this
0x180043714  mov     r9d, edi; char *
0x180043717  mov     edx, 12Bh; void *
0x18004371c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043721  jmp     short loc_18004377E
0x180043723  mov     rax, [rsp+278h+var_240]
0x180043728  lea     rcx, ds:0[rax*4]
0x180043730  test    rcx, rcx
0x180043733  jz      short loc_180043740
0x180043735  mov     [r14], rcx
0x180043738  mov     eax, [rcx]
0x18004373a  inc     eax
0x18004373c  mov     [rcx], eax
0x18004373e  jmp     short loc_18004377C
0x180043740  mov     r8, r14
0x180043743  lea     rdx, [rsp+278h+var_248]
0x180043748  lea     rcx, [rsp+278h+Name]; wchar_t *
0x18004374d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180043752  mov     edi, eax
0x180043754  test    eax, eax
0x180043756  jns     short loc_180043777
0x180043758  lfence
0x18004375b  mov     rcx, [rsp+278h]; this
0x180043763  mov     r9d, eax; char *
0x180043766  mov     edx, 134h; void *
0x18004376b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043770  mov     rbx, [rsp+278h+var_248]
0x180043775  jmp     short loc_18004377E
0x180043777  mov     rbx, [rsp+278h+var_248]
0x18004377c  xor     edi, edi
0x18004377e  test    rsi, rsi
0x180043781  jz      loc_180043655
0x180043787  mov     rcx, rsi; hMutex
0x18004378a  call    cs:__imp_ReleaseMutex
0x180043790  test    eax, eax
0x180043792  jz      short loc_1800437A7
0x180043794  jmp     loc_180043655
0x180043799  mov     rcx, [rsp+278h]; this
0x1800437a1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800437a7  mov     rcx, [rsp+278h]; this
0x1800437af  mov     edx, 9D7h; void *
0x1800437b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800437ba  mov     rcx, [rsp+278h]; this
0x1800437c2  mov     edx, 9CDh; void *
0x1800437c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
