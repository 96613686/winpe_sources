# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18004929c`
- end: `0x1800493fb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004ace0`

## callees

- `0x180003710`
- `0x1800449f0`
- `0x180048db0`
- `0x180048dcc`
- `0x18004929c`
- `0x18004ab9c`
- `0x18004b914`
- `0x18004ce50`
- `0x18004df50`
- `0x18004eca0`
- `0x18004f050`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800492d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800492d4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180049319`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180049319`

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
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18004929c  mov     [rsp-8+arg_10], rbx
0x1800492a1  mov     [rsp-8+arg_18], rdi
0x1800492a6  push    rbp
0x1800492a7  lea     rbp, [rsp-170h]
0x1800492af  sub     rsp, 270h
0x1800492b6  mov     rax, cs:__security_cookie
0x1800492bd  xor     rax, rsp
0x1800492c0  mov     [rbp+170h+var_10], rax
0x1800492c7  mov     rdi, rdx
0x1800492ca  mov     qword ptr [rdx], 0
0x1800492d1  mov     rbx, rcx
0x1800492d4  call    cs:__imp_GetCurrentProcessId
0x1800492da  mov     [rsp+270h+var_248], rbx
0x1800492df  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800492e6  mov     r9d, eax
0x1800492e9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800492f1  mov     edx, 104h; unsigned __int64
0x1800492f6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800492fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180049300  mov     r9d, 1F0001h; dwDesiredAccess
0x180049306  mov     [rsp+270h+var_240], 0
0x18004930f  xor     r8d, r8d; dwFlags
0x180049312  lea     rdx, [rsp+270h+Name]; lpName
0x180049317  xor     ecx, ecx; lpMutexAttributes
0x180049319  call    cs:__imp_CreateMutexExW
0x18004931f  mov     rdx, rax
0x180049322  lea     rcx, [rsp+270h+var_240]
0x180049327  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004932c  cmp     [rsp+270h+var_240], 0
0x180049332  jnz     short loc_18004933D
0x180049334  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180049339  mov     ebx, eax
0x18004933b  jmp     short loc_1800493A9
0x18004933d  lea     rdx, [rsp+270h+var_238]
0x180049342  lea     rcx, [rsp+270h+var_240]
0x180049347  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18004934c  lea     rdx, [rsp+270h+var_230]; void **
0x180049351  mov     [rsp+270h+var_230], 0
0x18004935a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004935f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180049364  mov     ebx, eax
0x180049366  test    eax, eax
0x180049368  jns     short loc_18004938A
0x18004936a  mov     edx, 12Eh; void *
0x18004936f  mov     rcx, [rbp+178h]; this
0x180049376  mov     r9d, eax; char *
0x180049379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004937e  lea     rcx, [rsp+270h+var_238]
0x180049383  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180049388  jmp     short loc_1800493A9
0x18004938a  mov     rcx, [rsp+270h+var_230]
0x18004938f  test    rcx, rcx
0x180049392  jz      short loc_1800493D9
0x180049394  mov     [rdi], rcx
0x180049397  mov     eax, [rcx]
0x180049399  inc     eax
0x18004939b  mov     [rcx], eax
0x18004939d  lea     rcx, [rsp+270h+var_238]
0x1800493a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800493a7  xor     ebx, ebx
0x1800493a9  lea     rcx, [rsp+270h+var_240]
0x1800493ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800493b3  mov     eax, ebx
0x1800493b5  mov     rcx, [rbp+170h+var_10]
0x1800493bc  xor     rcx, rsp; StackCookie
0x1800493bf  call    __security_check_cookie
0x1800493c4  lea     r11, [rsp+270h+var_s0]
0x1800493cc  mov     rbx, [r11+20h]
0x1800493d0  mov     rdi, [r11+28h]
0x1800493d4  mov     rsp, r11
0x1800493d7  pop     rbp
0x1800493d8  retn
0x1800493d9  mov     r8, rdi
0x1800493dc  lea     rdx, [rsp+270h+var_240]
0x1800493e1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800493e6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800493eb  mov     ebx, eax
0x1800493ed  test    eax, eax
0x1800493ef  jns     short loc_18004939D
0x1800493f1  mov     edx, 137h
0x1800493f6  jmp     loc_18004936F
```
