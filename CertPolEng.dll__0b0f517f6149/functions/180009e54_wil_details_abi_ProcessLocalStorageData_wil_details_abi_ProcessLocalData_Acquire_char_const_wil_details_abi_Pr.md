# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009e54`
- end: `0x180009fba`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180010374`

## callees

- `0x180009190`
- `0x180009e54`
- `0x18000a2ec`
- `0x18000a934`
- `0x18000a950`
- `0x18000a978`
- `0x18000f5b0`
- `0x180010784`
- `0x180011c60`
- `0x180012404`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009ed1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009ed1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009e8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009e8c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180009e54  mov     [rsp-8+arg_10], rbx
0x180009e59  mov     [rsp-8+arg_18], rdi
0x180009e5e  push    rbp
0x180009e5f  lea     rbp, [rsp-170h]
0x180009e67  sub     rsp, 270h
0x180009e6e  mov     rax, cs:__security_cookie
0x180009e75  xor     rax, rsp
0x180009e78  mov     [rbp+170h+var_10], rax
0x180009e7f  mov     rdi, rdx
0x180009e82  mov     qword ptr [rdx], 0
0x180009e89  mov     rbx, rcx
0x180009e8c  call    cs:__imp_GetCurrentProcessId
0x180009e92  mov     [rsp+270h+var_248], rbx
0x180009e97  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009e9e  mov     r9d, eax
0x180009ea1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180009ea9  mov     edx, 104h; unsigned __int64
0x180009eae  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009eb3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009eb8  mov     r9d, 1F0001h; dwDesiredAccess
0x180009ebe  mov     [rsp+270h+var_240], 0
0x180009ec7  xor     r8d, r8d; dwFlags
0x180009eca  lea     rdx, [rsp+270h+Name]; lpName
0x180009ecf  xor     ecx, ecx; lpMutexAttributes
0x180009ed1  call    cs:__imp_CreateMutexExW
0x180009ed7  mov     rdx, rax
0x180009eda  lea     rcx, [rsp+270h+var_240]
0x180009edf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009ee4  cmp     [rsp+270h+var_240], 0
0x180009eea  jnz     short loc_180009EF5
0x180009eec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009ef1  mov     ebx, eax
0x180009ef3  jmp     short loc_180009F68
0x180009ef5  lea     rdx, [rsp+270h+var_238]
0x180009efa  lea     rcx, [rsp+270h+var_240]
0x180009eff  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180009f04  lea     rdx, [rsp+270h+var_230]; void **
0x180009f09  mov     [rsp+270h+var_230], 0
0x180009f12  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009f17  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180009f1c  mov     ebx, eax
0x180009f1e  test    eax, eax
0x180009f20  jns     short loc_180009F49
0x180009f22  mov     edx, 12Eh; void *
0x180009f27  mov     rcx, [rbp+178h]; this
0x180009f2e  lea     r8, aWil; "wil"
0x180009f35  mov     r9d, eax; char *
0x180009f38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f3d  lea     rcx, [rsp+270h+var_238]
0x180009f42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009f47  jmp     short loc_180009F68
0x180009f49  mov     rcx, [rsp+270h+var_230]
0x180009f4e  test    rcx, rcx
0x180009f51  jz      short loc_180009F98
0x180009f53  mov     [rdi], rcx
0x180009f56  mov     eax, [rcx]
0x180009f58  inc     eax
0x180009f5a  mov     [rcx], eax
0x180009f5c  lea     rcx, [rsp+270h+var_238]
0x180009f61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009f66  xor     ebx, ebx
0x180009f68  lea     rcx, [rsp+270h+var_240]
0x180009f6d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009f72  mov     eax, ebx
0x180009f74  mov     rcx, [rbp+170h+var_10]
0x180009f7b  xor     rcx, rsp; StackCookie
0x180009f7e  call    __security_check_cookie
0x180009f83  lea     r11, [rsp+270h+var_s0]
0x180009f8b  mov     rbx, [r11+20h]
0x180009f8f  mov     rdi, [r11+28h]
0x180009f93  mov     rsp, r11
0x180009f96  pop     rbp
0x180009f97  retn
0x180009f98  mov     r8, rdi
0x180009f9b  lea     rdx, [rsp+270h+var_240]
0x180009fa0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009fa5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009faa  mov     ebx, eax
0x180009fac  test    eax, eax
0x180009fae  jns     short loc_180009F5C
0x180009fb0  mov     edx, 137h
0x180009fb5  jmp     loc_180009F27
```
