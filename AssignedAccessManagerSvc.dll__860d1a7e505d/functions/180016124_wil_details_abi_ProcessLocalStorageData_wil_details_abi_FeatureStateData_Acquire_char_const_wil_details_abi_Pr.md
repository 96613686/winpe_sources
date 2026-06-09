# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180016124`
- end: `0x18001628a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800197b4`

## callees

- `0x180006640`
- `0x180009cb8`
- `0x180009cd4`
- `0x18000a698`
- `0x18000b6b4`
- `0x18000bc4c`
- `0x18000be08`
- `0x18000c290`
- `0x18000c398`
- `0x180016124`
- `0x18001b554`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800161a1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800161a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001615c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001615c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180016124  mov     [rsp-8+arg_10], rbx
0x180016129  mov     [rsp-8+arg_18], rdi
0x18001612e  push    rbp
0x18001612f  lea     rbp, [rsp-170h]
0x180016137  sub     rsp, 270h
0x18001613e  mov     rax, cs:__security_cookie
0x180016145  xor     rax, rsp
0x180016148  mov     [rbp+170h+var_10], rax
0x18001614f  mov     rdi, rdx
0x180016152  mov     qword ptr [rdx], 0
0x180016159  mov     rbx, rcx
0x18001615c  call    cs:__imp_GetCurrentProcessId
0x180016162  mov     [rsp+270h+var_248], rbx
0x180016167  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001616e  mov     r9d, eax
0x180016171  mov     [rsp+270h+var_250], 130h; int
0x180016179  mov     edx, 104h; unsigned __int64
0x18001617e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180016183  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016188  mov     r9d, 1F0001h; dwDesiredAccess
0x18001618e  mov     [rsp+270h+var_240], 0
0x180016197  xor     r8d, r8d; dwFlags
0x18001619a  lea     rdx, [rsp+270h+Name]; lpName
0x18001619f  xor     ecx, ecx; lpMutexAttributes
0x1800161a1  call    cs:__imp_CreateMutexExW
0x1800161a7  mov     rdx, rax
0x1800161aa  lea     rcx, [rsp+270h+var_240]
0x1800161af  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800161b4  cmp     [rsp+270h+var_240], 0
0x1800161ba  jnz     short loc_1800161C5
0x1800161bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800161c1  mov     ebx, eax
0x1800161c3  jmp     short loc_180016238
0x1800161c5  lea     rdx, [rsp+270h+var_238]
0x1800161ca  lea     rcx, [rsp+270h+var_240]
0x1800161cf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800161d4  lea     rdx, [rsp+270h+var_230]; void **
0x1800161d9  mov     [rsp+270h+var_230], 0
0x1800161e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800161e7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800161ec  mov     ebx, eax
0x1800161ee  test    eax, eax
0x1800161f0  jns     short loc_180016219
0x1800161f2  mov     edx, 12Eh; void *
0x1800161f7  mov     rcx, [rbp+178h]; this
0x1800161fe  lea     r8, aWil; "wil"
0x180016205  mov     r9d, eax; char *
0x180016208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001620d  lea     rcx, [rsp+270h+var_238]
0x180016212  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016217  jmp     short loc_180016238
0x180016219  mov     rcx, [rsp+270h+var_230]
0x18001621e  test    rcx, rcx
0x180016221  jz      short loc_180016268
0x180016223  mov     [rdi], rcx
0x180016226  mov     eax, [rcx]
0x180016228  inc     eax
0x18001622a  mov     [rcx], eax
0x18001622c  lea     rcx, [rsp+270h+var_238]
0x180016231  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016236  xor     ebx, ebx
0x180016238  lea     rcx, [rsp+270h+var_240]
0x18001623d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016242  mov     eax, ebx
0x180016244  mov     rcx, [rbp+170h+var_10]
0x18001624b  xor     rcx, rsp; StackCookie
0x18001624e  call    __security_check_cookie
0x180016253  lea     r11, [rsp+270h+var_s0]
0x18001625b  mov     rbx, [r11+20h]
0x18001625f  mov     rdi, [r11+28h]
0x180016263  mov     rsp, r11
0x180016266  pop     rbp
0x180016267  retn
0x180016268  mov     r8, rdi
0x18001626b  lea     rdx, [rsp+270h+var_240]
0x180016270  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180016275  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001627a  mov     ebx, eax
0x18001627c  test    eax, eax
0x18001627e  jns     short loc_18001622C
0x180016280  mov     edx, 137h
0x180016285  jmp     loc_1800161F7
```
