# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18004afcc`
- end: `0x18004b12b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180066664`

## callees

- `0x18004372c`
- `0x180044440`
- `0x180046300`
- `0x18004663c`
- `0x18004afcc`
- `0x18004b134`
- `0x18004b3e0`
- `0x18004b410`
- `0x18004b42c`
- `0x180066728`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004b049`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004b049`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004b004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004b004`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18004afcc  mov     [rsp-8+arg_10], rbx
0x18004afd1  mov     [rsp-8+arg_18], rdi
0x18004afd6  push    rbp
0x18004afd7  lea     rbp, [rsp-170h]
0x18004afdf  sub     rsp, 270h
0x18004afe6  mov     rax, cs:__security_cookie
0x18004afed  xor     rax, rsp
0x18004aff0  mov     [rbp+170h+var_10], rax
0x18004aff7  mov     rdi, rdx
0x18004affa  mov     qword ptr [rdx], 0
0x18004b001  mov     rbx, rcx
0x18004b004  call    cs:__imp_GetCurrentProcessId
0x18004b00a  mov     [rsp+270h+var_248], rbx
0x18004b00f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004b016  mov     r9d, eax
0x18004b019  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18004b021  mov     edx, 104h; unsigned __int64
0x18004b026  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18004b02b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18004b030  mov     r9d, 1F0001h; dwDesiredAccess
0x18004b036  mov     [rsp+270h+var_240], 0
0x18004b03f  xor     r8d, r8d; dwFlags
0x18004b042  lea     rdx, [rsp+270h+Name]; lpName
0x18004b047  xor     ecx, ecx; lpMutexAttributes
0x18004b049  call    cs:__imp_CreateMutexExW
0x18004b04f  mov     rdx, rax
0x18004b052  lea     rcx, [rsp+270h+var_240]
0x18004b057  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004b05c  cmp     [rsp+270h+var_240], 0
0x18004b062  jnz     short loc_18004B06D
0x18004b064  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004b069  mov     ebx, eax
0x18004b06b  jmp     short loc_18004B0D9
0x18004b06d  lea     rdx, [rsp+270h+var_238]
0x18004b072  lea     rcx, [rsp+270h+var_240]
0x18004b077  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18004b07c  lea     rdx, [rsp+270h+var_230]; void **
0x18004b081  mov     [rsp+270h+var_230], 0
0x18004b08a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18004b08f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18004b094  mov     ebx, eax
0x18004b096  test    eax, eax
0x18004b098  jns     short loc_18004B0BA
0x18004b09a  mov     edx, 12Eh; void *
0x18004b09f  mov     rcx, [rbp+178h]; this
0x18004b0a6  mov     r9d, eax; char *
0x18004b0a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b0ae  lea     rcx, [rsp+270h+var_238]
0x18004b0b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004b0b8  jmp     short loc_18004B0D9
0x18004b0ba  mov     rcx, [rsp+270h+var_230]
0x18004b0bf  test    rcx, rcx
0x18004b0c2  jz      short loc_18004B109
0x18004b0c4  mov     [rdi], rcx
0x18004b0c7  mov     eax, [rcx]
0x18004b0c9  inc     eax
0x18004b0cb  mov     [rcx], eax
0x18004b0cd  lea     rcx, [rsp+270h+var_238]
0x18004b0d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004b0d7  xor     ebx, ebx
0x18004b0d9  lea     rcx, [rsp+270h+var_240]
0x18004b0de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004b0e3  mov     eax, ebx
0x18004b0e5  mov     rcx, [rbp+170h+var_10]
0x18004b0ec  xor     rcx, rsp; StackCookie
0x18004b0ef  call    __security_check_cookie
0x18004b0f4  lea     r11, [rsp+270h+var_s0]
0x18004b0fc  mov     rbx, [r11+20h]
0x18004b100  mov     rdi, [r11+28h]
0x18004b104  mov     rsp, r11
0x18004b107  pop     rbp
0x18004b108  retn
0x18004b109  mov     r8, rdi
0x18004b10c  lea     rdx, [rsp+270h+var_240]
0x18004b111  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18004b116  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004b11b  mov     ebx, eax
0x18004b11d  test    eax, eax
0x18004b11f  jns     short loc_18004B0CD
0x18004b121  mov     edx, 137h
0x18004b126  jmp     loc_18004B09F
```
