# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003440`
- end: `0x1400035ea`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140003f68`

## callees

- `0x14000330c`
- `0x140003328`
- `0x140003440`
- `0x140003cc8`
- `0x1400046d4`
- `0x140004d74`
- `0x1400052c8`
- `0x140005440`
- `0x140005a04`
- `0x140005f54`
- `0x1400094d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400034bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400034bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003478`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v16 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v18 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v18,
    Mutex);
  if ( v18 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v18,
      v19);
    v20 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v20, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v17);
      v11 = LastErrorFailHr;
      v12 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v12, (unsigned int)"wil", (const char *)v11, v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
      goto LABEL_9;
    }
    v13 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v13;
      ++*v13;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v15;
      if ( v15 < 0 )
      {
        v11 = (unsigned int)v15;
        v12 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v18,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140003440  mov     [rsp-8+arg_10], rbx
0x140003445  mov     [rsp-8+arg_18], rdi
0x14000344a  push    rbp
0x14000344b  lea     rbp, [rsp-170h]
0x140003453  sub     rsp, 270h
0x14000345a  mov     rax, cs:__security_cookie
0x140003461  xor     rax, rsp
0x140003464  mov     [rbp+170h+var_10], rax
0x14000346b  mov     rdi, rdx
0x14000346e  mov     qword ptr [rdx], 0
0x140003475  mov     rbx, rcx
0x140003478  call    cs:__imp_GetCurrentProcessId
0x14000347e  mov     [rsp+270h+var_248], rbx
0x140003483  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000348a  mov     r9d, eax
0x14000348d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140003495  mov     edx, 104h; unsigned __int64
0x14000349a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000349f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400034a4  mov     r9d, 1F0001h; dwDesiredAccess
0x1400034aa  mov     [rsp+270h+var_240], 0
0x1400034b3  xor     r8d, r8d; dwFlags
0x1400034b6  lea     rdx, [rsp+270h+Name]; lpName
0x1400034bb  xor     ecx, ecx; lpMutexAttributes
0x1400034bd  call    cs:__imp_CreateMutexExW
0x1400034c3  mov     rdx, rax
0x1400034c6  lea     rcx, [rsp+270h+var_240]
0x1400034cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400034d0  cmp     [rsp+270h+var_240], 0
0x1400034d6  jnz     short loc_1400034E4
0x1400034d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400034dd  mov     ebx, eax
0x1400034df  jmp     loc_140003595
0x1400034e4  lea     rdx, [rsp+270h+var_238]
0x1400034e9  lea     rcx, [rsp+270h+var_240]
0x1400034ee  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400034f3  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1400034f8  mov     [rsp+270h+var_230], 0
0x140003501  lea     rcx, [rsp+270h+Name]; pszSrc
0x140003506  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000350b  mov     ebx, eax
0x14000350d  test    eax, eax
0x14000350f  jns     short loc_14000356E
0x140003511  mov     rcx, [rbp+178h]; this
0x140003518  lea     r8, aWil; "wil"
0x14000351f  mov     r9d, eax; char *
0x140003522  mov     edx, 66h ; 'f'; void *
0x140003527  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000352c  mov     rcx, [rbp+178h]; this
0x140003533  lea     r8, aWil; "wil"
0x14000353a  mov     r9d, ebx; char *
0x14000353d  mov     edx, 6Fh ; 'o'; void *
0x140003542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003547  mov     r9d, ebx; char *
0x14000354a  mov     edx, 12Eh; void *
0x14000354f  mov     rcx, [rbp+178h]; this
0x140003556  lea     r8, aWil; "wil"
0x14000355d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003562  lea     rcx, [rsp+270h+var_238]
0x140003567  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000356c  jmp     short loc_140003595
0x14000356e  mov     rax, [rsp+270h+var_230]
0x140003573  lea     rcx, ds:0[rax*4]
0x14000357b  test    rcx, rcx
0x14000357e  jz      short loc_1400035C5
0x140003580  mov     [rdi], rcx
0x140003583  mov     eax, [rcx]
0x140003585  inc     eax
0x140003587  mov     [rcx], eax
0x140003589  lea     rcx, [rsp+270h+var_238]
0x14000358e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003593  xor     ebx, ebx
0x140003595  lea     rcx, [rsp+270h+var_240]
0x14000359a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000359f  mov     eax, ebx
0x1400035a1  mov     rcx, [rbp+170h+var_10]
0x1400035a8  xor     rcx, rsp; StackCookie
0x1400035ab  call    __security_check_cookie
0x1400035b0  lea     r11, [rsp+270h+var_s0]
0x1400035b8  mov     rbx, [r11+20h]
0x1400035bc  mov     rdi, [r11+28h]
0x1400035c0  mov     rsp, r11
0x1400035c3  pop     rbp
0x1400035c4  retn
0x1400035c5  mov     r8, rdi
0x1400035c8  lea     rdx, [rsp+270h+var_240]
0x1400035cd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400035d2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400035d7  mov     ebx, eax
0x1400035d9  test    eax, eax
0x1400035db  jns     short loc_140003589
0x1400035dd  mov     r9d, eax
0x1400035e0  mov     edx, 137h
0x1400035e5  jmp     loc_14000354F
```
