# CRPCServiceManager::`vector deleting destructor'(uint)

- ea: `0x180012470`
- end: `0x1800124a4`
- name: `??_ECRPCServiceManager@@UEAAPEAXI@Z`
- size: `52`
- prototype: `CRPCServiceManager *__fastcall(CRPCServiceManager *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x1800016f4`
- `0x180012424`
- `0x180012470`

## pseudocode

```c
CRPCServiceManager *__fastcall CRPCServiceManager::`vector deleting destructor'(CRPCServiceManager *this, char a2)
{
  CRPCServiceManager::~CRPCServiceManager(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180012470  mov     [rsp+arg_0], rbx
0x180012475  push    rdi
0x180012476  sub     rsp, 20h
0x18001247a  mov     ebx, edx
0x18001247c  mov     rdi, rcx
0x18001247f  call    ??1CRPCServiceManager@@UEAA@XZ; CRPCServiceManager::~CRPCServiceManager(void)
0x180012484  test    bl, 1
0x180012487  jz      short loc_180012496
0x180012489  mov     edx, 90h; unsigned __int64
0x18001248e  mov     rcx, rdi; void *
0x180012491  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012496  mov     rbx, [rsp+28h+arg_0]
0x18001249b  mov     rax, rdi
0x18001249e  add     rsp, 20h
0x1800124a2  pop     rdi
0x1800124a3  retn
```
