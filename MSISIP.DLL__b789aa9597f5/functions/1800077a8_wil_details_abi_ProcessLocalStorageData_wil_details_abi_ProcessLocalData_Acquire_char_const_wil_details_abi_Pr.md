# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800077a8`
- end: `0x180007907`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b620`

## callees

- `0x180007224`
- `0x1800077a8`
- `0x180007ab4`
- `0x180007c90`
- `0x180007cb8`
- `0x180007d0c`
- `0x18000983c`
- `0x18000ae0c`
- `0x18000ca58`
- `0x18000cc34`
- `0x18000d300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007825`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800077e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800077e0`

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
0x1800077a8  mov     [rsp-8+arg_10], rbx
0x1800077ad  mov     [rsp-8+arg_18], rdi
0x1800077b2  push    rbp
0x1800077b3  lea     rbp, [rsp-170h]
0x1800077bb  sub     rsp, 270h
0x1800077c2  mov     rax, cs:__security_cookie
0x1800077c9  xor     rax, rsp
0x1800077cc  mov     [rbp+170h+var_10], rax
0x1800077d3  mov     rdi, rdx
0x1800077d6  mov     qword ptr [rdx], 0
0x1800077dd  mov     rbx, rcx
0x1800077e0  call    cs:__imp_GetCurrentProcessId
0x1800077e6  mov     [rsp+270h+var_248], rbx
0x1800077eb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800077f2  mov     r9d, eax
0x1800077f5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800077fd  mov     edx, 104h; unsigned __int64
0x180007802  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007807  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000780c  mov     r9d, 1F0001h; dwDesiredAccess
0x180007812  mov     [rsp+270h+var_240], 0
0x18000781b  xor     r8d, r8d; dwFlags
0x18000781e  lea     rdx, [rsp+270h+Name]; lpName
0x180007823  xor     ecx, ecx; lpMutexAttributes
0x180007825  call    cs:__imp_CreateMutexExW
0x18000782b  mov     rdx, rax
0x18000782e  lea     rcx, [rsp+270h+var_240]
0x180007833  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007838  cmp     [rsp+270h+var_240], 0
0x18000783e  jnz     short loc_180007849
0x180007840  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007845  mov     ebx, eax
0x180007847  jmp     short loc_1800078B5
0x180007849  lea     rdx, [rsp+270h+var_238]
0x18000784e  lea     rcx, [rsp+270h+var_240]
0x180007853  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180007858  lea     rdx, [rsp+270h+var_230]; void **
0x18000785d  mov     [rsp+270h+var_230], 0
0x180007866  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000786b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180007870  mov     ebx, eax
0x180007872  test    eax, eax
0x180007874  jns     short loc_180007896
0x180007876  mov     edx, 12Eh; void *
0x18000787b  mov     rcx, [rbp+178h]; this
0x180007882  mov     r9d, eax; char *
0x180007885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000788a  lea     rcx, [rsp+270h+var_238]
0x18000788f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007894  jmp     short loc_1800078B5
0x180007896  mov     rcx, [rsp+270h+var_230]
0x18000789b  test    rcx, rcx
0x18000789e  jz      short loc_1800078E5
0x1800078a0  mov     [rdi], rcx
0x1800078a3  mov     eax, [rcx]
0x1800078a5  inc     eax
0x1800078a7  mov     [rcx], eax
0x1800078a9  lea     rcx, [rsp+270h+var_238]
0x1800078ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800078b3  xor     ebx, ebx
0x1800078b5  lea     rcx, [rsp+270h+var_240]
0x1800078ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800078bf  mov     eax, ebx
0x1800078c1  mov     rcx, [rbp+170h+var_10]
0x1800078c8  xor     rcx, rsp; StackCookie
0x1800078cb  call    __security_check_cookie
0x1800078d0  lea     r11, [rsp+270h+var_s0]
0x1800078d8  mov     rbx, [r11+20h]
0x1800078dc  mov     rdi, [r11+28h]
0x1800078e0  mov     rsp, r11
0x1800078e3  pop     rbp
0x1800078e4  retn
0x1800078e5  mov     r8, rdi
0x1800078e8  lea     rdx, [rsp+270h+var_240]
0x1800078ed  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800078f2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800078f7  mov     ebx, eax
0x1800078f9  test    eax, eax
0x1800078fb  jns     short loc_1800078A9
0x1800078fd  mov     edx, 137h
0x180007902  jmp     loc_18000787B
```
