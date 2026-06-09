# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180023894`
- end: `0x1800239fa`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024e54`

## callees

- `0x18001401c`
- `0x180014f70`
- `0x1800153f8`
- `0x180016140`
- `0x18001a540`
- `0x18001dc28`
- `0x18001dc44`
- `0x18001fac8`
- `0x18001fe74`
- `0x180020028`
- `0x180023894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023911`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800238cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800238cc`

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
0x180023894  mov     [rsp-8+arg_10], rbx
0x180023899  mov     [rsp-8+arg_18], rdi
0x18002389e  push    rbp
0x18002389f  lea     rbp, [rsp-170h]
0x1800238a7  sub     rsp, 270h
0x1800238ae  mov     rax, cs:__security_cookie
0x1800238b5  xor     rax, rsp
0x1800238b8  mov     [rbp+170h+var_10], rax
0x1800238bf  mov     rdi, rdx
0x1800238c2  mov     qword ptr [rdx], 0
0x1800238c9  mov     rbx, rcx
0x1800238cc  call    cs:__imp_GetCurrentProcessId
0x1800238d2  mov     [rsp+270h+var_248], rbx
0x1800238d7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800238de  mov     r9d, eax
0x1800238e1  mov     [rsp+270h+var_250], 130h; int
0x1800238e9  mov     edx, 104h; unsigned __int64
0x1800238ee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800238f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800238f8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800238fe  mov     [rsp+270h+var_240], 0
0x180023907  xor     r8d, r8d; dwFlags
0x18002390a  lea     rdx, [rsp+270h+Name]; lpName
0x18002390f  xor     ecx, ecx; lpMutexAttributes
0x180023911  call    cs:__imp_CreateMutexExW
0x180023917  mov     rdx, rax
0x18002391a  lea     rcx, [rsp+270h+var_240]
0x18002391f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180023924  cmp     [rsp+270h+var_240], 0
0x18002392a  jnz     short loc_180023935
0x18002392c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023931  mov     ebx, eax
0x180023933  jmp     short loc_1800239A8
0x180023935  lea     rdx, [rsp+270h+var_238]
0x18002393a  lea     rcx, [rsp+270h+var_240]
0x18002393f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180023944  lea     rdx, [rsp+270h+var_230]; void **
0x180023949  mov     [rsp+270h+var_230], 0
0x180023952  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023957  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002395c  mov     ebx, eax
0x18002395e  test    eax, eax
0x180023960  jns     short loc_180023989
0x180023962  mov     edx, 12Eh; void *
0x180023967  mov     rcx, [rbp+178h]; this
0x18002396e  lea     r8, aWil; "wil"
0x180023975  mov     r9d, eax; char *
0x180023978  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002397d  lea     rcx, [rsp+270h+var_238]
0x180023982  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023987  jmp     short loc_1800239A8
0x180023989  mov     rcx, [rsp+270h+var_230]
0x18002398e  test    rcx, rcx
0x180023991  jz      short loc_1800239D8
0x180023993  mov     [rdi], rcx
0x180023996  mov     eax, [rcx]
0x180023998  inc     eax
0x18002399a  mov     [rcx], eax
0x18002399c  lea     rcx, [rsp+270h+var_238]
0x1800239a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800239a6  xor     ebx, ebx
0x1800239a8  lea     rcx, [rsp+270h+var_240]
0x1800239ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800239b2  mov     eax, ebx
0x1800239b4  mov     rcx, [rbp+170h+var_10]
0x1800239bb  xor     rcx, rsp; StackCookie
0x1800239be  call    __security_check_cookie
0x1800239c3  lea     r11, [rsp+270h+var_s0]
0x1800239cb  mov     rbx, [r11+20h]
0x1800239cf  mov     rdi, [r11+28h]
0x1800239d3  mov     rsp, r11
0x1800239d6  pop     rbp
0x1800239d7  retn
0x1800239d8  mov     r8, rdi
0x1800239db  lea     rdx, [rsp+270h+var_240]
0x1800239e0  lea     rcx, [rsp+270h+Name]
0x1800239e5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800239ea  mov     ebx, eax
0x1800239ec  test    eax, eax
0x1800239ee  jns     short loc_18002399C
0x1800239f0  mov     edx, 137h
0x1800239f5  jmp     loc_180023967
```
