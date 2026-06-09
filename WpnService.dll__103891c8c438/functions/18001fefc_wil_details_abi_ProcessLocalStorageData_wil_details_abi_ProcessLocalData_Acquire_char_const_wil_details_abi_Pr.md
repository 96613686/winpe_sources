# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001fefc`
- end: `0x180020062`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d6e4`

## callees

- `0x1800130a0`
- `0x18001fefc`
- `0x180020110`
- `0x18002012c`
- `0x1800202bc`
- `0x180020344`
- `0x180026200`
- `0x180027294`
- `0x180027634`
- `0x180027c1c`
- `0x180027db4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001ff79`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001ff79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ff34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ff34`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
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
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
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
      (HANDLE *)&v12,
      &v13);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
0x18001fefc  mov     [rsp-8+arg_10], rbx
0x18001ff01  mov     [rsp-8+arg_18], rdi
0x18001ff06  push    rbp
0x18001ff07  lea     rbp, [rsp-170h]
0x18001ff0f  sub     rsp, 270h
0x18001ff16  mov     rax, cs:__security_cookie
0x18001ff1d  xor     rax, rsp
0x18001ff20  mov     [rbp+170h+var_10], rax
0x18001ff27  mov     rdi, rdx
0x18001ff2a  mov     qword ptr [rdx], 0
0x18001ff31  mov     rbx, rcx
0x18001ff34  call    cs:__imp_GetCurrentProcessId
0x18001ff3a  mov     [rsp+270h+var_248], rbx
0x18001ff3f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001ff46  mov     r9d, eax
0x18001ff49  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001ff51  mov     edx, 104h; unsigned __int64
0x18001ff56  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001ff5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ff60  mov     r9d, 1F0001h; dwDesiredAccess
0x18001ff66  mov     [rsp+270h+var_240], 0
0x18001ff6f  xor     r8d, r8d; dwFlags
0x18001ff72  lea     rdx, [rsp+270h+Name]; lpName
0x18001ff77  xor     ecx, ecx; lpMutexAttributes
0x18001ff79  call    cs:__imp_CreateMutexExW
0x18001ff7f  mov     rdx, rax
0x18001ff82  lea     rcx, [rsp+270h+var_240]
0x18001ff87  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001ff8c  cmp     [rsp+270h+var_240], 0
0x18001ff92  jnz     short loc_18001FF9D
0x18001ff94  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001ff99  mov     ebx, eax
0x18001ff9b  jmp     short loc_180020010
0x18001ff9d  lea     rdx, [rsp+270h+var_238]
0x18001ffa2  lea     rcx, [rsp+270h+var_240]
0x18001ffa7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001ffac  lea     rdx, [rsp+270h+var_230]; void **
0x18001ffb1  mov     [rsp+270h+var_230], 0
0x18001ffba  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001ffbf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001ffc4  mov     ebx, eax
0x18001ffc6  test    eax, eax
0x18001ffc8  jns     short loc_18001FFF1
0x18001ffca  mov     edx, 12Eh; void *
0x18001ffcf  mov     rcx, [rbp+178h]; this
0x18001ffd6  lea     r8, aWil; "wil"
0x18001ffdd  mov     r9d, eax; char *
0x18001ffe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffe5  lea     rcx, [rsp+270h+var_238]
0x18001ffea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ffef  jmp     short loc_180020010
0x18001fff1  mov     rcx, [rsp+270h+var_230]
0x18001fff6  test    rcx, rcx
0x18001fff9  jz      short loc_180020040
0x18001fffb  mov     [rdi], rcx
0x18001fffe  mov     eax, [rcx]
0x180020000  inc     eax
0x180020002  mov     [rcx], eax
0x180020004  lea     rcx, [rsp+270h+var_238]
0x180020009  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002000e  xor     ebx, ebx
0x180020010  lea     rcx, [rsp+270h+var_240]
0x180020015  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002001a  mov     eax, ebx
0x18002001c  mov     rcx, [rbp+170h+var_10]
0x180020023  xor     rcx, rsp; StackCookie
0x180020026  call    __security_check_cookie
0x18002002b  lea     r11, [rsp+270h+var_s0]
0x180020033  mov     rbx, [r11+20h]
0x180020037  mov     rdi, [r11+28h]
0x18002003b  mov     rsp, r11
0x18002003e  pop     rbp
0x18002003f  retn
0x180020040  mov     r8, rdi
0x180020043  lea     rdx, [rsp+270h+var_240]
0x180020048  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002004d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180020052  mov     ebx, eax
0x180020054  test    eax, eax
0x180020056  jns     short loc_180020004
0x180020058  mov     edx, 137h
0x18002005d  jmp     loc_18001FFCF
```
