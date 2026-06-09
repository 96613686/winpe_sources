# wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)

- ea: `0x180006b58`
- end: `0x180006d76`
- name: `?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800113f8`

## callees

- `0x180006b58`
- `0x180006edc`
- `0x180006f00`
- `0x180006f1c`
- `0x180024044`
- `0x180024794`
- `0x18002a294`
- `0x18002cdd8`
- `0x180043680`
- `0x18004b190`
- `0x18004bc20`
- `0x18004c860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006c4a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006c4a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006c01`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006c01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006bc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006bc5`

## pseudocode

```c
__int64 wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared()
{
  __int64 v0; // rsi
  _DWORD *v2; // rdi
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  int LastErrorFailHr; // ebx
  DWORD v8; // eax
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // r14
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // edi
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v24; // [rsp+48h] [rbp-B8h]
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v0 = wil::details_abi::g_pProcessLocalData;
  if ( *(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
  v2 = 0;
  v24 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v19 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    if ( LastErrorFailHr < 0 )
      return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
    goto LABEL_5;
  }
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  v23 = v12;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v22, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v20);
    v16 = v15;
    v17 = 302;
LABEL_11:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)v16, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
  }
  v2 = (_DWORD *)(4 * v22);
  if ( 4 * v22 )
  {
    ++*v2;
  }
  else
  {
    v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    if ( v18 < 0 )
    {
      v16 = (unsigned int)v18;
      v17 = 311;
      goto LABEL_11;
    }
    v2 = v24;
    v6 = v21;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
LABEL_5:
  if ( !*(_QWORD *)(v0 + 8) )
    *(_QWORD *)(v0 + 8) = v2;
  return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
}

```

## disassembly

```asm
0x180006b58  push    rbp
0x180006b5a  push    rbx
0x180006b5b  push    rsi
0x180006b5c  push    rdi
0x180006b5d  push    r14
0x180006b5f  lea     rbp, [rsp-170h]
0x180006b67  sub     rsp, 270h
0x180006b6e  mov     rax, cs:__security_cookie
0x180006b75  xor     rax, rsp
0x180006b78  mov     [rbp+190h+var_30], rax
0x180006b7f  mov     rsi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006b86  cmp     qword ptr [rsi+8], 0
0x180006b8b  jz      short loc_180006BBB
0x180006b8d  mov     rax, [rsi+8]
0x180006b91  lea     rcx, [rax+20h]
0x180006b95  neg     rax
0x180006b98  sbb     rax, rax
0x180006b9b  and     rax, rcx
0x180006b9e  mov     rcx, [rbp+190h+var_30]
0x180006ba5  xor     rcx, rsp; StackCookie
0x180006ba8  call    __security_check_cookie
0x180006bad  add     rsp, 270h
0x180006bb4  pop     r14
0x180006bb6  pop     rdi
0x180006bb7  pop     rsi
0x180006bb8  pop     rbx
0x180006bb9  pop     rbp
0x180006bba  retn
0x180006bbb  mov     rbx, [rsi]
0x180006bbe  xor     edi, edi
0x180006bc0  mov     [rsp+290h+var_248], rdi
0x180006bc5  call    cs:__imp_GetCurrentProcessId
0x180006bcb  mov     [rsp+290h+var_268], rbx
0x180006bd0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006bd7  mov     r9d, eax
0x180006bda  mov     [rsp+290h+var_270], 78h ; 'x'; int
0x180006be2  mov     edx, 104h; unsigned __int64
0x180006be7  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180006bec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006bf1  mov     r9d, 1F0001h; dwDesiredAccess
0x180006bf7  lea     rdx, [rsp+290h+Name]; lpName
0x180006bfc  xor     r8d, r8d; dwFlags
0x180006bff  xor     ecx, ecx; lpMutexAttributes
0x180006c01  call    cs:__imp_CreateMutexExW
0x180006c07  mov     [rsp+290h+var_260], rax
0x180006c0c  mov     rbx, rax
0x180006c0f  test    rax, rax
0x180006c12  jnz     short loc_180006C41
0x180006c14  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006c19  lea     rcx, [rsp+290h+var_260]
0x180006c1e  mov     ebx, eax
0x180006c20  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006c25  test    ebx, ebx
0x180006c27  js      loc_180006B8D
0x180006c2d  cmp     qword ptr [rsi+8], 0
0x180006c32  jnz     loc_180006B8D
0x180006c38  mov     [rsi+8], rdi
0x180006c3c  jmp     loc_180006B8D
0x180006c41  xor     r8d, r8d; bAlertable
0x180006c44  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006c47  mov     rcx, rbx; hHandle
0x180006c4a  call    cs:__imp_WaitForSingleObjectEx
0x180006c50  cmp     eax, 102h
0x180006c55  jnz     loc_180006D1A
0x180006c5b  xor     r14d, r14d
0x180006c5e  lea     r8, [rsp+290h+var_258]; unsigned __int64 *
0x180006c63  mov     [rsp+290h+var_250], r14
0x180006c68  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180006c6d  mov     [rsp+290h+var_258], rdi
0x180006c72  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006c77  mov     edi, eax
0x180006c79  test    eax, eax
0x180006c7b  jns     short loc_180006CE7
0x180006c7d  mov     rcx, [rbp+198h]; this
0x180006c84  lea     r8, aWil; "wil"
0x180006c8b  mov     r9d, eax; char *
0x180006c8e  mov     edx, 66h ; 'f'; void *
0x180006c93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c98  mov     rcx, [rbp+198h]; this
0x180006c9f  lea     r8, aWil; "wil"
0x180006ca6  mov     r9d, edi; char *
0x180006ca9  mov     edx, 6Fh ; 'o'; void *
0x180006cae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006cb3  mov     r9d, edi; char *
0x180006cb6  mov     edx, 12Eh; void *
0x180006cbb  mov     rcx, [rbp+198h]; this
0x180006cc2  lea     r8, aWil; "wil"
0x180006cc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006cce  lea     rcx, [rsp+290h+var_250]
0x180006cd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006cd8  lea     rcx, [rsp+290h+var_260]
0x180006cdd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006ce2  jmp     loc_180006B8D
0x180006ce7  mov     rax, [rsp+290h+var_258]
0x180006cec  lea     rdi, ds:0[rax*4]
0x180006cf4  test    rdi, rdi
0x180006cf7  jz      short loc_180006D3B
0x180006cf9  mov     eax, [rdi]
0x180006cfb  inc     eax
0x180006cfd  mov     [rdi], eax
0x180006cff  test    r14, r14
0x180006d02  jnz     short loc_180006D6C
0x180006d04  test    rbx, rbx
0x180006d07  jz      loc_180006C2D
0x180006d0d  mov     rcx, rbx; this
0x180006d10  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180006d15  jmp     loc_180006C2D
0x180006d1a  test    eax, 0FFFFFF7Fh
0x180006d1f  jz      short loc_180006D33
0x180006d21  mov     rcx, [rbp+198h]; this
0x180006d28  mov     edx, 0E01h; void *
0x180006d2d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006d33  mov     r14, rbx
0x180006d36  jmp     loc_180006C5E
0x180006d3b  lea     r8, [rsp+290h+var_248]
0x180006d40  lea     rdx, [rsp+290h+var_260]
0x180006d45  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180006d4a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006d4f  test    eax, eax
0x180006d51  jns     short loc_180006D60
0x180006d53  mov     r9d, eax
0x180006d56  mov     edx, 137h
0x180006d5b  jmp     loc_180006CBB
0x180006d60  mov     rdi, [rsp+290h+var_248]
0x180006d65  mov     rbx, [rsp+290h+var_260]
0x180006d6a  jmp     short loc_180006CFF
0x180006d6c  mov     rcx, r14; this
0x180006d6f  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180006d74  jmp     short loc_180006D04
```
