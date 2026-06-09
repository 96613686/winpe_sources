# SebHelper::~SebHelper(void)

- ea: `0x180090294`
- end: `0x1800902ea`
- name: `??1SebHelper@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(SebHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016fd4`

## callees

- `0x180071ef8`
- `0x18009025c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009029d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800902a7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800902b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800902bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009029d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800902a7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800902b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800902bb`

## pseudocode

```c
void __fastcall SebHelper::~SebHelper(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
  DeleteCriticalSection(this + 1);
  DeleteCriticalSection(this + 2);
  DeleteCriticalSection(this + 3);
  std::_Tree<std::_Tmap_traits<_GUID,WWAN_INTERFACE_INFO *,GuidLessThan,std::allocator<std::pair<_GUID const,WWAN_INTERFACE_INFO *>>,0>>::~_Tree<std::_Tmap_traits<_GUID,WWAN_INTERFACE_INFO *,GuidLessThan,std::allocator<std::pair<_GUID const,WWAN_INTERFACE_INFO *>>,0>>(&this[4].SpinCount);
  std::_Tree<std::_Tmap_traits<_GUID,enum _WWAN_RADIO,GuidLessThan,std::allocator<std::pair<_GUID const,enum _WWAN_RADIO>>,0>>::~_Tree<std::_Tmap_traits<_GUID,enum _WWAN_RADIO,GuidLessThan,std::allocator<std::pair<_GUID const,enum _WWAN_RADIO>>,0>>(&this[4].OwningThread);
  std::_Tree<std::_Tmap_traits<_GUID,enum _WWAN_RADIO,GuidLessThan,std::allocator<std::pair<_GUID const,enum _WWAN_RADIO>>,0>>::~_Tree<std::_Tmap_traits<_GUID,enum _WWAN_RADIO,GuidLessThan,std::allocator<std::pair<_GUID const,enum _WWAN_RADIO>>,0>>(&this[4]);
}

```

## disassembly

```asm
0x180090294  push    rbx
0x180090296  sub     rsp, 20h
0x18009029a  mov     rbx, rcx
0x18009029d  call    cs:__imp_DeleteCriticalSection
0x1800902a3  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800902a7  call    cs:__imp_DeleteCriticalSection
0x1800902ad  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800902b1  call    cs:__imp_DeleteCriticalSection
0x1800902b7  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800902bb  call    cs:__imp_DeleteCriticalSection
0x1800902c1  lea     rcx, [rbx+0C0h]
0x1800902c8  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@PEAUWWAN_INTERFACE_INFO@@UGuidLessThan@@V?$allocator@U?$pair@$$CBU_GUID@@PEAUWWAN_INTERFACE_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,WWAN_INTERFACE_INFO *,GuidLessThan,std::allocator<std::pair<_GUID const,WWAN_INTERFACE_INFO *>>,0>>::~_Tree<std::_Tmap_traits<_GUID,WWAN_INTERFACE_INFO *,GuidLessThan,std::allocator<std::pair<_GUID const,WWAN_INTERFACE_INFO *>>,0>>(void)
0x1800902cd  lea     rcx, [rbx+0B0h]
0x1800902d4  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@W4_WWAN_RADIO@@UGuidLessThan@@V?$allocator@U?$pair@$$CBU_GUID@@W4_WWAN_RADIO@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,_WWAN_RADIO,GuidLessThan,std::allocator<std::pair<_GUID const,_WWAN_RADIO>>,0>>::~_Tree<std::_Tmap_traits<_GUID,_WWAN_RADIO,GuidLessThan,std::allocator<std::pair<_GUID const,_WWAN_RADIO>>,0>>(void)
0x1800902d9  lea     rcx, [rbx+0A0h]
0x1800902e0  add     rsp, 20h
0x1800902e4  pop     rbx
0x1800902e5  jmp     ??1?$_Tree@V?$_Tmap_traits@U_GUID@@W4_WWAN_RADIO@@UGuidLessThan@@V?$allocator@U?$pair@$$CBU_GUID@@W4_WWAN_RADIO@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,_WWAN_RADIO,GuidLessThan,std::allocator<std::pair<_GUID const,_WWAN_RADIO>>,0>>::~_Tree<std::_Tmap_traits<_GUID,_WWAN_RADIO,GuidLessThan,std::allocator<std::pair<_GUID const,_WWAN_RADIO>>,0>>(void)
```
