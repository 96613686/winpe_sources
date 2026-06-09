# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001ab80`
- end: `0x18001ad98`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `536`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003683c`

## callees

- `0x18001ab80`
- `0x18001b7f0`
- `0x18002b1c8`
- `0x18002b398`
- `0x18002ba04`
- `0x18002ba24`
- `0x18002d970`
- `0x180030fac`
- `0x180034070`
- `0x180036178`
- `0x180036cd4`
- `0x18003737c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001ac2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001ac2b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001abfd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001abfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001abbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001abbb`

## string_xrefs

- `0x18001ac4c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  wil::details *v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v20 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    return LastErrorFailHr;
  }
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v10);
    v11 = v6;
  }
  v22[0] = v11;
  v21 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v21, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v18);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    LastErrorFailHr = v14;
    goto LABEL_14;
  }
  v15 = (_DWORD *)(4 * v21);
  if ( 4 * v21 )
  {
    *a2 = v15;
    ++*v15;
  }
  else
  {
    v16 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v16,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
      goto LABEL_14;
    }
    v6 = v20;
  }
  if ( v11 )
    wil::details::ReleaseMutex(v11, v13);
  if ( v6 )
    wil::details::CloseHandle(v6, v13);
  return 0;
}

```

## disassembly

```asm
0x18001ab80  mov     [rsp-8+arg_10], rbx
0x18001ab85  mov     [rsp-8+arg_18], rsi
0x18001ab8a  push    rbp
0x18001ab8b  push    rdi
0x18001ab8c  push    r14
0x18001ab8e  lea     rbp, [rsp-170h]
0x18001ab96  sub     rsp, 270h
0x18001ab9d  mov     rax, cs:__security_cookie
0x18001aba4  xor     rax, rsp
0x18001aba7  mov     [rbp+180h+var_20], rax
0x18001abae  mov     r14, rdx
0x18001abb1  mov     qword ptr [rdx], 0
0x18001abb8  mov     rbx, rcx
0x18001abbb  call    cs:__imp_GetCurrentProcessId
0x18001abc2  nop     dword ptr [rax+rax+00h]
0x18001abc7  mov     [rsp+280h+var_258], rbx
0x18001abcc  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001abd3  mov     r9d, eax
0x18001abd6  mov     [rsp+280h+var_260], 130h; int
0x18001abde  mov     edx, 104h; unsigned __int64
0x18001abe3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001abe8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001abed  mov     r9d, 1F0001h; dwDesiredAccess
0x18001abf3  lea     rdx, [rsp+280h+Name]; lpName
0x18001abf8  xor     r8d, r8d; dwFlags
0x18001abfb  xor     ecx, ecx; lpMutexAttributes
0x18001abfd  call    cs:__imp_CreateMutexExW
0x18001ac04  nop     dword ptr [rax+rax+00h]
0x18001ac09  mov     [rsp+280h+var_250], rax
0x18001ac0e  mov     rbx, rax
0x18001ac11  test    rax, rax
0x18001ac14  jnz     short loc_18001AC22
0x18001ac16  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001ac1b  mov     ebx, eax
0x18001ac1d  jmp     loc_18001AD41
0x18001ac22  xor     r8d, r8d; bAlertable
0x18001ac25  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001ac28  mov     rcx, rbx; hHandle
0x18001ac2b  call    cs:__imp_WaitForSingleObjectEx
0x18001ac32  nop     dword ptr [rax+rax+00h]
0x18001ac37  cmp     eax, 102h
0x18001ac3c  jz      short loc_18001AC63
0x18001ac3e  test    eax, 0FFFFFF7Fh
0x18001ac43  jz      short loc_18001AC5E
0x18001ac45  mov     rcx, [rbp+188h]; this
0x18001ac4c  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001ac53  mov     edx, 0E01h; void *
0x18001ac58  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001ac5e  mov     rdi, rbx
0x18001ac61  jmp     short loc_18001AC65
0x18001ac63  xor     edi, edi
0x18001ac65  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18001ac6a  mov     [rsp+280h+var_240], rdi
0x18001ac6f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001ac74  mov     [rsp+280h+var_248], 0
0x18001ac7d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001ac82  mov     esi, eax
0x18001ac84  test    eax, eax
0x18001ac86  jns     short loc_18001ACE7
0x18001ac88  mov     rcx, [rbp+188h]; this
0x18001ac8f  lea     r8, aWil; "wil"
0x18001ac96  mov     r9d, eax; char *
0x18001ac99  mov     edx, 66h ; 'f'; void *
0x18001ac9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aca3  mov     rcx, [rbp+188h]; this
0x18001acaa  lea     r8, aWil; "wil"
0x18001acb1  mov     r9d, esi; char *
0x18001acb4  mov     edx, 6Fh ; 'o'; void *
0x18001acb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001acbe  mov     rcx, [rbp+188h]; this
0x18001acc5  lea     r8, aWil; "wil"
0x18001accc  mov     r9d, esi; char *
0x18001accf  mov     edx, 12Eh; void *
0x18001acd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001acd9  lea     rcx, [rsp+280h+var_240]
0x18001acde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ace3  mov     ebx, esi
0x18001ace5  jmp     short loc_18001AD41
0x18001ace7  mov     rax, [rsp+280h+var_248]
0x18001acec  lea     rcx, ds:0[rax*4]
0x18001acf4  test    rcx, rcx
0x18001acf7  jz      short loc_18001AD04
0x18001acf9  mov     [r14], rcx
0x18001acfc  mov     eax, [rcx]
0x18001acfe  inc     eax
0x18001ad00  mov     [rcx], eax
0x18001ad02  jmp     short loc_18001AD54
0x18001ad04  mov     r8, r14
0x18001ad07  lea     rdx, [rsp+280h+var_250]
0x18001ad0c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001ad11  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001ad16  mov     ebx, eax
0x18001ad18  test    eax, eax
0x18001ad1a  jns     short loc_18001AD4F
0x18001ad1c  mov     rcx, [rbp+188h]; this
0x18001ad23  lea     r8, aWil; "wil"
0x18001ad2a  mov     r9d, eax; char *
0x18001ad2d  mov     edx, 137h; void *
0x18001ad32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad37  lea     rcx, [rsp+280h+var_240]
0x18001ad3c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ad41  lea     rcx, [rsp+280h+var_250]
0x18001ad46  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ad4b  mov     eax, ebx
0x18001ad4d  jmp     short loc_18001AD70
0x18001ad4f  mov     rbx, [rsp+280h+var_250]
0x18001ad54  test    rdi, rdi
0x18001ad57  jz      short loc_18001AD61
0x18001ad59  mov     rcx, rdi; this
0x18001ad5c  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18001ad61  test    rbx, rbx
0x18001ad64  jz      short loc_18001AD6E
0x18001ad66  mov     rcx, rbx; this
0x18001ad69  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001ad6e  xor     eax, eax
0x18001ad70  mov     rcx, [rbp+180h+var_20]
0x18001ad77  xor     rcx, rsp; StackCookie
0x18001ad7a  call    __security_check_cookie
0x18001ad7f  lea     r11, [rsp+280h+var_10]
0x18001ad87  mov     rbx, [r11+30h]
0x18001ad8b  mov     rsi, [r11+38h]
0x18001ad8f  mov     rsp, r11
0x18001ad92  pop     r14
0x18001ad94  pop     rdi
0x18001ad95  pop     rbp
0x18001ad96  retn
```
