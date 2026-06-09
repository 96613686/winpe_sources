# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180023db0`
- end: `0x180023f15`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024a28`

## callees

- `0x1800089f0`
- `0x180015ab4`
- `0x180015c10`
- `0x180015d84`
- `0x180016a40`
- `0x18001773c`
- `0x180023a64`
- `0x180023a84`
- `0x180023db0`
- `0x1800265f0`
- `0x180026da4`
- `0x180026f98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023e2c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023e2c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId_0; // eax
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
  CurrentProcessId_0 = GetCurrentProcessId_0();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId_0);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180023db0  mov     [rsp-8+arg_10], rbx
0x180023db5  mov     [rsp-8+arg_18], rdi
0x180023dba  push    rbp
0x180023dbb  lea     rbp, [rsp-170h]
0x180023dc3  sub     rsp, 270h
0x180023dca  mov     rax, cs:__security_cookie
0x180023dd1  xor     rax, rsp
0x180023dd4  mov     [rbp+170h+var_10], rax
0x180023ddb  mov     rdi, rdx
0x180023dde  mov     qword ptr [rdx], 0
0x180023de5  mov     rbx, rcx
0x180023de8  call    GetCurrentProcessId_0
0x180023ded  mov     r9d, eax
0x180023df0  mov     [rsp+270h+var_248], rbx
0x180023df5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180023dfc  mov     [rsp+270h+var_250], 130h; int
0x180023e04  mov     edx, 104h; unsigned __int64
0x180023e09  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023e0e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023e13  mov     r9d, 1F0001h; dwDesiredAccess
0x180023e19  mov     [rsp+270h+var_240], 0
0x180023e22  xor     r8d, r8d; dwFlags
0x180023e25  lea     rdx, [rsp+270h+Name]; lpName
0x180023e2a  xor     ecx, ecx; lpMutexAttributes
0x180023e2c  call    cs:__imp_CreateMutexExW
0x180023e33  nop     dword ptr [rax+rax+00h]
0x180023e38  mov     rdx, rax
0x180023e3b  lea     rcx, [rsp+270h+var_240]
0x180023e40  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180023e45  cmp     [rsp+270h+var_240], 0
0x180023e4b  jnz     short loc_180023E56
0x180023e4d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023e52  mov     ebx, eax
0x180023e54  jmp     short loc_180023EC2
0x180023e56  lea     rdx, [rsp+270h+var_238]
0x180023e5b  lea     rcx, [rsp+270h+var_240]
0x180023e60  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180023e65  lea     rdx, [rsp+270h+var_230]; void **
0x180023e6a  mov     [rsp+270h+var_230], 0
0x180023e73  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023e78  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180023e7d  mov     ebx, eax
0x180023e7f  test    eax, eax
0x180023e81  jns     short loc_180023EA3
0x180023e83  mov     edx, 12Eh; void *
0x180023e88  mov     rcx, [rbp+178h]; this
0x180023e8f  mov     r9d, eax; char *
0x180023e92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e97  lea     rcx, [rsp+270h+var_238]
0x180023e9c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023ea1  jmp     short loc_180023EC2
0x180023ea3  mov     rcx, [rsp+270h+var_230]
0x180023ea8  test    rcx, rcx
0x180023eab  jz      short loc_180023EF3
0x180023ead  mov     [rdi], rcx
0x180023eb0  mov     eax, [rcx]
0x180023eb2  inc     eax
0x180023eb4  mov     [rcx], eax
0x180023eb6  lea     rcx, [rsp+270h+var_238]
0x180023ebb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023ec0  xor     ebx, ebx
0x180023ec2  lea     rcx, [rsp+270h+var_240]
0x180023ec7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023ecc  mov     eax, ebx
0x180023ece  mov     rcx, [rbp+170h+var_10]
0x180023ed5  xor     rcx, rsp; StackCookie
0x180023ed8  call    __security_check_cookie
0x180023edd  lea     r11, [rsp+270h+var_s0]
0x180023ee5  mov     rbx, [r11+20h]
0x180023ee9  mov     rdi, [r11+28h]
0x180023eed  mov     rsp, r11
0x180023ef0  pop     rbp
0x180023ef1  retn
0x180023ef3  mov     r8, rdi
0x180023ef6  lea     rdx, [rsp+270h+var_240]
0x180023efb  lea     rcx, [rsp+270h+Name]
0x180023f00  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180023f05  mov     ebx, eax
0x180023f07  test    eax, eax
0x180023f09  jns     short loc_180023EB6
0x180023f0b  mov     edx, 137h
0x180023f10  jmp     loc_180023E88
```
