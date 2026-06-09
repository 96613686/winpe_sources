# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140010998`
- end: `0x140010afe`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140019cb0`

## callees

- `0x140005f30`
- `0x14000ee0c`
- `0x14000ee28`
- `0x140010998`
- `0x1400199b8`
- `0x14001ad10`
- `0x14001f3d4`
- `0x140026134`
- `0x1400267d8`
- `0x14002adac`
- `0x14002c37c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400109d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400109d0`
- `KERNEL32!CreateMutexExW` at `0x140010a15`
- `KERNEL32!CreateMutexExW` at `0x140010a15`

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
0x140010998  mov     [rsp-8+arg_10], rbx
0x14001099d  mov     [rsp-8+arg_18], rdi
0x1400109a2  push    rbp
0x1400109a3  lea     rbp, [rsp-170h]
0x1400109ab  sub     rsp, 270h
0x1400109b2  mov     rax, cs:__security_cookie
0x1400109b9  xor     rax, rsp
0x1400109bc  mov     [rbp+170h+var_10], rax
0x1400109c3  mov     rdi, rdx
0x1400109c6  mov     qword ptr [rdx], 0
0x1400109cd  mov     rbx, rcx
0x1400109d0  call    cs:__imp_GetCurrentProcessId
0x1400109d6  mov     [rsp+270h+var_248], rbx
0x1400109db  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400109e2  mov     r9d, eax
0x1400109e5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1400109ed  mov     edx, 104h; unsigned __int64
0x1400109f2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400109f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400109fc  mov     r9d, 1F0001h; dwDesiredAccess
0x140010a02  mov     [rsp+270h+var_240], 0
0x140010a0b  xor     r8d, r8d; dwFlags
0x140010a0e  lea     rdx, [rsp+270h+Name]; lpName
0x140010a13  xor     ecx, ecx; lpMutexAttributes
0x140010a15  call    cs:__imp_CreateMutexExW
0x140010a1b  mov     rdx, rax
0x140010a1e  lea     rcx, [rsp+270h+var_240]
0x140010a23  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140010a28  cmp     [rsp+270h+var_240], 0
0x140010a2e  jnz     short loc_140010A39
0x140010a30  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140010a35  mov     ebx, eax
0x140010a37  jmp     short loc_140010AAC
0x140010a39  lea     rdx, [rsp+270h+var_238]
0x140010a3e  lea     rcx, [rsp+270h+var_240]
0x140010a43  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140010a48  lea     rdx, [rsp+270h+var_230]; void **
0x140010a4d  mov     [rsp+270h+var_230], 0
0x140010a56  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140010a5b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140010a60  mov     ebx, eax
0x140010a62  test    eax, eax
0x140010a64  jns     short loc_140010A8D
0x140010a66  mov     edx, 12Eh; void *
0x140010a6b  mov     rcx, [rbp+178h]; this
0x140010a72  lea     r8, aWil; "wil"
0x140010a79  mov     r9d, eax; char *
0x140010a7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010a81  lea     rcx, [rsp+270h+var_238]
0x140010a86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140010a8b  jmp     short loc_140010AAC
0x140010a8d  mov     rcx, [rsp+270h+var_230]
0x140010a92  test    rcx, rcx
0x140010a95  jz      short loc_140010ADC
0x140010a97  mov     [rdi], rcx
0x140010a9a  mov     eax, [rcx]
0x140010a9c  inc     eax
0x140010a9e  mov     [rcx], eax
0x140010aa0  lea     rcx, [rsp+270h+var_238]
0x140010aa5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140010aaa  xor     ebx, ebx
0x140010aac  lea     rcx, [rsp+270h+var_240]
0x140010ab1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140010ab6  mov     eax, ebx
0x140010ab8  mov     rcx, [rbp+170h+var_10]
0x140010abf  xor     rcx, rsp; StackCookie
0x140010ac2  call    __security_check_cookie
0x140010ac7  lea     r11, [rsp+270h+var_s0]
0x140010acf  mov     rbx, [r11+20h]
0x140010ad3  mov     rdi, [r11+28h]
0x140010ad7  mov     rsp, r11
0x140010ada  pop     rbp
0x140010adb  retn
0x140010adc  mov     r8, rdi
0x140010adf  lea     rdx, [rsp+270h+var_240]
0x140010ae4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140010ae9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140010aee  mov     ebx, eax
0x140010af0  test    eax, eax
0x140010af2  jns     short loc_140010AA0
0x140010af4  mov     edx, 137h
0x140010af9  jmp     loc_140010A6B
```
