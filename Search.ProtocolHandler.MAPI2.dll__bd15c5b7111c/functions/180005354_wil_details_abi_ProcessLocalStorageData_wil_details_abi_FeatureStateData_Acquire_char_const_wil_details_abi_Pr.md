# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005354`
- end: `0x1800054ba`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800061b4`

## callees

- `0x180002300`
- `0x180004ce4`
- `0x180004d00`
- `0x180005354`
- `0x180005ff8`
- `0x180006ea8`
- `0x18000835c`
- `0x180008ae0`
- `0x180008f58`
- `0x1800098b4`
- `0x180009e88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800053d1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800053d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000538c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000538c`

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
0x180005354  mov     [rsp-8+arg_10], rbx
0x180005359  mov     [rsp-8+arg_18], rdi
0x18000535e  push    rbp
0x18000535f  lea     rbp, [rsp-170h]
0x180005367  sub     rsp, 270h
0x18000536e  mov     rax, cs:__security_cookie
0x180005375  xor     rax, rsp
0x180005378  mov     [rbp+170h+var_10], rax
0x18000537f  mov     rdi, rdx
0x180005382  mov     qword ptr [rdx], 0
0x180005389  mov     rbx, rcx
0x18000538c  call    cs:__imp_GetCurrentProcessId
0x180005392  mov     [rsp+270h+var_248], rbx
0x180005397  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000539e  mov     r9d, eax
0x1800053a1  mov     [rsp+270h+var_250], 130h; int
0x1800053a9  mov     edx, 104h; unsigned __int64
0x1800053ae  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800053b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800053b8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800053be  mov     [rsp+270h+var_240], 0
0x1800053c7  xor     r8d, r8d; dwFlags
0x1800053ca  lea     rdx, [rsp+270h+Name]; lpName
0x1800053cf  xor     ecx, ecx; lpMutexAttributes
0x1800053d1  call    cs:__imp_CreateMutexExW
0x1800053d7  mov     rdx, rax
0x1800053da  lea     rcx, [rsp+270h+var_240]
0x1800053df  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800053e4  cmp     [rsp+270h+var_240], 0
0x1800053ea  jnz     short loc_1800053F5
0x1800053ec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800053f1  mov     ebx, eax
0x1800053f3  jmp     short loc_180005468
0x1800053f5  lea     rdx, [rsp+270h+var_238]
0x1800053fa  lea     rcx, [rsp+270h+var_240]
0x1800053ff  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005404  lea     rdx, [rsp+270h+var_230]; void **
0x180005409  mov     [rsp+270h+var_230], 0
0x180005412  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180005417  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18000541c  mov     ebx, eax
0x18000541e  test    eax, eax
0x180005420  jns     short loc_180005449
0x180005422  mov     edx, 12Eh; void *
0x180005427  mov     rcx, [rbp+178h]; this
0x18000542e  lea     r8, aWil; "wil"
0x180005435  mov     r9d, eax; char *
0x180005438  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000543d  lea     rcx, [rsp+270h+var_238]
0x180005442  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005447  jmp     short loc_180005468
0x180005449  mov     rcx, [rsp+270h+var_230]
0x18000544e  test    rcx, rcx
0x180005451  jz      short loc_180005498
0x180005453  mov     [rdi], rcx
0x180005456  mov     eax, [rcx]
0x180005458  inc     eax
0x18000545a  mov     [rcx], eax
0x18000545c  lea     rcx, [rsp+270h+var_238]
0x180005461  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005466  xor     ebx, ebx
0x180005468  lea     rcx, [rsp+270h+var_240]
0x18000546d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005472  mov     eax, ebx
0x180005474  mov     rcx, [rbp+170h+var_10]
0x18000547b  xor     rcx, rsp; StackCookie
0x18000547e  call    __security_check_cookie
0x180005483  lea     r11, [rsp+270h+var_s0]
0x18000548b  mov     rbx, [r11+20h]
0x18000548f  mov     rdi, [r11+28h]
0x180005493  mov     rsp, r11
0x180005496  pop     rbp
0x180005497  retn
0x180005498  mov     r8, rdi
0x18000549b  lea     rdx, [rsp+270h+var_240]
0x1800054a0  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800054a5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800054aa  mov     ebx, eax
0x1800054ac  test    eax, eax
0x1800054ae  jns     short loc_18000545C
0x1800054b0  mov     edx, 137h
0x1800054b5  jmp     loc_180005427
```
