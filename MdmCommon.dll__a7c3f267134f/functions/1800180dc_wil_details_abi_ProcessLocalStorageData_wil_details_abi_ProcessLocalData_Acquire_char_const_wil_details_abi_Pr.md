# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800180dc`
- end: `0x1800183a1`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180018900`

## callees

- `0x180001520`
- `0x180006174`
- `0x1800180dc`
- `0x1800183c4`
- `0x180018684`
- `0x180018b4c`
- `0x180019364`
- `0x180019b7c`
- `0x180019e9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018117`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018117`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800182ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800182ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800182ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800182ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180018185`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180018185`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001820c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001828f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800182d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001820c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001828f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800182d2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018159`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018159`

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
  unsigned int v14; // r8d
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // ebx
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
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
  v37 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v37);
  if ( 4 * v37 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_21;
  }
  v23 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
          Name,
          &hObject,
          a2);
  v25 = v23;
  if ( v23 >= 0 )
  {
    v6 = hObject;
LABEL_21:
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v24, (const char *)(unsigned int)v23, 120);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x1800180dc  mov     [rsp-8+arg_10], rbx
0x1800180e1  mov     [rsp-8+arg_18], rsi
0x1800180e6  push    rbp
0x1800180e7  push    rdi
0x1800180e8  push    r14
0x1800180ea  lea     rbp, [rsp-160h]
0x1800180f2  sub     rsp, 260h
0x1800180f9  mov     rax, cs:__security_cookie
0x180018100  xor     rax, rsp
0x180018103  mov     [rbp+170h+var_20], rax
0x18001810a  mov     r14, rdx
0x18001810d  mov     qword ptr [rdx], 0
0x180018114  mov     rbx, rcx
0x180018117  call    cs:__imp_GetCurrentProcessId
0x18001811e  nop     dword ptr [rax+rax+00h]
0x180018123  mov     [rsp+270h+var_248], rbx
0x180018128  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001812f  mov     r9d, eax
0x180018132  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001813a  mov     edx, 104h; unsigned __int64
0x18001813f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018144  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018149  mov     r9d, 1F0001h; dwDesiredAccess
0x18001814f  lea     rdx, [rsp+270h+Name]; lpName
0x180018154  xor     r8d, r8d; dwFlags
0x180018157  xor     ecx, ecx; lpMutexAttributes
0x180018159  call    cs:__imp_CreateMutexExW
0x180018160  nop     dword ptr [rax+rax+00h]
0x180018165  mov     [rsp+270h+hObject], rax
0x18001816a  mov     rbx, rax
0x18001816d  test    rax, rax
0x180018170  jnz     short loc_18001817C
0x180018172  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018177  jmp     loc_180018300
0x18001817c  xor     r8d, r8d; bAlertable
0x18001817f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180018182  mov     rcx, rbx; hHandle
0x180018185  call    cs:__imp_WaitForSingleObjectEx
0x18001818c  nop     dword ptr [rax+rax+00h]
0x180018191  cmp     eax, 102h
0x180018196  jz      short loc_1800181A8
0x180018198  test    eax, 0FFFFFF7Fh
0x18001819d  jnz     loc_18001833A
0x1800181a3  mov     rdi, rbx
0x1800181a6  jmp     short loc_1800181AA
0x1800181a8  xor     edi, edi
0x1800181aa  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x1800181af  mov     [rsp+270h+var_238], 0
0x1800181b8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800181bd  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800181c2  mov     esi, eax
0x1800181c4  test    eax, eax
0x1800181c6  jns     short loc_18001823E
0x1800181c8  mov     rcx, [rbp+178h]; this
0x1800181cf  mov     r9d, eax; char *
0x1800181d2  mov     edx, 66h ; 'f'; void *
0x1800181d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181dc  mov     rcx, [rbp+178h]; this
0x1800181e3  mov     r9d, esi; char *
0x1800181e6  mov     edx, 6Fh ; 'o'; void *
0x1800181eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181f0  mov     rcx, [rbp+178h]; this
0x1800181f7  mov     r9d, esi; char *
0x1800181fa  mov     edx, 12Eh; void *
0x1800181ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018204  test    rdi, rdi
0x180018207  jz      short loc_180018220
0x180018209  mov     rcx, rdi; hMutex
0x18001820c  call    cs:__imp_ReleaseMutex
0x180018213  nop     dword ptr [rax+rax+00h]
0x180018218  test    eax, eax
0x18001821a  jz      loc_180018347
0x180018220  mov     rcx, rbx; hObject
0x180018223  call    cs:__imp_CloseHandle
0x18001822a  nop     dword ptr [rax+rax+00h]
0x18001822f  test    eax, eax
0x180018231  jz      loc_180018359
0x180018237  mov     eax, esi
0x180018239  jmp     loc_180018300
0x18001823e  mov     rax, [rsp+270h+var_238]
0x180018243  lea     rcx, ds:0[rax*4]
0x18001824b  test    rcx, rcx
0x18001824e  jz      short loc_18001825B
0x180018250  mov     [r14], rcx
0x180018253  mov     eax, [rcx]
0x180018255  inc     eax
0x180018257  mov     [rcx], eax
0x180018259  jmp     short loc_1800182CA
0x18001825b  mov     r8, r14
0x18001825e  lea     rdx, [rsp+270h+hObject]
0x180018263  lea     rcx, [rsp+270h+Name]
0x180018268  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001826d  mov     ebx, eax
0x18001826f  test    eax, eax
0x180018271  jns     short loc_1800182C5
0x180018273  mov     rcx, [rbp+178h]; this
0x18001827a  mov     r9d, eax; char *
0x18001827d  mov     edx, 137h; void *
0x180018282  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018287  test    rdi, rdi
0x18001828a  jz      short loc_1800182A3
0x18001828c  mov     rcx, rdi; hMutex
0x18001828f  call    cs:__imp_ReleaseMutex
0x180018296  nop     dword ptr [rax+rax+00h]
0x18001829b  test    eax, eax
0x18001829d  jz      loc_18001836B
0x1800182a3  mov     rcx, [rsp+270h+hObject]; hObject
0x1800182a8  test    rcx, rcx
0x1800182ab  jz      short loc_1800182C1
0x1800182ad  call    cs:__imp_CloseHandle
0x1800182b4  nop     dword ptr [rax+rax+00h]
0x1800182b9  test    eax, eax
0x1800182bb  jz      loc_18001837D
0x1800182c1  mov     eax, ebx
0x1800182c3  jmp     short loc_180018300
0x1800182c5  mov     rbx, [rsp+270h+hObject]
0x1800182ca  test    rdi, rdi
0x1800182cd  jz      short loc_1800182E6
0x1800182cf  mov     rcx, rdi; hMutex
0x1800182d2  call    cs:__imp_ReleaseMutex
0x1800182d9  nop     dword ptr [rax+rax+00h]
0x1800182de  test    eax, eax
0x1800182e0  jz      loc_18001838F
0x1800182e6  test    rbx, rbx
0x1800182e9  jz      short loc_1800182FE
0x1800182eb  mov     rcx, rbx; hObject
0x1800182ee  call    cs:__imp_CloseHandle
0x1800182f5  nop     dword ptr [rax+rax+00h]
0x1800182fa  test    eax, eax
0x1800182fc  jz      short loc_180018328
0x1800182fe  xor     eax, eax
0x180018300  mov     rcx, [rbp+170h+var_20]
0x180018307  xor     rcx, rsp; StackCookie
0x18001830a  call    __security_check_cookie
0x18001830f  lea     r11, [rsp+270h+var_10]
0x180018317  mov     rbx, [r11+30h]
0x18001831b  mov     rsi, [r11+38h]
0x18001831f  mov     rsp, r11
0x180018322  pop     r14
0x180018324  pop     rdi
0x180018325  pop     rbp
0x180018326  retn
0x180018328  mov     rcx, [rbp+178h]; this
0x18001832f  mov     edx, 0A0Bh; void *
0x180018334  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001833a  mov     rcx, [rbp+178h]; this
0x180018341  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180018347  mov     rcx, [rbp+178h]; this
0x18001834e  mov     edx, 0A15h; void *
0x180018353  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018359  mov     rcx, [rbp+178h]; this
0x180018360  mov     edx, 0A0Bh; void *
0x180018365  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001836b  mov     rcx, [rbp+178h]; this
0x180018372  mov     edx, 0A15h; void *
0x180018377  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001837d  mov     rcx, [rbp+178h]; this
0x180018384  mov     edx, 0A0Bh; void *
0x180018389  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001838f  mov     rcx, [rbp+178h]; this
0x180018396  mov     edx, 0A15h; void *
0x18001839b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
