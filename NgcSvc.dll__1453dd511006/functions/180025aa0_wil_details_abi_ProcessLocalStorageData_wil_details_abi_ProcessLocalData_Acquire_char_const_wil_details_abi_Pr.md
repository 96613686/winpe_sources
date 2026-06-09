# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180025aa0`
- end: `0x180025c69`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180052fe0`

## callees

- `0x18000782c`
- `0x18000948c`
- `0x180025aa0`
- `0x180025c70`
- `0x180026410`
- `0x180026498`
- `0x180048098`
- `0x18004cf08`
- `0x180051640`
- `0x18005cee0`
- `0x18006110c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180025b17`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180025b17`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180025b3d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180025b3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025adb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025adb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details *v12; // rdi
  int Pointer; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  void *v16; // rdx
  _DWORD *v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  void *v20; // rdx
  wil::details *v21; // [rsp+30h] [rbp-D0h]
  void *v22; // [rsp+38h] [rbp-C8h] BYREF
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
  v23[0] = v12;
  v22 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v22);
  v15 = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      120);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
    wil::details::CloseHandle(v6, v16);
    return v15;
  }
  v17 = v22;
  if ( v22 )
  {
    *a2 = v22;
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
    v6 = v21;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v18, 120);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
  if ( v21 )
    wil::details::CloseHandle(v21, v20);
  return v19;
}

```

## disassembly

```asm
0x180025aa0  mov     [rsp-8+arg_10], rbx
0x180025aa5  mov     [rsp-8+arg_18], rsi
0x180025aaa  push    rbp
0x180025aab  push    rdi
0x180025aac  push    r14
0x180025aae  lea     rbp, [rsp-170h]
0x180025ab6  sub     rsp, 270h
0x180025abd  mov     rax, cs:__security_cookie
0x180025ac4  xor     rax, rsp
0x180025ac7  mov     [rbp+180h+var_20], rax
0x180025ace  mov     r14, rdx
0x180025ad1  mov     qword ptr [rdx], 0
0x180025ad8  mov     rbx, rcx
0x180025adb  call    cs:__imp_GetCurrentProcessId
0x180025ae1  mov     [rsp+280h+var_258], rbx
0x180025ae6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180025aed  mov     r9d, eax
0x180025af0  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180025af8  mov     edx, 104h; unsigned __int64
0x180025afd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180025b02  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025b07  mov     r9d, 1F0001h; dwDesiredAccess
0x180025b0d  lea     rdx, [rsp+280h+Name]; lpName
0x180025b12  xor     r8d, r8d; dwFlags
0x180025b15  xor     ecx, ecx; lpMutexAttributes
0x180025b17  call    cs:__imp_CreateMutexExW
0x180025b1d  mov     [rsp+280h+var_250], rax
0x180025b22  mov     rbx, rax
0x180025b25  test    rax, rax
0x180025b28  jnz     short loc_180025B34
0x180025b2a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180025b2f  jmp     loc_180025C42
0x180025b34  xor     r8d, r8d; bAlertable
0x180025b37  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180025b3a  mov     rcx, rbx; hHandle
0x180025b3d  call    cs:__imp_WaitForSingleObjectEx
0x180025b43  cmp     eax, 102h
0x180025b48  jz      short loc_180025B63
0x180025b4a  test    eax, 0FFFFFF7Fh
0x180025b4f  jz      short loc_180025B5E
0x180025b51  mov     rcx, [rbp+188h]; this
0x180025b58  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180025b5e  mov     rdi, rbx
0x180025b61  jmp     short loc_180025B65
0x180025b63  xor     edi, edi
0x180025b65  lea     rdx, [rsp+280h+var_248]; void **
0x180025b6a  mov     [rsp+280h+var_240], rdi
0x180025b6f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180025b74  mov     [rsp+280h+var_248], 0
0x180025b7d  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180025b82  mov     esi, eax
0x180025b84  test    eax, eax
0x180025b86  jns     short loc_180025BBC
0x180025b88  mov     rcx, [rbp+188h]; this
0x180025b8f  lea     r8, aWil; "wil"
0x180025b96  mov     r9d, eax; char *
0x180025b99  mov     edx, 12Eh; void *
0x180025b9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025ba3  lea     rcx, [rsp+280h+var_240]
0x180025ba8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025bad  mov     rcx, rbx; this
0x180025bb0  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180025bb5  mov     eax, esi
0x180025bb7  jmp     loc_180025C42
0x180025bbc  mov     rcx, [rsp+280h+var_248]
0x180025bc1  test    rcx, rcx
0x180025bc4  jz      short loc_180025BD1
0x180025bc6  mov     [r14], rcx
0x180025bc9  mov     eax, [rcx]
0x180025bcb  inc     eax
0x180025bcd  mov     [rcx], eax
0x180025bcf  jmp     short loc_180025C26
0x180025bd1  mov     r8, r14
0x180025bd4  lea     rdx, [rsp+280h+var_250]
0x180025bd9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180025bde  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180025be3  mov     ebx, eax
0x180025be5  test    eax, eax
0x180025be7  jns     short loc_180025C21
0x180025be9  mov     rcx, [rbp+188h]; this
0x180025bf0  lea     r8, aWil; "wil"
0x180025bf7  mov     r9d, eax; char *
0x180025bfa  mov     edx, 137h; void *
0x180025bff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025c04  lea     rcx, [rsp+280h+var_240]
0x180025c09  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025c0e  mov     rcx, [rsp+280h+var_250]; this
0x180025c13  test    rcx, rcx
0x180025c16  jz      short loc_180025C1D
0x180025c18  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180025c1d  mov     eax, ebx
0x180025c1f  jmp     short loc_180025C42
0x180025c21  mov     rbx, [rsp+280h+var_250]
0x180025c26  test    rdi, rdi
0x180025c29  jz      short loc_180025C33
0x180025c2b  mov     rcx, rdi; this
0x180025c2e  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180025c33  test    rbx, rbx
0x180025c36  jz      short loc_180025C40
0x180025c38  mov     rcx, rbx; this
0x180025c3b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180025c40  xor     eax, eax
0x180025c42  mov     rcx, [rbp+180h+var_20]
0x180025c49  xor     rcx, rsp; StackCookie
0x180025c4c  call    __security_check_cookie
0x180025c51  lea     r11, [rsp+280h+var_10]
0x180025c59  mov     rbx, [r11+30h]
0x180025c5d  mov     rsi, [r11+38h]
0x180025c61  mov     rsp, r11
0x180025c64  pop     r14
0x180025c66  pop     rdi
0x180025c67  pop     rbp
0x180025c68  retn
```
