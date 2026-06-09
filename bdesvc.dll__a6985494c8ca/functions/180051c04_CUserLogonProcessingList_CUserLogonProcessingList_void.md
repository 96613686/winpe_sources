# CUserLogonProcessingList::~CUserLogonProcessingList(void)

- ea: `0x180051c04`
- end: `0x180051c57`
- name: `??1CUserLogonProcessingList@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(CUserLogonProcessingList *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180051f64`

## callees

- `0x18000dc4c`
- `0x18001d09c`
- `0x1800518a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051c2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051c2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051c4b`

## pseudocode

```c
void __fastcall CUserLogonProcessingList::~CUserLogonProcessingList(CUserLogonProcessingList *this)
{
  _QWORD *v2; // rcx

  v2 = (_QWORD *)((char *)this + 112);
  *v2 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(v2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<CSessionState>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<CSessionState>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<CSessionState>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<CSessionState>>>,0>>((char *)this + 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180051c04  push    rbx
0x180051c06  sub     rsp, 20h
0x180051c0a  mov     rbx, rcx
0x180051c0d  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180051c14  add     rcx, 70h ; 'p'
0x180051c18  mov     [rcx], rax
0x180051c1b  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x180051c20  lea     rcx, [rbx+68h]
0x180051c24  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051c29  lea     rcx, [rbx+40h]; lpCriticalSection
0x180051c2d  call    cs:__imp_DeleteCriticalSection
0x180051c34  nop     dword ptr [rax+rax+00h]
0x180051c39  lea     rcx, [rbx+30h]
0x180051c3d  call    ??1?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VCSessionState@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<CSessionState>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<CSessionState>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::shared_ptr<CSessionState>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<CSessionState>>>,0>>(void)
0x180051c42  lea     rcx, [rbx+8]
0x180051c46  add     rsp, 20h
0x180051c4a  pop     rbx
0x180051c4b  jmp     cs:__imp_DeleteCriticalSection
```
