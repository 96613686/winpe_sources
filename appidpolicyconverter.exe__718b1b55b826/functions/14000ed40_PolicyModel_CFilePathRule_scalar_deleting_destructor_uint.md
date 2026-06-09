# PolicyModel::CFilePathRule::`scalar deleting destructor'(uint)

- ea: `0x14000ed40`
- end: `0x14000ed6f`
- name: `??_GCFilePathRule@PolicyModel@@UEAAPEAXI@Z`
- size: `47`
- prototype: `PolicyModel::CFilePathRule *__fastcall(PolicyModel::CFilePathRule *this, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x14000ed30`

## callees

- `0x14000157c`
- `0x14000eccc`
- `0x14000ed40`

## pseudocode

```c
PolicyModel::CFilePathRule *__fastcall PolicyModel::CFilePathRule::`scalar deleting destructor'(
        PolicyModel::CFilePathRule *this,
        char a2)
{
  PolicyModel::CFilePathRule::~CFilePathRule(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000ed40  mov     [rsp+arg_0], rbx
0x14000ed45  push    rdi
0x14000ed46  sub     rsp, 20h
0x14000ed4a  mov     ebx, edx
0x14000ed4c  mov     rdi, rcx
0x14000ed4f  call    ??1CFilePathRule@PolicyModel@@UEAA@XZ; PolicyModel::CFilePathRule::~CFilePathRule(void)
0x14000ed54  test    bl, 1
0x14000ed57  jz      short loc_14000ED61
0x14000ed59  mov     rcx, rdi; Block
0x14000ed5c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000ed61  mov     rbx, [rsp+28h+arg_0]
0x14000ed66  mov     rax, rdi
0x14000ed69  add     rsp, 20h
0x14000ed6d  pop     rdi
0x14000ed6e  retn
```
