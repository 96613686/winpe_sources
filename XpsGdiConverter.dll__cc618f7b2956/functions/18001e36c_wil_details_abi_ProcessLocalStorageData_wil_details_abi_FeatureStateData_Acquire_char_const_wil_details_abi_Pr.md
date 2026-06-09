# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001e36c`
- end: `0x18001e4cb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001ebe4`

## callees

- `0x180008830`
- `0x18000aacc`
- `0x18000aae8`
- `0x18000b498`
- `0x18000c264`
- `0x18000c840`
- `0x18000c9ac`
- `0x18000cd9c`
- `0x18000cea0`
- `0x18001e36c`
- `0x18001f1b8`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18001e3a4`
- `KERNEL32!GetCurrentProcessId` at `0x18001e3a4`
- `KERNEL32!CreateMutexExW` at `0x18001e3e9`
- `KERNEL32!CreateMutexExW` at `0x18001e3e9`

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
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001e36c  mov     [rsp-8+arg_10], rbx
0x18001e371  mov     [rsp-8+arg_18], rdi
0x18001e376  push    rbp
0x18001e377  lea     rbp, [rsp-170h]
0x18001e37f  sub     rsp, 270h
0x18001e386  mov     rax, cs:__security_cookie
0x18001e38d  xor     rax, rsp
0x18001e390  mov     [rbp+170h+var_10], rax
0x18001e397  mov     rdi, rdx
0x18001e39a  mov     qword ptr [rdx], 0
0x18001e3a1  mov     rbx, rcx
0x18001e3a4  call    cs:__imp_GetCurrentProcessId
0x18001e3aa  mov     [rsp+270h+var_248], rbx
0x18001e3af  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001e3b6  mov     r9d, eax
0x18001e3b9  mov     [rsp+270h+var_250], 130h; int
0x18001e3c1  mov     edx, 104h; unsigned __int64
0x18001e3c6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18001e3cb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001e3d0  mov     r9d, 1F0001h; dwDesiredAccess
0x18001e3d6  mov     [rsp+270h+var_240], 0
0x18001e3df  xor     r8d, r8d; dwFlags
0x18001e3e2  lea     rdx, [rsp+270h+Name]; lpName
0x18001e3e7  xor     ecx, ecx; lpMutexAttributes
0x18001e3e9  call    cs:__imp_CreateMutexExW
0x18001e3ef  mov     rdx, rax
0x18001e3f2  lea     rcx, [rsp+270h+var_240]
0x18001e3f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001e3fc  cmp     [rsp+270h+var_240], 0
0x18001e402  jnz     short loc_18001E40D
0x18001e404  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001e409  mov     ebx, eax
0x18001e40b  jmp     short loc_18001E479
0x18001e40d  lea     rdx, [rsp+270h+var_238]
0x18001e412  lea     rcx, [rsp+270h+var_240]
0x18001e417  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001e41c  lea     rdx, [rsp+270h+var_230]; void **
0x18001e421  mov     [rsp+270h+var_230], 0
0x18001e42a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18001e42f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18001e434  mov     ebx, eax
0x18001e436  test    eax, eax
0x18001e438  jns     short loc_18001E45A
0x18001e43a  mov     edx, 12Eh; void *
0x18001e43f  mov     rcx, [rbp+178h]; this
0x18001e446  mov     r9d, eax; char *
0x18001e449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e44e  lea     rcx, [rsp+270h+var_238]
0x18001e453  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e458  jmp     short loc_18001E479
0x18001e45a  mov     rcx, [rsp+270h+var_230]
0x18001e45f  test    rcx, rcx
0x18001e462  jz      short loc_18001E4A9
0x18001e464  mov     [rdi], rcx
0x18001e467  mov     eax, [rcx]
0x18001e469  inc     eax
0x18001e46b  mov     [rcx], eax
0x18001e46d  lea     rcx, [rsp+270h+var_238]
0x18001e472  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e477  xor     ebx, ebx
0x18001e479  lea     rcx, [rsp+270h+var_240]
0x18001e47e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e483  mov     eax, ebx
0x18001e485  mov     rcx, [rbp+170h+var_10]
0x18001e48c  xor     rcx, rsp; StackCookie
0x18001e48f  call    __security_check_cookie
0x18001e494  lea     r11, [rsp+270h+var_s0]
0x18001e49c  mov     rbx, [r11+20h]
0x18001e4a0  mov     rdi, [r11+28h]
0x18001e4a4  mov     rsp, r11
0x18001e4a7  pop     rbp
0x18001e4a8  retn
0x18001e4a9  mov     r8, rdi
0x18001e4ac  lea     rdx, [rsp+270h+var_240]
0x18001e4b1  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18001e4b6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001e4bb  mov     ebx, eax
0x18001e4bd  test    eax, eax
0x18001e4bf  jns     short loc_18001E46D
0x18001e4c1  mov     edx, 137h
0x18001e4c6  jmp     loc_18001E43F
```
