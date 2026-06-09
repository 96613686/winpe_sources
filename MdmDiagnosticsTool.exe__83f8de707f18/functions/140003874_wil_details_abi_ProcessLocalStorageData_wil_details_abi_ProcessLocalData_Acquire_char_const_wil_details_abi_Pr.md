# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003874`
- end: `0x140003a2b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000516c`

## callees

- `0x140003498`
- `0x1400034b8`
- `0x140003874`
- `0x140004820`
- `0x140005934`
- `0x1400065e4`
- `0x140006b88`
- `0x140006e34`
- `0x14000769c`
- `0x1400082f0`
- `0x140009d00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400038f7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400038f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400038ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400038ac`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140003874  mov     [rsp-8+arg_10], rbx
0x140003879  mov     [rsp-8+arg_18], rdi
0x14000387e  push    rbp
0x14000387f  lea     rbp, [rsp-170h]
0x140003887  sub     rsp, 270h
0x14000388e  mov     rax, cs:__security_cookie
0x140003895  xor     rax, rsp
0x140003898  mov     [rbp+170h+var_10], rax
0x14000389f  mov     rdi, rdx
0x1400038a2  mov     qword ptr [rdx], 0
0x1400038a9  mov     rbx, rcx
0x1400038ac  call    cs:__imp_GetCurrentProcessId
0x1400038b3  nop     dword ptr [rax+rax+00h]
0x1400038b8  mov     [rsp+270h+var_248], rbx
0x1400038bd  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400038c4  mov     r9d, eax
0x1400038c7  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1400038cf  mov     edx, 104h; unsigned __int64
0x1400038d4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400038d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400038de  mov     r9d, 1F0001h; dwDesiredAccess
0x1400038e4  mov     [rsp+270h+var_240], 0
0x1400038ed  xor     r8d, r8d; dwFlags
0x1400038f0  lea     rdx, [rsp+270h+Name]; lpName
0x1400038f5  xor     ecx, ecx; lpMutexAttributes
0x1400038f7  call    cs:__imp_CreateMutexExW
0x1400038fe  nop     dword ptr [rax+rax+00h]
0x140003903  mov     rdx, rax
0x140003906  lea     rcx, [rsp+270h+var_240]
0x14000390b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140003910  cmp     [rsp+270h+var_240], 0
0x140003916  jnz     short loc_140003924
0x140003918  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000391d  mov     ebx, eax
0x14000391f  jmp     loc_1400039D5
0x140003924  lea     rdx, [rsp+270h+var_238]
0x140003929  lea     rcx, [rsp+270h+var_240]
0x14000392e  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140003933  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x140003938  mov     [rsp+270h+var_230], 0
0x140003941  lea     rcx, [rsp+270h+Name]; pszSrc
0x140003946  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000394b  mov     ebx, eax
0x14000394d  test    eax, eax
0x14000394f  jns     short loc_1400039AE
0x140003951  mov     rcx, [rbp+178h]; this
0x140003958  lea     r8, aWil; "wil"
0x14000395f  mov     r9d, eax; char *
0x140003962  mov     edx, 66h ; 'f'; void *
0x140003967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000396c  mov     rcx, [rbp+178h]; this
0x140003973  lea     r8, aWil; "wil"
0x14000397a  mov     r9d, ebx; char *
0x14000397d  mov     edx, 6Fh ; 'o'; void *
0x140003982  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003987  mov     r9d, ebx; char *
0x14000398a  mov     edx, 12Eh; void *
0x14000398f  mov     rcx, [rbp+178h]; this
0x140003996  lea     r8, aWil; "wil"
0x14000399d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400039a2  lea     rcx, [rsp+270h+var_238]
0x1400039a7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400039ac  jmp     short loc_1400039D5
0x1400039ae  mov     rax, [rsp+270h+var_230]
0x1400039b3  lea     rcx, ds:0[rax*4]
0x1400039bb  test    rcx, rcx
0x1400039be  jz      short loc_140003A06
0x1400039c0  mov     [rdi], rcx
0x1400039c3  mov     eax, [rcx]
0x1400039c5  inc     eax
0x1400039c7  mov     [rcx], eax
0x1400039c9  lea     rcx, [rsp+270h+var_238]
0x1400039ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400039d3  xor     ebx, ebx
0x1400039d5  lea     rcx, [rsp+270h+var_240]
0x1400039da  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400039df  mov     eax, ebx
0x1400039e1  mov     rcx, [rbp+170h+var_10]
0x1400039e8  xor     rcx, rsp; StackCookie
0x1400039eb  call    __security_check_cookie
0x1400039f0  lea     r11, [rsp+270h+var_s0]
0x1400039f8  mov     rbx, [r11+20h]
0x1400039fc  mov     rdi, [r11+28h]
0x140003a00  mov     rsp, r11
0x140003a03  pop     rbp
0x140003a04  retn
0x140003a06  mov     r8, rdi
0x140003a09  lea     rdx, [rsp+270h+var_240]
0x140003a0e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003a13  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140003a18  mov     ebx, eax
0x140003a1a  test    eax, eax
0x140003a1c  jns     short loc_1400039C9
0x140003a1e  mov     r9d, eax
0x140003a21  mov     edx, 137h
0x140003a26  jmp     loc_14000398F
```
