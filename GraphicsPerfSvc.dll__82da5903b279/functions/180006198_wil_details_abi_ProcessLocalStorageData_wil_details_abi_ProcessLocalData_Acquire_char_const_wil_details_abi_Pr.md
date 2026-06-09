# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006198`
- end: `0x1800062fe`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800072ac`

## callees

- `0x180003ab0`
- `0x180005d04`
- `0x180005d20`
- `0x180006198`
- `0x180006f38`
- `0x180007cf0`
- `0x1800091bc`
- `0x180009908`
- `0x180009d88`
- `0x18000a7a4`
- `0x18000aac8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006215`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006215`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800061d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800061d0`

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
0x180006198  mov     [rsp-8+arg_10], rbx
0x18000619d  mov     [rsp-8+arg_18], rdi
0x1800061a2  push    rbp
0x1800061a3  lea     rbp, [rsp-170h]
0x1800061ab  sub     rsp, 270h
0x1800061b2  mov     rax, cs:__security_cookie
0x1800061b9  xor     rax, rsp
0x1800061bc  mov     [rbp+170h+var_10], rax
0x1800061c3  mov     rdi, rdx
0x1800061c6  mov     qword ptr [rdx], 0
0x1800061cd  mov     rbx, rcx
0x1800061d0  call    cs:__imp_GetCurrentProcessId
0x1800061d6  mov     [rsp+270h+var_248], rbx
0x1800061db  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800061e2  mov     r9d, eax
0x1800061e5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800061ed  mov     edx, 104h; unsigned __int64
0x1800061f2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800061f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800061fc  mov     r9d, 1F0001h; dwDesiredAccess
0x180006202  mov     [rsp+270h+var_240], 0
0x18000620b  xor     r8d, r8d; dwFlags
0x18000620e  lea     rdx, [rsp+270h+Name]; lpName
0x180006213  xor     ecx, ecx; lpMutexAttributes
0x180006215  call    cs:__imp_CreateMutexExW
0x18000621b  mov     rdx, rax
0x18000621e  lea     rcx, [rsp+270h+var_240]
0x180006223  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006228  cmp     [rsp+270h+var_240], 0
0x18000622e  jnz     short loc_180006239
0x180006230  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006235  mov     ebx, eax
0x180006237  jmp     short loc_1800062AC
0x180006239  lea     rdx, [rsp+270h+var_238]
0x18000623e  lea     rcx, [rsp+270h+var_240]
0x180006243  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006248  lea     rdx, [rsp+270h+var_230]; void **
0x18000624d  mov     [rsp+270h+var_230], 0
0x180006256  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000625b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180006260  mov     ebx, eax
0x180006262  test    eax, eax
0x180006264  jns     short loc_18000628D
0x180006266  mov     edx, 12Eh; void *
0x18000626b  mov     rcx, [rbp+178h]; this
0x180006272  lea     r8, aWil; "wil"
0x180006279  mov     r9d, eax; char *
0x18000627c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006281  lea     rcx, [rsp+270h+var_238]
0x180006286  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000628b  jmp     short loc_1800062AC
0x18000628d  mov     rcx, [rsp+270h+var_230]
0x180006292  test    rcx, rcx
0x180006295  jz      short loc_1800062DC
0x180006297  mov     [rdi], rcx
0x18000629a  mov     eax, [rcx]
0x18000629c  inc     eax
0x18000629e  mov     [rcx], eax
0x1800062a0  lea     rcx, [rsp+270h+var_238]
0x1800062a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800062aa  xor     ebx, ebx
0x1800062ac  lea     rcx, [rsp+270h+var_240]
0x1800062b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800062b6  mov     eax, ebx
0x1800062b8  mov     rcx, [rbp+170h+var_10]
0x1800062bf  xor     rcx, rsp; StackCookie
0x1800062c2  call    __security_check_cookie
0x1800062c7  lea     r11, [rsp+270h+var_s0]
0x1800062cf  mov     rbx, [r11+20h]
0x1800062d3  mov     rdi, [r11+28h]
0x1800062d7  mov     rsp, r11
0x1800062da  pop     rbp
0x1800062db  retn
0x1800062dc  mov     r8, rdi
0x1800062df  lea     rdx, [rsp+270h+var_240]
0x1800062e4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800062e9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800062ee  mov     ebx, eax
0x1800062f0  test    eax, eax
0x1800062f2  jns     short loc_1800062A0
0x1800062f4  mov     edx, 137h
0x1800062f9  jmp     loc_18000626B
```
