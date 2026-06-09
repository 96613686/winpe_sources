# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005bd8`
- end: `0x180005d4b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007278`

## callees

- `0x180002a60`
- `0x1800055cc`
- `0x1800055ec`
- `0x180005bd8`
- `0x180006ef0`
- `0x180007d2c`
- `0x1800096ec`
- `0x180009eac`
- `0x18000a388`
- `0x18000ad34`
- `0x18000b090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005c5b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005c10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005c10`

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
0x180005bd8  mov     [rsp-8+arg_10], rbx
0x180005bdd  mov     [rsp-8+arg_18], rdi
0x180005be2  push    rbp
0x180005be3  lea     rbp, [rsp-170h]
0x180005beb  sub     rsp, 270h
0x180005bf2  mov     rax, cs:__security_cookie
0x180005bf9  xor     rax, rsp
0x180005bfc  mov     [rbp+170h+var_10], rax
0x180005c03  mov     rdi, rdx
0x180005c06  mov     qword ptr [rdx], 0
0x180005c0d  mov     rbx, rcx
0x180005c10  call    cs:__imp_GetCurrentProcessId
0x180005c17  nop     dword ptr [rax+rax+00h]
0x180005c1c  mov     [rsp+270h+var_248], rbx
0x180005c21  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005c28  mov     r9d, eax
0x180005c2b  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180005c33  mov     edx, 104h; unsigned __int64
0x180005c38  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005c3d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005c42  mov     r9d, 1F0001h; dwDesiredAccess
0x180005c48  mov     [rsp+270h+var_240], 0
0x180005c51  xor     r8d, r8d; dwFlags
0x180005c54  lea     rdx, [rsp+270h+Name]; lpName
0x180005c59  xor     ecx, ecx; lpMutexAttributes
0x180005c5b  call    cs:__imp_CreateMutexExW
0x180005c62  nop     dword ptr [rax+rax+00h]
0x180005c67  mov     rdx, rax
0x180005c6a  lea     rcx, [rsp+270h+var_240]
0x180005c6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005c74  cmp     [rsp+270h+var_240], 0
0x180005c7a  jnz     short loc_180005C85
0x180005c7c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005c81  mov     ebx, eax
0x180005c83  jmp     short loc_180005CF8
0x180005c85  lea     rdx, [rsp+270h+var_238]
0x180005c8a  lea     rcx, [rsp+270h+var_240]
0x180005c8f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005c94  lea     rdx, [rsp+270h+var_230]; void **
0x180005c99  mov     [rsp+270h+var_230], 0
0x180005ca2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005ca7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005cac  mov     ebx, eax
0x180005cae  test    eax, eax
0x180005cb0  jns     short loc_180005CD9
0x180005cb2  mov     edx, 12Eh; void *
0x180005cb7  mov     rcx, [rbp+178h]; this
0x180005cbe  lea     r8, aWil; "wil"
0x180005cc5  mov     r9d, eax; char *
0x180005cc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ccd  lea     rcx, [rsp+270h+var_238]
0x180005cd2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005cd7  jmp     short loc_180005CF8
0x180005cd9  mov     rcx, [rsp+270h+var_230]
0x180005cde  test    rcx, rcx
0x180005ce1  jz      short loc_180005D29
0x180005ce3  mov     [rdi], rcx
0x180005ce6  mov     eax, [rcx]
0x180005ce8  inc     eax
0x180005cea  mov     [rcx], eax
0x180005cec  lea     rcx, [rsp+270h+var_238]
0x180005cf1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005cf6  xor     ebx, ebx
0x180005cf8  lea     rcx, [rsp+270h+var_240]
0x180005cfd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005d02  mov     eax, ebx
0x180005d04  mov     rcx, [rbp+170h+var_10]
0x180005d0b  xor     rcx, rsp; StackCookie
0x180005d0e  call    __security_check_cookie
0x180005d13  lea     r11, [rsp+270h+var_s0]
0x180005d1b  mov     rbx, [r11+20h]
0x180005d1f  mov     rdi, [r11+28h]
0x180005d23  mov     rsp, r11
0x180005d26  pop     rbp
0x180005d27  retn
0x180005d29  mov     r8, rdi
0x180005d2c  lea     rdx, [rsp+270h+var_240]
0x180005d31  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005d36  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005d3b  mov     ebx, eax
0x180005d3d  test    eax, eax
0x180005d3f  jns     short loc_180005CEC
0x180005d41  mov     edx, 137h
0x180005d46  jmp     loc_180005CB7
```
