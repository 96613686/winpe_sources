# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180049404`
- end: `0x180049563`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004ad40`

## callees

- `0x180003710`
- `0x1800449f0`
- `0x180048db0`
- `0x180048dcc`
- `0x180049404`
- `0x18004ab9c`
- `0x18004ba3c`
- `0x18004ce50`
- `0x18004df50`
- `0x18004eca0`
- `0x18004f050`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004943c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004943c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180049481`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180049481`

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
0x180049404  mov     [rsp-8+arg_10], rbx
0x180049409  mov     [rsp-8+arg_18], rdi
0x18004940e  push    rbp
0x18004940f  lea     rbp, [rsp-170h]
0x180049417  sub     rsp, 270h
0x18004941e  mov     rax, cs:__security_cookie
0x180049425  xor     rax, rsp
0x180049428  mov     [rbp+170h+var_10], rax
0x18004942f  mov     rdi, rdx
0x180049432  mov     qword ptr [rdx], 0
0x180049439  mov     rbx, rcx
0x18004943c  call    cs:__imp_GetCurrentProcessId
0x180049442  mov     [rsp+270h+var_248], rbx
0x180049447  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004944e  mov     r9d, eax
0x180049451  mov     [rsp+270h+var_250], 130h; int
0x180049459  mov     edx, 104h; unsigned __int64
0x18004945e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180049463  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180049468  mov     r9d, 1F0001h; dwDesiredAccess
0x18004946e  mov     [rsp+270h+var_240], 0
0x180049477  xor     r8d, r8d; dwFlags
0x18004947a  lea     rdx, [rsp+270h+Name]; lpName
0x18004947f  xor     ecx, ecx; lpMutexAttributes
0x180049481  call    cs:__imp_CreateMutexExW
0x180049487  mov     rdx, rax
0x18004948a  lea     rcx, [rsp+270h+var_240]
0x18004948f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180049494  cmp     [rsp+270h+var_240], 0
0x18004949a  jnz     short loc_1800494A5
0x18004949c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800494a1  mov     ebx, eax
0x1800494a3  jmp     short loc_180049511
0x1800494a5  lea     rdx, [rsp+270h+var_238]
0x1800494aa  lea     rcx, [rsp+270h+var_240]
0x1800494af  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800494b4  lea     rdx, [rsp+270h+var_230]; void **
0x1800494b9  mov     [rsp+270h+var_230], 0
0x1800494c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800494c7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800494cc  mov     ebx, eax
0x1800494ce  test    eax, eax
0x1800494d0  jns     short loc_1800494F2
0x1800494d2  mov     edx, 12Eh; void *
0x1800494d7  mov     rcx, [rbp+178h]; this
0x1800494de  mov     r9d, eax; char *
0x1800494e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800494e6  lea     rcx, [rsp+270h+var_238]
0x1800494eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800494f0  jmp     short loc_180049511
0x1800494f2  mov     rcx, [rsp+270h+var_230]
0x1800494f7  test    rcx, rcx
0x1800494fa  jz      short loc_180049541
0x1800494fc  mov     [rdi], rcx
0x1800494ff  mov     eax, [rcx]
0x180049501  inc     eax
0x180049503  mov     [rcx], eax
0x180049505  lea     rcx, [rsp+270h+var_238]
0x18004950a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004950f  xor     ebx, ebx
0x180049511  lea     rcx, [rsp+270h+var_240]
0x180049516  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004951b  mov     eax, ebx
0x18004951d  mov     rcx, [rbp+170h+var_10]
0x180049524  xor     rcx, rsp; StackCookie
0x180049527  call    __security_check_cookie
0x18004952c  lea     r11, [rsp+270h+var_s0]
0x180049534  mov     rbx, [r11+20h]
0x180049538  mov     rdi, [r11+28h]
0x18004953c  mov     rsp, r11
0x18004953f  pop     rbp
0x180049540  retn
0x180049541  mov     r8, rdi
0x180049544  lea     rdx, [rsp+270h+var_240]
0x180049549  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004954e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180049553  mov     ebx, eax
0x180049555  test    eax, eax
0x180049557  jns     short loc_180049505
0x180049559  mov     edx, 137h
0x18004955e  jmp     loc_1800494D7
```
