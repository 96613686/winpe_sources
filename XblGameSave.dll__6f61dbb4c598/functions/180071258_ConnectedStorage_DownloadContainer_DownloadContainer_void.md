# ConnectedStorage::DownloadContainer::~DownloadContainer(void)

- ea: `0x180071258`
- end: `0x180071348`
- name: `??1DownloadContainer@ConnectedStorage@@QEAA@XZ`
- size: `240`
- prototype: `void __fastcall(ConnectedStorage::DownloadContainer *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180071474`

## callees

- `0x1800081f8`
- `0x180012278`
- `0x1800125ec`
- `0x18001c090`
- `0x180031244`
- `0x18003f4e8`
- `0x18005b020`
- `0x18007114c`
- `0x18007117c`
- `0x180071208`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180071274`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800712e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180071274`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800712e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800712c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071306`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800712c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071306`

## pseudocode

```c
void __fastcall ConnectedStorage::DownloadContainer::~DownloadContainer(ConnectedStorage::DownloadContainer *this)
{
  std::vector<Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>>::~vector<Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>>((char *)this + 624);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
  std::vector<std::shared_ptr<ConnectedStorage::NtmOperation const>>::~vector<std::shared_ptr<ConnectedStorage::NtmOperation const>>((char *)this + 544);
  std::deque<ConnectedStorage::BlobRecord>::~deque<ConnectedStorage::BlobRecord>((char *)this + 496);
  std::_Tree<std::_Tset_traits<ConnectedStorage::BlobRecord,std::less<ConnectedStorage::BlobRecord>,std::allocator<ConnectedStorage::BlobRecord>,0>>::~_Tree<std::_Tset_traits<ConnectedStorage::BlobRecord,std::less<ConnectedStorage::BlobRecord>,std::allocator<ConnectedStorage::BlobRecord>,0>>((char *)this + 480);
  std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>((char *)this + 464);
  std::vector<ConnectedStorage::BlobRecord>::~vector<ConnectedStorage::BlobRecord>((char *)this + 440);
  std::vector<ConnectedStorage::BlobRecord>::~vector<ConnectedStorage::BlobRecord>((char *)this + 416);
  WindowsDeleteString(*((HSTRING *)this + 51));
  *((_QWORD *)this + 51) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 9);
  std::_Func_class<void,>::~_Func_class<void,>((char *)this + 280);
  std::_Func_class<void,>::~_Func_class<void,>((char *)this + 216);
  WindowsDeleteString(*((HSTRING *)this + 20));
  *((_QWORD *)this + 20) = 0;
  ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)this + 14);
  std::wstring::_Tidy_deallocate((char *)this + 80);
  std::wstring::_Tidy_deallocate((char *)this + 48);
  std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>((char *)this + 32);
  ConnectedStorage::HasExecuteQueue<ConnectedStorage::ActivatingContext>::~HasExecuteQueue<ConnectedStorage::ActivatingContext>(this);
}

```

## disassembly

```asm
0x180071258  push    rbx
0x18007125a  sub     rsp, 20h
0x18007125e  mov     rbx, rcx
0x180071261  add     rcx, 270h
0x180071268  call    ??1?$vector@V?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>>::~vector<Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>>(void)
0x18007126d  lea     rcx, [rbx+240h]; lpCriticalSection
0x180071274  call    cs:__imp_DeleteCriticalSection
0x18007127a  lea     rcx, [rbx+220h]
0x180071281  call    ??1?$vector@V?$shared_ptr@$$CBVNtmOperation@ConnectedStorage@@@std@@V?$allocator@V?$shared_ptr@$$CBVNtmOperation@ConnectedStorage@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<ConnectedStorage::NtmOperation const>>::~vector<std::shared_ptr<ConnectedStorage::NtmOperation const>>(void)
0x180071286  lea     rcx, [rbx+1F0h]
0x18007128d  call    ??1?$deque@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::deque<ConnectedStorage::BlobRecord>::~deque<ConnectedStorage::BlobRecord>(void)
0x180071292  lea     rcx, [rbx+1E0h]
0x180071299  call    ??1?$_Tree@V?$_Tset_traits@UBlobRecord@ConnectedStorage@@U?$less@UBlobRecord@ConnectedStorage@@@std@@V?$allocator@UBlobRecord@ConnectedStorage@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ConnectedStorage::BlobRecord,std::less<ConnectedStorage::BlobRecord>,std::allocator<ConnectedStorage::BlobRecord>,0>>::~_Tree<std::_Tset_traits<ConnectedStorage::BlobRecord,std::less<ConnectedStorage::BlobRecord>,std::allocator<ConnectedStorage::BlobRecord>,0>>(void)
0x18007129e  lea     rcx, [rbx+1D0h]
0x1800712a5  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x1800712aa  lea     rcx, [rbx+1B8h]
0x1800712b1  call    ??1?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::BlobRecord>::~vector<ConnectedStorage::BlobRecord>(void)
0x1800712b6  lea     rcx, [rbx+1A0h]
0x1800712bd  call    ??1?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::BlobRecord>::~vector<ConnectedStorage::BlobRecord>(void)
0x1800712c2  mov     rcx, [rbx+198h]; string
0x1800712c9  call    cs:__imp_WindowsDeleteString
0x1800712cf  lea     rcx, [rbx+168h]; lpCriticalSection
0x1800712d6  mov     qword ptr [rbx+198h], 0
0x1800712e1  call    cs:__imp_DeleteCriticalSection
0x1800712e7  lea     rcx, [rbx+118h]
0x1800712ee  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1800712f3  lea     rcx, [rbx+0D8h]
0x1800712fa  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1800712ff  mov     rcx, [rbx+0A0h]; string
0x180071306  call    cs:__imp_WindowsDeleteString
0x18007130c  lea     rcx, [rbx+70h]; this
0x180071310  mov     qword ptr [rbx+0A0h], 0
0x18007131b  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180071320  lea     rcx, [rbx+50h]
0x180071324  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180071329  lea     rcx, [rbx+30h]
0x18007132d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180071332  lea     rcx, [rbx+20h]
0x180071336  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x18007133b  mov     rcx, rbx
0x18007133e  add     rsp, 20h
0x180071342  pop     rbx
0x180071343  jmp     ??1?$HasExecuteQueue@VActivatingContext@ConnectedStorage@@@ConnectedStorage@@QEAA@XZ; ConnectedStorage::HasExecuteQueue<ConnectedStorage::ActivatingContext>::~HasExecuteQueue<ConnectedStorage::ActivatingContext>(void)
```
