# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001dd20`
- end: `0x18001dec7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180043ea8`

## callees

- `0x18000c908`
- `0x18000dc10`
- `0x18000dea4`
- `0x180019908`
- `0x18001dd20`
- `0x18001ded0`
- `0x18001deec`
- `0x18001df88`
- `0x18001e798`
- `0x18001e840`
- `0x18002c570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001dd9a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001dd9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dd55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dd55`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  int Pointer; // eax
  unsigned int v9; // edi
  void *v10; // rdx
  _DWORD *v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  void *v14; // rdx
  void *v15; // rdx
  wil::details *v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v18; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v16 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v16,
    Mutex);
  v6 = v16;
  if ( !v16 )
    return wil::details::GetLastErrorFailHr(v5);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v16,
    v17);
  v18 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v18);
  v9 = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    wil::details::CloseHandle(v6, v10);
    return v9;
  }
  v11 = v18;
  if ( v18 )
  {
    *a2 = v18;
    ++*v11;
LABEL_12:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    if ( v6 )
      wil::details::CloseHandle(v6, v15);
    return 0;
  }
  v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v6 = v16;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v12, 304);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
  if ( v16 )
    wil::details::CloseHandle(v16, v14);
  return v13;
}

```

## disassembly

```asm
0x18001dd20  mov     [rsp-8+arg_10], rbx
0x18001dd25  push    rbp
0x18001dd26  push    rsi
0x18001dd27  push    rdi
0x18001dd28  lea     rbp, [rsp-170h]
0x18001dd30  sub     rsp, 270h
0x18001dd37  mov     rax, cs:__security_cookie
0x18001dd3e  xor     rax, rsp
0x18001dd41  mov     [rbp+180h+var_20], rax
0x18001dd48  mov     rsi, rdx
0x18001dd4b  mov     qword ptr [rdx], 0
0x18001dd52  mov     rbx, rcx
0x18001dd55  call    cs:__imp_GetCurrentProcessId
0x18001dd5b  mov     [rsp+280h+var_258], rbx
0x18001dd60  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001dd67  mov     r9d, eax
0x18001dd6a  mov     [rsp+280h+var_260], 130h; int
0x18001dd72  mov     edx, 104h; unsigned __int64
0x18001dd77  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001dd7c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001dd81  mov     r9d, 1F0001h; dwDesiredAccess
0x18001dd87  mov     [rsp+280h+var_250], 0
0x18001dd90  xor     r8d, r8d; dwFlags
0x18001dd93  lea     rdx, [rsp+280h+Name]; lpName
0x18001dd98  xor     ecx, ecx; lpMutexAttributes
0x18001dd9a  call    cs:__imp_CreateMutexExW
0x18001dda0  mov     rdx, rax
0x18001dda3  lea     rcx, [rsp+280h+var_250]
0x18001dda8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001ddad  mov     rbx, [rsp+280h+var_250]
0x18001ddb2  test    rbx, rbx
0x18001ddb5  jnz     short loc_18001DDC1
0x18001ddb7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001ddbc  jmp     loc_18001DEA5
0x18001ddc1  lea     rdx, [rsp+280h+var_248]
0x18001ddc6  lea     rcx, [rsp+280h+var_250]
0x18001ddcb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001ddd0  lea     rdx, [rsp+280h+var_240]; void **
0x18001ddd5  mov     [rsp+280h+var_240], 0
0x18001ddde  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001dde3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001dde8  mov     edi, eax
0x18001ddea  test    eax, eax
0x18001ddec  jns     short loc_18001DE22
0x18001ddee  mov     rcx, [rbp+188h]; this
0x18001ddf5  lea     r8, aWil; "wil"
0x18001ddfc  mov     r9d, eax; char *
0x18001ddff  mov     edx, 12Eh; void *
0x18001de04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de09  lea     rcx, [rsp+280h+var_248]
0x18001de0e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001de13  mov     rcx, rbx; this
0x18001de16  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001de1b  mov     eax, edi
0x18001de1d  jmp     loc_18001DEA5
0x18001de22  mov     rcx, [rsp+280h+var_240]
0x18001de27  test    rcx, rcx
0x18001de2a  jz      short loc_18001DE37
0x18001de2c  mov     [rsi], rcx
0x18001de2f  mov     eax, [rcx]
0x18001de31  inc     eax
0x18001de33  mov     [rcx], eax
0x18001de35  jmp     short loc_18001DE8C
0x18001de37  mov     r8, rsi
0x18001de3a  lea     rdx, [rsp+280h+var_250]
0x18001de3f  lea     rcx, [rsp+280h+Name]
0x18001de44  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001de49  mov     ebx, eax
0x18001de4b  test    eax, eax
0x18001de4d  jns     short loc_18001DE87
0x18001de4f  mov     rcx, [rbp+188h]; this
0x18001de56  lea     r8, aWil; "wil"
0x18001de5d  mov     r9d, eax; char *
0x18001de60  mov     edx, 137h; void *
0x18001de65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de6a  lea     rcx, [rsp+280h+var_248]
0x18001de6f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001de74  mov     rcx, [rsp+280h+var_250]; this
0x18001de79  test    rcx, rcx
0x18001de7c  jz      short loc_18001DE83
0x18001de7e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001de83  mov     eax, ebx
0x18001de85  jmp     short loc_18001DEA5
0x18001de87  mov     rbx, [rsp+280h+var_250]
0x18001de8c  lea     rcx, [rsp+280h+var_248]
0x18001de91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001de96  test    rbx, rbx
0x18001de99  jz      short loc_18001DEA3
0x18001de9b  mov     rcx, rbx; this
0x18001de9e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001dea3  xor     eax, eax
0x18001dea5  mov     rcx, [rbp+180h+var_20]
0x18001deac  xor     rcx, rsp; StackCookie
0x18001deaf  call    __security_check_cookie
0x18001deb4  mov     rbx, [rsp+280h+arg_10]
0x18001debc  add     rsp, 270h
0x18001dec3  pop     rdi
0x18001dec4  pop     rsi
0x18001dec5  pop     rbp
0x18001dec6  retn
```
