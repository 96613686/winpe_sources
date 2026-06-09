# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001b2c4`
- end: `0x18001b407`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001b1e0`

## callees

- `0x18001b2c4`
- `0x18001b410`
- `0x18001b628`
- `0x18001b668`
- `0x18001c058`
- `0x1800395bc`
- `0x18003f0b4`
- `0x18003fbe0`
- `0x180040270`
- `0x180043c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001b338`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001b338`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b2fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b2fc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *v4; // rcx
  int Pointer; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  HANDLE Mutex; // [rsp+30h] [rbp-D0h] BYREF
  void *v11; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v12[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v4);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &Mutex,
    v12);
  v11 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v11);
  v7 = Pointer;
  if ( Pointer < 0 )
  {
    v8 = 302;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      120);
    goto LABEL_8;
  }
  v9 = v11;
  if ( v11 )
  {
    *a2 = v11;
    ++*v9;
  }
  else
  {
    Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v7 = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 311;
      goto LABEL_11;
    }
  }
  v7 = 0;
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&Mutex);
  return v7;
}

```

## disassembly

```asm
0x18001b2c4  mov     [rsp-8+arg_10], rbx
0x18001b2c9  mov     [rsp-8+arg_18], rdi
0x18001b2ce  push    rbp
0x18001b2cf  lea     rbp, [rsp-170h]
0x18001b2d7  sub     rsp, 270h
0x18001b2de  mov     rax, cs:__security_cookie
0x18001b2e5  xor     rax, rsp
0x18001b2e8  mov     [rbp+170h+var_10], rax
0x18001b2ef  mov     rdi, rdx
0x18001b2f2  mov     qword ptr [rdx], 0
0x18001b2f9  mov     rbx, rcx
0x18001b2fc  call    cs:__imp_GetCurrentProcessId
0x18001b302  mov     [rsp+270h+var_248], rbx
0x18001b307  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001b30e  mov     r9d, eax
0x18001b311  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001b319  mov     edx, 104h; unsigned __int64
0x18001b31e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001b323  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b328  mov     r9d, 1F0001h; dwDesiredAccess
0x18001b32e  lea     rdx, [rsp+270h+Name]; lpName
0x18001b333  xor     r8d, r8d; dwFlags
0x18001b336  xor     ecx, ecx; lpMutexAttributes
0x18001b338  call    cs:__imp_CreateMutexExW
0x18001b33e  mov     [rsp+270h+var_240], rax
0x18001b343  test    rax, rax
0x18001b346  jnz     short loc_18001B34F
0x18001b348  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001b34d  jmp     short loc_18001B3AE
0x18001b34f  lea     rdx, [rsp+270h+var_230]
0x18001b354  lea     rcx, [rsp+270h+var_240]
0x18001b359  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001b35e  lea     rdx, [rsp+270h+var_238]; void **
0x18001b363  mov     [rsp+270h+var_238], 0
0x18001b36c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001b371  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001b376  mov     ebx, eax
0x18001b378  test    eax, eax
0x18001b37a  jns     short loc_18001B383
0x18001b37c  mov     edx, 12Eh
0x18001b381  jmp     short loc_18001B3EF
0x18001b383  mov     rcx, [rsp+270h+var_238]
0x18001b388  test    rcx, rcx
0x18001b38b  jz      short loc_18001B3D2
0x18001b38d  mov     [rdi], rcx
0x18001b390  mov     eax, [rcx]
0x18001b392  inc     eax
0x18001b394  mov     [rcx], eax
0x18001b396  xor     ebx, ebx
0x18001b398  lea     rcx, [rsp+270h+var_230]
0x18001b39d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b3a2  lea     rcx, [rsp+270h+var_240]
0x18001b3a7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b3ac  mov     eax, ebx
0x18001b3ae  mov     rcx, [rbp+170h+var_10]
0x18001b3b5  xor     rcx, rsp; StackCookie
0x18001b3b8  call    __security_check_cookie
0x18001b3bd  lea     r11, [rsp+270h+var_s0]
0x18001b3c5  mov     rbx, [r11+20h]
0x18001b3c9  mov     rdi, [r11+28h]
0x18001b3cd  mov     rsp, r11
0x18001b3d0  pop     rbp
0x18001b3d1  retn
0x18001b3d2  mov     r8, rdi
0x18001b3d5  lea     rdx, [rsp+270h+var_240]
0x18001b3da  lea     rcx, [rsp+270h+Name]
0x18001b3df  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001b3e4  mov     ebx, eax
0x18001b3e6  test    eax, eax
0x18001b3e8  jns     short loc_18001B396
0x18001b3ea  mov     edx, 137h; void *
0x18001b3ef  mov     rcx, [rbp+178h]; this
0x18001b3f6  lea     r8, aWil; "wil"
0x18001b3fd  mov     r9d, eax; char *
0x18001b400  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b405  jmp     short loc_18001B398
```
