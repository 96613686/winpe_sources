# MocompAverage8x8_Daytona

- ea: `0x18000c474`
- end: `0x18000c4c7`
- name: `MocompAverage8x8_Daytona`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bbd4`
- `0x18000c1b8`
- `0x18000ca20`

## callees

- `0x18000c474`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x18000c4a7`
- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x18000c4a7`
- `mfperfhelper!__imp_ippiAverage8x8_8u_C1IR` at `0x18000c4b8`
- `mfperfhelper!__imp_ippiAverage8x8_8u_C1IR` at `0x18000c4b8`

## pseudocode

```c
__int64 __fastcall MocompAverage8x8_Daytona(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 result; // rax

  result = a6 + 1;
  if ( 7 * (int)result < a5 && a5 >= 8 )
  {
    ippiCopy8x8_8u_C1R(a1, a3, a4, a6);
    return ippiAverage8x8_8u_C1IR(a2, a3, a4, a6);
  }
  return result;
}

```

## disassembly

```asm
0x18000c474  push    rbx
0x18000c476  push    rbp
0x18000c477  push    rsi
0x18000c478  push    rdi
0x18000c479  sub     rsp, 28h
0x18000c47d  mov     ebx, [rsp+48h+arg_28]
0x18000c481  mov     rdi, r9
0x18000c484  mov     esi, r8d
0x18000c487  mov     rbp, rdx
0x18000c48a  lea     eax, [rbx+1]
0x18000c48d  imul    r10d, eax, 7
0x18000c491  cmp     r10d, [rsp+48h+arg_20]
0x18000c496  jnb     short loc_18000C4BE
0x18000c498  cmp     [rsp+48h+arg_20], 8
0x18000c49d  jb      short loc_18000C4BE
0x18000c49f  mov     r9d, ebx
0x18000c4a2  mov     r8, rdi
0x18000c4a5  mov     edx, esi
0x18000c4a7  call    cs:__imp_ippiCopy8x8_8u_C1R
0x18000c4ad  mov     r9d, ebx
0x18000c4b0  mov     r8, rdi
0x18000c4b3  mov     edx, esi
0x18000c4b5  mov     rcx, rbp
0x18000c4b8  call    cs:__imp_ippiAverage8x8_8u_C1IR
0x18000c4be  add     rsp, 28h
0x18000c4c2  pop     rdi
0x18000c4c3  pop     rsi
0x18000c4c4  pop     rbp
0x18000c4c5  pop     rbx
0x18000c4c6  retn
```
