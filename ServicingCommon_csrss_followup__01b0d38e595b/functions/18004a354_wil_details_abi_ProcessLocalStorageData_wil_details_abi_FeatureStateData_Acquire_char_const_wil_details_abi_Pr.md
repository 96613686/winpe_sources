# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18004a354`
- end: `0x18004a4c7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004a770`

## callees

- `0x18001d660`
- `0x180020440`
- `0x18002d2b0`
- `0x1800441a4`
- `0x1800441c4`
- `0x180045b9c`
- `0x180045c58`
- `0x180045ed0`
- `0x180045f90`
- `0x18004a354`
- `0x18004ad18`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x18004a3d7`
- `KERNEL32!CreateMutexExW` at `0x18004a3d7`
- `KERNEL32!GetCurrentProcessId` at `0x18004a38c`
- `KERNEL32!GetCurrentProcessId` at `0x18004a38c`

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
0x18004a354  mov     [rsp-8+arg_10], rbx
0x18004a359  mov     [rsp-8+arg_18], rdi
0x18004a35e  push    rbp
0x18004a35f  lea     rbp, [rsp-170h]
0x18004a367  sub     rsp, 270h
0x18004a36e  mov     rax, cs:__security_cookie
0x18004a375  xor     rax, rsp
0x18004a378  mov     [rbp+170h+var_10], rax
0x18004a37f  mov     rdi, rdx
0x18004a382  mov     qword ptr [rdx], 0
0x18004a389  mov     rbx, rcx
0x18004a38c  call    cs:__imp_GetCurrentProcessId
0x18004a393  nop     dword ptr [rax+rax+00h]
0x18004a398  mov     [rsp+270h+var_248], rbx
0x18004a39d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004a3a4  mov     r9d, eax
0x18004a3a7  mov     [rsp+270h+var_250], 130h; int
0x18004a3af  mov     edx, 104h; unsigned __int64
0x18004a3b4  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18004a3b9  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18004a3be  mov     r9d, 1F0001h; dwDesiredAccess
0x18004a3c4  mov     [rsp+270h+var_240], 0
0x18004a3cd  xor     r8d, r8d; dwFlags
0x18004a3d0  lea     rdx, [rsp+270h+Name]; lpName
0x18004a3d5  xor     ecx, ecx; lpMutexAttributes
0x18004a3d7  call    cs:__imp_CreateMutexExW
0x18004a3de  nop     dword ptr [rax+rax+00h]
0x18004a3e3  mov     rdx, rax
0x18004a3e6  lea     rcx, [rsp+270h+var_240]
0x18004a3eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004a3f0  cmp     [rsp+270h+var_240], 0
0x18004a3f6  jnz     short loc_18004A401
0x18004a3f8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004a3fd  mov     ebx, eax
0x18004a3ff  jmp     short loc_18004A474
0x18004a401  lea     rdx, [rsp+270h+var_238]
0x18004a406  lea     rcx, [rsp+270h+var_240]
0x18004a40b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18004a410  lea     rdx, [rsp+270h+var_230]; void **
0x18004a415  mov     [rsp+270h+var_230], 0
0x18004a41e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18004a423  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18004a428  mov     ebx, eax
0x18004a42a  test    eax, eax
0x18004a42c  jns     short loc_18004A455
0x18004a42e  mov     edx, 12Eh; void *
0x18004a433  mov     rcx, [rbp+178h]; this
0x18004a43a  lea     r8, aWil; "wil"
0x18004a441  mov     r9d, eax; char *
0x18004a444  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a449  lea     rcx, [rsp+270h+var_238]
0x18004a44e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004a453  jmp     short loc_18004A474
0x18004a455  mov     rcx, [rsp+270h+var_230]
0x18004a45a  test    rcx, rcx
0x18004a45d  jz      short loc_18004A4A5
0x18004a45f  mov     [rdi], rcx
0x18004a462  mov     eax, [rcx]
0x18004a464  inc     eax
0x18004a466  mov     [rcx], eax
0x18004a468  lea     rcx, [rsp+270h+var_238]
0x18004a46d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004a472  xor     ebx, ebx
0x18004a474  lea     rcx, [rsp+270h+var_240]
0x18004a479  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004a47e  mov     eax, ebx
0x18004a480  mov     rcx, [rbp+170h+var_10]
0x18004a487  xor     rcx, rsp; StackCookie
0x18004a48a  call    __security_check_cookie
0x18004a48f  lea     r11, [rsp+270h+var_s0]
0x18004a497  mov     rbx, [r11+20h]
0x18004a49b  mov     rdi, [r11+28h]
0x18004a49f  mov     rsp, r11
0x18004a4a2  pop     rbp
0x18004a4a3  retn
0x18004a4a5  mov     r8, rdi
0x18004a4a8  lea     rdx, [rsp+270h+var_240]
0x18004a4ad  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18004a4b2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004a4b7  mov     ebx, eax
0x18004a4b9  test    eax, eax
0x18004a4bb  jns     short loc_18004A468
0x18004a4bd  mov     edx, 137h
0x18004a4c2  jmp     loc_18004A433
```
