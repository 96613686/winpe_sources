# wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)

- ea: `0x180004e10`
- end: `0x180005017`
- name: `?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ`
- size: `519`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180013464`

## callees

- `0x180004c94`
- `0x180004e10`
- `0x180005020`
- `0x1800050b0`
- `0x180005538`
- `0x180005564`
- `0x180012a48`
- `0x180012a8c`
- `0x180013244`
- `0x180016b4c`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004edd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004edd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004e7e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004e7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e42`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(__int64 a1)
{
  _DWORD *v2; // rsi
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  __int64 v7; // rdx
  __int64 result; // rax
  DWORD v9; // eax
  void *v10; // rdx
  __int64 v11; // r8
  char *v12; // r9
  wil::details *v13; // rbp
  int ValueInternal; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  unsigned int v17; // esi
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  void *v20; // rdx
  void *v21; // rdx
  int v22; // eax
  unsigned int v23; // r8d
  int v24; // [rsp+20h] [rbp-278h]
  int v25; // [rsp+20h] [rbp-278h]
  wil::details *v26; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int64 v27; // [rsp+38h] [rbp-260h] BYREF
  _DWORD *v28; // [rsp+40h] [rbp-258h]
  WCHAR Name[264]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  if ( *(_QWORD *)(a1 + 8) )
    goto LABEL_6;
  v2 = 0;
  v28 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v26 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    if ( (int)wil::details::GetLastErrorFailHr(v5) < 0 )
      goto LABEL_6;
    goto LABEL_4;
  }
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v13 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v10, v11, v12);
    v13 = v6;
  }
  v27 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, &v27, (bool *)v12);
  v17 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v16, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v18, (const char *)v17, v24);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v19, (const char *)v17, v25);
    if ( v13 )
      wil::details::ReleaseMutex(v13, v20);
    wil::details::CloseHandle(v6, v20);
  }
  else
  {
    v2 = (_DWORD *)(4 * v27);
    if ( 4 * v27 )
    {
      ++*v2;
LABEL_15:
      if ( v13 )
        wil::details::ReleaseMutex(v13, v15);
      if ( v6 )
        wil::details::CloseHandle(v6, v15);
LABEL_4:
      if ( !*(_QWORD *)(a1 + 8) )
        *(_QWORD *)(a1 + 8) = v2;
      goto LABEL_6;
    }
    v22 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    if ( v22 >= 0 )
    {
      v2 = v28;
      v6 = v26;
      goto LABEL_15;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v23, (const char *)(unsigned int)v22, 304);
    if ( v13 )
      wil::details::ReleaseMutex(v13, v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((void **)&v26);
  }
LABEL_6:
  v7 = *(_QWORD *)(a1 + 8);
  result = v7 + 32;
  if ( !v7 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180004e10  push    rbx
0x180004e12  push    rbp
0x180004e13  push    rsi
0x180004e14  push    rdi
0x180004e15  sub     rsp, 278h
0x180004e1c  mov     rax, cs:__security_cookie
0x180004e23  xor     rax, rsp
0x180004e26  mov     [rsp+298h+var_38], rax
0x180004e2e  cmp     qword ptr [rcx+8], 0
0x180004e33  mov     rdi, rcx
0x180004e36  jnz     short loc_180004EA5
0x180004e38  mov     rbx, [rcx]
0x180004e3b  xor     esi, esi
0x180004e3d  mov     [rsp+298h+var_258], rsi
0x180004e42  call    cs:__imp_GetCurrentProcessId
0x180004e48  mov     [rsp+298h+var_270], rbx
0x180004e4d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004e54  mov     r9d, eax
0x180004e57  mov     [rsp+298h+var_278], 130h; int
0x180004e5f  mov     edx, 104h; unsigned __int64
0x180004e64  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x180004e69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004e6e  mov     r9d, 1F0001h; dwDesiredAccess
0x180004e74  lea     rdx, [rsp+298h+Name]; lpName
0x180004e79  xor     r8d, r8d; dwFlags
0x180004e7c  xor     ecx, ecx; lpMutexAttributes
0x180004e7e  call    cs:__imp_CreateMutexExW
0x180004e84  mov     [rsp+298h+var_268], rax
0x180004e89  mov     rbx, rax
0x180004e8c  test    rax, rax
0x180004e8f  jnz     short loc_180004ED2
0x180004e91  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004e96  test    eax, eax
0x180004e98  js      short loc_180004EA5
0x180004e9a  cmp     qword ptr [rdi+8], 0
0x180004e9f  jnz     short loc_180004EA5
0x180004ea1  mov     [rdi+8], rsi
0x180004ea5  mov     rdx, [rdi+8]
0x180004ea9  xor     ecx, ecx
0x180004eab  test    rdx, rdx
0x180004eae  lea     rax, [rdx+20h]
0x180004eb2  cmovz   rax, rcx
0x180004eb6  mov     rcx, [rsp+298h+var_38]
0x180004ebe  xor     rcx, rsp; StackCookie
0x180004ec1  call    __security_check_cookie
0x180004ec6  add     rsp, 278h
0x180004ecd  pop     rdi
0x180004ece  pop     rsi
0x180004ecf  pop     rbp
0x180004ed0  pop     rbx
0x180004ed1  retn
0x180004ed2  xor     r8d, r8d; bAlertable
0x180004ed5  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180004eda  mov     rcx, rbx; hHandle
0x180004edd  call    cs:__imp_WaitForSingleObjectEx
0x180004ee3  cmp     eax, 102h
0x180004ee8  jz      loc_180004FE9
0x180004eee  test    eax, 0FFFFFF7Fh
0x180004ef3  jnz     short loc_180004F51
0x180004ef5  mov     rbp, rbx
0x180004ef8  lea     r8, [rsp+298h+var_260]; unsigned __int64 *
0x180004efd  mov     [rsp+298h+var_260], rsi
0x180004f02  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x180004f07  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004f0c  mov     esi, eax
0x180004f0e  test    eax, eax
0x180004f10  js      short loc_180004F5F
0x180004f12  mov     rax, [rsp+298h+var_260]
0x180004f17  lea     rsi, ds:0[rax*4]
0x180004f1f  test    rsi, rsi
0x180004f22  jz      loc_180004FF0
0x180004f28  mov     eax, [rsi]
0x180004f2a  inc     eax
0x180004f2c  mov     [rsi], eax
0x180004f2e  test    rbp, rbp
0x180004f31  jz      short loc_180004F3B
0x180004f33  mov     rcx, rbp; this
0x180004f36  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180004f3b  test    rbx, rbx
0x180004f3e  jz      loc_180004E9A
0x180004f44  mov     rcx, rbx; this
0x180004f47  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004f4c  jmp     loc_180004E9A
0x180004f51  mov     rcx, [rsp+298h]; this
0x180004f59  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004f5f  mov     rcx, [rsp+298h]; this
0x180004f67  mov     r9d, esi; char *
0x180004f6a  mov     edx, 66h ; 'f'; void *
0x180004f6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f74  mov     rcx, [rsp+298h]; this
0x180004f7c  mov     r9d, esi; char *
0x180004f7f  mov     edx, 6Fh ; 'o'; void *
0x180004f84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f89  mov     rcx, [rsp+298h]; this
0x180004f91  mov     r9d, esi; char *
0x180004f94  mov     edx, 12Eh; void *
0x180004f99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f9e  test    rbp, rbp
0x180004fa1  jz      short loc_180004FAB
0x180004fa3  mov     rcx, rbp; this
0x180004fa6  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180004fab  mov     rcx, rbx; this
0x180004fae  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004fb3  jmp     loc_180004EA5
0x180004fb8  mov     rcx, [rsp+298h]; this
0x180004fc0  mov     r9d, eax; char *
0x180004fc3  mov     edx, 137h; void *
0x180004fc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004fcd  test    rbp, rbp
0x180004fd0  jz      short loc_180004FDA
0x180004fd2  mov     rcx, rbp; this
0x180004fd5  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180004fda  lea     rcx, [rsp+298h+var_268]
0x180004fdf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004fe4  jmp     loc_180004EA5
0x180004fe9  xor     ebp, ebp
0x180004feb  jmp     loc_180004EF8
0x180004ff0  lea     r8, [rsp+298h+var_258]
0x180004ff5  lea     rdx, [rsp+298h+var_268]
0x180004ffa  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x180004fff  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005004  test    eax, eax
0x180005006  js      short loc_180004FB8
0x180005008  mov     rsi, [rsp+298h+var_258]
0x18000500d  mov     rbx, [rsp+298h+var_268]
0x180005012  jmp     loc_180004F2E
```
