# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180010a1c`
- end: `0x180010b82`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180011024`

## callees

- `0x180002dc0`
- `0x180005d00`
- `0x180005d1c`
- `0x180006b08`
- `0x180007d74`
- `0x18000831c`
- `0x1800085b8`
- `0x180008b34`
- `0x1800093bc`
- `0x180010a1c`
- `0x180011344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010a99`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010a99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010a54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010a54`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180010a1c  mov     [rsp-8+arg_10], rbx
0x180010a21  mov     [rsp-8+arg_18], rdi
0x180010a26  push    rbp
0x180010a27  lea     rbp, [rsp-170h]
0x180010a2f  sub     rsp, 270h
0x180010a36  mov     rax, cs:__security_cookie
0x180010a3d  xor     rax, rsp
0x180010a40  mov     [rbp+170h+var_10], rax
0x180010a47  mov     rdi, rdx
0x180010a4a  mov     qword ptr [rdx], 0
0x180010a51  mov     rbx, rcx
0x180010a54  call    cs:__imp_GetCurrentProcessId
0x180010a5a  mov     [rsp+270h+var_248], rbx
0x180010a5f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010a66  mov     r9d, eax
0x180010a69  mov     [rsp+270h+var_250], 130h; int
0x180010a71  mov     edx, 104h; unsigned __int64
0x180010a76  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010a7b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010a80  mov     r9d, 1F0001h; dwDesiredAccess
0x180010a86  mov     [rsp+270h+var_240], 0
0x180010a8f  xor     r8d, r8d; dwFlags
0x180010a92  lea     rdx, [rsp+270h+Name]; lpName
0x180010a97  xor     ecx, ecx; lpMutexAttributes
0x180010a99  call    cs:__imp_CreateMutexExW
0x180010a9f  mov     rdx, rax
0x180010aa2  lea     rcx, [rsp+270h+var_240]
0x180010aa7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180010aac  cmp     [rsp+270h+var_240], 0
0x180010ab2  jnz     short loc_180010ABD
0x180010ab4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010ab9  mov     ebx, eax
0x180010abb  jmp     short loc_180010B30
0x180010abd  lea     rdx, [rsp+270h+var_238]
0x180010ac2  lea     rcx, [rsp+270h+var_240]
0x180010ac7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180010acc  lea     rdx, [rsp+270h+var_230]; void **
0x180010ad1  mov     [rsp+270h+var_230], 0
0x180010ada  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010adf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180010ae4  mov     ebx, eax
0x180010ae6  test    eax, eax
0x180010ae8  jns     short loc_180010B11
0x180010aea  mov     edx, 12Eh; void *
0x180010aef  mov     rcx, [rbp+178h]; this
0x180010af6  lea     r8, aWil; "wil"
0x180010afd  mov     r9d, eax; char *
0x180010b00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b05  lea     rcx, [rsp+270h+var_238]
0x180010b0a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010b0f  jmp     short loc_180010B30
0x180010b11  mov     rcx, [rsp+270h+var_230]
0x180010b16  test    rcx, rcx
0x180010b19  jz      short loc_180010B60
0x180010b1b  mov     [rdi], rcx
0x180010b1e  mov     eax, [rcx]
0x180010b20  inc     eax
0x180010b22  mov     [rcx], eax
0x180010b24  lea     rcx, [rsp+270h+var_238]
0x180010b29  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010b2e  xor     ebx, ebx
0x180010b30  lea     rcx, [rsp+270h+var_240]
0x180010b35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010b3a  mov     eax, ebx
0x180010b3c  mov     rcx, [rbp+170h+var_10]
0x180010b43  xor     rcx, rsp; StackCookie
0x180010b46  call    __security_check_cookie
0x180010b4b  lea     r11, [rsp+270h+var_s0]
0x180010b53  mov     rbx, [r11+20h]
0x180010b57  mov     rdi, [r11+28h]
0x180010b5b  mov     rsp, r11
0x180010b5e  pop     rbp
0x180010b5f  retn
0x180010b60  mov     r8, rdi
0x180010b63  lea     rdx, [rsp+270h+var_240]
0x180010b68  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010b6d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180010b72  mov     ebx, eax
0x180010b74  test    eax, eax
0x180010b76  jns     short loc_180010B24
0x180010b78  mov     edx, 137h
0x180010b7d  jmp     loc_180010AEF
```
