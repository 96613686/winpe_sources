# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180008cfc`
- end: `0x180008d20`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a720`
- `0x18000ef10`

## callees

- `0x180001744`
- `0x1800083d0`

## pseudocode

```c
void *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(void *Block)
{
  ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180008cfc  push    rbx
0x180008cfe  sub     rsp, 20h
0x180008d02  mov     rbx, rcx
0x180008d05  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x180008d0a  mov     edx, 48h ; 'H'
0x180008d0f  mov     rcx, rbx; Block
0x180008d12  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008d17  mov     rax, rbx
0x180008d1a  add     rsp, 20h
0x180008d1e  pop     rbx
0x180008d1f  retn
```
