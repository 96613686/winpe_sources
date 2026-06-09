# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003ff8`
- end: `0x14000415e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140004b10`

## callees

- `0x140002360`
- `0x140003ea8`
- `0x140003ec4`
- `0x140003ff8`
- `0x1400048a0`
- `0x140005280`
- `0x1400056ac`
- `0x140005c7c`
- `0x140005ebc`
- `0x1400062d8`
- `0x1400063c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004075`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004075`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004030`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004030`

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
0x140003ff8  mov     [rsp-8+arg_10], rbx
0x140003ffd  mov     [rsp-8+arg_18], rdi
0x140004002  push    rbp
0x140004003  lea     rbp, [rsp-170h]
0x14000400b  sub     rsp, 270h
0x140004012  mov     rax, cs:__security_cookie
0x140004019  xor     rax, rsp
0x14000401c  mov     [rbp+170h+var_10], rax
0x140004023  mov     rdi, rdx
0x140004026  mov     qword ptr [rdx], 0
0x14000402d  mov     rbx, rcx
0x140004030  call    cs:__imp_GetCurrentProcessId
0x140004036  mov     [rsp+270h+var_248], rbx
0x14000403b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004042  mov     r9d, eax
0x140004045  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x14000404d  mov     edx, 104h; unsigned __int64
0x140004052  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140004057  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14000405c  mov     r9d, 1F0001h; dwDesiredAccess
0x140004062  mov     [rsp+270h+var_240], 0
0x14000406b  xor     r8d, r8d; dwFlags
0x14000406e  lea     rdx, [rsp+270h+Name]; lpName
0x140004073  xor     ecx, ecx; lpMutexAttributes
0x140004075  call    cs:__imp_CreateMutexExW
0x14000407b  mov     rdx, rax
0x14000407e  lea     rcx, [rsp+270h+var_240]
0x140004083  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140004088  cmp     [rsp+270h+var_240], 0
0x14000408e  jnz     short loc_140004099
0x140004090  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004095  mov     ebx, eax
0x140004097  jmp     short loc_14000410C
0x140004099  lea     rdx, [rsp+270h+var_238]
0x14000409e  lea     rcx, [rsp+270h+var_240]
0x1400040a3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400040a8  lea     rdx, [rsp+270h+var_230]; void **
0x1400040ad  mov     [rsp+270h+var_230], 0
0x1400040b6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1400040bb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1400040c0  mov     ebx, eax
0x1400040c2  test    eax, eax
0x1400040c4  jns     short loc_1400040ED
0x1400040c6  mov     edx, 12Eh; void *
0x1400040cb  mov     rcx, [rbp+178h]; this
0x1400040d2  lea     r8, aWil; "wil"
0x1400040d9  mov     r9d, eax; char *
0x1400040dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400040e1  lea     rcx, [rsp+270h+var_238]
0x1400040e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400040eb  jmp     short loc_14000410C
0x1400040ed  mov     rcx, [rsp+270h+var_230]
0x1400040f2  test    rcx, rcx
0x1400040f5  jz      short loc_14000413C
0x1400040f7  mov     [rdi], rcx
0x1400040fa  mov     eax, [rcx]
0x1400040fc  inc     eax
0x1400040fe  mov     [rcx], eax
0x140004100  lea     rcx, [rsp+270h+var_238]
0x140004105  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000410a  xor     ebx, ebx
0x14000410c  lea     rcx, [rsp+270h+var_240]
0x140004111  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004116  mov     eax, ebx
0x140004118  mov     rcx, [rbp+170h+var_10]
0x14000411f  xor     rcx, rsp; StackCookie
0x140004122  call    __security_check_cookie
0x140004127  lea     r11, [rsp+270h+var_s0]
0x14000412f  mov     rbx, [r11+20h]
0x140004133  mov     rdi, [r11+28h]
0x140004137  mov     rsp, r11
0x14000413a  pop     rbp
0x14000413b  retn
0x14000413c  mov     r8, rdi
0x14000413f  lea     rdx, [rsp+270h+var_240]
0x140004144  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140004149  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000414e  mov     ebx, eax
0x140004150  test    eax, eax
0x140004152  jns     short loc_140004100
0x140004154  mov     edx, 137h
0x140004159  jmp     loc_1400040CB
```
