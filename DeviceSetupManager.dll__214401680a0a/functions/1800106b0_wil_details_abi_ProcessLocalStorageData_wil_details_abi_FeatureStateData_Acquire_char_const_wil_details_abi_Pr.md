# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800106b0`
- end: `0x180010816`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001dcc4`

## callees

- `0x18000aeb0`
- `0x18001065c`
- `0x1800106b0`
- `0x180010b08`
- `0x180010e84`
- `0x1800112a4`
- `0x18001af70`
- `0x18001d814`
- `0x18001ec14`
- `0x1800204a8`
- `0x180020af4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001072d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001072d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800106e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800106e8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800106b0  mov     [rsp-8+arg_10], rbx
0x1800106b5  mov     [rsp-8+arg_18], rdi
0x1800106ba  push    rbp
0x1800106bb  lea     rbp, [rsp-170h]
0x1800106c3  sub     rsp, 270h
0x1800106ca  mov     rax, cs:__security_cookie
0x1800106d1  xor     rax, rsp
0x1800106d4  mov     [rbp+170h+var_10], rax
0x1800106db  mov     rdi, rdx
0x1800106de  mov     qword ptr [rdx], 0
0x1800106e5  mov     rbx, rcx
0x1800106e8  call    cs:__imp_GetCurrentProcessId
0x1800106ee  mov     [rsp+270h+var_248], rbx
0x1800106f3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800106fa  mov     r9d, eax
0x1800106fd  mov     [rsp+270h+var_250], 130h; int
0x180010705  mov     edx, 104h; unsigned __int64
0x18001070a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001070f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010714  mov     r9d, 1F0001h; dwDesiredAccess
0x18001071a  mov     [rsp+270h+var_240], 0
0x180010723  xor     r8d, r8d; dwFlags
0x180010726  lea     rdx, [rsp+270h+Name]; lpName
0x18001072b  xor     ecx, ecx; lpMutexAttributes
0x18001072d  call    cs:__imp_CreateMutexExW
0x180010733  mov     rdx, rax
0x180010736  lea     rcx, [rsp+270h+var_240]
0x18001073b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180010740  cmp     [rsp+270h+var_240], 0
0x180010746  jnz     short loc_180010751
0x180010748  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001074d  mov     ebx, eax
0x18001074f  jmp     short loc_1800107C4
0x180010751  lea     rdx, [rsp+270h+var_238]
0x180010756  lea     rcx, [rsp+270h+var_240]
0x18001075b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180010760  lea     rdx, [rsp+270h+var_230]; void **
0x180010765  mov     [rsp+270h+var_230], 0
0x18001076e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010773  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180010778  mov     ebx, eax
0x18001077a  test    eax, eax
0x18001077c  jns     short loc_1800107A5
0x18001077e  mov     edx, 12Eh; void *
0x180010783  mov     rcx, [rbp+178h]; this
0x18001078a  lea     r8, aWil; "wil"
0x180010791  mov     r9d, eax; char *
0x180010794  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010799  lea     rcx, [rsp+270h+var_238]
0x18001079e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800107a3  jmp     short loc_1800107C4
0x1800107a5  mov     rcx, [rsp+270h+var_230]
0x1800107aa  test    rcx, rcx
0x1800107ad  jz      short loc_1800107F4
0x1800107af  mov     [rdi], rcx
0x1800107b2  mov     eax, [rcx]
0x1800107b4  inc     eax
0x1800107b6  mov     [rcx], eax
0x1800107b8  lea     rcx, [rsp+270h+var_238]
0x1800107bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800107c2  xor     ebx, ebx
0x1800107c4  lea     rcx, [rsp+270h+var_240]
0x1800107c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800107ce  mov     eax, ebx
0x1800107d0  mov     rcx, [rbp+170h+var_10]
0x1800107d7  xor     rcx, rsp; StackCookie
0x1800107da  call    __security_check_cookie
0x1800107df  lea     r11, [rsp+270h+var_s0]
0x1800107e7  mov     rbx, [r11+20h]
0x1800107eb  mov     rdi, [r11+28h]
0x1800107ef  mov     rsp, r11
0x1800107f2  pop     rbp
0x1800107f3  retn
0x1800107f4  mov     r8, rdi
0x1800107f7  lea     rdx, [rsp+270h+var_240]
0x1800107fc  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010801  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180010806  mov     ebx, eax
0x180010808  test    eax, eax
0x18001080a  jns     short loc_1800107B8
0x18001080c  mov     edx, 137h
0x180010811  jmp     loc_180010783
```
