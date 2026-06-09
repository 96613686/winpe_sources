# PacReadFcn(void *,char * *,uint *)

- ea: `0x140036e40`
- end: `0x140036e53`
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
0x140036e40  mov     rax, [rcx]
0x140036e43  mov     [rdx], rax
0x140036e46  mov     eax, [r8]
0x140036e49  add     [rcx], rax
0x140036e4c  mov     eax, [r8]
0x140036e4f  sub     [rcx+8], eax
0x140036e52  retn
```
