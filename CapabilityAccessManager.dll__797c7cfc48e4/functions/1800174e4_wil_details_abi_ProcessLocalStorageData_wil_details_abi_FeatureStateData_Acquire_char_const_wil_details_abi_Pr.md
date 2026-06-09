# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800174e4`
- end: `0x18001764a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180018800`

## callees

- `0x1800094c0`
- `0x180016dcc`
- `0x180016de8`
- `0x1800174e4`
- `0x180018598`
- `0x18001963c`
- `0x18001ab9c`
- `0x18001b400`
- `0x18001b9ec`
- `0x18001c434`
- `0x18001c770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180017561`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180017561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001751c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001751c`

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
0x1800174e4  mov     [rsp-8+arg_10], rbx
0x1800174e9  mov     [rsp-8+arg_18], rdi
0x1800174ee  push    rbp
0x1800174ef  lea     rbp, [rsp-170h]
0x1800174f7  sub     rsp, 270h
0x1800174fe  mov     rax, cs:__security_cookie
0x180017505  xor     rax, rsp
0x180017508  mov     [rbp+170h+var_10], rax
0x18001750f  mov     rdi, rdx
0x180017512  mov     qword ptr [rdx], 0
0x180017519  mov     rbx, rcx
0x18001751c  call    cs:__imp_GetCurrentProcessId
0x180017522  mov     [rsp+270h+var_248], rbx
0x180017527  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001752e  mov     r9d, eax
0x180017531  mov     [rsp+270h+var_250], 130h; int
0x180017539  mov     edx, 104h; unsigned __int64
0x18001753e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017543  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017548  mov     r9d, 1F0001h; dwDesiredAccess
0x18001754e  mov     [rsp+270h+var_240], 0
0x180017557  xor     r8d, r8d; dwFlags
0x18001755a  lea     rdx, [rsp+270h+Name]; lpName
0x18001755f  xor     ecx, ecx; lpMutexAttributes
0x180017561  call    cs:__imp_CreateMutexExW
0x180017567  mov     rdx, rax
0x18001756a  lea     rcx, [rsp+270h+var_240]
0x18001756f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180017574  cmp     [rsp+270h+var_240], 0
0x18001757a  jnz     short loc_180017585
0x18001757c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017581  mov     ebx, eax
0x180017583  jmp     short loc_1800175F8
0x180017585  lea     rdx, [rsp+270h+var_238]
0x18001758a  lea     rcx, [rsp+270h+var_240]
0x18001758f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180017594  lea     rdx, [rsp+270h+var_230]; void **
0x180017599  mov     [rsp+270h+var_230], 0
0x1800175a2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800175a7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800175ac  mov     ebx, eax
0x1800175ae  test    eax, eax
0x1800175b0  jns     short loc_1800175D9
0x1800175b2  mov     edx, 12Eh; void *
0x1800175b7  mov     rcx, [rbp+178h]; this
0x1800175be  lea     r8, aWil; "wil"
0x1800175c5  mov     r9d, eax; char *
0x1800175c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800175cd  lea     rcx, [rsp+270h+var_238]
0x1800175d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800175d7  jmp     short loc_1800175F8
0x1800175d9  mov     rcx, [rsp+270h+var_230]
0x1800175de  test    rcx, rcx
0x1800175e1  jz      short loc_180017628
0x1800175e3  mov     [rdi], rcx
0x1800175e6  mov     eax, [rcx]
0x1800175e8  inc     eax
0x1800175ea  mov     [rcx], eax
0x1800175ec  lea     rcx, [rsp+270h+var_238]
0x1800175f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800175f6  xor     ebx, ebx
0x1800175f8  lea     rcx, [rsp+270h+var_240]
0x1800175fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017602  mov     eax, ebx
0x180017604  mov     rcx, [rbp+170h+var_10]
0x18001760b  xor     rcx, rsp; StackCookie
0x18001760e  call    __security_check_cookie
0x180017613  lea     r11, [rsp+270h+var_s0]
0x18001761b  mov     rbx, [r11+20h]
0x18001761f  mov     rdi, [r11+28h]
0x180017623  mov     rsp, r11
0x180017626  pop     rbp
0x180017627  retn
0x180017628  mov     r8, rdi
0x18001762b  lea     rdx, [rsp+270h+var_240]
0x180017630  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017635  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001763a  mov     ebx, eax
0x18001763c  test    eax, eax
0x18001763e  jns     short loc_1800175EC
0x180017640  mov     edx, 137h
0x180017645  jmp     loc_1800175B7
```
