# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008f7c`
- end: `0x180009126`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009f0c`

## callees

- `0x180003570`
- `0x180006e9c`
- `0x180008c10`
- `0x180008c2c`
- `0x180008f7c`
- `0x18000a60c`
- `0x18000b364`
- `0x18000c150`
- `0x18000cfa0`
- `0x18000d5f8`
- `0x18000f0a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008ff9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008ff9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008fb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008fb4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180008f7c  mov     [rsp-8+arg_10], rbx
0x180008f81  mov     [rsp-8+arg_18], rdi
0x180008f86  push    rbp
0x180008f87  lea     rbp, [rsp-170h]
0x180008f8f  sub     rsp, 270h
0x180008f96  mov     rax, cs:__security_cookie
0x180008f9d  xor     rax, rsp
0x180008fa0  mov     [rbp+170h+var_10], rax
0x180008fa7  mov     rdi, rdx
0x180008faa  mov     qword ptr [rdx], 0
0x180008fb1  mov     rbx, rcx
0x180008fb4  call    cs:__imp_GetCurrentProcessId
0x180008fba  mov     [rsp+270h+var_248], rbx
0x180008fbf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008fc6  mov     r9d, eax
0x180008fc9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180008fd1  mov     edx, 104h; unsigned __int64
0x180008fd6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008fdb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008fe0  mov     r9d, 1F0001h; dwDesiredAccess
0x180008fe6  mov     [rsp+270h+var_240], 0
0x180008fef  xor     r8d, r8d; dwFlags
0x180008ff2  lea     rdx, [rsp+270h+Name]; lpName
0x180008ff7  xor     ecx, ecx; lpMutexAttributes
0x180008ff9  call    cs:__imp_CreateMutexExW
0x180008fff  mov     rdx, rax
0x180009002  lea     rcx, [rsp+270h+var_240]
0x180009007  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000900c  cmp     [rsp+270h+var_240], 0
0x180009012  jnz     short loc_180009020
0x180009014  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009019  mov     ebx, eax
0x18000901b  jmp     loc_1800090D1
0x180009020  lea     rdx, [rsp+270h+var_238]
0x180009025  lea     rcx, [rsp+270h+var_240]
0x18000902a  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000902f  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180009034  mov     [rsp+270h+var_230], 0
0x18000903d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009042  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009047  mov     ebx, eax
0x180009049  test    eax, eax
0x18000904b  jns     short loc_1800090AA
0x18000904d  mov     rcx, [rbp+178h]; this
0x180009054  lea     r8, aWil; "wil"
0x18000905b  mov     r9d, eax; char *
0x18000905e  mov     edx, 66h ; 'f'; void *
0x180009063  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009068  mov     rcx, [rbp+178h]; this
0x18000906f  lea     r8, aWil; "wil"
0x180009076  mov     r9d, ebx; char *
0x180009079  mov     edx, 6Fh ; 'o'; void *
0x18000907e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009083  mov     r9d, ebx; char *
0x180009086  mov     edx, 12Eh; void *
0x18000908b  mov     rcx, [rbp+178h]; this
0x180009092  lea     r8, aWil; "wil"
0x180009099  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000909e  lea     rcx, [rsp+270h+var_238]
0x1800090a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800090a8  jmp     short loc_1800090D1
0x1800090aa  mov     rax, [rsp+270h+var_230]
0x1800090af  lea     rcx, ds:0[rax*4]
0x1800090b7  test    rcx, rcx
0x1800090ba  jz      short loc_180009101
0x1800090bc  mov     [rdi], rcx
0x1800090bf  mov     eax, [rcx]
0x1800090c1  inc     eax
0x1800090c3  mov     [rcx], eax
0x1800090c5  lea     rcx, [rsp+270h+var_238]
0x1800090ca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800090cf  xor     ebx, ebx
0x1800090d1  lea     rcx, [rsp+270h+var_240]
0x1800090d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800090db  mov     eax, ebx
0x1800090dd  mov     rcx, [rbp+170h+var_10]
0x1800090e4  xor     rcx, rsp; StackCookie
0x1800090e7  call    __security_check_cookie
0x1800090ec  lea     r11, [rsp+270h+var_s0]
0x1800090f4  mov     rbx, [r11+20h]
0x1800090f8  mov     rdi, [r11+28h]
0x1800090fc  mov     rsp, r11
0x1800090ff  pop     rbp
0x180009100  retn
0x180009101  mov     r8, rdi
0x180009104  lea     rdx, [rsp+270h+var_240]
0x180009109  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000910e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009113  mov     ebx, eax
0x180009115  test    eax, eax
0x180009117  jns     short loc_1800090C5
0x180009119  mov     r9d, eax
0x18000911c  mov     edx, 137h
0x180009121  jmp     loc_18000908B
```
