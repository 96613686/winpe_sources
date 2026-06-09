# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140045588`
- end: `0x1400456e7`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140047ce4`

## callees

- `0x14001f940`
- `0x1400451c8`
- `0x1400451e4`
- `0x140045588`
- `0x140046ddc`
- `0x1400488c8`
- `0x140049afc`
- `0x14004a610`
- `0x14004af14`
- `0x14004b2d0`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1400455c0`
- `KERNEL32!GetCurrentProcessId` at `0x1400455c0`
- `KERNEL32!CreateMutexExW` at `0x140045605`
- `KERNEL32!CreateMutexExW` at `0x140045605`

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
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x140045588  mov     [rsp-8+arg_10], rbx
0x14004558d  mov     [rsp-8+arg_18], rdi
0x140045592  push    rbp
0x140045593  lea     rbp, [rsp-170h]
0x14004559b  sub     rsp, 270h
0x1400455a2  mov     rax, cs:__security_cookie
0x1400455a9  xor     rax, rsp
0x1400455ac  mov     [rbp+170h+var_10], rax
0x1400455b3  mov     rdi, rdx
0x1400455b6  mov     qword ptr [rdx], 0
0x1400455bd  mov     rbx, rcx
0x1400455c0  call    cs:__imp_GetCurrentProcessId
0x1400455c6  mov     [rsp+270h+var_248], rbx
0x1400455cb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400455d2  mov     r9d, eax
0x1400455d5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1400455dd  mov     edx, 104h; unsigned __int64
0x1400455e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400455e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400455ec  mov     r9d, 1F0001h; dwDesiredAccess
0x1400455f2  mov     [rsp+270h+var_240], 0
0x1400455fb  xor     r8d, r8d; dwFlags
0x1400455fe  lea     rdx, [rsp+270h+Name]; lpName
0x140045603  xor     ecx, ecx; lpMutexAttributes
0x140045605  call    cs:__imp_CreateMutexExW
0x14004560b  mov     rdx, rax
0x14004560e  lea     rcx, [rsp+270h+var_240]
0x140045613  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140045618  cmp     [rsp+270h+var_240], 0
0x14004561e  jnz     short loc_140045629
0x140045620  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140045625  mov     ebx, eax
0x140045627  jmp     short loc_140045695
0x140045629  lea     rdx, [rsp+270h+var_238]
0x14004562e  lea     rcx, [rsp+270h+var_240]
0x140045633  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140045638  lea     rdx, [rsp+270h+var_230]; void **
0x14004563d  mov     [rsp+270h+var_230], 0
0x140045646  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14004564b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140045650  mov     ebx, eax
0x140045652  test    eax, eax
0x140045654  jns     short loc_140045676
0x140045656  mov     edx, 12Eh; void *
0x14004565b  mov     rcx, [rbp+178h]; this
0x140045662  mov     r9d, eax; char *
0x140045665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004566a  lea     rcx, [rsp+270h+var_238]
0x14004566f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140045674  jmp     short loc_140045695
0x140045676  mov     rcx, [rsp+270h+var_230]
0x14004567b  test    rcx, rcx
0x14004567e  jz      short loc_1400456C5
0x140045680  mov     [rdi], rcx
0x140045683  mov     eax, [rcx]
0x140045685  inc     eax
0x140045687  mov     [rcx], eax
0x140045689  lea     rcx, [rsp+270h+var_238]
0x14004568e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140045693  xor     ebx, ebx
0x140045695  lea     rcx, [rsp+270h+var_240]
0x14004569a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14004569f  mov     eax, ebx
0x1400456a1  mov     rcx, [rbp+170h+var_10]
0x1400456a8  xor     rcx, rsp; StackCookie
0x1400456ab  call    __security_check_cookie
0x1400456b0  lea     r11, [rsp+270h+var_s0]
0x1400456b8  mov     rbx, [r11+20h]
0x1400456bc  mov     rdi, [r11+28h]
0x1400456c0  mov     rsp, r11
0x1400456c3  pop     rbp
0x1400456c4  retn
0x1400456c5  mov     r8, rdi
0x1400456c8  lea     rdx, [rsp+270h+var_240]
0x1400456cd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400456d2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400456d7  mov     ebx, eax
0x1400456d9  test    eax, eax
0x1400456db  jns     short loc_140045689
0x1400456dd  mov     edx, 137h
0x1400456e2  jmp     loc_14004565B
```
