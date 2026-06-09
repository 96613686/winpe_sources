# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000870c`
- end: `0x1800088d3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18022aeb0`

## callees

- `0x1800082bc`
- `0x18000870c`
- `0x180008934`
- `0x180008e08`
- `0x18001c3c4`
- `0x18001ce34`
- `0x180042854`
- `0x180200468`
- `0x180200500`
- `0x180202100`
- `0x18021dd98`
- `0x180228490`
- `0x18022b194`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800087b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800087b1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008787`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008787`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008742`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008742`

## string_xrefs

- `0x180008893`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  DWORD v6; // eax
  bool v7; // dl
  char *v8; // r9
  wil::details *v9; // rbx
  int ValueInternal; // eax
  unsigned int v11; // edi
  void *v12; // rdx
  _DWORD *v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-C0h] BYREF
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
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v6 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v6 == 258 )
  {
    v9 = 0;
  }
  else
  {
    if ( (v6 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    v9 = (wil::details *)hHandle;
  }
  v21[0] = v9;
  v20 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v20, (bool *)v8);
  v11 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v14 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v14;
      ++*v14;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v15,
          304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
        return v16;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v11, v17);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v11, v18);
    if ( v9 )
      wil::details::ReleaseMutex(v9, v12);
    wil::details::CloseHandle((wil::details *)hHandle, v12);
    return v11;
  }
}

```

## disassembly

```asm
0x18000870c  mov     [rsp-8+arg_10], rbx
0x180008711  push    rbp
0x180008712  push    rdi
0x180008713  push    r14
0x180008715  lea     rbp, [rsp-170h]
0x18000871d  sub     rsp, 270h
0x180008724  mov     rax, cs:__security_cookie
0x18000872b  xor     rax, rsp
0x18000872e  mov     [rbp+180h+var_20], rax
0x180008735  mov     r14, rdx
0x180008738  mov     qword ptr [rdx], 0
0x18000873f  mov     rbx, rcx
0x180008742  call    cs:__imp_GetCurrentProcessId
0x180008748  mov     [rsp+280h+var_258], rbx
0x18000874d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008754  mov     r9d, eax
0x180008757  mov     [rsp+280h+var_260], 130h; int
0x18000875f  mov     edx, 104h; unsigned __int64
0x180008764  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008769  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000876e  mov     r9d, 1F0001h; dwDesiredAccess
0x180008774  mov     [rsp+280h+hHandle], 0
0x18000877d  xor     r8d, r8d; dwFlags
0x180008780  lea     rdx, [rsp+280h+Name]; lpName
0x180008785  xor     ecx, ecx; lpMutexAttributes
0x180008787  call    cs:__imp_CreateMutexExW
0x18000878d  mov     rdx, rax
0x180008790  lea     rcx, [rsp+280h+hHandle]
0x180008795  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000879a  cmp     [rsp+280h+hHandle], 0
0x1800087a0  jz      loc_18000887E
0x1800087a6  mov     rcx, [rsp+280h+hHandle]; hHandle
0x1800087ab  xor     r8d, r8d; bAlertable
0x1800087ae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800087b1  call    cs:__imp_WaitForSingleObjectEx
0x1800087b7  cmp     eax, 102h
0x1800087bc  jz      loc_180008885
0x1800087c2  test    eax, 0FFFFFF7Fh
0x1800087c7  jnz     loc_18000888C
0x1800087cd  mov     rbx, [rsp+280h+hHandle]
0x1800087d2  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800087d7  mov     [rsp+280h+var_240], rbx
0x1800087dc  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800087e1  mov     [rsp+280h+var_248], 0
0x1800087ea  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800087ef  mov     edi, eax
0x1800087f1  test    eax, eax
0x1800087f3  jns     loc_1800088AF
0x1800087f9  mov     rcx, [rbp+188h]; this
0x180008800  lea     r8, aWil; "wil"
0x180008807  mov     r9d, eax; char *
0x18000880a  mov     edx, 66h ; 'f'; void *
0x18000880f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008814  mov     rcx, [rbp+188h]; this
0x18000881b  lea     r8, aWil; "wil"
0x180008822  mov     r9d, edi; char *
0x180008825  mov     edx, 6Fh ; 'o'; void *
0x18000882a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000882f  mov     rcx, [rbp+188h]; this
0x180008836  lea     r8, aWil; "wil"
0x18000883d  mov     r9d, edi; char *
0x180008840  mov     edx, 12Eh; void *
0x180008845  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000884a  test    rbx, rbx
0x18000884d  jnz     short loc_1800088A5
0x18000884f  mov     rcx, [rsp+280h+hHandle]; this
0x180008854  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008859  mov     eax, edi
0x18000885b  mov     rcx, [rbp+180h+var_20]
0x180008862  xor     rcx, rsp; StackCookie
0x180008865  call    __security_check_cookie
0x18000886a  mov     rbx, [rsp+280h+arg_10]
0x180008872  add     rsp, 270h
0x180008879  pop     r14
0x18000887b  pop     rdi
0x18000887c  pop     rbp
0x18000887d  retn
0x18000887e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008883  jmp     short loc_18000885B
0x180008885  xor     ebx, ebx
0x180008887  jmp     loc_1800087D2
0x18000888c  mov     rcx, [rbp+188h]; this
0x180008893  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000889a  mov     edx, 0E01h; void *
0x18000889f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800088a5  mov     rcx, rbx; this
0x1800088a8  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800088ad  jmp     short loc_18000884F
0x1800088af  mov     rax, [rsp+280h+var_248]
0x1800088b4  lea     rcx, ds:0[rax*4]
0x1800088bc  test    rcx, rcx
0x1800088bf  jz      loc_18029B88E
0x1800088c5  mov     [r14], rcx
0x1800088c8  mov     eax, [rcx]
0x1800088ca  inc     eax
0x1800088cc  mov     [rcx], eax
0x1800088ce  jmp     loc_18029B8DC
0x18029b88e  mov     r8, r14
0x18029b891  lea     rdx, [rsp+280h+hHandle]
0x18029b896  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18029b89b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18029b8a0  mov     ebx, eax
0x18029b8a2  test    eax, eax
0x18029b8a4  jns     short loc_18029B8DC
0x18029b8a6  mov     rcx, [rbp+188h]; this
0x18029b8ad  lea     r8, aWil; "wil"
0x18029b8b4  mov     r9d, eax; char *
0x18029b8b7  mov     edx, 137h; void *
0x18029b8bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029b8c1  lea     rcx, [rsp+280h+var_240]
0x18029b8c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18029b8cb  lea     rcx, [rsp+280h+hHandle]
0x18029b8d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18029b8d5  mov     eax, ebx
0x18029b8d7  jmp     loc_18000885B
0x18029b8dc  lea     rcx, [rsp+280h+var_240]
0x18029b8e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18029b8e6  lea     rcx, [rsp+280h+hHandle]
0x18029b8eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18029b8f0  xor     eax, eax
0x18029b8f2  jmp     loc_18000885B
```
