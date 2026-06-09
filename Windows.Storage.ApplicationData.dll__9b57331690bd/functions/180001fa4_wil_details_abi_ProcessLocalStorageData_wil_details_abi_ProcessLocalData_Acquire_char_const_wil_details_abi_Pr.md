# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180001fa4`
- end: `0x1800021de`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `570`
- prototype: `HRESULT __fastcall(const char *staticNameWithVersion, wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> **data)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180001914`

## callees

- `0x180001708`
- `0x180001fa4`
- `0x1800026d0`
- `0x180002a84`
- `0x18000308c`
- `0x1800030bc`
- `0x180020904`
- `0x180021efc`
- `0x180028ce8`
- `0x180028e7c`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001fdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001fdf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000201b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000201b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002078`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002078`

## string_xrefs

- `0x1800021aa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
HRESULT __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        const char *staticNameWithVersion,
        wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> **data)
{
  DWORD CurrentProcessId; // eax
  HANDLE v5; // rax
  void *m_ptr; // rbx
  DWORD v8; // eax
  bool v9; // dl
  bool *v10; // r9
  void *v11; // rdi
  HRESULT ValueInternal; // eax
  HRESULT v13; // esi
  wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> *v14; // rcx
  HRESULT v15; // eax
  HRESULT v16; // ebx
  wil::unique_any_t<wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > mutex; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::ReleaseMutex,wistd::integral_constant<unsigned __int64,2>,void *,void *,0,std::nullptr_t> > > lock; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t name[264]; // [rsp+50h] [rbp-B0h] BYREF
  void *retaddr; // [rsp+288h] [rbp+188h]

  *data = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, staticNameWithVersion);
  v5 = CreateMutexExW(0, name, 0, 0x1F0001u);
  mutex.m_ptr = v5;
  m_ptr = v5;
  if ( !v5 )
    return wil::details::GetLastErrorFailHr();
  v8 = WaitForSingleObjectEx(v5, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        0xE01u,
        "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h");
    v11 = m_ptr;
  }
  lock.m_ptr = v11;
  v18 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(name, v9, &v18, v10);
  v13 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x66u, "wil", ValueInternal);
    wil::details::in1diag3::Return_Hr(retaddr, 0x6Fu, "wil", v13);
    wil::details::in1diag3::Return_Hr(retaddr, 0x12Eu, "wil", v13);
    if ( v11 )
      wil::details::ReleaseMutex(v11);
    wil::details::CloseHandle(m_ptr);
    return v13;
  }
  else
  {
    v14 = (wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> *)(4 * v18);
    if ( 4 * v18 )
    {
      *data = v14;
      ++v14->m_refCount;
LABEL_12:
      if ( v11 )
        wil::details::ReleaseMutex(v11);
      if ( m_ptr )
        wil::details::CloseHandle(m_ptr);
      return 0;
    }
    v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
            name,
            &mutex,
            data);
    v16 = v15;
    if ( v15 >= 0 )
    {
      m_ptr = mutex.m_ptr;
      goto LABEL_12;
    }
    wil::details::in1diag3::Return_Hr(retaddr, 0x137u, "wil", v15);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&lock);
    if ( mutex.m_ptr )
      wil::details::CloseHandle(mutex.m_ptr);
    return v16;
  }
}

```

## disassembly

```asm
0x180001fa4  mov     [rsp-8+arg_10], rbx
0x180001fa9  mov     [rsp-8+arg_18], rsi
0x180001fae  push    rbp
0x180001faf  push    rdi
0x180001fb0  push    r14
0x180001fb2  lea     rbp, [rsp-170h]
0x180001fba  sub     rsp, 270h
0x180001fc1  mov     rax, cs:__security_cookie
0x180001fc8  xor     rax, rsp
0x180001fcb  mov     [rbp+180h+var_20], rax
0x180001fd2  mov     r14, data
0x180001fd5  mov     qword ptr [data], 0
0x180001fdc  mov     rbx, staticNameWithVersion
0x180001fdf  call    cs:__imp_GetCurrentProcessId
0x180001fe5  mov     [rsp+280h+var_258], rbx
0x180001fea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180001ff1  mov     r9d, eax
0x180001ff4  mov     [rsp+280h+var_260], 78h ; 'x'
0x180001ffc  mov     edx, 104h; cchDest
0x180002001  lea     staticNameWithVersion, [rsp+280h+name]; pszDest
0x180002006  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000200b  mov     r9d, 1F0001h; dwDesiredAccess
0x180002011  lea     data, [rsp+280h+name]; lpName
0x180002016  xor     r8d, r8d; dwFlags
0x180002019  xor     ecx, ecx; lpMutexAttributes
0x18000201b  call    cs:__imp_CreateMutexExW
0x180002021  mov     [rsp+280h+mutex.m_ptr], rax
0x180002026  mov     rbx, rax
0x180002029  test    rax, rax
0x18000202c  jnz     short loc_18000206F
0x18000202e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180002033  jmp     short loc_180002048
0x180002035  mov     staticNameWithVersion, rdi; mutex
0x180002038  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000203d  test    rbx, rbx
0x180002040  jnz     loc_1800020E7
0x180002046  xor     eax, eax
0x180002048  mov     staticNameWithVersion, [rbp+180h+var_20]
0x18000204f  xor     staticNameWithVersion, rsp; StackCookie
0x180002052  call    __security_check_cookie
0x180002057  lea     r11, [rsp+280h+var_10]
0x18000205f  mov     rbx, [r11+30h]
0x180002063  mov     rsi, [r11+38h]
0x180002067  mov     rsp, r11
0x18000206a  pop     r14
0x18000206c  pop     rdi
0x18000206d  pop     rbp
0x18000206e  retn
0x18000206f  xor     r8d, r8d; bAlertable
0x180002072  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002075  mov     staticNameWithVersion, rbx; hHandle
0x180002078  call    cs:__imp_WaitForSingleObjectEx
0x18000207e  cmp     eax, 102h
0x180002083  jz      loc_180002161
0x180002089  test    eax, 0FFFFFF7Fh
0x18000208e  jnz     loc_1800021A3
0x180002094  mov     rdi, rbx
0x180002097  lea     r8, [rsp+280h+var_248]; name
0x18000209c  mov     [rsp+280h+lock.m_ptr], rdi
0x1800020a1  lea     staticNameWithVersion, [rsp+280h+name]; name
0x1800020a6  mov     [rsp+280h+var_248], 0
0x1800020af  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800020b4  mov     esi, eax
0x1800020b6  test    eax, eax
0x1800020b8  js      short loc_1800020F4
0x1800020ba  mov     rax, [rsp+280h+var_248]
0x1800020bf  lea     staticNameWithVersion, ds:0[rax*4]
0x1800020c7  test    staticNameWithVersion, staticNameWithVersion
0x1800020ca  jz      loc_1800021BC
0x1800020d0  mov     [r14], staticNameWithVersion
0x1800020d3  mov     eax, [staticNameWithVersion]
0x1800020d5  inc     eax
0x1800020d7  mov     [staticNameWithVersion], eax
0x1800020d9  test    rdi, rdi
0x1800020dc  jz      loc_18000203D
0x1800020e2  jmp     loc_180002035
0x1800020e7  mov     staticNameWithVersion, rbx; handle
0x1800020ea  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800020ef  jmp     loc_180002046
0x1800020f4  mov     staticNameWithVersion, [rbp+188h]; callerReturnAddress
0x1800020fb  lea     r8, fileName; "wil"
0x180002102  mov     r9d, esi; hr
0x180002105  mov     edx, 66h ; 'f'; lineNumber
0x18000210a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000210f  mov     staticNameWithVersion, [rbp+188h]; callerReturnAddress
0x180002116  lea     r8, fileName; "wil"
0x18000211d  mov     r9d, esi; hr
0x180002120  mov     edx, 6Fh ; 'o'; lineNumber
0x180002125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000212a  mov     staticNameWithVersion, [rbp+188h]; callerReturnAddress
0x180002131  lea     r8, fileName; "wil"
0x180002138  mov     r9d, esi; hr
0x18000213b  mov     edx, 12Eh; lineNumber
0x180002140  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002145  test    rdi, rdi
0x180002148  jz      short loc_180002152
0x18000214a  mov     staticNameWithVersion, rdi; mutex
0x18000214d  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180002152  mov     staticNameWithVersion, rbx; handle
0x180002155  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000215a  mov     eax, esi
0x18000215c  jmp     loc_180002048
0x180002161  xor     edi, edi
0x180002163  jmp     loc_180002097
0x180002168  mov     staticNameWithVersion, [rbp+188h]; callerReturnAddress
0x18000216f  lea     r8, fileName; "wil"
0x180002176  mov     r9d, ebx; hr
0x180002179  mov     edx, 137h; lineNumber
0x18000217e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002183  lea     staticNameWithVersion, [rsp+280h+lock]; this
0x180002188  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000218d  mov     staticNameWithVersion, [rsp+280h+mutex.m_ptr]; handle
0x180002192  test    staticNameWithVersion, staticNameWithVersion
0x180002195  jz      short loc_18000219C
0x180002197  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000219c  mov     eax, ebx
0x18000219e  jmp     loc_180002048
0x1800021a3  mov     staticNameWithVersion, [rbp+188h]; callerReturnAddress
0x1800021aa  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800021b1  mov     edx, 0E01h; lineNumber
0x1800021b6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800021bc  mov     r8, r14; data
0x1800021bf  lea     data, [rsp+280h+mutex]; mutex
0x1800021c4  lea     staticNameWithVersion, [rsp+280h+name]; name
0x1800021c9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800021ce  mov     ebx, eax
0x1800021d0  test    eax, eax
0x1800021d2  js      short loc_180002168
0x1800021d4  mov     rbx, [rsp+280h+mutex.m_ptr]
0x1800021d9  jmp     loc_1800020D9
```
