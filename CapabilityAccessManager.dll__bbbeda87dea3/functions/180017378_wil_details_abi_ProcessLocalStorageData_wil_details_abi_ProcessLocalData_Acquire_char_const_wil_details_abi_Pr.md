# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180017378`
- end: `0x1800174de`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180018970`

## callees

- `0x1800094c0`
- `0x180016dcc`
- `0x180016de8`
- `0x180017378`
- `0x180018598`
- `0x1800194d8`
- `0x18001ab9c`
- `0x18001b400`
- `0x18001b9ec`
- `0x18001c434`
- `0x18001c770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800173f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800173f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800173b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800173b0`

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
0x180017378  mov     [rsp-8+arg_10], rbx
0x18001737d  mov     [rsp-8+arg_18], rdi
0x180017382  push    rbp
0x180017383  lea     rbp, [rsp-170h]
0x18001738b  sub     rsp, 270h
0x180017392  mov     rax, cs:__security_cookie
0x180017399  xor     rax, rsp
0x18001739c  mov     [rbp+170h+var_10], rax
0x1800173a3  mov     rdi, rdx
0x1800173a6  mov     qword ptr [rdx], 0
0x1800173ad  mov     rbx, rcx
0x1800173b0  call    cs:__imp_GetCurrentProcessId
0x1800173b6  mov     [rsp+270h+var_248], rbx
0x1800173bb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800173c2  mov     r9d, eax
0x1800173c5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800173cd  mov     edx, 104h; unsigned __int64
0x1800173d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800173d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800173dc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800173e2  mov     [rsp+270h+var_240], 0
0x1800173eb  xor     r8d, r8d; dwFlags
0x1800173ee  lea     rdx, [rsp+270h+Name]; lpName
0x1800173f3  xor     ecx, ecx; lpMutexAttributes
0x1800173f5  call    cs:__imp_CreateMutexExW
0x1800173fb  mov     rdx, rax
0x1800173fe  lea     rcx, [rsp+270h+var_240]
0x180017403  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180017408  cmp     [rsp+270h+var_240], 0
0x18001740e  jnz     short loc_180017419
0x180017410  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017415  mov     ebx, eax
0x180017417  jmp     short loc_18001748C
0x180017419  lea     rdx, [rsp+270h+var_238]
0x18001741e  lea     rcx, [rsp+270h+var_240]
0x180017423  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180017428  lea     rdx, [rsp+270h+var_230]; void **
0x18001742d  mov     [rsp+270h+var_230], 0
0x180017436  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001743b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180017440  mov     ebx, eax
0x180017442  test    eax, eax
0x180017444  jns     short loc_18001746D
0x180017446  mov     edx, 12Eh; void *
0x18001744b  mov     rcx, [rbp+178h]; this
0x180017452  lea     r8, aWil; "wil"
0x180017459  mov     r9d, eax; char *
0x18001745c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017461  lea     rcx, [rsp+270h+var_238]
0x180017466  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001746b  jmp     short loc_18001748C
0x18001746d  mov     rcx, [rsp+270h+var_230]
0x180017472  test    rcx, rcx
0x180017475  jz      short loc_1800174BC
0x180017477  mov     [rdi], rcx
0x18001747a  mov     eax, [rcx]
0x18001747c  inc     eax
0x18001747e  mov     [rcx], eax
0x180017480  lea     rcx, [rsp+270h+var_238]
0x180017485  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001748a  xor     ebx, ebx
0x18001748c  lea     rcx, [rsp+270h+var_240]
0x180017491  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017496  mov     eax, ebx
0x180017498  mov     rcx, [rbp+170h+var_10]
0x18001749f  xor     rcx, rsp; StackCookie
0x1800174a2  call    __security_check_cookie
0x1800174a7  lea     r11, [rsp+270h+var_s0]
0x1800174af  mov     rbx, [r11+20h]
0x1800174b3  mov     rdi, [r11+28h]
0x1800174b7  mov     rsp, r11
0x1800174ba  pop     rbp
0x1800174bb  retn
0x1800174bc  mov     r8, rdi
0x1800174bf  lea     rdx, [rsp+270h+var_240]
0x1800174c4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800174c9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800174ce  mov     ebx, eax
0x1800174d0  test    eax, eax
0x1800174d2  jns     short loc_180017480
0x1800174d4  mov     edx, 137h
0x1800174d9  jmp     loc_18001744B
```
