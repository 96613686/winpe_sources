# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800300c8`
- end: `0x18003026f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `423`
- prototype: `HRESULT __fastcall(const char *staticNameWithVersion, wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> **data)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800311d0`

## callees

- `0x180001708`
- `0x180001f20`
- `0x1800026d0`
- `0x180003048`
- `0x18000308c`
- `0x18001b330`
- `0x180020904`
- `0x180021efc`
- `0x1800300c8`
- `0x18003187c`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800300fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800300fd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180030142`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180030142`

## pseudocode

```c
HRESULT __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        const char *staticNameWithVersion,
        wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> **data)
{
  DWORD CurrentProcessId; // eax
  HANDLE v5; // rax
  unsigned int *v6; // r8
  unsigned int v7; // r9d
  void *m_ptr; // rbx
  HRESULT v10; // eax
  HRESULT v11; // edi
  _DWORD *v12; // rcx
  HRESULT v13; // eax
  HRESULT v14; // ebx
  wil::unique_any_t<wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > mutex; // [rsp+30h] [rbp-D0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::ReleaseMutex,wistd::integral_constant<unsigned __int64,2>,void *,void *,0,std::nullptr_t> > > lock; // [rsp+38h] [rbp-C8h] BYREF
  void *pointer; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t name[264]; // [rsp+50h] [rbp-B0h] BYREF
  void *retaddr; // [rsp+288h] [rbp+188h]

  *data = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 304, staticNameWithVersion);
  mutex.m_ptr = 0;
  v5 = CreateMutexExW(0, name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &mutex,
    v5);
  m_ptr = mutex.m_ptr;
  if ( !mutex.m_ptr )
    return wil::details::GetLastErrorFailHr();
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &mutex,
    &lock,
    v6,
    v7);
  pointer = 0;
  v10 = wil::details_abi::SemaphoreValue::TryGetPointer(name, &pointer);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x12Eu, "wil", v10);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&lock);
    wil::details::CloseHandle(m_ptr);
    return v11;
  }
  v12 = pointer;
  if ( pointer )
  {
    *data = (wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> *)pointer;
    ++*v12;
LABEL_12:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&lock);
    if ( m_ptr )
      wil::details::CloseHandle(m_ptr);
    return 0;
  }
  v13 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(
          name,
          &mutex,
          data);
  v14 = v13;
  if ( v13 >= 0 )
  {
    m_ptr = mutex.m_ptr;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0x137u, "wil", v13);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&lock);
  if ( mutex.m_ptr )
    wil::details::CloseHandle(mutex.m_ptr);
  return v14;
}

```

## disassembly

```asm
0x1800300c8  mov     [rsp-8+arg_10], rbx
0x1800300cd  push    rbp
0x1800300ce  push    rsi
0x1800300cf  push    rdi
0x1800300d0  lea     rbp, [rsp-170h]
0x1800300d8  sub     rsp, 270h
0x1800300df  mov     rax, cs:__security_cookie
0x1800300e6  xor     rax, rsp
0x1800300e9  mov     [rbp+180h+var_20], rax
0x1800300f0  mov     rsi, data
0x1800300f3  mov     qword ptr [data], 0
0x1800300fa  mov     rbx, staticNameWithVersion
0x1800300fd  call    cs:__imp_GetCurrentProcessId
0x180030103  mov     [rsp+280h+var_258], rbx
0x180030108  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003010f  mov     r9d, eax
0x180030112  mov     [rsp+280h+bAlertable], 130h; bAlertable
0x18003011a  mov     edx, 104h; cchDest
0x18003011f  lea     staticNameWithVersion, [rsp+280h+name]; pszDest
0x180030124  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030129  mov     r9d, 1F0001h; dwDesiredAccess
0x18003012f  mov     [rsp+280h+mutex.m_ptr], 0
0x180030138  xor     r8d, r8d; dwFlags
0x18003013b  lea     data, [rsp+280h+name]; lpName
0x180030140  xor     ecx, ecx; lpMutexAttributes
0x180030142  call    cs:__imp_CreateMutexExW
0x180030148  mov     data, rax; ptr
0x18003014b  lea     staticNameWithVersion, [rsp+280h+mutex]; this
0x180030150  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180030155  mov     rbx, [rsp+280h+mutex.m_ptr]
0x18003015a  test    rbx, rbx
0x18003015d  jnz     short loc_180030169
0x18003015f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180030164  jmp     loc_18003024D
0x180030169  lea     data, [rsp+280h+lock]; result
0x18003016e  lea     staticNameWithVersion, [rsp+280h+mutex]; this
0x180030173  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180030178  lea     data, [rsp+280h+pointer]; pointer
0x18003017d  mov     [rsp+280h+pointer], 0
0x180030186  lea     staticNameWithVersion, [rsp+280h+name]; name
0x18003018b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180030190  mov     edi, eax
0x180030192  test    eax, eax
0x180030194  jns     short loc_1800301CA
0x180030196  mov     staticNameWithVersion, [rbp+188h]; callerReturnAddress
0x18003019d  lea     r8, fileName; "wil"
0x1800301a4  mov     r9d, eax; hr
0x1800301a7  mov     edx, 12Eh; lineNumber
0x1800301ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800301b1  lea     staticNameWithVersion, [rsp+280h+lock]; this
0x1800301b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800301bb  mov     staticNameWithVersion, rbx; handle
0x1800301be  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800301c3  mov     eax, edi
0x1800301c5  jmp     loc_18003024D
0x1800301ca  mov     staticNameWithVersion, [rsp+280h+pointer]
0x1800301cf  test    staticNameWithVersion, staticNameWithVersion
0x1800301d2  jz      short loc_1800301DF
0x1800301d4  mov     [rsi], staticNameWithVersion
0x1800301d7  mov     eax, [staticNameWithVersion]
0x1800301d9  inc     eax
0x1800301db  mov     [staticNameWithVersion], eax
0x1800301dd  jmp     short loc_180030234
0x1800301df  mov     r8, rsi; data
0x1800301e2  lea     data, [rsp+280h+mutex]; mutex
0x1800301e7  lea     staticNameWithVersion, [rsp+280h+name]; name
0x1800301ec  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800301f1  mov     ebx, eax
0x1800301f3  test    eax, eax
0x1800301f5  jns     short loc_18003022F
0x1800301f7  mov     staticNameWithVersion, [rbp+188h]; callerReturnAddress
0x1800301fe  lea     r8, fileName; "wil"
0x180030205  mov     r9d, eax; hr
0x180030208  mov     edx, 137h; lineNumber
0x18003020d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030212  lea     staticNameWithVersion, [rsp+280h+lock]; this
0x180030217  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003021c  mov     staticNameWithVersion, [rsp+280h+mutex.m_ptr]; handle
0x180030221  test    staticNameWithVersion, staticNameWithVersion
0x180030224  jz      short loc_18003022B
0x180030226  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003022b  mov     eax, ebx
0x18003022d  jmp     short loc_18003024D
0x18003022f  mov     rbx, [rsp+280h+mutex.m_ptr]
0x180030234  lea     staticNameWithVersion, [rsp+280h+lock]; this
0x180030239  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003023e  test    rbx, rbx
0x180030241  jz      short loc_18003024B
0x180030243  mov     staticNameWithVersion, rbx; handle
0x180030246  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003024b  xor     eax, eax
0x18003024d  mov     staticNameWithVersion, [rbp+180h+var_20]
0x180030254  xor     staticNameWithVersion, rsp; StackCookie
0x180030257  call    __security_check_cookie
0x18003025c  mov     rbx, [rsp+280h+arg_10]
0x180030264  add     rsp, 270h
0x18003026b  pop     rdi
0x18003026c  pop     rsi
0x18003026d  pop     rbp
0x18003026e  retn
```
