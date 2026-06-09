# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000daa0`
- end: `0x14000dc47`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140012298`

## callees

- `0x14000daa0`
- `0x14000dc50`
- `0x14000dc6c`
- `0x14000dfe0`
- `0x14000e034`
- `0x14000e058`
- `0x14000e160`
- `0x14000e1c0`
- `0x14000ec5c`
- `0x14000f6a0`
- `0x140012984`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000dad5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000dad5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000db1a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000db1a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  int Pointer; // eax
  unsigned int v9; // edi
  void *v10; // rdx
  _DWORD *v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  void *v14; // rdx
  void *v15; // rdx
  wil::details *v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v18; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v16 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v16,
    Mutex);
  v6 = v16;
  if ( !v16 )
    return wil::details::GetLastErrorFailHr(v5);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v16,
    v17);
  v18 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v18);
  v9 = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      120);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    wil::details::CloseHandle(v6, v10);
    return v9;
  }
  v11 = v18;
  if ( v18 )
  {
    *a2 = v18;
    ++*v11;
LABEL_12:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    if ( v6 )
      wil::details::CloseHandle(v6, v15);
    return 0;
  }
  v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v6 = v16;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v12, 120);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
  if ( v16 )
    wil::details::CloseHandle(v16, v14);
  return v13;
}

```

## disassembly

```asm
0x14000daa0  mov     [rsp-8+arg_10], rbx
0x14000daa5  push    rbp
0x14000daa6  push    rsi
0x14000daa7  push    rdi
0x14000daa8  lea     rbp, [rsp-170h]
0x14000dab0  sub     rsp, 270h
0x14000dab7  mov     rax, cs:__security_cookie
0x14000dabe  xor     rax, rsp
0x14000dac1  mov     [rbp+180h+var_20], rax
0x14000dac8  mov     rsi, rdx
0x14000dacb  mov     qword ptr [rdx], 0
0x14000dad2  mov     rbx, rcx
0x14000dad5  call    cs:__imp_GetCurrentProcessId
0x14000dadb  mov     [rsp+280h+var_258], rbx
0x14000dae0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000dae7  mov     r9d, eax
0x14000daea  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x14000daf2  mov     edx, 104h; unsigned __int64
0x14000daf7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000dafc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000db01  mov     r9d, 1F0001h; dwDesiredAccess
0x14000db07  mov     [rsp+280h+var_250], 0
0x14000db10  xor     r8d, r8d; dwFlags
0x14000db13  lea     rdx, [rsp+280h+Name]; lpName
0x14000db18  xor     ecx, ecx; lpMutexAttributes
0x14000db1a  call    cs:__imp_CreateMutexExW
0x14000db20  mov     rdx, rax
0x14000db23  lea     rcx, [rsp+280h+var_250]
0x14000db28  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000db2d  mov     rbx, [rsp+280h+var_250]
0x14000db32  test    rbx, rbx
0x14000db35  jnz     short loc_14000DB41
0x14000db37  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000db3c  jmp     loc_14000DC25
0x14000db41  lea     rdx, [rsp+280h+var_248]
0x14000db46  lea     rcx, [rsp+280h+var_250]
0x14000db4b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000db50  lea     rdx, [rsp+280h+var_240]; void **
0x14000db55  mov     [rsp+280h+var_240], 0
0x14000db5e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000db63  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x14000db68  mov     edi, eax
0x14000db6a  test    eax, eax
0x14000db6c  jns     short loc_14000DBA2
0x14000db6e  mov     rcx, [rbp+188h]; this
0x14000db75  lea     r8, aWil; "wil"
0x14000db7c  mov     r9d, eax; char *
0x14000db7f  mov     edx, 12Eh; void *
0x14000db84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000db89  lea     rcx, [rsp+280h+var_248]
0x14000db8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000db93  mov     rcx, rbx; this
0x14000db96  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000db9b  mov     eax, edi
0x14000db9d  jmp     loc_14000DC25
0x14000dba2  mov     rcx, [rsp+280h+var_240]
0x14000dba7  test    rcx, rcx
0x14000dbaa  jz      short loc_14000DBB7
0x14000dbac  mov     [rsi], rcx
0x14000dbaf  mov     eax, [rcx]
0x14000dbb1  inc     eax
0x14000dbb3  mov     [rcx], eax
0x14000dbb5  jmp     short loc_14000DC0C
0x14000dbb7  mov     r8, rsi
0x14000dbba  lea     rdx, [rsp+280h+var_250]
0x14000dbbf  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000dbc4  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000dbc9  mov     ebx, eax
0x14000dbcb  test    eax, eax
0x14000dbcd  jns     short loc_14000DC07
0x14000dbcf  mov     rcx, [rbp+188h]; this
0x14000dbd6  lea     r8, aWil; "wil"
0x14000dbdd  mov     r9d, eax; char *
0x14000dbe0  mov     edx, 137h; void *
0x14000dbe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000dbea  lea     rcx, [rsp+280h+var_248]
0x14000dbef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000dbf4  mov     rcx, [rsp+280h+var_250]; this
0x14000dbf9  test    rcx, rcx
0x14000dbfc  jz      short loc_14000DC03
0x14000dbfe  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000dc03  mov     eax, ebx
0x14000dc05  jmp     short loc_14000DC25
0x14000dc07  mov     rbx, [rsp+280h+var_250]
0x14000dc0c  lea     rcx, [rsp+280h+var_248]
0x14000dc11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000dc16  test    rbx, rbx
0x14000dc19  jz      short loc_14000DC23
0x14000dc1b  mov     rcx, rbx; this
0x14000dc1e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000dc23  xor     eax, eax
0x14000dc25  mov     rcx, [rbp+180h+var_20]
0x14000dc2c  xor     rcx, rsp; StackCookie
0x14000dc2f  call    __security_check_cookie
0x14000dc34  mov     rbx, [rsp+280h+arg_10]
0x14000dc3c  add     rsp, 270h
0x14000dc43  pop     rdi
0x14000dc44  pop     rsi
0x14000dc45  pop     rbp
0x14000dc46  retn
```
