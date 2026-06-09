# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004f14`
- end: `0x18000507a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005a00`

## callees

- `0x1800021d0`
- `0x1800046b0`
- `0x1800046cc`
- `0x180004f14`
- `0x1800069b8`
- `0x1800078f8`
- `0x18000972c`
- `0x180009f8c`
- `0x18000a58c`
- `0x18000aef4`
- `0x18000b38c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004f4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004f4c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004f91`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004f91`

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
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
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
0x180004f14  mov     [rsp-8+arg_10], rbx
0x180004f19  mov     [rsp-8+arg_18], rdi
0x180004f1e  push    rbp
0x180004f1f  lea     rbp, [rsp-170h]
0x180004f27  sub     rsp, 270h
0x180004f2e  mov     rax, cs:__security_cookie
0x180004f35  xor     rax, rsp
0x180004f38  mov     [rbp+170h+var_10], rax
0x180004f3f  mov     rdi, rdx
0x180004f42  mov     qword ptr [rdx], 0
0x180004f49  mov     rbx, rcx
0x180004f4c  call    cs:__imp_GetCurrentProcessId
0x180004f52  mov     [rsp+270h+var_248], rbx
0x180004f57  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004f5e  mov     r9d, eax
0x180004f61  mov     [rsp+270h+var_250], 130h; int
0x180004f69  mov     edx, 104h; unsigned __int64
0x180004f6e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004f73  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004f78  mov     r9d, 1F0001h; dwDesiredAccess
0x180004f7e  mov     [rsp+270h+var_240], 0
0x180004f87  xor     r8d, r8d; dwFlags
0x180004f8a  lea     rdx, [rsp+270h+Name]; lpName
0x180004f8f  xor     ecx, ecx; lpMutexAttributes
0x180004f91  call    cs:__imp_CreateMutexExW
0x180004f97  mov     rdx, rax
0x180004f9a  lea     rcx, [rsp+270h+var_240]
0x180004f9f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004fa4  cmp     [rsp+270h+var_240], 0
0x180004faa  jnz     short loc_180004FB5
0x180004fac  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004fb1  mov     ebx, eax
0x180004fb3  jmp     short loc_180005028
0x180004fb5  lea     rdx, [rsp+270h+var_238]
0x180004fba  lea     rcx, [rsp+270h+var_240]
0x180004fbf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004fc4  lea     rdx, [rsp+270h+var_230]; void **
0x180004fc9  mov     [rsp+270h+var_230], 0
0x180004fd2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004fd7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004fdc  mov     ebx, eax
0x180004fde  test    eax, eax
0x180004fe0  jns     short loc_180005009
0x180004fe2  mov     edx, 12Eh; void *
0x180004fe7  mov     rcx, [rbp+178h]; this
0x180004fee  lea     r8, aWil; "wil"
0x180004ff5  mov     r9d, eax; char *
0x180004ff8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ffd  lea     rcx, [rsp+270h+var_238]
0x180005002  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005007  jmp     short loc_180005028
0x180005009  mov     rcx, [rsp+270h+var_230]
0x18000500e  test    rcx, rcx
0x180005011  jz      short loc_180005058
0x180005013  mov     [rdi], rcx
0x180005016  mov     eax, [rcx]
0x180005018  inc     eax
0x18000501a  mov     [rcx], eax
0x18000501c  lea     rcx, [rsp+270h+var_238]
0x180005021  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005026  xor     ebx, ebx
0x180005028  lea     rcx, [rsp+270h+var_240]
0x18000502d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005032  mov     eax, ebx
0x180005034  mov     rcx, [rbp+170h+var_10]
0x18000503b  xor     rcx, rsp; StackCookie
0x18000503e  call    __security_check_cookie
0x180005043  lea     r11, [rsp+270h+var_s0]
0x18000504b  mov     rbx, [r11+20h]
0x18000504f  mov     rdi, [r11+28h]
0x180005053  mov     rsp, r11
0x180005056  pop     rbp
0x180005057  retn
0x180005058  mov     r8, rdi
0x18000505b  lea     rdx, [rsp+270h+var_240]
0x180005060  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005065  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000506a  mov     ebx, eax
0x18000506c  test    eax, eax
0x18000506e  jns     short loc_18000501C
0x180005070  mov     edx, 137h
0x180005075  jmp     loc_180004FE7
```
