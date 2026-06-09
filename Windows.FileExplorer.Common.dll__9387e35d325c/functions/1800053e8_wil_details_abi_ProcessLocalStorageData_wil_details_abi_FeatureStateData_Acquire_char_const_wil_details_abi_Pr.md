# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800053e8`
- end: `0x1800055e2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004cb0`

## callees

- `0x1800032d0`
- `0x180004494`
- `0x180004d8c`
- `0x1800051e8`
- `0x180005214`
- `0x1800053e8`
- `0x180006bc8`
- `0x1800077c8`
- `0x18002de04`
- `0x180031f34`
- `0x180037780`
- `0x18003a3fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000547f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000547f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000545f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000545f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005423`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005423`

## string_xrefs

- `0x1800055a4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v7; // eax
  bool v8; // dl
  char *v9; // r9
  wil::details *v10; // rsi
  int ValueInternal; // eax
  void *v12; // rdx
  unsigned int v13; // edi
  _DWORD *v14; // rcx
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v19 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v7 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v10 = 0;
  }
  else
  {
    if ( (v7 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    v10 = v6;
  }
  v23 = v10;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v22, (bool *)v9);
  v13 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v13, v20);
    v16 = v13;
    v17 = 302;
    goto LABEL_15;
  }
  v14 = (_DWORD *)(4 * v22);
  if ( !(4 * v22) )
  {
    v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v13 = v18;
    if ( v18 >= 0 )
    {
      v6 = v21;
      goto LABEL_8;
    }
    v16 = (unsigned int)v18;
    v17 = 311;
LABEL_15:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)v16, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return v13;
  }
  *a2 = v14;
  ++*v14;
LABEL_8:
  if ( v10 )
    wil::details::ReleaseMutex(v10, v12);
  if ( v6 )
    wil::details::CloseHandle(v6, v12);
  return 0;
}

```

## disassembly

```asm
0x1800053e8  mov     [rsp-8+arg_10], rbx
0x1800053ed  mov     [rsp-8+arg_18], rsi
0x1800053f2  push    rbp
0x1800053f3  push    rdi
0x1800053f4  push    r14
0x1800053f6  lea     rbp, [rsp-170h]
0x1800053fe  sub     rsp, 270h
0x180005405  mov     rax, cs:__security_cookie
0x18000540c  xor     rax, rsp
0x18000540f  mov     [rbp+180h+var_20], rax
0x180005416  mov     r14, rdx
0x180005419  mov     qword ptr [rdx], 0
0x180005420  mov     rbx, rcx
0x180005423  call    cs:__imp_GetCurrentProcessId
0x180005429  mov     [rsp+280h+var_258], rbx
0x18000542e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005435  mov     r9d, eax
0x180005438  mov     [rsp+280h+var_260], 130h; int
0x180005440  mov     edx, 104h; unsigned __int64
0x180005445  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000544a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000544f  mov     r9d, 1F0001h; dwDesiredAccess
0x180005455  lea     rdx, [rsp+280h+Name]; lpName
0x18000545a  xor     r8d, r8d; dwFlags
0x18000545d  xor     ecx, ecx; lpMutexAttributes
0x18000545f  call    cs:__imp_CreateMutexExW
0x180005465  mov     [rsp+280h+var_250], rax
0x18000546a  mov     rbx, rax
0x18000546d  test    rax, rax
0x180005470  jz      loc_180005523
0x180005476  xor     r8d, r8d; bAlertable
0x180005479  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000547c  mov     rcx, rax; hHandle
0x18000547f  call    cs:__imp_WaitForSingleObjectEx
0x180005485  cmp     eax, 102h
0x18000548a  jz      loc_180005596
0x180005490  test    eax, 0FFFFFF7Fh
0x180005495  jnz     loc_18000559D
0x18000549b  mov     rsi, rbx
0x18000549e  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800054a3  mov     [rsp+280h+var_240], rsi
0x1800054a8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800054ad  mov     [rsp+280h+var_248], 0
0x1800054b6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800054bb  mov     edi, eax
0x1800054bd  test    eax, eax
0x1800054bf  js      short loc_18000552A
0x1800054c1  mov     rax, [rsp+280h+var_248]
0x1800054c6  lea     rcx, ds:0[rax*4]
0x1800054ce  test    rcx, rcx
0x1800054d1  jz      loc_1800055B6
0x1800054d7  mov     [r14], rcx
0x1800054da  mov     eax, [rcx]
0x1800054dc  inc     eax
0x1800054de  mov     [rcx], eax
0x1800054e0  test    rsi, rsi
0x1800054e3  jz      short loc_1800054ED
0x1800054e5  mov     rcx, rsi; this
0x1800054e8  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800054ed  test    rbx, rbx
0x1800054f0  jz      short loc_1800054FA
0x1800054f2  mov     rcx, rbx; this
0x1800054f5  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800054fa  xor     eax, eax
0x1800054fc  mov     rcx, [rbp+180h+var_20]
0x180005503  xor     rcx, rsp; StackCookie
0x180005506  call    __security_check_cookie
0x18000550b  lea     r11, [rsp+280h+var_10]
0x180005513  mov     rbx, [r11+30h]
0x180005517  mov     rsi, [r11+38h]
0x18000551b  mov     rsp, r11
0x18000551e  pop     r14
0x180005520  pop     rdi
0x180005521  pop     rbp
0x180005522  retn
0x180005523  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005528  jmp     short loc_1800054FC
0x18000552a  mov     rcx, [rbp+188h]; this
0x180005531  lea     r8, aWil; "wil"
0x180005538  mov     r9d, edi; char *
0x18000553b  mov     edx, 66h ; 'f'; void *
0x180005540  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005545  mov     rcx, [rbp+188h]; this
0x18000554c  lea     r8, aWil; "wil"
0x180005553  mov     r9d, edi; char *
0x180005556  mov     edx, 6Fh ; 'o'; void *
0x18000555b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005560  mov     r9d, edi; char *
0x180005563  mov     edx, 12Eh; void *
0x180005568  mov     rcx, [rbp+188h]; this
0x18000556f  lea     r8, aWil; "wil"
0x180005576  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000557b  lea     rcx, [rsp+280h+var_240]
0x180005580  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005585  lea     rcx, [rsp+280h+var_250]
0x18000558a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000558f  mov     eax, edi
0x180005591  jmp     loc_1800054FC
0x180005596  xor     esi, esi
0x180005598  jmp     loc_18000549E
0x18000559d  mov     rcx, [rbp+188h]; this
0x1800055a4  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800055ab  mov     edx, 0E01h; void *
0x1800055b0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800055b6  mov     r8, r14
0x1800055b9  lea     rdx, [rsp+280h+var_250]
0x1800055be  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800055c3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800055c8  mov     edi, eax
0x1800055ca  test    eax, eax
0x1800055cc  jns     short loc_1800055D8
0x1800055ce  mov     r9d, eax
0x1800055d1  mov     edx, 137h
0x1800055d6  jmp     short loc_180005568
0x1800055d8  mov     rbx, [rsp+280h+var_250]
0x1800055dd  jmp     loc_1800054E0
```
