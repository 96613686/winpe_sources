# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006078`
- end: `0x1800061de`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006e4c`

## callees

- `0x180002dc0`
- `0x180005d00`
- `0x180005d1c`
- `0x180006078`
- `0x180006b08`
- `0x18000760c`
- `0x180007d74`
- `0x18000831c`
- `0x1800085b8`
- `0x180008b34`
- `0x1800093bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800060f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800060f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800060b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800060b0`

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
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180006078  mov     [rsp-8+arg_10], rbx
0x18000607d  mov     [rsp-8+arg_18], rdi
0x180006082  push    rbp
0x180006083  lea     rbp, [rsp-170h]
0x18000608b  sub     rsp, 270h
0x180006092  mov     rax, cs:__security_cookie
0x180006099  xor     rax, rsp
0x18000609c  mov     [rbp+170h+var_10], rax
0x1800060a3  mov     rdi, rdx
0x1800060a6  mov     qword ptr [rdx], 0
0x1800060ad  mov     rbx, rcx
0x1800060b0  call    cs:__imp_GetCurrentProcessId
0x1800060b6  mov     [rsp+270h+var_248], rbx
0x1800060bb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800060c2  mov     r9d, eax
0x1800060c5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800060cd  mov     edx, 104h; unsigned __int64
0x1800060d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800060d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800060dc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800060e2  mov     [rsp+270h+var_240], 0
0x1800060eb  xor     r8d, r8d; dwFlags
0x1800060ee  lea     rdx, [rsp+270h+Name]; lpName
0x1800060f3  xor     ecx, ecx; lpMutexAttributes
0x1800060f5  call    cs:__imp_CreateMutexExW
0x1800060fb  mov     rdx, rax
0x1800060fe  lea     rcx, [rsp+270h+var_240]
0x180006103  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006108  cmp     [rsp+270h+var_240], 0
0x18000610e  jnz     short loc_180006119
0x180006110  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006115  mov     ebx, eax
0x180006117  jmp     short loc_18000618C
0x180006119  lea     rdx, [rsp+270h+var_238]
0x18000611e  lea     rcx, [rsp+270h+var_240]
0x180006123  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006128  lea     rdx, [rsp+270h+var_230]; void **
0x18000612d  mov     [rsp+270h+var_230], 0
0x180006136  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000613b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180006140  mov     ebx, eax
0x180006142  test    eax, eax
0x180006144  jns     short loc_18000616D
0x180006146  mov     edx, 12Eh; void *
0x18000614b  mov     rcx, [rbp+178h]; this
0x180006152  lea     r8, aWil; "wil"
0x180006159  mov     r9d, eax; char *
0x18000615c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006161  lea     rcx, [rsp+270h+var_238]
0x180006166  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000616b  jmp     short loc_18000618C
0x18000616d  mov     rcx, [rsp+270h+var_230]
0x180006172  test    rcx, rcx
0x180006175  jz      short loc_1800061BC
0x180006177  mov     [rdi], rcx
0x18000617a  mov     eax, [rcx]
0x18000617c  inc     eax
0x18000617e  mov     [rcx], eax
0x180006180  lea     rcx, [rsp+270h+var_238]
0x180006185  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000618a  xor     ebx, ebx
0x18000618c  lea     rcx, [rsp+270h+var_240]
0x180006191  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006196  mov     eax, ebx
0x180006198  mov     rcx, [rbp+170h+var_10]
0x18000619f  xor     rcx, rsp; StackCookie
0x1800061a2  call    __security_check_cookie
0x1800061a7  lea     r11, [rsp+270h+var_s0]
0x1800061af  mov     rbx, [r11+20h]
0x1800061b3  mov     rdi, [r11+28h]
0x1800061b7  mov     rsp, r11
0x1800061ba  pop     rbp
0x1800061bb  retn
0x1800061bc  mov     r8, rdi
0x1800061bf  lea     rdx, [rsp+270h+var_240]
0x1800061c4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800061c9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800061ce  mov     ebx, eax
0x1800061d0  test    eax, eax
0x1800061d2  jns     short loc_180006180
0x1800061d4  mov     edx, 137h
0x1800061d9  jmp     loc_18000614B
```
