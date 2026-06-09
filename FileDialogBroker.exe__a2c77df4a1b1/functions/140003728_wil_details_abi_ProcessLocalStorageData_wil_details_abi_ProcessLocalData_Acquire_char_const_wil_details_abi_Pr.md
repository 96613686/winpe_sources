# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003728`
- end: `0x1400038d2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400042a0`

## callees

- `0x140001c80`
- `0x1400035e0`
- `0x1400035fc`
- `0x140003728`
- `0x140003fb8`
- `0x1400049e8`
- `0x140005084`
- `0x1400055d8`
- `0x140005748`
- `0x140005b90`
- `0x140005c94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400037a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400037a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003760`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003760`

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
0x140003728  mov     [rsp-8+arg_10], rbx
0x14000372d  mov     [rsp-8+arg_18], rdi
0x140003732  push    rbp
0x140003733  lea     rbp, [rsp-170h]
0x14000373b  sub     rsp, 270h
0x140003742  mov     rax, cs:__security_cookie
0x140003749  xor     rax, rsp
0x14000374c  mov     [rbp+170h+var_10], rax
0x140003753  mov     rdi, rdx
0x140003756  mov     qword ptr [rdx], 0
0x14000375d  mov     rbx, rcx
0x140003760  call    cs:__imp_GetCurrentProcessId
0x140003766  mov     [rsp+270h+var_248], rbx
0x14000376b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003772  mov     r9d, eax
0x140003775  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x14000377d  mov     edx, 104h; unsigned __int64
0x140003782  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003787  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000378c  mov     r9d, 1F0001h; dwDesiredAccess
0x140003792  mov     [rsp+270h+var_240], 0
0x14000379b  xor     r8d, r8d; dwFlags
0x14000379e  lea     rdx, [rsp+270h+Name]; lpName
0x1400037a3  xor     ecx, ecx; lpMutexAttributes
0x1400037a5  call    cs:__imp_CreateMutexExW
0x1400037ab  mov     rdx, rax
0x1400037ae  lea     rcx, [rsp+270h+var_240]
0x1400037b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400037b8  cmp     [rsp+270h+var_240], 0
0x1400037be  jnz     short loc_1400037CC
0x1400037c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400037c5  mov     ebx, eax
0x1400037c7  jmp     loc_14000387D
0x1400037cc  lea     rdx, [rsp+270h+var_238]
0x1400037d1  lea     rcx, [rsp+270h+var_240]
0x1400037d6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400037db  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1400037e0  mov     [rsp+270h+var_230], 0
0x1400037e9  lea     rcx, [rsp+270h+Name]; pszSrc
0x1400037ee  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400037f3  mov     ebx, eax
0x1400037f5  test    eax, eax
0x1400037f7  jns     short loc_140003856
0x1400037f9  mov     rcx, [rbp+178h]; this
0x140003800  lea     r8, aWil; "wil"
0x140003807  mov     r9d, eax; char *
0x14000380a  mov     edx, 66h ; 'f'; void *
0x14000380f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003814  mov     rcx, [rbp+178h]; this
0x14000381b  lea     r8, aWil; "wil"
0x140003822  mov     r9d, ebx; char *
0x140003825  mov     edx, 6Fh ; 'o'; void *
0x14000382a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000382f  mov     r9d, ebx; char *
0x140003832  mov     edx, 12Eh; void *
0x140003837  mov     rcx, [rbp+178h]; this
0x14000383e  lea     r8, aWil; "wil"
0x140003845  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000384a  lea     rcx, [rsp+270h+var_238]
0x14000384f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003854  jmp     short loc_14000387D
0x140003856  mov     rax, [rsp+270h+var_230]
0x14000385b  lea     rcx, ds:0[rax*4]
0x140003863  test    rcx, rcx
0x140003866  jz      short loc_1400038AD
0x140003868  mov     [rdi], rcx
0x14000386b  mov     eax, [rcx]
0x14000386d  inc     eax
0x14000386f  mov     [rcx], eax
0x140003871  lea     rcx, [rsp+270h+var_238]
0x140003876  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000387b  xor     ebx, ebx
0x14000387d  lea     rcx, [rsp+270h+var_240]
0x140003882  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003887  mov     eax, ebx
0x140003889  mov     rcx, [rbp+170h+var_10]
0x140003890  xor     rcx, rsp; StackCookie
0x140003893  call    __security_check_cookie
0x140003898  lea     r11, [rsp+270h+var_s0]
0x1400038a0  mov     rbx, [r11+20h]
0x1400038a4  mov     rdi, [r11+28h]
0x1400038a8  mov     rsp, r11
0x1400038ab  pop     rbp
0x1400038ac  retn
0x1400038ad  mov     r8, rdi
0x1400038b0  lea     rdx, [rsp+270h+var_240]
0x1400038b5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400038ba  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400038bf  mov     ebx, eax
0x1400038c1  test    eax, eax
0x1400038c3  jns     short loc_140003871
0x1400038c5  mov     r9d, eax
0x1400038c8  mov     edx, 137h
0x1400038cd  jmp     loc_140003837
```
