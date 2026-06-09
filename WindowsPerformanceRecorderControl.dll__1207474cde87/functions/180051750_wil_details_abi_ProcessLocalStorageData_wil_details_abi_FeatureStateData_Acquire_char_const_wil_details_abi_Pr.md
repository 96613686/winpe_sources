# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180051750`
- end: `0x1800518af`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180051e84`

## callees

- `0x180010208`
- `0x18004dcc0`
- `0x18004ece0`
- `0x1800511d0`
- `0x1800511ec`
- `0x180051750`
- `0x180053ea4`
- `0x180054e04`
- `0x180055a78`
- `0x180056234`
- `0x1800563b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800517cd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800517cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180051788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180051788`

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
0x180051750  mov     [rsp-8+arg_10], rbx
0x180051755  mov     [rsp-8+arg_18], rdi
0x18005175a  push    rbp
0x18005175b  lea     rbp, [rsp-170h]
0x180051763  sub     rsp, 270h
0x18005176a  mov     rax, cs:__security_cookie
0x180051771  xor     rax, rsp
0x180051774  mov     [rbp+170h+var_10], rax
0x18005177b  mov     rdi, rdx
0x18005177e  mov     qword ptr [rdx], 0
0x180051785  mov     rbx, rcx
0x180051788  call    cs:__imp_GetCurrentProcessId
0x18005178e  mov     [rsp+270h+var_248], rbx
0x180051793  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18005179a  mov     r9d, eax
0x18005179d  mov     [rsp+270h+var_250], 130h; int
0x1800517a5  mov     edx, 104h; unsigned __int64
0x1800517aa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800517af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800517b4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800517ba  mov     [rsp+270h+var_240], 0
0x1800517c3  xor     r8d, r8d; dwFlags
0x1800517c6  lea     rdx, [rsp+270h+Name]; lpName
0x1800517cb  xor     ecx, ecx; lpMutexAttributes
0x1800517cd  call    cs:__imp_CreateMutexExW
0x1800517d3  mov     rdx, rax
0x1800517d6  lea     rcx, [rsp+270h+var_240]
0x1800517db  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800517e0  cmp     [rsp+270h+var_240], 0
0x1800517e6  jnz     short loc_1800517F1
0x1800517e8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800517ed  mov     ebx, eax
0x1800517ef  jmp     short loc_18005185D
0x1800517f1  lea     rdx, [rsp+270h+var_238]
0x1800517f6  lea     rcx, [rsp+270h+var_240]
0x1800517fb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180051800  lea     rdx, [rsp+270h+var_230]; void **
0x180051805  mov     [rsp+270h+var_230], 0
0x18005180e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180051813  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180051818  mov     ebx, eax
0x18005181a  test    eax, eax
0x18005181c  jns     short loc_18005183E
0x18005181e  mov     edx, 12Eh; void *
0x180051823  mov     rcx, [rbp+178h]; this
0x18005182a  mov     r9d, eax; char *
0x18005182d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051832  lea     rcx, [rsp+270h+var_238]
0x180051837  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005183c  jmp     short loc_18005185D
0x18005183e  mov     rcx, [rsp+270h+var_230]
0x180051843  test    rcx, rcx
0x180051846  jz      short loc_18005188D
0x180051848  mov     [rdi], rcx
0x18005184b  mov     eax, [rcx]
0x18005184d  inc     eax
0x18005184f  mov     [rcx], eax
0x180051851  lea     rcx, [rsp+270h+var_238]
0x180051856  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005185b  xor     ebx, ebx
0x18005185d  lea     rcx, [rsp+270h+var_240]
0x180051862  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180051867  mov     eax, ebx
0x180051869  mov     rcx, [rbp+170h+var_10]
0x180051870  xor     rcx, rsp; StackCookie
0x180051873  call    __security_check_cookie
0x180051878  lea     r11, [rsp+270h+var_s0]
0x180051880  mov     rbx, [r11+20h]
0x180051884  mov     rdi, [r11+28h]
0x180051888  mov     rsp, r11
0x18005188b  pop     rbp
0x18005188c  retn
0x18005188d  mov     r8, rdi
0x180051890  lea     rdx, [rsp+270h+var_240]
0x180051895  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005189a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005189f  mov     ebx, eax
0x1800518a1  test    eax, eax
0x1800518a3  jns     short loc_180051851
0x1800518a5  mov     edx, 137h
0x1800518aa  jmp     loc_180051823
```
