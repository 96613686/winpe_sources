# g_MotionCompZeroMotion_Daytona

- ea: `0x1800199f0`
- end: `0x180019a7f`
- name: `g_MotionCompZeroMotion_Daytona`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800199f0`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180019a56`
- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180019a69`
- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180019a56`
- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180019a69`
- `mfperfhelper!__imp_ippiCopy16x16_8u_C1R` at `0x180019a43`
- `mfperfhelper!__imp_ippiCopy16x16_8u_C1R` at `0x180019a43`

## pseudocode

```c
__int64 __fastcall g_MotionCompZeroMotion_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        unsigned int a9,
        unsigned int a10)
{
  __int64 result; // rax

  result = a9 + 1;
  if ( 15 * (int)result < a2 && a2 >= 0x10 )
  {
    result = a5;
    if ( a5 >= 8 && 7 * (a10 + 1) < a5 )
    {
      ippiCopy16x16_8u_C1R(a6, a9, a1, a9);
      ippiCopy8x8_8u_C1R(a7, a10, a3, a10);
      return ippiCopy8x8_8u_C1R(a8, a10, a4, a10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800199f0  mov     [rsp+arg_8], rbx
0x1800199f5  push    rdi
0x1800199f6  sub     rsp, 20h
0x1800199fa  mov     r11d, [rsp+28h+arg_40]
0x1800199ff  mov     rbx, r9
0x180019a02  mov     rdi, r8
0x180019a05  lea     eax, [r11+1]
0x180019a09  imul    r10d, eax, 0Fh
0x180019a0d  cmp     r10d, edx
0x180019a10  jnb     short loc_180019A74
0x180019a12  cmp     edx, 10h
0x180019a15  jb      short loc_180019A74
0x180019a17  mov     [rsp+28h+arg_0], rsi
0x180019a1c  mov     esi, [rsp+28h+arg_48]
0x180019a20  lea     eax, [rsi+1]
0x180019a23  imul    r8d, eax, 7
0x180019a27  mov     eax, [rsp+28h+arg_20]
0x180019a2b  cmp     eax, 8
0x180019a2e  jb      short loc_180019A6F
0x180019a30  cmp     r8d, eax
0x180019a33  jnb     short loc_180019A6F
0x180019a35  mov     r8, rcx
0x180019a38  mov     r9d, r11d
0x180019a3b  mov     rcx, [rsp+28h+arg_28]
0x180019a40  mov     edx, r11d
0x180019a43  call    cs:__imp_ippiCopy16x16_8u_C1R
0x180019a49  mov     rcx, [rsp+28h+arg_30]
0x180019a4e  mov     r9d, esi
0x180019a51  mov     r8, rdi
0x180019a54  mov     edx, esi
0x180019a56  call    cs:__imp_ippiCopy8x8_8u_C1R
0x180019a5c  mov     rcx, [rsp+28h+arg_38]
0x180019a61  mov     r9d, esi
0x180019a64  mov     r8, rbx
0x180019a67  mov     edx, esi
0x180019a69  call    cs:__imp_ippiCopy8x8_8u_C1R
0x180019a6f  mov     rsi, [rsp+28h+arg_0]
0x180019a74  mov     rbx, [rsp+28h+arg_8]
0x180019a79  add     rsp, 20h
0x180019a7d  pop     rdi
0x180019a7e  retn
```
