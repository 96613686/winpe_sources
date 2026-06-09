# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004fd8`
- end: `0x18000513e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007430`

## callees

- `0x180004a48`
- `0x180004a64`
- `0x180004fd8`
- `0x180006fc4`
- `0x180012fe8`
- `0x180015c40`
- `0x18001a6c0`
- `0x18001abcc`
- `0x18001b544`
- `0x18001b8dc`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005055`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005055`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005010`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005010`

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
0x180004fd8  mov     [rsp-8+arg_10], rbx
0x180004fdd  mov     [rsp-8+arg_18], rdi
0x180004fe2  push    rbp
0x180004fe3  lea     rbp, [rsp-170h]
0x180004feb  sub     rsp, 270h
0x180004ff2  mov     rax, cs:__security_cookie
0x180004ff9  xor     rax, rsp
0x180004ffc  mov     [rbp+170h+var_10], rax
0x180005003  mov     rdi, rdx
0x180005006  mov     qword ptr [rdx], 0
0x18000500d  mov     rbx, rcx
0x180005010  call    cs:__imp_GetCurrentProcessId
0x180005016  mov     [rsp+270h+var_248], rbx
0x18000501b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005022  mov     r9d, eax
0x180005025  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000502d  mov     edx, 104h; unsigned __int64
0x180005032  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005037  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000503c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005042  mov     [rsp+270h+var_240], 0
0x18000504b  xor     r8d, r8d; dwFlags
0x18000504e  lea     rdx, [rsp+270h+Name]; lpName
0x180005053  xor     ecx, ecx; lpMutexAttributes
0x180005055  call    cs:__imp_CreateMutexExW
0x18000505b  mov     rdx, rax
0x18000505e  lea     rcx, [rsp+270h+var_240]
0x180005063  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005068  cmp     [rsp+270h+var_240], 0
0x18000506e  jnz     short loc_180005079
0x180005070  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005075  mov     ebx, eax
0x180005077  jmp     short loc_1800050EC
0x180005079  lea     rdx, [rsp+270h+var_238]
0x18000507e  lea     rcx, [rsp+270h+var_240]
0x180005083  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005088  lea     rdx, [rsp+270h+var_230]; void **
0x18000508d  mov     [rsp+270h+var_230], 0
0x180005096  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000509b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800050a0  mov     ebx, eax
0x1800050a2  test    eax, eax
0x1800050a4  jns     short loc_1800050CD
0x1800050a6  mov     edx, 12Eh; void *
0x1800050ab  mov     rcx, [rbp+178h]; this
0x1800050b2  lea     r8, aWil; "wil"
0x1800050b9  mov     r9d, eax; char *
0x1800050bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050c1  lea     rcx, [rsp+270h+var_238]
0x1800050c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800050cb  jmp     short loc_1800050EC
0x1800050cd  mov     rcx, [rsp+270h+var_230]
0x1800050d2  test    rcx, rcx
0x1800050d5  jz      short loc_18000511C
0x1800050d7  mov     [rdi], rcx
0x1800050da  mov     eax, [rcx]
0x1800050dc  inc     eax
0x1800050de  mov     [rcx], eax
0x1800050e0  lea     rcx, [rsp+270h+var_238]
0x1800050e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800050ea  xor     ebx, ebx
0x1800050ec  lea     rcx, [rsp+270h+var_240]
0x1800050f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800050f6  mov     eax, ebx
0x1800050f8  mov     rcx, [rbp+170h+var_10]
0x1800050ff  xor     rcx, rsp; StackCookie
0x180005102  call    __security_check_cookie
0x180005107  lea     r11, [rsp+270h+var_s0]
0x18000510f  mov     rbx, [r11+20h]
0x180005113  mov     rdi, [r11+28h]
0x180005117  mov     rsp, r11
0x18000511a  pop     rbp
0x18000511b  retn
0x18000511c  mov     r8, rdi
0x18000511f  lea     rdx, [rsp+270h+var_240]
0x180005124  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005129  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000512e  mov     ebx, eax
0x180005130  test    eax, eax
0x180005132  jns     short loc_1800050E0
0x180005134  mov     edx, 137h
0x180005139  jmp     loc_1800050AB
```
