# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180010dd8`
- end: `0x180010f61`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180011970`

## callees

- `0x18000d030`
- `0x180010b08`
- `0x180010b24`
- `0x180010dd8`
- `0x180011688`
- `0x1800120c0`
- `0x180012734`
- `0x180012ce0`
- `0x180012eec`
- `0x180013380`
- `0x180013484`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010e55`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010e55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010e10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010e10`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  _DWORD *v8; // rcx
  int v10; // eax
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
    if ( Pointer >= 0 )
    {
      v8 = v13;
      if ( v13 )
      {
        *a2 = v13;
        ++*v8;
      }
      else
      {
        v10 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
        LastErrorFailHr = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x137,
            (unsigned int)"wil",
            (const char *)(unsigned int)v10,
            120);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180010dd8  mov     [rsp-8+arg_10], rbx
0x180010ddd  mov     [rsp-8+arg_18], rdi
0x180010de2  push    rbp
0x180010de3  lea     rbp, [rsp-170h]
0x180010deb  sub     rsp, 270h
0x180010df2  mov     rax, cs:__security_cookie
0x180010df9  xor     rax, rsp
0x180010dfc  mov     [rbp+170h+var_10], rax
0x180010e03  mov     rdi, rdx
0x180010e06  mov     rbx, rcx
0x180010e09  mov     qword ptr [rdx], 0
0x180010e10  call    cs:__imp_GetCurrentProcessId
0x180010e16  mov     r9d, eax
0x180010e19  mov     [rsp+270h+var_248], rbx
0x180010e1e  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180010e26  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010e2d  mov     edx, 104h; unsigned __int64
0x180010e32  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010e37  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010e3c  mov     [rsp+270h+var_240], 0
0x180010e45  mov     r9d, 1F0001h; dwDesiredAccess
0x180010e4b  xor     r8d, r8d; dwFlags
0x180010e4e  lea     rdx, [rsp+270h+Name]; lpName
0x180010e53  xor     ecx, ecx; lpMutexAttributes
0x180010e55  call    cs:__imp_CreateMutexExW
0x180010e5b  mov     rdx, rax
0x180010e5e  lea     rcx, [rsp+270h+var_240]
0x180010e63  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180010e68  cmp     [rsp+270h+var_240], 0
0x180010e6e  jnz     short loc_180010E79
0x180010e70  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010e75  mov     ebx, eax
0x180010e77  jmp     short loc_180010EF0
0x180010e79  lea     rdx, [rsp+270h+var_238]
0x180010e7e  lea     rcx, [rsp+270h+var_240]
0x180010e83  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180010e88  nop
0x180010e89  mov     [rsp+270h+var_230], 0
0x180010e92  lea     rdx, [rsp+270h+var_230]; void **
0x180010e97  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010e9c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180010ea1  mov     ebx, eax
0x180010ea3  test    eax, eax
0x180010ea5  jns     short loc_180010ED0
0x180010ea7  mov     rcx, [rbp+178h]; this
0x180010eae  mov     r9d, eax; char *
0x180010eb1  lea     r8, aWil; "wil"
0x180010eb8  mov     edx, 12Eh; void *
0x180010ebd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ec2  nop
0x180010ec3  lea     rcx, [rsp+270h+var_238]
0x180010ec8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010ecd  nop
0x180010ece  jmp     short loc_180010EF0
0x180010ed0  mov     rcx, [rsp+270h+var_230]
0x180010ed5  test    rcx, rcx
0x180010ed8  jz      short loc_180010F20
0x180010eda  mov     [rdi], rcx
0x180010edd  mov     eax, [rcx]
0x180010edf  inc     eax
0x180010ee1  mov     [rcx], eax
0x180010ee3  lea     rcx, [rsp+270h+var_238]
0x180010ee8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010eed  nop
0x180010eee  xor     ebx, ebx
0x180010ef0  lea     rcx, [rsp+270h+var_240]
0x180010ef5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010efa  mov     eax, ebx
0x180010efc  mov     rcx, [rbp+170h+var_10]
0x180010f03  xor     rcx, rsp; StackCookie
0x180010f06  call    __security_check_cookie
0x180010f0b  lea     r11, [rsp+270h+var_s0]
0x180010f13  mov     rbx, [r11+20h]
0x180010f17  mov     rdi, [r11+28h]
0x180010f1b  mov     rsp, r11
0x180010f1e  pop     rbp
0x180010f1f  retn
0x180010f20  mov     r8, rdi
0x180010f23  lea     rdx, [rsp+270h+var_240]
0x180010f28  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010f2d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180010f32  mov     ebx, eax
0x180010f34  test    eax, eax
0x180010f36  jns     short loc_180010EE3
0x180010f38  mov     rcx, [rbp+178h]; this
0x180010f3f  mov     r9d, eax; char *
0x180010f42  lea     r8, aWil; "wil"
0x180010f49  mov     edx, 137h; void *
0x180010f4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f53  nop
0x180010f54  lea     rcx, [rsp+270h+var_238]
0x180010f59  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010f5e  nop
0x180010f5f  jmp     short loc_180010EF0
```
