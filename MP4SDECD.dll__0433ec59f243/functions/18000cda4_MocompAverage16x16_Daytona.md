# MocompAverage16x16_Daytona

- ea: `0x18000cda4`
- end: `0x18000ce07`
- name: `MocompAverage16x16_Daytona`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bbd4`
- `0x18000c1b8`
- `0x18000ca20`

## callees

- `0x18000cda4`

## import_xrefs

- `mfperfhelper!__imp_ippiAverage16x16_8u_C1IR` at `0x18000cdf1`
- `mfperfhelper!__imp_ippiAverage16x16_8u_C1IR` at `0x18000cdf1`
- `mfperfhelper!__imp_ippiCopy16x16_8u_C1R` at `0x18000cddd`
- `mfperfhelper!__imp_ippiCopy16x16_8u_C1R` at `0x18000cddd`

## pseudocode

```c
__int64 __fastcall MocompAverage16x16_Daytona(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 result; // rax

  result = a6 + 1;
  if ( 15 * (int)result < a5 && a5 >= 0x10 )
  {
    ippiCopy16x16_8u_C1R(a1, 16, a4, a6);
    return ippiAverage16x16_8u_C1IR(a2, 16, a4, a6);
  }
  return result;
}

```

## disassembly

```asm
0x18000cda4  mov     [rsp+arg_0], rbx
0x18000cda9  mov     [rsp+arg_8], rsi
0x18000cdae  push    rdi
0x18000cdaf  sub     rsp, 20h
0x18000cdb3  mov     ebx, [rsp+28h+arg_28]
0x18000cdb7  mov     rdi, r9
0x18000cdba  mov     rsi, rdx
0x18000cdbd  lea     eax, [rbx+1]
0x18000cdc0  imul    r8d, eax, 0Fh
0x18000cdc4  cmp     r8d, [rsp+28h+arg_20]
0x18000cdc9  jnb     short loc_18000CDF7
0x18000cdcb  cmp     [rsp+28h+arg_20], 10h
0x18000cdd0  jb      short loc_18000CDF7
0x18000cdd2  mov     r9d, ebx
0x18000cdd5  mov     r8, rdi
0x18000cdd8  mov     edx, 10h
0x18000cddd  call    cs:__imp_ippiCopy16x16_8u_C1R
0x18000cde3  mov     r9d, ebx
0x18000cde6  mov     r8, rdi
0x18000cde9  mov     edx, 10h
0x18000cdee  mov     rcx, rsi
0x18000cdf1  call    cs:__imp_ippiAverage16x16_8u_C1IR
0x18000cdf7  mov     rbx, [rsp+28h+arg_0]
0x18000cdfc  mov     rsi, [rsp+28h+arg_8]
0x18000ce01  add     rsp, 20h
0x18000ce05  pop     rdi
0x18000ce06  retn
```
