# CASFDataUnitExtensionObject::`scalar deleting destructor'(uint)

- ea: `0x180016efc`
- end: `0x180016f30`
- name: `??_GCASFDataUnitExtensionObject@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CASFDataUnitExtensionObject *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180016eb0`

## callees

- `0x1800011c0`
- `0x180016e50`
- `0x180016efc`

## pseudocode

```c
CASFDataUnitExtensionObject *__fastcall CASFDataUnitExtensionObject::`scalar deleting destructor'(
        CASFDataUnitExtensionObject *this,
        char a2)
{
  CASFDataUnitExtensionObject::~CASFDataUnitExtensionObject(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180016efc  mov     [rsp+arg_0], rbx
0x180016f01  push    rdi
0x180016f02  sub     rsp, 20h
0x180016f06  mov     ebx, edx
0x180016f08  mov     rdi, rcx
0x180016f0b  call    ??1CASFDataUnitExtensionObject@@UEAA@XZ; CASFDataUnitExtensionObject::~CASFDataUnitExtensionObject(void)
0x180016f10  test    bl, 1
0x180016f13  jz      short loc_180016F22
0x180016f15  mov     edx, 78h ; 'x'
0x180016f1a  mov     rcx, rdi; Block
0x180016f1d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016f22  mov     rbx, [rsp+28h+arg_0]
0x180016f27  mov     rax, rdi
0x180016f2a  add     rsp, 20h
0x180016f2e  pop     rdi
0x180016f2f  retn
```
