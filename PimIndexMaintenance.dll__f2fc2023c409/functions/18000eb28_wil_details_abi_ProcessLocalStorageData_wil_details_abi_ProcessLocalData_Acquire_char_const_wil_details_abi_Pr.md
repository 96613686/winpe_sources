# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000eb28`
- end: `0x18000ecd2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000fd18`

## callees

- `0x18000d0e0`
- `0x18000e904`
- `0x18000e920`
- `0x18000eb28`
- `0x18000f8b0`
- `0x180010508`
- `0x180010f54`
- `0x1800115e8`
- `0x1800124ec`
- `0x180012850`
- `0x180021240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000eba5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000eba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000eb60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000eb60`

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
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(pszDest, v7, &v19, v8);
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
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(pszDest);
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
0x18000eb28  mov     [rsp-8+arg_10], rbx
0x18000eb2d  mov     [rsp-8+arg_18], rdi
0x18000eb32  push    rbp
0x18000eb33  lea     rbp, [rsp-170h]
0x18000eb3b  sub     rsp, 270h
0x18000eb42  mov     rax, cs:__security_cookie
0x18000eb49  xor     rax, rsp
0x18000eb4c  mov     [rbp+170h+var_10], rax
0x18000eb53  mov     rdi, rdx
0x18000eb56  mov     qword ptr [rdx], 0
0x18000eb5d  mov     rbx, rcx
0x18000eb60  call    cs:__imp_GetCurrentProcessId
0x18000eb66  mov     [rsp+270h+var_248], rbx
0x18000eb6b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000eb72  mov     r9d, eax
0x18000eb75  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000eb7d  mov     edx, 104h; cchDest
0x18000eb82  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000eb87  call    StringCchPrintfW
0x18000eb8c  mov     r9d, 1F0001h; dwDesiredAccess
0x18000eb92  mov     [rsp+270h+var_240], 0
0x18000eb9b  xor     r8d, r8d; dwFlags
0x18000eb9e  lea     rdx, [rsp+270h+pszDest]; lpName
0x18000eba3  xor     ecx, ecx; lpMutexAttributes
0x18000eba5  call    cs:__imp_CreateMutexExW
0x18000ebab  mov     rdx, rax
0x18000ebae  lea     rcx, [rsp+270h+var_240]
0x18000ebb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ebb8  cmp     [rsp+270h+var_240], 0
0x18000ebbe  jnz     short loc_18000EBCC
0x18000ebc0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ebc5  mov     ebx, eax
0x18000ebc7  jmp     loc_18000EC7D
0x18000ebcc  lea     rdx, [rsp+270h+var_238]
0x18000ebd1  lea     rcx, [rsp+270h+var_240]
0x18000ebd6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000ebdb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18000ebe0  mov     [rsp+270h+var_230], 0
0x18000ebe9  lea     rcx, [rsp+270h+pszDest]; pszSrc
0x18000ebee  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000ebf3  mov     ebx, eax
0x18000ebf5  test    eax, eax
0x18000ebf7  jns     short loc_18000EC56
0x18000ebf9  mov     rcx, [rbp+178h]; this
0x18000ec00  lea     r8, aWil; "wil"
0x18000ec07  mov     r9d, eax; char *
0x18000ec0a  mov     edx, 66h ; 'f'; void *
0x18000ec0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec14  mov     rcx, [rbp+178h]; this
0x18000ec1b  lea     r8, aWil; "wil"
0x18000ec22  mov     r9d, ebx; char *
0x18000ec25  mov     edx, 6Fh ; 'o'; void *
0x18000ec2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec2f  mov     r9d, ebx; char *
0x18000ec32  mov     edx, 12Eh; void *
0x18000ec37  mov     rcx, [rbp+178h]; this
0x18000ec3e  lea     r8, aWil; "wil"
0x18000ec45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec4a  lea     rcx, [rsp+270h+var_238]
0x18000ec4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ec54  jmp     short loc_18000EC7D
0x18000ec56  mov     rax, [rsp+270h+var_230]
0x18000ec5b  lea     rcx, ds:0[rax*4]
0x18000ec63  test    rcx, rcx
0x18000ec66  jz      short loc_18000ECAD
0x18000ec68  mov     [rdi], rcx
0x18000ec6b  mov     eax, [rcx]
0x18000ec6d  inc     eax
0x18000ec6f  mov     [rcx], eax
0x18000ec71  lea     rcx, [rsp+270h+var_238]
0x18000ec76  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ec7b  xor     ebx, ebx
0x18000ec7d  lea     rcx, [rsp+270h+var_240]
0x18000ec82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ec87  mov     eax, ebx
0x18000ec89  mov     rcx, [rbp+170h+var_10]
0x18000ec90  xor     rcx, rsp; StackCookie
0x18000ec93  call    __security_check_cookie
0x18000ec98  lea     r11, [rsp+270h+var_s0]
0x18000eca0  mov     rbx, [r11+20h]
0x18000eca4  mov     rdi, [r11+28h]
0x18000eca8  mov     rsp, r11
0x18000ecab  pop     rbp
0x18000ecac  retn
0x18000ecad  mov     r8, rdi
0x18000ecb0  lea     rdx, [rsp+270h+var_240]
0x18000ecb5  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000ecba  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000ecbf  mov     ebx, eax
0x18000ecc1  test    eax, eax
0x18000ecc3  jns     short loc_18000EC71
0x18000ecc5  mov     r9d, eax
0x18000ecc8  mov     edx, 137h
0x18000eccd  jmp     loc_18000EC37
```
