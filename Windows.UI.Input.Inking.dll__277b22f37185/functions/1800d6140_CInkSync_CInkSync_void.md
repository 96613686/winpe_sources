# CInkSync::~CInkSync(void)

- ea: `0x1800d6140`
- end: `0x1800d625a`
- name: `??1CInkSync@@QEAA@XZ`
- size: `282`
- prototype: `void __fastcall(CInkSync *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800928d4`
- `0x180093c20`
- `0x1800f9f6b`

## callees

- `0x180002f6c`
- `0x1800101bc`
- `0x180093bc0`
- `0x1800af650`
- `0x1800d60f4`
- `0x1800d6140`
- `0x1800d63bc`
- `0x1800dac84`
- `0x1800de83c`
- `0x1800e6d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d6183`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d6183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d6176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d6176`

## pseudocode

```c
void __fastcall CInkSync::~CInkSync(CInkSync *this, unsigned int a2)
{
  CDryInkPresenter *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  const wchar_t *v5; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &CInkSync::`vftable'{for `DirectInkPrivate::IWetInkSink'};
  *((_QWORD *)this + 1) = &CInkSync::`vftable'{for `DirectInkPrivate::IInkSynchronizerInternal'};
  v3 = (CDryInkPresenter *)*((_QWORD *)this + 73);
  if ( v3 )
    CDryInkPresenter::`scalar deleting destructor'(v3, a2);
  WindowsDeleteString(*((HSTRING *)this + 99));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 21);
  if ( (unsigned int)dword_18015B128 > 4 )
  {
    v5 = L"CInkSync";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_18015B128,
      (unsigned int)&byte_18014368F,
      0,
      0,
      (__int64)&v5);
  }
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 123);
  if ( v4 )
    std::_Ref_count_base::_Decwref(v4);
  CRenderLatencyTracer::~CRenderLatencyTracer((CInkSync *)((char *)this + 904));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 896);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 824);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 816);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 808);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 800);
  CCommitHelper::~CCommitHelper((CInkSync *)((char *)this + 680));
  CCommitHelper::~CCommitHelper((CInkSync *)((char *)this + 592));
  CInkContentUpdateHelper::~CInkContentUpdateHelper((CInkSync *)((char *)this + 536));
  CDirectInkRenderManager::~CDirectInkRenderManager((CInkSync *)((char *)this + 336));
  CInkTree::~CInkTree((CInkSync *)((char *)this + 40));
}

```

## disassembly

```asm
0x1800d6140  push    rbx
0x1800d6142  sub     rsp, 30h
0x1800d6146  lea     rax, ??_7CInkSync@@6BIWetInkSink@DirectInkPrivate@@@; const CInkSync::`vftable'{for `DirectInkPrivate::IWetInkSink'}
0x1800d614d  mov     rbx, rcx
0x1800d6150  mov     [rcx], rax
0x1800d6153  lea     rax, ??_7CInkSync@@6BIInkSynchronizerInternal@DirectInkPrivate@@@; const CInkSync::`vftable'{for `DirectInkPrivate::IInkSynchronizerInternal'}
0x1800d615a  mov     [rcx+8], rax
0x1800d615e  mov     rcx, [rcx+248h]; this
0x1800d6165  test    rcx, rcx
0x1800d6168  jz      short loc_1800D616F
0x1800d616a  call    ??_GCDryInkPresenter@@QEAAPEAXI@Z; CDryInkPresenter::`scalar deleting destructor'(uint)
0x1800d616f  mov     rcx, [rbx+318h]; string
0x1800d6176  call    cs:__imp_WindowsDeleteString
0x1800d617c  lea     rcx, [rbx+348h]; lpCriticalSection
0x1800d6183  call    cs:__imp_DeleteCriticalSection
0x1800d6189  mov     eax, cs:dword_18015B128
0x1800d618f  cmp     eax, 4
0x1800d6192  jbe     short loc_1800D61C3
0x1800d6194  lea     rax, aCinksync; "CInkSync"
0x1800d619b  xor     r9d, r9d
0x1800d619e  mov     [rsp+38h+arg_0], rax
0x1800d61a3  lea     rdx, byte_18014368F
0x1800d61aa  lea     rax, [rsp+38h+arg_0]
0x1800d61af  xor     r8d, r8d
0x1800d61b2  lea     rcx, dword_18015B128
0x1800d61b9  mov     [rsp+38h+var_18], rax
0x1800d61be  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800d61c3  mov     rcx, [rbx+3D8h]; this
0x1800d61ca  test    rcx, rcx
0x1800d61cd  jz      short loc_1800D61D4
0x1800d61cf  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800d61d4  lea     rcx, [rbx+388h]; this
0x1800d61db  call    ??1CRenderLatencyTracer@@QEAA@XZ; CRenderLatencyTracer::~CRenderLatencyTracer(void)
0x1800d61e0  lea     rcx, [rbx+380h]
0x1800d61e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d61ec  lea     rcx, [rbx+338h]
0x1800d61f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d61f8  lea     rcx, [rbx+330h]
0x1800d61ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d6204  lea     rcx, [rbx+328h]
0x1800d620b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d6210  lea     rcx, [rbx+320h]
0x1800d6217  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d621c  lea     rcx, [rbx+2A8h]; this
0x1800d6223  call    ??1CCommitHelper@@QEAA@XZ; CCommitHelper::~CCommitHelper(void)
0x1800d6228  lea     rcx, [rbx+250h]; this
0x1800d622f  call    ??1CCommitHelper@@QEAA@XZ; CCommitHelper::~CCommitHelper(void)
0x1800d6234  lea     rcx, [rbx+218h]; this
0x1800d623b  call    ??1CInkContentUpdateHelper@@QEAA@XZ; CInkContentUpdateHelper::~CInkContentUpdateHelper(void)
0x1800d6240  lea     rcx, [rbx+150h]; this
0x1800d6247  call    ??1CDirectInkRenderManager@@QEAA@XZ; CDirectInkRenderManager::~CDirectInkRenderManager(void)
0x1800d624c  lea     rcx, [rbx+28h]; this
0x1800d6250  add     rsp, 30h
0x1800d6254  pop     rbx
0x1800d6255  jmp     ??1CInkTree@@QEAA@XZ; CInkTree::~CInkTree(void)
```
