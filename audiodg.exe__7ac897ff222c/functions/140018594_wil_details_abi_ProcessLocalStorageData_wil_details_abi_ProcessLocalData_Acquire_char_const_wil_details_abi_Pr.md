# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140018594`
- end: `0x140018728`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140051874`

## callees

- `0x14000c33c`
- `0x140016848`
- `0x140016f30`
- `0x140018594`
- `0x140018e68`
- `0x140059774`
- `0x14005d0e0`
- `0x140060f54`
- `0x140061ec8`
- `0x14006213c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140018605`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140018605`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400185c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400185c9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *v4; // rcx
  wil::details *v5; // rbx
  int Pointer; // eax
  unsigned int v8; // edi
  void *v9; // rdx
  _DWORD *v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  void *v13; // rdx
  void *v14; // rdx
  wil::details *Mutex; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v5 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v4);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &Mutex,
    v16);
  v17 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
  v8 = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      120);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
    wil::details::CloseHandle(v5, v9);
    return v8;
  }
  v10 = v17;
  if ( v17 )
  {
    *a2 = v17;
    ++*v10;
LABEL_12:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
    if ( v5 )
      wil::details::CloseHandle(v5, v14);
    return 0;
  }
  v11 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v5 = Mutex;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v11, 120);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  if ( Mutex )
    wil::details::CloseHandle(Mutex, v13);
  return v12;
}

```

## disassembly

```asm
0x140018594  mov     [rsp-8+arg_10], rbx
0x140018599  push    rbp
0x14001859a  push    rsi
0x14001859b  push    rdi
0x14001859c  lea     rbp, [rsp-170h]
0x1400185a4  sub     rsp, 270h
0x1400185ab  mov     rax, cs:__security_cookie
0x1400185b2  xor     rax, rsp
0x1400185b5  mov     [rbp+180h+var_20], rax
0x1400185bc  mov     rsi, rdx
0x1400185bf  mov     qword ptr [rdx], 0
0x1400185c6  mov     rbx, rcx
0x1400185c9  call    cs:__imp_GetCurrentProcessId
0x1400185cf  mov     [rsp+280h+var_258], rbx
0x1400185d4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400185db  mov     r9d, eax
0x1400185de  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x1400185e6  mov     edx, 104h; unsigned __int64
0x1400185eb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400185f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400185f5  mov     r9d, 1F0001h; dwDesiredAccess
0x1400185fb  lea     rdx, [rsp+280h+Name]; lpName
0x140018600  xor     r8d, r8d; dwFlags
0x140018603  xor     ecx, ecx; lpMutexAttributes
0x140018605  call    cs:__imp_CreateMutexExW
0x14001860b  mov     [rsp+280h+var_250], rax
0x140018610  mov     rbx, rax
0x140018613  test    rax, rax
0x140018616  jnz     short loc_140018622
0x140018618  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14001861d  jmp     loc_140018706
0x140018622  lea     rdx, [rsp+280h+var_248]
0x140018627  lea     rcx, [rsp+280h+var_250]
0x14001862c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140018631  lea     rdx, [rsp+280h+var_240]; void **
0x140018636  mov     [rsp+280h+var_240], 0
0x14001863f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140018644  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140018649  mov     edi, eax
0x14001864b  test    eax, eax
0x14001864d  jns     short loc_140018683
0x14001864f  mov     rcx, [rbp+188h]; this
0x140018656  lea     r8, aWil; "wil"
0x14001865d  mov     r9d, eax; char *
0x140018660  mov     edx, 12Eh; void *
0x140018665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001866a  lea     rcx, [rsp+280h+var_248]
0x14001866f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140018674  mov     rcx, rbx; this
0x140018677  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14001867c  mov     eax, edi
0x14001867e  jmp     loc_140018706
0x140018683  mov     rcx, [rsp+280h+var_240]
0x140018688  test    rcx, rcx
0x14001868b  jz      short loc_140018698
0x14001868d  mov     [rsi], rcx
0x140018690  mov     eax, [rcx]
0x140018692  inc     eax
0x140018694  mov     [rcx], eax
0x140018696  jmp     short loc_1400186ED
0x140018698  mov     r8, rsi
0x14001869b  lea     rdx, [rsp+280h+var_250]
0x1400186a0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400186a5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400186aa  mov     ebx, eax
0x1400186ac  test    eax, eax
0x1400186ae  jns     short loc_1400186E8
0x1400186b0  mov     rcx, [rbp+188h]; this
0x1400186b7  lea     r8, aWil; "wil"
0x1400186be  mov     r9d, eax; char *
0x1400186c1  mov     edx, 137h; void *
0x1400186c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400186cb  lea     rcx, [rsp+280h+var_248]
0x1400186d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400186d5  mov     rcx, [rsp+280h+var_250]; this
0x1400186da  test    rcx, rcx
0x1400186dd  jz      short loc_1400186E4
0x1400186df  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400186e4  mov     eax, ebx
0x1400186e6  jmp     short loc_140018706
0x1400186e8  mov     rbx, [rsp+280h+var_250]
0x1400186ed  lea     rcx, [rsp+280h+var_248]
0x1400186f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400186f7  test    rbx, rbx
0x1400186fa  jz      short loc_140018704
0x1400186fc  mov     rcx, rbx; this
0x1400186ff  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140018704  xor     eax, eax
0x140018706  mov     rcx, [rbp+180h+var_20]
0x14001870d  xor     rcx, rsp; StackCookie
0x140018710  call    __security_check_cookie
0x140018715  mov     rbx, [rsp+280h+arg_10]
0x14001871d  add     rsp, 270h
0x140018724  pop     rdi
0x140018725  pop     rsi
0x140018726  pop     rbp
0x140018727  retn
```
