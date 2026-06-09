# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007640`
- end: `0x18000779f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b4e4`

## callees

- `0x180007224`
- `0x180007640`
- `0x180007ab4`
- `0x180007c90`
- `0x180007cb8`
- `0x180007d0c`
- `0x180009990`
- `0x18000ae0c`
- `0x18000ca58`
- `0x18000cc34`
- `0x18000d300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800076bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800076bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007678`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007678`

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
0x180007640  mov     [rsp-8+arg_10], rbx
0x180007645  mov     [rsp-8+arg_18], rdi
0x18000764a  push    rbp
0x18000764b  lea     rbp, [rsp-170h]
0x180007653  sub     rsp, 270h
0x18000765a  mov     rax, cs:__security_cookie
0x180007661  xor     rax, rsp
0x180007664  mov     [rbp+170h+var_10], rax
0x18000766b  mov     rdi, rdx
0x18000766e  mov     qword ptr [rdx], 0
0x180007675  mov     rbx, rcx
0x180007678  call    cs:__imp_GetCurrentProcessId
0x18000767e  mov     [rsp+270h+var_248], rbx
0x180007683  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000768a  mov     r9d, eax
0x18000768d  mov     [rsp+270h+var_250], 130h; int
0x180007695  mov     edx, 104h; unsigned __int64
0x18000769a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000769f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800076a4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800076aa  mov     [rsp+270h+var_240], 0
0x1800076b3  xor     r8d, r8d; dwFlags
0x1800076b6  lea     rdx, [rsp+270h+Name]; lpName
0x1800076bb  xor     ecx, ecx; lpMutexAttributes
0x1800076bd  call    cs:__imp_CreateMutexExW
0x1800076c3  mov     rdx, rax
0x1800076c6  lea     rcx, [rsp+270h+var_240]
0x1800076cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800076d0  cmp     [rsp+270h+var_240], 0
0x1800076d6  jnz     short loc_1800076E1
0x1800076d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800076dd  mov     ebx, eax
0x1800076df  jmp     short loc_18000774D
0x1800076e1  lea     rdx, [rsp+270h+var_238]
0x1800076e6  lea     rcx, [rsp+270h+var_240]
0x1800076eb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800076f0  lea     rdx, [rsp+270h+var_230]; void **
0x1800076f5  mov     [rsp+270h+var_230], 0
0x1800076fe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007703  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180007708  mov     ebx, eax
0x18000770a  test    eax, eax
0x18000770c  jns     short loc_18000772E
0x18000770e  mov     edx, 12Eh; void *
0x180007713  mov     rcx, [rbp+178h]; this
0x18000771a  mov     r9d, eax; char *
0x18000771d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007722  lea     rcx, [rsp+270h+var_238]
0x180007727  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000772c  jmp     short loc_18000774D
0x18000772e  mov     rcx, [rsp+270h+var_230]
0x180007733  test    rcx, rcx
0x180007736  jz      short loc_18000777D
0x180007738  mov     [rdi], rcx
0x18000773b  mov     eax, [rcx]
0x18000773d  inc     eax
0x18000773f  mov     [rcx], eax
0x180007741  lea     rcx, [rsp+270h+var_238]
0x180007746  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000774b  xor     ebx, ebx
0x18000774d  lea     rcx, [rsp+270h+var_240]
0x180007752  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007757  mov     eax, ebx
0x180007759  mov     rcx, [rbp+170h+var_10]
0x180007760  xor     rcx, rsp; StackCookie
0x180007763  call    __security_check_cookie
0x180007768  lea     r11, [rsp+270h+var_s0]
0x180007770  mov     rbx, [r11+20h]
0x180007774  mov     rdi, [r11+28h]
0x180007778  mov     rsp, r11
0x18000777b  pop     rbp
0x18000777c  retn
0x18000777d  mov     r8, rdi
0x180007780  lea     rdx, [rsp+270h+var_240]
0x180007785  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000778a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000778f  mov     ebx, eax
0x180007791  test    eax, eax
0x180007793  jns     short loc_180007741
0x180007795  mov     edx, 137h
0x18000779a  jmp     loc_180007713
```
