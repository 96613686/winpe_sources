# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync$_ResumeCoro$1_::_1_::catch$32

- ea: `0x18001fa07`
- end: `0x18001fab6`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync$_ResumeCoro$1_::_1_::catch$32`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800017d0`
- `0x180001cc0`
- `0x1800040d0`
- `0x180009ca0`
- `0x180012070`
- `0x180012170`
- `0x1800121a0`
- `0x180012700`
- `0x180019c0c`
- `0x18001fa07`

## string_xrefs

- `0x18001fa70`: `An unknown error occurred during model caching.`

## pseudocode

```c
void __fastcall __noreturn winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync__ResumeCoro_1_::_1_::catch_32(
        __int64 a1,
        __int64 a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // rbx
  const wchar_t *v5; // rax
  const wchar_t **v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int *v9; // rax

  v3 = TraceLogger::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0, v3) )
  {
    v4 = *(_QWORD *)(a2 + 56);
    v5 = winrt::hstring::c_str((winrt::hstring *)(v4 + 208));
    v6 = (const wchar_t **)_tlgWrapSz<wchar_t>::_tlgWrapSz<wchar_t>(v4 + 128, v5);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v7,
      (unsigned __int8 *)&dword_1800276A4,
      v7,
      v8,
      v6);
  }
  else
  {
    v4 = *(_QWORD *)(a2 + 56);
  }
  winrt::param::hstring::hstring(
    (winrt::param::hstring *)(v4 + 136),
    L"An unknown error occurred during model caching.");
  v9 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(v4 + 168), -2147467259);
  winrt::hresult_error::hresult_error(a2 + 152, *v9, v4 + 136);
  throw (winrt::hresult_error *)(a2 + 152);
}

```

## disassembly

```asm
0x18001fa07  mov     [rsp+arg_8], rdx
0x18001fa0c  push    rbx
0x18001fa0d  push    rbp
0x18001fa0e  sub     rsp, 38h
0x18001fa12  mov     rbp, rdx
0x18001fa15  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18001fa1a  mov     r8, rax
0x18001fa1d  cmp     dword ptr [rax], 5
0x18001fa20  jbe     short loc_18001FA65
0x18001fa22  xor     edx, edx
0x18001fa24  mov     rcx, rax
0x18001fa27  call    _tlgKeywordOn
0x18001fa2c  test    al, al
0x18001fa2e  jz      short loc_18001FA65
0x18001fa30  mov     rbx, [rbp+38h]
0x18001fa34  lea     rcx, [rbx+0D0h]; this
0x18001fa3b  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18001fa40  mov     rdx, rax
0x18001fa43  lea     rcx, [rbx+80h]
0x18001fa4a  call    ??0?$_tlgWrapSz@_W@@QEAA@PEB_W@Z; _tlgWrapSz<wchar_t>::_tlgWrapSz<wchar_t>(wchar_t const *)
0x18001fa4f  mov     [rsp+48h+var_28], rax
0x18001fa54  lea     rdx, dword_1800276A4
0x18001fa5b  mov     rcx, r8
0x18001fa5e  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18001fa63  jmp     short loc_18001FA69
0x18001fa65  mov     rbx, [rbp+38h]
0x18001fa69  lea     rcx, [rbx+88h]; this
0x18001fa70  lea     rdx, aAnUnknownError; "An unknown error occurred during model "...
0x18001fa77  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18001fa7c  lea     rcx, [rbx+0A8h]; this
0x18001fa83  mov     edx, 80004005h; int
0x18001fa88  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18001fa8d  lea     r8, [rbx+88h]
0x18001fa94  mov     edx, [rax]
0x18001fa96  lea     rcx, [rbp+98h]
0x18001fa9d  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &)
0x18001faa2  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18001faa9  lea     rcx, [rbp+98h]; pExceptionObject
0x18001fab0  call    _CxxThrowException
```
