# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000fe70`
- end: `0x18001007b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `523`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x180023aa0`

## callees

- `0x18000720c`
- `0x18000fe70`
- `0x180010084`
- `0x180019d6c`
- `0x18001a110`
- `0x18001a330`
- `0x18001ddc4`
- `0x180021fa4`
- `0x18002401c`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000fed5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000fed5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ff05`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ff05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fe99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fe99`

## string_xrefs

- `0x18000ff21`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  void *v15; // rdx
  _DWORD *v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  void *v19; // rdx
  int v20; // [rsp+20h] [rbp-258h]
  int v21; // [rsp+20h] [rbp-258h]
  wil::details *v22; // [rsp+30h] [rbp-248h]
  unsigned __int64 v23; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v23, (bool *)v10);
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v21);
    if ( v11 )
      wil::details::ReleaseMutex(v11, v15);
    wil::details::CloseHandle(v6, v15);
    return v14;
  }
  v16 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    *a2 = v16;
    ++*v16;
LABEL_21:
    if ( v11 )
      wil::details::ReleaseMutex(v11, v13);
    if ( v6 )
      wil::details::CloseHandle(v6, v13);
    return 0;
  }
  v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
  v18 = v17;
  if ( v17 >= 0 )
  {
    v6 = v22;
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v17, 304);
  if ( v11 )
    wil::details::ReleaseMutex(v11, v19);
  if ( v22 )
    wil::details::CloseHandle(v22, v19);
  return v18;
}

```

## disassembly

```asm
0x18000fe70  push    rbx
0x18000fe72  push    rsi
0x18000fe73  push    r14
0x18000fe75  sub     rsp, 260h
0x18000fe7c  mov     rax, cs:__security_cookie
0x18000fe83  xor     rax, rsp
0x18000fe86  mov     [rsp+278h+var_28], rax
0x18000fe8e  xor     esi, esi
0x18000fe90  mov     r14, rdx
0x18000fe93  mov     [rdx], rsi
0x18000fe96  mov     rbx, rcx
0x18000fe99  call    cs:__imp_GetCurrentProcessId
0x18000fe9f  mov     [rsp+278h+var_250], rbx
0x18000fea4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000feab  mov     r9d, eax
0x18000feae  mov     [rsp+278h+var_258], 130h; int
0x18000feb6  mov     edx, 104h; unsigned __int64
0x18000febb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000fec0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fec5  mov     r9d, 1F0001h; dwDesiredAccess
0x18000fecb  lea     rdx, [rsp+278h+Name]; lpName
0x18000fed0  xor     r8d, r8d; dwFlags
0x18000fed3  xor     ecx, ecx; lpMutexAttributes
0x18000fed5  call    cs:__imp_CreateMutexExW
0x18000fedb  mov     [rsp+278h+var_248], rax
0x18000fee0  mov     rbx, rax
0x18000fee3  test    rax, rax
0x18000fee6  jnz     short loc_18000FEF2
0x18000fee8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000feed  jmp     loc_18001005F
0x18000fef2  xor     r8d, r8d; bAlertable
0x18000fef5  mov     [rsp+278h+arg_10], rdi
0x18000fefd  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000ff02  mov     rcx, rbx; hHandle
0x18000ff05  call    cs:__imp_WaitForSingleObjectEx
0x18000ff0b  cmp     eax, 102h
0x18000ff10  jz      short loc_18000FF38
0x18000ff12  test    eax, 0FFFFFF7Fh
0x18000ff17  jz      short loc_18000FF33
0x18000ff19  mov     rcx, [rsp+278h]; this
0x18000ff21  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ff28  mov     edx, 0E01h; void *
0x18000ff2d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000ff33  mov     rdi, rbx
0x18000ff36  jmp     short loc_18000FF3B
0x18000ff38  mov     rdi, rsi
0x18000ff3b  lea     r8, [rsp+278h+var_240]; unsigned __int64 *
0x18000ff40  mov     [rsp+278h+var_240], rsi
0x18000ff45  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000ff4a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000ff4f  mov     esi, eax
0x18000ff51  test    eax, eax
0x18000ff53  jns     short loc_18000FFC5
0x18000ff55  mov     rcx, [rsp+278h]; this
0x18000ff5d  lea     r8, aWil; "wil"
0x18000ff64  mov     r9d, eax; char *
0x18000ff67  mov     edx, 66h ; 'f'; void *
0x18000ff6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff71  mov     rcx, [rsp+278h]; this
0x18000ff79  lea     r8, aWil; "wil"
0x18000ff80  mov     r9d, esi; char *
0x18000ff83  mov     edx, 6Fh ; 'o'; void *
0x18000ff88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff8d  mov     rcx, [rsp+278h]; this
0x18000ff95  lea     r8, aWil; "wil"
0x18000ff9c  mov     r9d, esi; char *
0x18000ff9f  mov     edx, 12Eh; void *
0x18000ffa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffa9  test    rdi, rdi
0x18000ffac  jz      short loc_18000FFB6
0x18000ffae  mov     rcx, rdi; this
0x18000ffb1  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000ffb6  mov     rcx, rbx; this
0x18000ffb9  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000ffbe  mov     eax, esi
0x18000ffc0  jmp     loc_180010057
0x18000ffc5  mov     rax, [rsp+278h+var_240]
0x18000ffca  lea     rax, ds:0[rax*4]
0x18000ffd2  test    rax, rax
0x18000ffd5  jz      short loc_18000FFE2
0x18000ffd7  mov     [r14], rax
0x18000ffda  mov     ecx, [rax]
0x18000ffdc  inc     ecx
0x18000ffde  mov     [rax], ecx
0x18000ffe0  jmp     short loc_18001003B
0x18000ffe2  mov     r8, r14
0x18000ffe5  lea     rdx, [rsp+278h+var_248]
0x18000ffea  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000ffef  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000fff4  mov     ebx, eax
0x18000fff6  test    eax, eax
0x18000fff8  jns     short loc_180010036
0x18000fffa  mov     rcx, [rsp+278h]; this
0x180010002  lea     r8, aWil; "wil"
0x180010009  mov     r9d, eax; char *
0x18001000c  mov     edx, 137h; void *
0x180010011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010016  test    rdi, rdi
0x180010019  jz      short loc_180010023
0x18001001b  mov     rcx, rdi; this
0x18001001e  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180010023  mov     rcx, [rsp+278h+var_248]; this
0x180010028  test    rcx, rcx
0x18001002b  jz      short loc_180010032
0x18001002d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180010032  mov     eax, ebx
0x180010034  jmp     short loc_180010057
0x180010036  mov     rbx, [rsp+278h+var_248]
0x18001003b  test    rdi, rdi
0x18001003e  jz      short loc_180010048
0x180010040  mov     rcx, rdi; this
0x180010043  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180010048  test    rbx, rbx
0x18001004b  jz      short loc_180010055
0x18001004d  mov     rcx, rbx; this
0x180010050  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180010055  xor     eax, eax
0x180010057  mov     rdi, [rsp+278h+arg_10]
0x18001005f  mov     rcx, [rsp+278h+var_28]
0x180010067  xor     rcx, rsp; StackCookie
0x18001006a  call    __security_check_cookie
0x18001006f  add     rsp, 260h
0x180010076  pop     r14
0x180010078  pop     rsi
0x180010079  pop     rbx
0x18001007a  retn
```
