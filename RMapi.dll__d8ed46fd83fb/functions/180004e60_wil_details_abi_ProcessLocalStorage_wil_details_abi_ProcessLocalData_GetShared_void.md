# wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)

- ea: `0x180004e60`
- end: `0x18000503e`
- name: `?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004dfc`

## callees

- `0x180004e60`
- `0x180005050`
- `0x18000aac0`
- `0x18000d2a0`
- `0x18000f974`
- `0x180010140`
- `0x18001043c`
- `0x180010468`
- `0x1800106a4`
- `0x180010754`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e9d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004ed9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004ed9`

## pseudocode

```c
__int64 wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared()
{
  __int64 v0; // rdi
  void *v1; // rsi
  DWORD CurrentProcessId; // eax
  wil::details *v3; // rcx
  wil::details *v4; // rbx
  __int64 v5; // rdx
  __int64 result; // rax
  int Pointer; // eax
  void *v8; // rdx
  void *v9; // rdx
  int v10; // eax
  void *v11; // rdx
  wil::details *Mutex; // [rsp+30h] [rbp-248h] BYREF
  wil::details *v13; // [rsp+38h] [rbp-240h] BYREF
  void *v14; // [rsp+40h] [rbp-238h] BYREF
  void *v15; // [rsp+48h] [rbp-230h]
  WCHAR Name[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v0 = wil::details_abi::g_pProcessLocalData;
  if ( *(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    goto LABEL_4;
  v1 = 0;
  v15 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v4 = Mutex;
  if ( !Mutex )
  {
    if ( (int)wil::details::GetLastErrorFailHr(v3) < 0 )
      goto LABEL_4;
    goto LABEL_11;
  }
  v13 = 0;
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &Mutex,
    &v13);
  v14 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      120);
    if ( v13 )
      wil::details::ReleaseMutex(v13, v9);
    wil::details::CloseHandle(v4, v9);
    goto LABEL_4;
  }
  v1 = v14;
  if ( v14 )
  {
    ++*(_DWORD *)v14;
LABEL_23:
    if ( v13 )
      wil::details::ReleaseMutex(v13, v8);
    if ( v4 )
      wil::details::CloseHandle(v4, v8);
LABEL_11:
    if ( !*(_QWORD *)(v0 + 8) )
      *(_QWORD *)(v0 + 8) = v1;
    goto LABEL_4;
  }
  v10 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
  if ( v10 >= 0 )
  {
    v1 = v15;
    v4 = Mutex;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v10, 120);
  if ( v13 )
    wil::details::ReleaseMutex(v13, v11);
  if ( Mutex )
    wil::details::CloseHandle(Mutex, v11);
LABEL_4:
  v5 = *(_QWORD *)(v0 + 8);
  result = v5 + 32;
  if ( !v5 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180004e60  mov     r11, rsp
0x180004e63  push    rdi
0x180004e64  sub     rsp, 270h
0x180004e6b  mov     rax, cs:__security_cookie
0x180004e72  xor     rax, rsp
0x180004e75  mov     [rsp+278h+var_18], rax
0x180004e7d  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004e84  cmp     qword ptr [rdi+8], 0
0x180004e89  jnz     short loc_180004F05
0x180004e8b  mov     [r11+8], rbx
0x180004e8f  mov     rbx, [rdi]
0x180004e92  mov     [r11+10h], rsi
0x180004e96  xor     esi, esi
0x180004e98  mov     [rsp+278h+var_230], rsi
0x180004e9d  call    cs:__imp_GetCurrentProcessId
0x180004ea3  mov     [rsp+278h+var_250], rbx
0x180004ea8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004eaf  mov     r9d, eax
0x180004eb2  mov     [rsp+278h+var_258], 78h ; 'x'; int
0x180004eba  mov     edx, 104h; unsigned __int64
0x180004ebf  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180004ec4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004ec9  mov     r9d, 1F0001h; dwDesiredAccess
0x180004ecf  lea     rdx, [rsp+278h+Name]; lpName
0x180004ed4  xor     r8d, r8d; dwFlags
0x180004ed7  xor     ecx, ecx; lpMutexAttributes
0x180004ed9  call    cs:__imp_CreateMutexExW
0x180004edf  mov     [rsp+278h+var_248], rax
0x180004ee4  mov     rbx, rax
0x180004ee7  test    rax, rax
0x180004eea  jnz     short loc_180004F5A
0x180004eec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004ef1  test    eax, eax
0x180004ef3  jns     short loc_180004F4D
0x180004ef5  mov     rbx, [rsp+278h+arg_0]
0x180004efd  mov     rsi, [rsp+278h+arg_8]
0x180004f05  mov     rdx, [rdi+8]
0x180004f09  xor     ecx, ecx
0x180004f0b  test    rdx, rdx
0x180004f0e  lea     rax, [rdx+20h]
0x180004f12  cmovz   rax, rcx
0x180004f16  mov     rcx, [rsp+278h+var_18]
0x180004f1e  xor     rcx, rsp; StackCookie
0x180004f21  call    __security_check_cookie
0x180004f26  add     rsp, 270h
0x180004f2d  pop     rdi
0x180004f2e  retn
0x180004f2f  mov     rcx, [rsp+278h+var_248]; this
0x180004f34  test    rcx, rcx
0x180004f37  jz      short loc_180004EF5
0x180004f39  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004f3e  jmp     short loc_180004EF5
0x180004f40  test    rbx, rbx
0x180004f43  jz      short loc_180004F4D
0x180004f45  mov     rcx, rbx; this
0x180004f48  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004f4d  cmp     qword ptr [rdi+8], 0
0x180004f52  jnz     short loc_180004EF5
0x180004f54  mov     [rdi+8], rsi
0x180004f58  jmp     short loc_180004EF5
0x180004f5a  lea     rdx, [rsp+278h+var_240]
0x180004f5f  mov     [rsp+278h+var_240], rsi
0x180004f64  lea     rcx, [rsp+278h+var_248]
0x180004f69  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004f6e  lea     rdx, [rsp+278h+var_238]; void **
0x180004f73  mov     [rsp+278h+var_238], rsi
0x180004f78  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180004f7d  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180004f82  test    eax, eax
0x180004f84  jns     short loc_180004FBE
0x180004f86  mov     rcx, [rsp+278h]; this
0x180004f8e  lea     r8, aWil; "wil"
0x180004f95  mov     r9d, eax; char *
0x180004f98  mov     edx, 12Eh; void *
0x180004f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004fa2  mov     rcx, [rsp+278h+var_240]; this
0x180004fa7  test    rcx, rcx
0x180004faa  jz      short loc_180004FB1
0x180004fac  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180004fb1  mov     rcx, rbx; this
0x180004fb4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004fb9  jmp     loc_180004EF5
0x180004fbe  mov     rsi, [rsp+278h+var_238]
0x180004fc3  test    rsi, rsi
0x180004fc6  jz      short loc_180004FD0
0x180004fc8  mov     eax, [rsi]
0x180004fca  inc     eax
0x180004fcc  mov     [rsi], eax
0x180004fce  jmp     short loc_180005026
0x180004fd0  lea     r8, [rsp+278h+var_230]
0x180004fd5  lea     rdx, [rsp+278h+var_248]
0x180004fda  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180004fdf  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004fe4  test    eax, eax
0x180004fe6  jns     short loc_18000501C
0x180004fe8  mov     rcx, [rsp+278h]; this
0x180004ff0  lea     r8, aWil; "wil"
0x180004ff7  mov     r9d, eax; char *
0x180004ffa  mov     edx, 137h; void *
0x180004fff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005004  mov     rcx, [rsp+278h+var_240]; this
0x180005009  test    rcx, rcx
0x18000500c  jz      loc_180004F2F
0x180005012  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180005017  jmp     loc_180004F2F
0x18000501c  mov     rsi, [rsp+278h+var_230]
0x180005021  mov     rbx, [rsp+278h+var_248]
0x180005026  mov     rcx, [rsp+278h+var_240]; this
0x18000502b  test    rcx, rcx
0x18000502e  jz      loc_180004F40
0x180005034  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180005039  jmp     loc_180004F40
```
