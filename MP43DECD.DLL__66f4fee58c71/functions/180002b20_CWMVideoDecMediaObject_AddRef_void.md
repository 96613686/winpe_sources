# CWMVideoDecMediaObject::AddRef(void)

- ea: `0x180002b20`
- end: `0x180002b33`
- name: `?AddRef@CWMVideoDecMediaObject@@UEAAKXZ`
- size: `19`
- prototype: `unsigned int __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b40`
- `0x180002b60`
- `0x180002b80`
- `0x180002ba0`
- `0x180002bc0`

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
0x180002b20  mov     rcx, [rcx+150h]
0x180002b27  mov     rax, [rcx]
0x180002b2a  mov     rax, [rax+8]
0x180002b2e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
