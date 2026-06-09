# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1400595c4`
- end: `0x14005976b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140086c24`

## callees

- `0x14000c33c`
- `0x140016848`
- `0x140016eec`
- `0x140016f30`
- `0x140018e68`
- `0x1400595c4`
- `0x140059774`
- `0x14005d0e0`
- `0x140061ec8`
- `0x14006213c`
- `0x140089320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14005963e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14005963e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400595f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400595f9`

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
0x1400595c4  mov     [rsp-8+arg_10], rbx
0x1400595c9  push    rbp
0x1400595ca  push    rsi
0x1400595cb  push    rdi
0x1400595cc  lea     rbp, [rsp-170h]
0x1400595d4  sub     rsp, 270h
0x1400595db  mov     rax, cs:__security_cookie
0x1400595e2  xor     rax, rsp
0x1400595e5  mov     [rbp+180h+var_20], rax
0x1400595ec  mov     rsi, rdx
0x1400595ef  mov     qword ptr [rdx], 0
0x1400595f6  mov     rbx, rcx
0x1400595f9  call    cs:__imp_GetCurrentProcessId
0x1400595ff  mov     [rsp+280h+var_258], rbx
0x140059604  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14005960b  mov     r9d, eax
0x14005960e  mov     [rsp+280h+var_260], 130h; int
0x140059616  mov     edx, 104h; unsigned __int64
0x14005961b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140059620  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140059625  mov     r9d, 1F0001h; dwDesiredAccess
0x14005962b  mov     [rsp+280h+var_250], 0
0x140059634  xor     r8d, r8d; dwFlags
0x140059637  lea     rdx, [rsp+280h+Name]; lpName
0x14005963c  xor     ecx, ecx; lpMutexAttributes
0x14005963e  call    cs:__imp_CreateMutexExW
0x140059644  mov     rdx, rax
0x140059647  lea     rcx, [rsp+280h+var_250]
0x14005964c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140059651  mov     rbx, [rsp+280h+var_250]
0x140059656  test    rbx, rbx
0x140059659  jnz     short loc_140059665
0x14005965b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140059660  jmp     loc_140059749
0x140059665  lea     rdx, [rsp+280h+var_248]
0x14005966a  lea     rcx, [rsp+280h+var_250]
0x14005966f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140059674  lea     rdx, [rsp+280h+var_240]; void **
0x140059679  mov     [rsp+280h+var_240], 0
0x140059682  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140059687  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x14005968c  mov     edi, eax
0x14005968e  test    eax, eax
0x140059690  jns     short loc_1400596C6
0x140059692  mov     rcx, [rbp+188h]; this
0x140059699  lea     r8, aWil; "wil"
0x1400596a0  mov     r9d, eax; char *
0x1400596a3  mov     edx, 12Eh; void *
0x1400596a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400596ad  lea     rcx, [rsp+280h+var_248]
0x1400596b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400596b7  mov     rcx, rbx; this
0x1400596ba  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400596bf  mov     eax, edi
0x1400596c1  jmp     loc_140059749
0x1400596c6  mov     rcx, [rsp+280h+var_240]
0x1400596cb  test    rcx, rcx
0x1400596ce  jz      short loc_1400596DB
0x1400596d0  mov     [rsi], rcx
0x1400596d3  mov     eax, [rcx]
0x1400596d5  inc     eax
0x1400596d7  mov     [rcx], eax
0x1400596d9  jmp     short loc_140059730
0x1400596db  mov     r8, rsi
0x1400596de  lea     rdx, [rsp+280h+var_250]
0x1400596e3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400596e8  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400596ed  mov     ebx, eax
0x1400596ef  test    eax, eax
0x1400596f1  jns     short loc_14005972B
0x1400596f3  mov     rcx, [rbp+188h]; this
0x1400596fa  lea     r8, aWil; "wil"
0x140059701  mov     r9d, eax; char *
0x140059704  mov     edx, 137h; void *
0x140059709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005970e  lea     rcx, [rsp+280h+var_248]
0x140059713  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140059718  mov     rcx, [rsp+280h+var_250]; this
0x14005971d  test    rcx, rcx
0x140059720  jz      short loc_140059727
0x140059722  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140059727  mov     eax, ebx
0x140059729  jmp     short loc_140059749
0x14005972b  mov     rbx, [rsp+280h+var_250]
0x140059730  lea     rcx, [rsp+280h+var_248]
0x140059735  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14005973a  test    rbx, rbx
0x14005973d  jz      short loc_140059747
0x14005973f  mov     rcx, rbx; this
0x140059742  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140059747  xor     eax, eax
0x140059749  mov     rcx, [rbp+180h+var_20]
0x140059750  xor     rcx, rsp; StackCookie
0x140059753  call    __security_check_cookie
0x140059758  mov     rbx, [rsp+280h+arg_10]
0x140059760  add     rsp, 270h
0x140059767  pop     rdi
0x140059768  pop     rsi
0x140059769  pop     rbp
0x14005976a  retn
```
