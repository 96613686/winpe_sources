# DLL::`scalar deleting destructor'(uint)

- ea: `0x18000a750`
- end: `0x18000a76f`
- name: `??_GDLL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `HMODULE *__fastcall(HMODULE *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800058d8`
- `0x180005994`

## callees

- `0x180002a00`
- `0x18000a840`

## pseudocode

```c
HMODULE *__fastcall DLL::`scalar deleting destructor'(HMODULE *this)
{
  DLL::~DLL(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000a750  push    rbx
0x18000a752  sub     rsp, 20h
0x18000a756  mov     rbx, rcx
0x18000a759  call    ??1DLL@@QEAA@XZ; DLL::~DLL(void)
0x18000a75e  mov     rcx, rbx; void *
0x18000a761  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a766  mov     rax, rbx
0x18000a769  add     rsp, 20h
0x18000a76d  pop     rbx
0x18000a76e  retn
```
