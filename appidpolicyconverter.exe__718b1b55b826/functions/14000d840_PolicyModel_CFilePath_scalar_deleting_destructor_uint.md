# PolicyModel::CFilePath::`scalar deleting destructor'(uint)

- ea: `0x14000d840`
- end: `0x14000d86f`
- name: `??_GCFilePath@PolicyModel@@UEAAPEAXI@Z`
- size: `47`
- prototype: `PolicyModel::CFilePath *__fastcall(PolicyModel::CFilePath *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x14000d820`

## callees

- `0x14000157c`
- `0x14000d840`
- `0x14000db9c`

## pseudocode

```c
PolicyModel::CFilePath *__fastcall PolicyModel::CFilePath::`scalar deleting destructor'(
        PolicyModel::CFilePath *this,
        __int64 a2)
{
  char v2; // bl

  v2 = a2;
  PolicyModel::CFilePath::~CFilePath(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000d840  mov     [rsp+arg_0], rbx
0x14000d845  push    rdi
0x14000d846  sub     rsp, 20h
0x14000d84a  mov     ebx, edx
0x14000d84c  mov     rdi, rcx
0x14000d84f  call    ??1CFilePath@PolicyModel@@UEAA@XZ; PolicyModel::CFilePath::~CFilePath(void)
0x14000d854  test    bl, 1
0x14000d857  jz      short loc_14000D861
0x14000d859  mov     rcx, rdi; Block
0x14000d85c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000d861  mov     rbx, [rsp+28h+arg_0]
0x14000d866  mov     rax, rdi
0x14000d869  add     rsp, 20h
0x14000d86d  pop     rdi
0x14000d86e  retn
```
