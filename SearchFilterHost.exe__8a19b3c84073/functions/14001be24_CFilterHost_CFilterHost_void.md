# CFilterHost::~CFilterHost(void)

- ea: `0x14001be24`
- end: `0x14001be98`
- name: `??1CFilterHost@@QEAA@XZ`
- size: `116`
- prototype: `void __fastcall(CFilterHost *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001b740`

## callees

- `0x140018260`
- `0x14001b904`
- `0x14001ba7c`
- `0x14001bdc0`
- `0x14001be24`
- `0x140021a14`
- `0x140025108`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001be72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001be72`

## pseudocode

```c
void __fastcall CFilterHost::~CFilterHost(CFilterHost *this)
{
  std::_Ref_count_base *v2; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 30);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  if ( *((_QWORD *)this + 28) )
    winrt::com_ptr<ITextFilter>::unconditional_release_ref();
  if ( *((_QWORD *)this + 27) )
    winrt::com_ptr<ITextFilter>::unconditional_release_ref();
  std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>((__int64)this + 152);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  TComPointer<CBufferedProtocolStream>::~TComPointer<CBufferedProtocolStream>((CBufferedProtocolStream **)this + 12);
  Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease((char *)this + 88);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CFilterHost *)((char *)this + 32));
}

```

## disassembly

```asm
0x14001be24  push    rbx
0x14001be26  sub     rsp, 20h
0x14001be2a  mov     rbx, rcx
0x14001be2d  mov     rcx, [rcx+0F0h]; this
0x14001be34  test    rcx, rcx
0x14001be37  jz      short loc_14001BE3E
0x14001be39  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001be3e  lea     rcx, [rbx+0E0h]
0x14001be45  cmp     qword ptr [rcx], 0
0x14001be49  jz      short loc_14001BE50
0x14001be4b  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x14001be50  lea     rcx, [rbx+0D8h]
0x14001be57  cmp     qword ptr [rcx], 0
0x14001be5b  jz      short loc_14001BE62
0x14001be5d  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x14001be62  lea     rcx, [rbx+98h]
0x14001be69  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KV?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x14001be6e  lea     rcx, [rbx+70h]; lpCriticalSection
0x14001be72  call    cs:__imp_DeleteCriticalSection
0x14001be78  lea     rcx, [rbx+60h]
0x14001be7c  call    ??1?$TComPointer@VCBufferedProtocolStream@@@@QEAA@XZ; TComPointer<CBufferedProtocolStream>::~TComPointer<CBufferedProtocolStream>(void)
0x14001be81  lea     rcx, [rbx+58h]
0x14001be85  call    ?InternalRelease@?$ComPtr@UIFilterHostManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease(void)
0x14001be8a  lea     rcx, [rbx+20h]; this
0x14001be8e  add     rsp, 20h
0x14001be92  pop     rbx
0x14001be93  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
