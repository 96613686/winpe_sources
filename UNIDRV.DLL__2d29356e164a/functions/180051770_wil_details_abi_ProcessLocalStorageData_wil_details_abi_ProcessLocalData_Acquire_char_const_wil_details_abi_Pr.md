# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180051770`
- end: `0x1800518cf`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180052f44`

## callees

- `0x1800480c4`
- `0x1800487e0`
- `0x18005120c`
- `0x180051228`
- `0x180051770`
- `0x180053a0c`
- `0x180055430`
- `0x180055bfc`
- `0x180056424`
- `0x18005686c`
- `0x180056ba0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1800517ed`
- `KERNEL32!CreateMutexExW` at `0x1800517ed`
- `KERNEL32!GetCurrentProcessId` at `0x1800517a8`
- `KERNEL32!GetCurrentProcessId` at `0x1800517a8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(pszDest);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180051770  mov     [rsp-8+arg_10], rbx
0x180051775  mov     [rsp-8+arg_18], rdi
0x18005177a  push    rbp
0x18005177b  lea     rbp, [rsp-170h]
0x180051783  sub     rsp, 270h
0x18005178a  mov     rax, cs:__security_cookie
0x180051791  xor     rax, rsp
0x180051794  mov     [rbp+170h+var_10], rax
0x18005179b  mov     rdi, rdx
0x18005179e  mov     qword ptr [rdx], 0
0x1800517a5  mov     rbx, rcx
0x1800517a8  call    cs:__imp_GetCurrentProcessId
0x1800517ae  mov     [rsp+270h+var_248], rbx
0x1800517b3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800517ba  mov     r9d, eax
0x1800517bd  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800517c5  mov     edx, 104h; cchDest
0x1800517ca  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800517cf  call    StringCchPrintfW
0x1800517d4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800517da  mov     [rsp+270h+var_240], 0
0x1800517e3  xor     r8d, r8d; dwFlags
0x1800517e6  lea     rdx, [rsp+270h+pszDest]; lpName
0x1800517eb  xor     ecx, ecx; lpMutexAttributes
0x1800517ed  call    cs:__imp_CreateMutexExW
0x1800517f3  mov     rdx, rax
0x1800517f6  lea     rcx, [rsp+270h+var_240]
0x1800517fb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180051800  cmp     [rsp+270h+var_240], 0
0x180051806  jnz     short loc_180051811
0x180051808  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005180d  mov     ebx, eax
0x18005180f  jmp     short loc_18005187D
0x180051811  lea     rdx, [rsp+270h+var_238]
0x180051816  lea     rcx, [rsp+270h+var_240]
0x18005181b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180051820  lea     rdx, [rsp+270h+var_230]; void **
0x180051825  mov     [rsp+270h+var_230], 0
0x18005182e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180051833  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180051838  mov     ebx, eax
0x18005183a  test    eax, eax
0x18005183c  jns     short loc_18005185E
0x18005183e  mov     edx, 12Eh; void *
0x180051843  mov     rcx, [rbp+178h]; this
0x18005184a  mov     r9d, eax; char *
0x18005184d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051852  lea     rcx, [rsp+270h+var_238]
0x180051857  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005185c  jmp     short loc_18005187D
0x18005185e  mov     rcx, [rsp+270h+var_230]
0x180051863  test    rcx, rcx
0x180051866  jz      short loc_1800518AD
0x180051868  mov     [rdi], rcx
0x18005186b  mov     eax, [rcx]
0x18005186d  inc     eax
0x18005186f  mov     [rcx], eax
0x180051871  lea     rcx, [rsp+270h+var_238]
0x180051876  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005187b  xor     ebx, ebx
0x18005187d  lea     rcx, [rsp+270h+var_240]
0x180051882  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180051887  mov     eax, ebx
0x180051889  mov     rcx, [rbp+170h+var_10]
0x180051890  xor     rcx, rsp; StackCookie
0x180051893  call    __security_check_cookie
0x180051898  lea     r11, [rsp+270h+var_s0]
0x1800518a0  mov     rbx, [r11+20h]
0x1800518a4  mov     rdi, [r11+28h]
0x1800518a8  mov     rsp, r11
0x1800518ab  pop     rbp
0x1800518ac  retn
0x1800518ad  mov     r8, rdi
0x1800518b0  lea     rdx, [rsp+270h+var_240]
0x1800518b5  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800518ba  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800518bf  mov     ebx, eax
0x1800518c1  test    eax, eax
0x1800518c3  jns     short loc_180051871
0x1800518c5  mov     edx, 137h
0x1800518ca  jmp     loc_180051843
```
