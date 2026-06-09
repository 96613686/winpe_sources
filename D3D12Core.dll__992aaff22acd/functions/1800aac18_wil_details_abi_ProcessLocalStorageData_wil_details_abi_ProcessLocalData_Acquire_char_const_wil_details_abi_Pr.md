# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800aac18`
- end: `0x1800aad77`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c46b8`

## callees

- `0x180013e00`
- `0x180014134`
- `0x180014368`
- `0x1800146e8`
- `0x180016678`
- `0x18006c68c`
- `0x18008e540`
- `0x1800aac18`
- `0x1800aad80`
- `0x1800bb480`
- `0x1800c4d64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800aac95`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800aac95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aac50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aac50`

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
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800aac18  mov     [rsp-8+arg_10], rbx
0x1800aac1d  mov     [rsp-8+arg_18], rdi
0x1800aac22  push    rbp
0x1800aac23  lea     rbp, [rsp-170h]
0x1800aac2b  sub     rsp, 270h
0x1800aac32  mov     rax, cs:__security_cookie
0x1800aac39  xor     rax, rsp
0x1800aac3c  mov     [rbp+170h+var_10], rax
0x1800aac43  mov     rdi, rdx
0x1800aac46  mov     qword ptr [rdx], 0
0x1800aac4d  mov     rbx, rcx
0x1800aac50  call    cs:__imp_GetCurrentProcessId
0x1800aac56  mov     [rsp+270h+var_248], rbx
0x1800aac5b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800aac62  mov     r9d, eax
0x1800aac65  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800aac6d  mov     edx, 104h; unsigned __int64
0x1800aac72  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800aac77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800aac7c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800aac82  mov     [rsp+270h+var_240], 0
0x1800aac8b  xor     r8d, r8d; dwFlags
0x1800aac8e  lea     rdx, [rsp+270h+Name]; lpName
0x1800aac93  xor     ecx, ecx; lpMutexAttributes
0x1800aac95  call    cs:__imp_CreateMutexExW
0x1800aac9b  mov     rdx, rax
0x1800aac9e  lea     rcx, [rsp+270h+var_240]
0x1800aaca3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800aaca8  cmp     [rsp+270h+var_240], 0
0x1800aacae  jnz     short loc_1800AACB9
0x1800aacb0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800aacb5  mov     ebx, eax
0x1800aacb7  jmp     short loc_1800AAD25
0x1800aacb9  lea     rdx, [rsp+270h+var_238]
0x1800aacbe  lea     rcx, [rsp+270h+var_240]
0x1800aacc3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800aacc8  lea     rdx, [rsp+270h+var_230]; void **
0x1800aaccd  mov     [rsp+270h+var_230], 0
0x1800aacd6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800aacdb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800aace0  mov     ebx, eax
0x1800aace2  test    eax, eax
0x1800aace4  jns     short loc_1800AAD06
0x1800aace6  mov     edx, 12Eh; void *
0x1800aaceb  mov     rcx, [rbp+178h]; this
0x1800aacf2  mov     r9d, eax; char *
0x1800aacf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aacfa  lea     rcx, [rsp+270h+var_238]
0x1800aacff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800aad04  jmp     short loc_1800AAD25
0x1800aad06  mov     rcx, [rsp+270h+var_230]
0x1800aad0b  test    rcx, rcx
0x1800aad0e  jz      short loc_1800AAD55
0x1800aad10  mov     [rdi], rcx
0x1800aad13  mov     eax, [rcx]
0x1800aad15  inc     eax
0x1800aad17  mov     [rcx], eax
0x1800aad19  lea     rcx, [rsp+270h+var_238]
0x1800aad1e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800aad23  xor     ebx, ebx
0x1800aad25  lea     rcx, [rsp+270h+var_240]
0x1800aad2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800aad2f  mov     eax, ebx
0x1800aad31  mov     rcx, [rbp+170h+var_10]
0x1800aad38  xor     rcx, rsp; StackCookie
0x1800aad3b  call    __security_check_cookie
0x1800aad40  lea     r11, [rsp+270h+var_s0]
0x1800aad48  mov     rbx, [r11+20h]
0x1800aad4c  mov     rdi, [r11+28h]
0x1800aad50  mov     rsp, r11
0x1800aad53  pop     rbp
0x1800aad54  retn
0x1800aad55  mov     r8, rdi
0x1800aad58  lea     rdx, [rsp+270h+var_240]
0x1800aad5d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800aad62  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800aad67  mov     ebx, eax
0x1800aad69  test    eax, eax
0x1800aad6b  jns     short loc_1800AAD19
0x1800aad6d  mov     edx, 137h
0x1800aad72  jmp     loc_1800AACEB
```
