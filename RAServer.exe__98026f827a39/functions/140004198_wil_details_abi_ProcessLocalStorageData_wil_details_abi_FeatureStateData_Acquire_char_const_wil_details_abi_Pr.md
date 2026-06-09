# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140004198`
- end: `0x1400042f7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140006970`

## callees

- `0x140003994`
- `0x1400039b0`
- `0x140004198`
- `0x1400067f8`
- `0x140007ee0`
- `0x14000a18c`
- `0x14000aafc`
- `0x14000aea0`
- `0x14000bbf4`
- `0x14000c370`
- `0x140015aa0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140004215`
- `KERNEL32!CreateMutexExW` at `0x140004215`
- `KERNEL32!GetCurrentProcessId` at `0x1400041d0`
- `KERNEL32!GetCurrentProcessId` at `0x1400041d0`

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
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140004198  mov     [rsp-8+arg_10], rbx
0x14000419d  mov     [rsp-8+arg_18], rdi
0x1400041a2  push    rbp
0x1400041a3  lea     rbp, [rsp-170h]
0x1400041ab  sub     rsp, 270h
0x1400041b2  mov     rax, cs:__security_cookie
0x1400041b9  xor     rax, rsp
0x1400041bc  mov     [rbp+170h+var_10], rax
0x1400041c3  mov     rdi, rdx
0x1400041c6  mov     qword ptr [rdx], 0
0x1400041cd  mov     rbx, rcx
0x1400041d0  call    cs:__imp_GetCurrentProcessId
0x1400041d6  mov     [rsp+270h+var_248], rbx
0x1400041db  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400041e2  mov     r9d, eax
0x1400041e5  mov     [rsp+270h+var_250], 130h; int
0x1400041ed  mov     edx, 104h; unsigned __int64
0x1400041f2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400041f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400041fc  mov     r9d, 1F0001h; dwDesiredAccess
0x140004202  mov     [rsp+270h+var_240], 0
0x14000420b  xor     r8d, r8d; dwFlags
0x14000420e  lea     rdx, [rsp+270h+Name]; lpName
0x140004213  xor     ecx, ecx; lpMutexAttributes
0x140004215  call    cs:__imp_CreateMutexExW
0x14000421b  mov     rdx, rax
0x14000421e  lea     rcx, [rsp+270h+var_240]
0x140004223  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140004228  cmp     [rsp+270h+var_240], 0
0x14000422e  jnz     short loc_140004239
0x140004230  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004235  mov     ebx, eax
0x140004237  jmp     short loc_1400042A5
0x140004239  lea     rdx, [rsp+270h+var_238]
0x14000423e  lea     rcx, [rsp+270h+var_240]
0x140004243  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140004248  lea     rdx, [rsp+270h+var_230]; void **
0x14000424d  mov     [rsp+270h+var_230], 0
0x140004256  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000425b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140004260  mov     ebx, eax
0x140004262  test    eax, eax
0x140004264  jns     short loc_140004286
0x140004266  mov     edx, 12Eh; void *
0x14000426b  mov     rcx, [rbp+178h]; this
0x140004272  mov     r9d, eax; char *
0x140004275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000427a  lea     rcx, [rsp+270h+var_238]
0x14000427f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004284  jmp     short loc_1400042A5
0x140004286  mov     rcx, [rsp+270h+var_230]
0x14000428b  test    rcx, rcx
0x14000428e  jz      short loc_1400042D5
0x140004290  mov     [rdi], rcx
0x140004293  mov     eax, [rcx]
0x140004295  inc     eax
0x140004297  mov     [rcx], eax
0x140004299  lea     rcx, [rsp+270h+var_238]
0x14000429e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400042a3  xor     ebx, ebx
0x1400042a5  lea     rcx, [rsp+270h+var_240]
0x1400042aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400042af  mov     eax, ebx
0x1400042b1  mov     rcx, [rbp+170h+var_10]
0x1400042b8  xor     rcx, rsp; StackCookie
0x1400042bb  call    __security_check_cookie
0x1400042c0  lea     r11, [rsp+270h+var_s0]
0x1400042c8  mov     rbx, [r11+20h]
0x1400042cc  mov     rdi, [r11+28h]
0x1400042d0  mov     rsp, r11
0x1400042d3  pop     rbp
0x1400042d4  retn
0x1400042d5  mov     r8, rdi
0x1400042d8  lea     rdx, [rsp+270h+var_240]
0x1400042dd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400042e2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400042e7  mov     ebx, eax
0x1400042e9  test    eax, eax
0x1400042eb  jns     short loc_140004299
0x1400042ed  mov     edx, 137h
0x1400042f2  jmp     loc_14000426B
```
