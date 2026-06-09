# ConnectedStorage::Context::~Context(void)

- ea: `0x18005b134`
- end: `0x18005b20e`
- name: `??1Context@ConnectedStorage@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(ConnectedStorage::Context *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18005315c`

## callees

- `0x18000cb9c`
- `0x180012278`
- `0x1800124b0`
- `0x18001253c`
- `0x1800125ec`
- `0x18001c090`
- `0x180031244`
- `0x180031360`
- `0x18005afb4`
- `0x180073470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005b195`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005b19e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005b195`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005b19e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b164`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b164`

## pseudocode

```c
void __fastcall ConnectedStorage::Context::~Context(ConnectedStorage::Context *this, __int64 a2, char *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+20h] [rbp-18h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 328);
  *(_QWORD *)this = &ConnectedStorage::Context::`vftable';
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 328),
    a3);
  LeaveCriticalSection(lpCriticalSection[0]);
  std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>((char *)this + 488);
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>((char *)this + 472);
  std::list<std::function<void (std::shared_ptr<ConnectedStorage::ContextOperationToken>,ConnectedStorage::Context *)>>::~list<std::function<void (std::shared_ptr<ConnectedStorage::ContextOperationToken>,ConnectedStorage::Context *)>>((char *)this + 456);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  DeleteCriticalSection(v3);
  std::unique_ptr<ConnectedStorage::ContainerIndex>::~unique_ptr<ConnectedStorage::ContainerIndex>((char *)this + 304);
  ConnectedStorage::Containers::~Containers((ConnectedStorage::Context *)((char *)this + 264));
  std::wstring::_Tidy_deallocate((char *)this + 232);
  std::wstring::_Tidy_deallocate((char *)this + 200);
  ConnectedStorage::CallerInfo::~CallerInfo((HSTRING *)this + 17);
  ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)this + 11);
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>((char *)this + 64);
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>((char *)this + 40);
  ConnectedStorage::HasExecuteQueue<ConnectedStorage::ActivatingContext>::~HasExecuteQueue<ConnectedStorage::ActivatingContext>((char *)this + 8);
}

```

## disassembly

```asm
0x18005b134  mov     [rsp+arg_0], rbx
0x18005b139  push    rdi
0x18005b13a  sub     rsp, 30h
0x18005b13e  lea     rbx, [rcx+148h]
0x18005b145  mov     rdi, rcx
0x18005b148  lea     rax, ??_7Context@ConnectedStorage@@6B@; const ConnectedStorage::Context::`vftable'
0x18005b14f  mov     rdx, rbx; struct ConnectedStorage::Mutex *
0x18005b152  mov     [rcx], rax
0x18005b155  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x18005b15a  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18005b15f  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x18005b164  call    cs:__imp_LeaveCriticalSection
0x18005b16a  lea     rcx, [rdi+1E8h]
0x18005b171  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x18005b176  lea     rcx, [rdi+1D8h]
0x18005b17d  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x18005b182  lea     rcx, [rdi+1C8h]
0x18005b189  call    ??1?$list@V?$function@$$A6AXV?$shared_ptr@VContextOperationToken@ConnectedStorage@@@std@@PEAVContext@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXV?$shared_ptr@VContextOperationToken@ConnectedStorage@@@std@@PEAVContext@ConnectedStorage@@@Z@std@@@2@@std@@QEAA@XZ; std::list<std::function<void (std::shared_ptr<ConnectedStorage::ContextOperationToken>,ConnectedStorage::Context *)>>::~list<std::function<void (std::shared_ptr<ConnectedStorage::ContextOperationToken>,ConnectedStorage::Context *)>>(void)
0x18005b18e  lea     rcx, [rdi+180h]; lpCriticalSection
0x18005b195  call    cs:__imp_DeleteCriticalSection
0x18005b19b  mov     rcx, rbx; lpCriticalSection
0x18005b19e  call    cs:__imp_DeleteCriticalSection
0x18005b1a4  lea     rcx, [rdi+130h]
0x18005b1ab  call    ??1?$unique_ptr@VContainerIndex@ConnectedStorage@@U?$default_delete@VContainerIndex@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConnectedStorage::ContainerIndex>::~unique_ptr<ConnectedStorage::ContainerIndex>(void)
0x18005b1b0  lea     rcx, [rdi+108h]; this
0x18005b1b7  call    ??1Containers@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Containers::~Containers(void)
0x18005b1bc  lea     rcx, [rdi+0E8h]
0x18005b1c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b1c8  lea     rcx, [rdi+0C8h]
0x18005b1cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b1d4  lea     rcx, [rdi+88h]; this
0x18005b1db  call    ??1CallerInfo@ConnectedStorage@@QEAA@XZ; ConnectedStorage::CallerInfo::~CallerInfo(void)
0x18005b1e0  lea     rcx, [rdi+58h]; this
0x18005b1e4  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x18005b1e9  lea     rcx, [rdi+40h]
0x18005b1ed  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x18005b1f2  lea     rcx, [rdi+28h]
0x18005b1f6  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x18005b1fb  lea     rcx, [rdi+8]
0x18005b1ff  mov     rbx, [rsp+38h+arg_0]
0x18005b204  add     rsp, 30h
0x18005b208  pop     rdi
0x18005b209  jmp     ??1?$HasExecuteQueue@VActivatingContext@ConnectedStorage@@@ConnectedStorage@@QEAA@XZ; ConnectedStorage::HasExecuteQueue<ConnectedStorage::ActivatingContext>::~HasExecuteQueue<ConnectedStorage::ActivatingContext>(void)
```
