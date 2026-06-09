# IIsSchemaClass::Delete(void *)

- ea: `0x18001a0a0`
- end: `0x18001a0c0`
- name: `?Delete@IIsSchemaClass@@SAXPEAX@Z`
- size: `32`
- prototype: `void __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800010f0`
- `0x180019bec`
- `0x18001a0a0`

## pseudocode

```c
void __fastcall IIsSchemaClass::Delete(void **Block)
{
  if ( Block )
  {
    IIsSchemaClass::~IIsSchemaClass(Block);
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x18001a0a0  test    rcx, rcx
0x18001a0a3  jz      short locret_18001A0BF
0x18001a0a5  push    rbx
0x18001a0a6  sub     rsp, 20h
0x18001a0aa  mov     rbx, rcx
0x18001a0ad  call    ??1IIsSchemaClass@@QEAA@XZ
0x18001a0b2  mov     rcx, rbx; Block
0x18001a0b5  call    ??3@YAXPEAX@Z
0x18001a0ba  add     rsp, 20h
0x18001a0be  pop     rbx
0x18001a0bf  retn
```
