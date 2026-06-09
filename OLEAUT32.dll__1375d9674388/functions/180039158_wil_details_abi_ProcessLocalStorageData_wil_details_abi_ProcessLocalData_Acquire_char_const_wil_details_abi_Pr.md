# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180039158`
- end: `0x180039383`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180039018`

## callees

- `0x1800161b8`
- `0x180039158`
- `0x18003938c`
- `0x1800393e0`
- `0x18003942c`
- `0x1800397d8`
- `0x180039804`
- `0x180039820`
- `0x1800483d0`
- `0x18004a57c`
- `0x18004d900`
- `0x180050c9c`
- `0x180054850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039193`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039193`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800391d8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800391d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180039202`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180039202`

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
  DWORD v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  unsigned int LastErrorFailHr; // ebx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
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
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_13;
  }
  v7 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
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
  v23[0] = v11;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v8, &v22, (bool *)v10);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
    LastErrorFailHr = v14;
    goto LABEL_13;
  }
  v15 = (_DWORD *)(4 * v22);
  if ( !(4 * v22) )
  {
    v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    LastErrorFailHr = v18;
    if ( v18 >= 0 )
    {
      v6 = (wil::details *)hHandle;
      goto LABEL_7;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v18, 120);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
LABEL_13:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return LastErrorFailHr;
  }
  *a2 = v15;
  ++*v15;
LABEL_7:
  if ( v11 )
    wil::details::ReleaseMutex(v11, v13);
  if ( v6 )
    wil::details::CloseHandle(v6, v13);
  return 0;
}

```

## disassembly

```asm
0x180039158  mov     [rsp-8+arg_10], rbx
0x18003915d  mov     [rsp-8+arg_18], rsi
0x180039162  push    rbp
0x180039163  push    rdi
0x180039164  push    r14
0x180039166  lea     rbp, [rsp-170h]
0x18003916e  sub     rsp, 270h
0x180039175  mov     rax, cs:__security_cookie
0x18003917c  xor     rax, rsp
0x18003917f  mov     [rbp+180h+var_20], rax
0x180039186  mov     r14, rdx
0x180039189  mov     qword ptr [rdx], 0
0x180039190  mov     rbx, rcx
0x180039193  call    cs:__imp_GetCurrentProcessId
0x180039199  mov     [rsp+280h+var_258], rbx
0x18003919e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800391a5  mov     r9d, eax
0x1800391a8  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x1800391b0  mov     edx, 104h; unsigned __int64
0x1800391b5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800391ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800391bf  mov     r9d, 1F0001h; dwDesiredAccess
0x1800391c5  mov     [rsp+280h+hHandle], 0
0x1800391ce  xor     r8d, r8d; dwFlags
0x1800391d1  lea     rdx, [rsp+280h+Name]; lpName
0x1800391d6  xor     ecx, ecx; lpMutexAttributes
0x1800391d8  call    cs:__imp_CreateMutexExW
0x1800391de  mov     rdx, rax
0x1800391e1  lea     rcx, [rsp+280h+hHandle]
0x1800391e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800391eb  mov     rbx, [rsp+280h+hHandle]
0x1800391f0  test    rbx, rbx
0x1800391f3  jz      loc_180039296
0x1800391f9  xor     r8d, r8d; bAlertable
0x1800391fc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800391ff  mov     rcx, rbx; hHandle
0x180039202  call    cs:__imp_WaitForSingleObjectEx
0x180039208  cmp     eax, 102h
0x18003920d  jnz     loc_180039330
0x180039213  xor     edi, edi
0x180039215  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18003921a  mov     [rsp+280h+var_240], rdi
0x18003921f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180039224  mov     [rsp+280h+var_248], 0
0x18003922d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180039232  mov     esi, eax
0x180039234  test    eax, eax
0x180039236  js      loc_1800392CE
0x18003923c  mov     rax, [rsp+280h+var_248]
0x180039241  lea     rcx, ds:0[rax*4]
0x180039249  test    rcx, rcx
0x18003924c  jz      short loc_1800392AB
0x18003924e  mov     [r14], rcx
0x180039251  mov     eax, [rcx]
0x180039253  inc     eax
0x180039255  mov     [rcx], eax
0x180039257  test    rdi, rdi
0x18003925a  jnz     loc_180039376
0x180039260  test    rbx, rbx
0x180039263  jz      short loc_18003926D
0x180039265  mov     rcx, rbx; this
0x180039268  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003926d  xor     eax, eax
0x18003926f  mov     rcx, [rbp+180h+var_20]
0x180039276  xor     rcx, rsp; StackCookie
0x180039279  call    __security_check_cookie
0x18003927e  lea     r11, [rsp+280h+var_10]
0x180039286  mov     rbx, [r11+30h]
0x18003928a  mov     rsi, [r11+38h]
0x18003928e  mov     rsp, r11
0x180039291  pop     r14
0x180039293  pop     rdi
0x180039294  pop     rbp
0x180039295  retn
0x180039296  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003929b  mov     ebx, eax
0x18003929d  lea     rcx, [rsp+280h+hHandle]
0x1800392a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800392a7  mov     eax, ebx
0x1800392a9  jmp     short loc_18003926F
0x1800392ab  mov     r8, r14
0x1800392ae  lea     rdx, [rsp+280h+hHandle]
0x1800392b3  lea     rcx, [rsp+280h+Name]
0x1800392b8  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800392bd  mov     ebx, eax
0x1800392bf  test    eax, eax
0x1800392c1  js      loc_18003934C
0x1800392c7  mov     rbx, [rsp+280h+hHandle]
0x1800392cc  jmp     short loc_180039257
0x1800392ce  mov     rcx, [rbp+188h]; this
0x1800392d5  lea     r8, aWil; "wil"
0x1800392dc  mov     r9d, esi; char *
0x1800392df  mov     edx, 66h ; 'f'; void *
0x1800392e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800392e9  mov     rcx, [rbp+188h]; this
0x1800392f0  lea     r8, aWil; "wil"
0x1800392f7  mov     r9d, esi; char *
0x1800392fa  mov     edx, 6Fh ; 'o'; void *
0x1800392ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039304  mov     rcx, [rbp+188h]; this
0x18003930b  lea     r8, aWil; "wil"
0x180039312  mov     r9d, esi; char *
0x180039315  mov     edx, 12Eh; void *
0x18003931a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003931f  lea     rcx, [rsp+280h+var_240]
0x180039324  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180039329  mov     ebx, esi
0x18003932b  jmp     loc_18003929D
0x180039330  test    eax, 0FFFFFF7Fh
0x180039335  jz      short loc_180039344
0x180039337  mov     rcx, [rbp+188h]; this
0x18003933e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180039344  mov     rdi, rbx
0x180039347  jmp     loc_180039215
0x18003934c  mov     rcx, [rbp+188h]; this
0x180039353  lea     r8, aWil; "wil"
0x18003935a  mov     r9d, eax; char *
0x18003935d  mov     edx, 137h; void *
0x180039362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039367  lea     rcx, [rsp+280h+var_240]
0x18003936c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180039371  jmp     loc_18003929D
0x180039376  mov     rcx, rdi; this
0x180039379  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18003937e  jmp     loc_180039260
```
