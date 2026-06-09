# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800c4598`
- end: `0x1800c46f7`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c53fc`

## callees

- `0x1800180e4`
- `0x1800c4290`
- `0x1800c42ac`
- `0x1800c4598`
- `0x1800c5228`
- `0x1800c5f64`
- `0x1800c706c`
- `0x1800c7a4c`
- `0x1800c8194`
- `0x1800c8320`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800c4615`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800c4615`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c45d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c45d0`

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
0x1800c4598  mov     [rsp-8+arg_10], rbx
0x1800c459d  mov     [rsp-8+arg_18], rdi
0x1800c45a2  push    rbp
0x1800c45a3  lea     rbp, [rsp-170h]
0x1800c45ab  sub     rsp, 270h
0x1800c45b2  mov     rax, cs:__security_cookie
0x1800c45b9  xor     rax, rsp
0x1800c45bc  mov     [rbp+170h+var_10], rax
0x1800c45c3  mov     rdi, rdx
0x1800c45c6  mov     qword ptr [rdx], 0
0x1800c45cd  mov     rbx, rcx
0x1800c45d0  call    cs:__imp_GetCurrentProcessId
0x1800c45d6  mov     [rsp+270h+var_248], rbx
0x1800c45db  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800c45e2  mov     r9d, eax
0x1800c45e5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800c45ed  mov     edx, 104h; unsigned __int64
0x1800c45f2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800c45f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c45fc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800c4602  mov     [rsp+270h+var_240], 0
0x1800c460b  xor     r8d, r8d; dwFlags
0x1800c460e  lea     rdx, [rsp+270h+Name]; lpName
0x1800c4613  xor     ecx, ecx; lpMutexAttributes
0x1800c4615  call    cs:__imp_CreateMutexExW
0x1800c461b  mov     rdx, rax
0x1800c461e  lea     rcx, [rsp+270h+var_240]
0x1800c4623  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800c4628  cmp     [rsp+270h+var_240], 0
0x1800c462e  jnz     short loc_1800C4639
0x1800c4630  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800c4635  mov     ebx, eax
0x1800c4637  jmp     short loc_1800C46A5
0x1800c4639  lea     rdx, [rsp+270h+var_238]
0x1800c463e  lea     rcx, [rsp+270h+var_240]
0x1800c4643  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800c4648  lea     rdx, [rsp+270h+var_230]; void **
0x1800c464d  mov     [rsp+270h+var_230], 0
0x1800c4656  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800c465b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800c4660  mov     ebx, eax
0x1800c4662  test    eax, eax
0x1800c4664  jns     short loc_1800C4686
0x1800c4666  mov     edx, 12Eh; void *
0x1800c466b  mov     rcx, [rbp+178h]; this
0x1800c4672  mov     r9d, eax; char *
0x1800c4675  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c467a  lea     rcx, [rsp+270h+var_238]
0x1800c467f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c4684  jmp     short loc_1800C46A5
0x1800c4686  mov     rcx, [rsp+270h+var_230]
0x1800c468b  test    rcx, rcx
0x1800c468e  jz      short loc_1800C46D5
0x1800c4690  mov     [rdi], rcx
0x1800c4693  mov     eax, [rcx]
0x1800c4695  inc     eax
0x1800c4697  mov     [rcx], eax
0x1800c4699  lea     rcx, [rsp+270h+var_238]
0x1800c469e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c46a3  xor     ebx, ebx
0x1800c46a5  lea     rcx, [rsp+270h+var_240]
0x1800c46aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c46af  mov     eax, ebx
0x1800c46b1  mov     rcx, [rbp+170h+var_10]
0x1800c46b8  xor     rcx, rsp; StackCookie
0x1800c46bb  call    __security_check_cookie
0x1800c46c0  lea     r11, [rsp+270h+var_s0]
0x1800c46c8  mov     rbx, [r11+20h]
0x1800c46cc  mov     rdi, [r11+28h]
0x1800c46d0  mov     rsp, r11
0x1800c46d3  pop     rbp
0x1800c46d4  retn
0x1800c46d5  mov     r8, rdi
0x1800c46d8  lea     rdx, [rsp+270h+var_240]
0x1800c46dd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800c46e2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800c46e7  mov     ebx, eax
0x1800c46e9  test    eax, eax
0x1800c46eb  jns     short loc_1800C4699
0x1800c46ed  mov     edx, 137h
0x1800c46f2  jmp     loc_1800C466B
```
