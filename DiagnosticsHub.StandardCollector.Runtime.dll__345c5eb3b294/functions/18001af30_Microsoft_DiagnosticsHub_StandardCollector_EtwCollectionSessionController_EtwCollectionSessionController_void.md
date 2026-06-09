# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::~EtwCollectionSessionController(void)

- ea: `0x18001af30`
- end: `0x18001b008`
- name: `??1EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAA@XZ`
- size: `216`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001aefc`

## callees

- `0x180002c4c`
- `0x18000334c`
- `0x180017f54`
- `0x180019464`
- `0x180019bc4`
- `0x18001af30`
- `0x180024e14`
- `0x180024edc`
- `0x1800291c4`
- `0x18002e994`
- `0x180043154`
- `0x18004a078`
- `0x18004a0f8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001af7d`
- `KERNEL32!DeleteCriticalSection` at `0x18001af8a`
- `KERNEL32!DeleteCriticalSection` at `0x18001af7d`
- `KERNEL32!DeleteCriticalSection` at `0x18001af8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::~EtwCollectionSessionController(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *this,
        void *a2)
{
  void *v3; // rdi

  v3 = (void *)*((_QWORD *)this + 491);
  if ( v3 )
  {
    Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::~SecuredDirectory(
      *((Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory **)this + 491),
      a2);
    operator delete(v3);
  }
  Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::~KernelTraceControl((Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)((char *)this + 3616));
  std::vector<std::unique_ptr<Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter>>::~vector<std::unique_ptr<Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter>>((char *)this + 3592);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 3536));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 3496));
  `eh vector destructor iterator'(
    (char *)this + 2856,
    0x80u,
    5u,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::~EtwSessionInformation);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>((char *)this + 2808);
  std::list<std::pair<_GUID const,std::shared_ptr<Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal>>>::~list<std::pair<_GUID const,std::shared_ptr<Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal>>>((char *)this + 2792);
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::~EtwCollectionRundownController((Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)((char *)this + 2752));
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings::~EtwCollectionRecommendedSettings((Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)((char *)this + 2672));
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::~EtwCollectionSyncController((Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)((char *)this + 1104));
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::~EtwCollectionProcessFilter((Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)((char *)this + 1048));
  Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::~CollectionSessionController(this);
}

```

## disassembly

```asm
0x18001af30  mov     [rsp+arg_0], rbx
0x18001af35  push    rdi
0x18001af36  sub     rsp, 20h
0x18001af3a  mov     rbx, rcx
0x18001af3d  mov     rdi, [rcx+0F58h]
0x18001af44  test    rdi, rdi
0x18001af47  jz      short loc_18001AF5E
0x18001af49  mov     rcx, rdi; this
0x18001af4c  call    ??1SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::~SecuredDirectory(void)
0x18001af51  mov     edx, 0D0h
0x18001af56  mov     rcx, rdi; Block
0x18001af59  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001af5e  lea     rcx, [rbx+0E20h]; this
0x18001af65  call    ??1KernelTraceControl@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::~KernelTraceControl(void)
0x18001af6a  lea     rcx, [rbx+0E08h]
0x18001af71  call    ??1?$vector@V?$unique_ptr@VEventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@U?$default_delete@VEventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@V?$allocator@V?$unique_ptr@VEventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@U?$default_delete@VEventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter>>::~vector<std::unique_ptr<Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter>>(void)
0x18001af76  lea     rcx, [rbx+0DD0h]; lpCriticalSection
0x18001af7d  call    cs:__imp_DeleteCriticalSection
0x18001af83  lea     rcx, [rbx+0DA8h]; lpCriticalSection
0x18001af8a  call    cs:__imp_DeleteCriticalSection
0x18001af90  nop
0x18001af91  lea     rcx, [rbx+0B28h]; void *
0x18001af98  lea     r9, ??1EtwSessionInformation@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; void (*)(void *)
0x18001af9f  mov     edx, 80h; unsigned __int64
0x18001afa4  lea     r8d, [rdx-7Bh]; unsigned __int64
0x18001afa8  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001afad  nop
0x18001afae  lea     rcx, [rbx+0AF8h]
0x18001afb5  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x18001afba  lea     rcx, [rbx+0AE8h]
0x18001afc1  call    ??1?$list@U?$pair@$$CBU_GUID@@V?$shared_ptr@VEtwProviderConfigInternal@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VEtwProviderConfigInternal@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<_GUID const,std::shared_ptr<Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal>>>::~list<std::pair<_GUID const,std::shared_ptr<Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal>>>(void)
0x18001afc6  lea     rcx, [rbx+0AC0h]; this
0x18001afcd  call    ??1EtwCollectionRundownController@StandardCollector@DiagnosticsHub@Microsoft@@MEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::~EtwCollectionRundownController(void)
0x18001afd2  lea     rcx, [rbx+0A70h]; this
0x18001afd9  call    ??1EtwCollectionRecommendedSettings@StandardCollector@DiagnosticsHub@Microsoft@@MEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings::~EtwCollectionRecommendedSettings(void)
0x18001afde  lea     rcx, [rbx+450h]; this
0x18001afe5  call    ??1EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@MEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::~EtwCollectionSyncController(void)
0x18001afea  lea     rcx, [rbx+418h]; this
0x18001aff1  call    ??1EtwCollectionProcessFilter@StandardCollector@DiagnosticsHub@Microsoft@@MEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::~EtwCollectionProcessFilter(void)
0x18001aff6  mov     rcx, rbx; this
0x18001aff9  mov     rbx, [rsp+28h+arg_0]
0x18001affe  add     rsp, 20h
0x18001b002  pop     rdi
0x18001b003  jmp     ??1CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::~CollectionSessionController(void)
```
