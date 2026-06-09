# Completion::Completion(void)

- ea: `0x1400056a0`
- end: `0x1400056b9`
- name: `??0Completion@@QEAA@XZ`
- size: `25`
- prototype: `Completion *__fastcall(Completion *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140003518`

## pseudocode

```c
Completion *__fastcall Completion::Completion(Completion *this)
{
  Completion *result; // rax

  *((_QWORD *)this + 5) = this;
  *(_QWORD *)this = &Completion::`vftable';
  result = this;
  *((_DWORD *)this + 12) = 1;
  return result;
}

```

## disassembly

```asm
0x1400056a0  lea     rax, ??_7Completion@@6B@; const Completion::`vftable'
0x1400056a7  mov     [rcx+28h], rcx
0x1400056ab  mov     [rcx], rax
0x1400056ae  mov     rax, rcx
0x1400056b1  mov     dword ptr [rcx+30h], 1
0x1400056b8  retn
```
