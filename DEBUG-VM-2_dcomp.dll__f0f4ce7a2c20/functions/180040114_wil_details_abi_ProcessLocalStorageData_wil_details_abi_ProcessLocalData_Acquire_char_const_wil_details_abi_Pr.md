# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180040114`
- end: `0x180040340`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800400b0`

## callees

- `0x18001358c`
- `0x18003ff18`
- `0x180040114`
- `0x18004057c`
- `0x180040e6c`
- `0x180040f24`
- `0x180041358`
- `0x180041374`
- `0x1800413f8`
- `0x1800e4908`
- `0x1800f6f10`
- `0x1800f8e54`
- `0x1800f92cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800401e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800401e6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180040194`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180040194`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004014f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004014f`

## string_xrefs

- `0x1800402dc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  void *v16; // rdx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = (wil::details *)hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v19);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v20);
    if ( v11 )
      wil::details::ReleaseMutex(v11, v16);
    wil::details::CloseHandle(v6, v16);
    return v14;
  }
  else
  {
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
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
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
        return v18;
      }
      v6 = (wil::details *)hHandle;
    }
    if ( v11 )
      wil::details::ReleaseMutex(v11, v13);
    if ( v6 )
      wil::details::CloseHandle(v6, v13);
    return 0;
  }
}

```

## disassembly

```asm
0x180040114  mov     [rsp-8+arg_10], rbx
0x180040119  mov     [rsp-8+arg_18], rsi
0x18004011e  push    rbp
0x18004011f  push    rdi
0x180040120  push    r14
0x180040122  lea     rbp, [rsp-170h]
0x18004012a  sub     rsp, 270h
0x180040131  mov     rax, cs:__security_cookie
0x180040138  xor     rax, rsp
0x18004013b  mov     [rbp+180h+var_20], rax
0x180040142  mov     r14, rdx
0x180040145  mov     qword ptr [rdx], 0
0x18004014c  mov     rbx, rcx
0x18004014f  call    cs:__imp_GetCurrentProcessId
0x180040155  mov     [rsp+280h+var_258], rbx
0x18004015a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180040161  mov     r9d, eax
0x180040164  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x18004016c  mov     edx, 104h; unsigned __int64
0x180040171  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180040176  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004017b  mov     r9d, 1F0001h; dwDesiredAccess
0x180040181  mov     [rsp+280h+hHandle], 0
0x18004018a  xor     r8d, r8d; dwFlags
0x18004018d  lea     rdx, [rsp+280h+Name]; lpName
0x180040192  xor     ecx, ecx; lpMutexAttributes
0x180040194  call    cs:__imp_CreateMutexExW
0x18004019a  mov     rdx, rax
0x18004019d  lea     rcx, [rsp+280h+hHandle]
0x1800401a2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800401a7  mov     rbx, [rsp+280h+hHandle]
0x1800401ac  test    rbx, rbx
0x1800401af  jnz     short loc_1800401DD
0x1800401b1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800401b6  mov     rcx, [rbp+180h+var_20]
0x1800401bd  xor     rcx, rsp; StackCookie
0x1800401c0  call    __security_check_cookie
0x1800401c5  lea     r11, [rsp+280h+var_10]
0x1800401cd  mov     rbx, [r11+30h]
0x1800401d1  mov     rsi, [r11+38h]
0x1800401d5  mov     rsp, r11
0x1800401d8  pop     r14
0x1800401da  pop     rdi
0x1800401db  pop     rbp
0x1800401dc  retn
0x1800401dd  xor     r8d, r8d; bAlertable
0x1800401e0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800401e3  mov     rcx, rbx; hHandle
0x1800401e6  call    cs:__imp_WaitForSingleObjectEx
0x1800401ec  cmp     eax, 102h
0x1800401f1  jz      short loc_180040264
0x1800401f3  test    eax, 0FFFFFF7Fh
0x1800401f8  jnz     loc_1800402D5
0x1800401fe  mov     rdi, rbx
0x180040201  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180040206  mov     [rsp+280h+var_240], rdi
0x18004020b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180040210  mov     [rsp+280h+var_248], 0
0x180040219  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18004021e  mov     esi, eax
0x180040220  test    eax, eax
0x180040222  js      short loc_180040268
0x180040224  mov     rax, [rsp+280h+var_248]
0x180040229  lea     rcx, ds:0[rax*4]
0x180040231  test    rcx, rcx
0x180040234  jz      loc_1800402EE
0x18004023a  mov     [r14], rcx
0x18004023d  mov     eax, [rcx]
0x18004023f  inc     eax
0x180040241  mov     [rcx], eax
0x180040243  test    rdi, rdi
0x180040246  jz      short loc_180040250
0x180040248  mov     rcx, rdi; this
0x18004024b  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180040250  test    rbx, rbx
0x180040253  jz      short loc_18004025D
0x180040255  mov     rcx, rbx; this
0x180040258  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18004025d  xor     eax, eax
0x18004025f  jmp     loc_1800401B6
0x180040264  xor     edi, edi
0x180040266  jmp     short loc_180040201
0x180040268  mov     rcx, [rbp+188h]; this
0x18004026f  lea     r8, aWil; "wil"
0x180040276  mov     r9d, esi; char *
0x180040279  mov     edx, 66h ; 'f'; void *
0x18004027e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040283  mov     rcx, [rbp+188h]; this
0x18004028a  lea     r8, aWil; "wil"
0x180040291  mov     r9d, esi; char *
0x180040294  mov     edx, 6Fh ; 'o'; void *
0x180040299  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004029e  mov     rcx, [rbp+188h]; this
0x1800402a5  lea     r8, aWil; "wil"
0x1800402ac  mov     r9d, esi; char *
0x1800402af  mov     edx, 12Eh; void *
0x1800402b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800402b9  test    rdi, rdi
0x1800402bc  jz      short loc_1800402C6
0x1800402be  mov     rcx, rdi; this
0x1800402c1  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800402c6  mov     rcx, rbx; this
0x1800402c9  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800402ce  mov     eax, esi
0x1800402d0  jmp     loc_1800401B6
0x1800402d5  mov     rcx, [rbp+188h]; this
0x1800402dc  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800402e3  mov     edx, 0E01h; void *
0x1800402e8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800402ee  mov     r8, r14
0x1800402f1  lea     rdx, [rsp+280h+hHandle]
0x1800402f6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800402fb  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180040300  mov     ebx, eax
0x180040302  test    eax, eax
0x180040304  jns     loc_18017DACC
0x18004030a  mov     rcx, [rbp+188h]; this
0x180040311  lea     r8, aWil; "wil"
0x180040318  mov     r9d, eax; char *
0x18004031b  mov     edx, 137h; void *
0x180040320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040325  lea     rcx, [rsp+280h+var_240]
0x18004032a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004032f  lea     rcx, [rsp+280h+hHandle]
0x180040334  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040339  mov     eax, ebx
0x18004033b  jmp     loc_1800401B6
0x18017dacc  mov     rbx, [rsp+280h+hHandle]
0x18017dad1  jmp     loc_180040243
```
