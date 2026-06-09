# std::exception::exception(char const * const)

- ea: `0x180003a10`
- end: `0x180003a51`
- name: `??0exception@std@@QEAA@QEBD@Z`
- size: `65`
- prototype: `__int64 __fastcall(std::exception *__hidden this, const char *const)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002030`
- `0x1800024e0`
- `0x1800026b0`

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x180003a42`
- `VCRUNTIME140!__std_exception_copy` at `0x180003a42`

## pseudocode

```c
std::exception *__fastcall std::exception::exception(std::exception *this, const char *a2)
{
  const char *v4; // [rsp+20h] [rbp-18h] BYREF
  char v5; // [rsp+28h] [rbp-10h]

  v5 = 1;
  v4 = a2;
  *(_QWORD *)this = &std::exception::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  __std_exception_copy(&v4);
  return this;
}

```

## disassembly

```asm
0x180003a10  push    rbx
0x180003a12  sub     rsp, 30h
0x180003a16  mov     rbx, rcx
0x180003a19  mov     [rsp+38h+var_10], 1
0x180003a1e  mov     rax, rdx
0x180003a21  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180003a28  lea     rdx, [rbx+8]
0x180003a2c  mov     [rsp+38h+var_18], rax
0x180003a31  mov     [rbx], rcx
0x180003a34  xor     ecx, ecx
0x180003a36  mov     [rdx], rcx
0x180003a39  mov     [rdx+8], rcx
0x180003a3d  lea     rcx, [rsp+38h+var_18]
0x180003a42  call    cs:__imp___std_exception_copy
0x180003a48  mov     rax, rbx
0x180003a4b  add     rsp, 30h
0x180003a4f  pop     rbx
0x180003a50  retn
```
