# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800380d4`
- end: `0x180038241`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `365`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180049d8c`

## callees

- `0x180017858`
- `0x1800380d4`
- `0x180038248`
- `0x180038270`
- `0x180038294`
- `0x1800382c8`
- `0x180041520`
- `0x18004a83c`
- `0x18004c09c`
- `0x18004c574`
- `0x18004c894`
- `0x18009e300`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180038115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180038115`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003815c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003815c`

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
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C8h] BYREF
  void *v14[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v14[1] = (void *)-2LL;
  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  __0__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v12);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14[0] = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v13);
      goto LABEL_9;
    }
    v10 = v14[0];
    if ( v14[0] )
    {
      *a2 = v14[0];
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
    __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800380d4  mov     rax, rsp
0x1800380d7  push    rbp
0x1800380d8  lea     rbp, [rax-178h]
0x1800380df  sub     rsp, 270h
0x1800380e6  mov     qword ptr [rsp+270h+var_228], 0FFFFFFFFFFFFFFFEh
0x1800380ef  mov     [rax+18h], rbx
0x1800380f3  mov     [rax+20h], rdi
0x1800380f7  mov     rax, cs:__security_cookie
0x1800380fe  xor     rax, rsp
0x180038101  mov     [rbp+170h+var_10], rax
0x180038108  mov     rdi, rdx
0x18003810b  mov     rbx, rcx
0x18003810e  mov     qword ptr [rdx], 0
0x180038115  call    cs:__imp_GetCurrentProcessId
0x18003811b  mov     r9d, eax
0x18003811e  mov     [rsp+270h+var_248], rbx
0x180038123  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18003812b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180038132  mov     edx, 104h; unsigned __int64
0x180038137  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003813c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038141  lea     rcx, [rsp+270h+var_240]
0x180038146  call    ??0?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x18003814b  nop
0x18003814c  mov     r9d, 1F0001h; dwDesiredAccess
0x180038152  xor     r8d, r8d; dwFlags
0x180038155  lea     rdx, [rsp+270h+Name]; lpName
0x18003815a  xor     ecx, ecx; lpMutexAttributes
0x18003815c  call    cs:__imp_CreateMutexExW
0x180038162  mov     rdx, rax
0x180038165  lea     rcx, [rsp+270h+var_240]
0x18003816a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003816f  cmp     [rsp+270h+var_240], 0
0x180038175  jnz     short loc_180038180
0x180038177  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003817c  mov     ebx, eax
0x18003817e  jmp     short loc_1800381EE
0x180038180  lea     rdx, [rsp+270h+var_238]
0x180038185  lea     rcx, [rsp+270h+var_240]
0x18003818a  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003818f  nop
0x180038190  mov     [rsp+270h+var_230], 0
0x180038199  lea     rdx, [rsp+270h+var_230]; void **
0x18003819e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800381a3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800381a8  mov     ebx, eax
0x1800381aa  test    eax, eax
0x1800381ac  jns     short loc_1800381CF
0x1800381ae  mov     edx, 12Eh; void *
0x1800381b3  mov     r9d, eax; char *
0x1800381b6  mov     rcx, [rbp+178h]; this
0x1800381bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800381c2  nop
0x1800381c3  lea     rcx, [rsp+270h+var_238]
0x1800381c8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x1800381cd  jmp     short loc_1800381EE
0x1800381cf  mov     rcx, [rsp+270h+var_230]
0x1800381d4  test    rcx, rcx
0x1800381d7  jz      short loc_18003821E
0x1800381d9  mov     [rdi], rcx
0x1800381dc  mov     eax, [rcx]
0x1800381de  inc     eax
0x1800381e0  mov     [rcx], eax
0x1800381e2  lea     rcx, [rsp+270h+var_238]
0x1800381e7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x1800381ec  xor     ebx, ebx
0x1800381ee  lea     rcx, [rsp+270h+var_240]
0x1800381f3  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x1800381f8  mov     eax, ebx
0x1800381fa  mov     rcx, [rbp+170h+var_10]
0x180038201  xor     rcx, rsp; StackCookie
0x180038204  call    __security_check_cookie
0x180038209  lea     r11, [rsp+270h+var_s0]
0x180038211  mov     rbx, [r11+20h]
0x180038215  mov     rdi, [r11+28h]
0x180038219  mov     rsp, r11
0x18003821c  pop     rbp
0x18003821d  retn
0x18003821e  mov     r8, rdi
0x180038221  lea     rdx, [rsp+270h+var_240]
0x180038226  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003822b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180038230  mov     ebx, eax
0x180038232  test    eax, eax
0x180038234  jns     short loc_1800381E2
0x180038236  mov     edx, 137h
0x18003823b  jmp     loc_1800381B3
```
