# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14001421c`
- end: `0x140014382`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140015ef4`

## callees

- `0x140002d30`
- `0x140007fc8`
- `0x140007fe4`
- `0x14000bb58`
- `0x14000e030`
- `0x14000ffdc`
- `0x1400103ec`
- `0x140010ef0`
- `0x140011278`
- `0x14001421c`
- `0x14001650c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140014299`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140014299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140014254`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140014254`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x14001421c  mov     [rsp-8+arg_10], rbx
0x140014221  mov     [rsp-8+arg_18], rdi
0x140014226  push    rbp
0x140014227  lea     rbp, [rsp-170h]
0x14001422f  sub     rsp, 270h
0x140014236  mov     rax, cs:__security_cookie
0x14001423d  xor     rax, rsp
0x140014240  mov     [rbp+170h+var_10], rax
0x140014247  mov     rdi, rdx
0x14001424a  mov     qword ptr [rdx], 0
0x140014251  mov     rbx, rcx
0x140014254  call    cs:__imp_GetCurrentProcessId
0x14001425a  mov     [rsp+270h+var_248], rbx
0x14001425f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140014266  mov     r9d, eax
0x140014269  mov     [rsp+270h+var_250], 130h; int
0x140014271  mov     edx, 104h; unsigned __int64
0x140014276  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14001427b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014280  mov     r9d, 1F0001h; dwDesiredAccess
0x140014286  mov     [rsp+270h+var_240], 0
0x14001428f  xor     r8d, r8d; dwFlags
0x140014292  lea     rdx, [rsp+270h+Name]; lpName
0x140014297  xor     ecx, ecx; lpMutexAttributes
0x140014299  call    cs:__imp_CreateMutexExW
0x14001429f  mov     rdx, rax
0x1400142a2  lea     rcx, [rsp+270h+var_240]
0x1400142a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400142ac  cmp     [rsp+270h+var_240], 0
0x1400142b2  jnz     short loc_1400142BD
0x1400142b4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400142b9  mov     ebx, eax
0x1400142bb  jmp     short loc_140014330
0x1400142bd  lea     rdx, [rsp+270h+var_238]
0x1400142c2  lea     rcx, [rsp+270h+var_240]
0x1400142c7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400142cc  lea     rdx, [rsp+270h+var_230]; void **
0x1400142d1  mov     [rsp+270h+var_230], 0
0x1400142da  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400142df  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1400142e4  mov     ebx, eax
0x1400142e6  test    eax, eax
0x1400142e8  jns     short loc_140014311
0x1400142ea  mov     edx, 12Eh; void *
0x1400142ef  mov     rcx, [rbp+178h]; this
0x1400142f6  lea     r8, aWil; "wil"
0x1400142fd  mov     r9d, eax; char *
0x140014300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014305  lea     rcx, [rsp+270h+var_238]
0x14001430a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001430f  jmp     short loc_140014330
0x140014311  mov     rcx, [rsp+270h+var_230]
0x140014316  test    rcx, rcx
0x140014319  jz      short loc_140014360
0x14001431b  mov     [rdi], rcx
0x14001431e  mov     eax, [rcx]
0x140014320  inc     eax
0x140014322  mov     [rcx], eax
0x140014324  lea     rcx, [rsp+270h+var_238]
0x140014329  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001432e  xor     ebx, ebx
0x140014330  lea     rcx, [rsp+270h+var_240]
0x140014335  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001433a  mov     eax, ebx
0x14001433c  mov     rcx, [rbp+170h+var_10]
0x140014343  xor     rcx, rsp; StackCookie
0x140014346  call    __security_check_cookie
0x14001434b  lea     r11, [rsp+270h+var_s0]
0x140014353  mov     rbx, [r11+20h]
0x140014357  mov     rdi, [r11+28h]
0x14001435b  mov     rsp, r11
0x14001435e  pop     rbp
0x14001435f  retn
0x140014360  mov     r8, rdi
0x140014363  lea     rdx, [rsp+270h+var_240]
0x140014368  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14001436d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140014372  mov     ebx, eax
0x140014374  test    eax, eax
0x140014376  jns     short loc_140014324
0x140014378  mov     edx, 137h
0x14001437d  jmp     loc_1400142EF
```
