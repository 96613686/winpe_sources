# cFFT_norm_1

- ea: `0x18000bb10`
- end: `0x18000bb26`
- name: `cFFT_norm_1`
- size: `22`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d210`
- `0x18000df70`
- `0x18000e3c0`
- `0x18000f1d0`
- `0x18000f680`
- `0x180010490`
- `0x180047aa0`
- `0x1800486b0`
- `0x180048910`
- `0x180049510`
- `0x1800496a0`
- `0x18004a2a0`

## pseudocode

```c
void __fastcall cFFT_norm_1(float *a1, float *a2, float a3)
{
  *a2 = a3 * *a1;
  a2[1] = a3 * a1[1];
}

```

## disassembly

```asm
0x18000bb10  movaps  xmm0, xmm2
0x18000bb13  mulss   xmm0, dword ptr [rcx]
0x18000bb17  movss   dword ptr [rdx], xmm0
0x18000bb1b  mulss   xmm2, dword ptr [rcx+4]
0x18000bb20  movss   dword ptr [rdx+4], xmm2
0x18000bb25  retn
```
