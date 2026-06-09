# UpdateDstMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d2c0`
- end: `0x18001d33d`
- name: `?UpdateDstMBYV12@@YAXPEAE00PEBE11JJJJ@Z`
- size: `125`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001d2c0`

## pseudocode

```c
void __fastcall UpdateDstMBYV12(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        const unsigned __int8 *a6,
        int a7,
        int a8,
        int a9,
        int a10)
{
  int v10; // esi
  __int128 v13; // xmm1

  v10 = 8;
  do
  {
    *(_OWORD *)a1 = *(_OWORD *)a4;
    v13 = *(_OWORD *)&a4[a7];
    a4 += 2 * a7;
    *(_OWORD *)&a1[a9] = v13;
    a1 += 2 * a9;
    *(_QWORD *)a2 = *(_QWORD *)a5;
    a5 += a8;
    a2 += a10;
    *(_QWORD *)a3 = *(_QWORD *)a6;
    a6 += a8;
    a3 += a10;
    --v10;
  }
  while ( v10 );
}

```

## disassembly

```asm
0x18001d2c0  push    rbx
0x18001d2c2  push    rbp
0x18001d2c3  push    rsi
0x18001d2c4  push    rdi
0x18001d2c5  push    r12
0x18001d2c7  push    r14
0x18001d2c9  push    r15
0x18001d2cb  movsxd  r14, [rsp+38h+arg_30]
0x18001d2d0  mov     esi, 8
0x18001d2d5  movsxd  r15, [rsp+38h+arg_40]
0x18001d2dd  movsxd  rbx, [rsp+38h+arg_38]
0x18001d2e2  movsxd  rdi, [rsp+38h+arg_48]
0x18001d2ea  mov     r10, [rsp+38h+arg_28]
0x18001d2ef  lea     rbp, [r14+r14]
0x18001d2f3  mov     r11, [rsp+38h+arg_20]
0x18001d2f8  lea     r12, [r15+r15]
0x18001d2fc  movups  xmm0, xmmword ptr [r9]
0x18001d300  movdqu  xmmword ptr [rcx], xmm0
0x18001d304  movups  xmm1, xmmword ptr [r14+r9]
0x18001d309  add     r9, rbp
0x18001d30c  movdqu  xmmword ptr [r15+rcx], xmm1
0x18001d312  mov     rax, [r11]
0x18001d315  add     rcx, r12
0x18001d318  mov     [rdx], rax
0x18001d31b  add     r11, rbx
0x18001d31e  mov     rax, [r10]
0x18001d321  add     rdx, rdi
0x18001d324  mov     [r8], rax
0x18001d327  add     r10, rbx
0x18001d32a  add     r8, rdi
0x18001d32d  sub     esi, 1
0x18001d330  jnz     short loc_18001D2FC
0x18001d332  pop     r15
0x18001d334  pop     r14
0x18001d336  pop     r12
0x18001d338  pop     rdi
0x18001d339  pop     rsi
0x18001d33a  pop     rbp
0x18001d33b  pop     rbx
0x18001d33c  retn
```
