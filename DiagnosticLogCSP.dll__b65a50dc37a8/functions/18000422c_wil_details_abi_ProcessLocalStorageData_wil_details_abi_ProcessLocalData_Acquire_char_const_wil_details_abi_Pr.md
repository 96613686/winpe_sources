# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000422c`
- end: `0x180004511`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180004d5c`

## callees

- `0x180001b90`
- `0x18000422c`
- `0x180004534`
- `0x180004ae0`
- `0x180005508`
- `0x180005c24`
- `0x180006498`
- `0x18000655c`
- `0x180006988`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004267`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004375`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800043ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004442`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004375`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800043ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004442`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800042d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800042d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800042a9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800042a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000438c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000441d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000445e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000438c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000441d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000445e`

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
0x18000422c  mov     [rsp-8+arg_10], rbx
0x180004231  mov     [rsp-8+arg_18], rsi
0x180004236  push    rbp
0x180004237  push    rdi
0x180004238  push    r14
0x18000423a  lea     rbp, [rsp-160h]
0x180004242  sub     rsp, 260h
0x180004249  mov     rax, cs:__security_cookie
0x180004250  xor     rax, rsp
0x180004253  mov     [rbp+170h+var_20], rax
0x18000425a  mov     r14, rdx
0x18000425d  mov     qword ptr [rdx], 0
0x180004264  mov     rbx, rcx
0x180004267  call    cs:__imp_GetCurrentProcessId
0x18000426e  nop     dword ptr [rax+rax+00h]
0x180004273  mov     [rsp+270h+var_248], rbx
0x180004278  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000427f  mov     r9d, eax
0x180004282  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000428a  mov     edx, 104h; unsigned __int64
0x18000428f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004294  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004299  mov     r9d, 1F0001h; dwDesiredAccess
0x18000429f  lea     rdx, [rsp+270h+Name]; lpName
0x1800042a4  xor     r8d, r8d; dwFlags
0x1800042a7  xor     ecx, ecx; lpMutexAttributes
0x1800042a9  call    cs:__imp_CreateMutexExW
0x1800042b0  nop     dword ptr [rax+rax+00h]
0x1800042b5  mov     [rsp+270h+hObject], rax
0x1800042ba  mov     rbx, rax
0x1800042bd  test    rax, rax
0x1800042c0  jnz     short loc_1800042CC
0x1800042c2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800042c7  jmp     loc_180004470
0x1800042cc  xor     r8d, r8d; bAlertable
0x1800042cf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800042d2  mov     rcx, rbx; hHandle
0x1800042d5  call    cs:__imp_WaitForSingleObjectEx
0x1800042dc  nop     dword ptr [rax+rax+00h]
0x1800042e1  cmp     eax, 102h
0x1800042e6  jz      short loc_1800042F8
0x1800042e8  test    eax, 0FFFFFF7Fh
0x1800042ed  jnz     loc_1800044AA
0x1800042f3  mov     rdi, rbx
0x1800042f6  jmp     short loc_1800042FA
0x1800042f8  xor     edi, edi
0x1800042fa  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x1800042ff  mov     [rsp+270h+var_238], 0
0x180004308  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000430d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004312  mov     esi, eax
0x180004314  test    eax, eax
0x180004316  jns     loc_1800043A7
0x18000431c  mov     rcx, [rbp+178h]; this
0x180004323  lea     r8, aWil; "wil"
0x18000432a  mov     r9d, eax; char *
0x18000432d  mov     edx, 66h ; 'f'; void *
0x180004332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004337  mov     rcx, [rbp+178h]; this
0x18000433e  lea     r8, aWil; "wil"
0x180004345  mov     r9d, esi; char *
0x180004348  mov     edx, 6Fh ; 'o'; void *
0x18000434d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004352  mov     rcx, [rbp+178h]; this
0x180004359  lea     r8, aWil; "wil"
0x180004360  mov     r9d, esi; char *
0x180004363  mov     edx, 12Eh; void *
0x180004368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000436d  test    rdi, rdi
0x180004370  jz      short loc_180004389
0x180004372  mov     rcx, rdi; hMutex
0x180004375  call    cs:__imp_ReleaseMutex
0x18000437c  nop     dword ptr [rax+rax+00h]
0x180004381  test    eax, eax
0x180004383  jz      loc_1800044B7
0x180004389  mov     rcx, rbx; hObject
0x18000438c  call    cs:__imp_CloseHandle
0x180004393  nop     dword ptr [rax+rax+00h]
0x180004398  test    eax, eax
0x18000439a  jz      loc_1800044C9
0x1800043a0  mov     eax, esi
0x1800043a2  jmp     loc_180004470
0x1800043a7  mov     rax, [rsp+270h+var_238]
0x1800043ac  lea     rcx, ds:0[rax*4]
0x1800043b4  test    rcx, rcx
0x1800043b7  jz      short loc_1800043C4
0x1800043b9  mov     [r14], rcx
0x1800043bc  mov     eax, [rcx]
0x1800043be  inc     eax
0x1800043c0  mov     [rcx], eax
0x1800043c2  jmp     short loc_18000443A
0x1800043c4  mov     r8, r14
0x1800043c7  lea     rdx, [rsp+270h+hObject]
0x1800043cc  lea     rcx, [rsp+270h+Name]
0x1800043d1  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800043d6  mov     ebx, eax
0x1800043d8  test    eax, eax
0x1800043da  jns     short loc_180004435
0x1800043dc  mov     rcx, [rbp+178h]; this
0x1800043e3  lea     r8, aWil; "wil"
0x1800043ea  mov     r9d, eax; char *
0x1800043ed  mov     edx, 137h; void *
0x1800043f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043f7  test    rdi, rdi
0x1800043fa  jz      short loc_180004413
0x1800043fc  mov     rcx, rdi; hMutex
0x1800043ff  call    cs:__imp_ReleaseMutex
0x180004406  nop     dword ptr [rax+rax+00h]
0x18000440b  test    eax, eax
0x18000440d  jz      loc_1800044DB
0x180004413  mov     rcx, [rsp+270h+hObject]; hObject
0x180004418  test    rcx, rcx
0x18000441b  jz      short loc_180004431
0x18000441d  call    cs:__imp_CloseHandle
0x180004424  nop     dword ptr [rax+rax+00h]
0x180004429  test    eax, eax
0x18000442b  jz      loc_1800044ED
0x180004431  mov     eax, ebx
0x180004433  jmp     short loc_180004470
0x180004435  mov     rbx, [rsp+270h+hObject]
0x18000443a  test    rdi, rdi
0x18000443d  jz      short loc_180004456
0x18000443f  mov     rcx, rdi; hMutex
0x180004442  call    cs:__imp_ReleaseMutex
0x180004449  nop     dword ptr [rax+rax+00h]
0x18000444e  test    eax, eax
0x180004450  jz      loc_1800044FF
0x180004456  test    rbx, rbx
0x180004459  jz      short loc_18000446E
0x18000445b  mov     rcx, rbx; hObject
0x18000445e  call    cs:__imp_CloseHandle
0x180004465  nop     dword ptr [rax+rax+00h]
0x18000446a  test    eax, eax
0x18000446c  jz      short loc_180004498
0x18000446e  xor     eax, eax
0x180004470  mov     rcx, [rbp+170h+var_20]
0x180004477  xor     rcx, rsp; StackCookie
0x18000447a  call    __security_check_cookie
0x18000447f  lea     r11, [rsp+270h+var_10]
0x180004487  mov     rbx, [r11+30h]
0x18000448b  mov     rsi, [r11+38h]
0x18000448f  mov     rsp, r11
0x180004492  pop     r14
0x180004494  pop     rdi
0x180004495  pop     rbp
0x180004496  retn
0x180004498  mov     rcx, [rbp+178h]; this
0x18000449f  mov     edx, 0A0Bh; void *
0x1800044a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044aa  mov     rcx, [rbp+178h]; this
0x1800044b1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800044b7  mov     rcx, [rbp+178h]; this
0x1800044be  mov     edx, 0A15h; void *
0x1800044c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044c9  mov     rcx, [rbp+178h]; this
0x1800044d0  mov     edx, 0A0Bh; void *
0x1800044d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044db  mov     rcx, [rbp+178h]; this
0x1800044e2  mov     edx, 0A15h; void *
0x1800044e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044ed  mov     rcx, [rbp+178h]; this
0x1800044f4  mov     edx, 0A0Bh; void *
0x1800044f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044ff  mov     rcx, [rbp+178h]; this
0x180004506  mov     edx, 0A15h; void *
0x18000450b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
