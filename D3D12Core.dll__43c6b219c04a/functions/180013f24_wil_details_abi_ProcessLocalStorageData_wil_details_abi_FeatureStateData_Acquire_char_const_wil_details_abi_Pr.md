# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180013f24`
- end: `0x18001412e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180013ec8`

## callees

- `0x180013f24`
- `0x180014134`
- `0x180014368`
- `0x180014420`
- `0x1800146e8`
- `0x1800147fc`
- `0x180014b8c`
- `0x18006c68c`
- `0x18008e540`
- `0x1800aad80`
- `0x1800bb480`
- `0x1800c3908`
- `0x1800c4e88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180013fa4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180013fa4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014002`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014002`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013f5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013f5f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rdi
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rbx
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // esi
  _DWORD *v17; // rcx
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  void *v20; // rdx
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // edi
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v28; // [rsp+40h] [rbp-C0h] BYREF
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
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v28 = v12;
  v27 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v27, (bool *)v11);
  v16 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v15, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v18, (const char *)v16, v24);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v19, (const char *)v16, v25);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v20);
    wil::details::CloseHandle(v6, v20);
    return v16;
  }
  else
  {
    v17 = (_DWORD *)(4 * v27);
    if ( 4 * v27 )
    {
      *a2 = v17;
      ++*v17;
    }
    else
    {
      v21 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v23 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v22, (const char *)(unsigned int)v21, 304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
        return v23;
      }
      v6 = (wil::details *)hHandle;
    }
    if ( v12 )
      wil::details::ReleaseMutex(v12, v14);
    if ( v6 )
      wil::details::CloseHandle(v6, v14);
    return 0;
  }
}

```

## disassembly

```asm
0x180013f24  mov     [rsp-8+arg_10], rbx
0x180013f29  mov     [rsp-8+arg_18], rsi
0x180013f2e  push    rbp
0x180013f2f  push    rdi
0x180013f30  push    r14
0x180013f32  lea     rbp, [rsp-170h]
0x180013f3a  sub     rsp, 270h
0x180013f41  mov     rax, cs:__security_cookie
0x180013f48  xor     rax, rsp
0x180013f4b  mov     [rbp+180h+var_20], rax
0x180013f52  mov     r14, rdx
0x180013f55  mov     qword ptr [rdx], 0
0x180013f5c  mov     rbx, rcx
0x180013f5f  call    cs:__imp_GetCurrentProcessId
0x180013f65  mov     [rsp+280h+var_258], rbx
0x180013f6a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180013f71  mov     r9d, eax
0x180013f74  mov     [rsp+280h+var_260], 130h; int
0x180013f7c  mov     edx, 104h; unsigned __int64
0x180013f81  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180013f86  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013f8b  mov     r9d, 1F0001h; dwDesiredAccess
0x180013f91  mov     [rsp+280h+hHandle], 0
0x180013f9a  xor     r8d, r8d; dwFlags
0x180013f9d  lea     rdx, [rsp+280h+Name]; lpName
0x180013fa2  xor     ecx, ecx; lpMutexAttributes
0x180013fa4  call    cs:__imp_CreateMutexExW
0x180013faa  mov     rdx, rax
0x180013fad  lea     rcx, [rsp+280h+hHandle]
0x180013fb2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180013fb7  mov     rdi, [rsp+280h+hHandle]
0x180013fbc  test    rdi, rdi
0x180013fbf  jnz     short loc_180013FF9
0x180013fc1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180013fc6  jmp     short loc_180013FD2
0x180013fc8  mov     rcx, rdi; this
0x180013fcb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180013fd0  xor     eax, eax
0x180013fd2  mov     rcx, [rbp+180h+var_20]
0x180013fd9  xor     rcx, rsp; StackCookie
0x180013fdc  call    __security_check_cookie
0x180013fe1  lea     r11, [rsp+280h+var_10]
0x180013fe9  mov     rbx, [r11+30h]
0x180013fed  mov     rsi, [r11+38h]
0x180013ff1  mov     rsp, r11
0x180013ff4  pop     r14
0x180013ff6  pop     rdi
0x180013ff7  pop     rbp
0x180013ff8  retn
0x180013ff9  xor     r8d, r8d; bAlertable
0x180013ffc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013fff  mov     rcx, rdi; hHandle
0x180014002  call    cs:__imp_WaitForSingleObjectEx
0x180014008  cmp     eax, 102h
0x18001400d  jz      short loc_18001407A
0x18001400f  test    eax, 0FFFFFF7Fh
0x180014014  jnz     loc_1800140D6
0x18001401a  mov     rbx, rdi
0x18001401d  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180014022  mov     [rsp+280h+var_240], rbx
0x180014027  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001402c  mov     [rsp+280h+var_248], 0
0x180014035  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001403a  mov     esi, eax
0x18001403c  test    eax, eax
0x18001403e  js      short loc_18001407E
0x180014040  mov     rax, [rsp+280h+var_248]
0x180014045  lea     rcx, ds:0[rax*4]
0x18001404d  test    rcx, rcx
0x180014050  jz      loc_1800140E3
0x180014056  mov     [r14], rcx
0x180014059  mov     eax, [rcx]
0x18001405b  inc     eax
0x18001405d  mov     [rcx], eax
0x18001405f  test    rbx, rbx
0x180014062  jz      short loc_18001406C
0x180014064  mov     rcx, rbx; this
0x180014067  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18001406c  test    rdi, rdi
0x18001406f  jz      loc_180013FD0
0x180014075  jmp     loc_180013FC8
0x18001407a  xor     ebx, ebx
0x18001407c  jmp     short loc_18001401D
0x18001407e  mov     rcx, [rbp+188h]; this
0x180014085  mov     r9d, esi; char *
0x180014088  mov     edx, 66h ; 'f'; void *
0x18001408d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014092  mov     rcx, [rbp+188h]; this
0x180014099  mov     r9d, esi; char *
0x18001409c  mov     edx, 6Fh ; 'o'; void *
0x1800140a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800140a6  mov     rcx, [rbp+188h]; this
0x1800140ad  mov     r9d, esi; char *
0x1800140b0  mov     edx, 12Eh; void *
0x1800140b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800140ba  test    rbx, rbx
0x1800140bd  jz      short loc_1800140C7
0x1800140bf  mov     rcx, rbx; this
0x1800140c2  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800140c7  mov     rcx, rdi; this
0x1800140ca  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800140cf  mov     eax, esi
0x1800140d1  jmp     loc_180013FD2
0x1800140d6  mov     rcx, [rbp+188h]; this
0x1800140dd  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800140e3  mov     r8, r14
0x1800140e6  lea     rdx, [rsp+280h+hHandle]
0x1800140eb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800140f0  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800140f5  mov     edi, eax
0x1800140f7  test    eax, eax
0x1800140f9  jns     loc_180231F92
0x1800140ff  mov     rcx, [rbp+188h]; this
0x180014106  mov     r9d, eax; char *
0x180014109  mov     edx, 137h; void *
0x18001410e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014113  lea     rcx, [rsp+280h+var_240]
0x180014118  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001411d  lea     rcx, [rsp+280h+hHandle]
0x180014122  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014127  mov     eax, edi
0x180014129  jmp     loc_180013FD2
0x180231f92  mov     rdi, [rsp+280h+hHandle]
0x180231f97  jmp     loc_18001405F
```
