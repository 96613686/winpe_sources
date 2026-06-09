# std::bad_array_new_length::bad_array_new_length(void)

- ea: `0x180001dec`
- end: `0x180001e0d`
- name: `??0bad_array_new_length@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(std::bad_array_new_length *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001edc`

## pseudocode

```c
std::bad_array_new_length *__fastcall std::bad_array_new_length::bad_array_new_length(std::bad_array_new_length *this)
{
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = "bad array new length";
  *(_QWORD *)this = &std::bad_array_new_length::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001dec  lea     rax, aBadArrayNewLen; "bad array new length"
0x180001df3  mov     qword ptr [rcx+10h], 0
0x180001dfb  mov     [rcx+8], rax
0x180001dff  lea     rax, ??_7bad_array_new_length@std@@6B@; const std::bad_array_new_length::`vftable'
0x180001e06  mov     [rcx], rax
0x180001e09  mov     rax, rcx
0x180001e0c  retn
```
