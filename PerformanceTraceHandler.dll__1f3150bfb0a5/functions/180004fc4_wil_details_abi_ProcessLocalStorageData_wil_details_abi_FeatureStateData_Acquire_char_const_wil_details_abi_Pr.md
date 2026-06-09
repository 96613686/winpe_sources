# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004fc4`
- end: `0x18000512a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005378`

## callees

- `0x180002c00`
- `0x1800049b0`
- `0x1800049cc`
- `0x180004fc4`
- `0x180005c28`
- `0x180006abc`
- `0x180007f3c`
- `0x180008684`
- `0x180008b6c`
- `0x180009404`
- `0x180009aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005041`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005041`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004ffc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004ffc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180004fc4  mov     [rsp-8+arg_10], rbx
0x180004fc9  mov     [rsp-8+arg_18], rdi
0x180004fce  push    rbp
0x180004fcf  lea     rbp, [rsp-170h]
0x180004fd7  sub     rsp, 270h
0x180004fde  mov     rax, cs:__security_cookie
0x180004fe5  xor     rax, rsp
0x180004fe8  mov     [rbp+170h+var_10], rax
0x180004fef  mov     rdi, rdx
0x180004ff2  mov     qword ptr [rdx], 0
0x180004ff9  mov     rbx, rcx
0x180004ffc  call    cs:__imp_GetCurrentProcessId
0x180005002  mov     [rsp+270h+var_248], rbx
0x180005007  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000500e  mov     r9d, eax
0x180005011  mov     [rsp+270h+var_250], 130h; int
0x180005019  mov     edx, 104h; unsigned __int64
0x18000501e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005023  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005028  mov     r9d, 1F0001h; dwDesiredAccess
0x18000502e  mov     [rsp+270h+var_240], 0
0x180005037  xor     r8d, r8d; dwFlags
0x18000503a  lea     rdx, [rsp+270h+Name]; lpName
0x18000503f  xor     ecx, ecx; lpMutexAttributes
0x180005041  call    cs:__imp_CreateMutexExW
0x180005047  mov     rdx, rax
0x18000504a  lea     rcx, [rsp+270h+var_240]
0x18000504f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005054  cmp     [rsp+270h+var_240], 0
0x18000505a  jnz     short loc_180005065
0x18000505c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005061  mov     ebx, eax
0x180005063  jmp     short loc_1800050D8
0x180005065  lea     rdx, [rsp+270h+var_238]
0x18000506a  lea     rcx, [rsp+270h+var_240]
0x18000506f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005074  lea     rdx, [rsp+270h+var_230]; void **
0x180005079  mov     [rsp+270h+var_230], 0
0x180005082  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005087  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000508c  mov     ebx, eax
0x18000508e  test    eax, eax
0x180005090  jns     short loc_1800050B9
0x180005092  mov     edx, 12Eh; void *
0x180005097  mov     rcx, [rbp+178h]; this
0x18000509e  lea     r8, aWil; "wil"
0x1800050a5  mov     r9d, eax; char *
0x1800050a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050ad  lea     rcx, [rsp+270h+var_238]
0x1800050b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800050b7  jmp     short loc_1800050D8
0x1800050b9  mov     rcx, [rsp+270h+var_230]
0x1800050be  test    rcx, rcx
0x1800050c1  jz      short loc_180005108
0x1800050c3  mov     [rdi], rcx
0x1800050c6  mov     eax, [rcx]
0x1800050c8  inc     eax
0x1800050ca  mov     [rcx], eax
0x1800050cc  lea     rcx, [rsp+270h+var_238]
0x1800050d1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800050d6  xor     ebx, ebx
0x1800050d8  lea     rcx, [rsp+270h+var_240]
0x1800050dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800050e2  mov     eax, ebx
0x1800050e4  mov     rcx, [rbp+170h+var_10]
0x1800050eb  xor     rcx, rsp; StackCookie
0x1800050ee  call    __security_check_cookie
0x1800050f3  lea     r11, [rsp+270h+var_s0]
0x1800050fb  mov     rbx, [r11+20h]
0x1800050ff  mov     rdi, [r11+28h]
0x180005103  mov     rsp, r11
0x180005106  pop     rbp
0x180005107  retn
0x180005108  mov     r8, rdi
0x18000510b  lea     rdx, [rsp+270h+var_240]
0x180005110  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005115  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000511a  mov     ebx, eax
0x18000511c  test    eax, eax
0x18000511e  jns     short loc_1800050CC
0x180005120  mov     edx, 137h
0x180005125  jmp     loc_180005097
```
