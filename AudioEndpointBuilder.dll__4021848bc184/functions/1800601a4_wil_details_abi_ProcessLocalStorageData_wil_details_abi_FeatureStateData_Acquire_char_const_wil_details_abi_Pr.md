# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800601a4`
- end: `0x18006030a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800605ec`

## callees

- `0x180010da8`
- `0x180010dd0`
- `0x180026ec8`
- `0x1800318e0`
- `0x180033828`
- `0x180036bdc`
- `0x180036d30`
- `0x180037154`
- `0x18003e920`
- `0x1800601a4`
- `0x1800609bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180060221`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180060221`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800601dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800601dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x1800601a4  mov     [rsp-8+arg_10], rbx
0x1800601a9  mov     [rsp-8+arg_18], rdi
0x1800601ae  push    rbp
0x1800601af  lea     rbp, [rsp-170h]
0x1800601b7  sub     rsp, 270h
0x1800601be  mov     rax, cs:__security_cookie
0x1800601c5  xor     rax, rsp
0x1800601c8  mov     [rbp+170h+var_10], rax
0x1800601cf  mov     rdi, rdx
0x1800601d2  mov     qword ptr [rdx], 0
0x1800601d9  mov     rbx, rcx
0x1800601dc  call    cs:__imp_GetCurrentProcessId
0x1800601e2  mov     [rsp+270h+var_248], rbx
0x1800601e7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800601ee  mov     r9d, eax
0x1800601f1  mov     [rsp+270h+var_250], 130h; int
0x1800601f9  mov     edx, 104h; unsigned __int64
0x1800601fe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180060203  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180060208  mov     r9d, 1F0001h; dwDesiredAccess
0x18006020e  mov     [rsp+270h+var_240], 0
0x180060217  xor     r8d, r8d; dwFlags
0x18006021a  lea     rdx, [rsp+270h+Name]; lpName
0x18006021f  xor     ecx, ecx; lpMutexAttributes
0x180060221  call    cs:__imp_CreateMutexExW
0x180060227  mov     rdx, rax
0x18006022a  lea     rcx, [rsp+270h+var_240]
0x18006022f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180060234  cmp     [rsp+270h+var_240], 0
0x18006023a  jnz     short loc_180060245
0x18006023c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180060241  mov     ebx, eax
0x180060243  jmp     short loc_1800602B8
0x180060245  lea     rdx, [rsp+270h+var_238]
0x18006024a  lea     rcx, [rsp+270h+var_240]
0x18006024f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180060254  lea     rdx, [rsp+270h+var_230]; void **
0x180060259  mov     [rsp+270h+var_230], 0
0x180060262  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180060267  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18006026c  mov     ebx, eax
0x18006026e  test    eax, eax
0x180060270  jns     short loc_180060299
0x180060272  mov     edx, 12Eh; void *
0x180060277  mov     rcx, [rbp+178h]; this
0x18006027e  lea     r8, aWil; "wil"
0x180060285  mov     r9d, eax; char *
0x180060288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006028d  lea     rcx, [rsp+270h+var_238]
0x180060292  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180060297  jmp     short loc_1800602B8
0x180060299  mov     rcx, [rsp+270h+var_230]
0x18006029e  test    rcx, rcx
0x1800602a1  jz      short loc_1800602E8
0x1800602a3  mov     [rdi], rcx
0x1800602a6  mov     eax, [rcx]
0x1800602a8  inc     eax
0x1800602aa  mov     [rcx], eax
0x1800602ac  lea     rcx, [rsp+270h+var_238]
0x1800602b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800602b6  xor     ebx, ebx
0x1800602b8  lea     rcx, [rsp+270h+var_240]
0x1800602bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800602c2  mov     eax, ebx
0x1800602c4  mov     rcx, [rbp+170h+var_10]
0x1800602cb  xor     rcx, rsp; StackCookie
0x1800602ce  call    __security_check_cookie
0x1800602d3  lea     r11, [rsp+270h+var_s0]
0x1800602db  mov     rbx, [r11+20h]
0x1800602df  mov     rdi, [r11+28h]
0x1800602e3  mov     rsp, r11
0x1800602e6  pop     rbp
0x1800602e7  retn
0x1800602e8  mov     r8, rdi
0x1800602eb  lea     rdx, [rsp+270h+var_240]
0x1800602f0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800602f5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800602fa  mov     ebx, eax
0x1800602fc  test    eax, eax
0x1800602fe  jns     short loc_1800602AC
0x180060300  mov     edx, 137h
0x180060305  jmp     loc_180060277
```
