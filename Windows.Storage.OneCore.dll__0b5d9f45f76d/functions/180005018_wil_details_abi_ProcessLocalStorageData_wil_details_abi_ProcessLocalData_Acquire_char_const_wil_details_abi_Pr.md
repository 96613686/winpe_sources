# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005018`
- end: `0x18000517e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800060fc`

## callees

- `0x180002be0`
- `0x180004b90`
- `0x180004bac`
- `0x180005018`
- `0x180005db8`
- `0x180006b14`
- `0x180007fac`
- `0x180008704`
- `0x180008c18`
- `0x180009584`
- `0x1800098a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005095`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005095`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005050`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005050`

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
0x180005018  mov     [rsp-8+arg_10], rbx
0x18000501d  mov     [rsp-8+arg_18], rdi
0x180005022  push    rbp
0x180005023  lea     rbp, [rsp-170h]
0x18000502b  sub     rsp, 270h
0x180005032  mov     rax, cs:__security_cookie
0x180005039  xor     rax, rsp
0x18000503c  mov     [rbp+170h+var_10], rax
0x180005043  mov     rdi, rdx
0x180005046  mov     qword ptr [rdx], 0
0x18000504d  mov     rbx, rcx
0x180005050  call    cs:__imp_GetCurrentProcessId
0x180005056  mov     [rsp+270h+var_248], rbx
0x18000505b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005062  mov     r9d, eax
0x180005065  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000506d  mov     edx, 104h; unsigned __int64
0x180005072  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005077  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000507c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005082  mov     [rsp+270h+var_240], 0
0x18000508b  xor     r8d, r8d; dwFlags
0x18000508e  lea     rdx, [rsp+270h+Name]; lpName
0x180005093  xor     ecx, ecx; lpMutexAttributes
0x180005095  call    cs:__imp_CreateMutexExW
0x18000509b  mov     rdx, rax
0x18000509e  lea     rcx, [rsp+270h+var_240]
0x1800050a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800050a8  cmp     [rsp+270h+var_240], 0
0x1800050ae  jnz     short loc_1800050B9
0x1800050b0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800050b5  mov     ebx, eax
0x1800050b7  jmp     short loc_18000512C
0x1800050b9  lea     rdx, [rsp+270h+var_238]
0x1800050be  lea     rcx, [rsp+270h+var_240]
0x1800050c3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800050c8  lea     rdx, [rsp+270h+var_230]; void **
0x1800050cd  mov     [rsp+270h+var_230], 0
0x1800050d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800050db  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800050e0  mov     ebx, eax
0x1800050e2  test    eax, eax
0x1800050e4  jns     short loc_18000510D
0x1800050e6  mov     edx, 12Eh; void *
0x1800050eb  mov     rcx, [rbp+178h]; this
0x1800050f2  lea     r8, aWil; "wil"
0x1800050f9  mov     r9d, eax; char *
0x1800050fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005101  lea     rcx, [rsp+270h+var_238]
0x180005106  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000510b  jmp     short loc_18000512C
0x18000510d  mov     rcx, [rsp+270h+var_230]
0x180005112  test    rcx, rcx
0x180005115  jz      short loc_18000515C
0x180005117  mov     [rdi], rcx
0x18000511a  mov     eax, [rcx]
0x18000511c  inc     eax
0x18000511e  mov     [rcx], eax
0x180005120  lea     rcx, [rsp+270h+var_238]
0x180005125  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000512a  xor     ebx, ebx
0x18000512c  lea     rcx, [rsp+270h+var_240]
0x180005131  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005136  mov     eax, ebx
0x180005138  mov     rcx, [rbp+170h+var_10]
0x18000513f  xor     rcx, rsp; StackCookie
0x180005142  call    __security_check_cookie
0x180005147  lea     r11, [rsp+270h+var_s0]
0x18000514f  mov     rbx, [r11+20h]
0x180005153  mov     rdi, [r11+28h]
0x180005157  mov     rsp, r11
0x18000515a  pop     rbp
0x18000515b  retn
0x18000515c  mov     r8, rdi
0x18000515f  lea     rdx, [rsp+270h+var_240]
0x180005164  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005169  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000516e  mov     ebx, eax
0x180005170  test    eax, eax
0x180005172  jns     short loc_180005120
0x180005174  mov     edx, 137h
0x180005179  jmp     loc_1800050EB
```
