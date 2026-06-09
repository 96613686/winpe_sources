# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140011558`
- end: `0x1400116be`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140015710`

## callees

- `0x140005240`
- `0x14000f3d8`
- `0x14000f3f4`
- `0x140011558`
- `0x14001d1d8`
- `0x140020360`
- `0x140028044`
- `0x140029a8c`
- `0x140031920`
- `0x140034314`
- `0x140037ddc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400115d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400115d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140011590`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140011590`

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
0x140011558  mov     [rsp-8+arg_10], rbx
0x14001155d  mov     [rsp-8+arg_18], rdi
0x140011562  push    rbp
0x140011563  lea     rbp, [rsp-170h]
0x14001156b  sub     rsp, 270h
0x140011572  mov     rax, cs:__security_cookie
0x140011579  xor     rax, rsp
0x14001157c  mov     [rbp+170h+var_10], rax
0x140011583  mov     rdi, rdx
0x140011586  mov     qword ptr [rdx], 0
0x14001158d  mov     rbx, rcx
0x140011590  call    cs:__imp_GetCurrentProcessId
0x140011596  mov     [rsp+270h+var_248], rbx
0x14001159b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400115a2  mov     r9d, eax
0x1400115a5  mov     [rsp+270h+var_250], 130h; int
0x1400115ad  mov     edx, 104h; unsigned __int64
0x1400115b2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400115b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400115bc  mov     r9d, 1F0001h; dwDesiredAccess
0x1400115c2  mov     [rsp+270h+var_240], 0
0x1400115cb  xor     r8d, r8d; dwFlags
0x1400115ce  lea     rdx, [rsp+270h+Name]; lpName
0x1400115d3  xor     ecx, ecx; lpMutexAttributes
0x1400115d5  call    cs:__imp_CreateMutexExW
0x1400115db  mov     rdx, rax
0x1400115de  lea     rcx, [rsp+270h+var_240]
0x1400115e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400115e8  cmp     [rsp+270h+var_240], 0
0x1400115ee  jnz     short loc_1400115F9
0x1400115f0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400115f5  mov     ebx, eax
0x1400115f7  jmp     short loc_14001166C
0x1400115f9  lea     rdx, [rsp+270h+var_238]
0x1400115fe  lea     rcx, [rsp+270h+var_240]
0x140011603  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140011608  lea     rdx, [rsp+270h+var_230]; void **
0x14001160d  mov     [rsp+270h+var_230], 0
0x140011616  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14001161b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x140011620  mov     ebx, eax
0x140011622  test    eax, eax
0x140011624  jns     short loc_14001164D
0x140011626  mov     edx, 12Eh; void *
0x14001162b  mov     rcx, [rbp+178h]; this
0x140011632  lea     r8, aWil; "wil"
0x140011639  mov     r9d, eax; char *
0x14001163c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011641  lea     rcx, [rsp+270h+var_238]
0x140011646  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001164b  jmp     short loc_14001166C
0x14001164d  mov     rcx, [rsp+270h+var_230]
0x140011652  test    rcx, rcx
0x140011655  jz      short loc_14001169C
0x140011657  mov     [rdi], rcx
0x14001165a  mov     eax, [rcx]
0x14001165c  inc     eax
0x14001165e  mov     [rcx], eax
0x140011660  lea     rcx, [rsp+270h+var_238]
0x140011665  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001166a  xor     ebx, ebx
0x14001166c  lea     rcx, [rsp+270h+var_240]
0x140011671  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140011676  mov     eax, ebx
0x140011678  mov     rcx, [rbp+170h+var_10]
0x14001167f  xor     rcx, rsp; StackCookie
0x140011682  call    __security_check_cookie
0x140011687  lea     r11, [rsp+270h+var_s0]
0x14001168f  mov     rbx, [r11+20h]
0x140011693  mov     rdi, [r11+28h]
0x140011697  mov     rsp, r11
0x14001169a  pop     rbp
0x14001169b  retn
0x14001169c  mov     r8, rdi
0x14001169f  lea     rdx, [rsp+270h+var_240]
0x1400116a4  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1400116a9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400116ae  mov     ebx, eax
0x1400116b0  test    eax, eax
0x1400116b2  jns     short loc_140011660
0x1400116b4  mov     edx, 137h
0x1400116b9  jmp     loc_14001162B
```
