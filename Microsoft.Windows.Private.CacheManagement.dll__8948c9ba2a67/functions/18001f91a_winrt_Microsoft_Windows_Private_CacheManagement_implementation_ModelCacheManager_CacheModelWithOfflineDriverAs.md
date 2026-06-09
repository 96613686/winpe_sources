# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync$_ResumeCoro$1_::_1_::catch$31

- ea: `0x18001f91a`
- end: `0x18001f9dc`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync$_ResumeCoro$1_::_1_::catch$31`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800017d0`
- `0x180001cc0`
- `0x1800040d0`
- `0x180009ca0`
- `0x1800120d0`
- `0x180012170`
- `0x1800121a0`
- `0x180012700`
- `0x180012aa0`
- `0x180019c0c`
- `0x18001cdf0`
- `0x18001f91a`

## pseudocode

```c
void __fastcall __noreturn winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync__ResumeCoro_1_::_1_::catch_31(
        __int64 a1,
        __int64 a2)
{
  const struct _tlgProvider_t *v3; // rax
  _QWORD *v4; // rbx
  const wchar_t *v5; // rax
  const wchar_t **v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  const struct winrt::hstring *v9; // rax
  unsigned int *v10; // rax

  v3 = TraceLogger::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0, v3) )
  {
    v4 = *(_QWORD **)(a2 + 56);
    v5 = winrt::hstring::c_str((winrt::hstring *)(v4 + 26));
    v6 = (const wchar_t **)_tlgWrapSz<wchar_t>::_tlgWrapSz<wchar_t>(v4 + 8, v5);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v7,
      (unsigned __int8 *)byte_1800276EB,
      v7,
      v8,
      v6);
  }
  else
  {
    v4 = *(_QWORD **)(a2 + 56);
  }
  v4[13] = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 96) + 8LL))(*(_QWORD *)(a2 + 96));
  v9 = (const struct winrt::hstring *)winrt::to_hstring<char const *,0>(v4 + 14, v4 + 13);
  winrt::param::hstring::hstring((winrt::param::hstring *)(v4 + 9), v9);
  v10 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(v4 + 15), -2147467259);
  winrt::hresult_error::hresult_error(a2 + 128, *v10, v4 + 9);
  throw (winrt::hresult_error *)(a2 + 128);
}

```

## disassembly

```asm
0x18001f91a  mov     [rsp+arg_8], rdx
0x18001f91f  push    rbx
0x18001f920  push    rbp
0x18001f921  sub     rsp, 38h
0x18001f925  mov     rbp, rdx
0x18001f928  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18001f92d  mov     r8, rax
0x18001f930  cmp     dword ptr [rax], 5
0x18001f933  jbe     short loc_18001F975
0x18001f935  xor     edx, edx
0x18001f937  mov     rcx, rax
0x18001f93a  call    _tlgKeywordOn
0x18001f93f  test    al, al
0x18001f941  jz      short loc_18001F975
0x18001f943  mov     rbx, [rbp+38h]
0x18001f947  lea     rcx, [rbx+0D0h]; this
0x18001f94e  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18001f953  mov     rdx, rax
0x18001f956  lea     rcx, [rbx+40h]
0x18001f95a  call    ??0?$_tlgWrapSz@_W@@QEAA@PEB_W@Z; _tlgWrapSz<wchar_t>::_tlgWrapSz<wchar_t>(wchar_t const *)
0x18001f95f  mov     [rsp+48h+var_28], rax
0x18001f964  lea     rdx, byte_1800276EB
0x18001f96b  mov     rcx, r8
0x18001f96e  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18001f973  jmp     short loc_18001F979
0x18001f975  mov     rbx, [rbp+38h]
0x18001f979  mov     rcx, [rbp+60h]
0x18001f97d  mov     rax, [rcx]
0x18001f980  mov     rax, [rax+8]
0x18001f984  call    cs:__guard_dispatch_icall_fptr
0x18001f98a  mov     [rbx+68h], rax
0x18001f98e  lea     rdx, [rbx+68h]
0x18001f992  lea     rcx, [rbx+70h]
0x18001f996  call    ??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z; winrt::to_hstring<char const *,0>(char const * const &)
0x18001f99b  nop
0x18001f99c  lea     rcx, [rbx+48h]; this
0x18001f9a0  mov     rdx, rax; struct winrt::hstring *
0x18001f9a3  call    ??0hstring@param@winrt@@QEAA@AEBU02@@Z; winrt::param::hstring::hstring(winrt::hstring const &)
0x18001f9a8  lea     rcx, [rbx+78h]; this
0x18001f9ac  mov     edx, 80004005h; int
0x18001f9b1  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18001f9b6  lea     r8, [rbx+48h]
0x18001f9ba  mov     edx, [rax]
0x18001f9bc  lea     rcx, [rbp+80h]
0x18001f9c3  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &)
0x18001f9c8  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18001f9cf  lea     rcx, [rbp+80h]; pExceptionObject
0x18001f9d6  call    _CxxThrowException
```
