# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800047b8`
- end: `0x180004962`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005288`

## callees

- `0x180002420`
- `0x180004624`
- `0x180004640`
- `0x1800047b8`
- `0x180004fe8`
- `0x1800059dc`
- `0x180006014`
- `0x180006578`
- `0x180006728`
- `0x180006a40`
- `0x180006b48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004835`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004835`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800047f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800047f0`

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
0x1800047b8  mov     [rsp-8+arg_10], rbx
0x1800047bd  mov     [rsp-8+arg_18], rdi
0x1800047c2  push    rbp
0x1800047c3  lea     rbp, [rsp-170h]
0x1800047cb  sub     rsp, 270h
0x1800047d2  mov     rax, cs:__security_cookie
0x1800047d9  xor     rax, rsp
0x1800047dc  mov     [rbp+170h+var_10], rax
0x1800047e3  mov     rdi, rdx
0x1800047e6  mov     qword ptr [rdx], 0
0x1800047ed  mov     rbx, rcx
0x1800047f0  call    cs:__imp_GetCurrentProcessId
0x1800047f6  mov     [rsp+270h+var_248], rbx
0x1800047fb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004802  mov     r9d, eax
0x180004805  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000480d  mov     edx, 104h; unsigned __int64
0x180004812  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004817  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000481c  mov     r9d, 1F0001h; dwDesiredAccess
0x180004822  mov     [rsp+270h+var_240], 0
0x18000482b  xor     r8d, r8d; dwFlags
0x18000482e  lea     rdx, [rsp+270h+Name]; lpName
0x180004833  xor     ecx, ecx; lpMutexAttributes
0x180004835  call    cs:__imp_CreateMutexExW
0x18000483b  mov     rdx, rax
0x18000483e  lea     rcx, [rsp+270h+var_240]
0x180004843  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004848  cmp     [rsp+270h+var_240], 0
0x18000484e  jnz     short loc_18000485C
0x180004850  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004855  mov     ebx, eax
0x180004857  jmp     loc_18000490D
0x18000485c  lea     rdx, [rsp+270h+var_238]
0x180004861  lea     rcx, [rsp+270h+var_240]
0x180004866  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000486b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180004870  mov     [rsp+270h+var_230], 0
0x180004879  lea     rcx, [rsp+270h+Name]; pszSrc
0x18000487e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004883  mov     ebx, eax
0x180004885  test    eax, eax
0x180004887  jns     short loc_1800048E6
0x180004889  mov     rcx, [rbp+178h]; this
0x180004890  lea     r8, aWil; "wil"
0x180004897  mov     r9d, eax; char *
0x18000489a  mov     edx, 66h ; 'f'; void *
0x18000489f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048a4  mov     rcx, [rbp+178h]; this
0x1800048ab  lea     r8, aWil; "wil"
0x1800048b2  mov     r9d, ebx; char *
0x1800048b5  mov     edx, 6Fh ; 'o'; void *
0x1800048ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048bf  mov     r9d, ebx; char *
0x1800048c2  mov     edx, 12Eh; void *
0x1800048c7  mov     rcx, [rbp+178h]; this
0x1800048ce  lea     r8, aWil; "wil"
0x1800048d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048da  lea     rcx, [rsp+270h+var_238]
0x1800048df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800048e4  jmp     short loc_18000490D
0x1800048e6  mov     rax, [rsp+270h+var_230]
0x1800048eb  lea     rcx, ds:0[rax*4]
0x1800048f3  test    rcx, rcx
0x1800048f6  jz      short loc_18000493D
0x1800048f8  mov     [rdi], rcx
0x1800048fb  mov     eax, [rcx]
0x1800048fd  inc     eax
0x1800048ff  mov     [rcx], eax
0x180004901  lea     rcx, [rsp+270h+var_238]
0x180004906  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000490b  xor     ebx, ebx
0x18000490d  lea     rcx, [rsp+270h+var_240]
0x180004912  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004917  mov     eax, ebx
0x180004919  mov     rcx, [rbp+170h+var_10]
0x180004920  xor     rcx, rsp; StackCookie
0x180004923  call    __security_check_cookie
0x180004928  lea     r11, [rsp+270h+var_s0]
0x180004930  mov     rbx, [r11+20h]
0x180004934  mov     rdi, [r11+28h]
0x180004938  mov     rsp, r11
0x18000493b  pop     rbp
0x18000493c  retn
0x18000493d  mov     r8, rdi
0x180004940  lea     rdx, [rsp+270h+var_240]
0x180004945  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000494a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000494f  mov     ebx, eax
0x180004951  test    eax, eax
0x180004953  jns     short loc_180004901
0x180004955  mov     r9d, eax
0x180004958  mov     edx, 137h
0x18000495d  jmp     loc_1800048C7
```
