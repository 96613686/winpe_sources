# std::vector<uchar,std::allocator<uchar>>::vector<uchar,std::allocator<uchar>>(unsigned __int64)

- ea: `0x18000d710`
- end: `0x18000d734`
- name: `??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_K@Z`
- size: `36`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eec0`
- `0x18000efe8`
- `0x18000f140`
- `0x18000f268`
- `0x18000f378`
- `0x180010548`

## callees

- `0x18000ee40`

## pseudocode

```c
_QWORD *__fastcall std::vector<unsigned char>::vector<unsigned char>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  std::vector<unsigned char>::resize();
  return a1;
}

```

## disassembly

```asm
0x18000d710  push    rbx
0x18000d712  sub     rsp, 20h
0x18000d716  xor     eax, eax
0x18000d718  mov     rbx, rcx
0x18000d71b  mov     [rcx], rax
0x18000d71e  mov     [rcx+8], rax
0x18000d722  mov     [rcx+10h], rax
0x18000d726  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000d72b  mov     rax, rbx
0x18000d72e  add     rsp, 20h
0x18000d732  pop     rbx
0x18000d733  retn
```
