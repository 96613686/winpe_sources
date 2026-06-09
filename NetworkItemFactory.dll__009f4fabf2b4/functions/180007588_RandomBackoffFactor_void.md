# RandomBackoffFactor(void)

- ea: `0x180007588`
- end: `0x1800075b8`
- name: `?RandomBackoffFactor@@YANXZ`
- size: `48`
- prototype: `double(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800075f0`
- `0x1800076c8`
- `0x1800077fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000758c`
- `KERNEL32!GetCurrentThreadId` at `0x18000758c`

## pseudocode

```c
double RandomBackoffFactor(void)
{
  return *(double *)&qword_18000E4F0[GetCurrentThreadId() % 0xD];
}

```

## disassembly

```asm
0x180007588  sub     rsp, 28h
0x18000758c  call    cs:__imp_GetCurrentThreadId
0x180007592  mov     r8d, eax
0x180007595  mov     eax, 4EC4EC4Fh
0x18000759a  mul     r8d
0x18000759d  shr     edx, 2
0x1800075a0  imul    ecx, edx, 0Dh
0x1800075a3  sub     r8d, ecx
0x1800075a6  lea     rcx, qword_18000E4F0
0x1800075ad  movsd   xmm0, qword ptr [rcx+r8*8]
0x1800075b3  add     rsp, 28h
0x1800075b7  retn
```
