# rFFT_norm_1

- ea: `0x18000cb90`
- end: `0x18000cb99`
- name: `rFFT_norm_1`
- size: `9`
- prototype: ``
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d370`
- `0x18000d54c`
- `0x18000dd90`
- `0x18000e0cc`
- `0x18000e560`
- `0x18000e760`
- `0x18000efb0`
- `0x18000f364`
- `0x18000f820`
- `0x18000fa20`
- `0x180010270`
- `0x180010624`
- `0x180047c40`
- `0x1800483c0`
- `0x180048ab0`
- `0x180049220`
- `0x180049840`
- `0x180049fb0`

## pseudocode

```c
void __fastcall rFFT_norm_1(float *a1, float *a2, float a3)
{
  *a2 = a3 * *a1;
}

```

## disassembly

```asm
0x18000cb90  mulss   xmm2, dword ptr [rcx]
0x18000cb94  movss   dword ptr [rdx], xmm2
0x18000cb98  retn
```
