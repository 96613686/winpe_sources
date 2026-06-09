# DeringMB(uchar *,uchar *,uchar *,long,long,long)

- ea: `0x180019b90`
- end: `0x180019d2c`
- name: `?DeringMB@@YAXPEAE00JJJ@Z`
- size: `412`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002aac0`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180019cde`
- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180019cf0`
- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180019cde`
- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180019cf0`
- `mfperfhelper!__imp_ippiCopy16x16_8u_C1R` at `0x180019d03`
- `mfperfhelper!__imp_ippiCopy16x16_8u_C1R` at `0x180019d03`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019c16`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019c36`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019c66`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019c89`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019cad`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019ccb`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019c16`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019c36`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019c66`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019c89`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019cad`
- `mfperfhelper!__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R` at `0x180019ccb`
- `mfperfhelper!__imp_ippiFilterDeringingThreshold_MPEG4_8u_P3R` at `0x180019bf2`
- `mfperfhelper!__imp_ippiFilterDeringingThreshold_MPEG4_8u_P3R` at `0x180019bf2`

## pseudocode

```c
void __fastcall DeringMB(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned int a5,
        unsigned int a6)
{
  _DWORD v10[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[64]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v12[64]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v13[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v14[120]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v15[8]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v16[120]; // [rsp+168h] [rbp+68h] BYREF

  ippiFilterDeringingThreshold_MPEG4_8u_P3R(a1, a5, a2, a6, a3, a6, v10);
  ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R(a1, a5, v13, 16, a4, v10[0]);
  ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R(a1 + 8, a5, v14, 16, a4, v10[1]);
  ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R(&a1[8 * a5], a5, v15, 16, a4, v10[2]);
  ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R(&a1[8 * a5 + 8], a5, v16, 16, a4, v10[3]);
  ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R(a2, a6, v11, 8, a4, v10[4]);
  ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R(a3, a6, v12, 8, a4, v10[5]);
  ippiCopy8x8_8u_C1R(v11, 8, a2, a6);
  ippiCopy8x8_8u_C1R(v12, 8, a3, a6);
  ippiCopy16x16_8u_C1R(v13, 16, a1, a5);
}

```

## disassembly

```asm
0x180019b90  push    rbp
0x180019b92  push    rbx
0x180019b93  push    rsi
0x180019b94  push    rdi
0x180019b95  push    r12
0x180019b97  push    r13
0x180019b99  push    r14
0x180019b9b  push    r15
0x180019b9d  lea     rbp, [rsp-0F8h]
0x180019ba5  sub     rsp, 1F8h
0x180019bac  mov     rax, cs:__security_cookie
0x180019bb3  xor     rax, rsp
0x180019bb6  mov     [rbp+130h+var_50], rax
0x180019bbd  mov     edi, [rbp+130h+arg_28]
0x180019bc3  lea     rax, [rsp+230h+var_1F0]
0x180019bc8  mov     r15d, [rbp+130h+arg_20]
0x180019bcf  mov     r12, r8
0x180019bd2  mov     [rsp+230h+var_200], rax
0x180019bd7  mov     esi, r9d
0x180019bda  mov     r14, rdx
0x180019bdd  mov     [rsp+230h+var_208], edi
0x180019be1  mov     [rsp+230h+var_210], r8
0x180019be6  mov     r9d, edi
0x180019be9  mov     r8, rdx
0x180019bec  mov     r13, rcx
0x180019bef  mov     edx, r15d
0x180019bf2  call    cs:__imp_ippiFilterDeringingThreshold_MPEG4_8u_P3R
0x180019bf8  mov     eax, [rsp+230h+var_1F0]
0x180019bfc  lea     r8, [rbp+130h+var_150]
0x180019c00  mov     [rsp+230h+var_208], eax
0x180019c04  mov     ebx, 10h
0x180019c09  mov     r9d, ebx
0x180019c0c  mov     dword ptr [rsp+230h+var_210], esi
0x180019c10  mov     edx, r15d
0x180019c13  mov     rcx, r13
0x180019c16  call    cs:__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R
0x180019c1c  mov     eax, [rsp+230h+var_1EC]
0x180019c20  lea     rcx, [r13+8]
0x180019c24  mov     [rsp+230h+var_208], eax
0x180019c28  lea     r8, [rbp+130h+var_148]
0x180019c2c  mov     r9d, ebx
0x180019c2f  mov     dword ptr [rsp+230h+var_210], esi
0x180019c33  mov     edx, r15d
0x180019c36  call    cs:__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R
0x180019c3c  lea     eax, ds:0[r15*8]
0x180019c44  mov     r9d, 10h
0x180019c4a  movsxd  rbx, eax
0x180019c4d  lea     r8, [rbp+130h+var_D0]
0x180019c51  mov     eax, [rsp+230h+var_1E8]
0x180019c55  add     rbx, r13
0x180019c58  mov     [rsp+230h+var_208], eax
0x180019c5c  mov     rcx, rbx
0x180019c5f  mov     edx, r15d
0x180019c62  mov     dword ptr [rsp+230h+var_210], esi
0x180019c66  call    cs:__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R
0x180019c6c  mov     eax, [rsp+230h+var_1E4]
0x180019c70  lea     rcx, [rbx+8]
0x180019c74  mov     [rsp+230h+var_208], eax
0x180019c78  lea     r8, [rbp+130h+var_C8]
0x180019c7c  mov     r9d, 10h
0x180019c82  mov     dword ptr [rsp+230h+var_210], esi
0x180019c86  mov     edx, r15d
0x180019c89  call    cs:__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R
0x180019c8f  mov     eax, [rsp+230h+var_1E0]
0x180019c93  lea     r8, [rsp+230h+var_1D0]
0x180019c98  mov     [rsp+230h+var_208], eax
0x180019c9c  mov     ebx, 8
0x180019ca1  mov     r9d, ebx
0x180019ca4  mov     dword ptr [rsp+230h+var_210], esi
0x180019ca8  mov     edx, edi
0x180019caa  mov     rcx, r14
0x180019cad  call    cs:__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R
0x180019cb3  mov     eax, [rsp+230h+var_1DC]
0x180019cb7  lea     r8, [rbp+130h+var_190]
0x180019cbb  mov     [rsp+230h+var_208], eax
0x180019cbf  mov     r9d, ebx
0x180019cc2  mov     edx, edi
0x180019cc4  mov     dword ptr [rsp+230h+var_210], esi
0x180019cc8  mov     rcx, r12
0x180019ccb  call    cs:__imp_ippiFilterDeringingSmooth8x8_MPEG4_8u_C1R
0x180019cd1  mov     r9d, edi
0x180019cd4  lea     rcx, [rsp+230h+var_1D0]
0x180019cd9  mov     r8, r14
0x180019cdc  mov     edx, ebx
0x180019cde  call    cs:__imp_ippiCopy8x8_8u_C1R
0x180019ce4  mov     r9d, edi
0x180019ce7  lea     rcx, [rbp+130h+var_190]
0x180019ceb  mov     r8, r12
0x180019cee  mov     edx, ebx
0x180019cf0  call    cs:__imp_ippiCopy8x8_8u_C1R
0x180019cf6  mov     r9d, r15d
0x180019cf9  lea     edx, [rbx+8]
0x180019cfc  mov     r8, r13
0x180019cff  lea     rcx, [rbp+130h+var_150]
0x180019d03  call    cs:__imp_ippiCopy16x16_8u_C1R
0x180019d09  mov     rcx, [rbp+130h+var_50]
0x180019d10  xor     rcx, rsp; StackCookie
0x180019d13  call    __security_check_cookie
0x180019d18  add     rsp, 1F8h
0x180019d1f  pop     r15
0x180019d21  pop     r14
0x180019d23  pop     r13
0x180019d25  pop     r12
0x180019d27  pop     rdi
0x180019d28  pop     rsi
0x180019d29  pop     rbx
0x180019d2a  pop     rbp
0x180019d2b  retn
```
