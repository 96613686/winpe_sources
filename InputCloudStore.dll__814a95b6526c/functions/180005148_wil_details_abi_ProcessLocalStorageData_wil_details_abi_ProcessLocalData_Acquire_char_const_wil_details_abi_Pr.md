# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005148`
- end: `0x1800052ae`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005da0`

## callees

- `0x180003560`
- `0x180004fd8`
- `0x180004ff4`
- `0x180005148`
- `0x1800059f8`
- `0x1800064ec`
- `0x180006b14`
- `0x1800070e0`
- `0x18000723c`
- `0x1800076c0`
- `0x1800077bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800051c5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800051c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005180`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005180`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
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
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
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
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
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
0x180005148  mov     [rsp-8+arg_10], rbx
0x18000514d  mov     [rsp-8+arg_18], rdi
0x180005152  push    rbp
0x180005153  lea     rbp, [rsp-170h]
0x18000515b  sub     rsp, 270h
0x180005162  mov     rax, cs:__security_cookie
0x180005169  xor     rax, rsp
0x18000516c  mov     [rbp+170h+var_10], rax
0x180005173  mov     rdi, rdx
0x180005176  mov     qword ptr [rdx], 0
0x18000517d  mov     rbx, rcx
0x180005180  call    cs:__imp_GetCurrentProcessId
0x180005186  mov     [rsp+270h+var_248], rbx
0x18000518b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005192  mov     r9d, eax
0x180005195  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000519d  mov     edx, 104h; unsigned __int64
0x1800051a2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800051a7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800051ac  mov     r9d, 1F0001h; dwDesiredAccess
0x1800051b2  mov     [rsp+270h+var_240], 0
0x1800051bb  xor     r8d, r8d; dwFlags
0x1800051be  lea     rdx, [rsp+270h+Name]; lpName
0x1800051c3  xor     ecx, ecx; lpMutexAttributes
0x1800051c5  call    cs:__imp_CreateMutexExW
0x1800051cb  mov     rdx, rax
0x1800051ce  lea     rcx, [rsp+270h+var_240]
0x1800051d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800051d8  cmp     [rsp+270h+var_240], 0
0x1800051de  jnz     short loc_1800051E9
0x1800051e0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800051e5  mov     ebx, eax
0x1800051e7  jmp     short loc_18000525C
0x1800051e9  lea     rdx, [rsp+270h+var_238]
0x1800051ee  lea     rcx, [rsp+270h+var_240]
0x1800051f3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800051f8  lea     rdx, [rsp+270h+var_230]; void **
0x1800051fd  mov     [rsp+270h+var_230], 0
0x180005206  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000520b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180005210  mov     ebx, eax
0x180005212  test    eax, eax
0x180005214  jns     short loc_18000523D
0x180005216  mov     edx, 12Eh; void *
0x18000521b  mov     rcx, [rbp+178h]; this
0x180005222  lea     r8, aWil; "wil"
0x180005229  mov     r9d, eax; char *
0x18000522c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005231  lea     rcx, [rsp+270h+var_238]
0x180005236  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000523b  jmp     short loc_18000525C
0x18000523d  mov     rcx, [rsp+270h+var_230]
0x180005242  test    rcx, rcx
0x180005245  jz      short loc_18000528C
0x180005247  mov     [rdi], rcx
0x18000524a  mov     eax, [rcx]
0x18000524c  inc     eax
0x18000524e  mov     [rcx], eax
0x180005250  lea     rcx, [rsp+270h+var_238]
0x180005255  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000525a  xor     ebx, ebx
0x18000525c  lea     rcx, [rsp+270h+var_240]
0x180005261  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005266  mov     eax, ebx
0x180005268  mov     rcx, [rbp+170h+var_10]
0x18000526f  xor     rcx, rsp; StackCookie
0x180005272  call    __security_check_cookie
0x180005277  lea     r11, [rsp+270h+var_s0]
0x18000527f  mov     rbx, [r11+20h]
0x180005283  mov     rdi, [r11+28h]
0x180005287  mov     rsp, r11
0x18000528a  pop     rbp
0x18000528b  retn
0x18000528c  mov     r8, rdi
0x18000528f  lea     rdx, [rsp+270h+var_240]
0x180005294  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180005299  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000529e  mov     ebx, eax
0x1800052a0  test    eax, eax
0x1800052a2  jns     short loc_180005250
0x1800052a4  mov     edx, 137h
0x1800052a9  jmp     loc_18000521B
```
