# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180023e0c`
- end: `0x180023f72`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024528`

## callees

- `0x180010690`
- `0x180023414`
- `0x180023434`
- `0x180023e0c`
- `0x180024f50`
- `0x180026038`
- `0x180027218`
- `0x180027cf8`
- `0x1800297f4`
- `0x18002b26c`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023e41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023e41`
- `KERNEL32!CreateMutexExW` at `0x180023e89`
- `KERNEL32!CreateMutexExW` at `0x180023e89`

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
      v9 = 299;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      *(_DWORD *)*a2 = *v10 + 1;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 308;
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
0x180023e0c  mov     [rsp-8+arg_10], rbx
0x180023e11  mov     [rsp-8+arg_18], rdi
0x180023e16  push    rbp
0x180023e17  lea     rbp, [rsp-170h]
0x180023e1f  sub     rsp, 270h
0x180023e26  mov     rax, cs:__security_cookie
0x180023e2d  xor     rax, rsp
0x180023e30  mov     [rbp+170h+var_10], rax
0x180023e37  and     qword ptr [rdx], 0
0x180023e3b  mov     rdi, rdx
0x180023e3e  mov     rbx, rcx
0x180023e41  call    cs:__imp_GetCurrentProcessId
0x180023e48  nop     dword ptr [rax+rax+00h]
0x180023e4d  mov     [rsp+270h+var_248], rbx
0x180023e52  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180023e59  mov     r9d, eax
0x180023e5c  mov     [rsp+270h+var_250], 130h; int
0x180023e64  mov     edx, 104h; unsigned __int64
0x180023e69  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023e6e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023e73  and     [rsp+270h+var_240], 0
0x180023e79  lea     rdx, [rsp+270h+Name]; lpName
0x180023e7e  mov     r9d, 1F0001h; dwDesiredAccess
0x180023e84  xor     r8d, r8d; dwFlags
0x180023e87  xor     ecx, ecx; lpMutexAttributes
0x180023e89  call    cs:__imp_CreateMutexExW
0x180023e90  nop     dword ptr [rax+rax+00h]
0x180023e95  mov     rdx, rax
0x180023e98  lea     rcx, [rsp+270h+var_240]
0x180023e9d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180023ea2  cmp     [rsp+270h+var_240], 0
0x180023ea8  jnz     short loc_180023EB3
0x180023eaa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023eaf  mov     ebx, eax
0x180023eb1  jmp     short loc_180023F1F
0x180023eb3  lea     rdx, [rsp+270h+var_238]
0x180023eb8  lea     rcx, [rsp+270h+var_240]
0x180023ebd  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180023ec2  and     [rsp+270h+var_230], 0
0x180023ec8  lea     rdx, [rsp+270h+var_230]; void **
0x180023ecd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023ed2  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180023ed7  mov     ebx, eax
0x180023ed9  test    eax, eax
0x180023edb  jns     short loc_180023EFD
0x180023edd  mov     edx, 12Bh; void *
0x180023ee2  mov     rcx, [rbp+178h]; this
0x180023ee9  mov     r9d, eax; char *
0x180023eec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ef1  lea     rcx, [rsp+270h+var_238]
0x180023ef6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023efb  jmp     short loc_180023F1F
0x180023efd  mov     rcx, [rsp+270h+var_230]
0x180023f02  test    rcx, rcx
0x180023f05  jz      short loc_180023F50
0x180023f07  mov     [rdi], rcx
0x180023f0a  mov     ecx, [rcx]
0x180023f0c  mov     rax, [rdi]
0x180023f0f  inc     ecx
0x180023f11  mov     [rax], ecx
0x180023f13  lea     rcx, [rsp+270h+var_238]
0x180023f18  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023f1d  xor     ebx, ebx
0x180023f1f  lea     rcx, [rsp+270h+var_240]
0x180023f24  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023f29  mov     eax, ebx
0x180023f2b  mov     rcx, [rbp+170h+var_10]
0x180023f32  xor     rcx, rsp; StackCookie
0x180023f35  call    __security_check_cookie
0x180023f3a  lea     r11, [rsp+270h+var_s0]
0x180023f42  mov     rbx, [r11+20h]
0x180023f46  mov     rdi, [r11+28h]
0x180023f4a  mov     rsp, r11
0x180023f4d  pop     rbp
0x180023f4e  retn
0x180023f50  mov     r8, rdi
0x180023f53  lea     rdx, [rsp+270h+var_240]
0x180023f58  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023f5d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180023f62  mov     ebx, eax
0x180023f64  test    eax, eax
0x180023f66  jns     short loc_180023F13
0x180023f68  mov     edx, 134h
0x180023f6d  jmp     loc_180023EE2
```
