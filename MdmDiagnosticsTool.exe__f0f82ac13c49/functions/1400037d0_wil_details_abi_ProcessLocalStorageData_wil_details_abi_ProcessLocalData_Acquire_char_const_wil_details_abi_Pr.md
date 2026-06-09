# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400037d0`
- end: `0x14000397a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140004ed4`

## callees

- `0x140003438`
- `0x140003454`
- `0x1400037d0`
- `0x140004598`
- `0x140005648`
- `0x140006244`
- `0x1400067b8`
- `0x140006a1c`
- `0x14000728c`
- `0x140007eb8`
- `0x1400096d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000384d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000384d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003808`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003808`

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
0x1400037d0  mov     [rsp-8+arg_10], rbx
0x1400037d5  mov     [rsp-8+arg_18], rdi
0x1400037da  push    rbp
0x1400037db  lea     rbp, [rsp-170h]
0x1400037e3  sub     rsp, 270h
0x1400037ea  mov     rax, cs:__security_cookie
0x1400037f1  xor     rax, rsp
0x1400037f4  mov     [rbp+170h+var_10], rax
0x1400037fb  mov     rdi, rdx
0x1400037fe  mov     qword ptr [rdx], 0
0x140003805  mov     rbx, rcx
0x140003808  call    cs:__imp_GetCurrentProcessId
0x14000380e  mov     [rsp+270h+var_248], rbx
0x140003813  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000381a  mov     r9d, eax
0x14000381d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140003825  mov     edx, 104h; unsigned __int64
0x14000382a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000382f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003834  mov     r9d, 1F0001h; dwDesiredAccess
0x14000383a  mov     [rsp+270h+var_240], 0
0x140003843  xor     r8d, r8d; dwFlags
0x140003846  lea     rdx, [rsp+270h+Name]; lpName
0x14000384b  xor     ecx, ecx; lpMutexAttributes
0x14000384d  call    cs:__imp_CreateMutexExW
0x140003853  mov     rdx, rax
0x140003856  lea     rcx, [rsp+270h+var_240]
0x14000385b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140003860  cmp     [rsp+270h+var_240], 0
0x140003866  jnz     short loc_140003874
0x140003868  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000386d  mov     ebx, eax
0x14000386f  jmp     loc_140003925
0x140003874  lea     rdx, [rsp+270h+var_238]
0x140003879  lea     rcx, [rsp+270h+var_240]
0x14000387e  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140003883  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x140003888  mov     [rsp+270h+var_230], 0
0x140003891  lea     rcx, [rsp+270h+Name]; pszSrc
0x140003896  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000389b  mov     ebx, eax
0x14000389d  test    eax, eax
0x14000389f  jns     short loc_1400038FE
0x1400038a1  mov     rcx, [rbp+178h]; this
0x1400038a8  lea     r8, aWil; "wil"
0x1400038af  mov     r9d, eax; char *
0x1400038b2  mov     edx, 66h ; 'f'; void *
0x1400038b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400038bc  mov     rcx, [rbp+178h]; this
0x1400038c3  lea     r8, aWil; "wil"
0x1400038ca  mov     r9d, ebx; char *
0x1400038cd  mov     edx, 6Fh ; 'o'; void *
0x1400038d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400038d7  mov     r9d, ebx; char *
0x1400038da  mov     edx, 12Eh; void *
0x1400038df  mov     rcx, [rbp+178h]; this
0x1400038e6  lea     r8, aWil; "wil"
0x1400038ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400038f2  lea     rcx, [rsp+270h+var_238]
0x1400038f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400038fc  jmp     short loc_140003925
0x1400038fe  mov     rax, [rsp+270h+var_230]
0x140003903  lea     rcx, ds:0[rax*4]
0x14000390b  test    rcx, rcx
0x14000390e  jz      short loc_140003955
0x140003910  mov     [rdi], rcx
0x140003913  mov     eax, [rcx]
0x140003915  inc     eax
0x140003917  mov     [rcx], eax
0x140003919  lea     rcx, [rsp+270h+var_238]
0x14000391e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003923  xor     ebx, ebx
0x140003925  lea     rcx, [rsp+270h+var_240]
0x14000392a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000392f  mov     eax, ebx
0x140003931  mov     rcx, [rbp+170h+var_10]
0x140003938  xor     rcx, rsp; StackCookie
0x14000393b  call    __security_check_cookie
0x140003940  lea     r11, [rsp+270h+var_s0]
0x140003948  mov     rbx, [r11+20h]
0x14000394c  mov     rdi, [r11+28h]
0x140003950  mov     rsp, r11
0x140003953  pop     rbp
0x140003954  retn
0x140003955  mov     r8, rdi
0x140003958  lea     rdx, [rsp+270h+var_240]
0x14000395d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003962  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140003967  mov     ebx, eax
0x140003969  test    eax, eax
0x14000396b  jns     short loc_140003919
0x14000396d  mov     r9d, eax
0x140003970  mov     edx, 137h
0x140003975  jmp     loc_1400038DF
```
