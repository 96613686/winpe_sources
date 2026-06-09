# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001d1bc`
- end: `0x18001d322`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180026200`

## callees

- `0x18000ff1c`
- `0x180010250`
- `0x180017be8`
- `0x18001cb10`
- `0x18001d1bc`
- `0x18001d328`
- `0x18001d344`
- `0x18001d378`
- `0x18002537c`
- `0x18002cd20`
- `0x180030474`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001d239`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001d239`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d1f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d1f4`

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
0x18001d1bc  mov     [rsp-8+arg_10], rbx
0x18001d1c1  mov     [rsp-8+arg_18], rdi
0x18001d1c6  push    rbp
0x18001d1c7  lea     rbp, [rsp-170h]
0x18001d1cf  sub     rsp, 270h
0x18001d1d6  mov     rax, cs:__security_cookie
0x18001d1dd  xor     rax, rsp
0x18001d1e0  mov     [rbp+170h+var_10], rax
0x18001d1e7  mov     rdi, rdx
0x18001d1ea  mov     qword ptr [rdx], 0
0x18001d1f1  mov     rbx, rcx
0x18001d1f4  call    cs:__imp_GetCurrentProcessId
0x18001d1fa  mov     [rsp+270h+var_248], rbx
0x18001d1ff  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001d206  mov     r9d, eax
0x18001d209  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001d211  mov     edx, 104h; unsigned __int64
0x18001d216  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001d21b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d220  mov     r9d, 1F0001h; dwDesiredAccess
0x18001d226  mov     [rsp+270h+var_240], 0
0x18001d22f  xor     r8d, r8d; dwFlags
0x18001d232  lea     rdx, [rsp+270h+Name]; lpName
0x18001d237  xor     ecx, ecx; lpMutexAttributes
0x18001d239  call    cs:__imp_CreateMutexExW
0x18001d23f  mov     rdx, rax
0x18001d242  lea     rcx, [rsp+270h+var_240]
0x18001d247  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001d24c  cmp     [rsp+270h+var_240], 0
0x18001d252  jnz     short loc_18001D25D
0x18001d254  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001d259  mov     ebx, eax
0x18001d25b  jmp     short loc_18001D2D0
0x18001d25d  lea     rdx, [rsp+270h+var_238]
0x18001d262  lea     rcx, [rsp+270h+var_240]
0x18001d267  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001d26c  lea     rdx, [rsp+270h+var_230]; void **
0x18001d271  mov     [rsp+270h+var_230], 0
0x18001d27a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001d27f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001d284  mov     ebx, eax
0x18001d286  test    eax, eax
0x18001d288  jns     short loc_18001D2B1
0x18001d28a  mov     edx, 12Eh; void *
0x18001d28f  mov     rcx, [rbp+178h]; this
0x18001d296  lea     r8, aWil; "wil"
0x18001d29d  mov     r9d, eax; char *
0x18001d2a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d2a5  lea     rcx, [rsp+270h+var_238]
0x18001d2aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d2af  jmp     short loc_18001D2D0
0x18001d2b1  mov     rcx, [rsp+270h+var_230]
0x18001d2b6  test    rcx, rcx
0x18001d2b9  jz      short loc_18001D300
0x18001d2bb  mov     [rdi], rcx
0x18001d2be  mov     eax, [rcx]
0x18001d2c0  inc     eax
0x18001d2c2  mov     [rcx], eax
0x18001d2c4  lea     rcx, [rsp+270h+var_238]
0x18001d2c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d2ce  xor     ebx, ebx
0x18001d2d0  lea     rcx, [rsp+270h+var_240]
0x18001d2d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d2da  mov     eax, ebx
0x18001d2dc  mov     rcx, [rbp+170h+var_10]
0x18001d2e3  xor     rcx, rsp; StackCookie
0x18001d2e6  call    __security_check_cookie
0x18001d2eb  lea     r11, [rsp+270h+var_s0]
0x18001d2f3  mov     rbx, [r11+20h]
0x18001d2f7  mov     rdi, [r11+28h]
0x18001d2fb  mov     rsp, r11
0x18001d2fe  pop     rbp
0x18001d2ff  retn
0x18001d300  mov     r8, rdi
0x18001d303  lea     rdx, [rsp+270h+var_240]
0x18001d308  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001d30d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001d312  mov     ebx, eax
0x18001d314  test    eax, eax
0x18001d316  jns     short loc_18001D2C4
0x18001d318  mov     edx, 137h
0x18001d31d  jmp     loc_18001D28F
```
