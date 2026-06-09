# StateRepository::CacheContextEntry::`scalar deleting destructor'(uint)

- ea: `0x18000e45c`
- end: `0x18000e480`
- name: `??_GCacheContextEntry@StateRepository@@QEAAPEAXI@Z`
- size: `36`
- prototype: `HKEY *__fastcall(HKEY *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000e3e0`
- `0x18000f5c8`
- `0x18000f760`
- `0x18000f880`

## callees

- `0x1800022a0`
- `0x18000e434`

## pseudocode

```c
HKEY *__fastcall StateRepository::CacheContextEntry::`scalar deleting destructor'(HKEY *this)
{
  StateRepository::CacheContextEntry::~CacheContextEntry(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000e45c  push    rbx
0x18000e45e  sub     rsp, 20h
0x18000e462  mov     rbx, rcx
0x18000e465  call    ??1CacheContextEntry@StateRepository@@QEAA@XZ; StateRepository::CacheContextEntry::~CacheContextEntry(void)
0x18000e46a  mov     edx, 18h; unsigned __int64
0x18000e46f  mov     rcx, rbx; void *
0x18000e472  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e477  mov     rax, rbx
0x18000e47a  add     rsp, 20h
0x18000e47e  pop     rbx
0x18000e47f  retn
```
