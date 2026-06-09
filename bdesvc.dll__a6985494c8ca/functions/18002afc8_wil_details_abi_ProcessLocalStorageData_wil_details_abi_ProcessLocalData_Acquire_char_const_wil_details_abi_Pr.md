# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002afc8`
- end: `0x18002b13b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180036978`

## callees

- `0x18001b7f0`
- `0x18002afc8`
- `0x18002b144`
- `0x18002b1c8`
- `0x18002ba04`
- `0x18002ba24`
- `0x18002ba58`
- `0x180030ba0`
- `0x180030fac`
- `0x180034070`
- `0x180036b9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002b04b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002b04b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b000`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b000`

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
  HANDLE v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
      &v12);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x18002afc8  mov     [rsp-8+arg_10], rbx
0x18002afcd  mov     [rsp-8+arg_18], rdi
0x18002afd2  push    rbp
0x18002afd3  lea     rbp, [rsp-170h]
0x18002afdb  sub     rsp, 270h
0x18002afe2  mov     rax, cs:__security_cookie
0x18002afe9  xor     rax, rsp
0x18002afec  mov     [rbp+170h+var_10], rax
0x18002aff3  mov     rdi, rdx
0x18002aff6  mov     qword ptr [rdx], 0
0x18002affd  mov     rbx, rcx
0x18002b000  call    cs:__imp_GetCurrentProcessId
0x18002b007  nop     dword ptr [rax+rax+00h]
0x18002b00c  mov     [rsp+270h+var_248], rbx
0x18002b011  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002b018  mov     r9d, eax
0x18002b01b  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002b023  mov     edx, 104h; unsigned __int64
0x18002b028  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002b02d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b032  mov     r9d, 1F0001h; dwDesiredAccess
0x18002b038  mov     [rsp+270h+var_240], 0
0x18002b041  xor     r8d, r8d; dwFlags
0x18002b044  lea     rdx, [rsp+270h+Name]; lpName
0x18002b049  xor     ecx, ecx; lpMutexAttributes
0x18002b04b  call    cs:__imp_CreateMutexExW
0x18002b052  nop     dword ptr [rax+rax+00h]
0x18002b057  mov     rdx, rax
0x18002b05a  lea     rcx, [rsp+270h+var_240]
0x18002b05f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002b064  cmp     [rsp+270h+var_240], 0
0x18002b06a  jnz     short loc_18002B075
0x18002b06c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002b071  mov     ebx, eax
0x18002b073  jmp     short loc_18002B0E8
0x18002b075  lea     rdx, [rsp+270h+var_238]
0x18002b07a  lea     rcx, [rsp+270h+var_240]
0x18002b07f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002b084  lea     rdx, [rsp+270h+var_230]; void **
0x18002b089  mov     [rsp+270h+var_230], 0
0x18002b092  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002b097  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002b09c  mov     ebx, eax
0x18002b09e  test    eax, eax
0x18002b0a0  jns     short loc_18002B0C9
0x18002b0a2  mov     edx, 12Eh; void *
0x18002b0a7  mov     rcx, [rbp+178h]; this
0x18002b0ae  lea     r8, aWil; "wil"
0x18002b0b5  mov     r9d, eax; char *
0x18002b0b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b0bd  lea     rcx, [rsp+270h+var_238]
0x18002b0c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b0c7  jmp     short loc_18002B0E8
0x18002b0c9  mov     rcx, [rsp+270h+var_230]
0x18002b0ce  test    rcx, rcx
0x18002b0d1  jz      short loc_18002B119
0x18002b0d3  mov     [rdi], rcx
0x18002b0d6  mov     eax, [rcx]
0x18002b0d8  inc     eax
0x18002b0da  mov     [rcx], eax
0x18002b0dc  lea     rcx, [rsp+270h+var_238]
0x18002b0e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b0e6  xor     ebx, ebx
0x18002b0e8  lea     rcx, [rsp+270h+var_240]
0x18002b0ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b0f2  mov     eax, ebx
0x18002b0f4  mov     rcx, [rbp+170h+var_10]
0x18002b0fb  xor     rcx, rsp; StackCookie
0x18002b0fe  call    __security_check_cookie
0x18002b103  lea     r11, [rsp+270h+var_s0]
0x18002b10b  mov     rbx, [r11+20h]
0x18002b10f  mov     rdi, [r11+28h]
0x18002b113  mov     rsp, r11
0x18002b116  pop     rbp
0x18002b117  retn
0x18002b119  mov     r8, rdi
0x18002b11c  lea     rdx, [rsp+270h+var_240]
0x18002b121  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002b126  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002b12b  mov     ebx, eax
0x18002b12d  test    eax, eax
0x18002b12f  jns     short loc_18002B0DC
0x18002b131  mov     edx, 137h
0x18002b136  jmp     loc_18002B0A7
```
