# _atexit

- ea: `0x40cd9f`
- end: `0x40cdb6`
- name: `_atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x402560`
- `0x4025c0`
- `0x4025e0`

## callees

- `0x40ccf0`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *Func)())
{
  return (_onexit((_onexit_t)Func) != 0) - 1;
}

```

## disassembly

```asm
0x40cd9f  mov     edi, edi
0x40cda1  push    ebp
0x40cda2  mov     ebp, esp
0x40cda4  push    [ebp+Func]; Func
0x40cda7  call    __onexit
0x40cdac  neg     eax
0x40cdae  pop     ecx
0x40cdaf  sbb     eax, eax
0x40cdb1  neg     eax
0x40cdb3  dec     eax
0x40cdb4  pop     ebp
0x40cdb5  retn
```
