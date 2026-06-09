# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002fbd8`
- end: `0x18002fd47`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800307d4`

## callees

- `0x180015050`
- `0x18002fafc`
- `0x18002fb18`
- `0x18002fbd8`
- `0x180030660`
- `0x180030f98`
- `0x18003140c`
- `0x180031684`
- `0x1800319d0`
- `0x180031a90`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002fc55`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002fc55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002fc10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002fc10`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
    v12 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      &v12);
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
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x18002fbd8  mov     [rsp-8+arg_10], rbx
0x18002fbdd  mov     [rsp-8+arg_18], rdi
0x18002fbe2  push    rbp
0x18002fbe3  lea     rbp, [rsp-170h]
0x18002fbeb  sub     rsp, 270h
0x18002fbf2  mov     rax, cs:__security_cookie
0x18002fbf9  xor     rax, rsp
0x18002fbfc  mov     [rbp+170h+var_10], rax
0x18002fc03  mov     rdi, rdx
0x18002fc06  mov     qword ptr [rdx], 0
0x18002fc0d  mov     rbx, rcx
0x18002fc10  call    cs:__imp_GetCurrentProcessId
0x18002fc16  mov     [rsp+270h+var_248], rbx
0x18002fc1b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002fc22  mov     r9d, eax
0x18002fc25  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002fc2d  mov     edx, 104h; unsigned __int64
0x18002fc32  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002fc37  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002fc3c  mov     r9d, 1F0001h; dwDesiredAccess
0x18002fc42  mov     [rsp+270h+var_240], 0
0x18002fc4b  xor     r8d, r8d; dwFlags
0x18002fc4e  lea     rdx, [rsp+270h+Name]; lpName
0x18002fc53  xor     ecx, ecx; lpMutexAttributes
0x18002fc55  call    cs:__imp_CreateMutexExW
0x18002fc5b  mov     rdx, rax
0x18002fc5e  lea     rcx, [rsp+270h+var_240]
0x18002fc63  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002fc68  cmp     [rsp+270h+var_240], 0
0x18002fc6e  jnz     short loc_18002FC79
0x18002fc70  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002fc75  mov     ebx, eax
0x18002fc77  jmp     short loc_18002FCF5
0x18002fc79  lea     rdx, [rsp+270h+var_238]
0x18002fc7e  mov     [rsp+270h+var_238], 0
0x18002fc87  lea     rcx, [rsp+270h+var_240]
0x18002fc8c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002fc91  lea     rdx, [rsp+270h+var_230]; void **
0x18002fc96  mov     [rsp+270h+var_230], 0
0x18002fc9f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002fca4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002fca9  mov     ebx, eax
0x18002fcab  test    eax, eax
0x18002fcad  jns     short loc_18002FCD6
0x18002fcaf  mov     edx, 12Eh; void *
0x18002fcb4  mov     rcx, [rbp+178h]; this
0x18002fcbb  lea     r8, aWil; "wil"
0x18002fcc2  mov     r9d, eax; char *
0x18002fcc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fcca  lea     rcx, [rsp+270h+var_238]
0x18002fccf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002fcd4  jmp     short loc_18002FCF5
0x18002fcd6  mov     rcx, [rsp+270h+var_230]
0x18002fcdb  test    rcx, rcx
0x18002fcde  jz      short loc_18002FD25
0x18002fce0  mov     [rdi], rcx
0x18002fce3  mov     eax, [rcx]
0x18002fce5  inc     eax
0x18002fce7  mov     [rcx], eax
0x18002fce9  lea     rcx, [rsp+270h+var_238]
0x18002fcee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002fcf3  xor     ebx, ebx
0x18002fcf5  lea     rcx, [rsp+270h+var_240]
0x18002fcfa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002fcff  mov     eax, ebx
0x18002fd01  mov     rcx, [rbp+170h+var_10]
0x18002fd08  xor     rcx, rsp; StackCookie
0x18002fd0b  call    __security_check_cookie
0x18002fd10  lea     r11, [rsp+270h+var_s0]
0x18002fd18  mov     rbx, [r11+20h]
0x18002fd1c  mov     rdi, [r11+28h]
0x18002fd20  mov     rsp, r11
0x18002fd23  pop     rbp
0x18002fd24  retn
0x18002fd25  mov     r8, rdi
0x18002fd28  lea     rdx, [rsp+270h+var_240]
0x18002fd2d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002fd32  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002fd37  mov     ebx, eax
0x18002fd39  test    eax, eax
0x18002fd3b  jns     short loc_18002FCE9
0x18002fd3d  mov     edx, 137h
0x18002fd42  jmp     loc_18002FCB4
```
