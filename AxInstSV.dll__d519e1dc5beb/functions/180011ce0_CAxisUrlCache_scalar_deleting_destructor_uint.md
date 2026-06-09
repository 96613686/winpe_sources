# CAxisUrlCache::`scalar deleting destructor'(uint)

- ea: `0x180011ce0`
- end: `0x180011d14`
- name: `??_GCAxisUrlCache@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CAxisUrlCache *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001744`
- `0x180011c74`
- `0x180011ce0`

## pseudocode

```c
CAxisUrlCache *__fastcall CAxisUrlCache::`scalar deleting destructor'(CAxisUrlCache *this, char a2)
{
  CAxisUrlCache::~CAxisUrlCache(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180011ce0  mov     [rsp+arg_0], rbx
0x180011ce5  push    rdi
0x180011ce6  sub     rsp, 20h
0x180011cea  mov     ebx, edx
0x180011cec  mov     rdi, rcx
0x180011cef  call    ??1CAxisUrlCache@@UEAA@XZ; CAxisUrlCache::~CAxisUrlCache(void)
0x180011cf4  test    bl, 1
0x180011cf7  jz      short loc_180011D06
0x180011cf9  mov     edx, 80h
0x180011cfe  mov     rcx, rdi; Block
0x180011d01  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011d06  mov     rbx, [rsp+28h+arg_0]
0x180011d0b  mov     rax, rdi
0x180011d0e  add     rsp, 20h
0x180011d12  pop     rdi
0x180011d13  retn
```
