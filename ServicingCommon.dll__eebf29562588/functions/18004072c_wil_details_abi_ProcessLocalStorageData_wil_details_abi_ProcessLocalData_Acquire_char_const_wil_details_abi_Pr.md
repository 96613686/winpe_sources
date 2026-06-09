# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18004072c`
- end: `0x18004089f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180040d9c`

## callees

- `0x18001e3c8`
- `0x18001e51c`
- `0x1800293a0`
- `0x1800406c4`
- `0x1800406e4`
- `0x18004072c`
- `0x180041010`
- `0x180041568`
- `0x1800415d0`
- `0x180041848`
- `0x180041908`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1800407af`
- `KERNEL32!CreateMutexExW` at `0x1800407af`
- `KERNEL32!GetCurrentProcessId` at `0x180040764`
- `KERNEL32!GetCurrentProcessId` at `0x180040764`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18004072c  mov     [rsp-8+arg_10], rbx
0x180040731  mov     [rsp-8+arg_18], rdi
0x180040736  push    rbp
0x180040737  lea     rbp, [rsp-170h]
0x18004073f  sub     rsp, 270h
0x180040746  mov     rax, cs:__security_cookie
0x18004074d  xor     rax, rsp
0x180040750  mov     [rbp+170h+var_10], rax
0x180040757  mov     rdi, rdx
0x18004075a  mov     qword ptr [rdx], 0
0x180040761  mov     rbx, rcx
0x180040764  call    cs:__imp_GetCurrentProcessId
0x18004076b  nop     dword ptr [rax+rax+00h]
0x180040770  mov     [rsp+270h+var_248], rbx
0x180040775  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004077c  mov     r9d, eax
0x18004077f  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180040787  mov     edx, 104h; unsigned __int64
0x18004078c  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180040791  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180040796  mov     r9d, 1F0001h; dwDesiredAccess
0x18004079c  mov     [rsp+270h+var_240], 0
0x1800407a5  xor     r8d, r8d; dwFlags
0x1800407a8  lea     rdx, [rsp+270h+Name]; lpName
0x1800407ad  xor     ecx, ecx; lpMutexAttributes
0x1800407af  call    cs:__imp_CreateMutexExW
0x1800407b6  nop     dword ptr [rax+rax+00h]
0x1800407bb  mov     rdx, rax
0x1800407be  lea     rcx, [rsp+270h+var_240]
0x1800407c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800407c8  cmp     [rsp+270h+var_240], 0
0x1800407ce  jnz     short loc_1800407D9
0x1800407d0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800407d5  mov     ebx, eax
0x1800407d7  jmp     short loc_18004084C
0x1800407d9  lea     rdx, [rsp+270h+var_238]
0x1800407de  lea     rcx, [rsp+270h+var_240]
0x1800407e3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800407e8  lea     rdx, [rsp+270h+var_230]; void **
0x1800407ed  mov     [rsp+270h+var_230], 0
0x1800407f6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800407fb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180040800  mov     ebx, eax
0x180040802  test    eax, eax
0x180040804  jns     short loc_18004082D
0x180040806  mov     edx, 12Eh; void *
0x18004080b  mov     rcx, [rbp+178h]; this
0x180040812  lea     r8, aWil; "wil"
0x180040819  mov     r9d, eax; char *
0x18004081c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040821  lea     rcx, [rsp+270h+var_238]
0x180040826  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004082b  jmp     short loc_18004084C
0x18004082d  mov     rcx, [rsp+270h+var_230]
0x180040832  test    rcx, rcx
0x180040835  jz      short loc_18004087D
0x180040837  mov     [rdi], rcx
0x18004083a  mov     eax, [rcx]
0x18004083c  inc     eax
0x18004083e  mov     [rcx], eax
0x180040840  lea     rcx, [rsp+270h+var_238]
0x180040845  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004084a  xor     ebx, ebx
0x18004084c  lea     rcx, [rsp+270h+var_240]
0x180040851  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040856  mov     eax, ebx
0x180040858  mov     rcx, [rbp+170h+var_10]
0x18004085f  xor     rcx, rsp; StackCookie
0x180040862  call    __security_check_cookie
0x180040867  lea     r11, [rsp+270h+var_s0]
0x18004086f  mov     rbx, [r11+20h]
0x180040873  mov     rdi, [r11+28h]
0x180040877  mov     rsp, r11
0x18004087a  pop     rbp
0x18004087b  retn
0x18004087d  mov     r8, rdi
0x180040880  lea     rdx, [rsp+270h+var_240]
0x180040885  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18004088a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004088f  mov     ebx, eax
0x180040891  test    eax, eax
0x180040893  jns     short loc_180040840
0x180040895  mov     edx, 137h
0x18004089a  jmp     loc_18004080B
```
