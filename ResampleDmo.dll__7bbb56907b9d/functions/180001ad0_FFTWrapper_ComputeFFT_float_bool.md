# FFTWrapper::ComputeFFT(float *,bool)

- ea: `0x180001ad0`
- end: `0x180001b2c`
- name: `?ComputeFFT@FFTWrapper@@QEAAXPEAM_N@Z`
- size: `92`
- prototype: `void __fastcall(FFTWrapper *__hidden this, float *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001790`

## callees

- `0x180001ad0`
- `0x180001b90`

## pseudocode

```c
void __fastcall FFTWrapper::ComputeFFT(FFTWrapper *this, float *a2)
{
  int v2; // r10d
  int v3; // r9d
  float *v4; // r8
  float *i; // rax
  float v6; // xmm0_4
  float v7; // xmm0_4

  v2 = *((_DWORD *)this + 8);
  v3 = 0;
  v4 = (float *)*((_QWORD *)this + 3);
  for ( i = a2; v3 < v2; v2 = *((_DWORD *)this + 8) )
  {
    v6 = *v4++;
    v7 = v6 * *i++;
    ++v3;
    *(i - 1) = v7;
  }
  FFTWrapper::CFloatFft_realCore(this, a2, v2, *((_DWORD *)this + 9), *((float **)this + 2));
}

```

## disassembly

```asm
0x180001ad0  sub     rsp, 38h
0x180001ad4  mov     r10d, [rcx+20h]
0x180001ad8  xor     r9d, r9d
0x180001adb  mov     r8, [rcx+18h]
0x180001adf  mov     rax, rdx
0x180001ae2  test    r10d, r10d
0x180001ae5  jle     short loc_180001B12
0x180001ae7  nop     word ptr [rax+rax+00000000h]
0x180001af0  movss   xmm0, dword ptr [r8]
0x180001af5  lea     r8, [r8+4]
0x180001af9  mulss   xmm0, dword ptr [rax]
0x180001afd  lea     rax, [rax+4]
0x180001b01  inc     r9d
0x180001b04  movss   dword ptr [rax-4], xmm0
0x180001b09  mov     r10d, [rcx+20h]
0x180001b0d  cmp     r9d, r10d
0x180001b10  jl      short loc_180001AF0
0x180001b12  mov     rax, [rcx+10h]
0x180001b16  mov     r8d, r10d; int
0x180001b19  mov     r9d, [rcx+24h]; int
0x180001b1d  mov     [rsp+38h+var_18], rax; float *
0x180001b22  call    ?CFloatFft_realCore@FFTWrapper@@AEAAXPEAMJJ0@Z; FFTWrapper::CFloatFft_realCore(float *,long,long,float *)
0x180001b27  add     rsp, 38h
0x180001b2b  retn
```
