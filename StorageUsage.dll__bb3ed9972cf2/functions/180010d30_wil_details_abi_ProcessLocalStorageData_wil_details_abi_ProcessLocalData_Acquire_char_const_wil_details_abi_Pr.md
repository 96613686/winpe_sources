# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180010d30`
- end: `0x180010e99`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `361`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012c78`

## callees

- `0x1800050f0`
- `0x180010484`
- `0x1800104a0`
- `0x180010d30`
- `0x180011ea8`
- `0x180013f80`
- `0x1800152d4`
- `0x180015bac`
- `0x180015f0c`
- `0x180016830`
- `0x1800169a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010dad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010dad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010d68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010d68`

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
0x180010d30  mov     [rsp-8+arg_10], rbx
0x180010d35  mov     [rsp-8+arg_18], rdi
0x180010d3a  push    rbp
0x180010d3b  lea     rbp, [rsp-170h]
0x180010d43  sub     rsp, 270h
0x180010d4a  mov     rax, cs:__security_cookie
0x180010d51  xor     rax, rsp
0x180010d54  mov     [rbp+170h+var_10], rax
0x180010d5b  mov     rdi, rdx
0x180010d5e  mov     rbx, rcx
0x180010d61  mov     qword ptr [rdx], 0
0x180010d68  call    cs:__imp_GetCurrentProcessId
0x180010d6e  mov     r9d, eax
0x180010d71  mov     [rsp+270h+var_248], rbx
0x180010d76  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180010d7e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010d85  mov     edx, 104h; unsigned __int64
0x180010d8a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010d8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010d94  mov     [rsp+270h+var_240], 0
0x180010d9d  mov     r9d, 1F0001h; dwDesiredAccess
0x180010da3  xor     r8d, r8d; dwFlags
0x180010da6  lea     rdx, [rsp+270h+Name]; lpName
0x180010dab  xor     ecx, ecx; lpMutexAttributes
0x180010dad  call    cs:__imp_CreateMutexExW
0x180010db3  mov     rdx, rax
0x180010db6  lea     rcx, [rsp+270h+var_240]
0x180010dbb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180010dc0  cmp     [rsp+270h+var_240], 0
0x180010dc6  jnz     short loc_180010DD1
0x180010dc8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010dcd  mov     ebx, eax
0x180010dcf  jmp     short loc_180010E46
0x180010dd1  lea     rdx, [rsp+270h+var_238]
0x180010dd6  lea     rcx, [rsp+270h+var_240]
0x180010ddb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180010de0  nop
0x180010de1  mov     [rsp+270h+var_230], 0
0x180010dea  lea     rdx, [rsp+270h+var_230]; void **
0x180010def  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010df4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180010df9  mov     ebx, eax
0x180010dfb  test    eax, eax
0x180010dfd  jns     short loc_180010E27
0x180010dff  mov     edx, 12Eh; void *
0x180010e04  lea     r8, aWil; "wil"
0x180010e0b  mov     r9d, eax; char *
0x180010e0e  mov     rcx, [rbp+178h]; this
0x180010e15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010e1a  nop
0x180010e1b  lea     rcx, [rsp+270h+var_238]
0x180010e20  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010e25  jmp     short loc_180010E46
0x180010e27  mov     rcx, [rsp+270h+var_230]
0x180010e2c  test    rcx, rcx
0x180010e2f  jz      short loc_180010E76
0x180010e31  mov     [rdi], rcx
0x180010e34  mov     eax, [rcx]
0x180010e36  inc     eax
0x180010e38  mov     [rcx], eax
0x180010e3a  lea     rcx, [rsp+270h+var_238]
0x180010e3f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010e44  xor     ebx, ebx
0x180010e46  lea     rcx, [rsp+270h+var_240]
0x180010e4b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010e50  mov     eax, ebx
0x180010e52  mov     rcx, [rbp+170h+var_10]
0x180010e59  xor     rcx, rsp; StackCookie
0x180010e5c  call    __security_check_cookie
0x180010e61  lea     r11, [rsp+270h+var_s0]
0x180010e69  mov     rbx, [r11+20h]
0x180010e6d  mov     rdi, [r11+28h]
0x180010e71  mov     rsp, r11
0x180010e74  pop     rbp
0x180010e75  retn
0x180010e76  mov     r8, rdi
0x180010e79  lea     rdx, [rsp+270h+var_240]
0x180010e7e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010e83  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180010e88  mov     ebx, eax
0x180010e8a  test    eax, eax
0x180010e8c  jns     short loc_180010E3A
0x180010e8e  mov     edx, 137h
0x180010e93  jmp     loc_180010E04
```
