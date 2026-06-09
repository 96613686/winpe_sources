# GetVector(MglPoint<double> const &)

- ea: `0x100406e60`
- end: `0x100406f6b`
- name: `?GetVector@@YA?AVCPoint3D@@AEBU?$MglPoint@N@@@Z`
- size: `267`
- prototype: ``
- caller_count: `45`
- callee_count: `4`
- tags: ``

## callers

- `0x100408880`
- `0x100408cf0`
- `0x100408f60`
- `0x10040b910`
- `0x100417750`
- `0x100418280`
- `0x100426fe0`
- `0x10044efe0`
- `0x100451770`
- `0x100451bd0`
- `0x100452a00`
- `0x100454aa0`
- `0x100454ba0`
- `0x100454d20`
- `0x100454e20`
- `0x100454e70`
- `0x100455030`
- `0x100455270`
- `0x100459930`
- `0x100459ab0`
- `0x100459e10`
- `0x10045a5d0`
- `0x10045a620`
- `0x10045a7c0`
- `0x10045adc0`
- `0x10045de10`
- `0x10045e0c0`
- `0x10045e330`
- `0x10045e610`
- `0x10045ebb0`
- `0x10045ec90`
- `0x10045eec0`
- `0x10045f780`
- `0x10045f7c0`
- `0x10045f970`
- `0x100460a50`
- `0x100461120`
- `0x100461220`
- `0x100461610`
- `0x100461c30`
- `0x100465d20`
- `0x100466090`
- `0x100466290`
- `0x100466cc0`
- `0x100466e50`

## callees

- `0x100406e60`
- `0x100469ab0`
- `0x100469ac8`
- `0x100469aec`

## pseudocode

```c
double *__fastcall GetVector(double *a1, double *a2)
{
  double v4; // xmm8_8
  double v5; // xmm7_8
  double v6; // xmm8_8
  double v7; // xmm6_8
  double v8; // xmm0_8
  double *result; // rax

  v4 = a2[1];
  if ( v4 > -180.0 )
  {
    if ( v4 > 180.0 )
    {
      v4 = fmod_0(v4 + 180.0, 360.0) - 180.0;
      if ( v4 == -180.0 )
        *(_QWORD *)&v4 ^= _xmm;
    }
  }
  else
  {
    v4 = fmod_0(v4 - 180.0, 360.0) + 180.0;
  }
  v5 = *a2 * 0.0174532925199433;
  v6 = v4 * 0.0174532925199433;
  v7 = cos_0(v5);
  *a1 = cos_0(v6) * v7;
  a1[1] = sin_0(v6) * v7;
  v8 = sin_0(v5);
  result = a1;
  a1[2] = v8;
  return result;
}

```

## disassembly

```asm
0x100406e60  mov     [rsp+arg_0], rbx
0x100406e65  push    rdi
0x100406e66  sub     rsp, 50h
0x100406e6a  movaps  [rsp+58h+var_18], xmm6
0x100406e6f  mov     rbx, rdx
0x100406e72  movaps  [rsp+58h+var_28], xmm7
0x100406e77  mov     rdi, rcx
0x100406e7a  movsd   xmm7, cs:__real@c066800000000000
0x100406e82  movaps  [rsp+58h+var_38], xmm8
0x100406e88  movsd   xmm8, qword ptr [rdx+8]
0x100406e8e  comisd  xmm7, xmm8
0x100406e93  jb      short loc_100406EBE
0x100406e95  subsd   xmm8, cs:__real@4066800000000000
0x100406e9e  movsd   xmm1, cs:__real@4076800000000000; Y
0x100406ea6  movaps  xmm0, xmm8; X
0x100406eaa  call    fmod_0
0x100406eaf  movaps  xmm8, xmm0
0x100406eb3  addsd   xmm8, cs:__real@4066800000000000
0x100406ebc  jmp     short loc_100406EFD
0x100406ebe  movsd   xmm6, cs:__real@4066800000000000
0x100406ec6  comisd  xmm8, xmm6
0x100406ecb  jbe     short loc_100406EFD
0x100406ecd  movsd   xmm1, cs:__real@4076800000000000; Y
0x100406ed5  addsd   xmm8, xmm6
0x100406eda  movaps  xmm0, xmm8; X
0x100406ede  call    fmod_0
0x100406ee3  movaps  xmm8, xmm0
0x100406ee7  subsd   xmm8, xmm6
0x100406eec  ucomisd xmm8, xmm7
0x100406ef1  jp      short loc_100406EFD
0x100406ef3  jnz     short loc_100406EFD
0x100406ef5  xorps   xmm8, cs:__xmm@80000000000000008000000000000000
0x100406efd  movsd   xmm7, qword ptr [rbx]
0x100406f01  mulsd   xmm7, cs:__real@3f91df46a2529d39
0x100406f09  mulsd   xmm8, cs:__real@3f91df46a2529d39
0x100406f12  movaps  xmm0, xmm7; X
0x100406f15  call    cos_0
0x100406f1a  movaps  xmm6, xmm0
0x100406f1d  movaps  xmm0, xmm8; X
0x100406f21  call    cos_0
0x100406f26  mulsd   xmm0, xmm6
0x100406f2a  movsd   qword ptr [rdi], xmm0
0x100406f2e  movaps  xmm0, xmm8; X
0x100406f32  call    sin_0
0x100406f37  mulsd   xmm0, xmm6
0x100406f3b  movsd   qword ptr [rdi+8], xmm0
0x100406f40  movaps  xmm0, xmm7; X
0x100406f43  call    sin_0
0x100406f48  mov     rbx, [rsp+58h+arg_0]
0x100406f4d  mov     rax, rdi
0x100406f50  movaps  xmm6, [rsp+58h+var_18]
0x100406f55  movaps  xmm7, [rsp+58h+var_28]
0x100406f5a  movaps  xmm8, [rsp+58h+var_38]
0x100406f60  movsd   qword ptr [rdi+10h], xmm0
0x100406f65  add     rsp, 50h
0x100406f69  pop     rdi
0x100406f6a  retn
```
