# CMapiSession::~CMapiSession(void)

- ea: `0x1800356c4`
- end: `0x180035739`
- name: `??1CMapiSession@@UEAA@XZ`
- size: `117`
- prototype: `void __fastcall(CMapiSession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180035740`

## callees

- `0x18000ad14`
- `0x18002f6fc`
- `0x1800356c4`
- `0x180035c0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800356eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800356eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180035716`
- `OLEAUT32!__imp_SysFreeString` at `0x180035720`
- `OLEAUT32!__imp_SysFreeString` at `0x180035716`
- `OLEAUT32!__imp_SysFreeString` at `0x180035720`

## pseudocode

```c
void __fastcall CMapiSession::~CMapiSession(CMapiSession *this)
{
  *(_QWORD *)this = &CMapiSession::`vftable';
  if ( *((_QWORD *)this + 3) )
    CMapiSession::Logoff(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 21);
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::RemoveAll((char *)this + 48);
  SysFreeString(*((BSTR *)this + 5));
  SysFreeString(*((BSTR *)this + 4));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 3);
}

```

## disassembly

```asm
0x1800356c4  mov     [rsp+arg_0], rbx
0x1800356c9  push    rdi
0x1800356ca  sub     rsp, 20h
0x1800356ce  mov     rbx, rcx
0x1800356d1  lea     rax, ??_7CMapiSession@@6B@; const CMapiSession::`vftable'
0x1800356d8  mov     [rcx], rax
0x1800356db  cmp     qword ptr [rcx+18h], 0
0x1800356e0  jz      short loc_1800356E7
0x1800356e2  call    ?Logoff@CMapiSession@@QEAAJXZ; CMapiSession::Logoff(void)
0x1800356e7  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800356eb  call    cs:__imp_DeleteCriticalSection
0x1800356f1  lea     rcx, [rbx+0B0h]
0x1800356f8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800356fd  lea     rcx, [rbx+0A8h]
0x180035704  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180035709  lea     rcx, [rbx+30h]
0x18003570d  call    ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiStore@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiStore@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::RemoveAll(void)
0x180035712  mov     rcx, [rbx+28h]; bstrString
0x180035716  call    cs:__imp_SysFreeString
0x18003571c  mov     rcx, [rbx+20h]; bstrString
0x180035720  call    cs:__imp_SysFreeString
0x180035726  lea     rcx, [rbx+18h]
0x18003572a  mov     rbx, [rsp+28h+arg_0]
0x18003572f  add     rsp, 20h
0x180035733  pop     rdi
0x180035734  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
