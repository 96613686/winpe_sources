# Completion::~Completion(void)

- ea: `0x1400056bc`
- end: `0x1400056c7`
- name: `??1Completion@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(Completion *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000366c`

## pseudocode

```c
void __fastcall Completion::~Completion(Completion *this)
{
  *(_QWORD *)this = &Completion::`vftable';
}

```

## disassembly

```asm
0x1400056bc  lea     rax, ??_7Completion@@6B@; const Completion::`vftable'
0x1400056c3  mov     [rcx], rax
0x1400056c6  retn
```
