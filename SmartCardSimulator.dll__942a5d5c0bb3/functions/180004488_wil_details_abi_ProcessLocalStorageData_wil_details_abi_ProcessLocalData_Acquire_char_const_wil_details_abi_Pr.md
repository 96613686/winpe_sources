# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004488`
- end: `0x18000461d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004fa8`

## callees

- `0x18000438c`
- `0x1800043a8`
- `0x180004488`
- `0x180004d08`
- `0x1800056e4`
- `0x180005d74`
- `0x1800062c8`
- `0x180006440`
- `0x1800067dc`
- `0x1800068e0`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004505`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004505`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800044c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800044c0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180004488  mov     [rsp-8+arg_10], rbx
0x18000448d  mov     [rsp-8+arg_18], rdi
0x180004492  push    rbp
0x180004493  lea     rbp, [rsp-170h]
0x18000449b  sub     rsp, 270h
0x1800044a2  mov     rax, cs:__security_cookie
0x1800044a9  xor     rax, rsp
0x1800044ac  mov     [rbp+170h+var_10], rax
0x1800044b3  mov     rdi, rdx
0x1800044b6  mov     qword ptr [rdx], 0
0x1800044bd  mov     rbx, rcx
0x1800044c0  call    cs:__imp_GetCurrentProcessId
0x1800044c6  mov     [rsp+270h+var_248], rbx
0x1800044cb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800044d2  mov     r9d, eax
0x1800044d5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800044dd  mov     edx, 104h; unsigned __int64
0x1800044e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800044e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800044ec  mov     r9d, 1F0001h; dwDesiredAccess
0x1800044f2  mov     [rsp+270h+var_240], 0
0x1800044fb  xor     r8d, r8d; dwFlags
0x1800044fe  lea     rdx, [rsp+270h+Name]; lpName
0x180004503  xor     ecx, ecx; lpMutexAttributes
0x180004505  call    cs:__imp_CreateMutexExW
0x18000450b  mov     rdx, rax
0x18000450e  lea     rcx, [rsp+270h+var_240]
0x180004513  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004518  cmp     [rsp+270h+var_240], 0
0x18000451e  jnz     short loc_18000452C
0x180004520  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004525  mov     ebx, eax
0x180004527  jmp     loc_1800045C8
0x18000452c  lea     rdx, [rsp+270h+var_238]
0x180004531  lea     rcx, [rsp+270h+var_240]
0x180004536  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000453b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180004540  mov     [rsp+270h+var_230], 0
0x180004549  lea     rcx, [rsp+270h+Name]; pszSrc
0x18000454e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004553  mov     ebx, eax
0x180004555  test    eax, eax
0x180004557  jns     short loc_1800045A1
0x180004559  mov     rcx, [rbp+178h]; this
0x180004560  mov     r9d, eax; char *
0x180004563  mov     edx, 66h ; 'f'; void *
0x180004568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000456d  mov     rcx, [rbp+178h]; this
0x180004574  mov     r9d, ebx; char *
0x180004577  mov     edx, 6Fh ; 'o'; void *
0x18000457c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004581  mov     r9d, ebx; char *
0x180004584  mov     edx, 12Eh; void *
0x180004589  mov     rcx, [rbp+178h]; this
0x180004590  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004595  lea     rcx, [rsp+270h+var_238]
0x18000459a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000459f  jmp     short loc_1800045C8
0x1800045a1  mov     rax, [rsp+270h+var_230]
0x1800045a6  lea     rcx, ds:0[rax*4]
0x1800045ae  test    rcx, rcx
0x1800045b1  jz      short loc_1800045F8
0x1800045b3  mov     [rdi], rcx
0x1800045b6  mov     eax, [rcx]
0x1800045b8  inc     eax
0x1800045ba  mov     [rcx], eax
0x1800045bc  lea     rcx, [rsp+270h+var_238]
0x1800045c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800045c6  xor     ebx, ebx
0x1800045c8  lea     rcx, [rsp+270h+var_240]
0x1800045cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800045d2  mov     eax, ebx
0x1800045d4  mov     rcx, [rbp+170h+var_10]
0x1800045db  xor     rcx, rsp; StackCookie
0x1800045de  call    __security_check_cookie
0x1800045e3  lea     r11, [rsp+270h+var_s0]
0x1800045eb  mov     rbx, [r11+20h]
0x1800045ef  mov     rdi, [r11+28h]
0x1800045f3  mov     rsp, r11
0x1800045f6  pop     rbp
0x1800045f7  retn
0x1800045f8  mov     r8, rdi
0x1800045fb  lea     rdx, [rsp+270h+var_240]
0x180004600  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004605  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000460a  mov     ebx, eax
0x18000460c  test    eax, eax
0x18000460e  jns     short loc_1800045BC
0x180004610  mov     r9d, eax
0x180004613  mov     edx, 137h
0x180004618  jmp     loc_180004589
```
