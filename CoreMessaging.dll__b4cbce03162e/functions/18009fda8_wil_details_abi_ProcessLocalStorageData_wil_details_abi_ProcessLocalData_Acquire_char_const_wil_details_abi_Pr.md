# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18009fda8`
- end: `0x18009ff0e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800a080c`

## callees

- `0x180097b64`
- `0x18009a51c`
- `0x18009a7e8`
- `0x18009d670`
- `0x18009fc80`
- `0x18009fc9c`
- `0x18009fda8`
- `0x1800a15ac`
- `0x1800a1718`
- `0x1800a1b04`
- `0x1800a1bf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18009fe25`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18009fe25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009fde0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009fde0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18009fda8  mov     [rsp-8+arg_10], rbx
0x18009fdad  mov     [rsp-8+arg_18], rdi
0x18009fdb2  push    rbp
0x18009fdb3  lea     rbp, [rsp-170h]
0x18009fdbb  sub     rsp, 270h
0x18009fdc2  mov     rax, cs:__security_cookie
0x18009fdc9  xor     rax, rsp
0x18009fdcc  mov     [rbp+170h+var_10], rax
0x18009fdd3  mov     rdi, rdx
0x18009fdd6  mov     qword ptr [rdx], 0
0x18009fddd  mov     rbx, rcx
0x18009fde0  call    cs:__imp_GetCurrentProcessId
0x18009fde6  mov     [rsp+270h+var_248], rbx
0x18009fdeb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18009fdf2  mov     r9d, eax
0x18009fdf5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18009fdfd  mov     edx, 104h; unsigned __int64
0x18009fe02  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18009fe07  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009fe0c  mov     r9d, 1F0001h; dwDesiredAccess
0x18009fe12  mov     [rsp+270h+var_240], 0
0x18009fe1b  xor     r8d, r8d; dwFlags
0x18009fe1e  lea     rdx, [rsp+270h+Name]; lpName
0x18009fe23  xor     ecx, ecx; lpMutexAttributes
0x18009fe25  call    cs:__imp_CreateMutexExW
0x18009fe2b  mov     rdx, rax
0x18009fe2e  lea     rcx, [rsp+270h+var_240]
0x18009fe33  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18009fe38  cmp     [rsp+270h+var_240], 0
0x18009fe3e  jnz     short loc_18009FE49
0x18009fe40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18009fe45  mov     ebx, eax
0x18009fe47  jmp     short loc_18009FEBC
0x18009fe49  lea     rdx, [rsp+270h+var_238]
0x18009fe4e  lea     rcx, [rsp+270h+var_240]
0x18009fe53  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18009fe58  lea     rdx, [rsp+270h+var_230]; void **
0x18009fe5d  mov     [rsp+270h+var_230], 0
0x18009fe66  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18009fe6b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18009fe70  mov     ebx, eax
0x18009fe72  test    eax, eax
0x18009fe74  jns     short loc_18009FE9D
0x18009fe76  mov     edx, 12Eh; void *
0x18009fe7b  mov     rcx, [rbp+178h]; this
0x18009fe82  lea     r8, aWil; "wil"
0x18009fe89  mov     r9d, eax; char *
0x18009fe8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fe91  lea     rcx, [rsp+270h+var_238]
0x18009fe96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009fe9b  jmp     short loc_18009FEBC
0x18009fe9d  mov     rcx, [rsp+270h+var_230]
0x18009fea2  test    rcx, rcx
0x18009fea5  jz      short loc_18009FEEC
0x18009fea7  mov     [rdi], rcx
0x18009feaa  mov     eax, [rcx]
0x18009feac  inc     eax
0x18009feae  mov     [rcx], eax
0x18009feb0  lea     rcx, [rsp+270h+var_238]
0x18009feb5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009feba  xor     ebx, ebx
0x18009febc  lea     rcx, [rsp+270h+var_240]
0x18009fec1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009fec6  mov     eax, ebx
0x18009fec8  mov     rcx, [rbp+170h+var_10]
0x18009fecf  xor     rcx, rsp; StackCookie
0x18009fed2  call    __security_check_cookie
0x18009fed7  lea     r11, [rsp+270h+var_s0]
0x18009fedf  mov     rbx, [r11+20h]
0x18009fee3  mov     rdi, [r11+28h]
0x18009fee7  mov     rsp, r11
0x18009feea  pop     rbp
0x18009feeb  retn
0x18009feec  mov     r8, rdi
0x18009feef  lea     rdx, [rsp+270h+var_240]
0x18009fef4  lea     rcx, [rsp+270h+Name]
0x18009fef9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18009fefe  mov     ebx, eax
0x18009ff00  test    eax, eax
0x18009ff02  jns     short loc_18009FEB0
0x18009ff04  mov     edx, 137h
0x18009ff09  jmp     loc_18009FE7B
```
