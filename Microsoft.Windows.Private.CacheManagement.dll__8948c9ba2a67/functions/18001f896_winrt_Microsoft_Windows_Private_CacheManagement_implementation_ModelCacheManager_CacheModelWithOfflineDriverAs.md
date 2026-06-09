# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync$_ResumeCoro$1_::_1_::catch$30

- ea: `0x18001f896`
- end: `0x18001f91a`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync$_ResumeCoro$1_::_1_::catch$30`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001000`
- `0x180001cc0`
- `0x180003b40`
- `0x180009ca0`
- `0x1800121a0`
- `0x1800121c0`
- `0x180012700`
- `0x180019c0c`
- `0x18001f896`

## pseudocode

```c
void __fastcall __noreturn winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync__ResumeCoro_1_::_1_::catch_30(
        __int64 a1,
        __int64 a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // r8
  const wchar_t *v8; // rax
  __int64 v9; // r8
  const wchar_t **v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9

  v3 = TraceLogger::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v3, 0, v4) )
    {
      v5 = winrt::hresult_error::code(*(_QWORD *)(a2 + 88), *(_QWORD *)(a2 + 56) + 48LL);
      v6 = winrt::hresult::operator int(v5);
      *(_DWORD *)(v7 + 52) = v6;
      v8 = winrt::hstring::c_str((winrt::hstring *)(v7 + 208));
      v10 = (const wchar_t **)_tlgWrapSz<wchar_t>::_tlgWrapSz<wchar_t>(v9 + 56, v8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned __int8 *)word_180027732,
        v11,
        v12,
        v10,
        v11 + 52);
    }
  }
  throw;
}

```

## disassembly

```asm
0x18001f896  mov     [rsp+arg_8], rdx
0x18001f89b  push    rbp
0x18001f89c  sub     rsp, 30h
0x18001f8a0  mov     rbp, rdx
0x18001f8a3  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18001f8a8  mov     r9, rax
0x18001f8ab  cmp     dword ptr [rax], 5
0x18001f8ae  jbe     short loc_18001F910
0x18001f8b0  xor     edx, edx
0x18001f8b2  mov     rcx, rax
0x18001f8b5  call    _tlgKeywordOn
0x18001f8ba  test    al, al
0x18001f8bc  jz      short loc_18001F910
0x18001f8be  mov     r8, [rbp+38h]
0x18001f8c2  lea     rdx, [r8+30h]
0x18001f8c6  mov     rcx, [rbp+58h]
0x18001f8ca  call    ?code@hresult_error@winrt@@QEBA?AUhresult@2@XZ; winrt::hresult_error::code(void)
0x18001f8cf  mov     rcx, rax
0x18001f8d2  call    ??Bhresult@winrt@@QEBAHXZ; winrt::hresult::operator int(void)
0x18001f8d7  mov     [r8+34h], eax
0x18001f8db  lea     rcx, [r8+0D0h]; this
0x18001f8e2  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18001f8e7  mov     rdx, rax
0x18001f8ea  lea     rcx, [r8+38h]
0x18001f8ee  call    ??0?$_tlgWrapSz@_W@@QEAA@PEB_W@Z; _tlgWrapSz<wchar_t>::_tlgWrapSz<wchar_t>(wchar_t const *)
0x18001f8f3  lea     rcx, [r8+34h]
0x18001f8f7  mov     [rsp+38h+var_10], rcx
0x18001f8fc  mov     [rsp+38h+var_18], rax
0x18001f901  lea     rdx, word_180027732
0x18001f908  mov     rcx, r9
0x18001f90b  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001f910  xor     edx, edx; pThrowInfo
0x18001f912  xor     ecx, ecx; pExceptionObject
0x18001f914  call    _CxxThrowException
```
