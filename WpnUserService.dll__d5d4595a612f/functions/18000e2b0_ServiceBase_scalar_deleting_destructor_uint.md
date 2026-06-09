# ServiceBase::`scalar deleting destructor'(uint)

- ea: `0x18000e2b0`
- end: `0x18000e2e4`
- name: `??_GServiceBase@@UEAAPEAXI@Z`
- size: `52`
- prototype: `ServiceBase *__fastcall(ServiceBase *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180002f90`
- `0x18000ddf8`
- `0x18000e2b0`

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
0x18000e2b0  mov     [rsp+arg_0], rbx
0x18000e2b5  push    rdi
0x18000e2b6  sub     rsp, 20h
0x18000e2ba  mov     ebx, edx
0x18000e2bc  mov     rdi, rcx
0x18000e2bf  call    ??1ServiceBase@@UEAA@XZ; ServiceBase::~ServiceBase(void)
0x18000e2c4  test    bl, 1
0x18000e2c7  jz      short loc_18000E2D6
0x18000e2c9  mov     edx, 0C0h; unsigned __int64
0x18000e2ce  mov     rcx, rdi; void *
0x18000e2d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e2d6  mov     rbx, [rsp+28h+arg_0]
0x18000e2db  mov     rax, rdi
0x18000e2de  add     rsp, 20h
0x18000e2e2  pop     rdi
0x18000e2e3  retn
```
