# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800098a8`
- end: `0x180009a0e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180003660`

## callees

- `0x1800033d0`
- `0x180006900`
- `0x180009484`
- `0x1800094a0`
- `0x1800098a8`
- `0x18000b6b8`
- `0x18000c344`
- `0x18000eec0`
- `0x18000f4dc`
- `0x18000ff4c`
- `0x180010230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009925`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009925`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800098e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800098e0`

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
0x1800098a8  mov     [rsp-8+arg_10], rbx
0x1800098ad  mov     [rsp-8+arg_18], rdi
0x1800098b2  push    rbp
0x1800098b3  lea     rbp, [rsp-170h]
0x1800098bb  sub     rsp, 270h
0x1800098c2  mov     rax, cs:__security_cookie
0x1800098c9  xor     rax, rsp
0x1800098cc  mov     [rbp+170h+var_10], rax
0x1800098d3  mov     rdi, rdx
0x1800098d6  mov     qword ptr [rdx], 0
0x1800098dd  mov     rbx, rcx
0x1800098e0  call    cs:__imp_GetCurrentProcessId
0x1800098e6  mov     [rsp+270h+var_248], rbx
0x1800098eb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800098f2  mov     r9d, eax
0x1800098f5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800098fd  mov     edx, 104h; unsigned __int64
0x180009902  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009907  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000990c  mov     r9d, 1F0001h; dwDesiredAccess
0x180009912  mov     [rsp+270h+var_240], 0
0x18000991b  xor     r8d, r8d; dwFlags
0x18000991e  lea     rdx, [rsp+270h+Name]; lpName
0x180009923  xor     ecx, ecx; lpMutexAttributes
0x180009925  call    cs:__imp_CreateMutexExW
0x18000992b  mov     rdx, rax
0x18000992e  lea     rcx, [rsp+270h+var_240]
0x180009933  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009938  cmp     [rsp+270h+var_240], 0
0x18000993e  jnz     short loc_180009949
0x180009940  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009945  mov     ebx, eax
0x180009947  jmp     short loc_1800099BC
0x180009949  lea     rdx, [rsp+270h+var_238]
0x18000994e  lea     rcx, [rsp+270h+var_240]
0x180009953  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180009958  lea     rdx, [rsp+270h+var_230]; void **
0x18000995d  mov     [rsp+270h+var_230], 0
0x180009966  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000996b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180009970  mov     ebx, eax
0x180009972  test    eax, eax
0x180009974  jns     short loc_18000999D
0x180009976  mov     edx, 12Eh; void *
0x18000997b  mov     rcx, [rbp+178h]; this
0x180009982  lea     r8, aWil; "wil"
0x180009989  mov     r9d, eax; char *
0x18000998c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009991  lea     rcx, [rsp+270h+var_238]
0x180009996  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000999b  jmp     short loc_1800099BC
0x18000999d  mov     rcx, [rsp+270h+var_230]
0x1800099a2  test    rcx, rcx
0x1800099a5  jz      short loc_1800099EC
0x1800099a7  mov     [rdi], rcx
0x1800099aa  mov     eax, [rcx]
0x1800099ac  inc     eax
0x1800099ae  mov     [rcx], eax
0x1800099b0  lea     rcx, [rsp+270h+var_238]
0x1800099b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800099ba  xor     ebx, ebx
0x1800099bc  lea     rcx, [rsp+270h+var_240]
0x1800099c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800099c6  mov     eax, ebx
0x1800099c8  mov     rcx, [rbp+170h+var_10]
0x1800099cf  xor     rcx, rsp; StackCookie
0x1800099d2  call    __security_check_cookie
0x1800099d7  lea     r11, [rsp+270h+var_s0]
0x1800099df  mov     rbx, [r11+20h]
0x1800099e3  mov     rdi, [r11+28h]
0x1800099e7  mov     rsp, r11
0x1800099ea  pop     rbp
0x1800099eb  retn
0x1800099ec  mov     r8, rdi
0x1800099ef  lea     rdx, [rsp+270h+var_240]
0x1800099f4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800099f9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800099fe  mov     ebx, eax
0x180009a00  test    eax, eax
0x180009a02  jns     short loc_1800099B0
0x180009a04  mov     edx, 137h
0x180009a09  jmp     loc_18000997B
```
