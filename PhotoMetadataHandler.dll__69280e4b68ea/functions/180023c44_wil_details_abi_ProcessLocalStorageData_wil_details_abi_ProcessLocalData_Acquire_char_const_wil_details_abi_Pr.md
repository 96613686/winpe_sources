# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180023c44`
- end: `0x180023da9`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024b98`

## callees

- `0x1800089f0`
- `0x18001595c`
- `0x180015c10`
- `0x180015d84`
- `0x180016a40`
- `0x18001773c`
- `0x180023a64`
- `0x180023a84`
- `0x180023c44`
- `0x1800265f0`
- `0x180026da4`
- `0x180026f98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023cc0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023cc0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId_0; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId_0 = GetCurrentProcessId_0();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId_0);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180023c44  mov     [rsp-8+arg_10], rbx
0x180023c49  mov     [rsp-8+arg_18], rdi
0x180023c4e  push    rbp
0x180023c4f  lea     rbp, [rsp-170h]
0x180023c57  sub     rsp, 270h
0x180023c5e  mov     rax, cs:__security_cookie
0x180023c65  xor     rax, rsp
0x180023c68  mov     [rbp+170h+var_10], rax
0x180023c6f  mov     rdi, rdx
0x180023c72  mov     qword ptr [rdx], 0
0x180023c79  mov     rbx, rcx
0x180023c7c  call    GetCurrentProcessId_0
0x180023c81  mov     r9d, eax
0x180023c84  mov     [rsp+270h+var_248], rbx
0x180023c89  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180023c90  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180023c98  mov     edx, 104h; unsigned __int64
0x180023c9d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023ca2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023ca7  mov     r9d, 1F0001h; dwDesiredAccess
0x180023cad  mov     [rsp+270h+var_240], 0
0x180023cb6  xor     r8d, r8d; dwFlags
0x180023cb9  lea     rdx, [rsp+270h+Name]; lpName
0x180023cbe  xor     ecx, ecx; lpMutexAttributes
0x180023cc0  call    cs:__imp_CreateMutexExW
0x180023cc7  nop     dword ptr [rax+rax+00h]
0x180023ccc  mov     rdx, rax
0x180023ccf  lea     rcx, [rsp+270h+var_240]
0x180023cd4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180023cd9  cmp     [rsp+270h+var_240], 0
0x180023cdf  jnz     short loc_180023CEA
0x180023ce1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023ce6  mov     ebx, eax
0x180023ce8  jmp     short loc_180023D56
0x180023cea  lea     rdx, [rsp+270h+var_238]
0x180023cef  lea     rcx, [rsp+270h+var_240]
0x180023cf4  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180023cf9  lea     rdx, [rsp+270h+var_230]; void **
0x180023cfe  mov     [rsp+270h+var_230], 0
0x180023d07  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023d0c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180023d11  mov     ebx, eax
0x180023d13  test    eax, eax
0x180023d15  jns     short loc_180023D37
0x180023d17  mov     edx, 12Eh; void *
0x180023d1c  mov     rcx, [rbp+178h]; this
0x180023d23  mov     r9d, eax; char *
0x180023d26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d2b  lea     rcx, [rsp+270h+var_238]
0x180023d30  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023d35  jmp     short loc_180023D56
0x180023d37  mov     rcx, [rsp+270h+var_230]
0x180023d3c  test    rcx, rcx
0x180023d3f  jz      short loc_180023D87
0x180023d41  mov     [rdi], rcx
0x180023d44  mov     eax, [rcx]
0x180023d46  inc     eax
0x180023d48  mov     [rcx], eax
0x180023d4a  lea     rcx, [rsp+270h+var_238]
0x180023d4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023d54  xor     ebx, ebx
0x180023d56  lea     rcx, [rsp+270h+var_240]
0x180023d5b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023d60  mov     eax, ebx
0x180023d62  mov     rcx, [rbp+170h+var_10]
0x180023d69  xor     rcx, rsp; StackCookie
0x180023d6c  call    __security_check_cookie
0x180023d71  lea     r11, [rsp+270h+var_s0]
0x180023d79  mov     rbx, [r11+20h]
0x180023d7d  mov     rdi, [r11+28h]
0x180023d81  mov     rsp, r11
0x180023d84  pop     rbp
0x180023d85  retn
0x180023d87  mov     r8, rdi
0x180023d8a  lea     rdx, [rsp+270h+var_240]
0x180023d8f  lea     rcx, [rsp+270h+Name]
0x180023d94  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180023d99  mov     ebx, eax
0x180023d9b  test    eax, eax
0x180023d9d  jns     short loc_180023D4A
0x180023d9f  mov     edx, 137h
0x180023da4  jmp     loc_180023D1C
```
