# VmExdiServer::~VmExdiServer(void)

- ea: `0x14019928c`
- end: `0x14019937f`
- name: `??1VmExdiServer@@UEAA@XZ`
- size: `243`
- prototype: `void __fastcall(VmExdiServer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401993d0`

## callees

- `0x140032880`
- `0x140032ee0`
- `0x1401991ec`
- `0x140199220`
- `0x140199388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14019932d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199340`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199350`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199360`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14019932d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199340`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199350`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140199360`

## pseudocode

```c
void __fastcall VmExdiServer::~VmExdiServer(VmExdiServer *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &VmExdiServer::`vftable'{for `Vml::VmComObject'};
  *((_QWORD *)this + 3) = &VmExdiServer::`vftable'{for `IeXdiServer'};
  *((_QWORD *)this + 4) = &VmExdiServer::`vftable'{for `IeXdiX86ExContext'};
  *((_QWORD *)this + 5) = &VmExdiServer::`vftable'{for `IeXdiX86_64Context'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &VmExdiServer::`vftable'{for `Vml::VmSharableObject'};
  v2 = *(int *)(*((_QWORD *)this + 1) + 4LL);
  *(_DWORD *)((char *)this + v2 + 4) = v2 - 30192;
  Vml::VmReferencePtr<IVirtualMachineGuestState,Vml::VmWeakReferenceTraits>::~VmReferencePtr<IVirtualMachineGuestState,Vml::VmWeakReferenceTraits>((char *)this + 30176);
  VmExdiDebugHelper::`vbase destructor'((VmExdiServer *)((char *)this + 288));
  std::_Tree<std::_Tmap_traits<__int64,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>,std::less<__int64>,std::allocator<std::pair<__int64 const,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>>>,0>>::~_Tree<std::_Tmap_traits<__int64,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>,std::less<__int64>,std::allocator<std::pair<__int64 const,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>>>,0>>((char *)this + 264);
  CCookiedLinkList<IeXdiClientNotifyMemChg,unsigned long>::~CCookiedLinkList<IeXdiClientNotifyMemChg,unsigned long>((char *)this + 248);
  CCookiedLinkList<IeXdiClientNotifyMemChg,unsigned long>::~CCookiedLinkList<IeXdiClientNotifyMemChg,unsigned long>((char *)this + 232);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  WorkerModule::CleanUpFromRunSelf((VmExdiServer *)((char *)this + 24));
}

```

## disassembly

```asm
0x14019928c  mov     [rsp+arg_0], rbx
0x140199291  push    rdi
0x140199292  sub     rsp, 20h
0x140199296  mov     rdi, rcx
0x140199299  lea     rax, ??_7VmExdiServer@@6BVmComObject@Vml@@@; const VmExdiServer::`vftable'{for `Vml::VmComObject'}
0x1401992a0  mov     [rcx], rax
0x1401992a3  lea     rax, ??_7VmExdiServer@@6BIeXdiServer@@@; const VmExdiServer::`vftable'{for `IeXdiServer'}
0x1401992aa  mov     [rcx+18h], rax
0x1401992ae  lea     rax, ??_7VmExdiServer@@6BIeXdiX86ExContext@@@; const VmExdiServer::`vftable'{for `IeXdiX86ExContext'}
0x1401992b5  mov     [rcx+20h], rax
0x1401992b9  lea     rax, ??_7VmExdiServer@@6BIeXdiX86_64Context@@@; const VmExdiServer::`vftable'{for `IeXdiX86_64Context'}
0x1401992c0  mov     [rcx+28h], rax
0x1401992c4  mov     rax, [rcx+8]
0x1401992c8  movsxd  rdx, dword ptr [rax+4]
0x1401992cc  lea     rax, ??_7VmExdiServer@@6BVmSharableObject@Vml@@@; const VmExdiServer::`vftable'{for `Vml::VmSharableObject'}
0x1401992d3  mov     [rdx+rcx+8], rax
0x1401992d8  mov     rax, [rcx+8]
0x1401992dc  movsxd  rcx, dword ptr [rax+4]
0x1401992e0  lea     edx, [rcx-75F0h]
0x1401992e6  mov     [rcx+rdi+4], edx
0x1401992ea  lea     rcx, [rdi+75E0h]
0x1401992f1  call    ??1?$VmReferencePtr@UIVirtualMachineGuestState@@VVmWeakReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IVirtualMachineGuestState,Vml::VmWeakReferenceTraits>::~VmReferencePtr<IVirtualMachineGuestState,Vml::VmWeakReferenceTraits>(void)
0x1401992f6  lea     rcx, [rdi+120h]; this
0x1401992fd  call    ??_DVmExdiDebugHelper@@QEAAXXZ; VmExdiDebugHelper::`vbase destructor'(void)
0x140199302  lea     rcx, [rdi+108h]
0x140199309  call    ??1?$_Tree@V?$_Tmap_traits@_JV?$com_ptr_t@UIeXdiCodeBreakpoint@@Uerr_exception_policy@wil@@@wil@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JV?$com_ptr_t@UIeXdiCodeBreakpoint@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<__int64,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>,std::less<__int64>,std::allocator<std::pair<__int64 const,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>>>,0>>::~_Tree<std::_Tmap_traits<__int64,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>,std::less<__int64>,std::allocator<std::pair<__int64 const,wil::com_ptr_t<IeXdiCodeBreakpoint,wil::err_exception_policy>>>,0>>(void)
0x14019930e  lea     rcx, [rdi+0F8h]
0x140199315  call    ??1?$CCookiedLinkList@UIeXdiClientNotifyMemChg@@K@@QEAA@XZ; CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>::~CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>(void)
0x14019931a  lea     rcx, [rdi+0E8h]
0x140199321  call    ??1?$CCookiedLinkList@UIeXdiClientNotifyMemChg@@K@@QEAA@XZ; CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>::~CCookiedLinkList<IeXdiClientNotifyMemChg,ulong>(void)
0x140199326  lea     rcx, [rdi+0C0h]; lpCriticalSection
0x14019932d  call    cs:__imp_DeleteCriticalSection
0x140199334  nop     dword ptr [rax+rax+00h]
0x140199339  lea     rcx, [rdi+98h]; lpCriticalSection
0x140199340  call    cs:__imp_DeleteCriticalSection
0x140199347  nop     dword ptr [rax+rax+00h]
0x14019934c  lea     rcx, [rdi+70h]; lpCriticalSection
0x140199350  call    cs:__imp_DeleteCriticalSection
0x140199357  nop     dword ptr [rax+rax+00h]
0x14019935c  lea     rcx, [rdi+48h]; lpCriticalSection
0x140199360  call    cs:__imp_DeleteCriticalSection
0x140199367  nop     dword ptr [rax+rax+00h]
0x14019936c  lea     rcx, [rdi+18h]; this
0x140199370  mov     rbx, [rsp+28h+arg_0]
0x140199375  add     rsp, 20h
0x140199379  pop     rdi
0x14019937a  jmp     ?CleanUpFromRunSelf@WorkerModule@@QEAAXXZ; WorkerModule::CleanUpFromRunSelf(void)
```
