# Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::~CollectionSessionController(void)

- ea: `0x180002c4c`
- end: `0x180002d26`
- name: `??1CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAA@XZ`
- size: `218`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002e38`
- `0x180002fac`
- `0x18001af30`
- `0x18004caf2`

## callees

- `0x1800029bc`
- `0x180002c4c`
- `0x180003290`
- `0x18004b640`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180002cdf`
- `KERNEL32!CloseHandle` at `0x180002cdf`
- `KERNEL32!DeleteCriticalSection` at `0x180002c99`
- `KERNEL32!DeleteCriticalSection` at `0x180002c99`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::~CollectionSessionController(
        Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *this)
{
  __int64 v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::`vftable'{for `ICollectionSessionController'};
  *((_QWORD *)this + 1) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::ICollectionSessionControllerEx'};
  *((_QWORD *)this + 2) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 3) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::AgentController'};
  *((_QWORD *)this + 103) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::`vftable'{for `CModuleRefCount'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  std::_Tree<std::_Tset_traits<ATL::CComBSTR,std::less<ATL::CComBSTR>,std::allocator<ATL::CComBSTR>,0>>::~_Tree<std::_Tset_traits<ATL::CComBSTR,std::less<ATL::CComBSTR>,std::allocator<ATL::CComBSTR>,0>>((char *)this + 968);
  SysFreeString(*((BSTR *)this + 115));
  v2 = *((_QWORD *)this + 114);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (void *)*((_QWORD *)this + 112);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 112) = 0;
  }
  *((_QWORD *)this + 103) = &CModuleRefCount::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef);
  *((_QWORD *)this + 103) = &CRefCount::`vftable';
  Microsoft::DiagnosticsHub::StandardCollector::AgentController::~AgentController((Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *)((char *)this + 24));
}

```

## disassembly

```asm
0x180002c4c  mov     [rsp+arg_0], rbx
0x180002c51  push    rdi
0x180002c52  sub     rsp, 20h
0x180002c56  mov     rbx, rcx
0x180002c59  lea     rax, ??_7CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BICollectionSessionController@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::`vftable'{for `ICollectionSessionController'}
0x180002c60  mov     [rcx], rax
0x180002c63  lea     rax, ??_7CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BICollectionSessionControllerEx@123@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::ICollectionSessionControllerEx'}
0x180002c6a  mov     [rcx+8], rax
0x180002c6e  lea     rax, ??_7CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BISupportErrorInfo@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::`vftable'{for `ISupportErrorInfo'}
0x180002c75  mov     [rcx+10h], rax
0x180002c79  lea     rax, ??_7CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BAgentController@123@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::AgentController'}
0x180002c80  mov     [rcx+18h], rax
0x180002c84  lea     rax, ??_7CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BCModuleRefCount@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::`vftable'{for `CModuleRefCount'}
0x180002c8b  mov     [rcx+338h], rax
0x180002c92  add     rcx, 3D8h; lpCriticalSection
0x180002c99  call    cs:__imp_DeleteCriticalSection
0x180002c9f  lea     rcx, [rbx+3C8h]
0x180002ca6  call    ??1?$_Tree@V?$_Tset_traits@VCComBSTR@ATL@@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ATL::CComBSTR,std::less<ATL::CComBSTR>,std::allocator<ATL::CComBSTR>,0>>::~_Tree<std::_Tset_traits<ATL::CComBSTR,std::less<ATL::CComBSTR>,std::allocator<ATL::CComBSTR>,0>>(void)
0x180002cab  mov     rcx, [rbx+398h]; bstrString
0x180002cb2  call    cs:__imp_SysFreeString
0x180002cb8  nop
0x180002cb9  mov     rcx, [rbx+390h]
0x180002cc0  test    rcx, rcx
0x180002cc3  jz      short loc_180002CD3
0x180002cc5  mov     rax, [rcx]
0x180002cc8  mov     rax, [rax+10h]
0x180002ccc  call    cs:__guard_dispatch_icall_fptr
0x180002cd2  nop
0x180002cd3  mov     rcx, [rbx+380h]; hObject
0x180002cda  test    rcx, rcx
0x180002cdd  jz      short loc_180002CF0
0x180002cdf  call    cs:__imp_CloseHandle
0x180002ce5  mov     qword ptr [rbx+380h], 0
0x180002cf0  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x180002cf7  mov     [rbx+338h], rax
0x180002cfe  lock dec cs:?s_ulcModuleRef@CModuleRefCount@@0KA; ulong CModuleRefCount::s_ulcModuleRef
0x180002d05  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x180002d0c  mov     [rbx+338h], rax
0x180002d13  lea     rcx, [rbx+18h]; this
0x180002d17  mov     rbx, [rsp+28h+arg_0]
0x180002d1c  add     rsp, 20h
0x180002d20  pop     rdi
0x180002d21  jmp     ??1AgentController@StandardCollector@DiagnosticsHub@Microsoft@@UEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::AgentController::~AgentController(void)
```
