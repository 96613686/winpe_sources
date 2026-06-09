# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800515e8`
- end: `0x180051747`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180052dac`

## callees

- `0x180010208`
- `0x18004dcc0`
- `0x18004ece0`
- `0x1800511d0`
- `0x1800511ec`
- `0x1800515e8`
- `0x180053d80`
- `0x180054e04`
- `0x180055a78`
- `0x180056234`
- `0x1800563b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180051665`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180051665`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180051620`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180051620`

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
0x1800515e8  mov     [rsp-8+arg_10], rbx
0x1800515ed  mov     [rsp-8+arg_18], rdi
0x1800515f2  push    rbp
0x1800515f3  lea     rbp, [rsp-170h]
0x1800515fb  sub     rsp, 270h
0x180051602  mov     rax, cs:__security_cookie
0x180051609  xor     rax, rsp
0x18005160c  mov     [rbp+170h+var_10], rax
0x180051613  mov     rdi, rdx
0x180051616  mov     qword ptr [rdx], 0
0x18005161d  mov     rbx, rcx
0x180051620  call    cs:__imp_GetCurrentProcessId
0x180051626  mov     [rsp+270h+var_248], rbx
0x18005162b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180051632  mov     r9d, eax
0x180051635  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18005163d  mov     edx, 104h; unsigned __int64
0x180051642  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180051647  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005164c  mov     r9d, 1F0001h; dwDesiredAccess
0x180051652  mov     [rsp+270h+var_240], 0
0x18005165b  xor     r8d, r8d; dwFlags
0x18005165e  lea     rdx, [rsp+270h+Name]; lpName
0x180051663  xor     ecx, ecx; lpMutexAttributes
0x180051665  call    cs:__imp_CreateMutexExW
0x18005166b  mov     rdx, rax
0x18005166e  lea     rcx, [rsp+270h+var_240]
0x180051673  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180051678  cmp     [rsp+270h+var_240], 0
0x18005167e  jnz     short loc_180051689
0x180051680  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180051685  mov     ebx, eax
0x180051687  jmp     short loc_1800516F5
0x180051689  lea     rdx, [rsp+270h+var_238]
0x18005168e  lea     rcx, [rsp+270h+var_240]
0x180051693  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180051698  lea     rdx, [rsp+270h+var_230]; void **
0x18005169d  mov     [rsp+270h+var_230], 0
0x1800516a6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800516ab  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800516b0  mov     ebx, eax
0x1800516b2  test    eax, eax
0x1800516b4  jns     short loc_1800516D6
0x1800516b6  mov     edx, 12Eh; void *
0x1800516bb  mov     rcx, [rbp+178h]; this
0x1800516c2  mov     r9d, eax; char *
0x1800516c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800516ca  lea     rcx, [rsp+270h+var_238]
0x1800516cf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800516d4  jmp     short loc_1800516F5
0x1800516d6  mov     rcx, [rsp+270h+var_230]
0x1800516db  test    rcx, rcx
0x1800516de  jz      short loc_180051725
0x1800516e0  mov     [rdi], rcx
0x1800516e3  mov     eax, [rcx]
0x1800516e5  inc     eax
0x1800516e7  mov     [rcx], eax
0x1800516e9  lea     rcx, [rsp+270h+var_238]
0x1800516ee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800516f3  xor     ebx, ebx
0x1800516f5  lea     rcx, [rsp+270h+var_240]
0x1800516fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800516ff  mov     eax, ebx
0x180051701  mov     rcx, [rbp+170h+var_10]
0x180051708  xor     rcx, rsp; StackCookie
0x18005170b  call    __security_check_cookie
0x180051710  lea     r11, [rsp+270h+var_s0]
0x180051718  mov     rbx, [r11+20h]
0x18005171c  mov     rdi, [r11+28h]
0x180051720  mov     rsp, r11
0x180051723  pop     rbp
0x180051724  retn
0x180051725  mov     r8, rdi
0x180051728  lea     rdx, [rsp+270h+var_240]
0x18005172d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180051732  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180051737  mov     ebx, eax
0x180051739  test    eax, eax
0x18005173b  jns     short loc_1800516E9
0x18005173d  mov     edx, 137h
0x180051742  jmp     loc_1800516BB
```
