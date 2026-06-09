# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000404c`
- end: `0x1400041ab`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400043a4`

## callees

- `0x1400020dc`
- `0x1400024cc`
- `0x140002910`
- `0x140003d08`
- `0x140003d24`
- `0x14000404c`
- `0x1400055a8`
- `0x1400061ac`
- `0x1400068fc`
- `0x140007074`
- `0x1400071bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400040c9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400040c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004084`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x14000404c  mov     [rsp-8+arg_10], rbx
0x140004051  mov     [rsp-8+arg_18], rdi
0x140004056  push    rbp
0x140004057  lea     rbp, [rsp-170h]
0x14000405f  sub     rsp, 270h
0x140004066  mov     rax, cs:__security_cookie
0x14000406d  xor     rax, rsp
0x140004070  mov     [rbp+170h+var_10], rax
0x140004077  mov     rdi, rdx
0x14000407a  mov     qword ptr [rdx], 0
0x140004081  mov     rbx, rcx
0x140004084  call    cs:__imp_GetCurrentProcessId
0x14000408a  mov     [rsp+270h+var_248], rbx
0x14000408f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004096  mov     r9d, eax
0x140004099  mov     [rsp+270h+var_250], 130h; int
0x1400040a1  mov     edx, 104h; unsigned __int64
0x1400040a6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400040ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400040b0  mov     r9d, 1F0001h; dwDesiredAccess
0x1400040b6  mov     [rsp+270h+var_240], 0
0x1400040bf  xor     r8d, r8d; dwFlags
0x1400040c2  lea     rdx, [rsp+270h+Name]; lpName
0x1400040c7  xor     ecx, ecx; lpMutexAttributes
0x1400040c9  call    cs:__imp_CreateMutexExW
0x1400040cf  mov     rdx, rax
0x1400040d2  lea     rcx, [rsp+270h+var_240]
0x1400040d7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400040dc  cmp     [rsp+270h+var_240], 0
0x1400040e2  jnz     short loc_1400040ED
0x1400040e4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400040e9  mov     ebx, eax
0x1400040eb  jmp     short loc_140004159
0x1400040ed  lea     rdx, [rsp+270h+var_238]
0x1400040f2  lea     rcx, [rsp+270h+var_240]
0x1400040f7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400040fc  lea     rdx, [rsp+270h+var_230]; void **
0x140004101  mov     [rsp+270h+var_230], 0
0x14000410a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000410f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140004114  mov     ebx, eax
0x140004116  test    eax, eax
0x140004118  jns     short loc_14000413A
0x14000411a  mov     edx, 12Eh; void *
0x14000411f  mov     rcx, [rbp+178h]; this
0x140004126  mov     r9d, eax; char *
0x140004129  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000412e  lea     rcx, [rsp+270h+var_238]
0x140004133  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004138  jmp     short loc_140004159
0x14000413a  mov     rcx, [rsp+270h+var_230]
0x14000413f  test    rcx, rcx
0x140004142  jz      short loc_140004189
0x140004144  mov     [rdi], rcx
0x140004147  mov     eax, [rcx]
0x140004149  inc     eax
0x14000414b  mov     [rcx], eax
0x14000414d  lea     rcx, [rsp+270h+var_238]
0x140004152  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004157  xor     ebx, ebx
0x140004159  lea     rcx, [rsp+270h+var_240]
0x14000415e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004163  mov     eax, ebx
0x140004165  mov     rcx, [rbp+170h+var_10]
0x14000416c  xor     rcx, rsp; StackCookie
0x14000416f  call    __security_check_cookie
0x140004174  lea     r11, [rsp+270h+var_s0]
0x14000417c  mov     rbx, [r11+20h]
0x140004180  mov     rdi, [r11+28h]
0x140004184  mov     rsp, r11
0x140004187  pop     rbp
0x140004188  retn
0x140004189  mov     r8, rdi
0x14000418c  lea     rdx, [rsp+270h+var_240]
0x140004191  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004196  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000419b  mov     ebx, eax
0x14000419d  test    eax, eax
0x14000419f  jns     short loc_14000414D
0x1400041a1  mov     edx, 137h
0x1400041a6  jmp     loc_14000411F
```
