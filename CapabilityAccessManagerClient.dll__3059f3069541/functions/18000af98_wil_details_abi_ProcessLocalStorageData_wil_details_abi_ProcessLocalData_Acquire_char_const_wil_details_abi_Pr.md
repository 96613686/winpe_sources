# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000af98`
- end: `0x18000b0fe`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c2d0`

## callees

- `0x180003c80`
- `0x18000aa7c`
- `0x18000aa98`
- `0x18000af98`
- `0x18000bf68`
- `0x18000cd5c`
- `0x18000e21c`
- `0x18000ea70`
- `0x18000f01c`
- `0x18000fa64`
- `0x18000fda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b015`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000afd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000afd0`

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
0x18000af98  mov     [rsp-8+arg_10], rbx
0x18000af9d  mov     [rsp-8+arg_18], rdi
0x18000afa2  push    rbp
0x18000afa3  lea     rbp, [rsp-170h]
0x18000afab  sub     rsp, 270h
0x18000afb2  mov     rax, cs:__security_cookie
0x18000afb9  xor     rax, rsp
0x18000afbc  mov     [rbp+170h+var_10], rax
0x18000afc3  mov     rdi, rdx
0x18000afc6  mov     qword ptr [rdx], 0
0x18000afcd  mov     rbx, rcx
0x18000afd0  call    cs:__imp_GetCurrentProcessId
0x18000afd6  mov     [rsp+270h+var_248], rbx
0x18000afdb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000afe2  mov     r9d, eax
0x18000afe5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000afed  mov     edx, 104h; unsigned __int64
0x18000aff2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000aff7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000affc  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b002  mov     [rsp+270h+var_240], 0
0x18000b00b  xor     r8d, r8d; dwFlags
0x18000b00e  lea     rdx, [rsp+270h+Name]; lpName
0x18000b013  xor     ecx, ecx; lpMutexAttributes
0x18000b015  call    cs:__imp_CreateMutexExW
0x18000b01b  mov     rdx, rax
0x18000b01e  lea     rcx, [rsp+270h+var_240]
0x18000b023  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000b028  cmp     [rsp+270h+var_240], 0
0x18000b02e  jnz     short loc_18000B039
0x18000b030  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b035  mov     ebx, eax
0x18000b037  jmp     short loc_18000B0AC
0x18000b039  lea     rdx, [rsp+270h+var_238]
0x18000b03e  lea     rcx, [rsp+270h+var_240]
0x18000b043  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000b048  lea     rdx, [rsp+270h+var_230]; void **
0x18000b04d  mov     [rsp+270h+var_230], 0
0x18000b056  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b05b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000b060  mov     ebx, eax
0x18000b062  test    eax, eax
0x18000b064  jns     short loc_18000B08D
0x18000b066  mov     edx, 12Eh; void *
0x18000b06b  mov     rcx, [rbp+178h]; this
0x18000b072  lea     r8, aWil; "wil"
0x18000b079  mov     r9d, eax; char *
0x18000b07c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b081  lea     rcx, [rsp+270h+var_238]
0x18000b086  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b08b  jmp     short loc_18000B0AC
0x18000b08d  mov     rcx, [rsp+270h+var_230]
0x18000b092  test    rcx, rcx
0x18000b095  jz      short loc_18000B0DC
0x18000b097  mov     [rdi], rcx
0x18000b09a  mov     eax, [rcx]
0x18000b09c  inc     eax
0x18000b09e  mov     [rcx], eax
0x18000b0a0  lea     rcx, [rsp+270h+var_238]
0x18000b0a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b0aa  xor     ebx, ebx
0x18000b0ac  lea     rcx, [rsp+270h+var_240]
0x18000b0b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b0b6  mov     eax, ebx
0x18000b0b8  mov     rcx, [rbp+170h+var_10]
0x18000b0bf  xor     rcx, rsp; StackCookie
0x18000b0c2  call    __security_check_cookie
0x18000b0c7  lea     r11, [rsp+270h+var_s0]
0x18000b0cf  mov     rbx, [r11+20h]
0x18000b0d3  mov     rdi, [r11+28h]
0x18000b0d7  mov     rsp, r11
0x18000b0da  pop     rbp
0x18000b0db  retn
0x18000b0dc  mov     r8, rdi
0x18000b0df  lea     rdx, [rsp+270h+var_240]
0x18000b0e4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b0e9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000b0ee  mov     ebx, eax
0x18000b0f0  test    eax, eax
0x18000b0f2  jns     short loc_18000B0A0
0x18000b0f4  mov     edx, 137h
0x18000b0f9  jmp     loc_18000B06B
```
