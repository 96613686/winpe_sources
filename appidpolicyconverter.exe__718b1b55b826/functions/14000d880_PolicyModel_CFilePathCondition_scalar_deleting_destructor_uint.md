# PolicyModel::CFilePathCondition::`scalar deleting destructor'(uint)

- ea: `0x14000d880`
- end: `0x14000d8af`
- name: `??_GCFilePathCondition@PolicyModel@@UEAAPEAXI@Z`
- size: `47`
- prototype: `PolicyModel::CFilePathCondition *__fastcall(PolicyModel::CFilePathCondition *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x14000d830`

## callees

- `0x14000157c`
- `0x14000d7a8`
- `0x14000d880`

## pseudocode

```c
PolicyModel::CFilePathCondition *__fastcall PolicyModel::CFilePathCondition::`scalar deleting destructor'(
        PolicyModel::CFilePathCondition *this,
        __int64 a2)
{
  char v2; // bl

  v2 = a2;
  PolicyModel::CFilePathCondition::~CFilePathCondition(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000d880  mov     [rsp+arg_0], rbx
0x14000d885  push    rdi
0x14000d886  sub     rsp, 20h
0x14000d88a  mov     ebx, edx
0x14000d88c  mov     rdi, rcx
0x14000d88f  call    ??1CFilePathCondition@PolicyModel@@UEAA@XZ; PolicyModel::CFilePathCondition::~CFilePathCondition(void)
0x14000d894  test    bl, 1
0x14000d897  jz      short loc_14000D8A1
0x14000d899  mov     rcx, rdi; Block
0x14000d89c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000d8a1  mov     rbx, [rsp+28h+arg_0]
0x14000d8a6  mov     rax, rdi
0x14000d8a9  add     rsp, 20h
0x14000d8ad  pop     rdi
0x14000d8ae  retn
```
