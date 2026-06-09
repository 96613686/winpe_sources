# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18005af98`
- end: `0x18005b107`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005c0dc`

## callees

- `0x18005450c`
- `0x1800545bc`
- `0x180058b30`
- `0x18005ac90`
- `0x18005acac`
- `0x18005af98`
- `0x18005c674`
- `0x18005dbac`
- `0x18005e008`
- `0x18005e8d4`
- `0x18005eafc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005b015`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005b015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005afd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005afd0`

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
    v12 = 0;
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
0x18005af98  mov     [rsp-8+arg_10], rbx
0x18005af9d  mov     [rsp-8+arg_18], rdi
0x18005afa2  push    rbp
0x18005afa3  lea     rbp, [rsp-170h]
0x18005afab  sub     rsp, 270h
0x18005afb2  mov     rax, cs:__security_cookie
0x18005afb9  xor     rax, rsp
0x18005afbc  mov     [rbp+170h+var_10], rax
0x18005afc3  mov     rdi, rdx
0x18005afc6  mov     qword ptr [rdx], 0
0x18005afcd  mov     rbx, rcx
0x18005afd0  call    cs:__imp_GetCurrentProcessId
0x18005afd6  mov     [rsp+270h+var_248], rbx
0x18005afdb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18005afe2  mov     r9d, eax
0x18005afe5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18005afed  mov     edx, 104h; unsigned __int64
0x18005aff2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005aff7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005affc  mov     r9d, 1F0001h; dwDesiredAccess
0x18005b002  mov     [rsp+270h+var_240], 0
0x18005b00b  xor     r8d, r8d; dwFlags
0x18005b00e  lea     rdx, [rsp+270h+Name]; lpName
0x18005b013  xor     ecx, ecx; lpMutexAttributes
0x18005b015  call    cs:__imp_CreateMutexExW
0x18005b01b  mov     rdx, rax
0x18005b01e  lea     rcx, [rsp+270h+var_240]
0x18005b023  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005b028  cmp     [rsp+270h+var_240], 0
0x18005b02e  jnz     short loc_18005B039
0x18005b030  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005b035  mov     ebx, eax
0x18005b037  jmp     short loc_18005B0B5
0x18005b039  lea     rdx, [rsp+270h+var_238]
0x18005b03e  mov     [rsp+270h+var_238], 0
0x18005b047  lea     rcx, [rsp+270h+var_240]
0x18005b04c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18005b051  lea     rdx, [rsp+270h+var_230]; void **
0x18005b056  mov     [rsp+270h+var_230], 0
0x18005b05f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005b064  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18005b069  mov     ebx, eax
0x18005b06b  test    eax, eax
0x18005b06d  jns     short loc_18005B096
0x18005b06f  mov     edx, 12Eh; void *
0x18005b074  mov     rcx, [rbp+178h]; this
0x18005b07b  lea     r8, aWil; "wil"
0x18005b082  mov     r9d, eax; char *
0x18005b085  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b08a  lea     rcx, [rsp+270h+var_238]
0x18005b08f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005b094  jmp     short loc_18005B0B5
0x18005b096  mov     rcx, [rsp+270h+var_230]
0x18005b09b  test    rcx, rcx
0x18005b09e  jz      short loc_18005B0E5
0x18005b0a0  mov     [rdi], rcx
0x18005b0a3  mov     eax, [rcx]
0x18005b0a5  inc     eax
0x18005b0a7  mov     [rcx], eax
0x18005b0a9  lea     rcx, [rsp+270h+var_238]
0x18005b0ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005b0b3  xor     ebx, ebx
0x18005b0b5  lea     rcx, [rsp+270h+var_240]
0x18005b0ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005b0bf  mov     eax, ebx
0x18005b0c1  mov     rcx, [rbp+170h+var_10]
0x18005b0c8  xor     rcx, rsp; StackCookie
0x18005b0cb  call    __security_check_cookie
0x18005b0d0  lea     r11, [rsp+270h+var_s0]
0x18005b0d8  mov     rbx, [r11+20h]
0x18005b0dc  mov     rdi, [r11+28h]
0x18005b0e0  mov     rsp, r11
0x18005b0e3  pop     rbp
0x18005b0e4  retn
0x18005b0e5  mov     r8, rdi
0x18005b0e8  lea     rdx, [rsp+270h+var_240]
0x18005b0ed  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005b0f2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005b0f7  mov     ebx, eax
0x18005b0f9  test    eax, eax
0x18005b0fb  jns     short loc_18005B0A9
0x18005b0fd  mov     edx, 137h
0x18005b102  jmp     loc_18005B074
```
