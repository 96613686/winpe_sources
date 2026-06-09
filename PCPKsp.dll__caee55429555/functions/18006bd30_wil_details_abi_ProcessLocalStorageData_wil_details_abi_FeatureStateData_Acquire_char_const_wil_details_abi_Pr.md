# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18006bd30`
- end: `0x18006bea3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180078a08`

## callees

- `0x180011bd0`
- `0x1800133c4`
- `0x18004bf48`
- `0x1800573dc`
- `0x180058ec8`
- `0x18005c5e4`
- `0x18006bd30`
- `0x18006beac`
- `0x18006d0a0`
- `0x1800764d0`
- `0x180079090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18006bdb3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18006bdb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006bd68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006bd68`

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
0x18006bd30  mov     [rsp-8+arg_10], rbx
0x18006bd35  mov     [rsp-8+arg_18], rdi
0x18006bd3a  push    rbp
0x18006bd3b  lea     rbp, [rsp-170h]
0x18006bd43  sub     rsp, 270h
0x18006bd4a  mov     rax, cs:__security_cookie
0x18006bd51  xor     rax, rsp
0x18006bd54  mov     [rbp+170h+var_10], rax
0x18006bd5b  mov     rdi, rdx
0x18006bd5e  mov     qword ptr [rdx], 0
0x18006bd65  mov     rbx, rcx
0x18006bd68  call    cs:__imp_GetCurrentProcessId
0x18006bd6f  nop     dword ptr [rax+rax+00h]
0x18006bd74  mov     [rsp+270h+var_248], rbx
0x18006bd79  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18006bd80  mov     r9d, eax
0x18006bd83  mov     [rsp+270h+var_250], 130h; int
0x18006bd8b  mov     edx, 104h; unsigned __int64
0x18006bd90  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18006bd95  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006bd9a  mov     r9d, 1F0001h; dwDesiredAccess
0x18006bda0  mov     [rsp+270h+var_240], 0
0x18006bda9  xor     r8d, r8d; dwFlags
0x18006bdac  lea     rdx, [rsp+270h+Name]; lpName
0x18006bdb1  xor     ecx, ecx; lpMutexAttributes
0x18006bdb3  call    cs:__imp_CreateMutexExW
0x18006bdba  nop     dword ptr [rax+rax+00h]
0x18006bdbf  mov     rdx, rax
0x18006bdc2  lea     rcx, [rsp+270h+var_240]
0x18006bdc7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18006bdcc  cmp     [rsp+270h+var_240], 0
0x18006bdd2  jnz     short loc_18006BDDD
0x18006bdd4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18006bdd9  mov     ebx, eax
0x18006bddb  jmp     short loc_18006BE50
0x18006bddd  lea     rdx, [rsp+270h+var_238]
0x18006bde2  lea     rcx, [rsp+270h+var_240]
0x18006bde7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18006bdec  lea     rdx, [rsp+270h+var_230]; void **
0x18006bdf1  mov     [rsp+270h+var_230], 0
0x18006bdfa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18006bdff  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18006be04  mov     ebx, eax
0x18006be06  test    eax, eax
0x18006be08  jns     short loc_18006BE31
0x18006be0a  mov     edx, 12Eh; void *
0x18006be0f  mov     rcx, [rbp+178h]; this
0x18006be16  lea     r8, aWil; "wil"
0x18006be1d  mov     r9d, eax; char *
0x18006be20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006be25  lea     rcx, [rsp+270h+var_238]
0x18006be2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006be2f  jmp     short loc_18006BE50
0x18006be31  mov     rcx, [rsp+270h+var_230]
0x18006be36  test    rcx, rcx
0x18006be39  jz      short loc_18006BE81
0x18006be3b  mov     [rdi], rcx
0x18006be3e  mov     eax, [rcx]
0x18006be40  inc     eax
0x18006be42  mov     [rcx], eax
0x18006be44  lea     rcx, [rsp+270h+var_238]
0x18006be49  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006be4e  xor     ebx, ebx
0x18006be50  lea     rcx, [rsp+270h+var_240]
0x18006be55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006be5a  mov     eax, ebx
0x18006be5c  mov     rcx, [rbp+170h+var_10]
0x18006be63  xor     rcx, rsp; StackCookie
0x18006be66  call    __security_check_cookie
0x18006be6b  lea     r11, [rsp+270h+var_s0]
0x18006be73  mov     rbx, [r11+20h]
0x18006be77  mov     rdi, [r11+28h]
0x18006be7b  mov     rsp, r11
0x18006be7e  pop     rbp
0x18006be7f  retn
0x18006be81  mov     r8, rdi
0x18006be84  lea     rdx, [rsp+270h+var_240]
0x18006be89  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18006be8e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18006be93  mov     ebx, eax
0x18006be95  test    eax, eax
0x18006be97  jns     short loc_18006BE44
0x18006be99  mov     edx, 137h
0x18006be9e  jmp     loc_18006BE0F
```
