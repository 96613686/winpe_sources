# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800430fc`
- end: `0x1800432a6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180043b64`

## callees

- `0x180013300`
- `0x180038c6c`
- `0x18003a580`
- `0x180042dac`
- `0x180042dc8`
- `0x1800430fc`
- `0x180043908`
- `0x1800440c8`
- `0x180044ce8`
- `0x180045784`
- `0x180045908`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043134`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043134`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180043179`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180043179`

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
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800430fc  mov     [rsp-8+arg_10], rbx
0x180043101  mov     [rsp-8+arg_18], rdi
0x180043106  push    rbp
0x180043107  lea     rbp, [rsp-170h]
0x18004310f  sub     rsp, 270h
0x180043116  mov     rax, cs:__security_cookie
0x18004311d  xor     rax, rsp
0x180043120  mov     [rbp+170h+var_10], rax
0x180043127  mov     rdi, rdx
0x18004312a  mov     qword ptr [rdx], 0
0x180043131  mov     rbx, rcx
0x180043134  call    cs:__imp_GetCurrentProcessId
0x18004313a  mov     [rsp+270h+var_248], rbx
0x18004313f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180043146  mov     r9d, eax
0x180043149  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180043151  mov     edx, 104h; unsigned __int64
0x180043156  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004315b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043160  mov     r9d, 1F0001h; dwDesiredAccess
0x180043166  mov     [rsp+270h+var_240], 0
0x18004316f  xor     r8d, r8d; dwFlags
0x180043172  lea     rdx, [rsp+270h+Name]; lpName
0x180043177  xor     ecx, ecx; lpMutexAttributes
0x180043179  call    cs:__imp_CreateMutexExW
0x18004317f  mov     rdx, rax
0x180043182  lea     rcx, [rsp+270h+var_240]
0x180043187  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004318c  cmp     [rsp+270h+var_240], 0
0x180043192  jnz     short loc_1800431A0
0x180043194  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180043199  mov     ebx, eax
0x18004319b  jmp     loc_180043251
0x1800431a0  lea     rdx, [rsp+270h+var_238]
0x1800431a5  lea     rcx, [rsp+270h+var_240]
0x1800431aa  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800431af  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800431b4  mov     [rsp+270h+var_230], 0
0x1800431bd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800431c2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800431c7  mov     ebx, eax
0x1800431c9  test    eax, eax
0x1800431cb  jns     short loc_18004322A
0x1800431cd  mov     rcx, [rbp+178h]; this
0x1800431d4  lea     r8, aWil; "wil"
0x1800431db  mov     r9d, eax; char *
0x1800431de  mov     edx, 66h ; 'f'; void *
0x1800431e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800431e8  mov     rcx, [rbp+178h]; this
0x1800431ef  lea     r8, aWil; "wil"
0x1800431f6  mov     r9d, ebx; char *
0x1800431f9  mov     edx, 6Fh ; 'o'; void *
0x1800431fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043203  mov     r9d, ebx; char *
0x180043206  mov     edx, 12Eh; void *
0x18004320b  mov     rcx, [rbp+178h]; this
0x180043212  lea     r8, aWil; "wil"
0x180043219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004321e  lea     rcx, [rsp+270h+var_238]
0x180043223  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180043228  jmp     short loc_180043251
0x18004322a  mov     rax, [rsp+270h+var_230]
0x18004322f  lea     rcx, ds:0[rax*4]
0x180043237  test    rcx, rcx
0x18004323a  jz      short loc_180043281
0x18004323c  mov     [rdi], rcx
0x18004323f  mov     eax, [rcx]
0x180043241  inc     eax
0x180043243  mov     [rcx], eax
0x180043245  lea     rcx, [rsp+270h+var_238]
0x18004324a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004324f  xor     ebx, ebx
0x180043251  lea     rcx, [rsp+270h+var_240]
0x180043256  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004325b  mov     eax, ebx
0x18004325d  mov     rcx, [rbp+170h+var_10]
0x180043264  xor     rcx, rsp; StackCookie
0x180043267  call    __security_check_cookie
0x18004326c  lea     r11, [rsp+270h+var_s0]
0x180043274  mov     rbx, [r11+20h]
0x180043278  mov     rdi, [r11+28h]
0x18004327c  mov     rsp, r11
0x18004327f  pop     rbp
0x180043280  retn
0x180043281  mov     r8, rdi
0x180043284  lea     rdx, [rsp+270h+var_240]
0x180043289  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004328e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180043293  mov     ebx, eax
0x180043295  test    eax, eax
0x180043297  jns     short loc_180043245
0x180043299  mov     r9d, eax
0x18004329c  mov     edx, 137h
0x1800432a1  jmp     loc_18004320B
```
