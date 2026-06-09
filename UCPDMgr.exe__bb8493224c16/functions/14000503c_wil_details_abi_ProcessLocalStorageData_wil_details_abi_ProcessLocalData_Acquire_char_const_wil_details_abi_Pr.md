# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000503c`
- end: `0x140005233`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `503`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14000374c`

## callees

- `0x1400012a0`
- `0x140001d60`
- `0x140002ba4`
- `0x140002be8`
- `0x140002c04`
- `0x14000328c`
- `0x14000503c`
- `0x140005ba4`
- `0x14000a390`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x1400051f3`
- `KERNEL32!ReleaseMutex` at `0x1400051f3`
- `KERNEL32!WaitForSingleObjectEx` at `0x140005115`
- `KERNEL32!WaitForSingleObjectEx` at `0x140005115`
- `KERNEL32!CloseHandle` at `0x1400050d5`
- `KERNEL32!CloseHandle` at `0x1400050d5`
- `KERNEL32!CreateMutexExW` at `0x1400050b3`
- `KERNEL32!CreateMutexExW` at `0x1400050b3`
- `KERNEL32!GetCurrentProcessId` at `0x140005077`
- `KERNEL32!GetCurrentProcessId` at `0x140005077`

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
  __int64 v8; // r8
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
  __int64 v23; // r8
  const char *v24; // r9
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  HANDLE v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

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
      v21 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
              Name,
              &v27,
              a2);
      LastErrorFailHr = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v22, (const char *)(unsigned int)v21, 120);
        v6 = v27;
        goto LABEL_18;
      }
      v6 = v27;
    }
    LastErrorFailHr = 0;
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v17, (const char *)(unsigned int)ValueInternal, 120);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v18, (const char *)LastErrorFailHr, v25);
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
0x14000503c  mov     [rsp-8+arg_10], rbx
0x140005041  mov     [rsp-8+arg_18], rsi
0x140005046  push    rbp
0x140005047  push    rdi
0x140005048  push    r14
0x14000504a  lea     rbp, [rsp-160h]
0x140005052  sub     rsp, 260h
0x140005059  mov     rax, cs:__security_cookie
0x140005060  xor     rax, rsp
0x140005063  mov     [rbp+170h+var_20], rax
0x14000506a  mov     r14, rdx
0x14000506d  mov     qword ptr [rdx], 0
0x140005074  mov     rbx, rcx
0x140005077  call    cs:__imp_GetCurrentProcessId
0x14000507d  mov     [rsp+270h+var_248], rbx
0x140005082  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140005089  mov     r9d, eax
0x14000508c  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140005094  mov     edx, 104h; unsigned __int64
0x140005099  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14000509e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400050a3  mov     r9d, 1F0001h; dwDesiredAccess
0x1400050a9  lea     rdx, [rsp+270h+Name]; lpName
0x1400050ae  xor     r8d, r8d; dwFlags
0x1400050b1  xor     ecx, ecx; lpMutexAttributes
0x1400050b3  call    cs:__imp_CreateMutexExW
0x1400050b9  mov     [rsp+270h+var_240], rax
0x1400050be  mov     rbx, rax
0x1400050c1  test    rax, rax
0x1400050c4  jnz     short loc_14000510C
0x1400050c6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400050cb  mov     edi, eax
0x1400050cd  test    rbx, rbx
0x1400050d0  jz      short loc_1400050E3
0x1400050d2  mov     rcx, rbx; hObject
0x1400050d5  call    cs:__imp_CloseHandle
0x1400050db  test    eax, eax
0x1400050dd  jz      loc_140005221
0x1400050e3  mov     eax, edi
0x1400050e5  mov     rcx, [rbp+170h+var_20]
0x1400050ec  xor     rcx, rsp; StackCookie
0x1400050ef  call    __security_check_cookie
0x1400050f4  lea     r11, [rsp+270h+var_10]
0x1400050fc  mov     rbx, [r11+30h]
0x140005100  mov     rsi, [r11+38h]
0x140005104  mov     rsp, r11
0x140005107  pop     r14
0x140005109  pop     rdi
0x14000510a  pop     rbp
0x14000510b  retn
0x14000510c  xor     r8d, r8d; bAlertable
0x14000510f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005112  mov     rcx, rbx; hHandle
0x140005115  call    cs:__imp_WaitForSingleObjectEx
0x14000511b  cmp     eax, 102h
0x140005120  jz      short loc_140005132
0x140005122  test    eax, 0FFFFFF7Fh
0x140005127  jnz     loc_140005202
0x14000512d  mov     rsi, rbx
0x140005130  jmp     short loc_140005134
0x140005132  xor     esi, esi
0x140005134  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x140005139  mov     [rsp+270h+var_238], 0
0x140005142  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140005147  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x14000514c  mov     edi, eax
0x14000514e  test    eax, eax
0x140005150  jns     short loc_140005190
0x140005152  mov     rcx, [rbp+178h]; this
0x140005159  mov     r9d, eax; char *
0x14000515c  mov     edx, 64h ; 'd'; void *
0x140005161  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005166  mov     rcx, [rbp+178h]; this
0x14000516d  mov     r9d, edi; char *
0x140005170  mov     edx, 6Dh ; 'm'; void *
0x140005175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000517a  mov     rcx, [rbp+178h]; this
0x140005181  mov     r9d, edi; char *
0x140005184  mov     edx, 12Bh; void *
0x140005189  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000518e  jmp     short loc_1400051E7
0x140005190  mov     rax, [rsp+270h+var_238]
0x140005195  lea     rcx, ds:0[rax*4]
0x14000519d  test    rcx, rcx
0x1400051a0  jz      short loc_1400051AD
0x1400051a2  mov     [r14], rcx
0x1400051a5  mov     eax, [rcx]
0x1400051a7  inc     eax
0x1400051a9  mov     [rcx], eax
0x1400051ab  jmp     short loc_1400051E5
0x1400051ad  mov     r8, r14
0x1400051b0  lea     rdx, [rsp+270h+var_240]
0x1400051b5  lea     rcx, [rsp+270h+Name]
0x1400051ba  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400051bf  mov     edi, eax
0x1400051c1  test    eax, eax
0x1400051c3  jns     short loc_1400051E0
0x1400051c5  mov     rcx, [rbp+178h]; this
0x1400051cc  mov     r9d, eax; char *
0x1400051cf  mov     edx, 134h; void *
0x1400051d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400051d9  mov     rbx, [rsp+270h+var_240]
0x1400051de  jmp     short loc_1400051E7
0x1400051e0  mov     rbx, [rsp+270h+var_240]
0x1400051e5  xor     edi, edi
0x1400051e7  test    rsi, rsi
0x1400051ea  jz      loc_1400050CD
0x1400051f0  mov     rcx, rsi; hMutex
0x1400051f3  call    cs:__imp_ReleaseMutex
0x1400051f9  test    eax, eax
0x1400051fb  jz      short loc_14000520F
0x1400051fd  jmp     loc_1400050CD
0x140005202  mov     rcx, [rbp+178h]; this
0x140005209  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000520f  mov     rcx, [rbp+178h]; this
0x140005216  mov     edx, 9D7h; void *
0x14000521b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005221  mov     rcx, [rbp+178h]; this
0x140005228  mov     edx, 9CDh; void *
0x14000522d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
