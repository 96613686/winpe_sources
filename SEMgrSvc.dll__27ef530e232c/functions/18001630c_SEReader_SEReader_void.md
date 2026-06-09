# SEReader::~SEReader(void)

- ea: `0x18001630c`
- end: `0x1800164a5`
- name: `??1SEReader@@QEAA@XZ`
- size: `409`
- prototype: `void __fastcall(SEReader *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180012620`

## callees

- `0x1800049c4`
- `0x18001063c`
- `0x180013274`
- `0x18001630c`
- `0x180017a60`
- `0x18001fb2c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001633f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001634c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016359`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163e3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001640e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001646e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001633f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001634c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016359`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163e3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001640e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001646e`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18001636b`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18001636b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SEReader::~SEReader(SEReader *this)
{
  volatile signed __int32 *v2; // rdi
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  volatile signed __int32 *v5; // rdi
  volatile signed __int32 *v6; // rcx

  *(_QWORD *)this = &SEReader::`vftable'{for `IRoutingMgrNfcProvider'};
  *((_QWORD *)this + 1) = &SEReader::`vftable'{for `IRfFieldEventHandlerCallbacks'};
  SEReader::Uninitialize(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 9);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 7);
  if ( *((_QWORD *)this + 34) )
    CM_Unregister_Notification();
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>((char *)this + 240);
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 27);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  v3 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 19);
  if ( v3 )
  {
    RfFieldEventHandler::Uninitialize(*((RfFieldEventHandler **)this + 19));
    DeleteCriticalSection(v3);
    operator delete(v3);
  }
  v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 18);
  if ( v4 )
  {
    RfFieldEventHandler::Uninitialize(*((RfFieldEventHandler **)this + 18));
    DeleteCriticalSection(v4);
    operator delete(v4);
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 17);
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  std::wstring::~wstring((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v6 )
  {
    if ( !_InterlockedDecrement(v6 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
  }
}

```

## disassembly

```asm
0x18001630c  mov     [rsp+arg_0], rbx
0x180016311  mov     [rsp+arg_8], rsi
0x180016316  push    rdi
0x180016317  sub     rsp, 20h
0x18001631b  mov     rbx, rcx
0x18001631e  lea     rax, ??_7SEReader@@6BIRoutingMgrNfcProvider@@@; const SEReader::`vftable'{for `IRoutingMgrNfcProvider'}
0x180016325  mov     [rcx], rax
0x180016328  lea     rax, ??_7SEReader@@6BIRfFieldEventHandlerCallbacks@@@; const SEReader::`vftable'{for `IRfFieldEventHandlerCallbacks'}
0x18001632f  mov     [rcx+8], rax
0x180016333  call    ?Uninitialize@SEReader@@AEAAXXZ; SEReader::Uninitialize(void)
0x180016338  lea     rcx, [rbx+168h]; lpCriticalSection
0x18001633f  call    cs:__imp_DeleteCriticalSection
0x180016345  lea     rcx, [rbx+140h]; lpCriticalSection
0x18001634c  call    cs:__imp_DeleteCriticalSection
0x180016352  lea     rcx, [rbx+118h]; lpCriticalSection
0x180016359  call    cs:__imp_DeleteCriticalSection
0x18001635f  mov     rcx, [rbx+110h]
0x180016366  test    rcx, rcx
0x180016369  jz      short loc_180016371
0x18001636b  call    cs:__imp_CM_Unregister_Notification
0x180016371  lea     rcx, [rbx+0F0h]
0x180016378  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>(void)
0x18001637d  mov     rdi, [rbx+0D8h]
0x180016384  or      esi, 0FFFFFFFFh
0x180016387  test    rdi, rdi
0x18001638a  jz      short loc_1800163BF
0x18001638c  mov     eax, esi
0x18001638e  lock xadd [rdi+8], eax
0x180016393  add     eax, esi
0x180016395  jnz     short loc_1800163BF
0x180016397  mov     rax, [rdi]
0x18001639a  mov     rcx, rdi
0x18001639d  mov     rax, [rax]
0x1800163a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163a5  mov     eax, esi
0x1800163a7  lock xadd [rdi+0Ch], eax
0x1800163ac  add     eax, esi
0x1800163ae  jnz     short loc_1800163BF
0x1800163b0  mov     rax, [rdi]
0x1800163b3  mov     rcx, rdi
0x1800163b6  mov     rax, [rax+8]
0x1800163ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163bf  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1800163c6  call    cs:__imp_DeleteCriticalSection
0x1800163cc  mov     rdi, [rbx+98h]
0x1800163d3  test    rdi, rdi
0x1800163d6  jz      short loc_1800163F7
0x1800163d8  mov     rcx, rdi; this
0x1800163db  call    ?Uninitialize@RfFieldEventHandler@@QEAAXXZ; RfFieldEventHandler::Uninitialize(void)
0x1800163e0  mov     rcx, rdi; lpCriticalSection
0x1800163e3  call    cs:__imp_DeleteCriticalSection
0x1800163e9  nop
0x1800163ea  mov     edx, 70h ; 'p'
0x1800163ef  mov     rcx, rdi; Block
0x1800163f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800163f7  mov     rdi, [rbx+90h]
0x1800163fe  test    rdi, rdi
0x180016401  jz      short loc_180016422
0x180016403  mov     rcx, rdi; this
0x180016406  call    ?Uninitialize@RfFieldEventHandler@@QEAAXXZ; RfFieldEventHandler::Uninitialize(void)
0x18001640b  mov     rcx, rdi; lpCriticalSection
0x18001640e  call    cs:__imp_DeleteCriticalSection
0x180016414  nop
0x180016415  mov     edx, 70h ; 'p'
0x18001641a  mov     rcx, rdi; Block
0x18001641d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016422  mov     rdi, [rbx+88h]
0x180016429  test    rdi, rdi
0x18001642c  jz      short loc_180016461
0x18001642e  mov     eax, esi
0x180016430  lock xadd [rdi+8], eax
0x180016435  add     eax, esi
0x180016437  jnz     short loc_180016461
0x180016439  mov     rax, [rdi]
0x18001643c  mov     rcx, rdi
0x18001643f  mov     rax, [rax]
0x180016442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016447  mov     eax, esi
0x180016449  lock xadd [rdi+0Ch], eax
0x18001644e  add     eax, esi
0x180016450  jnz     short loc_180016461
0x180016452  mov     rax, [rdi]
0x180016455  mov     rcx, rdi
0x180016458  mov     rax, [rax+8]
0x18001645c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016461  lea     rcx, [rbx+60h]
0x180016465  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001646a  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001646e  call    cs:__imp_DeleteCriticalSection
0x180016474  mov     rcx, [rbx+18h]
0x180016478  test    rcx, rcx
0x18001647b  jz      short loc_180016495
0x18001647d  mov     eax, esi
0x18001647f  lock xadd [rcx+0Ch], eax
0x180016484  add     eax, esi
0x180016486  jnz     short loc_180016495
0x180016488  mov     rax, [rcx]
0x18001648b  mov     rax, [rax+8]
0x18001648f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016494  nop
0x180016495  mov     rbx, [rsp+28h+arg_0]
0x18001649a  mov     rsi, [rsp+28h+arg_8]
0x18001649f  add     rsp, 20h
0x1800164a3  pop     rdi
0x1800164a4  retn
```
