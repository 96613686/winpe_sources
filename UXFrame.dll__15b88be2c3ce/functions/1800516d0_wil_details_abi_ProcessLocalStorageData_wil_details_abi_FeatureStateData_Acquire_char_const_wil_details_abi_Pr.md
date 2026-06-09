# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800516d0`
- end: `0x18005183f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800519d8`

## callees

- `0x180002b20`
- `0x18000e360`
- `0x18000e37c`
- `0x180015f40`
- `0x180016414`
- `0x18001a878`
- `0x180043a20`
- `0x1800516d0`
- `0x180052bb8`
- `0x1800549d8`
- `0x180055014`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180051708`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180051708`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005174d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005174d`

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
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
    v12 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      &v12);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x1800516d0  mov     [rsp-8+arg_10], rbx
0x1800516d5  mov     [rsp-8+arg_18], rdi
0x1800516da  push    rbp
0x1800516db  lea     rbp, [rsp-170h]
0x1800516e3  sub     rsp, 270h
0x1800516ea  mov     rax, cs:__security_cookie
0x1800516f1  xor     rax, rsp
0x1800516f4  mov     [rbp+170h+var_10], rax
0x1800516fb  mov     rdi, rdx
0x1800516fe  mov     qword ptr [rdx], 0
0x180051705  mov     rbx, rcx
0x180051708  call    cs:__imp_GetCurrentProcessId
0x18005170e  mov     [rsp+270h+var_248], rbx
0x180051713  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18005171a  mov     r9d, eax
0x18005171d  mov     [rsp+270h+var_250], 130h; int
0x180051725  mov     edx, 104h; unsigned __int64
0x18005172a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18005172f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180051734  mov     r9d, 1F0001h; dwDesiredAccess
0x18005173a  mov     [rsp+270h+var_240], 0
0x180051743  xor     r8d, r8d; dwFlags
0x180051746  lea     rdx, [rsp+270h+Name]; lpName
0x18005174b  xor     ecx, ecx; lpMutexAttributes
0x18005174d  call    cs:__imp_CreateMutexExW
0x180051753  mov     rdx, rax
0x180051756  lea     rcx, [rsp+270h+var_240]
0x18005175b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180051760  cmp     [rsp+270h+var_240], 0
0x180051766  jnz     short loc_180051771
0x180051768  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005176d  mov     ebx, eax
0x18005176f  jmp     short loc_1800517ED
0x180051771  lea     rdx, [rsp+270h+var_238]
0x180051776  mov     [rsp+270h+var_238], 0
0x18005177f  lea     rcx, [rsp+270h+var_240]
0x180051784  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180051789  lea     rdx, [rsp+270h+var_230]; void **
0x18005178e  mov     [rsp+270h+var_230], 0
0x180051797  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18005179c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800517a1  mov     ebx, eax
0x1800517a3  test    eax, eax
0x1800517a5  jns     short loc_1800517CE
0x1800517a7  mov     edx, 12Eh; void *
0x1800517ac  mov     rcx, [rbp+178h]; this
0x1800517b3  lea     r8, aWil; "wil"
0x1800517ba  mov     r9d, eax; char *
0x1800517bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800517c2  lea     rcx, [rsp+270h+var_238]
0x1800517c7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800517cc  jmp     short loc_1800517ED
0x1800517ce  mov     rcx, [rsp+270h+var_230]
0x1800517d3  test    rcx, rcx
0x1800517d6  jz      short loc_18005181D
0x1800517d8  mov     [rdi], rcx
0x1800517db  mov     eax, [rcx]
0x1800517dd  inc     eax
0x1800517df  mov     [rcx], eax
0x1800517e1  lea     rcx, [rsp+270h+var_238]
0x1800517e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800517eb  xor     ebx, ebx
0x1800517ed  lea     rcx, [rsp+270h+var_240]
0x1800517f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800517f7  mov     eax, ebx
0x1800517f9  mov     rcx, [rbp+170h+var_10]
0x180051800  xor     rcx, rsp; StackCookie
0x180051803  call    __security_check_cookie
0x180051808  lea     r11, [rsp+270h+var_s0]
0x180051810  mov     rbx, [r11+20h]
0x180051814  mov     rdi, [r11+28h]
0x180051818  mov     rsp, r11
0x18005181b  pop     rbp
0x18005181c  retn
0x18005181d  mov     r8, rdi
0x180051820  lea     rdx, [rsp+270h+var_240]
0x180051825  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18005182a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005182f  mov     ebx, eax
0x180051831  test    eax, eax
0x180051833  jns     short loc_1800517E1
0x180051835  mov     edx, 137h
0x18005183a  jmp     loc_1800517AC
```
