# std::length_error::length_error(char const *)

- ea: `0x14000492c`
- end: `0x140004981`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `85`
- prototype: `std::length_error *__fastcall(std::length_error *this, const char *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400049cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x140004968`
- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x140004968`

## pseudocode

```c
std::length_error *__fastcall std::length_error::length_error(std::length_error *this, const char *a2)
{
  const char *v4; // [rsp+20h] [rbp-18h] BYREF
  char v5; // [rsp+28h] [rbp-10h]
  int v6; // [rsp+29h] [rbp-Fh]
  __int16 v7; // [rsp+2Dh] [rbp-Bh]
  char v8; // [rsp+2Fh] [rbp-9h]

  v4 = a2;
  v5 = 1;
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  __std_exception_copy(&v4);
  *(_QWORD *)this = &std::length_error::`vftable';
  return this;
}

```

## disassembly

```asm
0x14000492c  push    rbx
0x14000492e  sub     rsp, 30h
0x140004932  mov     rbx, rcx
0x140004935  mov     [rsp+38h+var_18], rdx
0x14000493a  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x140004941  mov     [rsp+38h+var_10], 1
0x140004946  mov     [rcx], rax
0x140004949  xorps   xmm0, xmm0
0x14000494c  movups  xmmword ptr [rcx+8], xmm0
0x140004950  xor     ecx, ecx
0x140004952  lea     rdx, [rbx+8]
0x140004956  mov     [rsp+38h+var_F], ecx
0x14000495a  mov     [rsp+38h+var_B], cx
0x14000495f  mov     [rsp+38h+var_9], cl
0x140004963  lea     rcx, [rsp+38h+var_18]
0x140004968  call    cs:__imp___std_exception_copy
0x14000496e  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x140004975  mov     [rbx], rax
0x140004978  mov     rax, rbx
0x14000497b  add     rsp, 30h
0x14000497f  pop     rbx
0x140004980  retn
```
