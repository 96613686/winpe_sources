# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180011c30`
- end: `0x180011d8f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012b3c`

## callees

- `0x180011898`
- `0x1800118b4`
- `0x180011c30`
- `0x180012968`
- `0x1800135dc`
- `0x1800147ac`
- `0x180014f58`
- `0x18001532c`
- `0x180016594`
- `0x180016d10`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011cad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011cad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011c68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011c68`

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
0x180011c30  mov     [rsp-8+arg_10], rbx
0x180011c35  mov     [rsp-8+arg_18], rdi
0x180011c3a  push    rbp
0x180011c3b  lea     rbp, [rsp-170h]
0x180011c43  sub     rsp, 270h
0x180011c4a  mov     rax, cs:__security_cookie
0x180011c51  xor     rax, rsp
0x180011c54  mov     [rbp+170h+var_10], rax
0x180011c5b  mov     rdi, rdx
0x180011c5e  mov     qword ptr [rdx], 0
0x180011c65  mov     rbx, rcx
0x180011c68  call    cs:__imp_GetCurrentProcessId
0x180011c6e  mov     [rsp+270h+var_248], rbx
0x180011c73  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180011c7a  mov     r9d, eax
0x180011c7d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180011c85  mov     edx, 104h; unsigned __int64
0x180011c8a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011c8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011c94  mov     r9d, 1F0001h; dwDesiredAccess
0x180011c9a  mov     [rsp+270h+var_240], 0
0x180011ca3  xor     r8d, r8d; dwFlags
0x180011ca6  lea     rdx, [rsp+270h+Name]; lpName
0x180011cab  xor     ecx, ecx; lpMutexAttributes
0x180011cad  call    cs:__imp_CreateMutexExW
0x180011cb3  mov     rdx, rax
0x180011cb6  lea     rcx, [rsp+270h+var_240]
0x180011cbb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180011cc0  cmp     [rsp+270h+var_240], 0
0x180011cc6  jnz     short loc_180011CD1
0x180011cc8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011ccd  mov     ebx, eax
0x180011ccf  jmp     short loc_180011D3D
0x180011cd1  lea     rdx, [rsp+270h+var_238]
0x180011cd6  lea     rcx, [rsp+270h+var_240]
0x180011cdb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180011ce0  lea     rdx, [rsp+270h+var_230]; void **
0x180011ce5  mov     [rsp+270h+var_230], 0
0x180011cee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011cf3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180011cf8  mov     ebx, eax
0x180011cfa  test    eax, eax
0x180011cfc  jns     short loc_180011D1E
0x180011cfe  mov     edx, 12Eh; void *
0x180011d03  mov     rcx, [rbp+178h]; this
0x180011d0a  mov     r9d, eax; char *
0x180011d0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d12  lea     rcx, [rsp+270h+var_238]
0x180011d17  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011d1c  jmp     short loc_180011D3D
0x180011d1e  mov     rcx, [rsp+270h+var_230]
0x180011d23  test    rcx, rcx
0x180011d26  jz      short loc_180011D6D
0x180011d28  mov     [rdi], rcx
0x180011d2b  mov     eax, [rcx]
0x180011d2d  inc     eax
0x180011d2f  mov     [rcx], eax
0x180011d31  lea     rcx, [rsp+270h+var_238]
0x180011d36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011d3b  xor     ebx, ebx
0x180011d3d  lea     rcx, [rsp+270h+var_240]
0x180011d42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011d47  mov     eax, ebx
0x180011d49  mov     rcx, [rbp+170h+var_10]
0x180011d50  xor     rcx, rsp; StackCookie
0x180011d53  call    __security_check_cookie
0x180011d58  lea     r11, [rsp+270h+var_s0]
0x180011d60  mov     rbx, [r11+20h]
0x180011d64  mov     rdi, [r11+28h]
0x180011d68  mov     rsp, r11
0x180011d6b  pop     rbp
0x180011d6c  retn
0x180011d6d  mov     r8, rdi
0x180011d70  lea     rdx, [rsp+270h+var_240]
0x180011d75  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011d7a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180011d7f  mov     ebx, eax
0x180011d81  test    eax, eax
0x180011d83  jns     short loc_180011D31
0x180011d85  mov     edx, 137h
0x180011d8a  jmp     loc_180011D03
```
