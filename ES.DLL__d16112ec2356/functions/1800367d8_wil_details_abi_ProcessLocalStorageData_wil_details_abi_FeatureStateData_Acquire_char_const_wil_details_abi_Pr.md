# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800367d8`
- end: `0x180036937`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180036b20`

## callees

- `0x180006194`
- `0x18002cdc0`
- `0x1800364d8`
- `0x1800364f4`
- `0x1800367d8`
- `0x180037d6c`
- `0x180038988`
- `0x180039118`
- `0x1800398a4`
- `0x1800399f0`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180036855`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180036855`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036810`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036810`

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
0x1800367d8  mov     [rsp-8+arg_10], rbx
0x1800367dd  mov     [rsp-8+arg_18], rdi
0x1800367e2  push    rbp
0x1800367e3  lea     rbp, [rsp-170h]
0x1800367eb  sub     rsp, 270h
0x1800367f2  mov     rax, cs:__security_cookie
0x1800367f9  xor     rax, rsp
0x1800367fc  mov     [rbp+170h+var_10], rax
0x180036803  mov     rdi, rdx
0x180036806  mov     qword ptr [rdx], 0
0x18003680d  mov     rbx, rcx
0x180036810  call    cs:__imp_GetCurrentProcessId
0x180036816  mov     [rsp+270h+var_248], rbx
0x18003681b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180036822  mov     r9d, eax
0x180036825  mov     [rsp+270h+var_250], 130h; int
0x18003682d  mov     edx, 104h; unsigned __int64
0x180036832  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180036837  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003683c  mov     r9d, 1F0001h; dwDesiredAccess
0x180036842  mov     [rsp+270h+var_240], 0
0x18003684b  xor     r8d, r8d; dwFlags
0x18003684e  lea     rdx, [rsp+270h+Name]; lpName
0x180036853  xor     ecx, ecx; lpMutexAttributes
0x180036855  call    cs:__imp_CreateMutexExW
0x18003685b  mov     rdx, rax
0x18003685e  lea     rcx, [rsp+270h+var_240]
0x180036863  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180036868  cmp     [rsp+270h+var_240], 0
0x18003686e  jnz     short loc_180036879
0x180036870  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180036875  mov     ebx, eax
0x180036877  jmp     short loc_1800368E5
0x180036879  lea     rdx, [rsp+270h+var_238]
0x18003687e  lea     rcx, [rsp+270h+var_240]
0x180036883  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180036888  lea     rdx, [rsp+270h+var_230]; void **
0x18003688d  mov     [rsp+270h+var_230], 0
0x180036896  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003689b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800368a0  mov     ebx, eax
0x1800368a2  test    eax, eax
0x1800368a4  jns     short loc_1800368C6
0x1800368a6  mov     edx, 12Eh; void *
0x1800368ab  mov     rcx, [rbp+178h]; this
0x1800368b2  mov     r9d, eax; char *
0x1800368b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800368ba  lea     rcx, [rsp+270h+var_238]
0x1800368bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800368c4  jmp     short loc_1800368E5
0x1800368c6  mov     rcx, [rsp+270h+var_230]
0x1800368cb  test    rcx, rcx
0x1800368ce  jz      short loc_180036915
0x1800368d0  mov     [rdi], rcx
0x1800368d3  mov     eax, [rcx]
0x1800368d5  inc     eax
0x1800368d7  mov     [rcx], eax
0x1800368d9  lea     rcx, [rsp+270h+var_238]
0x1800368de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800368e3  xor     ebx, ebx
0x1800368e5  lea     rcx, [rsp+270h+var_240]
0x1800368ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800368ef  mov     eax, ebx
0x1800368f1  mov     rcx, [rbp+170h+var_10]
0x1800368f8  xor     rcx, rsp; StackCookie
0x1800368fb  call    __security_check_cookie
0x180036900  lea     r11, [rsp+270h+var_s0]
0x180036908  mov     rbx, [r11+20h]
0x18003690c  mov     rdi, [r11+28h]
0x180036910  mov     rsp, r11
0x180036913  pop     rbp
0x180036914  retn
0x180036915  mov     r8, rdi
0x180036918  lea     rdx, [rsp+270h+var_240]
0x18003691d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180036922  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180036927  mov     ebx, eax
0x180036929  test    eax, eax
0x18003692b  jns     short loc_1800368D9
0x18003692d  mov     edx, 137h
0x180036932  jmp     loc_1800368AB
```
