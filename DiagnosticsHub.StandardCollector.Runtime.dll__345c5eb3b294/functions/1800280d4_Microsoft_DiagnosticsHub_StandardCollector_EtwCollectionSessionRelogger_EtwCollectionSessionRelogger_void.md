# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::~EtwCollectionSessionRelogger(void)

- ea: `0x1800280d4`
- end: `0x18002824c`
- name: `??1EtwCollectionSessionRelogger@StandardCollector@DiagnosticsHub@Microsoft@@UEAA@XZ`
- size: `376`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800280a0`

## callees

- `0x180008408`
- `0x1800280d4`
- `0x180028c10`
- `0x18004a078`
- `0x18004b640`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180028111`
- `KERNEL32!WaitForSingleObject` at `0x18002815d`
- `KERNEL32!WaitForSingleObject` at `0x180028111`
- `KERNEL32!WaitForSingleObject` at `0x18002815d`
- `KERNEL32!SetEvent` at `0x180028149`
- `KERNEL32!SetEvent` at `0x180028149`
- `KERNEL32!CloseHandle` at `0x1800281ae`
- `KERNEL32!CloseHandle` at `0x1800281cc`
- `KERNEL32!CloseHandle` at `0x1800281ae`
- `KERNEL32!CloseHandle` at `0x1800281cc`
- `KERNEL32!DeleteCriticalSection` at `0x180028210`
- `KERNEL32!DeleteCriticalSection` at `0x180028210`
- `KERNEL32!GetLastError` at `0x180028167`
- `KERNEL32!GetLastError` at `0x180028167`
- `OLEAUT32!__imp_SysFreeString` at `0x180028183`
- `OLEAUT32!__imp_SysFreeString` at `0x180028190`
- `OLEAUT32!__imp_SysFreeString` at `0x180028183`
- `OLEAUT32!__imp_SysFreeString` at `0x180028190`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::~EtwCollectionSessionRelogger(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void **v5; // rdi
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rcx
  void *v9; // rcx

  *(_QWORD *)this = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `ITraceEventCallback'};
  *((_QWORD *)this + 1) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `CModuleRefCount'};
  *((_QWORD *)this + 3) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `DiagHubCommon::HubTask<long,0>'};
  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    if ( WaitForSingleObject(v2, 0) )
    {
      v3 = *((_QWORD *)this + 29);
      if ( v3 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 88LL))(v3);
        if ( *((_QWORD *)this + 4) && *((int *)this + 30) >= 0 )
          SetEvent(*((HANDLE *)this + 14));
        v4 = (void *)*((_QWORD *)this + 4);
        if ( v4 && WaitForSingleObject(v4, 0xFFFFFFFF) == -1 )
          GetLastError();
      }
    }
  }
  v5 = (void **)((char *)this + 184);
  std::deque<ATL::CComPtr<ITraceEvent>>::_Tidy((char *)this + 184);
  SysFreeString(*((BSTR *)this + 35));
  SysFreeString(*((BSTR *)this + 34));
  v6 = (void *)*((_QWORD *)this + 32);
  if ( v6 != (void *)-1LL )
  {
    *((_QWORD *)this + 32) = -1;
    CloseHandle(v6);
  }
  v7 = (void *)*((_QWORD *)this + 30);
  if ( v7 != (void *)-1LL )
  {
    *((_QWORD *)this + 30) = -1;
    CloseHandle(v7);
  }
  v8 = *((_QWORD *)this + 29);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  std::deque<ATL::CComPtr<ITraceEvent>>::_Tidy((char *)this + 184);
  v9 = *v5;
  *v5 = 0;
  operator delete(v9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  DiagHubCommon::HubTask<long,0>::~HubTask<long,0>((char *)this + 24);
  *((_QWORD *)this + 1) = &CModuleRefCount::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef);
  *((_QWORD *)this + 1) = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x1800280d4  mov     [rsp+arg_8], rbx
0x1800280d9  mov     [rsp+arg_10], rsi
0x1800280de  push    rdi
0x1800280df  sub     rsp, 20h
0x1800280e3  mov     rbx, rcx
0x1800280e6  lea     rax, ??_7EtwCollectionSessionRelogger@StandardCollector@DiagnosticsHub@Microsoft@@6BITraceEventCallback@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `ITraceEventCallback'}
0x1800280ed  mov     [rcx], rax
0x1800280f0  lea     rax, ??_7EtwCollectionSessionRelogger@StandardCollector@DiagnosticsHub@Microsoft@@6BCModuleRefCount@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `CModuleRefCount'}
0x1800280f7  mov     [rcx+8], rax
0x1800280fb  lea     rax, ??_7EtwCollectionSessionRelogger@StandardCollector@DiagnosticsHub@Microsoft@@6B?$HubTask@J$0A@@DiagHubCommon@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::`vftable'{for `DiagHubCommon::HubTask<long,0>'}
0x180028102  mov     [rcx+18h], rax
0x180028106  mov     rcx, [rcx+20h]; hHandle
0x18002810a  test    rcx, rcx
0x18002810d  jz      short loc_18002816D
0x18002810f  xor     edx, edx; dwMilliseconds
0x180028111  call    cs:__imp_WaitForSingleObject
0x180028117  test    eax, eax
0x180028119  jz      short loc_18002816D
0x18002811b  mov     rcx, [rbx+0E8h]
0x180028122  test    rcx, rcx
0x180028125  jz      short loc_18002816D
0x180028127  mov     rax, [rcx]
0x18002812a  mov     rax, [rax+58h]
0x18002812e  call    cs:__guard_dispatch_icall_fptr
0x180028134  cmp     qword ptr [rbx+20h], 0
0x180028139  jz      short loc_18002814F
0x18002813b  mov     eax, [rbx+78h]
0x18002813e  shr     eax, 1Fh
0x180028141  test    al, al
0x180028143  jnz     short loc_18002814F
0x180028145  mov     rcx, [rbx+70h]; hEvent
0x180028149  call    cs:__imp_SetEvent
0x18002814f  mov     rcx, [rbx+20h]; hHandle
0x180028153  test    rcx, rcx
0x180028156  jz      short loc_18002816D
0x180028158  or      edi, 0FFFFFFFFh
0x18002815b  mov     edx, edi; dwMilliseconds
0x18002815d  call    cs:__imp_WaitForSingleObject
0x180028163  cmp     eax, edi
0x180028165  jnz     short loc_18002816D
0x180028167  call    cs:__imp_GetLastError
0x18002816d  lea     rdi, [rbx+0B8h]
0x180028174  mov     rcx, rdi
0x180028177  call    ?_Tidy@?$deque@V?$CComPtr@UITraceEvent@@@ATL@@V?$allocator@V?$CComPtr@UITraceEvent@@@ATL@@@std@@@std@@AEAAXXZ; std::deque<ATL::CComPtr<ITraceEvent>>::_Tidy(void)
0x18002817c  mov     rcx, [rbx+118h]; bstrString
0x180028183  call    cs:__imp_SysFreeString
0x180028189  mov     rcx, [rbx+110h]; bstrString
0x180028190  call    cs:__imp_SysFreeString
0x180028196  mov     rcx, [rbx+100h]; hObject
0x18002819d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800281a1  jz      short loc_1800281B4
0x1800281a3  mov     qword ptr [rbx+100h], 0FFFFFFFFFFFFFFFFh
0x1800281ae  call    cs:__imp_CloseHandle
0x1800281b4  mov     rcx, [rbx+0F0h]; hObject
0x1800281bb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800281bf  jz      short loc_1800281D3
0x1800281c1  mov     qword ptr [rbx+0F0h], 0FFFFFFFFFFFFFFFFh
0x1800281cc  call    cs:__imp_CloseHandle
0x1800281d2  nop
0x1800281d3  mov     rcx, [rbx+0E8h]
0x1800281da  test    rcx, rcx
0x1800281dd  jz      short loc_1800281ED
0x1800281df  mov     rax, [rcx]
0x1800281e2  mov     rax, [rax+10h]
0x1800281e6  call    cs:__guard_dispatch_icall_fptr
0x1800281ec  nop
0x1800281ed  mov     rcx, rdi
0x1800281f0  call    ?_Tidy@?$deque@V?$CComPtr@UITraceEvent@@@ATL@@V?$allocator@V?$CComPtr@UITraceEvent@@@ATL@@@std@@@std@@AEAAXXZ; std::deque<ATL::CComPtr<ITraceEvent>>::_Tidy(void)
0x1800281f5  mov     rcx, [rdi]; Block
0x1800281f8  mov     qword ptr [rdi], 0
0x1800281ff  mov     edx, 10h
0x180028204  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028209  lea     rcx, [rbx+90h]; lpCriticalSection
0x180028210  call    cs:__imp_DeleteCriticalSection
0x180028216  lea     rcx, [rbx+18h]
0x18002821a  call    ??1?$HubTask@J$0A@@DiagHubCommon@@UEAA@XZ; DiagHubCommon::HubTask<long,0>::~HubTask<long,0>(void)
0x18002821f  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x180028226  mov     [rbx+8], rax
0x18002822a  lock dec cs:?s_ulcModuleRef@CModuleRefCount@@0KA; ulong CModuleRefCount::s_ulcModuleRef
0x180028231  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x180028238  mov     [rbx+8], rax
0x18002823c  mov     rbx, [rsp+28h+arg_8]
0x180028241  mov     rsi, [rsp+28h+arg_10]
0x180028246  add     rsp, 20h
0x18002824a  pop     rdi
0x18002824b  retn
```
