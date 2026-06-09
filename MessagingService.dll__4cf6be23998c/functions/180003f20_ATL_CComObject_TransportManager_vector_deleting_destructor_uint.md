# ATL::CComObject<TransportManager>::`vector deleting destructor'(uint)

- ea: `0x180003f20`
- end: `0x180003f8d`
- name: `??_E?$CComObject@VTransportManager@@@ATL@@UEAAPEAXI@Z`
- size: `109`
- prototype: `TransportManager *__fastcall(TransportManager *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003dc8`
- `0x180003f20`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003f79`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003f79`

## pseudocode

```c
TransportManager *__fastcall ATL::CComObject<TransportManager>::`vector deleting destructor'(
        TransportManager *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<TransportManager>::`vftable'{for `ITransportTaskScheduler'};
  *((_QWORD *)this + 1) = &ATL::CComObject<TransportManager>::`vftable'{for `ITransportTaskCallback'};
  *((_QWORD *)this + 2) = &ATL::CComObject<TransportManager>::`vftable'{for `IOneShotTimerCallback'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  TransportManager::~TransportManager(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003f20  mov     [rsp+arg_0], rbx
0x180003f25  push    rdi
0x180003f26  sub     rsp, 20h
0x180003f2a  mov     dword ptr [rcx+18h], 0C0000001h
0x180003f31  lea     rax, ??_7?$CComObject@VTransportManager@@@ATL@@6BITransportTaskScheduler@@@; const ATL::CComObject<TransportManager>::`vftable'{for `ITransportTaskScheduler'}
0x180003f38  mov     [rcx], rax
0x180003f3b  mov     rdi, rcx
0x180003f3e  lea     rax, ??_7?$CComObject@VTransportManager@@@ATL@@6BITransportTaskCallback@@@; const ATL::CComObject<TransportManager>::`vftable'{for `ITransportTaskCallback'}
0x180003f45  mov     ebx, edx
0x180003f47  mov     [rcx+8], rax
0x180003f4b  lea     rax, ??_7?$CComObject@VTransportManager@@@ATL@@6BIOneShotTimerCallback@@@; const ATL::CComObject<TransportManager>::`vftable'{for `IOneShotTimerCallback'}
0x180003f52  mov     [rcx+10h], rax
0x180003f56  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003f5d  mov     rax, [rcx]
0x180003f60  mov     rax, [rax+10h]
0x180003f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f69  mov     rcx, rdi; this
0x180003f6c  call    ??1TransportManager@@MEAA@XZ; TransportManager::~TransportManager(void)
0x180003f71  test    bl, 1
0x180003f74  jz      short loc_180003F7F
0x180003f76  mov     rcx, rdi
0x180003f79  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003f7f  mov     rbx, [rsp+28h+arg_0]
0x180003f84  mov     rax, rdi
0x180003f87  add     rsp, 20h
0x180003f8b  pop     rdi
0x180003f8c  retn
```
