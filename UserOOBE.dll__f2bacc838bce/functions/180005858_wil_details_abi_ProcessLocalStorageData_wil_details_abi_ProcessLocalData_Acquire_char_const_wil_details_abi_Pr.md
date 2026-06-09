# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005858`
- end: `0x1800059be`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800063d0`

## callees

- `0x1800032b0`
- `0x1800056c8`
- `0x1800056e4`
- `0x180005858`
- `0x1800060e8`
- `0x180006b2c`
- `0x180007134`
- `0x180007710`
- `0x1800078bc`
- `0x180007d40`
- `0x180007e34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800058d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800058d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005890`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005890`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180005858  mov     [rsp-8+arg_10], rbx
0x18000585d  mov     [rsp-8+arg_18], rdi
0x180005862  push    rbp
0x180005863  lea     rbp, [rsp-170h]
0x18000586b  sub     rsp, 270h
0x180005872  mov     rax, cs:__security_cookie
0x180005879  xor     rax, rsp
0x18000587c  mov     [rbp+170h+var_10], rax
0x180005883  mov     rdi, rdx
0x180005886  mov     qword ptr [rdx], 0
0x18000588d  mov     rbx, rcx
0x180005890  call    cs:__imp_GetCurrentProcessId
0x180005896  mov     [rsp+270h+var_248], rbx
0x18000589b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800058a2  mov     r9d, eax
0x1800058a5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800058ad  mov     edx, 104h; unsigned __int64
0x1800058b2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800058b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800058bc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800058c2  mov     [rsp+270h+var_240], 0
0x1800058cb  xor     r8d, r8d; dwFlags
0x1800058ce  lea     rdx, [rsp+270h+Name]; lpName
0x1800058d3  xor     ecx, ecx; lpMutexAttributes
0x1800058d5  call    cs:__imp_CreateMutexExW
0x1800058db  mov     rdx, rax
0x1800058de  lea     rcx, [rsp+270h+var_240]
0x1800058e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800058e8  cmp     [rsp+270h+var_240], 0
0x1800058ee  jnz     short loc_1800058F9
0x1800058f0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800058f5  mov     ebx, eax
0x1800058f7  jmp     short loc_18000596C
0x1800058f9  lea     rdx, [rsp+270h+var_238]
0x1800058fe  lea     rcx, [rsp+270h+var_240]
0x180005903  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005908  lea     rdx, [rsp+270h+var_230]; void **
0x18000590d  mov     [rsp+270h+var_230], 0
0x180005916  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000591b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005920  mov     ebx, eax
0x180005922  test    eax, eax
0x180005924  jns     short loc_18000594D
0x180005926  mov     edx, 12Eh; void *
0x18000592b  mov     rcx, [rbp+178h]; this
0x180005932  lea     r8, aWil; "wil"
0x180005939  mov     r9d, eax; char *
0x18000593c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005941  lea     rcx, [rsp+270h+var_238]
0x180005946  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000594b  jmp     short loc_18000596C
0x18000594d  mov     rcx, [rsp+270h+var_230]
0x180005952  test    rcx, rcx
0x180005955  jz      short loc_18000599C
0x180005957  mov     [rdi], rcx
0x18000595a  mov     eax, [rcx]
0x18000595c  inc     eax
0x18000595e  mov     [rcx], eax
0x180005960  lea     rcx, [rsp+270h+var_238]
0x180005965  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000596a  xor     ebx, ebx
0x18000596c  lea     rcx, [rsp+270h+var_240]
0x180005971  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005976  mov     eax, ebx
0x180005978  mov     rcx, [rbp+170h+var_10]
0x18000597f  xor     rcx, rsp; StackCookie
0x180005982  call    __security_check_cookie
0x180005987  lea     r11, [rsp+270h+var_s0]
0x18000598f  mov     rbx, [r11+20h]
0x180005993  mov     rdi, [r11+28h]
0x180005997  mov     rsp, r11
0x18000599a  pop     rbp
0x18000599b  retn
0x18000599c  mov     r8, rdi
0x18000599f  lea     rdx, [rsp+270h+var_240]
0x1800059a4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800059a9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800059ae  mov     ebx, eax
0x1800059b0  test    eax, eax
0x1800059b2  jns     short loc_180005960
0x1800059b4  mov     edx, 137h
0x1800059b9  jmp     loc_18000592B
```
