# pcmLimiter_Create(uint,uint,float,uint,uint)

- ea: `0x180005dc0`
- end: `0x180005ece`
- name: `?pcmLimiter_Create@@YAPEAUTDLimiter@@IIMII@Z`
- size: `270`
- prototype: `struct TDLimiter *__fastcall(unsigned int, unsigned int, float, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005288`

## callees

- `0x180005dc0`
- `0x180005ed4`
- `0x180041c14`
- `0x18004dcfc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180005dd6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180005df8`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180005e12`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180005dd6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180005df8`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180005e12`

## pseudocode

```c
struct TDLimiter *__fastcall pcmLimiter_Create(__int64 a1, __int64 a2, float a3)
{
  _QWORD *v3; // rbx
  void *v4; // rax
  bool v5; // zf
  __int64 v6; // rdx
  __int64 v7; // r8

  v3 = calloc(1u, 0x68u);
  if ( v3 )
  {
    v3[7] = calloc(0x5A1u, 4u);
    v4 = calloc(0x2D00u, 4u);
    v5 = v3[7] == 0;
    v3[8] = v4;
    if ( !v5 && v4 )
    {
      *((_DWORD *)v3 + 3) = 15;
      *((_DWORD *)v3 + 5) = 15;
      *((_DWORD *)v3 + 4) = 50;
      *(_DWORD *)v3 = 1440;
      *((float *)v3 + 1) = powf(0.1, 0.0006939625);
      *((float *)v3 + 2) = powf(0.1, 0.00020828994);
      *((_DWORD *)v3 + 7) = 8;
      *((_DWORD *)v3 + 8) = 8;
      *((_DWORD *)v3 + 9) = 96000;
      *((_DWORD *)v3 + 10) = 96000;
      *((float *)v3 + 6) = a3;
      *((_DWORD *)v3 + 23) = 4800;
      *((_DWORD *)v3 + 22) = 43200;
      pcmLimiter_Reset(v3, v6, v7);
      return (struct TDLimiter *)v3;
    }
    pcmLimiter_Destroy(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180005dc0  push    rbx
0x180005dc2  sub     rsp, 30h
0x180005dc6  mov     edx, 68h ; 'h'; Size
0x180005dcb  movaps  [rsp+38h+var_18], xmm7
0x180005dd0  movaps  xmm7, xmm2
0x180005dd3  lea     ecx, [rdx-67h]; Count
0x180005dd6  call    cs:__imp_calloc
0x180005ddd  nop     dword ptr [rax+rax+00h]
0x180005de2  mov     rbx, rax
0x180005de5  test    rax, rax
0x180005de8  jz      loc_180005ECA
0x180005dee  mov     edx, 4; Size
0x180005df3  mov     ecx, 5A1h; Count
0x180005df8  call    cs:__imp_calloc
0x180005dff  nop     dword ptr [rax+rax+00h]
0x180005e04  mov     edx, 4; Size
0x180005e09  mov     ecx, 2D00h; Count
0x180005e0e  mov     [rbx+38h], rax
0x180005e12  call    cs:__imp_calloc
0x180005e19  nop     dword ptr [rax+rax+00h]
0x180005e1e  cmp     qword ptr [rbx+38h], 0
0x180005e23  mov     [rbx+40h], rax
0x180005e27  jz      loc_180005EC2
0x180005e2d  test    rax, rax
0x180005e30  jz      loc_180005EC2
0x180005e36  movss   xmm1, cs:__real@3a35eb09; Y
0x180005e3e  mov     eax, 0Fh
0x180005e43  movss   xmm0, cs:__real@3dcccccd; X
0x180005e4b  mov     [rbx+0Ch], eax
0x180005e4e  mov     [rbx+14h], eax
0x180005e51  mov     dword ptr [rbx+10h], 32h ; '2'
0x180005e58  mov     dword ptr [rbx], 5A0h
0x180005e5e  call    powf
0x180005e63  movss   xmm1, cs:__real@395a6868; Y
0x180005e6b  movss   dword ptr [rbx+4], xmm0
0x180005e70  movss   xmm0, cs:__real@3dcccccd; X
0x180005e78  call    powf
0x180005e7d  mov     eax, 8
0x180005e82  movss   dword ptr [rbx+8], xmm0
0x180005e87  mov     [rbx+1Ch], eax
0x180005e8a  mov     rcx, rbx
0x180005e8d  mov     [rbx+20h], eax
0x180005e90  mov     eax, 17700h
0x180005e95  mov     [rbx+24h], eax
0x180005e98  mov     [rbx+28h], eax
0x180005e9b  movss   dword ptr [rbx+18h], xmm7
0x180005ea0  mov     dword ptr [rbx+5Ch], 12C0h
0x180005ea7  mov     dword ptr [rbx+58h], 0A8C0h
0x180005eae  call    pcmLimiter_Reset
0x180005eb3  mov     rax, rbx
0x180005eb6  movaps  xmm7, [rsp+38h+var_18]
0x180005ebb  add     rsp, 30h
0x180005ebf  pop     rbx
0x180005ec0  retn
0x180005ec2  mov     rcx, rbx; Block
0x180005ec5  call    pcmLimiter_Destroy
0x180005eca  xor     eax, eax
0x180005ecc  jmp     short loc_180005EB6
```
