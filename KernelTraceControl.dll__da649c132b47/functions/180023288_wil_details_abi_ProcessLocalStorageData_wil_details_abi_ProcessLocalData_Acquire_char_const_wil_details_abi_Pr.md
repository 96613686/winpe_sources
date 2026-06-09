# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180023288`
- end: `0x18002349a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800208ec`

## callees

- `0x1800112ec`
- `0x18002018c`
- `0x1800201c4`
- `0x1800201dc`
- `0x1800203ac`
- `0x180023288`
- `0x180024418`
- `0x1800246cc`
- `0x180026e30`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x18002330b`
- `KERNEL32!CreateMutexExW` at `0x18002330b`
- `KERNEL32!ReleaseMutex` at `0x180023432`
- `KERNEL32!ReleaseMutex` at `0x180023432`
- `KERNEL32!GetCurrentProcessId` at `0x1800232c8`
- `KERNEL32!GetCurrentProcessId` at `0x1800232c8`
- `KERNEL32!CloseHandle` at `0x180023456`
- `KERNEL32!CloseHandle` at `0x180023456`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  void *v4; // rbx
  HANDLE Mutex; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  int LastError; // edi
  _DWORD *v9; // rsi
  unsigned __int64 v10; // r15
  bool v11; // dl
  bool *v12; // r9
  int ValueInternal; // eax
  unsigned int v14; // r8d
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  int v22; // [rsp+28h] [rbp-E0h]
  HANDLE v23; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int64 v24; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE hMutex[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  hMutex[1] = (HANDLE)-2LL;
  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v22 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%d:%d:%hs", CurrentProcessId);
  v4 = 0;
  v23 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  if ( Mutex )
  {
    v4 = Mutex;
    v23 = Mutex;
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x15B0,
                  (unsigned int)"internal\\sdk\\inc\\wil\\resultmacros.h",
                  v7);
  }
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr_NoOriginate(
      retaddr,
      (void *)0x11A,
      v6,
      (const char *)(unsigned int)LastError,
      120);
    goto LABEL_23;
  }
  wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,0,std::nullptr_t>>,wil::err_returncode_policy>::acquire(
    &v23,
    hMutex);
  v9 = 0;
  v10 = 0;
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v11, &v24, v12);
  LastError = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v10 = v24;
    LastError = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr_NoOriginate(
      retaddr,
      (void *)0x61,
      v14,
      (const char *)(unsigned int)ValueInternal,
      120);
  }
  if ( LastError >= 0 )
  {
    v9 = (_DWORD *)(4 * v10);
    LastError = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr_NoOriginate(
      retaddr,
      (void *)0x6A,
      v14,
      (const char *)(unsigned int)LastError,
      v22);
  }
  if ( LastError >= 0 )
  {
    if ( v9 )
    {
      *a2 = v9;
      *(_DWORD *)*a2 = *v9 + 1;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
              Name,
              &v23,
              a2);
      LastError = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr_NoOriginate(retaddr, (void *)0x126, v16, (const char *)(unsigned int)v15, v22);
LABEL_19:
        v4 = v23;
        goto LABEL_20;
      }
    }
    LastError = 0;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr_NoOriginate(retaddr, (void *)0x11E, v14, (const char *)(unsigned int)LastError, v22);
LABEL_20:
  if ( hMutex[0] && !ReleaseMutex(hMutex[0]) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x87B, v17, v18);
LABEL_23:
  if ( v4 && !CloseHandle(v4) )
  {
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x875, v19, v20);
    __debugbreak();
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180023288  mov     rax, rsp
0x18002328b  push    rbp
0x18002328c  push    rsi
0x18002328d  push    rdi
0x18002328e  push    r14
0x180023290  push    r15
0x180023292  lea     rbp, [rax-198h]
0x180023299  sub     rsp, 270h
0x1800232a0  mov     qword ptr [rsp+290h+var_248], 0FFFFFFFFFFFFFFFEh
0x1800232a9  mov     [rax+18h], rbx
0x1800232ad  mov     rax, cs:__security_cookie
0x1800232b4  xor     rax, rsp
0x1800232b7  mov     [rbp+190h+var_30], rax
0x1800232be  mov     r14, rdx
0x1800232c1  mov     rbx, rcx
0x1800232c4  and     qword ptr [rdx], 0
0x1800232c8  call    cs:__imp_GetCurrentProcessId
0x1800232ce  mov     r9d, eax
0x1800232d1  mov     [rsp+290h+var_268], rbx
0x1800232d6  mov     [rsp+290h+var_270], 78h ; 'x'; int
0x1800232de  lea     r8, aLocalSm0DDHs; "Local\\SM0:%d:%d:%hs"
0x1800232e5  mov     edx, 104h; unsigned __int64
0x1800232ea  lea     rcx, [rsp+290h+Name]; Buffer
0x1800232ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800232f4  xor     ebx, ebx
0x1800232f6  mov     [rsp+290h+var_260], rbx
0x1800232fb  mov     r9d, 1F0001h; dwDesiredAccess
0x180023301  xor     r8d, r8d; dwFlags
0x180023304  lea     rdx, [rsp+290h+Name]; lpName
0x180023309  xor     ecx, ecx; lpMutexAttributes
0x18002330b  call    cs:__imp_CreateMutexExW
0x180023311  test    rax, rax
0x180023314  jz      short loc_180023322
0x180023316  mov     rbx, rax
0x180023319  mov     [rsp+290h+var_260], rax
0x18002331e  xor     edi, edi
0x180023320  jmp     short loc_18002333C
0x180023322  mov     rcx, [rbp+198h]; this
0x180023329  lea     r8, aInternalSdkInc_0; "internal\\sdk\\inc\\wil\\resultmacros.h"
0x180023330  mov     edx, 15B0h; void *
0x180023335  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002333a  mov     edi, eax
0x18002333c  test    edi, edi
0x18002333e  jns     short loc_180023359
0x180023340  mov     rcx, [rbp+198h]; this
0x180023347  mov     r9d, edi; char *
0x18002334a  mov     edx, 11Ah; void *
0x18002334f  call    ?Return_Hr_NoOriginate@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr_NoOriginate(void *,uint,char const *,long)
0x180023354  jmp     loc_18002344E
0x180023359  lea     rdx, [rsp+290h+hMutex]
0x18002335e  lea     rcx, [rsp+290h+var_260]
0x180023363  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z; wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,0,std::nullptr_t>>,wil::err_returncode_policy>::acquire(ulong *,ulong,int)
0x180023368  nop
0x180023369  xor     esi, esi
0x18002336b  xor     r15d, r15d
0x18002336e  and     [rsp+290h+var_258], rsi
0x180023373  lea     r8, [rsp+290h+var_258]; unsigned __int64 *
0x180023378  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18002337d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180023382  mov     edi, eax
0x180023384  test    eax, eax
0x180023386  jns     short loc_18002339C
0x180023388  mov     rcx, [rbp+198h]; this
0x18002338f  mov     r9d, eax; char *
0x180023392  lea     edx, [rsi+61h]; void *
0x180023395  call    ?Return_Hr_NoOriginate@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr_NoOriginate(void *,uint,char const *,long)
0x18002339a  jmp     short loc_1800233A3
0x18002339c  mov     r15, [rsp+290h+var_258]
0x1800233a1  xor     edi, edi
0x1800233a3  test    edi, edi
0x1800233a5  jns     short loc_1800233BD
0x1800233a7  mov     rcx, [rbp+198h]; this
0x1800233ae  mov     r9d, edi; char *
0x1800233b1  mov     edx, 6Ah ; 'j'; void *
0x1800233b6  call    ?Return_Hr_NoOriginate@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr_NoOriginate(void *,uint,char const *,long)
0x1800233bb  jmp     short loc_1800233C6
0x1800233bd  mov     rsi, r15
0x1800233c0  shl     rsi, 2
0x1800233c4  xor     edi, edi
0x1800233c6  test    edi, edi
0x1800233c8  jns     short loc_1800233E0
0x1800233ca  mov     rcx, [rbp+198h]; this
0x1800233d1  mov     r9d, edi; char *
0x1800233d4  mov     edx, 11Eh; void *
0x1800233d9  call    ?Return_Hr_NoOriginate@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr_NoOriginate(void *,uint,char const *,long)
0x1800233de  jmp     short loc_180023428
0x1800233e0  test    rsi, rsi
0x1800233e3  jz      short loc_1800233F3
0x1800233e5  mov     [r14], rsi
0x1800233e8  mov     ecx, [rsi]
0x1800233ea  inc     ecx
0x1800233ec  mov     rax, [r14]
0x1800233ef  mov     [rax], ecx
0x1800233f1  jmp     short loc_180023421
0x1800233f3  mov     r8, r14
0x1800233f6  lea     rdx, [rsp+290h+var_260]
0x1800233fb  lea     rcx, [rsp+290h+Name]
0x180023400  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(ushort const *,wil::unique_any_t<wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,0,std::nullptr_t>>,wil::err_returncode_policy>> &&,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180023405  mov     edi, eax
0x180023407  test    eax, eax
0x180023409  jns     short loc_180023421
0x18002340b  mov     rcx, [rbp+198h]; this
0x180023412  mov     r9d, eax; char *
0x180023415  mov     edx, 126h; void *
0x18002341a  call    ?Return_Hr_NoOriginate@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr_NoOriginate(void *,uint,char const *,long)
0x18002341f  jmp     short loc_180023423
0x180023421  xor     edi, edi
0x180023423  mov     rbx, [rsp+290h+var_260]
0x180023428  mov     rcx, [rsp+290h+hMutex]; hMutex
0x18002342d  test    rcx, rcx
0x180023430  jz      short loc_18002344E
0x180023432  call    cs:__imp_ReleaseMutex
0x180023438  mov     rcx, [rbp+198h]; this
0x18002343f  test    eax, eax
0x180023441  jnz     short loc_18002344E
0x180023443  mov     edx, 87Bh; void *
0x180023448  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002344d  nop
0x18002344e  test    rbx, rbx
0x180023451  jz      short loc_180023472
0x180023453  mov     rcx, rbx; hObject
0x180023456  call    cs:__imp_CloseHandle
0x18002345c  test    eax, eax
0x18002345e  jnz     short loc_180023472
0x180023460  mov     rcx, [rbp+198h]; this
0x180023467  mov     edx, 875h; void *
0x18002346c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023471  int     3; Trap to Debugger
0x180023472  mov     eax, edi
0x180023474  mov     rcx, [rbp+190h+var_30]
0x18002347b  xor     rcx, rsp; StackCookie
0x18002347e  call    __security_check_cookie
0x180023483  mov     rbx, [rsp+290h+arg_10]
0x18002348b  add     rsp, 270h
0x180023492  pop     r15
0x180023494  pop     r14
0x180023496  pop     rdi
0x180023497  pop     rsi
0x180023498  pop     rbp
0x180023499  retn
```
