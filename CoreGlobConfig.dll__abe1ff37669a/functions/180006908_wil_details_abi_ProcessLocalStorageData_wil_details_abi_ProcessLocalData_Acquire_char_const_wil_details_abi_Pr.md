# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006908`
- end: `0x180006a6e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007560`

## callees

- `0x180002380`
- `0x1800067a4`
- `0x1800067c0`
- `0x180006908`
- `0x1800071b8`
- `0x180007c68`
- `0x180008294`
- `0x1800088b4`
- `0x180008a68`
- `0x180008ef0`
- `0x180008fec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006985`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006940`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006940`

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
0x180006908  mov     [rsp-8+arg_10], rbx
0x18000690d  mov     [rsp-8+arg_18], rdi
0x180006912  push    rbp
0x180006913  lea     rbp, [rsp-170h]
0x18000691b  sub     rsp, 270h
0x180006922  mov     rax, cs:__security_cookie
0x180006929  xor     rax, rsp
0x18000692c  mov     [rbp+170h+var_10], rax
0x180006933  mov     rdi, rdx
0x180006936  mov     qword ptr [rdx], 0
0x18000693d  mov     rbx, rcx
0x180006940  call    cs:__imp_GetCurrentProcessId
0x180006946  mov     [rsp+270h+var_248], rbx
0x18000694b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006952  mov     r9d, eax
0x180006955  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000695d  mov     edx, 104h; unsigned __int64
0x180006962  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006967  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000696c  mov     r9d, 1F0001h; dwDesiredAccess
0x180006972  mov     [rsp+270h+var_240], 0
0x18000697b  xor     r8d, r8d; dwFlags
0x18000697e  lea     rdx, [rsp+270h+Name]; lpName
0x180006983  xor     ecx, ecx; lpMutexAttributes
0x180006985  call    cs:__imp_CreateMutexExW
0x18000698b  mov     rdx, rax
0x18000698e  lea     rcx, [rsp+270h+var_240]
0x180006993  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006998  cmp     [rsp+270h+var_240], 0
0x18000699e  jnz     short loc_1800069A9
0x1800069a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800069a5  mov     ebx, eax
0x1800069a7  jmp     short loc_180006A1C
0x1800069a9  lea     rdx, [rsp+270h+var_238]
0x1800069ae  lea     rcx, [rsp+270h+var_240]
0x1800069b3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800069b8  lea     rdx, [rsp+270h+var_230]; void **
0x1800069bd  mov     [rsp+270h+var_230], 0
0x1800069c6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800069cb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800069d0  mov     ebx, eax
0x1800069d2  test    eax, eax
0x1800069d4  jns     short loc_1800069FD
0x1800069d6  mov     edx, 12Eh; void *
0x1800069db  mov     rcx, [rbp+178h]; this
0x1800069e2  lea     r8, aWil; "wil"
0x1800069e9  mov     r9d, eax; char *
0x1800069ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069f1  lea     rcx, [rsp+270h+var_238]
0x1800069f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800069fb  jmp     short loc_180006A1C
0x1800069fd  mov     rcx, [rsp+270h+var_230]
0x180006a02  test    rcx, rcx
0x180006a05  jz      short loc_180006A4C
0x180006a07  mov     [rdi], rcx
0x180006a0a  mov     eax, [rcx]
0x180006a0c  inc     eax
0x180006a0e  mov     [rcx], eax
0x180006a10  lea     rcx, [rsp+270h+var_238]
0x180006a15  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a1a  xor     ebx, ebx
0x180006a1c  lea     rcx, [rsp+270h+var_240]
0x180006a21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a26  mov     eax, ebx
0x180006a28  mov     rcx, [rbp+170h+var_10]
0x180006a2f  xor     rcx, rsp; StackCookie
0x180006a32  call    __security_check_cookie
0x180006a37  lea     r11, [rsp+270h+var_s0]
0x180006a3f  mov     rbx, [r11+20h]
0x180006a43  mov     rdi, [r11+28h]
0x180006a47  mov     rsp, r11
0x180006a4a  pop     rbp
0x180006a4b  retn
0x180006a4c  mov     r8, rdi
0x180006a4f  lea     rdx, [rsp+270h+var_240]
0x180006a54  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006a59  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006a5e  mov     ebx, eax
0x180006a60  test    eax, eax
0x180006a62  jns     short loc_180006A10
0x180006a64  mov     edx, 137h
0x180006a69  jmp     loc_1800069DB
```
