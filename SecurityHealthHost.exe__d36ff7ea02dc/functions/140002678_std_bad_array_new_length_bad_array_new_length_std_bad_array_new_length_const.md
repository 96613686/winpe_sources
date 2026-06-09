# std::bad_array_new_length::bad_array_new_length(std::bad_array_new_length const &)

- ea: `0x140002678`
- end: `0x1400026b5`
- name: `??0bad_array_new_length@std@@QEAA@AEBV01@@Z`
- size: `61`
- prototype: `std::bad_array_new_length *__fastcall(std::bad_array_new_length *this, const struct std::bad_array_new_length *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x14000269c`
- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x14000269c`

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
0x140002678  push    rbx
0x14000267a  sub     rsp, 20h
0x14000267e  mov     rbx, rcx
0x140002681  mov     rax, rdx
0x140002684  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14000268b  xorps   xmm0, xmm0
0x14000268e  mov     [rbx], rcx
0x140002691  lea     rdx, [rbx+8]
0x140002695  lea     rcx, [rax+8]
0x140002699  movups  xmmword ptr [rdx], xmm0
0x14000269c  call    cs:__imp___std_exception_copy
0x1400026a2  lea     rax, ??_7bad_array_new_length@std@@6B@; const std::bad_array_new_length::`vftable'
0x1400026a9  mov     [rbx], rax
0x1400026ac  mov     rax, rbx
0x1400026af  add     rsp, 20h
0x1400026b3  pop     rbx
0x1400026b4  retn
```
