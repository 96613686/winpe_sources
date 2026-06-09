# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001b6ec`
- end: `0x18001b8f1`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180048b04`

## callees

- `0x18001b410`
- `0x18001b4e0`
- `0x18001b628`
- `0x18001b6ec`
- `0x18001c058`
- `0x18001c0f8`
- `0x18003f0b4`
- `0x18003f2a0`
- `0x18003ff0c`
- `0x180040270`
- `0x180043c30`
- `0x1800481d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b78b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b78b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001b763`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001b763`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b727`

## string_xrefs

- `0x18001b7a6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  wil::details *v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v20 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    return LastErrorFailHr;
  }
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v22[0] = v11;
  v21 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v21, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v18);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    LastErrorFailHr = v14;
    goto LABEL_14;
  }
  v15 = (_DWORD *)(4 * v21);
  if ( 4 * v21 )
  {
    *a2 = v15;
    ++*v15;
  }
  else
  {
    v16 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v16,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
      goto LABEL_14;
    }
    v6 = v20;
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
0x18001b6ec  mov     [rsp-8+arg_10], rbx
0x18001b6f1  mov     [rsp-8+arg_18], rsi
0x18001b6f6  push    rbp
0x18001b6f7  push    rdi
0x18001b6f8  push    r14
0x18001b6fa  lea     rbp, [rsp-170h]
0x18001b702  sub     rsp, 270h
0x18001b709  mov     rax, cs:__security_cookie
0x18001b710  xor     rax, rsp
0x18001b713  mov     [rbp+180h+var_20], rax
0x18001b71a  mov     r14, rdx
0x18001b71d  mov     qword ptr [rdx], 0
0x18001b724  mov     rbx, rcx
0x18001b727  call    cs:__imp_GetCurrentProcessId
0x18001b72d  mov     [rsp+280h+var_258], rbx
0x18001b732  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001b739  mov     r9d, eax
0x18001b73c  mov     [rsp+280h+var_260], 130h; int
0x18001b744  mov     edx, 104h; unsigned __int64
0x18001b749  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001b74e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b753  mov     r9d, 1F0001h; dwDesiredAccess
0x18001b759  lea     rdx, [rsp+280h+Name]; lpName
0x18001b75e  xor     r8d, r8d; dwFlags
0x18001b761  xor     ecx, ecx; lpMutexAttributes
0x18001b763  call    cs:__imp_CreateMutexExW
0x18001b769  mov     [rsp+280h+var_250], rax
0x18001b76e  mov     rbx, rax
0x18001b771  test    rax, rax
0x18001b774  jnz     short loc_18001B782
0x18001b776  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001b77b  mov     ebx, eax
0x18001b77d  jmp     loc_18001B89B
0x18001b782  xor     r8d, r8d; bAlertable
0x18001b785  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001b788  mov     rcx, rbx; hHandle
0x18001b78b  call    cs:__imp_WaitForSingleObjectEx
0x18001b791  cmp     eax, 102h
0x18001b796  jz      short loc_18001B7BD
0x18001b798  test    eax, 0FFFFFF7Fh
0x18001b79d  jz      short loc_18001B7B8
0x18001b79f  mov     rcx, [rbp+188h]; this
0x18001b7a6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001b7ad  mov     edx, 0E01h; void *
0x18001b7b2  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001b7b8  mov     rdi, rbx
0x18001b7bb  jmp     short loc_18001B7BF
0x18001b7bd  xor     edi, edi
0x18001b7bf  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18001b7c4  mov     [rsp+280h+var_240], rdi
0x18001b7c9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001b7ce  mov     [rsp+280h+var_248], 0
0x18001b7d7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001b7dc  mov     esi, eax
0x18001b7de  test    eax, eax
0x18001b7e0  jns     short loc_18001B841
0x18001b7e2  mov     rcx, [rbp+188h]; this
0x18001b7e9  lea     r8, aWil; "wil"
0x18001b7f0  mov     r9d, eax; char *
0x18001b7f3  mov     edx, 66h ; 'f'; void *
0x18001b7f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b7fd  mov     rcx, [rbp+188h]; this
0x18001b804  lea     r8, aWil; "wil"
0x18001b80b  mov     r9d, esi; char *
0x18001b80e  mov     edx, 6Fh ; 'o'; void *
0x18001b813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b818  mov     rcx, [rbp+188h]; this
0x18001b81f  lea     r8, aWil; "wil"
0x18001b826  mov     r9d, esi; char *
0x18001b829  mov     edx, 12Eh; void *
0x18001b82e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b833  lea     rcx, [rsp+280h+var_240]
0x18001b838  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b83d  mov     ebx, esi
0x18001b83f  jmp     short loc_18001B89B
0x18001b841  mov     rax, [rsp+280h+var_248]
0x18001b846  lea     rcx, ds:0[rax*4]
0x18001b84e  test    rcx, rcx
0x18001b851  jz      short loc_18001B85E
0x18001b853  mov     [r14], rcx
0x18001b856  mov     eax, [rcx]
0x18001b858  inc     eax
0x18001b85a  mov     [rcx], eax
0x18001b85c  jmp     short loc_18001B8AE
0x18001b85e  mov     r8, r14
0x18001b861  lea     rdx, [rsp+280h+var_250]
0x18001b866  lea     rcx, [rsp+280h+Name]
0x18001b86b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001b870  mov     ebx, eax
0x18001b872  test    eax, eax
0x18001b874  jns     short loc_18001B8A9
0x18001b876  mov     rcx, [rbp+188h]; this
0x18001b87d  lea     r8, aWil; "wil"
0x18001b884  mov     r9d, eax; char *
0x18001b887  mov     edx, 137h; void *
0x18001b88c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b891  lea     rcx, [rsp+280h+var_240]
0x18001b896  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b89b  lea     rcx, [rsp+280h+var_250]
0x18001b8a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b8a5  mov     eax, ebx
0x18001b8a7  jmp     short loc_18001B8CA
0x18001b8a9  mov     rbx, [rsp+280h+var_250]
0x18001b8ae  test    rdi, rdi
0x18001b8b1  jz      short loc_18001B8BB
0x18001b8b3  mov     rcx, rdi; this
0x18001b8b6  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18001b8bb  test    rbx, rbx
0x18001b8be  jz      short loc_18001B8C8
0x18001b8c0  mov     rcx, rbx; this
0x18001b8c3  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001b8c8  xor     eax, eax
0x18001b8ca  mov     rcx, [rbp+180h+var_20]
0x18001b8d1  xor     rcx, rsp; StackCookie
0x18001b8d4  call    __security_check_cookie
0x18001b8d9  lea     r11, [rsp+280h+var_10]
0x18001b8e1  mov     rbx, [r11+30h]
0x18001b8e5  mov     rsi, [r11+38h]
0x18001b8e9  mov     rsp, r11
0x18001b8ec  pop     r14
0x18001b8ee  pop     rdi
0x18001b8ef  pop     rbp
0x18001b8f0  retn
```
