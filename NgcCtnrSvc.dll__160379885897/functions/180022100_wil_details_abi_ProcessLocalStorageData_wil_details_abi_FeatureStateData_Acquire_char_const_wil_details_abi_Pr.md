# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180022100`
- end: `0x180022273`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002f8d8`

## callees

- `0x18001505c`
- `0x18001aecc`
- `0x180022100`
- `0x180022510`
- `0x180023278`
- `0x180023534`
- `0x180023568`
- `0x18002c640`
- `0x18002ed9c`
- `0x18002fe84`
- `0x18003138c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022183`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022183`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022138`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022138`

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
0x180022100  mov     [rsp-8+arg_10], rbx
0x180022105  mov     [rsp-8+arg_18], rdi
0x18002210a  push    rbp
0x18002210b  lea     rbp, [rsp-170h]
0x180022113  sub     rsp, 270h
0x18002211a  mov     rax, cs:__security_cookie
0x180022121  xor     rax, rsp
0x180022124  mov     [rbp+170h+var_10], rax
0x18002212b  mov     rdi, rdx
0x18002212e  mov     qword ptr [rdx], 0
0x180022135  mov     rbx, rcx
0x180022138  call    cs:__imp_GetCurrentProcessId
0x18002213f  nop     dword ptr [rax+rax+00h]
0x180022144  mov     [rsp+270h+var_248], rbx
0x180022149  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180022150  mov     r9d, eax
0x180022153  mov     [rsp+270h+var_250], 130h; int
0x18002215b  mov     edx, 104h; unsigned __int64
0x180022160  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022165  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002216a  mov     r9d, 1F0001h; dwDesiredAccess
0x180022170  mov     [rsp+270h+var_240], 0
0x180022179  xor     r8d, r8d; dwFlags
0x18002217c  lea     rdx, [rsp+270h+Name]; lpName
0x180022181  xor     ecx, ecx; lpMutexAttributes
0x180022183  call    cs:__imp_CreateMutexExW
0x18002218a  nop     dword ptr [rax+rax+00h]
0x18002218f  mov     rdx, rax
0x180022192  lea     rcx, [rsp+270h+var_240]
0x180022197  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002219c  cmp     [rsp+270h+var_240], 0
0x1800221a2  jnz     short loc_1800221AD
0x1800221a4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800221a9  mov     ebx, eax
0x1800221ab  jmp     short loc_180022220
0x1800221ad  lea     rdx, [rsp+270h+var_238]
0x1800221b2  lea     rcx, [rsp+270h+var_240]
0x1800221b7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800221bc  lea     rdx, [rsp+270h+var_230]; void **
0x1800221c1  mov     [rsp+270h+var_230], 0
0x1800221ca  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800221cf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800221d4  mov     ebx, eax
0x1800221d6  test    eax, eax
0x1800221d8  jns     short loc_180022201
0x1800221da  mov     edx, 12Eh; void *
0x1800221df  mov     rcx, [rbp+178h]; this
0x1800221e6  lea     r8, aWil; "wil"
0x1800221ed  mov     r9d, eax; char *
0x1800221f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800221f5  lea     rcx, [rsp+270h+var_238]
0x1800221fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800221ff  jmp     short loc_180022220
0x180022201  mov     rcx, [rsp+270h+var_230]
0x180022206  test    rcx, rcx
0x180022209  jz      short loc_180022251
0x18002220b  mov     [rdi], rcx
0x18002220e  mov     eax, [rcx]
0x180022210  inc     eax
0x180022212  mov     [rcx], eax
0x180022214  lea     rcx, [rsp+270h+var_238]
0x180022219  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002221e  xor     ebx, ebx
0x180022220  lea     rcx, [rsp+270h+var_240]
0x180022225  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002222a  mov     eax, ebx
0x18002222c  mov     rcx, [rbp+170h+var_10]
0x180022233  xor     rcx, rsp; StackCookie
0x180022236  call    __security_check_cookie
0x18002223b  lea     r11, [rsp+270h+var_s0]
0x180022243  mov     rbx, [r11+20h]
0x180022247  mov     rdi, [r11+28h]
0x18002224b  mov     rsp, r11
0x18002224e  pop     rbp
0x18002224f  retn
0x180022251  mov     r8, rdi
0x180022254  lea     rdx, [rsp+270h+var_240]
0x180022259  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002225e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180022263  mov     ebx, eax
0x180022265  test    eax, eax
0x180022267  jns     short loc_180022214
0x180022269  mov     edx, 137h
0x18002226e  jmp     loc_1800221DF
```
