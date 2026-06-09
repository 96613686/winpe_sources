# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000279c`
- end: `0x180002902`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005cbc`

## callees

- `0x18000279c`
- `0x180002bc8`
- `0x180002be4`
- `0x180002c80`
- `0x180002cd4`
- `0x1800033d0`
- `0x1800051c0`
- `0x180006538`
- `0x180006c90`
- `0x180007338`
- `0x1800075a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002819`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002819`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800027d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800027d4`

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
0x18000279c  mov     [rsp-8+arg_10], rbx
0x1800027a1  mov     [rsp-8+arg_18], rdi
0x1800027a6  push    rbp
0x1800027a7  lea     rbp, [rsp-170h]
0x1800027af  sub     rsp, 270h
0x1800027b6  mov     rax, cs:__security_cookie
0x1800027bd  xor     rax, rsp
0x1800027c0  mov     [rbp+170h+var_10], rax
0x1800027c7  mov     rdi, rdx
0x1800027ca  mov     qword ptr [rdx], 0
0x1800027d1  mov     rbx, rcx
0x1800027d4  call    cs:__imp_GetCurrentProcessId
0x1800027da  mov     [rsp+270h+var_248], rbx
0x1800027df  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800027e6  mov     r9d, eax
0x1800027e9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800027f1  mov     edx, 104h; unsigned __int64
0x1800027f6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800027fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002800  mov     r9d, 1F0001h; dwDesiredAccess
0x180002806  mov     [rsp+270h+var_240], 0
0x18000280f  xor     r8d, r8d; dwFlags
0x180002812  lea     rdx, [rsp+270h+Name]; lpName
0x180002817  xor     ecx, ecx; lpMutexAttributes
0x180002819  call    cs:__imp_CreateMutexExW
0x18000281f  mov     rdx, rax
0x180002822  lea     rcx, [rsp+270h+var_240]
0x180002827  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000282c  cmp     [rsp+270h+var_240], 0
0x180002832  jnz     short loc_18000283D
0x180002834  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180002839  mov     ebx, eax
0x18000283b  jmp     short loc_1800028B0
0x18000283d  lea     rdx, [rsp+270h+var_238]
0x180002842  lea     rcx, [rsp+270h+var_240]
0x180002847  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000284c  lea     rdx, [rsp+270h+var_230]; void **
0x180002851  mov     [rsp+270h+var_230], 0
0x18000285a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000285f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180002864  mov     ebx, eax
0x180002866  test    eax, eax
0x180002868  jns     short loc_180002891
0x18000286a  mov     edx, 12Eh; void *
0x18000286f  mov     rcx, [rbp+178h]; this
0x180002876  lea     r8, aWil; "wil"
0x18000287d  mov     r9d, eax; char *
0x180002880  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002885  lea     rcx, [rsp+270h+var_238]
0x18000288a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000288f  jmp     short loc_1800028B0
0x180002891  mov     rcx, [rsp+270h+var_230]
0x180002896  test    rcx, rcx
0x180002899  jz      short loc_1800028E0
0x18000289b  mov     [rdi], rcx
0x18000289e  mov     eax, [rcx]
0x1800028a0  inc     eax
0x1800028a2  mov     [rcx], eax
0x1800028a4  lea     rcx, [rsp+270h+var_238]
0x1800028a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800028ae  xor     ebx, ebx
0x1800028b0  lea     rcx, [rsp+270h+var_240]
0x1800028b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800028ba  mov     eax, ebx
0x1800028bc  mov     rcx, [rbp+170h+var_10]
0x1800028c3  xor     rcx, rsp; StackCookie
0x1800028c6  call    __security_check_cookie
0x1800028cb  lea     r11, [rsp+270h+var_s0]
0x1800028d3  mov     rbx, [r11+20h]
0x1800028d7  mov     rdi, [r11+28h]
0x1800028db  mov     rsp, r11
0x1800028de  pop     rbp
0x1800028df  retn
0x1800028e0  mov     r8, rdi
0x1800028e3  lea     rdx, [rsp+270h+var_240]
0x1800028e8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800028ed  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800028f2  mov     ebx, eax
0x1800028f4  test    eax, eax
0x1800028f6  jns     short loc_1800028A4
0x1800028f8  mov     edx, 137h
0x1800028fd  jmp     loc_18000286F
```
