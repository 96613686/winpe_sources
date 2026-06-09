# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000966c`
- end: `0x180009816`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a0c8`

## callees

- `0x180007bb8`
- `0x180009544`
- `0x180009560`
- `0x18000966c`
- `0x18000a680`
- `0x18000ab5c`
- `0x18000ae68`
- `0x18000aff0`
- `0x18000b518`
- `0x18000ba60`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800096e9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800096e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800096a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800096a4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v16 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v18 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v18,
    Mutex);
  if ( v18 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v18,
      v19);
    v20 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v20, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v17);
      v11 = LastErrorFailHr;
      v12 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v12, (unsigned int)"wil", (const char *)v11, v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
      goto LABEL_9;
    }
    v13 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v13;
      ++*v13;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v15;
      if ( v15 < 0 )
      {
        v11 = (unsigned int)v15;
        v12 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v18,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18000966c  mov     [rsp-8+arg_10], rbx
0x180009671  mov     [rsp-8+arg_18], rdi
0x180009676  push    rbp
0x180009677  lea     rbp, [rsp-170h]
0x18000967f  sub     rsp, 270h
0x180009686  mov     rax, cs:__security_cookie
0x18000968d  xor     rax, rsp
0x180009690  mov     [rbp+170h+var_10], rax
0x180009697  mov     rdi, rdx
0x18000969a  mov     qword ptr [rdx], 0
0x1800096a1  mov     rbx, rcx
0x1800096a4  call    cs:__imp_GetCurrentProcessId
0x1800096aa  mov     [rsp+270h+var_248], rbx
0x1800096af  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800096b6  mov     r9d, eax
0x1800096b9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800096c1  mov     edx, 104h; unsigned __int64
0x1800096c6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800096cb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800096d0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800096d6  mov     [rsp+270h+var_240], 0
0x1800096df  xor     r8d, r8d; dwFlags
0x1800096e2  lea     rdx, [rsp+270h+Name]; lpName
0x1800096e7  xor     ecx, ecx; lpMutexAttributes
0x1800096e9  call    cs:__imp_CreateMutexExW
0x1800096ef  mov     rdx, rax
0x1800096f2  lea     rcx, [rsp+270h+var_240]
0x1800096f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800096fc  cmp     [rsp+270h+var_240], 0
0x180009702  jnz     short loc_180009710
0x180009704  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009709  mov     ebx, eax
0x18000970b  jmp     loc_1800097C1
0x180009710  lea     rdx, [rsp+270h+var_238]
0x180009715  lea     rcx, [rsp+270h+var_240]
0x18000971a  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000971f  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180009724  mov     [rsp+270h+var_230], 0
0x18000972d  lea     rcx, [rsp+270h+Name]; pszSrc
0x180009732  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180009737  mov     ebx, eax
0x180009739  test    eax, eax
0x18000973b  jns     short loc_18000979A
0x18000973d  mov     rcx, [rbp+178h]; this
0x180009744  lea     r8, aWil; "wil"
0x18000974b  mov     r9d, eax; char *
0x18000974e  mov     edx, 66h ; 'f'; void *
0x180009753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009758  mov     rcx, [rbp+178h]; this
0x18000975f  lea     r8, aWil; "wil"
0x180009766  mov     r9d, ebx; char *
0x180009769  mov     edx, 6Fh ; 'o'; void *
0x18000976e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009773  mov     r9d, ebx; char *
0x180009776  mov     edx, 12Eh; void *
0x18000977b  mov     rcx, [rbp+178h]; this
0x180009782  lea     r8, aWil; "wil"
0x180009789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000978e  lea     rcx, [rsp+270h+var_238]
0x180009793  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009798  jmp     short loc_1800097C1
0x18000979a  mov     rax, [rsp+270h+var_230]
0x18000979f  lea     rcx, ds:0[rax*4]
0x1800097a7  test    rcx, rcx
0x1800097aa  jz      short loc_1800097F1
0x1800097ac  mov     [rdi], rcx
0x1800097af  mov     eax, [rcx]
0x1800097b1  inc     eax
0x1800097b3  mov     [rcx], eax
0x1800097b5  lea     rcx, [rsp+270h+var_238]
0x1800097ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800097bf  xor     ebx, ebx
0x1800097c1  lea     rcx, [rsp+270h+var_240]
0x1800097c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800097cb  mov     eax, ebx
0x1800097cd  mov     rcx, [rbp+170h+var_10]
0x1800097d4  xor     rcx, rsp; StackCookie
0x1800097d7  call    __security_check_cookie
0x1800097dc  lea     r11, [rsp+270h+var_s0]
0x1800097e4  mov     rbx, [r11+20h]
0x1800097e8  mov     rdi, [r11+28h]
0x1800097ec  mov     rsp, r11
0x1800097ef  pop     rbp
0x1800097f0  retn
0x1800097f1  mov     r8, rdi
0x1800097f4  lea     rdx, [rsp+270h+var_240]
0x1800097f9  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800097fe  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009803  mov     ebx, eax
0x180009805  test    eax, eax
0x180009807  jns     short loc_1800097B5
0x180009809  mov     r9d, eax
0x18000980c  mov     edx, 137h
0x180009811  jmp     loc_18000977B
```
