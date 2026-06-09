# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800170ec`
- end: `0x180017252`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001858c`

## callees

- `0x18000c6e0`
- `0x18001024c`
- `0x180010268`
- `0x180010ca8`
- `0x180011ea4`
- `0x1800124b4`
- `0x18001265c`
- `0x180012ae0`
- `0x180012f30`
- `0x1800170ec`
- `0x180018c18`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180017124`
- `KERNEL32!GetCurrentProcessId` at `0x180017124`
- `KERNEL32!CreateMutexExW` at `0x180017169`
- `KERNEL32!CreateMutexExW` at `0x180017169`

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
0x1800170ec  mov     [rsp-8+arg_10], rbx
0x1800170f1  mov     [rsp-8+arg_18], rdi
0x1800170f6  push    rbp
0x1800170f7  lea     rbp, [rsp-170h]
0x1800170ff  sub     rsp, 270h
0x180017106  mov     rax, cs:__security_cookie
0x18001710d  xor     rax, rsp
0x180017110  mov     [rbp+170h+var_10], rax
0x180017117  mov     rdi, rdx
0x18001711a  mov     qword ptr [rdx], 0
0x180017121  mov     rbx, rcx
0x180017124  call    cs:__imp_GetCurrentProcessId
0x18001712a  mov     [rsp+270h+var_248], rbx
0x18001712f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180017136  mov     r9d, eax
0x180017139  mov     [rsp+270h+var_250], 130h; int
0x180017141  mov     edx, 104h; unsigned __int64
0x180017146  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001714b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017150  mov     r9d, 1F0001h; dwDesiredAccess
0x180017156  mov     [rsp+270h+var_240], 0
0x18001715f  xor     r8d, r8d; dwFlags
0x180017162  lea     rdx, [rsp+270h+Name]; lpName
0x180017167  xor     ecx, ecx; lpMutexAttributes
0x180017169  call    cs:__imp_CreateMutexExW
0x18001716f  mov     rdx, rax
0x180017172  lea     rcx, [rsp+270h+var_240]
0x180017177  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001717c  cmp     [rsp+270h+var_240], 0
0x180017182  jnz     short loc_18001718D
0x180017184  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017189  mov     ebx, eax
0x18001718b  jmp     short loc_180017200
0x18001718d  lea     rdx, [rsp+270h+var_238]
0x180017192  lea     rcx, [rsp+270h+var_240]
0x180017197  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001719c  lea     rdx, [rsp+270h+var_230]; void **
0x1800171a1  mov     [rsp+270h+var_230], 0
0x1800171aa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800171af  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800171b4  mov     ebx, eax
0x1800171b6  test    eax, eax
0x1800171b8  jns     short loc_1800171E1
0x1800171ba  mov     edx, 12Eh; void *
0x1800171bf  mov     rcx, [rbp+178h]; this
0x1800171c6  lea     r8, aWil; "wil"
0x1800171cd  mov     r9d, eax; char *
0x1800171d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800171d5  lea     rcx, [rsp+270h+var_238]
0x1800171da  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800171df  jmp     short loc_180017200
0x1800171e1  mov     rcx, [rsp+270h+var_230]
0x1800171e6  test    rcx, rcx
0x1800171e9  jz      short loc_180017230
0x1800171eb  mov     [rdi], rcx
0x1800171ee  mov     eax, [rcx]
0x1800171f0  inc     eax
0x1800171f2  mov     [rcx], eax
0x1800171f4  lea     rcx, [rsp+270h+var_238]
0x1800171f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800171fe  xor     ebx, ebx
0x180017200  lea     rcx, [rsp+270h+var_240]
0x180017205  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001720a  mov     eax, ebx
0x18001720c  mov     rcx, [rbp+170h+var_10]
0x180017213  xor     rcx, rsp; StackCookie
0x180017216  call    __security_check_cookie
0x18001721b  lea     r11, [rsp+270h+var_s0]
0x180017223  mov     rbx, [r11+20h]
0x180017227  mov     rdi, [r11+28h]
0x18001722b  mov     rsp, r11
0x18001722e  pop     rbp
0x18001722f  retn
0x180017230  mov     r8, rdi
0x180017233  lea     rdx, [rsp+270h+var_240]
0x180017238  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001723d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180017242  mov     ebx, eax
0x180017244  test    eax, eax
0x180017246  jns     short loc_1800171F4
0x180017248  mov     edx, 137h
0x18001724d  jmp     loc_1800171BF
```
