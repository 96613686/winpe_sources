# _atexit

- ea: `0x40d4c8`
- end: `0x40d4dd`
- name: `_atexit`
- size: `21`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x401290`
- `0x4012b0`
- `0x4012d0`
- `0x4012f0`
- `0x401300`
- `0x401320`
- `0x401340`
- `0x401360`
- `0x401380`
- `0x4013a0`
- `0x4013c0`
- `0x4013e0`
- `0x401400`
- `0x401420`
- `0x401440`
- `0x401450`
- `0x401460`
- `0x401480`
- `0x4015fb`
- `0x40d0a0`
- `0x40d4f0`

## callees

- `0x40d49b`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *Func)())
{
  return (_onexit((_onexit_t)Func) != 0) - 1;
}

```

## disassembly

```asm
0x40d4c8  push    ebp
0x40d4c9  mov     ebp, esp
0x40d4cb  push    [ebp+Func]; Func
0x40d4ce  call    __onexit
0x40d4d3  neg     eax
0x40d4d5  pop     ecx
0x40d4d6  sbb     eax, eax
0x40d4d8  neg     eax
0x40d4da  dec     eax
0x40d4db  pop     ebp
0x40d4dc  retn
```
