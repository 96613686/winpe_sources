# DAV_STRING_VIEW::DAV_STRING_VIEW(void)

- ea: `0x180003550`
- end: `0x18000355d`
- name: `??0DAV_STRING_VIEW@@QEAA@XZ`
- size: `13`
- prototype: `DAV_STRING_VIEW *__fastcall(DAV_STRING_VIEW *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ba0`
- `0x180003300`

## pseudocode

```c
DAV_STRING_VIEW *__fastcall DAV_STRING_VIEW::DAV_STRING_VIEW(DAV_STRING_VIEW *this)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  return this;
}

```

## disassembly

```asm
0x180003550  xor     eax, eax
0x180003552  mov     [rcx], rax
0x180003555  mov     [rcx+8], rax
0x180003559  mov     rax, rcx
0x18000355c  retn
```
