# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180026858`
- end: `0x1800269be`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800270b8`

## callees

- `0x180008584`
- `0x18000b770`
- `0x18000b8d8`
- `0x18000df0c`
- `0x18000df28`
- `0x18000e868`
- `0x18000f878`
- `0x18000fc74`
- `0x18000fd20`
- `0x180026858`
- `0x180052950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800268d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800268d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026890`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026890`

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
0x180026858  mov     [rsp-8+arg_10], rbx
0x18002685d  mov     [rsp-8+arg_18], rdi
0x180026862  push    rbp
0x180026863  lea     rbp, [rsp-170h]
0x18002686b  sub     rsp, 270h
0x180026872  mov     rax, cs:__security_cookie
0x180026879  xor     rax, rsp
0x18002687c  mov     [rbp+170h+var_10], rax
0x180026883  mov     rdi, rdx
0x180026886  mov     qword ptr [rdx], 0
0x18002688d  mov     rbx, rcx
0x180026890  call    cs:__imp_GetCurrentProcessId
0x180026896  mov     [rsp+270h+var_248], rbx
0x18002689b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800268a2  mov     r9d, eax
0x1800268a5  mov     [rsp+270h+var_250], 130h; int
0x1800268ad  mov     edx, 104h; unsigned __int64
0x1800268b2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800268b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800268bc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800268c2  mov     [rsp+270h+var_240], 0
0x1800268cb  xor     r8d, r8d; dwFlags
0x1800268ce  lea     rdx, [rsp+270h+Name]; lpName
0x1800268d3  xor     ecx, ecx; lpMutexAttributes
0x1800268d5  call    cs:__imp_CreateMutexExW
0x1800268db  mov     rdx, rax
0x1800268de  lea     rcx, [rsp+270h+var_240]
0x1800268e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800268e8  cmp     [rsp+270h+var_240], 0
0x1800268ee  jnz     short loc_1800268F9
0x1800268f0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800268f5  mov     ebx, eax
0x1800268f7  jmp     short loc_18002696C
0x1800268f9  lea     rdx, [rsp+270h+var_238]
0x1800268fe  lea     rcx, [rsp+270h+var_240]
0x180026903  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180026908  lea     rdx, [rsp+270h+var_230]; void **
0x18002690d  mov     [rsp+270h+var_230], 0
0x180026916  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002691b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180026920  mov     ebx, eax
0x180026922  test    eax, eax
0x180026924  jns     short loc_18002694D
0x180026926  mov     edx, 12Eh; void *
0x18002692b  mov     rcx, [rbp+178h]; this
0x180026932  lea     r8, aWil; "wil"
0x180026939  mov     r9d, eax; char *
0x18002693c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026941  lea     rcx, [rsp+270h+var_238]
0x180026946  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002694b  jmp     short loc_18002696C
0x18002694d  mov     rcx, [rsp+270h+var_230]
0x180026952  test    rcx, rcx
0x180026955  jz      short loc_18002699C
0x180026957  mov     [rdi], rcx
0x18002695a  mov     eax, [rcx]
0x18002695c  inc     eax
0x18002695e  mov     [rcx], eax
0x180026960  lea     rcx, [rsp+270h+var_238]
0x180026965  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002696a  xor     ebx, ebx
0x18002696c  lea     rcx, [rsp+270h+var_240]
0x180026971  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026976  mov     eax, ebx
0x180026978  mov     rcx, [rbp+170h+var_10]
0x18002697f  xor     rcx, rsp; StackCookie
0x180026982  call    __security_check_cookie
0x180026987  lea     r11, [rsp+270h+var_s0]
0x18002698f  mov     rbx, [r11+20h]
0x180026993  mov     rdi, [r11+28h]
0x180026997  mov     rsp, r11
0x18002699a  pop     rbp
0x18002699b  retn
0x18002699c  mov     r8, rdi
0x18002699f  lea     rdx, [rsp+270h+var_240]
0x1800269a4  lea     rcx, [rsp+270h+Name]
0x1800269a9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800269ae  mov     ebx, eax
0x1800269b0  test    eax, eax
0x1800269b2  jns     short loc_180026960
0x1800269b4  mov     edx, 137h
0x1800269b9  jmp     loc_18002692B
```
