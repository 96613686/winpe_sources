# std::bad_array_new_length::bad_array_new_length(void)

- ea: `0x180001d8c`
- end: `0x180001dad`
- name: `??0bad_array_new_length@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(std::bad_array_new_length *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e7c`

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
0x180001d8c  lea     rax, aBadArrayNewLen; "bad array new length"
0x180001d93  mov     qword ptr [rcx+10h], 0
0x180001d9b  mov     [rcx+8], rax
0x180001d9f  lea     rax, ??_7bad_array_new_length@std@@6B@; const std::bad_array_new_length::`vftable'
0x180001da6  mov     [rcx], rax
0x180001da9  mov     rax, rcx
0x180001dac  retn
```
