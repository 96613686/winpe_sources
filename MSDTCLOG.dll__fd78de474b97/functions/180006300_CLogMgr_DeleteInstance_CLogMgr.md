# CLogMgr::DeleteInstance(CLogMgr *)

- ea: `0x180006300`
- end: `0x180006320`
- name: `?DeleteInstance@CLogMgr@@SAXPEAV1@@Z`
- size: `32`
- prototype: `void __fastcall(struct CLogMgr *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x180005ff0`
- `0x180006300`

## pseudocode

```c
void __fastcall CLogMgr::DeleteInstance(void (***Block)(void))
{
  if ( Block )
  {
    CLogMgr::~CLogMgr(Block);
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x180006300  test    rcx, rcx
0x180006303  jz      short locret_18000631F
0x180006305  push    rbx
0x180006306  sub     rsp, 20h
0x18000630a  mov     rbx, rcx
0x18000630d  call    ??1CLogMgr@@QEAA@XZ
0x180006312  mov     rcx, rbx; Block
0x180006315  call    ??3@YAXPEAX@Z
0x18000631a  add     rsp, 20h
0x18000631e  pop     rbx
0x18000631f  retn
```
