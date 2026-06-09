# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140005464`
- end: `0x1400055ca`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140006510`

## callees

- `0x140002ce0`
- `0x1400031b0`
- `0x140004f08`
- `0x140004f24`
- `0x140005464`
- `0x140006360`
- `0x140006f70`
- `0x140008a78`
- `0x140008e08`
- `0x1400095d4`
- `0x1400098b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400054e1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400054e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000549c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000549c`

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
0x140005464  mov     [rsp-8+arg_10], rbx
0x140005469  mov     [rsp-8+arg_18], rdi
0x14000546e  push    rbp
0x14000546f  lea     rbp, [rsp-170h]
0x140005477  sub     rsp, 270h
0x14000547e  mov     rax, cs:__security_cookie
0x140005485  xor     rax, rsp
0x140005488  mov     [rbp+170h+var_10], rax
0x14000548f  mov     rdi, rdx
0x140005492  mov     qword ptr [rdx], 0
0x140005499  mov     rbx, rcx
0x14000549c  call    cs:__imp_GetCurrentProcessId
0x1400054a2  mov     [rsp+270h+var_248], rbx
0x1400054a7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400054ae  mov     r9d, eax
0x1400054b1  mov     [rsp+270h+var_250], 130h; int
0x1400054b9  mov     edx, 104h; unsigned __int64
0x1400054be  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400054c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400054c8  mov     r9d, 1F0001h; dwDesiredAccess
0x1400054ce  mov     [rsp+270h+var_240], 0
0x1400054d7  xor     r8d, r8d; dwFlags
0x1400054da  lea     rdx, [rsp+270h+Name]; lpName
0x1400054df  xor     ecx, ecx; lpMutexAttributes
0x1400054e1  call    cs:__imp_CreateMutexExW
0x1400054e7  mov     rdx, rax
0x1400054ea  lea     rcx, [rsp+270h+var_240]
0x1400054ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400054f4  cmp     [rsp+270h+var_240], 0
0x1400054fa  jnz     short loc_140005505
0x1400054fc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005501  mov     ebx, eax
0x140005503  jmp     short loc_140005578
0x140005505  lea     rdx, [rsp+270h+var_238]
0x14000550a  lea     rcx, [rsp+270h+var_240]
0x14000550f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140005514  lea     rdx, [rsp+270h+var_230]; void **
0x140005519  mov     [rsp+270h+var_230], 0
0x140005522  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140005527  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x14000552c  mov     ebx, eax
0x14000552e  test    eax, eax
0x140005530  jns     short loc_140005559
0x140005532  mov     edx, 12Eh; void *
0x140005537  mov     rcx, [rbp+178h]; this
0x14000553e  lea     r8, aWil; "wil"
0x140005545  mov     r9d, eax; char *
0x140005548  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000554d  lea     rcx, [rsp+270h+var_238]
0x140005552  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005557  jmp     short loc_140005578
0x140005559  mov     rcx, [rsp+270h+var_230]
0x14000555e  test    rcx, rcx
0x140005561  jz      short loc_1400055A8
0x140005563  mov     [rdi], rcx
0x140005566  mov     eax, [rcx]
0x140005568  inc     eax
0x14000556a  mov     [rcx], eax
0x14000556c  lea     rcx, [rsp+270h+var_238]
0x140005571  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005576  xor     ebx, ebx
0x140005578  lea     rcx, [rsp+270h+var_240]
0x14000557d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005582  mov     eax, ebx
0x140005584  mov     rcx, [rbp+170h+var_10]
0x14000558b  xor     rcx, rsp; StackCookie
0x14000558e  call    __security_check_cookie
0x140005593  lea     r11, [rsp+270h+var_s0]
0x14000559b  mov     rbx, [r11+20h]
0x14000559f  mov     rdi, [r11+28h]
0x1400055a3  mov     rsp, r11
0x1400055a6  pop     rbp
0x1400055a7  retn
0x1400055a8  mov     r8, rdi
0x1400055ab  lea     rdx, [rsp+270h+var_240]
0x1400055b0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400055b5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400055ba  mov     ebx, eax
0x1400055bc  test    eax, eax
0x1400055be  jns     short loc_14000556C
0x1400055c0  mov     edx, 137h
0x1400055c5  jmp     loc_140005537
```
