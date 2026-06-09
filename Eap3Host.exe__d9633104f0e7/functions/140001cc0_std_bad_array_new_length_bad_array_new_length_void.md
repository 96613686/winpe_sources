# std::bad_array_new_length::bad_array_new_length(void)

- ea: `0x140001cc0`
- end: `0x140001ce1`
- name: `??0bad_array_new_length@std@@QEAA@XZ`
- size: `33`
- prototype: `std::bad_array_new_length *__fastcall(std::bad_array_new_length *this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001dac`

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
0x140001cc0  lea     rax, aBadArrayNewLen; "bad array new length"
0x140001cc7  mov     qword ptr [rcx+10h], 0
0x140001ccf  mov     [rcx+8], rax
0x140001cd3  lea     rax, ??_7bad_array_new_length@std@@6B@; const std::bad_array_new_length::`vftable'
0x140001cda  mov     [rcx], rax
0x140001cdd  mov     rax, rcx
0x140001ce0  retn
```
