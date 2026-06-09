# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800245a4`
- end: `0x18002470a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180025698`

## callees

- `0x18001364c`
- `0x18001bd18`
- `0x18001be80`
- `0x18001becc`
- `0x180024144`
- `0x180024160`
- `0x1800245a4`
- `0x180027ab0`
- `0x180028394`
- `0x1800285d8`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180024621`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180024621`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800245dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800245dc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x1800245a4  mov     [rsp-8+arg_10], rbx
0x1800245a9  mov     [rsp-8+arg_18], rdi
0x1800245ae  push    rbp
0x1800245af  lea     rbp, [rsp-170h]
0x1800245b7  sub     rsp, 270h
0x1800245be  mov     rax, cs:__security_cookie
0x1800245c5  xor     rax, rsp
0x1800245c8  mov     [rbp+170h+var_10], rax
0x1800245cf  mov     rdi, rdx
0x1800245d2  mov     qword ptr [rdx], 0
0x1800245d9  mov     rbx, rcx
0x1800245dc  call    cs:__imp_GetCurrentProcessId
0x1800245e2  mov     [rsp+270h+var_248], rbx
0x1800245e7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800245ee  mov     r9d, eax
0x1800245f1  mov     [rsp+270h+var_250], 130h; int
0x1800245f9  mov     edx, 104h; unsigned __int64
0x1800245fe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180024603  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024608  mov     r9d, 1F0001h; dwDesiredAccess
0x18002460e  mov     [rsp+270h+var_240], 0
0x180024617  xor     r8d, r8d; dwFlags
0x18002461a  lea     rdx, [rsp+270h+Name]; lpName
0x18002461f  xor     ecx, ecx; lpMutexAttributes
0x180024621  call    cs:__imp_CreateMutexExW
0x180024627  mov     rdx, rax
0x18002462a  lea     rcx, [rsp+270h+var_240]
0x18002462f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180024634  cmp     [rsp+270h+var_240], 0
0x18002463a  jnz     short loc_180024645
0x18002463c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180024641  mov     ebx, eax
0x180024643  jmp     short loc_1800246B8
0x180024645  lea     rdx, [rsp+270h+var_238]
0x18002464a  lea     rcx, [rsp+270h+var_240]
0x18002464f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180024654  lea     rdx, [rsp+270h+var_230]; void **
0x180024659  mov     [rsp+270h+var_230], 0
0x180024662  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180024667  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002466c  mov     ebx, eax
0x18002466e  test    eax, eax
0x180024670  jns     short loc_180024699
0x180024672  mov     edx, 12Eh; void *
0x180024677  mov     rcx, [rbp+178h]; this
0x18002467e  lea     r8, aWil; "wil"
0x180024685  mov     r9d, eax; char *
0x180024688  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002468d  lea     rcx, [rsp+270h+var_238]
0x180024692  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180024697  jmp     short loc_1800246B8
0x180024699  mov     rcx, [rsp+270h+var_230]
0x18002469e  test    rcx, rcx
0x1800246a1  jz      short loc_1800246E8
0x1800246a3  mov     [rdi], rcx
0x1800246a6  mov     eax, [rcx]
0x1800246a8  inc     eax
0x1800246aa  mov     [rcx], eax
0x1800246ac  lea     rcx, [rsp+270h+var_238]
0x1800246b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800246b6  xor     ebx, ebx
0x1800246b8  lea     rcx, [rsp+270h+var_240]
0x1800246bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800246c2  mov     eax, ebx
0x1800246c4  mov     rcx, [rbp+170h+var_10]
0x1800246cb  xor     rcx, rsp; StackCookie
0x1800246ce  call    __security_check_cookie
0x1800246d3  lea     r11, [rsp+270h+var_s0]
0x1800246db  mov     rbx, [r11+20h]
0x1800246df  mov     rdi, [r11+28h]
0x1800246e3  mov     rsp, r11
0x1800246e6  pop     rbp
0x1800246e7  retn
0x1800246e8  mov     r8, rdi
0x1800246eb  lea     rdx, [rsp+270h+var_240]
0x1800246f0  lea     rcx, [rsp+270h+Name]
0x1800246f5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800246fa  mov     ebx, eax
0x1800246fc  test    eax, eax
0x1800246fe  jns     short loc_1800246AC
0x180024700  mov     edx, 137h
0x180024705  jmp     loc_180024677
```
