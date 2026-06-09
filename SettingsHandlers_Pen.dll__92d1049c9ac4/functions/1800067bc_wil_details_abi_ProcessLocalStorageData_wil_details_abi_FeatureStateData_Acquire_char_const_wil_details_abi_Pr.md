# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800067bc`
- end: `0x180006922`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007b60`

## callees

- `0x1800030e0`
- `0x180005f64`
- `0x180005f80`
- `0x1800067bc`
- `0x180007808`
- `0x180008970`
- `0x18000a2bc`
- `0x18000ac78`
- `0x18000b1fc`
- `0x18000bb94`
- `0x18000bec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006839`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006839`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800067f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800067f4`

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
0x1800067bc  mov     [rsp-8+arg_10], rbx
0x1800067c1  mov     [rsp-8+arg_18], rdi
0x1800067c6  push    rbp
0x1800067c7  lea     rbp, [rsp-170h]
0x1800067cf  sub     rsp, 270h
0x1800067d6  mov     rax, cs:__security_cookie
0x1800067dd  xor     rax, rsp
0x1800067e0  mov     [rbp+170h+var_10], rax
0x1800067e7  mov     rdi, rdx
0x1800067ea  mov     qword ptr [rdx], 0
0x1800067f1  mov     rbx, rcx
0x1800067f4  call    cs:__imp_GetCurrentProcessId
0x1800067fa  mov     [rsp+270h+var_248], rbx
0x1800067ff  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006806  mov     r9d, eax
0x180006809  mov     [rsp+270h+var_250], 130h; int
0x180006811  mov     edx, 104h; unsigned __int64
0x180006816  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000681b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006820  mov     r9d, 1F0001h; dwDesiredAccess
0x180006826  mov     [rsp+270h+var_240], 0
0x18000682f  xor     r8d, r8d; dwFlags
0x180006832  lea     rdx, [rsp+270h+Name]; lpName
0x180006837  xor     ecx, ecx; lpMutexAttributes
0x180006839  call    cs:__imp_CreateMutexExW
0x18000683f  mov     rdx, rax
0x180006842  lea     rcx, [rsp+270h+var_240]
0x180006847  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000684c  cmp     [rsp+270h+var_240], 0
0x180006852  jnz     short loc_18000685D
0x180006854  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006859  mov     ebx, eax
0x18000685b  jmp     short loc_1800068D0
0x18000685d  lea     rdx, [rsp+270h+var_238]
0x180006862  lea     rcx, [rsp+270h+var_240]
0x180006867  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000686c  lea     rdx, [rsp+270h+var_230]; void **
0x180006871  mov     [rsp+270h+var_230], 0
0x18000687a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000687f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180006884  mov     ebx, eax
0x180006886  test    eax, eax
0x180006888  jns     short loc_1800068B1
0x18000688a  mov     edx, 12Eh; void *
0x18000688f  mov     rcx, [rbp+178h]; this
0x180006896  lea     r8, aWil; "wil"
0x18000689d  mov     r9d, eax; char *
0x1800068a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800068a5  lea     rcx, [rsp+270h+var_238]
0x1800068aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800068af  jmp     short loc_1800068D0
0x1800068b1  mov     rcx, [rsp+270h+var_230]
0x1800068b6  test    rcx, rcx
0x1800068b9  jz      short loc_180006900
0x1800068bb  mov     [rdi], rcx
0x1800068be  mov     eax, [rcx]
0x1800068c0  inc     eax
0x1800068c2  mov     [rcx], eax
0x1800068c4  lea     rcx, [rsp+270h+var_238]
0x1800068c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800068ce  xor     ebx, ebx
0x1800068d0  lea     rcx, [rsp+270h+var_240]
0x1800068d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800068da  mov     eax, ebx
0x1800068dc  mov     rcx, [rbp+170h+var_10]
0x1800068e3  xor     rcx, rsp; StackCookie
0x1800068e6  call    __security_check_cookie
0x1800068eb  lea     r11, [rsp+270h+var_s0]
0x1800068f3  mov     rbx, [r11+20h]
0x1800068f7  mov     rdi, [r11+28h]
0x1800068fb  mov     rsp, r11
0x1800068fe  pop     rbp
0x1800068ff  retn
0x180006900  mov     r8, rdi
0x180006903  lea     rdx, [rsp+270h+var_240]
0x180006908  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000690d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006912  mov     ebx, eax
0x180006914  test    eax, eax
0x180006916  jns     short loc_1800068C4
0x180006918  mov     edx, 137h
0x18000691d  jmp     loc_18000688F
```
