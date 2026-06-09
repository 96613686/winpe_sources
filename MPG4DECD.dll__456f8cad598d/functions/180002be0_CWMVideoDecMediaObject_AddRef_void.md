# CWMVideoDecMediaObject::AddRef(void)

- ea: `0x180002be0`
- end: `0x180002bf3`
- name: `?AddRef@CWMVideoDecMediaObject@@UEAAKXZ`
- size: `19`
- prototype: `unsigned int __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c00`
- `0x180002c20`
- `0x180002c40`
- `0x180002c60`
- `0x180002c80`

## callees

- `0x180022010`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::AddRef(CWMVideoDecMediaObject *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 8LL))(*((_QWORD *)this + 42));
}

```

## disassembly

```asm
0x180002be0  mov     rcx, [rcx+150h]
0x180002be7  mov     rax, [rcx]
0x180002bea  mov     rax, [rax+8]
0x180002bee  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
