# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800efee8`
- end: `0x1800f007d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800f0970`

## callees

- `0x180015a68`
- `0x1800c6918`
- `0x1800efdb0`
- `0x1800efdcc`
- `0x1800efee8`
- `0x1800f1004`
- `0x1800f147c`
- `0x1800f1a8c`
- `0x1800f1e88`
- `0x1800f1f8c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800eff20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800eff20`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800eff65`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800eff65`

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
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800efee8  mov     [rsp-8+arg_10], rbx
0x1800efeed  mov     [rsp-8+arg_18], rdi
0x1800efef2  push    rbp
0x1800efef3  lea     rbp, [rsp-170h]
0x1800efefb  sub     rsp, 270h
0x1800eff02  mov     rax, cs:__security_cookie
0x1800eff09  xor     rax, rsp
0x1800eff0c  mov     [rbp+170h+var_10], rax
0x1800eff13  mov     rdi, rdx
0x1800eff16  mov     qword ptr [rdx], 0
0x1800eff1d  mov     rbx, rcx
0x1800eff20  call    cs:__imp_GetCurrentProcessId
0x1800eff26  mov     [rsp+270h+var_248], rbx
0x1800eff2b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800eff32  mov     r9d, eax
0x1800eff35  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800eff3d  mov     edx, 104h; unsigned __int64
0x1800eff42  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800eff47  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800eff4c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800eff52  mov     [rsp+270h+var_240], 0
0x1800eff5b  xor     r8d, r8d; dwFlags
0x1800eff5e  lea     rdx, [rsp+270h+Name]; lpName
0x1800eff63  xor     ecx, ecx; lpMutexAttributes
0x1800eff65  call    cs:__imp_CreateMutexExW
0x1800eff6b  mov     rdx, rax
0x1800eff6e  lea     rcx, [rsp+270h+var_240]
0x1800eff73  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800eff78  cmp     [rsp+270h+var_240], 0
0x1800eff7e  jnz     short loc_1800EFF8C
0x1800eff80  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800eff85  mov     ebx, eax
0x1800eff87  jmp     loc_1800F0028
0x1800eff8c  lea     rdx, [rsp+270h+var_238]
0x1800eff91  lea     rcx, [rsp+270h+var_240]
0x1800eff96  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800eff9b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800effa0  mov     [rsp+270h+var_230], 0
0x1800effa9  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800effae  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800effb3  mov     ebx, eax
0x1800effb5  test    eax, eax
0x1800effb7  jns     short loc_1800F0001
0x1800effb9  mov     rcx, [rbp+178h]; this
0x1800effc0  mov     r9d, eax; char *
0x1800effc3  mov     edx, 66h ; 'f'; void *
0x1800effc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800effcd  mov     rcx, [rbp+178h]; this
0x1800effd4  mov     r9d, ebx; char *
0x1800effd7  mov     edx, 6Fh ; 'o'; void *
0x1800effdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800effe1  mov     r9d, ebx; char *
0x1800effe4  mov     edx, 12Eh; void *
0x1800effe9  mov     rcx, [rbp+178h]; this
0x1800efff0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800efff5  lea     rcx, [rsp+270h+var_238]
0x1800efffa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800effff  jmp     short loc_1800F0028
0x1800f0001  mov     rax, [rsp+270h+var_230]
0x1800f0006  lea     rcx, ds:0[rax*4]
0x1800f000e  test    rcx, rcx
0x1800f0011  jz      short loc_1800F0058
0x1800f0013  mov     [rdi], rcx
0x1800f0016  mov     eax, [rcx]
0x1800f0018  inc     eax
0x1800f001a  mov     [rcx], eax
0x1800f001c  lea     rcx, [rsp+270h+var_238]
0x1800f0021  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800f0026  xor     ebx, ebx
0x1800f0028  lea     rcx, [rsp+270h+var_240]
0x1800f002d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800f0032  mov     eax, ebx
0x1800f0034  mov     rcx, [rbp+170h+var_10]
0x1800f003b  xor     rcx, rsp; StackCookie
0x1800f003e  call    __security_check_cookie
0x1800f0043  lea     r11, [rsp+270h+var_s0]
0x1800f004b  mov     rbx, [r11+20h]
0x1800f004f  mov     rdi, [r11+28h]
0x1800f0053  mov     rsp, r11
0x1800f0056  pop     rbp
0x1800f0057  retn
0x1800f0058  mov     r8, rdi
0x1800f005b  lea     rdx, [rsp+270h+var_240]
0x1800f0060  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800f0065  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800f006a  mov     ebx, eax
0x1800f006c  test    eax, eax
0x1800f006e  jns     short loc_1800F001C
0x1800f0070  mov     r9d, eax
0x1800f0073  mov     edx, 137h
0x1800f0078  jmp     loc_1800EFFE9
```
