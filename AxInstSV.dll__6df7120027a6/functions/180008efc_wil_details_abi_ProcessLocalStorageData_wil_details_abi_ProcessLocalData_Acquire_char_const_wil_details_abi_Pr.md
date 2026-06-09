# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008efc`
- end: `0x18000905b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b800`

## callees

- `0x180001720`
- `0x180005b78`
- `0x1800087c4`
- `0x1800087e0`
- `0x180008efc`
- `0x18000b514`
- `0x18000cd94`
- `0x18000f0cc`
- `0x180010278`
- `0x180010f14`
- `0x180011280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008f79`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008f79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f34`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v13,
      &v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180008efc  mov     [rsp-8+arg_10], rbx
0x180008f01  mov     [rsp-8+arg_18], rdi
0x180008f06  push    rbp
0x180008f07  lea     rbp, [rsp-170h]
0x180008f0f  sub     rsp, 270h
0x180008f16  mov     rax, cs:__security_cookie
0x180008f1d  xor     rax, rsp
0x180008f20  mov     [rbp+170h+var_10], rax
0x180008f27  mov     rdi, rdx
0x180008f2a  mov     qword ptr [rdx], 0
0x180008f31  mov     rbx, rcx
0x180008f34  call    cs:__imp_GetCurrentProcessId
0x180008f3a  mov     [rsp+270h+var_248], rbx
0x180008f3f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008f46  mov     r9d, eax
0x180008f49  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180008f51  mov     edx, 104h; unsigned __int64
0x180008f56  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008f5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008f60  mov     r9d, 1F0001h; dwDesiredAccess
0x180008f66  mov     [rsp+270h+var_240], 0
0x180008f6f  xor     r8d, r8d; dwFlags
0x180008f72  lea     rdx, [rsp+270h+Name]; lpName
0x180008f77  xor     ecx, ecx; lpMutexAttributes
0x180008f79  call    cs:__imp_CreateMutexExW
0x180008f7f  mov     rdx, rax
0x180008f82  lea     rcx, [rsp+270h+var_240]
0x180008f87  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008f8c  cmp     [rsp+270h+var_240], 0
0x180008f92  jnz     short loc_180008F9D
0x180008f94  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008f99  mov     ebx, eax
0x180008f9b  jmp     short loc_180009009
0x180008f9d  lea     rdx, [rsp+270h+var_238]
0x180008fa2  lea     rcx, [rsp+270h+var_240]
0x180008fa7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008fac  lea     rdx, [rsp+270h+var_230]; void **
0x180008fb1  mov     [rsp+270h+var_230], 0
0x180008fba  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008fbf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008fc4  mov     ebx, eax
0x180008fc6  test    eax, eax
0x180008fc8  jns     short loc_180008FEA
0x180008fca  mov     edx, 12Eh; void *
0x180008fcf  mov     rcx, [rbp+178h]; this
0x180008fd6  mov     r9d, eax; char *
0x180008fd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fde  lea     rcx, [rsp+270h+var_238]
0x180008fe3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008fe8  jmp     short loc_180009009
0x180008fea  mov     rcx, [rsp+270h+var_230]
0x180008fef  test    rcx, rcx
0x180008ff2  jz      short loc_180009039
0x180008ff4  mov     [rdi], rcx
0x180008ff7  mov     eax, [rcx]
0x180008ff9  inc     eax
0x180008ffb  mov     [rcx], eax
0x180008ffd  lea     rcx, [rsp+270h+var_238]
0x180009002  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009007  xor     ebx, ebx
0x180009009  lea     rcx, [rsp+270h+var_240]
0x18000900e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009013  mov     eax, ebx
0x180009015  mov     rcx, [rbp+170h+var_10]
0x18000901c  xor     rcx, rsp; StackCookie
0x18000901f  call    __security_check_cookie
0x180009024  lea     r11, [rsp+270h+var_s0]
0x18000902c  mov     rbx, [r11+20h]
0x180009030  mov     rdi, [r11+28h]
0x180009034  mov     rsp, r11
0x180009037  pop     rbp
0x180009038  retn
0x180009039  mov     r8, rdi
0x18000903c  lea     rdx, [rsp+270h+var_240]
0x180009041  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009046  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000904b  mov     ebx, eax
0x18000904d  test    eax, eax
0x18000904f  jns     short loc_180008FFD
0x180009051  mov     edx, 137h
0x180009056  jmp     loc_180008FCF
```
