# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001e2a8`
- end: `0x18001e41c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180020f14`

## callees

- `0x180007c78`
- `0x180010400`
- `0x180017c70`
- `0x180018410`
- `0x180018e14`
- `0x18001a710`
- `0x18001abcc`
- `0x18001ae20`
- `0x18001e2a8`
- `0x1800214f0`
- `0x180042950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001e325`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001e325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e2dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e2dd`

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
      v12,
      0,
      0xFFFFFFFFLL);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 299;
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
      *(_DWORD *)*a2 = *v9 + 1;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 308;
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
0x18001e2a8  mov     [rsp-8+arg_10], rbx
0x18001e2ad  mov     [rsp-8+arg_18], rdi
0x18001e2b2  push    rbp
0x18001e2b3  lea     rbp, [rsp-170h]
0x18001e2bb  sub     rsp, 270h
0x18001e2c2  mov     rax, cs:__security_cookie
0x18001e2c9  xor     rax, rsp
0x18001e2cc  mov     [rbp+170h+var_10], rax
0x18001e2d3  and     qword ptr [rdx], 0
0x18001e2d7  mov     rdi, rdx
0x18001e2da  mov     rbx, rcx
0x18001e2dd  call    cs:__imp_GetCurrentProcessId
0x18001e2e4  nop     dword ptr [rax+rax+00h]
0x18001e2e9  mov     [rsp+270h+var_248], rbx
0x18001e2ee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001e2f5  mov     r9d, eax
0x18001e2f8  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001e300  mov     edx, 104h; unsigned __int64
0x18001e305  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001e30a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e30f  and     [rsp+270h+var_240], 0
0x18001e315  lea     rdx, [rsp+270h+Name]; lpName
0x18001e31a  mov     r9d, 1F0001h; dwDesiredAccess
0x18001e320  xor     r8d, r8d; dwFlags
0x18001e323  xor     ecx, ecx; lpMutexAttributes
0x18001e325  call    cs:__imp_CreateMutexExW
0x18001e32c  nop     dword ptr [rax+rax+00h]
0x18001e331  mov     rdx, rax
0x18001e334  lea     rcx, [rsp+270h+var_240]
0x18001e339  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001e33e  cmp     [rsp+270h+var_240], 0
0x18001e344  jnz     short loc_18001E34F
0x18001e346  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001e34b  mov     ebx, eax
0x18001e34d  jmp     short loc_18001E3C9
0x18001e34f  or      r9d, 0FFFFFFFFh
0x18001e353  lea     rdx, [rsp+270h+var_238]
0x18001e358  xor     r8d, r8d
0x18001e35b  lea     rcx, [rsp+270h+var_240]
0x18001e360  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001e365  and     [rsp+270h+var_230], 0
0x18001e36b  lea     rdx, [rsp+270h+var_230]; void **
0x18001e370  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001e375  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001e37a  mov     ebx, eax
0x18001e37c  test    eax, eax
0x18001e37e  jns     short loc_18001E3A7
0x18001e380  mov     edx, 12Bh; void *
0x18001e385  mov     rcx, [rbp+178h]; this
0x18001e38c  lea     r8, aWil; "wil"
0x18001e393  mov     r9d, eax; char *
0x18001e396  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e39b  lea     rcx, [rsp+270h+var_238]
0x18001e3a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e3a5  jmp     short loc_18001E3C9
0x18001e3a7  mov     rcx, [rsp+270h+var_230]
0x18001e3ac  test    rcx, rcx
0x18001e3af  jz      short loc_18001E3FA
0x18001e3b1  mov     [rdi], rcx
0x18001e3b4  mov     ecx, [rcx]
0x18001e3b6  mov     rax, [rdi]
0x18001e3b9  inc     ecx
0x18001e3bb  mov     [rax], ecx
0x18001e3bd  lea     rcx, [rsp+270h+var_238]
0x18001e3c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e3c7  xor     ebx, ebx
0x18001e3c9  lea     rcx, [rsp+270h+var_240]
0x18001e3ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e3d3  mov     eax, ebx
0x18001e3d5  mov     rcx, [rbp+170h+var_10]
0x18001e3dc  xor     rcx, rsp; StackCookie
0x18001e3df  call    __security_check_cookie
0x18001e3e4  lea     r11, [rsp+270h+var_s0]
0x18001e3ec  mov     rbx, [r11+20h]
0x18001e3f0  mov     rdi, [r11+28h]
0x18001e3f4  mov     rsp, r11
0x18001e3f7  pop     rbp
0x18001e3f8  retn
0x18001e3fa  mov     r8, rdi
0x18001e3fd  lea     rdx, [rsp+270h+var_240]
0x18001e402  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001e407  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001e40c  mov     ebx, eax
0x18001e40e  test    eax, eax
0x18001e410  jns     short loc_18001E3BD
0x18001e412  mov     edx, 134h
0x18001e417  jmp     loc_18001E385
```
