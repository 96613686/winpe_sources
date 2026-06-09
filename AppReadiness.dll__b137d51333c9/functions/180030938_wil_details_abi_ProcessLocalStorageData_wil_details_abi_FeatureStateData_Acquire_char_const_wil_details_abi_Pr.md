# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180030938`
- end: `0x180030a7b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004173c`

## callees

- `0x180005564`
- `0x180009d80`
- `0x180023168`
- `0x180030914`
- `0x180030938`
- `0x180030ca0`
- `0x180036c88`
- `0x18003e210`
- `0x18004274c`
- `0x180043dc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800309ac`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800309ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180030970`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180030970`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
      304);
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
    Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x180030938  mov     [rsp-8+arg_10], rbx
0x18003093d  mov     [rsp-8+arg_18], rdi
0x180030942  push    rbp
0x180030943  lea     rbp, [rsp-170h]
0x18003094b  sub     rsp, 270h
0x180030952  mov     rax, cs:__security_cookie
0x180030959  xor     rax, rsp
0x18003095c  mov     [rbp+170h+var_10], rax
0x180030963  mov     rdi, rdx
0x180030966  mov     qword ptr [rdx], 0
0x18003096d  mov     rbx, rcx
0x180030970  call    cs:__imp_GetCurrentProcessId
0x180030976  mov     [rsp+270h+var_248], rbx
0x18003097b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180030982  mov     r9d, eax
0x180030985  mov     [rsp+270h+var_250], 130h; int
0x18003098d  mov     edx, 104h; unsigned __int64
0x180030992  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180030997  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003099c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800309a2  lea     rdx, [rsp+270h+Name]; lpName
0x1800309a7  xor     r8d, r8d; dwFlags
0x1800309aa  xor     ecx, ecx; lpMutexAttributes
0x1800309ac  call    cs:__imp_CreateMutexExW
0x1800309b2  mov     [rsp+270h+var_240], rax
0x1800309b7  test    rax, rax
0x1800309ba  jnz     short loc_1800309C3
0x1800309bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800309c1  jmp     short loc_180030A22
0x1800309c3  lea     rdx, [rsp+270h+var_230]
0x1800309c8  lea     rcx, [rsp+270h+var_240]
0x1800309cd  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800309d2  lea     rdx, [rsp+270h+var_238]; void **
0x1800309d7  mov     [rsp+270h+var_238], 0
0x1800309e0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800309e5  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800309ea  mov     ebx, eax
0x1800309ec  test    eax, eax
0x1800309ee  jns     short loc_1800309F7
0x1800309f0  mov     edx, 12Eh
0x1800309f5  jmp     short loc_180030A63
0x1800309f7  mov     rcx, [rsp+270h+var_238]
0x1800309fc  test    rcx, rcx
0x1800309ff  jz      short loc_180030A46
0x180030a01  mov     [rdi], rcx
0x180030a04  mov     eax, [rcx]
0x180030a06  inc     eax
0x180030a08  mov     [rcx], eax
0x180030a0a  xor     ebx, ebx
0x180030a0c  lea     rcx, [rsp+270h+var_230]
0x180030a11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030a16  lea     rcx, [rsp+270h+var_240]
0x180030a1b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030a20  mov     eax, ebx
0x180030a22  mov     rcx, [rbp+170h+var_10]
0x180030a29  xor     rcx, rsp; StackCookie
0x180030a2c  call    __security_check_cookie
0x180030a31  lea     r11, [rsp+270h+var_s0]
0x180030a39  mov     rbx, [r11+20h]
0x180030a3d  mov     rdi, [r11+28h]
0x180030a41  mov     rsp, r11
0x180030a44  pop     rbp
0x180030a45  retn
0x180030a46  mov     r8, rdi
0x180030a49  lea     rdx, [rsp+270h+var_240]
0x180030a4e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180030a53  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180030a58  mov     ebx, eax
0x180030a5a  test    eax, eax
0x180030a5c  jns     short loc_180030A0A
0x180030a5e  mov     edx, 137h; void *
0x180030a63  mov     rcx, [rbp+178h]; this
0x180030a6a  lea     r8, aWil; "wil"
0x180030a71  mov     r9d, eax; char *
0x180030a74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030a79  jmp     short loc_180030A0C
```
