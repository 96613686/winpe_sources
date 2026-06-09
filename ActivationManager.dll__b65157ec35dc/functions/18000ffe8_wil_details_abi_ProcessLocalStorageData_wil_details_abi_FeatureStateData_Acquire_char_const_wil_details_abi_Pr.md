# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000ffe8`
- end: `0x1800101cc`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000ff90`

## callees

- `0x18000b5c0`
- `0x18000dffc`
- `0x18000ffe8`
- `0x180010514`
- `0x18001059c`
- `0x1800109d4`
- `0x180043f5c`
- `0x18004498c`
- `0x180050e8c`
- `0x18005ae90`
- `0x18006091c`
- `0x180060d9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010085`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010085`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001005f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001005f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010023`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010023`

## string_xrefs

- `0x1800100a0`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rsi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // edi
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  _DWORD *v17; // rcx
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
  v23 = v11;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v22, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v20);
    v15 = v14;
    v16 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v16, (unsigned int)"wil", (const char *)v15, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return v14;
  }
  v17 = (_DWORD *)(4 * v22);
  if ( 4 * v22 )
  {
    *a2 = v17;
    ++*v17;
  }
  else
  {
    v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v14 = v18;
    if ( v18 < 0 )
    {
      v15 = (unsigned int)v18;
      v16 = 311;
      goto LABEL_14;
    }
    v6 = v21;
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
0x18000ffe8  mov     [rsp-8+arg_10], rbx
0x18000ffed  mov     [rsp-8+arg_18], rsi
0x18000fff2  push    rbp
0x18000fff3  push    rdi
0x18000fff4  push    r14
0x18000fff6  lea     rbp, [rsp-170h]
0x18000fffe  sub     rsp, 270h
0x180010005  mov     rax, cs:__security_cookie
0x18001000c  xor     rax, rsp
0x18001000f  mov     [rbp+180h+var_20], rax
0x180010016  mov     r14, rdx
0x180010019  mov     qword ptr [rdx], 0
0x180010020  mov     rbx, rcx
0x180010023  call    cs:__imp_GetCurrentProcessId
0x180010029  mov     [rsp+280h+var_258], rbx
0x18001002e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010035  mov     r9d, eax
0x180010038  mov     [rsp+280h+var_260], 130h; int
0x180010040  mov     edx, 104h; unsigned __int64
0x180010045  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001004a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001004f  mov     r9d, 1F0001h; dwDesiredAccess
0x180010055  lea     rdx, [rsp+280h+Name]; lpName
0x18001005a  xor     r8d, r8d; dwFlags
0x18001005d  xor     ecx, ecx; lpMutexAttributes
0x18001005f  call    cs:__imp_CreateMutexExW
0x180010065  mov     [rsp+280h+var_250], rax
0x18001006a  mov     rbx, rax
0x18001006d  test    rax, rax
0x180010070  jnz     short loc_18001007C
0x180010072  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010077  jmp     loc_1800101A5
0x18001007c  xor     r8d, r8d; bAlertable
0x18001007f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010082  mov     rcx, rbx; hHandle
0x180010085  call    cs:__imp_WaitForSingleObjectEx
0x18001008b  cmp     eax, 102h
0x180010090  jz      short loc_1800100B7
0x180010092  test    eax, 0FFFFFF7Fh
0x180010097  jz      short loc_1800100B2
0x180010099  mov     rcx, [rbp+188h]; this
0x1800100a0  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800100a7  mov     edx, 0E01h; void *
0x1800100ac  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800100b2  mov     rsi, rbx
0x1800100b5  jmp     short loc_1800100B9
0x1800100b7  xor     esi, esi
0x1800100b9  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800100be  mov     [rsp+280h+var_240], rsi
0x1800100c3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800100c8  mov     [rsp+280h+var_248], 0
0x1800100d1  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800100d6  mov     edi, eax
0x1800100d8  test    eax, eax
0x1800100da  jns     short loc_18001011C
0x1800100dc  mov     rcx, [rbp+188h]; this
0x1800100e3  lea     r8, aWil; "wil"
0x1800100ea  mov     r9d, eax; char *
0x1800100ed  mov     edx, 66h ; 'f'; void *
0x1800100f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100f7  mov     rcx, [rbp+188h]; this
0x1800100fe  lea     r8, aWil; "wil"
0x180010105  mov     r9d, edi; char *
0x180010108  mov     edx, 6Fh ; 'o'; void *
0x18001010d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010112  mov     r9d, edi
0x180010115  mov     edx, 12Eh
0x18001011a  jmp     short loc_180010159
0x18001011c  mov     rax, [rsp+280h+var_248]
0x180010121  lea     rcx, ds:0[rax*4]
0x180010129  test    rcx, rcx
0x18001012c  jz      short loc_180010139
0x18001012e  mov     [r14], rcx
0x180010131  mov     eax, [rcx]
0x180010133  inc     eax
0x180010135  mov     [rcx], eax
0x180010137  jmp     short loc_180010189
0x180010139  mov     r8, r14
0x18001013c  lea     rdx, [rsp+280h+var_250]
0x180010141  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010146  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001014b  mov     edi, eax
0x18001014d  test    eax, eax
0x18001014f  jns     short loc_180010184
0x180010151  mov     r9d, eax; char *
0x180010154  mov     edx, 137h; void *
0x180010159  mov     rcx, [rbp+188h]; this
0x180010160  lea     r8, aWil; "wil"
0x180010167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001016c  lea     rcx, [rsp+280h+var_240]
0x180010171  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010176  lea     rcx, [rsp+280h+var_250]
0x18001017b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010180  mov     eax, edi
0x180010182  jmp     short loc_1800101A5
0x180010184  mov     rbx, [rsp+280h+var_250]
0x180010189  test    rsi, rsi
0x18001018c  jz      short loc_180010196
0x18001018e  mov     rcx, rsi; this
0x180010191  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180010196  test    rbx, rbx
0x180010199  jz      short loc_1800101A3
0x18001019b  mov     rcx, rbx; this
0x18001019e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800101a3  xor     eax, eax
0x1800101a5  mov     rcx, [rbp+180h+var_20]
0x1800101ac  xor     rcx, rsp; StackCookie
0x1800101af  call    __security_check_cookie
0x1800101b4  lea     r11, [rsp+280h+var_10]
0x1800101bc  mov     rbx, [r11+30h]
0x1800101c0  mov     rsi, [r11+38h]
0x1800101c4  mov     rsp, r11
0x1800101c7  pop     r14
0x1800101c9  pop     rdi
0x1800101ca  pop     rbp
0x1800101cb  retn
```
