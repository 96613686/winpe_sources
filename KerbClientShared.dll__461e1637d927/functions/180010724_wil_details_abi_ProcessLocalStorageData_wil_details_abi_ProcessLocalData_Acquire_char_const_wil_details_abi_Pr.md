# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180010724`
- end: `0x180010883`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001176c`

## callees

- `0x18000eb70`
- `0x18001053c`
- `0x180010558`
- `0x180010724`
- `0x180011498`
- `0x1800122b8`
- `0x1800130f8`
- `0x180013624`
- `0x180013a74`
- `0x180014254`
- `0x18001439c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001075c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001075c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800107a1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800107a1`

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
0x180010724  mov     [rsp-8+arg_10], rbx
0x180010729  mov     [rsp-8+arg_18], rdi
0x18001072e  push    rbp
0x18001072f  lea     rbp, [rsp-170h]
0x180010737  sub     rsp, 270h
0x18001073e  mov     rax, cs:__security_cookie
0x180010745  xor     rax, rsp
0x180010748  mov     [rbp+170h+var_10], rax
0x18001074f  mov     rdi, rdx
0x180010752  mov     qword ptr [rdx], 0
0x180010759  mov     rbx, rcx
0x18001075c  call    cs:__imp_GetCurrentProcessId
0x180010762  mov     [rsp+270h+var_248], rbx
0x180010767  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001076e  mov     r9d, eax
0x180010771  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180010779  mov     edx, 104h; unsigned __int64
0x18001077e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010783  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010788  mov     r9d, 1F0001h; dwDesiredAccess
0x18001078e  mov     [rsp+270h+var_240], 0
0x180010797  xor     r8d, r8d; dwFlags
0x18001079a  lea     rdx, [rsp+270h+Name]; lpName
0x18001079f  xor     ecx, ecx; lpMutexAttributes
0x1800107a1  call    cs:__imp_CreateMutexExW
0x1800107a7  mov     rdx, rax
0x1800107aa  lea     rcx, [rsp+270h+var_240]
0x1800107af  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800107b4  cmp     [rsp+270h+var_240], 0
0x1800107ba  jnz     short loc_1800107C5
0x1800107bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800107c1  mov     ebx, eax
0x1800107c3  jmp     short loc_180010831
0x1800107c5  lea     rdx, [rsp+270h+var_238]
0x1800107ca  lea     rcx, [rsp+270h+var_240]
0x1800107cf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800107d4  lea     rdx, [rsp+270h+var_230]; void **
0x1800107d9  mov     [rsp+270h+var_230], 0
0x1800107e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800107e7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800107ec  mov     ebx, eax
0x1800107ee  test    eax, eax
0x1800107f0  jns     short loc_180010812
0x1800107f2  mov     edx, 12Eh; void *
0x1800107f7  mov     rcx, [rbp+178h]; this
0x1800107fe  mov     r9d, eax; char *
0x180010801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010806  lea     rcx, [rsp+270h+var_238]
0x18001080b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010810  jmp     short loc_180010831
0x180010812  mov     rcx, [rsp+270h+var_230]
0x180010817  test    rcx, rcx
0x18001081a  jz      short loc_180010861
0x18001081c  mov     [rdi], rcx
0x18001081f  mov     eax, [rcx]
0x180010821  inc     eax
0x180010823  mov     [rcx], eax
0x180010825  lea     rcx, [rsp+270h+var_238]
0x18001082a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001082f  xor     ebx, ebx
0x180010831  lea     rcx, [rsp+270h+var_240]
0x180010836  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001083b  mov     eax, ebx
0x18001083d  mov     rcx, [rbp+170h+var_10]
0x180010844  xor     rcx, rsp; StackCookie
0x180010847  call    __security_check_cookie
0x18001084c  lea     r11, [rsp+270h+var_s0]
0x180010854  mov     rbx, [r11+20h]
0x180010858  mov     rdi, [r11+28h]
0x18001085c  mov     rsp, r11
0x18001085f  pop     rbp
0x180010860  retn
0x180010861  mov     r8, rdi
0x180010864  lea     rdx, [rsp+270h+var_240]
0x180010869  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001086e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180010873  mov     ebx, eax
0x180010875  test    eax, eax
0x180010877  jns     short loc_180010825
0x180010879  mov     edx, 137h
0x18001087e  jmp     loc_1800107F7
```
