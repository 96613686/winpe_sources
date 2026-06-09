# CBusNode::CCreateContext::CCreateContext(void)

- ea: `0x1800083dc`
- end: `0x1800083ec`
- name: `??0CCreateContext@CBusNode@@QEAA@XZ`
- size: `16`
- prototype: `CBusNode::CCreateContext *__fastcall(CBusNode::CCreateContext *this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180008c14`

## pseudocode

```c
CBusNode::CCreateContext *__fastcall CBusNode::CCreateContext::CCreateContext(CBusNode::CCreateContext *this)
{
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  return this;
}

```

## disassembly

```asm
0x1800083dc  xor     eax, eax
0x1800083de  mov     [rcx], rax
0x1800083e1  mov     [rcx+8], eax
0x1800083e4  mov     [rcx+10h], rax
0x1800083e8  mov     rax, rcx
0x1800083eb  retn
```
