# PacReadFcn(void *,char * *,uint *)

- ea: `0x180027fa0`
- end: `0x180027fb3`
- name: `?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z`
- size: `19`
- prototype: `void __stdcall(void *state, char **pbuffer, unsigned int *psize)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall PacReadFcn(_DWORD *state, char **pbuffer, unsigned int *psize)
{
  *pbuffer = *(char **)state;
  *(_QWORD *)state += *psize;
  state[2] -= *psize;
}

```

## disassembly

```asm
0x180027fa0  mov     rax, [rcx]
0x180027fa3  mov     [rdx], rax
0x180027fa6  mov     eax, [r8]
0x180027fa9  add     [rcx], rax
0x180027fac  mov     eax, [r8]
0x180027faf  sub     [rcx+8], eax
0x180027fb2  retn
```
