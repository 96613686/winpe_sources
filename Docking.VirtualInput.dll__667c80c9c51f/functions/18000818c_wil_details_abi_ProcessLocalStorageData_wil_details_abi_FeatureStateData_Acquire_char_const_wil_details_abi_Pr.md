# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000818c`
- end: `0x1800082f2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008d40`

## callees

- `0x1800036a0`
- `0x180004f4c`
- `0x180004f68`
- `0x180005954`
- `0x1800067a4`
- `0x180006d3c`
- `0x180006eac`
- `0x1800072e0`
- `0x1800073d0`
- `0x18000818c`
- `0x180009030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008209`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008209`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800081c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800081c4`

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
0x18000818c  mov     [rsp-8+arg_10], rbx
0x180008191  mov     [rsp-8+arg_18], rdi
0x180008196  push    rbp
0x180008197  lea     rbp, [rsp-170h]
0x18000819f  sub     rsp, 270h
0x1800081a6  mov     rax, cs:__security_cookie
0x1800081ad  xor     rax, rsp
0x1800081b0  mov     [rbp+170h+var_10], rax
0x1800081b7  mov     rdi, rdx
0x1800081ba  mov     qword ptr [rdx], 0
0x1800081c1  mov     rbx, rcx
0x1800081c4  call    cs:__imp_GetCurrentProcessId
0x1800081ca  mov     [rsp+270h+var_248], rbx
0x1800081cf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800081d6  mov     r9d, eax
0x1800081d9  mov     [rsp+270h+var_250], 130h; int
0x1800081e1  mov     edx, 104h; unsigned __int64
0x1800081e6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800081eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800081f0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800081f6  mov     [rsp+270h+var_240], 0
0x1800081ff  xor     r8d, r8d; dwFlags
0x180008202  lea     rdx, [rsp+270h+Name]; lpName
0x180008207  xor     ecx, ecx; lpMutexAttributes
0x180008209  call    cs:__imp_CreateMutexExW
0x18000820f  mov     rdx, rax
0x180008212  lea     rcx, [rsp+270h+var_240]
0x180008217  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000821c  cmp     [rsp+270h+var_240], 0
0x180008222  jnz     short loc_18000822D
0x180008224  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008229  mov     ebx, eax
0x18000822b  jmp     short loc_1800082A0
0x18000822d  lea     rdx, [rsp+270h+var_238]
0x180008232  lea     rcx, [rsp+270h+var_240]
0x180008237  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000823c  lea     rdx, [rsp+270h+var_230]; void **
0x180008241  mov     [rsp+270h+var_230], 0
0x18000824a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000824f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008254  mov     ebx, eax
0x180008256  test    eax, eax
0x180008258  jns     short loc_180008281
0x18000825a  mov     edx, 12Eh; void *
0x18000825f  mov     rcx, [rbp+178h]; this
0x180008266  lea     r8, aWil; "wil"
0x18000826d  mov     r9d, eax; char *
0x180008270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008275  lea     rcx, [rsp+270h+var_238]
0x18000827a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000827f  jmp     short loc_1800082A0
0x180008281  mov     rcx, [rsp+270h+var_230]
0x180008286  test    rcx, rcx
0x180008289  jz      short loc_1800082D0
0x18000828b  mov     [rdi], rcx
0x18000828e  mov     eax, [rcx]
0x180008290  inc     eax
0x180008292  mov     [rcx], eax
0x180008294  lea     rcx, [rsp+270h+var_238]
0x180008299  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000829e  xor     ebx, ebx
0x1800082a0  lea     rcx, [rsp+270h+var_240]
0x1800082a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800082aa  mov     eax, ebx
0x1800082ac  mov     rcx, [rbp+170h+var_10]
0x1800082b3  xor     rcx, rsp; StackCookie
0x1800082b6  call    __security_check_cookie
0x1800082bb  lea     r11, [rsp+270h+var_s0]
0x1800082c3  mov     rbx, [r11+20h]
0x1800082c7  mov     rdi, [r11+28h]
0x1800082cb  mov     rsp, r11
0x1800082ce  pop     rbp
0x1800082cf  retn
0x1800082d0  mov     r8, rdi
0x1800082d3  lea     rdx, [rsp+270h+var_240]
0x1800082d8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800082dd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800082e2  mov     ebx, eax
0x1800082e4  test    eax, eax
0x1800082e6  jns     short loc_180008294
0x1800082e8  mov     edx, 137h
0x1800082ed  jmp     loc_18000825F
```
