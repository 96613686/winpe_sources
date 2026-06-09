# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000dc94`
- end: `0x18000de9b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001f4ec`

## callees

- `0x18000dc94`
- `0x18000dea4`
- `0x18000dee0`
- `0x18001dbbc`
- `0x18001ded0`
- `0x18001deec`
- `0x18001e798`
- `0x18001e840`
- `0x18002c570`
- `0x18003c324`
- `0x18003d2c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000dd0b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000dd0b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000dd31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000dd31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dccf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dccf`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  unsigned int v14; // esi
  void *v15; // rdx
  _DWORD *v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  void *v19; // rdx
  void *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  wil::details *v23; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v23 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
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
  v25[0] = v12;
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v24, (bool *)v11);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v21);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v22);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v15);
    wil::details::CloseHandle(v6, v15);
    return v14;
  }
  v16 = (_DWORD *)(4 * v24);
  if ( 4 * v24 )
  {
    *a2 = v16;
    ++*v16;
LABEL_19:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
    if ( v6 )
      wil::details::CloseHandle(v6, v20);
    return 0;
  }
  v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
  v18 = v17;
  if ( v17 >= 0 )
  {
    v6 = v23;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v17, 120);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
  if ( v23 )
    wil::details::CloseHandle(v23, v19);
  return v18;
}

```

## disassembly

```asm
0x18000dc94  mov     [rsp-8+arg_10], rbx
0x18000dc99  mov     [rsp-8+arg_18], rsi
0x18000dc9e  push    rbp
0x18000dc9f  push    rdi
0x18000dca0  push    r14
0x18000dca2  lea     rbp, [rsp-170h]
0x18000dcaa  sub     rsp, 270h
0x18000dcb1  mov     rax, cs:__security_cookie
0x18000dcb8  xor     rax, rsp
0x18000dcbb  mov     [rbp+180h+var_20], rax
0x18000dcc2  mov     r14, rdx
0x18000dcc5  mov     qword ptr [rdx], 0
0x18000dccc  mov     rbx, rcx
0x18000dccf  call    cs:__imp_GetCurrentProcessId
0x18000dcd5  mov     [rsp+280h+var_258], rbx
0x18000dcda  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000dce1  mov     r9d, eax
0x18000dce4  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x18000dcec  mov     edx, 104h; unsigned __int64
0x18000dcf1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000dcf6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dcfb  mov     r9d, 1F0001h; dwDesiredAccess
0x18000dd01  lea     rdx, [rsp+280h+Name]; lpName
0x18000dd06  xor     r8d, r8d; dwFlags
0x18000dd09  xor     ecx, ecx; lpMutexAttributes
0x18000dd0b  call    cs:__imp_CreateMutexExW
0x18000dd11  mov     [rsp+280h+var_250], rax
0x18000dd16  mov     rbx, rax
0x18000dd19  test    rax, rax
0x18000dd1c  jnz     short loc_18000DD28
0x18000dd1e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000dd23  jmp     loc_18000DE74
0x18000dd28  xor     r8d, r8d; bAlertable
0x18000dd2b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000dd2e  mov     rcx, rbx; hHandle
0x18000dd31  call    cs:__imp_WaitForSingleObjectEx
0x18000dd37  cmp     eax, 102h
0x18000dd3c  jz      short loc_18000DD57
0x18000dd3e  test    eax, 0FFFFFF7Fh
0x18000dd43  jz      short loc_18000DD52
0x18000dd45  mov     rcx, [rbp+188h]; this
0x18000dd4c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000dd52  mov     rdi, rbx
0x18000dd55  jmp     short loc_18000DD59
0x18000dd57  xor     edi, edi
0x18000dd59  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18000dd5e  mov     [rsp+280h+var_240], rdi
0x18000dd63  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000dd68  mov     [rsp+280h+var_248], 0
0x18000dd71  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000dd76  mov     esi, eax
0x18000dd78  test    eax, eax
0x18000dd7a  jns     short loc_18000DDE9
0x18000dd7c  mov     rcx, [rbp+188h]; this
0x18000dd83  lea     r8, aWil; "wil"
0x18000dd8a  mov     r9d, eax; char *
0x18000dd8d  mov     edx, 66h ; 'f'; void *
0x18000dd92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd97  mov     rcx, [rbp+188h]; this
0x18000dd9e  lea     r8, aWil; "wil"
0x18000dda5  mov     r9d, esi; char *
0x18000dda8  mov     edx, 6Fh ; 'o'; void *
0x18000ddad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ddb2  mov     rcx, [rbp+188h]; this
0x18000ddb9  lea     r8, aWil; "wil"
0x18000ddc0  mov     r9d, esi; char *
0x18000ddc3  mov     edx, 12Eh; void *
0x18000ddc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ddcd  test    rdi, rdi
0x18000ddd0  jz      short loc_18000DDDA
0x18000ddd2  mov     rcx, rdi; this
0x18000ddd5  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000ddda  mov     rcx, rbx; this
0x18000dddd  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000dde2  mov     eax, esi
0x18000dde4  jmp     loc_18000DE74
0x18000dde9  mov     rax, [rsp+280h+var_248]
0x18000ddee  lea     rcx, ds:0[rax*4]
0x18000ddf6  test    rcx, rcx
0x18000ddf9  jz      short loc_18000DE06
0x18000ddfb  mov     [r14], rcx
0x18000ddfe  mov     eax, [rcx]
0x18000de00  inc     eax
0x18000de02  mov     [rcx], eax
0x18000de04  jmp     short loc_18000DE5B
0x18000de06  mov     r8, r14
0x18000de09  lea     rdx, [rsp+280h+var_250]
0x18000de0e  lea     rcx, [rsp+280h+Name]
0x18000de13  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000de18  mov     ebx, eax
0x18000de1a  test    eax, eax
0x18000de1c  jns     short loc_18000DE56
0x18000de1e  mov     rcx, [rbp+188h]; this
0x18000de25  lea     r8, aWil; "wil"
0x18000de2c  mov     r9d, eax; char *
0x18000de2f  mov     edx, 137h; void *
0x18000de34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de39  lea     rcx, [rsp+280h+var_240]
0x18000de3e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000de43  mov     rcx, [rsp+280h+var_250]; this
0x18000de48  test    rcx, rcx
0x18000de4b  jz      short loc_18000DE52
0x18000de4d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000de52  mov     eax, ebx
0x18000de54  jmp     short loc_18000DE74
0x18000de56  mov     rbx, [rsp+280h+var_250]
0x18000de5b  lea     rcx, [rsp+280h+var_240]
0x18000de60  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000de65  test    rbx, rbx
0x18000de68  jz      short loc_18000DE72
0x18000de6a  mov     rcx, rbx; this
0x18000de6d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000de72  xor     eax, eax
0x18000de74  mov     rcx, [rbp+180h+var_20]
0x18000de7b  xor     rcx, rsp; StackCookie
0x18000de7e  call    __security_check_cookie
0x18000de83  lea     r11, [rsp+280h+var_10]
0x18000de8b  mov     rbx, [r11+30h]
0x18000de8f  mov     rsi, [r11+38h]
0x18000de93  mov     rsp, r11
0x18000de96  pop     r14
0x18000de98  pop     rdi
0x18000de99  pop     rbp
0x18000de9a  retn
```
