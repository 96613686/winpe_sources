# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18008bcc8`
- end: `0x18008be37`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18008c344`

## callees

- `0x180015050`
- `0x18002fafc`
- `0x18002fb18`
- `0x180030660`
- `0x18003140c`
- `0x180031684`
- `0x1800319d0`
- `0x180031a90`
- `0x18008bcc8`
- `0x18008c658`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18008bd45`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18008bd45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008bd00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008bd00`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    v12 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      &v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18008bcc8  mov     [rsp-8+arg_10], rbx
0x18008bccd  mov     [rsp-8+arg_18], rdi
0x18008bcd2  push    rbp
0x18008bcd3  lea     rbp, [rsp-170h]
0x18008bcdb  sub     rsp, 270h
0x18008bce2  mov     rax, cs:__security_cookie
0x18008bce9  xor     rax, rsp
0x18008bcec  mov     [rbp+170h+var_10], rax
0x18008bcf3  mov     rdi, rdx
0x18008bcf6  mov     qword ptr [rdx], 0
0x18008bcfd  mov     rbx, rcx
0x18008bd00  call    cs:__imp_GetCurrentProcessId
0x18008bd06  mov     [rsp+270h+var_248], rbx
0x18008bd0b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18008bd12  mov     r9d, eax
0x18008bd15  mov     [rsp+270h+var_250], 130h; int
0x18008bd1d  mov     edx, 104h; unsigned __int64
0x18008bd22  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18008bd27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008bd2c  mov     r9d, 1F0001h; dwDesiredAccess
0x18008bd32  mov     [rsp+270h+var_240], 0
0x18008bd3b  xor     r8d, r8d; dwFlags
0x18008bd3e  lea     rdx, [rsp+270h+Name]; lpName
0x18008bd43  xor     ecx, ecx; lpMutexAttributes
0x18008bd45  call    cs:__imp_CreateMutexExW
0x18008bd4b  mov     rdx, rax
0x18008bd4e  lea     rcx, [rsp+270h+var_240]
0x18008bd53  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18008bd58  cmp     [rsp+270h+var_240], 0
0x18008bd5e  jnz     short loc_18008BD69
0x18008bd60  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18008bd65  mov     ebx, eax
0x18008bd67  jmp     short loc_18008BDE5
0x18008bd69  lea     rdx, [rsp+270h+var_238]
0x18008bd6e  mov     [rsp+270h+var_238], 0
0x18008bd77  lea     rcx, [rsp+270h+var_240]
0x18008bd7c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18008bd81  lea     rdx, [rsp+270h+var_230]; void **
0x18008bd86  mov     [rsp+270h+var_230], 0
0x18008bd8f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18008bd94  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18008bd99  mov     ebx, eax
0x18008bd9b  test    eax, eax
0x18008bd9d  jns     short loc_18008BDC6
0x18008bd9f  mov     edx, 12Eh; void *
0x18008bda4  mov     rcx, [rbp+178h]; this
0x18008bdab  lea     r8, aWil; "wil"
0x18008bdb2  mov     r9d, eax; char *
0x18008bdb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bdba  lea     rcx, [rsp+270h+var_238]
0x18008bdbf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008bdc4  jmp     short loc_18008BDE5
0x18008bdc6  mov     rcx, [rsp+270h+var_230]
0x18008bdcb  test    rcx, rcx
0x18008bdce  jz      short loc_18008BE15
0x18008bdd0  mov     [rdi], rcx
0x18008bdd3  mov     eax, [rcx]
0x18008bdd5  inc     eax
0x18008bdd7  mov     [rcx], eax
0x18008bdd9  lea     rcx, [rsp+270h+var_238]
0x18008bdde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008bde3  xor     ebx, ebx
0x18008bde5  lea     rcx, [rsp+270h+var_240]
0x18008bdea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008bdef  mov     eax, ebx
0x18008bdf1  mov     rcx, [rbp+170h+var_10]
0x18008bdf8  xor     rcx, rsp; StackCookie
0x18008bdfb  call    __security_check_cookie
0x18008be00  lea     r11, [rsp+270h+var_s0]
0x18008be08  mov     rbx, [r11+20h]
0x18008be0c  mov     rdi, [r11+28h]
0x18008be10  mov     rsp, r11
0x18008be13  pop     rbp
0x18008be14  retn
0x18008be15  mov     r8, rdi
0x18008be18  lea     rdx, [rsp+270h+var_240]
0x18008be1d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18008be22  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18008be27  mov     ebx, eax
0x18008be29  test    eax, eax
0x18008be2b  jns     short loc_18008BDD9
0x18008be2d  mov     edx, 137h
0x18008be32  jmp     loc_18008BDA4
```
