# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180058e2c`
- end: `0x180059017`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `491`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180058bdc`

## callees

- `0x18002a220`
- `0x180035e7c`
- `0x180050354`
- `0x180058e2c`
- `0x180059020`
- `0x180059074`
- `0x180059090`
- `0x1800590ac`
- `0x180059528`
- `0x18005d300`
- `0x18005daf0`
- `0x18006129c`
- `0x180064b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180058eac`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180058eac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180058edc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180058edc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180058e67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180058e67`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rsi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // edi
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v20 = 120;
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
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v24 = v12;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v21);
    v16 = v15;
    v17 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)v16, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return v15;
  }
  v18 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    *a2 = v18;
    ++*v18;
  }
  else
  {
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v15 = v19;
    if ( v19 < 0 )
    {
      v16 = (unsigned int)v19;
      v17 = 311;
      goto LABEL_14;
    }
    v6 = (wil::details *)hHandle;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x180058e2c  mov     [rsp-8+arg_10], rbx
0x180058e31  mov     [rsp-8+arg_18], rsi
0x180058e36  push    rbp
0x180058e37  push    rdi
0x180058e38  push    r14
0x180058e3a  lea     rbp, [rsp-170h]
0x180058e42  sub     rsp, 270h
0x180058e49  mov     rax, cs:__security_cookie
0x180058e50  xor     rax, rsp
0x180058e53  mov     [rbp+180h+var_20], rax
0x180058e5a  mov     r14, rdx
0x180058e5d  mov     qword ptr [rdx], 0
0x180058e64  mov     rbx, rcx
0x180058e67  call    cs:__imp_GetCurrentProcessId
0x180058e6d  mov     [rsp+280h+var_258], rbx
0x180058e72  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180058e79  mov     r9d, eax
0x180058e7c  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180058e84  mov     edx, 104h; unsigned __int64
0x180058e89  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180058e8e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180058e93  mov     r9d, 1F0001h; dwDesiredAccess
0x180058e99  mov     [rsp+280h+hHandle], 0
0x180058ea2  xor     r8d, r8d; dwFlags
0x180058ea5  lea     rdx, [rsp+280h+Name]; lpName
0x180058eaa  xor     ecx, ecx; lpMutexAttributes
0x180058eac  call    cs:__imp_CreateMutexExW
0x180058eb2  mov     rdx, rax
0x180058eb5  lea     rcx, [rsp+280h+hHandle]
0x180058eba  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180058ebf  mov     rbx, [rsp+280h+hHandle]
0x180058ec4  test    rbx, rbx
0x180058ec7  jnz     short loc_180058ED3
0x180058ec9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180058ece  jmp     loc_180058FF0
0x180058ed3  xor     r8d, r8d; bAlertable
0x180058ed6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180058ed9  mov     rcx, rbx; hHandle
0x180058edc  call    cs:__imp_WaitForSingleObjectEx
0x180058ee2  cmp     eax, 102h
0x180058ee7  jz      short loc_180058F02
0x180058ee9  test    eax, 0FFFFFF7Fh
0x180058eee  jz      short loc_180058EFD
0x180058ef0  mov     rcx, [rbp+188h]; this
0x180058ef7  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180058efd  mov     rsi, rbx
0x180058f00  jmp     short loc_180058F04
0x180058f02  xor     esi, esi
0x180058f04  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180058f09  mov     [rsp+280h+var_240], rsi
0x180058f0e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180058f13  mov     [rsp+280h+var_248], 0
0x180058f1c  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180058f21  mov     edi, eax
0x180058f23  test    eax, eax
0x180058f25  jns     short loc_180058F67
0x180058f27  mov     rcx, [rbp+188h]; this
0x180058f2e  lea     r8, aWil; "wil"
0x180058f35  mov     r9d, eax; char *
0x180058f38  mov     edx, 66h ; 'f'; void *
0x180058f3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058f42  mov     rcx, [rbp+188h]; this
0x180058f49  lea     r8, aWil; "wil"
0x180058f50  mov     r9d, edi; char *
0x180058f53  mov     edx, 6Fh ; 'o'; void *
0x180058f58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058f5d  mov     r9d, edi
0x180058f60  mov     edx, 12Eh
0x180058f65  jmp     short loc_180058FA4
0x180058f67  mov     rax, [rsp+280h+var_248]
0x180058f6c  lea     rcx, ds:0[rax*4]
0x180058f74  test    rcx, rcx
0x180058f77  jz      short loc_180058F84
0x180058f79  mov     [r14], rcx
0x180058f7c  mov     eax, [rcx]
0x180058f7e  inc     eax
0x180058f80  mov     [rcx], eax
0x180058f82  jmp     short loc_180058FD4
0x180058f84  mov     r8, r14
0x180058f87  lea     rdx, [rsp+280h+hHandle]
0x180058f8c  lea     rcx, [rsp+280h+Name]
0x180058f91  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180058f96  mov     edi, eax
0x180058f98  test    eax, eax
0x180058f9a  jns     short loc_180058FCF
0x180058f9c  mov     r9d, eax; char *
0x180058f9f  mov     edx, 137h; void *
0x180058fa4  mov     rcx, [rbp+188h]; this
0x180058fab  lea     r8, aWil; "wil"
0x180058fb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058fb7  lea     rcx, [rsp+280h+var_240]
0x180058fbc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058fc1  lea     rcx, [rsp+280h+hHandle]
0x180058fc6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058fcb  mov     eax, edi
0x180058fcd  jmp     short loc_180058FF0
0x180058fcf  mov     rbx, [rsp+280h+hHandle]
0x180058fd4  test    rsi, rsi
0x180058fd7  jz      short loc_180058FE1
0x180058fd9  mov     rcx, rsi; this
0x180058fdc  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180058fe1  test    rbx, rbx
0x180058fe4  jz      short loc_180058FEE
0x180058fe6  mov     rcx, rbx; this
0x180058fe9  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180058fee  xor     eax, eax
0x180058ff0  mov     rcx, [rbp+180h+var_20]
0x180058ff7  xor     rcx, rsp; StackCookie
0x180058ffa  call    __security_check_cookie
0x180058fff  lea     r11, [rsp+280h+var_10]
0x180059007  mov     rbx, [r11+30h]
0x18005900b  mov     rsi, [r11+38h]
0x18005900f  mov     rsp, r11
0x180059012  pop     r14
0x180059014  pop     rdi
0x180059015  pop     rbp
0x180059016  retn
```
