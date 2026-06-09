# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000ffa0`
- end: `0x1800101a7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000fec4`

## callees

- `0x18000ffa0`
- `0x180010250`
- `0x1800102e0`
- `0x1800105c4`
- `0x18001cb10`
- `0x18001d328`
- `0x18001d344`
- `0x180024b88`
- `0x18002537c`
- `0x18002cd20`
- `0x18002fda8`
- `0x18003eac4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010017`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010017`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001003f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001003f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ffdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ffdb`

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
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  void *v16; // rdx
  _DWORD *v18; // rcx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_16:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    return LastErrorFailHr;
  }
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v24 = v12;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v18 = (_DWORD *)(4 * v23);
    if ( 4 * v23 )
    {
      *a2 = v18;
      ++*v18;
    }
    else
    {
      v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v19,
          304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
        goto LABEL_16;
      }
      v6 = v22;
    }
    if ( v12 )
      wil::details::ReleaseMutex(v12, v14);
    if ( v6 )
      wil::details::CloseHandle(v6, v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v20);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v21);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v16);
    wil::details::CloseHandle(v6, v16);
    return v15;
  }
}

```

## disassembly

```asm
0x18000ffa0  mov     [rsp-8+arg_10], rbx
0x18000ffa5  mov     [rsp-8+arg_18], rsi
0x18000ffaa  push    rbp
0x18000ffab  push    rdi
0x18000ffac  push    r14
0x18000ffae  lea     rbp, [rsp-170h]
0x18000ffb6  sub     rsp, 270h
0x18000ffbd  mov     rax, cs:__security_cookie
0x18000ffc4  xor     rax, rsp
0x18000ffc7  mov     [rbp+180h+var_20], rax
0x18000ffce  mov     r14, rdx
0x18000ffd1  mov     qword ptr [rdx], 0
0x18000ffd8  mov     rbx, rcx
0x18000ffdb  call    cs:__imp_GetCurrentProcessId
0x18000ffe1  mov     [rsp+280h+var_258], rbx
0x18000ffe6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000ffed  mov     r9d, eax
0x18000fff0  mov     [rsp+280h+var_260], 130h; int
0x18000fff8  mov     edx, 104h; unsigned __int64
0x18000fffd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010002  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010007  mov     r9d, 1F0001h; dwDesiredAccess
0x18001000d  lea     rdx, [rsp+280h+Name]; lpName
0x180010012  xor     r8d, r8d; dwFlags
0x180010015  xor     ecx, ecx; lpMutexAttributes
0x180010017  call    cs:__imp_CreateMutexExW
0x18001001d  mov     [rsp+280h+var_250], rax
0x180010022  mov     rbx, rax
0x180010025  test    rax, rax
0x180010028  jnz     short loc_180010036
0x18001002a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001002f  mov     ebx, eax
0x180010031  jmp     loc_180010151
0x180010036  xor     r8d, r8d; bAlertable
0x180010039  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001003c  mov     rcx, rbx; hHandle
0x18001003f  call    cs:__imp_WaitForSingleObjectEx
0x180010045  cmp     eax, 102h
0x18001004a  jz      short loc_180010065
0x18001004c  test    eax, 0FFFFFF7Fh
0x180010051  jz      short loc_180010060
0x180010053  mov     rcx, [rbp+188h]; this
0x18001005a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180010060  mov     rdi, rbx
0x180010063  jmp     short loc_180010067
0x180010065  xor     edi, edi
0x180010067  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18001006c  mov     [rsp+280h+var_240], rdi
0x180010071  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010076  mov     [rsp+280h+var_248], 0
0x18001007f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180010084  mov     esi, eax
0x180010086  test    eax, eax
0x180010088  jns     short loc_1800100F7
0x18001008a  mov     rcx, [rbp+188h]; this
0x180010091  lea     r8, aWil; "wil"
0x180010098  mov     r9d, eax; char *
0x18001009b  mov     edx, 66h ; 'f'; void *
0x1800100a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100a5  mov     rcx, [rbp+188h]; this
0x1800100ac  lea     r8, aWil; "wil"
0x1800100b3  mov     r9d, esi; char *
0x1800100b6  mov     edx, 6Fh ; 'o'; void *
0x1800100bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100c0  mov     rcx, [rbp+188h]; this
0x1800100c7  lea     r8, aWil; "wil"
0x1800100ce  mov     r9d, esi; char *
0x1800100d1  mov     edx, 12Eh; void *
0x1800100d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100db  test    rdi, rdi
0x1800100de  jz      short loc_1800100E8
0x1800100e0  mov     rcx, rdi; this
0x1800100e3  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800100e8  mov     rcx, rbx; this
0x1800100eb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800100f0  mov     eax, esi
0x1800100f2  jmp     loc_180010180
0x1800100f7  mov     rax, [rsp+280h+var_248]
0x1800100fc  lea     rcx, ds:0[rax*4]
0x180010104  test    rcx, rcx
0x180010107  jz      short loc_180010114
0x180010109  mov     [r14], rcx
0x18001010c  mov     eax, [rcx]
0x18001010e  inc     eax
0x180010110  mov     [rcx], eax
0x180010112  jmp     short loc_180010164
0x180010114  mov     r8, r14
0x180010117  lea     rdx, [rsp+280h+var_250]
0x18001011c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010121  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180010126  mov     ebx, eax
0x180010128  test    eax, eax
0x18001012a  jns     short loc_18001015F
0x18001012c  mov     rcx, [rbp+188h]; this
0x180010133  lea     r8, aWil; "wil"
0x18001013a  mov     r9d, eax; char *
0x18001013d  mov     edx, 137h; void *
0x180010142  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010147  lea     rcx, [rsp+280h+var_240]
0x18001014c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010151  lea     rcx, [rsp+280h+var_250]
0x180010156  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001015b  mov     eax, ebx
0x18001015d  jmp     short loc_180010180
0x18001015f  mov     rbx, [rsp+280h+var_250]
0x180010164  test    rdi, rdi
0x180010167  jz      short loc_180010171
0x180010169  mov     rcx, rdi; this
0x18001016c  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180010171  test    rbx, rbx
0x180010174  jz      short loc_18001017E
0x180010176  mov     rcx, rbx; this
0x180010179  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001017e  xor     eax, eax
0x180010180  mov     rcx, [rbp+180h+var_20]
0x180010187  xor     rcx, rsp; StackCookie
0x18001018a  call    __security_check_cookie
0x18001018f  lea     r11, [rsp+280h+var_10]
0x180010197  mov     rbx, [r11+30h]
0x18001019b  mov     rsi, [r11+38h]
0x18001019f  mov     rsp, r11
0x1800101a2  pop     r14
0x1800101a4  pop     rdi
0x1800101a5  pop     rbp
0x1800101a6  retn
```
