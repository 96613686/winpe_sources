# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180025118`
- end: `0x180025280`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `360`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180027a18`

## callees

- `0x180019e0c`
- `0x18001ef6c`
- `0x18001f650`
- `0x180024df8`
- `0x180024e14`
- `0x180025118`
- `0x18002846c`
- `0x180028ae4`
- `0x1800293b8`
- `0x180029c64`
- `0x180029d54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025150`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025150`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180025195`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180025195`

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
    v13 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180025118  mov     [rsp-8+arg_10], rbx
0x18002511d  mov     [rsp-8+arg_18], rdi
0x180025122  push    rbp
0x180025123  lea     rbp, [rsp-170h]
0x18002512b  sub     rsp, 270h
0x180025132  mov     rax, cs:__security_cookie
0x180025139  xor     rax, rsp
0x18002513c  mov     [rbp+170h+var_10], rax
0x180025143  mov     rdi, rdx
0x180025146  mov     qword ptr [rdx], 0
0x18002514d  mov     rbx, rcx
0x180025150  call    cs:__imp_GetCurrentProcessId
0x180025156  mov     [rsp+270h+var_248], rbx
0x18002515b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180025162  mov     r9d, eax
0x180025165  mov     [rsp+270h+var_250], 130h; int
0x18002516d  mov     edx, 104h; unsigned __int64
0x180025172  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025177  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002517c  mov     r9d, 1F0001h; dwDesiredAccess
0x180025182  mov     [rsp+270h+var_240], 0
0x18002518b  xor     r8d, r8d; dwFlags
0x18002518e  lea     rdx, [rsp+270h+Name]; lpName
0x180025193  xor     ecx, ecx; lpMutexAttributes
0x180025195  call    cs:__imp_CreateMutexExW
0x18002519b  mov     rdx, rax
0x18002519e  lea     rcx, [rsp+270h+var_240]
0x1800251a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800251a8  cmp     [rsp+270h+var_240], 0
0x1800251ae  jnz     short loc_1800251B9
0x1800251b0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800251b5  mov     ebx, eax
0x1800251b7  jmp     short loc_18002522E
0x1800251b9  lea     rdx, [rsp+270h+var_238]
0x1800251be  mov     [rsp+270h+var_238], 0
0x1800251c7  lea     rcx, [rsp+270h+var_240]
0x1800251cc  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800251d1  lea     rdx, [rsp+270h+var_230]; void **
0x1800251d6  mov     [rsp+270h+var_230], 0
0x1800251df  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800251e4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800251e9  mov     ebx, eax
0x1800251eb  test    eax, eax
0x1800251ed  jns     short loc_18002520F
0x1800251ef  mov     edx, 12Eh; void *
0x1800251f4  mov     rcx, [rbp+178h]; this
0x1800251fb  mov     r9d, eax; char *
0x1800251fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025203  lea     rcx, [rsp+270h+var_238]
0x180025208  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002520d  jmp     short loc_18002522E
0x18002520f  mov     rcx, [rsp+270h+var_230]
0x180025214  test    rcx, rcx
0x180025217  jz      short loc_18002525E
0x180025219  mov     [rdi], rcx
0x18002521c  mov     eax, [rcx]
0x18002521e  inc     eax
0x180025220  mov     [rcx], eax
0x180025222  lea     rcx, [rsp+270h+var_238]
0x180025227  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002522c  xor     ebx, ebx
0x18002522e  lea     rcx, [rsp+270h+var_240]
0x180025233  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025238  mov     eax, ebx
0x18002523a  mov     rcx, [rbp+170h+var_10]
0x180025241  xor     rcx, rsp; StackCookie
0x180025244  call    __security_check_cookie
0x180025249  lea     r11, [rsp+270h+var_s0]
0x180025251  mov     rbx, [r11+20h]
0x180025255  mov     rdi, [r11+28h]
0x180025259  mov     rsp, r11
0x18002525c  pop     rbp
0x18002525d  retn
0x18002525e  mov     r8, rdi
0x180025261  lea     rdx, [rsp+270h+var_240]
0x180025266  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002526b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180025270  mov     ebx, eax
0x180025272  test    eax, eax
0x180025274  jns     short loc_180025222
0x180025276  mov     edx, 137h
0x18002527b  jmp     loc_1800251F4
```
