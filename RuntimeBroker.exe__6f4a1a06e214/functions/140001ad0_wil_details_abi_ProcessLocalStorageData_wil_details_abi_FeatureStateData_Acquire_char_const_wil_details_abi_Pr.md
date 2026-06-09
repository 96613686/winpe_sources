# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140001ad0`
- end: `0x140001cfb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140003ac0`

## callees

- `0x140001ad0`
- `0x140001d04`
- `0x140001d90`
- `0x14000222c`
- `0x1400027ac`
- `0x140007730`
- `0x140007f58`
- `0x1400087cc`
- `0x140008c80`
- `0x14000b404`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140001b34`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140001b34`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140001b5e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140001b5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001af8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001af8`

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
  void *v8; // rdx
  unsigned int v9; // r8d
  char *v10; // r9
  wil::details *v11; // rsi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // ebp
  _DWORD *v15; // rax
  void *v17; // rdx
  void *v18; // rdx
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // [rsp+20h] [rbp-258h]
  int v22; // [rsp+20h] [rbp-258h]
  wil::details *v23; // [rsp+30h] [rbp-248h]
  unsigned __int64 v24; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v23 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v7 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v7 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v8, v9, v10);
    v11 = v6;
  }
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v8, &v24, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v21);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v22);
    if ( v11 )
      wil::details::ReleaseMutex(v11, v17);
    wil::details::CloseHandle(v6, v17);
    return v14;
  }
  else
  {
    v15 = (_DWORD *)(4 * v24);
    if ( 4 * v24 )
    {
      *a2 = v15;
      ++*v15;
LABEL_8:
      if ( v11 )
        wil::details::ReleaseMutex(v11, v13);
      if ( v6 )
        wil::details::CloseHandle(v6, v13);
      return 0;
    }
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v20 = v19;
    if ( v19 >= 0 )
    {
      v6 = v23;
      goto LABEL_8;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v19, 304);
    if ( v11 )
      wil::details::ReleaseMutex(v11, v18);
    if ( v23 )
      wil::details::CloseHandle(v23, v18);
    return v20;
  }
}

```

## disassembly

```asm
0x140001ad0  push    rbx
0x140001ad2  push    rbp
0x140001ad3  push    rdi
0x140001ad4  sub     rsp, 260h
0x140001adb  mov     rax, cs:__security_cookie
0x140001ae2  xor     rax, rsp
0x140001ae5  mov     [rsp+278h+var_28], rax
0x140001aed  xor     ebp, ebp
0x140001aef  mov     rdi, rdx
0x140001af2  mov     [rdx], rbp
0x140001af5  mov     rbx, rcx
0x140001af8  call    cs:__imp_GetCurrentProcessId
0x140001afe  mov     [rsp+278h+var_250], rbx
0x140001b03  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140001b0a  mov     r9d, eax
0x140001b0d  mov     [rsp+278h+var_258], 130h; int
0x140001b15  mov     edx, 104h; unsigned __int64
0x140001b1a  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140001b1f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140001b24  mov     r9d, 1F0001h; dwDesiredAccess
0x140001b2a  lea     rdx, [rsp+278h+Name]; lpName
0x140001b2f  xor     r8d, r8d; dwFlags
0x140001b32  xor     ecx, ecx; lpMutexAttributes
0x140001b34  call    cs:__imp_CreateMutexExW
0x140001b3a  mov     [rsp+278h+var_248], rax
0x140001b3f  mov     rbx, rax
0x140001b42  test    rax, rax
0x140001b45  jz      loc_140001BED
0x140001b4b  xor     r8d, r8d; bAlertable
0x140001b4e  mov     [rsp+278h+arg_10], rsi
0x140001b56  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140001b5b  mov     rcx, rax; hHandle
0x140001b5e  call    cs:__imp_WaitForSingleObjectEx
0x140001b64  cmp     eax, 102h
0x140001b69  jz      loc_140001C5C
0x140001b6f  test    eax, 0FFFFFF7Fh
0x140001b74  jnz     loc_140001C96
0x140001b7a  mov     rsi, rbx
0x140001b7d  lea     r8, [rsp+278h+var_240]; unsigned __int64 *
0x140001b82  mov     [rsp+278h+var_240], rbp
0x140001b87  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140001b8c  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140001b91  mov     ebp, eax
0x140001b93  test    eax, eax
0x140001b95  js      short loc_140001BF4
0x140001b97  mov     rax, [rsp+278h+var_240]
0x140001b9c  lea     rax, ds:0[rax*4]
0x140001ba4  test    rax, rax
0x140001ba7  jz      loc_140001CAE
0x140001bad  mov     [rdi], rax
0x140001bb0  mov     ecx, [rax]
0x140001bb2  inc     ecx
0x140001bb4  mov     [rax], ecx
0x140001bb6  test    rsi, rsi
0x140001bb9  jnz     loc_140001CE1
0x140001bbf  test    rbx, rbx
0x140001bc2  jnz     loc_140001CEE
0x140001bc8  xor     eax, eax
0x140001bca  mov     rsi, [rsp+278h+arg_10]
0x140001bd2  mov     rcx, [rsp+278h+var_28]
0x140001bda  xor     rcx, rsp; StackCookie
0x140001bdd  call    __security_check_cookie
0x140001be2  add     rsp, 260h
0x140001be9  pop     rdi
0x140001bea  pop     rbp
0x140001beb  pop     rbx
0x140001bec  retn
0x140001bed  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140001bf2  jmp     short loc_140001BD2
0x140001bf4  mov     rcx, [rsp+278h]; this
0x140001bfc  lea     r8, aWil; "wil"
0x140001c03  mov     r9d, ebp; char *
0x140001c06  mov     edx, 66h ; 'f'; void *
0x140001c0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140001c10  mov     rcx, [rsp+278h]; this
0x140001c18  lea     r8, aWil; "wil"
0x140001c1f  mov     r9d, ebp; char *
0x140001c22  mov     edx, 6Fh ; 'o'; void *
0x140001c27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140001c2c  mov     rcx, [rsp+278h]; this
0x140001c34  lea     r8, aWil; "wil"
0x140001c3b  mov     r9d, ebp; char *
0x140001c3e  mov     edx, 12Eh; void *
0x140001c43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140001c48  test    rsi, rsi
0x140001c4b  jnz     short loc_140001CA4
0x140001c4d  mov     rcx, rbx; this
0x140001c50  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140001c55  mov     eax, ebp
0x140001c57  jmp     loc_140001BCA
0x140001c5c  mov     rsi, rbp
0x140001c5f  jmp     loc_140001B7D
0x140001c64  mov     rcx, [rsp+278h]; this
0x140001c6c  lea     r8, aWil; "wil"
0x140001c73  mov     r9d, ebx; char *
0x140001c76  mov     edx, 137h; void *
0x140001c7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140001c80  test    rsi, rsi
0x140001c83  jnz     short loc_140001CD0
0x140001c85  mov     rcx, [rsp+278h+var_248]; this
0x140001c8a  test    rcx, rcx
0x140001c8d  jnz     short loc_140001CDA
0x140001c8f  mov     eax, ebx
0x140001c91  jmp     loc_140001BCA
0x140001c96  mov     rcx, [rsp+278h]; this
0x140001c9e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140001ca4  mov     rcx, rsi; this
0x140001ca7  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x140001cac  jmp     short loc_140001C4D
0x140001cae  mov     r8, rdi
0x140001cb1  lea     rdx, [rsp+278h+var_248]
0x140001cb6  lea     rcx, [rsp+278h+Name]
0x140001cbb  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140001cc0  mov     ebx, eax
0x140001cc2  test    eax, eax
0x140001cc4  js      short loc_140001C64
0x140001cc6  mov     rbx, [rsp+278h+var_248]
0x140001ccb  jmp     loc_140001BB6
0x140001cd0  mov     rcx, rsi; this
0x140001cd3  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x140001cd8  jmp     short loc_140001C85
0x140001cda  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140001cdf  jmp     short loc_140001C8F
0x140001ce1  mov     rcx, rsi; this
0x140001ce4  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x140001ce9  jmp     loc_140001BBF
0x140001cee  mov     rcx, rbx; this
0x140001cf1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140001cf6  jmp     loc_140001BC8
```
