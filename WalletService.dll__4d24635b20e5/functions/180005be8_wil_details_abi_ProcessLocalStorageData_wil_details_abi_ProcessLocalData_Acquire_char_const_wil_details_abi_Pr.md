# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005be8`
- end: `0x180005d47`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007ed0`

## callees

- `0x180005808`
- `0x180005824`
- `0x180005be8`
- `0x180007c44`
- `0x180008958`
- `0x18000a7b8`
- `0x18000acac`
- `0x18000b120`
- `0x18000ba3c`
- `0x18000bd50`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005c65`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005c65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005c20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005c20`

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
0x180005be8  mov     [rsp-8+arg_10], rbx
0x180005bed  mov     [rsp-8+arg_18], rdi
0x180005bf2  push    rbp
0x180005bf3  lea     rbp, [rsp-170h]
0x180005bfb  sub     rsp, 270h
0x180005c02  mov     rax, cs:__security_cookie
0x180005c09  xor     rax, rsp
0x180005c0c  mov     [rbp+170h+var_10], rax
0x180005c13  mov     rdi, rdx
0x180005c16  mov     qword ptr [rdx], 0
0x180005c1d  mov     rbx, rcx
0x180005c20  call    cs:__imp_GetCurrentProcessId
0x180005c26  mov     [rsp+270h+var_248], rbx
0x180005c2b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005c32  mov     r9d, eax
0x180005c35  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180005c3d  mov     edx, 104h; unsigned __int64
0x180005c42  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005c47  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005c4c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005c52  mov     [rsp+270h+var_240], 0
0x180005c5b  xor     r8d, r8d; dwFlags
0x180005c5e  lea     rdx, [rsp+270h+Name]; lpName
0x180005c63  xor     ecx, ecx; lpMutexAttributes
0x180005c65  call    cs:__imp_CreateMutexExW
0x180005c6b  mov     rdx, rax
0x180005c6e  lea     rcx, [rsp+270h+var_240]
0x180005c73  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005c78  cmp     [rsp+270h+var_240], 0
0x180005c7e  jnz     short loc_180005C89
0x180005c80  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005c85  mov     ebx, eax
0x180005c87  jmp     short loc_180005CF5
0x180005c89  lea     rdx, [rsp+270h+var_238]
0x180005c8e  lea     rcx, [rsp+270h+var_240]
0x180005c93  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005c98  lea     rdx, [rsp+270h+var_230]; void **
0x180005c9d  mov     [rsp+270h+var_230], 0
0x180005ca6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005cab  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005cb0  mov     ebx, eax
0x180005cb2  test    eax, eax
0x180005cb4  jns     short loc_180005CD6
0x180005cb6  mov     edx, 12Eh; void *
0x180005cbb  mov     rcx, [rbp+178h]; this
0x180005cc2  mov     r9d, eax; char *
0x180005cc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005cca  lea     rcx, [rsp+270h+var_238]
0x180005ccf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005cd4  jmp     short loc_180005CF5
0x180005cd6  mov     rcx, [rsp+270h+var_230]
0x180005cdb  test    rcx, rcx
0x180005cde  jz      short loc_180005D25
0x180005ce0  mov     [rdi], rcx
0x180005ce3  mov     eax, [rcx]
0x180005ce5  inc     eax
0x180005ce7  mov     [rcx], eax
0x180005ce9  lea     rcx, [rsp+270h+var_238]
0x180005cee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005cf3  xor     ebx, ebx
0x180005cf5  lea     rcx, [rsp+270h+var_240]
0x180005cfa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005cff  mov     eax, ebx
0x180005d01  mov     rcx, [rbp+170h+var_10]
0x180005d08  xor     rcx, rsp; StackCookie
0x180005d0b  call    __security_check_cookie
0x180005d10  lea     r11, [rsp+270h+var_s0]
0x180005d18  mov     rbx, [r11+20h]
0x180005d1c  mov     rdi, [r11+28h]
0x180005d20  mov     rsp, r11
0x180005d23  pop     rbp
0x180005d24  retn
0x180005d25  mov     r8, rdi
0x180005d28  lea     rdx, [rsp+270h+var_240]
0x180005d2d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005d32  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005d37  mov     ebx, eax
0x180005d39  test    eax, eax
0x180005d3b  jns     short loc_180005CE9
0x180005d3d  mov     edx, 137h
0x180005d42  jmp     loc_180005CBB
```
