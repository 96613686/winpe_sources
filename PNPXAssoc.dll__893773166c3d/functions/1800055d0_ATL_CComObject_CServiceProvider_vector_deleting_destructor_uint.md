# ATL::CComObject<CServiceProvider>::`vector deleting destructor'(uint)

- ea: `0x1800055d0`
- end: `0x180005647`
- name: `??_E?$CComObject@VCServiceProvider@@@ATL@@UEAAPEAXI@Z`
- size: `119`
- prototype: `__int64 __fastcall(CServiceProvider *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800019b0`
- `0x1800055d0`
- `0x180009990`
- `0x180014010`

## pseudocode

```c
CServiceProvider *__fastcall ATL::CComObject<CServiceProvider>::`vector deleting destructor'(
        CServiceProvider *this,
        char a2)
{
  *((_DWORD *)this + 8) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXDeviceAssociation'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXAssociation'};
  *((_QWORD *)this + 2) = &ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXAssociationAsync'};
  *((_QWORD *)this + 3) = &ATL::CComObject<CServiceProvider>::`vftable'{for `IFunctionDiscoveryServiceProvider'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CServiceProvider::~CServiceProvider(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800055d0  mov     [rsp+arg_0], rbx
0x1800055d5  push    rdi
0x1800055d6  sub     rsp, 20h
0x1800055da  mov     dword ptr [rcx+20h], 0C0000001h
0x1800055e1  lea     rax, ??_7?$CComObject@VCServiceProvider@@@ATL@@6BIPNPXDeviceAssociation@@@; const ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXDeviceAssociation'}
0x1800055e8  mov     [rcx], rax
0x1800055eb  mov     rdi, rcx
0x1800055ee  lea     rax, ??_7?$CComObject@VCServiceProvider@@@ATL@@6BIPNPXAssociation@@@; const ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXAssociation'}
0x1800055f5  mov     ebx, edx
0x1800055f7  mov     [rcx+8], rax
0x1800055fb  lea     rax, ??_7?$CComObject@VCServiceProvider@@@ATL@@6BIPNPXAssociationAsync@@@; const ATL::CComObject<CServiceProvider>::`vftable'{for `IPNPXAssociationAsync'}
0x180005602  mov     [rcx+10h], rax
0x180005606  lea     rax, ??_7?$CComObject@VCServiceProvider@@@ATL@@6BIFunctionDiscoveryServiceProvider@@@; const ATL::CComObject<CServiceProvider>::`vftable'{for `IFunctionDiscoveryServiceProvider'}
0x18000560d  mov     [rcx+18h], rax
0x180005611  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005618  mov     rax, [rcx]
0x18000561b  mov     rax, [rax+10h]
0x18000561f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005624  mov     rcx, rdi; this
0x180005627  call    ??1CServiceProvider@@UEAA@XZ; CServiceProvider::~CServiceProvider(void)
0x18000562c  test    bl, 1
0x18000562f  jz      short loc_180005639
0x180005631  mov     rcx, rdi; Block
0x180005634  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005639  mov     rbx, [rsp+28h+arg_0]
0x18000563e  mov     rax, rdi
0x180005641  add     rsp, 20h
0x180005645  pop     rdi
0x180005646  retn
```
