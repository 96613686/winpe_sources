# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004a80`
- end: `0x180004ca7`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001d914`

## callees

- `0x1800032d0`
- `0x180004494`
- `0x180004a80`
- `0x180004d8c`
- `0x1800051e8`
- `0x180005214`
- `0x180006bc8`
- `0x1800077c8`
- `0x18002de04`
- `0x180031f34`
- `0x180037780`
- `0x18003a2cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004b17`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004b17`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004af7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004af7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004abb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004abb`

## string_xrefs

- `0x180004c3d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v13, v19);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v13, v20);
    if ( v10 )
      wil::details::ReleaseMutex(v10, v16);
    wil::details::CloseHandle(v6, v16);
    return v13;
  }
  else
  {
    v14 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v14;
      ++*v14;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v17,
          120);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        return v18;
      }
      v6 = v21;
    }
    if ( v10 )
      wil::details::ReleaseMutex(v10, v12);
    if ( v6 )
      wil::details::CloseHandle(v6, v12);
    return 0;
  }
}

```

## disassembly

```asm
0x180004a80  mov     [rsp-8+arg_10], rbx
0x180004a85  mov     [rsp-8+arg_18], rsi
0x180004a8a  push    rbp
0x180004a8b  push    rdi
0x180004a8c  push    r14
0x180004a8e  lea     rbp, [rsp-170h]
0x180004a96  sub     rsp, 270h
0x180004a9d  mov     rax, cs:__security_cookie
0x180004aa4  xor     rax, rsp
0x180004aa7  mov     [rbp+180h+var_20], rax
0x180004aae  mov     r14, rdx
0x180004ab1  mov     qword ptr [rdx], 0
0x180004ab8  mov     rbx, rcx
0x180004abb  call    cs:__imp_GetCurrentProcessId
0x180004ac1  mov     [rsp+280h+var_258], rbx
0x180004ac6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004acd  mov     r9d, eax
0x180004ad0  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180004ad8  mov     edx, 104h; unsigned __int64
0x180004add  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004ae2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004ae7  mov     r9d, 1F0001h; dwDesiredAccess
0x180004aed  lea     rdx, [rsp+280h+Name]; lpName
0x180004af2  xor     r8d, r8d; dwFlags
0x180004af5  xor     ecx, ecx; lpMutexAttributes
0x180004af7  call    cs:__imp_CreateMutexExW
0x180004afd  mov     [rsp+280h+var_250], rax
0x180004b02  mov     rbx, rax
0x180004b05  test    rax, rax
0x180004b08  jz      loc_180004BBB
0x180004b0e  xor     r8d, r8d; bAlertable
0x180004b11  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004b14  mov     rcx, rax; hHandle
0x180004b17  call    cs:__imp_WaitForSingleObjectEx
0x180004b1d  cmp     eax, 102h
0x180004b22  jz      loc_180004C2F
0x180004b28  test    eax, 0FFFFFF7Fh
0x180004b2d  jnz     loc_180004C36
0x180004b33  mov     rdi, rbx
0x180004b36  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180004b3b  mov     [rsp+280h+var_240], rdi
0x180004b40  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004b45  mov     [rsp+280h+var_248], 0
0x180004b4e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004b53  mov     esi, eax
0x180004b55  test    eax, eax
0x180004b57  js      short loc_180004BC2
0x180004b59  mov     rax, [rsp+280h+var_248]
0x180004b5e  lea     rcx, ds:0[rax*4]
0x180004b66  test    rcx, rcx
0x180004b69  jz      loc_180004C4F
0x180004b6f  mov     [r14], rcx
0x180004b72  mov     eax, [rcx]
0x180004b74  inc     eax
0x180004b76  mov     [rcx], eax
0x180004b78  test    rdi, rdi
0x180004b7b  jz      short loc_180004B85
0x180004b7d  mov     rcx, rdi; this
0x180004b80  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180004b85  test    rbx, rbx
0x180004b88  jz      short loc_180004B92
0x180004b8a  mov     rcx, rbx; this
0x180004b8d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004b92  xor     eax, eax
0x180004b94  mov     rcx, [rbp+180h+var_20]
0x180004b9b  xor     rcx, rsp; StackCookie
0x180004b9e  call    __security_check_cookie
0x180004ba3  lea     r11, [rsp+280h+var_10]
0x180004bab  mov     rbx, [r11+30h]
0x180004baf  mov     rsi, [r11+38h]
0x180004bb3  mov     rsp, r11
0x180004bb6  pop     r14
0x180004bb8  pop     rdi
0x180004bb9  pop     rbp
0x180004bba  retn
0x180004bbb  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004bc0  jmp     short loc_180004B94
0x180004bc2  mov     rcx, [rbp+188h]; this
0x180004bc9  lea     r8, aWil; "wil"
0x180004bd0  mov     r9d, esi; char *
0x180004bd3  mov     edx, 66h ; 'f'; void *
0x180004bd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004bdd  mov     rcx, [rbp+188h]; this
0x180004be4  lea     r8, aWil; "wil"
0x180004beb  mov     r9d, esi; char *
0x180004bee  mov     edx, 6Fh ; 'o'; void *
0x180004bf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004bf8  mov     rcx, [rbp+188h]; this
0x180004bff  lea     r8, aWil; "wil"
0x180004c06  mov     r9d, esi; char *
0x180004c09  mov     edx, 12Eh; void *
0x180004c0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c13  test    rdi, rdi
0x180004c16  jz      short loc_180004C20
0x180004c18  mov     rcx, rdi; this
0x180004c1b  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180004c20  mov     rcx, rbx; this
0x180004c23  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004c28  mov     eax, esi
0x180004c2a  jmp     loc_180004B94
0x180004c2f  xor     edi, edi
0x180004c31  jmp     loc_180004B36
0x180004c36  mov     rcx, [rbp+188h]; this
0x180004c3d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004c44  mov     edx, 0E01h; void *
0x180004c49  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180004c4f  mov     r8, r14
0x180004c52  lea     rdx, [rsp+280h+var_250]
0x180004c57  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004c5c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004c61  mov     ebx, eax
0x180004c63  test    eax, eax
0x180004c65  jns     short loc_180004C9D
0x180004c67  mov     rcx, [rbp+188h]; this
0x180004c6e  lea     r8, aWil; "wil"
0x180004c75  mov     r9d, eax; char *
0x180004c78  mov     edx, 137h; void *
0x180004c7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c82  lea     rcx, [rsp+280h+var_240]
0x180004c87  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004c8c  lea     rcx, [rsp+280h+var_250]
0x180004c91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004c96  mov     eax, ebx
0x180004c98  jmp     loc_180004B94
0x180004c9d  mov     rbx, [rsp+280h+var_250]
0x180004ca2  jmp     loc_180004B78
```
