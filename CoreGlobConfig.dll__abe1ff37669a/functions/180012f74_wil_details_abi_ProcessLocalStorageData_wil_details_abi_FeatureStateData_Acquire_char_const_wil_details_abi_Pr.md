# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180012f74`
- end: `0x1800130da`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180015864`

## callees

- `0x180002380`
- `0x1800067a4`
- `0x1800067c0`
- `0x1800071b8`
- `0x180008294`
- `0x1800088b4`
- `0x180008a68`
- `0x180008ef0`
- `0x180008fec`
- `0x180012f74`
- `0x180016360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012ff1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012ff1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012fac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012fac`

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
0x180012f74  mov     [rsp-8+arg_10], rbx
0x180012f79  mov     [rsp-8+arg_18], rdi
0x180012f7e  push    rbp
0x180012f7f  lea     rbp, [rsp-170h]
0x180012f87  sub     rsp, 270h
0x180012f8e  mov     rax, cs:__security_cookie
0x180012f95  xor     rax, rsp
0x180012f98  mov     [rbp+170h+var_10], rax
0x180012f9f  mov     rdi, rdx
0x180012fa2  mov     qword ptr [rdx], 0
0x180012fa9  mov     rbx, rcx
0x180012fac  call    cs:__imp_GetCurrentProcessId
0x180012fb2  mov     [rsp+270h+var_248], rbx
0x180012fb7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180012fbe  mov     r9d, eax
0x180012fc1  mov     [rsp+270h+var_250], 130h; int
0x180012fc9  mov     edx, 104h; unsigned __int64
0x180012fce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012fd3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012fd8  mov     r9d, 1F0001h; dwDesiredAccess
0x180012fde  mov     [rsp+270h+var_240], 0
0x180012fe7  xor     r8d, r8d; dwFlags
0x180012fea  lea     rdx, [rsp+270h+Name]; lpName
0x180012fef  xor     ecx, ecx; lpMutexAttributes
0x180012ff1  call    cs:__imp_CreateMutexExW
0x180012ff7  mov     rdx, rax
0x180012ffa  lea     rcx, [rsp+270h+var_240]
0x180012fff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180013004  cmp     [rsp+270h+var_240], 0
0x18001300a  jnz     short loc_180013015
0x18001300c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180013011  mov     ebx, eax
0x180013013  jmp     short loc_180013088
0x180013015  lea     rdx, [rsp+270h+var_238]
0x18001301a  lea     rcx, [rsp+270h+var_240]
0x18001301f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180013024  lea     rdx, [rsp+270h+var_230]; void **
0x180013029  mov     [rsp+270h+var_230], 0
0x180013032  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180013037  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001303c  mov     ebx, eax
0x18001303e  test    eax, eax
0x180013040  jns     short loc_180013069
0x180013042  mov     edx, 12Eh; void *
0x180013047  mov     rcx, [rbp+178h]; this
0x18001304e  lea     r8, aWil; "wil"
0x180013055  mov     r9d, eax; char *
0x180013058  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001305d  lea     rcx, [rsp+270h+var_238]
0x180013062  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013067  jmp     short loc_180013088
0x180013069  mov     rcx, [rsp+270h+var_230]
0x18001306e  test    rcx, rcx
0x180013071  jz      short loc_1800130B8
0x180013073  mov     [rdi], rcx
0x180013076  mov     eax, [rcx]
0x180013078  inc     eax
0x18001307a  mov     [rcx], eax
0x18001307c  lea     rcx, [rsp+270h+var_238]
0x180013081  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013086  xor     ebx, ebx
0x180013088  lea     rcx, [rsp+270h+var_240]
0x18001308d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013092  mov     eax, ebx
0x180013094  mov     rcx, [rbp+170h+var_10]
0x18001309b  xor     rcx, rsp; StackCookie
0x18001309e  call    __security_check_cookie
0x1800130a3  lea     r11, [rsp+270h+var_s0]
0x1800130ab  mov     rbx, [r11+20h]
0x1800130af  mov     rdi, [r11+28h]
0x1800130b3  mov     rsp, r11
0x1800130b6  pop     rbp
0x1800130b7  retn
0x1800130b8  mov     r8, rdi
0x1800130bb  lea     rdx, [rsp+270h+var_240]
0x1800130c0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800130c5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800130ca  mov     ebx, eax
0x1800130cc  test    eax, eax
0x1800130ce  jns     short loc_18001307C
0x1800130d0  mov     edx, 137h
0x1800130d5  jmp     loc_180013047
```
