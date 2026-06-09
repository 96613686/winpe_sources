# MocompAverageAddError16x16_Daytona

- ea: `0x18000d4f8`
- end: `0x18000d675`
- name: `MocompAverageAddError16x16_Daytona`
- size: `381`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bbd4`
- `0x18000ca20`

## callees

- `0x18000d4f8`

## import_xrefs

- `mfperfhelper!__imp_ippiMC8x8B_8u_C1` at `0x18000d577`
- `mfperfhelper!__imp_ippiMC8x8B_8u_C1` at `0x18000d5bf`
- `mfperfhelper!__imp_ippiMC8x8B_8u_C1` at `0x18000d614`
- `mfperfhelper!__imp_ippiMC8x8B_8u_C1` at `0x18000d662`
- `mfperfhelper!__imp_ippiMC8x8B_8u_C1` at `0x18000d577`
- `mfperfhelper!__imp_ippiMC8x8B_8u_C1` at `0x18000d5bf`
- `mfperfhelper!__imp_ippiMC8x8B_8u_C1` at `0x18000d614`
- `mfperfhelper!__imp_ippiMC8x8B_8u_C1` at `0x18000d662`

## pseudocode

```c
__int64 __fastcall MocompAverageAddError16x16_Daytona(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        __int64 a7)
{
  __int64 result; // rax
  __int64 v11; // rbx

  result = (unsigned int)(a6 + 1);
  if ( 15 * (int)result < a5 && a5 >= 0x10 )
  {
    ippiMC8x8B_8u_C1(a1, 16, 0, a2, 16, 0, a7, 16, a4, a6, 1);
    ippiMC8x8B_8u_C1(a1 + 8, 16, 0, a2 + 8, 16, 0, a7 + 256, 16, a4 + 8, a6, 1);
    v11 = (unsigned int)(8 * a6) + a4;
    ippiMC8x8B_8u_C1(a1 + 128, 16, 0, a2 + 128, 16, 0, a7 + 512, 16, v11, a6, 1);
    return ippiMC8x8B_8u_C1(a1 + 136, 16, 0, a2 + 136, 16, 0, a7 + 768, 16, v11 + 8, a6, 1);
  }
  return result;
}

```

## disassembly

```asm
0x18000d4f8  mov     r11, rsp
0x18000d4fb  push    rbx
0x18000d4fc  push    rbp
0x18000d4fd  push    rsi
0x18000d4fe  push    rdi
0x18000d4ff  push    r13
0x18000d501  push    r14
0x18000d503  sub     rsp, 68h
0x18000d507  mov     r14d, [rsp+98h+arg_28]
0x18000d50f  mov     rbx, r9
0x18000d512  mov     rdi, rdx
0x18000d515  mov     rsi, rcx
0x18000d518  lea     eax, [r14+1]
0x18000d51c  imul    r8d, eax, 0Fh
0x18000d520  cmp     r8d, [rsp+98h+arg_20]
0x18000d528  jnb     loc_18000D668
0x18000d52e  mov     r13d, 10h
0x18000d534  cmp     [rsp+98h+arg_20], r13d
0x18000d53c  jb      loc_18000D668
0x18000d542  mov     rbp, [rsp+98h+arg_30]
0x18000d54a  mov     r9, rdx
0x18000d54d  mov     [rsp+98h+var_48], 1
0x18000d555  xor     r8d, r8d
0x18000d558  mov     [r11-50h], r14d
0x18000d55c  mov     edx, r13d
0x18000d55f  mov     [r11-58h], rbx
0x18000d563  mov     [r11-60h], r13d
0x18000d567  mov     [r11-68h], rbp
0x18000d56b  mov     [rsp+98h+var_70], 0
0x18000d573  mov     [r11-78h], r13d
0x18000d577  call    cs:__imp_ippiMC8x8B_8u_C1
0x18000d57d  mov     [rsp+98h+var_48], 1
0x18000d585  lea     rdx, [rbp+100h]
0x18000d58c  mov     [rsp+98h+var_50], r14d
0x18000d591  lea     rax, [rbx+8]
0x18000d595  mov     [rsp+98h+var_58], rax
0x18000d59a  lea     r9, [rdi+8]
0x18000d59e  mov     [rsp+98h+var_60], r13d
0x18000d5a3  lea     rcx, [rsi+8]
0x18000d5a7  mov     [rsp+98h+var_68], rdx
0x18000d5ac  xor     r8d, r8d
0x18000d5af  mov     [rsp+98h+var_70], 0
0x18000d5b7  mov     edx, r13d
0x18000d5ba  mov     [rsp+98h+var_78], r13d
0x18000d5bf  call    cs:__imp_ippiMC8x8B_8u_C1
0x18000d5c5  mov     [rsp+98h+var_48], 1
0x18000d5cd  lea     ecx, ds:0[r14*8]
0x18000d5d5  mov     [rsp+98h+var_50], r14d
0x18000d5da  lea     rax, [rbp+200h]
0x18000d5e1  add     rbx, rcx
0x18000d5e4  lea     r9, [rdi+80h]
0x18000d5eb  mov     [rsp+98h+var_58], rbx
0x18000d5f0  lea     rcx, [rsi+80h]
0x18000d5f7  mov     [rsp+98h+var_60], r13d
0x18000d5fc  xor     r8d, r8d
0x18000d5ff  mov     [rsp+98h+var_68], rax
0x18000d604  mov     edx, r13d
0x18000d607  mov     [rsp+98h+var_70], 0
0x18000d60f  mov     [rsp+98h+var_78], r13d
0x18000d614  call    cs:__imp_ippiMC8x8B_8u_C1
0x18000d61a  mov     [rsp+98h+var_48], 1
0x18000d622  lea     r8, [rbp+300h]
0x18000d629  mov     [rsp+98h+var_50], r14d
0x18000d62e  lea     rax, [rbx+8]
0x18000d632  mov     [rsp+98h+var_58], rax
0x18000d637  lea     r9, [rdi+88h]
0x18000d63e  mov     [rsp+98h+var_60], r13d
0x18000d643  lea     rcx, [rsi+88h]
0x18000d64a  mov     [rsp+98h+var_68], r8
0x18000d64f  mov     edx, r13d
0x18000d652  mov     [rsp+98h+var_70], 0
0x18000d65a  xor     r8d, r8d
0x18000d65d  mov     [rsp+98h+var_78], r13d
0x18000d662  call    cs:__imp_ippiMC8x8B_8u_C1
0x18000d668  add     rsp, 68h
0x18000d66c  pop     r14
0x18000d66e  pop     r13
0x18000d670  pop     rdi
0x18000d671  pop     rsi
0x18000d672  pop     rbp
0x18000d673  pop     rbx
0x18000d674  retn
```
