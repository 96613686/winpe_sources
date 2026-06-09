# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800040b4`
- end: `0x180004399`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180004c84`

## callees

- `0x180002910`
- `0x1800040b4`
- `0x1800043b4`
- `0x180004960`
- `0x180005434`
- `0x180005b28`
- `0x180005f08`
- `0x180005f94`
- `0x180006474`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800040ef`
- `KERNEL32!GetCurrentProcessId` at `0x1800040ef`
- `KERNEL32!CreateMutexExW` at `0x180004131`
- `KERNEL32!CreateMutexExW` at `0x180004131`
- `KERNEL32!CloseHandle` at `0x180004214`
- `KERNEL32!CloseHandle` at `0x1800042a5`
- `KERNEL32!CloseHandle` at `0x1800042e6`
- `KERNEL32!CloseHandle` at `0x180004214`
- `KERNEL32!CloseHandle` at `0x1800042a5`
- `KERNEL32!CloseHandle` at `0x1800042e6`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000415d`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000415d`
- `KERNEL32!ReleaseMutex` at `0x1800041fd`
- `KERNEL32!ReleaseMutex` at `0x180004287`
- `KERNEL32!ReleaseMutex` at `0x1800042ca`
- `KERNEL32!ReleaseMutex` at `0x1800041fd`
- `KERNEL32!ReleaseMutex` at `0x180004287`
- `KERNEL32!ReleaseMutex` at `0x1800042ca`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  int v20; // eax
  unsigned int v21; // ebx
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  hObject = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v33 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v33, (bool *)v11);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v30);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v31);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * v33);
  if ( 4 * v33 )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_21;
  }
  v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
          Name,
          &hObject,
          a2);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v6 = hObject;
LABEL_21:
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v20, 120);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v22, v23);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x1800040b4  mov     [rsp-8+arg_10], rbx
0x1800040b9  mov     [rsp-8+arg_18], rsi
0x1800040be  push    rbp
0x1800040bf  push    rdi
0x1800040c0  push    r14
0x1800040c2  lea     rbp, [rsp-160h]
0x1800040ca  sub     rsp, 260h
0x1800040d1  mov     rax, cs:__security_cookie
0x1800040d8  xor     rax, rsp
0x1800040db  mov     [rbp+170h+var_20], rax
0x1800040e2  mov     r14, rdx
0x1800040e5  mov     qword ptr [rdx], 0
0x1800040ec  mov     rbx, rcx
0x1800040ef  call    cs:__imp_GetCurrentProcessId
0x1800040f6  nop     dword ptr [rax+rax+00h]
0x1800040fb  mov     [rsp+270h+var_248], rbx
0x180004100  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004107  mov     r9d, eax
0x18000410a  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004112  mov     edx, 104h; unsigned __int64
0x180004117  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000411c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004121  mov     r9d, 1F0001h; dwDesiredAccess
0x180004127  lea     rdx, [rsp+270h+Name]; lpName
0x18000412c  xor     r8d, r8d; dwFlags
0x18000412f  xor     ecx, ecx; lpMutexAttributes
0x180004131  call    cs:__imp_CreateMutexExW
0x180004138  nop     dword ptr [rax+rax+00h]
0x18000413d  mov     [rsp+270h+hObject], rax
0x180004142  mov     rbx, rax
0x180004145  test    rax, rax
0x180004148  jnz     short loc_180004154
0x18000414a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000414f  jmp     loc_1800042F8
0x180004154  xor     r8d, r8d; bAlertable
0x180004157  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000415a  mov     rcx, rbx; hHandle
0x18000415d  call    cs:__imp_WaitForSingleObjectEx
0x180004164  nop     dword ptr [rax+rax+00h]
0x180004169  cmp     eax, 102h
0x18000416e  jz      short loc_180004180
0x180004170  test    eax, 0FFFFFF7Fh
0x180004175  jnz     loc_180004332
0x18000417b  mov     rdi, rbx
0x18000417e  jmp     short loc_180004182
0x180004180  xor     edi, edi
0x180004182  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180004187  mov     [rsp+270h+var_238], 0
0x180004190  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004195  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000419a  mov     esi, eax
0x18000419c  test    eax, eax
0x18000419e  jns     loc_18000422F
0x1800041a4  mov     rcx, [rbp+178h]; this
0x1800041ab  lea     r8, aWil; "wil"
0x1800041b2  mov     r9d, eax; char *
0x1800041b5  mov     edx, 66h ; 'f'; void *
0x1800041ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041bf  mov     rcx, [rbp+178h]; this
0x1800041c6  lea     r8, aWil; "wil"
0x1800041cd  mov     r9d, esi; char *
0x1800041d0  mov     edx, 6Fh ; 'o'; void *
0x1800041d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041da  mov     rcx, [rbp+178h]; this
0x1800041e1  lea     r8, aWil; "wil"
0x1800041e8  mov     r9d, esi; char *
0x1800041eb  mov     edx, 12Eh; void *
0x1800041f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041f5  test    rdi, rdi
0x1800041f8  jz      short loc_180004211
0x1800041fa  mov     rcx, rdi; hMutex
0x1800041fd  call    cs:__imp_ReleaseMutex
0x180004204  nop     dword ptr [rax+rax+00h]
0x180004209  test    eax, eax
0x18000420b  jz      loc_18000433F
0x180004211  mov     rcx, rbx; hObject
0x180004214  call    cs:__imp_CloseHandle
0x18000421b  nop     dword ptr [rax+rax+00h]
0x180004220  test    eax, eax
0x180004222  jz      loc_180004351
0x180004228  mov     eax, esi
0x18000422a  jmp     loc_1800042F8
0x18000422f  mov     rax, [rsp+270h+var_238]
0x180004234  lea     rcx, ds:0[rax*4]
0x18000423c  test    rcx, rcx
0x18000423f  jz      short loc_18000424C
0x180004241  mov     [r14], rcx
0x180004244  mov     eax, [rcx]
0x180004246  inc     eax
0x180004248  mov     [rcx], eax
0x18000424a  jmp     short loc_1800042C2
0x18000424c  mov     r8, r14
0x18000424f  lea     rdx, [rsp+270h+hObject]
0x180004254  lea     rcx, [rsp+270h+Name]
0x180004259  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000425e  mov     ebx, eax
0x180004260  test    eax, eax
0x180004262  jns     short loc_1800042BD
0x180004264  mov     rcx, [rbp+178h]; this
0x18000426b  lea     r8, aWil; "wil"
0x180004272  mov     r9d, eax; char *
0x180004275  mov     edx, 137h; void *
0x18000427a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000427f  test    rdi, rdi
0x180004282  jz      short loc_18000429B
0x180004284  mov     rcx, rdi; hMutex
0x180004287  call    cs:__imp_ReleaseMutex
0x18000428e  nop     dword ptr [rax+rax+00h]
0x180004293  test    eax, eax
0x180004295  jz      loc_180004363
0x18000429b  mov     rcx, [rsp+270h+hObject]; hObject
0x1800042a0  test    rcx, rcx
0x1800042a3  jz      short loc_1800042B9
0x1800042a5  call    cs:__imp_CloseHandle
0x1800042ac  nop     dword ptr [rax+rax+00h]
0x1800042b1  test    eax, eax
0x1800042b3  jz      loc_180004375
0x1800042b9  mov     eax, ebx
0x1800042bb  jmp     short loc_1800042F8
0x1800042bd  mov     rbx, [rsp+270h+hObject]
0x1800042c2  test    rdi, rdi
0x1800042c5  jz      short loc_1800042DE
0x1800042c7  mov     rcx, rdi; hMutex
0x1800042ca  call    cs:__imp_ReleaseMutex
0x1800042d1  nop     dword ptr [rax+rax+00h]
0x1800042d6  test    eax, eax
0x1800042d8  jz      loc_180004387
0x1800042de  test    rbx, rbx
0x1800042e1  jz      short loc_1800042F6
0x1800042e3  mov     rcx, rbx; hObject
0x1800042e6  call    cs:__imp_CloseHandle
0x1800042ed  nop     dword ptr [rax+rax+00h]
0x1800042f2  test    eax, eax
0x1800042f4  jz      short loc_180004320
0x1800042f6  xor     eax, eax
0x1800042f8  mov     rcx, [rbp+170h+var_20]
0x1800042ff  xor     rcx, rsp; StackCookie
0x180004302  call    __security_check_cookie
0x180004307  lea     r11, [rsp+270h+var_10]
0x18000430f  mov     rbx, [r11+30h]
0x180004313  mov     rsi, [r11+38h]
0x180004317  mov     rsp, r11
0x18000431a  pop     r14
0x18000431c  pop     rdi
0x18000431d  pop     rbp
0x18000431e  retn
0x180004320  mov     rcx, [rbp+178h]; this
0x180004327  mov     edx, 0A0Bh; void *
0x18000432c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004332  mov     rcx, [rbp+178h]; this
0x180004339  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000433f  mov     rcx, [rbp+178h]; this
0x180004346  mov     edx, 0A15h; void *
0x18000434b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004351  mov     rcx, [rbp+178h]; this
0x180004358  mov     edx, 0A0Bh; void *
0x18000435d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004363  mov     rcx, [rbp+178h]; this
0x18000436a  mov     edx, 0A15h; void *
0x18000436f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004375  mov     rcx, [rbp+178h]; this
0x18000437c  mov     edx, 0A0Bh; void *
0x180004381  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004387  mov     rcx, [rbp+178h]; this
0x18000438e  mov     edx, 0A15h; void *
0x180004393  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
