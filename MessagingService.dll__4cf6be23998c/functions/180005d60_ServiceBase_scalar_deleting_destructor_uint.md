# ServiceBase::`scalar deleting destructor'(uint)

- ea: `0x180005d60`
- end: `0x180005d90`
- name: `??_GServiceBase@@UEAAPEAXI@Z`
- size: `48`
- prototype: `ServiceBase *__fastcall(ServiceBase *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180005d18`
- `0x180005d60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005d7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005d7c`

## pseudocode

```c
ServiceBase *__fastcall ServiceBase::`scalar deleting destructor'(ServiceBase *this, char a2)
{
  ServiceBase::~ServiceBase(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005d60  mov     [rsp+arg_0], rbx
0x180005d65  push    rdi
0x180005d66  sub     rsp, 20h
0x180005d6a  mov     ebx, edx
0x180005d6c  mov     rdi, rcx
0x180005d6f  call    ??1ServiceBase@@UEAA@XZ; ServiceBase::~ServiceBase(void)
0x180005d74  test    bl, 1
0x180005d77  jz      short loc_180005D82
0x180005d79  mov     rcx, rdi
0x180005d7c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005d82  mov     rbx, [rsp+28h+arg_0]
0x180005d87  mov     rax, rdi
0x180005d8a  add     rsp, 20h
0x180005d8e  pop     rdi
0x180005d8f  retn
```
