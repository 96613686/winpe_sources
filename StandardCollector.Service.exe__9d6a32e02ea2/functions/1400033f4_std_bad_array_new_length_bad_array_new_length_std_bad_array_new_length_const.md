# std::bad_array_new_length::bad_array_new_length(std::bad_array_new_length const &)

- ea: `0x1400033f4`
- end: `0x140003431`
- name: `??0bad_array_new_length@std@@QEAA@AEBV01@@Z`
- size: `61`
- prototype: `std::bad_array_new_length *__fastcall(std::bad_array_new_length *this, const struct std::bad_array_new_length *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x140003418`
- `VCRUNTIME140!__std_exception_copy` at `0x140003418`

## pseudocode

```c
std::bad_array_new_length *__fastcall std::bad_array_new_length::bad_array_new_length(
        std::bad_array_new_length *this,
        const struct std::bad_array_new_length *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &std::bad_array_new_length::`vftable';
  return this;
}

```

## disassembly

```asm
0x1400033f4  push    rbx
0x1400033f6  sub     rsp, 20h
0x1400033fa  mov     rbx, rcx
0x1400033fd  mov     rax, rdx
0x140003400  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x140003407  xorps   xmm0, xmm0
0x14000340a  mov     [rbx], rcx
0x14000340d  lea     rdx, [rbx+8]
0x140003411  lea     rcx, [rax+8]
0x140003415  movups  xmmword ptr [rdx], xmm0
0x140003418  call    cs:__imp___std_exception_copy
0x14000341e  lea     rax, ??_7bad_array_new_length@std@@6B@; const std::bad_array_new_length::`vftable'
0x140003425  mov     [rbx], rax
0x140003428  mov     rax, rbx
0x14000342b  add     rsp, 20h
0x14000342f  pop     rbx
0x140003430  retn
```
