# SIPolicyReadPrimitive

- ea: `0x18002906c`
- end: `0x1800290ca`
- name: `SIPolicyReadPrimitive`
- size: `94`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180025288`
- `0x180025b20`
- `0x180025da4`
- `0x180025e58`
- `0x18002612c`
- `0x18002644c`
- `0x180026624`
- `0x180026788`
- `0x180026938`
- `0x180026b44`
- `0x180026bb8`
- `0x180026de4`
- `0x180028f84`
- `0x1800290d0`

## callees

- `0x180003870`
- `0x18002906c`

## pseudocode

```c
__int64 __fastcall SIPolicyReadPrimitive(__int64 *a1, size_t a2, void *a3)
{
  __int64 v3; // rsi
  __int64 v5; // rcx

  v3 = a1[2];
  v5 = *a1;
  if ( a1[1] - v5 - v3 < a2 )
    return 3236495363LL;
  memcpy_0(a3, (const void *)(v5 + v3), a2);
  a1[2] = v3 + a2;
  return 0;
}

```

## disassembly

```asm
0x18002906c  mov     [rsp+arg_0], rbx
0x180029071  mov     [rsp+arg_8], rsi
0x180029076  push    rdi
0x180029077  sub     rsp, 20h
0x18002907b  mov     rsi, [rcx+10h]
0x18002907f  mov     rbx, rcx
0x180029082  mov     rcx, [rcx]
0x180029085  mov     r9, r8
0x180029088  mov     rdi, rdx
0x18002908b  mov     rax, [rbx+8]
0x18002908f  sub     rax, rcx
0x180029092  sub     rax, rsi
0x180029095  cmp     rax, rdx
0x180029098  jnb     short loc_1800290A1
0x18002909a  mov     eax, 0C0E90003h
0x18002909f  jmp     short loc_1800290BA
0x1800290a1  lea     rdx, [rcx+rsi]; Src
0x1800290a5  mov     r8, rdi; Size
0x1800290a8  mov     rcx, r9; void *
0x1800290ab  call    memcpy_0
0x1800290b0  lea     rax, [rsi+rdi]
0x1800290b4  mov     [rbx+10h], rax
0x1800290b8  xor     eax, eax
0x1800290ba  mov     rbx, [rsp+28h+arg_0]
0x1800290bf  mov     rsi, [rsp+28h+arg_8]
0x1800290c4  add     rsp, 20h
0x1800290c8  pop     rdi
0x1800290c9  retn
```
