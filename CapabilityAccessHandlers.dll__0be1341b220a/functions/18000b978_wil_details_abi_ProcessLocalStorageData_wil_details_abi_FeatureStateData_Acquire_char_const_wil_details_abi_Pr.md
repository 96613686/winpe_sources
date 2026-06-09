# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000b978`
- end: `0x18000bade`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000bb54`

## callees

- `0x180004c70`
- `0x1800071a4`
- `0x1800071c0`
- `0x180007f58`
- `0x1800090f4`
- `0x1800096d0`
- `0x180009838`
- `0x180009be0`
- `0x180009cd0`
- `0x18000b978`
- `0x18000c01c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b9f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b9f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b9b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b9b0`

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
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
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
      (HANDLE *)&v12,
      &v13);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
0x18000b978  mov     [rsp-8+arg_10], rbx
0x18000b97d  mov     [rsp-8+arg_18], rdi
0x18000b982  push    rbp
0x18000b983  lea     rbp, [rsp-170h]
0x18000b98b  sub     rsp, 270h
0x18000b992  mov     rax, cs:__security_cookie
0x18000b999  xor     rax, rsp
0x18000b99c  mov     [rbp+170h+var_10], rax
0x18000b9a3  mov     rdi, rdx
0x18000b9a6  mov     qword ptr [rdx], 0
0x18000b9ad  mov     rbx, rcx
0x18000b9b0  call    cs:__imp_GetCurrentProcessId
0x18000b9b6  mov     [rsp+270h+var_248], rbx
0x18000b9bb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b9c2  mov     r9d, eax
0x18000b9c5  mov     [rsp+270h+var_250], 130h; int
0x18000b9cd  mov     edx, 104h; unsigned __int64
0x18000b9d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b9d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b9dc  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b9e2  mov     [rsp+270h+var_240], 0
0x18000b9eb  xor     r8d, r8d; dwFlags
0x18000b9ee  lea     rdx, [rsp+270h+Name]; lpName
0x18000b9f3  xor     ecx, ecx; lpMutexAttributes
0x18000b9f5  call    cs:__imp_CreateMutexExW
0x18000b9fb  mov     rdx, rax
0x18000b9fe  lea     rcx, [rsp+270h+var_240]
0x18000ba03  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ba08  cmp     [rsp+270h+var_240], 0
0x18000ba0e  jnz     short loc_18000BA19
0x18000ba10  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ba15  mov     ebx, eax
0x18000ba17  jmp     short loc_18000BA8C
0x18000ba19  lea     rdx, [rsp+270h+var_238]
0x18000ba1e  lea     rcx, [rsp+270h+var_240]
0x18000ba23  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000ba28  lea     rdx, [rsp+270h+var_230]; void **
0x18000ba2d  mov     [rsp+270h+var_230], 0
0x18000ba36  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000ba3b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000ba40  mov     ebx, eax
0x18000ba42  test    eax, eax
0x18000ba44  jns     short loc_18000BA6D
0x18000ba46  mov     edx, 12Eh; void *
0x18000ba4b  mov     rcx, [rbp+178h]; this
0x18000ba52  lea     r8, aWil; "wil"
0x18000ba59  mov     r9d, eax; char *
0x18000ba5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba61  lea     rcx, [rsp+270h+var_238]
0x18000ba66  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ba6b  jmp     short loc_18000BA8C
0x18000ba6d  mov     rcx, [rsp+270h+var_230]
0x18000ba72  test    rcx, rcx
0x18000ba75  jz      short loc_18000BABC
0x18000ba77  mov     [rdi], rcx
0x18000ba7a  mov     eax, [rcx]
0x18000ba7c  inc     eax
0x18000ba7e  mov     [rcx], eax
0x18000ba80  lea     rcx, [rsp+270h+var_238]
0x18000ba85  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ba8a  xor     ebx, ebx
0x18000ba8c  lea     rcx, [rsp+270h+var_240]
0x18000ba91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ba96  mov     eax, ebx
0x18000ba98  mov     rcx, [rbp+170h+var_10]
0x18000ba9f  xor     rcx, rsp; StackCookie
0x18000baa2  call    __security_check_cookie
0x18000baa7  lea     r11, [rsp+270h+var_s0]
0x18000baaf  mov     rbx, [r11+20h]
0x18000bab3  mov     rdi, [r11+28h]
0x18000bab7  mov     rsp, r11
0x18000baba  pop     rbp
0x18000babb  retn
0x18000babc  mov     r8, rdi
0x18000babf  lea     rdx, [rsp+270h+var_240]
0x18000bac4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000bac9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000bace  mov     ebx, eax
0x18000bad0  test    eax, eax
0x18000bad2  jns     short loc_18000BA80
0x18000bad4  mov     edx, 137h
0x18000bad9  jmp     loc_18000BA4B
```
