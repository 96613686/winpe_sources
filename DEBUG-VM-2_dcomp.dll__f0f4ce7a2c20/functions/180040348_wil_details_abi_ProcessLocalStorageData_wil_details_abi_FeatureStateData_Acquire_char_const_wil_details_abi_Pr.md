# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180040348`
- end: `0x180040574`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180040058`

## callees

- `0x18001358c`
- `0x18003ff18`
- `0x180040348`
- `0x18004057c`
- `0x180040e6c`
- `0x180040f24`
- `0x180041358`
- `0x180041374`
- `0x1800413f8`
- `0x1800e4908`
- `0x1800f6f10`
- `0x1800f8e54`
- `0x1800f93fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004041a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004041a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800403c8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800403c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180040383`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180040383`

## string_xrefs

- `0x180040510`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  void *v16; // rdx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = (wil::details *)hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v19);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v20);
    if ( v11 )
      wil::details::ReleaseMutex(v11, v16);
    wil::details::CloseHandle(v6, v16);
    return v14;
  }
  else
  {
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v17,
          304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
        return v18;
      }
      v6 = (wil::details *)hHandle;
    }
    if ( v11 )
      wil::details::ReleaseMutex(v11, v13);
    if ( v6 )
      wil::details::CloseHandle(v6, v13);
    return 0;
  }
}

```

## disassembly

```asm
0x180040348  mov     [rsp-8+arg_10], rbx
0x18004034d  mov     [rsp-8+arg_18], rsi
0x180040352  push    rbp
0x180040353  push    rdi
0x180040354  push    r14
0x180040356  lea     rbp, [rsp-170h]
0x18004035e  sub     rsp, 270h
0x180040365  mov     rax, cs:__security_cookie
0x18004036c  xor     rax, rsp
0x18004036f  mov     [rbp+180h+var_20], rax
0x180040376  mov     r14, rdx
0x180040379  mov     qword ptr [rdx], 0
0x180040380  mov     rbx, rcx
0x180040383  call    cs:__imp_GetCurrentProcessId
0x180040389  mov     [rsp+280h+var_258], rbx
0x18004038e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180040395  mov     r9d, eax
0x180040398  mov     [rsp+280h+var_260], 130h; int
0x1800403a0  mov     edx, 104h; unsigned __int64
0x1800403a5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800403aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800403af  mov     r9d, 1F0001h; dwDesiredAccess
0x1800403b5  mov     [rsp+280h+hHandle], 0
0x1800403be  xor     r8d, r8d; dwFlags
0x1800403c1  lea     rdx, [rsp+280h+Name]; lpName
0x1800403c6  xor     ecx, ecx; lpMutexAttributes
0x1800403c8  call    cs:__imp_CreateMutexExW
0x1800403ce  mov     rdx, rax
0x1800403d1  lea     rcx, [rsp+280h+hHandle]
0x1800403d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800403db  mov     rbx, [rsp+280h+hHandle]
0x1800403e0  test    rbx, rbx
0x1800403e3  jnz     short loc_180040411
0x1800403e5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800403ea  mov     rcx, [rbp+180h+var_20]
0x1800403f1  xor     rcx, rsp; StackCookie
0x1800403f4  call    __security_check_cookie
0x1800403f9  lea     r11, [rsp+280h+var_10]
0x180040401  mov     rbx, [r11+30h]
0x180040405  mov     rsi, [r11+38h]
0x180040409  mov     rsp, r11
0x18004040c  pop     r14
0x18004040e  pop     rdi
0x18004040f  pop     rbp
0x180040410  retn
0x180040411  xor     r8d, r8d; bAlertable
0x180040414  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180040417  mov     rcx, rbx; hHandle
0x18004041a  call    cs:__imp_WaitForSingleObjectEx
0x180040420  cmp     eax, 102h
0x180040425  jz      short loc_180040498
0x180040427  test    eax, 0FFFFFF7Fh
0x18004042c  jnz     loc_180040509
0x180040432  mov     rdi, rbx
0x180040435  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18004043a  mov     [rsp+280h+var_240], rdi
0x18004043f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180040444  mov     [rsp+280h+var_248], 0
0x18004044d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180040452  mov     esi, eax
0x180040454  test    eax, eax
0x180040456  js      short loc_18004049C
0x180040458  mov     rax, [rsp+280h+var_248]
0x18004045d  lea     rcx, ds:0[rax*4]
0x180040465  test    rcx, rcx
0x180040468  jz      loc_180040522
0x18004046e  mov     [r14], rcx
0x180040471  mov     eax, [rcx]
0x180040473  inc     eax
0x180040475  mov     [rcx], eax
0x180040477  test    rdi, rdi
0x18004047a  jz      short loc_180040484
0x18004047c  mov     rcx, rdi; this
0x18004047f  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180040484  test    rbx, rbx
0x180040487  jz      short loc_180040491
0x180040489  mov     rcx, rbx; this
0x18004048c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180040491  xor     eax, eax
0x180040493  jmp     loc_1800403EA
0x180040498  xor     edi, edi
0x18004049a  jmp     short loc_180040435
0x18004049c  mov     rcx, [rbp+188h]; this
0x1800404a3  lea     r8, aWil; "wil"
0x1800404aa  mov     r9d, esi; char *
0x1800404ad  mov     edx, 66h ; 'f'; void *
0x1800404b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800404b7  mov     rcx, [rbp+188h]; this
0x1800404be  lea     r8, aWil; "wil"
0x1800404c5  mov     r9d, esi; char *
0x1800404c8  mov     edx, 6Fh ; 'o'; void *
0x1800404cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800404d2  mov     rcx, [rbp+188h]; this
0x1800404d9  lea     r8, aWil; "wil"
0x1800404e0  mov     r9d, esi; char *
0x1800404e3  mov     edx, 12Eh; void *
0x1800404e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800404ed  test    rdi, rdi
0x1800404f0  jz      short loc_1800404FA
0x1800404f2  mov     rcx, rdi; this
0x1800404f5  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800404fa  mov     rcx, rbx; this
0x1800404fd  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180040502  mov     eax, esi
0x180040504  jmp     loc_1800403EA
0x180040509  mov     rcx, [rbp+188h]; this
0x180040510  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180040517  mov     edx, 0E01h; void *
0x18004051c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180040522  mov     r8, r14
0x180040525  lea     rdx, [rsp+280h+hHandle]
0x18004052a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18004052f  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180040534  mov     ebx, eax
0x180040536  test    eax, eax
0x180040538  jns     loc_18017DAD6
0x18004053e  mov     rcx, [rbp+188h]; this
0x180040545  lea     r8, aWil; "wil"
0x18004054c  mov     r9d, eax; char *
0x18004054f  mov     edx, 137h; void *
0x180040554  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040559  lea     rcx, [rsp+280h+var_240]
0x18004055e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040563  lea     rcx, [rsp+280h+hHandle]
0x180040568  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004056d  mov     eax, ebx
0x18004056f  jmp     loc_1800403EA
0x18017dad6  mov     rbx, [rsp+280h+hHandle]
0x18017dadb  jmp     loc_180040477
```
