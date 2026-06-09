# wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)

- ea: `0x18000ad24`
- end: `0x18000ae9c`
- name: `?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000accc`

## callees

- `0x18000ad24`
- `0x18000aeb0`
- `0x180010b08`
- `0x180010e84`
- `0x1800112a4`
- `0x18001af70`
- `0x18001d814`
- `0x18001eae4`
- `0x1800204a8`
- `0x180020af4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ada1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ada1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ad65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ad65`

## pseudocode

```c
__int64 wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared()
{
  __int64 v0; // rsi
  void *v1; // rdi
  DWORD CurrentProcessId; // eax
  wil::details *v3; // rcx
  int Pointer; // eax
  __int64 v5; // rdx
  void *v6; // rdx
  void *v7; // rdx
  wil::details *Mutex; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v11; // [rsp+40h] [rbp-C0h] BYREF
  void *v12; // [rsp+48h] [rbp-B8h]
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v0 = wil::details_abi::g_pProcessLocalData;
  if ( *(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
  v1 = 0;
  v12 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  if ( !Mutex )
  {
    if ( (int)wil::details::GetLastErrorFailHr(v3) < 0 )
      return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
    goto LABEL_14;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &Mutex,
    v10);
  v11 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v11);
  if ( Pointer < 0 )
  {
    v5 = 302;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      120);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v10);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &Mutex,
      v6);
    return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
  }
  v1 = v11;
  if ( v11 )
  {
    ++*(_DWORD *)v11;
  }
  else
  {
    Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    if ( Pointer < 0 )
    {
      v5 = 311;
      goto LABEL_7;
    }
    v1 = v12;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v10);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &Mutex,
    v7);
LABEL_14:
  if ( !*(_QWORD *)(v0 + 8) )
    *(_QWORD *)(v0 + 8) = v1;
  return (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
}

```

## disassembly

```asm
0x18000ad24  push    rbp
0x18000ad26  push    rbx
0x18000ad27  push    rsi
0x18000ad28  push    rdi
0x18000ad29  lea     rbp, [rsp-178h]
0x18000ad31  sub     rsp, 278h
0x18000ad38  mov     rax, cs:__security_cookie
0x18000ad3f  xor     rax, rsp
0x18000ad42  mov     [rbp+190h+var_30], rax
0x18000ad49  mov     rsi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000ad50  cmp     qword ptr [rsi+8], 0
0x18000ad55  jnz     loc_18000AE70
0x18000ad5b  mov     rbx, [rsi]
0x18000ad5e  xor     edi, edi
0x18000ad60  mov     [rsp+290h+var_248], rdi
0x18000ad65  call    cs:__imp_GetCurrentProcessId
0x18000ad6b  mov     [rsp+290h+var_268], rbx
0x18000ad70  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000ad77  mov     r9d, eax
0x18000ad7a  mov     [rsp+290h+var_270], 78h ; 'x'; int
0x18000ad82  mov     edx, 104h; unsigned __int64
0x18000ad87  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000ad8c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ad91  mov     r9d, 1F0001h; dwDesiredAccess
0x18000ad97  lea     rdx, [rsp+290h+Name]; lpName
0x18000ad9c  xor     r8d, r8d; dwFlags
0x18000ad9f  xor     ecx, ecx; lpMutexAttributes
0x18000ada1  call    cs:__imp_CreateMutexExW
0x18000ada7  mov     [rsp+290h+var_260], rax
0x18000adac  test    rax, rax
0x18000adaf  jnz     short loc_18000ADC3
0x18000adb1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000adb6  test    eax, eax
0x18000adb8  jns     loc_18000AE65
0x18000adbe  jmp     loc_18000AE70
0x18000adc3  lea     rdx, [rsp+290h+var_258]
0x18000adc8  lea     rcx, [rsp+290h+var_260]
0x18000adcd  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000add2  lea     rdx, [rsp+290h+var_250]; void **
0x18000add7  mov     [rsp+290h+var_250], rdi
0x18000addc  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000ade1  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000ade6  test    eax, eax
0x18000ade8  jns     short loc_18000AE1B
0x18000adea  mov     edx, 12Eh; void *
0x18000adef  mov     rcx, [rbp+198h]; this
0x18000adf6  lea     r8, aWil; "wil"
0x18000adfd  mov     r9d, eax; char *
0x18000ae00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae05  lea     rcx, [rsp+290h+var_258]
0x18000ae0a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ae0f  lea     rcx, [rsp+290h+var_260]
0x18000ae14  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ae19  jmp     short loc_18000AE70
0x18000ae1b  mov     rdi, [rsp+290h+var_250]
0x18000ae20  test    rdi, rdi
0x18000ae23  jz      short loc_18000AE2D
0x18000ae25  mov     eax, [rdi]
0x18000ae27  inc     eax
0x18000ae29  mov     [rdi], eax
0x18000ae2b  jmp     short loc_18000AE51
0x18000ae2d  lea     r8, [rsp+290h+var_248]
0x18000ae32  lea     rdx, [rsp+290h+var_260]
0x18000ae37  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000ae3c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000ae41  test    eax, eax
0x18000ae43  jns     short loc_18000AE4C
0x18000ae45  mov     edx, 137h
0x18000ae4a  jmp     short loc_18000ADEF
0x18000ae4c  mov     rdi, [rsp+290h+var_248]
0x18000ae51  lea     rcx, [rsp+290h+var_258]
0x18000ae56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ae5b  lea     rcx, [rsp+290h+var_260]
0x18000ae60  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ae65  cmp     qword ptr [rsi+8], 0
0x18000ae6a  jnz     short loc_18000AE70
0x18000ae6c  mov     [rsi+8], rdi
0x18000ae70  mov     rax, [rsi+8]
0x18000ae74  lea     rcx, [rax+20h]
0x18000ae78  neg     rax
0x18000ae7b  sbb     rax, rax
0x18000ae7e  and     rax, rcx
0x18000ae81  mov     rcx, [rbp+190h+var_30]
0x18000ae88  xor     rcx, rsp; StackCookie
0x18000ae8b  call    __security_check_cookie
0x18000ae90  add     rsp, 278h
0x18000ae97  pop     rdi
0x18000ae98  pop     rsi
0x18000ae99  pop     rbx
0x18000ae9a  pop     rbp
0x18000ae9b  retn
```
