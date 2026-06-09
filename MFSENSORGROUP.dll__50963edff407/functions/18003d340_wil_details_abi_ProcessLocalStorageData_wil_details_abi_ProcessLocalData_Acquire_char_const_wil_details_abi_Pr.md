# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18003d340`
- end: `0x18003d4ea`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180046d68`

## callees

- `0x18000f518`
- `0x18003d340`
- `0x18003d4f0`
- `0x18003d71c`
- `0x18003d738`
- `0x18003d76c`
- `0x18003d8cc`
- `0x180044f30`
- `0x18004654c`
- `0x180046ff8`
- `0x180047738`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003d3bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003d3bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d378`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d378`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18003d340  mov     [rsp-8+arg_10], rbx
0x18003d345  mov     [rsp-8+arg_18], rdi
0x18003d34a  push    rbp
0x18003d34b  lea     rbp, [rsp-170h]
0x18003d353  sub     rsp, 270h
0x18003d35a  mov     rax, cs:__security_cookie
0x18003d361  xor     rax, rsp
0x18003d364  mov     [rbp+170h+var_10], rax
0x18003d36b  mov     rdi, rdx
0x18003d36e  mov     qword ptr [rdx], 0
0x18003d375  mov     rbx, rcx
0x18003d378  call    cs:__imp_GetCurrentProcessId
0x18003d37e  mov     [rsp+270h+var_248], rbx
0x18003d383  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003d38a  mov     r9d, eax
0x18003d38d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18003d395  mov     edx, 104h; unsigned __int64
0x18003d39a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d39f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d3a4  mov     r9d, 1F0001h; dwDesiredAccess
0x18003d3aa  mov     [rsp+270h+var_240], 0
0x18003d3b3  xor     r8d, r8d; dwFlags
0x18003d3b6  lea     rdx, [rsp+270h+Name]; lpName
0x18003d3bb  xor     ecx, ecx; lpMutexAttributes
0x18003d3bd  call    cs:__imp_CreateMutexExW
0x18003d3c3  mov     rdx, rax
0x18003d3c6  lea     rcx, [rsp+270h+var_240]
0x18003d3cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003d3d0  cmp     [rsp+270h+var_240], 0
0x18003d3d6  jnz     short loc_18003D3E4
0x18003d3d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003d3dd  mov     ebx, eax
0x18003d3df  jmp     loc_18003D495
0x18003d3e4  lea     rdx, [rsp+270h+var_238]
0x18003d3e9  lea     rcx, [rsp+270h+var_240]
0x18003d3ee  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003d3f3  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18003d3f8  mov     [rsp+270h+var_230], 0
0x18003d401  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d406  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18003d40b  mov     ebx, eax
0x18003d40d  test    eax, eax
0x18003d40f  jns     short loc_18003D46E
0x18003d411  mov     rcx, [rbp+178h]; this
0x18003d418  lea     r8, aWil; "wil"
0x18003d41f  mov     r9d, eax; char *
0x18003d422  mov     edx, 66h ; 'f'; void *
0x18003d427  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d42c  mov     rcx, [rbp+178h]; this
0x18003d433  lea     r8, aWil; "wil"
0x18003d43a  mov     r9d, ebx; char *
0x18003d43d  mov     edx, 6Fh ; 'o'; void *
0x18003d442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d447  mov     r9d, ebx; char *
0x18003d44a  mov     edx, 12Eh; void *
0x18003d44f  mov     rcx, [rbp+178h]; this
0x18003d456  lea     r8, aWil; "wil"
0x18003d45d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d462  lea     rcx, [rsp+270h+var_238]
0x18003d467  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d46c  jmp     short loc_18003D495
0x18003d46e  mov     rax, [rsp+270h+var_230]
0x18003d473  lea     rcx, ds:0[rax*4]
0x18003d47b  test    rcx, rcx
0x18003d47e  jz      short loc_18003D4C5
0x18003d480  mov     [rdi], rcx
0x18003d483  mov     eax, [rcx]
0x18003d485  inc     eax
0x18003d487  mov     [rcx], eax
0x18003d489  lea     rcx, [rsp+270h+var_238]
0x18003d48e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d493  xor     ebx, ebx
0x18003d495  lea     rcx, [rsp+270h+var_240]
0x18003d49a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d49f  mov     eax, ebx
0x18003d4a1  mov     rcx, [rbp+170h+var_10]
0x18003d4a8  xor     rcx, rsp; StackCookie
0x18003d4ab  call    __security_check_cookie
0x18003d4b0  lea     r11, [rsp+270h+var_s0]
0x18003d4b8  mov     rbx, [r11+20h]
0x18003d4bc  mov     rdi, [r11+28h]
0x18003d4c0  mov     rsp, r11
0x18003d4c3  pop     rbp
0x18003d4c4  retn
0x18003d4c5  mov     r8, rdi
0x18003d4c8  lea     rdx, [rsp+270h+var_240]
0x18003d4cd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d4d2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003d4d7  mov     ebx, eax
0x18003d4d9  test    eax, eax
0x18003d4db  jns     short loc_18003D489
0x18003d4dd  mov     r9d, eax
0x18003d4e0  mov     edx, 137h
0x18003d4e5  jmp     loc_18003D44F
```
