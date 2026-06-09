# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002e05c`
- end: `0x18002e1c2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002f1a4`

## callees

- `0x18001a8e8`
- `0x18001d8e0`
- `0x1800290d4`
- `0x1800293dc`
- `0x18002dec4`
- `0x18002dee0`
- `0x18002e05c`
- `0x18002f698`
- `0x180030fa0`
- `0x180031738`
- `0x180031874`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002e0d9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002e0d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e094`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e094`

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
0x18002e05c  mov     [rsp-8+arg_10], rbx
0x18002e061  mov     [rsp-8+arg_18], rdi
0x18002e066  push    rbp
0x18002e067  lea     rbp, [rsp-170h]
0x18002e06f  sub     rsp, 270h
0x18002e076  mov     rax, cs:__security_cookie
0x18002e07d  xor     rax, rsp
0x18002e080  mov     [rbp+170h+var_10], rax
0x18002e087  mov     rdi, rdx
0x18002e08a  mov     qword ptr [rdx], 0
0x18002e091  mov     rbx, rcx
0x18002e094  call    cs:__imp_GetCurrentProcessId
0x18002e09a  mov     [rsp+270h+var_248], rbx
0x18002e09f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002e0a6  mov     r9d, eax
0x18002e0a9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002e0b1  mov     edx, 104h; unsigned __int64
0x18002e0b6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002e0bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e0c0  mov     r9d, 1F0001h; dwDesiredAccess
0x18002e0c6  mov     [rsp+270h+var_240], 0
0x18002e0cf  xor     r8d, r8d; dwFlags
0x18002e0d2  lea     rdx, [rsp+270h+Name]; lpName
0x18002e0d7  xor     ecx, ecx; lpMutexAttributes
0x18002e0d9  call    cs:__imp_CreateMutexExW
0x18002e0df  mov     rdx, rax
0x18002e0e2  lea     rcx, [rsp+270h+var_240]
0x18002e0e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002e0ec  cmp     [rsp+270h+var_240], 0
0x18002e0f2  jnz     short loc_18002E0FD
0x18002e0f4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002e0f9  mov     ebx, eax
0x18002e0fb  jmp     short loc_18002E170
0x18002e0fd  lea     rdx, [rsp+270h+var_238]
0x18002e102  lea     rcx, [rsp+270h+var_240]
0x18002e107  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002e10c  lea     rdx, [rsp+270h+var_230]; void **
0x18002e111  mov     [rsp+270h+var_230], 0
0x18002e11a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002e11f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002e124  mov     ebx, eax
0x18002e126  test    eax, eax
0x18002e128  jns     short loc_18002E151
0x18002e12a  mov     edx, 12Eh; void *
0x18002e12f  mov     rcx, [rbp+178h]; this
0x18002e136  lea     r8, aWil; "wil"
0x18002e13d  mov     r9d, eax; char *
0x18002e140  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e145  lea     rcx, [rsp+270h+var_238]
0x18002e14a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002e14f  jmp     short loc_18002E170
0x18002e151  mov     rcx, [rsp+270h+var_230]
0x18002e156  test    rcx, rcx
0x18002e159  jz      short loc_18002E1A0
0x18002e15b  mov     [rdi], rcx
0x18002e15e  mov     eax, [rcx]
0x18002e160  inc     eax
0x18002e162  mov     [rcx], eax
0x18002e164  lea     rcx, [rsp+270h+var_238]
0x18002e169  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002e16e  xor     ebx, ebx
0x18002e170  lea     rcx, [rsp+270h+var_240]
0x18002e175  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002e17a  mov     eax, ebx
0x18002e17c  mov     rcx, [rbp+170h+var_10]
0x18002e183  xor     rcx, rsp; StackCookie
0x18002e186  call    __security_check_cookie
0x18002e18b  lea     r11, [rsp+270h+var_s0]
0x18002e193  mov     rbx, [r11+20h]
0x18002e197  mov     rdi, [r11+28h]
0x18002e19b  mov     rsp, r11
0x18002e19e  pop     rbp
0x18002e19f  retn
0x18002e1a0  mov     r8, rdi
0x18002e1a3  lea     rdx, [rsp+270h+var_240]
0x18002e1a8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002e1ad  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002e1b2  mov     ebx, eax
0x18002e1b4  test    eax, eax
0x18002e1b6  jns     short loc_18002E164
0x18002e1b8  mov     edx, 137h
0x18002e1bd  jmp     loc_18002E12F
```
