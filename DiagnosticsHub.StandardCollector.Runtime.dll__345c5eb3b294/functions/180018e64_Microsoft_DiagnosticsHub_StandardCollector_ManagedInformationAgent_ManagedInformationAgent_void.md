# Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::~ManagedInformationAgent(void)

- ea: `0x180018e64`
- end: `0x180018f94`
- name: `??1ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@UEAA@XZ`
- size: `304`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018e30`

## callees

- `0x18000334c`
- `0x180018e64`
- `0x1800195f0`
- `0x180019658`
- `0x1800196c0`
- `0x18004b640`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180018f61`
- `KERNEL32!DeleteCriticalSection` at `0x180018f6b`
- `KERNEL32!DeleteCriticalSection` at `0x180018f61`
- `KERNEL32!DeleteCriticalSection` at `0x180018f6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::~ManagedInformationAgent(
        Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *this)
{
  volatile signed __int32 *v2; // rdx
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rdx
  __int64 v5; // rcx

  v2 = (volatile signed __int32 *)(*((_QWORD *)this + 57) - 24LL);
  if ( _InterlockedExchangeAdd(v2 + 4, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v2 + 8LL))(*(_QWORD *)v2);
  }
  v3 = (volatile signed __int32 *)(*((_QWORD *)this + 56) - 24LL);
  if ( _InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  }
  v4 = (volatile signed __int32 *)(*((_QWORD *)this + 55) - 24LL);
  if ( _InterlockedExchangeAdd(v4 + 4, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  }
  v5 = *((_QWORD *)this + 53);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  std::vector<std::wstring>::~vector<std::wstring>((char *)this + 320);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>((char *)this + 280);
  std::list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails>>::~list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails>>((char *)this + 264);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>((char *)this + 216);
  std::list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>>::~list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>>((char *)this + 200);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>((char *)this + 152);
  std::list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>>::~list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>>((char *)this + 136);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_QWORD *)this + 1) = &CModuleRefCount::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef);
  *((_QWORD *)this + 1) = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x180018e64  push    rbx
0x180018e66  sub     rsp, 20h
0x180018e6a  mov     rbx, rcx
0x180018e6d  mov     rdx, [rcx+1C8h]
0x180018e74  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180018e78  or      eax, 0FFFFFFFFh
0x180018e7b  lock xadd [rdx+10h], eax
0x180018e80  sub     eax, 1
0x180018e83  jg      short loc_180018E98
0x180018e85  lfence
0x180018e88  mov     rcx, [rdx]
0x180018e8b  mov     rax, [rcx]
0x180018e8e  mov     rax, [rax+8]
0x180018e92  call    cs:__guard_dispatch_icall_fptr
0x180018e98  mov     rdx, [rbx+1C0h]
0x180018e9f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180018ea3  or      eax, 0FFFFFFFFh
0x180018ea6  lock xadd [rdx+10h], eax
0x180018eab  sub     eax, 1
0x180018eae  jg      short loc_180018EC3
0x180018eb0  lfence
0x180018eb3  mov     rcx, [rdx]
0x180018eb6  mov     rax, [rcx]
0x180018eb9  mov     rax, [rax+8]
0x180018ebd  call    cs:__guard_dispatch_icall_fptr
0x180018ec3  mov     rdx, [rbx+1B8h]
0x180018eca  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180018ece  or      eax, 0FFFFFFFFh
0x180018ed1  lock xadd [rdx+10h], eax
0x180018ed6  sub     eax, 1
0x180018ed9  jg      short loc_180018EEF
0x180018edb  lfence
0x180018ede  mov     rcx, [rdx]
0x180018ee1  mov     rax, [rcx]
0x180018ee4  mov     rax, [rax+8]
0x180018ee8  call    cs:__guard_dispatch_icall_fptr
0x180018eee  nop
0x180018eef  mov     rcx, [rbx+1A8h]
0x180018ef6  test    rcx, rcx
0x180018ef9  jz      short loc_180018F09
0x180018efb  mov     rax, [rcx]
0x180018efe  mov     rax, [rax+10h]
0x180018f02  call    cs:__guard_dispatch_icall_fptr
0x180018f08  nop
0x180018f09  lea     rcx, [rbx+140h]
0x180018f10  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180018f15  lea     rcx, [rbx+118h]
0x180018f1c  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x180018f21  lea     rcx, [rbx+108h]
0x180018f28  call    ??1?$list@U?$pair@$$CB_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@@std@@V?$allocator@U?$pair@$$CB_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails>>::~list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails>>(void)
0x180018f2d  lea     rcx, [rbx+0D8h]
0x180018f34  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x180018f39  lea     rcx, [rbx+0C8h]
0x180018f40  call    ??1?$list@U?$pair@$$CB_KUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@V?$allocator@U?$pair@$$CB_KUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>>::~list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>>(void)
0x180018f45  lea     rcx, [rbx+98h]
0x180018f4c  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x180018f51  lea     rcx, [rbx+88h]
0x180018f58  call    ??1?$list@U?$pair@$$CB_KUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@V?$allocator@U?$pair@$$CB_KUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>>::~list<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>>(void)
0x180018f5d  lea     rcx, [rbx+40h]; lpCriticalSection
0x180018f61  call    cs:__imp_DeleteCriticalSection
0x180018f67  lea     rcx, [rbx+18h]; lpCriticalSection
0x180018f6b  call    cs:__imp_DeleteCriticalSection
0x180018f71  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x180018f78  mov     [rbx+8], rax
0x180018f7c  lock dec cs:?s_ulcModuleRef@CModuleRefCount@@0KA; ulong CModuleRefCount::s_ulcModuleRef
0x180018f83  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x180018f8a  mov     [rbx+8], rax
0x180018f8e  add     rsp, 20h
0x180018f92  pop     rbx
0x180018f93  retn
```
