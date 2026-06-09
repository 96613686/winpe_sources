# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180011624`
- end: `0x18001178a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180011f6c`

## callees

- `0x180002ce0`
- `0x180007034`
- `0x180007050`
- `0x180009c78`
- `0x18000c164`
- `0x18000d1c0`
- `0x18000d5b8`
- `0x18000deec`
- `0x18000e01c`
- `0x180011624`
- `0x1800122e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800116a1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800116a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001165c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001165c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180011624  mov     [rsp-8+arg_10], rbx
0x180011629  mov     [rsp-8+arg_18], rdi
0x18001162e  push    rbp
0x18001162f  lea     rbp, [rsp-170h]
0x180011637  sub     rsp, 270h
0x18001163e  mov     rax, cs:__security_cookie
0x180011645  xor     rax, rsp
0x180011648  mov     [rbp+170h+var_10], rax
0x18001164f  mov     rdi, rdx
0x180011652  mov     qword ptr [rdx], 0
0x180011659  mov     rbx, rcx
0x18001165c  call    cs:__imp_GetCurrentProcessId
0x180011662  mov     [rsp+270h+var_248], rbx
0x180011667  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001166e  mov     r9d, eax
0x180011671  mov     [rsp+270h+var_250], 130h; int
0x180011679  mov     edx, 104h; unsigned __int64
0x18001167e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011683  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011688  mov     r9d, 1F0001h; dwDesiredAccess
0x18001168e  mov     [rsp+270h+var_240], 0
0x180011697  xor     r8d, r8d; dwFlags
0x18001169a  lea     rdx, [rsp+270h+Name]; lpName
0x18001169f  xor     ecx, ecx; lpMutexAttributes
0x1800116a1  call    cs:__imp_CreateMutexExW
0x1800116a7  mov     rdx, rax
0x1800116aa  lea     rcx, [rsp+270h+var_240]
0x1800116af  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800116b4  cmp     [rsp+270h+var_240], 0
0x1800116ba  jnz     short loc_1800116C5
0x1800116bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800116c1  mov     ebx, eax
0x1800116c3  jmp     short loc_180011738
0x1800116c5  lea     rdx, [rsp+270h+var_238]
0x1800116ca  lea     rcx, [rsp+270h+var_240]
0x1800116cf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800116d4  lea     rdx, [rsp+270h+var_230]; void **
0x1800116d9  mov     [rsp+270h+var_230], 0
0x1800116e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800116e7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800116ec  mov     ebx, eax
0x1800116ee  test    eax, eax
0x1800116f0  jns     short loc_180011719
0x1800116f2  mov     edx, 12Eh; void *
0x1800116f7  mov     rcx, [rbp+178h]; this
0x1800116fe  lea     r8, aWil; "wil"
0x180011705  mov     r9d, eax; char *
0x180011708  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001170d  lea     rcx, [rsp+270h+var_238]
0x180011712  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011717  jmp     short loc_180011738
0x180011719  mov     rcx, [rsp+270h+var_230]
0x18001171e  test    rcx, rcx
0x180011721  jz      short loc_180011768
0x180011723  mov     [rdi], rcx
0x180011726  mov     eax, [rcx]
0x180011728  inc     eax
0x18001172a  mov     [rcx], eax
0x18001172c  lea     rcx, [rsp+270h+var_238]
0x180011731  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011736  xor     ebx, ebx
0x180011738  lea     rcx, [rsp+270h+var_240]
0x18001173d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011742  mov     eax, ebx
0x180011744  mov     rcx, [rbp+170h+var_10]
0x18001174b  xor     rcx, rsp; StackCookie
0x18001174e  call    __security_check_cookie
0x180011753  lea     r11, [rsp+270h+var_s0]
0x18001175b  mov     rbx, [r11+20h]
0x18001175f  mov     rdi, [r11+28h]
0x180011763  mov     rsp, r11
0x180011766  pop     rbp
0x180011767  retn
0x180011768  mov     r8, rdi
0x18001176b  lea     rdx, [rsp+270h+var_240]
0x180011770  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011775  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001177a  mov     ebx, eax
0x18001177c  test    eax, eax
0x18001177e  jns     short loc_18001172C
0x180011780  mov     edx, 137h
0x180011785  jmp     loc_1800116F7
```
