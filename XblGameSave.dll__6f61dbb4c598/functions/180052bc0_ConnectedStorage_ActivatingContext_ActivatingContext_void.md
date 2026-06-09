# ConnectedStorage::ActivatingContext::~ActivatingContext(void)

- ea: `0x180052bc0`
- end: `0x180052cb5`
- name: `??1ActivatingContext@ConnectedStorage@@QEAA@XZ`
- size: `245`
- prototype: `void __fastcall(ConnectedStorage::ActivatingContext *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800530b4`

## callees

- `0x18000a040`
- `0x18000c218`
- `0x180012278`
- `0x1800124b0`
- `0x18001253c`
- `0x1800125ec`
- `0x18001c090`
- `0x180031244`
- `0x180031360`
- `0x180052b44`
- `0x180054094`
- `0x18006cab8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052c26`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052c26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052c63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052c63`

## pseudocode

```c
void __fastcall ConnectedStorage::ActivatingContext::~ActivatingContext(ConnectedStorage::ActivatingContext *this)
{
  *(_QWORD *)this = &ConnectedStorage::ActivatingContext::`vftable'{for `ConnectedStorage::ISyncCancelProgress'};
  *((_QWORD *)this + 1) = &ConnectedStorage::ActivatingContext::`vftable'{for `ConnectedStorage::ISyncRetry'};
  *((_QWORD *)this + 2) = &ConnectedStorage::ActivatingContext::`vftable'{for `ConnectedStorage::ISyncLockContention'};
  *((_QWORD *)this + 3) = &ConnectedStorage::ActivatingContext::`vftable'{for `ConnectedStorage::ISyncConflictResolution'};
  ConnectedStorage::ActivatingContext::CancelImpl(this, 1);
  std::list<std::function<void (ConnectedStorage::Context const *,bool,long)>>::~list<std::function<void (ConnectedStorage::Context const *,bool,long)>>((char *)this + 704);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 688);
  std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>((char *)this + 664);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 15);
  std::unique_ptr<ConnectedStorage::ContainerIndex>::~unique_ptr<ConnectedStorage::ContainerIndex>((char *)this + 592);
  std::wstring::_Tidy_deallocate((char *)this + 560);
  std::wstring::_Tidy_deallocate((char *)this + 528);
  ConnectedStorage::UiProvider::~UiProvider((ConnectedStorage::ActivatingContext *)((char *)this + 312));
  WindowsDeleteString(*((HSTRING *)this + 37));
  *((_QWORD *)this + 37) = 0;
  std::function<long (void)>::~function<long (void)>((char *)this + 224);
  ConnectedStorage::CallerInfo::~CallerInfo((HSTRING *)this + 20);
  ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)this + 14);
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>((char *)this + 88);
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>((char *)this + 64);
  ConnectedStorage::HasExecuteQueue<ConnectedStorage::ActivatingContext>::~HasExecuteQueue<ConnectedStorage::ActivatingContext>((char *)this + 32);
}

```

## disassembly

```asm
0x180052bc0  push    rbx
0x180052bc2  sub     rsp, 20h
0x180052bc6  mov     rbx, rcx
0x180052bc9  lea     rax, ??_7ActivatingContext@ConnectedStorage@@6BISyncCancelProgress@1@@; const ConnectedStorage::ActivatingContext::`vftable'{for `ConnectedStorage::ISyncCancelProgress'}
0x180052bd0  mov     [rcx], rax
0x180052bd3  lea     rax, ??_7ActivatingContext@ConnectedStorage@@6BISyncRetry@1@@; const ConnectedStorage::ActivatingContext::`vftable'{for `ConnectedStorage::ISyncRetry'}
0x180052bda  mov     [rcx+8], rax
0x180052bde  lea     rax, ??_7ActivatingContext@ConnectedStorage@@6BISyncLockContention@1@@; const ConnectedStorage::ActivatingContext::`vftable'{for `ConnectedStorage::ISyncLockContention'}
0x180052be5  mov     [rcx+10h], rax
0x180052be9  lea     rax, ??_7ActivatingContext@ConnectedStorage@@6BISyncConflictResolution@1@@; const ConnectedStorage::ActivatingContext::`vftable'{for `ConnectedStorage::ISyncConflictResolution'}
0x180052bf0  mov     [rcx+18h], rax
0x180052bf4  mov     dl, 1; bool
0x180052bf6  call    ?CancelImpl@ActivatingContext@ConnectedStorage@@AEBAX_N@Z; ConnectedStorage::ActivatingContext::CancelImpl(bool)
0x180052bfb  lea     rcx, [rbx+2C0h]
0x180052c02  call    ??1?$list@V?$function@$$A6AXPEBVContext@ConnectedStorage@@_NJ@Z@std@@V?$allocator@V?$function@$$A6AXPEBVContext@ConnectedStorage@@_NJ@Z@std@@@2@@std@@QEAA@XZ; std::list<std::function<void (ConnectedStorage::Context const *,bool,long)>>::~list<std::function<void (ConnectedStorage::Context const *,bool,long)>>(void)
0x180052c07  lea     rcx, [rbx+2B0h]
0x180052c0e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052c13  lea     rcx, [rbx+298h]
0x180052c1a  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x180052c1f  lea     rcx, [rbx+258h]; lpCriticalSection
0x180052c26  call    cs:__imp_DeleteCriticalSection
0x180052c2c  lea     rcx, [rbx+250h]
0x180052c33  call    ??1?$unique_ptr@VContainerIndex@ConnectedStorage@@U?$default_delete@VContainerIndex@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConnectedStorage::ContainerIndex>::~unique_ptr<ConnectedStorage::ContainerIndex>(void)
0x180052c38  lea     rcx, [rbx+230h]
0x180052c3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052c44  lea     rcx, [rbx+210h]
0x180052c4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052c50  lea     rcx, [rbx+138h]; this
0x180052c57  call    ??1UiProvider@ConnectedStorage@@QEAA@XZ; ConnectedStorage::UiProvider::~UiProvider(void)
0x180052c5c  mov     rcx, [rbx+128h]; string
0x180052c63  call    cs:__imp_WindowsDeleteString
0x180052c69  mov     qword ptr [rbx+128h], 0
0x180052c74  lea     rcx, [rbx+0E0h]
0x180052c7b  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180052c80  lea     rcx, [rbx+0A0h]; this
0x180052c87  call    ??1CallerInfo@ConnectedStorage@@QEAA@XZ; ConnectedStorage::CallerInfo::~CallerInfo(void)
0x180052c8c  lea     rcx, [rbx+70h]; this
0x180052c90  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180052c95  lea     rcx, [rbx+58h]
0x180052c99  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x180052c9e  lea     rcx, [rbx+40h]
0x180052ca2  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x180052ca7  lea     rcx, [rbx+20h]
0x180052cab  add     rsp, 20h
0x180052caf  pop     rbx
0x180052cb0  jmp     ??1?$HasExecuteQueue@VActivatingContext@ConnectedStorage@@@ConnectedStorage@@QEAA@XZ; ConnectedStorage::HasExecuteQueue<ConnectedStorage::ActivatingContext>::~HasExecuteQueue<ConnectedStorage::ActivatingContext>(void)
```
