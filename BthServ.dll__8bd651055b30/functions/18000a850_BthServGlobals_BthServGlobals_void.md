# BthServGlobals::~BthServGlobals(void)

- ea: `0x18000a850`
- end: `0x18000a953`
- name: `??1BthServGlobals@@QEAA@XZ`
- size: `259`
- prototype: `void __fastcall(BthServGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180033c90`

## callees

- `0x180001b60`
- `0x18000a418`
- `0x18000a850`
- `0x18000a95c`
- `0x180012ed8`
- `0x18001d324`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a8d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a8d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a8fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a8fa`

## pseudocode

```c
void __fastcall BthServGlobals::~BthServGlobals(BthServGlobals *this)
{
  void *v1; // rbx
  void *v3; // rbx
  HMODULE v4; // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  volatile signed __int32 *v6; // rbx

  v1 = (void *)*((_QWORD *)this + 48);
  if ( v1 )
  {
    LocalCorePerformanceTelemetryCollector::~LocalCorePerformanceTelemetryCollector(*((LocalCorePerformanceTelemetryCollector **)this
                                                                                    + 48));
    operator delete(v1, (const struct std::nothrow_t *)0x10);
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>,void *>>>(
    (char *)this + 368,
    (char *)this + 368,
    *(_QWORD *)(*((_QWORD *)this + 46) + 8LL));
  operator delete(*((void **)this + 46), (const struct std::nothrow_t *)0x38);
  v3 = (void *)*((_QWORD *)this + 44);
  if ( v3 )
  {
    Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(*((Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher **)this
                                                                                             + 44));
    operator delete(v3, (const struct std::nothrow_t *)0x28);
  }
  v4 = (HMODULE)*((_QWORD *)this + 42);
  if ( v4 )
    FreeLibrary(v4);
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 41);
  if ( v5 )
    (**v5)(v5, 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 14);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  BthServRadioInterfaceWatcher::~BthServRadioInterfaceWatcher((BthServGlobals *)((char *)this + 64));
}

```

## disassembly

```asm
0x18000a850  mov     [rsp+arg_0], rbx
0x18000a855  push    rdi
0x18000a856  sub     rsp, 20h
0x18000a85a  mov     rbx, [rcx+180h]
0x18000a861  mov     rdi, rcx
0x18000a864  test    rbx, rbx
0x18000a867  jz      short loc_18000A87E
0x18000a869  mov     rcx, rbx; this
0x18000a86c  call    ??1LocalCorePerformanceTelemetryCollector@@QEAA@XZ; LocalCorePerformanceTelemetryCollector::~LocalCorePerformanceTelemetryCollector(void)
0x18000a871  mov     edx, 10h; struct std::nothrow_t *
0x18000a876  mov     rcx, rbx; void *
0x18000a879  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a87e  lea     rbx, [rdi+170h]
0x18000a885  mov     r8, [rbx]
0x18000a888  mov     rdx, rbx
0x18000a88b  mov     rcx, rbx
0x18000a88e  mov     r8, [r8+8]
0x18000a892  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@VFingerprintCollectorTimer@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@VFingerprintCollectorTimer@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@VFingerprintCollectorTimer@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@VFingerprintCollectorTimer@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>,void *> *)
0x18000a897  mov     rcx, [rbx]; void *
0x18000a89a  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x18000a89f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a8a4  mov     rbx, [rdi+160h]
0x18000a8ab  test    rbx, rbx
0x18000a8ae  jz      short loc_18000A8C5
0x18000a8b0  mov     rcx, rbx; this
0x18000a8b3  call    ??1BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(void)
0x18000a8b8  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18000a8bd  mov     rcx, rbx; void *
0x18000a8c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a8c5  mov     rcx, [rdi+150h]; hLibModule
0x18000a8cc  test    rcx, rcx
0x18000a8cf  jz      short loc_18000A8D7
0x18000a8d1  call    cs:__imp_FreeLibrary
0x18000a8d7  mov     rcx, [rdi+148h]
0x18000a8de  test    rcx, rcx
0x18000a8e1  jz      short loc_18000A8F3
0x18000a8e3  mov     rax, [rcx]
0x18000a8e6  mov     edx, 1
0x18000a8eb  mov     rax, [rax]
0x18000a8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8f3  lea     rcx, [rdi+100h]; lpCriticalSection
0x18000a8fa  call    cs:__imp_DeleteCriticalSection
0x18000a900  mov     rbx, [rdi+70h]
0x18000a904  test    rbx, rbx
0x18000a907  jz      short loc_18000A940
0x18000a909  or      eax, 0FFFFFFFFh
0x18000a90c  lock xadd [rbx+8], eax
0x18000a911  cmp     eax, 1
0x18000a914  jnz     short loc_18000A940
0x18000a916  mov     rax, [rbx]
0x18000a919  mov     rcx, rbx
0x18000a91c  mov     rax, [rax]
0x18000a91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a924  or      eax, 0FFFFFFFFh
0x18000a927  lock xadd [rbx+0Ch], eax
0x18000a92c  cmp     eax, 1
0x18000a92f  jnz     short loc_18000A940
0x18000a931  mov     rax, [rbx]
0x18000a934  mov     rcx, rbx
0x18000a937  mov     rax, [rax+8]
0x18000a93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a940  lea     rcx, [rdi+40h]; this
0x18000a944  mov     rbx, [rsp+28h+arg_0]
0x18000a949  add     rsp, 20h
0x18000a94d  pop     rdi
0x18000a94e  jmp     ??1BthServRadioInterfaceWatcher@@QEAA@XZ; BthServRadioInterfaceWatcher::~BthServRadioInterfaceWatcher(void)
```
