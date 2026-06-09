# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180030afc`
- end: `0x180030c3f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180042258`

## callees

- `0x180005564`
- `0x180009d80`
- `0x180023168`
- `0x180030914`
- `0x180030afc`
- `0x180030ca0`
- `0x180036c88`
- `0x18003e210`
- `0x18004261c`
- `0x180043dc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180030b70`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180030b70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180030b34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180030b34`

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
0x180030afc  mov     [rsp-8+arg_10], rbx
0x180030b01  mov     [rsp-8+arg_18], rdi
0x180030b06  push    rbp
0x180030b07  lea     rbp, [rsp-170h]
0x180030b0f  sub     rsp, 270h
0x180030b16  mov     rax, cs:__security_cookie
0x180030b1d  xor     rax, rsp
0x180030b20  mov     [rbp+170h+var_10], rax
0x180030b27  mov     rdi, rdx
0x180030b2a  mov     qword ptr [rdx], 0
0x180030b31  mov     rbx, rcx
0x180030b34  call    cs:__imp_GetCurrentProcessId
0x180030b3a  mov     [rsp+270h+var_248], rbx
0x180030b3f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180030b46  mov     r9d, eax
0x180030b49  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180030b51  mov     edx, 104h; unsigned __int64
0x180030b56  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180030b5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030b60  mov     r9d, 1F0001h; dwDesiredAccess
0x180030b66  lea     rdx, [rsp+270h+Name]; lpName
0x180030b6b  xor     r8d, r8d; dwFlags
0x180030b6e  xor     ecx, ecx; lpMutexAttributes
0x180030b70  call    cs:__imp_CreateMutexExW
0x180030b76  mov     [rsp+270h+var_240], rax
0x180030b7b  test    rax, rax
0x180030b7e  jnz     short loc_180030B87
0x180030b80  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180030b85  jmp     short loc_180030BE6
0x180030b87  lea     rdx, [rsp+270h+var_230]
0x180030b8c  lea     rcx, [rsp+270h+var_240]
0x180030b91  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180030b96  lea     rdx, [rsp+270h+var_238]; void **
0x180030b9b  mov     [rsp+270h+var_238], 0
0x180030ba4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180030ba9  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180030bae  mov     ebx, eax
0x180030bb0  test    eax, eax
0x180030bb2  jns     short loc_180030BBB
0x180030bb4  mov     edx, 12Eh
0x180030bb9  jmp     short loc_180030C27
0x180030bbb  mov     rcx, [rsp+270h+var_238]
0x180030bc0  test    rcx, rcx
0x180030bc3  jz      short loc_180030C0A
0x180030bc5  mov     [rdi], rcx
0x180030bc8  mov     eax, [rcx]
0x180030bca  inc     eax
0x180030bcc  mov     [rcx], eax
0x180030bce  xor     ebx, ebx
0x180030bd0  lea     rcx, [rsp+270h+var_230]
0x180030bd5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030bda  lea     rcx, [rsp+270h+var_240]
0x180030bdf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030be4  mov     eax, ebx
0x180030be6  mov     rcx, [rbp+170h+var_10]
0x180030bed  xor     rcx, rsp; StackCookie
0x180030bf0  call    __security_check_cookie
0x180030bf5  lea     r11, [rsp+270h+var_s0]
0x180030bfd  mov     rbx, [r11+20h]
0x180030c01  mov     rdi, [r11+28h]
0x180030c05  mov     rsp, r11
0x180030c08  pop     rbp
0x180030c09  retn
0x180030c0a  mov     r8, rdi
0x180030c0d  lea     rdx, [rsp+270h+var_240]
0x180030c12  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180030c17  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180030c1c  mov     ebx, eax
0x180030c1e  test    eax, eax
0x180030c20  jns     short loc_180030BCE
0x180030c22  mov     edx, 137h; void *
0x180030c27  mov     rcx, [rbp+178h]; this
0x180030c2e  lea     r8, aWil; "wil"
0x180030c35  mov     r9d, eax; char *
0x180030c38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030c3d  jmp     short loc_180030BD0
```
