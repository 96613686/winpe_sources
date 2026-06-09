# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140003fd8`
- end: `0x140004137`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140004dc4`

## callees

- `0x140003b30`
- `0x140003b4c`
- `0x140003fd8`
- `0x140004c08`
- `0x140005aa4`
- `0x140006b9c`
- `0x140007100`
- `0x1400074f4`
- `0x140007da4`
- `0x14000808c`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004055`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004055`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004010`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004010`

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
0x140003fd8  mov     [rsp-8+arg_10], rbx
0x140003fdd  mov     [rsp-8+arg_18], rdi
0x140003fe2  push    rbp
0x140003fe3  lea     rbp, [rsp-170h]
0x140003feb  sub     rsp, 270h
0x140003ff2  mov     rax, cs:__security_cookie
0x140003ff9  xor     rax, rsp
0x140003ffc  mov     [rbp+170h+var_10], rax
0x140004003  mov     rdi, rdx
0x140004006  mov     qword ptr [rdx], 0
0x14000400d  mov     rbx, rcx
0x140004010  call    cs:__imp_GetCurrentProcessId
0x140004016  mov     [rsp+270h+var_248], rbx
0x14000401b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004022  mov     r9d, eax
0x140004025  mov     [rsp+270h+var_250], 130h; int
0x14000402d  mov     edx, 104h; unsigned __int64
0x140004032  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004037  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000403c  mov     r9d, 1F0001h; dwDesiredAccess
0x140004042  mov     [rsp+270h+var_240], 0
0x14000404b  xor     r8d, r8d; dwFlags
0x14000404e  lea     rdx, [rsp+270h+Name]; lpName
0x140004053  xor     ecx, ecx; lpMutexAttributes
0x140004055  call    cs:__imp_CreateMutexExW
0x14000405b  mov     rdx, rax
0x14000405e  lea     rcx, [rsp+270h+var_240]
0x140004063  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140004068  cmp     [rsp+270h+var_240], 0
0x14000406e  jnz     short loc_140004079
0x140004070  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004075  mov     ebx, eax
0x140004077  jmp     short loc_1400040E5
0x140004079  lea     rdx, [rsp+270h+var_238]
0x14000407e  lea     rcx, [rsp+270h+var_240]
0x140004083  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140004088  lea     rdx, [rsp+270h+var_230]; void **
0x14000408d  mov     [rsp+270h+var_230], 0
0x140004096  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000409b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1400040a0  mov     ebx, eax
0x1400040a2  test    eax, eax
0x1400040a4  jns     short loc_1400040C6
0x1400040a6  mov     edx, 12Eh; void *
0x1400040ab  mov     rcx, [rbp+178h]; this
0x1400040b2  mov     r9d, eax; char *
0x1400040b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400040ba  lea     rcx, [rsp+270h+var_238]
0x1400040bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400040c4  jmp     short loc_1400040E5
0x1400040c6  mov     rcx, [rsp+270h+var_230]
0x1400040cb  test    rcx, rcx
0x1400040ce  jz      short loc_140004115
0x1400040d0  mov     [rdi], rcx
0x1400040d3  mov     eax, [rcx]
0x1400040d5  inc     eax
0x1400040d7  mov     [rcx], eax
0x1400040d9  lea     rcx, [rsp+270h+var_238]
0x1400040de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400040e3  xor     ebx, ebx
0x1400040e5  lea     rcx, [rsp+270h+var_240]
0x1400040ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400040ef  mov     eax, ebx
0x1400040f1  mov     rcx, [rbp+170h+var_10]
0x1400040f8  xor     rcx, rsp; StackCookie
0x1400040fb  call    __security_check_cookie
0x140004100  lea     r11, [rsp+270h+var_s0]
0x140004108  mov     rbx, [r11+20h]
0x14000410c  mov     rdi, [r11+28h]
0x140004110  mov     rsp, r11
0x140004113  pop     rbp
0x140004114  retn
0x140004115  mov     r8, rdi
0x140004118  lea     rdx, [rsp+270h+var_240]
0x14000411d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004122  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140004127  mov     ebx, eax
0x140004129  test    eax, eax
0x14000412b  jns     short loc_1400040D9
0x14000412d  mov     edx, 137h
0x140004132  jmp     loc_1400040AB
```
