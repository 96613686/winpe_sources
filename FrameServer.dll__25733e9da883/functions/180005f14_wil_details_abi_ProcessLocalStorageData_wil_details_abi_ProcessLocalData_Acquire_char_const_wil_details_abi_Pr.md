# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005f14`
- end: `0x1800060be`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006b34`

## callees

- `0x180003e20`
- `0x180005d98`
- `0x180005db4`
- `0x180005f14`
- `0x180006890`
- `0x180007294`
- `0x180007824`
- `0x180007c10`
- `0x180007d20`
- `0x1800080f0`
- `0x180008338`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005f91`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005f91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005f4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005f4c`

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
  HANDLE v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
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
      &v18);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
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
0x180005f14  mov     [rsp-8+arg_10], rbx
0x180005f19  mov     [rsp-8+arg_18], rdi
0x180005f1e  push    rbp
0x180005f1f  lea     rbp, [rsp-170h]
0x180005f27  sub     rsp, 270h
0x180005f2e  mov     rax, cs:__security_cookie
0x180005f35  xor     rax, rsp
0x180005f38  mov     [rbp+170h+var_10], rax
0x180005f3f  mov     rdi, rdx
0x180005f42  mov     qword ptr [rdx], 0
0x180005f49  mov     rbx, rcx
0x180005f4c  call    cs:__imp_GetCurrentProcessId
0x180005f52  mov     [rsp+270h+var_248], rbx
0x180005f57  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005f5e  mov     r9d, eax
0x180005f61  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180005f69  mov     edx, 104h; unsigned __int64
0x180005f6e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005f73  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005f78  mov     r9d, 1F0001h; dwDesiredAccess
0x180005f7e  mov     [rsp+270h+var_240], 0
0x180005f87  xor     r8d, r8d; dwFlags
0x180005f8a  lea     rdx, [rsp+270h+Name]; lpName
0x180005f8f  xor     ecx, ecx; lpMutexAttributes
0x180005f91  call    cs:__imp_CreateMutexExW
0x180005f97  mov     rdx, rax
0x180005f9a  lea     rcx, [rsp+270h+var_240]
0x180005f9f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005fa4  cmp     [rsp+270h+var_240], 0
0x180005faa  jnz     short loc_180005FB8
0x180005fac  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005fb1  mov     ebx, eax
0x180005fb3  jmp     loc_180006069
0x180005fb8  lea     rdx, [rsp+270h+var_238]
0x180005fbd  lea     rcx, [rsp+270h+var_240]
0x180005fc2  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005fc7  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180005fcc  mov     [rsp+270h+var_230], 0
0x180005fd5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005fda  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005fdf  mov     ebx, eax
0x180005fe1  test    eax, eax
0x180005fe3  jns     short loc_180006042
0x180005fe5  mov     rcx, [rbp+178h]; this
0x180005fec  lea     r8, aWil; "wil"
0x180005ff3  mov     r9d, eax; char *
0x180005ff6  mov     edx, 66h ; 'f'; void *
0x180005ffb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006000  mov     rcx, [rbp+178h]; this
0x180006007  lea     r8, aWil; "wil"
0x18000600e  mov     r9d, ebx; char *
0x180006011  mov     edx, 6Fh ; 'o'; void *
0x180006016  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000601b  mov     r9d, ebx; char *
0x18000601e  mov     edx, 12Eh; void *
0x180006023  mov     rcx, [rbp+178h]; this
0x18000602a  lea     r8, aWil; "wil"
0x180006031  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006036  lea     rcx, [rsp+270h+var_238]
0x18000603b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006040  jmp     short loc_180006069
0x180006042  mov     rax, [rsp+270h+var_230]
0x180006047  lea     rcx, ds:0[rax*4]
0x18000604f  test    rcx, rcx
0x180006052  jz      short loc_180006099
0x180006054  mov     [rdi], rcx
0x180006057  mov     eax, [rcx]
0x180006059  inc     eax
0x18000605b  mov     [rcx], eax
0x18000605d  lea     rcx, [rsp+270h+var_238]
0x180006062  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006067  xor     ebx, ebx
0x180006069  lea     rcx, [rsp+270h+var_240]
0x18000606e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006073  mov     eax, ebx
0x180006075  mov     rcx, [rbp+170h+var_10]
0x18000607c  xor     rcx, rsp; StackCookie
0x18000607f  call    __security_check_cookie
0x180006084  lea     r11, [rsp+270h+var_s0]
0x18000608c  mov     rbx, [r11+20h]
0x180006090  mov     rdi, [r11+28h]
0x180006094  mov     rsp, r11
0x180006097  pop     rbp
0x180006098  retn
0x180006099  mov     r8, rdi
0x18000609c  lea     rdx, [rsp+270h+var_240]
0x1800060a1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800060a6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800060ab  mov     ebx, eax
0x1800060ad  test    eax, eax
0x1800060af  jns     short loc_18000605D
0x1800060b1  mov     r9d, eax
0x1800060b4  mov     edx, 137h
0x1800060b9  jmp     loc_180006023
```
