# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005064`
- end: `0x1800051f9`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005b88`

## callees

- `0x180003410`
- `0x180004f10`
- `0x180004f2c`
- `0x180005064`
- `0x1800058e8`
- `0x1800062c4`
- `0x180006954`
- `0x180006eec`
- `0x180007058`
- `0x1800073ec`
- `0x1800074f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800050e1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800050e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000509c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000509c`

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
0x180005064  mov     [rsp-8+arg_10], rbx
0x180005069  mov     [rsp-8+arg_18], rdi
0x18000506e  push    rbp
0x18000506f  lea     rbp, [rsp-170h]
0x180005077  sub     rsp, 270h
0x18000507e  mov     rax, cs:__security_cookie
0x180005085  xor     rax, rsp
0x180005088  mov     [rbp+170h+var_10], rax
0x18000508f  mov     rdi, rdx
0x180005092  mov     qword ptr [rdx], 0
0x180005099  mov     rbx, rcx
0x18000509c  call    cs:__imp_GetCurrentProcessId
0x1800050a2  mov     [rsp+270h+var_248], rbx
0x1800050a7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800050ae  mov     r9d, eax
0x1800050b1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800050b9  mov     edx, 104h; unsigned __int64
0x1800050be  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800050c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800050c8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800050ce  mov     [rsp+270h+var_240], 0
0x1800050d7  xor     r8d, r8d; dwFlags
0x1800050da  lea     rdx, [rsp+270h+Name]; lpName
0x1800050df  xor     ecx, ecx; lpMutexAttributes
0x1800050e1  call    cs:__imp_CreateMutexExW
0x1800050e7  mov     rdx, rax
0x1800050ea  lea     rcx, [rsp+270h+var_240]
0x1800050ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800050f4  cmp     [rsp+270h+var_240], 0
0x1800050fa  jnz     short loc_180005108
0x1800050fc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005101  mov     ebx, eax
0x180005103  jmp     loc_1800051A4
0x180005108  lea     rdx, [rsp+270h+var_238]
0x18000510d  lea     rcx, [rsp+270h+var_240]
0x180005112  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005117  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18000511c  mov     [rsp+270h+var_230], 0
0x180005125  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000512a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000512f  mov     ebx, eax
0x180005131  test    eax, eax
0x180005133  jns     short loc_18000517D
0x180005135  mov     rcx, [rbp+178h]; this
0x18000513c  mov     r9d, eax; char *
0x18000513f  mov     edx, 66h ; 'f'; void *
0x180005144  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005149  mov     rcx, [rbp+178h]; this
0x180005150  mov     r9d, ebx; char *
0x180005153  mov     edx, 6Fh ; 'o'; void *
0x180005158  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000515d  mov     r9d, ebx; char *
0x180005160  mov     edx, 12Eh; void *
0x180005165  mov     rcx, [rbp+178h]; this
0x18000516c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005171  lea     rcx, [rsp+270h+var_238]
0x180005176  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000517b  jmp     short loc_1800051A4
0x18000517d  mov     rax, [rsp+270h+var_230]
0x180005182  lea     rcx, ds:0[rax*4]
0x18000518a  test    rcx, rcx
0x18000518d  jz      short loc_1800051D4
0x18000518f  mov     [rdi], rcx
0x180005192  mov     eax, [rcx]
0x180005194  inc     eax
0x180005196  mov     [rcx], eax
0x180005198  lea     rcx, [rsp+270h+var_238]
0x18000519d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800051a2  xor     ebx, ebx
0x1800051a4  lea     rcx, [rsp+270h+var_240]
0x1800051a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800051ae  mov     eax, ebx
0x1800051b0  mov     rcx, [rbp+170h+var_10]
0x1800051b7  xor     rcx, rsp; StackCookie
0x1800051ba  call    __security_check_cookie
0x1800051bf  lea     r11, [rsp+270h+var_s0]
0x1800051c7  mov     rbx, [r11+20h]
0x1800051cb  mov     rdi, [r11+28h]
0x1800051cf  mov     rsp, r11
0x1800051d2  pop     rbp
0x1800051d3  retn
0x1800051d4  mov     r8, rdi
0x1800051d7  lea     rdx, [rsp+270h+var_240]
0x1800051dc  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800051e1  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800051e6  mov     ebx, eax
0x1800051e8  test    eax, eax
0x1800051ea  jns     short loc_180005198
0x1800051ec  mov     r9d, eax
0x1800051ef  mov     edx, 137h
0x1800051f4  jmp     loc_180005165
```
