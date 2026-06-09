# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18004416c`
- end: `0x180044366`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180044114`

## callees

- `0x180043e44`
- `0x180043fd8`
- `0x1800440c4`
- `0x18004416c`
- `0x18004436c`
- `0x1800443f8`
- `0x180044840`
- `0x1800c8458`
- `0x1800d1d50`
- `0x1800ede94`
- `0x1801201a0`
- `0x18012662c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800441a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800441a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180044203`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180044203`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800441e3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800441e3`

## string_xrefs

- `0x180044321`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
0x18004416c  mov     [rsp-8+arg_10], rbx
0x180044171  mov     [rsp-8+arg_18], rsi
0x180044176  push    rbp
0x180044177  push    rdi
0x180044178  push    r14
0x18004417a  lea     rbp, [rsp-170h]
0x180044182  sub     rsp, 270h
0x180044189  mov     rax, cs:__security_cookie
0x180044190  xor     rax, rsp
0x180044193  mov     [rbp+180h+var_20], rax
0x18004419a  mov     r14, rdx
0x18004419d  mov     qword ptr [rdx], 0
0x1800441a4  mov     rbx, rcx
0x1800441a7  call    cs:__imp_GetCurrentProcessId
0x1800441ad  mov     [rsp+280h+var_258], rbx
0x1800441b2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800441b9  mov     r9d, eax
0x1800441bc  mov     [rsp+280h+var_260], 130h; int
0x1800441c4  mov     edx, 104h; unsigned __int64
0x1800441c9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800441ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800441d3  mov     r9d, 1F0001h; dwDesiredAccess
0x1800441d9  lea     rdx, [rsp+280h+Name]; lpName
0x1800441de  xor     r8d, r8d; dwFlags
0x1800441e1  xor     ecx, ecx; lpMutexAttributes
0x1800441e3  call    cs:__imp_CreateMutexExW
0x1800441e9  mov     [rsp+280h+var_250], rax
0x1800441ee  mov     rbx, rax
0x1800441f1  test    rax, rax
0x1800441f4  jz      loc_1800442A7
0x1800441fa  xor     r8d, r8d; bAlertable
0x1800441fd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180044200  mov     rcx, rax; hHandle
0x180044203  call    cs:__imp_WaitForSingleObjectEx
0x180044209  cmp     eax, 102h
0x18004420e  jz      loc_180044333
0x180044214  test    eax, 0FFFFFF7Fh
0x180044219  jnz     loc_18004431A
0x18004421f  mov     rsi, rbx
0x180044222  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180044227  mov     [rsp+280h+var_240], rsi
0x18004422c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180044231  mov     [rsp+280h+var_248], 0
0x18004423a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18004423f  mov     edi, eax
0x180044241  test    eax, eax
0x180044243  js      short loc_1800442AE
0x180044245  mov     rax, [rsp+280h+var_248]
0x18004424a  lea     rcx, ds:0[rax*4]
0x180044252  test    rcx, rcx
0x180044255  jz      loc_18004433A
0x18004425b  mov     [r14], rcx
0x18004425e  mov     eax, [rcx]
0x180044260  inc     eax
0x180044262  mov     [rcx], eax
0x180044264  test    rsi, rsi
0x180044267  jz      short loc_180044271
0x180044269  mov     rcx, rsi; this
0x18004426c  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180044271  test    rbx, rbx
0x180044274  jz      short loc_18004427E
0x180044276  mov     rcx, rbx; this
0x180044279  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18004427e  xor     eax, eax
0x180044280  mov     rcx, [rbp+180h+var_20]
0x180044287  xor     rcx, rsp; StackCookie
0x18004428a  call    __security_check_cookie
0x18004428f  lea     r11, [rsp+280h+var_10]
0x180044297  mov     rbx, [r11+30h]
0x18004429b  mov     rsi, [r11+38h]
0x18004429f  mov     rsp, r11
0x1800442a2  pop     r14
0x1800442a4  pop     rdi
0x1800442a5  pop     rbp
0x1800442a6  retn
0x1800442a7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800442ac  jmp     short loc_180044280
0x1800442ae  mov     rcx, [rbp+188h]; this
0x1800442b5  lea     r8, aWil; "wil"
0x1800442bc  mov     r9d, edi; char *
0x1800442bf  mov     edx, 66h ; 'f'; void *
0x1800442c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442c9  mov     rcx, [rbp+188h]; this
0x1800442d0  lea     r8, aWil; "wil"
0x1800442d7  mov     r9d, edi; char *
0x1800442da  mov     edx, 6Fh ; 'o'; void *
0x1800442df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442e4  mov     r9d, edi; char *
0x1800442e7  mov     edx, 12Eh; void *
0x1800442ec  mov     rcx, [rbp+188h]; this
0x1800442f3  lea     r8, aWil; "wil"
0x1800442fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442ff  lea     rcx, [rsp+280h+var_240]
0x180044304  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044309  lea     rcx, [rsp+280h+var_250]
0x18004430e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044313  mov     eax, edi
0x180044315  jmp     loc_180044280
0x18004431a  mov     rcx, [rbp+188h]; this
0x180044321  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180044328  mov     edx, 0E01h; void *
0x18004432d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180044333  xor     esi, esi
0x180044335  jmp     loc_180044222
0x18004433a  mov     r8, r14
0x18004433d  lea     rdx, [rsp+280h+var_250]
0x180044342  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180044347  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004434c  mov     edi, eax
0x18004434e  test    eax, eax
0x180044350  jns     short loc_18004435C
0x180044352  mov     r9d, eax
0x180044355  mov     edx, 137h
0x18004435a  jmp     short loc_1800442EC
0x18004435c  mov     rbx, [rsp+280h+var_250]
0x180044361  jmp     loc_180044264
```
