# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180015f30`
- end: `0x18001613c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180033058`

## callees

- `0x18000a6fc`
- `0x180010a90`
- `0x1800154e0`
- `0x180015f30`
- `0x1800165ac`
- `0x180017e64`
- `0x18005d8bc`
- `0x180069394`
- `0x1800753a0`
- `0x180087e80`
- `0x18008cd48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015fcd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015fcd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180015fa7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180015fa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015f6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015f6b`

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
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  void *v16; // rdx
  _DWORD *v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  v25[0] = v12;
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v24, (bool *)v11);
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v22);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
    wil::details::CloseHandle(v6, v16);
    return v15;
  }
  v17 = (_DWORD *)(4 * v24);
  if ( 4 * v24 )
  {
    *a2 = v17;
    ++*v17;
LABEL_17:
    if ( v12 )
      wil::details::ReleaseMutex(v12, v14);
    if ( v6 )
      wil::details::CloseHandle(v6, v14);
    return 0;
  }
  v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v6 = v23;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v18, 120);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
  if ( v23 )
    wil::details::CloseHandle(v23, v20);
  return v19;
}

```

## disassembly

```asm
0x180015f30  mov     [rsp-8+arg_10], rbx
0x180015f35  mov     [rsp-8+arg_18], rsi
0x180015f3a  push    rbp
0x180015f3b  push    rdi
0x180015f3c  push    r14
0x180015f3e  lea     rbp, [rsp-170h]
0x180015f46  sub     rsp, 270h
0x180015f4d  mov     rax, cs:__security_cookie
0x180015f54  xor     rax, rsp
0x180015f57  mov     [rbp+180h+var_20], rax
0x180015f5e  mov     r14, rdx
0x180015f61  mov     qword ptr [rdx], 0
0x180015f68  mov     rbx, rcx
0x180015f6b  call    cs:__imp_GetCurrentProcessId
0x180015f71  mov     [rsp+280h+var_258], rbx
0x180015f76  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180015f7d  mov     r9d, eax
0x180015f80  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180015f88  mov     edx, 104h; unsigned __int64
0x180015f8d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180015f92  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015f97  mov     r9d, 1F0001h; dwDesiredAccess
0x180015f9d  lea     rdx, [rsp+280h+Name]; lpName
0x180015fa2  xor     r8d, r8d; dwFlags
0x180015fa5  xor     ecx, ecx; lpMutexAttributes
0x180015fa7  call    cs:__imp_CreateMutexExW
0x180015fad  mov     [rsp+280h+var_250], rax
0x180015fb2  mov     rbx, rax
0x180015fb5  test    rax, rax
0x180015fb8  jnz     short loc_180015FC4
0x180015fba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180015fbf  jmp     loc_180016115
0x180015fc4  xor     r8d, r8d; bAlertable
0x180015fc7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180015fca  mov     rcx, rbx; hHandle
0x180015fcd  call    cs:__imp_WaitForSingleObjectEx
0x180015fd3  cmp     eax, 102h
0x180015fd8  jz      short loc_180015FF8
0x180015fda  test    eax, 0FFFFFF7Fh
0x180015fdf  jz      short loc_180015FF3
0x180015fe1  mov     rcx, [rbp+188h]; this
0x180015fe8  mov     edx, 0E01h; void *
0x180015fed  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180015ff3  mov     rdi, rbx
0x180015ff6  jmp     short loc_180015FFA
0x180015ff8  xor     edi, edi
0x180015ffa  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180015fff  mov     [rsp+280h+var_240], rdi
0x180016004  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180016009  mov     [rsp+280h+var_248], 0
0x180016012  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180016017  mov     esi, eax
0x180016019  test    eax, eax
0x18001601b  jns     short loc_180016087
0x18001601d  mov     rcx, [rbp+188h]; this
0x180016024  lea     r8, aWil; "wil"
0x18001602b  mov     r9d, eax; char *
0x18001602e  mov     edx, 66h ; 'f'; void *
0x180016033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016038  mov     rcx, [rbp+188h]; this
0x18001603f  lea     r8, aWil; "wil"
0x180016046  mov     r9d, esi; char *
0x180016049  mov     edx, 6Fh ; 'o'; void *
0x18001604e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016053  mov     rcx, [rbp+188h]; this
0x18001605a  lea     r8, aWil; "wil"
0x180016061  mov     r9d, esi; char *
0x180016064  mov     edx, 12Eh; void *
0x180016069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001606e  lea     rcx, [rsp+280h+var_240]
0x180016073  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016078  mov     rcx, rbx; this
0x18001607b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180016080  mov     eax, esi
0x180016082  jmp     loc_180016115
0x180016087  mov     rax, [rsp+280h+var_248]
0x18001608c  lea     rcx, ds:0[rax*4]
0x180016094  test    rcx, rcx
0x180016097  jz      short loc_1800160A4
0x180016099  mov     [r14], rcx
0x18001609c  mov     eax, [rcx]
0x18001609e  inc     eax
0x1800160a0  mov     [rcx], eax
0x1800160a2  jmp     short loc_1800160F9
0x1800160a4  mov     r8, r14
0x1800160a7  lea     rdx, [rsp+280h+var_250]
0x1800160ac  lea     rcx, [rsp+280h+Name]
0x1800160b1  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800160b6  mov     ebx, eax
0x1800160b8  test    eax, eax
0x1800160ba  jns     short loc_1800160F4
0x1800160bc  mov     rcx, [rbp+188h]; this
0x1800160c3  lea     r8, aWil; "wil"
0x1800160ca  mov     r9d, eax; char *
0x1800160cd  mov     edx, 137h; void *
0x1800160d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800160d7  lea     rcx, [rsp+280h+var_240]
0x1800160dc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800160e1  mov     rcx, [rsp+280h+var_250]; this
0x1800160e6  test    rcx, rcx
0x1800160e9  jz      short loc_1800160F0
0x1800160eb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800160f0  mov     eax, ebx
0x1800160f2  jmp     short loc_180016115
0x1800160f4  mov     rbx, [rsp+280h+var_250]
0x1800160f9  test    rdi, rdi
0x1800160fc  jz      short loc_180016106
0x1800160fe  mov     rcx, rdi; this
0x180016101  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180016106  test    rbx, rbx
0x180016109  jz      short loc_180016113
0x18001610b  mov     rcx, rbx; this
0x18001610e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180016113  xor     eax, eax
0x180016115  mov     rcx, [rbp+180h+var_20]
0x18001611c  xor     rcx, rsp; StackCookie
0x18001611f  call    __security_check_cookie
0x180016124  lea     r11, [rsp+280h+var_10]
0x18001612c  mov     rbx, [r11+30h]
0x180016130  mov     rsi, [r11+38h]
0x180016134  mov     rsp, r11
0x180016137  pop     r14
0x180016139  pop     rdi
0x18001613a  pop     rbp
0x18001613b  retn
```
