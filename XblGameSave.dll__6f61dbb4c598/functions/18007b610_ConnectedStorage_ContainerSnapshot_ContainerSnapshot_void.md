# ConnectedStorage::ContainerSnapshot::~ContainerSnapshot(void)

- ea: `0x18007b610`
- end: `0x18007b6a5`
- name: `??1ContainerSnapshot@ConnectedStorage@@UEAA@XZ`
- size: `149`
- prototype: `void __fastcall(ConnectedStorage::ContainerSnapshot *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007b720`

## callees

- `0x180012278`
- `0x1800124b0`
- `0x1800125ec`
- `0x18003f360`
- `0x18005b020`
- `0x18007b7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007b63b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007b63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b65a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b66c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b65a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b66c`

## pseudocode

```c
void __fastcall ConnectedStorage::ContainerSnapshot::~ContainerSnapshot(ConnectedStorage::ContainerSnapshot *this)
{
  *(_QWORD *)this = &ConnectedStorage::ContainerSnapshot::`vftable';
  ConnectedStorage::ContainerSnapshot::CancelUpload(this);
  std::_Tree<std::_Tset_traits<ConnectedStorage::Atom,std::less<ConnectedStorage::Atom>,std::allocator<ConnectedStorage::Atom>,0>>::~_Tree<std::_Tset_traits<ConnectedStorage::Atom,std::less<ConnectedStorage::Atom>,std::allocator<ConnectedStorage::Atom>,0>>((char *)this + 200);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>((char *)this + 136);
  std::vector<ConnectedStorage::BlobRecord>::~vector<ConnectedStorage::BlobRecord>((char *)this + 112);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)this + 5);
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>((char *)this + 24);
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>((char *)this + 8);
  *(_QWORD *)this = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>::`vftable';
}

```

## disassembly

```asm
0x18007b610  push    rbx
0x18007b612  sub     rsp, 20h
0x18007b616  mov     rbx, rcx
0x18007b619  lea     rax, ??_7ContainerSnapshot@ConnectedStorage@@6B@; const ConnectedStorage::ContainerSnapshot::`vftable'
0x18007b620  mov     [rcx], rax
0x18007b623  call    ?CancelUpload@ContainerSnapshot@ConnectedStorage@@UEBAXXZ; ConnectedStorage::ContainerSnapshot::CancelUpload(void)
0x18007b628  lea     rcx, [rbx+0C8h]
0x18007b62f  call    ??1?$_Tree@V?$_Tset_traits@VAtom@ConnectedStorage@@U?$less@VAtom@ConnectedStorage@@@std@@V?$allocator@VAtom@ConnectedStorage@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ConnectedStorage::Atom,std::less<ConnectedStorage::Atom>,std::allocator<ConnectedStorage::Atom>,0>>::~_Tree<std::_Tset_traits<ConnectedStorage::Atom,std::less<ConnectedStorage::Atom>,std::allocator<ConnectedStorage::Atom>,0>>(void)
0x18007b634  lea     rcx, [rbx+98h]; lpCriticalSection
0x18007b63b  call    cs:__imp_DeleteCriticalSection
0x18007b641  lea     rcx, [rbx+88h]
0x18007b648  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x18007b64d  lea     rcx, [rbx+70h]
0x18007b651  call    ??1?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::BlobRecord>::~vector<ConnectedStorage::BlobRecord>(void)
0x18007b656  mov     rcx, [rbx+60h]; string
0x18007b65a  call    cs:__imp_WindowsDeleteString
0x18007b660  mov     qword ptr [rbx+60h], 0
0x18007b668  mov     rcx, [rbx+58h]; string
0x18007b66c  call    cs:__imp_WindowsDeleteString
0x18007b672  mov     qword ptr [rbx+58h], 0
0x18007b67a  lea     rcx, [rbx+28h]; this
0x18007b67e  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x18007b683  lea     rcx, [rbx+18h]
0x18007b687  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x18007b68c  lea     rcx, [rbx+8]
0x18007b690  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x18007b695  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>::`vftable'
0x18007b69c  mov     [rbx], rax
0x18007b69f  add     rsp, 20h
0x18007b6a3  pop     rbx
0x18007b6a4  retn
```
