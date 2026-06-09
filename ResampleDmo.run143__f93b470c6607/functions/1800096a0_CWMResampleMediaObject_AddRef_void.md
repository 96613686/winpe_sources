# CWMResampleMediaObject::AddRef(void)

- ea: `0x1800096a0`
- end: `0x1800096b0`
- name: `?AddRef@CWMResampleMediaObject@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CWMResampleMediaObject *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18006ae30`
- `0x18006ae40`
- `0x18006ae60`
- `0x18006ae80`
- `0x18006aea0`
- `0x180080d80`
- `0x180080da0`
- `0x180080dc0`
- `0x180080de0`

## callees

- `0x180085010`

## pseudocode

```c
__int64 __fastcall CWMResampleMediaObject::AddRef(CWMResampleMediaObject *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this - 2) + 8LL))(*((_QWORD *)this - 2));
}

```

## disassembly

```asm
0x1800096a0  mov     rcx, [rcx-10h]
0x1800096a4  mov     rax, [rcx]
0x1800096a7  mov     rax, [rax+8]
0x1800096ab  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
