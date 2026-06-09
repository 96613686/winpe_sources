# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140008a38`
- end: `0x140008b9e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000be44`

## callees

- `0x140002d30`
- `0x140007fc8`
- `0x140007fe4`
- `0x140008a38`
- `0x14000bb58`
- `0x14000cc98`
- `0x14000e030`
- `0x14000ffdc`
- `0x1400103ec`
- `0x140010ef0`
- `0x140011278`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140008ab5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140008ab5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008a70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008a70`

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
0x140008a38  mov     [rsp-8+arg_10], rbx
0x140008a3d  mov     [rsp-8+arg_18], rdi
0x140008a42  push    rbp
0x140008a43  lea     rbp, [rsp-170h]
0x140008a4b  sub     rsp, 270h
0x140008a52  mov     rax, cs:__security_cookie
0x140008a59  xor     rax, rsp
0x140008a5c  mov     [rbp+170h+var_10], rax
0x140008a63  mov     rdi, rdx
0x140008a66  mov     qword ptr [rdx], 0
0x140008a6d  mov     rbx, rcx
0x140008a70  call    cs:__imp_GetCurrentProcessId
0x140008a76  mov     [rsp+270h+var_248], rbx
0x140008a7b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140008a82  mov     r9d, eax
0x140008a85  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140008a8d  mov     edx, 104h; unsigned __int64
0x140008a92  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140008a97  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008a9c  mov     r9d, 1F0001h; dwDesiredAccess
0x140008aa2  mov     [rsp+270h+var_240], 0
0x140008aab  xor     r8d, r8d; dwFlags
0x140008aae  lea     rdx, [rsp+270h+Name]; lpName
0x140008ab3  xor     ecx, ecx; lpMutexAttributes
0x140008ab5  call    cs:__imp_CreateMutexExW
0x140008abb  mov     rdx, rax
0x140008abe  lea     rcx, [rsp+270h+var_240]
0x140008ac3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140008ac8  cmp     [rsp+270h+var_240], 0
0x140008ace  jnz     short loc_140008AD9
0x140008ad0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140008ad5  mov     ebx, eax
0x140008ad7  jmp     short loc_140008B4C
0x140008ad9  lea     rdx, [rsp+270h+var_238]
0x140008ade  lea     rcx, [rsp+270h+var_240]
0x140008ae3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140008ae8  lea     rdx, [rsp+270h+var_230]; void **
0x140008aed  mov     [rsp+270h+var_230], 0
0x140008af6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140008afb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140008b00  mov     ebx, eax
0x140008b02  test    eax, eax
0x140008b04  jns     short loc_140008B2D
0x140008b06  mov     edx, 12Eh; void *
0x140008b0b  mov     rcx, [rbp+178h]; this
0x140008b12  lea     r8, aWil; "wil"
0x140008b19  mov     r9d, eax; char *
0x140008b1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008b21  lea     rcx, [rsp+270h+var_238]
0x140008b26  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140008b2b  jmp     short loc_140008B4C
0x140008b2d  mov     rcx, [rsp+270h+var_230]
0x140008b32  test    rcx, rcx
0x140008b35  jz      short loc_140008B7C
0x140008b37  mov     [rdi], rcx
0x140008b3a  mov     eax, [rcx]
0x140008b3c  inc     eax
0x140008b3e  mov     [rcx], eax
0x140008b40  lea     rcx, [rsp+270h+var_238]
0x140008b45  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140008b4a  xor     ebx, ebx
0x140008b4c  lea     rcx, [rsp+270h+var_240]
0x140008b51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140008b56  mov     eax, ebx
0x140008b58  mov     rcx, [rbp+170h+var_10]
0x140008b5f  xor     rcx, rsp; StackCookie
0x140008b62  call    __security_check_cookie
0x140008b67  lea     r11, [rsp+270h+var_s0]
0x140008b6f  mov     rbx, [r11+20h]
0x140008b73  mov     rdi, [r11+28h]
0x140008b77  mov     rsp, r11
0x140008b7a  pop     rbp
0x140008b7b  retn
0x140008b7c  mov     r8, rdi
0x140008b7f  lea     rdx, [rsp+270h+var_240]
0x140008b84  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140008b89  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140008b8e  mov     ebx, eax
0x140008b90  test    eax, eax
0x140008b92  jns     short loc_140008B40
0x140008b94  mov     edx, 137h
0x140008b99  jmp     loc_140008B0B
```
