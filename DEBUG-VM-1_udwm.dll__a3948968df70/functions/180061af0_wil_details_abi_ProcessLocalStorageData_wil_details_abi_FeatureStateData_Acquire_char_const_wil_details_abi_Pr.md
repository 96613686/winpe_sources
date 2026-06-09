# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180061af0`
- end: `0x180061c97`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180061a98`

## callees

- `0x180061af0`
- `0x180061e54`
- `0x180061f48`
- `0x1800623e4`
- `0x180071328`
- `0x18007f694`
- `0x180080308`
- `0x180081a68`
- `0x180082800`
- `0x180095130`
- `0x1800990a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180061b6a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180061b6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180061b25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180061b25`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  int Pointer; // eax
  unsigned int v9; // edi
  void *v10; // rdx
  _DWORD *v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  void *v14; // rdx
  void *v15; // rdx
  wil::details *v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v18; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v16 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v16,
    Mutex);
  v6 = v16;
  if ( !v16 )
    return wil::details::GetLastErrorFailHr(v5);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v16,
    v17);
  v18 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v18);
  v9 = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    wil::details::CloseHandle(v6, v10);
    return v9;
  }
  v11 = v18;
  if ( v18 )
  {
    *a2 = v18;
    ++*v11;
LABEL_12:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    if ( v6 )
      wil::details::CloseHandle(v6, v15);
    return 0;
  }
  v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v6 = v16;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v12, 304);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
  if ( v16 )
    wil::details::CloseHandle(v16, v14);
  return v13;
}

```

## disassembly

```asm
0x180061af0  mov     [rsp-8+arg_10], rbx
0x180061af5  push    rbp
0x180061af6  push    rsi
0x180061af7  push    rdi
0x180061af8  lea     rbp, [rsp-170h]
0x180061b00  sub     rsp, 270h
0x180061b07  mov     rax, cs:__security_cookie
0x180061b0e  xor     rax, rsp
0x180061b11  mov     [rbp+180h+var_20], rax
0x180061b18  mov     rsi, rdx
0x180061b1b  mov     qword ptr [rdx], 0
0x180061b22  mov     rbx, rcx
0x180061b25  call    cs:__imp_GetCurrentProcessId
0x180061b2b  mov     [rsp+280h+var_258], rbx
0x180061b30  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180061b37  mov     r9d, eax
0x180061b3a  mov     [rsp+280h+var_260], 130h; int
0x180061b42  mov     edx, 104h; unsigned __int64
0x180061b47  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180061b4c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180061b51  mov     r9d, 1F0001h; dwDesiredAccess
0x180061b57  mov     [rsp+280h+var_250], 0
0x180061b60  xor     r8d, r8d; dwFlags
0x180061b63  lea     rdx, [rsp+280h+Name]; lpName
0x180061b68  xor     ecx, ecx; lpMutexAttributes
0x180061b6a  call    cs:__imp_CreateMutexExW
0x180061b70  mov     rdx, rax
0x180061b73  lea     rcx, [rsp+280h+var_250]
0x180061b78  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180061b7d  mov     rbx, [rsp+280h+var_250]
0x180061b82  test    rbx, rbx
0x180061b85  jnz     short loc_180061B91
0x180061b87  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180061b8c  jmp     loc_180061C75
0x180061b91  lea     rdx, [rsp+280h+var_248]
0x180061b96  lea     rcx, [rsp+280h+var_250]
0x180061b9b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180061ba0  lea     rdx, [rsp+280h+var_240]; void **
0x180061ba5  mov     [rsp+280h+var_240], 0
0x180061bae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180061bb3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180061bb8  mov     edi, eax
0x180061bba  test    eax, eax
0x180061bbc  jns     short loc_180061BF2
0x180061bbe  mov     rcx, [rbp+188h]; this
0x180061bc5  lea     r8, aWil; "wil"
0x180061bcc  mov     r9d, eax; char *
0x180061bcf  mov     edx, 12Eh; void *
0x180061bd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061bd9  lea     rcx, [rsp+280h+var_248]
0x180061bde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061be3  mov     rcx, rbx; this
0x180061be6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180061beb  mov     eax, edi
0x180061bed  jmp     loc_180061C75
0x180061bf2  mov     rcx, [rsp+280h+var_240]
0x180061bf7  test    rcx, rcx
0x180061bfa  jz      short loc_180061C07
0x180061bfc  mov     [rsi], rcx
0x180061bff  mov     eax, [rcx]
0x180061c01  inc     eax
0x180061c03  mov     [rcx], eax
0x180061c05  jmp     short loc_180061C5C
0x180061c07  mov     r8, rsi
0x180061c0a  lea     rdx, [rsp+280h+var_250]
0x180061c0f  lea     rcx, [rsp+280h+Name]
0x180061c14  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180061c19  mov     ebx, eax
0x180061c1b  test    eax, eax
0x180061c1d  jns     short loc_180061C57
0x180061c1f  mov     rcx, [rbp+188h]; this
0x180061c26  lea     r8, aWil; "wil"
0x180061c2d  mov     r9d, eax; char *
0x180061c30  mov     edx, 137h; void *
0x180061c35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061c3a  lea     rcx, [rsp+280h+var_248]
0x180061c3f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061c44  mov     rcx, [rsp+280h+var_250]; this
0x180061c49  test    rcx, rcx
0x180061c4c  jz      short loc_180061C53
0x180061c4e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180061c53  mov     eax, ebx
0x180061c55  jmp     short loc_180061C75
0x180061c57  mov     rbx, [rsp+280h+var_250]
0x180061c5c  lea     rcx, [rsp+280h+var_248]
0x180061c61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061c66  test    rbx, rbx
0x180061c69  jz      short loc_180061C73
0x180061c6b  mov     rcx, rbx; this
0x180061c6e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180061c73  xor     eax, eax
0x180061c75  mov     rcx, [rbp+180h+var_20]
0x180061c7c  xor     rcx, rsp; StackCookie
0x180061c7f  call    __security_check_cookie
0x180061c84  mov     rbx, [rsp+280h+arg_10]
0x180061c8c  add     rsp, 270h
0x180061c93  pop     rdi
0x180061c94  pop     rsi
0x180061c95  pop     rbp
0x180061c96  retn
```
