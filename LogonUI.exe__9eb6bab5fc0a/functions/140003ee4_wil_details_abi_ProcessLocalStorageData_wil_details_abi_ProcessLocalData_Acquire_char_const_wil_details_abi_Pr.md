# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003ee4`
- end: `0x140004043`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140004d84`

## callees

- `0x1400020dc`
- `0x1400024cc`
- `0x140002910`
- `0x140003d08`
- `0x140003d24`
- `0x140003ee4`
- `0x140005484`
- `0x1400061ac`
- `0x1400068fc`
- `0x140007074`
- `0x1400071bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003f61`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003f61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003f1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003f1c`

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
0x140003ee4  mov     [rsp-8+arg_10], rbx
0x140003ee9  mov     [rsp-8+arg_18], rdi
0x140003eee  push    rbp
0x140003eef  lea     rbp, [rsp-170h]
0x140003ef7  sub     rsp, 270h
0x140003efe  mov     rax, cs:__security_cookie
0x140003f05  xor     rax, rsp
0x140003f08  mov     [rbp+170h+var_10], rax
0x140003f0f  mov     rdi, rdx
0x140003f12  mov     qword ptr [rdx], 0
0x140003f19  mov     rbx, rcx
0x140003f1c  call    cs:__imp_GetCurrentProcessId
0x140003f22  mov     [rsp+270h+var_248], rbx
0x140003f27  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003f2e  mov     r9d, eax
0x140003f31  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140003f39  mov     edx, 104h; unsigned __int64
0x140003f3e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003f43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003f48  mov     r9d, 1F0001h; dwDesiredAccess
0x140003f4e  mov     [rsp+270h+var_240], 0
0x140003f57  xor     r8d, r8d; dwFlags
0x140003f5a  lea     rdx, [rsp+270h+Name]; lpName
0x140003f5f  xor     ecx, ecx; lpMutexAttributes
0x140003f61  call    cs:__imp_CreateMutexExW
0x140003f67  mov     rdx, rax
0x140003f6a  lea     rcx, [rsp+270h+var_240]
0x140003f6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140003f74  cmp     [rsp+270h+var_240], 0
0x140003f7a  jnz     short loc_140003F85
0x140003f7c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003f81  mov     ebx, eax
0x140003f83  jmp     short loc_140003FF1
0x140003f85  lea     rdx, [rsp+270h+var_238]
0x140003f8a  lea     rcx, [rsp+270h+var_240]
0x140003f8f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140003f94  lea     rdx, [rsp+270h+var_230]; void **
0x140003f99  mov     [rsp+270h+var_230], 0
0x140003fa2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003fa7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140003fac  mov     ebx, eax
0x140003fae  test    eax, eax
0x140003fb0  jns     short loc_140003FD2
0x140003fb2  mov     edx, 12Eh; void *
0x140003fb7  mov     rcx, [rbp+178h]; this
0x140003fbe  mov     r9d, eax; char *
0x140003fc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fc6  lea     rcx, [rsp+270h+var_238]
0x140003fcb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003fd0  jmp     short loc_140003FF1
0x140003fd2  mov     rcx, [rsp+270h+var_230]
0x140003fd7  test    rcx, rcx
0x140003fda  jz      short loc_140004021
0x140003fdc  mov     [rdi], rcx
0x140003fdf  mov     eax, [rcx]
0x140003fe1  inc     eax
0x140003fe3  mov     [rcx], eax
0x140003fe5  lea     rcx, [rsp+270h+var_238]
0x140003fea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003fef  xor     ebx, ebx
0x140003ff1  lea     rcx, [rsp+270h+var_240]
0x140003ff6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003ffb  mov     eax, ebx
0x140003ffd  mov     rcx, [rbp+170h+var_10]
0x140004004  xor     rcx, rsp; StackCookie
0x140004007  call    __security_check_cookie
0x14000400c  lea     r11, [rsp+270h+var_s0]
0x140004014  mov     rbx, [r11+20h]
0x140004018  mov     rdi, [r11+28h]
0x14000401c  mov     rsp, r11
0x14000401f  pop     rbp
0x140004020  retn
0x140004021  mov     r8, rdi
0x140004024  lea     rdx, [rsp+270h+var_240]
0x140004029  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000402e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140004033  mov     ebx, eax
0x140004035  test    eax, eax
0x140004037  jns     short loc_140003FE5
0x140004039  mov     edx, 137h
0x14000403e  jmp     loc_140003FB7
```
