# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180136ad8`
- end: `0x180136c37`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180137f60`

## callees

- `0x18011b44c`
- `0x180128ca4`
- `0x180134b70`
- `0x180136788`
- `0x1801367a4`
- `0x180136ad8`
- `0x180138798`
- `0x18013984c`
- `0x18013a2d8`
- `0x18013aaf4`
- `0x18013ac74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180136b55`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180136b55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180136b10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180136b10`

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
0x180136ad8  mov     [rsp-8+arg_10], rbx
0x180136add  mov     [rsp-8+arg_18], rdi
0x180136ae2  push    rbp
0x180136ae3  lea     rbp, [rsp-170h]
0x180136aeb  sub     rsp, 270h
0x180136af2  mov     rax, cs:__security_cookie
0x180136af9  xor     rax, rsp
0x180136afc  mov     [rbp+170h+var_10], rax
0x180136b03  mov     rdi, rdx
0x180136b06  mov     qword ptr [rdx], 0
0x180136b0d  mov     rbx, rcx
0x180136b10  call    cs:__imp_GetCurrentProcessId
0x180136b16  mov     [rsp+270h+var_248], rbx
0x180136b1b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180136b22  mov     r9d, eax
0x180136b25  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180136b2d  mov     edx, 104h; unsigned __int64
0x180136b32  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180136b37  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180136b3c  mov     r9d, 1F0001h; dwDesiredAccess
0x180136b42  mov     [rsp+270h+var_240], 0
0x180136b4b  xor     r8d, r8d; dwFlags
0x180136b4e  lea     rdx, [rsp+270h+Name]; lpName
0x180136b53  xor     ecx, ecx; lpMutexAttributes
0x180136b55  call    cs:__imp_CreateMutexExW
0x180136b5b  mov     rdx, rax
0x180136b5e  lea     rcx, [rsp+270h+var_240]
0x180136b63  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180136b68  cmp     [rsp+270h+var_240], 0
0x180136b6e  jnz     short loc_180136B79
0x180136b70  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180136b75  mov     ebx, eax
0x180136b77  jmp     short loc_180136BE5
0x180136b79  lea     rdx, [rsp+270h+var_238]
0x180136b7e  lea     rcx, [rsp+270h+var_240]
0x180136b83  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180136b88  lea     rdx, [rsp+270h+var_230]; void **
0x180136b8d  mov     [rsp+270h+var_230], 0
0x180136b96  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180136b9b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180136ba0  mov     ebx, eax
0x180136ba2  test    eax, eax
0x180136ba4  jns     short loc_180136BC6
0x180136ba6  mov     edx, 12Eh; void *
0x180136bab  mov     rcx, [rbp+178h]; this
0x180136bb2  mov     r9d, eax; char *
0x180136bb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180136bba  lea     rcx, [rsp+270h+var_238]
0x180136bbf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180136bc4  jmp     short loc_180136BE5
0x180136bc6  mov     rcx, [rsp+270h+var_230]
0x180136bcb  test    rcx, rcx
0x180136bce  jz      short loc_180136C15
0x180136bd0  mov     [rdi], rcx
0x180136bd3  mov     eax, [rcx]
0x180136bd5  inc     eax
0x180136bd7  mov     [rcx], eax
0x180136bd9  lea     rcx, [rsp+270h+var_238]
0x180136bde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180136be3  xor     ebx, ebx
0x180136be5  lea     rcx, [rsp+270h+var_240]
0x180136bea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180136bef  mov     eax, ebx
0x180136bf1  mov     rcx, [rbp+170h+var_10]
0x180136bf8  xor     rcx, rsp; StackCookie
0x180136bfb  call    __security_check_cookie
0x180136c00  lea     r11, [rsp+270h+var_s0]
0x180136c08  mov     rbx, [r11+20h]
0x180136c0c  mov     rdi, [r11+28h]
0x180136c10  mov     rsp, r11
0x180136c13  pop     rbp
0x180136c14  retn
0x180136c15  mov     r8, rdi
0x180136c18  lea     rdx, [rsp+270h+var_240]
0x180136c1d  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180136c22  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180136c27  mov     ebx, eax
0x180136c29  test    eax, eax
0x180136c2b  jns     short loc_180136BD9
0x180136c2d  mov     edx, 137h
0x180136c32  jmp     loc_180136BAB
```
