# ConnectedStorage::ActivatingContainer::~ActivatingContainer(void)

- ea: `0x180073d1c`
- end: `0x180073e09`
- name: `??1ActivatingContainer@ConnectedStorage@@QEAA@XZ`
- size: `237`
- prototype: `void __fastcall(ConnectedStorage::ActivatingContainer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180073ea8`

## callees

- `0x1800081f8`
- `0x18000a040`
- `0x180012278`
- `0x18001253c`
- `0x1800125ec`
- `0x18001c090`
- `0x180031244`
- `0x18006cab8`
- `0x1800741f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073d6b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073d6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073d84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073dc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073d84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073dc0`

## pseudocode

```c
void __fastcall ConnectedStorage::ActivatingContainer::~ActivatingContainer(
        ConnectedStorage::ActivatingContainer *this)
{
  *(_QWORD *)this = &ConnectedStorage::ActivatingContainer::`vftable'{for `ConnectedStorage::ISyncCancelProgress'};
  *((_QWORD *)this + 1) = &ConnectedStorage::ActivatingContainer::`vftable'{for `ConnectedStorage::ISyncRetry'};
  *((_QWORD *)this + 2) = &ConnectedStorage::ActivatingContainer::`vftable'{for `ConnectedStorage::ISyncConflictResolution'};
  ConnectedStorage::ActivatingContainer::CancelImpl(this, 1);
  std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>((char *)this + 624);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 616);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 14);
  std::wstring::_Tidy_deallocate((char *)this + 512);
  WindowsDeleteString(*((HSTRING *)this + 63));
  *((_QWORD *)this + 63) = 0;
  WindowsDeleteString(*((HSTRING *)this + 62));
  *((_QWORD *)this + 62) = 0;
  ConnectedStorage::UiProvider::~UiProvider((ConnectedStorage::ActivatingContainer *)((char *)this + 288));
  WindowsDeleteString(*((HSTRING *)this + 35));
  *((_QWORD *)this + 35) = 0;
  ConnectedStorage::CallerInfo::~CallerInfo((ConnectedStorage::ActivatingContainer *)((char *)this + 216));
  std::_Func_class<void,>::~_Func_class<void,>((char *)this + 152);
  std::wstring::_Tidy_deallocate((char *)this + 112);
  ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)this + 8);
  ConnectedStorage::HasExecuteQueue<ConnectedStorage::ActivatingContext>::~HasExecuteQueue<ConnectedStorage::ActivatingContext>((char *)this + 24);
}

```

## disassembly

```asm
0x180073d1c  push    rbx
0x180073d1e  sub     rsp, 20h
0x180073d22  mov     rbx, rcx
0x180073d25  lea     rax, ??_7ActivatingContainer@ConnectedStorage@@6BISyncCancelProgress@1@@; const ConnectedStorage::ActivatingContainer::`vftable'{for `ConnectedStorage::ISyncCancelProgress'}
0x180073d2c  mov     [rcx], rax
0x180073d2f  lea     rax, ??_7ActivatingContainer@ConnectedStorage@@6BISyncRetry@1@@; const ConnectedStorage::ActivatingContainer::`vftable'{for `ConnectedStorage::ISyncRetry'}
0x180073d36  mov     [rcx+8], rax
0x180073d3a  lea     rax, ??_7ActivatingContainer@ConnectedStorage@@6BISyncConflictResolution@1@@; const ConnectedStorage::ActivatingContainer::`vftable'{for `ConnectedStorage::ISyncConflictResolution'}
0x180073d41  mov     [rcx+10h], rax
0x180073d45  mov     dl, 1; bool
0x180073d47  call    ?CancelImpl@ActivatingContainer@ConnectedStorage@@AEBAX_N@Z; ConnectedStorage::ActivatingContainer::CancelImpl(bool)
0x180073d4c  lea     rcx, [rbx+270h]
0x180073d53  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x180073d58  lea     rcx, [rbx+268h]
0x180073d5f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180073d64  lea     rcx, [rbx+230h]; lpCriticalSection
0x180073d6b  call    cs:__imp_DeleteCriticalSection
0x180073d71  lea     rcx, [rbx+200h]
0x180073d78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073d7d  mov     rcx, [rbx+1F8h]; string
0x180073d84  call    cs:__imp_WindowsDeleteString
0x180073d8a  mov     qword ptr [rbx+1F8h], 0
0x180073d95  mov     rcx, [rbx+1F0h]; string
0x180073d9c  call    cs:__imp_WindowsDeleteString
0x180073da2  mov     qword ptr [rbx+1F0h], 0
0x180073dad  lea     rcx, [rbx+120h]; this
0x180073db4  call    ??1UiProvider@ConnectedStorage@@QEAA@XZ; ConnectedStorage::UiProvider::~UiProvider(void)
0x180073db9  mov     rcx, [rbx+118h]; string
0x180073dc0  call    cs:__imp_WindowsDeleteString
0x180073dc6  mov     qword ptr [rbx+118h], 0
0x180073dd1  lea     rcx, [rbx+0D8h]; this
0x180073dd8  call    ??1CallerInfo@ConnectedStorage@@QEAA@XZ; ConnectedStorage::CallerInfo::~CallerInfo(void)
0x180073ddd  lea     rcx, [rbx+98h]
0x180073de4  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180073de9  lea     rcx, [rbx+70h]
0x180073ded  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073df2  lea     rcx, [rbx+40h]; this
0x180073df6  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180073dfb  lea     rcx, [rbx+18h]
0x180073dff  add     rsp, 20h
0x180073e03  pop     rbx
0x180073e04  jmp     ??1?$HasExecuteQueue@VActivatingContext@ConnectedStorage@@@ConnectedStorage@@QEAA@XZ; ConnectedStorage::HasExecuteQueue<ConnectedStorage::ActivatingContext>::~HasExecuteQueue<ConnectedStorage::ActivatingContext>(void)
```
