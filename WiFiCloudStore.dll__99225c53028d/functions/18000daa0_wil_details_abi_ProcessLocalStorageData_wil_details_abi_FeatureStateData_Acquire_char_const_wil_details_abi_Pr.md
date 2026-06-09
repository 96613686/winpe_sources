# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000daa0`
- end: `0x18000dcd3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x18000da48`

## callees

- `0x180006390`
- `0x18000daa0`
- `0x18000dcdc`
- `0x18000e124`
- `0x18000e150`
- `0x180023f80`
- `0x18002477c`
- `0x1800264cc`
- `0x18002a030`
- `0x18002c138`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000db17`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000db17`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000db37`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000db37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dadb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dadb`

## string_xrefs

- `0x18000dc83`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  wil::details *v10; // rdi
  int ValueInternal; // eax
  void *v12; // rdx
  unsigned int v13; // esi
  _DWORD *v14; // rcx
  void *v16; // rdx
  void *v17; // rdx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
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
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v23, (bool *)v9);
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v13, v21);
    if ( v10 )
      wil::details::ReleaseMutex(v10, v16);
    wil::details::CloseHandle(v6, v16);
    return v13;
  }
  else
  {
    v14 = (_DWORD *)(4 * v23);
    if ( 4 * v23 )
    {
      *a2 = v14;
      ++*v14;
LABEL_7:
      if ( v10 )
        wil::details::ReleaseMutex(v10, v12);
      if ( v6 )
        wil::details::CloseHandle(v6, v12);
      return 0;
    }
    v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v19 = v18;
    if ( v18 >= 0 )
    {
      v6 = v22;
      goto LABEL_7;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v18, 304);
    if ( v10 )
      wil::details::ReleaseMutex(v10, v17);
    if ( v22 )
      wil::details::CloseHandle(v22, v17);
    return v19;
  }
}

```

## disassembly

```asm
0x18000daa0  mov     [rsp-8+arg_10], rbx
0x18000daa5  mov     [rsp-8+arg_18], rsi
0x18000daaa  push    rbp
0x18000daab  push    rdi
0x18000daac  push    r14
0x18000daae  lea     rbp, [rsp-160h]
0x18000dab6  sub     rsp, 260h
0x18000dabd  mov     rax, cs:__security_cookie
0x18000dac4  xor     rax, rsp
0x18000dac7  mov     [rbp+170h+var_20], rax
0x18000dace  mov     r14, rdx
0x18000dad1  mov     qword ptr [rdx], 0
0x18000dad8  mov     rbx, rcx
0x18000dadb  call    cs:__imp_GetCurrentProcessId
0x18000dae1  mov     [rsp+270h+var_248], rbx
0x18000dae6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000daed  mov     r9d, eax
0x18000daf0  mov     [rsp+270h+var_250], 130h; int
0x18000daf8  mov     edx, 104h; unsigned __int64
0x18000dafd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000db02  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000db07  mov     r9d, 1F0001h; dwDesiredAccess
0x18000db0d  lea     rdx, [rsp+270h+Name]; lpName
0x18000db12  xor     r8d, r8d; dwFlags
0x18000db15  xor     ecx, ecx; lpMutexAttributes
0x18000db17  call    cs:__imp_CreateMutexExW
0x18000db1d  mov     [rsp+270h+var_240], rax
0x18000db22  mov     rbx, rax
0x18000db25  test    rax, rax
0x18000db28  jz      loc_18000DBBE
0x18000db2e  xor     r8d, r8d; bAlertable
0x18000db31  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000db34  mov     rcx, rax; hHandle
0x18000db37  call    cs:__imp_WaitForSingleObjectEx
0x18000db3d  cmp     eax, 102h
0x18000db42  jnz     loc_18000DC75
0x18000db48  xor     edi, edi
0x18000db4a  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18000db4f  mov     [rsp+270h+var_238], 0
0x18000db58  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000db5d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000db62  mov     esi, eax
0x18000db64  test    eax, eax
0x18000db66  js      short loc_18000DBCF
0x18000db68  mov     rax, [rsp+270h+var_238]
0x18000db6d  lea     rcx, ds:0[rax*4]
0x18000db75  test    rcx, rcx
0x18000db78  jz      loc_18000DC9D
0x18000db7e  mov     [r14], rcx
0x18000db81  mov     eax, [rcx]
0x18000db83  inc     eax
0x18000db85  mov     [rcx], eax
0x18000db87  test    rdi, rdi
0x18000db8a  jnz     short loc_18000DBC5
0x18000db8c  test    rbx, rbx
0x18000db8f  jnz     loc_18000DCC6
0x18000db95  xor     eax, eax
0x18000db97  mov     rcx, [rbp+170h+var_20]
0x18000db9e  xor     rcx, rsp; StackCookie
0x18000dba1  call    __security_check_cookie
0x18000dba6  lea     r11, [rsp+270h+var_10]
0x18000dbae  mov     rbx, [r11+30h]
0x18000dbb2  mov     rsi, [r11+38h]
0x18000dbb6  mov     rsp, r11
0x18000dbb9  pop     r14
0x18000dbbb  pop     rdi
0x18000dbbc  pop     rbp
0x18000dbbd  retn
0x18000dbbe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000dbc3  jmp     short loc_18000DB97
0x18000dbc5  mov     rcx, rdi; this
0x18000dbc8  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000dbcd  jmp     short loc_18000DB8C
0x18000dbcf  mov     rcx, [rbp+178h]; this
0x18000dbd6  lea     r8, aWil; "wil"
0x18000dbdd  mov     r9d, esi; char *
0x18000dbe0  mov     edx, 66h ; 'f'; void *
0x18000dbe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbea  mov     rcx, [rbp+178h]; this
0x18000dbf1  lea     r8, aWil; "wil"
0x18000dbf8  mov     r9d, esi; char *
0x18000dbfb  mov     edx, 6Fh ; 'o'; void *
0x18000dc00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc05  mov     rcx, [rbp+178h]; this
0x18000dc0c  lea     r8, aWil; "wil"
0x18000dc13  mov     r9d, esi; char *
0x18000dc16  mov     edx, 12Eh; void *
0x18000dc1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc20  test    rdi, rdi
0x18000dc23  jz      short loc_18000DC2D
0x18000dc25  mov     rcx, rdi; this
0x18000dc28  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000dc2d  mov     rcx, rbx; this
0x18000dc30  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000dc35  mov     eax, esi
0x18000dc37  jmp     loc_18000DB97
0x18000dc3c  mov     rcx, [rbp+178h]; this
0x18000dc43  lea     r8, aWil; "wil"
0x18000dc4a  mov     r9d, ebx; char *
0x18000dc4d  mov     edx, 137h; void *
0x18000dc52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc57  test    rdi, rdi
0x18000dc5a  jz      short loc_18000DC64
0x18000dc5c  mov     rcx, rdi; this
0x18000dc5f  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000dc64  mov     rcx, [rsp+270h+var_240]; this
0x18000dc69  test    rcx, rcx
0x18000dc6c  jnz     short loc_18000DCBF
0x18000dc6e  mov     eax, ebx
0x18000dc70  jmp     loc_18000DB97
0x18000dc75  test    eax, 0FFFFFF7Fh
0x18000dc7a  jz      short loc_18000DC95
0x18000dc7c  mov     rcx, [rbp+178h]; this
0x18000dc83  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dc8a  mov     edx, 0E01h; void *
0x18000dc8f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000dc95  mov     rdi, rbx
0x18000dc98  jmp     loc_18000DB4A
0x18000dc9d  mov     r8, r14
0x18000dca0  lea     rdx, [rsp+270h+var_240]
0x18000dca5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000dcaa  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000dcaf  mov     ebx, eax
0x18000dcb1  test    eax, eax
0x18000dcb3  js      short loc_18000DC3C
0x18000dcb5  mov     rbx, [rsp+270h+var_240]
0x18000dcba  jmp     loc_18000DB87
0x18000dcbf  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000dcc4  jmp     short loc_18000DC6E
0x18000dcc6  mov     rcx, rbx; this
0x18000dcc9  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000dcce  jmp     loc_18000DB95
```
