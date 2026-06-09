# Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::~CollectionSession(void)

- ea: `0x180004950`
- end: `0x180004b21`
- name: `??1CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@UEAA@XZ`
- size: `465`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000491c`
- `0x180007f20`

## callees

- `0x18000334c`
- `0x180004950`
- `0x180008408`
- `0x18004b640`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800049df`
- `KERNEL32!FreeLibrary` at `0x1800049df`
- `KERNEL32!CloseHandle` at `0x180004ae0`
- `KERNEL32!CloseHandle` at `0x180004ae0`
- `KERNEL32!DeleteCriticalSection` at `0x180004abf`
- `KERNEL32!DeleteCriticalSection` at `0x180004ad1`
- `KERNEL32!DeleteCriticalSection` at `0x180004abf`
- `KERNEL32!DeleteCriticalSection` at `0x180004ad1`
- `OLEAUT32!__imp_SysFreeString` at `0x180004a71`
- `OLEAUT32!__imp_SysFreeString` at `0x180004a71`
- `OLEAUT32!__imp_VariantClear` at `0x180004a2f`
- `OLEAUT32!__imp_VariantClear` at `0x180004a2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::~CollectionSession(
        Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *this)
{
  HMODULE *v2; // rsi
  HMODULE *i; // rdi
  volatile signed __int32 *v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  volatile signed __int32 *v7; // rdi
  void *v8; // rcx

  *(_QWORD *)this = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ICollectionSession'};
  *((_QWORD *)this + 1) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ICollectionSessionPausable'};
  *((_QWORD *)this + 2) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::ICollectionSessionEx'};
  *((_QWORD *)this + 3) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `IDebuggerCollectionSession'};
  *((_QWORD *)this + 4) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `IStandardCollectorVersion'};
  *((_QWORD *)this + 5) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 6) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `CModuleRefCount'};
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 31) + 24LL) + 8LL))(*((_QWORD *)this + 31) + 24LL);
  v2 = (HMODULE *)*((_QWORD *)this + 19);
  for ( i = (HMODULE *)*((_QWORD *)this + 18); i != v2; ++i )
    FreeLibrary(*i);
  v4 = (volatile signed __int32 *)(*((_QWORD *)this + 49) - 24LL);
  if ( _InterlockedDecrement(v4 + 4) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  }
  DiagHubCommon::HubTask<long,0>::~HubTask<long,0>((char *)this + 280);
  VariantClear((VARIANTARG *)((char *)this + 256));
  v5 = *((_QWORD *)this + 31);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 30);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  SysFreeString(*((BSTR *)this + 28));
  v7 = (volatile signed __int32 *)*((_QWORD *)this + 27);
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>((char *)this + 144);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v8 = (void *)*((_QWORD *)this + 12);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 12) = 0;
  }
  *((_QWORD *)this + 6) = &CModuleRefCount::`vftable';
  _InterlockedAdd((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef, 0xFFFFFFFF);
  *((_QWORD *)this + 6) = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x180004950  mov     [rsp+arg_0], rbx
0x180004955  mov     [rsp+arg_8], rsi
0x18000495a  mov     [rsp+arg_10], rdi
0x18000495f  push    r14
0x180004961  sub     rsp, 20h
0x180004965  mov     rbx, rcx
0x180004968  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BICollectionSession@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ICollectionSession'}
0x18000496f  mov     [rcx], rax
0x180004972  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BICollectionSessionPausable@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ICollectionSessionPausable'}
0x180004979  mov     [rcx+8], rax
0x18000497d  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BICollectionSessionEx@123@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::ICollectionSessionEx'}
0x180004984  mov     [rcx+10h], rax
0x180004988  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BIDebuggerCollectionSession@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `IDebuggerCollectionSession'}
0x18000498f  mov     [rcx+18h], rax
0x180004993  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BIStandardCollectorVersion@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `IStandardCollectorVersion'}
0x18000499a  mov     [rcx+20h], rax
0x18000499e  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BISupportErrorInfo@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ISupportErrorInfo'}
0x1800049a5  mov     [rcx+28h], rax
0x1800049a9  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BCModuleRefCount@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `CModuleRefCount'}
0x1800049b0  mov     [rcx+30h], rax
0x1800049b4  mov     rcx, [rcx+0F8h]
0x1800049bb  add     rcx, 18h
0x1800049bf  mov     rax, [rcx]
0x1800049c2  mov     rax, [rax+8]
0x1800049c6  call    cs:__guard_dispatch_icall_fptr
0x1800049cc  lea     r14, [rbx+90h]
0x1800049d3  mov     rsi, [r14+8]
0x1800049d7  mov     rdi, [r14]
0x1800049da  jmp     short loc_1800049E9
0x1800049dc  mov     rcx, [rdi]; hLibModule
0x1800049df  call    cs:__imp_FreeLibrary
0x1800049e5  add     rdi, 8
0x1800049e9  cmp     rdi, rsi
0x1800049ec  jnz     short loc_1800049DC
0x1800049ee  mov     rdx, [rbx+188h]
0x1800049f5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800049f9  or      esi, 0FFFFFFFFh
0x1800049fc  mov     eax, esi
0x1800049fe  lock xadd [rdx+10h], eax
0x180004a03  add     eax, esi
0x180004a05  test    eax, eax
0x180004a07  jg      short loc_180004A1C
0x180004a09  lfence
0x180004a0c  mov     rcx, [rdx]
0x180004a0f  mov     rax, [rcx]
0x180004a12  mov     rax, [rax+8]
0x180004a16  call    cs:__guard_dispatch_icall_fptr
0x180004a1c  lea     rcx, [rbx+118h]
0x180004a23  call    ??1?$HubTask@J$0A@@DiagHubCommon@@UEAA@XZ; DiagHubCommon::HubTask<long,0>::~HubTask<long,0>(void)
0x180004a28  lea     rcx, [rbx+100h]; pvarg
0x180004a2f  call    cs:__imp_VariantClear
0x180004a35  nop
0x180004a36  mov     rcx, [rbx+0F8h]
0x180004a3d  test    rcx, rcx
0x180004a40  jz      short loc_180004A50
0x180004a42  mov     rax, [rcx]
0x180004a45  mov     rax, [rax+10h]
0x180004a49  call    cs:__guard_dispatch_icall_fptr
0x180004a4f  nop
0x180004a50  mov     rcx, [rbx+0F0h]
0x180004a57  test    rcx, rcx
0x180004a5a  jz      short loc_180004A6A
0x180004a5c  mov     rax, [rcx]
0x180004a5f  mov     rax, [rax+10h]
0x180004a63  call    cs:__guard_dispatch_icall_fptr
0x180004a69  nop
0x180004a6a  mov     rcx, [rbx+0E0h]; bstrString
0x180004a71  call    cs:__imp_SysFreeString
0x180004a77  mov     rdi, [rbx+0D8h]
0x180004a7e  test    rdi, rdi
0x180004a81  jz      short loc_180004AB8
0x180004a83  mov     eax, esi
0x180004a85  lock xadd [rdi+8], eax
0x180004a8a  add     eax, esi
0x180004a8c  jnz     short loc_180004AB8
0x180004a8e  mov     rax, [rdi]
0x180004a91  mov     rcx, rdi
0x180004a94  mov     rax, [rax]
0x180004a97  call    cs:__guard_dispatch_icall_fptr
0x180004a9d  mov     eax, esi
0x180004a9f  lock xadd [rdi+0Ch], eax
0x180004aa4  add     eax, esi
0x180004aa6  jnz     short loc_180004AB8
0x180004aa8  mov     rax, [rdi]
0x180004aab  mov     rcx, rdi
0x180004aae  mov     rax, [rax+8]
0x180004ab2  call    cs:__guard_dispatch_icall_fptr
0x180004ab8  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x180004abf  call    cs:__imp_DeleteCriticalSection
0x180004ac5  mov     rcx, r14
0x180004ac8  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x180004acd  lea     rcx, [rbx+68h]; lpCriticalSection
0x180004ad1  call    cs:__imp_DeleteCriticalSection
0x180004ad7  mov     rcx, [rbx+60h]; hObject
0x180004adb  test    rcx, rcx
0x180004ade  jz      short loc_180004AEE
0x180004ae0  call    cs:__imp_CloseHandle
0x180004ae6  mov     qword ptr [rbx+60h], 0
0x180004aee  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x180004af5  mov     [rbx+30h], rax
0x180004af9  lock add cs:?s_ulcModuleRef@CModuleRefCount@@0KA, esi; ulong CModuleRefCount::s_ulcModuleRef
0x180004b00  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x180004b07  mov     [rbx+30h], rax
0x180004b0b  mov     rbx, [rsp+28h+arg_0]
0x180004b10  mov     rsi, [rsp+28h+arg_8]
0x180004b15  mov     rdi, [rsp+28h+arg_10]
0x180004b1a  add     rsp, 20h
0x180004b1e  pop     r14
0x180004b20  retn
```
