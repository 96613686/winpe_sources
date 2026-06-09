# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003478`
- end: `0x1400035de`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400044f4`

## callees

- `0x1400014c0`
- `0x140003078`
- `0x140003094`
- `0x140003478`
- `0x1400041c8`
- `0x140004e38`
- `0x140005fcc`
- `0x14000670c`
- `0x140006af8`
- `0x1400071e4`
- `0x140007508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400034f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400034f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400034b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400034b0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  void *v9; // rdx
  __int64 v10; // rdx
  void *v11; // rdx
  _DWORD *v12; // rcx
  wil::details *v14; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v15; // [rsp+38h] [rbp-C8h] BYREF
  void *v16; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v14 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v14,
    Mutex);
  if ( v14 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v14,
      &v15);
    v16 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v16);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v15,
        v11);
      goto LABEL_9;
    }
    v12 = v16;
    if ( v16 )
    {
      *a2 = v16;
      ++*v12;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v15,
      v9);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v14,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140003478  mov     [rsp-8+arg_10], rbx
0x14000347d  mov     [rsp-8+arg_18], rdi
0x140003482  push    rbp
0x140003483  lea     rbp, [rsp-170h]
0x14000348b  sub     rsp, 270h
0x140003492  mov     rax, cs:__security_cookie
0x140003499  xor     rax, rsp
0x14000349c  mov     [rbp+170h+var_10], rax
0x1400034a3  mov     rdi, rdx
0x1400034a6  mov     qword ptr [rdx], 0
0x1400034ad  mov     rbx, rcx
0x1400034b0  call    cs:__imp_GetCurrentProcessId
0x1400034b6  mov     [rsp+270h+var_248], rbx
0x1400034bb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400034c2  mov     r9d, eax
0x1400034c5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1400034cd  mov     edx, 104h; unsigned __int64
0x1400034d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400034d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400034dc  mov     r9d, 1F0001h; dwDesiredAccess
0x1400034e2  mov     [rsp+270h+var_240], 0
0x1400034eb  xor     r8d, r8d; dwFlags
0x1400034ee  lea     rdx, [rsp+270h+Name]; lpName
0x1400034f3  xor     ecx, ecx; lpMutexAttributes
0x1400034f5  call    cs:__imp_CreateMutexExW
0x1400034fb  mov     rdx, rax
0x1400034fe  lea     rcx, [rsp+270h+var_240]
0x140003503  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140003508  cmp     [rsp+270h+var_240], 0
0x14000350e  jnz     short loc_140003519
0x140003510  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003515  mov     ebx, eax
0x140003517  jmp     short loc_14000358C
0x140003519  lea     rdx, [rsp+270h+var_238]
0x14000351e  lea     rcx, [rsp+270h+var_240]
0x140003523  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140003528  lea     rdx, [rsp+270h+var_230]; void **
0x14000352d  mov     [rsp+270h+var_230], 0
0x140003536  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000353b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140003540  mov     ebx, eax
0x140003542  test    eax, eax
0x140003544  jns     short loc_14000356D
0x140003546  mov     edx, 12Eh; void *
0x14000354b  mov     rcx, [rbp+178h]; this
0x140003552  lea     r8, aWil; "wil"
0x140003559  mov     r9d, eax; char *
0x14000355c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003561  lea     rcx, [rsp+270h+var_238]
0x140003566  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000356b  jmp     short loc_14000358C
0x14000356d  mov     rcx, [rsp+270h+var_230]
0x140003572  test    rcx, rcx
0x140003575  jz      short loc_1400035BC
0x140003577  mov     [rdi], rcx
0x14000357a  mov     eax, [rcx]
0x14000357c  inc     eax
0x14000357e  mov     [rcx], eax
0x140003580  lea     rcx, [rsp+270h+var_238]
0x140003585  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000358a  xor     ebx, ebx
0x14000358c  lea     rcx, [rsp+270h+var_240]
0x140003591  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003596  mov     eax, ebx
0x140003598  mov     rcx, [rbp+170h+var_10]
0x14000359f  xor     rcx, rsp; StackCookie
0x1400035a2  call    __security_check_cookie
0x1400035a7  lea     r11, [rsp+270h+var_s0]
0x1400035af  mov     rbx, [r11+20h]
0x1400035b3  mov     rdi, [r11+28h]
0x1400035b7  mov     rsp, r11
0x1400035ba  pop     rbp
0x1400035bb  retn
0x1400035bc  mov     r8, rdi
0x1400035bf  lea     rdx, [rsp+270h+var_240]
0x1400035c4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400035c9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400035ce  mov     ebx, eax
0x1400035d0  test    eax, eax
0x1400035d2  jns     short loc_140003580
0x1400035d4  mov     edx, 137h
0x1400035d9  jmp     loc_14000354B
```
