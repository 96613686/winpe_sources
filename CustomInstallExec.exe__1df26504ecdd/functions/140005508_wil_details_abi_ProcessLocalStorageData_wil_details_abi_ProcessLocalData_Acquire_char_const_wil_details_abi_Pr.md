# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140005508`
- end: `0x1400056b2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140005f54`

## callees

- `0x1400033b0`
- `0x1400053c0`
- `0x1400053dc`
- `0x140005508`
- `0x140005d98`
- `0x1400067b0`
- `0x140006c24`
- `0x140007178`
- `0x140007338`
- `0x140007780`
- `0x140007884`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140005585`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140005585`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005540`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005540`

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
0x140005508  mov     [rsp-8+arg_10], rbx
0x14000550d  mov     [rsp-8+arg_18], rdi
0x140005512  push    rbp
0x140005513  lea     rbp, [rsp-170h]
0x14000551b  sub     rsp, 270h
0x140005522  mov     rax, cs:__security_cookie
0x140005529  xor     rax, rsp
0x14000552c  mov     [rbp+170h+var_10], rax
0x140005533  mov     rdi, rdx
0x140005536  mov     qword ptr [rdx], 0
0x14000553d  mov     rbx, rcx
0x140005540  call    cs:__imp_GetCurrentProcessId
0x140005546  mov     [rsp+270h+var_248], rbx
0x14000554b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140005552  mov     r9d, eax
0x140005555  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x14000555d  mov     edx, 104h; unsigned __int64
0x140005562  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140005567  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000556c  mov     r9d, 1F0001h; dwDesiredAccess
0x140005572  mov     [rsp+270h+var_240], 0
0x14000557b  xor     r8d, r8d; dwFlags
0x14000557e  lea     rdx, [rsp+270h+Name]; lpName
0x140005583  xor     ecx, ecx; lpMutexAttributes
0x140005585  call    cs:__imp_CreateMutexExW
0x14000558b  mov     rdx, rax
0x14000558e  lea     rcx, [rsp+270h+var_240]
0x140005593  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140005598  cmp     [rsp+270h+var_240], 0
0x14000559e  jnz     short loc_1400055AC
0x1400055a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400055a5  mov     ebx, eax
0x1400055a7  jmp     loc_14000565D
0x1400055ac  lea     rdx, [rsp+270h+var_238]
0x1400055b1  lea     rcx, [rsp+270h+var_240]
0x1400055b6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400055bb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1400055c0  mov     [rsp+270h+var_230], 0
0x1400055c9  lea     rcx, [rsp+270h+Name]; pszSrc
0x1400055ce  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400055d3  mov     ebx, eax
0x1400055d5  test    eax, eax
0x1400055d7  jns     short loc_140005636
0x1400055d9  mov     rcx, [rbp+178h]; this
0x1400055e0  lea     r8, aWil; "wil"
0x1400055e7  mov     r9d, eax; char *
0x1400055ea  mov     edx, 66h ; 'f'; void *
0x1400055ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400055f4  mov     rcx, [rbp+178h]; this
0x1400055fb  lea     r8, aWil; "wil"
0x140005602  mov     r9d, ebx; char *
0x140005605  mov     edx, 6Fh ; 'o'; void *
0x14000560a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000560f  mov     r9d, ebx; char *
0x140005612  mov     edx, 12Eh; void *
0x140005617  mov     rcx, [rbp+178h]; this
0x14000561e  lea     r8, aWil; "wil"
0x140005625  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000562a  lea     rcx, [rsp+270h+var_238]
0x14000562f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005634  jmp     short loc_14000565D
0x140005636  mov     rax, [rsp+270h+var_230]
0x14000563b  lea     rcx, ds:0[rax*4]
0x140005643  test    rcx, rcx
0x140005646  jz      short loc_14000568D
0x140005648  mov     [rdi], rcx
0x14000564b  mov     eax, [rcx]
0x14000564d  inc     eax
0x14000564f  mov     [rcx], eax
0x140005651  lea     rcx, [rsp+270h+var_238]
0x140005656  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000565b  xor     ebx, ebx
0x14000565d  lea     rcx, [rsp+270h+var_240]
0x140005662  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005667  mov     eax, ebx
0x140005669  mov     rcx, [rbp+170h+var_10]
0x140005670  xor     rcx, rsp; StackCookie
0x140005673  call    __security_check_cookie
0x140005678  lea     r11, [rsp+270h+var_s0]
0x140005680  mov     rbx, [r11+20h]
0x140005684  mov     rdi, [r11+28h]
0x140005688  mov     rsp, r11
0x14000568b  pop     rbp
0x14000568c  retn
0x14000568d  mov     r8, rdi
0x140005690  lea     rdx, [rsp+270h+var_240]
0x140005695  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000569a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000569f  mov     ebx, eax
0x1400056a1  test    eax, eax
0x1400056a3  jns     short loc_140005651
0x1400056a5  mov     r9d, eax
0x1400056a8  mov     edx, 137h
0x1400056ad  jmp     loc_140005617
```
