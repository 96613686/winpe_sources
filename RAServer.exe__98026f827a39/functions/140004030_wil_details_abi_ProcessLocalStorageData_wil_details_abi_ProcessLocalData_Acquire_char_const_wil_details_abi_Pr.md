# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140004030`
- end: `0x14000418f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140006d7c`

## callees

- `0x140003994`
- `0x1400039b0`
- `0x140004030`
- `0x1400067f8`
- `0x140007d8c`
- `0x14000a18c`
- `0x14000aafc`
- `0x14000aea0`
- `0x14000bbf4`
- `0x14000c370`
- `0x140015aa0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1400040ad`
- `KERNEL32!CreateMutexExW` at `0x1400040ad`
- `KERNEL32!GetCurrentProcessId` at `0x140004068`
- `KERNEL32!GetCurrentProcessId` at `0x140004068`

## pseudocode

```c
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
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140004030  mov     [rsp-8+arg_10], rbx
0x140004035  mov     [rsp-8+arg_18], rdi
0x14000403a  push    rbp
0x14000403b  lea     rbp, [rsp-170h]
0x140004043  sub     rsp, 270h
0x14000404a  mov     rax, cs:__security_cookie
0x140004051  xor     rax, rsp
0x140004054  mov     [rbp+170h+var_10], rax
0x14000405b  mov     rdi, rdx
0x14000405e  mov     qword ptr [rdx], 0
0x140004065  mov     rbx, rcx
0x140004068  call    cs:__imp_GetCurrentProcessId
0x14000406e  mov     [rsp+270h+var_248], rbx
0x140004073  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000407a  mov     r9d, eax
0x14000407d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140004085  mov     edx, 104h; unsigned __int64
0x14000408a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000408f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004094  mov     r9d, 1F0001h; dwDesiredAccess
0x14000409a  mov     [rsp+270h+var_240], 0
0x1400040a3  xor     r8d, r8d; dwFlags
0x1400040a6  lea     rdx, [rsp+270h+Name]; lpName
0x1400040ab  xor     ecx, ecx; lpMutexAttributes
0x1400040ad  call    cs:__imp_CreateMutexExW
0x1400040b3  mov     rdx, rax
0x1400040b6  lea     rcx, [rsp+270h+var_240]
0x1400040bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400040c0  cmp     [rsp+270h+var_240], 0
0x1400040c6  jnz     short loc_1400040D1
0x1400040c8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400040cd  mov     ebx, eax
0x1400040cf  jmp     short loc_14000413D
0x1400040d1  lea     rdx, [rsp+270h+var_238]
0x1400040d6  lea     rcx, [rsp+270h+var_240]
0x1400040db  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400040e0  lea     rdx, [rsp+270h+var_230]; void **
0x1400040e5  mov     [rsp+270h+var_230], 0
0x1400040ee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400040f3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1400040f8  mov     ebx, eax
0x1400040fa  test    eax, eax
0x1400040fc  jns     short loc_14000411E
0x1400040fe  mov     edx, 12Eh; void *
0x140004103  mov     rcx, [rbp+178h]; this
0x14000410a  mov     r9d, eax; char *
0x14000410d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004112  lea     rcx, [rsp+270h+var_238]
0x140004117  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000411c  jmp     short loc_14000413D
0x14000411e  mov     rcx, [rsp+270h+var_230]
0x140004123  test    rcx, rcx
0x140004126  jz      short loc_14000416D
0x140004128  mov     [rdi], rcx
0x14000412b  mov     eax, [rcx]
0x14000412d  inc     eax
0x14000412f  mov     [rcx], eax
0x140004131  lea     rcx, [rsp+270h+var_238]
0x140004136  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000413b  xor     ebx, ebx
0x14000413d  lea     rcx, [rsp+270h+var_240]
0x140004142  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004147  mov     eax, ebx
0x140004149  mov     rcx, [rbp+170h+var_10]
0x140004150  xor     rcx, rsp; StackCookie
0x140004153  call    __security_check_cookie
0x140004158  lea     r11, [rsp+270h+var_s0]
0x140004160  mov     rbx, [r11+20h]
0x140004164  mov     rdi, [r11+28h]
0x140004168  mov     rsp, r11
0x14000416b  pop     rbp
0x14000416c  retn
0x14000416d  mov     r8, rdi
0x140004170  lea     rdx, [rsp+270h+var_240]
0x140004175  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000417a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000417f  mov     ebx, eax
0x140004181  test    eax, eax
0x140004183  jns     short loc_140004131
0x140004185  mov     edx, 137h
0x14000418a  jmp     loc_140004103
```
