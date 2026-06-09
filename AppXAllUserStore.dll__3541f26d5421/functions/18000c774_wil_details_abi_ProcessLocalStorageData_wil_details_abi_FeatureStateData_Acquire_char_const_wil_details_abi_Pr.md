# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000c774`
- end: `0x18000c958`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `484`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001e9a8`

## callees

- `0x18000ae80`
- `0x18000c774`
- `0x18000c960`
- `0x18000cc38`
- `0x18001294c`
- `0x180018248`
- `0x180019338`
- `0x18001a274`
- `0x18001a344`
- `0x18001f260`
- `0x180023ed8`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c811`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c811`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c7eb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c7eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c7af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c7af`

## string_xrefs

- `0x18000c82c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rsi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // edi
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  _DWORD *v17; // rcx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v19 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v23 = v11;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v22, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v20);
    v15 = v14;
    v16 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v16, (unsigned int)"wil", (const char *)v15, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return v14;
  }
  v17 = (_DWORD *)(4 * v22);
  if ( 4 * v22 )
  {
    *a2 = v17;
    ++*v17;
  }
  else
  {
    v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v14 = v18;
    if ( v18 < 0 )
    {
      v15 = (unsigned int)v18;
      v16 = 311;
      goto LABEL_14;
    }
    v6 = v21;
  }
  if ( v11 )
    wil::details::ReleaseMutex(v11, v13);
  if ( v6 )
    wil::details::CloseHandle(v6, v13);
  return 0;
}

```

## disassembly

```asm
0x18000c774  mov     [rsp-8+arg_10], rbx
0x18000c779  mov     [rsp-8+arg_18], rsi
0x18000c77e  push    rbp
0x18000c77f  push    rdi
0x18000c780  push    r14
0x18000c782  lea     rbp, [rsp-170h]
0x18000c78a  sub     rsp, 270h
0x18000c791  mov     rax, cs:__security_cookie
0x18000c798  xor     rax, rsp
0x18000c79b  mov     [rbp+180h+var_20], rax
0x18000c7a2  mov     r14, rdx
0x18000c7a5  mov     qword ptr [rdx], 0
0x18000c7ac  mov     rbx, rcx
0x18000c7af  call    cs:__imp_GetCurrentProcessId
0x18000c7b5  mov     [rsp+280h+var_258], rbx
0x18000c7ba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c7c1  mov     r9d, eax
0x18000c7c4  mov     [rsp+280h+var_260], 130h; int
0x18000c7cc  mov     edx, 104h; unsigned __int64
0x18000c7d1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c7d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c7db  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c7e1  lea     rdx, [rsp+280h+Name]; lpName
0x18000c7e6  xor     r8d, r8d; dwFlags
0x18000c7e9  xor     ecx, ecx; lpMutexAttributes
0x18000c7eb  call    cs:__imp_CreateMutexExW
0x18000c7f1  mov     [rsp+280h+var_250], rax
0x18000c7f6  mov     rbx, rax
0x18000c7f9  test    rax, rax
0x18000c7fc  jnz     short loc_18000C808
0x18000c7fe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c803  jmp     loc_18000C931
0x18000c808  xor     r8d, r8d; bAlertable
0x18000c80b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c80e  mov     rcx, rbx; hHandle
0x18000c811  call    cs:__imp_WaitForSingleObjectEx
0x18000c817  cmp     eax, 102h
0x18000c81c  jz      short loc_18000C843
0x18000c81e  test    eax, 0FFFFFF7Fh
0x18000c823  jz      short loc_18000C83E
0x18000c825  mov     rcx, [rbp+188h]; this
0x18000c82c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c833  mov     edx, 0E01h; void *
0x18000c838  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000c83e  mov     rsi, rbx
0x18000c841  jmp     short loc_18000C845
0x18000c843  xor     esi, esi
0x18000c845  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18000c84a  mov     [rsp+280h+var_240], rsi
0x18000c84f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c854  mov     [rsp+280h+var_248], 0
0x18000c85d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000c862  mov     edi, eax
0x18000c864  test    eax, eax
0x18000c866  jns     short loc_18000C8A8
0x18000c868  mov     rcx, [rbp+188h]; this
0x18000c86f  lea     r8, aWil; "wil"
0x18000c876  mov     r9d, eax; char *
0x18000c879  mov     edx, 66h ; 'f'; void *
0x18000c87e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c883  mov     rcx, [rbp+188h]; this
0x18000c88a  lea     r8, aWil; "wil"
0x18000c891  mov     r9d, edi; char *
0x18000c894  mov     edx, 6Fh ; 'o'; void *
0x18000c899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c89e  mov     r9d, edi
0x18000c8a1  mov     edx, 12Eh
0x18000c8a6  jmp     short loc_18000C8E5
0x18000c8a8  mov     rax, [rsp+280h+var_248]
0x18000c8ad  lea     rcx, ds:0[rax*4]
0x18000c8b5  test    rcx, rcx
0x18000c8b8  jz      short loc_18000C8C5
0x18000c8ba  mov     [r14], rcx
0x18000c8bd  mov     eax, [rcx]
0x18000c8bf  inc     eax
0x18000c8c1  mov     [rcx], eax
0x18000c8c3  jmp     short loc_18000C915
0x18000c8c5  mov     r8, r14
0x18000c8c8  lea     rdx, [rsp+280h+var_250]
0x18000c8cd  lea     rcx, [rsp+280h+Name]
0x18000c8d2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000c8d7  mov     edi, eax
0x18000c8d9  test    eax, eax
0x18000c8db  jns     short loc_18000C910
0x18000c8dd  mov     r9d, eax; char *
0x18000c8e0  mov     edx, 137h; void *
0x18000c8e5  mov     rcx, [rbp+188h]; this
0x18000c8ec  lea     r8, aWil; "wil"
0x18000c8f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c8f8  lea     rcx, [rsp+280h+var_240]
0x18000c8fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c902  lea     rcx, [rsp+280h+var_250]
0x18000c907  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c90c  mov     eax, edi
0x18000c90e  jmp     short loc_18000C931
0x18000c910  mov     rbx, [rsp+280h+var_250]
0x18000c915  test    rsi, rsi
0x18000c918  jz      short loc_18000C922
0x18000c91a  mov     rcx, rsi; this
0x18000c91d  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000c922  test    rbx, rbx
0x18000c925  jz      short loc_18000C92F
0x18000c927  mov     rcx, rbx; this
0x18000c92a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000c92f  xor     eax, eax
0x18000c931  mov     rcx, [rbp+180h+var_20]
0x18000c938  xor     rcx, rsp; StackCookie
0x18000c93b  call    __security_check_cookie
0x18000c940  lea     r11, [rsp+280h+var_10]
0x18000c948  mov     rbx, [r11+30h]
0x18000c94c  mov     rsi, [r11+38h]
0x18000c950  mov     rsp, r11
0x18000c953  pop     r14
0x18000c955  pop     rdi
0x18000c956  pop     rbp
0x18000c957  retn
```
