# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005ed8`
- end: `0x18000603e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800069fc`

## callees

- `0x180005e58`
- `0x180005e74`
- `0x180005ed8`
- `0x180006758`
- `0x180007170`
- `0x180007560`
- `0x180007960`
- `0x180007a70`
- `0x180007f00`
- `0x180007fac`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005f55`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005f55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005f10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005f10`

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
0x180005ed8  mov     [rsp-8+arg_10], rbx
0x180005edd  mov     [rsp-8+arg_18], rdi
0x180005ee2  push    rbp
0x180005ee3  lea     rbp, [rsp-170h]
0x180005eeb  sub     rsp, 270h
0x180005ef2  mov     rax, cs:__security_cookie
0x180005ef9  xor     rax, rsp
0x180005efc  mov     [rbp+170h+var_10], rax
0x180005f03  mov     rdi, rdx
0x180005f06  mov     qword ptr [rdx], 0
0x180005f0d  mov     rbx, rcx
0x180005f10  call    cs:__imp_GetCurrentProcessId
0x180005f16  mov     [rsp+270h+var_248], rbx
0x180005f1b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005f22  mov     r9d, eax
0x180005f25  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180005f2d  mov     edx, 104h; unsigned __int64
0x180005f32  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005f37  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005f3c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005f42  mov     [rsp+270h+var_240], 0
0x180005f4b  xor     r8d, r8d; dwFlags
0x180005f4e  lea     rdx, [rsp+270h+Name]; lpName
0x180005f53  xor     ecx, ecx; lpMutexAttributes
0x180005f55  call    cs:__imp_CreateMutexExW
0x180005f5b  mov     rdx, rax
0x180005f5e  lea     rcx, [rsp+270h+var_240]
0x180005f63  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005f68  cmp     [rsp+270h+var_240], 0
0x180005f6e  jnz     short loc_180005F79
0x180005f70  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005f75  mov     ebx, eax
0x180005f77  jmp     short loc_180005FEC
0x180005f79  lea     rdx, [rsp+270h+var_238]
0x180005f7e  lea     rcx, [rsp+270h+var_240]
0x180005f83  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005f88  lea     rdx, [rsp+270h+var_230]; void **
0x180005f8d  mov     [rsp+270h+var_230], 0
0x180005f96  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005f9b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005fa0  mov     ebx, eax
0x180005fa2  test    eax, eax
0x180005fa4  jns     short loc_180005FCD
0x180005fa6  mov     edx, 12Eh; void *
0x180005fab  mov     rcx, [rbp+178h]; this
0x180005fb2  lea     r8, aWil; "wil"
0x180005fb9  mov     r9d, eax; char *
0x180005fbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005fc1  lea     rcx, [rsp+270h+var_238]
0x180005fc6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005fcb  jmp     short loc_180005FEC
0x180005fcd  mov     rcx, [rsp+270h+var_230]
0x180005fd2  test    rcx, rcx
0x180005fd5  jz      short loc_18000601C
0x180005fd7  mov     [rdi], rcx
0x180005fda  mov     eax, [rcx]
0x180005fdc  inc     eax
0x180005fde  mov     [rcx], eax
0x180005fe0  lea     rcx, [rsp+270h+var_238]
0x180005fe5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005fea  xor     ebx, ebx
0x180005fec  lea     rcx, [rsp+270h+var_240]
0x180005ff1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005ff6  mov     eax, ebx
0x180005ff8  mov     rcx, [rbp+170h+var_10]
0x180005fff  xor     rcx, rsp; StackCookie
0x180006002  call    __security_check_cookie
0x180006007  lea     r11, [rsp+270h+var_s0]
0x18000600f  mov     rbx, [r11+20h]
0x180006013  mov     rdi, [r11+28h]
0x180006017  mov     rsp, r11
0x18000601a  pop     rbp
0x18000601b  retn
0x18000601c  mov     r8, rdi
0x18000601f  lea     rdx, [rsp+270h+var_240]
0x180006024  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006029  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000602e  mov     ebx, eax
0x180006030  test    eax, eax
0x180006032  jns     short loc_180005FE0
0x180006034  mov     edx, 137h
0x180006039  jmp     loc_180005FAB
```
