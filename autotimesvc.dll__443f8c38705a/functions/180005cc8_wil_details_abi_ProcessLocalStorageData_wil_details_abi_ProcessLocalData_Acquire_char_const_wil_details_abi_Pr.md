# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005cc8`
- end: `0x180005e72`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007004`

## callees

- `0x180002a70`
- `0x18000587c`
- `0x180005898`
- `0x180005cc8`
- `0x180006d08`
- `0x180007e70`
- `0x180009194`
- `0x180009a60`
- `0x180009f48`
- `0x18000a798`
- `0x18000aa8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005d45`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005d45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d00`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v16 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v18 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v18,
    Mutex);
  if ( v18 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v18,
      v19);
    v20 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v20, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v17);
      v11 = LastErrorFailHr;
      v12 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v12, (unsigned int)"wil", (const char *)v11, v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
      goto LABEL_9;
    }
    v13 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v13;
      ++*v13;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v15;
      if ( v15 < 0 )
      {
        v11 = (unsigned int)v15;
        v12 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v18,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180005cc8  mov     [rsp-8+arg_10], rbx
0x180005ccd  mov     [rsp-8+arg_18], rdi
0x180005cd2  push    rbp
0x180005cd3  lea     rbp, [rsp-170h]
0x180005cdb  sub     rsp, 270h
0x180005ce2  mov     rax, cs:__security_cookie
0x180005ce9  xor     rax, rsp
0x180005cec  mov     [rbp+170h+var_10], rax
0x180005cf3  mov     rdi, rdx
0x180005cf6  mov     qword ptr [rdx], 0
0x180005cfd  mov     rbx, rcx
0x180005d00  call    cs:__imp_GetCurrentProcessId
0x180005d06  mov     [rsp+270h+var_248], rbx
0x180005d0b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005d12  mov     r9d, eax
0x180005d15  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180005d1d  mov     edx, 104h; unsigned __int64
0x180005d22  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005d27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005d2c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005d32  mov     [rsp+270h+var_240], 0
0x180005d3b  xor     r8d, r8d; dwFlags
0x180005d3e  lea     rdx, [rsp+270h+Name]; lpName
0x180005d43  xor     ecx, ecx; lpMutexAttributes
0x180005d45  call    cs:__imp_CreateMutexExW
0x180005d4b  mov     rdx, rax
0x180005d4e  lea     rcx, [rsp+270h+var_240]
0x180005d53  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005d58  cmp     [rsp+270h+var_240], 0
0x180005d5e  jnz     short loc_180005D6C
0x180005d60  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005d65  mov     ebx, eax
0x180005d67  jmp     loc_180005E1D
0x180005d6c  lea     rdx, [rsp+270h+var_238]
0x180005d71  lea     rcx, [rsp+270h+var_240]
0x180005d76  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005d7b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180005d80  mov     [rsp+270h+var_230], 0
0x180005d89  lea     rcx, [rsp+270h+Name]; pszSrc
0x180005d8e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005d93  mov     ebx, eax
0x180005d95  test    eax, eax
0x180005d97  jns     short loc_180005DF6
0x180005d99  mov     rcx, [rbp+178h]; this
0x180005da0  lea     r8, aWil; "wil"
0x180005da7  mov     r9d, eax; char *
0x180005daa  mov     edx, 66h ; 'f'; void *
0x180005daf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005db4  mov     rcx, [rbp+178h]; this
0x180005dbb  lea     r8, aWil; "wil"
0x180005dc2  mov     r9d, ebx; char *
0x180005dc5  mov     edx, 6Fh ; 'o'; void *
0x180005dca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005dcf  mov     r9d, ebx; char *
0x180005dd2  mov     edx, 12Eh; void *
0x180005dd7  mov     rcx, [rbp+178h]; this
0x180005dde  lea     r8, aWil; "wil"
0x180005de5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005dea  lea     rcx, [rsp+270h+var_238]
0x180005def  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005df4  jmp     short loc_180005E1D
0x180005df6  mov     rax, [rsp+270h+var_230]
0x180005dfb  lea     rcx, ds:0[rax*4]
0x180005e03  test    rcx, rcx
0x180005e06  jz      short loc_180005E4D
0x180005e08  mov     [rdi], rcx
0x180005e0b  mov     eax, [rcx]
0x180005e0d  inc     eax
0x180005e0f  mov     [rcx], eax
0x180005e11  lea     rcx, [rsp+270h+var_238]
0x180005e16  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e1b  xor     ebx, ebx
0x180005e1d  lea     rcx, [rsp+270h+var_240]
0x180005e22  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e27  mov     eax, ebx
0x180005e29  mov     rcx, [rbp+170h+var_10]
0x180005e30  xor     rcx, rsp; StackCookie
0x180005e33  call    __security_check_cookie
0x180005e38  lea     r11, [rsp+270h+var_s0]
0x180005e40  mov     rbx, [r11+20h]
0x180005e44  mov     rdi, [r11+28h]
0x180005e48  mov     rsp, r11
0x180005e4b  pop     rbp
0x180005e4c  retn
0x180005e4d  mov     r8, rdi
0x180005e50  lea     rdx, [rsp+270h+var_240]
0x180005e55  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005e5a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005e5f  mov     ebx, eax
0x180005e61  test    eax, eax
0x180005e63  jns     short loc_180005E11
0x180005e65  mov     r9d, eax
0x180005e68  mov     edx, 137h
0x180005e6d  jmp     loc_180005DD7
```
