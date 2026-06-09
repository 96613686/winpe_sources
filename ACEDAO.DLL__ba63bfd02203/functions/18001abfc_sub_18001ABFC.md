# sub_18001ABFC

- ea: `0x18001abfc`
- end: `0x18001ac2f`
- name: `sub_18001ABFC`
- size: `51`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x18001ac20`
- `VCRUNTIME140!__std_exception_copy` at `0x18001ac20`

## pseudocode

```c
__int64 __fastcall sub_18001ABFC(__int64 a1, __int64 a2)
{
  *(_QWORD *)a1 = &std::exception::`vftable';
  *(_OWORD *)(a1 + 8) = 0;
  _std_exception_copy(a2 + 8);
  return a1;
}

```

## disassembly

```asm
0x18001abfc  push    rbx
0x18001abfe  sub     rsp, 20h
0x18001ac02  mov     rbx, rcx
0x18001ac05  mov     rax, rdx
0x18001ac08  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18001ac0f  xorps   xmm0, xmm0
0x18001ac12  mov     [rbx], rcx
0x18001ac15  lea     rdx, [rbx+8]
0x18001ac19  lea     rcx, [rax+8]
0x18001ac1d  movups  xmmword ptr [rdx], xmm0
0x18001ac20  call    cs:__std_exception_copy
0x18001ac26  mov     rax, rbx
0x18001ac29  add     rsp, 20h
0x18001ac2d  pop     rbx
0x18001ac2e  retn
```
