# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800288d8`
- end: `0x180028acf`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024a24`

## callees

- `0x180010da8`
- `0x180010dd0`
- `0x1800288d8`
- `0x1800318e0`
- `0x18003322c`
- `0x180033828`
- `0x180037154`
- `0x18003e920`
- `0x1800414b8`
- `0x180041648`
- `0x180041ce4`
- `0x180042024`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002894f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002894f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180028977`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180028977`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028913`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rsi
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rbx
  int ValueInternal; // eax
  unsigned int v14; // edi
  void *v15; // rdx
  _DWORD *v17; // rcx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_17:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return LastErrorFailHr;
  }
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
  v23[0] = v12;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v22, (bool *)v11);
  v14 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v17 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v17;
      ++*v17;
    }
    else
    {
      v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v18,
          120);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
        goto LABEL_17;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x66,
    (unsigned int)"wil",
    (const char *)(unsigned int)ValueInternal,
    120);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v19);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v20);
  if ( v12 )
    wil::details::ReleaseMutex(v12, v15);
  wil::details::CloseHandle(v6, v15);
  return v14;
}

```

## disassembly

```asm
0x1800288d8  mov     [rsp-8+arg_10], rbx
0x1800288dd  mov     [rsp-8+arg_18], rsi
0x1800288e2  push    rbp
0x1800288e3  push    rdi
0x1800288e4  push    r14
0x1800288e6  lea     rbp, [rsp-170h]
0x1800288ee  sub     rsp, 270h
0x1800288f5  mov     rax, cs:__security_cookie
0x1800288fc  xor     rax, rsp
0x1800288ff  mov     [rbp+180h+var_20], rax
0x180028906  mov     r14, rdx
0x180028909  mov     qword ptr [rdx], 0
0x180028910  mov     rbx, rcx
0x180028913  call    cs:__imp_GetCurrentProcessId
0x180028919  mov     [rsp+280h+var_258], rbx
0x18002891e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180028925  mov     r9d, eax
0x180028928  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180028930  mov     edx, 104h; unsigned __int64
0x180028935  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002893a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002893f  mov     r9d, 1F0001h; dwDesiredAccess
0x180028945  lea     rdx, [rsp+280h+Name]; lpName
0x18002894a  xor     r8d, r8d; dwFlags
0x18002894d  xor     ecx, ecx; lpMutexAttributes
0x18002894f  call    cs:__imp_CreateMutexExW
0x180028955  mov     [rsp+280h+var_250], rax
0x18002895a  mov     rsi, rax
0x18002895d  test    rax, rax
0x180028960  jnz     short loc_18002896E
0x180028962  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180028967  mov     ebx, eax
0x180028969  jmp     loc_180028AC1
0x18002896e  xor     r8d, r8d; bAlertable
0x180028971  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180028974  mov     rcx, rsi; hHandle
0x180028977  call    cs:__imp_WaitForSingleObjectEx
0x18002897d  cmp     eax, 102h
0x180028982  jz      short loc_18002899D
0x180028984  test    eax, 0FFFFFF7Fh
0x180028989  jz      short loc_180028998
0x18002898b  mov     rcx, [rbp+188h]; this
0x180028992  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180028998  mov     rbx, rsi
0x18002899b  jmp     short loc_18002899F
0x18002899d  xor     ebx, ebx
0x18002899f  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800289a4  mov     [rsp+280h+var_240], rbx
0x1800289a9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800289ae  mov     [rsp+280h+var_248], 0
0x1800289b7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800289bc  mov     edi, eax
0x1800289be  test    eax, eax
0x1800289c0  jns     short loc_180028A2C
0x1800289c2  mov     rcx, [rbp+188h]; this
0x1800289c9  lea     r8, aWil; "wil"
0x1800289d0  mov     r9d, eax; char *
0x1800289d3  mov     edx, 66h ; 'f'; void *
0x1800289d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800289dd  mov     rcx, [rbp+188h]; this
0x1800289e4  lea     r8, aWil; "wil"
0x1800289eb  mov     r9d, edi; char *
0x1800289ee  mov     edx, 6Fh ; 'o'; void *
0x1800289f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800289f8  mov     rcx, [rbp+188h]; this
0x1800289ff  lea     r8, aWil; "wil"
0x180028a06  mov     r9d, edi; char *
0x180028a09  mov     edx, 12Eh; void *
0x180028a0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a13  test    rbx, rbx
0x180028a16  jz      short loc_180028A20
0x180028a18  mov     rcx, rbx; this
0x180028a1b  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180028a20  mov     rcx, rsi; this
0x180028a23  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180028a28  mov     eax, edi
0x180028a2a  jmp     short loc_180028A5D
0x180028a2c  mov     rax, [rsp+280h+var_248]
0x180028a31  lea     rcx, ds:0[rax*4]
0x180028a39  test    rcx, rcx
0x180028a3c  jz      short loc_180028A84
0x180028a3e  mov     [r14], rcx
0x180028a41  mov     eax, [rcx]
0x180028a43  inc     eax
0x180028a45  mov     [rcx], eax
0x180028a47  lea     rcx, [rsp+280h+var_240]
0x180028a4c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028a51  lea     rcx, [rsp+280h+var_250]
0x180028a56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028a5b  xor     eax, eax
0x180028a5d  mov     rcx, [rbp+180h+var_20]
0x180028a64  xor     rcx, rsp; StackCookie
0x180028a67  call    __security_check_cookie
0x180028a6c  lea     r11, [rsp+280h+var_10]
0x180028a74  mov     rbx, [r11+30h]
0x180028a78  mov     rsi, [r11+38h]
0x180028a7c  mov     rsp, r11
0x180028a7f  pop     r14
0x180028a81  pop     rdi
0x180028a82  pop     rbp
0x180028a83  retn
0x180028a84  mov     r8, r14
0x180028a87  lea     rdx, [rsp+280h+var_250]
0x180028a8c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180028a91  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180028a96  mov     ebx, eax
0x180028a98  test    eax, eax
0x180028a9a  jns     short loc_180028A47
0x180028a9c  mov     rcx, [rbp+188h]; this
0x180028aa3  lea     r8, aWil; "wil"
0x180028aaa  mov     r9d, eax; char *
0x180028aad  mov     edx, 137h; void *
0x180028ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ab7  lea     rcx, [rsp+280h+var_240]
0x180028abc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028ac1  lea     rcx, [rsp+280h+var_250]
0x180028ac6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028acb  mov     eax, ebx
0x180028acd  jmp     short loc_180028A5D
```
