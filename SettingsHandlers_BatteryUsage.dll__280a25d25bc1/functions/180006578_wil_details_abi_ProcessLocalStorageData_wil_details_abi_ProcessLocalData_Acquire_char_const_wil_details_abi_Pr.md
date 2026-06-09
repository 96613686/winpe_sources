# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006578`
- end: `0x1800066de`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007d1c`

## callees

- `0x1800028d0`
- `0x1800060f4`
- `0x180006110`
- `0x180006578`
- `0x1800079a8`
- `0x18000878c`
- `0x18000a13c`
- `0x18000a8fc`
- `0x18000ad6c`
- `0x18000b78c`
- `0x18000bab8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065b0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800065f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800065f5`

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
0x180006578  mov     [rsp-8+arg_10], rbx
0x18000657d  mov     [rsp-8+arg_18], rdi
0x180006582  push    rbp
0x180006583  lea     rbp, [rsp-170h]
0x18000658b  sub     rsp, 270h
0x180006592  mov     rax, cs:__security_cookie
0x180006599  xor     rax, rsp
0x18000659c  mov     [rbp+170h+var_10], rax
0x1800065a3  mov     rdi, rdx
0x1800065a6  mov     qword ptr [rdx], 0
0x1800065ad  mov     rbx, rcx
0x1800065b0  call    cs:__imp_GetCurrentProcessId
0x1800065b6  mov     [rsp+270h+var_248], rbx
0x1800065bb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800065c2  mov     r9d, eax
0x1800065c5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800065cd  mov     edx, 104h; unsigned __int64
0x1800065d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800065d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800065dc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800065e2  mov     [rsp+270h+var_240], 0
0x1800065eb  xor     r8d, r8d; dwFlags
0x1800065ee  lea     rdx, [rsp+270h+Name]; lpName
0x1800065f3  xor     ecx, ecx; lpMutexAttributes
0x1800065f5  call    cs:__imp_CreateMutexExW
0x1800065fb  mov     rdx, rax
0x1800065fe  lea     rcx, [rsp+270h+var_240]
0x180006603  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006608  cmp     [rsp+270h+var_240], 0
0x18000660e  jnz     short loc_180006619
0x180006610  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006615  mov     ebx, eax
0x180006617  jmp     short loc_18000668C
0x180006619  lea     rdx, [rsp+270h+var_238]
0x18000661e  lea     rcx, [rsp+270h+var_240]
0x180006623  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006628  lea     rdx, [rsp+270h+var_230]; void **
0x18000662d  mov     [rsp+270h+var_230], 0
0x180006636  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000663b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180006640  mov     ebx, eax
0x180006642  test    eax, eax
0x180006644  jns     short loc_18000666D
0x180006646  mov     edx, 12Eh; void *
0x18000664b  mov     rcx, [rbp+178h]; this
0x180006652  lea     r8, aWil; "wil"
0x180006659  mov     r9d, eax; char *
0x18000665c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006661  lea     rcx, [rsp+270h+var_238]
0x180006666  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000666b  jmp     short loc_18000668C
0x18000666d  mov     rcx, [rsp+270h+var_230]
0x180006672  test    rcx, rcx
0x180006675  jz      short loc_1800066BC
0x180006677  mov     [rdi], rcx
0x18000667a  mov     eax, [rcx]
0x18000667c  inc     eax
0x18000667e  mov     [rcx], eax
0x180006680  lea     rcx, [rsp+270h+var_238]
0x180006685  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000668a  xor     ebx, ebx
0x18000668c  lea     rcx, [rsp+270h+var_240]
0x180006691  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006696  mov     eax, ebx
0x180006698  mov     rcx, [rbp+170h+var_10]
0x18000669f  xor     rcx, rsp; StackCookie
0x1800066a2  call    __security_check_cookie
0x1800066a7  lea     r11, [rsp+270h+var_s0]
0x1800066af  mov     rbx, [r11+20h]
0x1800066b3  mov     rdi, [r11+28h]
0x1800066b7  mov     rsp, r11
0x1800066ba  pop     rbp
0x1800066bb  retn
0x1800066bc  mov     r8, rdi
0x1800066bf  lea     rdx, [rsp+270h+var_240]
0x1800066c4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800066c9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800066ce  mov     ebx, eax
0x1800066d0  test    eax, eax
0x1800066d2  jns     short loc_180006680
0x1800066d4  mov     edx, 137h
0x1800066d9  jmp     loc_18000664B
```
